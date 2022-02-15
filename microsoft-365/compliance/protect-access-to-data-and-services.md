---
title: Proteger el acceso de usuario y dispositivo
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Aprende a proteger el acceso de usuarios y dispositivos a Microsoft 365 y servicios y a defenderte de la pérdida de datos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 121c5b8f1168e9986693fea128aa66626b3e31fe
ms.sourcegitcommit: 19e16b16f144159b55bb4c544403e3642b69e335
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2022
ms.locfileid: "62818545"
---
# <a name="protect-user-and-device-access"></a>Proteger el acceso de usuario y dispositivo

Proteger el acceso a sus Microsoft 365 y servicios es fundamental para defenderse de los ciberataques y protegerse contra la pérdida de datos. Las mismas protecciones se pueden aplicar a otras aplicaciones SaaS del entorno e incluso a las aplicaciones locales publicadas Azure Active Directory proxy de aplicación.
  
## <a name="step-1-review-recommendations"></a>Paso 1: Revisar recomendaciones

Capacidades recomendadas para la protección de las identidades y los dispositivos que tienen acceso a Office 365, otros servicios de SaaS y aplicaciones locales publicadas con Proxy de la aplicación de Azure AD.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Más idiomas](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>Paso 2: Proteger cuentas de administrador y acceso
Las cuentas administrativas que usa para administrar el entorno Microsoft 365 incluyen privilegios elevados. Estos son objetivos valiosos para los hackers y ciberattackers. 

Empiece por usar cuentas de administrador solo para la administración. Los administradores deben tener una cuenta de usuario independiente para un uso normal y no administrativo y usar solo su cuenta administrativa cuando sea necesario para completar una tarea asociada a su función de trabajo.

Proteja las cuentas de administrador con autenticación multifactor y acceso condicional. Para obtener más información, vea [Protecting administrator accounts](../security/office-365-security/identity-access-prerequisites.md#protecting-administrator-accounts). 

Después, configure la administración de acceso con privilegios en Office 365. La administración de acceso con privilegios permite un control de acceso granular sobre las tareas de administración con privilegios en Office 365. Puede ayudar a proteger su organización de infracciones que pueden usar cuentas de administrador con privilegios existentes con acceso permanente a datos confidenciales o acceso a opciones de configuración críticas.

- [Información general sobre la administración de acceso con privilegios](privileged-access-management-overview.md)
- [Configurar la administración del acceso con privilegios](privileged-access-management-configuration.md)

Otra recomendación principal es usar estaciones de trabajo especialmente configuradas para el trabajo administrativo. Se trata de dispositivos dedicados que solo se usan para tareas administrativas. Consulte [Proteger el acceso con privilegios](/windows-server/identity/securing-privileged-access/securing-privileged-access).

Por último, puede mitigar el impacto de la falta involuntaria de acceso administrativo mediante la creación de dos o más cuentas de acceso de emergencia en el inquilino. Consulte [Administrar cuentas de acceso de emergencia en Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access). 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>Paso 3: Configurar directivas recomendadas de acceso a dispositivos y identidades
La autenticación multifactor (MFA) y las directivas de acceso condicional son herramientas eficaces para mitigar las cuentas comprometidas y el acceso no autorizado. Se recomienda implementar un conjunto de directivas que se han probado conjuntamente. Para obtener más información, incluidos los pasos de implementación, consulte [Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md).

 Estas directivas implementan las siguientes funcionalidades:
- Autenticación multifactor
- Acceso condicional
- Protección de aplicaciones de Intune (protección de datos y aplicaciones para dispositivos)
- Conformidad de dispositivos de Intune
- Azure AD Identity Protection

La implementación del cumplimiento de dispositivos de Intune requiere la inscripción de dispositivos. La administración de dispositivos le permite asegurarse de que son correctos y compatibles antes de permitirles tener acceso a los recursos de su entorno. Consulta [Inscribir dispositivos para la administración en Intune](/mem/intune/user-help/enroll-windows-10-device)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>Paso 4: Configurar SharePoint de acceso a dispositivos

Microsoft recomienda proteger el contenido en sitios SharePoint con contenido confidencial y altamente regulado con controles de acceso a dispositivos. Para obtener más información, vea [Policy recommendations for securing SharePoint sites and files](../security/office-365-security/sharepoint-file-access-policies.md).



