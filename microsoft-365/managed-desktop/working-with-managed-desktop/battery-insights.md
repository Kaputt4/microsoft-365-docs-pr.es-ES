---
title: Información sobre las baterías
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f339fc98ea94c291c533045e9906f626f4b74e2a
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529844"
---
# <a name="battery-insights"></a>Información sobre las baterías
Esta vista proporciona métricas de uso de energía, batería y aplicaciones para los dispositivos de Escritorio administrado de Microsoft. Para estos fines, una aplicación se considera "en uso" si se está ejecutando y en foco.

Para ver los datos de uso, selecciona la **pestaña** Batería.

![Panel de batería: duración de la batería pronosticada por modelo de dispositivo en la parte superior izquierda, consumidores de energía superiores (por aplicación) en la parte superior derecha, tabla insights en la parte inferior. Vínculo de documentación en la parte superior derecha.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>Duración de la batería pronosticada

En el **área de duración prevista** de la batería, proporcionamos las previsiones para la duración prevista de la batería de los dispositivos, organizadas por modelo de dispositivo.

> [!NOTE]
> Estos datos se derivan del uso de energía de <em></em> muestreo, el tiempo de uso y la capacidad de la batería de una selección aleatoria de los dispositivos de la implementación de Escritorio administrado de Microsoft que también informan de los datos.

La tabla proporciona la duración de la batería pronosticada (en horas), la duración media de la batería para los mismos modelos en otras implementaciones de Escritorio administrado de Microsoft y el número de dispositivos que informan de estos datos en su entorno. Ordene los datos seleccionando los encabezados de columna.



## <a name="top-energy-consumers"></a>Principales consumidores de energía

En el **área de consumidores** principales de energía, encontrarás las aplicaciones de tu entorno que consumen la mayor cantidad de energía en milisegundos-hora (mWh). Las aplicaciones que se muestran son por dispositivo específico, que seleccionas en la sección **Duración** de la batería previsto a la izquierda. Por ejemplo, para ver el consumo por aplicación de los dispositivos Microsoft Surface Book 2, selecciona esa fila en el área de duración de la batería. Si no seleccionas ningún modelo, los datos de consumo de aplicaciones que se muestran son para todas las aplicaciones para las que tenemos datos de forma colectiva.

 Para cada aplicación, los segmentos de colores muestran la distribución del uso de energía de la aplicación entre estas categorías:

- CPU
- Visualización
- Red
- Otros

"Otros" podría incluir el consumo de energía por parte de una variedad de fuentes, como la actividad de disco, el uso de banda ancha móvil y la energía perdida a la resistencia interna. 

Puedes filtrar esta vista para mostrar solo aplicaciones en primer plano, aplicaciones en segundo plano o ambas mediante el menú de la esquina superior derecha. Las aplicaciones en primer plano son aquellas que han tenido interacción del usuario en los últimos 28 días, como seleccionar algo con un mouse.

## <a name="insights"></a>Insights

El **área Insights** muestra los tres principales consumidores de energía en las categorías de CPU y red. Estos elementos consumen una energía superior a la media en comparación con todas las implementaciones de Escritorio administrado de Microsoft. No se muestra el recurso de pantalla porque depende en gran medida del tiempo de uso del dispositivo y de la configuración de brillo de la pantalla. 

Seleccione los listados en la **columna Detalles** para obtener más información.

## <a name="battery-optimization"></a>Optimización de la batería

Windows 10 ofrece numerosas opciones de [configuración de dispositivos](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) para mejorar el uso de energía y aumentar la duración de la batería de los dispositivos de Escritorio administrado de Microsoft. Algunas de estas opciones de configuración pueden disminuir otras funciones de Windows, por lo que también tendrás que tener en cuenta otros factores, como el rol del dispositivo en la organización. El soporte técnico de Windows mantiene una lista de estas sugerencias [de ahorro de batería.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)

Los usuarios pueden ajustar algunas opciones de configuración por sí mismos sin necesidad de elevación o soporte técnico de administrador. Otras opciones requieren soporte técnico del administrador de TI de la organización.
