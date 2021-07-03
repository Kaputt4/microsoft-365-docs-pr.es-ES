---
title: Tecnologías de seguridad en Escritorio administrado de Microsoft
description: Tecnologías usadas para la seguridad de dispositivos, la administración de identidades y acceso, la seguridad de red y la seguridad de la información
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 07d4632c6ce775d98d9606f9edc4566aa48d9d8e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287812"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Tecnologías de seguridad en Escritorio administrado de Microsoft

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Escritorio administrado de Microsoft varias tecnologías de Microsoft para ayudar a proteger los datos y dispositivos administrados. Además, el Centro Escritorio administrado de Microsoft operaciones de seguridad usa varios [procesos](security-operations.md) junto con estas tecnologías.

En particular:

- [Seguridad de dispositivos:](#device-security) seguridad y protección en Escritorio administrado de Microsoft dispositivos
- [Administración de identidades y acceso:](#identity-and-access-management) administración del uso seguro de dispositivos mediante Azure Active Directory de identidades
- [Seguridad de red:](#network-security) información de VPN y Escritorio administrado de Microsoft y configuración recomendadas
- [Seguridad de la](#information-security) información: servicios disponibles opcionales para proteger aún más la información confidencial

Para obtener información sobre el almacenamiento de datos, el uso y las prácticas de seguridad usadas por Escritorio administrado de Microsoft, consulte nuestra whitepaper en [https://aka.ms/mmd-data](https://aka.ms/mmd-data) .


## <a name="device-security"></a>Seguridad de dispositivos

Escritorio administrado de Microsoft garantiza que todos los dispositivos administrados estén protegidos y protegidos y detecte amenazas lo antes posible mediante los siguientes servicios:

Servicio | Descripción
--- | ---
Antivirus | Microsoft Defender AV está instalado y configurado<br>Las definiciones de ANTIVIRUS de Microsoft Defender están actualizadas
Cifrado de volumen completo | Windows BitLocker es la solución de cifrado de volumen para Escritorio administrado de Microsoft dispositivos.<br><br>Una vez que una organización se incorpore al servicio, los dispositivos se cifrarán mediante Windows BitLocker con módulo de plataforma de confianza (TPM) integrado para evitar el acceso no autorizado a los datos locales cuando el dispositivo está en modo de suspensión o desactivado.
Supervisión | Microsoft Defender para endpoint se usa para la supervisión de amenazas de seguridad en todos Escritorio administrado de Microsoft dispositivos. Defender for Endpoint permite a los clientes empresariales detectar, investigar y responder a amenazas avanzadas en su red corporativa. Para obtener más información, consulte [Microsoft Defender for Endpoint.](/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
Actualizaciones del sistema operativo | Escritorio administrado de Microsoft dispositivos siempre están protegidos con las actualizaciones de seguridad más recientes.
Configuración de dispositivos seguros | Escritorio administrado de Microsoft implementa la línea base de seguridad de Microsoft. Para obtener más información, [vea Windows líneas base de seguridad.](/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Administración de identidad y acceso

La administración de identidades y acceso protege los activos corporativos y los datos críticos para la empresa. Escritorio administrado de Microsoft los dispositivos para garantizar un uso seguro con Azure Active Directory (Azure AD) identidades administradas. Es responsabilidad del cliente mantener información precisa en su inquilino de Azure AD.

Servicio | Descripción
--- | ---
Autenticación biométrica | Windows Hello permite a los usuarios iniciar sesión usando su rostro o un PIN, lo que dificulta que las contraseñas se olviden o roben. Los clientes son responsables de implementar los requisitos previos necesarios para su Active Directory local para el uso de este servicio en una configuración híbrida. Para obtener más información, [vea Windows Hello.](/windows-hardware/design/device-experiences/windows-hello) 
Permiso de usuario estándar | Para proteger el sistema y hacerlo más seguro, se le asignarán permisos de usuario estándar. Este permiso se asigna como parte de la Windows de autopiloto.



## <a name="network-security"></a>Seguridad de red

Los clientes son responsables de la seguridad de la red. 

Servicio | Descripción
--- | ---
VPN | Los clientes son propietarios de su infraestructura VPN, para garantizar que los recursos corporativos limitados se puedan exponer fuera de la intranet.<br><br>Requisito mínimo: Escritorio administrado de Microsoft requiere una Windows 10 de VPN compatible y compatible. Si su organización necesita una solución VPN, debe admitir Windows 10 y empaquetarse e implementarse a través de Intune. Póngase en contacto con el editor de software para obtener más información.<br><br>Recomendación:<br>- Microsoft recomienda una solución de VPN moderna que podría implementarse fácilmente a través de Intune para insertar perfiles de VPN. Este enfoque proporciona una forma continua, transparente, confiable y segura de acceder a la red corporativa. Para obtener más información, vea [[Configuración de VPN en Intune]](/intune/vpn-settings-configure).<br>- Los clientes vpn gruesos o los clientes VPN antiguos no son recomendados por Microsoft al usar Escritorio administrado de Microsoft, ya que puede afectar al entorno del usuario.<br>- Microsoft recomienda que el tráfico web saliente vaya directamente a Internet sin pasar por la VPN para evitar problemas de rendimiento.<br>- Lo ideal es que Microsoft recomiende el uso de Azure Active Directory proxy de aplicación en lugar de una VPN.


## <a name="information-security"></a>Seguridad de la información

Puede configurar estos servicios opcionales para ayudar a proteger los activos corporativos de alto valor. 

Servicio | Descripción
--- | ---
Recuperación de datos  | La información almacenada en las carpetas clave del dispositivo se hace una copia de seguridad de OneDrive para la Empresa. Escritorio administrado de Microsoft no es responsable de los datos que no están sincronizados con OneDrive para la Empresa.
Windows Information Protection | Para las empresas que requieren altos niveles de seguridad de la información, [recomendamos](/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) Windows Information Protection y [Azure Information Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection)
