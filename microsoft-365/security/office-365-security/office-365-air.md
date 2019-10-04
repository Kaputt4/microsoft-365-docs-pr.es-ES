---
title: Investigar y responder automáticamente ante amenazas en Office 365
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 10/03/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Introducción al uso de las capacidades de respuesta a incidentes automatizada en Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 293b567cf24e9c6b0e33e28e9dd1ca0453fd0cd1
ms.sourcegitcommit: d4aa94716b33e6c270ae7adfbdc4c19cf4a0087d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "37385737"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a><span data-ttu-id="349da-104">Investigar y responder automáticamente ante amenazas en Office 365</span><span class="sxs-lookup"><span data-stu-id="349da-104">Automatically investigate and respond to threats in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="349da-105">Información general</span><span class="sxs-lookup"><span data-stu-id="349da-105">Overview</span></span>

<span data-ttu-id="349da-106">Según su suscripción, la [protección contra amenazas avanzada de Office 365](office-365-atp.md) puede incluir capacidades de respuesta de incidente (Air) automatizadas que pueden salvar el tiempo y el esfuerzo del equipo de operaciones de seguridad para tratar las alertas y amenazas.</span><span class="sxs-lookup"><span data-stu-id="349da-106">Depending on your subscription, [Office 365 Advanced Threat Protection](office-365-atp.md) can include automated incident response (AIR) capabilities that can save your security operations team time and effort in dealing with alerts and threats.</span></span>

- <span data-ttu-id="349da-107">Para empezar a usar las funcionalidades de AIR en Office 365, use este artículo.</span><span class="sxs-lookup"><span data-stu-id="349da-107">To get started using AIR capabilities in Office 365, use this article.</span></span> 
- <span data-ttu-id="349da-108">Para obtener información general sobre cómo funciona AIR, vea [respuesta de incidente automatizada (Air) en Office 365](automated-investigation-response-office.md).</span><span class="sxs-lookup"><span data-stu-id="349da-108">To get an overview of how AIR works, see [Automated incident response (AIR) in Office 365](automated-investigation-response-office.md).</span></span>

<span data-ttu-id="349da-109">Con AIR, cuando se desencadenan determinadas alertas, se inician una o más guías de seguridad y comienza la investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="349da-109">With AIR, when certain alerts are triggered, one or more security playbooks initiate, and automated investigation begins.</span></span> <span data-ttu-id="349da-110">Durante y después de un proceso de investigación automatizado, los administradores y el equipo de operaciones de seguridad pueden:</span><span class="sxs-lookup"><span data-stu-id="349da-110">During and after an automated investigation process, your administrators and security operations team can:</span></span>

- [<span data-ttu-id="349da-111">Ver los detalles de una investigación</span><span class="sxs-lookup"><span data-stu-id="349da-111">View the details of an investigation</span></span>](#view-details-of-an-investigation)
- [<span data-ttu-id="349da-112">Revisión y aprobación de acciones como resultado de una investigación</span><span class="sxs-lookup"><span data-stu-id="349da-112">Review and approve actions as a result of an investigation</span></span>](#review-and-approve-actions) 
- [<span data-ttu-id="349da-113">Ver los detalles de una alerta relacionada con una investigación</span><span class="sxs-lookup"><span data-stu-id="349da-113">View details about an alert related to an investigation</span></span>](#view-details-about-an-alert-related-to-an-investigation)

> [!NOTE]
> <span data-ttu-id="349da-114">Debe ser administrador global, administrador de seguridad, operador de seguridad o lector de seguridad para realizar las tareas descritas en este artículo.</span><span class="sxs-lookup"><span data-stu-id="349da-114">You must be a global administrator, security administrator, security operator, or security reader to perform the tasks described in this article.</span></span> <span data-ttu-id="349da-115">Para obtener más información, consulte [Microsoft 365 Security Center: roles y permisos](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span><span class="sxs-lookup"><span data-stu-id="349da-115">To learn more, see [Microsoft 365 security center: roles and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="349da-116">AIR se incluye en las siguientes suscripciones:</span><span class="sxs-lookup"><span data-stu-id="349da-116">AIR is included in the following subscriptions:</span></span>
- <span data-ttu-id="349da-117">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="349da-117">Microsoft 365 E5</span></span>
- <span data-ttu-id="349da-118">Seguridad de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="349da-118">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="349da-119">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="349da-119">Office 365 E5</span></span>
- <span data-ttu-id="349da-120">Plan 2 de protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="349da-120">Office 365 Advanced Threat Protection Plan 2</span></span>

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="349da-121">Ver los detalles de una investigación</span><span class="sxs-lookup"><span data-stu-id="349da-121">View details of an investigation</span></span>

1. <span data-ttu-id="349da-122">Como administrador global de Office 365, administrador de seguridad o lector de seguridad, vaya [https://protection.office.com](https://protection.office.com) a e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="349da-122">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="349da-123">Esto le llevará al centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="349da-123">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="349da-124">Realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="349da-124">Do one of the following:</span></span>

    - <span data-ttu-id="349da-125">Vaya al \*\*\*\* > **Panel**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="349da-125">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="349da-126">Esto le llevará al [Panel de seguridad](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="349da-126">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="349da-127">Los widgets de AIR aparecen en la parte superior del [Panel de seguridad](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="349da-127">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="349da-128">Seleccione un widget, como un **Resumen de investigaciones**.</span><span class="sxs-lookup"><span data-stu-id="349da-128">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="349da-129">Vaya a \*\*\*\* > **investigaciones**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="349da-129">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="349da-130">Cualquiera de estos métodos le lleva a una lista de investigaciones.</span><span class="sxs-lookup"><span data-stu-id="349da-130">Either method takes you to a list of investigations.</span></span>

    ![Página principal de investigación para AIR](../media/air-maininvestigationpage.png) 

3. <span data-ttu-id="349da-132">En la lista de investigaciones, seleccione un elemento en la columna **ID** .</span><span class="sxs-lookup"><span data-stu-id="349da-132">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="349da-133">Se abrirá la página Detalles de la investigación, empezando por el gráfico de investigación en la vista.</span><span class="sxs-lookup"><span data-stu-id="349da-133">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![Página de gráfico de investigación de aire](../media/air-investigationgraphpage.png)

4. <span data-ttu-id="349da-135">Use las distintas pestañas para obtener más información sobre la investigación.</span><span class="sxs-lookup"><span data-stu-id="349da-135">Use the various tabs to learn more about the investigation.</span></span>

## <a name="review-and-approve-actions"></a><span data-ttu-id="349da-136">Revisión y aprobación de acciones</span><span class="sxs-lookup"><span data-stu-id="349da-136">Review and approve actions</span></span>

<span data-ttu-id="349da-137">En Office 365, las investigaciones automatizadas suelen dar como resultado una o varias acciones recomendadas.</span><span class="sxs-lookup"><span data-stu-id="349da-137">In Office 365, automated investigations typically result in one or more recommended actions.</span></span> <span data-ttu-id="349da-138">Sin embargo, no se lleva a cabo ninguna acción hasta que la aprueba el equipo de operaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="349da-138">However, no actions are taken until they are approved by your security operations team.</span></span> <span data-ttu-id="349da-139">Use el siguiente procedimiento para revisar y aprobar acciones.</span><span class="sxs-lookup"><span data-stu-id="349da-139">Use the following procedure to review and approve actions.</span></span>

1. <span data-ttu-id="349da-140">Como administrador global de Office 365, administrador de seguridad o lector de seguridad, vaya [https://protection.office.com](https://protection.office.com) a e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="349da-140">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> 

2. <span data-ttu-id="349da-141">Vaya a \*\*\*\* > **investigaciones**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="349da-141">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="349da-142">En la lista de investigaciones, seleccione un elemento en la columna **ID** .</span><span class="sxs-lookup"><span data-stu-id="349da-142">In the list of investigations, select an item in the **ID** column.</span></span> 

3. <span data-ttu-id="349da-143">En la vista detalles de la investigación, seleccione la ficha **acciones** . Aquí se enumeran las acciones pendientes de aprobación.</span><span class="sxs-lookup"><span data-stu-id="349da-143">On the investigation details view, select the **Actions** tab. Any actions that are pending approval are listed here.</span></span>

4. <span data-ttu-id="349da-144">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="349da-144">Select an item in the list.</span></span>

5. <span data-ttu-id="349da-145">Seleccione **aprobar** para realizar la acción recomendada (o **rechazar** para cerrar la investigación sin emprender ninguna acción).</span><span class="sxs-lookup"><span data-stu-id="349da-145">Select **Approve** to take the recommended action (or **Reject** to close the investigation without taking action).</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="349da-146">Ver los detalles de una alerta relacionada con una investigación</span><span class="sxs-lookup"><span data-stu-id="349da-146">View details about an alert related to an investigation</span></span>

<span data-ttu-id="349da-147">Ciertos tipos de alertas desencadenan la investigación automática en Office 365.</span><span class="sxs-lookup"><span data-stu-id="349da-147">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="349da-148">Para obtener más información, vea [alertas](automated-investigation-response-office.md#alerts).</span><span class="sxs-lookup"><span data-stu-id="349da-148">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="349da-149">Use el siguiente procedimiento para ver los detalles de una alerta asociada a una investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="349da-149">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="349da-150">Como administrador global de Office 365, administrador de seguridad o lector de seguridad, vaya [https://protection.office.com](https://protection.office.com) a e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="349da-150">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="349da-151">Esto le llevará al centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="349da-151">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="349da-152">Vaya a \*\*\*\* > **investigaciones**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="349da-152">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="349da-153">En la lista de investigaciones, seleccione un elemento en la columna **ID** .</span><span class="sxs-lookup"><span data-stu-id="349da-153">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="349da-154">Con los detalles de una investigación abierta, seleccione la pestaña **alertas** . Aquí se enumeran las alertas que desencadenaron la investigación.</span><span class="sxs-lookup"><span data-stu-id="349da-154">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="349da-155">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="349da-155">Select an item in the list.</span></span> <span data-ttu-id="349da-156">Se abre un control flotante, con detalles sobre la alerta y vínculos a acciones e información adicionales.</span><span class="sxs-lookup"><span data-stu-id="349da-156">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="349da-157">Revise la información en el control flotante y, en función de la alerta en particular, realice una acción, como **resolver**, **suprimir**o **notificar a los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="349da-157">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

    - <span data-ttu-id="349da-158">**Resolve** equivale a cerrar una alerta</span><span class="sxs-lookup"><span data-stu-id="349da-158">**Resolve** is equivalent to closing an alert</span></span>
    
    - <span data-ttu-id="349da-159">**Suprimir** hace que una directiva no desencadene alertas durante un período de tiempo especificado</span><span class="sxs-lookup"><span data-stu-id="349da-159">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>
    
    - <span data-ttu-id="349da-160">**Notify users** inicia un correo electrónico con las direcciones de correo electrónico de los usuarios que ya se han especificado y permite que el equipo de operaciones de seguridad escriba un mensaje para esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="349da-160">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="349da-161">(Es similar a enviar un mensaje a los destinatarios mediante el [Explorador de amenazas](threat-explorer.md)).</span><span class="sxs-lookup"><span data-stu-id="349da-161">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="349da-162">Usar la API de actividad de administración de Office 365 para soluciones de informes personalizadas o de terceros</span><span class="sxs-lookup"><span data-stu-id="349da-162">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="349da-163">Si su organización usa una solución de informes personalizada o de terceros, puede ver información sobre las investigaciones automatizadas en esa solución mediante la API de actividad de administración 365 de Office.</span><span class="sxs-lookup"><span data-stu-id="349da-163">If your organization is using a custom or third-party reporting solution, you can view information about automated investigations in that solution by using the Office 365 Management Activity API.</span></span>

<span data-ttu-id="349da-164">Use los siguientes recursos para configurar esto:</span><span class="sxs-lookup"><span data-stu-id="349da-164">Use the following resources to set this up:</span></span>

|<span data-ttu-id="349da-165">Recurso</span><span class="sxs-lookup"><span data-stu-id="349da-165">Resource</span></span>  |<span data-ttu-id="349da-166">Descripción</span><span class="sxs-lookup"><span data-stu-id="349da-166">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="349da-167">Información general de las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="349da-167">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="349da-168">La API de actividad de administración de Office 365 proporciona información sobre diversas acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Office 365 y Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="349da-168">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="349da-169">Introducción a las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="349da-169">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="349da-170">La API de administración 365 de Office usa Azure AD para proporcionar servicios de autenticación para que la aplicación tenga acceso a los datos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="349da-170">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="349da-171">Siga los pasos de este artículo para configurarlo.</span><span class="sxs-lookup"><span data-stu-id="349da-171">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="349da-172">Referencia de las API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="349da-172">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="349da-173">Puede usar la API de actividad de administración de Office 365 para recuperar información sobre las acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Office 365 y Azure AD.</span><span class="sxs-lookup"><span data-stu-id="349da-173">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="349da-174">Lea este artículo para obtener más información sobre cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="349da-174">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="349da-175">Esquema de la API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="349da-175">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="349da-176">Obtenga información general sobre el [esquema común](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) y el [esquema de investigación y respuesta de ATP y la investigación de amenazas de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) para obtener información sobre los tipos de datos específicos disponibles a través de la API de actividad de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="349da-176">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="next-steps"></a><span data-ttu-id="349da-177">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="349da-177">Next steps</span></span>

[<span data-ttu-id="349da-178">Más información acerca de las alertas</span><span class="sxs-lookup"><span data-stu-id="349da-178">Learn more about alerts</span></span>](../../compliance/alert-policies.md)

[<span data-ttu-id="349da-179">Buscar y investigar manualmente el correo electrónico malintencionado que se entregó en Office 365</span><span class="sxs-lookup"><span data-stu-id="349da-179">Manually find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

[<span data-ttu-id="349da-180">Obtener información sobre AIR en ATP de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="349da-180">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

[<span data-ttu-id="349da-181">Visite el plan de desarrollo de Microsoft 365 para ver lo que estará próximamente y que se implementará</span><span class="sxs-lookup"><span data-stu-id="349da-181">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)