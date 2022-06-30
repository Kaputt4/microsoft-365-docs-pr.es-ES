---
title: Protección de equipos Mac y Windows no administrados en Microsoft 365 para la Empresa Premium
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
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
description: Proteja dispositivos no administrados o sus propios dispositivos (BYOD) frente a ciberataques con Microsoft 365 Empresa Premium. Cómo configurar la ciberseguridad para equipos Windows y Mac.
ms.openlocfilehash: 32f491e1a124bacf50f0efa553f6b141c08409b9
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66489132"
---
# <a name="protect-unmanaged-windows-pcs-and-macs-in-microsoft-365-business-premium"></a>Protección de equipos Mac y Windows no administrados en Microsoft 365 para la Empresa Premium

Este objetivo se centra en la creación de protección para los equipos Mac y Windows 10 no administrados que no estén inscritos en Microsoft Intune. Es muy probable que su pequeña empresa o campaña tenga personal que lleve sus propios dispositivos (BYOD) y estos dispositivos no estén administrados. Los BYOD incluyen teléfonos, tabletas y PC de propiedad personal.

>[!NOTE]
>Cada usuario BYOD debe instalar y ejecutar la aplicación Portal de empresa de Intune para inscribir estos dispositivos y recibir acceso a los recursos de la empresa.

Es fundamental garantizar que los usuarios de primera línea siguen estas directrices para que las funcionalidades de seguridad mínimas estén configuradas en todos los dispositivos BYOD.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**Activar el cifrado de dispositivos**<p>
El cifrado de dispositivos está disponible en una amplia gama de dispositivos Windows y ayuda a proteger los datos cifrándolos. Si activa el cifrado de dispositivos, solo los usuarios autorizados podrán acceder al dispositivo y a los datos. Consulte [activar el cifrado de dispositivos](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) para obtener instrucciones.

 Si el cifrado de dispositivos no está disponible en el dispositivo, puede activar el [cifrado BitLocker](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) estándar en su lugar. (BitLocker no está disponible en la edición Windows 10 Home). 

**Proteger el dispositivo con Seguridad de Windows**<p>
Si tiene Windows 10, obtendrá la protección antivirus más reciente con Seguridad de Windows. Al iniciar Windows 10 por primera vez, Seguridad de Windows estará activado y ayudando constantemente a proteger el equipo mediante la detección de malware (software malintencionado), virus y amenazas de seguridad. Seguridad de Windows usa protección en tiempo real para analizar todo lo que descargue o ejecute en su equipo.

Windows Update descarga automáticamente las actualizaciones de Seguridad de Windows para ayudar a mantener su equipo seguro y protegerlo contra amenazas.

Si tiene una versión anterior de Windows y usa Microsoft Security Essentials, es una buena idea pasar a Seguridad de Windows. Para obtener más información, consulte [ayuda proteger mi dispositivo con Seguridad de Windows](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).

**Activar el Firewall de Windows**<p>
Siempre debería ejecutar el Firewall de Windows aunque tenga otro firewall activado. Desactivar el Firewall de Windows puede hacer que su dispositivo (y la red, si tiene una) sea más vulnerable al acceso no autorizado. Consulte [Activar o desactivar Firewall de Windows](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) para obtener instrucciones.

## <a name="next-mission"></a>Próxima misión

¡De acuerdo, misión completada! Ahora, vamos a trabajar en [proteger el sistema de correo electrónico](m365bp-protect-email-overview.md) contra la suplantación de identidad (phishing) y otros ataques.

## <a name="mac"></a>[Mac](#tab/Mac)

**Usar FileVault para cifrar el disco Mac**<p>
El cifrado de disco protege los datos cuando los dispositivos se extravían por pérdida o robo. El cifrado de disco completo de FileVault ayuda a impedir el acceso no autorizado a la información en el disco de inicio. Consulte [usar FileVault para cifrar el disco de inicio en su Mac](https://support.apple.com/HT204837) para obtener instrucciones.

**Proteger su Mac frente al malware**<p>
Microsoft le recomienda instalar y usar software antivirus fiable en su Mac. Consulte el siguiente artículo para obtener una lista de opciones: [Mejores antivirus Mac 2019](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).

También puede reducir el riesgo de malware usando solo software de orígenes fiables. La configuración de preferencias de Seguridad y privacidad le permite especificar los orígenes del software instalado en su Mac. Para obtener más información, consulte [proteger el equipo Mac contra malware](https://support.apple.com/kb/PH25087).

**Activar la protección de firewall**<p>
Use la configuración de firewall para impedir contactos no deseados con su Mac iniciados por otros equipos cuando esté conectado a Internet o a una red. Sin esta protección su Mac podría ser más vulnerable al acceso no autorizado. Consulte [sobre la aplicación firewall](https://support.apple.com/HT201642) para obtener instrucciones.

## <a name="next-mission"></a>Próxima misión

¡De acuerdo, misión completada! Ahora, vamos a trabajar en [proteger el sistema de correo electrónico](m365bp-protect-email-overview.md) contra la suplantación de identidad (phishing) y otros ataques.