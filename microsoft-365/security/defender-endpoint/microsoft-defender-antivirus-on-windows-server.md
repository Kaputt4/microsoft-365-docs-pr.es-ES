---
title: Antivirus de Microsoft Defender en Windows Server
description: Obtenga información sobre cómo habilitar y configurar Antivirus de Microsoft Defender en Windows Server 2016 y Windows Server 2019.
keywords: windows defender, server, scep, system center endpoint protection, server 2016, current branch, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 05/13/2021
ms.openlocfilehash: 1a1083d15698eb5bbdf2f6080b152b6f326c689a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539280"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Antivirus de Microsoft Defender en Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Antivirus de Microsoft Defender está disponible en las siguientes ediciones o versiones de Windows Server:
- Windows Server 2019
- Windows Servidor, versión 1803 o posterior
- Windows Server 2016. 

En algunos casos, Antivirus de Microsoft Defender se conoce como *Endpoint Protection*; sin embargo, el motor de protección es el mismo. Aunque la funcionalidad, la configuración y la administración son en gran medida las mismas para Antivirus de Microsoft Defender en [Windows 10,](microsoft-defender-antivirus-in-windows-10.md)hay algunas diferencias clave en Windows Server:

- En Windows server, [las exclusiones automáticas](configure-server-exclusions-microsoft-defender-antivirus.md) se aplican en función del rol de servidor definido.
 
- En Windows Server, si está ejecutando una solución antivirus o antimalware que no sea de Microsoft, Antivirus de Microsoft Defender no entra en modo pasivo ni en modo deshabilitado automáticamente. Sin embargo, puede establecer Antivirus de Microsoft Defender modo pasivo o deshabilitado manualmente.

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>Configuración de Antivirus de Microsoft Defender en Windows Server

El proceso de configuración y ejecución de Antivirus de Microsoft Defender en una plataforma de servidor incluye varios pasos:

1. [Habilitar la interfaz](#enable-the-user-interface-on-windows-server).
2. [Instalar Antivirus de Microsoft Defender](#install-microsoft-defender-antivirus-on-windows-server).
3. [Compruebe Antivirus de Microsoft Defender se está ejecutando](#verify-microsoft-defender-antivirus-is-running).
4. [Actualizar la inteligencia de seguridad antimalware](#update-antimalware-security-intelligence).
5. (Según sea necesario) [Enviar ejemplos](#submit-samples).
6. (Según sea necesario) [Configurar exclusiones automáticas](#configure-automatic-exclusions).
7. (Solo si es necesario) [Establezca Antivirus de Microsoft Defender en modo pasivo](#need-to-set-microsoft-defender-antivirus-to-passive-mode).

## <a name="enable-the-user-interface-on-windows-server"></a>Habilitar la interfaz de usuario en Windows Server

De forma predeterminada, Antivirus de Microsoft Defender está instalado y funcional en Windows server. A veces, la interfaz de usuario (GUI) se instala de forma predeterminada, pero no es necesaria. Puede usar PowerShell, directiva de grupo u otros métodos para administrar Antivirus de Microsoft Defender. 

Si la GUI no está instalada en el servidor y desea instalarla, el Asistente para agregar **roles** y características o cmdlets de PowerShell.

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>Activar la GUI mediante el Asistente para agregar roles y características

1. Consulte [Instalar roles, servicios de roles](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)y características mediante el Asistente para agregar roles y características y usar el Asistente para agregar roles y **características.**

2. Cuando llegue al paso **Características** del asistente, en **Windows Defender Características,** seleccione la **guia para Windows Defender.**

   En Windows Server 2016, el **Asistente** para agregar roles y características tiene este aspecto:

   ![Agregar roles y asistente para características que muestran la gui Windows Defender opción](images/server-add-gui.png)

   En Windows Server 2019, el Asistente para agregar **roles y** características es similar.

### <a name="turn-on-the-gui-using-powershell"></a>Activar la GUI con PowerShell

El siguiente cmdlet de PowerShell habilitará la interfaz: 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>Instalar Antivirus de Microsoft Defender en Windows Server

Si necesita instalar o reinstalar Antivirus de Microsoft Defender en Windows Server, puede hacerlo con el Asistente para agregar **roles** y características o PowerShell.

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a>Use el Asistente para agregar roles y características para instalar Antivirus de Microsoft Defender

1. Consulte este [artículo y](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)use el Asistente para agregar roles **y características.**

2. Cuando llegue al paso **Características** del asistente, seleccione la Antivirus de Microsoft Defender configuración. También seleccione la **guia para Windows Defender** opción.

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a>Use PowerShell para instalar Antivirus de Microsoft Defender

Para usar PowerShell para instalar Antivirus de Microsoft Defender, ejecute el siguiente cmdlet:

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

Los mensajes de evento para el motor de antimalware incluidos Antivirus de Microsoft Defender pueden encontrarse en [Eventos AV de Microsoft Defender](troubleshoot-microsoft-defender-antivirus.md).


## <a name="verify-microsoft-defender-antivirus-is-running"></a>Comprobar Antivirus de Microsoft Defender se está ejecutando

Una Antivirus de Microsoft Defender está instalada, el siguiente paso es comprobar que se está ejecutando. En el Windows de servidor, ejecute el siguiente cmdlet de PowerShell:

```PowerShell
Get-Service -Name windefend
```

Para comprobar que la protección del firewall está activada, ejecute el siguiente cmdlet de PowerShell:

```PowerShell 
Get-Service -Name mpssvc
```

Como alternativa a PowerShell, puede usar el símbolo del sistema para comprobar que Antivirus de Microsoft Defender se está ejecutando. Para ello, ejecute el siguiente comando desde un símbolo del sistema: 

```console
sc query Windefend
```

El `sc query` comando devuelve información sobre el Antivirus de Microsoft Defender servicio. Cuando Antivirus de Microsoft Defender se está ejecutando, `STATE` el valor muestra `RUNNING` .

## <a name="update-antimalware-security-intelligence"></a>Actualizar inteligencia de seguridad antimalware 

Para obtener la inteligencia de seguridad antimalware actualizada, debe tener el servicio Windows update en ejecución. Si usa un servicio de administración de actualizaciones, como Windows Server Update Services (WSUS), asegúrese de que las actualizaciones de la inteligencia de seguridad de Antivirus de Microsoft Defender están aprobadas para los equipos que administra.

De forma predeterminada, Windows Update no descarga e instala actualizaciones automáticamente en Windows Server 2019 o Windows Server 2016. Puede cambiar esta configuración mediante uno de los métodos siguientes:


|Método  |Descripción  |
|---------|---------|
|**Windows actualización en** el Panel de control     | **Instalar actualizaciones automáticamente da como** resultado que todas las actualizaciones se instalen automáticamente, incluidas Windows Defender de inteligencia de seguridad. <p>**Descargue las actualizaciones, pero permítanme** elegir si instalarlas permite a Windows Defender descargar e instalar actualizaciones de inteligencia de seguridad automáticamente, pero otras actualizaciones no se instalan automáticamente.       |
|**Directiva de grupo**     | Puede configurar y administrar Windows Update mediante la configuración disponible en la directiva de grupo, en la siguiente ruta de acceso: **Plantillas administrativas\componentes Windows\Windows Actualizar\Configurar** actualizaciones automáticas         |
|La **clave del Registro AUOptions**     | Los dos valores siguientes permiten a Windows Update descargar e instalar automáticamente las actualizaciones de inteligencia de seguridad: <p>**4**  -  **Instalar actualizaciones automáticamente**. Este valor da como resultado que todas las actualizaciones se instalen automáticamente, incluidas Windows Defender de inteligencia de seguridad. <p>**3**  -  **Descargue las actualizaciones, pero permítanme elegir si desea instalarlas.**  Este valor permite Windows Defender descargar e instalar actualizaciones de inteligencia de seguridad automáticamente, pero otras actualizaciones no se instalan automáticamente.         |

Para garantizar que se mantiene la protección contra malware, se recomienda habilitar los siguientes servicios:

- Informe de errores de Windows servicio

- Windows Actualizar servicio

En la tabla siguiente se enumeran los servicios Antivirus de Microsoft Defender y los servicios dependientes.

|Nombre del servicio|Ubicación del archivo|Descripción|
|--------|---------|--------|
|Windows Defender Servicio (WinDefend)|`C:\Program Files\Windows Defender\MsMpEng.exe`|Este es el servicio Antivirus de Microsoft Defender principal que debe ejecutarse en todo momento.|
|Informe de errores de Windows Servicio (Wersvc)|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|Este servicio devuelve informes de error a Microsoft.|
|Firewall de Windows Defender (MpsSvc)|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|Se recomienda dejar el servicio Firewall de Windows Defender habilitado.|
|Windows Actualización (Wuauserv)|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|Windows La actualización es necesaria para obtener actualizaciones de inteligencia de seguridad y actualizaciones del motor antimalware|

## <a name="submit-samples"></a>Enviar ejemplos

El envío de ejemplo permite a Microsoft recopilar muestras de software potencialmente malintencionado. Para ayudar a proporcionar una protección continua y actualizada, los investigadores de Microsoft usan estas muestras para analizar actividades sospechosas y producir inteligencia de seguridad antimalware actualizada. Recopilamos archivos ejecutables del programa, como .exe archivos y .dll archivos. No recopilamos archivos que contienen datos personales, como documentos Microsoft Word documentos y archivos PDF.

### <a name="submit-a-file"></a>Enviar un archivo

1. Revise la [guía de envío](/windows/security/threat-protection/intelligence/submission-guide).

2. Visite el portal [de envío de ejemplo](https://www.microsoft.com/wdsi/filesubmission)y envíe el archivo.


### <a name="enable-automatic-sample-submission"></a>Habilitar el envío automático de muestra

Para habilitar el envío automático de ejemplo, inicie una consola Windows PowerShell como administrador y establezca los datos de valor **SubmitSamplesConsent** de acuerdo con una de las opciones siguientes:

|Configuración  |Descripción  |
|---------|---------|
|**0**  -  **Preguntar siempre**     |El Antivirus de Microsoft Defender solicita que confirme el envío de todos los archivos necesarios. Esta es la configuración predeterminada para Antivirus de Microsoft Defender, pero no se recomienda para instalaciones en Windows Server 2016 o 2019 sin una GUI.         |
|**1**   -  **Enviar muestras seguras automáticamente**     |El Antivirus de Microsoft Defender envía todos los archivos marcados como "seguros" y solicita el resto de los archivos.         |
|**2**  -  **Nunca enviar**      |El Antivirus de Microsoft Defender no solicita y no envía ningún archivo.         |
|**3**  -  **Enviar todas las muestras automáticamente**     |El Antivirus de Microsoft Defender envía todos los archivos sin necesidad de confirmación.         |

## <a name="configure-automatic-exclusions"></a>Configurar exclusiones automáticas

Para garantizar la seguridad y el rendimiento, se agregan automáticamente determinadas exclusiones en función de los roles y características que se instalan al usar Antivirus de Microsoft Defender en Windows Server 2016 o 2019.

Vea [Configure exclusions in Antivirus de Microsoft Defender on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md). 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a>¿Necesita establecer Antivirus de Microsoft Defender en modo pasivo?

Si usa un producto antivirus que no sea de Microsoft como solución antivirus principal en Windows Server, debe establecer Antivirus de Microsoft Defender en modo pasivo o en modo deshabilitado.

- En Windows Server, versión 1803 o posterior, o Windows Server 2019, puede establecer Antivirus de Microsoft Defender en modo pasivo.  

- En Windows Server 2016, Antivirus de Microsoft Defender no se admite junto con un producto antivirus o antimalware que no sea de Microsoft. En estos casos, debe establecer Antivirus de Microsoft Defender modo deshabilitado.

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>Establecer Antivirus de Microsoft Defender en modo pasivo mediante una clave del Registro

Si usa Windows Server, versión 1803 o Windows Server 2019, puede establecer Antivirus de Microsoft Defender en modo pasivo estableciendo la siguiente clave del Registro:
- Ruta de acceso: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Nombre: `ForceDefenderPassiveMode`
- Tipo: `REG_DWORD`
- Valor: `1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>Deshabilitar Antivirus de Microsoft Defender mediante el Asistente para quitar roles y características

1. Vea [Instalar o desinstalar roles, servicios de roles o características](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)y use el Asistente para quitar roles y **características.** 

2. Cuando llegue al paso **Características** del asistente, desactive la **opción Windows Defender características.** 

    Si borras **Windows Defender** en la sección características de **Windows Defender,** se te pedirá que quites la **guia** de opción de interfaz para Windows Defender . 
    
    Antivirus de Microsoft Defender se ejecutará normalmente sin la interfaz de usuario, pero la interfaz de usuario no se puede habilitar si deshabilita la característica principal **Windows Defender** usuario.

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>Desactivar la interfaz Antivirus de Microsoft Defender usuario con PowerShell

Para desactivar la GUI Antivirus de Microsoft Defender, use el siguiente cmdlet de PowerShell:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a>¿Estás usando Windows Server 2016?

Si usas Windows Server 2016 y un producto antivirus o antimalware de terceros que microsoft no ofrece ni desarrolla, tendrás que deshabilitar o desinstalar Antivirus de Microsoft Defender. 

> [!NOTE]
> No puedes desinstalar la aplicación Seguridad de Windows, pero puedes deshabilitar la interfaz con estas instrucciones.

El siguiente cmdlet de PowerShell desinstala Antivirus de Microsoft Defender en Windows Server 2016:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

Para deshabilitar Antivirus de Microsoft Defender en Windows Server 2016, use el siguiente cmdlet de PowerShell:

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a>Vea también

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Antivirus de Microsoft Defender compatibilidad](microsoft-defender-antivirus-compatibility.md)
