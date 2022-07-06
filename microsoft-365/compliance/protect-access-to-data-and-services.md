---
title: Proteger el acceso de usuario y dispositivo
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: landing-page
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Aprenda a proteger el acceso de usuarios y dispositivos a los datos y servicios de Microsoft 365 y a defenderse de la pérdida de datos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f8b6b266d037e8bbc185643e530bf7a2f6919038
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66623722"
---
# <a name="protect-user-and-device-access"></a>Proteger el acceso de usuario y dispositivo

La protección del acceso a los datos y servicios de Microsoft 365 es fundamental para defenderse frente a ciberataques y protegerse contra la pérdida de datos. Las mismas protecciones se pueden aplicar a otras aplicaciones SaaS del entorno e incluso a aplicaciones locales publicadas con Azure Active Directory Application Proxy.
  
## <a name="step-1-review-recommendations"></a>Paso 1: Revisar recomendaciones

Capacidades recomendadas para la protección de las identidades y los dispositivos que tienen acceso a Office 365, otros servicios de SaaS y aplicaciones locales publicadas con Proxy de la aplicación de Azure AD.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Más idiomas](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>Paso 2: Proteger las cuentas de administrador y el acceso

Las cuentas administrativas que usa para administrar el entorno de Microsoft 365 incluyen privilegios elevados. Estos son objetivos valiosos para los hackers y ciberattackers.

Empiece por usar cuentas de administrador solo para la administración. Los administradores deben tener una cuenta de usuario independiente para un uso normal y no administrativo y solo usar su cuenta administrativa cuando sea necesario para completar una tarea asociada a su función de trabajo.

Proteja las cuentas de administrador con autenticación multifactor y acceso condicional. Para obtener más información, consulte [Protección de cuentas de administrador](../security/office-365-security/identity-access-prerequisites.md#protecting-administrator-accounts). 

A continuación, configure Microsoft Purview Privileged Access Management. La administración de acceso con privilegios permite un control de acceso granular sobre las tareas de administración con privilegios en Office 365. Puede ayudar a proteger su organización frente a infracciones que pueden usar cuentas de administrador con privilegios existentes con acceso permanente a datos confidenciales o acceso a configuraciones críticas.

- [Introducción a la administración de acceso con privilegios](privileged-access-management.md)
- [Configurar la administración del acceso con privilegios](privileged-access-management-configuration.md)

Otra recomendación principal es usar estaciones de trabajo especialmente configuradas para el trabajo administrativo. Se trata de dispositivos dedicados que solo se usan para tareas administrativas. Consulte [Protección del acceso con privilegios](/windows-server/identity/securing-privileged-access/securing-privileged-access).

Por último, puede mitigar el impacto de la falta involuntaria de acceso administrativo mediante la creación de dos o más cuentas de acceso de emergencia en el inquilino. Consulte [Administración de cuentas de acceso de emergencia en Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access). 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>Paso 3: Configuración de directivas de acceso a dispositivos e identidades recomendadas

La autenticación multifactor (MFA) y las directivas de acceso condicional son herramientas eficaces para mitigar las cuentas en peligro y el acceso no autorizado. Se recomienda implementar un conjunto de directivas que se han probado conjuntamente. Para obtener más información, incluidos los pasos de implementación, consulte [Configuraciones de acceso a dispositivos y identidades](../security/office-365-security/microsoft-365-policies-configurations.md).

 Estas directivas implementan las siguientes funcionalidades:

- Autenticación multifactor
- Acceso condicional
- Intune protección de aplicaciones (protección de aplicaciones y datos para dispositivos)
- Conformidad de dispositivos de Intune
- Azure AD Identity Protection

La implementación de Intune cumplimiento de dispositivos requiere la inscripción de dispositivos. La administración de dispositivos le permite asegurarse de que son correctos y compatibles antes de permitirles acceder a los recursos de su entorno. Consulte [Inscripción de dispositivos para la administración en Intune](/mem/intune/user-help/enroll-windows-10-device)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>Paso 4: Configurar directivas de acceso a dispositivos de SharePoint

Microsoft recomienda proteger el contenido de sitios de SharePoint con contenido confidencial y altamente regulado con controles de acceso a dispositivos. Para obtener más información, vea [Recomendaciones de directivas para proteger archivos y sitios de SharePoint](../security/office-365-security/sharepoint-file-access-policies.md).
