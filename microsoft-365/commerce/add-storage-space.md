---
title: Agregar espacio de almacenamiento para la suscripción
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Aprenda a agregar y reducir el almacenamiento de archivos en su suscripción a Microsoft 365. Con el almacenamiento adicional de archivos, puede almacenar más contenido en SharePoint Online y OneDrive.
ms.date: ''
ms.openlocfilehash: fd59de31a27a1dd29800ae1d081e1f509f399124
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114912"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="3aa1e-104">Agregar espacio de almacenamiento para la suscripción</span><span class="sxs-lookup"><span data-stu-id="3aa1e-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3aa1e-105">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-105">The admin center is changing.</span></span> <span data-ttu-id="3aa1e-106">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="3aa1e-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="3aa1e-107">Si empieza a quedarse sin espacio de almacenamiento en las colecciones de sitios de SharePoint Online, puede aumentar el almacenamiento de su suscripción si su plan cumple con los requisitos.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="3aa1e-108">Si no ve el almacenamiento adicional de archivos de **Office 365** en la lista de complementos disponibles, significa que su plan no es apto.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="3aa1e-109">Para obtener más información, vea [¿Mi plan es apto?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="3aa1e-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="3aa1e-110">Si compró la suscripción a través de licencias por volumen o un CSP, no puede comprar Office **365 Extra File Storage** para su organización directamente a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="3aa1e-111">Póngase en contacto con su representante o partner para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3aa1e-112">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="3aa1e-112">Before you begin</span></span>

<span data-ttu-id="3aa1e-113">Debe ser administrador global o de SharePoint para realizar las tareas de este artículo.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="3aa1e-114">Para obtener más información, vea [Sobre los roles de administrador](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3aa1e-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="3aa1e-115">Ver el almacenamiento disponible</span><span class="sxs-lookup"><span data-stu-id="3aa1e-115">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3aa1e-116">En el Centro de administración <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank"></a> de SharePoint, vaya a la página Sitios activos e inicie sesión con una cuenta que tenga permisos de administrador [para](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) su organización.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="3aa1e-117">En la esquina superior derecha de la página, puede ver la cantidad de almacenamiento empleado en todos los sitios, así como el almacenamiento total de su suscripción.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="3aa1e-118">Si su organización ha configurado Multi-Geo en Office 365, la barra también muestra la cantidad de almacenamiento que se usa en todas las ubicaciones geográficas.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Barra de almacenamiento en la página de Sitios activos](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="3aa1e-120">El almacenamiento usado no incluye cambios realizados en las últimas 24-48 horas.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3aa1e-121">Inicie sesión como administrador global o de SharePoint y, a continuación, seleccione el icono De administración https://portal.office.de para abrir el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-121">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="3aa1e-122">Si ve un mensaje que indica que no tiene permiso para acceder a la página, significa que no tiene permisos de administrador de Microsoft 365 en su organización.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-122">If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="3aa1e-123">En el panel izquierdo, en Centros **de administración,** **seleccione SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="3aa1e-124">Si se muestra el Centro de administración de SharePoint clásico, seleccione **Abrirlo ahora** en la parte superior de la página para abrir el nuevo Centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="3aa1e-125">En el panel izquierdo del nuevo Centro de administración de SharePoint, seleccione **Sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="3aa1e-126">En la esquina superior derecha de la página, puede ver la cantidad de almacenamiento empleado en todos los sitios, así como el almacenamiento total de su suscripción.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

   ![Barra de almacenamiento en la página de Sitios activos](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="3aa1e-128">El almacenamiento usado no incluye cambios realizados en las últimas 24-48 horas.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3aa1e-129">Inicie sesión como administrador global o de SharePoint y, a continuación, seleccione el icono De administración https://login.partner.microsoftonline.cn/ para abrir el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-129">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="3aa1e-130">(Si ve un mensaje que indica que no tiene permiso para acceder a la página, significa que no tiene permisos de administrador de Microsoft 365 en su organización.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-130">(If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="3aa1e-131">En el panel izquierdo, en Centros **de administración,** **seleccione SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-131">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="3aa1e-132">Si se muestra el Centro de administración de SharePoint clásico, seleccione **Abrirlo ahora** en la parte superior de la página para abrir el nuevo Centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-132">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="3aa1e-133">En el panel izquierdo del nuevo Centro de administración de SharePoint, seleccione **Sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-133">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="3aa1e-134">En la esquina superior derecha de la página, puede ver la cantidad de almacenamiento empleado en todos los sitios, así como el almacenamiento total de su suscripción.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-134">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

   ![Barra de almacenamiento en la página de Sitios activos](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="3aa1e-136">El almacenamiento usado no incluye cambios realizados en las últimas 24-48 horas.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-136">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

<span data-ttu-id="3aa1e-137">Una vez que haya determinado cuánto espacio de almacenamiento está usando, puede agregar o quitar espacio de almacenamiento para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-137">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="3aa1e-138">Para averiguar cuánto costará agregar espacio de almacenamiento, siga los pasos de este artículo y revise la información de precios antes de comprar.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-138">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="3aa1e-139">Para obtener información acerca de cómo establecer límites de almacenamiento de colecciones de sitios, vea Administrar límites de [almacenamiento de colecciones de sitios.](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)</span><span class="sxs-lookup"><span data-stu-id="3aa1e-139">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="3aa1e-140">Agregar almacenamiento a la suscripción</span><span class="sxs-lookup"><span data-stu-id="3aa1e-140">Add storage to your subscription</span></span>

<span data-ttu-id="3aa1e-141">Si aún no ha comprado almacenamiento adicional para su suscripción, puede hacerlo.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-141">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3aa1e-142">En el centro de administración, vaya a la página **Servicios de compra** de \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">facturación.</a></span><span class="sxs-lookup"><span data-stu-id="3aa1e-142">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="3aa1e-143">At the bottom of the **Purchase services** page, select **Add-ons**.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-143">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>
3. <span data-ttu-id="3aa1e-144">Seleccione **Almacenamiento de archivos adicional de Office 365.**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-144">Select **Office 365 Extra File Storage**.</span></span>
4. <span data-ttu-id="3aa1e-145">En la página Almacenamiento adicional de archivos de **Office 365,** si se muestra, elija la suscripción base y, a continuación, escriba el número de gigabytes de almacenamiento que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-145">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="3aa1e-146">Seleccione **Des check out now**.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-146">Select **Check out now**.</span></span>
6. <span data-ttu-id="3aa1e-147">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-147">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="3aa1e-148">En la **página Completar pedido,** compruebe el total.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-148">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="3aa1e-149">Si necesita realizar cambios, seleccione **Editar orden.**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-149">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="3aa1e-150">Si el pedido requiere una comprobación de crédito, active la casilla.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-150">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="3aa1e-151">Cuando haya terminado, seleccione **Realizar pedido** Ir a la página principal \> **de administración.**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-151">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3aa1e-152">En el centro de administración, vaya a la página **Suscripciones** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">de facturación.</a>  </span><span class="sxs-lookup"><span data-stu-id="3aa1e-152">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="3aa1e-153">En la **página** Suscripciones, elija la suscripción a la que desea agregar espacio de almacenamiento y, a continuación, **seleccione Complementos.**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-153">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="3aa1e-155">Si no ve complementos y la suscripción se compró a través de un partner, seleccione Centro de servicios de licencias por **volumen (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-155">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="3aa1e-156">Seleccione **Comprar complementos.**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-156">Select **Buy add-ons**.</span></span>

    ![Vínculo Comprar complementos en la página Suscripciones del centro de administración.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="3aa1e-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select Buy **now**.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="3aa1e-159">Escriba el número de licencias de usuario que necesita y, si se muestra, elija una suscripción base.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-159">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="3aa1e-160">Seleccione **Des check out now**.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-160">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="3aa1e-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="3aa1e-162">En la **página Completar pedido,** seleccione **Realizar pedido.**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-162">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3aa1e-163">En el Centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Suscripciones</a>.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="3aa1e-164">En la **página** Suscripciones, elija la suscripción a la que desea agregar espacio de almacenamiento y, a continuación, **seleccione Complementos.**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-164">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="3aa1e-166">Si no ve complementos y la suscripción se compró a través de un partner, seleccione Centro de servicios de licencias por **volumen (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-166">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="3aa1e-167">Seleccione **Comprar complementos.**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-167">Select **Buy add-ons**.</span></span>

    ![Vínculo Comprar complementos en la página Suscripciones del centro de administración.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="3aa1e-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select Buy **now**.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="3aa1e-170">Escriba el número de licencias de usuario que necesita y, si se muestra, elija una suscripción base.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-170">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="3aa1e-171">Seleccione **Des check out now**.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-171">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="3aa1e-172">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-172">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="3aa1e-173">En la **página Completar pedido,** seleccione **Realizar pedido.**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-173">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="3aa1e-174">Aumentar o disminuir el almacenamiento</span><span class="sxs-lookup"><span data-stu-id="3aa1e-174">Increase or decrease storage</span></span>

<span data-ttu-id="3aa1e-175">Si ya ha adquirido almacenamiento adicional de archivos a través del complemento de almacenamiento de archivos adicional de **Office 365,** puede seguir estos pasos para aumentar o reducir el espacio de almacenamiento adicional para su suscripción.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-175">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="3aa1e-176">Puede reducir el almacenamiento a un mínimo de 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-176">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="3aa1e-177">Para quitar todo el espacio de almacenamiento adicional, [póngase en contacto con el soporte técnico.](../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="3aa1e-177">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3aa1e-178">En el Centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="3aa1e-179">En la **pestaña** Productos, seleccione la suscripción que contiene el complemento De almacenamiento de archivos adicional de **Office 365.**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-179">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="3aa1e-180">En la página detalles del producto, en la sección **Complementos,** seleccione Administrar **complementos.**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-180">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="3aa1e-181">En el **panel Administrar complementos,** en la lista De **complementos,** elija Almacenamiento de **archivos adicional de Office 365.**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-181">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="3aa1e-182">En el **cuadro de texto** Cantidad, escriba el número de GBs de espacio de almacenamiento que desea para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-182">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="3aa1e-183">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-183">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3aa1e-184">En el Centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Suscripciones</a>.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="3aa1e-185">En la **página Suscripciones,** **seleccione Complementos.**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-185">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="3aa1e-187">Si no ve complementos y la suscripción se compró a través de un partner, seleccione Centro de servicios de licencias por **volumen (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-187">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="3aa1e-188">En Almacenamiento adicional de archivos de **Office 365,** seleccione **Cambiar cantidad.**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-188">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Cambiar vínculo Cantidad.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="3aa1e-190">En el panel derecho, escriba el número total de gigabytes que necesita y, a continuación, **seleccione Enviar**.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-190">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="3aa1e-191">Por ejemplo, si actualmente tiene 200 gigabytes de almacenamiento adicional de archivos pero solo necesita 100 gigabytes, tendría que escribir **100** en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-191">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="3aa1e-192">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-192">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3aa1e-193">En el Centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Suscripciones</a>.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-193">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="3aa1e-194">En la **página Suscripciones,** **seleccione Complementos.**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-194">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="3aa1e-196">Si no ve complementos y la suscripción se compró a través de un partner, seleccione Centro de servicios de licencias por **volumen (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-196">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="3aa1e-197">En Almacenamiento adicional de archivos de **Office 365,** seleccione **Cambiar cantidad.**</span><span class="sxs-lookup"><span data-stu-id="3aa1e-197">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Cambiar vínculo Cantidad.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="3aa1e-199">En el panel derecho, escriba el número total de gigabytes que necesita y, a continuación, **seleccione Enviar**.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-199">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="3aa1e-200">Por ejemplo, si actualmente tiene 200 gigabytes de almacenamiento adicional de archivos pero solo necesita 100 gigabytes, tendría que escribir **100** en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-200">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="3aa1e-201">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-201">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="3aa1e-202">¿Mi plan me permite optar a Office 365 Extra File Storage?</span><span class="sxs-lookup"><span data-stu-id="3aa1e-202">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="3aa1e-203">Office 365 Extra File Storage está disponible para las siguientes suscripciones:</span><span class="sxs-lookup"><span data-stu-id="3aa1e-203">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="3aa1e-204">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="3aa1e-204">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="3aa1e-205">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="3aa1e-205">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="3aa1e-206">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="3aa1e-206">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="3aa1e-207">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="3aa1e-207">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="3aa1e-208">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="3aa1e-208">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="3aa1e-209">Office para la web con SharePoint Plan 1</span><span class="sxs-lookup"><span data-stu-id="3aa1e-209">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="3aa1e-210">Office para la web con SharePoint Plan 2</span><span class="sxs-lookup"><span data-stu-id="3aa1e-210">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="3aa1e-211">SharePoint Online Plan 1</span><span class="sxs-lookup"><span data-stu-id="3aa1e-211">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="3aa1e-212">SharePoint Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="3aa1e-212">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="3aa1e-213">Microsoft 365 Empresa Básico</span><span class="sxs-lookup"><span data-stu-id="3aa1e-213">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="3aa1e-214">Microsoft 365 Empresa Estándar</span><span class="sxs-lookup"><span data-stu-id="3aa1e-214">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="3aa1e-215">Microsoft 365 Empresa Premium</span><span class="sxs-lookup"><span data-stu-id="3aa1e-215">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="3aa1e-216">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="3aa1e-216">Microsoft 365 E3</span></span>

- <span data-ttu-id="3aa1e-217">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3aa1e-217">Microsoft 365 E5</span></span>

- <span data-ttu-id="3aa1e-218">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="3aa1e-218">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="3aa1e-219">El almacenamiento adicional de archivos de Office 365 también está disponible para los planes GCC, GCC High y DOD.</span><span class="sxs-lookup"><span data-stu-id="3aa1e-219">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="3aa1e-220">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="3aa1e-220">Related content</span></span>

<span data-ttu-id="3aa1e-221">[Administrar los límites de almacenamiento del](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) sitio (artículo)</span><span class="sxs-lookup"><span data-stu-id="3aa1e-221">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="3aa1e-222">[Establecer el espacio de almacenamiento predeterminado para los usuarios de OneDrive](https://docs.microsoft.com/onedrive/set-default-storage-space)(artículo)</span><span class="sxs-lookup"><span data-stu-id="3aa1e-222">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>
