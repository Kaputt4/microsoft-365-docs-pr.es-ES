---
title: Configurar Antivirus de Microsoft Defender exclusiones en Windows Server
ms.reviewer: ''
manager: dansimp
description: Windows El servidor incluye exclusiones automáticas, según el rol de servidor. También puede agregar exclusiones personalizadas.
keywords: exclusiones, servidor, exclusiones automáticas, automáticas, personalizadas, exámenes, Antivirus de Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 02/10/2021
ms.topic: article
ms.openlocfilehash: f82da8eb0dcba39404c2b7f191e166aa78357cee
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274765"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a>Configurar Antivirus de Microsoft Defender exclusiones en Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Antivirus de Microsoft Defender en Windows Server 2016 y Windows Server 2019 lo inscribe automáticamente en determinadas exclusiones, tal como lo define el rol de servidor especificado. Estas exclusiones no aparecen en las listas de exclusión estándar que se muestran en la [Seguridad de Windows aplicación](microsoft-defender-security-center-antivirus.md).

> [!NOTE]
> Las exclusiones automáticas solo se aplican al examen de protección en tiempo real (RTP). Las exclusiones automáticas no se respetan durante un examen completo/rápido o a petición.

Además de las exclusiones automáticas definidas por roles de servidor, puede agregar o quitar exclusiones personalizadas. Para ello, consulte estos artículos:
- [Configurar y validar exclusiones según el nombre de archivo, la extensión y la ubicación de la carpeta](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Configurar y validar exclusiones para archivos abiertos por procesos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a>Algunos puntos a tener en cuenta

Tenga en cuenta los siguientes puntos importantes:

- Las exclusiones personalizadas tienen prioridad sobre las exclusiones automáticas.
- Las exclusiones automáticas solo se aplican al examen de protección en tiempo real (RTP). Las exclusiones automáticas no se respetan durante un examen completo/rápido o a petición.
- Las exclusiones personalizadas y duplicadas no están en conflicto con las exclusiones automáticas.
- Antivirus de Microsoft Defender usa las herramientas de administración y mantenimiento de imágenes de implementación (DISM) para determinar qué roles están instalados en el equipo.

## <a name="opt-out-of-automatic-exclusions"></a>No participar en exclusiones automáticas

En Windows Server 2016 y Windows Server 2019, las exclusiones predefinidas que entregan las actualizaciones de inteligencia de seguridad solo excluyen las rutas predeterminadas para un rol o característica. Si instaló un rol o una característica en una ruta de acceso personalizada o desea controlar manualmente el conjunto de exclusiones, asegúrese de no participar en las exclusiones automáticas que se entregan en Actualizaciones de inteligencia de seguridad. Pero tenga en cuenta que las exclusiones que se entregan automáticamente están optimizadas para los roles Windows Server 2016 y 2019. Consulte [Recomendaciones para definir exclusiones antes](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) de definir las listas de exclusión.

> [!WARNING]
> La exclusión automática puede afectar negativamente al rendimiento o provocar daños en los datos. Las exclusiones que se entregan automáticamente se optimizan para Windows Server 2016 y Windows roles de Server 2019.

Dado que las exclusiones predefinidas solo excluyen las rutas predeterminadas **,** si mueve NTDS y SYSVOL a otra unidad o ruta de acceso que sea diferente de la ruta de acceso *original,* debe agregar exclusiones manualmente con la información aquí [.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension)

Puede deshabilitar las listas de exclusión automática con la directiva de grupo, los cmdlets de PowerShell y WMI.

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>Usar la directiva de grupo para deshabilitar la lista de exclusiones automáticas en Windows Server 2016 y Windows Server 2019

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)). Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, haga clic en **Editar**.
2. En el **Editor de administración de directivas de** grupo, vaya a Configuración **del** equipo y, a continuación, haga clic en **Plantillas administrativas.**
3. Expanda el árbol para **Windows componentes**  >  **Antivirus de Microsoft Defender**  >  **exclusiones**.
4. Haga doble clic **en Desactivar exclusiones automáticas** y establezca la opción en **Habilitado**. Después, haga clic en **Aceptar**. 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a>Usar cmdlets de PowerShell para deshabilitar la lista de exclusiones automáticas en Windows Server 2016 y 2019

Use los cmdlets siguientes:

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

Para obtener más información, consulte los siguientes recursos:

- [Use cmdlets de PowerShell para configurar y ejecutar Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md).
- [Use PowerShell con Antivirus de Microsoft Defender](/powershell/module/defender/).

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>Use Windows Management Instruction (WMI) para deshabilitar la lista de exclusiones automáticas en Windows Server 2016 y Windows Server 2019

Utilice el **método Set** de la [clase MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) para las siguientes propiedades:

```WMI
DisableAutoExclusions
```

Vea lo siguiente para obtener más información y parámetros permitidos:
- [Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a>Lista de exclusiones automáticas

Las secciones siguientes contienen las exclusiones que se entregan con rutas de acceso de archivo de exclusiones automáticas y tipos de archivo.

### <a name="default-exclusions-for-all-roles"></a>Exclusiones predeterminadas para todos los roles

En esta sección se enumeran las exclusiones predeterminadas para todos los Windows Server 2016 y 2019.

> [!NOTE]
> Las ubicaciones predeterminadas pueden ser diferentes de las que se enumeran en este artículo.

#### <a name="windows-tempedb-files"></a>Windows Archivos "temp.edb"

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a>Windows Actualizar archivos o archivos de actualización automática

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a>Seguridad de Windows archivos

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a>Archivos de directiva de grupo

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a>Archivos WINS

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a>Exclusiones del Servicio de replicación de archivos (FRS)

- Archivos en la carpeta de trabajo servicio de replicación de archivos (FRS). La carpeta de trabajo de FRS se especifica en la clave del Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- Archivos de registro de base de datos FRS. La carpeta de archivos de registro de base de datos FRS se especifica en la clave del Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`

  - `%windir%\Ntfrs\*\Edb\*.log`

- La carpeta de almacenamiento provisional de FRS. La carpeta provisional se especifica en la clave del Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- La carpeta de preinstalación frs. Esta carpeta se especifica mediante la carpeta `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- La base de datos de replicación del sistema de archivos distribuido (DFSR) y las carpetas de trabajo. Estas carpetas se especifican mediante la clave del Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`

  > [!NOTE]
  > Para las ubicaciones personalizadas, vea [Opt out of automatic exclusions](#opt-out-of-automatic-exclusions).

  - `%systemdrive%\System Volume Information\DFSR\$db_normal$`
  - `%systemdrive%\System Volume Information\DFSR\FileIDTable_*`
  - `%systemdrive%\System Volume Information\DFSR\SimilarityTable_*`
  - `%systemdrive%\System Volume Information\DFSR\*.XML`
  - `%systemdrive%\System Volume Information\DFSR\$db_dirty$`
  - `%systemdrive%\System Volume Information\DFSR\$db_clean$`
  - `%systemdrive%\System Volume Information\DFSR\$db_lostl$`
  - `%systemdrive%\System Volume Information\DFSR\Dfsr.db`
  - `%systemdrive%\System Volume Information\DFSR\*.frx`
  - `%systemdrive%\System Volume Information\DFSR\*.log`
  - `%systemdrive%\System Volume Information\DFSR\Fsr*.jrs`
  - `%systemdrive%\System Volume Information\DFSR\Tmp.edb`

#### <a name="process-exclusions"></a>Exclusiones de procesos

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a>Exclusiones de Hyper-V

En la tabla siguiente se enumeran las exclusiones de tipo de archivo, las exclusiones de carpetas y las exclusiones de proceso que se entregan automáticamente al instalar el rol de Hyper-V.

|Exclusiones de tipos de archivo |Exclusiones de carpetas  | Process exclusions |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a>Archivos SYSVOL

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a>Exclusiones de Active Directory

En esta sección se enumeran las exclusiones que se entregan automáticamente al instalar los Servicios de dominio de Active Directory.

#### <a name="ntds-database-files"></a>Archivos de base de datos NTDS

Los archivos de base de datos se especifican en la clave del Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a>Los archivos de registro de transacciones de AD DS

Los archivos de registro de transacciones se especifican en la clave del Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a>La carpeta de trabajo NTDS

Esta carpeta se especifica en la clave del Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a>Exclusiones de procesos para archivos de soporte técnico relacionados con AD DS y AD DS

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a>Exclusiones del servidor DHCP

En esta sección se enumeran las exclusiones que se entregan automáticamente al instalar el rol de servidor DHCP. Las ubicaciones de archivos del servidor DHCP se especifican mediante los parámetros *DatabasePath*, *DhcpLogFilePath* y *BackupDatabasePath* en la clave del Registro. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a>Exclusiones del servidor DNS

En esta sección se enumeran las exclusiones de archivos y carpetas y las exclusiones de proceso que se entregan automáticamente al instalar el rol servidor DNS.

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a>Exclusiones de archivos y carpetas para el rol servidor DNS

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a>Procesar exclusiones para el rol de servidor DNS

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a>Exclusiones de Storage de archivos y servicios

En esta sección se enumeran las exclusiones de archivos y carpetas que se entregan automáticamente al instalar el rol Archivo y Storage servicios. Las exclusiones enumeradas a continuación no incluyen exclusiones para el rol Agrupación en clústeres.

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a>Exclusiones del servidor de impresión

En esta sección se enumeran las exclusiones de tipo de archivo, las exclusiones de carpetas y las exclusiones de proceso que se entregan automáticamente al instalar el rol Servidor de impresión.

#### <a name="file-type-exclusions"></a>Exclusiones de tipos de archivo

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a>Exclusiones de carpetas

Esta carpeta se especifica en la clave del Registro `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a>Exclusiones de procesos

- `spoolsv.exe`

### <a name="web-server-exclusions"></a>Exclusiones de servidor web

En esta sección se enumeran las exclusiones de carpetas y las exclusiones de proceso que se entregan automáticamente al instalar el rol servidor web.

#### <a name="folder-exclusions"></a>Exclusiones de carpetas

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a>Process exclusions

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a>Desactivar el examen de archivos en la carpeta Sysvol\Sysvol o en la carpeta SYSVOL_DFSR\Sysvol

La ubicación actual de la carpeta or y todas las subcarpetas es el destino de reeplo de sistema de archivos `Sysvol\Sysvol` de la raíz del conjunto de `SYSVOL_DFSR\Sysvol` réplicas. Las `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` carpetas y usan las siguientes ubicaciones de forma predeterminada:

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

El recurso compartido NETLOGON hace referencia a la ruta de acceso al recurso compartido NETLOGON y puede determinarse mediante el nombre del valor `SYSVOL` SysVol en la siguiente subclave: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`

Excluya los siguientes archivos de esta carpeta y todas sus subcarpetas:

- `*.adm`
- `*.admx`
- `*.adml`
- `Registry.pol`
- `Registry.tmp`
- `*.aas`
- `*.inf`
- `Scripts.ini`
- `*.ins`
- `Oscfilter.ini`

### <a name="windows-server-update-services-exclusions"></a>Windows Server Update Services exclusiones

En esta sección se enumeran las exclusiones de carpetas que se entregan automáticamente al instalar el rol Windows Server Update Services (WSUS). La carpeta WSUS se especifica en la clave del Registro `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a>Consulte también

- [Configurar y validar exclusiones para Antivirus de Microsoft Defender exámenes](configure-exclusions-microsoft-defender-antivirus.md)
- [Configurar y validar exclusiones según el nombre de archivo, la extensión y la ubicación de la carpeta](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Configurar y validar exclusiones para archivos abiertos por procesos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Errores comunes para evitarlos cuando se definen exclusiones](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [Personalizar, iniciar y revisar los resultados de Antivirus de Microsoft Defender análisis y corrección](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)