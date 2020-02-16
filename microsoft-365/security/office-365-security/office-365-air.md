---
title: Investigar y responder automáticamente ante amenazas en Office 365
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Empiece a usar la investigación automatizada y las capacidades de respuesta en Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: d45141ce671a4615cb4fd550e36bc7215cd38d51
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42088319"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a><span data-ttu-id="2fe02-104">Investigar y responder automáticamente ante amenazas en Office 365</span><span class="sxs-lookup"><span data-stu-id="2fe02-104">Automatically investigate and respond to threats in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="2fe02-105">Información general</span><span class="sxs-lookup"><span data-stu-id="2fe02-105">Overview</span></span>

<span data-ttu-id="2fe02-106">Según su suscripción, la [protección contra amenazas avanzada de Office 365](office-365-atp.md) puede incluir capacidades de investigación y respuesta automáticas (Air) que pueden ahorrar tiempo y esfuerzo en el equipo de operaciones de seguridad para tratar las alertas y las amenazas.</span><span class="sxs-lookup"><span data-stu-id="2fe02-106">Depending on your subscription, [Office 365 Advanced Threat Protection](office-365-atp.md) can include automated investigation and response (AIR) capabilities that can save your security operations team time and effort in dealing with alerts and threats.</span></span>

- <span data-ttu-id="2fe02-107">Para empezar a usar las capacidades de investigación y respuesta automatizadas en Office 365, use este artículo.</span><span class="sxs-lookup"><span data-stu-id="2fe02-107">To get started using automated investigation and response capabilities in Office 365, use this article.</span></span> 
- <span data-ttu-id="2fe02-108">Para obtener información general sobre cómo funciona, consulte la [investigación y la respuesta automatizadas en Office 365](automated-investigation-response-office.md).</span><span class="sxs-lookup"><span data-stu-id="2fe02-108">To get an overview of how it works, see [Automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span>

> [!TIP]
> <span data-ttu-id="2fe02-109">¿Tiene Microsoft 365 E5 o Microsoft 365 E3 junto con la protección de la identidad y contra amenazas?</span><span class="sxs-lookup"><span data-stu-id="2fe02-109">Do you have Microsoft 365 E5 or Microsoft 365 E3 together with Identity & Threat Protection?</span></span> <span data-ttu-id="2fe02-110">Considere la posibilidad de probar la [investigación y respuesta automatizadas (Air) en la protección contra amenazas de Microsoft](../mtp/mtp-autoir.md).</span><span class="sxs-lookup"><span data-stu-id="2fe02-110">Consider trying [Automated investigation and response (AIR) in Microsoft Threat Protection](../mtp/mtp-autoir.md).</span></span>

<span data-ttu-id="2fe02-111">Con las capacidades de investigación y respuesta automatizadas, cuando se desencadenan determinadas alertas, se inician una o más guías de seguridad y se inicia el proceso de investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="2fe02-111">With automated investigation and response capabilities, when certain alerts are triggered, one or more security playbooks initiate, and the automated investigation process begins.</span></span> <span data-ttu-id="2fe02-112">Durante y después de un proceso de investigación automatizado, su equipo de seguridad puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2fe02-112">During and after an automated investigation process, your security team can do the following:</span></span>

- [<span data-ttu-id="2fe02-113">Ver los detalles de una investigación</span><span class="sxs-lookup"><span data-stu-id="2fe02-113">View the details of an investigation</span></span>](#view-details-of-an-investigation)
- [<span data-ttu-id="2fe02-114">Revisión y aprobación de acciones como resultado de una investigación</span><span class="sxs-lookup"><span data-stu-id="2fe02-114">Review and approve actions as a result of an investigation</span></span>](#review-and-approve-actions) 
- [<span data-ttu-id="2fe02-115">Ver los detalles de una alerta relacionada con una investigación</span><span class="sxs-lookup"><span data-stu-id="2fe02-115">View details about an alert related to an investigation</span></span>](#view-details-about-an-alert-related-to-an-investigation)

> [!IMPORTANT]
> <span data-ttu-id="2fe02-116">Para llevar a cabo las tareas descritas en este artículo, debe tener asignados los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="2fe02-116">To perform the tasks described in this article, you must have appropriate permissions assigned.</span></span> <span data-ttu-id="2fe02-117">Consulte [permisos necesarios para usar la funcionalidad de Air](automated-investigation-response-office.md#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="2fe02-117">See [required permissions to use AIR capabilities](automated-investigation-response-office.md#required-permissions-to-use-air-capabilities).</span></span>

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="2fe02-118">Ver los detalles de una investigación</span><span class="sxs-lookup"><span data-stu-id="2fe02-118">View details of an investigation</span></span>

1. <span data-ttu-id="2fe02-119">Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="2fe02-119">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="2fe02-120">Esto le llevará al centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="2fe02-120">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="2fe02-121">Realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2fe02-121">Do one of the following:</span></span>

    - <span data-ttu-id="2fe02-122">Vaya al \*\*\*\* > **Panel**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="2fe02-122">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="2fe02-123">Esto le llevará al [Panel de seguridad](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="2fe02-123">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="2fe02-124">Los widgets de AIR aparecen en la parte superior del [Panel de seguridad](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="2fe02-124">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="2fe02-125">Seleccione un widget, como un **Resumen de investigaciones**.</span><span class="sxs-lookup"><span data-stu-id="2fe02-125">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="2fe02-126">Vaya a \*\*\*\* > **investigaciones**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="2fe02-126">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="2fe02-127">Cualquiera de estos métodos le lleva a una lista de investigaciones.</span><span class="sxs-lookup"><span data-stu-id="2fe02-127">Either method takes you to a list of investigations.</span></span>

    ![Página principal de investigación para AIR](../../media/air-maininvestigationpage.png) 

3. <span data-ttu-id="2fe02-129">En la lista de investigaciones, seleccione un elemento en la columna **ID** .</span><span class="sxs-lookup"><span data-stu-id="2fe02-129">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="2fe02-130">Se abrirá la página Detalles de la investigación, empezando por el gráfico de investigación en la vista.</span><span class="sxs-lookup"><span data-stu-id="2fe02-130">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![Página de gráfico de investigación de aire](../../media/air-investigationgraphpage.png)

4. <span data-ttu-id="2fe02-132">Use las distintas pestañas para obtener más información sobre la investigación.</span><span class="sxs-lookup"><span data-stu-id="2fe02-132">Use the various tabs to learn more about the investigation.</span></span>

## <a name="review-and-approve-actions"></a><span data-ttu-id="2fe02-133">Revisión y aprobación de acciones</span><span class="sxs-lookup"><span data-stu-id="2fe02-133">Review and approve actions</span></span>

<span data-ttu-id="2fe02-134">En Office 365, las investigaciones automatizadas suelen dar como resultado una o varias acciones recomendadas.</span><span class="sxs-lookup"><span data-stu-id="2fe02-134">In Office 365, automated investigations typically result in one or more recommended actions.</span></span> <span data-ttu-id="2fe02-135">Sin embargo, no se lleva a cabo ninguna acción hasta que la aprueba el equipo de operaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2fe02-135">However, no actions are taken until they are approved by your security operations team.</span></span> <span data-ttu-id="2fe02-136">Use el siguiente procedimiento para revisar y aprobar acciones.</span><span class="sxs-lookup"><span data-stu-id="2fe02-136">Use the following procedure to review and approve actions.</span></span>

1. <span data-ttu-id="2fe02-137">Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="2fe02-137">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> 

2. <span data-ttu-id="2fe02-138">Vaya a \*\*\*\* > **investigaciones**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="2fe02-138">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="2fe02-139">En la lista de investigaciones, seleccione un elemento en la columna **ID** .</span><span class="sxs-lookup"><span data-stu-id="2fe02-139">In the list of investigations, select an item in the **ID** column.</span></span> 

3. <span data-ttu-id="2fe02-140">En la vista detalles de la investigación, seleccione la ficha **acciones** . Aquí se enumeran las acciones pendientes de aprobación.</span><span class="sxs-lookup"><span data-stu-id="2fe02-140">On the investigation details view, select the **Actions** tab. Any actions that are pending approval are listed here.</span></span>

4. <span data-ttu-id="2fe02-141">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="2fe02-141">Select an item in the list.</span></span>

5. <span data-ttu-id="2fe02-142">Seleccione **aprobar** para realizar la acción recomendada (o **rechazar** para cerrar la investigación sin emprender ninguna acción).</span><span class="sxs-lookup"><span data-stu-id="2fe02-142">Select **Approve** to take the recommended action (or **Reject** to close the investigation without taking action).</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="2fe02-143">Ver los detalles de una alerta relacionada con una investigación</span><span class="sxs-lookup"><span data-stu-id="2fe02-143">View details about an alert related to an investigation</span></span>

<span data-ttu-id="2fe02-144">Ciertos tipos de alertas desencadenan la investigación automática en Office 365.</span><span class="sxs-lookup"><span data-stu-id="2fe02-144">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="2fe02-145">Para obtener más información, vea [alertas](automated-investigation-response-office.md#alerts).</span><span class="sxs-lookup"><span data-stu-id="2fe02-145">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="2fe02-146">Use el siguiente procedimiento para ver los detalles de una alerta asociada a una investigación automatizada.</span><span class="sxs-lookup"><span data-stu-id="2fe02-146">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="2fe02-147">Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="2fe02-147">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="2fe02-148">Esto le llevará al centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="2fe02-148">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="2fe02-149">Vaya a \*\*\*\* > **investigaciones**de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="2fe02-149">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="2fe02-150">En la lista de investigaciones, seleccione un elemento en la columna **ID** .</span><span class="sxs-lookup"><span data-stu-id="2fe02-150">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="2fe02-151">Con los detalles de una investigación abierta, seleccione la pestaña **alertas** . Aquí se enumeran las alertas que desencadenaron la investigación.</span><span class="sxs-lookup"><span data-stu-id="2fe02-151">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="2fe02-152">Seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="2fe02-152">Select an item in the list.</span></span> <span data-ttu-id="2fe02-153">Se abre un control flotante, con detalles sobre la alerta y vínculos a acciones e información adicionales.</span><span class="sxs-lookup"><span data-stu-id="2fe02-153">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="2fe02-154">Revise la información en el control flotante y, en función de la alerta en particular, realice una acción, como **resolver**, **suprimir**o **notificar a los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="2fe02-154">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

    - <span data-ttu-id="2fe02-155">**Resolve** equivale a cerrar una alerta</span><span class="sxs-lookup"><span data-stu-id="2fe02-155">**Resolve** is equivalent to closing an alert</span></span>
    
    - <span data-ttu-id="2fe02-156">**Suprimir** hace que una directiva no desencadene alertas durante un período de tiempo especificado</span><span class="sxs-lookup"><span data-stu-id="2fe02-156">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>
    
    - <span data-ttu-id="2fe02-157">**Notify users** inicia un correo electrónico con las direcciones de correo electrónico de los usuarios que ya se han especificado y permite que el equipo de operaciones de seguridad escriba un mensaje para esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="2fe02-157">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="2fe02-158">(Es similar a enviar un mensaje a los destinatarios mediante el [Explorador de amenazas](threat-explorer.md)).</span><span class="sxs-lookup"><span data-stu-id="2fe02-158">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="2fe02-159">Usar la API de actividad de administración de Office 365 para soluciones de informes personalizadas o de terceros</span><span class="sxs-lookup"><span data-stu-id="2fe02-159">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="2fe02-160">Si su organización usa una solución de informes personalizada o de terceros, puede ver información sobre las investigaciones automatizadas en esa solución mediante la API de actividad de administración 365 de Office.</span><span class="sxs-lookup"><span data-stu-id="2fe02-160">If your organization is using a custom or third-party reporting solution, you can view information about automated investigations in that solution by using the Office 365 Management Activity API.</span></span>

<span data-ttu-id="2fe02-161">Use los siguientes recursos para configurar esto:</span><span class="sxs-lookup"><span data-stu-id="2fe02-161">Use the following resources to set this up:</span></span>

|<span data-ttu-id="2fe02-162">Resource</span><span class="sxs-lookup"><span data-stu-id="2fe02-162">Resource</span></span>  |<span data-ttu-id="2fe02-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="2fe02-163">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="2fe02-164">Información general de las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="2fe02-164">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="2fe02-165">La API de actividad de administración de Office 365 proporciona información sobre diversas acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Office 365 y Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2fe02-165">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="2fe02-166">Introducción a las API de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="2fe02-166">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="2fe02-167">La API de administración 365 de Office usa Azure AD para proporcionar servicios de autenticación para que la aplicación tenga acceso a los datos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2fe02-167">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="2fe02-168">Siga los pasos de este artículo para configurarlo.</span><span class="sxs-lookup"><span data-stu-id="2fe02-168">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="2fe02-169">Referencia de las API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="2fe02-169">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="2fe02-170">Puede usar la API de actividad de administración de Office 365 para recuperar información sobre las acciones y eventos de usuario, administrador, sistema y Directiva de los registros de actividad de Office 365 y Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2fe02-170">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="2fe02-171">Lea este artículo para obtener más información sobre cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="2fe02-171">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="2fe02-172">Esquema de la API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="2fe02-172">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="2fe02-173">Obtenga información general sobre el [esquema común](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) y el [esquema de investigación y respuesta de ATP y la investigación de amenazas de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) para obtener información sobre los tipos de datos específicos disponibles a través de la API de actividad de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2fe02-173">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="next-steps"></a><span data-ttu-id="2fe02-174">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="2fe02-174">Next steps</span></span>

- [<span data-ttu-id="2fe02-175">Descubra cómo obtener acceso a AIR y ver los permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="2fe02-175">Find out how to get AIR and see required permissions</span></span>](automated-investigation-response-office.md#how-to-get-air)
- [<span data-ttu-id="2fe02-176">Más información acerca de las alertas</span><span class="sxs-lookup"><span data-stu-id="2fe02-176">Learn more about alerts</span></span>](../../compliance/alert-policies.md)
- [<span data-ttu-id="2fe02-177">Buscar y investigar manualmente el correo electrónico malintencionado que se entregó en Office 365</span><span class="sxs-lookup"><span data-stu-id="2fe02-177">Manually find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="2fe02-178">Obtener información sobre AIR en ATP de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="2fe02-178">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [<span data-ttu-id="2fe02-179">Visite el plan de desarrollo de Microsoft 365 para ver lo que estará próximamente y que se implementará</span><span class="sxs-lookup"><span data-stu-id="2fe02-179">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
