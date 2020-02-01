---
title: Inscribir dispositivos iOS y Android en su entorno de prueba de Microsoft 365 Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Use esta guía del laboratorio de pruebas para inscribir dispositivos en el entorno de prueba de Microsoft 365 y administrarlos de forma remota.
ms.openlocfilehash: e2508e94cadb7f16f88991545756662292849158
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596997"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="85edb-103">Inscribir dispositivos iOS y Android en su entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="85edb-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="85edb-104">*Esta guía del laboratorio de pruebas solo se puede usar para entornos de prueba de Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="85edb-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="85edb-105">Si sigue las instrucciones que se proporcionan en este artículo, podrá inscribir y probar las funciones básicas de administración de dispositivos móviles para iOS y dispositivos Android en su entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="85edb-105">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Guías del laboratorio de pruebas para la nube de Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="85edb-107">Haga clic [aquí](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="85edb-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="85edb-108">Fase 1: Crear el entorno de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="85edb-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="85edb-109">Si solo quiere inscribir dispositivos iOS y Android de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="85edb-109">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="85edb-110">Si desea inscribir dispositivos iOS y Android en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="85edb-110">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="85edb-111">La prueba de la concesión de licencias automatizada y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="85edb-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="85edb-112">Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="85edb-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="85edb-113">Fase 2: inscribir los dispositivos Android y iOS</span><span class="sxs-lookup"><span data-stu-id="85edb-113">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="85edb-114">En primer lugar, siga las instrucciones de [instalar e iniciar sesión en la aplicación portal de empresa](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) para personalizar la aplicación del portal de empresa de Microsoft Intune para su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="85edb-114">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="85edb-115">A continuación, siga las instrucciones que se [definen en configurar el acceso a los recursos de la empresa](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) para inscribir un dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="85edb-115">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="85edb-116">A continuación, siga las instrucciones de [inscribir el dispositivo Android en Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) para inscribir un dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="85edb-116">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="85edb-117">Fase 3: administrar los dispositivos iOS y Android de forma remota</span><span class="sxs-lookup"><span data-stu-id="85edb-117">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="85edb-118">Microsoft Intune proporciona capacidades de restablecimiento de código de acceso y bloqueo remoto.</span><span class="sxs-lookup"><span data-stu-id="85edb-118">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="85edb-119">Si alguien pierde su dispositivo, puede bloquearlo de forma remota.</span><span class="sxs-lookup"><span data-stu-id="85edb-119">If someone loses their device, you can lock the device remotely.</span></span> <span data-ttu-id="85edb-120">Si alguien olvida su código de acceso, puede restablecerlo de forma remota.</span><span class="sxs-lookup"><span data-stu-id="85edb-120">If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="85edb-121">Para bloquear de forma remota un dispositivo iOS o Android:</span><span class="sxs-lookup"><span data-stu-id="85edb-121">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="85edb-122">Inicie sesión en el portal de Azure [https://portal.azure.com](https://portal.azure.com) en con las credenciales de su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="85edb-122">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="85edb-123">En la pestaña Azure portal del explorador, escriba **Intune** en el cuadro de búsqueda y, a continuación, haga clic en **Intune**.</span><span class="sxs-lookup"><span data-stu-id="85edb-123">On the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
3. <span data-ttu-id="85edb-124">Haga clic en **dispositivos > todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="85edb-124">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="85edb-125">En la lista de dispositivos, haga clic en un dispositivo iOS o Android y, a continuación, haga clic en la acción **bloqueo remoto** .</span><span class="sxs-lookup"><span data-stu-id="85edb-125">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="85edb-126">Para restablecer el código de acceso de forma remota:</span><span class="sxs-lookup"><span data-stu-id="85edb-126">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="85edb-127">Si es necesario, inicie sesión en el portal de [https://portal.azure.com](https://portal.azure.com) Azure en con las credenciales de su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="85edb-127">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="85edb-128">En la pestaña Azure portal del explorador, escriba **Intune** en el cuadro de búsqueda y, a continuación, haga clic en **Intune**.</span><span class="sxs-lookup"><span data-stu-id="85edb-128">On the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
3. <span data-ttu-id="85edb-129">Haga clic en **dispositivos > todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="85edb-129">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="85edb-130">En la lista de dispositivos que administra, haga clic en un dispositivo iOS o Android y elija **... Más**.</span><span class="sxs-lookup"><span data-stu-id="85edb-130">From the list of devices you manage, click an iOS or Android device, and choose **...More**.</span></span> <span data-ttu-id="85edb-131">A continuación, elija la acción quitar el dispositivo de **código** de acceso remoto.</span><span class="sxs-lookup"><span data-stu-id="85edb-131">Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="85edb-132">Para experimentación adicional, consulte [available Device Actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="85edb-132">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="85edb-133">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="85edb-133">Next step</span></span>

<span data-ttu-id="85edb-134">Explore otras características y funciones de [Administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="85edb-134">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="85edb-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="85edb-135">See Also</span></span>

[<span data-ttu-id="85edb-136">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="85edb-136">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="85edb-137">Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="85edb-137">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="85edb-138">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="85edb-138">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

