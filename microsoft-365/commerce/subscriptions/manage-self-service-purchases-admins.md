---
title: Administración de las compras sin servicio (administradores)
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
search.appverid:
- MET150
description: Los administradores pueden aprender a administrar las compras de autoservicio realizadas por los usuarios de su organización.
ms.openlocfilehash: 4cd59bc10d6a6a856932c8bd94e67469217c1313
ms.sourcegitcommit: 3c296126ba69a32af07e339f2f1eacdd8e5b878e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "41120238"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="28173-103">Administración de compras sin servicio (administración)</span><span class="sxs-lookup"><span data-stu-id="28173-103">Manage self-service purchases (Admin)</span></span>

<span data-ttu-id="28173-104">Como administrador, puede ver las compras de autoservicio realizadas por las personas de su organización.</span><span class="sxs-lookup"><span data-stu-id="28173-104">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="28173-105">Puede ver el producto, el nombre del comprador, las suscripciones adquiridas, la fecha de expiración, el precio de compra y los usuarios asignados para cada compra de servicio autónomo.</span><span class="sxs-lookup"><span data-stu-id="28173-105">You can see the product, purchaser name, subscriptions purchased, expiry date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="28173-106">Si es necesario para su organización, puede desactivar las compras de autoservicio por producto a través de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28173-106">If required for your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="28173-107">Tiene las mismas directivas de administración y acceso de datos que los productos adquiridos a través de la compra de autoservicio o de forma centralizada.</span><span class="sxs-lookup"><span data-stu-id="28173-107">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="28173-108">También puede controlar si los usuarios de la organización pueden realizar compras sin servicio de asistencia.</span><span class="sxs-lookup"><span data-stu-id="28173-108">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="28173-109">Para obtener más información, vea [usar AllowSelfServicePurchase para el módulo de PowerShell de MSCommerce](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="28173-109">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="28173-110">Ver suscripciones de autoservicio</span><span class="sxs-lookup"><span data-stu-id="28173-110">View self-service subscriptions</span></span>

1. <span data-ttu-id="28173-111">En el centro de administración, vaya a la página productos de **facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">& Services</a> .</span><span class="sxs-lookup"><span data-stu-id="28173-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="28173-112">Junto a **refinar resultados**, en la lista desplegable **tipo de cuenta** , elija **Self-Service**.</span><span class="sxs-lookup"><span data-stu-id="28173-112">Next to **Refine results**, from the **Account type** drop-down, choose **Self-service**.</span></span>

3. <span data-ttu-id="28173-113">Para ver más detalles sobre una suscripción, seleccione una de la lista.</span><span class="sxs-lookup"><span data-stu-id="28173-113">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="28173-114">Ver quién tiene licencias para una suscripción de compra de autoservicio</span><span class="sxs-lookup"><span data-stu-id="28173-114">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="28173-115">En el centro de administración, vaya a la página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licencias</a> de **facturación** > .</span><span class="sxs-lookup"><span data-stu-id="28173-115">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

2. <span data-ttu-id="28173-116">Elija el icono filtrar y, a continuación, elija **autoservicio**.</span><span class="sxs-lookup"><span data-stu-id="28173-116">Choose the filter icon, then choose **Self-service**.</span></span>

3. <span data-ttu-id="28173-117">Seleccione un producto para ver las licencias asignadas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="28173-117">Select a product to see licenses assigned to people.</span></span>

    > [!NOTE]
    > <span data-ttu-id="28173-118">Si hay varias compras para un producto, dicho producto solo aparece una vez y la columna **cantidad disponible** muestra el total de todas las suscripciones que ha comprado para ese producto.</span><span class="sxs-lookup"><span data-stu-id="28173-118">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>

4. <span data-ttu-id="28173-119">La lista de **usuarios** se agrupa por los nombres de las personas que realizaron compras sin servicio.</span><span class="sxs-lookup"><span data-stu-id="28173-119">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>

5. <span data-ttu-id="28173-120">Para exportar una lista de usuarios con licencias para estas suscripciones, elija las suscripciones que quiere exportar y, después, elija **exportar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="28173-120">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="28173-121">Deshabilitación o habilitación de compras sin servicio</span><span class="sxs-lookup"><span data-stu-id="28173-121">Disable or enable self-service purchases</span></span>

<span data-ttu-id="28173-122">Puede deshabilitar o habilitar las compras de autoservicio para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="28173-122">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="28173-123">El módulo de PowerShell **MSCommerce** incluye un valor de parámetro **PolicyID** para **AllowSelfServicePurchase** que le permite controlar si los usuarios de su organización pueden realizar compras sin servicio y para qué productos.</span><span class="sxs-lookup"><span data-stu-id="28173-123">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="28173-124">Puede usar el módulo de PowerShell **MSCommerce** para:</span><span class="sxs-lookup"><span data-stu-id="28173-124">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="28173-125">Ver el estado predeterminado del valor \*\*\*\* &mdash; del parámetro AllowSelfServicePurchase si está habilitado o deshabilitado por el producto.</span><span class="sxs-lookup"><span data-stu-id="28173-125">View the default state of the **AllowSelfServicePurchase** parameter value &mdash; whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="28173-126">Ver una lista de los productos aplicables y si la compra de servicios automáticos está habilitada o deshabilitada</span><span class="sxs-lookup"><span data-stu-id="28173-126">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="28173-127">Ver o modificar la configuración actual de un producto específico para habilitarlo o deshabilitarlo</span><span class="sxs-lookup"><span data-stu-id="28173-127">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="28173-128">Para obtener más información, vea [usar AllowSelfServicePurchase para el módulo de PowerShell de MSCommerce](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="28173-128">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="28173-129">Centralizar licencias en una sola suscripción</span><span class="sxs-lookup"><span data-stu-id="28173-129">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="28173-130">Puede asignar licencias existentes o comprar suscripciones adicionales a través de acuerdos existentes para usuarios asignados a las compras de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="28173-130">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="28173-131">Después de asignar estas licencias adquiridas de forma centralizada, puede solicitar que los compradores cancelen sus suscripciones existentes.</span><span class="sxs-lookup"><span data-stu-id="28173-131">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="28173-132">Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración</a> con su cuenta de administrador global o de administrador de facturación.</span><span class="sxs-lookup"><span data-stu-id="28173-132">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> with your Global admin or Billing admin account.</span></span>

2. <span data-ttu-id="28173-133">Vaya a la página<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">servicios de compra</a> de **facturación** > .</span><span class="sxs-lookup"><span data-stu-id="28173-133">Go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

3. <span data-ttu-id="28173-134">Busque y seleccione el producto que desea comprar y, después, elija **comprar**.</span><span class="sxs-lookup"><span data-stu-id="28173-134">Find and choose the product that you want to buy, then choose **Buy**.</span></span>

4. <span data-ttu-id="28173-135">Complete los pasos restantes para completar la compra.</span><span class="sxs-lookup"><span data-stu-id="28173-135">Complete the remaining steps to complete your purchase.</span></span>

5. <span data-ttu-id="28173-136">Siga los pasos [que se indican en View of licenses for a Self-Service adquirid subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) para exportar una lista de usuarios a la que hacer referencia en el paso 6.</span><span class="sxs-lookup"><span data-stu-id="28173-136">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in step 6.</span></span>

6. <span data-ttu-id="28173-137">Asigne licencias a todos los usuarios que tengan una licencia en la otra suscripción.</span><span class="sxs-lookup"><span data-stu-id="28173-137">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="28173-138">Para obtener los pasos completos, consulte [asignar licencias a usuarios](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="28173-138">For full steps, see [Assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>

7. <span data-ttu-id="28173-139">Póngase en contacto con la persona que compró la suscripción de compra de autoservicio y pídale que la cancele.</span><span class="sxs-lookup"><span data-stu-id="28173-139">Contact the person who bought the self-service purchase subscription and ask them to cancel it.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="28173-140">¿Necesita ayuda?</span><span class="sxs-lookup"><span data-stu-id="28173-140">Need help?</span></span> <span data-ttu-id="28173-141">Póngase en contacto con nosotros.</span><span class="sxs-lookup"><span data-stu-id="28173-141">Contact us.</span></span>

<span data-ttu-id="28173-142">Para obtener preguntas comunes sobre las compras de autoservicio, consulte [preguntas más frecuentes](self-service-purchase-faq.md)sobre las compras sin ayuda.</span><span class="sxs-lookup"><span data-stu-id="28173-142">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="28173-143">Si tiene alguna pregunta o necesita ayuda con las compras de servicios de autoservicio, [póngase en contacto con el soporte técnico](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="28173-143">If you have questions or need help with self-service purchases, [contact support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>