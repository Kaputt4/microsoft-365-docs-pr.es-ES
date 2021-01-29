---
title: Proteger equipos Windows 10 y Mac no administrados
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Proteger dispositivos no administrados o bring your own devices (BYOD) con Microsoft 365.
ms.openlocfilehash: 5c27b29b5bb4fb445655e671d8c654ad8e9abc6b
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044389"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Proteger equipos Windows 10 y Mac no administrados

Puedes administrar equipos Windows 10 y Mac inscribándolos en Microsoft Intune, lo que te permite asegurarte de que están en buen estado y seguros antes de acceder a los datos de tu entorno. Sin embargo, muchas campañas y pequeñas empresas incluyen personal que lleva sus propios dispositivos (BYOD), que la organización no administrará. Para estos equipos y Mac no administrados, use este artículo para asegurarse de que se configuran las funcionalidades de seguridad mínimas.

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Proteger un equipo que ejecute Windows 10 o mac

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Si tu equipo Windows 10 o Mac no está administrado por tu organización, asegúrate de configurar estas funcionalidades de seguridad.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**Activar el cifrado de dispositivos**<p>

El cifrado de dispositivos está disponible en una amplia variedad de dispositivos Windows y ayuda a proteger los datos mediante su cifrado. Si activas el cifrado del dispositivo, solo las personas autorizadas podrán acceder a tu dispositivo y datos. Consulta [activar el cifrado del dispositivo](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) para obtener instrucciones.

 Si el cifrado del dispositivo no está disponible en el dispositivo, puedes activar el cifrado [de BitLocker](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) estándar en su lugar. (BitLocker no está disponible en Windows 10 Home Edition). 

**Proteger el dispositivo con seguridad de Windows**<p>
Si tienes Windows 10, tendrás la protección antivirus más reciente con Seguridad de Windows. Cuando inicias Windows 10 por primera vez, Seguridad de Windows está activado y ayuda activamente a proteger tu equipo mediante el análisis de malware (software malintencionado), virus y amenazas de seguridad. Seguridad de Windows usa la protección en tiempo real para examinar todo lo que descargues o ejecutes en el equipo.

Windows Update descarga automáticamente las actualizaciones de Seguridad de Windows para ayudar a mantener su equipo seguro y protegerlo contra amenazas.

Si tienes una versión anterior de Windows y usas Microsoft Security Essentials, es una buena idea pasar a Seguridad de Windows. Para obtener más información, [consulta la ayuda para proteger mi dispositivo con Seguridad de Windows.](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)

**Activar Firewall de Windows**<p>
Siempre debe ejecutar Firewall de Windows incluso si tiene otro firewall activado. Desactivar Firewall de Windows puede hacer que tu dispositivo (y tu red, si tienes uno) sean más vulnerables al acceso no autorizado. Consulta [Activar o desactivar Firewall de Windows para](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) obtener instrucciones

## <a name="mac"></a>[Mac](#tab/Mac)

**Usar FileVault para cifrar el disco Mac**<p>
El cifrado de disco protege los datos cuando se pierden o roban dispositivos. El cifrado de disco completo de FileVault ayuda a evitar el acceso no autorizado a la información del disco de inicio. Consulta [usar FileVault para cifrar el disco de inicio en tu Mac](https://support.apple.com/HT204837) para obtener instrucciones.

**Proteger su mac contra malware**<p>
Microsoft recomienda instalar y usar software antivirus confiable en su Equipo Mac. Vea el siguiente artículo para obtener una lista de opciones: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).

También puede reducir el riesgo de malware mediante el uso de software solo de orígenes confiables. La configuración de las & privacidad le permite especificar los orígenes de software instalados en su Equipo Mac. Para obtener más información, [vea proteger su Equipo Mac contra malware.](https://support.apple.com/kb/PH25087)

**Activar la protección del firewall**<p>
Usa la configuración del firewall para proteger tu Equipo Mac contra contactos no deseados iniciados por otros equipos cuando estás conectado a Internet o a una red. Sin esta protección, es posible que el equipo Mac sea más vulnerable al acceso no autorizado. Consulte [sobre el firewall de la aplicación](https://support.apple.com/HT201642) para obtener instrucciones.
