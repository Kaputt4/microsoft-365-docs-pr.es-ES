---
title: Plantillas de aviso de administración de riesgos de Insider
description: Obtenga información sobre las plantillas de aviso de administración de riesgos de insider en Microsoft 365
keywords: Microsoft 365, administración de riesgos internos, administración de riesgos, cumplimiento
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 3a74c62e84c1cb9e4c749a364c0e5b6da25a8af9
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416484"
---
# <a name="insider-risk-management-notice-templates"></a><span data-ttu-id="c157c-104">Plantillas de aviso de administración de riesgos de Insider</span><span class="sxs-lookup"><span data-stu-id="c157c-104">Insider risk management notice templates</span></span>

<span data-ttu-id="c157c-105">Las plantillas de aviso de administración de riesgos de Insider permiten enviar mensajes de correo electrónico a los usuarios cuando sus actividades generan una alerta y coincidencia de directiva.</span><span class="sxs-lookup"><span data-stu-id="c157c-105">Insider risk management notice templates allow you to send email messages to users when their activities generate a policy match and alert.</span></span> <span data-ttu-id="c157c-106">En la mayoría de los casos, las acciones de usuario que generan alertas son el resultado de errores o actividades involuntarias sin mala intención.</span><span class="sxs-lookup"><span data-stu-id="c157c-106">In most cases, user actions that generate alerts are the result of mistakes or inadvertent activities without ill intent.</span></span> <span data-ttu-id="c157c-107">Los avisos sirven como simples avisos a los usuarios para que tengan más cuidado, proporcionen vínculos a información para el aprendizaje de actualización o a recursos de directivas corporativas.</span><span class="sxs-lookup"><span data-stu-id="c157c-107">Notices serve as simple reminders to users to be more careful, to provide links to information for refresher training, or to corporate policy resources.</span></span> <span data-ttu-id="c157c-108">Los avisos pueden ser una parte importante del programa de aprendizaje de cumplimiento interno y pueden ayudar a crear una pista de auditoría documentada para los usuarios con actividades de riesgo periódicas.</span><span class="sxs-lookup"><span data-stu-id="c157c-108">Notices can be an important part of your internal compliance training program and can help create a documented audit trail for users with recurring risk activities.</span></span>

<span data-ttu-id="c157c-109">Cree plantillas de aviso si desea enviar a los usuarios un aviso de aviso por correo electrónico para las coincidencias de directiva como parte del proceso de resolución de problemas.</span><span class="sxs-lookup"><span data-stu-id="c157c-109">Create notice templates if you want to send users an email reminder notice for policy matches as part of the issue resolution process.</span></span> <span data-ttu-id="c157c-110">Los avisos solo se pueden enviar a la dirección de correo electrónico del usuario asociada con la alerta específica que se está revisando.</span><span class="sxs-lookup"><span data-stu-id="c157c-110">Notices can only be sent to the user email address associated with the specific alert being reviewed.</span></span> <span data-ttu-id="c157c-111">Al seleccionar una plantilla de aviso para aplicar a una coincidencia de directiva, puede elegir aceptar los valores de campo definidos en la plantilla o sobrescribir los campos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="c157c-111">When selecting a notice template to apply to a policy match, you can choose to accept the field values defined in the template or overwrite the fields as needed.</span></span>

## <a name="notice-templates-dashboard"></a><span data-ttu-id="c157c-112">Panel de plantillas de aviso</span><span class="sxs-lookup"><span data-stu-id="c157c-112">Notice templates dashboard</span></span>

<span data-ttu-id="c157c-113">El **panel de plantillas de avisos** muestra una lista de plantillas de avisos configuradas y le permite crear nuevas plantillas de avisos.</span><span class="sxs-lookup"><span data-stu-id="c157c-113">The **Notices templates dashboard** displays a list of configured notice templates and allows you to create new notice templates.</span></span> <span data-ttu-id="c157c-114">Las plantillas de aviso se muestran en orden de fecha inverso con la plantilla de aviso más reciente al principio de la lista.</span><span class="sxs-lookup"><span data-stu-id="c157c-114">The notice templates are listed in reverse date order with the most recent notice template listed first.</span></span>

![Panel de plantillas de aviso de administración de riesgos de Insider](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a><span data-ttu-id="c157c-116">HTML para avisos</span><span class="sxs-lookup"><span data-stu-id="c157c-116">HTML for notices</span></span>

<span data-ttu-id="c157c-117">Si desea crear más que un mensaje de correo electrónico simple basado en texto para notificaciones, puede crear un mensaje más detallado mediante HTML en el campo cuerpo del mensaje de una plantilla de aviso.</span><span class="sxs-lookup"><span data-stu-id="c157c-117">If you'd like to create more than a simple text-based email message for notifications, you can create a more detailed message by using HTML in the message body field of a notice template.</span></span> <span data-ttu-id="c157c-118">En el siguiente ejemplo se proporciona el formato del cuerpo del mensaje para una plantilla básica de notificación de correo electrónico basada en HTML:</span><span class="sxs-lookup"><span data-stu-id="c157c-118">The following example provides the message body format for a basic HTML-based email notification template:</span></span>

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso User Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso User <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso User Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> <span data-ttu-id="c157c-119">La implementación de atributos href HTML en las plantillas de aviso de administración de riesgos insider admiten actualmente sólo comillas simples en lugar de comillas dobles para las referencias url.</span><span class="sxs-lookup"><span data-stu-id="c157c-119">HTML href attribute implementation in the insider risk management notice templates currently support only single quotation marks instead of double quotation marks for URL references.</span></span>

## <a name="create-a-new-notice-template"></a><span data-ttu-id="c157c-120">Crear una nueva plantilla de aviso</span><span class="sxs-lookup"><span data-stu-id="c157c-120">Create a new notice template</span></span>

<span data-ttu-id="c157c-121">Para crear una nueva plantilla de aviso de administración de riesgos de **insider,** usará el Asistente para avisos en la solución de administración de riesgos insider en el centro de Microsoft 365 cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="c157c-121">To create a new insider risk management notice template, you'll use the notice wizard in **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="c157c-122">Complete los siguientes pasos para crear una nueva plantilla de aviso de administración de riesgos insider:</span><span class="sxs-lookup"><span data-stu-id="c157c-122">Complete the following steps to create a new insider risk management notice template:</span></span>

1. <span data-ttu-id="c157c-123">En el [centro Microsoft 365 cumplimiento,](https://compliance.microsoft.com)vaya a Administración de riesgos **de Insider** y seleccione la pestaña **Plantillas de** aviso.</span><span class="sxs-lookup"><span data-stu-id="c157c-123">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="c157c-124">Seleccione **Crear plantilla de aviso** para abrir el asistente para avisos.</span><span class="sxs-lookup"><span data-stu-id="c157c-124">Select **Create notice template** to open the notice wizard.</span></span>
3. <span data-ttu-id="c157c-125">En la **página Crear una nueva plantilla de aviso,** complete los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="c157c-125">On the **Create a new notice template** page, complete the following fields:</span></span>
    - <span data-ttu-id="c157c-126">**Nombre de plantilla:** escriba un nombre descriptivo para el aviso.</span><span class="sxs-lookup"><span data-stu-id="c157c-126">**Template name**: Enter a friendly name for the notice.</span></span> <span data-ttu-id="c157c-127">Este nombre aparece en la lista de avisos en el panel de avisos y en la lista de selección de avisos al enviar avisos desde un caso.</span><span class="sxs-lookup"><span data-stu-id="c157c-127">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="c157c-128">**Enviar desde:** escriba la dirección de correo electrónico del remitente para el aviso.</span><span class="sxs-lookup"><span data-stu-id="c157c-128">**Send from**: Enter the sender email address for the notice.</span></span> <span data-ttu-id="c157c-129">Esta dirección aparecerá en el **campo De:** en todos los avisos enviados a los usuarios a menos que se cambie al enviar un aviso desde un caso.</span><span class="sxs-lookup"><span data-stu-id="c157c-129">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="c157c-130">Campos CC y **CCO:** usuarios o grupos opcionales que se notificarán de la coincidencia de directiva, seleccionados desde Active Directory para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="c157c-130">**Cc and Bcc** fields: Optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="c157c-131">**Asunto:** la información que aparece en la línea de asunto del mensaje admite caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="c157c-131">**Subject**: Information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="c157c-132">**Cuerpo del mensaje:** información que aparece en el cuerpo del mensaje, admite valores de texto o HTML.</span><span class="sxs-lookup"><span data-stu-id="c157c-132">**Message body**: Information that appears in the message body, supports text or HTML values.</span></span>
4. <span data-ttu-id="c157c-133">Seleccione **Crear** para crear y guardar la plantilla de aviso o **seleccione Cancelar** para cerrarla sin guardar la plantilla de aviso.</span><span class="sxs-lookup"><span data-stu-id="c157c-133">Select **Create** to create and save the notice template or select **Cancel** to close without saving the notice template.</span></span>

## <a name="update-a-notice-template"></a><span data-ttu-id="c157c-134">Actualizar una plantilla de aviso</span><span class="sxs-lookup"><span data-stu-id="c157c-134">Update a notice template</span></span>

<span data-ttu-id="c157c-135">Para actualizar una plantilla de aviso de administración de riesgos insider existente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c157c-135">To update an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="c157c-136">En el [centro Microsoft 365 cumplimiento,](https://compliance.microsoft.com)vaya a Administración de riesgos **de Insider** y seleccione la pestaña **Plantillas de** aviso.</span><span class="sxs-lookup"><span data-stu-id="c157c-136">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="c157c-137">En el panel de avisos, seleccione la plantilla de aviso que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="c157c-137">On the notice dashboard, select the notice template you want to manage.</span></span>
3. <span data-ttu-id="c157c-138">En la página de detalles del aviso, seleccione **Editar**</span><span class="sxs-lookup"><span data-stu-id="c157c-138">On the notice details page, select **Edit**</span></span>
4. <span data-ttu-id="c157c-139">En la **página** Editar, puede editar los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c157c-139">On the **Edit** page, you can edit the following fields:</span></span>
    - <span data-ttu-id="c157c-140">**Nombre de plantilla:** escriba un nuevo nombre descriptivo para el aviso.</span><span class="sxs-lookup"><span data-stu-id="c157c-140">**Template name**: Enter a new friendly name for the notice.</span></span> <span data-ttu-id="c157c-141">Este nombre aparece en la lista de avisos en el panel de avisos y en la lista de selección de avisos al enviar avisos desde un caso.</span><span class="sxs-lookup"><span data-stu-id="c157c-141">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="c157c-142">**Enviar desde**: Actualizar la dirección de correo electrónico del remitente para el aviso.</span><span class="sxs-lookup"><span data-stu-id="c157c-142">**Send from**: Update the sender email address for the notice.</span></span> <span data-ttu-id="c157c-143">Esta dirección aparecerá en el **campo De:** en todos los avisos enviados a los usuarios a menos que se cambie al enviar un aviso desde un caso.</span><span class="sxs-lookup"><span data-stu-id="c157c-143">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="c157c-144">Campos CC y **CCO:** actualice los usuarios o grupos opcionales que se notificarán de la coincidencia de directiva, seleccionados en Active Directory para su suscripción.</span><span class="sxs-lookup"><span data-stu-id="c157c-144">**Cc and Bcc** fields: Update optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="c157c-145">**Asunto:** actualiza la información que aparece en la línea de asunto del mensaje y admite caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="c157c-145">**Subject**: Update information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="c157c-146">**Cuerpo del mensaje:** actualice la información que aparece en el cuerpo del mensaje, admite valores de texto o HTML.</span><span class="sxs-lookup"><span data-stu-id="c157c-146">**Message body**: Update information that appears in the message body, supports text or HTML values.</span></span>
5. <span data-ttu-id="c157c-147">Seleccione **Guardar** para actualizar y guardar el aviso o **seleccione Cancelar** para cerrar sin guardar la plantilla de aviso.</span><span class="sxs-lookup"><span data-stu-id="c157c-147">Select **Save** to update and save the notice or select **Cancel** to close without saving the notice template.</span></span>

## <a name="delete-a-notice-template"></a><span data-ttu-id="c157c-148">Eliminar una plantilla de aviso</span><span class="sxs-lookup"><span data-stu-id="c157c-148">Delete a notice template</span></span>

<span data-ttu-id="c157c-149">Para eliminar una plantilla de aviso de administración de riesgos insider existente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c157c-149">To delete an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="c157c-150">En el [centro Microsoft 365 cumplimiento,](https://compliance.microsoft.com)vaya a Administración de riesgos **de Insider** y seleccione la pestaña **Plantillas de** aviso.</span><span class="sxs-lookup"><span data-stu-id="c157c-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="c157c-151">En el panel de avisos, seleccione la plantilla de aviso que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="c157c-151">On the notice dashboard, select the notice template you want to delete.</span></span>
3. <span data-ttu-id="c157c-152">Seleccione el **icono Eliminar** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="c157c-152">Select the **Delete** icon on the toolbar.</span></span>
4. <span data-ttu-id="c157c-153">Para eliminar la plantilla de aviso, seleccione **Sí** en el cuadro de diálogo eliminar.</span><span class="sxs-lookup"><span data-stu-id="c157c-153">To delete the notice template, select **Yes** in the delete dialog.</span></span> <span data-ttu-id="c157c-154">Para cancelar la eliminación, seleccione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="c157c-154">To cancel the deletion, select **Cancel**.</span></span>
