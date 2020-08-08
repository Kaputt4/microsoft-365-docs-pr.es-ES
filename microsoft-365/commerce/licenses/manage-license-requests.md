---
title: Administrar solicitudes de licencia
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- commerce
ms.custom: MACBillingLicensesRequests
search.appverid:
- MET150
description: Obtenga información sobre cómo revisar y aprobar o rechazar solicitudes de licencias de los usuarios para su suscripción a Microsoft 365 para empresas.
ms.date: 08/07/2020
ms.openlocfilehash: cbcdc5550d404278832cc702560ac55f6ace8a44
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597663"
---
# <a name="manage-license-requests"></a><span data-ttu-id="4b38b-103">Administrar solicitudes de licencia</span><span class="sxs-lookup"><span data-stu-id="4b38b-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="4b38b-104">La información de este artículo solo se aplica a los productos adquiridos sin servicio de asistencia.</span><span class="sxs-lookup"><span data-stu-id="4b38b-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="4b38b-105">Para obtener más información, consulte [preguntas más frecuentes sobre las compras sin ayuda](../subscriptions/self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="4b38b-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.md).</span></span>

<span data-ttu-id="4b38b-106">Si deshabilita las compras de servicios de autoservicio en su organización, puede usar solicitudes de licencias para administrar el proceso de solicitud de licencias para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4b38b-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="4b38b-107">Cuando un usuario intenta realizar una compra de autoservicio para un producto que ha bloqueado, puede enviar una solicitud de una licencia para usted, el administrador. Cuando realizan una solicitud, pueden agregar los nombres de otros usuarios que también necesitan licencias para el producto.</span><span class="sxs-lookup"><span data-stu-id="4b38b-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="4b38b-108">Si impide que los usuarios realicen compras sin servicio, Microsoft no les envía correos electrónicos de marketing.</span><span class="sxs-lookup"><span data-stu-id="4b38b-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="4b38b-109">Además, si está usando una versión de prueba de un producto, no verán mensajes para comprarla.</span><span class="sxs-lookup"><span data-stu-id="4b38b-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="4b38b-110">Para obtener más información, consulte [Manage Self-Service Purchases (admin)](../subscriptions/manage-self-service-purchases-admins.md).</span><span class="sxs-lookup"><span data-stu-id="4b38b-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="4b38b-111">Para ver y administrar solicitudes de licencia, el administrador usa la pestaña **solicitudes** de la página **licencias** .</span><span class="sxs-lookup"><span data-stu-id="4b38b-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="4b38b-112">La lista muestra el nombre del producto solicitado, el nombre de la persona que solicita una licencia, la fecha solicitada y el estado de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="4b38b-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="4b38b-113">Los administradores pueden filtrar la lista para mostrar las solicitudes pendientes o completadas.</span><span class="sxs-lookup"><span data-stu-id="4b38b-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="4b38b-114">Las solicitudes se conservan durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="4b38b-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4b38b-115">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="4b38b-115">Before you begin</span></span>

<span data-ttu-id="4b38b-116">Debe ser un administrador global para realizar las tareas de este artículo.</span><span class="sxs-lookup"><span data-stu-id="4b38b-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="4b38b-117">Para obtener más información, vea [Asignar roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="4b38b-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="4b38b-118">Usar su propio proceso de solicitud</span><span class="sxs-lookup"><span data-stu-id="4b38b-118">Use your own request process</span></span>

<span data-ttu-id="4b38b-119">Si su organización tiene su propio proceso de solicitud, puede usarlo en su lugar.</span><span class="sxs-lookup"><span data-stu-id="4b38b-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="4b38b-120">Cree un mensaje que se mostrará a los usuarios cuando soliciten una licencia.</span><span class="sxs-lookup"><span data-stu-id="4b38b-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4b38b-121">Si usa su propio proceso de solicitud, no se muestra ninguna solicitud en la pestaña **solicitudes** . las solicitudes existentes desde antes de agregar el mensaje seguirán apareciendo hasta que los apruebe o los rechace.</span><span class="sxs-lookup"><span data-stu-id="4b38b-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="4b38b-122">En el centro de administración, vaya a la página licencias de **facturación**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> y, a continuación, seleccione la pestaña **solicitudes** .</span><span class="sxs-lookup"><span data-stu-id="4b38b-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="4b38b-123">Seleccione **usar el proceso de solicitud existente en su lugar**.</span><span class="sxs-lookup"><span data-stu-id="4b38b-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="4b38b-124">En el panel derecho, en el cuadro **mensaje** , escriba el mensaje que desea que los usuarios vean cuando soliciten una licencia.</span><span class="sxs-lookup"><span data-stu-id="4b38b-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="4b38b-125">Si también desea incluir un vínculo a la Directiva de la organización o a otra documentación, escriba la dirección URL en el cuadro de texto **vínculo a documentación (opcional)** .</span><span class="sxs-lookup"><span data-stu-id="4b38b-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="4b38b-126">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4b38b-126">Select **Save**.</span></span>

<span data-ttu-id="4b38b-127">Cuando regrese a la lista **solicitudes** , verá el mensaje **que está usando su propio proceso de solicitud de licencia**.</span><span class="sxs-lookup"><span data-stu-id="4b38b-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="4b38b-128">Para realizar cambios en el mensaje que se envía a los usuarios, seleccione **usar el proceso de solicitud existente en su lugar**.</span><span class="sxs-lookup"><span data-stu-id="4b38b-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="4b38b-129">Dejar de usar su propio proceso de solicitud</span><span class="sxs-lookup"><span data-stu-id="4b38b-129">Stop using your own request process</span></span>

1. <span data-ttu-id="4b38b-130">En el centro de administración, vaya a la página licencias de **facturación**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> y, a continuación, seleccione la pestaña **solicitudes** .</span><span class="sxs-lookup"><span data-stu-id="4b38b-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="4b38b-131">Seleccione **usar el proceso de solicitud existente en su lugar**.</span><span class="sxs-lookup"><span data-stu-id="4b38b-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="4b38b-132">En el panel derecho, desactive la casilla **usar proceso de solicitud de mi organización** .</span><span class="sxs-lookup"><span data-stu-id="4b38b-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="4b38b-133">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4b38b-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="4b38b-134">Aprobar o denegar una solicitud de licencia</span><span class="sxs-lookup"><span data-stu-id="4b38b-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="4b38b-135">En el centro de administración, vaya a la página licencias de **facturación**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> y, a continuación, seleccione la pestaña **solicitudes** .</span><span class="sxs-lookup"><span data-stu-id="4b38b-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="4b38b-136">Seleccione la fila que contiene la solicitud que desea revisar.</span><span class="sxs-lookup"><span data-stu-id="4b38b-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="4b38b-137">El panel derecho muestra detalles sobre qué usuarios quieren licencias para el producto.</span><span class="sxs-lookup"><span data-stu-id="4b38b-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="4b38b-138">Para denegar toda la solicitud, seleccione **no aprobar**y, en el cuadro de diálogo, seleccione **no aprobar**.</span><span class="sxs-lookup"><span data-stu-id="4b38b-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="4b38b-139">Para denegar a algunos usuarios la solicitud, pero aprobar otros, seleccione la X por el nombre de los usuarios que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="4b38b-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="4b38b-140">Sus nombres se mueven bajo **no asignar a estos usuarios**.</span><span class="sxs-lookup"><span data-stu-id="4b38b-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="4b38b-141">Si tiene más de un producto, en **seleccionar un producto**, seleccione el que desea usar para asignar licencias.</span><span class="sxs-lookup"><span data-stu-id="4b38b-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="4b38b-142">Para denegar a los usuarios el acceso a ciertas aplicaciones y servicios, expanda **activar y desactivar aplicaciones y servicios**y, a continuación, desactive las casillas de los que desee excluir.</span><span class="sxs-lookup"><span data-stu-id="4b38b-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="4b38b-143">En la parte inferior del panel, escriba un mensaje opcional en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="4b38b-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="4b38b-144">Cuando haya terminado, seleccione **aprobar**.</span><span class="sxs-lookup"><span data-stu-id="4b38b-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="4b38b-145">En el panel derecho se muestran los detalles de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="4b38b-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="4b38b-146">Cierre el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="4b38b-146">Close the right pane.</span></span>
    <span data-ttu-id="4b38b-147">Los usuarios reciben un correo electrónico que dice que su solicitud se aprobó o denegó.</span><span class="sxs-lookup"><span data-stu-id="4b38b-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="4b38b-148">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="4b38b-148">Related content</span></span>

<span data-ttu-id="4b38b-149">[Asignar licencias a usuarios](../../admin/manage/assign-licenses-to-users.md) (artículo) </span><span class="sxs-lookup"><span data-stu-id="4b38b-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="4b38b-150">[Mover usuarios a otra suscripción](../subscriptions/move-users-different-subscription.md) (artículo) </span><span class="sxs-lookup"><span data-stu-id="4b38b-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="4b38b-151">[Comprar o quitar licencias de suscripción](buy-licenses.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="4b38b-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>