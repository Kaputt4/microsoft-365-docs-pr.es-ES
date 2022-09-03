---
title: Informar y solucionar problemas Microsoft Defender para punto de conexión reglas de ASR
description: En este tema se describe cómo notificar y solucionar problemas Microsoft Defender para punto de conexión reglas de ASR
keywords: Reglas de reducción de superficie expuesta a ataques, asr, caderas, sistema de prevención de intrusiones de host, reglas de protección, anti-vulnerabilidad, antiexploit, vulnerabilidad de seguridad, prevención de infecciones, microsoft defender para punto de conexión
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
author: lovina-saldanha
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.custom:
- asr
- admindeeplinkDEFENDER
ms.topic: article
ms.subservice: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 660aa5935d01aa00fbac0b1cafbdeca126d909ed
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67584273"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-endpoint-asr-rules"></a>Informar y solucionar problemas Microsoft Defender para punto de conexión reglas de ASR

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

El <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a> es la nueva interfaz para supervisar y administrar la seguridad en las identidades, los datos, los dispositivos, las aplicaciones y la infraestructura de Microsoft. Aquí podrá ver fácilmente el estado de seguridad de su organización; configurar dispositivos, usuarios y aplicaciones, así como recibir alertas sobre actividad sospechosa. El portal de Microsoft 365 Defender está pensado para que los administradores de seguridad y los equipos de operaciones de seguridad administren y protejan mejor su organización. Visite el portal de Microsoft 365 Defender en<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><https://security.microsoft.com></a> .

En <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>, le ofrecemos una vista completa de la configuración y los eventos actuales de las reglas de ASR en su patrimonio. Tenga en cuenta que los dispositivos deben incorporarse al servicio Microsoft Defender para punto de conexión para que se rellenen estos informes.
Esta es una captura de pantalla del portal de Microsoft 365 Defender (en **Dispositivos de informes** \>  \> **Reducción de la superficie expuesta a ataques**). En el nivel de dispositivo, seleccione **Configuración** en el panel **Reglas de reducción de superficie expuesta a ataques** . Se muestra la siguiente pantalla, donde puede seleccionar un dispositivo específico y comprobar su configuración de regla ASR individual.

:::image type="content" source="images/asrrulesnew.png" alt-text="Página reglas de ASR" lightbox="images/asrrulesnew.png":::

## <a name="microsoft-defender-for-endpoint---advanced-hunting"></a>Microsoft Defender para punto de conexión: búsqueda avanzada

Una de las características más eficaces de Microsoft Defender para punto de conexión es la búsqueda avanzada. Si no está familiarizado con la búsqueda avanzada, consulte [búsqueda proactiva de amenazas con la búsqueda avanzada](advanced-hunting-overview.md).

La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consultas (Lenguaje de consulta Kusto) que permite explorar hasta 30 días de los datos capturados (sin procesar) que Defender para punto de conexión recopila de los dispositivos. Mediante la búsqueda avanzada, puede inspeccionar eventos de forma proactiva para localizar indicadores y entidades interesantes. El acceso flexible a los datos ayuda a la búsqueda sin restricciones de amenazas conocidas y potenciales.

Mediante la búsqueda avanzada, es posible extraer información de reglas de ASR, crear informes y obtener información detallada sobre el contexto de un evento de bloque o auditoría de reglas de ASR determinado.

Los eventos de reglas de ASR están disponibles para consultarse desde la tabla DeviceEvents de la sección de búsqueda avanzada del Microsoft 365 Defender. Por ejemplo, una consulta simple como la siguiente puede notificar todos los eventos que tienen reglas ASR como origen de datos, durante los últimos 30 días, y los resumirá por el recuento ActionType, que en este caso será el nombre de código real de la regla ASR.

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="Consulta de búsqueda avanzada" lightbox="images/adv-hunt-querynew.png":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="Página Búsqueda avanzada" lightbox="images/adv-hunt-sc-2new.png":::

Con la búsqueda avanzada, puede dar forma a las consultas a su gusto, de modo que pueda ver lo que está sucediendo, independientemente de si desea identificar algo en una máquina individual o si desea extraer información de todo el entorno.

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a>escala de tiempo de Microsoft Defender para punto de conexión máquina

Una alternativa a la búsqueda avanzada, pero con un ámbito más estrecho, es la escala de tiempo Microsoft Defender para punto de conexión máquina. Puede ver todos los eventos recopilados de un dispositivo, durante los últimos seis meses, en el Microsoft 365 Defender, en la lista Máquinas, seleccione una máquina determinada y, a continuación, haga clic en la pestaña Escala de tiempo.

En la imagen siguiente se muestra una captura de pantalla de la vista Escala de tiempo de estos eventos en un punto de conexión determinado. Desde esta vista, puede filtrar la lista de eventos en función de cualquiera de los grupos de eventos a lo largo del panel derecho. También puede habilitar o deshabilitar eventos marcados y detallados al ver alertas y desplazarse por la escala de tiempo histórica.

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="Escala de tiempo de Microsoft 365 Defender" lightbox="images/mic-sec-def-timelinenew.png":::

## <a name="how-to-troubleshoot-asr-rules"></a>¿Cómo solucionar problemas de reglas de ASR?

La primera y más inmediata es comprobar localmente, en un dispositivo Windows, qué reglas de ASR están habilitadas (y su configuración) mediante los cmdlets de PowerShell.

Estas son algunas otras fuentes de información que Ofrece Windows para solucionar el impacto y el funcionamiento de las reglas de ASR.

### <a name="querying-which-rules-are-active"></a>Consulta de qué reglas están activas

Una de las maneras más sencillas de determinar si las reglas de ASR ya están habilitadas es a través de un cmdlet de PowerShell, Get-MpPreference.

Aquí le mostramos un ejemplo:

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="El script get mppreference" lightbox="images/getmpreferencescriptnew.png":::

Hay varias reglas de ASR activas, con diferentes acciones configuradas.

Para expandir la información anterior sobre las reglas de ASR, puede usar las propiedades **AttackSurfaceReductionRules_Ids** o **AttackSurfaceReductionRules_Actions**.

Ejemplo:

```powershell
Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Ids
```

:::image type="content" source="images/getmpref-examplenew.png" alt-text="Ejemplo de obtención de mpreference" lightbox="images/getmpref-examplenew.png":::

En lo anterior se muestran todos los identificadores de las reglas asr que tienen una configuración diferente de 0 (no configurada).

El siguiente paso es enumerar las acciones reales (Bloquear o Auditar) con las que se configura cada regla.

```powershell
Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Actions
```

:::image type="content" source="images/getmpref-example2new.png" alt-text="Ejemplo de get mppreference2" lightbox="images/getmpref-example2new.png":::

### <a name="querying-blocking-and-auditing-events"></a>Consulta de eventos de bloqueo y auditoría

Los eventos de regla de ASR se pueden ver en el registro de Windows Defender.

Para acceder a ella, abra Windows Visor de eventos y vaya a Registros de **aplicaciones y servicios** \> **de Microsoft** \> **Windows** \> **Windows Defender** \> **Operativo**.

:::image type="content" source="images/eventviewerscrnew.png" alt-text="Página Visor de eventos" lightbox="images/eventviewerscrnew.png":::

## <a name="microsoft-defender-antimalware-protection-logs"></a>Registros de protección antimalware de Microsoft Defender

También puede ver los eventos de regla a través de la herramienta de línea de comandos dedicada antivirus de Microsoft Defender, denominada `*mpcmdrun.exe*`, que se puede usar para administrar y configurar y automatizar las tareas si es necesario.

Puede encontrar esta utilidad en *%ProgramFiles%\Windows Defender\MpCmdRun.exe*. Debe ejecutarlo desde un símbolo del sistema con privilegios elevados (es decir, ejecutarlo como Administración).

Para generar la información de soporte técnico, escriba *MpCmdRun.exe -getfiles*. Después de un tiempo, varios registros se empaquetarán en un archivo (MpSupportFiles.cab) y estarán disponibles en *C:\ProgramData\Microsoft\Windows Defender\Support*.

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="Registros de protección contra malware" lightbox="images/malware-prot-logsnew.png":::

Extraiga ese archivo y tendrá muchos archivos disponibles para solucionar problemas.

Los archivos más relevantes son los siguientes:

- **MPOperationalEvents.txt**: este archivo contiene el mismo nivel de información que se encuentra en Visor de eventos para el registro operativo de Windows Defender.
- **MPRegistry.txt**: en este archivo puede analizar todas las configuraciones de Windows Defender actuales, desde el momento en que se capturaron los registros de soporte técnico.
- **MPLog.txt**: este registro contiene información más detallada sobre todas las acciones o operaciones del Windows Defender.
