---
title: Automatizar las licencias y la pertenencia a grupos para el entorno de prueba de Microsoft 365 para empresas
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
description: Configure las licencias basadas en grupos y la pertenencia dinámica a grupos en el entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: 26840e2884202a0fa9c4bb563f3d7c653482ef87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905373"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="b7073-103">Automatizar las licencias y la pertenencia a grupos para el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="b7073-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="b7073-104">*Esta Guía del laboratorio de pruebas solo se puede usar para Microsoft 365 para entornos de prueba empresariales.*</span><span class="sxs-lookup"><span data-stu-id="b7073-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="b7073-105">Las licencias basadas en grupos asignan o quitan automáticamente las licencias de una cuenta de usuario en función de la pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="b7073-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="b7073-106">La pertenencia dinámica a grupos agrega o quita miembros a un grupo en función de las propiedades de la cuenta de usuario, como **Department** o **Country**.</span><span class="sxs-lookup"><span data-stu-id="b7073-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="b7073-107">En este artículo se le indican las demostraciones de agregar y quitar miembros del grupo en el entorno de prueba de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="b7073-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="b7073-108">Configurar las licencias automáticas y la pertenencia dinámica a grupos en el entorno de prueba de Microsoft 365 para empresas implica dos fases:</span><span class="sxs-lookup"><span data-stu-id="b7073-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="b7073-109">Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="b7073-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="b7073-110">Fase 2: Configurar y probar la pertenencia dinámica a grupos y las licencias automáticas</span><span class="sxs-lookup"><span data-stu-id="b7073-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="b7073-112">Para obtener un mapa visual de todos los artículos de la pila guía del laboratorio de pruebas de Microsoft 365 para empresas, vaya a [Microsoft 365 para](../downloads/Microsoft365EnterpriseTLGStack.pdf)enterprise Test Lab Guide Stack .</span><span class="sxs-lookup"><span data-stu-id="b7073-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="b7073-113">Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="b7073-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="b7073-114">Si solo desea probar las licencias automatizadas y la pertenencia a grupos de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="b7073-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b7073-115">Si desea probar las licencias automatizadas y la pertenencia a grupos en una empresa simulada, siga las instrucciones de [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b7073-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7073-116">Las pruebas de licencias automatizadas y pertenencia a grupos no requieren el entorno de prueba de empresa simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="b7073-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b7073-117">Se proporciona aquí como una opción para que pueda probar las licencias automatizadas y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="b7073-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="b7073-118">Fase 2: Configurar y probar la pertenencia dinámica a grupos y las licencias automáticas</span><span class="sxs-lookup"><span data-stu-id="b7073-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="b7073-119">En primer lugar, cree un nuevo grupo denominado Ventas y agregue  una regla de pertenencia a grupos dinámicos para que las cuentas de usuario con el Departamento establecido en **Ventas** se unan automáticamente al grupo Ventas.</span><span class="sxs-lookup"><span data-stu-id="b7073-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="b7073-120">En una instancia privada de su explorador de Internet, inicie sesión en el Centro de administración de [Microsoft 365](https://admin.microsoft.com) con la cuenta de administrador global de su suscripción al laboratorio de pruebas de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b7073-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="b7073-121">En una pestaña independiente del explorador, vaya a Azure Portal en [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="b7073-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="b7073-122">En Azure Portal, escriba **grupos en** el cuadro de búsqueda y, a continuación, **seleccione Grupos**.</span><span class="sxs-lookup"><span data-stu-id="b7073-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="b7073-123">en el **panel Todos los** grupos, seleccione Nuevo **grupo**.</span><span class="sxs-lookup"><span data-stu-id="b7073-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="b7073-124">En **Tipo de grupo**, seleccione Microsoft **365**.</span><span class="sxs-lookup"><span data-stu-id="b7073-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="b7073-125">En **Nombre del grupo**, escriba **Ventas**.</span><span class="sxs-lookup"><span data-stu-id="b7073-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="b7073-126">En **Tipo de pertenencia,** seleccione **Usuario dinámico**.</span><span class="sxs-lookup"><span data-stu-id="b7073-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="b7073-127">Seleccione **Miembros de usuario dinámicos**.</span><span class="sxs-lookup"><span data-stu-id="b7073-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="b7073-128">En el **panel Reglas de pertenencia dinámica:**</span><span class="sxs-lookup"><span data-stu-id="b7073-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="b7073-129">Seleccione la **propiedad department.**</span><span class="sxs-lookup"><span data-stu-id="b7073-129">Select the **department** property.</span></span>
   - <span data-ttu-id="b7073-130">Seleccione el **operador Equals.**</span><span class="sxs-lookup"><span data-stu-id="b7073-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="b7073-131">En el **cuadro** Valor, escriba **Ventas**.</span><span class="sxs-lookup"><span data-stu-id="b7073-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="b7073-132">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b7073-132">Select **Save**.</span></span>
11. <span data-ttu-id="b7073-133">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="b7073-133">Select **Create**.</span></span>

<span data-ttu-id="b7073-134">Después, configure el grupo Ventas para que los miembros se asignen automáticamente la licencia de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b7073-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="b7073-135">Seleccione el **grupo** Ventas y, a continuación, **licencias**.</span><span class="sxs-lookup"><span data-stu-id="b7073-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="b7073-136">En el **panel Actualizar asignaciones de licencias,** **seleccione Microsoft 365 E5** y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b7073-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="b7073-137">En el explorador, cierre la pestaña Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="b7073-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="b7073-138">A continuación, pruebe la pertenencia a grupos dinámicos y las licencias automáticas en la cuenta de usuario 4:</span><span class="sxs-lookup"><span data-stu-id="b7073-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="b7073-139">En la **Microsoft Office inicio** del explorador, seleccione **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="b7073-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="b7073-140">En la pestaña Centro de administración de **Microsoft 365,** seleccione **Usuarios activos.**</span><span class="sxs-lookup"><span data-stu-id="b7073-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="b7073-141">En la **página Usuarios activos,** seleccione la **cuenta Usuario 4.**</span><span class="sxs-lookup"><span data-stu-id="b7073-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="b7073-142">En el **panel Usuario 4,** seleccione **Editar para** licencias **de producto.**</span><span class="sxs-lookup"><span data-stu-id="b7073-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="b7073-143">En el **panel Licencias de productos,** deshabilite la licencia de **Microsoft 365 E5** y, a continuación, **seleccione Guardar**  >  **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b7073-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="b7073-144">En las propiedades de la cuenta de usuario 4, compruebe que no se han asignado licencias de productos y que no hay pertenencias a grupos.</span><span class="sxs-lookup"><span data-stu-id="b7073-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="b7073-145">Para **Información de contacto,** seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b7073-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="b7073-146">En el **panel Editar información de contacto,** seleccione Información de **contacto**.</span><span class="sxs-lookup"><span data-stu-id="b7073-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="b7073-147">En el **cuadro Departamento,** escriba **Ventas** y, a continuación, **seleccione Guardar**  >  **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b7073-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="b7073-148">Espere unos minutos y, a continuación, seleccione periódicamente el icono **Actualizar** en la esquina superior derecha del panel cuenta usuario 4.</span><span class="sxs-lookup"><span data-stu-id="b7073-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="b7073-149">Con el tiempo, debería ver lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7073-149">In time, you should see the:</span></span>

- <span data-ttu-id="b7073-150">**Propiedad pertenencias a grupos** actualizada con el **grupo** Ventas.</span><span class="sxs-lookup"><span data-stu-id="b7073-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="b7073-151">**Propiedad de licencias de productos** actualizada con la licencia de Microsoft **365 E5.**</span><span class="sxs-lookup"><span data-stu-id="b7073-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="b7073-152">Vea estos artículos para implementar la pertenencia dinámica a grupos y las licencias automáticas en producción:</span><span class="sxs-lookup"><span data-stu-id="b7073-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="b7073-153">Licencias basadas en grupos en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b7073-153">Group-based licensing in Azure Active Directory</span></span>](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="b7073-154">Grupos dinámicos en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b7073-154">Dynamic groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="b7073-155">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="b7073-155">Next step</span></span>

<span data-ttu-id="b7073-156">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="b7073-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7073-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7073-157">See also</span></span>

[<span data-ttu-id="b7073-158">Guía básica de identidad</span><span class="sxs-lookup"><span data-stu-id="b7073-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="b7073-159">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="b7073-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b7073-160">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b7073-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b7073-161">Documentación para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b7073-161">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)