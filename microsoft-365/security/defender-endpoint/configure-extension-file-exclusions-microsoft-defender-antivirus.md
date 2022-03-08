---
title: Configurar y validar exclusiones en función de la extensión, el nombre o la ubicación
description: Excluir archivos de Antivirus de Microsoft Defender en función de su extensión de archivo, nombre de archivo o ubicación.
keywords: exclusiones, archivos, extensión, tipo de archivo, nombre de carpeta, nombre de archivo, exámenes
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.date: 02/27/2022
ms.collection: M365-security-compliance
ms.openlocfilehash: be22c80e51551b5de2a2aeed2f0dff0db9a8481f
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63323659"
---
# <a name="configure-and-validate-exclusions-based-on-file-extension-and-folder-location"></a>Configurar y validar exclusiones en función de la extensión de archivo y la ubicación de la carpeta

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

Puede definir exclusiones para Antivirus de Microsoft Defender que se aplican a exámenes programados[, exámenes](schedule-antivirus-scans.md) a petición [](run-scan-microsoft-defender-antivirus.md)y protección y supervisión siempre activas [en tiempo real](configure-real-time-protection-microsoft-defender-antivirus.md). **Por lo general, no es necesario aplicar exclusiones**. Si necesita aplicar exclusiones, puede elegir entre varios tipos diferentes:

- Exclusiones basadas en extensiones de archivo y ubicaciones de carpetas (descritas en este artículo)
- [Exclusiones de archivos abiertos por procesos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

> [!IMPORTANT]
> Antivirus de Microsoft Defender exclusiones no se aplican a otras funcionalidades de Microsoft Defender para endpoints, como [detección y respuesta de puntos de conexión (EDR),](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)reglas de reducción de superficie de ataque [(ASR)](/microsoft-365/security/defender-endpoint/attack-surface-reduction) y acceso controlado a [carpetas](/microsoft-365/security/defender-endpoint/controlled-folders). Los archivos que se excluyen mediante los métodos descritos en este artículo aún pueden desencadenar EDR alertas y otras detecciones.
> Para excluir archivos de forma general, agrégálos a los indicadores [personalizados](/microsoft-365/security/defender-endpoint/manage-indicators) de Microsoft Defender para endpoint.

## <a name="before-you-begin"></a>Antes de empezar...

Consulte [Recomendaciones para definir exclusiones antes](configure-exclusions-microsoft-defender-antivirus.md) de definir las listas de exclusión.

## <a name="exclusion-lists"></a>Listas de exclusión

Para excluir determinados archivos de Antivirus de Microsoft Defender exámenes, modifique las listas de exclusión. Antivirus de Microsoft Defender incluye muchas exclusiones automáticas basadas en comportamientos conocidos del sistema operativo y archivos de administración típicos, como los que se usan en la administración empresarial, la administración de bases de datos y otros escenarios y situaciones empresariales.

> [!NOTE]
> Las exclusiones también se aplican a las detecciones de aplicaciones potencialmente no deseadas (PUA).
>
> Las exclusiones automáticas solo se aplican Windows Server 2016 y posteriores. Estas exclusiones no son visibles en la aplicación Seguridad de Windows y en PowerShell.

En la tabla siguiente se enumeran algunos ejemplos de exclusiones basadas en la extensión de archivo y la ubicación de la carpeta. 
<br/><br/>

|Exclusión|Ejemplos|Lista de exclusión|
|---|---|---|
|Cualquier archivo con una extensión específica|Todos los archivos con la extensión especificada, en cualquier lugar del equipo. <p> Sintaxis válida: `.test` y `test`|Exclusiones de extensión|
|Cualquier archivo de una carpeta específica|Todos los archivos de la `c:\test\sample` carpeta|Exclusiones de archivos y carpetas|
|Un archivo específico en una carpeta específica|Solo el `c:\sample\sample.test` archivo|Exclusiones de archivos y carpetas|
|Un proceso específico|El archivo ejecutable `c:\test\process.exe`|Exclusiones de archivos y carpetas|

## <a name="characteristics-of-exclusion-lists"></a>Características de las listas de exclusión

- Las exclusiones de carpetas se aplican a todos los archivos y carpetas de esa carpeta, a menos que la subcarpeta sea un punto de repetición. Las subcarpetas de punto de repetición deben excluirse por separado.
- Las extensiones de archivo se aplican a cualquier nombre de archivo con la extensión definida si no se define una ruta de acceso o carpeta.

## <a name="important-notes-about-exclusions-based-on-file-extensions-and-folder-locations"></a>Notas importantes sobre exclusiones basadas en extensiones de archivo y ubicaciones de carpetas

- El uso de caracteres comodín como el asterisco (\*) modificará la forma en que se interpretan las reglas de exclusión. Vea la [sección Usar caracteres comodín](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) en la sección Ruta de acceso de carpeta y nombre de archivo o listas de exclusión de extensión para obtener información importante sobre cómo funcionan los caracteres comodín.

- No excluya las unidades de red asignadas. Especifique la ruta de acceso de red real.

- Las carpetas que son puntos de reanco que se crean después de que se inicie el servicio Antivirus de Microsoft Defender y que se hayan agregado a la lista de exclusión no se incluirán. Reinicie el servicio (reiniciando Windows) para que los nuevos puntos de reanualción se reconozcan como un destino de exclusión válido.

- Las exclusiones se aplican [a los exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md), los exámenes [a](run-scan-microsoft-defender-antivirus.md) petición y la protección [en tiempo real](configure-real-time-protection-microsoft-defender-antivirus.md), pero no en Defender para endpoint. Para definir exclusiones en Defender para endpoint, usa [indicadores personalizados](manage-indicators.md).

- De forma predeterminada, los cambios locales realizados en las listas (por usuarios con privilegios de administrador, incluidos los cambios realizados con PowerShell y WMI) se combinarán con las listas definidas (e implementadas) por la directiva de grupo, Configuration Manager o Intune. Las listas de directivas de grupo tienen prioridad cuando hay conflictos. Además, los cambios en la lista de exclusión realizados con la directiva de grupo están visibles en [la Seguridad de Windows aplicación](microsoft-defender-security-center-antivirus.md).

- Para permitir que los cambios locales invaliden la configuración de implementación administrada, configure cómo se combinan las listas de [exclusiones definidas local y globalmente](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists).

## <a name="configure-the-list-of-exclusions-based-on-folder-name-or-file-extension"></a>Configurar la lista de exclusiones según el nombre de carpeta o la extensión de archivo

Puede elegir entre varios métodos para definir exclusiones para Antivirus de Microsoft Defender.

### <a name="use-intune-to-configure-file-name-folder-or-file-extension-exclusions"></a>Usar Intune para configurar exclusiones de nombre de archivo, carpeta o extensión de archivo

Consulte los siguientes artículos:

- [Configurar restricciones de dispositivos en Microsoft Intune](/intune/device-restrictions-configure)
- [Antivirus de Microsoft Defender de restricción de dispositivos para Windows 10 en Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-file-name-folder-or-file-extension-exclusions"></a>Usar Configuration Manager para configurar exclusiones de nombre de archivo, carpeta o extensión de archivo

Vea [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) para obtener más información sobre cómo Microsoft Endpoint Manager (rama actual).

### <a name="use-group-policy-to-configure-folder-or-file-extension-exclusions"></a>Usar la directiva de grupo para configurar exclusiones de extensiones de archivo o carpetas

> [!NOTE]
> Si especifica una ruta de acceso completa a un archivo, solo se excluye ese archivo. Si se define una carpeta en la exclusión, se excluyen todos los archivos y subdirectorios de esa carpeta.

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón secundario en el objeto de directiva de grupo que quiera configurar y seleccione **Editar**.

2. En el **Editor de administración de directivas de grupo** , vaya **a Configuración del equipo y** seleccione **Plantillas administrativas**.

3. Expanda el árbol para **Windows componentes Antivirus de Microsoft Defender** \>  \> **exclusiones**.

4. Abra la **configuración Exclusiones de ruta de** acceso para su edición y agregue las exclusiones.
    1. Establezca la opción en **Habilitado**.
    2. En la **sección Opciones** , seleccione **Mostrar**.
    3. Especifique cada carpeta en su propia línea en la **columna Nombre de** valor.
    4. Si va a especificar un archivo, asegúrese de escribir una ruta de acceso completa al archivo, incluida la letra de unidad, la ruta de acceso de carpeta, el nombre del archivo y la extensión. 
    5. Escriba **0** en la **columna** Valor.

5. Elija **Aceptar**.

6. Abra la **configuración Exclusiones de extensión** para editar y agregue las exclusiones.
    1. Establezca la opción en **Habilitado**.
    2. En la **sección Opciones** , seleccione **Mostrar**.
    3. Escriba cada extensión de archivo en su propia línea en la **columna Nombre de** valor.
    4. Escriba **0** en la **columna** Valor.

7. Elija **Aceptar**.

<a id="ps"></a>

### <a name="use-powershell-cmdlets-to-configure-file-name-folder-or-file-extension-exclusions"></a>Usar cmdlets de PowerShell para configurar exclusiones de nombre de archivo, carpeta o extensión de archivo

El uso de PowerShell para agregar o quitar exclusiones de archivos en función de la extensión, ubicación o nombre de archivo requiere el uso de una combinación de tres cmdlets y el parámetro de lista de exclusión adecuado. Los cmdlets están todos en el [módulo Defender](/powershell/module/defender/).

El formato de los cmdlets es el siguiente:

```PowerShell
<cmdlet> -<exclusion list> "<item>"
```

En la tabla siguiente se enumeran los cmdlets que puede usar en la `<cmdlet>` parte del cmdlet de PowerShell:

<br/><br/>

|Acción de configuración|Cmdlet de PowerShell|
|:---|:---|
|Crear o sobrescribir la lista|`Set-MpPreference`|
|Agregar a la lista|`Add-MpPreference`|
|Quitar elemento de la lista|`Remove-MpPreference`|

En la tabla siguiente se enumeran los valores que puede usar en la `<exclusion list>` parte del cmdlet de PowerShell:

<br/><br/>

|Tipo de exclusión|Parámetro de PowerShell|
|---|---|
|Todos los archivos con una extensión de archivo especificada|`-ExclusionExtension`|
|Todos los archivos de una carpeta (incluidos los archivos en subdirectorios) o un archivo específico|`-ExclusionPath`|

> [!IMPORTANT]
> Si ha creado una lista, ya sea con `Set-MpPreference` o `Add-MpPreference`con `Set-MpPreference` el cmdlet de nuevo sobrescribirá la lista existente.

Por ejemplo, el siguiente fragmento de código haría que Antivirus de Microsoft Defender análisis excluyan cualquier archivo con la extensión `.test` de archivo:

```PowerShell
Add-MpPreference -ExclusionExtension ".test"
```

> [!TIP]
> Para obtener más información, vea [Usar cmdlets de PowerShell para configurar y ejecutar el Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [Cmdlets de Antivirus de Microsoft Defender](/powershell/module/defender/).

### <a name="use-windows-management-instrumentation-wmi-to-configure-file-name-folder-or-file-extension-exclusions"></a>Usar Windows Instrumental de administración de archivos (WMI) para configurar exclusiones de nombre de archivo, carpeta o extensión de archivo

Use los [métodos Set, Add y Remove de la clase MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
ExclusionExtension
ExclusionPath
```

El **uso de Set**, **Add** y **Remove** es análogo a sus equivalentes en PowerShell: `Set-MpPreference`, `Add-MpPreference`y `Remove-MpPreference`.

> [!TIP]
> Para obtener más información, [vea Windows Defender API de WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

<a id="man-tools"></a>

### <a name="use-the-windows-security-app-to-configure-file-name-folder-or-file-extension-exclusions"></a>Usar la aplicación Seguridad de Windows para configurar exclusiones de nombre de archivo, carpeta o extensión de archivo

Consulta [Agregar exclusiones en la aplicación Seguridad de Windows para](microsoft-defender-security-center-antivirus.md) obtener instrucciones.

<a id="wildcards"></a>

## <a name="use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>Usar caracteres comodín en el nombre de archivo y la ruta de acceso de carpeta o listas de exclusión de extensión

Puede usar el asterisco `*`, el signo `?`de interrogación o las variables de entorno ( `%ALLUSERSPROFILE%`como ) como caracteres comodín al definir elementos en la lista de exclusión de ruta de acceso de carpeta o nombre de archivo. La forma en que se interpretan estos caracteres comodín difiere de su uso habitual en otras aplicaciones e idiomas. Asegúrese de leer esta sección para comprender sus limitaciones específicas.

> [!IMPORTANT]
> Existen limitaciones clave y escenarios de uso para estos caracteres comodín:
>
> - El uso de variables de entorno se limita a las variables de máquina y las aplicables a los procesos que se ejecutan como una cuenta NT AUTHORITY\SYSTEM.
> - Solo puede usar un máximo de seis caracteres comodín por entrada.
> - No puede usar un comodín en lugar de una letra de unidad.
> - Un asterisco `*` en una exclusión de carpeta se mantiene en su lugar para una sola carpeta. Use varias instancias de para `\*\` indicar varias carpetas anidadas con nombres no especificados.
> - Actualmente, Microsoft Endpoint Configuration Manager admite caracteres comodín (como `*` o `?`).
    
En la tabla siguiente se describe cómo se pueden usar los caracteres comodín y se proporcionan algunos ejemplos.

<br/><br/>

|Carácter comodín|Ejemplos|
|---|---|
|`*` (asterisco) <p> En **las inclusiones** de nombre de archivo y extensión de archivo, el asterisco reemplaza cualquier número de caracteres y solo se aplica a los archivos de la última carpeta definida en el argumento. <p> En **las exclusiones de carpetas**, el asterisco reemplaza a una sola carpeta. Use varias barras `*` diagonales de carpeta `\` para indicar varias carpetas anidadas. Después de hacer coincidir el número de carpetas comodín y con nombre, también se incluyen todas las subcarpetas.|`C:\MyData\*.txt` incluye `C:\MyData\notes.txt` <p> `C:\somepath\*\Data` incluye cualquier archivo y `C:\somepath\Archives\Data` sus subcarpetas, y `C:\somepath\Authorized\Data` sus subcarpetas <p> `C:\Serv\*\*\Backup` incluye cualquier archivo y `C:\Serv\Primary\Denied\Backup` sus subcarpetas y `C:\Serv\Secondary\Allowed\Backup` sus subcarpetas|
|`?` (signo de interrogación)  <p> En **las inclusiones** de nombre de archivo y extensión de archivo, el signo de interrogación reemplaza a un solo carácter y solo se aplica a los archivos de la última carpeta definida en el argumento. <p> En **las exclusiones de carpetas**, el signo de interrogación reemplaza un solo carácter en un nombre de carpeta. Después de hacer coincidir el número de carpetas comodín y con nombre, también se incluyen todas las subcarpetas.|`C:\MyData\my?.zip` incluye `C:\MyData\my1.zip` <p> `C:\somepath\?\Data` incluye cualquier archivo en `C:\somepath\P\Data` y sus subcarpetas  <p> `C:\somepath\test0?\Data` incluiría cualquier archivo en `C:\somepath\test01\Data` y sus subcarpetas|
|Variables de entorno <p> La variable definida se rellena como una ruta de acceso cuando se evalúa la exclusión.|`%ALLUSERSPROFILE%\CustomLogFiles` incluiría `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`|

> [!IMPORTANT]
> Si mezcla un argumento de exclusión de archivos con un argumento de exclusión de carpeta, las reglas se detendrán en la coincidencia del argumento de archivo en la carpeta coincidente y no buscarán coincidencias de archivos en ninguna subcarpeta.
>
> Por ejemplo, puede excluir todos los archivos que comiencen por "date" `c:\data\final\marked` en las carpetas y `c:\data\review\marked` mediante el argumento rule `c:\data\*\marked\date*`.
>
> Sin embargo, este argumento no coincidirá con ningún archivo de subcarpetas en o `c:\data\final\marked` `c:\data\review\marked`.

<a id="review"></a>

### <a name="system-environment-variables"></a>Variables de entorno del sistema

En la tabla siguiente se enumeran y describen las variables de entorno de cuentas del sistema.

<br/><br/>

|Esta variable de entorno del sistema...|Redirige a esto|
|---|---|
|`%APPDATA%`|`C:\Users\UserName.DomainName\AppData\Roaming`|
|`%APPDATA%\Microsoft\Internet Explorer\Quick Launch`|`C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch`|
|`%APPDATA%\Microsoft\Windows\Start Menu`|`C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu`|
|`%APPDATA%\Microsoft\Windows\Start Menu\Programs`|`C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu\Programs`|
|`%LOCALAPPDATA%`|`C:\Windows\System32\config\systemprofile\AppData\Local`|
|`%ProgramData%`|`C:\ProgramData`|
|`%ProgramFiles%`|`C:\Program Files`|
|`%ProgramFiles%\Common Files`|`C:\Program Files\Common Files`|
|`%ProgramFiles%\Windows Sidebar\Gadgets`|`C:\Program Files\Windows Sidebar\Gadgets`|
|`%ProgramFiles%\Common Files`|`C:\Program Files\Common Files`|
|`%ProgramFiles(x86)%`|`C:\Program Files (x86)`|
|`%ProgramFiles(x86)%\Common Files`|`C:\Program Files (x86)\Common Files`|
|`%SystemDrive%`|`C:`|
|`%SystemDrive%\Program Files`|`C:\Program Files`|
|`%SystemDrive%\Program Files (x86)`|`C:\Program Files (x86)`|
|`%SystemDrive%\Users`|`C:\Users`|
|`%SystemDrive%\Users\Public`|`C:\Users\Public`|
|`%SystemRoot%`|`C:\Windows`|
|`%windir%`|`C:\Windows`|
|`%windir%\Fonts`|`C:\Windows\Fonts`|
|`%windir%\Resources`|`C:\Windows\Resources`|
|`%windir%\resources\0409`|`C:\Windows\resources\0409`|
|`%windir%\system32`|`C:\Windows\System32`|
|`%ALLUSERSPROFILE%`|`C:\ProgramData`|
|`%ALLUSERSPROFILE%\Application Data`|`C:\ProgramData\Application Data`|
|`%ALLUSERSPROFILE%\Documents`|`C:\ProgramData\Documents`|
|`%ALLUSERSPROFILE%\Documents\My Music\Sample Music`|`C:\ProgramData\Documents\My Music\Sample Music`|
|`%ALLUSERSPROFILE%\Documents\My Music`|`C:\ProgramData\Documents\My Music`|
|`%ALLUSERSPROFILE%\Documents\My Pictures`|`C:\ProgramData\Documents\My Pictures`|
|`%ALLUSERSPROFILE%\Documents\My Pictures\Sample Pictures`|`C:\ProgramData\Documents\My Pictures\Sample Pictures`|
|`%ALLUSERSPROFILE%\Documents\My Videos`|`C:\ProgramData\Documents\My Videos`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\DeviceMetadataStore`|`C:\ProgramData\Microsoft\Windows\DeviceMetadataStore`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\GameExplorer`|`C:\ProgramData\Microsoft\Windows\GameExplorer`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Ringtones`|`C:\ProgramData\Microsoft\Windows\Ringtones`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu`|`C:\ProgramData\Microsoft\Windows\Start Menu`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs`|`C:\ProgramData\Microsoft\Windows\Start Menu\Programs`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Administrative Tools`|`C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Administrative Tools`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\StartUp`|`C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Templates`|`C:\ProgramData\Microsoft\Windows\Templates`|
|`%ALLUSERSPROFILE%\Start Menu`|`C:\ProgramData\Start Menu`|
|`%ALLUSERSPROFILE%\Start Menu\Programs`| `C:\ProgramData\Start Menu\Programs`|
|`%ALLUSERSPROFILE%\Start Menu\Programs\Administrative Tools`|`C:\ProgramData\Start Menu\Programs\Administrative Tools`|
|`%ALLUSERSPROFILE%\Templates`|`C:\ProgramData\Templates`|
|`%LOCALAPPDATA%\Microsoft\Windows\ConnectedSearch\Templates`|`C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\ConnectedSearch\Templates`|
|`%LOCALAPPDATA%\Microsoft\Windows\History`|`C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\History`|
|`%PUBLIC%`|`C:\Users\Public`|
|`%PUBLIC%\AccountPictures`|`C:\Users\Public\AccountPictures`|
|`%PUBLIC%\Desktop`|`C:\Users\Public\Desktop`|
|`%PUBLIC%\Documents`|`C:\Users\Public\Documents`|
|`%PUBLIC%\Downloads`|`C:\Users\Public\Downloads`|
|`%PUBLIC%\Music\Sample Music`|`C:\Users\Public\Music\Sample Music`|
|`%PUBLIC%\Music\Sample Playlists`|`C:\Users\Public\Music\Sample Playlists`|
|`%PUBLIC%\Pictures\Sample Pictures`|`C:\Users\Public\Pictures\Sample Pictures`|
|`%PUBLIC%\RecordedTV.library-ms`|`C:\Users\Public\RecordedTV.library-ms`|
|`%PUBLIC%\Videos`|`C:\Users\Public\Videos`|
|`%PUBLIC%\Videos\Sample Videos`|`C:\Users\Public\Videos\Sample Videos`|
|`%USERPROFILE%`|`C:\Users\UserName`|
|`%USERPROFILE%\AppData\Local`|`C:\Users\UserName\AppData\Local`|
|`%USERPROFILE%\AppData\LocalLow`|`C:\Users\UserName\AppData\LocalLow`|
|`%USERPROFILE%\AppData\Roaming`|`C:\Users\UserName\AppData\Roaming`|

## <a name="review-the-list-of-exclusions"></a>Revisar la lista de exclusiones

Puede recuperar los elementos de la lista de exclusión mediante uno de los siguientes métodos:

- [Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- MpCmdRun
- PowerShell
- [Seguridad de Windows app](microsoft-defender-security-center-antivirus.md)

> [!IMPORTANT]
> Los cambios en la lista de exclusión realizados con la directiva de **grupo se** mostrarán en las listas de la [Seguridad de Windows aplicación](microsoft-defender-security-center-antivirus.md).
>
> Los cambios realizados en la Seguridad de Windows no **se mostrarán** en las listas de directivas de grupo.

Si usa PowerShell, puede recuperar la lista de dos maneras:

- Recupera el estado de todas las Antivirus de Microsoft Defender preferencias. Cada lista se muestra en líneas independientes, pero los elementos de cada lista se combinan en la misma línea.
- Escribe el estado de todas las preferencias en una variable y usa esa variable para llamar solo a la lista específica que te interesa. Cada uso de `Add-MpPreference` se escribe en una nueva línea.

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>Validar la lista de exclusión mediante MpCmdRun

Para comprobar las exclusiones con la herramienta de línea de [comandos ](./command-line-arguments-microsoft-defender-antivirus.md)mpcmdrun.exe, use el siguiente comando:

```console
Start, CMD (Run as admin)
cd "%programdata%\microsoft\windows defender\platform"
cd 4.18.2111-5.0 (Where 4.18.2111-5.0 is this month's Microsoft Defender Antivirus "Platform Update".)
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> La comprobación de exclusiones con MpCmdRun requiere Antivirus de Microsoft Defender versión 4.18.2111-5.0 de CAMP (publicada en diciembre de 2021) o posterior.

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>Revise la lista de exclusiones junto con el resto de Antivirus de Microsoft Defender preferencias mediante PowerShell

Use el siguiente cmdlet:

```PowerShell
Get-MpPreference
```

En el siguiente ejemplo, se resaltan `ExclusionExtension` los elementos contenidos en la lista:

:::image type="content" source="../../media/wdav-powershell-get-exclusions-variable.png" alt-text="Salida de PowerShell para Get-MpPreference.":::

Para obtener más información, vea [Usar cmdlets de PowerShell para configurar y ejecutar el Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [Cmdlets de Antivirus de Microsoft Defender](/powershell/module/defender/).

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>Recuperar una lista de exclusiones específica mediante PowerShell

Use el siguiente fragmento de código (escriba cada línea como un comando independiente); reemplace **WDAVprefs** por la etiqueta que desee nombrar la variable:

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionExtension
$WDAVprefs.ExclusionPath
```

En el siguiente ejemplo, la lista se divide en nuevas líneas para cada uso del `Add-MpPreference` cmdlet:

:::image type="content" source="../../media/wdav-powershell-get-exclusions-variable.png" alt-text="Salida de PowerShell que muestra solo las entradas de la lista de exclusión.":::

Para obtener más información, vea [Usar cmdlets de PowerShell para configurar y ejecutar el Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [Cmdlets de Antivirus de Microsoft Defender](/powershell/module/defender/).

<a id="validate"></a>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>Validar listas de exclusiones con el archivo de prueba EICAR

Puede validar que las listas de exclusión funcionan mediante PowerShell `Invoke-WebRequest` con el cmdlet o la clase WebClient de .NET para descargar un archivo de prueba.

En el siguiente fragmento de código de PowerShell, reemplace `test.txt` por un archivo que cumpla las reglas de exclusión. Por ejemplo, si ha excluido la `.testing` extensión, reemplace `test.txt` por `test.testing`. Si está probando una ruta de acceso, asegúrese de ejecutar el cmdlet dentro de esa ruta de acceso.

```PowerShell
Invoke-WebRequest "http://www.eicar.org/download/eicar.com.txt" -OutFile "test.txt"
```

Si Antivirus de Microsoft Defender informa de malware, la regla no funciona. Si no hay ningún informe de malware y existe el archivo descargado, la exclusión funciona. Puede abrir el archivo para confirmar que el contenido es el mismo que el que se describe en el sitio web del archivo [de prueba eicar](http://www.eicar.org/86-0-Intended-use.html).

También puede usar el siguiente código de PowerShell, que llama a la clase .NET WebClient `Invoke-WebRequest` para descargar el archivo de prueba, como con el cmdlet; `c:\test.txt` reemplace por un archivo que cumpla con la regla que va a validar:

```PowerShell
$client = new-object System.Net.WebClient
$client.DownloadFile("http://www.eicar.org/download/eicar.com.txt","c:\test.txt")
```

Si no tiene acceso a Internet, puede crear su propio archivo de prueba EICAR escribiendo la cadena EICAR en un nuevo archivo de texto con el siguiente comando de PowerShell:

```PowerShell
[io.file]::WriteAllText("test.txt",'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*')
```

También puede copiar la cadena en un archivo de texto en blanco e intentar guardarla con el nombre de archivo o en la carpeta que está intentando excluir.

## <a name="see-also"></a>Consulte también

- [Configurar y validar exclusiones en Antivirus de Microsoft Defender exámenes](configure-exclusions-microsoft-defender-antivirus.md)
- [Configurar y validar exclusiones para archivos abiertos por procesos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Configurar Antivirus de Microsoft Defender exclusiones en Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Errores comunes para evitarlos cuando se definen exclusiones](common-exclusion-mistakes-microsoft-defender-antivirus.md)
