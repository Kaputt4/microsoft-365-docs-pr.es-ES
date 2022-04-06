---
title: Informe de estado y cumplimiento del dispositivo en Microsoft Defender para punto de conexión
description: Realizar un seguimiento de las detecciones de estado de estado del dispositivo, el estado del antivirus, la plataforma del sistema operativo y Windows 10 versiones con el informe de estado y cumplimiento del dispositivo
keywords: estado de mantenimiento, antivirus, plataforma del sistema operativo, versión de Windows 10, versión, estado, estado
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: bf89c0e57cbe14980b15ecf6f5a88f6db2b83e84
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64474033"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a>Informe de estado y cumplimiento del dispositivo en Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

El informe de estado de dispositivos proporciona información de alto nivel sobre los dispositivos de la organización. El informe incluye información de tendencias que muestra el estado del sensor, el estado del antivirus, las plataformas del sistema operativo y las Windows 10 (y Windows 11).

El panel está estructurado en dos secciones:

:::image type="content" source="images/device-reports.png" alt-text="El informe del dispositivo" lightbox="images/device-reports.png":::


<br>

****

|Sección|Descripción|
|---|---|
|1|Tendencias de dispositivos|
|2|Resumen del dispositivo (día actual)|
|||

## <a name="device-trends"></a>Tendencias de dispositivos

De forma predeterminada, las tendencias del dispositivo muestran información del dispositivo del período de 30 días que termina en el último día completo. Para obtener una mejor perspectiva de las tendencias que se producen en su organización, puede ajustar el período de informes ajustando el período de tiempo que se muestra. Para ajustar el período de tiempo, seleccione un intervalo de tiempo en las opciones desplegables:

- 30 días
- Tres meses
- Seis meses
- Personalizado

> [!NOTE]
> Estos filtros solo se aplican en la sección de tendencias de dispositivos. No afecta a la sección de resumen del dispositivo.

## <a name="device-summary"></a>Resumen del dispositivo

Aunque las tendencias de dispositivos muestran información de dispositivos de tendencia, el resumen del dispositivo muestra información del dispositivo con el ámbito del día actual.

> [!NOTE]
> Los datos reflejados en la sección de resumen están en el ámbito de 180 días antes de la fecha actual. Por ejemplo, si la fecha de hoy es el 27 de marzo de 2019, los datos de la sección de resumen reflejarán números a partir del 28 de septiembre de 2018 al 27 de marzo de 2019.
>
> El filtro aplicado en la sección tendencias no se aplica en la sección de resumen.

La sección de tendencias de dispositivos te permite explorar en profundidad la lista de dispositivos con el filtro correspondiente aplicado. Por ejemplo, al hacer clic en la barra Inactiva de la tarjeta de estado estado del sensor, aparecerá la lista de dispositivos con resultados que muestran solo los dispositivos cuyo estado del sensor está inactivo.

## <a name="device-attributes"></a>Atributos de dispositivo

El informe está hecho de tarjetas que muestran los siguientes atributos de dispositivo:

- **Estado de** mantenimiento: muestra información sobre el estado del sensor en los dispositivos, lo que proporciona una vista agregada de los dispositivos que están activos, que experimentan comunicaciones deficientes, inactivos o donde no se ven datos del sensor.
- **Estado del antivirus para dispositivos Windows 10** activos: muestra el número de dispositivos y el estado de Antivirus de Microsoft Defender.
- **Plataformas del sistema** operativo: muestra la distribución de las plataformas del sistema operativo que existen en la organización.
- **Windows 10:** muestra la distribución de Windows 10 dispositivos y sus versiones en la organización.

## <a name="filter-data"></a>Filtrar datos

Usa los filtros proporcionados para incluir o excluir dispositivos con determinados atributos.

Puedes seleccionar varios filtros para aplicar desde los atributos del dispositivo.

> [!NOTE]
> Estos filtros se aplican a **todas** las tarjetas del informe.

Por ejemplo, para mostrar datos sobre Windows 10 dispositivos con estado de mantenimiento del sensor activo:

1. En **Filtros > Estado de mantenimiento del sensor > Activo**.
2. A continuación, seleccione **Plataformas del sistema operativo > Windows 10**.
3. Seleccione **Aplicar**.

## <a name="related-topic"></a>Tema relacionado

- [Informe de protección contra amenazas](threat-protection-reports.md)
