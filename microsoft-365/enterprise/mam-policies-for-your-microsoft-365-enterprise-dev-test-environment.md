---
title: Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 para empresas
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía del laboratorio de pruebas para agregar directivas de cumplimiento de dispositivos de Intune a su entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367100"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e3ae3-103">Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="e3ae3-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e3ae3-104">*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="e3ae3-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="e3ae3-105">En este artículo se describe cómo agregar una directiva de cumplimiento de dispositivos de Intune para dispositivos Windows 10 y Microsoft 365 apps for Enterprise a su Microsoft 365 para el entorno de prueba Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e3ae3-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="e3ae3-106">La adición de una directiva de cumplimiento de dispositivos de Intune implica dos fases:</span><span class="sxs-lookup"><span data-stu-id="e3ae3-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="e3ae3-107">Fase 1: crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="e3ae3-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="e3ae3-108">Fase 2: crear una directiva de cumplimiento de dispositivos para dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="e3ae3-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="e3ae3-110">Para obtener un mapa visual de todos los artículos de la pila de la guía del entorno de pruebas de 365 para empresas, vaya a la [pila de la guía de entorno de pruebas 365 de Microsoft para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="e3ae3-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e3ae3-111">Fase 1: crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="e3ae3-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e3ae3-112">Si desea configurar directivas de MAM solo de una manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="e3ae3-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e3ae3-113">Si desea configurar directivas de MAM en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e3ae3-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3ae3-114">La prueba de la concesión de licencias automatizada y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="e3ae3-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="e3ae3-115">Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="e3ae3-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="e3ae3-116">Fase 2: crear una directiva de cumplimiento de dispositivos para dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="e3ae3-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="e3ae3-117">En esta fase, creará una directiva de cumplimiento de dispositivos para dispositivos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e3ae3-117">In this phase, you create a device compliance policy for Windows 10 devices.</span></span> <span data-ttu-id="e3ae3-118">En esta fase se usa Microsoft Intune y el [centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) para agregar un grupo y crear una directiva de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="e3ae3-118">This phase uses Microsoft Intune and the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) to add a group, and create a compliance policy.</span></span>

1. <span data-ttu-id="e3ae3-119">Vaya al [centro de administración de microsoft 365](https://admin.microsoft.com)y inicie sesión en su suscripción de laboratorio de pruebas de Microsoft 365 con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="e3ae3-119">Go to the [Microsoft 365 admin center](https://admin.microsoft.com), and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span> <span data-ttu-id="e3ae3-120">Seleccione el centro de administración de **Endpoint Manager** .</span><span class="sxs-lookup"><span data-stu-id="e3ae3-120">Select the **Endpoint Manager** admin center.</span></span> <span data-ttu-id="e3ae3-121">Se abre el [centro de administración de Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) .</span><span class="sxs-lookup"><span data-stu-id="e3ae3-121">The [Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) opens.</span></span>

    <span data-ttu-id="e3ae3-122">Si un mensaje es similar a **no ha habilitado la administración de dispositivos, pero** se muestra el mensaje, seleccione Intune como la entidad de MDM.</span><span class="sxs-lookup"><span data-stu-id="e3ae3-122">If a message similar to **You haven't enabled device management yet** message is shown, then select Intune as the MDM authority.</span></span> <span data-ttu-id="e3ae3-123">Para conocer los pasos específicos, consulte [establecer la entidad de administración de dispositivos móviles](/mem/intune/fundamentals/mdm-authority-set).</span><span class="sxs-lookup"><span data-stu-id="e3ae3-123">For the specific steps, see [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).</span></span>

    <span data-ttu-id="e3ae3-124">El centro de administración de Endpoint Manager se centra en la administración de dispositivos y la administración de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e3ae3-124">The Endpoint Manager admin center focuses on device management and app management.</span></span> <span data-ttu-id="e3ae3-125">Para obtener un paseo por este centro de administración, vea [Tutorial: tutorial Intune en Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span><span class="sxs-lookup"><span data-stu-id="e3ae3-125">For a tour of this admin center, see [Tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span>

2. <span data-ttu-id="e3ae3-126">En **grupos**, agregue un nuevo grupo de **seguridad** de **Microsoft 365** o con el nombre **usuarios de dispositivos de Windows 10 administrados**, con un tipo de pertenencia **asignado** .</span><span class="sxs-lookup"><span data-stu-id="e3ae3-126">In **Groups**, add a new **Microsoft 365** or **Security** group named **Managed Windows 10 device users**, with an **Assigned** membership type.</span></span> <span data-ttu-id="e3ae3-127">En los pasos siguientes, asignará la Directiva de cumplimiento a este grupo.</span><span class="sxs-lookup"><span data-stu-id="e3ae3-127">In the next steps, you'll assign your compliance policy to this group.</span></span> 

    <span data-ttu-id="e3ae3-128">Para conocer los pasos específicos y para obtener información sobre los grupos de **seguridad** de **Microsoft 365** o, consulte [Add groups to organizte Users and Devices](/mem/intune/fundamentals/groups-add).</span><span class="sxs-lookup"><span data-stu-id="e3ae3-128">For the specific steps, and for information on **Microsoft 365** or **Security** groups, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

3. <span data-ttu-id="e3ae3-129">En **dispositivos**, cree una directiva de cumplimiento de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e3ae3-129">In **Devices**, create a Windows 10 compliance policy.</span></span> <span data-ttu-id="e3ae3-130">Asigne esta directiva al grupo de **usuarios de dispositivos de Windows 10 administrado** que ha creado.</span><span class="sxs-lookup"><span data-stu-id="e3ae3-130">Assign this policy to the **Managed Windows 10 device users** group you created.</span></span>

    <span data-ttu-id="e3ae3-131">En la Directiva, puede bloquear contraseñas sencillas, requerir un firewall, requerir que el servicio antimalware de Microsoft defender se esté ejecutando y mucho más.</span><span class="sxs-lookup"><span data-stu-id="e3ae3-131">In your policy, you can block simple passwords, require a firewall, require the Microsoft Defender Antimalware service be running, and more.</span></span> <span data-ttu-id="e3ae3-132">Una directiva de cumplimiento normalmente incluye la configuración base o el mínimo que debe tener cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e3ae3-132">A compliance policy typically includes the base settings, or bare minimum that every device should have.</span></span>

    <span data-ttu-id="e3ae3-133">Para conocer los pasos específicos y obtener información sobre la configuración de cumplimiento disponible que puede configurar, consulte [usar directivas de cumplimiento para establecer las reglas para los dispositivos que administra](/mem/intune/protect/device-compliance-get-started).</span><span class="sxs-lookup"><span data-stu-id="e3ae3-133">For the specific steps, and for information on the available compliance settings you can configure, see [Use compliance policies to set rules for devices you manage](/mem/intune/protect/device-compliance-get-started).</span></span>

<span data-ttu-id="e3ae3-134">Al finalizar, tiene una directiva de cumplimiento de dispositivos para probar los miembros del grupo **administrado de usuarios de dispositivos de Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="e3ae3-134">When finished, you have a device compliance policy for testing members in the **Managed Windows 10 device users** group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="e3ae3-135">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="e3ae3-135">Next step</span></span>

<span data-ttu-id="e3ae3-136">Explore otras características y funciones de [Administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="e3ae3-136">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3ae3-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3ae3-137">See also</span></span>

<span data-ttu-id="e3ae3-138">[Microsoft 365 para las guías del laboratorio de pruebas de la empresa](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="e3ae3-138">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="e3ae3-139">Inscribir dispositivos iOS y Android en el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="e3ae3-139">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="e3ae3-140">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e3ae3-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e3ae3-141">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="e3ae3-141">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
