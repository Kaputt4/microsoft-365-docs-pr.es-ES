---
title: Uso de la línea de comandos para administrar Microsoft Defender Antivirus
description: Ejecute Microsoft Defender antivirus y configure la protección de próxima generación con una utilidad de línea de comandos dedicada.
keywords: ejecutar examen de Windows Defender, ejecutar examen antivirus desde la línea de comandos, ejecutar examen de Windows Defender desde la línea de comandos, mpcmdrun, defender
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/24/2021
ms.subservice: mde
ms.topic: how-to
ms.collection:
- m365-security
- tier3
search.appverid: met150
ms.openlocfilehash: 57fc2406410b3a24394ae6a11d5c06b0e6110418
ms.sourcegitcommit: b9282493c371d59c2e583b9803825096499b5e2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68153265"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>Configuración y administración de Microsoft Defender Antivirus con la herramienta de línea de comandos de mpcmdrun.exe

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender 

**Plataformas**
- Windows

Puede realizar varias funciones en Microsoft Defender Antivirus mediante la herramienta de línea de comandos dedicada **mpcmdrun.exe**. Esta utilidad es útil cuando se desea automatizar Microsoft Defender tareas antivirus. Puede encontrar la utilidad en `%ProgramFiles%\Windows Defender\MpCmdRun.exe`. Ejecútelo desde un símbolo del sistema.

> [!TIP]
> Es posible que tenga que abrir una versión de nivel de administrador del símbolo del sistema. Al buscar **el símbolo del sistema** en el menú Inicio, elija **Ejecutar como administrador**. Si ejecuta una versión actualizada Microsoft Defender plataforma antimalware, ejecute `MpCmdRun` desde la siguiente ubicación: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>`. Para obtener más información sobre la plataforma antimalware, consulte [Microsoft Defender actualizaciones y líneas base del Antivirus](manage-updates-baselines-microsoft-defender-antivirus.md).

La utilidad MpCmdRun usa la sintaxis siguiente:

```console
MpCmdRun.exe [command] [-options]
```

Aquí le mostramos un ejemplo:

```console
MpCmdRun.exe -Scan -ScanType 2
```

En nuestro ejemplo, la utilidad MpCmdRun inicia un examen antivirus completo en el dispositivo.

## <a name="commands"></a>Comandos

|Comando|Descripción|
|---|---|
|`-?` **o** `-h`|Muestra todas las opciones disponibles para la herramienta MpCmdRun.|
|`-Scan [-ScanType [<value>]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]`|Busca software malintencionado. Los valores de **ScanType** son:<p>**0** Valor predeterminado, según la configuración<p>**1** Examen rápido<p>**2** Examen completo<p>**3** Examen personalizado de archivos y directorios.<p>CpuThrottling se ejecuta según las configuraciones de directiva|
|`-Trace [-Grouping #] [-Level #]`|Inicia el seguimiento de diagnóstico|
|`-GetFiles [-SupportLogLocation <path>]`|Recopila información de soporte técnico. Consulte "[Recopilación de datos de diagnóstico](collect-diagnostic-data.md)"|
|`-GetFilesDiagTrack`|Igual que `-GetFiles`, pero se genera en la carpeta DiagTrack temporal|
|`-RemoveDefinitions [-All]`|Restaura la inteligencia de seguridad instalada en una copia de seguridad anterior o en el conjunto predeterminado original.|
|`-RemoveDefinitions [-DynamicSignatures]`|Quita solo la inteligencia de seguridad descargada dinámicamente.|
|`-RemoveDefinitions [-Engine]`|Restaura el motor instalado anterior|
|`-SignatureUpdate [-UNC \|-MMPC]`|Comprueba si hay nuevas actualizaciones de inteligencia de seguridad|
|`-Restore  [-ListAll \|[[-Name <name>] [-All] \|[-FilePath <filePath>]] [-Path <path>]]`|Restaura o enumera elementos en cuarentena|
|`-AddDynamicSignature [-Path]`|Carga la inteligencia de seguridad dinámica|
|`-ListAllDynamicSignatures`|Enumera la inteligencia de seguridad dinámica cargada|
|`-RemoveDynamicSignature [-SignatureSetID]`|Quita la inteligencia de seguridad dinámica|
|`-CheckExclusion -path <path>`|Comprueba si se excluye una ruta de acceso|
|`-ValidateMapsConnection`|Comprueba que la red puede comunicarse con el servicio en la nube Microsoft Defender Antivirus. Este comando solo funcionará en Windows 10, versión 1703 o posterior.|

## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>Errores comunes en la ejecución de comandos a través de mpcmdrun.exe

En la tabla siguiente se enumeran los errores comunes que pueden producirse al usar la herramienta MpCmdRun.

|Mensaje de error|Posible motivo|
|---|---|
|**Error en ValidateMapsConnection (800106BA)** o **0x800106BA**|El servicio antivirus de Microsoft Defender está deshabilitado. Habilite el servicio e inténtelo de nuevo. Si necesita ayuda para volver a habilitar Microsoft Defender Antivirus, consulte [Reinstalación o habilitación de Microsoft Defender Antivirus en los puntos de conexión](switch-to-mde-phase-2.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints).<p> **SUGERENCIA**: En Windows 10 1909 o anterior, y Windows Server 2019 o versiones anteriores, el servicio se llamaba anteriormente *antivirus de Windows Defender*.|
|**0x80070667**|Ejecuta el `-ValidateMapsConnection` comando desde un equipo Windows 10 versión 1607 o anterior, o Windows Server 2016 o versiones anteriores. Ejecute el comando desde una máquina Windows 10 versión 1703 o posterior, o desde Windows Server 2019 o posterior.|
|**MpCmdRun no se reconoce como un comando interno o externo, un programa operable o un archivo por lotes.**|La herramienta debe ejecutarse desde `%ProgramFiles%\Windows Defender` o `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (donde `2012.4-0` puede diferir, ya que las actualizaciones de la plataforma son mensuales excepto en marzo).|
|**ValidateMapsConnection no pudo establecer una conexión a MAPS (hr=80070005 httpcode=450)**|El comando se intentó usar privilegios insuficientes. Use el símbolo del sistema (cmd.exe) como administrador.|
|**ValidateMapsConnection no pudo establecer una conexión a MAPS (hr=80070006 httpcode=451)**|El firewall está bloqueando la conexión o realizando la inspección SSL.|
|**ValidateMapsConnection no pudo establecer una conexión a MAPS (hr=80004005 httpcode=450)**|Posibles problemas relacionados con la red, como problemas de resolución de nombres|
|**ValidateMapsConnection no pudo establecer una conexión a MAPS (hr=0x80508015**|El firewall está bloqueando la conexión o realizando la inspección SSL.|
|**ValidateMapsConnection no pudo establecer una conexión a MAPS (hr=800722F0D)**|El firewall está bloqueando la conexión o realizando la inspección SSL.|
|**ValidateMapsConnection no pudo establecer una conexión a MAPS (hr=80072EE7 httpcode=451)**|El firewall está bloqueando la conexión o realizando la inspección SSL.|

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características iOS](ios-configure-features.md)

## <a name="see-also"></a>Vea también

- [Configurar las funciones del Antivirus de Microsoft Defender](configure-microsoft-defender-antivirus-features.md)
- [Configurar y validar las conexiones de red del Antivirus de Windows Defender](configure-network-connections-microsoft-defender-antivirus.md)
- [Temas de referencia para herramientas de administración y configuración](configuration-management-reference-microsoft-defender-antivirus.md)
