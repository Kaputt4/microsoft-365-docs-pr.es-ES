---
title: Proteger equipos Windows 10 y Mac no administrados
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
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
description: Proteja dispositivos no administrados o bring-your-own (BYOD) con Microsoft 365.
ms.openlocfilehash: 430f5446f86c26cb1f0fd1c7f34613cddec473b2
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398258"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Proteger equipos Windows 10 y Mac no administrados

Puede administrar Windows 10 equipos y Mac inscribándolos en Microsoft Intune, lo que le permite asegurarse de que están en buen estado y seguros antes de acceder a los datos del entorno. Sin embargo, muchas campañas y pequeñas empresas incluyen personal que trae sus propios dispositivos (BYOD), que la organización no administrará. Para estos equipos y Mac no administrados, use este artículo para asegurarse de que se configuran las capacidades de seguridad mínimas.

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Proteger un equipo que ejecuta Windows 10 o un Mac

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Si su Windows 10 pc o Mac no está administrado por su organización, asegúrese de configurar estas capacidades de seguridad.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**Activar el cifrado de dispositivos**<p>

El cifrado de dispositivos está disponible en una amplia variedad de Windows dispositivos y ayuda a proteger los datos al cifrarlos. Si activas el cifrado de dispositivos, solo las personas autorizadas podrán acceder al dispositivo y a los datos. Consulta [Activar el cifrado de dispositivos](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) para obtener instrucciones.

 Si el cifrado de dispositivo no está disponible en el dispositivo, puedes activar el cifrado [BitLocker en](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) su lugar. (BitLocker no está disponible en Windows 10 Home edición). 

**Proteger el dispositivo con Seguridad de Windows**<p>
Si tienes Windows 10, tendrás la protección antivirus más reciente con Seguridad de Windows. Cuando se inicia Windows 10 por primera vez, Seguridad de Windows está activa y ayuda activamente a proteger el equipo mediante el examen de malware (software malintencionado), virus y amenazas de seguridad. Seguridad de Windows la protección en tiempo real para examinar todo lo que descarga o ejecuta en el equipo.

Windows Update descarga automáticamente las actualizaciones de Seguridad de Windows para ayudar a mantener su equipo seguro y protegerlo contra amenazas.

Si tienes una versión anterior de Windows y estás usando Microsoft Security Essentials, es una buena idea pasar a Seguridad de Windows. Para obtener más información, [consulta ayuda a proteger mi dispositivo con Seguridad de Windows](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).

**Activar el firewall Windows de seguridad**<p>
Siempre debe ejecutar el firewall Windows aunque tenga otro firewall activado. Desactivar Windows firewall podría hacer que el dispositivo (y su red, si tiene uno) sean más vulnerables al acceso no autorizado. Consulta [Activar o desactivar Windows firewall](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) para obtener instrucciones.

## <a name="mac"></a>[Mac](#tab/Mac)

**Usar FileVault para cifrar el disco mac**<p>
El cifrado de disco protege los datos cuando se pierden o se roban dispositivos. El cifrado de disco completo de FileVault ayuda a evitar el acceso no autorizado a la información del disco de inicio. Consulta [Usar FileVault para cifrar el disco de inicio en tu Mac](https://support.apple.com/HT204837) para obtener instrucciones.

**Proteger el mac contra malware**<p>
Microsoft recomienda instalar y usar software antivirus confiable en su Mac. Vea el siguiente artículo para obtener una lista de opciones: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).

También puede reducir el riesgo de malware mediante el uso de software solo desde orígenes confiables. La configuración de Seguridad & Preferencias de privacidad te permiten especificar los orígenes de software instalados en tu Mac. Para obtener más información, [consulta proteger tu Mac contra malware.](https://support.apple.com/kb/PH25087)

**Activar la protección de firewall**<p>
Usa la configuración del firewall para proteger tu Mac de contactos no deseados iniciados por otros equipos cuando estás conectado a Internet o a una red. Sin esta protección, es posible que tu Mac sea más vulnerable al acceso no autorizado. Consulte [sobre el firewall de aplicaciones](https://support.apple.com/HT201642) para obtener instrucciones.
