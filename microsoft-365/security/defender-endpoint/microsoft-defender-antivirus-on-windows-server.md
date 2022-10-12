---
title: Antivirus de Microsoft Defender en Windows Server
description: Obtenga información sobre cómo habilitar y configurar Microsoft Defender Antivirus en Windows Server 2016, Windows Server 2019 y Windows Server 2022.
keywords: windows defender, server, scep, system center endpoint protection, server 2016, rama actual, servidor 2012
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.topic: article
ms.date: 10/10/2022
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 74d56fe8f7c2ceeee23017a7932cd642438a3a69
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68536200"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Antivirus de Microsoft Defender en Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender Antivirus está disponible en las siguientes ediciones o versiones de Windows Server:

- Windows Server 2022
- Windows Server 2019
- Windows Server, versión 1803 o posterior
- Windows Server 2016
- Windows Server 2012 R2 (requiere Microsoft Defender para punto de conexión)

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>Configuración de Microsoft Defender Antivirus en Windows Server

El proceso de configuración y ejecución de Microsoft Defender Antivirus en Windows Server incluye los pasos siguientes:

1. [Habilite la interfaz](#enable-the-user-interface-on-windows-server).
2. [Instale Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).
3. [Compruebe Microsoft Defender antivirus está en ejecución](#verify-microsoft-defender-antivirus-is-running).
4. [Actualice la inteligencia de seguridad antimalware](#update-antimalware-security-intelligence).
5. (Según sea necesario) [Envíe ejemplos](#submit-samples).
6. (Según sea necesario) [Configurar exclusiones automáticas](#configure-automatic-exclusions).
7. (Solo si es necesario) [Establezca Windows Server en modo pasivo](#passive-mode-and-windows-server).

## <a name="enable-the-user-interface-on-windows-server"></a>Habilitación de la interfaz de usuario en Windows Server

> [!IMPORTANT]
> Si usa Windows Server 2012 R2, consulte [Opciones para instalar Microsoft Defender para punto de conexión](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages).

De forma predeterminada, Microsoft Defender Antivirus está instalado y funciona en Windows Server. A veces, la interfaz de usuario (GUI) se instala de forma predeterminada. La GUI no es necesaria; puede usar PowerShell, directiva de grupo u otros métodos para administrar Microsoft Defender Antivirus. Sin embargo, muchas organizaciones prefieren usar la GUI para Microsoft Defender Antivirus. Para instalar la GUI, use uno de los procedimientos de la tabla siguiente:

| Procedure | Qué hacer |
|:---|:---|
| Active la GUI mediante el Asistente para agregar roles y características. | 1. Vea [Instalar roles, servicios de roles y características mediante el Asistente para agregar roles y características](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), y use el **Asistente para agregar roles y características**. <br/><br/>2. Cuando llegue al paso **Características** del asistente, en **características de Windows Defender**, seleccione la **guia para Windows Defender** opción. |
| Activar la GUI mediante PowerShell | 1. En windows Server, abra Windows PowerShell como administrador. <br/><br/>2. Ejecute el siguiente cmdlet de PowerShell: `Install-WindowsFeature -Name Windows-Defender-GUI` |

Para obtener más información, consulte [Introducción con PowerShell](/powershell/scripting/learn/ps101/01-getting-started).

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>Instalación de Microsoft Defender Antivirus en Windows Server

Si necesita instalar o reinstalar Microsoft Defender Antivirus en Windows Server, use uno de los procedimientos de la tabla siguiente:

| Procedure | Qué hacer |
|:---|:---|
| Use el Asistente para agregar roles y características para instalar Microsoft Defender Antivirus | 1. Vea [Instalar o desinstalar roles, servicios de rol o características](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), y use el **Asistente para agregar roles y características**. <br/><br/>2. Cuando llegue al paso **Características** del asistente, seleccione la opción Microsoft Defender Antivirus. Seleccione también la opción **GUI para Windows Defender**. |
| Uso de PowerShell para instalar Microsoft Defender Antivirus | 1. En windows Server, abra Windows PowerShell como administrador. <br/><br/>2. Ejecute el siguiente cmdlet de PowerShell: `Install-WindowsFeature -Name Windows-Defender` |

> [!NOTE]
> Los mensajes de evento del motor de antimalware incluidos con Microsoft Defender Antivirus se pueden encontrar en [Microsoft Defender Antivirus Events](troubleshoot-microsoft-defender-antivirus.md).

## <a name="verify-microsoft-defender-antivirus-is-running"></a>Comprobación de Microsoft Defender antivirus en ejecución

Después de instalar (o reinstalar) Microsoft Defender Antivirus, el siguiente paso es comprobar que se está ejecutando. Use los cmdlets de PowerShell en la tabla siguiente:

| Procedure | Cmdlet de PowerShell |
|:---|:---|
| Comprobar que Microsoft Defender Antivirus está en ejecución | `Get-Service -Name windefend` |
| Comprobación de que la protección del firewall está activada | `Get-Service -Name mpssvc` |

Como alternativa a PowerShell, puede usar el símbolo del sistema para comprobar que Microsoft Defender Antivirus se está ejecutando. Para ello, ejecute el siguiente comando desde un símbolo del sistema:

```cmd
sc query Windefend
```

El `sc query` comando devuelve información sobre el servicio antivirus de Microsoft Defender. Cuando se ejecuta Microsoft Defender Antivirus, el `STATE` valor muestra `RUNNING`.

Para ver todos los servicios que no se ejecutan, ejecute el siguiente cmdlet de PowerShell:

```cmd
sc query state= all
```

## <a name="update-antimalware-security-intelligence"></a>Actualización de la inteligencia de seguridad antimalware

> [!IMPORTANT]
> A partir de la [versión de la plataforma 4.18.2208.0 y versiones posteriores](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions): si un servidor se ha incorporado a Microsoft Defender para punto de conexión, la configuración de directiva de [grupo](configure-endpoints-gp.md#update-endpoint-protection-configuration) "Desactivar Windows Defender" ya no deshabilitará completamente Windows Defender Antivirus activado. Windows Server 2012 R2 y versiones posteriores. En su lugar, lo colocará en modo pasivo. Además, la característica de [protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md) permitirá cambiar al modo activo, pero no al modo pasivo.
> 
> - Si ya se ha implementado "Desactivar Windows Defender" antes de incorporarse a Microsoft Defender para punto de conexión, no habrá ningún cambio y Antivirus de Defender permanecerá deshabilitado.
> - Para cambiar antivirus de Defender al modo pasivo, incluso si se deshabilitó antes de la incorporación, puede aplicar la [configuración de ForceDefenderPassiveMode](switch-to-mde-phase-2.md#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server) con un valor de `1`. Para colocarlo en modo activo, cambie este valor a `0` en su lugar.
> 
> Tenga en cuenta la lógica modificada para `ForceDefenderPassiveMode` cuando se habilita la protección contra alteraciones: una vez que Microsoft Defender Antivirus cambia al modo activo, la protección contra alteraciones impedirá que vuelva al modo pasivo incluso cuando `ForceDefenderPassiveMode` se establezca en `1`.

Para obtener las actualizaciones periódicas de inteligencia de seguridad, el servicio de Windows Update debe estar en ejecución. Si usa un servicio de administración de actualizaciones, como Windows Server Update Services (WSUS), asegúrese de que las actualizaciones de Microsoft Defender Antivirus Security intelligence están aprobadas para los equipos que administra.

De forma predeterminada, Windows Update no descarga ni instala actualizaciones automáticamente en Windows Server 2019 o Windows Server 2022 o Windows Server 2016. Puede cambiar esta configuración mediante uno de los métodos siguientes:

| Método | Descripción |
|---|---|
| **Windows Update** en Panel de control | **La instalación de actualizaciones provoca que** todas las actualizaciones se instalen automáticamente, incluidas Windows Defender actualizaciones de inteligencia de seguridad. <br/><br/> **Descargue las actualizaciones, pero permítanme elegir si instalarlas permite Windows Defender** descargar e instalar actualizaciones de Inteligencia de seguridad automáticamente, pero otras actualizaciones no se instalan automáticamente. |
| **Directiva de grupo** | Puede configurar y administrar Windows Update mediante la configuración disponible en directiva de grupo, en la ruta de acceso siguiente: **Plantillas administrativas\Componentes de Windows\Windows Update\Configurar Novedades automático** |
| Clave del Registro **AUOptions** | Los dos valores siguientes permiten Windows Update descargar e instalar automáticamente las actualizaciones de Inteligencia de seguridad: <br/><br/> **4** -  **Instale las actualizaciones automáticamente**. Este valor hace que todas las actualizaciones se instalen automáticamente, incluidas Windows Defender actualizaciones de inteligencia de seguridad. <br/><br/> **3** -  **Descargue las actualizaciones, pero permítanme elegir si desea instalarlas**. Este valor permite Windows Defender descargar e instalar actualizaciones de Inteligencia de seguridad automáticamente, pero otras actualizaciones no se instalan automáticamente. |

Para asegurarse de que se mantiene la protección contra malware, habilite los siguientes servicios:

- Informe de errores de Windows servicio
- Windows Update servicio

En la tabla siguiente se enumeran los servicios de Microsoft Defender Antivirus y los servicios dependientes.

| Nombre del servicio | Ubicación del archivo | Descripción |
|---|---|---|
| Windows Defender Service (WinDefend) | `C:\Program Files\Windows Defender\MsMpEng.exe` | Este servicio es el principal Microsoft Defender servicio antivirus que debe ejecutarse siempre.|
| servicio Informe de errores de Windows (Wersvc) | `C:\WINDOWS\System32\svchost.exe -k WerSvcGroup` | Este servicio envía informes de errores a Microsoft. |
| firewall de Windows Defender (MpsSvc) | `C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork` | Se recomienda mantener habilitado el servicio firewall de Windows Defender. |
| Windows Update (Wuauserv) | `C:\WINDOWS\system32\svchost.exe -k netsvcs`| Windows Update es necesario para obtener actualizaciones de inteligencia de seguridad y actualizaciones del motor antimalware |

## <a name="submit-samples"></a>Envío de ejemplos

El envío de ejemplos permite a Microsoft recopilar ejemplos de software potencialmente malintencionado. Para ayudar a proporcionar protección continua y actualizada, los investigadores de Microsoft usan estos ejemplos para analizar actividades sospechosas y producir inteligencia de seguridad antimalware actualizada. Recopilamos archivos ejecutables del programa, como archivos .exe y archivos .dll. No recopilamos archivos que contengan datos personales, como documentos de Microsoft Word y archivos PDF.

### <a name="submit-a-file"></a>Envío de un archivo

1. Revise la [guía de envío](/windows/security/threat-protection/intelligence/submission-guide).

2. Visite el [portal de envío de ejemplo](https://www.microsoft.com/wdsi/filesubmission) y envíe el archivo.

### <a name="enable-automatic-sample-submission"></a>Habilitación del envío automático de ejemplos

Para habilitar el envío automático de ejemplo, inicie una consola de Windows PowerShell como administrador y establezca los datos del valor **SubmitSamplesConsent** según una de las opciones siguientes:

|Configuración|Descripción|
|---|---|
| **0** -  **Preguntar siempre** | El servicio antivirus Microsoft Defender le pide que confirme el envío de todos los archivos necesarios. Esta es la configuración predeterminada para Microsoft Defender Antivirus, pero no se recomienda para instalaciones en Windows Server 2016 o 2019 o Windows Server 2022 sin una GUI. |
| **1**  -  **Enviar muestras seguras automáticamente** | El servicio antivirus Microsoft Defender envía todos los archivos marcados como "seguros" y solicita el resto de los archivos. |
| **2** -  **Nunca enviar** | El servicio antivirus de Microsoft Defender no solicita y no envía ningún archivo. |
| **3** -  **Enviar todos los ejemplos automáticamente** | El servicio antivirus de Microsoft Defender envía todos los archivos sin necesidad de confirmación. |

> [!NOTE]
> Esta opción no está disponible para Windows Server 2012 R2. 

## <a name="configure-automatic-exclusions"></a>Configuración de exclusiones automáticas

Para garantizar la seguridad y el rendimiento, algunas exclusiones se agregan automáticamente en función de los roles y características que se instalan al usar Microsoft Defender Antivirus en Windows Server 2016 o 2019 o Windows Server 2022.

Consulta [Configurar exclusiones en Microsoft Defender Antivirus en Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).

## <a name="passive-mode-and-windows-server"></a>Modo pasivo y Windows Server

Si usa un producto antivirus que no es de Microsoft como solución antivirus principal en Windows Server, debe establecer Microsoft Defender Antivirus en modo pasivo o en modo deshabilitado. Si el punto de conexión de Windows Server está incorporado a Microsoft Defender para punto de conexión, puede establecer Microsoft Defender Antivirus en modo pasivo. Si no usa Microsoft Defender para punto de conexión, establezca Microsoft Defender Antivirus en modo deshabilitado. 

> [!TIP]
> Consulte [Microsoft Defender Compatibilidad de Antivirus con otros productos de seguridad](microsoft-defender-antivirus-compatibility.md).

En la tabla siguiente se describen los métodos para establecer Microsoft Defender Antivirus en modo pasivo, deshabilitar Microsoft Defender Antivirus y desinstalar Microsoft Defender Antivirus:

| Procedure | Descripción |
|---|---|
| Establecer Microsoft Defender Antivirus en modo pasivo mediante una clave del Registro | Establezca la clave del `ForceDefenderPassiveMode` Registro como se indica a continuación: <br/>-Camino: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` <br/>-Nombre: `ForceDefenderPassiveMode` <br/>-Tipo: `REG_DWORD` <br/>-Valor: `1` |
| Desactivar la interfaz de usuario Microsoft Defender Antivirus mediante PowerShell | Abra Windows PowerShell como administrador y ejecute el siguiente cmdlet de PowerShell:`Uninstall-WindowsFeature -Name Windows-Defender-GUI`
| Deshabilitación de Microsoft Defender Antivirus mediante PowerShell | Use el siguiente cmdlet de PowerShell: `Set-MpPreference -DisableRealtimeMonitoring $true` |
| Deshabilitar Microsoft Defender Antivirus mediante el Asistente para quitar roles y características | Consulte [Instalar o desinstalar roles, servicios de rol o características](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard) y usar el **Asistente para quitar roles y características**. <br/><br/>Cuando llegue al paso **Características** del asistente, desactive la opción **características de Windows Defender**. <br/><br/> Si borra **Windows Defender** por sí mismo en la sección **características de Windows Defender**, se le pedirá que quite la GUI de la opción de interfaz **para Windows Defender**.<br/><br/>Microsoft Defender Antivirus seguirá ejecutándose normalmente sin la interfaz de usuario, pero la interfaz de usuario no se puede habilitar si deshabilita la característica **de Windows Defender** principal. |
| Desinstalación de Microsoft Defender Antivirus mediante PowerShell | Use el siguiente cmdlet de PowerShell: `Uninstall-WindowsFeature -Name Windows-Defender` |
| Deshabilite Microsoft Defender Antivirus mediante directiva de grupo | En el Editor de directiva de grupo local, vaya a **Plantilla** >  administrativa **Windows Component** > **Endpoint Protection** > **Disable Endpoint Protection (Deshabilitar Endpoint Protection**) y, a continuación, seleccione Enabled **OK (Aceptar** **habilitado).** >  |

Para obtener más información, vea [Trabajar con claves del Registro](/powershell/scripting/samples/working-with-registry-keys).

### <a name="are-you-using-windows-server-2012-r2-or-windows-server-2016"></a>¿Usa Windows Server 2012 R2 o Windows Server 2016?

Si windows Server está incorporado a Microsoft Defender para punto de conexión, ahora puede ejecutar Microsoft Defender Antivirus en modo pasivo en Windows Server 2012 R2 y Windows Server 2016. Consulte los siguientes artículos:

- [Opciones para instalar Microsoft Defender para punto de conexión](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages)

- [compatibilidad de Microsoft Defender Antivirus con otros productos de seguridad](microsoft-defender-antivirus-compatibility.md)

## <a name="see-also"></a>Vea también

- [Antivirus de Microsoft Defender en Windows](microsoft-defender-antivirus-windows.md)
