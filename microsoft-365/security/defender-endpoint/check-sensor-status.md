---
title: Comprobar el estado del sensor en ATP de Microsoft Defender
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
ms.openlocfilehash: 21313463519383f4bf052465a0d907d2df293ec8
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165278"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a>Comprobar el estado del sensor en Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-checksensor-abovefoldlink)

El **icono Dispositivos con problemas de sensor** se encuentra en el panel Operaciones de seguridad. Este icono proporciona información sobre la capacidad del dispositivo individual para proporcionar datos del sensor y comunicarse con el servicio Defender for Endpoint. Informa de cuántos dispositivos requieren atención y le ayuda a identificar dispositivos problemáticos y a tomar medidas para corregir problemas conocidos.

Hay dos indicadores de estado en el icono que proporcionan información sobre el número de dispositivos que no están informando correctamente al servicio:
- **Mal configurados:** estos dispositivos podrían estar informando parcialmente los datos del sensor al servicio Defender for Endpoint y podrían tener errores de configuración que deben corregirse.
- **Inactivo:** dispositivos que han dejado de informar al servicio Defender for Endpoint durante más de siete días en el último mes.

Hacer clic en cualquiera de los grupos te dirige a **la lista Dispositivos,** filtrada según tu elección.

![Captura de pantalla de dispositivos con icono de problemas de sensor](images/atp-devices-with-sensor-issues-tile.png)

En **la lista dispositivos,** puede filtrar la lista de estado de mantenimiento por el siguiente estado:
- **Activo:** dispositivos que están informando activamente al servicio Defender for Endpoint.
- **Mal configurado: estos** dispositivos pueden estar informando parcialmente los datos del sensor al servicio defender para endpoints, pero tienen errores de configuración que deben corregirse. Los dispositivos mal configurados pueden tener uno o una combinación de los siguientes problemas:
  - **Sin datos de sensor:** los dispositivos han dejado de enviar datos del sensor. Las alertas limitadas se pueden desencadenar desde el dispositivo.
  - **Comunicaciones deficientes:** la capacidad de comunicarse con el dispositivo se ve afectada. Es posible que el envío de archivos para un análisis profundo, el bloqueo de archivos, el aislamiento del dispositivo de la red y otras acciones que requieran comunicación con el dispositivo no funcionen.
- **Inactivo:** dispositivos que han dejado de informar al servicio Defender for Endpoint.

También puede descargar toda la lista en formato CSV mediante la **característica** Exportar. Para obtener más información sobre los filtros, [vea Ver y organizar la lista Dispositivos](machines-view-overview.md).

>[!NOTE]
>Exporte la lista en formato CSV para mostrar los datos sin filtrar. El archivo CSV incluirá todos los dispositivos de la organización, independientemente de cualquier filtrado aplicado en la vista en sí y puede tardar una cantidad significativa de tiempo en descargarse, según el tamaño de la organización.

![Captura de pantalla de la página de lista Dispositivos](images/atp-devices-list-page.png)

Puedes ver los detalles del dispositivo al hacer clic en un dispositivo mal configurado o inactivo.

## <a name="related-topic"></a>Tema relacionado
- [Corregir sensores incorrectos en Defender for Endpoint](fix-unhealthy-sensors.md)
