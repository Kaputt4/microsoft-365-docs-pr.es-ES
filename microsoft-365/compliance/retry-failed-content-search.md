---
title: Reintentar una búsqueda de contenido para resolver un error de ubicación de contenido
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Durante una investigación, puede usar el botón Reintentar para resolver las búsquedas de contenido que tienen errores de ubicación de contenido.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b64fccc03cec5963459981f2f826eab01fc70203
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67817871"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>Reintentar una búsqueda de contenido para resolver un error de ubicación de contenido

Al usar búsqueda de contenido en el centro de seguridad y cumplimiento para buscar un gran número de buzones de correo, puede obtener errores de búsqueda similares al error:

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

Estos errores (con códigos de error de CS001-002, CS003-002, CS008-009, CS012-002 y otros errores del formulario CS0XX-0XX) indican que búsqueda de contenido no pudo buscar ubicaciones de contenido específicas; en este ejemplo, no se buscaron dos buzones. Estos errores se muestran en la página desplegable detalles de estado de la búsqueda de contenido.

## <a name="cause-of-content-location-errors"></a>Causa de errores de ubicación de contenido

Al buscar un gran número de buzones, la búsqueda se distribuye entre miles de servidores en un centro de datos de Microsoft. En cualquier momento, los servidores específicos podrían estar en estado de reinicio o en proceso de conmutación por error a copias redundantes. En cualquiera de estos casos, se agotará el tiempo de espera de la solicitud de búsqueda de contenido para recuperar datos. En el ejemplo anterior, los errores de los buzones con errores eran el resultado del tiempo de espera de la búsqueda.

## <a name="resolving-content-location-errors"></a>Resolución de errores de ubicación de contenido

Al reiniciar la búsqueda, a menudo se producirán errores similares en distintos servidores. En lugar de reiniciar la búsqueda, haga clic en el botón **Reintentar** que se muestra en la parte superior de la página de resultados de la búsqueda.

![Haga clic en el botón Reintentar para resolver errores de ubicación de contenido.](../media/retrycontentsearch3.png)

Esto dará lugar a que vuelva a intentar la búsqueda solo de los buzones con errores. Al reintentar la búsqueda, se conservan los demás resultados que se devolvieron correctamente.

## <a name="tips-to-avoid-content-location-errors"></a>Sugerencias para evitar errores de ubicación de contenido

Estas son algunas causas adicionales de errores de ubicación de contenido y algunas sugerencias que le ayudarán a evitarlos al buscar un gran número de buzones.

- El buzón que se busca puede estar ocupado debido a la actividad del usuario. En este caso, el servicio de búsqueda podría limitarse a sí mismo para evitar que el buzón deje de estar disponible. Para evitarlo, intente ejecutar búsquedas durante horas no laborables.

- Es posible que la consulta de búsqueda esté recuperando demasiado contenido del buzón. Si es posible, intente restringir el ámbito de la búsqueda mediante palabras clave, intervalos de fechas y condiciones de búsqueda.

- Demasiadas palabras clave o frases de palabras clave al crear una consulta de búsqueda mediante la [lista de palabras clave](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches). Al ejecutar una consulta de búsqueda que usa la lista de palabras clave, el servicio ejecuta básicamente una búsqueda independiente para cada fila de la lista de palabras clave para que se puedan generar estadísticas. Si usa la lista de palabras clave en consultas de búsqueda, minimice el número de filas de la lista de palabras clave o divida las palabras clave numéricas en listas más pequeñas y cree una búsqueda diferente para cada lista de palabras clave.

  > [!NOTE]
  > Para ayudar a reducir los problemas causados por listas de palabras clave grandes, ahora está limitado a un máximo de 20 filas en la lista de palabras clave de una consulta de búsqueda.

- Se están realizando demasiadas búsquedas en el mismo buzón al mismo tiempo. Si es posible, intente ejecutar una búsqueda a la vez en cualquier buzón de correo.

- Buscar demasiados buzones en una sola búsqueda. La probabilidad de errores de ubicación de contenido aumenta al buscar un gran número de buzones. Si es posible, intente ejecutar varias búsquedas para que cada búsqueda incluya un subconjunto de buzones de su organización.

- El mantenimiento necesario se realiza en el buzón de correo. Aunque esta causa probablemente se produzca con poca frecuencia, espere un poco después de recibir el error de ubicación de contenido y vuelva a intentar la búsqueda.
