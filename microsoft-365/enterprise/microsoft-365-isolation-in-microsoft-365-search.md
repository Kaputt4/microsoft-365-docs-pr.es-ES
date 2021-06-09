---
title: Aislamiento de inquilino en Búsqueda de Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: En este artículo, busque una explicación de cómo funciona el aislamiento del espacio empresarial para separar los datos del espacio empresarial en Microsoft 365 búsqueda.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3416afdeceaa7000b516ec89b4a2a1e59d8708d0
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332405"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a>Aislamiento de inquilino en Búsqueda de Microsoft 365

SharePoint La búsqueda en línea usa un modelo de separación de inquilinos que equilibra la eficacia de las estructuras de datos compartidas con la protección contra la pérdida de información entre inquilinos. Con este modelo, evitamos que las características de búsqueda:

- Devolver resultados de consulta que contienen documentos de otros inquilinos
- Exponer información suficiente en los resultados de consulta que un usuario cualificado podría deducir información sobre otros inquilinos
- Mostrar el esquema o la configuración de otro inquilino
- La combinación de información de procesamiento de análisis entre inquilinos o almacén da como resultado un inquilino incorrecto
- Uso de entradas de diccionario de otro inquilino

Para cada tipo de datos de inquilino, usamos una o más capas de protección en el código para evitar la pérdida accidental de información. Los datos más críticos tienen la mayoría de las capas de protección para asegurarse de que un solo defecto no da como resultado una fuga de información real o percibida.

## <a name="tenant-separation-for-the-search-index"></a>Separación de inquilinos para el índice de búsqueda

El índice de búsqueda se almacena en el disco en los servidores que hospedan los componentes de índice y los inquilinos comparten los archivos de índice. Los documentos indizados de un inquilino solo son visibles para las consultas de ese espacio empresarial. Tres mecanismos independientes evitan la filtración de información:

- Filtrado de identificadores de inquilino
- Prefijo de término de identificador de inquilino
- Comprobaciones de ACL

Los tres mecanismos tendrían que fallar para que Search devuelva documentos al inquilino incorrecto.

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>Filtrado de id. de inquilino y prefijo de término de identificador de inquilino

La búsqueda prefida todos los términos indizados en el índice de texto completo con el identificador de inquilino. Por ejemplo, cuando el término "*foo*" se indiza para un inquilino con un identificador de "*123*", la entrada en el índice de texto completo es "*123foo.*"

Cada consulta se convierte para incluir el identificador de inquilino mediante un proceso denominado filtrado de identificadores de inquilino. Por ejemplo, la consulta "*foo*" se convierte en "<*guid>.* *foo* AND *tenantID*:<*guid*>", donde <*guid*> representa al inquilino que realiza la consulta. Esta conversión de consulta se produce en cada nodo de índice y ni la consulta ni el procesamiento de contenido pueden influir en él. Dado que el identificador de inquilino se agrega a todas las consultas, la frecuencia de un término en otros inquilinos no se puede deducir si se busca la mejor clasificación de coincidencias en un inquilino.

El prefijo de término de identificador de inquilino solo se produce en el índice de texto completo. Las búsquedas con campo, como "*title:foo",* van a un índice de búsqueda sintética donde los términos no están precedido por el identificador de inquilino. En su lugar, las búsquedas con campos tienen el prefijo con el nombre del campo. Por ejemplo, la consulta "*title:foo*" se convierte en "*fields.title:foo AND fields.tenantID*:<*guid*>." Dado que la frecuencia de un término no influye en la clasificación de aciertos en el índice de búsqueda sintética, no es necesario separar el espacio empresarial por prefijo de término. Para una búsqueda con campo como "*title:foo",* la separación de contenido del espacio empresarial depende del filtrado de identificadores de inquilino por conversión de consulta.

## <a name="document-access-control-list-checks"></a>Comprobaciones de listas de control de acceso a documentos

La búsqueda controla el acceso a documentos a través de ACL que se guardan en el índice de búsqueda. Cada elemento se indiza con un conjunto de términos en un campo de ACL especial. El campo ACL contiene un término por grupo o usuario que puede ver el documento. Cada consulta se aumenta con una lista de términos de entrada de control de acceso (ACE), uno para cada grupo al que pertenece el usuario autenticado.

Por ejemplo, una consulta como "<*guid>.* *foo AND tenantID*:<*guid>"* se convierte en: "<*guid>.* *foo AND tenantID*:<*guid* >  *AND* (*docACL:* < *ace1* >  *OR docACL*:<*ace2* >  *OR docACL*:<*ace3* >  *...*)"

Dado que los identificadores de usuario y grupo y, por lo tanto, las ACE son únicos, esto proporciona un nivel adicional de seguridad entre inquilinos para documentos que solo son visibles para algunos usuarios. El mismo es el caso de la ACE especial "Todos excepto los usuarios externos" que concede acceso a usuarios normales en el espacio empresarial. Pero dado que las ACE para "Todos" son las mismas para todos los inquilinos, la separación de inquilinos para documentos públicos depende del filtrado de identificadores de inquilino. También se admiten LAS ACE de denegación. El aumento de consulta agrega una cláusula que quita un documento del resultado cuando hay una coincidencia con una ACE de denegación.

En Exchange Online búsqueda, el índice se particiona en el identificador de buzón de correo de los buzones de un usuario individual en lugar del identificador de inquilino (id. de suscripción) como en SharePoint Online. El mecanismo de particionamiento es el mismo que SharePoint online, pero no hay ningún filtrado de ACL.
