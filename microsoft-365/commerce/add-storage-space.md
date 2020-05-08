---
title: Agregar espacio de almacenamiento para la suscripción
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEU150
- GEA150
- GSP150
ms.assetid: 96ea3533-de64-4b01-839a-c560875a662c
description: Obtenga información sobre cómo agregar y reducir el almacenamiento de archivos en su suscripción de Microsoft 365. Con el almacenamiento de archivos adicionales, puede almacenar más contenido en SharePoint Online y OneDrive.
ms.openlocfilehash: 921fd4a232d288971150a3379b138613f009f9dc
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140971"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="b8671-104">Agregar espacio de almacenamiento para la suscripción</span><span class="sxs-lookup"><span data-stu-id="b8671-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b8671-105">El centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="b8671-105">The admin center is changing.</span></span> <span data-ttu-id="b8671-106">Si su experiencia no coincide con los detalles que se presentan aquí, vea [acerca del nuevo centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="b8671-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="b8671-107">Si empieza a quedarse sin espacio de almacenamiento en las colecciones de sitios de SharePoint Online, puede aumentar el almacenamiento de su suscripción si su plan cumple con los requisitos.</span><span class="sxs-lookup"><span data-stu-id="b8671-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="b8671-108">Si no ve el **almacenamiento de archivos adicionales de Office 365** en la lista de complementos disponibles, significa que su plan no es elegible.</span><span class="sxs-lookup"><span data-stu-id="b8671-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="b8671-109">Para obtener más información, vea [¿es elegible el plan?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="b8671-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="b8671-110">Ver el almacenamiento disponible</span><span class="sxs-lookup"><span data-stu-id="b8671-110">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b8671-111">Vaya a la página [Sitios activos del nuevo Centro de administración de SharePoint](https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true) e inicie sesión con una cuenta que tenga [permisos de administrador](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) para su organización.</span><span class="sxs-lookup"><span data-stu-id="b8671-111">Go to the [Active sites page of the new SharePoint admin center](https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true), and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="b8671-112">En la parte superior derecha de la página, vea la cantidad de almacenamiento usado en todos los sitios y el almacenamiento total de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="b8671-112">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="b8671-113">(Si su organización ha configurado multigeográfico en Office 365, la barra también muestra la cantidad de almacenamiento que se usa en todas las ubicaciones geográficas).</span><span class="sxs-lookup"><span data-stu-id="b8671-113">(If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.)</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b8671-114">Inicie sesión en https://portal.office.de como administrador global o de SharePoint y, a continuación, seleccione el icono administrador para abrir el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="b8671-114">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="b8671-115">(Si ve un mensaje que indica que no tiene permiso para obtener acceso a la página, no tiene permisos de administrador de Microsoft 365 en su organización).</span><span class="sxs-lookup"><span data-stu-id="b8671-115">(If you see a message that you don't have permission to access the page, you don't have Microsoft 365 administrator permissions in your organization.)</span></span>

2. <span data-ttu-id="b8671-116">En el panel izquierdo, en **centros de administración**, seleccione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="b8671-116">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="b8671-117">Si se muestra el Centro de administración de SharePoint clásico, seleccione **Abrirlo ahora** en la parte superior de la página para abrir el nuevo Centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b8671-117">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="b8671-118">En el panel izquierdo del nuevo Centro de administración de SharePoint, seleccione **Sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="b8671-118">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="b8671-119">En la parte superior derecha de la página, vea la cantidad de almacenamiento usado en todos los sitios y el almacenamiento total de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="b8671-119">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b8671-120">Inicie sesión en https://login.partner.microsoftonline.cn/ como administrador global o de SharePoint y, a continuación, seleccione el icono administrador para abrir el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="b8671-120">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="b8671-121">(Si ve un mensaje que indica que no tiene permiso para obtener acceso a la página, no tiene permisos de administrador de Microsoft 365 en su organización).</span><span class="sxs-lookup"><span data-stu-id="b8671-121">(If you see a message that you don't have permission to access the page, you don't have Microsoft 365 administrator permissions in your organization.)</span></span>

2. <span data-ttu-id="b8671-122">En el panel izquierdo, en **centros de administración**, seleccione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="b8671-122">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="b8671-123">Si se muestra el Centro de administración de SharePoint clásico, seleccione **Abrirlo ahora** en la parte superior de la página para abrir el nuevo Centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b8671-123">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="b8671-124">En el panel izquierdo del nuevo Centro de administración de SharePoint, seleccione **Sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="b8671-124">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="b8671-125">En la parte superior derecha de la página, vea la cantidad de almacenamiento usado en todos los sitios y el almacenamiento total de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="b8671-125">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

::: moniker-end

![Barra de almacenamiento en la página sitios activos](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

> [!NOTE]
> <span data-ttu-id="b8671-127">El almacenamiento usado no incluye los cambios realizados en las últimas 24-48 horas.</span><span class="sxs-lookup"><span data-stu-id="b8671-127">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="b8671-128">Una vez que haya determinado cuánto espacio de almacenamiento está usando, puede agregar o quitar espacio de almacenamiento para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="b8671-128">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="b8671-129">Para averiguar cuánto costará agregar espacio de almacenamiento, siga los pasos descritos en este artículo y revise la información sobre precios antes de comprar.</span><span class="sxs-lookup"><span data-stu-id="b8671-129">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="b8671-130">Para obtener información sobre cómo establecer los límites de almacenamiento de la colección de sitios, vea [Manage site Collection Storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span><span class="sxs-lookup"><span data-stu-id="b8671-130">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="b8671-131">Agregar almacenamiento a su suscripción</span><span class="sxs-lookup"><span data-stu-id="b8671-131">Add storage to your subscription</span></span>

<span data-ttu-id="b8671-132">Si aún no ha adquirido almacenamiento extra para su suscripción, puede hacerlo.</span><span class="sxs-lookup"><span data-stu-id="b8671-132">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b8671-133">En el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">servicios de compra</a> de **facturación** \> .</span><span class="sxs-lookup"><span data-stu-id="b8671-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

2. <span data-ttu-id="b8671-134">En la parte inferior de la página **servicios de compra** , seleccione **Complementos**.</span><span class="sxs-lookup"><span data-stu-id="b8671-134">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>

3. <span data-ttu-id="b8671-135">Seleccione **Office 365 extra File Storage**.</span><span class="sxs-lookup"><span data-stu-id="b8671-135">Select **Office 365 Extra File Storage**.</span></span>

4. <span data-ttu-id="b8671-136">En la página **almacenamiento de archivos adicionales de Office 365** , si se muestra, elija la suscripción base y, a continuación, escriba el número de gigabytes de almacenamiento que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="b8671-136">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>

5. <span data-ttu-id="b8671-137">Seleccione **Desproteger ahora**.</span><span class="sxs-lookup"><span data-stu-id="b8671-137">Select **Check out now**.</span></span>

6. <span data-ttu-id="b8671-138">En la página **¿qué aspecto?** , compruebe el número de gigabytes de almacenamiento que ha seleccionado, revise la información de precios y, después, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b8671-138">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="b8671-139">En la página **completar pedido** , compruebe el total.</span><span class="sxs-lookup"><span data-stu-id="b8671-139">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="b8671-140">Si necesita realizar cambios, seleccione **Editar pedido**.</span><span class="sxs-lookup"><span data-stu-id="b8671-140">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="b8671-141">Si el pedido requiere una comprobación de crédito, active la casilla.</span><span class="sxs-lookup"><span data-stu-id="b8671-141">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="b8671-142">Cuando haya terminado, seleccione **realizar pedido** \> **ir a la Página principal de administración**.</span><span class="sxs-lookup"><span data-stu-id="b8671-142">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b8671-143">En el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">suscripciones</a> de **facturación** \>.  </span><span class="sxs-lookup"><span data-stu-id="b8671-143">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="b8671-144">En la página **suscripciones** , elija la suscripción a la que desea agregar espacio de almacenamiento y, a continuación, seleccione **Complementos**.</span><span class="sxs-lookup"><span data-stu-id="b8671-144">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="b8671-146">Si no ve **Complementos**y la suscripción se compró a través de un partner, seleccione **centro de servicios de licencias por volumen (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="b8671-146">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="b8671-147">Seleccione **Buy add-ons**.</span><span class="sxs-lookup"><span data-stu-id="b8671-147">Select **Buy add-ons**.</span></span>

    ![Vínculo comprar complementos en la página suscripciones del centro de administración.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="b8671-149">En la página **servicios de compra** , pase el mouse por el servicio de **almacenamiento extra de archivos de Office 365**y seleccione **comprar ahora**.</span><span class="sxs-lookup"><span data-stu-id="b8671-149">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="b8671-150">Escriba el número de licencias de usuario que necesita y, si se muestra, elija una suscripción base.</span><span class="sxs-lookup"><span data-stu-id="b8671-150">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="b8671-151">Seleccione **Desproteger ahora**.</span><span class="sxs-lookup"><span data-stu-id="b8671-151">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="b8671-152">En la página **¿qué aspecto?** , compruebe el número de gigabytes de almacenamiento que ha seleccionado, revise la información de precios y, después, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b8671-152">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="b8671-153">En la página **completar pedido** , seleccione **realizar pedido**.</span><span class="sxs-lookup"><span data-stu-id="b8671-153">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b8671-154">En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Suscripciones</a>.</span><span class="sxs-lookup"><span data-stu-id="b8671-154">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="b8671-155">En la página **suscripciones** , elija la suscripción a la que desea agregar espacio de almacenamiento y, a continuación, seleccione **Complementos**.</span><span class="sxs-lookup"><span data-stu-id="b8671-155">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="b8671-157">Si no ve **Complementos**y la suscripción se compró a través de un partner, seleccione **centro de servicios de licencias por volumen (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="b8671-157">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="b8671-158">Seleccione **Buy add-ons**.</span><span class="sxs-lookup"><span data-stu-id="b8671-158">Select **Buy add-ons**.</span></span>

    ![Vínculo comprar complementos en la página suscripciones del centro de administración.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="b8671-160">En la página **servicios de compra** , pase el mouse por el servicio de **almacenamiento extra de archivos de Office 365**y seleccione **comprar ahora**.</span><span class="sxs-lookup"><span data-stu-id="b8671-160">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="b8671-161">Escriba el número de licencias de usuario que necesita y, si se muestra, elija una suscripción base.</span><span class="sxs-lookup"><span data-stu-id="b8671-161">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="b8671-162">Seleccione **Desproteger ahora**.</span><span class="sxs-lookup"><span data-stu-id="b8671-162">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="b8671-163">En la página **¿qué aspecto?** , compruebe el número de gigabytes de almacenamiento que ha seleccionado, revise la información de precios y, después, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b8671-163">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="b8671-164">En la página **completar pedido** , seleccione **realizar pedido**.</span><span class="sxs-lookup"><span data-stu-id="b8671-164">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="b8671-165">Aumentar o disminuir el almacenamiento</span><span class="sxs-lookup"><span data-stu-id="b8671-165">Increase or decrease storage</span></span>

<span data-ttu-id="b8671-166">Si ya ha comprado almacenamiento de archivos extra mediante el complemento de **almacenamiento de archivos adicionales de Office 365** , puede usar estos pasos para aumentar o disminuir el espacio de almacenamiento adicional de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="b8671-166">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="b8671-167">Puede reducir el almacenamiento a un mínimo de 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="b8671-167">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="b8671-168">Para quitar todo el espacio de almacenamiento adicional, debe ponerse en [contacto con el soporte técnico](../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="b8671-168">To remove all of the extra storage space, you need to [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b8671-169">En el centro de administración, vaya a la página **facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">de productos</a> .</span><span class="sxs-lookup"><span data-stu-id="b8671-169">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="b8671-170">Elija la suscripción que contiene el complemento de **almacenamiento de archivos adicionales de Office 365** .</span><span class="sxs-lookup"><span data-stu-id="b8671-170">Choose the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>

3. <span data-ttu-id="b8671-171">Seleccione **Complementos**y, a continuación, elija **cambiar cantidad**.</span><span class="sxs-lookup"><span data-stu-id="b8671-171">Select **Add-ons**, then choose **Change quantity**.</span></span>

4. <span data-ttu-id="b8671-172">En el panel **Agregar o quitar gigabytes** , escriba el total de gigabytes que desee para la suscripción y, a continuación, seleccione **Enviar cambio**.</span><span class="sxs-lookup"><span data-stu-id="b8671-172">In the **Add/Remove gigabytes** pane, enter the total gigabytes you want for the subscription, then select **Submit change**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b8671-173">En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Suscripciones</a>.</span><span class="sxs-lookup"><span data-stu-id="b8671-173">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="b8671-174">En la página **suscripciones** , seleccione **Complementos**.</span><span class="sxs-lookup"><span data-stu-id="b8671-174">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="b8671-176">Si no ve **Complementos**y la suscripción se compró a través de un partner, seleccione **centro de servicios de licencias por volumen (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="b8671-176">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="b8671-177">En **Office 365 extra File Storage**, seleccione **cambiar cantidad**.</span><span class="sxs-lookup"><span data-stu-id="b8671-177">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Cambiar vínculo Cantidad.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="b8671-179">En el panel derecho, escriba el número total de gigabytes que necesita y, después, seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="b8671-179">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="b8671-180">Por ejemplo, si actualmente tiene 200 gigabytes de almacenamiento adicional de archivos pero solo necesita 100 gigabytes, tendría que escribir **100** en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="b8671-180">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="b8671-181">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b8671-181">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b8671-182">En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Suscripciones</a>.</span><span class="sxs-lookup"><span data-stu-id="b8671-182">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="b8671-183">En la página **suscripciones** , seleccione **Complementos**.</span><span class="sxs-lookup"><span data-stu-id="b8671-183">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="b8671-185">Si no ve **Complementos**y la suscripción se compró a través de un partner, seleccione **centro de servicios de licencias por volumen (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="b8671-185">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="b8671-186">En **Office 365 extra File Storage**, seleccione **cambiar cantidad**.</span><span class="sxs-lookup"><span data-stu-id="b8671-186">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Cambiar vínculo Cantidad.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="b8671-188">En el panel derecho, escriba el número total de gigabytes que necesita y, después, seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="b8671-188">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="b8671-189">Por ejemplo, si actualmente tiene 200 gigabytes de almacenamiento adicional de archivos pero solo necesita 100 gigabytes, tendría que escribir **100** en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="b8671-189">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="b8671-190">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b8671-190">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="b8671-191">¿Mi plan me permite optar a Office 365 Extra File Storage?</span><span class="sxs-lookup"><span data-stu-id="b8671-191">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="b8671-192">Office 365 Extra File Storage está disponible para las siguientes suscripciones:</span><span class="sxs-lookup"><span data-stu-id="b8671-192">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="b8671-193">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="b8671-193">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="b8671-194">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="b8671-194">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="b8671-195">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="b8671-195">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="b8671-196">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="b8671-196">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="b8671-197">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="b8671-197">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="b8671-198">Office para la web con SharePoint plan 1</span><span class="sxs-lookup"><span data-stu-id="b8671-198">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="b8671-199">Office para la web con SharePoint plan 2</span><span class="sxs-lookup"><span data-stu-id="b8671-199">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="b8671-200">SharePoint Online Plan 1</span><span class="sxs-lookup"><span data-stu-id="b8671-200">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="b8671-201">SharePoint Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="b8671-201">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="b8671-202">Microsoft 365 Empresa Básico</span><span class="sxs-lookup"><span data-stu-id="b8671-202">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="b8671-203">Microsoft 365 Empresa Estándar</span><span class="sxs-lookup"><span data-stu-id="b8671-203">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="b8671-204">Microsoft 365 Empresa Premium</span><span class="sxs-lookup"><span data-stu-id="b8671-204">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="b8671-205">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="b8671-205">Microsoft 365 E3</span></span>

- <span data-ttu-id="b8671-206">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b8671-206">Microsoft 365 E5</span></span>

- <span data-ttu-id="b8671-207">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="b8671-207">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="b8671-208">El almacenamiento de archivos adicionales de Office 365 también está disponible para los planes de GCC, GCC High y DOD.</span><span class="sxs-lookup"><span data-stu-id="b8671-208">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>
