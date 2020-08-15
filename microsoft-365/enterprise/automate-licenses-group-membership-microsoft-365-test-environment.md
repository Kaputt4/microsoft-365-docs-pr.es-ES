---
title: Automatizar la concesión de licencias y la pertenencia a grupos de un entorno de prueba de Microsoft 365 para empresas
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
ms.custom:
- TLG
- Ent_TLGs
description: Configure las licencias basadas en grupos y la pertenencia a grupos dinámicas en el entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: a25a47b81ce8c119e7aeb44660af32bb9cafb08a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685563"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="25a2f-103">Automatizar la concesión de licencias y la pertenencia a grupos de un entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="25a2f-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="25a2f-104">*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="25a2f-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="25a2f-105">Las licencias basadas en grupos asignan o eliminan automáticamente licencias de una cuenta de usuario en función de la pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="25a2f-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="25a2f-106">La pertenencia al grupo dinámico agrega o quita miembros de un grupo en función de las propiedades de la cuenta de usuario, como departamento o país.</span><span class="sxs-lookup"><span data-stu-id="25a2f-106">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="25a2f-107">Este artículo le guiará a través de una demostración de ambos en el entorno de prueba de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="25a2f-107">This article steps you through a demonstration of both in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="25a2f-108">Hay dos fases para configurar la licencia automática y la pertenencia a grupos dinámicas en el entorno de prueba de Microsoft 365 para empresas:</span><span class="sxs-lookup"><span data-stu-id="25a2f-108">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment:</span></span>

1. <span data-ttu-id="25a2f-109">Cree el entorno de prueba de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="25a2f-109">Create the Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="25a2f-110">Configurar y probar la pertenencia a grupos dinámica y las licencias automáticas.</span><span class="sxs-lookup"><span data-stu-id="25a2f-110">Configure and test dynamic group membership and automatic licensing.</span></span>

![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="25a2f-112">Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual con todos los artículos en la pila de la guías de laboratorio para pruebas de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="25a2f-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="25a2f-113">Fase 1: crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="25a2f-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="25a2f-114">Si solo quiere probar la concesión de licencias automatizadas y la pertenencia a grupos de una manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="25a2f-114">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="25a2f-115">Si desea probar la concesión de licencias automatizadas y la pertenencia a grupos en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="25a2f-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="25a2f-116">La prueba de la concesión de licencias automatizada y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="25a2f-116">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="25a2f-117">Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="25a2f-117">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="25a2f-118">Fase 2: configurar y probar la pertenencia a grupos dinámica y las licencias automáticas</span><span class="sxs-lookup"><span data-stu-id="25a2f-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="25a2f-119">En primer lugar, cree un nuevo grupo de ventas y agregue una regla de pertenencia a grupos dinámicos para que las cuentas de usuario con el Departamento establecido en ventas se agreguen automáticamente al grupo ventas.</span><span class="sxs-lookup"><span data-stu-id="25a2f-119">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="25a2f-120">Con una instancia privada del explorador de Internet, inicie sesión en el [centro de administración de microsoft 365](https://admin.microsoft.com) con la cuenta de administrador global de la suscripción al laboratorio de pruebas de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="25a2f-120">Using a private instance of your Internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="25a2f-121">En una pestaña independiente del explorador, vaya a Azure portal en [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="25a2f-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="25a2f-122">En el portal de Azure, escriba **grupos** en el cuadro de búsqueda y, a continuación, haga clic en **grupos**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-122">In the Azure portal, type **groups** in the search box, and then click **Groups**.</span></span>
4. <span data-ttu-id="25a2f-123">en el panel **todos los grupos** , haga clic en **nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-123">in the **All groups** pane, click **New group**.</span></span>
5. <span data-ttu-id="25a2f-124">En **tipo de grupo**, seleccione **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="25a2f-125">En **nombre de grupo**, escriba **sales**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-125">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="25a2f-126">En **tipo de pertenencia**, seleccione **usuario dinámico**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="25a2f-127">Haga clic en **miembros de usuario dinámicos**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-127">Click **Dynamic user members**.</span></span>
9. <span data-ttu-id="25a2f-128">En el panel **reglas de pertenencia dinámica** :</span><span class="sxs-lookup"><span data-stu-id="25a2f-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="25a2f-129">Seleccione la propiedad **Department** .</span><span class="sxs-lookup"><span data-stu-id="25a2f-129">Select the **department** property.</span></span>
   - <span data-ttu-id="25a2f-130">Seleccione el operador **es igual** a.</span><span class="sxs-lookup"><span data-stu-id="25a2f-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="25a2f-131">Escriba **sales** en **Value**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-131">Type **Sales** in **Value**.</span></span>
10. <span data-ttu-id="25a2f-132">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="25a2f-132">Click **Save**.</span></span>
11. <span data-ttu-id="25a2f-133">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-133">Click **Create**.</span></span>

<span data-ttu-id="25a2f-134">A continuación, configure el grupo ventas para que a los miembros se les asigne automáticamente la licencia 365 E5 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="25a2f-134">Next, you configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="25a2f-135">Haga clic en el grupo **ventas** y, a continuación, haga clic en **licencias**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-135">Click the **Sales** group, and then click **Licenses**.</span></span>
2. <span data-ttu-id="25a2f-136">En el panel **Actualizar asignaciones de licencia** , seleccione **Microsoft 365 E5**y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then click **Save**.</span></span>
3. <span data-ttu-id="25a2f-137">Cierre la pestaña Azure Portal del explorador.</span><span class="sxs-lookup"><span data-stu-id="25a2f-137">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="25a2f-138">A continuación, pruebe la pertenencia a grupos dinámica y las licencias automáticas en la cuenta de usuario 4.</span><span class="sxs-lookup"><span data-stu-id="25a2f-138">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="25a2f-139">Desde la pestaña **Página principal de Microsoft Office** del explorador, haga clic en **Administración**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-139">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="25a2f-140">En la pestaña **centro de administración de 365 de Microsoft** , haga clic en **usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-140">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="25a2f-141">En la página **usuarios activos** , haga clic en la cuenta de **usuario 4** .</span><span class="sxs-lookup"><span data-stu-id="25a2f-141">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="25a2f-142">En el panel **usuario 4** , haga clic en **Editar** para **licencias de productos**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-142">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="25a2f-143">En el panel **licencias de productos** , deshabilite la licencia de **Microsoft 365 E5** y, a continuación, haga clic en **Guardar > cerrar**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="25a2f-144">En las propiedades de la cuenta usuario 4, compruebe que no se haya asignado ninguna licencia de producto y que no hay pertenencias a grupos.</span><span class="sxs-lookup"><span data-stu-id="25a2f-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="25a2f-145">Haga clic en **Editar** para obtener **información de contacto**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-145">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="25a2f-146">En el panel **editar información de contacto** , haga clic en **información de contacto**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-146">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="25a2f-147">En el campo **Departamento** , escriba **ventas**y, a continuación, haga clic en **Guardar > cerrar**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-147">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="25a2f-148">Espere unos minutos y, a continuación, haga clic periódicamente en el icono de actualización en la esquina superior derecha del panel de la cuenta de usuario 4.</span><span class="sxs-lookup"><span data-stu-id="25a2f-148">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="25a2f-149">En el tiempo debería ver lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="25a2f-149">In time you should see the:</span></span>

- <span data-ttu-id="25a2f-150">**Pertenencias a grupos** (propiedad) actualizada con el grupo **ventas** .</span><span class="sxs-lookup"><span data-stu-id="25a2f-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="25a2f-151">Propiedad de **licencias de producto** actualizada con la licencia de **Microsoft 365 E5** .</span><span class="sxs-lookup"><span data-stu-id="25a2f-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="25a2f-152">Consulte estos artículos para implementar la pertenencia a grupos dinámica y las licencias automáticas en producción:</span><span class="sxs-lookup"><span data-stu-id="25a2f-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- <span data-ttu-id="25a2f-153">VÍNCULO TBD</span><span class="sxs-lookup"><span data-stu-id="25a2f-153">LINK TBD</span></span>
- <span data-ttu-id="25a2f-154">VÍNCULO TBD</span><span class="sxs-lookup"><span data-stu-id="25a2f-154">LINK TBD</span></span>

## <a name="next-step"></a><span data-ttu-id="25a2f-155">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="25a2f-155">Next step</span></span>

<span data-ttu-id="25a2f-156">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="25a2f-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="25a2f-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="25a2f-157">See also</span></span>

[<span data-ttu-id="25a2f-158">Mapa de ruta de identidad</span><span class="sxs-lookup"><span data-stu-id="25a2f-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="25a2f-159">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="25a2f-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="25a2f-160">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="25a2f-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="25a2f-161">Documentación de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="25a2f-161">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
