---
title: Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 Enterprise
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía del laboratorio de pruebas para agregar directivas de cumplimiento de dispositivos de Intune a su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 5ef39310ff74e5d5a38e8a5dd8c7ca24a126af58
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679031"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6e1d2-103">Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6e1d2-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6e1d2-104">*Esta guía del laboratorio de pruebas solo se puede usar para entornos de prueba de Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="6e1d2-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="6e1d2-105">Con las instrucciones de este artículo, agregará una directiva de cumplimiento de dispositivos de Intune para dispositivos Windows 10 y Microsoft 365 apps for Enterprise a su entorno de prueba empresarial 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-105">With the instructions in this article, you add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 Enterprise test environment.</span></span>

![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="6e1d2-107">Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6e1d2-108">Fase 1: Crear el entorno de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6e1d2-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6e1d2-109">Si solo quiere configurar directivas de MAM de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="6e1d2-109">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6e1d2-110">Si desea configurar directivas de MAM en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6e1d2-110">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6e1d2-111">La prueba de la concesión de licencias automatizada y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="6e1d2-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="6e1d2-112">Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="6e1d2-113">Fase 2: crear una directiva de cumplimiento de dispositivos para dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="6e1d2-113">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="6e1d2-114">En esta fase, creará una directiva de cumplimiento de dispositivos para dispositivos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-114">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="6e1d2-115">Vaya al portal de Office 365 en ( [https://portal.office.com](https://portal.office.com) ) e inicie sesión en su suscripción de laboratorio de pruebas de office 365 con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-115">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="6e1d2-116">En una pestaña nueva del explorador, abra Azure portal en [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="6e1d2-116">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="6e1d2-117">En la pestaña Azure portal del explorador, escriba **Intune** en el cuadro de búsqueda y, a continuación, haga clic en **Intune**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-117">From the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="6e1d2-118">Si ve un mensaje **que indica que no ha habilitado la administración de dispositivos todavía** en el panel de **Microsoft Intune** , haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-118">If you see a **You haven't enabled device management yet** message In the **Microsoft Intune** pane, click it.</span></span> <span data-ttu-id="6e1d2-119">En el panel **entidad de administración de dispositivos móviles** , haga clic en **Intune MDM**y, a continuación, haga clic en **elegir**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-119">In the **Mobile Device Management authority** pane, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="6e1d2-120">Actualice la pestaña del explorador.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-120">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="6e1d2-121">En el panel izquierdo de navegación, haga clic en **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-121">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="6e1d2-122">En el panel **grupos todos los grupos** , haga clic en **+ nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-122">In the **Groups-All groups** pane, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="6e1d2-123">En el panel **Grupo** , seleccione **Office 365** o **seguridad** para **tipo de grupo**, escriba **usuarios de dispositivos de Windows 10 administrados** en **nombre**, seleccione **asignado** en **tipo de pertenencia**y, a continuación, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-123">In the **Group** pane, select **Office 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="6e1d2-124">Haga clic en **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-124">Click **Microsoft Intune**.</span></span> <span data-ttu-id="6e1d2-125">En el panel de **Microsoft Intune** , en la lista **tareas rápidas** , haga clic en **crear una directiva de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-125">In the **Microsoft Intune** pane, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
9. <span data-ttu-id="6e1d2-126">En el panel **perfiles de directiva de cumplimiento** , haga clic en **crear Directiva**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-126">In the **Compliance Policy Profiles** pane, click **Create Policy**.</span></span>
    
10. <span data-ttu-id="6e1d2-127">En el panel **crear Directiva** , en **nombre**, escriba **Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-127">In the **Create Policy** pane, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="6e1d2-128">En **plataforma**, seleccione **Windows 10 y versiones posteriores**, haga clic en **Aceptar** en el panel **Directiva de cumplimiento de Windows 10** y, a continuación, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-128">In **Platform**, select **Windows 10 and later**, click **OK** In the **Windows 10 compliance policy** pane, and then click **Create**.</span></span> 
    
11. <span data-ttu-id="6e1d2-129">Haga clic en **perfiles de directiva de cumplimiento**y, a continuación, en el nombre de directiva de **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="6e1d2-129">Click **Compliance Policy Profiles**, and then click the **Windows 10** policy name.</span></span>
    
12. <span data-ttu-id="6e1d2-130">En el panel **Windows 10** , haga clic en **tareas**y, a continuación, haga clic en **seleccionar grupos para incluir**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-130">In the **Windows 10** pane, click **Assignments**, and then click **Select groups to include**.</span></span>
    
13. <span data-ttu-id="6e1d2-131">En el panel **seleccionar grupos para incluir** , haga clic en el grupo **usuarios de dispositivos de Windows 10 administrados** y, a continuación, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-131">In the **Select groups to include** pane, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
14. <span data-ttu-id="6e1d2-132">Haga clic en **Guardar**, haga clic en **Microsoft Intune-Overview**y, a continuación, haga clic en **aplicaciones cliente** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-132">Click **Save**, click **Microsoft Intune-Overview**, and then click **Client apps** in the left navigation.</span></span>
    
15. <span data-ttu-id="6e1d2-133">En el panel **aplicaciones cliente** , haga clic en **aplicaciones**y, a continuación, en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-133">In the **Client Apps** pane, click **Apps**, and then click **Add**.</span></span> 

16. <span data-ttu-id="6e1d2-134">En el panel **Agregar aplicación** , seleccione **tipo de aplicación**y, después, seleccione **Windows 10** en **Office 365 Suite**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-134">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

17. <span data-ttu-id="6e1d2-135">En el panel **Agregar aplicación** , seleccione **información del conjunto de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-135">In the **Add App** pane, select **App Suite Information**.</span></span>
 
18. <span data-ttu-id="6e1d2-136">En el panel de **información del conjunto de aplicaciones** , escriba **Microsoft 365 apps for Enterprise** en **el nombre del conjunto** y la descripción del **conjunto**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-136">In the **App Suite Information** pane, type **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**.</span></span>
<span data-ttu-id="6e1d2-137">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-137">Click OK.</span></span>

19. <span data-ttu-id="6e1d2-138">En el panel **Agregar aplicación** , seleccione **configurar conjunto de aplicaciones**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-138">In the **Add App** pane, select **Configure App Suite**, and then click **OK**.</span></span>

20. <span data-ttu-id="6e1d2-139">En el panel **Agregar aplicación** , seleccione **configuración del conjunto de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-139">In the **Add App** pane, select **App Suite Settings**.</span></span>

21. <span data-ttu-id="6e1d2-140">En **canal de actualización**, seleccione **empresa semianual**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-140">For **Update Channel**, select **Semi-Annual Enterprise**, and then click **OK**.</span></span>

22. <span data-ttu-id="6e1d2-141">En el panel **Agregar aplicación** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-141">In the **Add app** pane, click **Add**.</span></span>

<span data-ttu-id="6e1d2-142">Ahora tiene una directiva de cumplimiento de dispositivos para probar las aplicaciones seleccionadas en la Directiva de cumplimiento de dispositivos de **Windows 10** y para los miembros del grupo de **usuarios de dispositivos de Windows 10 administrados** .</span><span class="sxs-lookup"><span data-stu-id="6e1d2-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="6e1d2-143">Tenga en cuenta que, al seleccionar Office 365 como tipo de grupo, se crearán recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-143">Please note that selecting Office 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="6e1d2-144">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="6e1d2-144">Next step</span></span>

<span data-ttu-id="6e1d2-145">Explore otras características y funciones de [Administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="6e1d2-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e1d2-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e1d2-146">See also</span></span>

<span data-ttu-id="6e1d2-147">[Guías del laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="6e1d2-147">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="6e1d2-148">Inscribir dispositivos iOS y Android en su entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6e1d2-148">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="6e1d2-149">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6e1d2-149">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="6e1d2-150">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="6e1d2-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
