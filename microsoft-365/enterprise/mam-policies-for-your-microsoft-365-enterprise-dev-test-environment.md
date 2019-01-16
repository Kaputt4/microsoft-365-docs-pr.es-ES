---
title: Entorno de prueba de las directivas de cumplimiento de normas de dispositivo para su empresa de 365 de Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía de laboratorio de prueba para agregar el entorno de prueba de directivas de cumplimiento de dispositivo Intune a la empresa de 365 de Microsoft.
ms.openlocfilehash: 1d957c5cdc888251224bbca43fe82ab0a15e7a93
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871788"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b8522-103">Entorno de prueba de las directivas de cumplimiento de normas de dispositivo para su empresa de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b8522-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b8522-104">Con las instrucciones de este artículo, se agrega una directiva de cumplimiento de normas de dispositivo Intune al entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b8522-104">With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.</span></span>

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="b8522-106">Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b8522-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b8522-107">Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b8522-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b8522-108">Si desea configurar directivas de MAM en una forma sencilla con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="b8522-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b8522-109">Si desea configurar directivas de MAM en una empresa simulada, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b8522-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b8522-p101">Las pruebas automatizadas de licencias y pertenencia a grupos no requiere el entorno de prueba simulado enterprise, que incluye una intranet simulada conectada a Internet y sincronización de Active directory para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar licencias automatizada y la pertenencia a grupos y experimentar con él en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="b8522-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="b8522-112">Fase 2: Crear una directiva de cumplimiento de normas de dispositivo para los dispositivos de Windows 10</span><span class="sxs-lookup"><span data-stu-id="b8522-112">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="b8522-113">En esta fase, se crea una directiva de cumplimiento de normas de dispositivo para dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b8522-113">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="b8522-114">Vaya al portal de Office en ([https://office.com](https://office.com)) e inicie sesión en su suscripción de prueba de Office 365 con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="b8522-114">Go to the Office portal at ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="b8522-115">En una nueva ficha del explorador, abra el portal de Azure en [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="b8522-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="b8522-116">En la ficha portal Azure en el explorador, en el panel de navegación, haga clic en **todos los servicios**, escriba **Intune**y, a continuación, haga clic en **Intune**.</span><span class="sxs-lookup"><span data-stu-id="b8522-116">On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="b8522-p102">Si ve un mensaje **no ha habilitado la administración de dispositivos todavía** en el servidor blade de **Intune de Microsoft** , haga clic en él. En el servidor blade de **autoridad de administración de dispositivos móviles** , haga clic en **Intune MDM entidad**y, a continuación, haga clic en **Elegir**. Actualización de la ficha del explorador.</span><span class="sxs-lookup"><span data-stu-id="b8522-p102">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="b8522-120">En el panel de navegación izquierdo, haga clic en **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="b8522-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="b8522-121">En el servidor blade de **grupos a todos los grupos** , haga clic en **+ nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="b8522-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="b8522-122">En el servidor blade de **grupo** , seleccione **Office 365** para **tipo de grupo?**, escriba **los usuarios de dispositivos administrados 10 de Windows** en **nombre**, seleccione **asignado** en **tipo de pertenencia**y, a continuación, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="b8522-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="b8522-123">Cierre la hoja **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="b8522-123">Close the **Group** blade.</span></span>
    
11. <span data-ttu-id="b8522-124">Cierre el servidor blade de **grupos a todos los grupos** .</span><span class="sxs-lookup"><span data-stu-id="b8522-124">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="b8522-125">En el servidor blade **Intune de Microsoft** , en la lista de **tareas rápidas** , haga clic en **crear una directiva de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="b8522-125">On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="b8522-126">En la hoja **Perfiles de directiva de cumplimiento**, haga clic en **Crear directiva**.</span><span class="sxs-lookup"><span data-stu-id="b8522-126">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="b8522-p103">En el módulo de **Directiva de crear** , en **nombre**, escriba **10 de Windows**. En la **plataforma**, seleccione **10 y versiones posteriores de Windows**, haga clic en **Aceptar** en el servidor blade de la **Directiva de cumplimiento del 10 de Windows** y, a continuación, haga clic en **crear**. Cierre el blade **10 de Windows** .</span><span class="sxs-lookup"><span data-stu-id="b8522-p103">On the **Create Policy** blade, in **Name**, type **Windows 10**. In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**. Close the **Windows 10** blade.</span></span>
    
15. <span data-ttu-id="b8522-130">En el servidor blade de **Perfiles de directivas de cumplimiento** , haga clic en el nombre de la directiva de **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="b8522-130">On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.</span></span>
    
16. <span data-ttu-id="b8522-131">En el módulo **10 de Windows** , haga clic en **asignaciones**y, a continuación, haga clic en **Seleccionar grupos que se incluirán**.</span><span class="sxs-lookup"><span data-stu-id="b8522-131">On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.</span></span>
    
17. <span data-ttu-id="b8522-132">En el servidor blade **seleccione grupos para incluir** , haga clic en el grupo de **usuarios de dispositivos administrados 10 de Windows** y, a continuación, haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="b8522-132">On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
18. <span data-ttu-id="b8522-133">Haga clic en **Guardar**y, a continuación, cierre el módulo **Windows 10 - las asignaciones** .</span><span class="sxs-lookup"><span data-stu-id="b8522-133">Click **Save**, and then close the **Windows 10 - Assignments** blade.</span></span>
    
19. <span data-ttu-id="b8522-134">Cierre la hoja **Perfiles de directiva de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="b8522-134">Close the **Compliance Policy Profiles** blade.</span></span>
    
20. <span data-ttu-id="b8522-135">En el servidor blade **Intune de Microsoft** , haga clic en **aplicaciones de cliente** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="b8522-135">On the **Microsoft Intune** blade, click **Client apps** in the left navigation.</span></span>
    
21. <span data-ttu-id="b8522-136">En el módulo de **Aplicaciones de cliente** , haga clic en **aplicaciones**y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b8522-136">On the **Client Apps** blade, click **Apps**, and then click **Add**.</span></span> 

22. <span data-ttu-id="b8522-137">En el módulo de **aplicación de agregar** , seleccione el **tipo de aplicación**y, a continuación, seleccione **Windows 10** en **El conjunto de aplicaciones de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="b8522-137">In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

23. <span data-ttu-id="b8522-138">Haga clic en **Configurar el conjunto de aplicaciones**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8522-138">Click **Configure App Suite**, and then click **OK**.</span></span>

24. <span data-ttu-id="b8522-139">Haga clic en **Información de conjunto de aplicaciones de una aplicación**, escriba **aplicaciones de Office para Windows 10** en **Nombre del conjunto de aplicaciones**, **aplicaciones de Office para Windows 10** en la **Descripción del conjunto de aplicaciones**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8522-139">Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.</span></span>

25. <span data-ttu-id="b8522-140">Haga clic en **Configuración del conjunto de programas de aplicación**, seleccione **anual punto y** en el **canal de actualización de**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8522-140">Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.</span></span>

26. <span data-ttu-id="b8522-141">En el módulo de **aplicación de agregar** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b8522-141">On the **Add app** blade, click **Add**.</span></span>

<span data-ttu-id="b8522-142">Ahora dispone de una directiva de cumplimiento de normas de dispositivo para probar las aplicaciones seleccionadas en la directiva de cumplimiento de normas de dispositivo de **Windows 10** y para los miembros del grupo de **usuarios de dispositivos administrados 10 de Windows** .</span><span class="sxs-lookup"><span data-stu-id="b8522-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="b8522-143">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="b8522-143">Next step</span></span>

<span data-ttu-id="b8522-144">Explorar las características adicionales de [administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="b8522-144">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8522-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8522-145">See also</span></span>

<span data-ttu-id="b8522-146">[Guías de laboratorio de pruebas de Microsoft Enterprise 365](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="b8522-146">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="b8522-147">Inscriba sus dispositivos iOS y Android en su entorno de desarrollo y prueba de Microsoft Enterprise 365</span><span class="sxs-lookup"><span data-stu-id="b8522-147">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="b8522-148">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b8522-148">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b8522-149">Movilidad de la empresa + seguridad (EMS)</span><span class="sxs-lookup"><span data-stu-id="b8522-149">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
