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
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 04/01/2022
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 412033e274cce22b9350292c612b91ef6e34e209
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634853"
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
- Windows Server 2012 R2 (requiere Pertahanan Microsoft untuk Titik Akhir)

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>Configuración de Antivirus de Microsoft Defender en Windows Server

El proceso de configuración y ejecución de Antivirus de Microsoft Defender en Windows Server incluye los siguientes pasos:

1. [Habilite la interfaz](#enable-the-user-interface-on-windows-server).
2. [Instale Antivirus de Microsoft Defender](#install-microsoft-defender-antivirus-on-windows-server).
3. [Compruebe Antivirus de Microsoft Defender se está ejecutando](#verify-microsoft-defender-antivirus-is-running).
4. [Actualice la inteligencia de seguridad antimalware](#update-antimalware-security-intelligence).
5. (Según sea necesario) [Enviar ejemplos](#submit-samples).
6. (Según sea necesario) [Configurar exclusiones automáticas](#configure-automatic-exclusions).
7. (Solo si es necesario) Establezca [Windows server en modo pasivo](#passive-mode-and-windows-server).

## <a name="enable-the-user-interface-on-windows-server"></a>Habilitar la interfaz de usuario en Windows Server

> [!IMPORTANT]
> Si usas Windows Server 2012 R2, consulta [Opciones para instalar Pertahanan Microsoft untuk Titik Akhir](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages).

De forma predeterminada, Antivirus de Microsoft Defender está instalado y funcional en Windows Server. A veces, la interfaz de usuario (GUI) está instalada de forma predeterminada. La GUI no es necesaria; puede usar PowerShell, directiva de grupo u otros métodos para administrar Antivirus de Microsoft Defender. Sin embargo, muchas organizaciones prefieren usar la GUI para Antivirus de Microsoft Defender. Para instalar la GUI, use uno de los procedimientos de la tabla siguiente:

| Procedure | Qué hacer |
|:---|:---|
| Activar la GUI mediante el Asistente para agregar roles y características | 1. Vea [Instalar roles, servicios de](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard) roles y características mediante el Asistente para agregar roles y características y usar el Asistente para agregar **roles y características**. <br/><br/>2. Cuando llegue al paso Características del  asistente, en **Windows Defender características**, seleccione la **guia para Windows Defender**. |
| Activar la GUI con PowerShell | 1. En el servidor Windows, abra Windows PowerShell como administrador. <br/><br/>2. Ejecute el siguiente cmdlet de PowerShell: `Install-WindowsFeature -Name Windows-Defender-GUI` |

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>Instalar Antivirus de Microsoft Defender en Windows Server

Si necesita instalar o reinstalar Antivirus de Microsoft Defender en Windows Server, use uno de los procedimientos de la tabla siguiente:

| Procedure | Qué hacer |
|:---|:---|
| Use el Asistente para agregar roles y características para instalar Antivirus de Microsoft Defender | 1. Vea [Instalar o desinstalar roles, servicios de roles](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard) o características y use el Asistente **para agregar roles y características**. <br/><br/>2. Cuando llegue al paso **Características** del asistente, seleccione la Antivirus de Microsoft Defender configuración. También seleccione la **guia para Windows Defender** opción. |
| Use PowerShell para instalar Antivirus de Microsoft Defender | 1. En el servidor Windows, abra Windows PowerShell como administrador. <br/><br/>2. Ejecute el siguiente cmdlet de PowerShell: `Install-WindowsFeature -Name Windows-Defender` |

> [!NOTE]
> Los mensajes de evento para el motor de antimalware incluidos con Antivirus de Microsoft Defender pueden encontrarse en [Antivirus de Microsoft Defender eventos](troubleshoot-microsoft-defender-antivirus.md).

## <a name="verify-microsoft-defender-antivirus-is-running"></a>Comprobar Antivirus de Microsoft Defender se está ejecutando

Después de instalar (o reinstalar) Antivirus de Microsoft Defender, el siguiente paso es comprobar que se está ejecutando. Use los cmdlets de PowerShell en la tabla siguiente:

| Procedure | Cmdlet de PowerShell |
|:---|:---|
| Comprobar que Antivirus de Microsoft Defender se está ejecutando | `Get-Service -Name windefend` |
| Comprobar que la protección del firewall está activada | `Get-Service -Name mpssvc` |

Como alternativa a PowerShell, puede usar el símbolo del sistema para comprobar que Antivirus de Microsoft Defender se está ejecutando. Para ello, ejecute el siguiente comando desde un símbolo del sistema:

```cmd
sc query Windefend
```

El `sc query` comando devuelve información sobre el Antivirus de Microsoft Defender servicio. Cuando Antivirus de Microsoft Defender se está ejecutando, el `STATE` valor muestra `RUNNING`.

Para ver todos los servicios que no se están ejecutando, ejecute el siguiente cmdlet de PowerShell:

```cmd
sc query state= all
```

## <a name="update-antimalware-security-intelligence"></a>Actualizar inteligencia de seguridad antimalware

Para obtener las actualizaciones regulares de inteligencia de seguridad, el Windows Update debe estar en ejecución. Si usa un servicio de administración de actualizaciones, como Windows Server Update Services (WSUS), asegúrese de que las actualizaciones de la inteligencia de seguridad de Antivirus de Microsoft Defender están aprobadas para los equipos que administra.

De forma predeterminada, Windows Update descarga e instala actualizaciones automáticamente en Windows Server 2019 o Windows Server 2022 o Windows Server 2016. Puede cambiar esta configuración mediante uno de los métodos siguientes:

| Método | Descripción |
|---|---|
| **Windows Update** en Panel de control | **Instalar actualizaciones automáticamente da como** resultado que todas las actualizaciones se instalen automáticamente, incluidas Windows Defender de inteligencia de seguridad. <br/><br/> **Descargue las actualizaciones, pero permítanme** elegir si instalarlas permite Windows Defender descargar e instalar actualizaciones de inteligencia de seguridad automáticamente, pero otras actualizaciones no se instalan automáticamente. |
| **Directiva de grupo** | Puede configurar y administrar Windows Update mediante la configuración disponible en directiva de grupo, en la siguiente ruta de acceso: **Plantillas administrativas\componentes Windows\Windows Update\Configurar actualizaciones automáticas** |
| La **clave del Registro AUOptions** | Los dos valores siguientes permiten Windows Update descargar e instalar automáticamente las actualizaciones de inteligencia de seguridad: <br/><br/> **4** -  **Instale las actualizaciones automáticamente**. Este valor da como resultado que todas las actualizaciones se instalen automáticamente, incluidas Windows Defender de inteligencia de seguridad. <br/><br/> **3** -  **Descargue las actualizaciones, pero permítanme elegir si desea instalarlas**. Este valor permite Windows Defender descargar e instalar actualizaciones de inteligencia de seguridad automáticamente, pero otras actualizaciones no se instalan automáticamente. |

Para garantizar que se mantiene la protección contra malware, habilite los siguientes servicios:

- Informe de errores de Windows servicio
- Windows Update servicio

En la tabla siguiente se enumeran los servicios Antivirus de Microsoft Defender y los servicios dependientes.

| Nombre del servicio | Ubicación del archivo | Descripción |
|---|---|---|
| Windows Defender (WinDefend) | `C:\Program Files\Windows Defender\MsMpEng.exe` | Este es el servicio Antivirus de Microsoft Defender principal que debe ejecutarse siempre.|
| Informe de errores de Windows (Wersvc) | `C:\WINDOWS\System32\svchost.exe -k WerSvcGroup` | Este servicio devuelve informes de error a Microsoft. |
| Windows Defender firewall (MpsSvc) | `C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork` | Se recomienda mantener el servicio Windows Defender firewall habilitado. |
| Windows Update (Wuauserv) | `C:\WINDOWS\system32\svchost.exe -k netsvcs`| Windows Update para obtener actualizaciones de inteligencia de seguridad y actualizaciones del motor antimalware |

## <a name="submit-samples"></a>Enviar ejemplos

El envío de ejemplo permite a Microsoft recopilar muestras de software potencialmente malintencionado. Para ayudar a proporcionar una protección continua y actualizada, los investigadores de Microsoft usan estas muestras para analizar actividades sospechosas y producir inteligencia de seguridad antimalware actualizada. Recopilamos archivos ejecutables del programa, como .exe archivos y .dll archivos. No recopilamos archivos que contienen datos personales, como documentos Microsoft Word documentos y archivos PDF.

### <a name="submit-a-file"></a>Enviar un archivo

1. Revise la [guía de envío](/windows/security/threat-protection/intelligence/submission-guide).

2. Visite el portal [de envío de ejemplo](https://www.microsoft.com/wdsi/filesubmission) y envíe el archivo.

### <a name="enable-automatic-sample-submission"></a>Habilitar el envío automático de muestra

Para habilitar el envío automático de ejemplo, inicie una consola Windows PowerShell como administrador y establezca los datos de valor **SubmitSamplesConsent** de acuerdo con una de las opciones siguientes:

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

Si usa un producto antivirus que no sea de Microsoft como solución antivirus principal en Windows Server, debe establecer Antivirus de Microsoft Defender en modo pasivo o en modo deshabilitado. Si el Windows de servidor está incorporado a Pertahanan Microsoft untuk Titik Akhir, puede establecer Antivirus de Microsoft Defender en modo pasivo. Si no usa el Pertahanan Microsoft untuk Titik Akhir, establezca Antivirus de Microsoft Defender modo deshabilitado. 

> [!TIP]
> Consulte [Antivirus de Microsoft Defender compatibilidad con otros productos de seguridad](microsoft-defender-antivirus-compatibility.md).

En la tabla siguiente se describen los métodos para establecer Antivirus de Microsoft Defender modo pasivo, deshabilitar Antivirus de Microsoft Defender y desinstalar Antivirus de Microsoft Defender:

| Procedure | Descripción |
|---|---|
| Establecer Antivirus de Microsoft Defender en modo pasivo mediante una clave del Registro | Establezca la clave del Registro ForceDefenderPassiveMode de la siguiente manera: <br/>- Ruta de acceso: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` <br/>- Nombre: `ForceDefenderPassiveMode` <br/>- Tipo: `REG_DWORD` <br/>- Valor: `1` |
| Desactivar la interfaz Antivirus de Microsoft Defender usuario con PowerShell | Abra Windows PowerShell como administrador y ejecute el siguiente cmdlet de PowerShell:`Uninstall-WindowsFeature -Name Windows-Defender-GUI`
| Deshabilitar Antivirus de Microsoft Defender con PowerShell | Use el siguiente cmdlet de PowerShell: `Set-MpPreference -DisableRealtimeMonitoring $true` |
| Deshabilitar Antivirus de Microsoft Defender mediante el Asistente para quitar roles y características | Consulta [Instalar o desinstalar roles, servicios de roles o características](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard) y usa **el Asistente para quitar roles y características**. <br/><br/>Cuando llegue al paso **Características** del asistente, desactive la opción **Windows Defender características**. <br/><br/> Si borras **Windows Defender** en la sección **características de Windows Defender**, se te pedirá que quites la GUI de opción de interfaz para **Windows Defender**.<br/><br/>Antivirus de Microsoft Defender se ejecutará normalmente sin la interfaz de usuario, pero la interfaz de usuario no se puede habilitar si deshabilita la característica principal **Windows Defender** usuario. |
| Desinstalar Antivirus de Microsoft Defender con PowerShell | Use el siguiente cmdlet de PowerShell: `Uninstall-WindowsFeature -Name Windows-Defender` |
| Deshabilitar Antivirus de Microsoft Defender usar directiva de grupo | En el Editor de directiva de grupo local, vaya a **Plantilla** >  administrativa **Windows Componente** >  **Endpoint Protection** >  **Disable Endpoint Protection** y, a continuación, **seleccione EnabledOK** > . |

### <a name="are-you-using-windows-server-2012-r2-or-windows-server-2016"></a>¿Usa Windows Server 2012 R2 o Windows Server 2016?

Si el servidor Windows está incorporado a Pertahanan Microsoft untuk Titik Akhir, ahora puede ejecutar Antivirus de Microsoft Defender en modo pasivo en Windows Server 2012 R2 y Windows Server 2016. Consulte los siguientes artículos:

- [Opciones para instalar Pertahanan Microsoft untuk Titik Akhir](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages)

- [Antivirus de Microsoft Defender compatibilidad con otros productos de seguridad](microsoft-defender-antivirus-compatibility.md)

## <a name="see-also"></a>Vea también

- [Antivirus de Microsoft Defender en Windows](microsoft-defender-antivirus-windows.md)

