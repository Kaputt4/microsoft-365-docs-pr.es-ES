---
title: Crear etiquetas de retención para excepciones
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Instrucciones para crear etiquetas de retención para excepciones a las directivas de retención para la administración del ciclo de vida de los datos, de modo que pueda conservar lo que necesita y eliminar lo que no.
ms.openlocfilehash: ca78c4df6decaf71bfddd899ac13afaa9ada5df6
ms.sourcegitcommit: 702fba4b6e6210bb7933cdbff0ad72426fcb9ef2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2022
ms.locfileid: "67336230"
---
# <a name="create-retention-labels-for-exceptions-to-your-retention-policies"></a>Crear etiquetas de retención para excepciones a las directivas de retención

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Como parte de la estrategia de gobernanza de datos para conservar lo que necesita y eliminar lo que no, es posible que tenga que crear algunas etiquetas de retención para los elementos que necesitan excepciones a las directivas de retención.

Mientras que las directivas de retención se aplican automáticamente a todos los elementos en el nivel de contenedor (como sitios de SharePoint, buzones de usuario, etc.), las etiquetas de retención se aplican a elementos individuales, como un documento de SharePoint o un mensaje de correo electrónico.

Asegúrese de comprender los [principios de retención](retention.md#the-principles-of-retention-or-what-takes-precedence) antes de usar etiquetas de retención para complementar una directiva de retención para elementos específicos de SharePoint, OneDrive o Exchange. Normalmente, usará etiquetas de retención para conservar elementos específicos durante más tiempo que una directiva de retención aplicada, pero también se pueden usar para invalidar la eliminación automática al final del período de retención o aplicar un período de eliminación diferente.

Por ejemplo: la mayoría del contenido de los sitios SharePoint debe conservarse durante tres años, lo que está cubierto por una directiva de retención. Pero tiene algunos documentos del contrato que deben conservarse durante siete años. Estas excepciones se pueden solucionar con etiquetas de retención. Después de asignar la directiva de retención a todos los sitios de SharePoint, aplique las etiquetas de retención a los documentos del contrato. Todos los elementos de SharePoint se conservarán durante tres años y solo los documentos del contrato se conservarán durante siete años.

Para obtener más ejemplos de cómo se pueden usar las etiquetas de retención como excepciones a las directivas de retención, vea [Combinación de directivas de retención y etiquetas de retención](retention.md#combining-retention-policies-and-retention-labels).

Las etiquetas de retención también admiten más funcionalidades que las directivas de retención. Para obtener más información, vea [Comparar las capacidades de las directivas de retención y las etiquetas de retención](retention.md#compare-capabilities-for-retention-policies-and-retention-labels).

Use la siguiente información para ayudarle a crear etiquetas de retención para complementar las directivas de retención como parte de la estrategia de administración del ciclo de vida de los datos.

> [!NOTE]
> Cree etiquetas de retención desde la solución de **Administración de registros** en lugar de la **Administración del ciclo de vida de los datos** si necesita usar etiquetas de retención para administrar elementos de alto valor para los requisitos de mantenimiento de registros empresariales, legales o reglamentarios. Por ejemplo, quiere usar la retención basada en eventos o la revisión para eliminación. Para obtener instrucciones, vea [Usar el plan de archivos para crear y administrar etiquetas de retención](file-plan-manager.md).

## <a name="before-you-begin"></a>Antes de empezar

El administrador global de su organización tiene permisos totales para crear y modificar etiquetas de retención y las directivas de las mismas. Si no inicia sesión como administrador global, consulte [Permisos para directivas de retención y etiquetas de retención](get-started-with-data-lifecycle-management.md#permissions-for-retention-policies-and-retention-labels).

## <a name="how-to-create-retention-labels-for-data-lifecycle-management"></a>Creación de etiquetas de retención para la administración del ciclo de vida de los datos

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/), vaya a: Administración **del ciclo de vida** >  de los datos **de soluciones** >  pestaña **Etiquetas** de **Microsoft 365** >  > + **Crear una etiqueta**
    
    ¿No ve inmediatamente la solución **Administración del ciclo de vida de los datos**? Primero seleccione **Mostrar todo**. 

2. Siga las indicaciones para crear la etiqueta de retención. Tenga cuidado con el nombre que elija, ya que no se puede cambiar después de guardar la etiqueta.
    
    Para obtener más información sobre la configuración de retención, consulte [Configuración para conservar y eliminar contenido](retention-settings.md#settings-for-retaining-and-deleting-content).

3. Después de crear la etiqueta y ver las opciones para publicar la etiqueta, aplicar la etiqueta automáticamente o simplemente guardar la etiqueta: seleccione **Solo guardar la etiqueta por ahora** y después seleccione **Hecho**.

4. Repita estos pasos para crear más etiquetas de retención que necesite para diferentes configuraciones de retención.

Para editar una etiqueta existente, selecciónela y, a continuación, seleccione la opción **Editar etiqueta** para iniciar la configuración Editar etiqueta de retención que le permite cambiar las descripciones de las etiquetas y cualquier configuración elegible.

La mayoría de las opciones de configuración no se pueden cambiar después de crear y guardar la etiqueta, entre las que se incluyen:
- El nombre de la etiqueta de retención y la configuración de retención, excepto el período de retención. Sin embargo, no se puede cambiar el período de retención cuando el período de retención se basa en cuándo se etiquetaron los elementos.

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha creado etiquetas de retención, están listas para agregarse a los elementos publicando las etiquetas o aplicándolas automáticamente:
- [Publicar etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)
- [Aplicar una etiqueta de retención automáticamente al contenido](apply-retention-labels-automatically.md)
