---
title: Usar la línea de comandos para administrar Antivirus de Microsoft Defender
description: Ejecute los exámenes de Antivirus de Microsoft Defender y configure la protección de próxima generación con una utilidad de línea de comandos dedicada.
keywords: ejecutar el examen de Windows Defender, ejecutar el examen antivirus desde la línea de comandos, ejecutar el examen de Windows Defender desde la línea de comandos, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 03/19/2021
ms.technology: mde
ms.openlocfilehash: 1b357f7c1e02211f3949383a380666cb7444f814
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764632"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>Configurar y administrar Antivirus de Microsoft Defender con la mpcmdrun.exe de línea de comandos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Puede realizar varias funciones de Antivirus de Microsoft Defender con la herramienta de línea de comandos dedicada **mpcmdrun.exe**. Esta utilidad es útil cuando desea automatizar el uso de Antivirus de Microsoft Defender. Puede encontrar la utilidad en `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Debe ejecutarlo desde un símbolo del sistema.

> [!NOTE]
> Es posible que deba abrir una versión de nivel de administrador del símbolo del sistema. Cuando busque símbolo **del sistema en** el menú Inicio, elija Ejecutar como **administrador**.
> Si está ejecutando una versión actualizada de Microsoft Defender Platform, ejecute `**MpCmdRun**` desde la siguiente ubicación: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .

La utilidad tiene los siguientes comandos:

```console
MpCmdRun.exe [command] [-options]
```
Aquí le mostramos un ejemplo:

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| Comando  | Descripción   |
|:----|:----|
| `-?`**o**`-h`   | Muestra todas las opciones disponibles para esta herramienta |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | Busca software malintencionado. Los valores **de ScanType** son: **0** Valor predeterminado, según la configuración, **-1** Examen rápido, **-2** Examen completo, **-3** Examen personalizado de archivos y directorios.  CpuThrottling respetará la limitación de CPU configurada desde la directiva |
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
| `-ValidateMapsConnection` | Comprueba que la red puede comunicarse con el servicio en la nube antivirus de Microsoft Defender. Este comando solo funcionará en Windows 10, versión 1703 o posterior.|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>Errores comunes al ejecutar comandos mediante mpcmdrun.exe 

|Mensaje de error | Posible motivo
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | El servicio Antivirus de Microsoft Defender está deshabilitado. Habilite el servicio e inténtelo de nuevo. <br>   **Nota:**  En Windows 10 1909 o versiones anteriores, y Windows Server 2019 o versiones anteriores, el servicio se llamaba servicio "Windows Defender Antivirus".|
| `0x80070667` | Estás ejecutando el comando desde un equipo que es `-ValidateMapsConnection` Windows 10 versión 1607 o posterior, o Windows Server 2016 o posterior. Ejecute el comando desde un equipo que sea Windows 10 versión 1703 o posterior, o Windows Server 2019 o posterior.|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | La herramienta debe ejecutarse desde: o (donde puede diferir dado que las actualizaciones de la plataforma `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` son `2012.4-0` mensuales excepto marzo)|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | No hay suficientes privilegios. Use el símbolo del sistema (cmd.exe) como administrador.|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | El firewall bloquea la conexión o realiza una inspección SSL. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | Posibles problemas relacionados con la red, como problemas de resolución de nombres|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | El firewall bloquea la conexión o realiza una inspección SSL. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | El firewall bloquea la conexión o realiza una inspección SSL. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | El firewall bloquea la conexión o realiza una inspección SSL. |

## <a name="see-also"></a>Vea también

- [Configurar características de Antivirus de Microsoft Defender](configure-microsoft-defender-antivirus-features.md)
- [Administrar antivirus de Microsoft Defender en su empresa](configuration-management-reference-microsoft-defender-antivirus.md)
- [Temas de referencia para herramientas de administración y configuración](configuration-management-reference-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)