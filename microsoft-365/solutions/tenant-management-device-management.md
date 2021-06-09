---
title: Paso 5. Administración de dispositivos y aplicaciones para Microsoft 365 para inquilinos empresariales
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Implemente la opción correcta para la administración de dispositivos y aplicaciones para Microsoft 365 inquilinos.
ms.openlocfilehash: 0351f6be3f191e1a131da5b0b665a205a0abda8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050999"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="0a07a-104">Paso 5.</span><span class="sxs-lookup"><span data-stu-id="0a07a-104">Step 5.</span></span> <span data-ttu-id="0a07a-105">Administración de dispositivos y aplicaciones para Microsoft 365 para inquilinos empresariales</span><span class="sxs-lookup"><span data-stu-id="0a07a-105">Device and app management for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="0a07a-106">Microsoft 365 para empresas incluye características para ayudar a administrar dispositivos y el uso de aplicaciones en esos dispositivos dentro de la organización con administración de dispositivos móviles (MDM) y administración de aplicaciones móviles (MAM).</span><span class="sxs-lookup"><span data-stu-id="0a07a-106">Microsoft 365 for enterprise includes features to help manage devices and the use of apps on those devices within your organization with mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="0a07a-107">Puedes administrar dispositivos iOS, Android, macOS y Windows para proteger el acceso a los recursos de la organización, incluidos los datos.</span><span class="sxs-lookup"><span data-stu-id="0a07a-107">You can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="0a07a-108">Por ejemplo, puede impedir que los correos electrónicos se envíen a personas de fuera de la organización o aislar los datos de la organización de datos personales en los dispositivos personales del trabajador.</span><span class="sxs-lookup"><span data-stu-id="0a07a-108">For example, you can prevent emails from being sent to people outside your organization or isolate organization data from personal data on your worker's personal devices.</span></span>

<span data-ttu-id="0a07a-109">Este es un ejemplo de validación y administración de los usuarios, sus dispositivos y el uso de aplicaciones de productividad locales y en la nube como Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0a07a-109">Here is an example of the validation and management of users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Validación y administración de usuarios, dispositivos y aplicaciones](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

<span data-ttu-id="0a07a-111">Para ayudarle a proteger y proteger los recursos de su organización, Microsoft 365 para empresas incluye características para ayudar a administrar dispositivos y su acceso a aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0a07a-111">To help you secure and protect your organization's resources, Microsoft 365 for enterprise includes features to help manage devices and their access to apps.</span></span> <span data-ttu-id="0a07a-112">Hay dos opciones para la administración de dispositivos:</span><span class="sxs-lookup"><span data-stu-id="0a07a-112">There are two options for device management:</span></span>

- <span data-ttu-id="0a07a-113">Microsoft Intune, que es una solución completa de administración de dispositivos y aplicaciones para empresas.</span><span class="sxs-lookup"><span data-stu-id="0a07a-113">Microsoft Intune, which is a comprehensive device and app management solution for enterprises.</span></span>
- <span data-ttu-id="0a07a-114">Movilidad y seguridad básicas, que es un subconjunto de servicios de Intune incluidos con todos los Microsoft 365 para administrar dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="0a07a-114">Basic Mobility and Security, which is a subset of Intune services included with all Microsoft 365 products for managing devices in your organization.</span></span> <span data-ttu-id="0a07a-115">Para obtener más información, vea [Capabilities of Basic Mobility and Security](../admin/basic-mobility-security/capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="0a07a-115">For more information, see [Capabilities of Basic Mobility and Security](../admin/basic-mobility-security/capabilities.md).</span></span>

<span data-ttu-id="0a07a-116">Si tiene Microsoft 365 E3 O E5, debe usar Intune.</span><span class="sxs-lookup"><span data-stu-id="0a07a-116">If you have Microsoft 365 E3 or E5, you should use Intune.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="0a07a-117">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="0a07a-117">Microsoft Intune</span></span>

<span data-ttu-id="0a07a-118">Usas [Microsoft Intune](/mem/intune/fundamentals/planning-guide) para administrar el acceso a tu organización con MDM o MAM.</span><span class="sxs-lookup"><span data-stu-id="0a07a-118">You use [Microsoft Intune](/mem/intune/fundamentals/planning-guide) to manage access to your organization using MDM or MAM.</span></span> <span data-ttu-id="0a07a-119">MDM es cuando los usuarios "inscriben" sus dispositivos en Intune.</span><span class="sxs-lookup"><span data-stu-id="0a07a-119">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="0a07a-120">Después de inscribir un dispositivo, es un dispositivo administrado y puede recibir las directivas, reglas y configuración de la organización.</span><span class="sxs-lookup"><span data-stu-id="0a07a-120">After a device is enrolled, it is a managed device and can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="0a07a-121">Por ejemplo, puedes instalar aplicaciones específicas, crear una directiva de contraseña, instalar una conexión VPN y mucho más.</span><span class="sxs-lookup"><span data-stu-id="0a07a-121">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="0a07a-122">Es posible que los usuarios con sus propios dispositivos personales no quieran inscribir sus dispositivos o que Intune y las directivas de su organización lo administren.</span><span class="sxs-lookup"><span data-stu-id="0a07a-122">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="0a07a-123">Pero aún necesita proteger los recursos y los datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="0a07a-123">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="0a07a-124">En este escenario, puedes proteger tus aplicaciones con MAM.</span><span class="sxs-lookup"><span data-stu-id="0a07a-124">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="0a07a-125">Por ejemplo, puedes usar una directiva MAM que requiere que un usuario escriba un PIN al acceder a SharePoint en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0a07a-125">For example, you can use an MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="0a07a-126">También determinarás cómo vas a administrar dispositivos personales y dispositivos propiedad de la organización.</span><span class="sxs-lookup"><span data-stu-id="0a07a-126">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="0a07a-127">Es posible que quieras tratar los dispositivos de forma diferente, según sus usos.</span><span class="sxs-lookup"><span data-stu-id="0a07a-127">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="0a07a-128">Configuraciones de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="0a07a-128">Identity and device access configurations</span></span>

<span data-ttu-id="0a07a-129">Microsoft proporciona un conjunto de configuraciones para el acceso a identidades y [dispositivos](../security/defender-365-security/microsoft-365-policies-configurations.md) para garantizar un personal seguro y productivo.</span><span class="sxs-lookup"><span data-stu-id="0a07a-129">Microsoft provides a set of configurations for [identity and device access](../security/defender-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="0a07a-130">Estas configuraciones incluyen el uso de:</span><span class="sxs-lookup"><span data-stu-id="0a07a-130">These configurations include the use of:</span></span>

- <span data-ttu-id="0a07a-131">Directivas de acceso condicional de Azure AD</span><span class="sxs-lookup"><span data-stu-id="0a07a-131">Azure AD Conditional Access policies</span></span>
- <span data-ttu-id="0a07a-132">Microsoft Intune de cumplimiento de dispositivos y protección de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0a07a-132">Microsoft Intune device compliance and app protection policies</span></span>
- <span data-ttu-id="0a07a-133">Directivas de riesgo de usuario de Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="0a07a-133">Azure AD Identity Protection user risk policies</span></span>
- <span data-ttu-id="0a07a-134">Directivas adicionales de aplicaciones en la nube</span><span class="sxs-lookup"><span data-stu-id="0a07a-134">Additional policies of cloud apps</span></span>

<span data-ttu-id="0a07a-135">Este es un ejemplo de la aplicación de estas directivas y configuraciones para validar y restringir a los usuarios, sus dispositivos y su uso de aplicaciones de productividad locales y en la nube, como Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0a07a-135">Here is an example of the application of these settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Configuraciones de acceso a identidades y dispositivos para requisitos y restricciones en los usuarios, sus dispositivos y el uso de aplicaciones](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

<span data-ttu-id="0a07a-137">Para el acceso a dispositivos y la administración de aplicaciones, usa las configuraciones de estos artículos:</span><span class="sxs-lookup"><span data-stu-id="0a07a-137">For device access and app management, use the configurations in these articles:</span></span>

- [<span data-ttu-id="0a07a-138">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0a07a-138">Prerequisites</span></span>](../security/defender-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="0a07a-139">Directivas comunes de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="0a07a-139">Common identity and device access policies</span></span>](../security/defender-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a><span data-ttu-id="0a07a-140">Resultados del paso 5</span><span class="sxs-lookup"><span data-stu-id="0a07a-140">Results of Step 5</span></span>

<span data-ttu-id="0a07a-141">Para la administración de dispositivos y aplicaciones para su inquilino de Microsoft 365, ha determinado la configuración y las directivas de Intune para validar y restringir los usuarios, sus dispositivos y su uso de aplicaciones de productividad locales y en la nube.</span><span class="sxs-lookup"><span data-stu-id="0a07a-141">For device and app management for your Microsoft 365 tenant, you have determined the Intune settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps.</span></span>

<span data-ttu-id="0a07a-142">Este es un ejemplo de un inquilino con la administración de dispositivos y aplicaciones de Intune con los nuevos elementos resaltados.</span><span class="sxs-lookup"><span data-stu-id="0a07a-142">Here is an example of a tenant with Intune device and app management with the new elements highlighted.</span></span>

![Ejemplo de inquilino con administración de dispositivos y aplicaciones de Intune](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

<span data-ttu-id="0a07a-144">En esta ilustración, el inquilino tiene:</span><span class="sxs-lookup"><span data-stu-id="0a07a-144">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="0a07a-145">Dispositivos propiedad de la organización inscritos en Intune.</span><span class="sxs-lookup"><span data-stu-id="0a07a-145">Organization-owned devices enrolled in Intune.</span></span>
- <span data-ttu-id="0a07a-146">Directivas de dispositivos y aplicaciones de Intune para dispositivos inscritos y personales.</span><span class="sxs-lookup"><span data-stu-id="0a07a-146">Intune device and app policies for enrolled and personal devices.</span></span>

## <a name="ongoing-maintenance-for-device-and-app-management"></a><span data-ttu-id="0a07a-147">Mantenimiento continuo para la administración de dispositivos y aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0a07a-147">Ongoing maintenance for device and app management</span></span>

<span data-ttu-id="0a07a-148">De forma continua, es posible que deba:</span><span class="sxs-lookup"><span data-stu-id="0a07a-148">On an ongoing basis, you might need to:</span></span> 

- <span data-ttu-id="0a07a-149">Administrar la inscripción de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0a07a-149">Manage device enrollment.</span></span>
- <span data-ttu-id="0a07a-150">Revise la configuración y las directivas para obtener más aplicaciones, dispositivos y requisitos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0a07a-150">Revise your settings and policies for additional apps, devices, and security requirements.</span></span>