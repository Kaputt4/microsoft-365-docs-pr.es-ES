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
# <a name="protect-user-and-device-access"></a><span data-ttu-id="d7a04-103">Proteger el acceso de usuario y dispositivo</span><span class="sxs-lookup"><span data-stu-id="d7a04-103">Protect user and device access</span></span>

<span data-ttu-id="d7a04-104">Proteger el acceso a los datos y servicios de Microsoft 365 es fundamental para protegerse contra ciberataques y protegerse contra la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="d7a04-104">Protecting access to your Microsoft 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="d7a04-105">Se pueden aplicar las mismas protecciones a otras aplicaciones SaaS de su entorno e incluso a aplicaciones locales publicadas con Azure Active Directory Application Proxy.</span><span class="sxs-lookup"><span data-stu-id="d7a04-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="d7a04-106">Paso 1: Revisar recomendaciones</span><span class="sxs-lookup"><span data-stu-id="d7a04-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="d7a04-107">Capacidades recomendadas para la protección de las identidades y los dispositivos que tienen acceso a Office 365, otros servicios de SaaS y aplicaciones locales publicadas con Proxy de la aplicación de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d7a04-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="d7a04-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Más idiomas](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="d7a04-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="d7a04-109">Paso 2: Proteger las cuentas de administrador y el acceso</span><span class="sxs-lookup"><span data-stu-id="d7a04-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="d7a04-110">Las cuentas administrativas que usa para administrar el entorno de Microsoft 365 incluyen privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="d7a04-110">The administrative accounts you use to administer your Microsoft 365 environment include elevated privileges.</span></span> <span data-ttu-id="d7a04-111">Estos son objetivos valiosos para hackers y ciberattackers.</span><span class="sxs-lookup"><span data-stu-id="d7a04-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="d7a04-112">Comience por usar cuentas de administrador solo para la administración.</span><span class="sxs-lookup"><span data-stu-id="d7a04-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="d7a04-113">Los administradores deben tener una cuenta de usuario independiente para uso normal y no administrativo y usar solo su cuenta administrativa cuando sea necesario para completar una tarea asociada a su función de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d7a04-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="d7a04-114">Proteja las cuentas de administrador con autenticación multifactor y acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="d7a04-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="d7a04-115">Para obtener más información, vea [Protección de cuentas de administrador.](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts)</span><span class="sxs-lookup"><span data-stu-id="d7a04-115">For more information, see [Protecting administrator accounts](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="d7a04-116">A continuación, configure la administración de acceso con privilegios en Office 365.</span><span class="sxs-lookup"><span data-stu-id="d7a04-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="d7a04-117">La administración de acceso con privilegios permite el control de acceso granular sobre las tareas de administración con privilegios en Office 365.</span><span class="sxs-lookup"><span data-stu-id="d7a04-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="d7a04-118">Puede ayudar a proteger su organización de infracciones que pueden usar cuentas de administrador con privilegios existentes con acceso permanente a datos confidenciales o acceso a opciones de configuración críticas.</span><span class="sxs-lookup"><span data-stu-id="d7a04-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="d7a04-119">Introducción a la administración de acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="d7a04-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="d7a04-120">Configurar la administración del acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="d7a04-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="d7a04-121">Otra recomendación principal es usar estaciones de trabajo configuradas específicamente para el trabajo administrativo.</span><span class="sxs-lookup"><span data-stu-id="d7a04-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="d7a04-122">Se trata de dispositivos dedicados que solo se usan para tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="d7a04-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="d7a04-123">Vea [Proteger el acceso con privilegios.](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)</span><span class="sxs-lookup"><span data-stu-id="d7a04-123">See [Securing privileged access](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="d7a04-124">Por último, puede mitigar el impacto de la falta involuntaria de acceso administrativo creando dos o más cuentas de acceso de emergencia en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="d7a04-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="d7a04-125">Vea [Administrar cuentas de acceso de emergencia en Azure AD.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)</span><span class="sxs-lookup"><span data-stu-id="d7a04-125">See [Manage emergency access accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="d7a04-126">Paso 3: Configurar directivas recomendadas de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="d7a04-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="d7a04-127">La autenticación multifactor (MFA) y las directivas de acceso condicional son herramientas eficaces para mitigar las cuentas comprometidas y el acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="d7a04-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="d7a04-128">Se recomienda implementar un conjunto de directivas que se hayan probado conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="d7a04-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="d7a04-129">Para obtener más información, incluidos los pasos de implementación, consulte [Configuración de identidad y acceso a dispositivos.](../security/office-365-security/microsoft-365-policies-configurations.md)</span><span class="sxs-lookup"><span data-stu-id="d7a04-129">For more information, including deployment steps, see [Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md).</span></span>

 <span data-ttu-id="d7a04-130">Estas directivas implementan las siguientes funcionalidades:</span><span class="sxs-lookup"><span data-stu-id="d7a04-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="d7a04-131">Autenticación Mult-factor</span><span class="sxs-lookup"><span data-stu-id="d7a04-131">Mult-factor authentication</span></span>
- <span data-ttu-id="d7a04-132">Acceso condicional</span><span class="sxs-lookup"><span data-stu-id="d7a04-132">Conditional access</span></span>
- <span data-ttu-id="d7a04-133">Protección de aplicaciones de Intune (protección de aplicaciones y datos para dispositivos)</span><span class="sxs-lookup"><span data-stu-id="d7a04-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="d7a04-134">Conformidad de dispositivos de Intune</span><span class="sxs-lookup"><span data-stu-id="d7a04-134">Intune device compliance</span></span>
- <span data-ttu-id="d7a04-135">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="d7a04-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="d7a04-136">La implementación del cumplimiento de dispositivos de Intune requiere la inscripción de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d7a04-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="d7a04-137">La administración de dispositivos le permite asegurarse de que son correctos y compatibles antes de permitirles acceder a los recursos de su entorno.</span><span class="sxs-lookup"><span data-stu-id="d7a04-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="d7a04-138">Consulta [Inscribir dispositivos para su administración en Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="d7a04-138">See [Enroll devices for management in Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="d7a04-139">Paso 4: Configurar directivas de acceso a dispositivos de SharePoint</span><span class="sxs-lookup"><span data-stu-id="d7a04-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="d7a04-140">Microsoft recomienda proteger el contenido de los sitios de SharePoint con contenido confidencial y altamente regulado con controles de acceso a dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d7a04-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="d7a04-141">Para obtener más información, vea [recomendaciones de directiva para proteger archivos y sitios de SharePoint.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d7a04-141">For more information, see [Policy recommendations for securing SharePoint sites and files](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>



    

