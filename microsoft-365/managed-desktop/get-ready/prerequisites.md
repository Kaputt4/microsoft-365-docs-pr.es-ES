---
title: Requisitos previos del Escritorio administrado de Microsoft
description: Licencias, cuentas de Azure, configuración de autenticación y configuración de Microsoft 365 para configurar antes de inscribirse en Microsoft Managed Desktop
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: e4469d8abcfa8308c64e2efa7f7dc4f0156e5718
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957532"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Requisitos previos del Escritorio administrado de Microsoft

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

En este tema se describen los requisitos de infraestructura que debe cumplir para garantizar el éxito con Microsoft Managed Desktop. 


Área | Detalles de requisitos previos
--- | ---
Licencias |Microsoft Managed Desktop requiere la licencia de Microsoft 365 E3 con Microsoft Defender para puntos de conexión (o equivalentes) asignados a los usuarios.<br>Para obtener más información sobre los planes de servicio [específicos,](#more-about-licenses) vea Más información sobre las licencias en este tema.<br>Para obtener más información sobre las licencias disponibles, vea [Licencias de Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans).
Conectividad |  Todos los dispositivos de Escritorio administrado de Microsoft requieren conectividad a numerosos puntos de conexión de servicio de Microsoft desde la red corporativa.<br><br>Para obtener la lista completa de direcciones IP y direcciones URL necesarias, vea [Configuración de red](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) debe ser el origen de la autoridad de todas las cuentas de usuario o las cuentas de usuario deben sincronizarse desde Active Directory local con la versión compatible más reciente de Azure AD Connect.<br><br>[La itinerancia de estado](/azure/active-directory/devices/enterprise-state-roaming-overview) de empresa debe estar habilitada para los usuarios de Escritorio administrado de Microsoft.<br><br>Para obtener más información, [vea Azure AD Connect](/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Para obtener más información sobre las versiones compatibles de Azure AD Connect, consulte Historial de versiones de [Azure AD Connect:Version](/azure/active-directory/hybrid/reference-connect-version-history).
Autenticación |    Si Azure AD no es el origen de la autenticación principal para cuentas de usuario, debe configurar una de estas en Azure AD Connect:<br>- Sincronización de hash de contraseña<br>- Autenticación de paso a través<br>- Un proveedor de identidades externo (incluidos los ADFS de Windows Server y los IDP que no son de Microsoft) configurados para cumplir los requisitos de integración de Azure AD. Vea las [directrices](https://www.microsoft.com/download/details.aspx?id=56843) para obtener más información. <br><br>Al establecer opciones de autenticación con Azure AD Connect, también se recomienda la reescribición de contraseñas. Para obtener más información, vea [Password writeback](/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Si se implementa un proveedor de identidades externo, debe validar la solución:<br>- Cumple los requisitos de integración de Azure AD<br>- Admite el acceso condicional de Azure AD, que permite configurar la directiva de cumplimiento de dispositivos de Escritorio administrado de Microsoft<br>- Habilita la inscripción de dispositivos y el uso de los servicios o características de Microsoft 365 necesarios como parte del escritorio administrado de Microsoft <br><br>Para obtener más información sobre las opciones de autenticación con Azure AD, vea Opciones de inicio de sesión de usuario [de Azure AD Connect.](/azure/active-directory/connect/active-directory-aadconnect-user-signin)
Microsoft 365 | OneDrive para la Empresa debe estar habilitado para los usuarios de Escritorio administrado de Microsoft.<br><br>Aunque no es necesario inscribirse en Microsoft Managed Desktop, se recomienda encarecidamente migrar los siguientes servicios a la nube:<br>- Correo electrónico: migrar a buzones basados en la nube, Exchange Online o configurar con Exchange Online Hybrid con Exchange 2013 o posterior, localmente.<br>- Archivos y carpetas: migrar a OneDrive para la Empresa o SharePoint Online.<br>- Herramientas de colaboración en línea: migrar a Teams.
Administración de dispositivos | Los dispositivos de Escritorio administrado de Microsoft requieren administración con Microsoft Intune. Intune debe establecerse como la entidad de administración de dispositivos móviles.<br><br>Para obtener más información, vea [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Copia de seguridad y recuperación de datos |  Microsoft Managed Desktop requiere que los archivos se sincronicen con OneDrive para la Empresa para protegerse. Los archivos que no estén sincronizados con OneDrive para la Empresa no están garantizados por Microsoft Managed Desktop y pueden perderse durante los intercambios de dispositivos o las llamadas de soporte técnico que requieren un restablecimiento del dispositivo.<br><br>Aunque no es necesario, Microsoft Managed Desktop recomienda encarecidamente la migración desde unidades de red asignadas a la solución en la nube adecuada. Para obtener más información, vea [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md)

Cuando estés listo para empezar a usar Microsoft Managed Desktop, ponte en contacto con el Administrador de cuentas de Microsoft. 

## <a name="more-about-licenses"></a>Más información sobre las licencias

Microsoft Managed Desktop requiere determinadas opciones de licencia para funcionar. Consulte [Tecnologías de Escritorio administrado de Microsoft](../intro/technologies.md) para obtener información sobre cómo se usan estas licencias.

> [!TIP]
> Para asignar estas opciones de licencia a usuarios específicos, se recomienda aprovechar la característica de licencias basadas en [grupos](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) de Azure Active Directory.

- Azure Active Directory Premium P1
- Microsoft Intune 
- Windows 10 Enterprise  
- Microsoft Defender para punto de conexión
- Aplicaciones de Microsoft 365 para empresas
- Microsoft Teams
- [SharePoint Online plan 2](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online (plan 2)](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> El Administrador de cuentas de Microsoft le ayudará a revisar sus licencias y planes de servicio actuales y a encontrar la ruta de acceso más eficaz para obtener las licencias o planes de servicio adicionales que pueda necesitar, a la vez que evitará la duplicación.

## <a name="steps-to-get-ready"></a>Pasos para prepararse

1. Revisar [Requisitos previos de Microsoft Managed Desktop](prerequisites.md). (Este artículo)
2. Usar [herramientas de evaluación de preparación](readiness-assessment-tool.md).
3. [Requisitos previos para las cuentas de invitado](guest-accounts.md)
4. [Configuración de red para el Escritorio administrado de Microsoft](network.md)
5. [Preparar los certificados y los perfiles de red para el Escritorio administrado de Microsoft](certs-wifi-lan.md)
6. [Preparar el acceso a los recursos locales para el Escritorio administrado de Microsoft](authentication.md)
7. [Aplicaciones en el Escritorio administrado de Microsoft](apps.md)
8. [Preparar unidades asignadas para el Escritorio administrado de Microsoft](mapped-drives.md)
9. [Preparar recursos de impresión para el Escritorio administrado de Microsoft](printing.md)
