---
title: Información sobre las baterías
description: Un informe que muestra datos sobre la duración de la batería y los principales consumidores de energía
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739830"
---
# <a name="battery-insights"></a>Información sobre las baterías
Esta vista proporciona métricas de consumo de energía, batería y aplicaciones para los Escritorio administrado de Microsoft dispositivos. Para estos fines, una aplicación se considera "en uso" si se está ejecutando y en foco.

Para ver los datos de uso, seleccione la **pestaña** Batería.

![Panel de batería: duración de la batería pronosticada por modelo de dispositivo en la parte superior izquierda, consumidores de energía superiores (por aplicación) en la parte superior derecha, tabla de información en la parte inferior. Vínculo documentación en la parte superior derecha](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>Duración de la batería pronosticada

En el **área Duración de la batería** predicho, proporcionamos previsiones para la duración de la batería esperada para los dispositivos, organizadas por el modelo de dispositivos.

> [!NOTE]
> Estos datos se derivan del uso de energía de <em></em> muestreo, el tiempo de uso y la capacidad de batería de una selección aleatoria de los dispositivos de la implementación de Escritorio administrado de Microsoft que también están informando datos.

La tabla proporciona la duración de la batería predicho (en horas), la duración media de la batería de los mismos modelos en otras implementaciones de Escritorio administrado de Microsoft y el número de dispositivos que informan de estos datos en el entorno. Para ordenar los datos, seleccione los encabezados de columna.



## <a name="top-energy-consumers"></a>Principales consumidores de energía

En el **área Principales consumidores** de energía, encontrarás las aplicaciones de tu entorno que consumen más energía en milivavatio-hora (mWh). Las aplicaciones que se muestran son por dispositivo específico, que seleccionas en la sección **Duración** de la batería predicho a la izquierda. Por ejemplo, para ver el consumo por aplicación de los dispositivos de Microsoft Surface Book 2, selecciona esa fila en el área de duración de la batería. Si no seleccionas ningún modelo, los datos de consumo de aplicaciones que se muestran son para todas las aplicaciones para las que tenemos datos de forma colectiva.

 Para cada aplicación, los segmentos de color muestran la distribución del uso de energía de la aplicación entre estas categorías:

- CPU
- Pantalla
- Red
- Otros

"Otros" podría incluir el consumo de energía por una variedad de fuentes, como la actividad de disco, el uso de banda ancha móvil y la energía perdida por la resistencia interna. 

Puedes filtrar esta vista para mostrar solo aplicaciones en primer plano, aplicaciones en segundo plano o ambas mediante el menú de la parte superior derecha. Las aplicaciones en primer plano son aquellas que han tenido interacción del usuario en los últimos 28 días, como seleccionar algo con un mouse.

## <a name="insights"></a>Insights

El **área Insights** muestra los tres principales consumidores de energía en las categorías de CPU y red. Estos elementos consumen energía superior a la media en comparación con todas Escritorio administrado de Microsoft implementaciones. No mostramos el recurso de presentación porque depende en gran medida del tiempo de uso del dispositivo y de la configuración de brillo de la pantalla. 

Seleccione los listados de la columna **Detalles** para obtener más información.

## <a name="battery-optimization"></a>Optimización de batería

Windows 10 ofrece numerosas [configuraciones de dispositivos](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) para mejorar el uso de energía y aumentar la duración de la batería de los Escritorio administrado de Microsoft dispositivos. Algunas de estas opciones pueden disminuir otras funciones Windows, por lo que también tendrás que tener en cuenta otros factores, como el rol del dispositivo en tu organización. Windows soporte técnico mantiene una lista de estas sugerencias [de ahorro de batería.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)

Los usuarios pueden ajustar algunas configuraciones por su cuenta sin necesidad de elevación de administrador o soporte técnico. Otras opciones requieren soporte técnico del administrador de TI de la organización.
