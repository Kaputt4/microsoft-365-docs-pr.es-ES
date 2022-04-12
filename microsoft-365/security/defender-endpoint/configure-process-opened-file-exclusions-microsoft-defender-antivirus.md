---
title: Configuración de exclusiones para archivos abiertos por procesos específicos
description: Puede excluir archivos de los exámenes si un proceso específico los ha abierto.
keywords: Antivirus de Microsoft Defender, proceso, exclusión, archivos, exámenes
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: e8cf075c0a35095f72d847a17f1fb48d590ad385
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788994"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a>Configuración de exclusiones para archivos abiertos por procesos


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows 

Puede excluir archivos abiertos por procesos específicos de Antivirus de Microsoft Defender exámenes. Consulte [Recomendaciones para definir exclusiones](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) antes de definir las listas de exclusión.

En este artículo se describe cómo configurar listas de exclusión.

## <a name="examples-of-exclusions"></a>Ejemplos de exclusiones

<br/><br/>

|Exclusión|Ejemplo|
|---|---|
|Cualquier archivo de la máquina abierto por cualquier proceso con un nombre de archivo específico|La especificación `test.exe` excluiría los archivos abiertos por: <p>`c:\sample\test.exe` <p> `d:\internal\files\test.exe`|
|Cualquier archivo en el equipo abierto por cualquier proceso en una carpeta específica|La especificación `c:\test\sample\*` excluiría los archivos abiertos por: <p> `c:\test\sample\test.exe` <p> `c:\test\sample\test2.exe` <p> `c:\test\sample\utility.exe`|
|Cualquier archivo de la máquina abierto por un proceso específico en una carpeta específica|La especificación `c:\test\process.exe` excluiría los archivos abiertos solo por `c:\test\process.exe`|

Al agregar un proceso a la lista de exclusión de procesos, Antivirus de Microsoft Defender no examinará los archivos abiertos por ese proceso, independientemente de dónde se encuentren los archivos. Sin embargo, el propio proceso se examinará a menos que también se haya agregado a la [lista de exclusión de archivos](configure-extension-file-exclusions-microsoft-defender-antivirus.md).

Las exclusiones solo se aplican a la [protección y supervisión en tiempo real always-on](configure-real-time-protection-microsoft-defender-antivirus.md). No se aplican a exámenes programados o a petición.

Los cambios realizados con directiva de grupo en las listas de exclusión **se mostrarán** en las listas de la [aplicación Seguridad de Windows](microsoft-defender-security-center-antivirus.md). Sin embargo, los cambios realizados en la aplicación Seguridad de Windows **no se mostrarán** en las listas de directiva de grupo.

Puede agregar, quitar y revisar las listas de exclusiones en directiva de grupo, Microsoft Endpoint Configuration Manager, Microsoft Intune y con la aplicación Seguridad de Windows, y puede usar caracteres comodín para personalizar aún más el Listas.

También puede usar cmdlets de PowerShell y WMI para configurar las listas de exclusión, incluida la revisión de las listas.

De forma predeterminada, los cambios locales realizados en las listas (por los usuarios con privilegios de administrador; los cambios realizados con PowerShell y WMI) se combinarán con las listas según se definan (e implementen) directiva de grupo, Configuration Manager o Intune. Las listas de directiva de grupo tendrán prioridad en el caso de conflictos.

Puede [configurar cómo se combinan las listas de exclusiones definidas local y globalmente](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) para permitir que los cambios locales invaliden la configuración de implementación administrada.

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a>Configurar la lista de exclusiones para los archivos abiertos por procesos especificados

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Use Microsoft Intune para excluir los archivos abiertos por procesos especificados de los exámenes.

Consulte [Configurar la configuración de restricciones de dispositivo en Microsoft Intune](/intune/device-restrictions-configure) y la [Configuración de restricciones de dispositivo de Antivirus de Microsoft Defender para Windows 10 en Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) para más información.

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Use Microsoft Endpoint Manager para excluir los archivos abiertos por procesos especificados de los exámenes.

Consulte [Creación e implementación de directivas antimalware: configuración de exclusión](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) para obtener más información sobre cómo configurar Microsoft Endpoint Manager (rama actual).

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Use directiva de grupo para excluir los archivos abiertos por procesos especificados de los exámenes.

1. En el equipo de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y haga clic en **Plantillas administrativas**.

3. Expanda el árbol para **Windows componentes \> Antivirus de Microsoft Defender \> exclusiones**.

4. Haga doble clic en **Exclusiones de proceso y** agregue las exclusiones:
    1. Establezca la opción **en Habilitado**.
    2. En la sección **Opciones** , haga clic en **Mostrar...**.
    3. Escriba cada proceso en su propia línea en la columna **Nombre de valor** . Consulte la tabla de ejemplo para ver los distintos tipos de exclusiones de procesos. Escriba **0** en la columna **Valor** para todos los procesos.

5. Haga clic en **Aceptar**.

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Uso de cmdlets de PowerShell para excluir archivos abiertos por procesos especificados de exámenes

El uso de PowerShell para agregar o quitar exclusiones de archivos abiertos por procesos requiere usar una combinación de tres cmdlets con el `-ExclusionProcess` parámetro . Los cmdlets están todos en el [módulo de Defender](/powershell/module/defender/).

El formato de los cmdlets es:

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

Se permite lo siguiente como \<cmdlet\>:

<br/><br/>

|Acción de configuración|Cmdlet de PowerShell|
|---|---|
|Creación o sobrescritura de la lista|`Set-MpPreference`|
|Agregar a la lista|`Add-MpPreference`|
|Quitar elementos de la lista|`Remove-MpPreference`|

> [!IMPORTANT]
> Si ha creado una lista, con `Set-MpPreference` o `Add-MpPreference`, el uso del `Set-MpPreference` cmdlet volverá a sobrescribir la lista existente.

Por ejemplo, el siguiente fragmento de código haría que los exámenes del antivirus de Microsoft Defender excluyan cualquier archivo abierto por el proceso especificado:

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

Para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender, consulte Administración de antivirus con cmdlets de PowerShell y [cmdlets de Antivirus de Microsoft Defender](/powershell/module/defender).

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Use Windows Management Instruction (WMI) para excluir de los exámenes los archivos abiertos por procesos especificados.

Use los [métodos **Set**, **Add** y **Remove** de la clase **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
ExclusionProcess
```

El uso de **Set**, **Add** y **Remove** es análogo a sus homólogos de PowerShell: `Set-MpPreference`, `Add-MpPreference`y `Remove-MpPreference`.

Para obtener más información y parámetros permitidos, consulte [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Use la aplicación Seguridad de Windows para excluir los archivos abiertos por procesos especificados de los exámenes.

Consulta [Agregar exclusiones en la aplicación Seguridad de Windows](microsoft-defender-security-center-antivirus.md) para obtener instrucciones.

## <a name="use-wildcards-in-the-process-exclusion-list"></a>Uso de caracteres comodín en la lista de exclusión de procesos

El uso de caracteres comodín en la lista de exclusión de procesos es diferente de su uso en otras listas de exclusión.

En concreto, no se puede usar el carácter comodín del signo de interrogación (`?`) y el carácter comodín de asterisco (`*`) solo se puede usar al final de una ruta de acceso completa. Todavía puede usar variables de entorno (como `%ALLUSERSPROFILE%`) como caracteres comodín al definir elementos en la lista de exclusión de procesos.

En la tabla siguiente se describe cómo se pueden usar los caracteres comodín en la lista de exclusión de procesos:

<br/><br/>

|Carácter comodín|Ejemplo de uso|Coincidencias de ejemplo|
|---|---|---|
|`*` (asterisco) <p> Reemplaza cualquier número de caracteres.|`C:\MyData\*`|Cualquier archivo abierto por `C:\MyData\file.exe`|
|Variables de entorno <p> La variable definida se rellena como una ruta de acceso cuando se evalúa la exclusión.|`%ALLUSERSPROFILE%\CustomLogFiles\file.exe`|Cualquier archivo abierto por `C:\ProgramData\CustomLogFiles\file.exe`|

## <a name="review-the-list-of-exclusions"></a>Revisar la lista de exclusiones

Puede recuperar los elementos de la lista de exclusión con MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings), [Intune](/intune/device-restrictions-configure) o la [aplicación Seguridad de Windows](microsoft-defender-security-center-antivirus.md).

Si usa PowerShell, puede recuperar la lista de dos maneras:

- Recupere el estado de todas las preferencias de Antivirus de Microsoft Defender. Cada una de las listas se mostrará en líneas independientes, pero los elementos de cada lista se combinarán en la misma línea.
- Escriba el estado de todas las preferencias en una variable y use esa variable para llamar solo a la lista específica que le interesa. Cada uso de `Add-MpPreference` se escribe en una nueva línea.

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>Validación de la lista de exclusión mediante MpCmdRun

Para comprobar las exclusiones con la [herramienta de línea de comandos dedicada mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use el siguiente comando:

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> La comprobación de exclusiones con MpCmdRun requiere Antivirus de Microsoft Defender versión 4.18.1812.3 de CAMP (publicada en diciembre de 2018) o posterior.

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>Revise la lista de exclusiones junto con todas las demás preferencias de Antivirus de Microsoft Defender mediante PowerShell.

Use el siguiente cmdlet:

```PowerShell
Get-MpPreference
```

Consulte [Uso de cmdlets de PowerShell para configurar y ejecutar cmdlets de Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [Antivirus de Microsoft Defender](/powershell/module/defender) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>Recuperación de una lista de exclusiones específica mediante PowerShell

Use el siguiente fragmento de código (escriba cada línea como un comando independiente); reemplace **WDAVprefs** por la etiqueta que quiera asignar a la variable:

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

Consulte [Uso de cmdlets de PowerShell para configurar y ejecutar cmdlets de Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [Antivirus de Microsoft Defender](/powershell/module/defender) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configuración de características de Defender para punto de conexión en Android](android-configure.md)
> - [Configuración de Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

## <a name="related-articles"></a>Artículos relacionados

- [Configuración y validación de exclusiones en exámenes de Antivirus de Microsoft Defender](configure-exclusions-microsoft-defender-antivirus.md)
- [Configuración y validación de exclusiones basadas en el nombre de archivo, la extensión y la ubicación de la carpeta](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Configuración de exclusiones de Antivirus de Microsoft Defender en Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Errores comunes para evitarlos cuando se definen exclusiones](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [Personalización, inicio y revisión de los resultados de los exámenes y correcciones de Antivirus de Microsoft Defender](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
