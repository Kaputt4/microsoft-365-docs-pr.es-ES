---
title: Use la línea de comandos para administrar Antivirus de Microsoft Defender
description: Ejecute Antivirus de Microsoft Defender y configure la protección de próxima generación con una utilidad de línea de comandos dedicada.
keywords: ejecutar el examen de Windows Defender, ejecutar el examen antivirus desde la línea de comandos, ejecutar el examen de Windows Defender desde la línea de comandos, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: efeb49b2741bdc45f7924032c2deb8a27458ca29
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289420"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>Configurar y administrar Antivirus de Microsoft Defender con la mpcmdrun.exe de línea de comandos

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Puede realizar varias funciones en Antivirus de Microsoft Defender con la herramienta de línea de comandos dedicada **mpcmdrun.exe**. Esta utilidad es útil cuando se desea automatizar Antivirus de Microsoft Defender tareas. Puede encontrar la utilidad en `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Ejecutarlo desde un símbolo del sistema.

> [!TIP]
> Es posible que deba abrir una versión de nivel de administrador del símbolo del sistema. Cuando busque el símbolo **del sistema en** el menú Inicio, elija Ejecutar como **administrador**. Si está ejecutando una versión actualizada de Microsoft Defender Platform, ejecute `MpCmdRun` desde la siguiente ubicación: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` . Para obtener más información acerca de la plataforma antimalware, [vea Antivirus de Microsoft Defender actualizaciones y líneas base](manage-updates-baselines-microsoft-defender-antivirus.md).

La utilidad MpCmdRun usa la siguiente sintaxis:

```console
MpCmdRun.exe [command] [-options]
```

Aquí le mostramos un ejemplo:

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

En nuestro ejemplo, la utilidad MpCmdRun inicia un examen antivirus completo en el dispositivo.

## <a name="commands"></a>Comandos

| Comando  | Descripción   |
|:----|:----|
| `-?` **o** `-h`   | Muestra todas las opciones disponibles para la herramienta MpCmdRun |
| `-Scan [-ScanType [<value>]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | Busca software malintencionado. Los valores **de ScanType** son:<p>**0** Valor predeterminado, según la configuración<p>**1** Examen rápido<p>**2** Examen completo<p>**3** Examen personalizado de archivos y directorios.<p>CpuThrottling se ejecuta según las configuraciones de directivas |
| `-Trace [-Grouping #] [-Level #]` | Inicia el seguimiento de diagnóstico |
| `-GetFiles [-SupportLogLocation <path>]` | Recopila información de soporte técnico. Vea '[collecting diagnostic data](collect-diagnostic-data.md)'  |
| `-GetFilesDiagTrack`  | Igual que `-GetFiles` , pero salidas a la carpeta temporal de DiagTrack |
| `-RemoveDefinitions [-All]` | Restaura la inteligencia de seguridad instalada a una copia de seguridad anterior o al conjunto predeterminado original |
| `-RemoveDefinitions [-DynamicSignatures]` | Quita solo la inteligencia de seguridad descargada dinámicamente |
| `-RemoveDefinitions [-Engine]` | Restaura el motor instalado anterior |
| `-SignatureUpdate [-UNC \| -MMPC]` | Comprueba si hay nuevas actualizaciones de inteligencia de seguridad |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | Restaura o enumera elementos en cuarentena |
| `-AddDynamicSignature [-Path]` | Carga inteligencia de seguridad dinámica |
| `-ListAllDynamicSignatures` | Enumera la inteligencia de seguridad dinámica cargada |
| `-RemoveDynamicSignature [-SignatureSetID]` | Quita la inteligencia de seguridad dinámica |
| `-CheckExclusion -path <path>` | Comprueba si se excluye una ruta de acceso |
| `-ValidateMapsConnection` | Comprueba que la red se puede comunicar con el Antivirus de Microsoft Defender de nube. Este comando solo funcionará en Windows 10 versión 1703 o posterior.|

## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>Errores comunes al ejecutar comandos mediante mpcmdrun.exe 

En la tabla siguiente se enumeran los errores comunes que pueden producirse al usar la herramienta MpCmdRun.

|Mensaje de error | Posible motivo |
|:----|:----|
| **Error en ValidateMapsConnection (800106BA)** **o 0x800106BA** | El Antivirus de Microsoft Defender está deshabilitado. Habilite el servicio e inténtelo de nuevo. Si necesita ayuda para volver a habilitar Antivirus de Microsoft Defender, vea [Reinstall/enable Antivirus de Microsoft Defender on your endpoints](switch-to-microsoft-defender-setup.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints).<p> **SUGERENCIA:** En Windows 10 1909 o versiones anteriores y Windows Server 2019 o versiones anteriores, el servicio se llamaba anteriormente *Antivirus de Windows Defender*. |
| **0x80070667** | Está ejecutando el comando desde un equipo que Windows 10 versión 1607 o anterior, o Windows Server 2016 `-ValidateMapsConnection` o posterior. Ejecute el comando desde un equipo que Windows 10 versión 1703 o posterior, o Windows Server 2019 o posterior.|
| **MpCmdRun no se reconoce como un comando interno o externo, un programa operable o un archivo por lotes.** | La herramienta debe ejecutarse desde cualquiera o (donde podría diferir ya que las actualizaciones de la plataforma `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` son `2012.4-0` mensuales excepto marzo)|
| **ValidateMapsConnection no pudo establecer una conexión a MAPS (hr=80070005 httpcode=450)** | El comando se intentó con privilegios insuficientes. Use el símbolo del sistema (cmd.exe) como administrador.|
| **ValidateMapsConnection no pudo establecer una conexión a MAPS (hr=80070006 httpcode=451)** | El firewall bloquea la conexión o realiza una inspección SSL. |
| **ValidateMapsConnection no pudo establecer una conexión a MAPS (hr=80004005 httpcode=450)** | Posibles problemas relacionados con la red, como problemas de resolución de nombres|
| **ValidateMapsConnection no pudo establecer una conexión a MAPS (hr=0x80508015** | El firewall bloquea la conexión o realiza una inspección SSL. |
| **ValidateMapsConnection no pudo establecer una conexión a MAPS (hr=800722F0D** | El firewall bloquea la conexión o realiza una inspección SSL. |
| **ValidateMapsConnection no pudo establecer una conexión a MAPS (hr=80072EE7 httpcode=451)** | El firewall bloquea la conexión o realiza una inspección SSL. |

## <a name="see-also"></a>Vea también

- [Configurar las funciones del Antivirus de Microsoft Defender](configure-microsoft-defender-antivirus-features.md)
- [Configurar y validar las conexiones de red del Antivirus de Windows Defender](configure-network-connections-microsoft-defender-antivirus.md)
- [Temas de referencia para herramientas de administración y configuración](configuration-management-reference-microsoft-defender-antivirus.md)
