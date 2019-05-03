---
title: Requisitos previos para el escritorio administrado de Microsoft
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 11/1/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 19bd7c553840b0de51f7b26a8f1206a9c5d7b3af
ms.sourcegitcommit: b27650d1388ca136f85fcc662fe3ba069e9ee895
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/02/2019
ms.locfileid: "33560059"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Requisitos previos para el escritorio administrado de Microsoft

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

El éxito con el escritorio administrado de Microsoft comienza con requisitos bien conocidos, documentados y acordados para la infraestructura del cliente. En esta sección se describen los requisitos de Infastructure. 

Microsoft FastTrack está disponible para ayudar a los clientes a cumplir estos requisitos y ayudarle a prepararse para participar en el escritorio administrado de Microsoft. Para obtener más información, consulte [Microsoft FastTrack](https://fasttrack.microsoft.com/about). 

Área | Detalles de requisitos previos
--- | ---
Licencia |Microsoft Managed Desktop requiere las siguientes licencias de Microsoft 365 (o equivalentes):<br>-Microsoft 365 E5<br>-Microsoft 365 E3 + Security E5<br><br>Para obtener más información sobre las licencias disponibles, vea [licencias de Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Conectividad |  Todos los dispositivos de escritorio administrados por Microsoft requieren conectividad con numerosos puntos de conexión de servicios de Microsoft desde la red corporativa.<br><br>Para obtener la lista completa de direcciones URL e IP necesarias, consulte Configuración de la [red](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) debe ser el origen de la autoridad para todas las cuentas de usuario o se deben sincronizar las cuentas de usuario de Active Directory local con la última versión compatible de Azure AD Connect.<br><br>Para obtener más información sobre Azure AD Connect, consulte [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Para obtener más información sobre las versiones de Azure AD Connect admitidas, consulte [Azure ad Connect: version Release History](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Autenticación |    Si Azure AD no es el origen de la autoridad para las cuentas de usuario, debe configurar uno de estos en Azure AD Connect:<br>-Sincronización de hash de contraseña<br>: Autenticación de paso a través<br>-Federación con ADFS<br><br>Al configurar las opciones de autenticación con Azure AD Connect, también se requiere la escritura diferida de contraseñas. Para obtener más información, vea [escritura diferida](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)de contraseñas. <br><br>Para obtener más información sobre las opciones de autenticación con Azure AD, consulte [Opciones de inicio de sesión de usuario de Azure ad Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Office 365 |    Aunque no es necesario inscribirse en el escritorio administrado de Microsoft, es muy recomendable que los siguientes servicios se migren a la nube:<br>-Correo electrónico: migre a buzones de correo basados en la nube, Exchange Online, o configurarlo con Exchange Online híbrido con Exchange 2013 o superior, local.<br>-Archivos y carpetas: migre a OneDrive para la empresa/SharePoint Online.<br>-Herramientas de colaboración en línea: migre a teams.
Administración de dispositivos | Los dispositivos de escritorio administrados por Microsoft requieren administración con Microsoft Intune. Intune se debe establecer como la entidad de administración de dispositivos móviles.<br><br>Para obtener más información, consulte [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Copia de seguridad y recuperación de datos | Microsoft Managed Desktop requiere que los archivos se sincronicen con OneDrive para la empresa para la protección. El escritorio administrado de Microsoft no garantiza los archivos que no se hayan sincronizado con OneDrive para la empresa, por lo que se pueden perder durante los intercambios de dispositivos o admitir llamadas que requieran el restablecimiento de un dispositivo.<br><br>Aunque no es necesario, Microsoft Managed Desktop recomienda la migración de unidades de red asignadas a la solución de nube adecuada.  

Cuando esté listo para empezar con el escritorio administrado de Microsoft, póngase en contacto con el administrador de cuentas de Microsoft. 
