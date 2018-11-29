---
title: Directivas MAM para sus entornos de prueba de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía de laboratorio de prueba para agregar el entorno de prueba de directivas de administración (MAM) de Intune aplicaciones móviles para la empresa de 365 de Microsoft.
ms.openlocfilehash: f00379a5e70dce5e07c031a7647b27041d3fa9d1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871788"
---
# <a name="mam-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1a64e-103">Directivas MAM para sus entornos de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1a64e-103">MAM policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1a64e-104">Con las instrucciones de este artículo, se agrega el entorno de prueba de directivas de administración (MAM) de Intune aplicaciones móviles para la empresa de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1a64e-104">With the instructions in this article, you add Intune mobile application management (MAM) policies to your Microsoft 365 Enterprise test environment.</span></span>

![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="1a64e-106">Haga clic [aquí](https://aka.ms/m365etlgstack) para acceder a un mapa visual de todos los artículos de la pila Guía del laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1a64e-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1a64e-107">Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1a64e-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1a64e-108">Si desea configurar directivas de MAM en una forma sencilla con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="1a64e-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="1a64e-109">Si desea configurar directivas de MAM en una empresa simulada, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1a64e-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1a64e-p101">Las pruebas automatizadas de licencias y pertenencia a grupos no requiere el entorno de prueba simulado enterprise, que incluye una intranet simulada conectada a Internet y sincronización de Active directory para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar licencias automatizada y la pertenencia a grupos y experimentar con él en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="1a64e-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-and-deploy-mam-policies-for-ios-and-android-devices"></a><span data-ttu-id="1a64e-112">Fase 2: Crear e implementar directivas de MAM para dispositivos iOS y Android</span><span class="sxs-lookup"><span data-stu-id="1a64e-112">Phase 2: Create and deploy MAM policies for iOS and Android devices</span></span>

<span data-ttu-id="1a64e-113">En esta fase, creará e implementará dos directivas de MAM diferentes: una para dispositivos iOS y otra para dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="1a64e-113">In this phase, you create and deploy two different MAM policies: one for iOS devices and one for Android devices.</span></span>
  
1. <span data-ttu-id="1a64e-114">Vaya al portal de Office 365 en ([https://portal.office.com](https://portal.office.com)) e inicie sesión en su suscripción de prueba de Office 365 con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="1a64e-114">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="1a64e-115">En una nueva ficha del explorador, abra el portal de Azure en [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="1a64e-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="1a64e-116">En la ficha portal Azure en Internet Explorer, en el panel de navegación, haga clic en **todos los servicios**, escriba **Intune**y, a continuación, haga clic en **Intune**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-116">On the Azure portal tab in Internet Explorer, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="1a64e-p102">Si ve un mensaje **no ha habilitado la administración de dispositivos todavía** en el servidor blade de **Intune de Microsoft** , haga clic en él. En el servidor blade de **autoridad de administración de dispositivos móviles** , haga clic en **Intune MDM entidad**y, a continuación, haga clic en **Elegir**. Actualización de la ficha del explorador.</span><span class="sxs-lookup"><span data-stu-id="1a64e-p102">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="1a64e-120">En el panel de navegación izquierdo, haga clic en **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="1a64e-121">En el servidor blade de **grupos a todos los grupos** , haga clic en **+ nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="1a64e-122">En el servidor blade de **grupo** , seleccione **Office 365** para **tipo de grupo?**, escriba **administrado a los usuarios de dispositivos iOS** en **nombre**, seleccione **asignado** en **tipo de pertenencia**y, a continuación, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed iOS device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="1a64e-123">Cierre la hoja **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-123">Close the **Group** blade.</span></span>
    
9. <span data-ttu-id="1a64e-124">En el servidor blade de **grupos a todos los grupos** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-124">On the **Groups-All groups** blade, click **Add**.</span></span>
    
10. <span data-ttu-id="1a64e-125">En el servidor blade de **grupo** , seleccione **Office 365** para **tipo de grupo?**, escriba **usuario de dispositivos Android administrado** en **nombre**, seleccione **asignado** en **tipo de pertenencia**y, a continuación, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-125">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Android device user** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span>
    
11. <span data-ttu-id="1a64e-126">Cierre el servidor blade de **grupos a todos los grupos** .</span><span class="sxs-lookup"><span data-stu-id="1a64e-126">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="1a64e-127">En la hoja **Intune**, en la lista **Tareas rápidas**, haga clic en **Crear una directiva de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-127">On the **Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="1a64e-128">En la hoja **Perfiles de directiva de cumplimiento**, haga clic en **Crear directiva**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-128">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="1a64e-p103">En la hoja **Crear directiva**, en **Nombre**, escriba **iOS**. En **Plataforma**, seleccione **iOS**, haga clic en **Aceptar** en la hoja **Directiva de cumplimiento de iOS** y, a continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-p103">On the **Create Policy** blade, in **Name**, type **iOS**. In **Platform**, select **iOS**, click **OK** on the **iOS compliance policy** blade, and then click **Create**.</span></span>
    
15. <span data-ttu-id="1a64e-131">En la hoja **Perfiles de directiva de cumplimiento**, haga clic en **Crear directiva**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-131">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
16. <span data-ttu-id="1a64e-p104">En la hoja **Crear directiva**, en **Nombre**, escriba **Android**. En **Plataforma**, seleccione **Android**, haga clic en **Aceptar** en la hoja **Directiva de cumplimiento de Android** y, a continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-p104">On the **Create Policy** blade, in **Name**, type **Android**. In **Platform**, select **Android**, click **OK** on the **Android compliance policy** blade, and then click **Create**.</span></span>
    
17. <span data-ttu-id="1a64e-134">En la hoja **Perfiles de directiva de cumplimiento**, haga clic en el nombre de directiva **Android**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-134">On the **Compliance Policy Profiles** blade, click the **Android** policy name.</span></span>
    
18. <span data-ttu-id="1a64e-135">En el panel de navegación izquierdo de la hoja **Android - Propiedades**, haga clic en **Tareas** y, a continuación, en **Seleccionar grupos**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-135">In the left navigation of the **Android - Properties** blade, click **Assignments**, and then click **Select groups**.</span></span>
    
19. <span data-ttu-id="1a64e-136">En la hoja **Seleccionar grupos**, haga clic en **Usuarios de dispositivos Android administrados** y después haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-136">On the **Select groups** blade, click the **Managed Android device users** group, and then click **Select**.</span></span>
    
20. <span data-ttu-id="1a64e-137">Haga clic en **Guardar**y, a continuación, cierre el blade **Android - las asignaciones** .</span><span class="sxs-lookup"><span data-stu-id="1a64e-137">Click **Save**, and then close the **Android - Assignments** blade.</span></span>
    
21. <span data-ttu-id="1a64e-138">En la hoja **Perfiles de directiva de cumplimiento**, haga clic en el nombre de directiva **iOS**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-138">On the **Compliance Policy Profiles** blade, click the **iOS** policy name.</span></span>
    
22. <span data-ttu-id="1a64e-139">En el panel de navegación izquierdo de la hoja **iOS - Propiedades**, haga clic en **Tareas** y, a continuación, en **Seleccionar grupos**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-139">In the left navigation of the **iOS - Properties** blade, click **Assignments**, and then click **Select groups**.</span></span>
    
23. <span data-ttu-id="1a64e-140">En la hoja **Seleccionar grupos**, haga clic en el grupo **Usuarios de dispositivos iOS administrados** y después haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-140">On the **Select groups** blade, click the **Managed iOS device users** group, and then click **Select**.</span></span>
    
24. <span data-ttu-id="1a64e-141">Haga clic en **Guardar**y, a continuación, cierre el blade **iOS - las asignaciones** .</span><span class="sxs-lookup"><span data-stu-id="1a64e-141">Click **Save**, and then close the **iOS - Assignments** blade.</span></span>
    
25. <span data-ttu-id="1a64e-142">Cierre la hoja **Perfiles de directiva de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-142">Close the **Compliance Policy Profiles** blade.</span></span>
    
26. <span data-ttu-id="1a64e-143">En la hoja **Intune**, haga clic en **Administrar aplicaciones** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="1a64e-143">On the **Intune** blade, click **Manage apps** in the left navigation.</span></span>
    
27. <span data-ttu-id="1a64e-144">En la hoja **Aplicaciones móviles**, haga clic en **Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-144">On the **Mobile Apps** blade, click **Apps**.</span></span>
    
28. <span data-ttu-id="1a64e-145">En la lista de aplicaciones, haga clic en **PowerPoint**, </span><span class="sxs-lookup"><span data-stu-id="1a64e-145">In the list of apps, click **PowerPoint**,</span></span> 
    
29. <span data-ttu-id="1a64e-p105">En la hoja **Información general sobre PowerPoint**, haga clic en **Tareas > Seleccionar grupos > Dispositivos iOS administrados > Seleccionar**. En **Tipo**, seleccione **Disponible** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-p105">On the **PowerPoint Overview** blade, click **Assignments > Select groups > Managed iOS devices > Select**. In **Type**, select **Available**, and then click **Save**.</span></span>
    
30. <span data-ttu-id="1a64e-148">Repita el paso 29 para las aplicaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="1a64e-148">Repeat step 29 for the following apps:</span></span>
    
    - <span data-ttu-id="1a64e-149">Outlook para Android</span><span class="sxs-lookup"><span data-stu-id="1a64e-149">Outlook for Android</span></span>
    
    - <span data-ttu-id="1a64e-150">Word para iOS</span><span class="sxs-lookup"><span data-stu-id="1a64e-150">Word for iOS</span></span>
    
    - <span data-ttu-id="1a64e-151">Excel para iOS</span><span class="sxs-lookup"><span data-stu-id="1a64e-151">Excel for iOS</span></span>
    
    - <span data-ttu-id="1a64e-152">Outlook para iOS</span><span class="sxs-lookup"><span data-stu-id="1a64e-152">Outlook for iOS</span></span>
    
    - <span data-ttu-id="1a64e-153">Microsoft Dynamics CRM en iPad para iOS</span><span class="sxs-lookup"><span data-stu-id="1a64e-153">Microsoft Dynamics CRM on iPad for iOS</span></span>
    
    - <span data-ttu-id="1a64e-154">Microsoft Dynamics CRM en iPhone para iOS</span><span class="sxs-lookup"><span data-stu-id="1a64e-154">Microsoft Dynamics CRM on iPhone for iOS</span></span>
    
    - <span data-ttu-id="1a64e-155">Dynamics CRM para teléfonos Android</span><span class="sxs-lookup"><span data-stu-id="1a64e-155">Dynamics CRM for Phones for Android</span></span>
    
    - <span data-ttu-id="1a64e-156">Dynamics CRM para tabletas Android</span><span class="sxs-lookup"><span data-stu-id="1a64e-156">Dynamics CRM for Tablets for Android</span></span>
    
    - <span data-ttu-id="1a64e-157">Excel para Android</span><span class="sxs-lookup"><span data-stu-id="1a64e-157">Excel for Android</span></span>
    
    - <span data-ttu-id="1a64e-158">Word para Android</span><span class="sxs-lookup"><span data-stu-id="1a64e-158">Word for Android</span></span>
    
    - <span data-ttu-id="1a64e-159">OneNote para iOS</span><span class="sxs-lookup"><span data-stu-id="1a64e-159">OneNote for iOS</span></span>
    
31. <span data-ttu-id="1a64e-160">Cierre la hoja **Aplicaciones móviles - Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-160">Close the **Mobile Apps - Apps** blade.</span></span>
    
32. <span data-ttu-id="1a64e-161">En la hoja **Aplicaciones móviles**, haga clic en **Directivas de protección de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-161">On the **Mobile Apps** blade, click **App Protection Policies**.</span></span>
    
33. <span data-ttu-id="1a64e-162">En la hoja **Directivas de protección de aplicaciones**, haga clic en **Agregar directiva**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-162">On the **App Protection Policies** blade, click **Add a policy**.</span></span>
    
34. <span data-ttu-id="1a64e-163">En la hoja **Agregar directiva**, escriba **iOS** y, a continuación, haga clic en **Elegir aplicaciones obligatorias**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-163">On the **Add a policy** blade, type **iOS**, and then click **Select required apps**.</span></span>
    
35. <span data-ttu-id="1a64e-164">En la hoja **Aplicaciones**, haga clic en **PowerPoint**, **Microsoft Dynamics CRM en iPhone**, **Excel**, **Microsoft Dynamics CRM en iPhone**, **Word**, **OneNote** y **Outlook**, y, a continuación, en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-164">On the **Apps** blade, click **PowerPoint**, **Microsoft Dynamics CRM on iPhone**, **Excel**, **Microsoft Dynamics CRM on iPhone**, **Word**, **OneNote**, and **Outlook**, and then click **Select**.</span></span>
    
36. <span data-ttu-id="1a64e-165">En la hoja **Agregar una directiva**, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-165">On the **Add a policy** blade, click **Create**.</span></span>
    
37. <span data-ttu-id="1a64e-166">En la hoja **Directivas de protección de aplicaciones**, haga clic en **Agregar directiva**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-166">On the **App Protection Policies** blade, click **Add a policy**.</span></span>
    
38. <span data-ttu-id="1a64e-167">En la hoja **Agregar una directiva**, escriba **Android**, seleccione **Android** en **Plataforma** y, a continuación, haga clic en **Elegir aplicaciones obligatorias**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-167">On the **Add a policy** blade, type **Android**, select **Android** in **Platform**, and then click **Select required apps**.</span></span>
    
39. <span data-ttu-id="1a64e-168">En la hoja **Aplicaciones**, haga clic en **PowerPoint**, **Dynamics CRM para tabletas**, **Excel**, **Word**, **Outlook** y **Dynamics CRM para teléfonos** y, a continuación, en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-168">On the **Apps** blade, click **PowerPoint**, **Dynamics CRM for tablets**, **Excel**, **Word**, **Outlook**, and **Dynamics CRM for phones**, and then click **Select**.</span></span>
    
40. <span data-ttu-id="1a64e-169">En la hoja **Agregar una directiva**, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="1a64e-169">On the **Add a policy** blade, click **Create**.</span></span>
    
<span data-ttu-id="1a64e-170">Ahora tiene dos directivas de MAM, una para dispositivos iOS y otra para dispositivos Android, y está preparado para experimentar con la configuración de prueba para las aplicaciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="1a64e-170">You now have two MAM policies, one for iOS devices and one for Android devices, and are ready to experiment with testing settings for the selected apps.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="1a64e-171">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="1a64e-171">Next step</span></span>

<span data-ttu-id="1a64e-172">Explorar las características adicionales de [administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="1a64e-172">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a64e-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a64e-173">See also</span></span>

<span data-ttu-id="1a64e-174">[Guías de laboratorio de pruebas de Microsoft Enterprise 365](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="1a64e-174">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="1a64e-175">Inscriba sus dispositivos iOS y Android en su entorno de desarrollo y prueba de Microsoft Enterprise 365</span><span class="sxs-lookup"><span data-stu-id="1a64e-175">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="1a64e-176">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1a64e-176">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="1a64e-177">Movilidad de la empresa + seguridad (EMS)</span><span class="sxs-lookup"><span data-stu-id="1a64e-177">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
