---
title: Seguridad en el escritorio administrado por Microsoft
description: ''
keywords: Servicio de escritorio administrado de Microsoft, Microsoft 365, documentación
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 928d01e7386bedc500e984b9c2a3240c6229bb43
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871784"
---
# <a name="security-in-microsoft-managed-desktop"></a>Seguridad en el escritorio administrado por Microsoft

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop se aplica un conjunto estándar de las directivas y utiliza diversas tecnologías de Microsoft para ayudar a los dispositivos de escritorio administrado de Microsoft seguros, datos de la compañía almacenados y mucho más. Las áreas que se enumeran a continuación se detallan aún más:  

- [Seguridad de los datos](#data-security) - tipos de datos recopilados por Microsoft Managed Desktop y donde se almacena con seguridad
- [Seguridad de dispositivos](#device-security) : seguridad y protección en dispositivos de escritorio administrado de Microsoft
- [Identity and Access Management](#identity-and-access-management) : administración de uso seguro de los dispositivos a través de servicios de identidad de Active Directory de Azure
- Solución y la configuración de [seguridad de red](#network-security) – información de VPN y administrado de escritorio de Microsoft recomendadas
- [Seguridad de la información](#information-security) – opcionales servicios disponibles para proteger la información confidencial 

## <a name="data-security"></a>Seguridad de datos

Los datos recopilados de los inquilinos de cliente (que permite que las operaciones y servicios de TI de escritorio administrado de Microsoft) se almacenan en las bases de datos de SQL Azure en el inquilino de Microsoft que se hospeda en los Estados Unidos de América.

Para obtener más información, vea [seguridad de Microsoft Azure](https://docs.microsoft.com/azure/security/azure-database-security-overview).

Enumerados a continuación son los tipos de datos que se transmiten desde el inquilino:

- Datos de actualización, el uso y la confiabilidad de dispositivo
- Datos de implementación y la confiabilidad de la aplicación
- Datos de implementación de directivas de seguridad y actualización
- Usuarios asignados a los dispositivos



## <a name="device-security"></a>Seguridad de dispositivos

Escritorio administrado de Microsoft garantiza que todos los dispositivos administrados se protegen y protegidos y detecta las amenazas tan pronto como sea posible con los siguientes servicios:

Servicio | Descripción
--- | ---
Antivirus | Windows Defender AV está instalado y configurado<br>Las definiciones de Windows Defender AV estén actualizadas
Cifrado de volumen completo |    BitLocker de Windows es la solución de cifrado de volumen para dispositivos de escritorio administrado de Microsoft.<br><br>Una vez que una organización se onboarded en el servicio, se cifrarán dispositivos con Windows BitLocker con confianza plataforma Module (TPM) integrado para evitar el acceso no autorizado a los datos locales cuando el dispositivo está en modo de suspensión, o desactivar. 
Supervisión |    Protección de amenaza avanzada de Windows Defender (Windows Defender ATP) se usa para la supervisión de amenazas de seguridad en todos los dispositivos de escritorio administrado de Microsoft. Windows Defender ATP permite a los clientes de empresa detectar, investigar y responder a las amenazas avanzadas en su red corporativa. Para obtener más información, vea [protección de amenaza avanzada de Windows Defender.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Actualizaciones de software |  Dispositivos de escritorio de Microsoft administrado siempre se protegen con las últimas actualizaciones de seguridad.
Configuración de dispositivo seguro |   Escritorio administrado de Microsoft implementa la línea de base de seguridad de Microsoft. Para obtener más información, vea [líneas base de seguridad de Windows.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Administración de identidad y acceso

Administración de identidades y acceso protege los activos corporativos y datos críticos para el negocio. Microsoft Managed Desktop configura dispositivos para garantizar un uso seguro con Azure Active Directory (AD Azure) administra las identidades. Es responsabilidad del cliente para conservar la información precisa en su inquilino de Azure AD. 

Servicio | Descripción
--- | ---
Autenticación biométrica |  Hola de Windows permite a los usuarios iniciar sesión utilizando su cara o un PIN, lo más difícil olvida o robar las contraseñas. Para obtener más información, vea [Windows Hola.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)
Autenticación multifactor | Autenticación multifactor Azure manera más estricta controla el acceso a funciones confidenciales del servicio de escritorio administrado de Microsoft, ya que proporciona un nivel adicional de la autenticación mediante un teléfono móvil, como el restablecimiento de contraseña así como self-service. 
Permisos de usuario estándar |  Para proteger el sistema y que sea más seguro, el usuario se asignará permisos de usuario estándar. Esto se asigna como parte de la experiencia de fábrica de piloto automático de Windows.



## <a name="network-security"></a>Seguridad de red

Los clientes son responsables de la seguridad de red. 

Servicio | Descripción
--- | ---
VPN | Los clientes poseen su infraestructura de VPN, para asegurarse de que se pueden exponer los recursos corporativos limitados fuera de la intranet.<br><br>El requisito mínimo: escritorio de Microsoft Managed requiere una solución VPN 10 de Windows compatible y compatible. Si su organización necesita una solución de VPN, necesita admitir Windows 10 y ser empaquetada y que se pueden implementar a través de Intune. Para obtener más información, póngase en contacto con su compañía de software.<br><br>Recomendación:<br>-Microsoft recomienda una solución VPN moderna que podría implementarse fácilmente a través de Intune a los perfiles VPN de inserción. Esto proporciona una manera siempre en, sin problemas, confiable y segura para tener acceso a la red corporativa. Para obtener más información, vea [[configuración de VPN en Intune]](https://docs.microsoft.com/intune/vpn-settings-configure).<br>-Los clientes VPN gruesas o los clientes heredados de VPN, no se recomiendan por Microsoft durante el uso de escritorio de Microsoft administrado tal y como puede influir en el entorno del usuario final.<br>-Microsoft recomienda que el tráfico web saliente irán directamente a Internet sin tener que pasar a través de la VPN para evitar los problemas de rendimiento.<br>-Ideal, Microsoft recomienda el uso de Azure Proxy de aplicación de Active Directory en lugar de una red privada virtual.


## <a name="information-security"></a>Seguridad de la información

Los clientes pueden configurar estos servicios opcionales para ayudar a proteger los activos corporativos de gran valor. 

Servicio | Descripción
--- | ---
Recuperación de datos  | Información almacenada en carpetas clave en el dispositivo se hace una copia a OneDrive para la empresa. Escritorio administrado de Microsoft no es responsable de los datos que no se sincronizan con OneDrive para la empresa. 
Windows Information Protection |    Para las empresas que requieren altos niveles de seguridad de la información, se recomienda la [Protección de la información de Windows](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) y [protección de la información de Azure.](https://www.microsoft.com/cloud-platform/azure-information-protection). 

