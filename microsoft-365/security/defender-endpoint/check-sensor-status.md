---
title: Comprobar el estado de mantenimiento del sensor en Microsoft Defender para endpoint
description: Compruebe el estado del sensor en los dispositivos para identificar cuáles están mal configurados, inactivos o no están informando datos del sensor.
keywords: sensor, estado del sensor, mal configurado, inactivo, sin datos de sensor, datos de sensor, comunicaciones deficientes, comunicación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 8168977629f80923ed65e84127478eea0b526597
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58256374"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a>Comprobar el estado del sensor en Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-checksensor-abovefoldlink)

El **icono Dispositivos con problemas de sensor** se encuentra en el panel Operaciones de seguridad. Este icono proporciona información sobre la capacidad del dispositivo individual para proporcionar datos del sensor y comunicarse con el servicio Defender for Endpoint. Indica cuántos dispositivos requieren atención y le ayuda a identificar dispositivos problemáticos y tomar medidas para corregir los problemas conocidos.

Hay dos indicadores de estado en el icono que proporcionan información sobre el número de dispositivos que no están informando correctamente al servicio:
- **Mal configurados:** estos dispositivos podrían estar informando parcialmente los datos del sensor al servicio Defender for Endpoint y podrían tener errores de configuración que deben corregirse.
- **Inactivo:** dispositivos que han dejado de informar al servicio Defender for Endpoint durante más de siete días en el último mes.

Hacer clic en cualquiera de los grupos te dirige a **la lista Dispositivos,** filtrada según tu elección.

![Captura de pantalla de dispositivos con icono de problemas de sensor](images/atp-devices-with-sensor-issues-tile.png)

En **la lista dispositivos,** puede filtrar la lista de estado de mantenimiento por el siguiente estado:
- **Activo:** dispositivos que están informando activamente al servicio Defender for Endpoint.
- **Mal configurado: estos** dispositivos pueden estar informando parcialmente los datos del sensor al servicio defender para endpoints, pero tienen errores de configuración que deben corregirse. Los dispositivos mal configurados pueden tener uno o varios de los siguientes problemas:
  - **Sin datos de sensor:** los dispositivos han dejado de enviar datos del sensor. Se pueden activar alertas limitadas desde el dispositivo.
  - **Comunicaciones deficientes:** la capacidad de comunicarse con el dispositivo se ve afectada. Puede que el envío de archivos para un análisis profundo, el bloqueo de archivos, el aislamiento de dispositivo de la red y otras acciones que requieran comunicación con el dispositivo no funcionen.
- **Inactivo:** dispositivos que han dejado de informar al servicio Defender for Endpoint.

También puede descargar toda la lista en formato CSV mediante la **característica** Exportar. Para obtener más información sobre los filtros, [vea Ver y organizar la lista Dispositivos](machines-view-overview.md).

>[!NOTE]
>Exporte la lista en formato CSV para mostrar los datos sin filtrar. El archivo CSV incluirá todos los dispositivos de la organización, independientemente de cualquier filtrado aplicado en la vista en sí y puede tardar una cantidad significativa de tiempo en descargarse, según el tamaño de la organización.

![Captura de pantalla de la página de lista Dispositivos](images/atp-devices-list-page.png)

Puedes ver los detalles del dispositivo al hacer clic en un dispositivo mal configurado o inactivo.

## <a name="see-also"></a>Consulte también
- [Corregir sensores incorrectos en Defender for Endpoint](fix-unhealthy-sensors.md)
- [Información general del Analizador de clientes](overview-client-analyzer.md)
- [Descargar y ejecutar el Analizador de clientes](download-client-analyzer.md)
- [Ejecutar el Analizador de clientes en Windows](run-analyzer-windows.md)
- [Ejecutar el Analizador de clientes en macOS o Linux](run-analyzer-macos-linux.md)
- [ Recopilación de datos para solucionar problemas avanzados en Windows](data-collection-analyzer.md)
