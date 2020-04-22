---
title: Proteger equipos con Windows 10 PC y Mac no administrados
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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Protéjase contra el phishing y otros ataques con Microsoft 365 para las campañas.
ms.openlocfilehash: 0cd96cb73ad3d0b38ab1e5ff31c913d97528c2d4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632796"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Proteger equipos con Windows 10 PC y Mac no administrados

Para administrar equipos con Windows 10 y equipos Mac, puede inscribirse en Microsoft Intune, lo que le permite asegurarse de que son correctos y seguros antes de obtener acceso a los datos de su entorno. Sin embargo, muchas campañas y pequeñas empresas incluyen el personal que lleva sus propios dispositivos (BYOD), que no se administrará en la organización. Para estos equipos PC y Mac no administrados, use este artículo para asegurarse de que las capacidades de seguridad mínima están configuradas. 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Proteger un equipo que ejecuta Windows 10 o un Mac

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Si tu organización no administra tu PC con Windows 10 o Mac, asegúrate de configurar estas funciones de seguridad.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)
**Activar el cifrado del dispositivo**<p>

El cifrado de dispositivos está disponible en una amplia gama de dispositivos Windows y ayuda a proteger los datos cifrándolos. Si activa el cifrado del dispositivo, solo podrán tener acceso a su dispositivo y a sus datos los usuarios autorizados. Consulte [activar el cifrado del dispositivo](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) para obtener instrucciones.

 Si el cifrado del dispositivo no está disponible en el dispositivo, puede activar el [cifrado de BitLocker](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) estándar en su lugar. (BitLocker no está disponible en Windows 10 Home Edition). 


**Proteger el dispositivo con la seguridad de Windows**<p>
Si tiene Windows 10, obtendrá la protección antivirus más reciente con la seguridad de Windows. Al iniciar Windows 10 por primera vez, la seguridad de Windows está activa y ayudando activamente a proteger tu equipo mediante la detección de malware (software malintencionado), virus y amenazas de seguridad. La seguridad de Windows usa la protección en tiempo real para analizar todo lo que descarga o ejecuta en el equipo.

Windows Update descarga automáticamente las actualizaciones para la seguridad de Windows para ayudar a mantener tu PC seguro y protegerlo de amenazas.

Si tiene una versión anterior de Windows y usa Microsoft Security Essentials, es una buena idea cambiar a la seguridad de Windows. Para obtener más información, consulte [ayudar a proteger el dispositivo con la seguridad de Windows](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).

**Activar Firewall de Windows**<p>
Siempre debe ejecutar Firewall de Windows incluso si tiene activado otro Firewall. Si se desactiva el Firewall de Windows, es posible que el dispositivo (y la red, si tiene uno) sean más vulnerables a un acceso no autorizado. Consulte [activar o desactivar Firewall de Windows](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) para obtener instrucciones

## <a name="mac"></a>[Mac](#tab/Mac)
**Usar FileVault para cifrar el disco Mac**<p>
El cifrado de disco protege los datos cuando se pierden o roban dispositivos. FileVault el cifrado de disco completo ayuda a impedir el acceso no autorizado a la información del disco de inicio. Consulte [usar FileVault para cifrar el disco de inicio en su Mac](https://support.apple.com/HT204837) para obtener instrucciones.

**Proteger su Mac del malware**<p>
Microsoft recomienda instalar y usar software antivirus fiable en su Mac. Vea el siguiente artículo para obtener una lista de opciones: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).

También puede reducir el riesgo del malware mediante el uso de software solo de orígenes confiables. Las opciones de configuración de seguridad & preferencias de privacidad le permiten especificar los orígenes del software instalado en su Mac. Para obtener más información, consulte [proteger su Mac del malware](https://support.apple.com/kb/PH25087).

**Activar la protección del firewall**<p>
Use la configuración del firewall para proteger su Mac del contacto no deseado iniciados por otros equipos cuando esté conectado a Internet o a una red. Sin esta protección, es posible que su Mac sea más vulnerable al acceso no autorizado. Consulte [acerca del firewall de la aplicación](https://support.apple.com/HT201642) para obtener instrucciones.
