---
title: Solucionar cuentas de usuario comprometidas con investigación y respuesta automatizadas
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección, en peligro
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Obtenga información sobre cómo acelerar el proceso de detección y tratamiento de cuentas de usuario comprometidas con capacidades automatizadas de investigación y respuesta en Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1dda8c9b4aec30fd35efa153aaf032eee23b5e8a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288746"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="a3b5c-104">Solucionar cuentas de usuario comprometidas con investigación y respuesta automatizadas</span><span class="sxs-lookup"><span data-stu-id="a3b5c-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a3b5c-105">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="a3b5c-105">**Applies to**</span></span>
- [<span data-ttu-id="a3b5c-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a3b5c-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a3b5c-107">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a3b5c-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a3b5c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a3b5c-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


<span data-ttu-id="a3b5c-109">El Plan 2 de Microsoft Defender para [Office 365](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) incluye potentes capacidades de investigación y [respuesta automatizadas](office-365-air.md) (AIR).</span><span class="sxs-lookup"><span data-stu-id="a3b5c-109">[Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="a3b5c-110">Estas funcionalidades pueden ahorrarle mucho tiempo y esfuerzo al equipo de operaciones de seguridad que se enfrenta a las amenazas.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-110">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="a3b5c-111">Microsoft continúa mejorando las capacidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-111">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="a3b5c-112">Recientemente, las capacidades de AIR se han mejorado para incluir un libro de juegos de seguridad de usuario comprometido (actualmente en versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="a3b5c-112">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="a3b5c-113">Lea este artículo para obtener más información sobre el libro de juegos de seguridad de usuario comprometido.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-113">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="a3b5c-114">Vea la entrada de blog Acelerar el tiempo para detectar y responder al compromiso del usuario y limitar el ámbito de infracción con [Microsoft Defender para Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-114">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![Investigación automatizada de un usuario comprometido](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="a3b5c-116">El libro de juegos de seguridad de usuario comprometido permite al equipo de seguridad de su organización:</span><span class="sxs-lookup"><span data-stu-id="a3b5c-116">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="a3b5c-117">Acelerar la detección de cuentas de usuario comprometidas;</span><span class="sxs-lookup"><span data-stu-id="a3b5c-117">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="a3b5c-118">Limitar el ámbito de una infracción cuando se pone en peligro una cuenta; y</span><span class="sxs-lookup"><span data-stu-id="a3b5c-118">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="a3b5c-119">Responder a los usuarios comprometidos de forma más eficaz y eficaz.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-119">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="a3b5c-120">Alertas de usuario comprometidas</span><span class="sxs-lookup"><span data-stu-id="a3b5c-120">Compromised user alerts</span></span>

<span data-ttu-id="a3b5c-121">Cuando una cuenta de usuario está en peligro, se producen comportamientos atípicos o anómalos.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-121">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="a3b5c-122">Por ejemplo, los mensajes de suplantación de identidad (phishing) y correo no deseado pueden enviarse internamente desde una cuenta de usuario de confianza.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-122">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="a3b5c-123">Defender para Office 365 puede detectar estas anomalías en los patrones de correo electrónico y la actividad de colaboración en Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-123">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="a3b5c-124">Cuando esto sucede, se desencadenan alertas y comienza el proceso de mitigación de amenazas.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-124">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="a3b5c-125">Por ejemplo, esta es una alerta que se desencadenó debido al envío sospechoso de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="a3b5c-125">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![Alerta activada debido al envío sospechoso de correo electrónico](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="a3b5c-127">Y este es un ejemplo de una alerta que se desencadenó cuando se alcanzó un límite de envío para un usuario:</span><span class="sxs-lookup"><span data-stu-id="a3b5c-127">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![Alerta desencadenada por el límite de envío alcanzado](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="a3b5c-129">Investigar y responder a un usuario comprometido</span><span class="sxs-lookup"><span data-stu-id="a3b5c-129">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="a3b5c-130">Cuando una cuenta de usuario está en peligro, se desencadenan alertas.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-130">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="a3b5c-131">Y, en algunos casos, se bloquea esa cuenta de usuario e impide que se envíen más mensajes de correo electrónico hasta que el equipo de operaciones de seguridad de la organización resuelva el problema.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-131">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="a3b5c-132">En otros casos, se inicia una investigación automatizada que puede dar como resultado acciones recomendadas que el equipo de seguridad debe realizar.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-132">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="a3b5c-133">Ver e investigar usuarios restringidos</span><span class="sxs-lookup"><span data-stu-id="a3b5c-133">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="a3b5c-134">Ver detalles sobre investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="a3b5c-134">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="a3b5c-135">Debe tener los permisos adecuados para realizar las siguientes tareas.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-135">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="a3b5c-136">Vea [los permisos necesarios para usar las funcionalidades de AIR.](office-365-air.md#required-permissions-to-use-air-capabilities)</span><span class="sxs-lookup"><span data-stu-id="a3b5c-136">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="a3b5c-137">Ver e investigar usuarios restringidos</span><span class="sxs-lookup"><span data-stu-id="a3b5c-137">View and investigate restricted users</span></span>

<span data-ttu-id="a3b5c-138">Tienes algunas opciones para navegar a una lista de usuarios restringidos.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-138">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="a3b5c-139">Por ejemplo, en el Centro de seguridad & cumplimiento, puede ir a Administración **de** amenazas \> **Revisar** \> **usuarios restringidos.**</span><span class="sxs-lookup"><span data-stu-id="a3b5c-139">For example, in the Security & Compliance Center, you can go to **Threat management** \> **Review** \> **Restricted Users**.</span></span> <span data-ttu-id="a3b5c-140">En el siguiente procedimiento  se describe la navegación mediante el panel alertas, que es una buena manera de ver varios tipos de alertas que se podrían haber desencadenado.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-140">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="a3b5c-141">Vaya a <https://protection.office.com> e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-141">Go to <https://protection.office.com> and sign in.</span></span>

2. <span data-ttu-id="a3b5c-142">En el panel de navegación, elija **Panel de** \> **alertas.**</span><span class="sxs-lookup"><span data-stu-id="a3b5c-142">In the navigation pane, choose **Alerts** \> **Dashboard**.</span></span>

3. <span data-ttu-id="a3b5c-143">En el widget **Otras alertas,** elija **Usuarios restringidos.**</span><span class="sxs-lookup"><span data-stu-id="a3b5c-143">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![Widget Otras alertas](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="a3b5c-145">Se abrirá la lista de usuarios restringidos.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-145">This opens the list of restricted users.</span></span>

   ![Usuarios restringidos en Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="a3b5c-147">Seleccione una cuenta de usuario en la lista para ver los detalles y tomar medidas, como liberar [el usuario restringido.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="a3b5c-147">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="a3b5c-148">Ver detalles sobre investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="a3b5c-148">View details about automated investigations</span></span>

<span data-ttu-id="a3b5c-149">Cuando haya comenzado una investigación automatizada, puede ver sus detalles y resultados en el Centro de & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-149">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="a3b5c-150">Vaya  a \> **Investigaciones de administración de** amenazas y, a continuación, seleccione una investigación para ver sus detalles.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-150">Go to **Threat management** \> **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="a3b5c-151">Para obtener más información, [vea Ver detalles de una investigación.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="a3b5c-151">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="a3b5c-152">Tenga en cuenta lo siguiente</span><span class="sxs-lookup"><span data-stu-id="a3b5c-152">Keep the following points in mind</span></span>

- <span data-ttu-id="a3b5c-153">**Manténgase al tanto de las alertas.**</span><span class="sxs-lookup"><span data-stu-id="a3b5c-153">**Stay on top of your alerts**.</span></span> <span data-ttu-id="a3b5c-154">Como ya sabe, cuanto más tiempo no se detecte un compromiso, mayor será el potencial de un impacto y costo generalizados para su organización, clientes y partners.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-154">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="a3b5c-155">La detección temprana y la respuesta oportuna son fundamentales para mitigar las amenazas, especialmente cuando la cuenta de un usuario está en peligro.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-155">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="a3b5c-156">**La automatización ayuda, pero no reemplaza,** al equipo de operaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-156">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="a3b5c-157">Las capacidades automatizadas de investigación y respuesta pueden detectar un usuario comprometido desde el principio, pero es probable que el equipo de operaciones de seguridad deba implicarse y realizar alguna investigación y corrección.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-157">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="a3b5c-158">¿Necesita ayuda con esto?</span><span class="sxs-lookup"><span data-stu-id="a3b5c-158">Need some help with this?</span></span> <span data-ttu-id="a3b5c-159">Vea [Revisar y aprobar acciones.](air-review-approve-pending-completed-actions.md)</span><span class="sxs-lookup"><span data-stu-id="a3b5c-159">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="a3b5c-160">**No confíes en una alerta de inicio de sesión sospechoso como tu único indicador.**</span><span class="sxs-lookup"><span data-stu-id="a3b5c-160">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="a3b5c-161">Cuando una cuenta de usuario está en peligro, es posible que desencadene o no una alerta de inicio de sesión sospechoso.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-161">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="a3b5c-162">A veces, es la serie de actividades que se producen después de que una cuenta está en peligro que desencadena una alerta.</span><span class="sxs-lookup"><span data-stu-id="a3b5c-162">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="a3b5c-163">¿Desea obtener más información sobre las alertas?</span><span class="sxs-lookup"><span data-stu-id="a3b5c-163">Want to know more about alerts?</span></span> <span data-ttu-id="a3b5c-164">Vea [Directivas de alerta.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a3b5c-164">See [Alert policies](../../compliance/alert-policies.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a3b5c-165">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a3b5c-165">Next steps</span></span>

- [<span data-ttu-id="a3b5c-166">Revisar los permisos necesarios para usar las funcionalidades de AIR</span><span class="sxs-lookup"><span data-stu-id="a3b5c-166">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="a3b5c-167">Buscar e investigar correo electrónico malintencionado en Office 365</span><span class="sxs-lookup"><span data-stu-id="a3b5c-167">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="a3b5c-168">Más información sobre AIR en Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="a3b5c-168">Learn about AIR in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="a3b5c-169">Visite el mapa de ruta de Microsoft 365 para ver lo que estará próximamente y su implementación</span><span class="sxs-lookup"><span data-stu-id="a3b5c-169">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
