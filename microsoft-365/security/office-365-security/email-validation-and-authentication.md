---
title: Autenticación de correo electrónico en Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Los administradores pueden obtener información sobre cómo EOP usa la autenticación de correo electrónico (SPF, DKIM y DMARC) para ayudar a evitar la suplantación de identidad, el phishing y el correo no deseado.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d1e0fbe8a00b17e871adf65f86a337a0a94493ed
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286518"
---
# <a name="email-authentication-in-eop"></a><span data-ttu-id="6122c-103">Autenticación de correo electrónico en EOP</span><span class="sxs-lookup"><span data-stu-id="6122c-103">Email authentication in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6122c-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="6122c-104">**Applies to**</span></span>
- [<span data-ttu-id="6122c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6122c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6122c-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="6122c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="6122c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6122c-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


<span data-ttu-id="6122c-108">La autenticación de correo electrónico (conocida también como validación de correo electrónico) es un grupo de normas que intentan detener la suplantación (mensajes de correo electrónico de remitentes falsos).</span><span class="sxs-lookup"><span data-stu-id="6122c-108">Email authentication (also known as email validation) is a group of standards that tries to stop spoofing (email messages from forged senders).</span></span> <span data-ttu-id="6122c-109">En todas las organizaciones de Microsoft 365, EOP usa estos estándares para comprobar el correo electrónico entrante:</span><span class="sxs-lookup"><span data-stu-id="6122c-109">In all Microsoft 365 organizations, EOP uses these standards to verify inbound email:</span></span>

- [<span data-ttu-id="6122c-110">SPF</span><span class="sxs-lookup"><span data-stu-id="6122c-110">SPF</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

- [<span data-ttu-id="6122c-111">DKIM</span><span class="sxs-lookup"><span data-stu-id="6122c-111">DKIM</span></span>](use-dkim-to-validate-outbound-email.md)

- [<span data-ttu-id="6122c-112">DMARC</span><span class="sxs-lookup"><span data-stu-id="6122c-112">DMARC</span></span>](use-dmarc-to-validate-email.md)

<span data-ttu-id="6122c-113">La autenticación de correo electrónico comprueba que los mensajes de correo electrónico de un remitente (por ejemplo, laura@contoso.com) son legítimos y provienen de fuentes previstas para ese dominio de correo electrónico (por ejemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6122c-113">Email authentication verifies that email messages from a sender (for example, laura@contoso.com) are legitimate and come from expected sources for that email domain (for example, contoso.com.)</span></span>

<span data-ttu-id="6122c-114">En el resto de este artículo, se explica cómo funcionan estas tecnologías y cómo EOP las usa para comprobar el correo electrónico entrante.</span><span class="sxs-lookup"><span data-stu-id="6122c-114">The rest of this article explains how these technologies work, and how EOP uses them to check inbound email.</span></span>

## <a name="use-email-authentication-to-help-prevent-spoofing"></a><span data-ttu-id="6122c-115">Uso de la autenticación de correo electrónico para ayudar a evitar la suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6122c-115">Use email authentication to help prevent spoofing</span></span>

<span data-ttu-id="6122c-116">DMARC impide la suplantación electrónica mediante el examen de la dirección **De** en mensajes.</span><span class="sxs-lookup"><span data-stu-id="6122c-116">DMARC prevents spoofing by examining the **From** address in messages.</span></span> <span data-ttu-id="6122c-117">La dirección **De** es la dirección de correo electrónico del remitente que verán los usuarios en su cliente de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6122c-117">The **From** address is the sender's email address that users see in their email client.</span></span> <span data-ttu-id="6122c-118">Las organizaciones de correo electrónico de destino también pueden comprobar que el dominio de correo electrónico ha pasado SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="6122c-118">Destination email organizations can also verify that the email domain has passed SPF or DKIM.</span></span> <span data-ttu-id="6122c-119">Es decir, el dominio se ha autenticado y, por tanto, la dirección de correo del remitente no está suplantada.</span><span class="sxs-lookup"><span data-stu-id="6122c-119">In other words, the domain has been authenticated and therefore the sender's email address is not spoofed.</span></span>

<span data-ttu-id="6122c-120">Sin embargo, los registros DNS para SPF, DKIM y DMARC (denominados directivas de autenticación de correo electrónico) son opcionales.</span><span class="sxs-lookup"><span data-stu-id="6122c-120">However, DNS records for SPF, DKIM, and DMARC (collectively known as email authentication policies) are optional.</span></span> <span data-ttu-id="6122c-121">Los dominios con directivas de autenticación de correo electrónico seguras como microsoft.com y skype.com están protegidos frente a la suplantación electrónica. </span><span class="sxs-lookup"><span data-stu-id="6122c-121">Domains with strong email authentication policies like microsoft.com and skype.com are protected from spoofing.</span></span> <span data-ttu-id="6122c-122">Sin embargo, los dominios con directivas de autenticación de correo electrónico más débiles, o sin directivas, son los principales objetivos para la suplantación.</span><span class="sxs-lookup"><span data-stu-id="6122c-122">But domains with weaker email authentication policies, or no policy at all, are prime targets for being spoofed.</span></span>

<span data-ttu-id="6122c-123">En marzo de 2018, sólo un 9 % de los dominios de las empresas en la Fortune 500 publicaron directivas de autenticación de correo electrónico seguras.</span><span class="sxs-lookup"><span data-stu-id="6122c-123">As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies.</span></span> <span data-ttu-id="6122c-124">Un atacante podría suplantar electrónicamente al 91 % restante de empresas.</span><span class="sxs-lookup"><span data-stu-id="6122c-124">The remaining 91% of companies might be spoofed by an attacker.</span></span> <span data-ttu-id="6122c-125">A no ser que haya otro mecanismo de filtrado de correo electrónico en contexto, el correo electrónico de los remitentes falsos de estos dominios podría entregarse a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6122c-125">Unless some other email filtering mechanism is in-place, email from spoofed senders in these domains might be delivered to users.</span></span>

![Directivas DMARC de las empresas en Fortune 500](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

<span data-ttu-id="6122c-127">La proporción de pequeñas y medianas empresas que publican directivas de autenticación de correo electrónico seguras es menor.</span><span class="sxs-lookup"><span data-stu-id="6122c-127">The proportion of small-to-medium sized companies that publish strong email authentication policies is smaller.</span></span> <span data-ttu-id="6122c-128">Y el número es aún más pequeño para los dominios de correo electrónico fuera de Norteamérica y Europa occidental.</span><span class="sxs-lookup"><span data-stu-id="6122c-128">And the number is even smaller for email domains outside North America and western Europe.</span></span>

<span data-ttu-id="6122c-129">La falta de directivas de autenticación de correo electrónico seguras es un gran problema.</span><span class="sxs-lookup"><span data-stu-id="6122c-129">Lack of strong email authentication policies is a large problem.</span></span> <span data-ttu-id="6122c-130">Aunque es posible que las organizaciones no sepan cómo funciona la autenticación de correo electrónico, los atacantes si lo saben y se aprovechan de ello.</span><span class="sxs-lookup"><span data-stu-id="6122c-130">W while organizations might not understand how email authentication works, attackers fully understand, and they take advantage.</span></span> <span data-ttu-id="6122c-131">Debido a preocupaciones con respecto al phishing y a una adopción de directivas de autenticación de correo electrónico seguras tan limitada, Microsoft usa *autenticación de correo electrónico implícita* para comprobar el correo electrónico entrante.</span><span class="sxs-lookup"><span data-stu-id="6122c-131">Because of phishing concerns and the limited adoption of strong email authentication policies, Microsoft uses *implicit email authentication* to check inbound email.</span></span>

<span data-ttu-id="6122c-132">La autenticación de correo electrónico implícita es una extensión de las directivas de autenticación de correo electrónico habituales.</span><span class="sxs-lookup"><span data-stu-id="6122c-132">Implicit email authentication is an extension of regular email authentication policies.</span></span> <span data-ttu-id="6122c-133">Entre estas extensiones se incluyen: la reputación del remitente, el historial del remitente, el historial del destinatario, el análisis de comportamiento y otras técnicas avanzadas.</span><span class="sxs-lookup"><span data-stu-id="6122c-133">These extensions include: sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques.</span></span> <span data-ttu-id="6122c-134">En ausencia de otras señales de estas extensiones, los mensajes enviados desde dominios que no usan directivas de autenticación de correo electrónico se marcarán como suplantación electrónica.</span><span class="sxs-lookup"><span data-stu-id="6122c-134">In the absence of other signals from these extensions, messages sent from domains that don't use email authentication policies will be marked as spoof.</span></span>

<span data-ttu-id="6122c-135">Para ver el anuncio general de Microsoft, vea [Un mar de phishing, parte 2: Protección contra la suplantación de identidad mejorada en Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span><span class="sxs-lookup"><span data-stu-id="6122c-135">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>

## <a name="composite-authentication"></a><span data-ttu-id="6122c-136">Autenticación compuesta</span><span class="sxs-lookup"><span data-stu-id="6122c-136">Composite authentication</span></span>

<span data-ttu-id="6122c-137">Si un dominio no tiene registros de SPF, DKIM y DMARC tradicionales, esas comprobaciones de registro no comunican suficiente información de estado de autenticación.</span><span class="sxs-lookup"><span data-stu-id="6122c-137">If a domain doesn't have traditional SPF, DKIM, and DMARC records, those record checks don't communicate enough authentication status information.</span></span> <span data-ttu-id="6122c-138">Por lo tanto, Microsoft ha desarrollado un algoritmo para la autenticación de correo electrónico implícita.</span><span class="sxs-lookup"><span data-stu-id="6122c-138">Therefore, Microsoft has developed an algorithm for implicit email authentication.</span></span> <span data-ttu-id="6122c-139">Este algoritmo combina varias señales en un único valor denominado _autenticación compuesta_ (`compauth` para abreviar).</span><span class="sxs-lookup"><span data-stu-id="6122c-139">This algorithm combines multiple signals into a single value called _composite authentication_, or `compauth` for short.</span></span> <span data-ttu-id="6122c-140">El valor de `compauth` se marca en el encabezado **Authentication-Results** en los encabezados de mensaje.</span><span class="sxs-lookup"><span data-stu-id="6122c-140">The `compauth` value is stamped into the **Authentication-Results** header in the message headers.</span></span>

```text
Authentication-Results:
   compauth=<fail | pass | softpass | none> reason=<yyy>
```

<span data-ttu-id="6122c-141">Estos valores se explican en [Encabezado de mensaje Authentication-results](anti-spam-message-headers.md#authentication-results-message-header).</span><span class="sxs-lookup"><span data-stu-id="6122c-141">These values are explained at [Authentication-results message header](anti-spam-message-headers.md#authentication-results-message-header).</span></span>

<span data-ttu-id="6122c-142">Al examinar los encabezados de mensajes, los administradores o incluso los usuarios finales podrán determinar cómo Microsoft 365 determinó que el remitente está falsificado.</span><span class="sxs-lookup"><span data-stu-id="6122c-142">By examining the message headers, admins or even end users can determine how Microsoft 365 determined that the sender is spoofed.</span></span>

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="6122c-143">Por qué la autenticación de correo electrónico no siempre es suficiente para detener la suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="6122c-143">Why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="6122c-144">Depender solo de los registros de autenticación de correo electrónico para determinar si un mensaje entrante está falsificado tiene las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="6122c-144">Relying only on email authentication records to determine if an incoming message is spoofed has the following limitations:</span></span>

- <span data-ttu-id="6122c-145">Es posible que el dominio remitente carezca de los registros DNS necesarios o que los registros no estén configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="6122c-145">The sending domain might lack the required DNS records, or the records are incorrectly configured.</span></span>

- <span data-ttu-id="6122c-146">El dominio de origen ha configurado correctamente los registros DNS, pero ese dominio no coincide con el dominio de la dirección De.</span><span class="sxs-lookup"><span data-stu-id="6122c-146">The source domain has correctly configured DNS records, but that domain doesn't match the domain in the From address.</span></span> <span data-ttu-id="6122c-147">SPF y DKIM no requieren que el dominio se use en la dirección De.</span><span class="sxs-lookup"><span data-stu-id="6122c-147">SPF and DKIM don't require the domain to be used in the From address.</span></span> <span data-ttu-id="6122c-148">Los intrusos y los servicios legítimos pueden registrar un dominio, configurar SPF y DKIM para el dominio, y usar un dominio completamente distinto en la dirección De.</span><span class="sxs-lookup"><span data-stu-id="6122c-148">Attackers or legitimate services can register a domain, configure SPF and DKIM for the domain, and use a completely different domain in the From address.</span></span> <span data-ttu-id="6122c-149">Los mensajes de los remitentes de este dominio pasarán SPF y DKIM.</span><span class="sxs-lookup"><span data-stu-id="6122c-149">Messages from senders in this domain will pass SPF and DKIM.</span></span>

<span data-ttu-id="6122c-150">Las autenticaciones compuestas pueden superar estas limitaciones pasando mensajes que, de otra forma, no superarían las comprobaciones de autenticación de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6122c-150">Composite authentication can address these limitations by passing messages that would otherwise fail email authentication checks.</span></span>

<span data-ttu-id="6122c-151">Para simplificar, los ejemplos siguientes se centran en los resultados de la autenticación de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6122c-151">For simplicity, the following examples concentrate on email authentication results.</span></span> <span data-ttu-id="6122c-152">Otros factores de inteligencia de back-end podrían identificar mensajes que pasan la autenticación de correo electrónico como suplantados o mensajes que la pasan como legítimos.</span><span class="sxs-lookup"><span data-stu-id="6122c-152">Other back-end intelligence factors could identify messages that pass email authentication as spoofed, or messages that fail email email authentication as legitimate.</span></span>

<span data-ttu-id="6122c-153">Por ejemplo, el dominio fabrikam.com no tiene registros SPF, DKIM o DMARC.</span><span class="sxs-lookup"><span data-stu-id="6122c-153">For example, the fabrikam.com domain has no SPF, DKIM, or DMARC records.</span></span> <span data-ttu-id="6122c-154">Los mensajes de los remitentes del dominio fabrikam.com pueden producir un error en la autenticación compuesta (tenga en cuenta que el valor  y razón de `compauth`):</span><span class="sxs-lookup"><span data-stu-id="6122c-154">Messages from senders in the fabrikam.com domain can fail composite authentication (note the `compauth` value and reason):</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="6122c-155">Si fabrikam.com configura un SPF sin un registro DKIM, este mensaje no produciría un error de autenticación compuesta.</span><span class="sxs-lookup"><span data-stu-id="6122c-155">If fabrikam.com configures an SPF without a DKIM record, the message can pass composite authentication.</span></span> <span data-ttu-id="6122c-156">El dominio que ha pasado comprobaciones de SPF está alineado con el dominio de la dirección De:</span><span class="sxs-lookup"><span data-stu-id="6122c-156">The domain that passed SPF checks is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="6122c-157">Si fabrikam.com configura un registro DKIM sin un registro SPF, este mensaje no produciría un error de autenticación compuesta.</span><span class="sxs-lookup"><span data-stu-id="6122c-157">If fabrikam.com configures a DKIM record without an SPF record, the message can pass composite authentication.</span></span> <span data-ttu-id="6122c-158">El dominio de la firma DKIM está alineado con el dominio de la dirección De:</span><span class="sxs-lookup"><span data-stu-id="6122c-158">The domain in the DKIM signature is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="6122c-159">Si el dominio en SPF o la firma DKIM no están alineados con el dominio de la dirección De, el mensaje puede producir un error de autenticación compuesta:</span><span class="sxs-lookup"><span data-stu-id="6122c-159">If the domain in SPF or the DKIM signature doesn't align with the domain in the From address, the message can fail composite authentication:</span></span>

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="6122c-160">Soluciones para remitentes legítimos que envían correo electrónico sin autenticar</span><span class="sxs-lookup"><span data-stu-id="6122c-160">Solutions for legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="6122c-161">Microsoft 365 realiza un seguimiento de quién está enviando correo sin autenticar en su organización.</span><span class="sxs-lookup"><span data-stu-id="6122c-161">Microsoft 365 keeps track of who is sending unauthenticated email to your organization.</span></span> <span data-ttu-id="6122c-162">Si el servicio considera que el remitente no es legítimo, marcará los mensajes de este remitente como error de autenticación compuesta.</span><span class="sxs-lookup"><span data-stu-id="6122c-162">If the service thinks the sender is not legitimate, it will mark messages from this sender as a composite authentication failure.</span></span> <span data-ttu-id="6122c-163">Para evitar este veredicto, puede usar las recomendaciones de esta sección.</span><span class="sxs-lookup"><span data-stu-id="6122c-163">To avoid this verdict, you can use the recommendations in this section.</span></span>

### <a name="configure-email-authentication-for-domains-you-own"></a><span data-ttu-id="6122c-164">Configuración de la autenticación de correo electrónico para los dominios de su propiedad</span><span class="sxs-lookup"><span data-stu-id="6122c-164">Configure email authentication for domains you own</span></span>

<span data-ttu-id="6122c-165">Puede usar este método para resolver la suplantación de identidad dentro de la organización y entre dominios en caso de que es propietario o interactúa con varios espacios empresariales.</span><span class="sxs-lookup"><span data-stu-id="6122c-165">You can use this method to resolve intra-org spoofing and cross-domain spoofing in cases where you own or interact with multiple tenants.</span></span> <span data-ttu-id="6122c-166">También le ayuda a resolver la suplantación entre dominios donde envía a otros clientes de Microsoft 365 o servicios de terceros hospedados por otros proveedores.</span><span class="sxs-lookup"><span data-stu-id="6122c-166">It also helps resolve cross-domain spoofing where you send to other customers within Microsoft 365 or third parties that are hosted by other providers.</span></span>

- <span data-ttu-id="6122c-167">[Configure los registros de SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) para sus dominios.</span><span class="sxs-lookup"><span data-stu-id="6122c-167">[Configure SPF records](set-up-spf-in-office-365-to-help-prevent-spoofing.md) for your domains.</span></span>

- <span data-ttu-id="6122c-168">[Configure los registros de DKIM](use-dkim-to-validate-outbound-email.md) para sus dominios principales.</span><span class="sxs-lookup"><span data-stu-id="6122c-168">[Configure DKIM records](use-dkim-to-validate-outbound-email.md) for your primary domains.</span></span>

- <span data-ttu-id="6122c-169">[Puede configurar los registros DMARC](use-dmarc-to-validate-email.md) para su dominio para determinar la lista de remitentes legítimos.</span><span class="sxs-lookup"><span data-stu-id="6122c-169">[Consider setting up DMARC records](use-dmarc-to-validate-email.md) for your domain to determine your legitimate senders.</span></span>

<span data-ttu-id="6122c-170">Microsoft no proporciona instrucciones detalladas de implementación para los registros SPF, DKIM y DMARC.</span><span class="sxs-lookup"><span data-stu-id="6122c-170">Microsoft doesn't provide detailed implementation guidelines for SPF, DKIM, and DMARC records.</span></span> <span data-ttu-id="6122c-171">Sin embargo, hay una gran cantidad de información disponible en línea.</span><span class="sxs-lookup"><span data-stu-id="6122c-171">However, there's many information available online.</span></span> <span data-ttu-id="6122c-172">También existen compañías de terceros dedicadas a ayudar a su organización a configurar los registros de autenticación de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6122c-172">There are also third party companies dedicated to helping your organization set up email authentication records.</span></span>

#### <a name="you-dont-know-all-sources-for-your-email"></a><span data-ttu-id="6122c-173">No conoce todas las fuentes del correo electrónico</span><span class="sxs-lookup"><span data-stu-id="6122c-173">You don't know all sources for your email</span></span>

<span data-ttu-id="6122c-174">Muchos dominios no publican registros de SPF porque no conocen todos los orígenes de correo electrónico de los mensajes de su dominio.</span><span class="sxs-lookup"><span data-stu-id="6122c-174">Many domains don't publish SPF records because they don't know all of the email sources for messages in their domain.</span></span> <span data-ttu-id="6122c-175">Debe empezar publicando un registro SPF que contenga las fuentes de correo que conoce, especialmente donde se encuentra el tráfico corporativo y publicar una directiva de SPF neutra, `?all`:</span><span class="sxs-lookup"><span data-stu-id="6122c-175">Start by publishing an SPF record that contains all of the email sources you know about (especially where your corporate traffic is located), and publish the neutral SPF policy `?all`.</span></span> <span data-ttu-id="6122c-176">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6122c-176">For example:</span></span>

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

<span data-ttu-id="6122c-177">Este ejemplo significa que el correo electrónico de su infraestructura corporativa pasará la autenticación de correo electrónico, pero el correo electrónico procedente de fuentes desconocidas se revertirá a neutra.</span><span class="sxs-lookup"><span data-stu-id="6122c-177">This example means that email from your corporate infrastructure will pass email authentication, but email from unknown sources will fall back to neutral.</span></span>

<span data-ttu-id="6122c-178">Microsoft 365 considerará el correo electrónico entrante de su infraestructura corporativa como autenticado.</span><span class="sxs-lookup"><span data-stu-id="6122c-178">Microsoft 365 will treat inbound email from your corporate infrastructure as authenticated.</span></span> <span data-ttu-id="6122c-179">El correo electrónico procedente de orígenes no identificados podría seguir marcándose como suplantación electrónica si falla la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="6122c-179">Email from unidentified sources might still be marked as spoof if it fails implicit authentication.</span></span> <span data-ttu-id="6122c-180">Pero, sigue siendo una mejora a que Microsoft 365 marque todo el correo electrónico como suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="6122c-180">However, this is still an improvement from all email being marked as spoof by Microsoft 365.</span></span>

<span data-ttu-id="6122c-181">Una vez que haya empezado con una directiva de reserva SPF de `?all`, puede descubrir e incluir más orígenes de correo electrónico para los mensajes de forma gradual y, después, actualizar el registro SPF con una directiva más estricta.</span><span class="sxs-lookup"><span data-stu-id="6122c-181">Once you've gotten started with an SPF fallback policy of `?all`, you can gradually discover and include more email sources for your messages, and then update your SPF record with a stricter policy.</span></span>

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a><span data-ttu-id="6122c-182">Uso de la inteligencia de suplantación de identidad para configurar los remitentes permitidos de correo electrónico sin autenticar</span><span class="sxs-lookup"><span data-stu-id="6122c-182">Use spoof intelligence to configure permitted senders of unauthenticated email</span></span>

<span data-ttu-id="6122c-183">También puede usar la [inteligencia de suplantación de identidad](learn-about-spoof-intelligence.md) para que los remitentes puedan enviar correos electrónicos sin autenticar a su organización.</span><span class="sxs-lookup"><span data-stu-id="6122c-183">You can also use [spoof intelligence](learn-about-spoof-intelligence.md) to permit senders to transmit unauthenticated messages to your organization.</span></span>

<span data-ttu-id="6122c-184">En el caso de los dominios externos, el usuario falso es el dominio de la dirección De, mientras que la infraestructura de envío es la dirección IP de origen (dividida en /24 rangos CIDR) o el dominio de la organización del registro de DNS (PTR) invertido.</span><span class="sxs-lookup"><span data-stu-id="6122c-184">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the source IP address (divided up into /24 CIDR ranges), or the organizational domain of the reverse DNS (PTR) record.</span></span>

<span data-ttu-id="6122c-185">En la siguiente captura de pantalla, la dirección IP de origen podría ser 131.107.18.4 con el registro PTR outbound.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="6122c-185">In the screenshot below, the source IP might be 131.107.18.4 with the PTR record outbound.mail.protection.outlook.com.</span></span> <span data-ttu-id="6122c-186">Esto se mostraría como outlook.com para la infraestructura de envío.</span><span class="sxs-lookup"><span data-stu-id="6122c-186">This would show up as outlook.com for the sending infrastructure.</span></span>

<span data-ttu-id="6122c-187">Para permitir que este remitente envíe correos electrónicos sin autenticar, cambie de **No** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="6122c-187">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>

![Configurar remitentes permitidos en la protección contra la suplantación ](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a><span data-ttu-id="6122c-189">Creación de una entrada de permiso para el par de remitente y destinatario</span><span class="sxs-lookup"><span data-stu-id="6122c-189">Create an allow entry for the sender/recipient pair</span></span>

<span data-ttu-id="6122c-190">Para omitir el filtrado de correo no deseado, algunas partes del filtrado de phishing, pero no el filtrado de malware de remitentes específicos, consulte [Creación de listas de remitentes seguros en Microsoft 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="6122c-190">To bypass spam filtering, some parts of filtering for phishing, but not malware filtering for specific senders, see [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a><span data-ttu-id="6122c-191">Solicitar al remitente que configure de la autenticación de correo electrónico para los dominios que no son de su propiedad</span><span class="sxs-lookup"><span data-stu-id="6122c-191">Ask the sender to configure email authentication for domains you don't own</span></span>

<span data-ttu-id="6122c-192">Por el problema del correo no deseado y la suplantación de identidad, Microsoft recomienda la autenticación de correo electrónico para todas las organizaciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6122c-192">Because of the problem of spam and phishing, Microsoft recommends email authentication for all email organizations.</span></span> <span data-ttu-id="6122c-193">En lugar de configurar anulaciones manuales en la organización, puede solicitar a un administrador del dominio remitente que configure los registros de autenticación de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6122c-193">Instead of configuring manual overrides in your organization, you can ask an admin in the sending domain to configure their email authentication records.</span></span>

- <span data-ttu-id="6122c-194">Aunque no tuviesen necesidad de publicar registros de autenticación de correo electrónico en el pasado, deben hacerlo si envían correo electrónico a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6122c-194">Even if they didn't need to publish email authentication records in the past, they should do so if they send email to Microsoft.</span></span>

- <span data-ttu-id="6122c-195">Configure SPF para publicar direcciones IP de envío y configurar DKIM (si disponible) para firmar digitalmente los mensajes.</span><span class="sxs-lookup"><span data-stu-id="6122c-195">Set up SPF to publish the domain's sending IP addresses, and set up DKIM (if available) to digitally sign messages.</span></span> <span data-ttu-id="6122c-196">También deberían considerar al configuración de los registros DMARC.</span><span class="sxs-lookup"><span data-stu-id="6122c-196">They should also consider setting up DMARC records.</span></span>

- <span data-ttu-id="6122c-197">Si usan remitentes en masa para enviar mensajes de correo electrónico en su nombre, compruebe que el dominio de la dirección De (si les pertenece) se alinee con el dominio que supera el SPF o el DMARC.</span><span class="sxs-lookup"><span data-stu-id="6122c-197">If they use bulk senders to send email on their behalf, verify that the domain in the From address (if it belongs to them) aligns with the domain that passes SPF or DMARC.</span></span>

- <span data-ttu-id="6122c-198">Compruebe que las siguientes ubicaciones (si las usan) se incluyen en el registro de SPF:</span><span class="sxs-lookup"><span data-stu-id="6122c-198">Verify the following locations (if they use them) are included in the SPF record:</span></span>

  - <span data-ttu-id="6122c-199">Servidores de correo electrónico locales.</span><span class="sxs-lookup"><span data-stu-id="6122c-199">On-premises email servers.</span></span>
  - <span data-ttu-id="6122c-200">Correo electrónico enviado desde un proveedor de software como servicio (SaaS).</span><span class="sxs-lookup"><span data-stu-id="6122c-200">Email sent from a software-as-a-service (SaaS) provider.</span></span>
  - <span data-ttu-id="6122c-201">Correo electrónico enviado desde un servicio de hospedaje en la nube (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, etc.).</span><span class="sxs-lookup"><span data-stu-id="6122c-201">Email sent from a cloud-hosting service (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, etc.).</span></span>

- <span data-ttu-id="6122c-202">Para los dominios pequeños alojados en un ISP, configure el registro de SPF según las instrucciones del ISP.</span><span class="sxs-lookup"><span data-stu-id="6122c-202">For small domains that are hosted by an ISP, configure the SPF record according to the instructions from the ISP.</span></span>

<span data-ttu-id="6122c-203">Aunque puede ser difícil empezar a enviar dominios para la autenticación, con el tiempo, como más filtros de correo electrónico comienzan a eliminar o incluso rechazan su correo electrónico, deberán configurar los registros adecuados para garantizar una mejor entrega.</span><span class="sxs-lookup"><span data-stu-id="6122c-203">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span> <span data-ttu-id="6122c-204">Asimismo, la participación puede ayudar a luchar contra la suplantación de identidad, y puede reducir la posibilidad de que se produzca suplantación de identidad en la organización u organizaciones a las que envíen correo.</span><span class="sxs-lookup"><span data-stu-id="6122c-204">Also, their participation can help in the fight against phishing, and can reduce the possibility of phishing in their organization or organizations that they send email to.</span></span>

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a><span data-ttu-id="6122c-205">Información para proveedores de infraestructura (ISP, ESP o servicios de hospedaje en la nube)</span><span class="sxs-lookup"><span data-stu-id="6122c-205">Information for infrastructure providers (ISPs, ESPs, or cloud hosting services)</span></span>

<span data-ttu-id="6122c-206">Si hospeda un correo electrónico de un dominio o si proporciona una infraestructura de hospedaje que puede enviar correo electrónico, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6122c-206">If you host a domain's email or provide hosting infrastructure that can send email, you should do the following steps:</span></span>

- <span data-ttu-id="6122c-207">Asegúrese de que los clientes tienen documentación en la que se explica cómo deben configurar sus registros de SPF.</span><span class="sxs-lookup"><span data-stu-id="6122c-207">Ensure your customers have documentation that explains how your customers should configure their SPF records</span></span>

- <span data-ttu-id="6122c-208">Considere añadir firmas DKIM en el correo electrónico saliente, incluso si el cliente no lo configura explícitamente (firma con un dominio predeterminado).</span><span class="sxs-lookup"><span data-stu-id="6122c-208">Consider signing DKIM-signatures on outbound email, even if the customer doesn't explicitly set it up (sign with a default domain).</span></span> <span data-ttu-id="6122c-209">Puede incluso añadir dos firmas DKIM en el correo electrónico (una con el dominio del cliente, si lo ha configurado, y otra con la firma DKIM de su empresa)</span><span class="sxs-lookup"><span data-stu-id="6122c-209">You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>

<span data-ttu-id="6122c-210">No se garantiza la capacidad de entrega a Microsoft aunque se autentique el correo electrónico que proviene de su plataforma, pero al menos se garantiza que Microsoft no marque el correo electrónico como no deseado por no estar autenticado.</span><span class="sxs-lookup"><span data-stu-id="6122c-210">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it isn't authenticated.</span></span>

## <a name="related-links"></a><span data-ttu-id="6122c-211">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="6122c-211">Related links</span></span>

<span data-ttu-id="6122c-212">Para más información sobre procedimientos recomendados de proveedores de servicio, consulte [Procedimientos recomendados de mensajería móvil de M3AAWG para proveedores de servicios](https://www.m3aawg.org/sites/default/files/m3aawg-mobile-messaging-best-practices-service-providers-2015-08_0.pdf).</span><span class="sxs-lookup"><span data-stu-id="6122c-212">For more information about service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/m3aawg-mobile-messaging-best-practices-service-providers-2015-08_0.pdf).</span></span>

<span data-ttu-id="6122c-213">Obtenga más información sobre cómo Office 365 usa SPF y admite la validación de DKIM:</span><span class="sxs-lookup"><span data-stu-id="6122c-213">Learn how Office 365 uses SPF and supports DKIM validation:</span></span>

- [<span data-ttu-id="6122c-214">Ver más información acerca de SPF</span><span class="sxs-lookup"><span data-stu-id="6122c-214">More about SPF</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)

- [<span data-ttu-id="6122c-215">Ver más información acerca de DKIM</span><span class="sxs-lookup"><span data-stu-id="6122c-215">More about DKIM</span></span>](support-for-validation-of-dkim-signed-messages.md)
