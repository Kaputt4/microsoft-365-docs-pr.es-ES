---
title: Guía básica de administración de dispositivos para Microsoft 365
keywords: Microsoft 365, Microsoft 365 para empresas, documentación de Microsoft 365, administración de dispositivos móviles, Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: La guía básica para configurar la administración de dispositivos para Microsoft 365.
ms.openlocfilehash: 79be47d6bc83c124f2203866986e06181a1f7f3d
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749544"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="a962a-104">Guía básica de administración de dispositivos para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a962a-104">Device management roadmap for Microsoft 365</span></span>

<span data-ttu-id="a962a-105">Microsoft 365 para empresas incluye características que ayudan a administrar los dispositivos y sus aplicaciones dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="a962a-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="a962a-106">La administración de dispositivos móviles le ayuda a proteger y proteger los recursos de la organización.</span><span class="sxs-lookup"><span data-stu-id="a962a-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="a962a-107">Hay dos opciones para la administración de dispositivos:</span><span class="sxs-lookup"><span data-stu-id="a962a-107">There are two options for device management:</span></span>

- [<span data-ttu-id="a962a-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a962a-108">Microsoft Intune</span></span>](#microsoft-intune)
- [<span data-ttu-id="a962a-109">Movilidad y seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="a962a-109">Basic Mobility and Security</span></span>](#basic-mobility-and-security)

## <a name="microsoft-intune"></a><span data-ttu-id="a962a-110">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a962a-110">Microsoft Intune</span></span>

<span data-ttu-id="a962a-111">Puede usar Microsoft Intune para administrar el acceso a su organización mediante la administración de dispositivos móviles o la administración de aplicaciones móviles.</span><span class="sxs-lookup"><span data-stu-id="a962a-111">You can use Microsoft Intune to manage access to your organization using mobile device management or mobile application management.</span></span> <span data-ttu-id="a962a-112">La administración de dispositivos móviles es cuando los usuarios "inscriben" sus dispositivos en Intune.</span><span class="sxs-lookup"><span data-stu-id="a962a-112">Mobile device management is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="a962a-113">Una vez inscrito un dispositivo, se trata de un dispositivo administrado; por lo tanto, puede recibir las directivas, reglas y opciones de configuración de su organización.</span><span class="sxs-lookup"><span data-stu-id="a962a-113">After a device is enrolled, it is a managed device; therefore, it can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="a962a-114">Por ejemplo, puede instalar aplicaciones específicas, crear una directiva de contraseñas, instalar una conexión VPN, etc.</span><span class="sxs-lookup"><span data-stu-id="a962a-114">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="a962a-115">Es posible que los usuarios con sus propios dispositivos personales no deseen inscribir sus dispositivos o ser administrados por Intune y las directivas de su organización.</span><span class="sxs-lookup"><span data-stu-id="a962a-115">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="a962a-116">Sin embargo, debe proteger los recursos y los datos de la organización.</span><span class="sxs-lookup"><span data-stu-id="a962a-116">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="a962a-117">En este escenario, puede proteger sus aplicaciones con la administración de aplicaciones móviles.</span><span class="sxs-lookup"><span data-stu-id="a962a-117">In this scenario, you can protect your apps using mobile application management.</span></span> <span data-ttu-id="a962a-118">Por ejemplo, puede usar una directiva de administración de aplicaciones móviles que requiera que un usuario escriba un PIN al obtener acceso a SharePoint Online en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a962a-118">For example, you can use a mobile application management policy that requires a user to enter a PIN when accessing SharePoint Online on the device.</span></span>

<span data-ttu-id="a962a-119">También determinará cómo va a administrar los dispositivos personales y los dispositivos de propiedad de la organización.</span><span class="sxs-lookup"><span data-stu-id="a962a-119">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="a962a-120">Es posible que quiera tratar los dispositivos de forma diferente, en función de sus usos.</span><span class="sxs-lookup"><span data-stu-id="a962a-120">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="a962a-121">Movilidad y seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="a962a-121">Basic Mobility and Security</span></span>

<span data-ttu-id="a962a-122">Esto está integrado en Microsoft 365 y le ayuda a proteger y administrar los dispositivos móviles de los usuarios, como iPhone, iPad, Android y Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="a962a-122">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="a962a-123">Puede crear y administrar directivas de seguridad de dispositivo, borrar un dispositivo de forma remota y ver informes detallados del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a962a-123">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

## <a name="choose-between-the-two-options"></a><span data-ttu-id="a962a-124">Elegir entre las dos opciones</span><span class="sxs-lookup"><span data-stu-id="a962a-124">Choose between the two options</span></span>

<span data-ttu-id="a962a-125">Para ayudarle a evaluar mejor qué opción de administración de dispositivos es la mejor para usted, consulte [Choose between Basic Mobility Security and Intune](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune).</span><span class="sxs-lookup"><span data-stu-id="a962a-125">To help you better assess which device management option is best for you, see [Choose between Basic Mobility Security and Intune](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune).</span></span>

<span data-ttu-id="a962a-126">En función de la evaluación, empiece a administrar sus dispositivos con:</span><span class="sxs-lookup"><span data-stu-id="a962a-126">Based on your assessment, get started managing your devices with:</span></span>

- [<span data-ttu-id="a962a-127">Intune</span><span class="sxs-lookup"><span data-stu-id="a962a-127">Intune</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)
- [<span data-ttu-id="a962a-128">Movilidad y seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="a962a-128">Basic Mobility and Security</span></span>](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="a962a-129">Recomendaciones de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="a962a-129">Identity and device access recommendations</span></span>

<span data-ttu-id="a962a-130">Microsoft proporciona un conjunto de recomendaciones para el [acceso a identidades y dispositivos](../security/office-365-security/microsoft-365-policies-configurations.md) para asegurar la seguridad y la productividad de los empleados.</span><span class="sxs-lookup"><span data-stu-id="a962a-130">Microsoft provides a set of recommendations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="a962a-131">Para el acceso a los dispositivos, use las recomendaciones y la configuración de estos artículos:</span><span class="sxs-lookup"><span data-stu-id="a962a-131">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="a962a-132">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a962a-132">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="a962a-133">Directivas comunes de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="a962a-133">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="a962a-134">Cómo contoso realizó la administración de dispositivos para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a962a-134">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="a962a-135">Para obtener información sobre cómo una empresa multinacional ficticia pero representativa ha implementado la infraestructura de administración de dispositivos móviles con los servicios en la nube de Microsoft 365, vea [Mobile Device Management for contoso](contoso-mdm.md).</span><span class="sxs-lookup"><span data-stu-id="a962a-135">For information about how a fictional but representative multi-national business deployed their mobile device management infrastructure with Microsoft 365 cloud services, see [Mobile device management for Contoso](contoso-mdm.md).</span></span>
