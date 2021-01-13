---
title: Tecnologías de seguridad en escritorio administrado de Microsoft
description: Tecnologías usadas para la seguridad de dispositivos, la administración de identidades y accesos, la seguridad de red y la seguridad de la información
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5076ddca6053adc7cebb9599c8d82a42c7ab5a63
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840918"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Tecnologías de seguridad en escritorio administrado de Microsoft

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Escritorio administrado de Microsoft usa varias tecnologías de Microsoft para ayudar a proteger los datos y dispositivos administrados. Además, el Centro de operaciones de seguridad de escritorio administrado de Microsoft usa varios [procesos](security-operations.md) junto con estas tecnologías.

En particular: 

- [Seguridad de dispositivos:](#device-security) seguridad y protección en dispositivos de Escritorio administrado de Microsoft
- [Administración de identidades y acceso:](#identity-and-access-management) administración del uso seguro de dispositivos a través de los servicios de identidad de Azure Active Directory
- [Seguridad de red:](#network-security) información de VPN y configuración recomendadas para escritorio administrado de Microsoft
- [Seguridad de la](#information-security) información: servicios disponibles opcionales para proteger aún más la información confidencial 

Para obtener información sobre los procedimientos de almacenamiento, uso y seguridad de datos usados por el Escritorio administrado de Microsoft, consulte nuestras whitepaper en [https://aka.ms/mmd-data](https://aka.ms/mmd-data) .


## <a name="device-security"></a>Seguridad del dispositivo

Escritorio administrado de Microsoft garantiza que todos los dispositivos administrados estén protegidos y protegidos, y detecta las amenazas lo antes posible mediante los siguientes servicios:

Servicio | Descripción
--- | ---
Antivirus | El Antivirus de Microsoft Defender está instalado y configurado<br>Las definiciones del Antivirus de Microsoft Defender están actualizadas
Cifrado de volumen completo |    Windows BitLocker es la solución de cifrado de volumen para dispositivos de Escritorio administrado de Microsoft.<br><br>Una vez que una organización está incorporada en el servicio, los dispositivos se cifrarán con BitLocker de Windows con el Módulo de plataforma de confianza (TPM) integrado para evitar el acceso no autorizado a los datos locales cuando el dispositivo esté en modo de suspensión o desactivado. 
Supervisión |    Microsoft Defender para endpoint se usa para la supervisión de amenazas de seguridad en todos los dispositivos de Escritorio administrado de Microsoft. Defender for Endpoint permite a los clientes empresariales detectar, investigar y responder a amenazas avanzadas en su red corporativa. Para obtener más información, consulte [Microsoft Defender para Endpoint.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Actualizaciones del sistema operativo |  Los dispositivos de escritorio administrado de Microsoft siempre están protegidos con las últimas actualizaciones de seguridad.
Configuración de dispositivos seguros |   Escritorio administrado de Microsoft implementa la línea base de seguridad de Microsoft. Para obtener más información, consulta líneas [base de seguridad de Windows.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Administración de acceso e identidad  

La administración de identidades y acceso protege los activos corporativos y los datos críticos para la empresa. Escritorio administrado de Microsoft configura dispositivos para garantizar un uso seguro con identidades administradas de Azure Active Directory (Azure AD). Es responsabilidad del cliente mantener información precisa en su inquilino de Azure AD. 

Servicio | Descripción
--- | ---
Autenticación biométrica |  Windows Hello permite a los usuarios iniciar sesión con la cara o un PIN, lo que dificulta el olvido o el robo de contraseñas. Los clientes son responsables de implementar los requisitos previos necesarios para su Active Directory local para el uso de este servicio en una configuración híbrida. Para obtener más información, consulta [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
Permiso de usuario estándar |  Para proteger el sistema y hacerlo más seguro, al usuario se le asignarán permisos de usuario estándar. Este permiso se asigna como parte de la configuración de Windows Autopilot.



## <a name="network-security"></a>Seguridad de red

Los clientes son responsables de la seguridad de red. 

Servicio | Descripción
--- | ---
VPN | Los clientes son propietarios de su infraestructura de VPN, para garantizar que los recursos corporativos limitados se puedan exponer fuera de la intranet.<br><br>Requisito mínimo: Escritorio administrado de Microsoft requiere una solución VPN compatible con Windows 10 y compatible. Si tu organización necesita una solución VPN, debe admitir Windows 10 y empaquetarse e implementarse a través de Intune. Póngase en contacto con el editor de software para obtener más información.<br><br>Recomendación:<br>- Microsoft recomienda una solución de VPN moderna que se pueda implementar fácilmente a través de Intune para insertar perfiles de VPN. Este enfoque proporciona una forma continua, fluida, confiable y segura de acceder a la red corporativa. Para obtener más información, [vea [Configuración de VPN en Intune]](https://docs.microsoft.com/intune/vpn-settings-configure).<br>- Los clientes vpn gruesos o los clientes VPN más antiguos no son recomendados por Microsoft mientras se usa el escritorio administrado de Microsoft, ya que puede afectar al entorno de usuario.<br>- Microsoft recomienda que el tráfico web saliente vaya directamente a Internet sin pasar por la VPN para evitar problemas de rendimiento.<br>- Lo ideal es que Microsoft recomiende el uso de Azure Active Directory App Proxy en lugar de una VPN.


## <a name="information-security"></a>Seguridad de la información

Puedes configurar estos servicios opcionales para ayudar a proteger los activos corporativos de gran valor. 

Servicio | Descripción
--- | ---
Recuperación de datos  | La información almacenada en las carpetas clave del dispositivo se copia en OneDrive para la Empresa. Escritorio administrado de Microsoft no es responsable de los datos que no están sincronizados con OneDrive para la Empresa. 
Windows Information Protection |    Para las empresas que requieren altos niveles de seguridad de la información, recomendamos [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) y Azure Information [Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection) 

