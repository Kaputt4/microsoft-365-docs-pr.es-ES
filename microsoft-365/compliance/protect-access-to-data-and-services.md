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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Aprenda a proteger el acceso de usuarios y dispositivos a los datos y servicios de Microsoft 365 y a defenderse contra la pérdida de datos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64baa2c9e49a9b24841ec50db3e5592ba3d7d55d
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399029"
---
# <a name="protect-user-and-device-access"></a>Proteger el acceso de usuario y dispositivo

Proteger el acceso a los datos y servicios de Microsoft 365 es fundamental para protegerse contra ciberataques y protegerse contra la pérdida de datos. Se pueden aplicar las mismas protecciones a otras aplicaciones SaaS de su entorno e incluso a aplicaciones locales publicadas con Azure Active Directory Application Proxy.
  
## <a name="step-1-review-recommendations"></a>Paso 1: Revisar recomendaciones

Capacidades recomendadas para la protección de las identidades y los dispositivos que tienen acceso a Office 365, otros servicios de SaaS y aplicaciones locales publicadas con Proxy de la aplicación de Azure AD.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Más idiomas](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>Paso 2: Proteger las cuentas de administrador y el acceso
Las cuentas administrativas que usa para administrar el entorno de Microsoft 365 incluyen privilegios elevados. Estos son objetivos valiosos para hackers y ciberattackers. 

Comience por usar cuentas de administrador solo para la administración. Los administradores deben tener una cuenta de usuario independiente para uso normal y no administrativo y usar solo su cuenta administrativa cuando sea necesario para completar una tarea asociada a su función de trabajo.

Proteja las cuentas de administrador con autenticación multifactor y acceso condicional. Para obtener más información, vea [Protección de cuentas de administrador.](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts) 

A continuación, configure la administración de acceso con privilegios en Office 365. La administración de acceso con privilegios permite el control de acceso granular sobre las tareas de administración con privilegios en Office 365. Puede ayudar a proteger su organización de infracciones que pueden usar cuentas de administrador con privilegios existentes con acceso permanente a datos confidenciales o acceso a opciones de configuración críticas.

- [Introducción a la administración de acceso con privilegios](privileged-access-management-overview.md)
- [Configurar la administración del acceso con privilegios](privileged-access-management-configuration.md)

Otra recomendación principal es usar estaciones de trabajo configuradas específicamente para el trabajo administrativo. Se trata de dispositivos dedicados que solo se usan para tareas administrativas. Vea [Proteger el acceso con privilegios.](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)

Por último, puede mitigar el impacto de la falta involuntaria de acceso administrativo creando dos o más cuentas de acceso de emergencia en su espacio empresarial. Vea [Administrar cuentas de acceso de emergencia en Azure AD.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access) 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>Paso 3: Configurar directivas recomendadas de acceso a dispositivos e identidades
La autenticación multifactor (MFA) y las directivas de acceso condicional son herramientas eficaces para mitigar las cuentas comprometidas y el acceso no autorizado. Se recomienda implementar un conjunto de directivas que se hayan probado conjuntamente. Para obtener más información, incluidos los pasos de implementación, consulte [Configuración de identidad y acceso a dispositivos.](../security/office-365-security/microsoft-365-policies-configurations.md)

 Estas directivas implementan las siguientes funcionalidades:
- Autenticación Mult-factor
- Acceso condicional
- Protección de aplicaciones de Intune (protección de aplicaciones y datos para dispositivos)
- Conformidad de dispositivos de Intune
- Azure AD Identity Protection

La implementación del cumplimiento de dispositivos de Intune requiere la inscripción de dispositivos. La administración de dispositivos le permite asegurarse de que son correctos y compatibles antes de permitirles acceder a los recursos de su entorno. Consulta [Inscribir dispositivos para su administración en Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>Paso 4: Configurar directivas de acceso a dispositivos de SharePoint

Microsoft recomienda proteger el contenido de los sitios de SharePoint con contenido confidencial y altamente regulado con controles de acceso a dispositivos. Para obtener más información, vea [recomendaciones de directiva para proteger archivos y sitios de SharePoint.](../security/office-365-security/sharepoint-file-access-policies.md)



    

