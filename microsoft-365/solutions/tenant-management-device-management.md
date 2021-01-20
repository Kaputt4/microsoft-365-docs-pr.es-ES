---
title: Paso 5. Administración de dispositivos y aplicaciones para los inquilinos de Microsoft 365 para empresas
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
ms.custom:
- Ent_Solutions
description: Implemente la opción correcta para la administración de dispositivos y aplicaciones para sus inquilinos de Microsoft 365.
ms.openlocfilehash: a581af3ec2ec192112656f1919e27f5b05a41cb1
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908712"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="b1e1f-104">Paso 5.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-104">Step 5.</span></span> <span data-ttu-id="b1e1f-105">Administración de dispositivos y aplicaciones para los inquilinos de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="b1e1f-105">Device and app management for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="b1e1f-106">Microsoft 365 para empresas incluye características para ayudar a administrar dispositivos y el uso de aplicaciones en esos dispositivos dentro de la organización con la administración de dispositivos móviles (MDM) y la administración de aplicaciones móviles (MAM).</span><span class="sxs-lookup"><span data-stu-id="b1e1f-106">Microsoft 365 for enterprise includes features to help manage devices and the use of apps on those devices within your organization with mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="b1e1f-107">Puedes administrar dispositivos iOS, Android, macOS y Windows para proteger el acceso a los recursos de la organización, incluidos los datos.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-107">You can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="b1e1f-108">Por ejemplo, puede evitar que se envíen correos electrónicos a personas ajenas a la organización o aislar los datos de la organización de datos personales en los dispositivos personales de su trabajador.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-108">For example, you can prevent emails from being sent to people outside your organization or isolate organization data from personal data on your worker's personal devices.</span></span>

<span data-ttu-id="b1e1f-109">Este es un ejemplo de la validación y administración de los usuarios, sus dispositivos y su uso de aplicaciones de productividad locales y en la nube, como Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-109">Here is an example of the validation and management of users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Validación y administración de usuarios, dispositivos y aplicaciones](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

<span data-ttu-id="b1e1f-111">Para ayudarle a proteger y proteger los recursos de su organización, Microsoft 365 para empresas incluye características para ayudar a administrar los dispositivos y su acceso a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-111">To help you secure and protect your organization's resources, Microsoft 365 for enterprise includes features to help manage devices and their access to apps.</span></span> <span data-ttu-id="b1e1f-112">Existen dos opciones para la administración de dispositivos:</span><span class="sxs-lookup"><span data-stu-id="b1e1f-112">There are two options for device management:</span></span>

- <span data-ttu-id="b1e1f-113">Microsoft Intune, que es una solución completa de administración de dispositivos y aplicaciones para empresas.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-113">Microsoft Intune, which is a comprehensive device and app management solution for enterprises.</span></span>
- <span data-ttu-id="b1e1f-114">Movilidad y seguridad básicas, que es un subconjunto de servicios de Intune incluidos con todos los productos de Microsoft 365 para administrar dispositivos en su organización.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-114">Basic Mobility and Security, which is a subset of Intune services included with all Microsoft 365 products for managing devices in your organization.</span></span> <span data-ttu-id="b1e1f-115">Para obtener más información, vea [Funcionalidades de movilidad y seguridad básicas.](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities)</span><span class="sxs-lookup"><span data-stu-id="b1e1f-115">For more information, see [Capabilities of Basic Mobility and Security](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities).</span></span>

<span data-ttu-id="b1e1f-116">Si tiene Microsoft 365 E3 o E5, debe usar Intune.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-116">If you have Microsoft 365 E3 or E5, you should use Intune.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="b1e1f-117">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b1e1f-117">Microsoft Intune</span></span>

<span data-ttu-id="b1e1f-118">Usas [Microsoft Intune para](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) administrar el acceso a tu organización mediante MDM o MAM.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-118">You use [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) to manage access to your organization using MDM or MAM.</span></span> <span data-ttu-id="b1e1f-119">MDM es cuando los usuarios "inscriben" sus dispositivos en Intune.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-119">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="b1e1f-120">Después de inscribir un dispositivo, es un dispositivo administrado y puede recibir las directivas, reglas y configuración de la organización.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-120">After a device is enrolled, it is a managed device and can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="b1e1f-121">Por ejemplo, puedes instalar aplicaciones específicas, crear una directiva de contraseña, instalar una conexión VPN y mucho más.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-121">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="b1e1f-122">Es posible que los usuarios con sus propios dispositivos personales no quieran inscribir sus dispositivos o que Intune y las directivas de la organización los administren.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-122">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="b1e1f-123">Pero aún necesita proteger los recursos y los datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-123">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="b1e1f-124">En este escenario, puedes proteger tus aplicaciones mediante MAM.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-124">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="b1e1f-125">Por ejemplo, puede usar una directiva MAM que requiera que un usuario escriba un PIN al acceder a SharePoint en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-125">For example, you can use an MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="b1e1f-126">También determinará cómo va a administrar los dispositivos personales y los dispositivos propiedad de la organización.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-126">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="b1e1f-127">Es posible que quieras tratar los dispositivos de forma diferente, en función de sus usos.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-127">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="b1e1f-128">Configuraciones de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="b1e1f-128">Identity and device access configurations</span></span>

<span data-ttu-id="b1e1f-129">Microsoft proporciona un conjunto de configuraciones para el acceso a dispositivos e [identidades](../security/office-365-security/microsoft-365-policies-configurations.md) para garantizar un personal seguro y productivo.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-129">Microsoft provides a set of configurations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="b1e1f-130">Estas configuraciones incluyen el uso de:</span><span class="sxs-lookup"><span data-stu-id="b1e1f-130">These configurations include the use of:</span></span>

- <span data-ttu-id="b1e1f-131">Directivas de acceso condicional de Azure AD</span><span class="sxs-lookup"><span data-stu-id="b1e1f-131">Azure AD Conditional Access policies</span></span>
- <span data-ttu-id="b1e1f-132">Directivas de cumplimiento de dispositivos y protección de aplicaciones de Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b1e1f-132">Microsoft Intune device compliance and app protection policies</span></span>
- <span data-ttu-id="b1e1f-133">Directivas de riesgo de usuario de Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="b1e1f-133">Azure AD Identity Protection user risk policies</span></span>
- <span data-ttu-id="b1e1f-134">Directivas adicionales de aplicaciones en la nube</span><span class="sxs-lookup"><span data-stu-id="b1e1f-134">Additional policies of cloud apps</span></span>

<span data-ttu-id="b1e1f-135">Este es un ejemplo de la aplicación de estas configuraciones y directivas para validar y restringir usuarios, sus dispositivos y el uso de aplicaciones de productividad locales y en la nube, como Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-135">Here is an example of the application of these settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Configuraciones de acceso a dispositivos e identidades para requisitos y restricciones en los usuarios, sus dispositivos y el uso de aplicaciones](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

<span data-ttu-id="b1e1f-137">Para el acceso a dispositivos y la administración de aplicaciones, usa las configuraciones de estos artículos:</span><span class="sxs-lookup"><span data-stu-id="b1e1f-137">For device access and app management, use the configurations in these articles:</span></span>

- [<span data-ttu-id="b1e1f-138">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b1e1f-138">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="b1e1f-139">Directivas comunes de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="b1e1f-139">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a><span data-ttu-id="b1e1f-140">Resultados del paso 5</span><span class="sxs-lookup"><span data-stu-id="b1e1f-140">Results of Step 5</span></span>

<span data-ttu-id="b1e1f-141">Para la administración de dispositivos y aplicaciones para su inquilino de Microsoft 365, ha determinado la configuración y las directivas de Intune para validar y restringir a los usuarios, sus dispositivos y el uso de aplicaciones de productividad locales y en la nube.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-141">For device and app management for your Microsoft 365 tenant, you have determined the Intune settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps.</span></span>

<span data-ttu-id="b1e1f-142">Este es un ejemplo de un inquilino con la administración de dispositivos y aplicaciones de Intune con los nuevos elementos resaltados.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-142">Here is an example of a tenant with Intune device and app management with the new elements highlighted.</span></span>

![Ejemplo de un inquilino con administración de dispositivos y aplicaciones de Intune](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

<span data-ttu-id="b1e1f-144">En esta ilustración, el inquilino tiene:</span><span class="sxs-lookup"><span data-stu-id="b1e1f-144">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="b1e1f-145">Dispositivos propiedad de la organización inscritos en Intune.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-145">Organization-owned devices enrolled in Intune.</span></span>
- <span data-ttu-id="b1e1f-146">Directivas de dispositivos y aplicaciones de Intune para dispositivos inscritos y personales.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-146">Intune device and app policies for enrolled and personal devices.</span></span>

## <a name="ongoing-maintenance-for-device-and-app-management"></a><span data-ttu-id="b1e1f-147">Mantenimiento continuo para la administración de dispositivos y aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b1e1f-147">Ongoing maintenance for device and app management</span></span>

<span data-ttu-id="b1e1f-148">De forma continua, es posible que deba:</span><span class="sxs-lookup"><span data-stu-id="b1e1f-148">On an ongoing basis, you might need to:</span></span> 

- <span data-ttu-id="b1e1f-149">Administrar la inscripción de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-149">Manage device enrollment.</span></span>
- <span data-ttu-id="b1e1f-150">Revise la configuración y las directivas para obtener más aplicaciones, dispositivos y requisitos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b1e1f-150">Revise your settings and policies for additional apps, devices, and security requirements.</span></span>
