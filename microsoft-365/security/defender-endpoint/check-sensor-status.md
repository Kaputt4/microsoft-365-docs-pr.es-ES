---
title: Compruebe el estado de mantenimiento del sensor en Microsoft Defender para punto de conexión
description: Compruebe el estado del sensor en los dispositivos para identificar cuáles están mal configurados, inactivos o no informan de los datos del sensor.
keywords: sensor, estado del sensor, mal configurado, inactivo, sin datos del sensor, datos del sensor, comunicaciones dañadas, comunicación
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/24/2018
search.appverid: met150
ms.openlocfilehash: 353dad94d14ccfd807a946161d3879815526899d
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2022
ms.locfileid: "67799096"
---
# <a name="check-sensor-health-state-at-microsoft-defender-for-endpoint"></a>Comprobación del estado del sensor en Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-checksensor-abovefoldlink)

El icono **Dispositivos con problemas de sensor** proporciona información sobre la capacidad del dispositivo individual para proporcionar datos del sensor y comunicarse con el servicio Defender para punto de conexión. Indica cuántos dispositivos requieren atención y le ayuda a identificar dispositivos problemáticos y tomar medidas para corregir los problemas conocidos.

Hay dos indicadores de estado en el icono que proporcionan información sobre el número de dispositivos que no informan correctamente al servicio:

- **Mal configurados** : estos dispositivos podrían estar notificando parcialmente los datos del sensor al servicio Defender para punto de conexión y pueden tener errores de configuración que deben corregirse.
- **Inactivo** : dispositivos que han dejado de informar al servicio Defender para punto de conexión durante más de siete días en el último mes.

Al hacer clic en cualquiera de los grupos, se le dirige a la **lista Dispositivos**, filtrada según su elección.

:::image type="content" source="images/atp-devices-with-sensor-issues-tile.png" alt-text="Icono Dispositivos con problemas de sensor" lightbox="images/atp-devices-with-sensor-issues-tile.png":::

En **la lista Dispositivos**, puede filtrar la lista de estado de mantenimiento por el siguiente estado:

- **Activo** : dispositivos que informan activamente al servicio Defender para punto de conexión.
- **Mal configurados** : estos dispositivos podrían estar notificando parcialmente los datos del sensor al servicio Defender para punto de conexión, pero tienen errores de configuración que deben corregirse. Los dispositivos mal configurados pueden tener uno o varios de los siguientes problemas:
  - **Sin datos del sensor** : los dispositivos han dejado de enviar datos del sensor. Se pueden activar alertas limitadas desde el dispositivo.
  - **Comunicaciones deterioradas** : la capacidad de comunicarse con el dispositivo se ve afectada. Puede que el envío de archivos para un análisis profundo, el bloqueo de archivos, el aislamiento de dispositivo de la red y otras acciones que requieran comunicación con el dispositivo no funcionen.
- **Inactivo** : dispositivos que han dejado de informar al servicio Defender para punto de conexión.

También puede descargar toda la lista en formato CSV mediante la característica **Exportar** . Para obtener más información sobre los filtros, vea [Ver y organizar la lista dispositivos](machines-view-overview.md).

> [!NOTE]
> Exporte la lista en formato CSV para mostrar los datos sin filtrar. El archivo CSV incluirá todos los dispositivos de la organización, independientemente de los filtros aplicados en la propia vista y puede tardar mucho tiempo en descargarse, en función del tamaño de su organización.

:::image type="content" source="images/atp-devices-list-page.png" alt-text="La pestaña Exportar de la página de lista Dispositivo" lightbox="images/atp-devices-list-page.png":::

Puede ver los detalles del dispositivo al hacer clic en un dispositivo mal configurado o inactivo.

## <a name="see-also"></a>Vea también

- [Corrección de sensores incorrectos en Defender para punto de conexión](fix-unhealthy-sensors.md)
- [Información general del Analizador de clientes](overview-client-analyzer.md)
- [Descargar y ejecutar el Analizador de clientes](download-client-analyzer.md)
- [Ejecutar el Analizador de clientes en Windows](run-analyzer-windows.md)
- [Ejecutar el Analizador de clientes en macOS o Linux](run-analyzer-macos-linux.md)
- [ Recopilación de datos para solucionar problemas avanzados en Windows](data-collection-analyzer.md)
