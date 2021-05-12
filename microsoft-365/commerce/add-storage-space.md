---
title: Agregar espacio de almacenamiento para la suscripción
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: drjones, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
- commerce_purchase
search.appverid: MET150
description: Aprenda a agregar y reducir el almacenamiento de archivos en su Microsoft 365 suscripción. Con el almacenamiento de archivos adicional, puede almacenar más contenido en SharePoint Online y OneDrive.
ms.date: 04/02/2021
ms.openlocfilehash: 98fdb4412f263bd9e0a22b6890ff66509cb3e799
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332191"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="a7182-104">Agregar espacio de almacenamiento para la suscripción</span><span class="sxs-lookup"><span data-stu-id="a7182-104">Add storage space for your subscription</span></span>

<span data-ttu-id="a7182-105">Si empieza a quedarse sin espacio de almacenamiento en las colecciones de sitios de SharePoint Online, puede aumentar el almacenamiento de su suscripción si su plan cumple con los requisitos.</span><span class="sxs-lookup"><span data-stu-id="a7182-105">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="a7182-106">Si no ve el Office 365 Extra File Storage **en** la lista de complementos disponibles, significa que su plan no es apto.</span><span class="sxs-lookup"><span data-stu-id="a7182-106">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="a7182-107">Para obtener más información, vea [¿Mi plan es apto?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="a7182-107">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="a7182-108">Si compró la suscripción a través de licencias  por volumen o un CSP, no puede comprar Office 365 Extra File Storage para su organización directamente a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a7182-108">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="a7182-109">Póngase en contacto con su representante o partner para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="a7182-109">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a7182-110">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="a7182-110">Before you begin</span></span>

<span data-ttu-id="a7182-111">Debe ser un administrador global o SharePoint para realizar las tareas de este artículo.</span><span class="sxs-lookup"><span data-stu-id="a7182-111">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="a7182-112">Para más información, vea [Sobre los roles de administrador](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a7182-112">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="a7182-113">Ver almacenamiento disponible</span><span class="sxs-lookup"><span data-stu-id="a7182-113">View available storage</span></span>

1. <span data-ttu-id="a7182-114">En el SharePoint de administración, vaya a la <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">página Sitios</a> activos e inicie sesión con una cuenta que tenga permisos de administrador [para](/sharepoint/sharepoint-admin-role) su organización.</span><span class="sxs-lookup"><span data-stu-id="a7182-114">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="a7182-115">En la esquina superior derecha de la página, puede ver la cantidad de almacenamiento empleado en todos los sitios, así como el almacenamiento total de su suscripción.</span><span class="sxs-lookup"><span data-stu-id="a7182-115">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="a7182-116">Si su organización ha configurado Multi-Geo en Office 365, la barra también muestra la cantidad de almacenamiento usada en todas las ubicaciones geográficas.</span><span class="sxs-lookup"><span data-stu-id="a7182-116">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Barra de almacenamiento en la página de Sitios activos](/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="a7182-118">El almacenamiento usado no incluye cambios realizados en las últimas 24-48 horas.</span><span class="sxs-lookup"><span data-stu-id="a7182-118">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="a7182-119">Después de determinar cuánto almacenamiento está usando, puede agregar o quitar espacio de almacenamiento para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="a7182-119">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="a7182-120">Para averiguar cuánto costará agregar espacio de almacenamiento, siga los pasos de este artículo y revise la información de precios antes de comprar más.</span><span class="sxs-lookup"><span data-stu-id="a7182-120">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="a7182-121">Para obtener información sobre cómo establecer límites de almacenamiento de colecciones de [sitios,](/sharepoint/manage-site-collection-storage-limits)vea Manage site collection storage limits .</span><span class="sxs-lookup"><span data-stu-id="a7182-121">For information about setting site collection storage limits, see [Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="a7182-122">Agregar almacenamiento a la suscripción</span><span class="sxs-lookup"><span data-stu-id="a7182-122">Add storage to your subscription</span></span>

<span data-ttu-id="a7182-123">Si aún no has comprado almacenamiento adicional para la suscripción, puedes hacerlo.</span><span class="sxs-lookup"><span data-stu-id="a7182-123">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="a7182-124">En el Centro de administración, vaya a la página **Servicios de compra** de \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">facturación.</a></span><span class="sxs-lookup"><span data-stu-id="a7182-124">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="a7182-125">En la parte inferior de la  **página Servicios** de compra, en la sección Complementos, busque Office 365 Extra File Storage **y** seleccione **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="a7182-125">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="a7182-126">En la página de detalles del producto, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a7182-126">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="a7182-127">Si es necesario, elija la suscripción base y, a continuación, escriba el número de gigabytes de almacenamiento que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="a7182-127">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="a7182-128">Seleccione **Des check-out now**.</span><span class="sxs-lookup"><span data-stu-id="a7182-128">Select **Check out now**.</span></span>
6. <span data-ttu-id="a7182-129">En la **página ¿Cómo se ve esto?,** compruebe el número de gigabytes de almacenamiento que seleccionó, revise la información de precios y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a7182-129">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="a7182-130">En la **página Completar pedido,** compruebe el total.</span><span class="sxs-lookup"><span data-stu-id="a7182-130">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="a7182-131">Si necesita realizar cambios, seleccione **Editar orden**.</span><span class="sxs-lookup"><span data-stu-id="a7182-131">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="a7182-132">Si el pedido requiere una comprobación de crédito, active la casilla.</span><span class="sxs-lookup"><span data-stu-id="a7182-132">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="a7182-133">Cuando haya terminado, seleccione **Realizar pedido** Vaya a Inicio \> **de administración.**</span><span class="sxs-lookup"><span data-stu-id="a7182-133">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="a7182-134">Aumentar o disminuir el almacenamiento</span><span class="sxs-lookup"><span data-stu-id="a7182-134">Increase or decrease storage</span></span>

<span data-ttu-id="a7182-135">Si ya compró almacenamiento de archivos adicional a través del complemento **Office 365 Extra File Storage,** puede usar estos pasos para aumentar o disminuir el espacio de almacenamiento adicional para su suscripción.</span><span class="sxs-lookup"><span data-stu-id="a7182-135">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="a7182-136">Puede reducir el almacenamiento hasta 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="a7182-136">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="a7182-137">Para quitar todo el espacio de almacenamiento adicional, póngase [en contacto con el soporte técnico](../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="a7182-137">To remove all of the extra storage space, [contact support](../business-video/get-help-support.md).</span></span>

1. <span data-ttu-id="a7182-138">En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.</span><span class="sxs-lookup"><span data-stu-id="a7182-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="a7182-139">En la **pestaña** Productos, seleccione la suscripción que contiene **el Office 365 Extra File Storage** complemento.</span><span class="sxs-lookup"><span data-stu-id="a7182-139">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="a7182-140">En la página detalles del producto, en la **sección Complementos,** seleccione **Administrar complementos**.</span><span class="sxs-lookup"><span data-stu-id="a7182-140">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="a7182-141">En el **panel Administrar complementos,** en la **lista Complementos,** elija **Office 365 Extra File Storage**.</span><span class="sxs-lookup"><span data-stu-id="a7182-141">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="a7182-142">En el **cuadro de texto** Cantidad, escriba el número de GB de espacio de almacenamiento que desea para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="a7182-142">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="a7182-143">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a7182-143">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="a7182-144">¿Mi plan me permite optar a Office 365 Extra File Storage?</span><span class="sxs-lookup"><span data-stu-id="a7182-144">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="a7182-145">Office 365 Extra File Storage está disponible para las siguientes suscripciones:</span><span class="sxs-lookup"><span data-stu-id="a7182-145">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="a7182-146">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="a7182-146">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="a7182-147">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="a7182-147">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="a7182-148">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="a7182-148">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="a7182-149">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="a7182-149">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="a7182-150">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="a7182-150">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="a7182-151">Office web con SharePoint plan 1</span><span class="sxs-lookup"><span data-stu-id="a7182-151">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="a7182-152">Office web con SharePoint plan 2</span><span class="sxs-lookup"><span data-stu-id="a7182-152">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="a7182-153">SharePoint Online Plan 1</span><span class="sxs-lookup"><span data-stu-id="a7182-153">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="a7182-154">SharePoint Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="a7182-154">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="a7182-155">Microsoft 365 Empresa Básico</span><span class="sxs-lookup"><span data-stu-id="a7182-155">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="a7182-156">Microsoft 365 Empresa Estándar</span><span class="sxs-lookup"><span data-stu-id="a7182-156">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="a7182-157">Microsoft 365 Empresa Premium</span><span class="sxs-lookup"><span data-stu-id="a7182-157">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="a7182-158">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="a7182-158">Microsoft 365 E3</span></span>
- <span data-ttu-id="a7182-159">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="a7182-159">Microsoft 365 E5</span></span>
- <span data-ttu-id="a7182-160">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="a7182-160">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="a7182-161">Office 365 Extra File Storage también está disponible para planes GCC, GCC High y DOD.</span><span class="sxs-lookup"><span data-stu-id="a7182-161">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="a7182-162">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="a7182-162">Related content</span></span>

<span data-ttu-id="a7182-163">[Administrar límites de almacenamiento de sitios](/sharepoint/manage-site-collection-storage-limits) (artículo)</span><span class="sxs-lookup"><span data-stu-id="a7182-163">[Manage site storage limits](/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="a7182-164">[Establecer el espacio de almacenamiento predeterminado para OneDrive usuarios](/onedrive/set-default-storage-space)(artículo)</span><span class="sxs-lookup"><span data-stu-id="a7182-164">[Set the default storage space for OneDrive users](/onedrive/set-default-storage-space)(article)</span></span>
