---
title: Configurar exclusiones para archivos abiertos por procesos específicos
description: Puede excluir archivos de los exámenes si se han abierto mediante un proceso específico.
keywords: Antivirus de Microsoft Defender, proceso, exclusión, archivos, exámenes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 2fdc646cf616ff6a6fa36a83be3d2b1dd0432fbe
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274621"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a>Configurar exclusiones para archivos abiertos por procesos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Puede excluir los archivos abiertos por procesos específicos de Antivirus de Microsoft Defender exámenes. Consulte [Recomendaciones para definir exclusiones antes](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) de definir las listas de exclusión.

En este artículo se describe cómo configurar listas de exclusión. 

## <a name="examples-of-exclusions"></a>Ejemplos de exclusiones

|Exclusión | Ejemplo: |
|---|---|
|Cualquier archivo del equipo que abra cualquier proceso con un nombre de archivo específico | Especificar `test.exe` excluiría los archivos abiertos por: <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|Cualquier archivo del equipo que abra cualquier proceso en una carpeta específica | Especificar `c:\test\sample\*` excluiría los archivos abiertos por:<br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|Cualquier archivo del equipo que se abra mediante un proceso específico en una carpeta específica | Especificar `c:\test\process.exe` excluiría los archivos solo abiertos por `c:\test\process.exe` |


Al agregar un proceso a la lista de exclusión de procesos, Antivirus de Microsoft Defender no examinará los archivos abiertos por ese proceso, independientemente de dónde se encuentran los archivos. Sin embargo, el proceso en sí se examinará a menos que también se haya agregado a la lista [de exclusión de archivos](configure-extension-file-exclusions-microsoft-defender-antivirus.md).

Las exclusiones solo se aplican a la protección y supervisión siempre activas [en tiempo real.](configure-real-time-protection-microsoft-defender-antivirus.md) No se aplican a exámenes programados o a petición.

Los cambios realizados con la directiva de grupo en las listas de exclusión **se** mostrarán en las listas de la [Seguridad de Windows aplicación](microsoft-defender-security-center-antivirus.md). Sin embargo, los cambios realizados en la aplicación Seguridad de Windows no **se mostrarán** en las listas de directivas de grupo.

Puedes agregar, quitar y revisar las listas de exclusiones en la directiva de grupo, Microsoft Endpoint Configuration Manager, Microsoft Intune y con la aplicación Seguridad de Windows, y puedes usar caracteres comodín para personalizar aún más las listas.

También puede usar cmdlets de PowerShell y WMI para configurar las listas de exclusión, incluida la revisión de las listas.

De forma predeterminada, los cambios locales realizados en las listas (por usuarios con privilegios de administrador; los cambios realizados con PowerShell y WMI) se combinarán con las listas definidas (e implementadas) por la directiva de grupo, Configuration Manager o Intune. Las listas de directivas de grupo tendrán prioridad en caso de conflictos.

Puede configurar cómo se combinan las listas de [exclusiones definidas local](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) y globalmente para permitir que los cambios locales invaliden la configuración de implementación administrada.

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a>Configurar la lista de exclusiones de archivos abiertos por procesos especificados

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Use Microsoft Intune para excluir los archivos abiertos por procesos especificados de los exámenes

Consulte [Configurar la configuración de restricciones de dispositivo en Microsoft Intune](/intune/device-restrictions-configure) y la [Configuración de restricciones de dispositivo de Antivirus de Microsoft Defender para Windows 10 en Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) para más información.

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Use Microsoft Endpoint Manager para excluir de los exámenes los archivos abiertos por procesos especificados

Vea [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) para obtener más información sobre cómo Microsoft Endpoint Manager (rama actual).

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Usar la directiva de grupo para excluir de los exámenes los archivos abiertos por procesos especificados

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directivas de grupo,** vaya a Configuración del equipo **y** haga clic en **Plantillas administrativas.**

3. Expanda el árbol para **Windows componentes > Antivirus de Microsoft Defender > exclusiones**.

4. Haga doble clic **en Exclusiones de proceso** y agregue las exclusiones:

    1. Establezca la opción en **Habilitado**.
    2. En la **sección Opciones,** haga clic **en Mostrar...**.
    3. Escriba cada proceso en su propia línea en la **columna Nombre de** valor. Vea la tabla de ejemplo para ver los distintos tipos de exclusiones de procesos.  Escriba **0 en** la **columna Valor** para todos los procesos.

5. Haga clic en **Aceptar**.

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Usar cmdlets de PowerShell para excluir archivos abiertos por procesos especificados de exámenes

El uso de PowerShell para agregar o quitar exclusiones de archivos abiertos por procesos requiere el uso de una combinación de tres cmdlets con el `-ExclusionProcess` parámetro. Los cmdlets están todos en el [módulo Defender](/powershell/module/defender/).

El formato de los cmdlets es:

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

Se permite lo siguiente como \<cmdlet> :

|Acción de configuración | Cmdlet de PowerShell |
|---|---|
|Crear o sobrescribir la lista | `Set-MpPreference` |
|Agregar a la lista | `Add-MpPreference` |
|Quitar elementos de la lista | `Remove-MpPreference` |

>[!IMPORTANT]
>Si ha creado una lista, ya sea con o con el `Set-MpPreference` `Add-MpPreference` cmdlet de nuevo `Set-MpPreference` sobrescribirá la lista existente.

Por ejemplo, el siguiente fragmento de código provocaría que los exámenes antivirus de Microsoft Defender excluyan cualquier archivo abierto por el proceso especificado:

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

Para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender, vea Manage antivirus with PowerShell cmdlets and [Antivirus de Microsoft Defender cmdlets](/powershell/module/defender).

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Use Windows Management Instruction (WMI) para excluir de los exámenes los archivos abiertos por procesos especificados

Utilice los [ **métodos Set**, **Add** y **Remove** de **la clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
ExclusionProcess
```

El uso **de Set**, **Add** y **Remove** es análogo a sus equivalentes en PowerShell: , `Set-MpPreference` y `Add-MpPreference` `Remove-MpPreference` .

Para obtener más información y parámetros [permitidos, vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Usar la Seguridad de Windows para excluir los archivos abiertos por procesos especificados de los exámenes

Consulta [Agregar exclusiones en la aplicación Seguridad de Windows para](microsoft-defender-security-center-antivirus.md) obtener instrucciones.

## <a name="use-wildcards-in-the-process-exclusion-list"></a>Usar caracteres comodín en la lista de exclusión de procesos

El uso de caracteres comodín en la lista de exclusión de procesos es diferente de su uso en otras listas de exclusión.

En concreto, no puede usar el signo de interrogación ( ) comodín y el asterisco ( ) comodín solo se puede usar al final `?` de una ruta de acceso `*` completa. Todavía puede usar variables de entorno (como ) como caracteres comodín al `%ALLUSERSPROFILE%` definir elementos en la lista de exclusión de procesos.

En la tabla siguiente se describe cómo se pueden usar los caracteres comodín en la lista de exclusión de procesos:

|Carácter comodín | Uso de ejemplo | Coincidencias de ejemplo |
|:---|:---|:---|
|`*` (asterisco) <br/><br/> Reemplaza cualquier número de caracteres | `C:\MyData\*` | Cualquier archivo abierto por `C:\MyData\file.exe` |
|Variables de entorno <br/><br/> La variable definida se rellena como una ruta de acceso cuando se evalúa la exclusión | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | Cualquier archivo abierto por `C:\ProgramData\CustomLogFiles\file.exe` |

## <a name="review-the-list-of-exclusions"></a>Revisar la lista de exclusiones

Puede recuperar los elementos de la lista de exclusión con MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager,](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) [Intune](/intune/device-restrictions-configure)o la [Seguridad de Windows aplicación](microsoft-defender-security-center-antivirus.md).

Si usa PowerShell, puede recuperar la lista de dos maneras:

- Recupere el estado de todas las Antivirus de Microsoft Defender preferencias. Cada una de las listas se mostrará en líneas independientes, pero los elementos de cada lista se combinarán en la misma línea.
- Escribe el estado de todas las preferencias en una variable y usa esa variable para llamar solo a la lista específica que te interesa. Cada uso de `Add-MpPreference` se escribe en una nueva línea.

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>Validar la lista de exclusión mediante MpCmdRun

Para comprobar las exclusiones con la herramienta de línea de [comandos ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)mpcmdrun.exe, use el siguiente comando:

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> La comprobación de exclusiones con MpCmdRun requiere Antivirus de Microsoft Defender versión 4.18.1812.3 de CAMP (publicada en diciembre de 2018) o posterior.


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>Revise la lista de exclusiones junto con el resto de Antivirus de Microsoft Defender preferencias mediante PowerShell

Use el siguiente cmdlet:

```PowerShell
Get-MpPreference
```

Consulte [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>Recuperar una lista de exclusiones específica mediante PowerShell

Use el siguiente fragmento de código (escriba cada línea como un comando independiente); reemplace **WDAVprefs** por la etiqueta que desee nombrar la variable:

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

Consulte [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.

## <a name="related-articles"></a>Artículos relacionados

- [Configurar y validar exclusiones en Antivirus de Microsoft Defender exámenes](configure-exclusions-microsoft-defender-antivirus.md)
- [Configurar y validar exclusiones según el nombre de archivo, la extensión y la ubicación de la carpeta](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Configurar Antivirus de Microsoft Defender exclusiones en Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Errores comunes para evitarlos cuando se definen exclusiones](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [Personalizar, iniciar y revisar los resultados de Antivirus de Microsoft Defender análisis y corrección](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)