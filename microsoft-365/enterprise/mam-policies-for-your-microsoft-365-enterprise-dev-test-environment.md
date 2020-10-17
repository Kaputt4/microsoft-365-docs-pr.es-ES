---
title: Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 para empresas
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
description: Use esta guía del laboratorio de pruebas para agregar directivas de cumplimiento de dispositivos de Intune a su entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487417"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a6a58-103">Directivas de cumplimiento de dispositivos para el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="a6a58-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a6a58-104">*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="a6a58-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="a6a58-105">En este artículo se describe cómo agregar una directiva de cumplimiento de dispositivos de Intune para dispositivos Windows 10 y Microsoft 365 apps for Enterprise a su Microsoft 365 para el entorno de prueba Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a6a58-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="a6a58-106">La adición de una directiva de cumplimiento de dispositivos de Intune implica dos fases:</span><span class="sxs-lookup"><span data-stu-id="a6a58-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="a6a58-107">Fase 1: crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="a6a58-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="a6a58-108">Fase 2: crear una directiva de cumplimiento de dispositivos para dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="a6a58-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="a6a58-110">Para obtener un mapa visual de todos los artículos de la pila de la guía del entorno de pruebas de 365 para empresas, vaya a la [pila de la guía de entorno de pruebas 365 de Microsoft para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="a6a58-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a6a58-111">Fase 1: crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="a6a58-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a6a58-112">Si desea configurar directivas de MAM solo de una manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="a6a58-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a6a58-113">Si desea configurar directivas de MAM en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a6a58-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a6a58-114">La prueba de la concesión de licencias automatizada y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="a6a58-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="a6a58-115">Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="a6a58-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="a6a58-116">Fase 2: crear una directiva de cumplimiento de dispositivos para dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="a6a58-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="a6a58-117">En esta fase, cree una directiva de cumplimiento de dispositivos para dispositivos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a6a58-117">In this phase, create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="a6a58-118">Vaya al [centro de administración de microsoft 365](https://admin.microsoft.com) e inicie sesión en su suscripción de laboratorio de pruebas de Microsoft 365 con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="a6a58-118">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
1. <span data-ttu-id="a6a58-119">En una pestaña nueva del explorador, abra Azure portal en [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="a6a58-119">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
1. <span data-ttu-id="a6a58-120">En el cuadro de búsqueda de Azure portal, escriba **Intune**y, a continuación, seleccione **Intune**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-120">In the search box of the Azure portal, enter **Intune**, and then select **Intune**.</span></span>
1. <span data-ttu-id="a6a58-121">Si ve un mensaje **que indica que no ha habilitado la administración de dispositivos todavía** en el panel de **Microsoft Intune** , selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="a6a58-121">If you see a **You haven't enabled device management yet** message in the **Microsoft Intune** pane, select it.</span></span> <span data-ttu-id="a6a58-122">En el panel **entidad de administración de dispositivos móviles** , seleccione **Intune MDM Authority**y, a continuación, seleccione **elegir**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-122">In the **Mobile Device Management authority** pane, select **Intune MDM Authority**, and then select **Choose**.</span></span>
1. <span data-ttu-id="a6a58-123">Actualice la pestaña del explorador.</span><span class="sxs-lookup"><span data-stu-id="a6a58-123">Refresh your browser tab.</span></span>
1. <span data-ttu-id="a6a58-124">En el panel de navegación izquierdo, seleccione **grupos**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-124">In the left navigation pane, select **Groups**.</span></span>
1. <span data-ttu-id="a6a58-125">En el panel **grupos todos los grupos** , seleccione **+ nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-125">In the **Groups-All groups** pane, select **+ New Group**.</span></span>
1. <span data-ttu-id="a6a58-126">En el panel de **Grupo** , **seleccione Microsoft 365** o **seguridad** para **tipo de grupo**, escriba usuarios de dispositivos de **Windows 10 administrados** en **nombre**, seleccione **asignado** en **tipo de pertenencia**y, después, seleccione **crear**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-126">In the **Group** pane, select **Microsoft 365** or **Security** for **Group type?**, enter **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then select **Create**.</span></span>
1. <span data-ttu-id="a6a58-127">Seleccione **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-127">Select **Microsoft Intune**.</span></span>
1. <span data-ttu-id="a6a58-128">En el panel de **Microsoft Intune** , en la lista **tareas rápidas** , seleccione **crear una directiva de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-128">In the **Microsoft Intune** pane, in the **Quick tasks** list, select **Create a compliance policy**.</span></span>
1. <span data-ttu-id="a6a58-129">En el panel **perfiles de directiva de cumplimiento** , seleccione **crear Directiva**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-129">In the **Compliance Policy Profiles** pane, select **Create Policy**.</span></span>
1. <span data-ttu-id="a6a58-130">En el panel **crear Directiva** , en **nombre**, escriba **Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-130">In the **Create Policy** pane, in **Name**, enter **Windows 10**.</span></span> <span data-ttu-id="a6a58-131">En **plataforma**, seleccione **Windows 10 y versiones posteriores**, seleccione **Aceptar** en el panel **Directiva de cumplimiento de Windows 10** y, a continuación, seleccione **crear**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-131">In **Platform**, select **Windows 10 and later**, select **OK** in the **Windows 10 compliance policy** pane, and then select **Create**.</span></span>
1. <span data-ttu-id="a6a58-132">Selecciona **perfiles de directiva de cumplimiento**y, a continuación, selecciona el nombre de la Directiva de **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="a6a58-132">Select **Compliance Policy Profiles**, and then select the **Windows 10** policy name.</span></span>
1. <span data-ttu-id="a6a58-133">En el panel de **Windows 10** , seleccione **tareas**y, a continuación, seleccione **seleccionar grupos para incluirlos**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-133">In the **Windows 10** pane, select **Assignments**, and then select **Select groups to include**.</span></span>
1. <span data-ttu-id="a6a58-134">En el panel **seleccionar grupos para incluir** , seleccione el grupo de **usuarios de dispositivos de Windows 10 administrados** y, a continuación, seleccione **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-134">In the **Select groups to include** pane, select the **Managed Windows 10 device users** group, and then select **Select**.</span></span>
1. <span data-ttu-id="a6a58-135">Seleccione **Guardar**, seleccione **Microsoft Intune-Overview**y, a continuación, seleccione **aplicaciones cliente** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="a6a58-135">Select **Save**, select **Microsoft Intune-Overview**, and then select **Client apps** in the left navigation.</span></span>
1. <span data-ttu-id="a6a58-136">En el panel **aplicaciones cliente** , seleccione **aplicaciones**y, después, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-136">In the **Client Apps** pane, select **Apps**, and then select **Add**.</span></span>
1. <span data-ttu-id="a6a58-137">En el panel **Agregar aplicación** , seleccione **tipo de aplicación**y, después, seleccione **Windows 10** en **Microsoft 365 Suite**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-137">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Microsoft 365 Suite**.</span></span>
1. <span data-ttu-id="a6a58-138">En el panel **Agregar aplicación** , seleccione **información del conjunto de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-138">In the **Add App** pane, select **App Suite Information**.</span></span>
1. <span data-ttu-id="a6a58-139">En el panel de **información del conjunto de aplicaciones** , escriba **Microsoft 365 apps for Enterprise** en el **nombre del conjunto** de aplicaciones y la **Descripción del conjunto**y, después, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-139">In the **App Suite Information** pane, enter **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**, and then select **OK**.</span></span>
1. <span data-ttu-id="a6a58-140">En el panel **Agregar aplicación** , seleccione **configurar conjunto de aplicaciones**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-140">In the **Add App** pane, select **Configure App Suite**, and then select **OK**.</span></span>
1. <span data-ttu-id="a6a58-141">En el panel **Agregar aplicación** , seleccione **configuración del conjunto de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-141">In the **Add App** pane, select **App Suite Settings**.</span></span>
1. <span data-ttu-id="a6a58-142">En **canal de actualización**, seleccione **empresa semianual**y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-142">For **Update Channel**, select **Semi-Annual Enterprise**, and then select **OK**.</span></span>
1. <span data-ttu-id="a6a58-143">En el panel **Agregar aplicación** , seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a6a58-143">In the **Add app** pane, select **Add**.</span></span>

<span data-ttu-id="a6a58-144">Ahora tiene una directiva de cumplimiento de dispositivos para probar las aplicaciones seleccionadas en la Directiva de cumplimiento de dispositivos de **Windows 10** y para los miembros del grupo de **usuarios de dispositivos de Windows 10 administrados** .</span><span class="sxs-lookup"><span data-stu-id="a6a58-144">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="a6a58-145">Tenga en cuenta que seleccionar **Microsoft 365** como el tipo de grupo crea recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="a6a58-145">Please note that selecting **Microsoft 365** as the group type creates additional resources.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="a6a58-146">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="a6a58-146">Next step</span></span>

<span data-ttu-id="a6a58-147">Explore otras características y funciones de [Administración de dispositivos móviles](m365-enterprise-test-lab-guides.md#mobile-device-management) en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="a6a58-147">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6a58-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6a58-148">See also</span></span>

<span data-ttu-id="a6a58-149">[Microsoft 365 para las guías del laboratorio de pruebas de la empresa](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="a6a58-149">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="a6a58-150">Inscribir dispositivos iOS y Android en el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="a6a58-150">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="a6a58-151">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a6a58-151">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="a6a58-152">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="a6a58-152">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
