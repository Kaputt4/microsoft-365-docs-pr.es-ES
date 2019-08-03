---
title: Requisitos previos para el escritorio administrado de Microsoft
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6351dd4696ed21b177dc2789b18c380fba4ebe91
ms.sourcegitcommit: 6b5370cded5d8259c9ed561eed324227f74c410b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/03/2019
ms.locfileid: "36171730"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Requisitos previos para el escritorio administrado de Microsoft

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

En este tema se describen los requisitos de infraestructura que debe cumplir para garantizar el éxito con Microsoft Managed Desktop. 

Microsoft FastTrack está disponible para ayudarle a cumplir con estos requisitos y a prepararse para participar en el escritorio administrado de Microsoft. Para obtener más información, consulte [Microsoft FastTrack](https://fasttrack.microsoft.com/about). 

Área | Detalles de requisitos previos
--- | ---
Licencias |Microsoft Managed Desktop requiere cualquiera de las siguientes licencias (o equivalencias) de Microsoft 365:<br>-Microsoft 365 E5<br>-Microsoft 365 E3 con el complemento de seguridad E5 de Microsoft 365<br><br>Para obtener más información sobre las licencias disponibles, vea [licencias de Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Conectividad |  Todos los dispositivos de escritorio administrados por Microsoft requieren conectividad con numerosos puntos de conexión de servicios de Microsoft desde la red corporativa.<br><br>Para obtener la lista completa de direcciones URL e IP necesarias, consulte Configuración de la [red](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) debe ser el origen de la autoridad para todas las cuentas de usuario o se deben sincronizar las cuentas de usuario de Active Directory local con la última versión compatible de Azure AD Connect.<br><br>La [itinerancia del estado](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) de la empresa debe estar habilitada para los usuarios de escritorio administrado de Microsoft.<br><br>Para obtener más información sobre Azure AD Connect, consulte [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Para obtener más información sobre las versiones de Azure AD Connect admitidas, consulte [Azure ad Connect: version Release History](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Autenticación |    Si Azure AD no es el origen de la autoridad para las cuentas de usuario, debe configurar uno de estos en Azure AD Connect:<br>-Sincronización de hash de contraseña<br>: Autenticación de paso a través<br>-Federación con ADFS<br><br>Al configurar las opciones de autenticación con Azure AD Connect, también se recomienda la escritura diferida de contraseñas. Para obtener más información, vea [escritura diferida](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)de contraseñas. <br><br>Para obtener más información sobre las opciones de autenticación con Azure AD, consulte [Opciones de inicio de sesión de usuario de Azure ad Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Office 365 |    OneDrive para la empresa debe estar habilitado para los usuarios de escritorio administrados por Microsoft.<br><br>Aunque no es necesario inscribirse en el escritorio administrado de Microsoft, se recomienda encarecidamente que los siguientes servicios se migren a la nube:<br>-Email: migrar a buzones de correo basados en la nube, Exchange online o configurar con Exchange Online híbrido con Exchange 2013 o superior, local.<br>-Archivos y carpetas: migrar a OneDrive para la empresa o SharePoint Online.<br>-Herramientas de colaboración en línea: migrar a teams.
Administración de dispositivos | Los dispositivos de escritorio administrados por Microsoft requieren administración con Microsoft Intune. Intune se debe establecer como la entidad de administración de dispositivos móviles.<br><br>Para obtener más información, consulte [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Copia de seguridad y recuperación de datos | Microsoft Managed Desktop requiere que los archivos se sincronicen con OneDrive para la empresa para la protección. El escritorio administrado de Microsoft no garantiza los archivos que no se hayan sincronizado con OneDrive para la empresa, por lo que podrían perderse durante los intercambios de dispositivos o llamadas de soporte técnico que requieran un restablecimiento del dispositivo.<br><br>Aunque no es necesario, Microsoft Managed Desktop recomienda la migración de unidades de red asignadas a la solución de nube adecuada. 

Cuando esté listo para empezar con el escritorio administrado de Microsoft, póngase en contacto con el administrador de cuentas de Microsoft. 
