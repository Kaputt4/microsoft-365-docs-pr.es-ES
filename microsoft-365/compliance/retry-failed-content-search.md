---
title: Reintentar una búsqueda de contenido para resolver un error de ubicación de contenido
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Durante una investigación, puede usar el botón Reintentar para resolver las búsquedas de contenido que tienen errores de ubicación de contenido.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fb85a882ef111aa38a73dbe155a9ad0ef57dd3de
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311825"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>Reintentar una búsqueda de contenido para resolver un error de ubicación de contenido

Al usar la búsqueda de contenido en el Centro de seguridad y cumplimiento para buscar en un gran número de buzones, puede obtener errores de búsqueda similares al error:

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

Estos errores (con códigos de error de CS001-002, CS003-002, CS008-009, CS012-002 y otros errores del formulario CS0XX-0XX) indican que la búsqueda de contenido no pudo buscar ubicaciones de contenido específicas; en este ejemplo, no se buscaron dos buzones. Estos errores se muestran en la página desplegable de detalles de estado de la búsqueda de contenido.

## <a name="cause-of-content-location-errors"></a>Causa de errores de ubicación de contenido

Al buscar un gran número de buzones, la búsqueda se distribuye entre miles de servidores en un centro de datos de Microsoft. En cualquier momento, servidores específicos podrían estar en estado de reinicio o en el proceso de con error a copias redundantes. En cualquiera de estos casos, la solicitud de búsqueda de contenido para recuperar datos dará tiempo de espera. En el ejemplo anterior, los errores de los buzones que fallaron fueron el resultado del tiempo de ejecución de la búsqueda.

## <a name="resolving-content-location-errors"></a>Resolución de errores de ubicación de contenido

Reiniciar la búsqueda suele provocar errores similares en diferentes servidores. En lugar de reiniciar la búsqueda, haga clic en el **botón Reintentar** que se muestra en la parte superior de la página de resultados de búsqueda.

![Haga clic en el botón Reintentar para resolver errores de ubicación de contenido](../media/retrycontentsearch3.png)

Esto dará como resultado reintentar la búsqueda solo para los buzones que han fallado. Al reintentar la búsqueda, se conservan los demás resultados que se devolvieron correctamente.

## <a name="tips-to-avoid-content-location-errors"></a>Sugerencias evitar errores de ubicación de contenido

Estas son algunas causas adicionales de errores de ubicación de contenido y algunas sugerencias para ayudarle a evitarlos al buscar grandes cantidades de buzones.

- El buzón que se está buscando puede estar ocupado debido a la actividad del usuario. En este caso, el servicio de búsqueda puede limitarse a sí mismo para evitar que el buzón no esté disponible. Para evitar esto, intente ejecutar búsquedas durante el horario no comercial.

- Es posible que la consulta de búsqueda recupere demasiado contenido del buzón. Si es posible, intente restringir el ámbito de la búsqueda mediante palabras clave, intervalos de fechas y condiciones de búsqueda.

- Demasiadas palabras clave o frases de palabras clave al crear una consulta de búsqueda con la lista [de palabras clave](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches). Cuando se ejecuta una consulta de búsqueda que usa la lista de palabras clave, el servicio ejecuta básicamente una búsqueda independiente para cada fila de la lista de palabras clave para que se puedan generar estadísticas. Si usa la lista de palabras clave en las consultas de búsqueda, minimice el número de filas de la lista de palabras clave o divida las palabras clave de número en listas más pequeñas y cree una búsqueda diferente para cada lista de palabras clave.

  > [!NOTE]
  > Para ayudar a reducir los problemas causados por listas de palabras clave grandes, ahora está limitado a un máximo de 20 filas en la lista de palabras clave de una consulta de búsqueda.

- Se están realizando demasiadas búsquedas en el mismo buzón al mismo tiempo. Si es posible, intente ejecutar una búsqueda a la vez en cualquier buzón.

- Buscar demasiados buzones en una sola búsqueda. La probabilidad de errores de ubicación de contenido aumenta al buscar un gran número de buzones. Si es posible, intente ejecutar varias búsquedas para que cada búsqueda incluya un subconjunto de buzones en su organización.

- Se está realizando el mantenimiento necesario en el buzón. Aunque esta causa probablemente se produzca con poca frecuencia, espere un poco después de recibir el error de ubicación de contenido y vuelva a intentar la búsqueda.
