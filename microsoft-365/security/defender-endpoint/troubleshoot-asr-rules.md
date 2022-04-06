---
title: Informar y solucionar problemas de Microsoft Defender para las reglas de ASR de punto de conexión
description: En este tema se describe cómo informar y solucionar problemas de Microsoft Defender para las reglas de ASR de punto de conexión
keywords: Reglas de reducción de superficie de ataque, asr, hips, host intrusion prevention system, protection rules, anti-exploit, antiexploit, exploit, infection prevention, microsoft defender for endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
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
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: b1a90ec887f62a3c486c30ed50b87482de451c01
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64471019"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-endpoint-asr-rules"></a>Informar y solucionar problemas de Microsoft Defender para las reglas de ASR de punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

El <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender es</a> la nueva interfaz para supervisar y administrar la seguridad en todas las identidades, datos, dispositivos, aplicaciones e infraestructura de Microsoft. Aquí podrá ver fácilmente el estado de seguridad de su organización; configurar dispositivos, usuarios y aplicaciones, así como recibir alertas sobre actividad sospechosa. El portal Microsoft 365 Defender está pensado para que los administradores de seguridad y los equipos de operaciones de seguridad administren y protejan mejor su organización. Visite el portal Microsoft 365 Defender en<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><https://security.microsoft.com></a>.

En <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>, le ofrecemos una vista completa de la configuración y los eventos de reglas ASR actuales en su estado. Tenga en cuenta que los dispositivos deben incorporarse al servicio Microsoft Defender para endpoints para que estos informes se rellenen.
Esta es una captura de pantalla del portal de Microsoft 365 Defender (en **Reports** \> **Devices** \> **Attack surface reduction**). En el nivel de dispositivo, selecciona **Configuración en** el **panel Reglas de reducción de superficie de** ataque. Se muestra la siguiente pantalla, donde puedes seleccionar un dispositivo específico y comprobar su configuración de regla ASR individual.

:::image type="content" source="images/asrrulesnew.png" alt-text="La página reglas de ASR" lightbox="images/asrrulesnew.png":::

## <a name="microsoft-defender-for-endpoint---advanced-hunting"></a>Microsoft Defender para endpoint: búsqueda avanzada

Una de las características más eficaces de Microsoft Defender para Endpoint es la búsqueda avanzada. Si no estás familiarizado con la búsqueda avanzada, consulta la búsqueda [proactiva de amenazas con la búsqueda avanzada](advanced-hunting-overview.md).

La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consultas (Kusto Query Language) que te permite explorar hasta 30 días de los datos capturados (sin procesar) que Defender for Endpoint recopila de tus dispositivos. A través de la búsqueda avanzada, puede inspeccionar proactivamente eventos para localizar indicadores y entidades interesantes. El acceso flexible a los datos ayuda a la búsqueda sin restricciones de amenazas conocidas y potenciales.

Mediante la búsqueda avanzada, es posible extraer información de reglas ASR, crear informes y obtener información detallada sobre el contexto de un evento de bloqueo o auditoría de regla ASR determinado.

Los eventos de reglas ASR están disponibles para consultarse desde la tabla DeviceEvents en la sección de búsqueda avanzada de la Microsoft 365 Defender. Por ejemplo, una consulta sencilla, como la siguiente, puede informar de todos los eventos que tienen reglas ASR como origen de datos durante los últimos 30 días y los resumirá mediante el recuento ActionType, que en este caso será el nombre de código real de la regla ASR.

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="Consulta de búsqueda avanzada" lightbox="images/adv-hunt-querynew.png":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="La página Búsqueda avanzada" lightbox="images/adv-hunt-sc-2new.png":::

Con la búsqueda avanzada puedes dar forma a las consultas a tu gusto, para que puedas ver lo que está sucediendo, independientemente de si quieres identificar algo en una máquina individual o quieres extraer información de todo el entorno.

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a>Escala de tiempo de la máquina de Microsoft Defender para endpoint

Una alternativa a la búsqueda avanzada, pero con un ámbito más estrecho, es la escala de tiempo de la máquina de Microsoft Defender para endpoint. Puedes ver todos los eventos recopilados de un dispositivo, durante los últimos seis meses, en el Microsoft 365 Defender, yendo a la lista Máquinas, selecciona una máquina determinada y, a continuación, haz clic en la pestaña Escala de tiempo.

A continuación se muestra una captura de pantalla de la vista Escala de tiempo de estos eventos en un punto de conexión determinado. Desde esta vista, puede filtrar la lista de eventos en función de cualquiera de los grupos de eventos a lo largo del panel derecho. También puedes habilitar o deshabilitar eventos marcados y detallados al ver alertas y desplazarte por la escala de tiempo histórica.

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="Escala Microsoft 365 Defender escala de tiempo" lightbox="images/mic-sec-def-timelinenew.png":::

## <a name="how-to-troubleshoot-asr-rules"></a>¿Cómo solucionar problemas de reglas ASR?

La primera y más inmediata es comprobar localmente, en un dispositivo Windows, qué reglas ASR están habilitadas (y su configuración) es mediante los cmdlets de PowerShell.

Estas son algunas otras fuentes de información que Windows, para solucionar el impacto y el funcionamiento de las reglas ASR.

### <a name="querying-which-rules-are-active"></a>Consultar qué reglas están activas

Una de las formas más sencillas de determinar si las reglas ASR ya están habilitadas es a través de un cmdlet de PowerShell, Get-MpPreference.

Aquí le mostramos un ejemplo:

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="Script get mppreference" lightbox="images/getmpreferencescriptnew.png":::

Hay varias reglas ASR activas, con distintas acciones configuradas.

Para expandir la información anterior sobre las reglas ASR, puede usar las propiedades **AttackSurfaceReductionRules_Ids y/** o **AttackSurfaceReductionRules_Actions**.

Ejemplo:

```powershell
Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Ids
```

:::image type="content" source="images/getmpref-examplenew.png" alt-text="Ejemplo de obtener mpreference" lightbox="images/getmpref-examplenew.png":::

Lo anterior muestra todos los IDs de las reglas ASR que tienen una configuración diferente de 0 (No configurado).

A continuación, el siguiente paso es enumerar las acciones reales (Bloquear o Auditar) con las que se configura cada regla.

```powershell
Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Actions
```

:::image type="content" source="images/getmpref-example2new.png" alt-text="Ejemplo de get mppreference2" lightbox="images/getmpref-example2new.png":::

### <a name="querying-blocking-and-auditing-events"></a>Consulta de eventos de bloqueo y auditoría

Los eventos de regla ASR se pueden ver en el Windows Defender registro.

Para acceder a él, abra Windows visor de eventos y  \> vaya a Registros de aplicaciones y servicios **de Microsoft** \> **Windows** \> **Windows Defender** \> **Operativo**.

:::image type="content" source="images/eventviewerscrnew.png" alt-text="Página Visor de eventos" lightbox="images/eventviewerscrnew.png":::

## <a name="microsoft-defender-antimalware-protection-logs"></a>Registros de protección antimalware de Microsoft Defender

También puede ver eventos de regla Antivirus de Microsoft Defender la herramienta de línea de comandos dedicada, `*mpcmdrun.exe*`denominada , que se puede usar para administrar y configurar y automatizar tareas si es necesario.

Puede encontrar esta utilidad en *%ProgramFiles%\Windows Defender\MpCmdRun.exe*. Debe ejecutarlo desde un símbolo del sistema con privilegios elevados (es decir, ejecutar como administrador).

Para generar la información de compatibilidad, *escribaMpCmdRun.exe -getfiles*. Después de un tiempo, varios registros se empaquetarán en un archivo (MpSupportFiles.cab) y estarán disponibles en *C:\ProgramData\Microsoft\Windows Defender\Support*.

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="Registros de protección contra malware" lightbox="images/malware-prot-logsnew.png":::

Extrae ese archivo y tendrás muchos archivos disponibles para solucionar problemas.

Los archivos más relevantes son los siguientes:

- **MPOperationalEvents.txt**: este archivo contiene el mismo nivel de información que se encuentra en el Visor de eventos para el registro operativo de Windows Defender.
- **MPRegistry.txt**: en este archivo puede analizar todas las configuraciones Windows Defender actuales, desde el momento en que se capturaron los registros de soporte técnico.
- **MPLog.txt**: este registro contiene información más detallada sobre todas las acciones y operaciones del Windows Defender.
