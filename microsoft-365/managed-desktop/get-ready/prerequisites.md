---
title: Requisitos previos del Escritorio administrado de Microsoft
description: Licencias, cuentas de Azure, configuración de autenticación y Microsoft 365 configuración para configurar antes de inscribirse en Microsoft Managed Desktop
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 8b2fc786ee8887c6050dd67721f8c8a23d54e2a3
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035179"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Requisitos previos del Escritorio administrado de Microsoft

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure). DO NOT DELETE.-->
<!--from Prerequisites -->

En este tema se describen los requisitos de infraestructura que debe cumplir para garantizar el éxito con Microsoft Managed Desktop.


Área | Detalles de requisitos previos
--- | ---
Licencias |Microsoft Managed Desktop requiere la Microsoft 365 E3 con Microsoft Defender para puntos de conexión (o equivalentes) asignados a los usuarios.<br>Para obtener más información sobre los planes de servicio [específicos,](#more-about-licenses) vea Más información sobre las licencias en este tema.<br>Para obtener más información sobre las licencias disponibles, [vea Microsoft 365 licensing](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans).
Conectividad | Todos los dispositivos de Escritorio administrado de Microsoft requieren conectividad a numerosos puntos de conexión de servicio de Microsoft desde la red corporativa.<br><br>Para obtener la lista completa de direcciones IP y direcciones URL necesarias, vea [Configuración de red](../get-ready/network.md). 
Azure Active Directory | Azure Active Directory (Azure AD) debe ser el origen de la autoridad para todas las cuentas de usuario, o bien las cuentas de usuario deben sincronizarse desde Active Directory local con la última versión compatible de Azure AD Conectar.<br><br>Para obtener más información, [vea Azure AD Conectar](/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Para obtener más información sobre las Azure AD Conectar compatibles, vea [Azure AD Conectar:Version release history](/azure/active-directory/hybrid/reference-connect-version-history).
Autenticación | Si Azure AD no es el origen de la autenticación principal para las cuentas de usuario, debe configurar una de estas en Azure AD Conectar:<br>- Sincronización de hash de contraseña<br>- Autenticación de paso a través<br>- Un proveedor de identidades externo (incluidos Windows ADFS de servidor y identificadores que no son de Microsoft) configurados para cumplir Azure AD de integración. Vea las [directrices](https://www.microsoft.com/download/details.aspx?id=56843) para obtener más información. <br><br>Al establecer opciones de autenticación con Azure AD Conectar, también se recomienda la reescribición de contraseña. Para obtener más información, vea [Password writeback](/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Si se implementa un proveedor de identidades externo, debe validar la solución:<br>- Cumple los Azure AD de integración<br>- Admite Azure AD condicional, que permite configurar la directiva de cumplimiento de dispositivos de Escritorio administrado de Microsoft<br>- Habilita la inscripción y el uso de dispositivos Microsoft 365 servicios o características necesarios como parte del escritorio administrado de Microsoft <br><br>Para obtener más información sobre las opciones de autenticación Azure AD, vea [Azure AD Conectar opciones de inicio de sesión del usuario.](/azure/active-directory/connect/active-directory-aadconnect-user-signin)
Microsoft 365 | OneDrive para la Empresa se debe habilitar para los usuarios de Escritorio administrado de Microsoft.<br><br>Aunque no es necesario inscribirse en Microsoft Managed Desktop, se recomienda encarecidamente migrar los siguientes servicios a la nube:<br>- Correo electrónico: migrar a buzones basados en la nube, Exchange en línea o configurar con Exchange Online Hybrid con Exchange 2013 o posterior, localmente.<br>- Archivos y carpetas: migrar a OneDrive para la Empresa o SharePoint Online.<br>- Herramientas de colaboración en línea: migrar a Teams.
Administración de dispositivos | Los dispositivos de Escritorio administrado de Microsoft requieren administración mediante Microsoft Intune. Intune debe establecerse como la entidad de administración de dispositivos móviles.<br><br>Para obtener más información, [vea Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).
Copia de seguridad y recuperación de datos | Microsoft Managed Desktop requiere que los archivos se sincronicen con OneDrive para la Empresa para la protección. Microsoft Managed Desktop no garantiza los archivos que no estén sincronizados con OneDrive para la Empresa que se pierdan durante los intercambios de dispositivos o las llamadas de soporte técnico que requieran un restablecimiento del dispositivo.<br><br>Aunque no es necesario, Microsoft Managed Desktop recomienda encarecidamente la migración desde unidades de red asignadas a la solución en la nube adecuada. Para obtener más información, vea [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md)

Cuando estés listo para empezar a usar Microsoft Managed Desktop, ponte en contacto con el Administrador de cuentas de Microsoft. 

## <a name="more-about-licenses"></a>Más información sobre las licencias

Microsoft Managed Desktop requiere determinadas opciones de licencia para funcionar. Consulte [Tecnologías de Escritorio administrado de Microsoft](../intro/technologies.md) para obtener información sobre cómo se usan estas licencias.

> [!TIP]
> Para asignar estas opciones de licencia a usuarios específicos, se recomienda aprovechar la característica de licencias basadas en grupos [de](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) Azure Active Directory.

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

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Pasos para prepararse para El escritorio administrado de Microsoft

1. Revisar los requisitos previos (en este artículo).
2. Ejecutar las [herramientas para evaluar la preparación](readiness-assessment-tool.md).
1. Comprar el [Portal de empresa](../get-started/company-portal.md).
1. Revisar los [requisitos previos para las cuentas de invitado](guest-accounts.md).
1. Comprobar la [configuración de red](network.md).
1. [Preparar los certificados y perfiles de red](certs-wifi-lan.md).
1. [Preparar el acceso de usuario a los datos](authentication.md).
1. [Preparar las aplicaciones](apps.md).
1. [Preparar las unidades asignadas](mapped-drives.md).
1. [Preparar los recursos de impresión](printing.md).
1. [Nombres del dispositivo](address-device-names.md) de dirección.