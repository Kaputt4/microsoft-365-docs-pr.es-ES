---
title: Inscriba sus dispositivos iOS y Android en su entorno de desarrollo y prueba de Microsoft Enterprise 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Use esta guía de laboratorio de prueba para inscribirse dispositivos en su entorno de prueba de Microsoft 365 y administrar de forma remota.
ms.openlocfilehash: a78db19099ccacd1b2f62e8438d1749f28d22f52
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871296"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="172a3-103">Inscriba sus dispositivos iOS y Android en su entorno de desarrollo y prueba de Microsoft Enterprise 365</span><span class="sxs-lookup"><span data-stu-id="172a3-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="172a3-104">Siguiendo las instrucciones proporcionadas en este artículo, podrá inscribirse y probar las capacidades de administración básica de dispositivo móvil para iOS y Android dispositivos en su entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="172a3-104">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="172a3-106">Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="172a3-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="172a3-107">Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="172a3-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="172a3-108">Si desea inscribirse iOS y Android dispositivos en una forma sencilla con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="172a3-108">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="172a3-109">Si desea inscribirse iOS y Android dispositivos en una empresa simulado, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="172a3-109">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="172a3-p101">Las pruebas automatizadas de licencias y pertenencia a grupos no requiere el entorno de prueba simulado enterprise, que incluye una intranet simulada conectada a Internet y sincronización de Active directory para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar licencias automatizada y la pertenencia a grupos y experimentar con él en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="172a3-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="172a3-112">Fase 2: Inscribirse los dispositivos Android y iOS</span><span class="sxs-lookup"><span data-stu-id="172a3-112">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="172a3-113">En primer lugar, use las instrucciones de [instalar e inicie sesión en la aplicación de Portal de empresa](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) para personalizar la aplicación de Portal de empresa de Microsoft Intune para su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="172a3-113">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="172a3-114">A continuación, siga las instrucciones de [Configurar el acceso a los recursos de empresa](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) para inscribirse en un dispositivo de iOS.</span><span class="sxs-lookup"><span data-stu-id="172a3-114">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="172a3-115">A continuación, siga las instrucciones de [inscripción su dispositivo Android en Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) para inscribirse en un dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="172a3-115">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="172a3-116">Fase 3: Administrar su iOS y Android dispositivos de forma remota</span><span class="sxs-lookup"><span data-stu-id="172a3-116">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="172a3-p102">Microsoft Intune proporciona capacidades de restablecimiento de bloqueo remoto y código de acceso. Si alguien pierde su dispositivo, puede bloquear el dispositivo de forma remota. Si alguien olvida su código de acceso, puede restablecer de forma remota.</span><span class="sxs-lookup"><span data-stu-id="172a3-p102">Microsoft Intune provides both remote lock and passcode reset capabilities. If someone loses their device, you can lock the device remotely. If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="172a3-120">Para bloquear una iOS o Android dispositivo de forma remota:</span><span class="sxs-lookup"><span data-stu-id="172a3-120">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="172a3-121">Inicie sesión en el portal de Azure en [https://portal.azure.com](https://portal.azure.com) con las credenciales de su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="172a3-121">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="172a3-122">Haga clic en **todos los servicios**, escriba **Intune**y, a continuación, haga clic en **Intune**.</span><span class="sxs-lookup"><span data-stu-id="172a3-122">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="172a3-123">Haga clic en **dispositivos > todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="172a3-123">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="172a3-124">En la lista de dispositivos, haga clic en un dispositivo Android o iOS y, a continuación, haga clic en la acción de **bloqueo remoto** .</span><span class="sxs-lookup"><span data-stu-id="172a3-124">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="172a3-125">Para restablecer el código de acceso de forma remota:</span><span class="sxs-lookup"><span data-stu-id="172a3-125">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="172a3-126">Si es necesario, inicie sesión en el portal de Azure en [https://portal.azure.com](https://portal.azure.com) con las credenciales de su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="172a3-126">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="172a3-127">Haga clic en **todos los servicios**, escriba **Intune**y, a continuación, haga clic en **Intune**.</span><span class="sxs-lookup"><span data-stu-id="172a3-127">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="172a3-128">Haga clic en **dispositivos > todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="172a3-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="172a3-p103">En la lista de los dispositivos de administrar, haga clic en un dispositivo Android o iOS y elija **... Más**. A continuación, elija la acción **quitar el código de acceso de** dispositivo remota.</span><span class="sxs-lookup"><span data-stu-id="172a3-p103">From the list of devices you manage, click an iOS or Android device, and choose **...More**. Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="172a3-131">Para realizar otras pruebas, consulte [acciones de dispositivo disponible](https://docs.microsoft.com/intune/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="172a3-131">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="172a3-132">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="172a3-132">Next step</span></span>

<span data-ttu-id="172a3-133">Explorar las características adicionales de [administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="172a3-133">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="172a3-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="172a3-134">See Also</span></span>

[<span data-ttu-id="172a3-135">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="172a3-135">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="172a3-136">Entorno de prueba de las directivas de cumplimiento de normas de dispositivo para su empresa de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="172a3-136">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="172a3-137">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="172a3-137">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="172a3-138">Movilidad de la empresa + seguridad (EMS)</span><span class="sxs-lookup"><span data-stu-id="172a3-138">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
