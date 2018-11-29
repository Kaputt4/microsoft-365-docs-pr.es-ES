---
title: Automatizar la pertenencia a grupo y de la licencia para el entorno de prueba de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Configurar licencias basadas en grupos y pertenencia a grupos dinámicos en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 46d2f0ca063b387d1a4a51b4ea97bd5d60c03fe5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871547"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="2dca2-103">Automatizar la pertenencia a grupo y de la licencia para el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2dca2-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="2dca2-p101">Basadas en grupos de licencias automáticamente asignan o quitan las licencias para una cuenta de usuario en función de la pertenencia a grupos. Pertenencia al grupo dinámico agrega o quita a miembros a un grupo en función de las propiedades de cuenta de usuario, como el departamento o país. En este artículo le guiará por una demostración de ambos tipos en el entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2dca2-p101">Group-based licensing automatically assigns or removes licenses for a user account based on group membership. Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country. This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="2dca2-107">Hay dos fases para configurar la pertenencia a grupos de licencias automático y dinámico en su entorno de prueba de Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="2dca2-107">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="2dca2-108">Crear el entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2dca2-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="2dca2-109">Configurar y probar la pertenencia al grupo dinámico y licencias automática.</span><span class="sxs-lookup"><span data-stu-id="2dca2-109">Configure and test dynamic group membership and automatic licensing.</span></span>

![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="2dca2-111">Haga clic [aquí](https://aka.ms/m365etlgstack) para acceder a un mapa visual de todos los artículos de la pila Guía del laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2dca2-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="2dca2-112">Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2dca2-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="2dca2-113">Si desea probar licencias automatizada y la pertenencia a grupos en una forma sencilla con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="2dca2-113">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="2dca2-114">Si desea probar licencias automatizada y la pertenencia a grupos en una empresa simulada, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="2dca2-114">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2dca2-p102">Las pruebas automatizadas de licencias y pertenencia a grupos no requiere el entorno de prueba simulado enterprise, que incluye una intranet simulada conectada a Internet y sincronización de Active directory para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar licencias automatizada y la pertenencia a grupos y experimentar con él en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="2dca2-p102">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="2dca2-117">Fase 2: Configurar y probar la pertenencia al grupo dinámico y licencias automática</span><span class="sxs-lookup"><span data-stu-id="2dca2-117">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="2dca2-118">En primer lugar, cree un nuevo grupo de ventas y agregar una regla de pertenencia a grupo dinámico para que las cuentas de usuario con el departamento de ventas se agregan automáticamente al grupo de ventas.</span><span class="sxs-lookup"><span data-stu-id="2dca2-118">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="2dca2-119">Uso de una instancia privada de su explorador de Internet, inicie sesión en el portal de Office 365 en [https://portal.office.com](https://portal.office.com) con la cuenta de administrador global de su suscripción de prueba de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="2dca2-119">Using a private instance of your Internet browser, sign in to the Office 365 portal at [https://portal.office.com](https://portal.office.com) with the global administrator account of your Office 365 E5 trial subscription.</span></span>
2. <span data-ttu-id="2dca2-120">En una ficha independiente del explorador, vaya al portal de Azure en [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="2dca2-120">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="2dca2-121">En Azure Portal, haga clic en **Azure Active Directory > Usuarios y grupos > Todos los grupos**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-121">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
4. <span data-ttu-id="2dca2-122">En el servidor blade de **todos los grupos** , haga clic en **nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-122">On the **All groups** blade, click **New group**.</span></span>
5. <span data-ttu-id="2dca2-123">En **tipo de grupo**, seleccione **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-123">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="2dca2-124">En **nombre de grupo**, escriba **ventas**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-124">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="2dca2-125">En **tipo de pertenencia**, seleccione **usuario dinámico** .</span><span class="sxs-lookup"><span data-stu-id="2dca2-125">In **Membership type**, select **Dynamic user** .</span></span>
8. <span data-ttu-id="2dca2-126">Haga clic en **Agregar una consulta dinámica**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-126">Click **Add dynamic query**.</span></span>
9. <span data-ttu-id="2dca2-127">En **Add users where** (Agregar usuarios donde), seleccione **departamento**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-127">In **Add users where**, select **department**.</span></span>
10. <span data-ttu-id="2dca2-128">En el siguiente campo, seleccione **Es igual a**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-128">In the next field, select **Equals**.</span></span>
11. <span data-ttu-id="2dca2-129">En el siguiente campo, escriba **ventas**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-129">In the next field, type **Sales**.</span></span>
12. <span data-ttu-id="2dca2-130">Haga clic en **Agregar consulta** luego en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-130">Click **Add query**, and then click **Create**.</span></span>
13. <span data-ttu-id="2dca2-131">Cierre los módulos de **grupo** y **grupos a todos los grupos** .</span><span class="sxs-lookup"><span data-stu-id="2dca2-131">Close the **Group** and **Groups-All groups** blades.</span></span>

<span data-ttu-id="2dca2-132">A continuación, configure el grupo de ventas para que los miembros se les asigna automáticamente Office 365 E5 y movilidad en la empresa + licencias E5 de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2dca2-132">Next, you configure the Sales group so that members are automatically assigned Office 365 E5 and Enterprise Mobility + Security E5 licenses.</span></span>

1. <span data-ttu-id="2dca2-133">En el módulo de **información general** para Azure Active Directory, haga clic en **licencias > todos los productos de**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-133">On the **Overview** blade for Azure Active Directory, click **Licenses > All products**.</span></span>
2. <span data-ttu-id="2dca2-134">En la lista, seleccione **Enterprise Mobility + Security E5** y **Office 365 Enterprise E5** y, después, haga clic en **+ Asignar**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-134">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
3. <span data-ttu-id="2dca2-135">En el servidor blade **Asignar licencia** , haga clic en **usuarios y grupos**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-135">On the **Assign license** blade, click **Users and groups**.</span></span>
4. <span data-ttu-id="2dca2-136">En la lista de grupos, seleccione el grupo de **ventas** .</span><span class="sxs-lookup"><span data-stu-id="2dca2-136">In the list of groups, select the **Sales** group.</span></span>
5. <span data-ttu-id="2dca2-137">Haga clic en **Seleccionar** y, después, en **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-137">Click **Select**, and then click **Assign**.</span></span>
6. <span data-ttu-id="2dca2-138">Cierre la pestaña Azure Portal del explorador.</span><span class="sxs-lookup"><span data-stu-id="2dca2-138">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="2dca2-139">A continuación, se prueba la pertenencia al grupo dinámico y licencias automática en la cuenta de usuario 4.</span><span class="sxs-lookup"><span data-stu-id="2dca2-139">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="2dca2-140">En la ficha **Página principal de Microsoft Office** en el explorador, haga clic en **Admin**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-140">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="2dca2-141">En la ficha del **Centro de administración de Office** , haga clic en **usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-141">From the **Office Admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="2dca2-142">En la página **usuarios activos** , haga clic en la cuenta de **usuario 4** .</span><span class="sxs-lookup"><span data-stu-id="2dca2-142">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="2dca2-143">En el panel **de usuario 4** , haga clic en **Editar** para **licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-143">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="2dca2-144">En el panel de **licencias de producto** , activar la **movilidad de la empresa + E5 de seguridad** y licencias de **Office 365 Enterprise E5** desactivada y, a continuación, haga clic en **Guardar > Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-144">On the **Product licenses** pane, turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses off, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="2dca2-145">En las propiedades de la cuenta de usuario 4, compruebe que se han asignado ninguna licencia de producto y no hay ningún pertenencias a grupo.</span><span class="sxs-lookup"><span data-stu-id="2dca2-145">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="2dca2-146">Para **obtener información de contacto**, haga clic en **Editar** .</span><span class="sxs-lookup"><span data-stu-id="2dca2-146">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="2dca2-147">En el panel de **información de contacto de editar** , haga clic en **información de contacto**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-147">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="2dca2-148">En el campo **departamento** , escriba **ventas**y, a continuación, haga clic en **Guardar > Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2dca2-148">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="2dca2-149">Espere unos minutos y, a continuación, haga clic periódicamente en el icono de actualización en la parte superior derecha del panel de la cuenta de usuario 4.</span><span class="sxs-lookup"><span data-stu-id="2dca2-149">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="2dca2-150">En el tiempo debería ver el:</span><span class="sxs-lookup"><span data-stu-id="2dca2-150">In time you should see the:</span></span>

- <span data-ttu-id="2dca2-151">Propiedad **pertenencias a grupo** actualizado con el grupo de **ventas** .</span><span class="sxs-lookup"><span data-stu-id="2dca2-151">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="2dca2-152">Propiedad de **licencias de producto** que se ha actualizado con las licencias de **movilidad en la empresa + seguridad E5** y **Office 365 Enterprise E5** .</span><span class="sxs-lookup"><span data-stu-id="2dca2-152">**Product licenses** property updated with the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses.</span></span>

<span data-ttu-id="2dca2-153">En la fase de identidad para obtener información y vínculos para implementar la pertenencia a grupos dinámicos y licencias automática en producción, vea estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2dca2-153">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="2dca2-154">Configurar las licencias automáticas</span><span class="sxs-lookup"><span data-stu-id="2dca2-154">Set up automatic licensing</span></span>](identity-group-based-licensing.md)
- [<span data-ttu-id="2dca2-155">Configurar pertenencia a grupo dinámico</span><span class="sxs-lookup"><span data-stu-id="2dca2-155">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md)

## <a name="next-step"></a><span data-ttu-id="2dca2-156">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="2dca2-156">Next step</span></span>

<span data-ttu-id="2dca2-157">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="2dca2-157">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="2dca2-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="2dca2-158">See also</span></span>

[<span data-ttu-id="2dca2-159">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="2dca2-159">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="2dca2-160">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2dca2-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2dca2-161">Implementación de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2dca2-161">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="2dca2-162">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2dca2-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
