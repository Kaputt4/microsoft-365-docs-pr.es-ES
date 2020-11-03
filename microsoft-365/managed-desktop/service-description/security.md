---
title: Tecnologías de seguridad en el escritorio administrado por Microsoft
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e69656e13cd9a300cd56bdd5db7703f2387d23d4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846209"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Tecnologías de seguridad en el escritorio administrado por Microsoft

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop usa varias tecnologías de Microsoft para ayudar a proteger los datos y los dispositivos administrados. Además, el centro de operaciones de seguridad de escritorio administrada de Microsoft usa una variedad de [procesos](security-operations.md) junto con estas tecnologías.

En particular: 

- [Seguridad](#device-security) de los dispositivos: seguridad y protección en dispositivos de escritorio administrados por Microsoft
- [Administración de acceso e identidades](#identity-and-access-management) : administración del uso seguro de dispositivos a través de Azure Active Directory Identity Services
- [Seguridad de red](#network-security) : información de VPN y configuración y solución recomendadas para escritorio administrado de Microsoft
- [Seguridad](#information-security) de la información: servicios opcionales disponibles para proteger aún más la información confidencial 

Para obtener información sobre el almacenamiento de datos, el uso y las prácticas de seguridad que usa el escritorio administrado por Microsoft, consulte nuestras notas del producto en [https://aka.ms/mmd-data](https://aka.ms/mmd-data) .


## <a name="device-security"></a>Seguridad del dispositivo

El escritorio administrado de Microsoft garantiza que todos los dispositivos administrados están protegidos y protegidos, y detecta las amenazas tan pronto como sea posible mediante los siguientes servicios:

Servicio | Descripción
--- | ---
Antivirus | Microsoft defender AV está instalado y configurado<br>Definiciones de antivirus de Microsoft defender actualizadas
Cifrado completo de volumen |    Windows BitLocker es la solución de cifrado de volumen para los dispositivos de escritorio administrados por Microsoft.<br><br>Una vez que una organización está incorporada en el servicio, los dispositivos se cifrarán con Windows BitLocker con el módulo de plataforma de confianza integrado (TPM) para evitar el acceso no autorizado a los datos locales cuando el dispositivo esté en modo de suspensión o desactivado. 
Supervisión |    Microsoft defender for Endpoint se usa para la supervisión de amenazas de seguridad en todos los dispositivos de escritorio administrados por Microsoft. Defender for Endpoint permite a los clientes de empresa detectar, investigar y responder a amenazas avanzadas en su red corporativa. Para obtener más información, vea [Microsoft defender para Endpoint.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Actualizaciones del sistema operativo |  Los dispositivos de escritorio administrados por Microsoft siempre están protegidos con las actualizaciones de seguridad más recientes.
Configuración de dispositivos seguros |   Microsoft Managed Desktop implementa la línea de base de seguridad de Microsoft. Para obtener más información, vea [líneas de base de seguridad de Windows.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Administración de identidad y acceso

La administración de identidades y acceso protege los activos corporativos y los datos críticos del negocio. Microsoft Managed Desktop configura dispositivos para garantizar un uso seguro con las identidades administradas de Azure Active Directory (Azure AD). Es responsabilidad del cliente mantener la información precisa en su espacio empresarial de Azure AD. 

Servicio | Descripción
--- | ---
Autenticación biométrica |  Windows Hello permite que los usuarios inicien sesión con su cara o un PIN, lo que dificulta la olvidar o robar las contraseñas. Los clientes son responsables de implementar los requisitos previos necesarios para su Active Directory local para el uso de este servicio en una configuración híbrida. Para obtener más información, consulta [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
Permiso de usuario estándar |  Para proteger el sistema y hacer que sea más seguro, se asignará al usuario permisos de usuario estándar. Se asigna como parte de la experiencia rápida de Windows AutoPilot.



## <a name="network-security"></a>Seguridad de red

Los clientes son responsables de la seguridad de la red. 

Servicio | Descripción
--- | ---
VPN | Los clientes poseen su infraestructura de VPN para garantizar que los recursos corporativos limitados puedan exponerse fuera de la intranet.<br><br>Requisito mínimo: el escritorio administrado de Microsoft requiere una solución VPN compatible con Windows 10. Si su organización necesita una solución de VPN, debe admitir Windows 10 y ser empaquetada e implementable a través de Intune. Póngase en contacto con el editor de software para obtener más información.<br><br>Norma<br>-Microsoft recomienda una solución de VPN moderna que puede implementarse fácilmente a través de Intune para insertar perfiles de VPN. Esto proporciona una forma de acceso a la red corporativa siempre activa, sin problemas, fiable y segura. Para obtener más información, consulte [[configuración de VPN en Intune]](https://docs.microsoft.com/intune/vpn-settings-configure).<br>-Microsoft no recomienda a los clientes VPN de gran grueso o a los clientes VPN heredados mientras usan Microsoft Managed Desktop ya que pueden afectar al entorno del usuario.<br>-Microsoft recomienda que el tráfico web saliente se envíe directamente a Internet sin tener que pasar por la VPN para evitar problemas de rendimiento.<br>-Idealmente, Microsoft recomienda usar el proxy de aplicación de Azure Active Directory en lugar de una VPN.


## <a name="information-security"></a>Seguridad de la información

Puede configurar estos servicios opcionales para ayudar a proteger los activos de gran valor corporativos. 

Servicio | Descripción
--- | ---
Recuperación de datos  | Se realiza una copia de seguridad de la información almacenada en las carpetas clave del dispositivo en OneDrive para la empresa. El escritorio administrado de Microsoft no es responsable de los datos que no se sincronizan con OneDrive para la empresa. 
Windows Information Protection |    Para las empresas que requieran altos niveles de seguridad de la información, recomendamos [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) y [Azure Information Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection) 

