---
title: Seguridad en el escritorio administrado por Microsoft
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 6d3be89b52d71543687a02a1fd3fbae8bc1543f8
ms.sourcegitcommit: 4460975970ae13e917d4d336e92dbd76ae26493b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243941"
---
# <a name="security-in-microsoft-managed-desktop"></a>Seguridad en el escritorio administrado por Microsoft

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop usa varias tecnologías de Microsoft para ayudar a proteger los datos y los dispositivos administrados. En particular: 

- [Seguridad de datos](#data-security) : tipos de datos recopilados por el escritorio administrado por Microsoft y donde se almacenan de forma segura
- [Seguridad](#device-security) de los dispositivos: seguridad y protección en dispositivos de escritorio administrados por Microsoft
- [Administración de acceso e identidades](#identity-and-access-management) : administración del uso seguro de dispositivos a través de Azure Active Directory Identity Services
- [Seguridad de red](#network-security) : información de VPN y configuración y solución recomendadas para escritorio administrado de Microsoft
- [Seguridad](#information-security) de la información: servicios opcionales disponibles para proteger aún más la información confidencial 

## <a name="data-security"></a>Seguridad de datos

Los datos recopilados de inquilinos de clientes (que habilitan las operaciones y servicios de TI de escritorio administrados de Microsoft) se almacenan en bases de datos de Azure SQL en el inquilino de Microsoft hospedado en Estados Unidos de América.

Para obtener más información, vea [seguridad de Microsoft Azure](https://docs.microsoft.com/azure/security/azure-database-security-overview).

A continuación se enumeran los tipos de datos que se transmiten desde su espacio empresarial:

- Datos de actualización de dispositivos, uso y confiabilidad
- Datos de confiabilidad y de implementación de aplicaciones
- Actualización y datos de implementación de la Directiva de seguridad
- Usuarios asignados a dispositivos
- Registros de seguridad de su espacio empresarial relacionados con las cuentas usadas por el escritorio administrado por Microsoft para administrar el servicio



## <a name="device-security"></a>Seguridad del dispositivo

El escritorio administrado de Microsoft garantiza que todos los dispositivos administrados están protegidos y protegidos, y detecta las amenazas tan pronto como sea posible mediante los siguientes servicios:

Servicio | Descripción
--- | ---
Antivirus | Microsoft defender AV está instalado y configurado<br>Definiciones de antivirus de Microsoft defender actualizadas
Cifrado completo de volumen |    Windows BitLocker es la solución de cifrado de volumen para los dispositivos de escritorio administrados por Microsoft.<br><br>Una vez que una organización está incorporada en el servicio, los dispositivos se cifrarán con Windows BitLocker con el módulo de plataforma de confianza integrado (TPM) para evitar el acceso no autorizado a los datos locales cuando el dispositivo esté en modo de suspensión o desactivado. 
Supervisión |    La protección contra amenazas avanzada de Microsoft defender (ATP de Microsoft defender) se usa para la supervisión de amenazas de seguridad en todos los dispositivos de escritorio administrados por Microsoft. ATP de Microsoft defender permite a los clientes empresariales detectar, investigar y responder a amenazas avanzadas en su red corporativa. Para obtener más información, consulte [protección contra amenazas avanzada de Microsoft defender.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Actualizaciones del sistema operativo |  Los dispositivos de escritorio administrados por Microsoft siempre están protegidos con las actualizaciones de seguridad más recientes.
Configuración de dispositivos seguros |   Microsoft Managed Desktop implementa la línea de base de seguridad de Microsoft. Para obtener más información, vea [líneas de base de seguridad de Windows.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Administración de identidad y acceso

La administración de identidades y acceso protege los activos corporativos y los datos críticos del negocio. Microsoft Managed Desktop configura dispositivos para garantizar un uso seguro con las identidades administradas de Azure Active Directory (Azure AD). Es responsabilidad del cliente mantener la información precisa en su espacio empresarial de Azure AD. 

Servicio | Descripción
--- | ---
Autenticación biométrica |  Windows Hello permite a los usuarios iniciar sesión con su cara o un PIN, lo que dificulta la olvidar o robar las contraseñas. Los clientes son responsables de implementar los requisitos previos necesarios para su Active Directory local para el uso de este servicio en una configuración híbrida. Para obtener más información, consulta [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
Permiso de usuario estándar |  Para proteger el sistema y hacer que sea más seguro, se asignará al usuario permisos de usuario estándar. Se asigna como parte de la experiencia rápida de Windows AutoPilot.



## <a name="network-security"></a>Seguridad de red

Los clientes son responsables de la seguridad de la red. 

Servicio | Descripción
--- | ---
VPN | Los clientes poseen su infraestructura de VPN para garantizar que los recursos corporativos limitados puedan exponerse fuera de la intranet.<br><br>Requisito mínimo: el escritorio administrado de Microsoft requiere una solución VPN compatible con Windows 10. Si su organización necesita una solución de VPN, debe admitir Windows 10 y ser empaquetada e implementable a través de Intune. Póngase en contacto con el editor de software para obtener más información.<br><br>Norma<br>-Microsoft recomienda una solución de VPN moderna que puede implementarse fácilmente a través de Intune para insertar perfiles de VPN. Esto proporciona una forma de acceso a la red corporativa siempre activa, sin problemas, fiable y segura. Para obtener más información, consulte [[configuración de VPN en Intune]](https://docs.microsoft.com/intune/vpn-settings-configure).<br>-Microsoft no recomienda a los clientes VPN de gran grueso o a los clientes VPN heredados que usen Microsoft Managed Desktop ya que puede influir en el entorno del usuario final.<br>-Microsoft recomienda que el tráfico web saliente se envíe directamente a Internet sin tener que pasar por la VPN para evitar problemas de rendimiento.<br>-Idealmente, Microsoft recomienda usar el proxy de aplicación de Azure Active Directory en lugar de una VPN.


## <a name="information-security"></a>Seguridad de la información

Los clientes pueden configurar estos servicios opcionales para ayudar a proteger los activos de gran valor corporativos. 

Servicio | Descripción
--- | ---
Recuperación de datos  | Se realiza una copia de seguridad de la información almacenada en las carpetas clave del dispositivo en OneDrive para la empresa. El escritorio administrado de Microsoft no es responsable de los datos que no se sincronizan con OneDrive para la empresa. 
Windows Information Protection |    Para las empresas que requieran altos niveles de seguridad de la información, recomendamos [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) y [Azure Information Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection) 

