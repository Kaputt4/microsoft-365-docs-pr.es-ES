---
title: Investigar y responder automáticamente ante amenazas en Office 365
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 11/15/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Introducción al uso de las capacidades de respuesta a incidentes automatizada en Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 13f7e95829b8cf3adf17a40cf7b02c5322b15ea7
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673426"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a><span data-ttu-id="acbc0-104">Investigar y responder automáticamente ante amenazas en Office 365</span><span class="sxs-lookup"><span data-stu-id="acbc0-104">Automatically investigate and respond to threats in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="acbc0-105">Información general</span><span class="sxs-lookup"><span data-stu-id="acbc0-105">Overview</span></span>

<span data-ttu-id="acbc0-106">Según su suscripción, la [protección contra amenazas avanzada de Office 365](office-365-atp.md) puede incluir capacidades de respuesta de incidente (Air) automatizadas que pueden salvar el tiempo y el esfuerzo del equipo de operaciones de seguridad para tratar las alertas y amenazas.</span><span class="sxs-lookup"><span data-stu-id="acbc0-106">Depending on your subscription, [Office 365 Advanced Threat Protection](office-365-atp.md) can include automated incident response (AIR) capabilities that can save your security operations team time and effort in dealing with alerts and threats.</span></span>

- <span data-ttu-id="acbc0-107">Para empezar a usar las funcionalidades de AIR en Office 365, use este artículo.</span><span class="sxs-lookup"><span data-stu-id="acbc0-107">To get started using AIR capabilities in Office 365, use this article.</span></span> 
- <span data-ttu-id="acbc0-108">Para obtener información general sobre cómo funciona AIR, vea [respuesta de incidente automatizada (Air) en Office 365](automated-investigation-response-office.md).</span><span class="sxs-lookup"><span data-stu-id="acbc0-108">To get an overview of how AIR works, see [Automated incident response (AIR) in Office 365](automated-investigation-response-office.md).</span></span>

<span data-ttu-id="acbc0-109">Con AIR, cuando se desencadenan determinadas alertas, se inician una o más guías de seguridad y comienza la investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="acbc0-109">With AIR, when certain alerts are triggered, one or more security playbooks initiate, and automated investigation begins.</span></span> <span data-ttu-id="acbc0-110">Durante y después de un proceso de investigación automatizado, los administradores y el equipo de operaciones de seguridad pueden:</span><span class="sxs-lookup"><span data-stu-id="acbc0-110">During and after an automated investigation process, your administrators and security operations team can:</span></span>

- [<span data-ttu-id="acbc0-111">Ver los detalles de una investigación</span><span class="sxs-lookup"><span data-stu-id="acbc0-111">View the details of an investigation</span></span>](#view-details-of-an-investigation)
- [<span data-ttu-id="acbc0-112">Revisión y aprobación de acciones como resultado de una investigación</span><span class="sxs-lookup"><span data-stu-id="acbc0-112">Review and approve actions as a result of an investigation</span></span>](#review-and-approve-actions) 
- [<span data-ttu-id="acbc0-113">Ver los detalles de una alerta relacionada con una investigación</span><span class="sxs-lookup"><span data-stu-id="acbc0-113">View details about an alert related to an investigation</span></span>](#view-details-about-an-alert-related-to-an-investigation)

> [!NOTE]
> <span data-ttu-id="acbc0-114">Debe tener los permisos adecuados para realizar las tareas descritas en este artículo.</span><span class="sxs-lookup"><span data-stu-id="acbc0-114">You must have appropriate permissions to perform the tasks described in this article.</span></span> <span data-ttu-id="acbc0-115">Por ejemplo, Myst ser un administrador global, un administrador de seguridad, un operador de seguridad o un lector de seguridad.</span><span class="sxs-lookup"><span data-stu-id="acbc0-115">For example, you myst be a global administrator, security administrator, security operator, or security reader.</span></span> <span data-ttu-id="acbc0-116">[Obtenga más información sobre los roles y permisos de Microsoft 365 Security Center](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span><span class="sxs-lookup"><span data-stu-id="acbc0-116">[Learn more about Microsoft 365 security center roles and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="acbc0-117">AIR se incluye en las siguientes suscripciones:</span><span class="sxs-lookup"><span data-stu-id="acbc0-117">AIR is included in the following subscriptions:</span></span>
- <span data-ttu-id="acbc0-118">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="acbc0-118">Microsoft 365 E5</span></span>
- <span data-ttu-id="acbc0-119">Seguridad de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="acbc0-119">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="acbc0-120">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="acbc0-120">Office 365 E5</span></span>
- <span data-ttu-id="acbc0-121">Protección contra amenazas avanzada de Office 365 (plan 2)</span><span class="sxs-lookup"><span data-stu-id="acbc0-121">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="acbc0-122">Si no tiene una de estas suscripciones, [inicie una prueba gratuita](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="acbc0-122">If you don't have one of these subscriptions, [start a free trial](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="acbc0-123">Ver los detalles de una investigación</span><span class="sxs-lookup"><span data-stu-id="acbc0-123">View details of an investigation</span></span>

1. <span data-ttu-id="acbc0-124">Como administrador global de Office 365, administrador de seguridad o lector de seguridad, vaya [https://protection.office.com](https://protection.office.com) a e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="acbc0-124">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="acbc0-125">Esto le llevará al centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="acbc0-125">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="acbc0-126">Realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="acbc0-126">Do one of the following:</span></span>

    - <span data-ttu-id="acbc0-127">Vaya al \*\*\*\* > **Panel**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="acbc0-127">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="acbc0-128">Esto le llevará al [Panel de seguridad](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="acbc0-128">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="acbc0-129">Los widgets de AIR aparecen en la parte superior del [Panel de seguridad](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="acbc0-129">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="acbc0-130">Seleccione un widget, como un **Resumen de investigaciones**.</span><span class="sxs-lookup"><span data-stu-id="acbc0-130">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="acbc0-131">Vaya a \*\*\*\* > **investigaciones**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="acbc0-131">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="acbc0-132">Cualquiera de estos métodos le lleva a una lista de investigaciones.</span><span class="sxs-lookup"><span data-stu-id="acbc0-132">Either method takes you to a list of investigations.</span></span>

    ![Página principal de investigación para AIR](../media/air-maininvestigationpage.png) 

3. <span data-ttu-id="acbc0-134">En la lista de investigaciones, seleccione un elemento en la columna **ID** .</span><span class="sxs-lookup"><span data-stu-id="acbc0-134">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="acbc0-135">Se abrirá la página Detalles de la investigación, empezando por el gráfico de investigación en la vista.</span><span class="sxs-lookup"><span data-stu-id="acbc0-135">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![Página de gráfico de investigación de aire](../media/air-investigationgraphpage.png)

4. <span data-ttu-id="acbc0-137">Use las distintas pestañas para obtener más información sobre la investigación.</span><span class="sxs-lookup"><span data-stu-id="acbc0-137">Use the various tabs to learn more about the investigation.</span></span>

## <a name="review-and-approve-actions"></a><span data-ttu-id="acbc0-138">Revisión y aprobación de acciones</span><span class="sxs-lookup"><span data-stu-id="acbc0-138">Review and approve actions</span></span>

<span data-ttu-id="acbc0-139">En Office 365, las investigaciones automatizadas suelen dar como resultado una o varias acciones recomendadas.</span><span class="sxs-lookup"><span data-stu-id="acbc0-139">In Office 365, automated investigations typically result in one or more recommended actions.</span></span> <span data-ttu-id="acbc0-140">Sin embargo, no se lleva a cabo ninguna acción hasta que la aprueba el equipo de operaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="acbc0-140">However, no actions are taken until they are approved by your security operations team.</span></span> <span data-ttu-id="acbc0-141">Use el siguiente procedimiento para revisar y aprobar acciones.</span><span class="sxs-lookup"><span data-stu-id="acbc0-141">Use the following procedure to review and approve actions.</span></span>

1. <span data-ttu-id="acbc0-142">Como administrador global de Office 365, administrador de seguridad o lector de seguridad, vaya [https://protection.office.com](https://protection.office.com) a e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="acbc0-142">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> 

2. <span data-ttu-id="acbc0-143">Vaya a \*\*\*\* > **investigaciones**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="acbc0-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="acbc0-144">En la lista de investigaciones, seleccione un elemento en la columna **ID** .</span><span class="sxs-lookup"><span data-stu-id="acbc0-144">In the list of investigations, select an item in the **ID** column.</span></span> 

3. <span data-ttu-id="acbc0-145">En la vista detalles de la investigación, seleccione la ficha **acciones** . Aquí se enumeran las acciones pendientes de aprobación.</span><span class="sxs-lookup"><span data-stu-id="acbc0-145">On the investigation details view, select the **Actions** tab. Any actions that are pending approval are listed here.</span></span>

4. <span data-ttu-id="acbc0-146">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="acbc0-146">Select an item in the list.</span></span>

5. <span data-ttu-id="acbc0-147">Seleccione **aprobar** para realizar la acción recomendada (o **rechazar** para cerrar la investigación sin emprender ninguna acción).</span><span class="sxs-lookup"><span data-stu-id="acbc0-147">Select **Approve** to take the recommended action (or **Reject** to close the investigation without taking action).</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="acbc0-148">Ver los detalles de una alerta relacionada con una investigación</span><span class="sxs-lookup"><span data-stu-id="acbc0-148">View details about an alert related to an investigation</span></span>

<span data-ttu-id="acbc0-149">Ciertos tipos de alertas desencadenan la investigación automática en Office 365.</span><span class="sxs-lookup"><span data-stu-id="acbc0-149">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="acbc0-150">Para obtener más información, vea [alertas](automated-investigation-response-office.md#alerts).</span><span class="sxs-lookup"><span data-stu-id="acbc0-150">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="acbc0-151">Use el siguiente procedimiento para ver los detalles de una alerta asociada a una investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="acbc0-151">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="acbc0-152">Como administrador global de Office 365, administrador de seguridad o lector de seguridad, vaya [https://protection.office.com](https://protection.office.com) a e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="acbc0-152">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="acbc0-153">Esto le llevará al centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="acbc0-153">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="acbc0-154">Vaya a \*\*\*\* > **investigaciones**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="acbc0-154">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="acbc0-155">En la lista de investigaciones, seleccione un elemento en la columna **ID** .</span><span class="sxs-lookup"><span data-stu-id="acbc0-155">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="acbc0-156">Con los detalles de una investigación abierta, seleccione la pestaña **alertas** . Aquí se enumeran las alertas que desencadenaron la investigación.</span><span class="sxs-lookup"><span data-stu-id="acbc0-156">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="acbc0-157">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="acbc0-157">Select an item in the list.</span></span> <span data-ttu-id="acbc0-158">Se abre un control flotante, con detalles sobre la alerta y vínculos a acciones e información adicionales.</span><span class="sxs-lookup"><span data-stu-id="acbc0-158">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="acbc0-159">Revise la información en el control flotante y, en función de la alerta en particular, realice una acción, como **resolver**, **suprimir**o **notificar a los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="acbc0-159">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

    - <span data-ttu-id="acbc0-160">**Resolve** equivale a cerrar una alerta</span><span class="sxs-lookup"><span data-stu-id="acbc0-160">**Resolve** is equivalent to closing an alert</span></span>
    
    - <span data-ttu-id="acbc0-161">**Suprimir** hace que una directiva no desencadene alertas durante un período de tiempo especificado</span><span class="sxs-lookup"><span data-stu-id="acbc0-161">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>
    
    - <span data-ttu-id="acbc0-162">**Notify users** inicia un correo electrónico con las direcciones de correo electrónico de los usuarios que ya se han especificado y permite que el equipo de operaciones de seguridad escriba un mensaje para esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="acbc0-162">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="acbc0-163">(Es similar a enviar un mensaje a los destinatarios mediante el [Explorador de amenazas](threat-explorer.md)).</span><span class="sxs-lookup"><span data-stu-id="acbc0-163">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="acbc0-164">Usar la API de actividad de administración de Office 365 para soluciones de informes personalizadas o de terceros</span><span class="sxs-lookup"><span data-stu-id="acbc0-164">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="acbc0-165">Si su organización usa una solución de informes personalizada o de terceros, puede ver información sobre las investigaciones automatizadas en esa solución mediante la API de actividad de administración 365 de Office.</span><span class="sxs-lookup"><span data-stu-id="acbc0-165">If your organization is using a custom or third-party reporting solution, you can view information about automated investigations in that solution by using the Office 365 Management Activity API.</span></span>

<span data-ttu-id="acbc0-166">Use los siguientes recursos para configurar esto:</span><span class="sxs-lookup"><span data-stu-id="acbc0-166">Use the following resources to set this up:</span></span>

|<span data-ttu-id="acbc0-167">Recurso</span><span class="sxs-lookup"><span data-stu-id="acbc0-167">Resource</span></span>  |<span data-ttu-id="acbc0-168">Descripción</span><span class="sxs-lookup"><span data-stu-id="acbc0-168">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="acbc0-169">Información general de las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="acbc0-169">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="acbc0-170">La API de actividad de administración de Office 365 proporciona información sobre diversas acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Office 365 y Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="acbc0-170">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="acbc0-171">Introducción a las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="acbc0-171">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="acbc0-172">La API de administración 365 de Office usa Azure AD para proporcionar servicios de autenticación para que la aplicación tenga acceso a los datos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="acbc0-172">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="acbc0-173">Siga los pasos de este artículo para configurarlo.</span><span class="sxs-lookup"><span data-stu-id="acbc0-173">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="acbc0-174">Referencia de las API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="acbc0-174">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="acbc0-175">Puede usar la API de actividad de administración de Office 365 para recuperar información sobre las acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Office 365 y Azure AD.</span><span class="sxs-lookup"><span data-stu-id="acbc0-175">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="acbc0-176">Lea este artículo para obtener más información sobre cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="acbc0-176">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="acbc0-177">Esquema de la API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="acbc0-177">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="acbc0-178">Obtenga información general sobre el [esquema común](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) y el [esquema de investigación y respuesta de ATP y la investigación de amenazas de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) para obtener información sobre los tipos de datos específicos disponibles a través de la API de actividad de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="acbc0-178">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="next-steps"></a><span data-ttu-id="acbc0-179">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="acbc0-179">Next steps</span></span>

[<span data-ttu-id="acbc0-180">Más información acerca de las alertas</span><span class="sxs-lookup"><span data-stu-id="acbc0-180">Learn more about alerts</span></span>](../../compliance/alert-policies.md)

[<span data-ttu-id="acbc0-181">Buscar y investigar manualmente el correo electrónico malintencionado que se entregó en Office 365</span><span class="sxs-lookup"><span data-stu-id="acbc0-181">Manually find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

[<span data-ttu-id="acbc0-182">Obtener información sobre AIR en ATP de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="acbc0-182">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

[<span data-ttu-id="acbc0-183">Visite el plan de desarrollo de Microsoft 365 para ver lo que estará próximamente y que se implementará</span><span class="sxs-lookup"><span data-stu-id="acbc0-183">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)