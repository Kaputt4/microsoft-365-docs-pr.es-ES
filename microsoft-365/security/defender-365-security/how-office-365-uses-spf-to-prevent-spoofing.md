---
title: Cómo el marco de directivas de remitente (SPF) impide la suplantación de identidad
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/15/2016
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo Microsoft 365 usa el registro TXT del Marco de directivas de remitente (SPF) en DNS para garantizar que los sistemas de correo electrónico de destino confíen en los mensajes enviados desde su dominio personalizado.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 972f283f6138bafcebd877a19f0bfc429e0eed03
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071400"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a><span data-ttu-id="cf625-103">Cómo Microsoft 365 usa el marco de directivas de remitente (SPF) para evitar la suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="cf625-103">How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cf625-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="cf625-104">**Applies to**</span></span>
- [<span data-ttu-id="cf625-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cf625-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="cf625-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="cf625-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="cf625-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf625-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

 <span data-ttu-id="cf625-108">**Resumen:** En este artículo se describe cómo Microsoft 365 usa el registro TXT del Marco de directivas de remitente (SPF) en DNS para garantizar que los sistemas de correo electrónico de destino confíen en los mensajes enviados desde el dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="cf625-108">**Summary:** This article describes how Microsoft 365 uses the Sender Policy Framework (SPF) TXT record in DNS to ensure that destination email systems trust messages sent from your custom domain.</span></span> <span data-ttu-id="cf625-109">Esto se aplica al correo saliente enviado desde Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf625-109">This applies to outbound mail sent from Microsoft 365.</span></span> <span data-ttu-id="cf625-110">Los mensajes enviados desde Microsoft 365 a un destinatario dentro de Microsoft 365 siempre pasarán SPF.</span><span class="sxs-lookup"><span data-stu-id="cf625-110">Messages sent from Microsoft 365 to a recipient within Microsoft 365 will always pass SPF.</span></span>

<span data-ttu-id="cf625-p102">Un registro TXT SPF es un registro DNS que ayuda a evitar la suplantación de IP y la suplantación de identidad mediante la comprobación del nombre del dominio desde el que se envían los mensajes de correo electrónico. Para validar el origen de los mensajes de correo electrónico, SPF contrasta la dirección IP del remitente con el supuesto propietario del dominio de envío.</span><span class="sxs-lookup"><span data-stu-id="cf625-p102">An SPF TXT record is a DNS record that helps prevent spoofing and phishing by verifying the domain name from which email messages are sent. SPF validates the origin of email messages by verifying the IP address of the sender against the alleged owner of the sending domain.</span></span>

> [!NOTE]
> <span data-ttu-id="cf625-p103">El Grupo de trabajo de ingeniería de Internet (IETF) consideró en desuso los tipos de registro SPF en 2014. En su lugar, asegúrese de que usa registros TXT en DNS para publicar la información SPF. El resto del artículo usa el término registro TXT SPF para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="cf625-p103">SPF record types were deprecated by the Internet Engineering Task Force (IETF) in 2014. Instead, ensure that you use TXT records in DNS to publish your SPF information. The rest of this article uses the term SPF TXT record for clarity.</span></span>

<span data-ttu-id="cf625-116">Los administradores de dominio publican información SPF en registros TXT de DNS.</span><span class="sxs-lookup"><span data-stu-id="cf625-116">Domain administrators publish SPF information in TXT records in DNS.</span></span> <span data-ttu-id="cf625-117">La información SPF identifica los servidores autorizados de correo electrónico saliente.</span><span class="sxs-lookup"><span data-stu-id="cf625-117">The SPF information identifies authorized outbound email servers.</span></span> <span data-ttu-id="cf625-118">Los sistemas de correo electrónico de destino comprueban que los mensajes proceden de servidores de correo electrónico saliente autorizados.</span><span class="sxs-lookup"><span data-stu-id="cf625-118">Destination email systems verify that messages originate from authorized outbound email servers.</span></span> <span data-ttu-id="cf625-119">Si ya está familiarizado con SPF, o tiene una implementación sencilla, y solo necesita saber qué incluir en su registro TXT de SPF en DNS para Microsoft 365, puede ir a Configurar SPF en [Microsoft 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md)para ayudar a evitar la suplantación .</span><span class="sxs-lookup"><span data-stu-id="cf625-119">If you are already familiar with SPF, or you have a simple deployment, and just need to know what to include in your SPF TXT record in DNS for Microsoft 365, you can go to [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="cf625-120">Si no tiene una implementación totalmente hospedada en Microsoft 365 o desea obtener más información sobre cómo funciona SPF o cómo solucionar problemas de SPF para Microsoft 365, siga leyendo.</span><span class="sxs-lookup"><span data-stu-id="cf625-120">If you do not have a deployment that is fully-hosted in Microsoft 365, or you want more information about how SPF works or how to troubleshoot SPF for Microsoft 365, keep reading.</span></span>

> [!NOTE]
> <span data-ttu-id="cf625-121">Antes, debía agregar un registro SPF TXT diferente a su dominio personalizado si también utilizaba SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cf625-121">Previously, you had to add a different SPF TXT record to your custom domain if you also used SharePoint Online.</span></span> <span data-ttu-id="cf625-122">Esto ya no es necesario.</span><span class="sxs-lookup"><span data-stu-id="cf625-122">This is no longer required.</span></span> <span data-ttu-id="cf625-123">Este cambio debería reducir el riesgo de que los mensajes de notificación de SharePoint Online acaben en la carpeta de Correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="cf625-123">This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder.</span></span> <span data-ttu-id="cf625-124">No es necesario realizar ningún cambio inmediatamente, pero si recibe el error de "demasiadas búsquedas", modifique el registro TXT de SPF como se describe en Configurar SPF en [Microsoft 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md)para ayudar a evitar la suplantación .</span><span class="sxs-lookup"><span data-stu-id="cf625-124">You do not need to make any changes immediately, but if you receive the "too many lookups" error, modify your SPF TXT record as described in [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span>

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a><span data-ttu-id="cf625-125">Cómo funciona SPF para evitar la suplantación de identidad y suplantación de identidad en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf625-125">How SPF works to prevent spoofing and phishing in Microsoft 365</span></span>
<span data-ttu-id="cf625-126"><a name="HowSPFWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="cf625-126"><a name="HowSPFWorks"> </a></span></span>

<span data-ttu-id="cf625-p106">SPF determina si permite o no que un destinatario envíe en nombre de un dominio. Si el remitente no tiene permiso para hacerlo, es decir, si el correo electrónico no supera la comprobación SPF en el servidor de recepción, la directiva contra el correo no deseado configurada en ese servidor determina qué hacer con el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cf625-p106">SPF determines whether or not a sender is permitted to send on behalf of a domain. If the sender is not permitted to do so, that is, if the email fails the SPF check on the receiving server, the spam policy configured on that server determines what to do with the message.</span></span>

<span data-ttu-id="cf625-129">Cada registro TXT SPF contiene tres partes: la declaración de que se trata de un registro TXT SPF, las direcciones IP que pueden enviar correo desde su dominio y los dominios externos que pueden enviar en nombre de su dominio, y una regla de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="cf625-129">Each SPF TXT record contains three parts: the declaration that it is an SPF TXT record, the IP addresses that are allowed to send mail from your domain and the external domains that can send on your domain's behalf, and an enforcement rule.</span></span> <span data-ttu-id="cf625-130">Un registro TXT SPF válido debe constar de esas tres partes.</span><span class="sxs-lookup"><span data-stu-id="cf625-130">You need all three in a valid SPF TXT record.</span></span> <span data-ttu-id="cf625-131">En este artículo se describe cómo forma el registro TXT de SPF y se proporcionan procedimientos recomendados para trabajar con los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf625-131">This article describes how you form your SPF TXT record and provides best practices for working with the services in Microsoft 365.</span></span> <span data-ttu-id="cf625-132">También se proporcionan los vínculos a las instrucciones sobre cómo trabajar con el registrador de dominios para publicar el registro en DNS.</span><span class="sxs-lookup"><span data-stu-id="cf625-132">Links to instructions on working with your domain registrar to publish your record to DNS are also provided.</span></span>

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a><span data-ttu-id="cf625-133">Conceptos básicos de SPF: Direcciones IP que pueden enviar desde su dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="cf625-133">SPF basics: IP addresses allowed to send from your custom domain</span></span>
<span data-ttu-id="cf625-134"><a name="SPFBasicsIPaddresses"> </a></span><span class="sxs-lookup"><span data-stu-id="cf625-134"><a name="SPFBasicsIPaddresses"> </a></span></span>

<span data-ttu-id="cf625-135">Observe la sintaxis básica de una regla SPF:</span><span class="sxs-lookup"><span data-stu-id="cf625-135">Take a look at the basic syntax for an SPF rule:</span></span>

<span data-ttu-id="cf625-136">v=spf1 \<IP\>\<enforcement rule\></span><span class="sxs-lookup"><span data-stu-id="cf625-136">v=spf1 \<IP\> \<enforcement rule\></span></span>

<span data-ttu-id="cf625-137">Por ejemplo, supongamos que existe la siguiente regla SPF para contoso.com:</span><span class="sxs-lookup"><span data-stu-id="cf625-137">For example, let's say the following SPF rule exists for contoso.com:</span></span>

<span data-ttu-id="cf625-138">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\>\<enforcement rule\></span><span class="sxs-lookup"><span data-stu-id="cf625-138">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\> \<enforcement rule\></span></span>

<span data-ttu-id="cf625-139">En este ejemplo, la regla SPF indica al servidor de correo electrónico de recepción que solo debe aceptar correo de estas direcciones IP para el dominio contoso.com:</span><span class="sxs-lookup"><span data-stu-id="cf625-139">In this example, the SPF rule instructs the receiving email server to only accept mail from these IP addresses for the domain contoso.com:</span></span>

- <span data-ttu-id="cf625-140">IP address #1</span><span class="sxs-lookup"><span data-stu-id="cf625-140">IP address #1</span></span>

- <span data-ttu-id="cf625-141">IP address #2</span><span class="sxs-lookup"><span data-stu-id="cf625-141">IP address #2</span></span>

- <span data-ttu-id="cf625-142">IP address #3</span><span class="sxs-lookup"><span data-stu-id="cf625-142">IP address #3</span></span>

<span data-ttu-id="cf625-p108">Esta regla SPF indica al servidor de correo electrónico de recepción que si un mensaje proviene de contoso.com, pero no de una de estas tres direcciones IP, el servidor de recepción debe aplicar la regla de cumplimiento en el mensaje. Normalmente, la regla de cumplimiento es una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="cf625-p108">This SPF rule tells the receiving email server that if a message comes from contoso.com, but not from one of these three IP addresses, the receiving server should apply the enforcement rule to the message. The enforcement rule is usually one of these options:</span></span>

- <span data-ttu-id="cf625-p109">**Error grave.** Marca el mensaje con "error grave" en el sobre del mensaje y, después, sigue la política de correo no deseado configurada en el servidor de recepción para este tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="cf625-p109">**Hard fail.** Mark the message with 'hard fail' in the message envelope and then follow the receiving server's configured spam policy for this type of message.</span></span>

- <span data-ttu-id="cf625-p110">**Error leve.** Marca el mensaje con "error leve" en el sobre del mensaje. Normalmente, los servidores de correo electrónico están configurados para enviar estos mensajes de todos modos. La mayoría de los usuarios finales no ve esta marca.</span><span class="sxs-lookup"><span data-stu-id="cf625-p110">**Soft fail.** Mark the message with 'soft fail' in the message envelope. Typically, email servers are configured to deliver these messages anyway. Most end users do not see this mark.</span></span>

- <span data-ttu-id="cf625-p111">**Neutro.** No hace nada, es decir, no marca el sobre del mensaje. Esto se reserva normalmente para fines de prueba y rara vez se usa.</span><span class="sxs-lookup"><span data-stu-id="cf625-p111">**Neutral.** Do nothing, that is, do not mark the message envelope. This is usually reserved for testing purposes and is rarely used.</span></span>

<span data-ttu-id="cf625-p112">Los ejemplos siguientes muestran cómo funciona SPF en diferentes situaciones. En estos ejemplos, contoso.com es el remitente y woodgrovebank.com es el receptor.</span><span class="sxs-lookup"><span data-stu-id="cf625-p112">The following examples show how SPF works in different situations. In these examples, contoso.com is the sender and woodgrovebank.com is the receiver.</span></span>

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a><span data-ttu-id="cf625-156">Ejemplo 1: Autenticación de correo electrónico de un mensaje enviado directamente del remitente al receptor</span><span class="sxs-lookup"><span data-stu-id="cf625-156">Example 1: Email authentication of a message sent directly from sender to receiver</span></span>
<span data-ttu-id="cf625-157"><a name="spfExample1"> </a></span><span class="sxs-lookup"><span data-stu-id="cf625-157"><a name="spfExample1"> </a></span></span>

<span data-ttu-id="cf625-158">SPF funciona mejor cuando la ruta de acceso del remitente al receptor es directa, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cf625-158">SPF works best when the path from sender to receiver is direct, for example:</span></span>

![Diagrama que muestra cómo SPF autentica el correo electrónico cuando se envía directamente de servidor a servidor.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

<span data-ttu-id="cf625-160">Cuando woodgrovebank.com recibe el mensaje, si la dirección IP #1 está en el registro TXT SPF para contoso.com, el mensaje supera la comprobación SPF y se autentica.</span><span class="sxs-lookup"><span data-stu-id="cf625-160">When woodgrovebank.com receives the message, if IP address #1 is in the SPF TXT record for contoso.com, the message passes the SPF check and is authenticated.</span></span>

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a><span data-ttu-id="cf625-161">Ejemplo 2: La dirección falsificada del remitente no supera la comprobación SPF</span><span class="sxs-lookup"><span data-stu-id="cf625-161">Example 2: Spoofed sender address fails the SPF check</span></span>
<span data-ttu-id="cf625-162"><a name="spfExample2"> </a></span><span class="sxs-lookup"><span data-stu-id="cf625-162"><a name="spfExample2"> </a></span></span>

<span data-ttu-id="cf625-163">Supongamos que un suplantador de identidad busca una forma de suplantar contoso.com:</span><span class="sxs-lookup"><span data-stu-id="cf625-163">Suppose a phisher finds a way to spoof contoso.com:</span></span>

![Diagrama que muestra cómo SPF autentica el correo electrónico cuando se envía desde un servidor falsificado.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

<span data-ttu-id="cf625-165">Como la dirección IP #12 no está en el registro TXT SPF de contoso.com, el mensaje no supera la comprobación SPF y el receptor puede marcarlo como correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="cf625-165">Since IP address #12 is not in contoso.com's SPF TXT record, the message fails the SPF check and the receiver may choose to mark it as spam.</span></span>

### <a name="example-3-spf-and-forwarded-messages"></a><span data-ttu-id="cf625-166">Ejemplo 3: SPF y los mensajes reenviados</span><span class="sxs-lookup"><span data-stu-id="cf625-166">Example 3: SPF and forwarded messages</span></span>
<span data-ttu-id="cf625-167"><a name="spfExample3"> </a></span><span class="sxs-lookup"><span data-stu-id="cf625-167"><a name="spfExample3"> </a></span></span>

<span data-ttu-id="cf625-p113">Un inconveniente de SPF es que no funciona cuando se ha reenviado un correo electrónico. Por ejemplo, supongamos que el usuario de woodgrovebank.com ha configurado una regla de reenvío para enviar todo el correo electrónico a una cuenta de outlook.com:</span><span class="sxs-lookup"><span data-stu-id="cf625-p113">One drawback of SPF is that it doesn't work when an email has been forwarded. For example, suppose the user at woodgrovebank.com has set up a forwarding rule to send all email to an outlook.com account:</span></span>

![Diagrama que muestra que SPF no puede autenticar el correo electrónico cuando se reenvía el mensaje.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

<span data-ttu-id="cf625-p114">En un principio, el mensaje supera la comprobación SPF en woodgrovebank.com pero no supera la comprobación SPF en outlook.com, ya que la dirección IP #25 no se encuentra en el registro TXT SPF de contoso.com. Outlook.com puede marcar entonces el mensaje como correo no deseado. Para solucionar este problema, use SPF junto con otros métodos de autenticación de correo electrónico como DKIM y DMARC.</span><span class="sxs-lookup"><span data-stu-id="cf625-p114">The message originally passes the SPF check at woodgrovebank.com but it fails the SPF check at outlook.com because IP #25 is not in contoso.com's SPF TXT record. Outlook.com might then mark the message as spam. To work around this problem, use SPF in conjunction with other email authentication methods such as DKIM and DMARC.</span></span>

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a><span data-ttu-id="cf625-174">Conceptos básicos de SPF: Incluir dominios de terceros que pueden enviar correo en nombre del dominio</span><span class="sxs-lookup"><span data-stu-id="cf625-174">SPF basics: Including third-party domains that can send mail on behalf of your domain</span></span>
<span data-ttu-id="cf625-175"><a name="SPFBasicsIncludes"> </a></span><span class="sxs-lookup"><span data-stu-id="cf625-175"><a name="SPFBasicsIncludes"> </a></span></span>

<span data-ttu-id="cf625-p115">Además de las direcciones IP, también puede configurar el registro TXT SPF para incluir dominios como remitentes. Estos se agregan al registro TXT SPF como instrucciones "Include". Por ejemplo, contoso.com quiere incluir todas las direcciones IP de los servidores de correo de contoso.net y contoso.org que también le pertenece. Para ello, contoso.com publica un registro TXT SPF que tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="cf625-p115">In addition to IP addresses, you can also configure your SPF TXT record to include domains as senders. These are added to the SPF TXT record as "include" statements. For example, contoso.com might want to include all of the IP addresses of the mail servers from contoso.net and contoso.org which it also owns. To do this, contoso.com publishes an SPF TXT record that looks like this:</span></span>

```text
v=spf1 include:contoso.net include:contoso.org -all
```

<span data-ttu-id="cf625-180">Cuando el servidor de recepción ve este registro en DNS, también realiza una búsqueda DNS en el registro TXT de SPF para contoso.net y, a continuación, para contoso.org. Si encuentra una instrucción include adicional dentro de los registros para contoso.net o contoso.org, también los seguirá.</span><span class="sxs-lookup"><span data-stu-id="cf625-180">When the receiving server sees this record in DNS, it also performs a DNS lookup on the SPF TXT record for contoso.net and then for contoso.org. If it finds an additional include statement within the records for contoso.net or contoso.org, it will follow those too.</span></span> <span data-ttu-id="cf625-181">Con el fin de ayudar a evitar los ataques por denegación de servicio, el número máximo de búsquedas DNS para un único mensaje de correo electrónico es 10.</span><span class="sxs-lookup"><span data-stu-id="cf625-181">In order to help prevent denial of service attacks, the maximum number of DNS lookups for a single email message is 10.</span></span> <span data-ttu-id="cf625-182">Cada instrucción Include representa una búsqueda DNS adicional.</span><span class="sxs-lookup"><span data-stu-id="cf625-182">Each include statement represents an additional DNS lookup.</span></span> <span data-ttu-id="cf625-183">Si un mensaje supera el límite de 10, el mensaje tiene errores SPF.</span><span class="sxs-lookup"><span data-stu-id="cf625-183">If a message exceeds the 10 limit, the message fails SPF.</span></span> <span data-ttu-id="cf625-184">Una vez que un mensaje alcanza este límite, según la forma en que se configure el servidor de recepción, el remitente puede obtener un mensaje que diga que el mensaje generó "demasiadas búsquedas" o que se superó el "número máximo de saltos para el mensaje" (lo que puede ocurrir cuando las búsquedas se buclen y superan el tiempo de espera dns).</span><span class="sxs-lookup"><span data-stu-id="cf625-184">Once a message reaches this limit, depending on the way the receiving server is configured, the sender may get a message that says the message generated "too many lookups" or that the "maximum hop count for the message has been exceeded" (which can happen when the lookups loop and surpass the DNS timeout).</span></span> <span data-ttu-id="cf625-185">Para obtener sugerencias sobre cómo evitar esto, vea [Troubleshooting: Best practices for SPF in Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span><span class="sxs-lookup"><span data-stu-id="cf625-185">For tips on how to avoid this, see [Troubleshooting: Best practices for SPF in Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a><span data-ttu-id="cf625-186">Requisitos para el registro TXT de SPF y Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf625-186">Requirements for your SPF TXT record and Microsoft 365</span></span>
<span data-ttu-id="cf625-187"><a name="SPFReqsinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="cf625-187"><a name="SPFReqsinO365"> </a></span></span>

<span data-ttu-id="cf625-188">Si configura el correo al configurar Microsoft 365, ya creó un registro TXT de SPF que identifica los servidores de mensajería de Microsoft como un origen legítimo de correo para su dominio.</span><span class="sxs-lookup"><span data-stu-id="cf625-188">If you set up mail when you set up Microsoft 365, you already created an SPF TXT record that identifies the Microsoft messaging servers as a legitimate source of mail for your domain.</span></span> <span data-ttu-id="cf625-189">Probablemente, este registro tenga un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf625-189">This record probably looks like this:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

<span data-ttu-id="cf625-190">Si es un cliente completamente hospedado, es decir, no tiene servidores de correo locales que envíen correo saliente, este es el único registro TXT de SPF que necesita publicar para Office 365.</span><span class="sxs-lookup"><span data-stu-id="cf625-190">If you're a fully-hosted customer, that is, you have no on-premises mail servers that send outbound mail, this is the only SPF TXT record that you need to publish for Office 365.</span></span>

<span data-ttu-id="cf625-191">Si tiene una implementación híbrida (es decir, tiene algunos buzones locales y otros hospedados en Microsoft 365) o si es un cliente independiente de Exchange Online Protection (EOP) (es decir, su organización usa EOP para proteger los buzones locales), debe agregar la dirección IP saliente para cada uno de los servidores de correo perimetral local al registro TXT de SPF en DNS.</span><span class="sxs-lookup"><span data-stu-id="cf625-191">If you have a hybrid deployment (that is, you have some mailboxes on-premises and some hosted in Microsoft 365), or if you're an Exchange Online Protection (EOP) standalone customer (that is, your organization uses EOP to protect your on-premises mailboxes), you should add the outbound IP address for each of your on-premises edge mail servers to the SPF TXT record in DNS.</span></span>

## <a name="form-your-spf-txt-record-for-microsoft-365"></a><span data-ttu-id="cf625-192">Formar el registro TXT de SPF para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf625-192">Form your SPF TXT record for Microsoft 365</span></span>
<span data-ttu-id="cf625-193"><a name="FormYourSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="cf625-193"><a name="FormYourSPF"> </a></span></span>

<span data-ttu-id="cf625-p118">Use la información de sintaxis de este artículo para formar el registro TXT de SPF para su dominio personalizado. Aunque existan otras opciones de sintaxis que no se mencionan aquí, estas son las opciones más usadas. Una vez que haya formado el registro, debe actualizarlo en el registrador de dominios.</span><span class="sxs-lookup"><span data-stu-id="cf625-p118">Use the syntax information in this article to form the SPF TXT record for your custom domain. Although there are other syntax options that are not mentioned here, these are the most commonly used options. Once you have formed your record, you need to update the record at your domain registrar.</span></span>

<span data-ttu-id="cf625-197">Para obtener información sobre los dominios que deberá incluir para Microsoft 365, vea [Registros DNS externos necesarios para SPF](../../enterprise/external-domain-name-system-records.md).</span><span class="sxs-lookup"><span data-stu-id="cf625-197">For information about the domains you will need to include for Microsoft 365, see [External DNS records required for SPF](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="cf625-198">Use las [instrucciones paso a paso](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) para actualizar registros SPF (TXT) para el registrador de dominios.</span><span class="sxs-lookup"><span data-stu-id="cf625-198">Use the [step-by-step instructions](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) for updating SPF (TXT) records for your domain registrar.</span></span>

### <a name="spf-txt-record-syntax-for-microsoft-365"></a><span data-ttu-id="cf625-199">Sintaxis de registro TXT de SPF para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf625-199">SPF TXT record syntax for Microsoft 365</span></span>
<span data-ttu-id="cf625-200"><a name="SPFSyntaxO365"> </a></span><span class="sxs-lookup"><span data-stu-id="cf625-200"><a name="SPFSyntaxO365"> </a></span></span>

<span data-ttu-id="cf625-201">Un registro TXT de SPF típico para Microsoft 365 tiene la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="cf625-201">A typical SPF TXT record for Microsoft 365 has the following syntax:</span></span>

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

<span data-ttu-id="cf625-202">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cf625-202">For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

<span data-ttu-id="cf625-203">donde:</span><span class="sxs-lookup"><span data-stu-id="cf625-203">where:</span></span>

- <span data-ttu-id="cf625-p120">Se requiere **v=spf1**. Esto define el registro TXT como un registro TXT SPF.</span><span class="sxs-lookup"><span data-stu-id="cf625-p120">**v=spf1** is required. This defines the TXT record as an SPF TXT record.</span></span>

- <span data-ttu-id="cf625-p121">**ip4** indica que está usando direcciones IP de la versión 4. **ip6** indica que está usando direcciones IP de la versión 6. Si usa direcciones IPv6 IP, reemplace **ip4** por **ip6** en los ejemplos de este artículo. También puede especificar los intervalos de direcciones IP mediante la notación CIDR, por ejemplo **ip4:192.168.0.1/26**.</span><span class="sxs-lookup"><span data-stu-id="cf625-p121">**ip4** indicates that you are using IP version 4 addresses. **ip6** indicates that you are using IP version 6 addresses. If you are using IPv6 IP addresses, replace **ip4** with **ip6** in the examples in this article. You can also specify IP address ranges using CIDR notation, for example **ip4:192.168.0.1/26**.</span></span>

- <span data-ttu-id="cf625-210">_IP address_ es la dirección IP que quiere agregar al registro TXT SPF.</span><span class="sxs-lookup"><span data-stu-id="cf625-210">_IP address_ is the IP address that you want to add to the SPF TXT record.</span></span> <span data-ttu-id="cf625-211">Normalmente, esta es la dirección IP del servidor de correo saliente de su organización.</span><span class="sxs-lookup"><span data-stu-id="cf625-211">Usually, this is the IP address of the outbound mail server for your organization.</span></span> <span data-ttu-id="cf625-212">Puede enumerar varios servidores de correo saliente.</span><span class="sxs-lookup"><span data-stu-id="cf625-212">You can list multiple outbound mail servers.</span></span> <span data-ttu-id="cf625-213">Para obtener más información, vea [Example: SPF TXT record for multiple outbound on-premises mail servers and Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).</span><span class="sxs-lookup"><span data-stu-id="cf625-213">For more information, see [Example: SPF TXT record for multiple outbound on-premises mail servers and Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).</span></span>

- <span data-ttu-id="cf625-214">_domain name_ es el dominio que quiere agregar como un remitente legítimo.</span><span class="sxs-lookup"><span data-stu-id="cf625-214">_domain name_ is the domain you want to add as a legitimate sender.</span></span> <span data-ttu-id="cf625-215">Para obtener una lista de nombres de dominio que debe incluir para Microsoft 365, vea [Registros DNS externos necesarios para SPF](../../enterprise/external-domain-name-system-records.md).</span><span class="sxs-lookup"><span data-stu-id="cf625-215">For a list of domain names you should include for Microsoft 365, see [External DNS records required for SPF](../../enterprise/external-domain-name-system-records.md).</span></span>

- <span data-ttu-id="cf625-216">Normalmente, la regla de cumplimiento es una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="cf625-216">Enforcement rule is usually one of the following:</span></span>

  - <span data-ttu-id="cf625-217">-all</span><span class="sxs-lookup"><span data-stu-id="cf625-217">-all</span></span>

    <span data-ttu-id="cf625-p124">Indica un error grave. Si conoce todas las direcciones IP autorizadas para el dominio, debe enumerarlas en el registro TXT SPF y usar el calificador -all (error grave). Además, si solo usa SPF, es decir, no está usando DMARC o DKIM, debe usar el calificador -all. Se recomienda que siempre use este calificador.</span><span class="sxs-lookup"><span data-stu-id="cf625-p124">Indicates hard fail. If you know all of the authorized IP addresses for your domain, list them in the SPF TXT record and use the -all (hard fail) qualifier. Also, if you are only using SPF, that is, you are not using DMARC or DKIM, you should use the -all qualifier. We recommend that you use always this qualifier.</span></span>

  - <span data-ttu-id="cf625-222">~all</span><span class="sxs-lookup"><span data-stu-id="cf625-222">~all</span></span>

    <span data-ttu-id="cf625-p125">Indica los errores leves. Si no está seguro de tener la lista completa de direcciones IP, entonces debería usar el calificador ~all (error leve). Además, si usa DMARC con p=quarantine o p=reject, entonces puede usar ~all. De lo contrario, use -all.</span><span class="sxs-lookup"><span data-stu-id="cf625-p125">Indicates soft fail. If you're not sure that you have the complete list of IP addresses, then you should use the ~all (soft fail) qualifier. Also, if you are using DMARC with p=quarantine or p=reject, then you can use ~all. Otherwise, use -all.</span></span>

  - <span data-ttu-id="cf625-227">?all</span><span class="sxs-lookup"><span data-stu-id="cf625-227">?all</span></span>

    <span data-ttu-id="cf625-p126">Indica neutro. Se usa al probar SPF. No es recomendable usar este calificador en la implementación activa.</span><span class="sxs-lookup"><span data-stu-id="cf625-p126">Indicates neutral. This is used when testing SPF. We do not recommend that you use this qualifier in your live deployment.</span></span>

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a><span data-ttu-id="cf625-231">Ejemplo: registro TXT de SPF que se usará cuando todo el correo sea enviado por Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf625-231">Example: SPF TXT record to use when all of your mail is sent by Microsoft 365</span></span>
<span data-ttu-id="cf625-232"><a name="ExampleSPFNoSP"> </a></span><span class="sxs-lookup"><span data-stu-id="cf625-232"><a name="ExampleSPFNoSP"> </a></span></span>

<span data-ttu-id="cf625-233">Si Microsoft 365 envía todo el correo, úselo en el registro TXT de SPF:</span><span class="sxs-lookup"><span data-stu-id="cf625-233">If all of your mail is sent by Microsoft 365, use this in your SPF TXT record:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a><span data-ttu-id="cf625-234">Ejemplo: registro TXT de SPF para un escenario híbrido con una Exchange Server local y Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf625-234">Example: SPF TXT record for a hybrid scenario with one on-premises Exchange Server and Microsoft 365</span></span>
<span data-ttu-id="cf625-235"><a name="ExampleSPFHybridOneExchangeServer"> </a></span><span class="sxs-lookup"><span data-stu-id="cf625-235"><a name="ExampleSPFHybridOneExchangeServer"> </a></span></span>

<span data-ttu-id="cf625-236">En un entorno híbrido, si la dirección IP del servidor Exchange Server local es 192.168.0.1, para establecer la regla de cumplimiento SPF en error grave, forme el registro TXT SPF de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf625-236">In a hybrid environment, if the IP address of your on-premises Exchange Server is 192.168.0.1, in order to set the SPF enforcement rule to hard fail, form the SPF TXT record as follows:</span></span>

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a><span data-ttu-id="cf625-237">Ejemplo: registro TXT de SPF para varios servidores de correo local salientes y Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf625-237">Example: SPF TXT record for multiple outbound on-premises mail servers and Microsoft 365</span></span>
<span data-ttu-id="cf625-238"><a name="ExampleSPFMultipleMailServerO365"> </a></span><span class="sxs-lookup"><span data-stu-id="cf625-238"><a name="ExampleSPFMultipleMailServerO365"> </a></span></span>

<span data-ttu-id="cf625-p127">Si dispone de varios servidores de correo saliente, incluya la dirección IP de cada servidor de correo en el registro SPF TXT separando cada dirección con un espacio seguido de "ip4": instrucción. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cf625-p127">If you have multiple outbound mail servers, include the IP address for each mail server in the SPF TXT record and separate each IP address with a space followed by an "ip4:" statement. For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a><span data-ttu-id="cf625-241">Pasos siguientes: Configurar SPF para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf625-241">Next steps: Set up SPF for Microsoft 365</span></span>
<span data-ttu-id="cf625-242"><a name="SPFNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="cf625-242"><a name="SPFNextSteps"> </a></span></span>

<span data-ttu-id="cf625-243">Una vez que haya formulado el registro TXT de SPF, siga los pasos descritos en Configurar SPF en [Microsoft 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md) para ayudar a evitar la suplantación de dominio para agregarlo a su dominio.</span><span class="sxs-lookup"><span data-stu-id="cf625-243">Once you have formulated your SPF TXT record, follow the steps in [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) to add it to your domain.</span></span>

<span data-ttu-id="cf625-244">Aunque SPF está diseñado para ayudar a evitar la suplantación de identidad, existen técnicas de suplantación de identidad contra las que SPF no puede ofrecer protección.</span><span class="sxs-lookup"><span data-stu-id="cf625-244">Although SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="cf625-245">Para protegerse de estos, una vez que haya configurado SPF, también debe configurar DKIM y DMARC para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf625-245">In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Microsoft 365.</span></span> <span data-ttu-id="cf625-246">Para empezar, vea [Use DKIM to validate outbound email sent from your custom domain in Microsoft 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="cf625-246">To get started, see [Use DKIM to validate outbound email sent from your custom domain in Microsoft 365](use-dkim-to-validate-outbound-email.md).</span></span> <span data-ttu-id="cf625-247">Después, vea [Usar DMARC para validar el correo electrónico en Microsoft 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="cf625-247">Next, see [Use DMARC to validate email in Microsoft 365](use-dmarc-to-validate-email.md).</span></span>

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a><span data-ttu-id="cf625-248">Solución de problemas: procedimientos recomendados para SPF en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf625-248">Troubleshooting: Best practices for SPF in Microsoft 365</span></span>
<span data-ttu-id="cf625-249"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="cf625-249"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="cf625-p129">Solo puede crear un registro TXT SPF para su dominio personalizado. La creación de varios registros provoca una situación de round robin y SPF producirá un error. Para evitar esto, puede crear registros independientes para cada subdominio. Por ejemplo, cree un registro para contoso.com y otro registro para bulkmail.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cf625-p129">You can only create one SPF TXT record for your custom domain. Creating multiple records causes a round robin situation and SPF will fail. To avoid this, you can create separate records for each subdomain. For example, create one record for contoso.com and another record for bulkmail.contoso.com.</span></span>

<span data-ttu-id="cf625-p130">Si un mensaje de correo electrónico provoca más de 10 búsquedas DNS antes de que se envíe, el servidor de correo de recepción responderá con un error permanente, también denominado un  _permerror_, y provocará que el mensaje no supere la comprobación SPF. El servidor de recepción también puede responder con un informe de no entrega (NDR) que contiene un error similar a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="cf625-p130">If an email message causes more than 10 DNS lookups before it is delivered, the receiving mail server will respond with a permanent error, also called a  _permerror_, and cause the message to fail the SPF check. The receiving server may also respond with a non-delivery report (NDR) that contains an error similar to these:</span></span>

- <span data-ttu-id="cf625-256">El mensaje ha superado el recuento de saltos.</span><span class="sxs-lookup"><span data-stu-id="cf625-256">The message exceeded the hop count.</span></span>

- <span data-ttu-id="cf625-257">El mensaje ha necesitado demasiadas búsquedas.</span><span class="sxs-lookup"><span data-stu-id="cf625-257">The message required too many lookups.</span></span>

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a><span data-ttu-id="cf625-258">Evitar el error de "demasiadas búsquedas" al usar dominios de terceros con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf625-258">Avoiding the "too many lookups" error when you use third-party domains with Microsoft 365</span></span>
<span data-ttu-id="cf625-259"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="cf625-259"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="cf625-p131">Algunos registros TXT SPF para dominios de terceros ordenan al servidor de recepción que realicen un gran número de búsquedas DNS. Por ejemplo, en el momento de escribir este artículo, Salesforce.com contiene 5 instrucciones Include en el registro:</span><span class="sxs-lookup"><span data-stu-id="cf625-p131">Some SPF TXT records for third-party domains direct the receiving server to perform a large number of DNS lookups. For example, at the time of this writing, Salesforce.com contains 5 include statements in its record:</span></span>

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

<span data-ttu-id="cf625-p132">Para evitar el error, puede implementar una directiva donde cualquier usuario pueda enviar correo masivo, por ejemplo, tiene que usar específicamente un subdominio para este propósito. Después, defina un registro TXT SPF diferente para el subdominio que incluye el correo masivo.</span><span class="sxs-lookup"><span data-stu-id="cf625-p132">To avoid the error, you can implement a policy where anyone sending bulk email, for example, has to use a subdomain specifically for this purpose. You then define a different SPF TXT record for the subdomain that includes the bulk email.</span></span>

 <span data-ttu-id="cf625-p133">En algunos casos, como en el ejemplo de salesforce.com, tiene que usar el dominio en el registro TXT SPF, pero en otros casos, puede que el tercero ya haya creado un subdominio para que lo use para este propósito. Por ejemplo, exacttarget.com ha creado un subdominio que debe usar para el registro TXT SPF:</span><span class="sxs-lookup"><span data-stu-id="cf625-p133">In some cases, like the salesforce.com example, you have to use the domain in your SPF TXT record, but in other cases, the third-party may have already created a subdomain for you to use for this purpose. For example, exacttarget.com has created a subdomain that you need to use for your SPF TXT record:</span></span>

```text
cust-spf.exacttarget.com
```

<span data-ttu-id="cf625-266">Al incluir dominios de terceros en el registro TXT SPF, debe confirmar con el tercero qué dominio o subdominio usar para evitar verse afectado por el límite de 10 búsquedas.</span><span class="sxs-lookup"><span data-stu-id="cf625-266">When you include third-party domains in your SPF TXT record, you need to confirm with the third-party which domain or subdomain to use in order to avoid running into the 10 lookup limit.</span></span>

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a><span data-ttu-id="cf625-267">Cómo ver el registro TXT SPF actual y determinar el número de búsquedas que requiere</span><span class="sxs-lookup"><span data-stu-id="cf625-267">How to view your current SPF TXT record and determine the number of lookups that it requires</span></span>
<span data-ttu-id="cf625-268"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="cf625-268"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="cf625-p134">Puede usar nslookup para ver los registros DNS, incluido el registro TXT SPF. O bien, si lo prefiere, hay varias herramientas disponibles, gratuitas y en línea que puede usar para ver el contenido del registro TXT SPF. Puede determinar cuántas búsquedas DNS requiere el registro al observar el registro TXT SPF y seguir la cadena de instrucciones Include y redireccionamientos. Algunas herramientas en línea incluso harán un recuento y le mostrarán estas búsquedas. Realizar un seguimiento de este número le ayudará a evitar que los mensajes enviados desde su organización desencadenen un error permanente, denominado un permerror, desde el servidor de recepción.</span><span class="sxs-lookup"><span data-stu-id="cf625-p134">You can use nslookup to view your DNS records, including your SPF TXT record. Or, if you prefer, there are a number of free, online tools available that you can use to view the contents of your SPF TXT record. By looking at your SPF TXT record and following the chain of include statements and redirects, you can determine how many DNS lookups the record requires. Some online tools will even count and display these lookups for you. Keeping track of this number will help prevent messages sent from your organization from triggering a permanent error, called a permerror, from the receiving server.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="cf625-274">Más información</span><span class="sxs-lookup"><span data-stu-id="cf625-274">For more information</span></span>
<span data-ttu-id="cf625-275"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="cf625-275"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="cf625-276">¿Necesita ayuda para agregar el registro TXT SPF?</span><span class="sxs-lookup"><span data-stu-id="cf625-276">Need help adding the SPF TXT record?</span></span> <span data-ttu-id="cf625-277">Lea el artículo Crear registros DNS en cualquier proveedor de hospedaje DNS para [Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) para obtener información detallada sobre el uso de Sender Policy Framework con su dominio personalizado en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf625-277">Read the article [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) for detailed information about usage of Sender Policy Framework with your custom domain in Microsoft 365.</span></span> <span data-ttu-id="cf625-278">[Los encabezados de mensajes contra correo](anti-spam-message-headers.md) no deseado incluyen la sintaxis y los campos de encabezado usados por Microsoft 365 para las comprobaciones de SPF.</span><span class="sxs-lookup"><span data-stu-id="cf625-278">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for SPF checks.</span></span>
