---
title: Cómo usar DKIM para el correo electrónico en su dominio personalizado
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
audience: ITPro
ms.topic: article
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Más información sobre cómo usar DomainKeys Identified Mail (DKIM) con Microsoft 365 para asegurarse de que los mensajes que se envían desde su dominio personalizado sean de confianza para los sistemas de correo electrónico de destino.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2cd04911e3663bb6b9fa00d4946b26086dc8094d
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538272"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a><span data-ttu-id="2c5c6-103">Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="2c5c6-103">Use DKIM to validate outbound email sent from your custom domain</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2c5c6-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="2c5c6-104">**Applies to**</span></span>
- [<span data-ttu-id="2c5c6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2c5c6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2c5c6-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="2c5c6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2c5c6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c5c6-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

 <span data-ttu-id="2c5c6-108">Este artículo muestra los pasos para usar DomainKeys Identified Mail (DKIM) con Microsoft 365 para asegurarse de que los sistemas de correo electrónico de destino confían en los mensajes enviados desde su dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-108">This article lists the steps to use DomainKeys Identified Mail (DKIM) with Microsoft 365 to ensure that destination email systems trust messages sent outbound from your custom domain.</span></span>

<span data-ttu-id="2c5c6-109">En este artículo:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-109">In this article:</span></span>

- [<span data-ttu-id="2c5c6-110">Cómo DKIM funciona mejor que SPF solo para evitar la suplantación de identidad malintencionada</span><span class="sxs-lookup"><span data-stu-id="2c5c6-110">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [<span data-ttu-id="2c5c6-111">Pasos para actualizar manualmente las claves de 1024 bits a claves de cifrado DKIM de 2048 bits</span><span class="sxs-lookup"><span data-stu-id="2c5c6-111">Steps to manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [<span data-ttu-id="2c5c6-112">Pasos para configurar manualmente DKIM</span><span class="sxs-lookup"><span data-stu-id="2c5c6-112">Steps to manually set up DKIM</span></span>](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [<span data-ttu-id="2c5c6-113">Pasos para configurar DKIM para más de un dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="2c5c6-113">Steps to configure DKIM for more than one custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [<span data-ttu-id="2c5c6-114">Deshabilitar la directiva de firmas DKIM para un dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="2c5c6-114">Disabling the DKIM signing policy for a custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [<span data-ttu-id="2c5c6-115">Comportamiento predeterminado para DKIM y Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2c5c6-115">Default behavior for DKIM and Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [<span data-ttu-id="2c5c6-116">Configurar DKIM para que un servicio de terceros pueda enviar, o suplantar, correo electrónico en nombre de su dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="2c5c6-116">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [<span data-ttu-id="2c5c6-117">Pasos siguientes: una vez configurado DKIM para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2c5c6-117">Next steps: After you set up DKIM for Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

> [!NOTE]
> <span data-ttu-id="2c5c6-118">Microsoft 365 configura automáticamente DKIM para sus dominios "onmicrosoft.com" iniciales.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-118">Microsoft 365 automatically sets up DKIM for its initial 'onmicrosoft.com' domains.</span></span> <span data-ttu-id="2c5c6-119">Lo que significa que no es necesario realizar ninguna acción para configurar DKIM para un nombre de dominio inicial (por ejemplo, litware.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="2c5c6-119">That means you don't need to do anything to set up DKIM for any initial domain names (for example, litware.onmicrosoft.com).</span></span> <span data-ttu-id="2c5c6-120">Para más información sobre los dominios, vea [Preguntas más frecuentes de dominios](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span><span class="sxs-lookup"><span data-stu-id="2c5c6-120">For more information about domains, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

<span data-ttu-id="2c5c6-121">DKIM es uno de los tres métodos de autenticación (SPF, KIM y DMARC) que ayudan a evitar que los atacantes envíen mensajes que parecen procedentes de su dominio.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-121">DKIM is one of the trio of Authentication methods (SPF, DKIM and DMARC) that help prevent attackers from sending messages that look like they come from your domain.</span></span>

<span data-ttu-id="2c5c6-p102">DKIM le permite agregar una firma digital a los mensajes de correo electrónico salientes en el encabezado del mensaje. Suena complicado, pero realmente no lo es. Cuando configura DKIM, autoriza que su dominio pueda asociar su nombre (o firmar) a un mensaje de correo electrónico mediante la autenticación criptográfica. Los sistemas de correo electrónico que reciben correo electrónico desde el dominio pueden usar esta firma digital para ayudar a determinar si el correo entrante que reciben es legítimo.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p102">DKIM lets you add a digital signature to outbound email messages in the message header. When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message using cryptographic authentication. Email systems that get email from your domain can use this digital signature to help verify whether incoming email is legitimate.</span></span>

<span data-ttu-id="2c5c6-125">Básicamente, una clave privada cifra el encabezado en un correo electrónico saliente del dominio.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-125">In basic, a private key encrypts the header in a domain's outgoing email.</span></span> <span data-ttu-id="2c5c6-126">La clave pública se publica en los registros DNS del dominio, y los servidores de recepción pueden usar esa clave para descodificar la firma.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-126">The public key is published in the domain's DNS records, and receiving servers can use that key to decode the signature.</span></span> <span data-ttu-id="2c5c6-127">La verificación de DKIM ayuda a los servidores de recepción a confirmar que el correo realmente procede de su dominio y no se trata de alguien que está *suplantando* su dominio.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-127">DKIM verification helps the receiving servers confirm the mail is really coming from your domain and not someone *spoofing* your domain.</span></span>

> [!TIP]
><span data-ttu-id="2c5c6-p104">También puede elegir no hacer nada relacionado con DKIM para su dominio personalizado. Si no configura DKIM para su dominio personalizado, Microsoft 365 crea un par de claves privadas y públicas que permiten que DKIM firme y configure la directiva predeterminada de Microsoft 365 para su dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p104">You can choose to do nothing about DKIM for your custom domain too. If you don't set up DKIM for your custom domain, Microsoft 365 creates a private and public key pair, enables DKIM signing, and then configures the Microsoft 365 default policy for your custom domain.</span></span>

 <span data-ttu-id="2c5c6-p105">El DKIM integrado de Microsoft 365 es una cobertura suficiente para la mayoría de los clientes. Sin embargo, debería configurar manualmente DKIM para su dominio personalizado en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p105">Microsoft-365's built-in DKIM configuration is sufficient coverage for most customers. However, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>

- <span data-ttu-id="2c5c6-132">Tiene más de un dominio personalizado en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2c5c6-132">You have more than one custom domain in Microsoft 365</span></span>

- <span data-ttu-id="2c5c6-133">También va a configurar DMARC (**recomendado**)</span><span class="sxs-lookup"><span data-stu-id="2c5c6-133">You're going to set up DMARC too (**recommended**)</span></span>

- <span data-ttu-id="2c5c6-134">Quiere tener el control sobre la clave privada</span><span class="sxs-lookup"><span data-stu-id="2c5c6-134">You want control over your private key</span></span>

- <span data-ttu-id="2c5c6-135">Quiere personalizar los registros CNAME</span><span class="sxs-lookup"><span data-stu-id="2c5c6-135">You want to customize your CNAME records</span></span>

- <span data-ttu-id="2c5c6-136">Quiere configurar claves de DKIM para los correos electrónicos que se originen en un dominio de terceros, por ejemplo, si usa un troyano de envío masivo de correo electrónico de terceros.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-136">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>


## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a><span data-ttu-id="2c5c6-137">Cómo DKIM funciona mejor que SPF solo para evitar la suplantación de identidad malintencionada</span><span class="sxs-lookup"><span data-stu-id="2c5c6-137">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>
<span data-ttu-id="2c5c6-138"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="2c5c6-138"><a name="HowDKIMWorks"> </a></span></span>

<span data-ttu-id="2c5c6-139">SPF agrega información a un sobre del mensaje pero DKIM *cifra* una firma dentro del encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-139">SPF adds information to a message envelope but DKIM *encrypts* a signature within the message header.</span></span> <span data-ttu-id="2c5c6-140">Cuando reenvía un mensaje, el servidor de reenvío puede quitar partes de ese sobre del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-140">When you forward a message, portions of that message's envelope can be stripped away by the forwarding server.</span></span> <span data-ttu-id="2c5c6-141">Como la firma digital permanece en el mensaje de correo electrónico porque forma parte del encabezado del correo, DKIM funciona incluso cuando un mensaje se ha reenviado como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-141">Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>

![Diagrama que muestra un mensaje reenviado que pasa por la autenticación DKIM, donde se produce un error en la comprobación de SPF.](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

<span data-ttu-id="2c5c6-p107">En este ejemplo, si solo había publicado un registro TXT de SPF en su dominio, el servidor de correo del destinatario podría haber marcado el correo electrónico como correo no deseado y generar un resultado de falso positivo. **La adición de DKIM en este escenario reduce los *informes de correo no deseado* de falso positivo**. Debido a que DKIM se basa en la criptografía de clave pública para autenticar y no solo en las direcciones IP, DKIM se considera una forma mucho más segura de autenticación que SPF. Se recomienda usar SPF y DKIM, así como DMARC, en la implementación.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p107">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result. **The addition of DKIM in this scenario reduces *false positive* spam reporting.** Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF. We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>

> [!TIP]
> <span data-ttu-id="2c5c6-147">DKIM usa una clave privada para insertar una firma cifrada en los encabezados del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-147">DKIM uses a private key to insert an encrypted signature into the message headers.</span></span> <span data-ttu-id="2c5c6-148">El dominio de firma, o el dominio saliente, se inserta como el valor del campo **d=** en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-148">The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header.</span></span> <span data-ttu-id="2c5c6-149">El dominio de comprobación, o dominio del destinatario, usa entonces el campo **=d** para buscar la clave pública desde DNS y autenticar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-149">The verifying domain, or recipient's domain, then uses the **d=** field to look up the public key from DNS, and authenticate the message.</span></span> <span data-ttu-id="2c5c6-150">Si el mensaje se comprueba, supera la comprobación DKIM.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-150">If the message is verified, the DKIM check passes.</span></span>


## <a name="steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a><span data-ttu-id="2c5c6-151">Pasos para actualizar manualmente las claves de 1024 bits a claves de cifrado DKIM de 2048 bits</span><span class="sxs-lookup"><span data-stu-id="2c5c6-151">Steps to manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>
<span data-ttu-id="2c5c6-152"><a name="1024to2048DKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="2c5c6-152"><a name="1024to2048DKIM"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="2c5c6-153">Microsoft 365 configura automáticamente DKIM para los dominios *"onmicrosoft.com"*.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-153">Microsoft 365 automatically sets up DKIM for *onmicrosoft.com* domains.</span></span> <span data-ttu-id="2c5c6-154">No es necesario seguir ningún paso para usar DKIM para los nombres de dominio iniciales (como litware.*onmicrosoft.com*).</span><span class="sxs-lookup"><span data-stu-id="2c5c6-154">No steps are needed to use DKIM for any initial domain names (like litware.*onmicrosoft.com*).</span></span> <span data-ttu-id="2c5c6-155">Para más información sobre los dominios, vea [Preguntas más frecuentes de dominios](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span><span class="sxs-lookup"><span data-stu-id="2c5c6-155">For more information about domains, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

<span data-ttu-id="2c5c6-156">Ya que ambos valores de bits, 1024 y 2048, son compatibles con las claves DKIM, estas instrucciones le indicarán cómo actualizar la clave de 1024 bits a 2048 en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2c5c6-156">Since both 1024 and 2048 bitness are supported for DKIM keys, these directions will tell you how to upgrade your 1024-bit key to 2048 in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2c5c6-157">Los pasos que se muestran a continuación son dos casos de uso distintos, elija el que mejor se ajuste a su configuración.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-157">The steps below are for two use-cases, please choose the one that best fits your configuration.</span></span>

- <span data-ttu-id="2c5c6-158">Cuando **ya tenga DKIM configurado**, cambie el valor de los bits ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-158">When you **already have DKIM configured**, you rotate bitness by running the following command:</span></span>

  ```powershell
  Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
  ```

  <span data-ttu-id="2c5c6-159">**o bien**</span><span class="sxs-lookup"><span data-stu-id="2c5c6-159">**or**</span></span>

- <span data-ttu-id="2c5c6-160">Para una **implementación nueva de DKIM**, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-160">For a **new implementation of DKIM**, run the following command:</span></span>

  ```powershell
  New-DkimSigningConfig -DomainName <Domain for which config is to be created> -KeySize 2048 -Enabled $true
  ```

<span data-ttu-id="2c5c6-161">Permanezca conectado a Exchange Online PowerShell para *comprobar* la configuración ejecutando el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-161">Stay connected to Exchange Online PowerShell to *verify* the configuration by running the following command:</span></span>

```powershell
Get-DkimSigningConfig -Identity <Domain for which the configuration was set> | Format-List
```

> [!TIP]
> <span data-ttu-id="2c5c6-162">Esta nueva clave de 2048 bits tendrá efecto en el RotateOnDate y mientras tanto enviará los mensajes de correo electrónico con la clave de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-162">This new 2048-bit key takes effect on the RotateOnDate, and will send emails with the 1024-bit key in the interim.</span></span> <span data-ttu-id="2c5c6-163">Después de cuatro días, puede volver a probar con la clave de 2048 bits (es decir, cuando la rotación surta efecto al segundo selector).</span><span class="sxs-lookup"><span data-stu-id="2c5c6-163">After four days, you can test again with the 2048-bit key (that is, once the rotation takes effect to the second selector).</span></span>

<span data-ttu-id="2c5c6-164">Si desea rotar hasta el segundo selector, las opciones son: a) dejar que el servicio de Microsoft 365 rote el selector y actualice al valor de 2048 bits en los próximos 6 meses, o b) después de 4 días y de confirmar que se está utilizando el valor de 2048 bits, rote manualmente la clave del segundo selector por usando el cmdlet apropiado de los que se enumeran arriba.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-164">If you want to rotate to the second selector, your options are a) let the Microsoft 365 service rotate the selector and upgrade to 2048-bitness within the next 6 months, or b) after 4 days and confirming that 2048-bitness is in use, manually rotate the second selector key by using the appropriate cmdlet listed above.</span></span>

<span data-ttu-id="2c5c6-165">Para obtener información detallada sobre la sintaxis y los parámetros, vea los siguientes artículos: [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig), [New-DkimSigningConfig](/powershell/module/exchange/new-dkimsigningconfig) y [Get-DkimSigningConfig](/powershell/module/exchange/get-dkimsigningconfig).</span><span class="sxs-lookup"><span data-stu-id="2c5c6-165">For detailed syntax and parameter information, see the following articles: [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig), [New-DkimSigningConfig](/powershell/module/exchange/new-dkimsigningconfig), and [Get-DkimSigningConfig](/powershell/module/exchange/get-dkimsigningconfig).</span></span>

## <a name="steps-to-manually-set-up-dkim"></a><span data-ttu-id="2c5c6-166">Pasos que necesita seguir para configurar manualmente DKIM</span><span class="sxs-lookup"><span data-stu-id="2c5c6-166">Steps to manually set up DKIM</span></span>
<span data-ttu-id="2c5c6-167"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="2c5c6-167"><a name="SetUpDKIMO365"> </a></span></span>

<span data-ttu-id="2c5c6-168">Para configurar DKIM, deberá completar estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-168">To configure DKIM, you will complete these steps:</span></span>

- [<span data-ttu-id="2c5c6-169">Publicar dos registros CNAME para su dominio personalizado en DNS</span><span class="sxs-lookup"><span data-stu-id="2c5c6-169">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [<span data-ttu-id="2c5c6-170">Habilitar la firma DKIM para su dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="2c5c6-170">Enable DKIM signing for your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="2c5c6-171">Publicar dos registros CNAME para su dominio personalizado en DNS</span><span class="sxs-lookup"><span data-stu-id="2c5c6-171">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="2c5c6-172"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="2c5c6-172"><a name="Publish2CNAME"> </a></span></span>

<span data-ttu-id="2c5c6-173">Para cada dominio para el que quiera agregar una firma DKIM en DNS, necesita publicar dos registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-173">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span>

> [!NOTE]
> <span data-ttu-id="2c5c6-174">Si no ha leído el artículo completo, es posible que se haya perdido esta información de conexión de PowerShell para ahorrar tiempo: [Conectarse a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2c5c6-174">If you haven't read the full article, you may have missed this time-saving PowerShell connection information: [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="2c5c6-175">Ejecute los siguientes comandos de Exchange Online PowerShell para crear los registros del selector:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-175">Run the following commands in Exchange Online PowerShell to create the selector records:</span></span>

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

<span data-ttu-id="2c5c6-p112">Si ha aprovisionado dominios personalizados adicionales además del dominio inicial de Microsoft 365, debe publicar dos registros CNAME para cada dominio adicional. Por lo tanto, si tiene dos dominios, debe publicar dos registros CNAME adicionales, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p112">If you have provisioned custom domains in addition to the initial domain in Microsoft 365, you must publish two CNAME records for each additional domain. So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>

<span data-ttu-id="2c5c6-178">Use el formato siguiente para los registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-178">Use the following format for the CNAME records.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c5c6-179">Si es uno de nuestros clientes de GCC High, calcularemos _domainGuid_ de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-179">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="2c5c6-180">En lugar de buscar el registro MX para su _initialDomain_ para calcular _domainGuid_, lo calculamos directamente desde el dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-180">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="2c5c6-181">Por ejemplo, si su dominio personalizado es "contoso.com", su domainGuid se convierte en "contoso-com", los puntos se reemplazan por un guión.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-181">For example, if your customized domain is "contoso.com" your domainGuid becomes "contoso-com", any periods are replaced with a dash.</span></span> <span data-ttu-id="2c5c6-182">Por lo tanto, independientemente del registro MX al que señale su initialDomain, siempre se usará el método anterior para calcular el domainGuid que se usará en sus registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-182">So, regardless of what MX record your initialDomain points to, you'll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

<span data-ttu-id="2c5c6-183">Donde:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-183">Where:</span></span>

- <span data-ttu-id="2c5c6-184">Para Microsoft 365, los selectores siempre serán "selector1" o "selector2".</span><span class="sxs-lookup"><span data-stu-id="2c5c6-184">For Microsoft 365, the selectors will always be "selector1" or "selector2".</span></span>

- <span data-ttu-id="2c5c6-p114">_domainGUID_ es el mismo que el _domainGUID_ en el registro MX personalizado para su dominio personalizado que aparece antes de mail.protection.outlook.com. Por ejemplo, en el siguiente registro MX del dominio contoso.com, el _domainGUID_ es contoso-com:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p114">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com. For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span>

  > <span data-ttu-id="2c5c6-p115">contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p115">contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span></span>

- <span data-ttu-id="2c5c6-189">_initialDomain_ es el dominio que usó al registrarse en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-189">_initialDomain_ is the domain that you used when you signed up for Microsoft 365.</span></span> <span data-ttu-id="2c5c6-190">Los dominios iniciales siempre terminan en onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-190">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="2c5c6-191">Para obtener información sobre cómo determinar el dominio inicial, vea [Preguntas más frecuentes de dominios](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span><span class="sxs-lookup"><span data-stu-id="2c5c6-191">For information about determining your initial domain, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

<span data-ttu-id="2c5c6-192">Por ejemplo, si tiene un dominio inicial de cohovineyardandwinery.onmicrosoft.com y dos dominios personalizados cohovineyard.com y cohowinery.com, necesitará configurar dos registros CNAME para cada dominio adicional, un total de cuatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-192">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector1._domainkey
Points to address or value:    selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> <span data-ttu-id="2c5c6-193">Es importante crear el segundo registro, pero solo uno de los selectores puede estar disponible en el momento de la creación.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-193">It's important to create the second record, but only one of the selectors may be available at the time of creation.</span></span> <span data-ttu-id="2c5c6-194">En esencia, el segundo selector podría apuntar a una dirección que aún no ha sido creada.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-194">In essence, the second selector might point to an address that hasn't been created yet.</span></span> <span data-ttu-id="2c5c6-195">Aun así, recomendamos crear el segundo registro CNAME, ya que la rotación de las teclas será perfecta.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-195">We still recommended that you create the second CNAME record, because your key rotation will be seamless.</span></span>


### <a name="steps-to-enable-dkim-signing-for-your-custom-domain"></a><span data-ttu-id="2c5c6-196">Pasos para habilitar la firma DKIM para su dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="2c5c6-196">Steps to enable DKIM signing for your custom domain</span></span>
<span data-ttu-id="2c5c6-197"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="2c5c6-197"><a name="EnableDKIMinO365"> </a></span></span>

<span data-ttu-id="2c5c6-p118">Una vez que haya publicado los registros CNAME en DNS, está preparado para habilitar la firma DKIM mediante Microsoft 365. Puede hacerlo a través del Centro de administración de Microsoft 365 o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p118">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Microsoft 365. You can do this either through the Microsoft 365 admin center or by using PowerShell.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a><span data-ttu-id="2c5c6-200">Para habilitar la firma DKIM para su dominio personalizado a través del Centro de administración</span><span class="sxs-lookup"><span data-stu-id="2c5c6-200">To enable DKIM signing for your custom domain through the admin center</span></span>

1. <span data-ttu-id="2c5c6-201">[Inicie sesión en Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-201">[Sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="2c5c6-202">Vaya a [protection.office.com](https://protection.office.com) o [security.microsoft.com](https://security.microsoft.com) según el portal que use y siga la ruta que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-202">Go to [protection.office.com](https://protection.office.com) or [security.microsoft.com](https://security.microsoft.com) depending on which portal you use, and follow the path below.</span></span>

|<span data-ttu-id="2c5c6-203">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="2c5c6-203">protection.office.com</span></span>  |<span data-ttu-id="2c5c6-204">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2c5c6-204">security.microsoft.com</span></span>  |
|---------|---------|
| <span data-ttu-id="2c5c6-205">Administración de amenazas > Directiva > Directivas adicionales > DKIM</span><span class="sxs-lookup"><span data-stu-id="2c5c6-205">Threat Management > Policy > Additional Policies > DKIM</span></span>     | <span data-ttu-id="2c5c6-206">Correo electrónico y colaboración > Directivas y reglas > Directivas de amenazas > Directivas adicionales > DKIM</span><span class="sxs-lookup"><span data-stu-id="2c5c6-206">Email & Collaboration > Policies & rules > Threat policies > Additional policies > DKIM</span></span>        | 

3. <span data-ttu-id="2c5c6-p119">Seleccione el dominio para el que quiere habilitar DKIM y, después, en **Firmar los mensajes de este dominio con firmas DKIM**, elija **Habilitar**. Repita este paso para cada dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p119">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**. Repeat this step for each custom domain.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="2c5c6-209">Para habilitar la firma DKIM para su dominio personalizado mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c5c6-209">To enable DKIM signing for your custom domain by using PowerShell</span></span>

> [!IMPORTANT]
>:::image type="content" source="../../media/DKIMNoKeysSavedForThisDomain.PNG" alt-text="El error &quot;No hay claves DKIM guardadas para este dominio&quot;.":::
> <span data-ttu-id="2c5c6-211">Si está configurando DKIM por primera vez y ve el error "No hay claves DKIM guardadas para este dominio",</span><span class="sxs-lookup"><span data-stu-id="2c5c6-211">If you are configuring DKIM for the first time and see the error 'No DKIM keys saved for this domain.'</span></span> <span data-ttu-id="2c5c6-212">complete el comando en el paso 2, a continuación (por ejemplo, *Set-DkimSigningConfig -Identity contoso.com -Enabled $true*) para ver la clave.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-212">complete the command in step 2, below (for example, *Set-DkimSigningConfig -Identity contoso.com -Enabled $true*) to see the key.</span></span>

1. <span data-ttu-id="2c5c6-213">[Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2c5c6-213">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="2c5c6-214">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-214">Run the following command:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity <domain> -Enabled $true
   ```

   <span data-ttu-id="2c5c6-215">Donde _domain_ es el nombre del dominio personalizado para el que quiere habilitar la firma DKIM.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-215">Where _domain_ is the name of the custom domain that you want to enable DKIM signing for.</span></span>

   <span data-ttu-id="2c5c6-216">Por ejemplo, para el dominio contoso.com:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-216">For example, for the domain contoso.com:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a><span data-ttu-id="2c5c6-217">Para confirmar que la firma DKIM está configurada correctamente en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2c5c6-217">To Confirm DKIM signing is configured properly for Microsoft 365</span></span>

<span data-ttu-id="2c5c6-p121">Espere unos minutos antes de seguir estos pasos para confirmar que ha configurado correctamente DKIM. Esto proporciona tiempo para que la información DKIM acerca del dominio se reparta por toda la red.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p121">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM. This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>

- <span data-ttu-id="2c5c6-220">Envíe un mensaje desde una cuenta dentro de su dominio habilitado para DKIM en Microsoft 365 a otra cuenta de correo electrónico como outlook.com o Hotmail.com.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-220">Send a message from an account within your Microsoft 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>

- <span data-ttu-id="2c5c6-p122">No use una cuenta de aol.com con fines de prueba. AOL puede omitir la comprobación DKIM si se supera la comprobación SPF. Esto anulará la prueba.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p122">Do not use an aol.com account for testing purposes. AOL may skip the DKIM check if the SPF check passes. This will nullify your test.</span></span>

- <span data-ttu-id="2c5c6-p123">Abra el mensaje y observe el encabezado. Las instrucciones para ver el encabezado del mensaje variarán según el cliente de mensajería. Para obtener instrucciones acerca de cómo ver los encabezados de los mensajes en Outlook, consulte [Ver los encabezados de los mensajes de Internet en Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p123">Open the message and look at the header. Instructions for viewing the header for the message will vary depending on your messaging client. For instructions on viewing message headers in Outlook, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

  <span data-ttu-id="2c5c6-p124">El mensaje con firma DKIM contendrá el nombre de host y el dominio que definió cuando publicó las entradas CNAME. El mensaje tendrá un aspecto similar al de este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p124">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries. The message will look something like this example:</span></span>

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- <span data-ttu-id="2c5c6-p125">Busque el encabezado Authentication-Results. Aunque cada servicio de recepción usa un formato ligeramente diferente para estampar el correo entrante, el resultado debe incluir algo como **DKIM=pass** o **DKIM=OK**.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p125">Look for the Authentication-Results header. While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span>

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a><span data-ttu-id="2c5c6-231">Configuración de DKIM para más de un dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="2c5c6-231">To configure DKIM for more than one custom domain</span></span>
<span data-ttu-id="2c5c6-232"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="2c5c6-232"><a name="DKIMMultiDomain"> </a></span></span>

<span data-ttu-id="2c5c6-233">Si en algún momento en el futuro decide agregar otro dominio personalizado y quiere habilitar DKIM para el dominio nuevo, debe completar los pasos de este artículo para cada dominio.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-233">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain.</span></span> <span data-ttu-id="2c5c6-234">En concreto, complete todos los pasos de [Lo que necesita hacer para configurar manualmente DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span><span class="sxs-lookup"><span data-stu-id="2c5c6-234">Specifically, complete all steps in [What you need to do to manually set up DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a><span data-ttu-id="2c5c6-235">Deshabilitación de la directiva de firmas DKIM para un dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="2c5c6-235">Disabling the DKIM signing policy for a custom domain</span></span>
<span data-ttu-id="2c5c6-236"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="2c5c6-236"><a name="DisableDKIMSigningPolicy"> </a></span></span>

<span data-ttu-id="2c5c6-237">Deshabilitar la directiva de firmas no deshabilita DKIM completamente.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-237">Disabling the signing policy does not completely disable DKIM.</span></span> <span data-ttu-id="2c5c6-238">Después de un período de tiempo, Microsoft 365 aplicará automáticamente la directiva predeterminada para el dominio.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-238">After a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span> <span data-ttu-id="2c5c6-239">Para más información sobre esta firma, consulte [Comportamiento predeterminado para DKIM y Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span><span class="sxs-lookup"><span data-stu-id="2c5c6-239">For more information, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="2c5c6-240">Para deshabilitar la directiva de firmas DKIM mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c5c6-240">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="2c5c6-241">[Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2c5c6-241">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="2c5c6-242">Ejecute uno de los siguientes comandos para cada dominio para el que quiera deshabilitar la firma DKIM.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-242">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity <domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="2c5c6-243">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-243">For example:</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="2c5c6-244">O bien</span><span class="sxs-lookup"><span data-stu-id="2c5c6-244">Or</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   <span data-ttu-id="2c5c6-p128">Donde _number_ es el índice de la directiva. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p128">Where _number_ is the index of the policy. For example:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a><span data-ttu-id="2c5c6-247">Comportamiento predeterminado para DKIM y Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2c5c6-247">Default behavior for DKIM and Microsoft 365</span></span>
<span data-ttu-id="2c5c6-248"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="2c5c6-248"><a name="DefaultDKIMbehavior"> </a></span></span>

<span data-ttu-id="2c5c6-p129">Si no habilita DKIM, Microsoft 365 crea automáticamente una clave pública DKIM de 1024 bits para su dominio predeterminado y la clave privada asociada que se almacena internamente en nuestro centro de datos. De forma predeterminada, Microsoft 365 usa una configuración de firmas predeterminada para los dominios que no tienen una directiva local. Esto significa que si no configura DKIM, Microsoft 365 usará su política predeterminada y se creará la clave para habilitar DKIM para el dominio.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p129">If you do not enable DKIM, Microsoft 365 automatically creates a 1024-bit DKIM public key for your default domain and the associated private key which we store internally in our datacenter. By default, Microsoft 365 uses a default signing configuration for domains that do not have a policy in place. This means that if you do not set up DKIM yourself, Microsoft 365 will use its default policy and keys it creates to enable DKIM for your domain.</span></span>

<span data-ttu-id="2c5c6-252">Además, si deshabilita la firma DKIM después de habilitarla, después de un período de tiempo, Microsoft 365 aplicará automáticamente la directiva predeterminada para el dominio.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-252">Also, if you disable DKIM signing after enabling it, after a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span>

<span data-ttu-id="2c5c6-p130">En el ejemplo siguiente, suponga que Microsoft 365 ha habilitado DKIM para fabrikam.com, no el administrador del dominio. Esto significa que los CNAME necesarios no existen en DNS. Las firmas DKIM para el correo electrónico de este dominio tendrán un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p130">In the following example, suppose that DKIM for fabrikam.com was enabled by Microsoft 365, not by the administrator of the domain. This means that the required CNAMEs do not exist in DNS. DKIM signatures for email from this domain will look something like this:</span></span>

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

<span data-ttu-id="2c5c6-256">En este ejemplo, el nombre de host y el dominio contienen los valores a los que señalaría el registro CNAME si el administrador del dominio hubiera habilitado la firma DKIM para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-256">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator.</span></span> <span data-ttu-id="2c5c6-257">Finalmente, cada mensaje enviado desde Microsoft 365 contendrá una firma DKIM.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-257">Eventually, every single message sent from Microsoft 365 will be DKIM-signed.</span></span> <span data-ttu-id="2c5c6-258">Si habilita DKIM, el dominio será el mismo que el dominio de la dirección en el campo De:, en este caso, fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-258">If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com.</span></span> <span data-ttu-id="2c5c6-259">Si no lo hace, el dominio no se alineará y en su lugar se usará el dominio inicial de la organización.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-259">If you don't, it will not align and instead will use your organization's initial domain.</span></span> <span data-ttu-id="2c5c6-260">Para obtener información sobre cómo determinar el dominio inicial, vea [Preguntas más frecuentes de dominios](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span><span class="sxs-lookup"><span data-stu-id="2c5c6-260">For information about determining your initial domain, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="2c5c6-261">Configurar DKIM para que un servicio de terceros pueda enviar, o suplantar, correo electrónico en nombre de su dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="2c5c6-261">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="2c5c6-262"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="2c5c6-262"><a name="SetUp3rdPartyspoof"> </a></span></span>

<span data-ttu-id="2c5c6-p132">Algunos proveedores de servicio de correo electrónico masivo o proveedores de software como servicio le permiten configurar claves DKIM para el correo electrónico que se origina de su servicio. Esto requiere la coordinación entre el usuario y el servicio de terceros para configurar los registros DNS necesarios. Algunos servidores de terceros pueden tener sus propios registros CNAME con diferentes selectores. No existen dos organizaciones que lo hagan exactamente de la misma manera. En su lugar, el proceso depende completamente de la organización.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p132">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service. This requires coordination between yourself and the third-party in order to set up the necessary DNS records. Some third-party servers can have their own CNAME records with different selectors. No two organizations do it exactly the same way. Instead, the process depends entirely on the organization.</span></span>

<span data-ttu-id="2c5c6-268">Un mensaje de ejemplo que muestra un DKIM configurado correctamente para contoso.com y bulkemailprovider.com puede tener el aspecto siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-268">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="2c5c6-269">En este ejemplo, para conseguir este resultado:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-269">In this example, in order to achieve this result:</span></span>

1. <span data-ttu-id="2c5c6-270">El proveedor de correo electrónico masivo le ha proporcionado una clave DKIM pública a Contoso.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-270">Bulk Email Provider gave Contoso a public DKIM key.</span></span>

2. <span data-ttu-id="2c5c6-271">Contoso ha publicado la clave DKIM en su registro DNS.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-271">Contoso published the DKIM key to its DNS record.</span></span>

3. <span data-ttu-id="2c5c6-p133">Al enviar el correo electrónico, el proveedor de correo electrónico masivo ha firmado la clave con la clave privada correspondiente. Al hacer esto, el proveedor de correo electrónico masivo ha adjuntado la firma DKIM al encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-p133">When sending email, Bulk Email Provider signs the key with the corresponding private key. By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>

4. <span data-ttu-id="2c5c6-274">Los sistemas de correo electrónico de recepción realizan una comprobación DKIM mediante la autenticación del valor d=\<domain\> comparado con el dominio en el campo De: (5322.From) de la dirección del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-274">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message.</span></span> <span data-ttu-id="2c5c6-275">En este ejemplo, los valores coinciden:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-275">In this example, the values match:</span></span>

   > <span data-ttu-id="2c5c6-276">sender@**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="2c5c6-276">sender@**contoso.com**</span></span>

   > <span data-ttu-id="2c5c6-277">d=**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="2c5c6-277">d=**contoso.com**</span></span>

## <a name="identify-domains-that-do-not-send-email"></a><span data-ttu-id="2c5c6-278">Identificar dominios que no envían correos electrónicos</span><span class="sxs-lookup"><span data-stu-id="2c5c6-278">Identify domains that do not send email</span></span>

<span data-ttu-id="2c5c6-279">Las organizaciones deben indicar explícitamente si un dominio no envía correos electrónicos especificando `v=DKIM1; p=` en el registro DKIM de estos dominios.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-279">Organizations should explicitly state if a domain does not send email by specifying `v=DKIM1; p=` in the DKIM record for those domains.</span></span> <span data-ttu-id="2c5c6-280">Esto aconseja rechazar la recepción de servidores de correo electrónico que no tengan claves públicas válidas para el dominio y cualquier correo electrónico que declare ser de ese dominio.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-280">This advises receiving email servers that there are no valid public keys for the domain, and any email claiming to be from that domain should be rejected.</span></span> <span data-ttu-id="2c5c6-281">Debe hacerlo para cada dominio y subdominio mediante un carácter comodín DKIM.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-281">You should do this for each domain and subdomain using a wildcard DKIM.</span></span>

<span data-ttu-id="2c5c6-282">Por ejemplo, el registro DKIM tendría el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="2c5c6-282">For example, the DKIM record would look like this:</span></span>

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a><span data-ttu-id="2c5c6-283">Pasos siguientes: una vez configurado DKIM para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2c5c6-283">Next steps: After you set up DKIM for Microsoft 365</span></span>
<span data-ttu-id="2c5c6-284"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="2c5c6-284"><a name="DKIMNextSteps"> </a></span></span>

<span data-ttu-id="2c5c6-285">Aunque DKIM está diseñado para ayudar a evitar la suplantación de identidad, DKIM funciona mejor con SPF y DMARC.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-285">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="2c5c6-286">Cuando haya configurado DKIM, si todavía no ha configurado SPF, debería hacerlo.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-286">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="2c5c6-287">Para obtener una introducción rápida a SPF y configurarlo rápidamente, consulte [Configuración de SPF en Microsoft 365 para evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="2c5c6-287">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="2c5c6-288">Para comprender en detalle cómo Microsoft 365 usa SPF, o para la solución de problemas o las implementaciones no estándar (por ejemplo, implementaciones híbridas), comience con [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md) (Cómo Microsoft 365 usa el marco de directivas permanente [SPF] para evitar la suplantación de identidad).</span><span class="sxs-lookup"><span data-stu-id="2c5c6-288">For a more in-depth understanding of how Microsoft 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="2c5c6-289">Después, consulte [Uso de DMARC para validar el correo electrónico](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="2c5c6-289">Next, see [Use DMARC to validate email](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="2c5c6-290">Los [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md) incluyen la sintaxis y los campos de encabezado que usa Microsoft 365 para efectuar comprobaciones de DKIM.</span><span class="sxs-lookup"><span data-stu-id="2c5c6-290">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for DKIM checks.</span></span>

## <a name="more-information"></a><span data-ttu-id="2c5c6-291">Más información</span><span class="sxs-lookup"><span data-stu-id="2c5c6-291">More information</span></span>

<span data-ttu-id="2c5c6-292">Rotación de clave mediante PowerShell [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig)</span><span class="sxs-lookup"><span data-stu-id="2c5c6-292">Key rotation via PowerShell [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig)</span></span>
