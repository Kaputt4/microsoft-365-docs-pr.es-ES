---
title: Inscriba iOS/iPados y dispositivos Android en el entorno de prueba de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Use esta guía del laboratorio de pruebas para inscribir dispositivos en el entorno de prueba de Microsoft 365 y administrarlos de forma remota.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367088"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="dc4c9-103">Inscribir dispositivos iOS y Android en el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="dc4c9-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="dc4c9-104">*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="dc4c9-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="dc4c9-105">En este artículo se describe cómo inscribir y probar capacidades básicas de administración de dispositivos móviles para iOS/iPados y dispositivos Android en el entorno de prueba de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-105">This article describes how to enroll and test basic mobile device management capabilities for iOS/iPadOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="dc4c9-106">La inscripción en iOS/iPados y dispositivos Android en el entorno de prueba implica tres fases:</span><span class="sxs-lookup"><span data-stu-id="dc4c9-106">Enrolling iOS/iPadOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="dc4c9-107">Fase 1: crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="dc4c9-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="dc4c9-108">Fase 2: inscribir a iOS/iPados y dispositivos Android</span><span class="sxs-lookup"><span data-stu-id="dc4c9-108">Phase 2: Enroll your iOS/iPadOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="dc4c9-109">Fase 3: administrar de forma remota sus dispositivos Android/iPad y iOS</span><span class="sxs-lookup"><span data-stu-id="dc4c9-109">Phase 3: Manage your iOS/iPadOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="dc4c9-111">Para obtener un mapa visual de todos los artículos de la pila de la guía del entorno de pruebas de 365 para empresas, vaya a la [pila de la guía de entorno de pruebas 365 de Microsoft para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="dc4c9-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="dc4c9-112">Fase 1: crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="dc4c9-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="dc4c9-113">Si desea inscribir iOS/iPados y dispositivos Android de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="dc4c9-113">If you want to enroll iOS/iPadOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="dc4c9-114">Si desea inscribir iOS/iPados y dispositivos Android en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="dc4c9-114">If you want to enroll iOS/iPadOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc4c9-115">La prueba de la concesión de licencias automatizada y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="dc4c9-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="dc4c9-116">Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y puede experimentar con ella en un entorno que represente una organización típica.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="dc4c9-117">Fase 2: inscribir los dispositivos Android y iOS</span><span class="sxs-lookup"><span data-stu-id="dc4c9-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="dc4c9-118">Si está pensando en una solución de administración de dispositivos móviles (MDM) para administrar los dispositivos, puede usar Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-118">If you're considering a mobile device management (MDM) solution to manage your devices, you can use Microsoft Intune.</span></span> <span data-ttu-id="dc4c9-119">Cuando se trabaja con un proveedor de MDM, que incluye Intune, los dispositivos se "inscriben".</span><span class="sxs-lookup"><span data-stu-id="dc4c9-119">When working with any MDM provider, including Intune, devices are "enrolled".</span></span> <span data-ttu-id="dc4c9-120">Cuando se inscriben, reciben las características y la configuración que configure.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-120">When enrolled, they receive the features and settings you configure.</span></span> 

<span data-ttu-id="dc4c9-121">En Intune, hay varias formas de inscribir sus dispositivos iOS/iPad y Android.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-121">In Intune, there are a few ways to enroll your iOS/iPadOS and Android devices.</span></span> <span data-ttu-id="dc4c9-122">Puede elegir la opción de inscripción que mejor se adapte a su organización.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-122">You can choose the enrollment option that works best for your organization.</span></span> <span data-ttu-id="dc4c9-123">Para obtener más información y orientación, vea los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="dc4c9-123">For more information and guidance, see the following articles:</span></span>

- [<span data-ttu-id="dc4c9-124">Guía de implementación: inscribir dispositivos iOS y iPados en Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="dc4c9-124">Deployment guide: Enroll iOS and iPadOS devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [<span data-ttu-id="dc4c9-125">Guía de implementación: inscribir dispositivos Android en Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="dc4c9-125">Deployment guide: Enroll Android devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-android)

<span data-ttu-id="dc4c9-126">Si está listo para usar Intune para la administración de dispositivos y desea tener alguna orientación, la siguiente información puede serle útil:</span><span class="sxs-lookup"><span data-stu-id="dc4c9-126">If you're ready to use Intune for device management, and want some guidance, then the following information may help:</span></span>

- [<span data-ttu-id="dc4c9-127">Introducción a la administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="dc4c9-127">Device management overview</span></span>](/mem/intune/fundamentals/what-is-device-management)
- [<span data-ttu-id="dc4c9-128">Tutorial: Guía de Intune en Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="dc4c9-128">Tutorial: Walkthrough Intune in Microsoft Endpoint Manager</span></span>](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [<span data-ttu-id="dc4c9-129">Guía de implementación: configuración o traslado a Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="dc4c9-129">Deployment guide: Setup or move to Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="dc4c9-130">Fase 3: administrar los dispositivos iOS y Android de forma remota</span><span class="sxs-lookup"><span data-stu-id="dc4c9-130">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="dc4c9-131">Microsoft Intune proporciona características de bloqueo remoto y restablecimiento de código de acceso.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-131">Microsoft Intune provides remote lock and passcode reset feature.</span></span> <span data-ttu-id="dc4c9-132">Si alguien pierde el dispositivo, puedes bloquear el dispositivo de forma remota.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-132">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="dc4c9-133">Si alguien olvida su código de acceso, puede restablecerlo de forma remota.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-133">If someone forgets their passcode, you can remotely reset it.</span></span>

- <span data-ttu-id="dc4c9-134">Para bloquear de forma remota un dispositivo iOS/iPado o Android, vea [bloquear dispositivos de forma remota con Intune](/mem/intune/remote-actions/device-remote-lock).</span><span class="sxs-lookup"><span data-stu-id="dc4c9-134">To remotely lock an iOS/iPadOS or Android device, see [Remotely lock devices with Intune](/mem/intune/remote-actions/device-remote-lock).</span></span>
- <span data-ttu-id="dc4c9-135">Para restablecer el código de acceso de forma remota, vea [restablecer o quitar el código de acceso del dispositivo en Intune](/mem/intune/remote-actions/device-passcode-reset).</span><span class="sxs-lookup"><span data-stu-id="dc4c9-135">To remotely reset the passcode, see [Reset or remove a device passcode in Intune](/mem/intune/remote-actions/device-passcode-reset).</span></span>

<span data-ttu-id="dc4c9-136">Para las tareas adicionales que puede ejecutar de forma remota, consulte [available Device Actions](/mem/intune/remote-actions/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="dc4c9-136">For additional tasks you can run remotely, see [available device actions](/mem/intune/remote-actions/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="dc4c9-137">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="dc4c9-137">Next step</span></span>

<span data-ttu-id="dc4c9-138">Explore otras características y funciones de [Administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="dc4c9-138">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc4c9-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc4c9-139">See Also</span></span>

[<span data-ttu-id="dc4c9-140">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="dc4c9-140">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="dc4c9-141">Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="dc4c9-141">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="dc4c9-142">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="dc4c9-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
