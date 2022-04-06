---
title: Antivirus de Microsoft Defender en Windows Server
description: Obtenga información sobre cómo habilitar y configurar Antivirus de Microsoft Defender en Windows Server 2016, Windows Server 2019 y Windows Server 2022.
keywords: windows defender, server, scep, system center endpoint protection, server 2016, current branch, server 2012
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 01/26/2022
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 4962537e86010fceeb2845fdd6408270c97742dc
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64469765"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Antivirus de Microsoft Defender en Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Antivirus de Microsoft Defender está disponible en las siguientes ediciones o versiones de Windows Server:

- Windows Server 2022
- Windows Server 2019
- Windows Server, versión 1803 o posterior
- Windows Server 2016
- Windows Server 2012 R2 (requiere Microsoft Defender para endpoint)

En algunos casos, Antivirus de Microsoft Defender se conoce *como Endpoint Protection*; sin embargo, el motor de protección es el mismo. Aunque la funcionalidad, la configuración y la administración son en gran medida las mismas para [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-windows.md) y Windows 11, hay algunas diferencias clave en Windows Server:

- En Windows server, [las exclusiones automáticas](configure-server-exclusions-microsoft-defender-antivirus.md) se aplican en función del rol de servidor definido.

- En Windows Server, si está ejecutando una solución antivirus o antimalware que no sea de Microsoft, Antivirus de Microsoft Defender no entra en modo pasivo ni en modo deshabilitado automáticamente. Sin embargo, puede establecer Antivirus de Microsoft Defender modo pasivo o deshabilitado manualmente.

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>Configuración de Antivirus de Microsoft Defender en Windows Server

El proceso de configuración y ejecución de Antivirus de Microsoft Defender en una plataforma de servidor incluye varios pasos:

1. [Habilite la interfaz](#enable-the-user-interface-on-windows-server).
2. [Instale Antivirus de Microsoft Defender](#install-microsoft-defender-antivirus-on-windows-server).
3. [Compruebe Antivirus de Microsoft Defender se está ejecutando](#verify-microsoft-defender-antivirus-is-running).
4. [Actualice la inteligencia de seguridad antimalware](#update-antimalware-security-intelligence).
5. (Según sea necesario) [Enviar ejemplos](#submit-samples).
6. (Según sea necesario) [Configurar exclusiones automáticas](#configure-automatic-exclusions).
7. (Solo si es necesario) Establezca [Windows server en modo pasivo](#passive-mode-and-windows-server).

## <a name="enable-the-user-interface-on-windows-server"></a>Habilitar la interfaz de usuario en Windows Server

De forma predeterminada, Antivirus de Microsoft Defender está instalado y funcional en Windows Server. A veces, la interfaz de usuario (GUI) está instalada de forma predeterminada, pero la GUI no es necesaria. Puede usar PowerShell, directiva de grupo u otros métodos para administrar Antivirus de Microsoft Defender.

Si la GUI no está instalada en el servidor y desea instalarla, el Asistente para agregar **roles** y características o cmdlets de PowerShell.

> [!NOTE]
> Esta opción no está disponible para Windows Server 2012 R2. Para obtener más información, consulta [Opciones para instalar Microsoft Defender para endpoint](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages).

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>Activar la GUI mediante el Asistente para agregar roles y características

1. Consulte [Instalar roles, servicios de roles](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard) y características mediante el Asistente para agregar roles y características y usar el Asistente para agregar **roles y características**.

2. Cuando llegue al paso **Características** del asistente, en **Windows Defender características**, seleccione la **gui Windows Defender**.

   En Windows Server 2016, el Asistente para agregar **roles y características** tiene este aspecto:

   :::image type="content" source="images/server-add-gui.png" alt-text="El Asistente para agregar roles y características que muestra la gui Windows Defender usuario." lightbox="images/server-add-gui.png":::

   En Windows Server 2019 y Windows Server 2022, el Asistente para agregar **roles y** características es similar.

### <a name="turn-on-the-gui-using-powershell"></a>Activar la GUI con PowerShell

El siguiente cmdlet de PowerShell habilitará la interfaz:

```powershell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>Instalar Antivirus de Microsoft Defender en Windows Server

Si necesita instalar o reinstalar Antivirus de Microsoft Defender en Windows Server, puede hacerlo con el Asistente para agregar **roles** y características o PowerShell.

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a>Use el Asistente para agregar roles y características para instalar Antivirus de Microsoft Defender

1. Consulte este [artículo y](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard) use el Asistente **para agregar roles y características**.

2. Cuando llegue al paso **Características** del asistente, seleccione Antivirus de Microsoft Defender opción. También seleccione la **guia para Windows Defender** opción.

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a>Use PowerShell para instalar Antivirus de Microsoft Defender

Para usar PowerShell para instalar Antivirus de Microsoft Defender, ejecute el siguiente cmdlet:

```powershell
Install-WindowsFeature -Name Windows-Defender
```

Los mensajes de evento para el motor de antimalware incluidos con Antivirus de Microsoft Defender pueden encontrarse en [Antivirus de Microsoft Defender eventos](troubleshoot-microsoft-defender-antivirus.md).

## <a name="verify-microsoft-defender-antivirus-is-running"></a>Comprobar Antivirus de Microsoft Defender se está ejecutando

Una Antivirus de Microsoft Defender está instalada, el siguiente paso es comprobar que se está ejecutando. En el punto Windows servidor, ejecute el siguiente cmdlet de PowerShell:

```powershell
Get-Service -Name windefend
```

Para comprobar que la protección del firewall está activada, ejecute el siguiente cmdlet de PowerShell:

```powershell
Get-Service -Name mpssvc
```

Como alternativa a PowerShell, puede usar el símbolo del sistema para comprobar que Antivirus de Microsoft Defender se está ejecutando. Para ello, ejecute el siguiente comando desde un símbolo del sistema:

```console
sc query Windefend
```

El `sc query` comando devuelve información sobre el Antivirus de Microsoft Defender servicio. Cuando Antivirus de Microsoft Defender se está ejecutando, el `STATE` valor muestra `RUNNING`.

Para ver todos los servicios que no se están ejecutando, ejecute el siguiente cmdlet de PowerShell:

```console
sc query state= all
```

## <a name="update-antimalware-security-intelligence"></a>Actualizar inteligencia de seguridad antimalware

Para obtener la inteligencia de seguridad antimalware actualizada, debe tener el servicio Windows update en ejecución. Si usa un servicio de administración de actualizaciones, como Windows Server Update Services (WSUS), asegúrese de que las actualizaciones de la inteligencia de seguridad de Antivirus de Microsoft Defender están aprobadas para los equipos que administra.

De forma predeterminada, Windows Update no descarga e instala actualizaciones automáticamente en Windows Server 2019 o Windows Server 2022 o Windows Server 2016. Puede cambiar esta configuración mediante uno de los métodos siguientes:

<br/><br/>

| Método | Descripción |
|---|---|
| **Windows actualización en** el Panel de control | **Instalar actualizaciones automáticamente da como** resultado que todas las actualizaciones se instalen automáticamente, incluidas Windows Defender de inteligencia de seguridad. <br/><br/> **Descargue las actualizaciones, pero permítanme** elegir si instalarlas permite Windows Defender descargar e instalar actualizaciones de inteligencia de seguridad automáticamente, pero otras actualizaciones no se instalan automáticamente. |
| **Directiva de grupo** | Puede configurar y administrar Windows Update mediante la configuración disponible en la directiva de grupo, en la siguiente ruta de acceso: Plantillas administrativas **\componentes Windows\Windows Update\Configurar actualizaciones automáticas** |
| La **clave del Registro AUOptions** | Los dos valores siguientes permiten a Windows Update descargar e instalar automáticamente las actualizaciones de inteligencia de seguridad: <br/><br/> **4** -  **Instale las actualizaciones automáticamente**. Este valor da como resultado que todas las actualizaciones se instalen automáticamente, incluidas Windows Defender de inteligencia de seguridad. <br/><br/> **3** -  **Descargue las actualizaciones, pero permítanme elegir si desea instalarlas**. Este valor permite Windows Defender descargar e instalar actualizaciones de inteligencia de seguridad automáticamente, pero otras actualizaciones no se instalan automáticamente. |

Para garantizar que se mantiene la protección contra malware, se recomienda habilitar los siguientes servicios:

- Informe de errores de Windows servicio
- Windows update

En la tabla siguiente se enumeran los servicios Antivirus de Microsoft Defender y los servicios dependientes.

<br/><br/>


| Nombre del servicio | Ubicación del archivo | Descripción |
|---|---|---|
| Windows Defender (WinDefend) | `C:\Program Files\Windows Defender\MsMpEng.exe` | Este es el servicio Antivirus de Microsoft Defender principal que debe ejecutarse en todo momento.|
| Informe de errores de Windows (Wersvc) | `C:\WINDOWS\System32\svchost.exe -k WerSvcGroup` | Este servicio devuelve informes de error a Microsoft. |
| Windows Defender firewall (MpsSvc) | `C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork` | Se recomienda dejar el servicio Windows Defender firewall habilitado. |
| Windows (Wuauserv) | `C:\WINDOWS\system32\svchost.exe -k netsvcs`| Windows update es necesario para obtener actualizaciones de inteligencia de seguridad y actualizaciones del motor antimalware |

## <a name="submit-samples"></a>Enviar ejemplos

El envío de ejemplo permite a Microsoft recopilar muestras de software potencialmente malintencionado. Para ayudar a proporcionar una protección continua y actualizada, los investigadores de Microsoft usan estas muestras para analizar actividades sospechosas y producir inteligencia de seguridad antimalware actualizada. Recopilamos archivos ejecutables del programa, como .exe archivos y .dll archivos. No recopilamos archivos que contienen datos personales, como documentos Microsoft Word documentos y archivos PDF.

### <a name="submit-a-file"></a>Enviar un archivo

1. Revise la [guía de envío](/windows/security/threat-protection/intelligence/submission-guide).
2. Visite el portal [de envío de ejemplo](https://www.microsoft.com/wdsi/filesubmission) y envíe el archivo.

### <a name="enable-automatic-sample-submission"></a>Habilitar el envío automático de muestra

Para habilitar el envío automático de ejemplo, inicie una consola Windows PowerShell como administrador y establezca los datos de valor **SubmitSamplesConsent** de acuerdo con una de las opciones siguientes:

<br/><br/>

|Valor|Descripción|
|---|---|
| **0** -  **Preguntar siempre** | El Antivirus de Microsoft Defender solicita que confirme el envío de todos los archivos necesarios. Esta es la configuración predeterminada para Antivirus de Microsoft Defender, pero no se recomienda para instalaciones en Windows Server 2016 o 2019, o Windows Server 2022 sin una GUI. |
| **1**  -  **Enviar muestras seguras automáticamente** | El Antivirus de Microsoft Defender envía todos los archivos marcados como "seguros" y solicita el resto de los archivos. |
| **2** -  **Nunca enviar** | El Antivirus de Microsoft Defender no solicita y no envía ningún archivo. |
| **3** -  **Enviar todas las muestras automáticamente** | El Antivirus de Microsoft Defender envía todos los archivos sin necesidad de confirmación. |

> [!NOTE]
> Esta opción no está disponible para Windows Server 2012 R2. 


## <a name="configure-automatic-exclusions"></a>Configurar exclusiones automáticas

Para garantizar la seguridad y el rendimiento, se agregan automáticamente determinadas exclusiones en función de los roles y características que se instalan al usar Antivirus de Microsoft Defender en Windows Server 2016 o 2019, o Windows Server 2022.

Consulte [Configure exclusions in Antivirus de Microsoft Defender on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).

## <a name="passive-mode-and-windows-server"></a>Modo pasivo y servidor Windows servidor

Si usa un producto antivirus que no sea de Microsoft como solución antivirus principal en Windows Server, debe establecer Antivirus de Microsoft Defender en modo pasivo o en modo deshabilitado.

Para obtener más información, vea [Install Antivirus de Microsoft Defender on Windows Server](microsoft-defender-antivirus-on-windows-server.md#install-microsoft-defender-antivirus-on-windows-server).


### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>Establecer Antivirus de Microsoft Defender en modo pasivo mediante una clave del Registro

Puede establecer el Antivirus de Microsoft Defender en modo pasivo estableciendo la siguiente clave del Registro:
- Ruta de acceso: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Nombre: `ForceDefenderPassiveMode`
- Tipo: `REG_DWORD`
- Valor: `1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>Deshabilitar Antivirus de Microsoft Defender mediante el Asistente para quitar roles y características

1. Consulta [Instalar o desinstalar roles, servicios de roles o características](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard) y usa **el Asistente para quitar roles y características**.

2. Cuando llegue al paso **Características** del asistente, desactive la opción **Windows Defender características**.

    Si borras **Windows Defender** en la sección **características de Windows Defender**, se te pedirá que quites la GUI de opción de interfaz para **Windows Defender**.

    Antivirus de Microsoft Defender se ejecutará normalmente sin la interfaz de usuario, pero la interfaz de usuario no se puede habilitar si deshabilita la característica principal **Windows Defender** usuario.

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>Desactivar la interfaz Antivirus de Microsoft Defender usuario con PowerShell

Para desactivar la GUI Antivirus de Microsoft Defender, use el siguiente cmdlet de PowerShell:

```powershell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2012-r2-or-windows-server-2016"></a>¿Usa Windows Server 2012 R2 o Windows Server 2016?

Ahora puede ejecutar Antivirus de Microsoft Defender en modo pasivo en Windows Server 2012 R2 y Windows Server 2016. Para obtener más información, consulta [Opciones para instalar Microsoft Defender para endpoint](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages).

<br/><br/>

| Procedure | Descripción |
|---|---|
| Deshabilitar Antivirus de Microsoft Defender con la directiva de grupo | En el Editor de directivas de grupo local, vaya a **Plantilla** >  administrativa **Windows Componente** >  **Endpoint Protection** >  **Disable Endpoint Protection** y, a continuación, **seleccione EnabledOK** > . |
| Deshabilitar Antivirus de Microsoft Defender con una clave del Registro | Para usar la [clave del Registro DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) , vaya `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`a y establezca o cree una entrada DWORD denominada `DisableAntiSpyware`. Establezca su valor en `1` (que establece el valor de la clave del Registro en *true*). |
| Deshabilitar Antivirus de Microsoft Defender con PowerShell | Use el siguiente cmdlet de PowerShell: `Set-MpPreference -DisableRealtimeMonitoring $true` |
| Desinstalar Antivirus de Microsoft Defender con PowerShell | Use el siguiente cmdlet de PowerShell: `Uninstall-WindowsFeature -Name Windows-Defender` |


## <a name="see-also"></a>Vea también

- [Antivirus de Microsoft Defender en Windows](microsoft-defender-antivirus-windows.md)
- [Antivirus de Microsoft Defender compatibilidad](microsoft-defender-antivirus-compatibility.md)
