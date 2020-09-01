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
ms.openlocfilehash: 1a1bdb449aa1d1ba12cf1de422b3e279df6c1376
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315746"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="475d2-104">Guía básica de administración de dispositivos para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="475d2-104">Device management roadmap for Microsoft 365</span></span>


<span data-ttu-id="475d2-105">Microsoft 365 para empresas incluye características que ayudan a administrar los dispositivos y sus aplicaciones dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="475d2-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="475d2-106">La administración de dispositivos móviles le ayuda a proteger y proteger los recursos de la organización.</span><span class="sxs-lookup"><span data-stu-id="475d2-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="475d2-107">Hay dos opciones para la administración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="475d2-107">There are two options for device management.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="475d2-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="475d2-108">Microsoft Intune</span></span>

<span data-ttu-id="475d2-109">Intune le ofrece opciones para administrar el acceso a su organización mediante el uso de la administración de dispositivos móviles (MDM) o la administración de aplicaciones móviles (MAM).</span><span class="sxs-lookup"><span data-stu-id="475d2-109">Intune gives you options to manage access to your organization using Mobile Device Management (MDM) or Mobile Application Management (MAM).</span></span> <span data-ttu-id="475d2-110">MDM es cuando los usuarios "inscriben" sus dispositivos en Intune.</span><span class="sxs-lookup"><span data-stu-id="475d2-110">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="475d2-111">Una vez inscritos, son dispositivos administrados y pueden recibir directivas, reglas y opciones de configuración usadas por la organización.</span><span class="sxs-lookup"><span data-stu-id="475d2-111">Once enrolled, they are managed devices, and can receive any policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="475d2-112">Por ejemplo, puede instalar aplicaciones específicas, crear una directiva de contraseñas, instalar una conexión VPN, etc.</span><span class="sxs-lookup"><span data-stu-id="475d2-112">For example, you can install specifics apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="475d2-113">Es posible que los usuarios con sus propios dispositivos personales no deseen inscribir sus dispositivos o ser administrados por Intune y sus directivas.</span><span class="sxs-lookup"><span data-stu-id="475d2-113">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your policies.</span></span> <span data-ttu-id="475d2-114">Sin embargo, debe proteger los recursos y los datos de la organización.</span><span class="sxs-lookup"><span data-stu-id="475d2-114">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="475d2-115">En este escenario, puede proteger sus aplicaciones con MAM.</span><span class="sxs-lookup"><span data-stu-id="475d2-115">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="475d2-116">Por ejemplo, puede usar una directiva de MAM que requiera que un usuario escriba un PIN cuando obtenga acceso a SharePoint en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="475d2-116">For example, you can use a MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="475d2-117">También determinará cómo va a administrar los dispositivos personales o de propiedad de la organización.</span><span class="sxs-lookup"><span data-stu-id="475d2-117">You'll also determine how you're going to manage personal or organization-owned devices.</span></span> <span data-ttu-id="475d2-118">Es posible que quiera tratar los dispositivos de forma diferente, en función de su uso.</span><span class="sxs-lookup"><span data-stu-id="475d2-118">You may want to treat devices differently, depending on their use.</span></span> 

<span data-ttu-id="475d2-119">Empiece [aquí](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span><span class="sxs-lookup"><span data-stu-id="475d2-119">Start [here](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="475d2-120">Movilidad y seguridad básica</span><span class="sxs-lookup"><span data-stu-id="475d2-120">Basic Mobility and Security</span></span>
 
<span data-ttu-id="475d2-121">Esto está integrado en Microsoft 365 y le ayuda a proteger y administrar los dispositivos móviles de los usuarios, como iPhone, iPad, Android y Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="475d2-121">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="475d2-122">Puede crear y administrar directivas de seguridad de dispositivo, borrar un dispositivo de forma remota y ver informes detallados del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="475d2-122">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span> 

<span data-ttu-id="475d2-123">Empiece [aquí](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span><span class="sxs-lookup"><span data-stu-id="475d2-123">Start [here](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span></span>
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="475d2-124">Recomendaciones de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="475d2-124">Identity and device access recommendations</span></span>

<span data-ttu-id="475d2-125">Microsoft proporciona un conjunto de recomendaciones para el [acceso a identidades y dispositivos](microsoft-365-policies-configurations.md) para asegurar la seguridad y la productividad de los empleados.</span><span class="sxs-lookup"><span data-stu-id="475d2-125">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="475d2-126">Para el acceso a los dispositivos, use las recomendaciones y la configuración de estos artículos:</span><span class="sxs-lookup"><span data-stu-id="475d2-126">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="475d2-127">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="475d2-127">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="475d2-128">Directivas comunes de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="475d2-128">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="475d2-129">Cómo contoso realizó la administración de dispositivos para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="475d2-129">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="475d2-130">Vea cómo contoso Corporation, una empresa multinacional ficticia pero representativa, [implementó la infraestructura de administración de dispositivos móviles con los](contoso-mdm.md) servicios en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="475d2-130">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed their mobile device management infrastructure](contoso-mdm.md) with Microsoft 365 cloud services.</span></span>
