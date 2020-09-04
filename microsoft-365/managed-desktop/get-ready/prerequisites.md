---
title: Requisitos previos del Escritorio administrado de Microsoft
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 4850aabfac0774f899d6497543b74ff77c446523
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47361956"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Requisitos previos del Escritorio administrado de Microsoft

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

En este tema se describen los requisitos de infraestructura que debe cumplir para garantizar el éxito con Microsoft Managed Desktop. 

Microsoft FastTrack está disponible para ayudarle a cumplir con estos requisitos y a prepararse para participar en el escritorio administrado de Microsoft. Para obtener más información, consulte [Microsoft FastTrack](https://fasttrack.microsoft.com/about). 

Área | Detalles de requisitos previos
--- | ---
Licencias |Microsoft Managed Desktop requiere cualquiera de las siguientes licencias de Microsoft 365 (o equivalentes):<br>-Microsoft 365 E5<br>-Microsoft 365 E3 con el complemento de seguridad E5 de Microsoft 365<br><br>Para obtener más información sobre los planes de servicio específicos y su función en el escritorio administrado de Microsoft, vea [más información sobre las licencias](#more-about-licenses) en este tema.<br>Para obtener más información sobre las licencias disponibles, vea [licencias de Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Conectividad |  Todos los dispositivos de escritorio administrados por Microsoft requieren conectividad con numerosos puntos de conexión de servicios de Microsoft desde la red corporativa.<br><br>Para obtener la lista completa de direcciones URL e IP necesarias, consulte Configuración de la [red](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) debe ser el origen de la autoridad para todas las cuentas de usuario o se deben sincronizar las cuentas de usuario de Active Directory local con la última versión compatible de Azure AD Connect.<br><br>La [itinerancia del estado](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) de la empresa debe estar habilitada para los usuarios de escritorio administrado de Microsoft.<br><br>Para obtener más información, vea [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Para obtener más información sobre las versiones de Azure AD Connect admitidas, consulte [Azure ad Connect: version Release History](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Autenticación |    Si Azure AD no es el origen de la autenticación principal de las cuentas de usuario, debe configurar uno de estos en Azure AD Connect:<br>-Sincronización de hash de contraseña<br>: Autenticación de paso a través<br>-Un proveedor de identidades externo (incluidos los ADFS de Windows Server y distintos de Microsoft IDP) configurados para cumplir los requisitos de integración de Azure AD. Vea las [instrucciones](https://www.microsoft.com/download/details.aspx?id=56843) para obtener más información. <br><br>Al configurar las opciones de autenticación con Azure AD Connect, también se recomienda la escritura diferida de contraseñas. Para obtener más información, vea [escritura diferida de contraseñas](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Si se implementa un proveedor de identidades externo, debe validar la solución:<br>-Cumple los requisitos de integración de Azure AD<br>-Compatible con el acceso condicional de Azure AD, esto es para habilitar la configuración de la Directiva de cumplimiento de dispositivos de MMD<br>-Habilita la inscripción de dispositivos y el uso de los servicios de Microsoft 365 o las características necesarias como parte del escritorio administrado por Microsoft <br><br>Para obtener más información sobre las opciones de autenticación con Azure AD, consulte [Opciones de inicio de sesión de usuario de Azure ad Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Microsoft 365 | OneDrive para la empresa debe estar habilitado para los usuarios de escritorio administrados por Microsoft.<br><br>Aunque no es necesario inscribirse en el escritorio administrado de Microsoft, se recomienda encarecidamente que los siguientes servicios se migren a la nube:<br>-Email: migrar a buzones de correo basados en la nube, Exchange online o configurar con Exchange Online híbrido con Exchange 2013 o superior, local.<br>-Archivos y carpetas: migrar a OneDrive para la empresa o SharePoint Online.<br>-Herramientas de colaboración en línea: migrar a teams.
Administración de dispositivos | Los dispositivos de escritorio administrados por Microsoft requieren administración con Microsoft Intune. Intune se debe establecer como la entidad de administración de dispositivos móviles.<br><br>Para obtener más información, consulte [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Copia de seguridad y recuperación de datos | Microsoft Managed Desktop requiere que los archivos se sincronicen con OneDrive para la empresa para la protección. El escritorio administrado de Microsoft no garantiza los archivos que no se hayan sincronizado con OneDrive para la empresa, por lo que podrían perderse durante los intercambios de dispositivos o llamadas de soporte técnico que requieran un restablecimiento del dispositivo.<br><br>Aunque no es necesario, Microsoft Managed Desktop recomienda la migración de unidades de red asignadas a la solución de nube adecuada. Para obtener más información, vea [preparar unidades asignadas para el escritorio administrado por Microsoft](mapped-drives.md)

Cuando esté listo para empezar con el escritorio administrado de Microsoft, póngase en contacto con el administrador de cuentas de Microsoft. 

## <a name="more-about-licenses"></a>Más información sobre las licencias

Microsoft Managed Desktop requiere determinadas opciones de licencia para poder funcionar. Estas opciones están disponibles en varios paquetes de licencias, algunos de los cuales puede que ya sea propietario. En esta tabla se muestran las opciones necesarias disponibles en las que las licencias y el Resumen de su función en el escritorio administrado por Microsoft.

> [!TIP]
> Para asignar estas opciones de licencia a usuarios específicos, le recomendamos que aproveche la [característica de licencias basadas en grupos](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) de Azure Active Directory.



|Opción de licencia |Disponible en *cualquiera* de estos productos de licencia |Cómo lo usa Microsoft Managed Desktop|
|-------------|-------------|-------------|
|Azure Active Directory Premium P2     |-Microsoft 365 E5<br>-Complemento de seguridad Microsoft 365 E3 + Microsoft 365 *E5*<br>-Enterprise Mobility + Security E5<br>-Enterprise Mobility + Security E3<br>-Azure Active Directory Premium P2|  Proporciona acceso a los servicios en la nube de Microsoft; permite que AutoPilot registre dispositivos      |
|Microsoft Intune | -Microsoft 365 E5<br>-Complemento de seguridad Microsoft 365 E3 + Microsoft 365 *E5*<br>-Enterprise Mobility + Security E5<br>-Enterprise Mobility + Security E3<br>-Microsoft Intune  |  Necesario para registrar dispositivos, implementar actualizaciones y administrar dispositivos       |
|Windows 10 Enterprise  |-Microsoft 365 E5<br>-Complemento de seguridad Microsoft 365 E3 + Microsoft 365 *E5*<br>-Windows 10 Enterprise E3<br>-Windows 10 Enterprise E5 | Proporciona características empresariales de Windows 10       |
|Protección contra amenazas avanzada de Microsoft Defender | -Microsoft 365 E5<br>-Complemento de seguridad Microsoft 365 E3 + Microsoft 365 *E5*<br>-Windows 10 Enterprise E5<br>-Protección contra amenazas avanzada de Microsoft defender   |  Proporciona detección, supervisión, alertas y respuesta a amenazas  |
|Aplicaciones de Microsoft 365 para empresas  |-Microsoft 365 E5<br>-Microsoft 365 E3<br>-Office 365 E5<br>-Office 365 E3| Activa la oficina y las herramientas de colaboración y productividad    |

> [!TIP]
> El administrador de cuentas de Microsoft le ayudará a revisar sus licencias y planes de servicio actuales y a encontrar la ruta de acceso más eficiente para obtener cualquier licencia o plan de servicio adicional que necesite, mientras evita la duplicación.
