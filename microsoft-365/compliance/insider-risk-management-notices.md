---
title: Plantillas de aviso de administración de riesgos de Insider
description: Obtenga información sobre las plantillas de aviso de administración de riesgos de Insider en Microsoft 365
keywords: Microsoft 365, administración de riesgos de Insider, administración de riesgos, cumplimiento
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 92844691cba4adf39c7b4eee30de97ccff9d0890
ms.sourcegitcommit: 87cc278ea2ddcd536ecfaa3dfae9a5ddaa502cf9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179091"
---
# <a name="insider-risk-management-notice-templates"></a><span data-ttu-id="02e47-104">Plantillas de aviso de administración de riesgos de Insider</span><span class="sxs-lookup"><span data-stu-id="02e47-104">Insider risk management notice templates</span></span>

<span data-ttu-id="02e47-105">Las plantillas de aviso de administración de riesgos de Insider permiten enviar mensajes de correo electrónico a los empleados cuando sus actividades generan una coincidencia de directiva y una alerta.</span><span class="sxs-lookup"><span data-stu-id="02e47-105">Insider risk management notice templates allow you to send email messages to employees when their activities generate a policy match and alert.</span></span> <span data-ttu-id="02e47-106">En la mayoría de los casos, las acciones de los empleados que generan alertas son el resultado de errores o actividades involuntarias sin intención.</span><span class="sxs-lookup"><span data-stu-id="02e47-106">In most cases, employee actions that generate alerts are the result of mistakes or inadvertent activities without ill intent.</span></span> <span data-ttu-id="02e47-107">Los avisos sirven como sencillos avisos a los empleados para que tengan más cuidado o proporcionen vínculos o información para un aprendizaje de refresco o recursos de directivas corporativas.</span><span class="sxs-lookup"><span data-stu-id="02e47-107">Notices serve as simple reminders to employees to be more careful or to provide links or information for refresher training or corporate policy resources.</span></span> <span data-ttu-id="02e47-108">Los avisos pueden ser una parte importante del programa de formación de cumplimiento interno y pueden ayudar a crear una pista de auditoría documentada para los empleados con actividades recurrentes de riesgo.</span><span class="sxs-lookup"><span data-stu-id="02e47-108">Notices can be an important part of your internal compliance training program and can help create a documented audit trail for employees with recurring risk activities.</span></span>

<span data-ttu-id="02e47-109">Cree plantillas de aviso si desea enviar a los usuarios un aviso de recordatorio de correo electrónico sobre las coincidencias de directivas como parte del proceso de resolución de problemas.</span><span class="sxs-lookup"><span data-stu-id="02e47-109">Create notice templates if you want to send users an email reminder notice for policy matches as part of the issue resolution process.</span></span> <span data-ttu-id="02e47-110">Los avisos solo pueden enviarse a la dirección de correo electrónico del empleado asociada a la alerta específica que se está revisando.</span><span class="sxs-lookup"><span data-stu-id="02e47-110">Notices can only be sent to the employee email address associated with the specific alert being reviewed.</span></span> <span data-ttu-id="02e47-111">Al seleccionar una plantilla de notificación para aplicar a una coincidencia de Directiva, puede optar por aceptar los valores de campo definidos en la plantilla o sobrescribir los campos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="02e47-111">When selecting a notice template to apply to a policy match, you can choose to accept the field values defined in the template or overwrite the fields as needed.</span></span>

## <a name="notice-templates-dashboard"></a><span data-ttu-id="02e47-112">Panel plantillas de aviso</span><span class="sxs-lookup"><span data-stu-id="02e47-112">Notice templates dashboard</span></span>

<span data-ttu-id="02e47-113">El **Panel plantillas de notificaciones** muestra una lista de plantillas de aviso configuradas y le permite crear nuevas plantillas de aviso.</span><span class="sxs-lookup"><span data-stu-id="02e47-113">The **Notices templates dashboard** displays a list of configured notice templates and allows you to create new notice templates.</span></span> <span data-ttu-id="02e47-114">Las plantillas de aviso se enumeran en orden de fecha inverso con la plantilla de aviso más reciente que aparece en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="02e47-114">The notice templates are listed in reverse date order with the most recent notice template listed first.</span></span>

![Panel de plantillas de aviso de administración de riesgos de Insider](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a><span data-ttu-id="02e47-116">HTML para avisos</span><span class="sxs-lookup"><span data-stu-id="02e47-116">HTML for notices</span></span>

<span data-ttu-id="02e47-117">Si desea crear más de un mensaje de correo electrónico basado en texto sencillo para las notificaciones, puede crear un mensaje más detallado usando HTML en el campo cuerpo del mensaje de una plantilla de notificación.</span><span class="sxs-lookup"><span data-stu-id="02e47-117">If you'd like to create more than a simple text-based email message for notifications, you can create a more detailed message by using HTML in the message body field of a notice template.</span></span> <span data-ttu-id="02e47-118">El siguiente ejemplo proporciona el formato del cuerpo del mensaje para una plantilla básica de notificación de correo electrónico basada en HTML:</span><span class="sxs-lookup"><span data-stu-id="02e47-118">The following example provides the message body format for a basic HTML-based email notification template:</span></span>

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso Employee Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso Employee <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso Employee Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> <span data-ttu-id="02e47-119">La implementación de atributos de href HTML en las plantillas de aviso de administración de riesgos de Insider solo admiten comillas simples en lugar de comillas dobles para las referencias a direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="02e47-119">HTML href attribute implementation in the insider risk management notice templates currently support only single quotation marks instead of double quotation marks for URL references.</span></span>

## <a name="create-a-new-notice-template"></a><span data-ttu-id="02e47-120">Crear una nueva plantilla de aviso</span><span class="sxs-lookup"><span data-stu-id="02e47-120">Create a new notice template</span></span>

<span data-ttu-id="02e47-121">Para crear una nueva plantilla de aviso de administración de riesgos de Insider, use el Asistente para notificaciones de la solución de **Administración de riesgos de Insider** en el centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="02e47-121">To create a new insider risk management notice template, you'll use the notice wizard in **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="02e47-122">Complete los siguientes pasos para crear una nueva plantilla de aviso de administración de riesgos de Insider:</span><span class="sxs-lookup"><span data-stu-id="02e47-122">Complete the following steps to create a new insider risk management notice template:</span></span>

1. <span data-ttu-id="02e47-123">En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **plantillas de notificación** .</span><span class="sxs-lookup"><span data-stu-id="02e47-123">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="02e47-124">Seleccione **Crear plantilla de notificación** para abrir el Asistente para anuncios.</span><span class="sxs-lookup"><span data-stu-id="02e47-124">Select **Create notice template** to open the notice wizard.</span></span>
3. <span data-ttu-id="02e47-125">En la página **crear una nueva plantilla de notificación** , complete los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="02e47-125">On the **Create a new notice template** page, complete the following fields:</span></span>
    - <span data-ttu-id="02e47-126">**Nombre de plantilla**: escriba un nombre descriptivo para el aviso.</span><span class="sxs-lookup"><span data-stu-id="02e47-126">**Template name**: Enter a friendly name for the notice.</span></span> <span data-ttu-id="02e47-127">Este nombre aparece en la lista de avisos en el panel de notificación y en la lista de selección de aviso al enviar avisos desde un caso.</span><span class="sxs-lookup"><span data-stu-id="02e47-127">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="02e47-128">**Enviar desde**: escriba la dirección de correo electrónico del remitente para el aviso.</span><span class="sxs-lookup"><span data-stu-id="02e47-128">**Send from**: Enter the sender email address for the notice.</span></span> <span data-ttu-id="02e47-129">Esta dirección aparecerá en el campo **desde:** de todos los avisos que se envían a los empleados a menos que se cambie al enviar un aviso desde un caso.</span><span class="sxs-lookup"><span data-stu-id="02e47-129">This address will appear in the **From:** field in all notices sent to employees unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="02e47-130">Campos **CC y CCO** : usuarios o grupos opcionales a los que se les notificará la coincidencia de la Directiva, seleccionada en Active Directory de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="02e47-130">**Cc and Bcc** fields: Optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="02e47-131">**Asunto**: la información que aparece en la línea de asunto del mensaje admite caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="02e47-131">**Subject**: Information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="02e47-132">**Cuerpo del mensaje**: información que aparece en el cuerpo del mensaje, compatible con texto o con valores HTML.</span><span class="sxs-lookup"><span data-stu-id="02e47-132">**Message body**: Information that appears in the message body, supports text or HTML values.</span></span>
4. <span data-ttu-id="02e47-133">Seleccione **crear** para crear y guardar la plantilla de aviso o seleccione **Cancelar** para cerrar sin guardar la plantilla de aviso.</span><span class="sxs-lookup"><span data-stu-id="02e47-133">Select **Create** to create and save the notice template or select **Cancel** to close without saving the notice template.</span></span>

## <a name="update-a-notice-template"></a><span data-ttu-id="02e47-134">Actualizar una plantilla de aviso</span><span class="sxs-lookup"><span data-stu-id="02e47-134">Update a notice template</span></span>

<span data-ttu-id="02e47-135">Para actualizar una plantilla de aviso de administración de riesgos de Insider existente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="02e47-135">To update an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="02e47-136">En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **plantillas de notificación** .</span><span class="sxs-lookup"><span data-stu-id="02e47-136">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="02e47-137">En el panel de notificación, seleccione la plantilla de notificación que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="02e47-137">On the notice dashboard, select the notice template you want to manage.</span></span>
3. <span data-ttu-id="02e47-138">En la página Detalles de la notificación, seleccione **Editar**</span><span class="sxs-lookup"><span data-stu-id="02e47-138">On the notice details page, select **Edit**</span></span>
4. <span data-ttu-id="02e47-139">En la página **Editar** , puede editar los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="02e47-139">On the **Edit** page, you can edit the following fields:</span></span>
    - <span data-ttu-id="02e47-140">**Nombre de plantilla**: escriba un nuevo nombre descriptivo para el aviso.</span><span class="sxs-lookup"><span data-stu-id="02e47-140">**Template name**: Enter a new friendly name for the notice.</span></span> <span data-ttu-id="02e47-141">Este nombre aparece en la lista de avisos en el panel de notificación y en la lista de selección de aviso al enviar avisos desde un caso.</span><span class="sxs-lookup"><span data-stu-id="02e47-141">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="02e47-142">**Send from**: actualizar la dirección de correo electrónico del remitente para el aviso.</span><span class="sxs-lookup"><span data-stu-id="02e47-142">**Send from**: Update the sender email address for the notice.</span></span> <span data-ttu-id="02e47-143">Esta dirección aparecerá en el campo **desde:** de todos los avisos que se envían a los empleados a menos que se cambie al enviar un aviso desde un caso.</span><span class="sxs-lookup"><span data-stu-id="02e47-143">This address will appear in the **From:** field in all notices sent to employees unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="02e47-144">Campos **CC y CCO** : actualizar grupos o usuarios opcionales para recibir una notificación de la coincidencia de la Directiva, seleccionada en Active Directory de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="02e47-144">**Cc and Bcc** fields: Update optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="02e47-145">**Asunto**: la información de actualización que aparece en la línea de asunto del mensaje admite caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="02e47-145">**Subject**: Update information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="02e47-146">**Cuerpo del mensaje**: actualizar la información que aparece en el cuerpo del mensaje, admite texto o valores HTML.</span><span class="sxs-lookup"><span data-stu-id="02e47-146">**Message body**: Update information that appears in the message body, supports text or HTML values.</span></span>
5. <span data-ttu-id="02e47-147">Seleccione **Guardar** para actualizar y guardar el aviso o seleccione **Cancelar** para cerrar sin guardar la plantilla de aviso.</span><span class="sxs-lookup"><span data-stu-id="02e47-147">Select **Save** to update and save the notice or select **Cancel** to close without saving the notice template.</span></span>

## <a name="delete-a-notice-template"></a><span data-ttu-id="02e47-148">Eliminar una plantilla de aviso</span><span class="sxs-lookup"><span data-stu-id="02e47-148">Delete a notice template</span></span>

<span data-ttu-id="02e47-149">Para eliminar una plantilla de aviso de administración de riesgos de Insider existente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="02e47-149">To delete an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="02e47-150">En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **plantillas de notificación** .</span><span class="sxs-lookup"><span data-stu-id="02e47-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="02e47-151">En el panel de notificación, seleccione la plantilla de aviso que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="02e47-151">On the notice dashboard, select the notice template you want to delete.</span></span>
3. <span data-ttu-id="02e47-152">Seleccione el icono **eliminar** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="02e47-152">Select the **Delete** icon on the toolbar.</span></span>
4. <span data-ttu-id="02e47-153">Para eliminar la plantilla de aviso, seleccione **sí** en el cuadro de diálogo eliminar.</span><span class="sxs-lookup"><span data-stu-id="02e47-153">To delete the notice template, select **Yes** in the delete dialog.</span></span> <span data-ttu-id="02e47-154">Para cancelar la eliminación, seleccione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="02e47-154">To cancel the deletion, select **Cancel**.</span></span>
