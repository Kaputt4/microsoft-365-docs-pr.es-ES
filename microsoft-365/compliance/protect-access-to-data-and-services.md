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
description: Aprende a proteger el acceso de usuarios y dispositivos a los datos y servicios de Microsoft 365 y a defenderte de la pérdida de datos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd8bbb62bc87ff59594e2fb2a3e21311c2452d9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925546"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="28ab3-103">Proteger el acceso de usuario y dispositivo</span><span class="sxs-lookup"><span data-stu-id="28ab3-103">Protect user and device access</span></span>

<span data-ttu-id="28ab3-104">Proteger el acceso a los datos y servicios de Microsoft 365 es fundamental para protegerse contra ataques cibernéticos y protegerse contra la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="28ab3-104">Protecting access to your Microsoft 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="28ab3-105">Las mismas protecciones se pueden aplicar a otras aplicaciones SaaS de su entorno e incluso a aplicaciones locales publicadas con proxy de aplicación de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="28ab3-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="28ab3-106">Paso 1: Revisar recomendaciones</span><span class="sxs-lookup"><span data-stu-id="28ab3-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="28ab3-107">Capacidades recomendadas para la protección de las identidades y los dispositivos que tienen acceso a Office 365, otros servicios de SaaS y aplicaciones locales publicadas con Proxy de la aplicación de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="28ab3-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="28ab3-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Más idiomas](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="28ab3-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="28ab3-109">Paso 2: Proteger cuentas de administrador y acceso</span><span class="sxs-lookup"><span data-stu-id="28ab3-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="28ab3-110">Las cuentas administrativas que usa para administrar el entorno de Microsoft 365 incluyen privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="28ab3-110">The administrative accounts you use to administer your Microsoft 365 environment include elevated privileges.</span></span> <span data-ttu-id="28ab3-111">Estos son objetivos valiosos para los hackers y ciberattackers.</span><span class="sxs-lookup"><span data-stu-id="28ab3-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="28ab3-112">Empiece por usar cuentas de administrador solo para la administración.</span><span class="sxs-lookup"><span data-stu-id="28ab3-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="28ab3-113">Los administradores deben tener una cuenta de usuario independiente para un uso normal y no administrativo y usar solo su cuenta administrativa cuando sea necesario para completar una tarea asociada a su función de trabajo.</span><span class="sxs-lookup"><span data-stu-id="28ab3-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="28ab3-114">Proteja las cuentas de administrador con autenticación multifactor y acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="28ab3-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="28ab3-115">Para obtener más información, vea [Protecting administrator accounts](../security/office-365-security/identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="28ab3-115">For more information, see [Protecting administrator accounts](../security/office-365-security/identity-access-prerequisites.md#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="28ab3-116">A continuación, configure la administración de acceso con privilegios en Office 365.</span><span class="sxs-lookup"><span data-stu-id="28ab3-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="28ab3-117">La administración de acceso con privilegios permite un control de acceso granular sobre las tareas de administración con privilegios en Office 365.</span><span class="sxs-lookup"><span data-stu-id="28ab3-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="28ab3-118">Puede ayudar a proteger su organización de infracciones que pueden usar cuentas de administrador con privilegios existentes con acceso permanente a datos confidenciales o acceso a opciones de configuración críticas.</span><span class="sxs-lookup"><span data-stu-id="28ab3-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="28ab3-119">Información general sobre la administración de acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="28ab3-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="28ab3-120">Configurar la administración del acceso con privilegios</span><span class="sxs-lookup"><span data-stu-id="28ab3-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="28ab3-121">Otra recomendación principal es usar estaciones de trabajo configuradas específicamente para el trabajo administrativo.</span><span class="sxs-lookup"><span data-stu-id="28ab3-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="28ab3-122">Se trata de dispositivos dedicados que solo se usan para tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="28ab3-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="28ab3-123">Consulte [Securing privileged access](/windows-server/identity/securing-privileged-access/securing-privileged-access).</span><span class="sxs-lookup"><span data-stu-id="28ab3-123">See [Securing privileged access](/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="28ab3-124">Por último, puede mitigar el impacto de la falta involuntaria de acceso administrativo mediante la creación de dos o más cuentas de acceso de emergencia en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="28ab3-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="28ab3-125">Consulta [Administrar cuentas de acceso de emergencia en Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="28ab3-125">See [Manage emergency access accounts in Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="28ab3-126">Paso 3: Configurar directivas recomendadas de acceso a dispositivos y identidades</span><span class="sxs-lookup"><span data-stu-id="28ab3-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="28ab3-127">La autenticación multifactor (MFA) y las directivas de acceso condicional son herramientas eficaces para mitigar las cuentas comprometidas y el acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="28ab3-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="28ab3-128">Se recomienda implementar un conjunto de directivas que se han probado conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="28ab3-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="28ab3-129">Para obtener más información, incluidos los pasos de implementación, consulte [Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="28ab3-129">For more information, including deployment steps, see [Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md).</span></span>

 <span data-ttu-id="28ab3-130">Estas directivas implementan las siguientes funcionalidades:</span><span class="sxs-lookup"><span data-stu-id="28ab3-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="28ab3-131">Autenticación Mult-factor</span><span class="sxs-lookup"><span data-stu-id="28ab3-131">Mult-factor authentication</span></span>
- <span data-ttu-id="28ab3-132">Acceso condicional</span><span class="sxs-lookup"><span data-stu-id="28ab3-132">Conditional access</span></span>
- <span data-ttu-id="28ab3-133">Protección de aplicaciones de Intune (protección de datos y aplicaciones para dispositivos)</span><span class="sxs-lookup"><span data-stu-id="28ab3-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="28ab3-134">Conformidad de dispositivos de Intune</span><span class="sxs-lookup"><span data-stu-id="28ab3-134">Intune device compliance</span></span>
- <span data-ttu-id="28ab3-135">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="28ab3-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="28ab3-136">La implementación del cumplimiento de dispositivos de Intune requiere la inscripción de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="28ab3-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="28ab3-137">La administración de dispositivos le permite asegurarse de que son correctos y compatibles antes de permitirles tener acceso a los recursos de su entorno.</span><span class="sxs-lookup"><span data-stu-id="28ab3-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="28ab3-138">Consulta [Inscribir dispositivos para la administración en Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="28ab3-138">See [Enroll devices for management in Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="28ab3-139">Paso 4: Configurar directivas de acceso a dispositivos de SharePoint</span><span class="sxs-lookup"><span data-stu-id="28ab3-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="28ab3-140">Microsoft recomienda proteger el contenido de los sitios de SharePoint con contenido confidencial y altamente regulado con controles de acceso a dispositivos.</span><span class="sxs-lookup"><span data-stu-id="28ab3-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="28ab3-141">Para obtener más información, vea [Policy recommendations for securing SharePoint sites and files](../security/office-365-security/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="28ab3-141">For more information, see [Policy recommendations for securing SharePoint sites and files](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>



