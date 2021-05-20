---
title: Agregue espacio de almacenamiento para su suscripción
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
description: Agregue almacenamiento de archivos en la suscripción Microsoft 365. Con el almacenamiento de archivos adicional, puede almacenar más contenido en SharePoint en línea y OneDrive.
ms.date: 04/02/2021
ms.openlocfilehash: b573205c7053aba0339d1f32deb2996ef80f8754
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572326"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="98c59-104">Agregue espacio de almacenamiento para su suscripción</span><span class="sxs-lookup"><span data-stu-id="98c59-104">Add storage space for your subscription</span></span>

<span data-ttu-id="98c59-105">Si empieza a quedarse sin espacio de almacenamiento en las colecciones de sitios de SharePoint Online, puede aumentar el almacenamiento de su suscripción si su plan cumple con los requisitos.</span><span class="sxs-lookup"><span data-stu-id="98c59-105">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="98c59-106">Si no ves el **Office 365 Extra File Storage** en la lista de complementos disponibles, significa que tu plan no es elegible.</span><span class="sxs-lookup"><span data-stu-id="98c59-106">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="98c59-107">Para obtener más información, consulte [¿Es mi plan elegible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="98c59-107">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="98c59-108">Si compraste tu suscripción a través de licencias por volumen o un CSP, no puedes comprar **Office 365 Extra File Storage** para tu organización directamente en Microsoft.</span><span class="sxs-lookup"><span data-stu-id="98c59-108">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="98c59-109">Póngase en contacto con su representante o socio para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="98c59-109">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="98c59-110">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="98c59-110">Before you begin</span></span>

<span data-ttu-id="98c59-111">Debe ser un administrador global o SharePoint para realizar las tareas de este artículo.</span><span class="sxs-lookup"><span data-stu-id="98c59-111">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="98c59-112">Para más información, vea [Sobre los roles de administrador](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="98c59-112">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="98c59-113">Ver el almacenamiento disponible</span><span class="sxs-lookup"><span data-stu-id="98c59-113">View available storage</span></span>

1. <span data-ttu-id="98c59-114">En el Centro de administración de SharePoint, vaya a la página <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Sitios activos</a> e inicie sesión con una cuenta que tenga permisos [de administrador](/sharepoint/sharepoint-admin-role) para su organización.</span><span class="sxs-lookup"><span data-stu-id="98c59-114">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="98c59-115">En la esquina superior derecha de la página, puede ver la cantidad de almacenamiento empleado en todos los sitios, así como el almacenamiento total de su suscripción.</span><span class="sxs-lookup"><span data-stu-id="98c59-115">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="98c59-116">Si su organización ha configurado Multi-Geo en Office 365, la barra también muestra la cantidad de almacenamiento utilizado en todas las ubicaciones geográficas.</span><span class="sxs-lookup"><span data-stu-id="98c59-116">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Barra de almacenamiento en la página de Sitios activos](/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="98c59-118">El almacenamiento usado no incluye cambios realizados en las últimas 24-48 horas.</span><span class="sxs-lookup"><span data-stu-id="98c59-118">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="98c59-119">Después de determinar la cantidad de almacenamiento que está utilizando, puede agregar o quitar espacio de almacenamiento para su suscripción.</span><span class="sxs-lookup"><span data-stu-id="98c59-119">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="98c59-120">Para averiguar cuánto costará agregar espacio de almacenamiento, siga los pasos de este artículo y revise la información de precios antes de comprar más.</span><span class="sxs-lookup"><span data-stu-id="98c59-120">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="98c59-121">Para obtener información acerca de cómo establecer límites de almacenamiento de recopilación de sitios, vea [Administrar límites de almacenamiento de recopilación de sitios.](/sharepoint/manage-site-collection-storage-limits)</span><span class="sxs-lookup"><span data-stu-id="98c59-121">For information about setting site collection storage limits, see [Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="98c59-122">Agregue almacenamiento a su suscripción</span><span class="sxs-lookup"><span data-stu-id="98c59-122">Add storage to your subscription</span></span>

<span data-ttu-id="98c59-123">Si aún no has comprado almacenamiento adicional para tu suscripción, puedes hacerlo.</span><span class="sxs-lookup"><span data-stu-id="98c59-123">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="98c59-124">En el centro de  administración, vaya a la página \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Servicios de compra de</a> facturación.</span><span class="sxs-lookup"><span data-stu-id="98c59-124">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="98c59-125">En la parte inferior de la página Servicios de **compra,** en la sección **Complementos,** busque **Office 365 Extra File Storage** y seleccione **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="98c59-125">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="98c59-126">En la página detalles del producto, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="98c59-126">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="98c59-127">Si es necesario, elija la suscripción base y, a continuación, escriba el número de gigabytes de almacenamiento que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="98c59-127">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="98c59-128">Seleccione **Despropro salida ahora**.</span><span class="sxs-lookup"><span data-stu-id="98c59-128">Select **Check out now**.</span></span>
6. <span data-ttu-id="98c59-129">En la página **¿Cómo se ve esto?,** compruebe el número de gigabytes de almacenamiento que seleccionó, revise la información de precios y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="98c59-129">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="98c59-130">En la página **Pedido completo,** compruebe el total.</span><span class="sxs-lookup"><span data-stu-id="98c59-130">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="98c59-131">Si necesita realizar algún cambio, seleccione **Editar orden**.</span><span class="sxs-lookup"><span data-stu-id="98c59-131">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="98c59-132">Si el pedido requiere una verificación de crédito, active la casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="98c59-132">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="98c59-133">Cuando haya terminado, seleccione **Realizar orden** Vaya a \> **Admin Home**.</span><span class="sxs-lookup"><span data-stu-id="98c59-133">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="98c59-134">Aumentar o disminuir el almacenamiento</span><span class="sxs-lookup"><span data-stu-id="98c59-134">Increase or decrease storage</span></span>

<span data-ttu-id="98c59-135">Si ya ha comprado almacenamiento de archivos adicional a través del complemento **Office 365 Extra File Storage,** puede usar estos pasos para aumentar o disminuir el espacio de almacenamiento adicional para su suscripción.</span><span class="sxs-lookup"><span data-stu-id="98c59-135">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="98c59-136">Puede reducir el almacenamiento a tan solo 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="98c59-136">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="98c59-137">Para eliminar todo el espacio de almacenamiento adicional, [póngase en contacto con el soporte técnico](../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="98c59-137">To remove all of the extra storage space, [contact support](../business-video/get-help-support.md).</span></span>

1. <span data-ttu-id="98c59-138">En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.</span><span class="sxs-lookup"><span data-stu-id="98c59-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="98c59-139">En la pestaña **Productos,** seleccione la suscripción que contiene el **complemento Office 365 Extra File Storage.**</span><span class="sxs-lookup"><span data-stu-id="98c59-139">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="98c59-140">En la página detalles del producto, en la sección **Complementos,** seleccione **Administrar complementos**.</span><span class="sxs-lookup"><span data-stu-id="98c59-140">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="98c59-141">En el panel **Administrar complementos,** en la lista **Complemento,** elija **Office 365 Extra File Storage**.</span><span class="sxs-lookup"><span data-stu-id="98c59-141">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="98c59-142">En el cuadro de texto **Cantidad,** especifique el número de GB de espacio de almacenamiento que desee para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="98c59-142">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="98c59-143">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="98c59-143">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="98c59-144">¿Mi plan me permite optar a Office 365 Extra File Storage?</span><span class="sxs-lookup"><span data-stu-id="98c59-144">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="98c59-145">Office 365 Extra File Storage está disponible para las siguientes suscripciones:</span><span class="sxs-lookup"><span data-stu-id="98c59-145">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="98c59-146">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="98c59-146">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="98c59-147">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="98c59-147">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="98c59-148">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="98c59-148">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="98c59-149">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="98c59-149">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="98c59-150">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="98c59-150">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="98c59-151">Office para la web con SharePoint Plan 1</span><span class="sxs-lookup"><span data-stu-id="98c59-151">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="98c59-152">Office para la web con SharePoint Plan 2</span><span class="sxs-lookup"><span data-stu-id="98c59-152">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="98c59-153">SharePoint Online Plan 1</span><span class="sxs-lookup"><span data-stu-id="98c59-153">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="98c59-154">SharePoint Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="98c59-154">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="98c59-155">Microsoft 365 Empresa Básico</span><span class="sxs-lookup"><span data-stu-id="98c59-155">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="98c59-156">Microsoft 365 Empresa Estándar</span><span class="sxs-lookup"><span data-stu-id="98c59-156">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="98c59-157">Microsoft 365 Empresa Premium</span><span class="sxs-lookup"><span data-stu-id="98c59-157">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="98c59-158">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="98c59-158">Microsoft 365 E3</span></span>
- <span data-ttu-id="98c59-159">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="98c59-159">Microsoft 365 E5</span></span>
- <span data-ttu-id="98c59-160">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="98c59-160">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="98c59-161">Office 365 Extra File Storage también está disponible para planes de GCC, GCC High y DOD.</span><span class="sxs-lookup"><span data-stu-id="98c59-161">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="98c59-162">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="98c59-162">Related content</span></span>

<span data-ttu-id="98c59-163">[Administrar los límites de almacenamiento del sitio](/sharepoint/manage-site-collection-storage-limits) (artículo)</span><span class="sxs-lookup"><span data-stu-id="98c59-163">[Manage site storage limits](/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="98c59-164">[Establezca el espacio de almacenamiento predeterminado para los usuarios de OneDrive](/onedrive/set-default-storage-space)(artículo)</span><span class="sxs-lookup"><span data-stu-id="98c59-164">[Set the default storage space for OneDrive users](/onedrive/set-default-storage-space)(article)</span></span>
