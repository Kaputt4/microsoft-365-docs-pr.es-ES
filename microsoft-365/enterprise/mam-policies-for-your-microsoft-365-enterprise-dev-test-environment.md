---
title: Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía del laboratorio de pruebas para agregar directivas de cumplimiento de dispositivos de Intune a su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: eb140844eba4bc5cf5eba7fe452345f251ced0ff
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072120"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c45be-103">Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c45be-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c45be-104">Con las instrucciones de este artículo, agregará una directiva de cumplimiento de dispositivos de Intune a su entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c45be-104">With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.</span></span>

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="c45be-106">Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c45be-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c45be-107">Fase 1: crear el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c45be-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c45be-108">Si solo quiere configurar directivas de MAM de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="c45be-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="c45be-109">Si desea configurar directivas de MAM en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="c45be-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c45be-110">La prueba de la concesión de licencias automatizada y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="c45be-110">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="c45be-111">Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="c45be-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="c45be-112">Fase 2: crear una directiva de cumplimiento de dispositivos para dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="c45be-112">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="c45be-113">En esta fase, creará una directiva de cumplimiento de dispositivos para dispositivos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c45be-113">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="c45be-114">Vaya al portal de Office 365 en ([https://portal.office.com](https://portal.office.com)) e inicie sesión en su suscripción de laboratorio de pruebas de Office 365 con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="c45be-114">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="c45be-115">En una pestaña nueva del explorador, abra Azure portal en [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="c45be-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="c45be-116">En la pestaña Azure portal del explorador, en el panel de navegación, haga clic en **todos los servicios**, escriba Intune y, a continuación, haga clic en \*\*\*\* Intune. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c45be-116">On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="c45be-117">Si ve un mensaje **que indica que no ha habilitado la administración de dispositivos todavía** en la hoja de **Microsoft Intune** , haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="c45be-117">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it.</span></span> <span data-ttu-id="c45be-118">En la hoja **entidad de administración de dispositivos móviles** , haga clic en Intune **MDM**y, a continuación, haga clic en **elegir**.</span><span class="sxs-lookup"><span data-stu-id="c45be-118">On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="c45be-119">Actualice la pestaña del explorador.</span><span class="sxs-lookup"><span data-stu-id="c45be-119">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="c45be-120">En el panel izquierdo de navegación, haga clic en **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="c45be-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="c45be-121">En la hoja **grupos-todos los grupos** , haga clic en **+ nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="c45be-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="c45be-122">En la hoja **Grupo** , seleccione **Office 365** o **seguridad** para **tipo de grupo**, escriba **usuarios de dispositivos Windows 10 administrados** en **nombre**, seleccione **asignado** en tipo de pertenencia y, a continuación, haga clic en **crear**. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c45be-122">On the **Group** blade, select **Office 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="c45be-123">Cierre la hoja **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="c45be-123">Close the **Group** blade.</span></span>
    
11. <span data-ttu-id="c45be-124">Cierre la hoja **grupos-todos los grupos** .</span><span class="sxs-lookup"><span data-stu-id="c45be-124">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="c45be-125">En la hoja de **Microsoft Intune** , en la lista **tareas rápidas** , haga clic en **crear una directiva de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="c45be-125">On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="c45be-126">En la hoja **Perfiles de directiva de cumplimiento**, haga clic en **Crear directiva**.</span><span class="sxs-lookup"><span data-stu-id="c45be-126">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="c45be-127">En la hoja **crear Directiva** , en **nombre**, escriba **Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="c45be-127">On the **Create Policy** blade, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="c45be-128">En **plataforma**, seleccione **Windows 10 y versiones posteriores**, haga clic en **Aceptar** en la hoja **Directiva de cumplimiento de Windows 10** y, a continuación, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="c45be-128">In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**.</span></span> <span data-ttu-id="c45be-129">Cierra la hoja de **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="c45be-129">Close the **Windows 10** blade.</span></span>
    
15. <span data-ttu-id="c45be-130">En la hoja **perfiles de directiva de cumplimiento** , haga clic en el nombre de directiva de **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="c45be-130">On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.</span></span>
    
16. <span data-ttu-id="c45be-131">En la hoja de **Windows 10** , haga clic en **tareas**y, a continuación, haga clic en **seleccionar grupos para incluir**.</span><span class="sxs-lookup"><span data-stu-id="c45be-131">On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.</span></span>
    
17. <span data-ttu-id="c45be-132">En la hoja **seleccionar grupos para incluir** , haga clic en el grupo **usuarios de dispositivos de Windows 10 administrados** y, a continuación, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="c45be-132">On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
18. <span data-ttu-id="c45be-133">Haga clic en **Guardar**y, a continuación, cierre la hoja **Windows 10-asignaciones** .</span><span class="sxs-lookup"><span data-stu-id="c45be-133">Click **Save**, and then close the **Windows 10 - Assignments** blade.</span></span>
    
19. <span data-ttu-id="c45be-134">Cierre la hoja **Perfiles de directiva de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="c45be-134">Close the **Compliance Policy Profiles** blade.</span></span>
    
20. <span data-ttu-id="c45be-135">En la hoja de **Microsoft Intune** , haga clic en **aplicaciones cliente** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="c45be-135">On the **Microsoft Intune** blade, click **Client apps** in the left navigation.</span></span>
    
21. <span data-ttu-id="c45be-136">En la hoja **aplicaciones cliente** , haga clic en **aplicaciones**y, a continuación, en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c45be-136">On the **Client Apps** blade, click **Apps**, and then click **Add**.</span></span> 

22. <span data-ttu-id="c45be-137">En la hoja **Agregar aplicación** , seleccione **tipo de aplicación**y, a continuación, seleccione **Windows 10** en **Office 365 Suite**.</span><span class="sxs-lookup"><span data-stu-id="c45be-137">In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

23. <span data-ttu-id="c45be-138">Haga clic en **configurar conjunto de aplicaciones**y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c45be-138">Click **Configure App Suite**, and then click **OK**.</span></span>

24. <span data-ttu-id="c45be-139">Haga clic en **información del conjunto de aplicaciones**, escriba **Office apps para Windows 10** en **nombre del conjunto**, **aplicaciones de Office para Windows 10** en la **Descripción del paquete**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c45be-139">Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.</span></span>

25. <span data-ttu-id="c45be-140">Haga clic en **configuración del conjunto de aplicaciones**, seleccione **semestral** en **Actualizar canal**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c45be-140">Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.</span></span>

26. <span data-ttu-id="c45be-141">En la hoja **Agregar aplicación** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c45be-141">On the **Add app** blade, click **Add**.</span></span>

<span data-ttu-id="c45be-142">Ahora tiene una directiva de cumplimiento de dispositivos para probar las aplicaciones seleccionadas en la Directiva de cumplimiento de dispositivos de **Windows 10** y para los miembros del grupo de **usuarios de dispositivos de Windows 10 administrados** .</span><span class="sxs-lookup"><span data-stu-id="c45be-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="c45be-143">Tenga en cuenta que, al seleccionar Office 365 como tipo de grupo, se crearán recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="c45be-143">Please note that selecting Office 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="c45be-144">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="c45be-144">Next step</span></span>

<span data-ttu-id="c45be-145">Explore otras características y funciones de [Administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="c45be-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c45be-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="c45be-146">See also</span></span>

<span data-ttu-id="c45be-147">[Guías del laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="c45be-147">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="c45be-148">Inscribir dispositivos iOS y Android en su entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c45be-148">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="c45be-149">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c45be-149">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="c45be-150">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="c45be-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
