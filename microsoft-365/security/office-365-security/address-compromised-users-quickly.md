---
title: Dirigir las cuentas de usuario en peligro con investigación y respuesta automatizadas
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección, protección, riesgo
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
ms.date: 02/25/2020
description: Obtenga información acerca de cómo acelerar el proceso de detección y direccionamiento de cuentas de usuario en peligro con capacidades automatizadas de investigación y respuesta en Microsoft defender para Office 365 plan 2.
ms.openlocfilehash: 80e4529f864d83d2a1711007f0f095de39955e68
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357916"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="37c3c-104">Dirigir las cuentas de usuario en peligro con investigación y respuesta automatizadas</span><span class="sxs-lookup"><span data-stu-id="37c3c-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="37c3c-105">[Microsoft defender para Office 365 plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) incluye capacidades [de investigación y respuesta automáticas](office-365-air.md) (Air) eficaces.</span><span class="sxs-lookup"><span data-stu-id="37c3c-105">[Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="37c3c-106">Estas capacidades pueden guardar el equipo de operaciones de seguridad en gran cantidad de tiempo y esfuerzo relacionados con las amenazas.</span><span class="sxs-lookup"><span data-stu-id="37c3c-106">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="37c3c-107">Microsoft sigue mejorando las capacidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="37c3c-107">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="37c3c-108">Recientemente, las capacidades de AIR se mejoraron para incluir una guía de seguridad de usuario en peligro (actualmente en versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="37c3c-108">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="37c3c-109">Lea este artículo para obtener más información acerca de la guía de seguridad de usuario comprometida.</span><span class="sxs-lookup"><span data-stu-id="37c3c-109">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="37c3c-110">Y ve la entrada de blog [acelerar el tiempo de espera para detectar y responder a la puesta en peligro del usuario y limitar el ámbito de infracción con Microsoft defender para Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="37c3c-110">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![Investigación automatizada para un usuario en peligro](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="37c3c-112">La guía de seguridad de usuario comprometida permite que el equipo de seguridad de su organización:</span><span class="sxs-lookup"><span data-stu-id="37c3c-112">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="37c3c-113">Acelerar la detección de las cuentas de usuario en peligro;</span><span class="sxs-lookup"><span data-stu-id="37c3c-113">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="37c3c-114">Limitar el ámbito de una infracción cuando una cuenta está en peligro; y</span><span class="sxs-lookup"><span data-stu-id="37c3c-114">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="37c3c-115">Responder a los usuarios comprometidos de forma más eficaz y eficiente.</span><span class="sxs-lookup"><span data-stu-id="37c3c-115">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="37c3c-116">Alertas de usuario en peligro</span><span class="sxs-lookup"><span data-stu-id="37c3c-116">Compromised user alerts</span></span>

<span data-ttu-id="37c3c-117">Cuando una cuenta de usuario se ve comprometida, se producen comportamientos atípicos o anómalos.</span><span class="sxs-lookup"><span data-stu-id="37c3c-117">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="37c3c-118">Por ejemplo, los mensajes de suplantación de identidad (phishing) y correo no deseado pueden enviarse internamente desde una cuenta de usuario de confianza.</span><span class="sxs-lookup"><span data-stu-id="37c3c-118">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="37c3c-119">Defender para Office 365 puede detectar estas anomalías en los patrones de correo electrónico y la actividad de colaboración dentro de Office 365.</span><span class="sxs-lookup"><span data-stu-id="37c3c-119">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="37c3c-120">Cuando esto ocurre, se desencadenan alertas y se inicia el proceso de mitigación de amenazas.</span><span class="sxs-lookup"><span data-stu-id="37c3c-120">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="37c3c-121">Por ejemplo, a continuación se muestra una alerta que se ha desencadenado debido al envío de correo sospechoso:</span><span class="sxs-lookup"><span data-stu-id="37c3c-121">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![Alerta desencadenada por un envío de correo electrónico sospechoso](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="37c3c-123">Y este es un ejemplo de una alerta que se ha desencadenado cuando se ha alcanzado el límite de envío de un usuario:</span><span class="sxs-lookup"><span data-stu-id="37c3c-123">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![Alerta desencadenada por el límite de envío alcanzado](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="37c3c-125">Investigar y responder a un usuario comprometido</span><span class="sxs-lookup"><span data-stu-id="37c3c-125">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="37c3c-126">Cuando una cuenta de usuario se ve comprometida, se desencadenan alertas.</span><span class="sxs-lookup"><span data-stu-id="37c3c-126">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="37c3c-127">Y, en algunos casos, la cuenta de usuario está bloqueada y se evita que se envíen mensajes de correo electrónico adicionales hasta que el problema se resuelva por el equipo de operaciones de seguridad de la organización.</span><span class="sxs-lookup"><span data-stu-id="37c3c-127">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="37c3c-128">En otros casos, se inicia una investigación automatizada que puede dar como resultado acciones recomendadas que el equipo de seguridad debe llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="37c3c-128">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="37c3c-129">Ver e investigar usuarios restringidos</span><span class="sxs-lookup"><span data-stu-id="37c3c-129">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="37c3c-130">Ver detalles sobre las investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="37c3c-130">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="37c3c-131">Debe tener los permisos adecuados para realizar las siguientes tareas.</span><span class="sxs-lookup"><span data-stu-id="37c3c-131">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="37c3c-132">Consulte [permisos necesarios para usar la funcionalidad de Air](office-365-air.md#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="37c3c-132">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="37c3c-133">Ver e investigar usuarios restringidos</span><span class="sxs-lookup"><span data-stu-id="37c3c-133">View and investigate restricted users</span></span>

<span data-ttu-id="37c3c-134">Tiene algunas opciones para desplazarse a una lista de usuarios restringidos.</span><span class="sxs-lookup"><span data-stu-id="37c3c-134">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="37c3c-135">Por ejemplo, en el centro de seguridad & cumplimiento, puede ir a **Threat management**  >  **Review**  >  **los usuarios restringidos** de revisión de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="37c3c-135">For example, in the Security & Compliance Center, you can go to **Threat management** > **Review** > **Restricted Users**.</span></span> <span data-ttu-id="37c3c-136">El siguiente procedimiento describe la navegación mediante el panel de **alertas** , que es una buena forma de ver los distintos tipos de alertas que se pueden haber desencadenado.</span><span class="sxs-lookup"><span data-stu-id="37c3c-136">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="37c3c-137">Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="37c3c-137">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="37c3c-138">En el panel de navegación, elija Panel de **alertas**  >  **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="37c3c-138">In the navigation pane, choose **Alerts** > **Dashboard**.</span></span>

3. <span data-ttu-id="37c3c-139">En el widget **otras alertas** , seleccione **usuarios restringidos**.</span><span class="sxs-lookup"><span data-stu-id="37c3c-139">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![Widget de otras alertas](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="37c3c-141">Se abrirá la lista de usuarios restringidos.</span><span class="sxs-lookup"><span data-stu-id="37c3c-141">This opens the list of restricted users.</span></span>

   ![Usuarios restringidos en Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="37c3c-143">Seleccione una cuenta de usuario en la lista para ver los detalles y realizar acciones, como [la liberación del usuario restringido](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="37c3c-143">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="37c3c-144">Ver detalles sobre las investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="37c3c-144">View details about automated investigations</span></span>

<span data-ttu-id="37c3c-145">Una vez iniciada una investigación automatizada, puede ver los detalles y los resultados en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="37c3c-145">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="37c3c-146">Vaya a investigaciones de **Administración de amenazas**  >  **Investigations** y, a continuación, seleccione una investigación para ver sus detalles.</span><span class="sxs-lookup"><span data-stu-id="37c3c-146">Go to **Threat management** > **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="37c3c-147">Para obtener más información, consulte [Ver detalles de una investigación](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="37c3c-147">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="37c3c-148">Tenga en cuenta los siguientes puntos</span><span class="sxs-lookup"><span data-stu-id="37c3c-148">Keep the following points in mind</span></span>

- <span data-ttu-id="37c3c-149">**Mantente al tanto de tus avisos**.</span><span class="sxs-lookup"><span data-stu-id="37c3c-149">**Stay on top of your alerts**.</span></span> <span data-ttu-id="37c3c-150">Como sabe, cuanto más tiempo no se detecte un riesgo, mayor será el potencial de impacto y de costos generalizados para la organización, los clientes y los asociados.</span><span class="sxs-lookup"><span data-stu-id="37c3c-150">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="37c3c-151">La detección temprana y la respuesta oportuna son críticas para mitigar las amenazas y, especialmente, cuando la cuenta de un usuario está en peligro.</span><span class="sxs-lookup"><span data-stu-id="37c3c-151">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="37c3c-152">**Automatización ayuda al equipo de operaciones de seguridad, pero no sustituye a él**.</span><span class="sxs-lookup"><span data-stu-id="37c3c-152">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="37c3c-153">Las capacidades automatizadas de investigación y respuesta pueden detectar los usuarios comprometidos en un primer momento, pero es probable que el equipo de operaciones de seguridad deba participar y realizar alguna investigación y corrección.</span><span class="sxs-lookup"><span data-stu-id="37c3c-153">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="37c3c-154">¿Necesita ayuda con esto?</span><span class="sxs-lookup"><span data-stu-id="37c3c-154">Need some help with this?</span></span> <span data-ttu-id="37c3c-155">Consulte [acciones de revisión y aprobación](air-review-approve-pending-completed-actions.md).</span><span class="sxs-lookup"><span data-stu-id="37c3c-155">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="37c3c-156">**No confíe en una alerta de inicio de sesión sospechosa como el único indicador**.</span><span class="sxs-lookup"><span data-stu-id="37c3c-156">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="37c3c-157">Cuando una cuenta de usuario está en peligro, puede o no activar una alerta de inicio de sesión sospechosa.</span><span class="sxs-lookup"><span data-stu-id="37c3c-157">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="37c3c-158">A veces, es la serie de actividades que se producen después de que se haya comprometido una cuenta que desencadena una alerta.</span><span class="sxs-lookup"><span data-stu-id="37c3c-158">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="37c3c-159">¿Desea saber más sobre las alertas?</span><span class="sxs-lookup"><span data-stu-id="37c3c-159">Want to know more about alerts?</span></span> <span data-ttu-id="37c3c-160">Consulte [directivas de alerta](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span><span class="sxs-lookup"><span data-stu-id="37c3c-160">See [Alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="37c3c-161">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="37c3c-161">Next steps</span></span>

- [<span data-ttu-id="37c3c-162">Revisar los permisos necesarios para usar la funcionalidad de AIR</span><span class="sxs-lookup"><span data-stu-id="37c3c-162">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="37c3c-163">Buscar e investigar correo electrónico malintencionado en Office 365</span><span class="sxs-lookup"><span data-stu-id="37c3c-163">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="37c3c-164">Obtener información sobre AIR en Microsoft defender para el punto de conexión</span><span class="sxs-lookup"><span data-stu-id="37c3c-164">Learn about AIR in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="37c3c-165">Visite el plan de desarrollo de Microsoft 365 para ver lo que estará próximamente y que se implementará</span><span class="sxs-lookup"><span data-stu-id="37c3c-165">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
