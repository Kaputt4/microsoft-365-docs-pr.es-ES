---
title: Información sobre las baterías
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 434f62d5ddfc8bc75c54de422aafc8c6325c4086
ms.sourcegitcommit: 1c445d68e54ca4249024ca4bb72460dd6fac0a2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "42170600"
---
# <a name="battery-insights"></a>Información sobre las baterías
Esta vista proporciona métricas de uso de energía, batería y aplicaciones para los dispositivos de escritorio administrados por Microsoft. Por estos motivos, una aplicación se considera "en uso" si está en ejecución y en enfoque.

Para ver los datos de uso, seleccione la pestaña **batería** .

![Panel batería: duración prevista de la batería por modelo de dispositivo en la parte superior izquierda y los principales consumidores de energía (por aplicación) en la parte superior derecha y en la tabla información en la parte inferior. Vínculo de documentación en la esquina superior derecha.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>Duración prevista de la batería

En el área de duración de la **batería prevista** , proporcionamos predicciones para la duración prevista de la batería de los dispositivos, organizadas por modelo de dispositivo.

> [!NOTE]
> Estos datos se derivan del uso de energía de muestreo, el tiempo de uso y la capacidad de la batería desde una <em>selección</em> aleatoria de los dispositivos en su implementación de escritorio administrada de Microsoft que también son datos de informes.

La tabla proporciona la duración prevista de la batería (en horas), la duración media de la batería para los mismos modelos en otras implementaciones de escritorio administradas por Microsoft y el número de dispositivos que notifican estos datos en el entorno. Ordene los datos seleccionando los encabezados de columna.



## <a name="top-energy-consumers"></a>Principales consumidores de energía

En el área de los **principales consumidores de energía** , encontrará las aplicaciones de su entorno que consumen más energía en milliWatt-horas (MWh). Las aplicaciones que se muestran son por dispositivo específico, que se seleccionan en la sección duración de la **batería de previsiones** a la izquierda. Por ejemplo, para ver el consumo por aplicación para los dispositivos de Microsoft Surface Book 2, seleccione esa fila en el área duración de la batería. Si no selecciona ningún modelo, los datos de consumo de la aplicación mostrados son para todas las aplicaciones para las que tenemos datos colectivamente.

 Para cada aplicación, los segmentos de color muestran la distribución del uso de energía de la aplicación entre estas categorías:

- CPU
- Visualización
- Red
- Otros

"Otros" podrían incluir consumo energético por una variedad de orígenes, como la actividad de disco, el uso de banda ancha móvil y la pérdida de energía de resistencia interna. 

Puede filtrar esta vista para mostrar solo las aplicaciones en primer plano, las aplicaciones en segundo plano o ambas mediante el menú de la esquina superior derecha. Las aplicaciones en primer plano son aquellas en las que se ha producido la interacción del usuario en los últimos 28 días, como seleccionar algo con un mouse (ratón).

## <a name="insights"></a>Información

El área de **información** muestra los tres consumidores de energía principales en las categorías CPU y red. Estos elementos consumen más de una energía media en comparación con todas las implementaciones de escritorio administradas por Microsoft. No se muestra el recurso para mostrar porque depende en gran medida del tiempo de uso del dispositivo y la configuración del brillo de la pantalla. 

Seleccione los listados en la columna **detalles** para obtener más información.

## <a name="battery-optimization"></a>Optimización de la batería

Windows 10 ofrece varias [Opciones de configuración de dispositivo](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) para mejorar el uso de energía y aumentar la duración de la batería de los dispositivos de escritorio administrados por Microsoft. Algunas de estas opciones de configuración pueden disminuir otras funciones de Windows, por lo que también tendrá que tener en cuenta otros factores, como la función del dispositivo en su organización. El soporte técnico de Windows mantiene una lista de estas [sugerencias de ahorro de batería](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).

Los usuarios pueden ajustar algunas opciones de configuración por su cuenta sin necesidad de elevación o soporte administrativo. Otras opciones requieren la asistencia del administrador de TI de la organización.
