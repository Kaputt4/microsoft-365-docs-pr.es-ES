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
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487581"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="b5b3e-103">Automatizar la concesión de licencias y la pertenencia a grupos de un entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="b5b3e-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="b5b3e-104">*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="b5b3e-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="b5b3e-105">Las licencias basadas en grupos asignan o eliminan automáticamente licencias de una cuenta de usuario en función de la pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="b5b3e-106">La pertenencia al grupo dinámico agrega o quita miembros de un grupo en función de las propiedades de la cuenta de usuario, como **Departamento** o **país**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="b5b3e-107">En este artículo se explican las demostraciones de agregar y quitar miembros de grupo en el entorno de prueba de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="b5b3e-108">La configuración de licencias automáticas y la pertenencia a grupos dinámicas en el entorno de prueba de Microsoft 365 para empresas implica dos fases:</span><span class="sxs-lookup"><span data-stu-id="b5b3e-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="b5b3e-109">Fase 1: crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="b5b3e-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="b5b3e-110">Fase 2: configurar y probar la pertenencia a grupos dinámica y las licencias automáticas</span><span class="sxs-lookup"><span data-stu-id="b5b3e-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="b5b3e-112">Para obtener un mapa visual de todos los artículos de la pila de la guía del entorno de pruebas de 365 para empresas, vaya a la [pila de la guía de entorno de pruebas 365 de Microsoft para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="b5b3e-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="b5b3e-113">Fase 1: crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="b5b3e-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="b5b3e-114">Si solo quiere probar la concesión de licencias automatizadas y la pertenencia a grupos de una manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="b5b3e-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b5b3e-115">Si desea probar la concesión de licencias automatizadas y la pertenencia a grupos en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b5b3e-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b5b3e-116">La prueba de la concesión de licencias automatizada y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="b5b3e-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b5b3e-117">Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="b5b3e-118">Fase 2: configurar y probar la pertenencia a grupos dinámica y las licencias automáticas</span><span class="sxs-lookup"><span data-stu-id="b5b3e-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="b5b3e-119">En primer lugar, cree un nuevo grupo denominado ventas y agregue una regla de pertenencia a grupos dinámicos para que las cuentas de usuario con el **Departamento** establecido en **ventas** se unan automáticamente al grupo ventas.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="b5b3e-120">En una instancia privada del explorador de Internet, inicie sesión en el [centro de administración de microsoft 365](https://admin.microsoft.com) con la cuenta de administrador global de la suscripción al laboratorio de pruebas de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="b5b3e-121">En una pestaña independiente del explorador, vaya a Azure portal en [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="b5b3e-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="b5b3e-122">En el portal de Azure, escriba **grupos** en el cuadro de búsqueda y, a continuación, seleccione **grupos**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="b5b3e-123">en el panel **todos los grupos** , seleccione **nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="b5b3e-124">En **tipo de grupo**, seleccione **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="b5b3e-125">En **nombre de grupo**, escriba **ventas**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="b5b3e-126">En **tipo de pertenencia**, seleccione **usuario dinámico**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="b5b3e-127">Seleccione **miembros de usuario dinámicos**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="b5b3e-128">En el panel **reglas de pertenencia dinámica** :</span><span class="sxs-lookup"><span data-stu-id="b5b3e-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="b5b3e-129">Seleccione la propiedad **Department** .</span><span class="sxs-lookup"><span data-stu-id="b5b3e-129">Select the **department** property.</span></span>
   - <span data-ttu-id="b5b3e-130">Seleccione el operador **es igual** a.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="b5b3e-131">En el cuadro **valor** , escriba **sales**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="b5b3e-132">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-132">Select **Save**.</span></span>
11. <span data-ttu-id="b5b3e-133">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-133">Select **Create**.</span></span>

<span data-ttu-id="b5b3e-134">A continuación, configure el grupo ventas para que a los miembros se les asigne automáticamente la licencia 365 E5 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="b5b3e-135">Seleccione el grupo **ventas** y, a continuación, seleccione **licencias**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="b5b3e-136">En el panel **Actualizar asignaciones de licencia** , seleccione **Microsoft 365 E5**y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="b5b3e-137">En el explorador, cierre la pestaña Azure portal.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="b5b3e-138">A continuación, pruebe la pertenencia al grupo dinámico y la licencia automática en la cuenta de usuario 4:</span><span class="sxs-lookup"><span data-stu-id="b5b3e-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="b5b3e-139">En la pestaña **Página principal de Microsoft Office** del explorador, seleccione **Administración**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="b5b3e-140">En la pestaña **centro de administración de 365 de Microsoft** , seleccione **usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="b5b3e-141">En la página **usuarios activos** , seleccione la cuenta de **usuario 4** .</span><span class="sxs-lookup"><span data-stu-id="b5b3e-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="b5b3e-142">En el panel **usuario 4** , seleccione **Editar** para **licencias de productos**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="b5b3e-143">En el panel **licencias de productos** , deshabilite la licencia de **Microsoft 365 E5** y, a continuación, seleccione **Guardar**  >  **cierre**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="b5b3e-144">En las propiedades de la cuenta usuario 4, compruebe que no se haya asignado ninguna licencia de producto y que no hay pertenencias a grupos.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="b5b3e-145">Para obtener **información de contacto**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="b5b3e-146">En el panel **editar información de contacto** , seleccione **información de contacto**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="b5b3e-147">En el cuadro **Departamento** , escriba **sales**y, a continuación, seleccione **Guardar**  >  **cierre**.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="b5b3e-148">Espere unos minutos y, a continuación, seleccione periódicamente el icono de **actualización** en la esquina superior derecha del panel de la cuenta de usuario 4.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="b5b3e-149">En el tiempo, debería ver lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5b3e-149">In time, you should see the:</span></span>

- <span data-ttu-id="b5b3e-150">**Pertenencias a grupos** (propiedad) actualizada con el grupo **ventas** .</span><span class="sxs-lookup"><span data-stu-id="b5b3e-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="b5b3e-151">Propiedad de **licencias de producto** actualizada con la licencia de **Microsoft 365 E5** .</span><span class="sxs-lookup"><span data-stu-id="b5b3e-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="b5b3e-152">Consulte estos artículos para implementar la pertenencia a grupos dinámica y las licencias automáticas en producción:</span><span class="sxs-lookup"><span data-stu-id="b5b3e-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="b5b3e-153">Licencias basadas en grupos en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b5b3e-153">Group-based licensing in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="b5b3e-154">Grupos dinámicos en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b5b3e-154">Dynamic groups in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="b5b3e-155">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="b5b3e-155">Next step</span></span>

<span data-ttu-id="b5b3e-156">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="b5b3e-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5b3e-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5b3e-157">See also</span></span>

[<span data-ttu-id="b5b3e-158">Mapa de ruta de identidad</span><span class="sxs-lookup"><span data-stu-id="b5b3e-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="b5b3e-159">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="b5b3e-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b5b3e-160">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b5b3e-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b5b3e-161">Documentación de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="b5b3e-161">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
