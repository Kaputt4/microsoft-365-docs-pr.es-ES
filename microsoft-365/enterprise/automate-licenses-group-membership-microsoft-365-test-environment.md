---
title: Automatizar la concesión de licencias y la pertenencia a grupos para el entorno de prueba de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure las licencias basadas en grupos y la pertenencia a grupos dinámica en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: b1f3bc4a44e66d162360e82295c8f2877131cd07
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202481"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6424d-103">Automatizar la concesión de licencias y la pertenencia a grupos para el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6424d-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6424d-104">*Esta guía del laboratorio de pruebas solo se puede usar para entornos de prueba de Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="6424d-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="6424d-105">Las licencias basadas en grupos asignan o eliminan automáticamente licencias de una cuenta de usuario en función de la pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="6424d-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="6424d-106">La pertenencia al grupo dinámico agrega o quita miembros de un grupo en función de las propiedades de la cuenta de usuario, como departamento o país.</span><span class="sxs-lookup"><span data-stu-id="6424d-106">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="6424d-107">Este artículo le guiará por el proceso de demostración tanto en el entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6424d-107">This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="6424d-108">Hay dos fases para configurar la licencia automática y la pertenencia a grupos dinámica en el entorno de prueba de Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="6424d-108">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="6424d-109">Crear el entorno de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6424d-109">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="6424d-110">Configurar y probar la pertenencia a grupos dinámica y las licencias automáticas.</span><span class="sxs-lookup"><span data-stu-id="6424d-110">Configure and test dynamic group membership and automatic licensing.</span></span>

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="6424d-112">Haga clic [aquí](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6424d-112">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6424d-113">Fase 1: Crear el entorno de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6424d-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6424d-114">Si solo quiere probar la concesión de licencias automatizadas y la pertenencia a grupos de una manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="6424d-114">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6424d-115">Si desea probar la concesión de licencias automatizadas y la pertenencia a grupos en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6424d-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6424d-116">La prueba de la concesión de licencias automatizada y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="6424d-116">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="6424d-117">Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="6424d-117">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="6424d-118">Fase 2: configurar y probar la pertenencia a grupos dinámica y las licencias automáticas</span><span class="sxs-lookup"><span data-stu-id="6424d-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="6424d-119">En primer lugar, cree un nuevo grupo de ventas y agregue una regla de pertenencia a grupos dinámicos para que las cuentas de usuario con el Departamento establecido en ventas se agreguen automáticamente al grupo ventas.</span><span class="sxs-lookup"><span data-stu-id="6424d-119">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="6424d-120">Con una instancia privada del explorador de Internet, inicie sesión en el portal de Office 365 [https://portal.office.com](https://portal.office.com) en con la cuenta de administrador global de la suscripción a Office 365 E5 del laboratorio de pruebas.</span><span class="sxs-lookup"><span data-stu-id="6424d-120">Using a private instance of your Internet browser, sign in to the Office 365 portal at [https://portal.office.com](https://portal.office.com) with the global administrator account of your Office 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="6424d-121">En una pestaña independiente del explorador, vaya a Azure portal en [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="6424d-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="6424d-122">En Azure Portal, haga clic en **Azure Active Directory > Usuarios y grupos > Todos los grupos**.</span><span class="sxs-lookup"><span data-stu-id="6424d-122">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
4. <span data-ttu-id="6424d-123">En la hoja **todos los grupos** , haga clic en **nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="6424d-123">On the **All groups** blade, click **New group**.</span></span>
5. <span data-ttu-id="6424d-124">En **tipo de grupo**, seleccione **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="6424d-124">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="6424d-125">En **nombre de grupo**, escriba **sales**.</span><span class="sxs-lookup"><span data-stu-id="6424d-125">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="6424d-126">En **tipo de pertenencia**, seleccione **usuario dinámico** .</span><span class="sxs-lookup"><span data-stu-id="6424d-126">In **Membership type**, select **Dynamic user** .</span></span>
8. <span data-ttu-id="6424d-127">Haga clic en **Agregar una consulta dinámica**.</span><span class="sxs-lookup"><span data-stu-id="6424d-127">Click **Add dynamic query**.</span></span>
9. <span data-ttu-id="6424d-128">En **Add users where** (Agregar usuarios donde), seleccione **departamento**.</span><span class="sxs-lookup"><span data-stu-id="6424d-128">In **Add users where**, select **department**.</span></span>
10. <span data-ttu-id="6424d-129">En el siguiente campo, seleccione **Es igual a**.</span><span class="sxs-lookup"><span data-stu-id="6424d-129">In the next field, select **Equals**.</span></span>
11. <span data-ttu-id="6424d-130">En el campo NEXT, escriba **sales**.</span><span class="sxs-lookup"><span data-stu-id="6424d-130">In the next field, type **Sales**.</span></span>
12. <span data-ttu-id="6424d-131">Haga clic en **Agregar consulta** luego en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="6424d-131">Click **Add query**, and then click **Create**.</span></span>
13. <span data-ttu-id="6424d-132">Cierre los blades **Grupo** y **grupos-todos los grupos** .</span><span class="sxs-lookup"><span data-stu-id="6424d-132">Close the **Group** and **Groups-All groups** blades.</span></span>

<span data-ttu-id="6424d-133">A continuación, configure el grupo ventas para que a los miembros se les asigne automáticamente la licencia 365 E5 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6424d-133">Next, you configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="6424d-134">En la hoja de **información general** de Azure Active Directory, haga clic en **licencias > todos los productos**.</span><span class="sxs-lookup"><span data-stu-id="6424d-134">On the **Overview** blade for Azure Active Directory, click **Licenses > All products**.</span></span>
2. <span data-ttu-id="6424d-135">En la lista, seleccione **Micrsooft 365 E5**y, a continuación, haga clic en **asignar**.</span><span class="sxs-lookup"><span data-stu-id="6424d-135">In the list, select **Micrsooft 365 E5**, and then click **Assign**.</span></span>
3. <span data-ttu-id="6424d-136">En la hoja **asignar licencia** , haga clic en **usuarios y grupos**.</span><span class="sxs-lookup"><span data-stu-id="6424d-136">On the **Assign license** blade, click **Users and groups**.</span></span>
4. <span data-ttu-id="6424d-137">En la lista de grupos, seleccione el grupo **ventas** .</span><span class="sxs-lookup"><span data-stu-id="6424d-137">In the list of groups, select the **Sales** group.</span></span>
5. <span data-ttu-id="6424d-138">Haga clic en **Seleccionar** y, después, en **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="6424d-138">Click **Select**, and then click **Assign**.</span></span>
6. <span data-ttu-id="6424d-139">Cierre la pestaña Azure Portal del explorador.</span><span class="sxs-lookup"><span data-stu-id="6424d-139">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="6424d-140">A continuación, pruebe la pertenencia a grupos dinámica y las licencias automáticas en la cuenta de usuario 4.</span><span class="sxs-lookup"><span data-stu-id="6424d-140">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="6424d-141">Desde la pestaña **Página principal de Microsoft Office** del explorador, haga clic en **Administración**.</span><span class="sxs-lookup"><span data-stu-id="6424d-141">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="6424d-142">En la pestaña **centro de administración de 365 de Microsoft** , haga clic en **usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="6424d-142">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="6424d-143">En la página **usuarios activos** , haga clic en la cuenta de **usuario 4** .</span><span class="sxs-lookup"><span data-stu-id="6424d-143">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="6424d-144">En el panel **usuario 4** , haga clic en **Editar** para **licencias de productos**.</span><span class="sxs-lookup"><span data-stu-id="6424d-144">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="6424d-145">En el panel **licencias de productos** , deshabilite la licencia de **Microsoft 365 E5** y, a continuación, haga clic en **Guardar > cerrar**.</span><span class="sxs-lookup"><span data-stu-id="6424d-145">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="6424d-146">En las propiedades de la cuenta usuario 4, compruebe que no se haya asignado ninguna licencia de producto y que no hay pertenencias a grupos.</span><span class="sxs-lookup"><span data-stu-id="6424d-146">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="6424d-147">Haga clic en **Editar** para obtener **información de contacto**.</span><span class="sxs-lookup"><span data-stu-id="6424d-147">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="6424d-148">En el panel **editar información de contacto** , haga clic en **información de contacto**.</span><span class="sxs-lookup"><span data-stu-id="6424d-148">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="6424d-149">En el campo **Departamento** , escriba **ventas**y, a continuación, haga clic en **Guardar > cerrar**.</span><span class="sxs-lookup"><span data-stu-id="6424d-149">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="6424d-150">Espere unos minutos y, a continuación, haga clic periódicamente en el icono de actualización en la esquina superior derecha del panel de la cuenta de usuario 4.</span><span class="sxs-lookup"><span data-stu-id="6424d-150">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="6424d-151">En el tiempo debería ver lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6424d-151">In time you should see the:</span></span>

- <span data-ttu-id="6424d-152">**Pertenencias a grupos** (propiedad) actualizada con el grupo **ventas** .</span><span class="sxs-lookup"><span data-stu-id="6424d-152">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="6424d-153">Propiedad de **licencias de producto** actualizada con la licencia de **Microsoft 365 E5** .</span><span class="sxs-lookup"><span data-stu-id="6424d-153">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="6424d-154">Consulte estos pasos en la fase de identidad para obtener información y vínculos para implementar la pertenencia a grupos dinámica y las licencias automáticas en producción:</span><span class="sxs-lookup"><span data-stu-id="6424d-154">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="6424d-155">Configurar las licencias automáticas</span><span class="sxs-lookup"><span data-stu-id="6424d-155">Set up automatic licensing</span></span>](identity-use-group-management.md#identity-group-license)
- [<span data-ttu-id="6424d-156">Configurar la pertenencia a grupos dinámica</span><span class="sxs-lookup"><span data-stu-id="6424d-156">Set up dynamic group membership</span></span>](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a><span data-ttu-id="6424d-157">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="6424d-157">Next step</span></span>

<span data-ttu-id="6424d-158">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="6424d-158">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6424d-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="6424d-159">See also</span></span>

[<span data-ttu-id="6424d-160">Fase 2: Identidad</span><span class="sxs-lookup"><span data-stu-id="6424d-160">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="6424d-161">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6424d-161">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6424d-162">Implementación de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6424d-162">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="6424d-163">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6424d-163">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
