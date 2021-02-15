---
title: Requisitos previos del Escritorio administrado de Microsoft
description: Licencias, cuentas de Azure, configuración de autenticación y configuración de Microsoft 365 para configurar antes de inscribirse en el Escritorio administrado de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 79ae949d9624021121492edb811a4ea5bfcc729a
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659145"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Requisitos previos del Escritorio administrado de Microsoft

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

En este tema se describen los requisitos de infraestructura que debe cumplir para garantizar el éxito con el Escritorio administrado de Microsoft. 


Área | Detalles de requisitos previos
--- | ---
Licencias |Escritorio administrado de Microsoft requiere la licencia de Microsoft 365 E3 con Microsoft Defender para Endpoint y Azure Active Directory Premium 2 (o equivalentes).<br>Para obtener más información sobre los planes de servicio [específicos,](#more-about-licenses) consulte Más información sobre las licencias en este tema.<br>Para obtener más información sobre las licencias disponibles, consulte [Licencias de Microsoft 365.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)
Conectividad |  Todos los dispositivos de Escritorio administrado de Microsoft requieren conectividad a numerosos puntos de conexión de servicio de Microsoft desde la red corporativa.<br><br>Para obtener la lista completa de direcciones IP y direcciones URL necesarias, consulte [Configuración de red.](../get-ready/network.md) 
Azure Active Directory |    Azure Active Directory (Azure AD) debe ser el origen de autoridad para todas las cuentas de usuario o las cuentas de usuario deben sincronizarse desde Active Directory local con la última versión compatible de Azure AD Connect.<br><br>[Enterprise State Roaming](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) debe estar habilitado para los usuarios de Escritorio administrado de Microsoft.<br><br>Para obtener más información, [vea Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)<br><br>Para obtener más información sobre las versiones compatibles de Azure AD Connect, vea El historial [de versiones de Azure AD Connect:Version.](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)
Autenticación |    Si Azure AD no es el origen de la autenticación principal para las cuentas de usuario, debe configurar una de estas en Azure AD Connect:<br>- Sincronización de hash de contraseña<br>- Autenticación de paso a través<br>- Un proveedor de identidades externo (incluidos los ADFS de Windows Server y los IDP que no son de Microsoft) configurados para cumplir los requisitos de integración de Azure AD. Consulta las [directrices](https://www.microsoft.com/download/details.aspx?id=56843) para obtener más información. <br><br>Al establecer opciones de autenticación con Azure AD Connect, también se recomienda la reescribición de contraseñas. Para obtener más información, vea [Escritura reescribición de contraseña.](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback) <br><br>Si se implementa un proveedor de identidades externo, debe validar la solución:<br>- Cumple los requisitos de integración de Azure AD<br>- Admite el acceso condicional de Azure AD, que permite configurar la directiva de cumplimiento de dispositivos de Escritorio administrado de Microsoft<br>- Habilita la inscripción de dispositivos y el uso de servicios o características de Microsoft 365 necesarios como parte del Escritorio administrado de Microsoft <br><br>Para obtener más información sobre las opciones de autenticación con Azure AD, vea opciones de inicio de sesión de usuario [de Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)
Microsoft 365 | OneDrive para la Empresa debe estar habilitado para los usuarios de Escritorio administrado de Microsoft.<br><br>Aunque no es necesario inscribirse en el Escritorio administrado de Microsoft, recomendamos encarecidamente migrar los siguientes servicios a la nube:<br>- Correo electrónico: migrar a buzones basados en la nube, Exchange Online o configurar con Exchange Online Hybrid con Exchange 2013 o superior, localmente.<br>- Archivos y carpetas: migrar a OneDrive para la Empresa o SharePoint Online.<br>- Herramientas de colaboración en línea: migrar a Teams.
Administración de dispositivos | Los dispositivos de escritorio administrado de Microsoft requieren administración con Microsoft Intune. Intune debe establecerse como entidad de administración de dispositivos móviles.<br><br>Para obtener más información, vea [Microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune) 
Copia de seguridad y recuperación de datos |  Escritorio administrado de Microsoft requiere que los archivos se sincronicen con OneDrive para la Empresa para la protección. El Escritorio administrado de Microsoft no garantiza que los archivos no sincronizados con OneDrive para la Empresa se pierdan durante los intercambios de dispositivos o las llamadas de soporte técnico que requieran un restablecimiento del dispositivo.<br><br>Aunque no es necesario, El Escritorio administrado de Microsoft recomienda encarecidamente la migración de unidades de red asignadas a la solución en la nube adecuada. Para obtener más información, vea [Preparar unidades asignadas para escritorio administrado de Microsoft](mapped-drives.md)

Cuando esté listo para empezar a usar el Escritorio administrado de Microsoft, póngase en contacto con el Administrador de cuentas de Microsoft. 

## <a name="more-about-licenses"></a>Más información sobre las licencias

Escritorio administrado de Microsoft requiere determinadas opciones de licencia para funcionar. Vea [las tecnologías de Escritorio](../intro/technologies.md) administrado de Microsoft para obtener información sobre cómo se usan estas licencias.

> [!TIP]
> Para asignar estas opciones de licencia a usuarios específicos, le recomendamos que aproveche la característica de licencias basadas en grupos [de](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) Azure Active Directory.

- Azure Active Directory Premium P2
- Microsoft Intune 
- Windows 10 Enterprise  
- Microsoft Defender para punto de conexión
- Aplicaciones de Microsoft 365 para empresas
- Microsoft Teams
- [SharePoint Online plan 2](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online (plan 2)](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> El Administrador de cuentas de Microsoft le ayudará a revisar sus licencias y planes de servicio actuales y a encontrar la ruta más eficaz para obtener las licencias o planes de servicio adicionales que pueda necesitar, a la vez que evita la duplicación.
