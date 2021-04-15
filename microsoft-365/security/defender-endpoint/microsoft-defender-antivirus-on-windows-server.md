---
title: Antivirus de Microsoft Defender en Windows Server
description: Aprende a habilitar y configurar Microsoft Defender Antivirus en Windows Server 2016 y Windows Server 2019.
keywords: windows defender, server, scep, system center endpoint protection, server 2016, current branch, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: d9452b6d2eeaad3880894b9ec66c8bc71797b429
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764608"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Antivirus de Microsoft Defender en Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Antivirus de Microsoft Defender está disponible en las siguientes ediciones o versiones de Windows Server:
- Windows Server 2019
- Windows Server, versión 1803 o posterior
- Windows Server 2016. 

En algunos casos, Antivirus de Microsoft Defender se conoce como *Endpoint Protection*; sin embargo, el motor de protección es el mismo. Aunque la funcionalidad, configuración y administración son en gran medida las mismas para Antivirus de Microsoft Defender en [Windows 10,](microsoft-defender-antivirus-in-windows-10.md)existen algunas diferencias clave en Windows Server:

- En Windows Server, [las exclusiones automáticas](configure-server-exclusions-microsoft-defender-antivirus.md) se aplican en función del rol de servidor definido.
- En Windows Server, Antivirus de Microsoft Defender no se deshabilita automáticamente si ejecutas otro producto antivirus.

## <a name="the-process-at-a-glance"></a>El proceso de un vistazo

El proceso de configuración y ejecución de Antivirus de Microsoft Defender en una plataforma de servidor incluye varios pasos:

1. [Habilitar la interfaz](#enable-the-user-interface-on-windows-server).
2. [Instalar Antivirus de Microsoft Defender](#install-microsoft-defender-antivirus-on-windows-server).
3. [Compruebe que antivirus de Microsoft Defender se está ejecutando](#verify-microsoft-defender-antivirus-is-running).
4. [Actualizar la inteligencia de seguridad antimalware](#update-antimalware-security-intelligence).
5. (Según sea necesario) [Enviar ejemplos](#submit-samples).
6. (Según sea necesario) [Configurar exclusiones automáticas](#configure-automatic-exclusions).
7. (Solo si es necesario) [Establece Antivirus de Microsoft Defender en modo pasivo](#need-to-set-microsoft-defender-antivirus-to-passive-mode).

## <a name="enable-the-user-interface-on-windows-server"></a>Habilitar la interfaz de usuario en Windows Server

De forma predeterminada, Antivirus de Microsoft Defender está instalado y funciona en Windows Server. La interfaz de usuario (GUI) está instalada de forma predeterminada en algunas SKU, pero no es necesaria porque puede usar PowerShell u otros métodos para administrar Antivirus de Microsoft Defender. Si la GUI no está instalada en el servidor, puede agregarla mediante el Asistente para agregar **roles** y características o mediante cmdlets de PowerShell.

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>Activar la GUI mediante el Asistente para agregar roles y características

1. Consulte [Instalar roles, servicios de roles](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)y características mediante el Asistente para agregar roles y características y usar el Asistente para agregar roles y **características.**

2. Cuando llegue al paso **Características** del asistente, en **Windows Defender,** seleccione la **guia para Windows Defender.**

   En Windows Server 2016, el Asistente para agregar **roles y** características tiene este aspecto:

   ![Agregar roles y asistente para características que muestran la gui Windows Defender opción](images/server-add-gui.png)

   En Windows Server 2019, el Asistente para agregar roles y **características** es similar.

### <a name="turn-on-the-gui-using-powershell"></a>Activar la GUI con PowerShell

El siguiente cmdlet de PowerShell habilitará la interfaz: 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>Instalar Antivirus de Microsoft Defender en Windows Server

Puede usar el Asistente para agregar **roles y características** o PowerShell para instalar Antivirus de Microsoft Defender.

### <a name="use-the-add-roles-and-features-wizard"></a>Usar el Asistente para agregar roles y características

1. Consulte este [artículo y](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)use el Asistente para agregar roles **y características.**

2. Cuando llegues al paso **Características** del asistente, selecciona la opción Antivirus de Microsoft Defender. También seleccione la **GUI para Windows Defender** opción.

### <a name="use-powershell"></a>Usar PowerShell

Para usar PowerShell para instalar Microsoft Defender Antivirus, ejecute el siguiente cmdlet:

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

Los mensajes de evento para el motor de antimalware incluido con Antivirus de Microsoft Defender se pueden encontrar en [Eventos AV de Microsoft Defender.](troubleshoot-microsoft-defender-antivirus.md)


## <a name="verify-microsoft-defender-antivirus-is-running"></a>Comprobar que antivirus de Microsoft Defender se está ejecutando

Para comprobar que Antivirus de Microsoft Defender se está ejecutando en el servidor, ejecute el siguiente cmdlet de PowerShell:

```PowerShell
Get-Service -Name windefend
```

Para comprobar que la protección del firewall está activada, ejecute el siguiente cmdlet de PowerShell:

```PowerShell 
Get-Service -Name mpssvc
```

Como alternativa a PowerShell, puede usar el símbolo del sistema para comprobar que se está ejecutando Antivirus de Microsoft Defender. Para ello, ejecute el siguiente comando desde un símbolo del sistema: 

```console
sc query Windefend
```

El `sc query` comando devuelve información sobre el servicio Antivirus de Microsoft Defender. Cuando se ejecuta Antivirus de Microsoft Defender, `STATE` el valor muestra `RUNNING` .

## <a name="update-antimalware-security-intelligence"></a>Actualizar inteligencia de seguridad antimalware 

Para obtener la inteligencia de seguridad antimalware actualizada, debe tener el servicio Windows Update en ejecución. Si usas un servicio de administración de actualizaciones, como Windows Server Update Services (WSUS), asegúrate de que las actualizaciones de inteligencia de Seguridad antivirus de Microsoft Defender estén aprobadas para los equipos que administras.

De forma predeterminada, Windows Update no descarga e instala actualizaciones automáticamente en Windows Server 2019 o Windows Server 2016. Puede cambiar esta configuración mediante uno de los métodos siguientes:


|Método  |Descripción  |
|---------|---------|
|**Windows Update** en el Panel de control     |- **Instalar actualizaciones automáticamente da como** resultado que todas las actualizaciones se instalen automáticamente, incluidas Windows Defender de inteligencia de seguridad. <br/>- **Descargue las actualizaciones, pero permítanme** elegir si instalarlas permite a Windows Defender descargar e instalar actualizaciones de inteligencia de seguridad automáticamente, pero otras actualizaciones no se instalan automáticamente.       |
|**Directiva de grupo**     | Puedes configurar y administrar Windows Update mediante la configuración disponible en la directiva de grupo, en la siguiente ruta de acceso: **Plantillas administrativas\Componentes de Windows\Windows Update\Configurar actualizaciones automáticas**         |
|La **clave del Registro AUOptions**     |Los dos valores siguientes permiten a Windows Update descargar e instalar automáticamente las actualizaciones de inteligencia de seguridad: <br/>- **4**  -  **Instalar actualizaciones automáticamente**. Este valor da como resultado que todas las actualizaciones se instalen automáticamente, incluidas Windows Defender de inteligencia de seguridad. <br/>- **3**  -  **Descargue las actualizaciones, pero permítanme elegir si desea instalarlas.**  Este valor permite Windows Defender descargar e instalar actualizaciones de inteligencia de seguridad automáticamente, pero otras actualizaciones no se instalan automáticamente.         |

Para garantizar que se mantiene la protección contra malware, se recomienda habilitar los siguientes servicios:

- Servicio de informes de errores de Windows

- Servicio de Windows Update

En la tabla siguiente se enumeran los servicios de Antivirus de Microsoft Defender y los servicios dependientes.

|Nombre del servicio|Ubicación del archivo|Descripción|
|--------|---------|--------|
|Windows Defender (WinDefend)|`C:\Program Files\Windows Defender\MsMpEng.exe`|Este es el servicio antivirus principal de Microsoft Defender que debe ejecutarse en todo momento.|
|Servicio de informes de errores de Windows (Wersvc)|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|Este servicio devuelve informes de error a Microsoft.|
|Windows Defender firewall (MpsSvc)|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|Se recomienda dejar el servicio Windows Defender firewall habilitado.|
|Windows Update (Wuauserv)|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|Windows Update es necesario para obtener actualizaciones de inteligencia de seguridad y actualizaciones del motor de antimalware|

## <a name="submit-samples"></a>Enviar ejemplos

El envío de ejemplo permite a Microsoft recopilar muestras de software potencialmente malintencionado. Para ayudar a proporcionar una protección continua y actualizada, los investigadores de Microsoft usan estas muestras para analizar actividades sospechosas y producir inteligencia de seguridad antimalware actualizada. Recopilamos archivos ejecutables del programa, como archivos .exe y archivos .dll. No recopilamos archivos que contienen datos personales, como documentos de Microsoft Word y archivos PDF.

### <a name="submit-a-file"></a>Enviar un archivo

1. Revise la [guía de envío](/windows/security/threat-protection/intelligence/submission-guide).

2. Visite el portal [de envío de ejemplo](https://www.microsoft.com/wdsi/filesubmission)y envíe el archivo.


### <a name="enable-automatic-sample-submission"></a>Habilitar el envío automático de muestra

Para habilitar el envío automático de ejemplo, inicie una consola Windows PowerShell como administrador y establezca los datos de valor **SubmitSamplesConsent** de acuerdo con una de las opciones siguientes:

|Configuración  |Descripción  |
|---------|---------|
|**0**  -  **Preguntar siempre**     |El servicio Antivirus de Microsoft Defender le pide que confirme el envío de todos los archivos necesarios. Esta es la configuración predeterminada para Antivirus de Microsoft Defender, pero no se recomienda para instalaciones en Windows Server 2016 o 2019 sin una GUI.         |
|**1**   -  **Enviar muestras seguras automáticamente**     |El servicio Antivirus de Microsoft Defender envía todos los archivos marcados como "seguros" y solicita el resto de los archivos.         |
|**2**  -  **Nunca enviar**      |El servicio antivirus de Microsoft Defender no solicita y no envía ningún archivo.         |
|**3**  -  **Enviar todas las muestras automáticamente**     |El servicio Antivirus de Microsoft Defender envía todos los archivos sin necesidad de confirmación.         |

## <a name="configure-automatic-exclusions"></a>Configurar exclusiones automáticas

Para garantizar la seguridad y el rendimiento, se agregan automáticamente determinadas exclusiones en función de los roles y características que instales al usar Antivirus de Microsoft Defender en Windows Server 2016 o 2019.

Consulta [Configurar exclusiones en Antivirus de Microsoft Defender en Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md). 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a>¿Necesita establecer Antivirus de Microsoft Defender en modo pasivo?

Si usa un producto antivirus que no sea de Microsoft como solución antivirus principal, establezca Antivirus de Microsoft Defender en modo pasivo.  

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>Establecer Antivirus de Microsoft Defender en modo pasivo con una clave del Registro

Si usa Windows Server, versión 1803 o Windows Server 2019, puede establecer Antivirus de Microsoft Defender en modo pasivo estableciendo la siguiente clave del Registro:
- Ruta de acceso: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Nombre: `ForcePassiveMode`
- Tipo: `REG_DWORD`
- Valor: `1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>Deshabilitar Antivirus de Microsoft Defender con el Asistente para quitar roles y características

1. Vea [Instalar o desinstalar roles, servicios de roles o características](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)y use el Asistente para quitar roles y **características.** 

2. Cuando llegue al paso **Características** del asistente, desactive la **opción Windows Defender Características.** 

    Si borras **Windows Defender** en la sección Características de **Windows Defender,** se te pedirá que quites la gui de opción de interfaz para **Windows Defender**. 
    
    Antivirus de Microsoft Defender seguirá ejecundo normalmente sin la interfaz de usuario, pero la interfaz de usuario no se puede habilitar si deshabilita la característica **principal Windows Defender** usuario.

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>Desactivar la interfaz de usuario de Antivirus de Microsoft Defender con PowerShell

Para desactivar la GUI de Antivirus de Microsoft Defender, use el siguiente cmdlet de PowerShell:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a>¿Estás usando Windows Server 2016?

Si usas Windows Server 2016 y un producto antivirus o antimalware de terceros que Microsoft no ofrece ni desarrolla, tendrás que deshabilitar o desinstalar Antivirus de Microsoft Defender. 

> [!NOTE]
> No puedes desinstalar la aplicación seguridad de Windows, pero puedes deshabilitar la interfaz con estas instrucciones.

El siguiente cmdlet de PowerShell desinstala Antivirus de Microsoft Defender en Windows Server 2016:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

## <a name="see-also"></a>Vea también

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Compatibilidad con Antivirus de Microsoft Defender](microsoft-defender-antivirus-compatibility.md)