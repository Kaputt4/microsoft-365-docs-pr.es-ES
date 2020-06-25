---
title: Cómo usar DKIM para el correo electrónico en su dominio personalizado
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/8/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Más información sobre cómo usar DomainKeys Identified Mail (DKIM) con Microsoft 365 para asegurarse de que los mensajes que se envían desde su dominio personalizado sean de confianza para los sistemas de correo electrónico de destino.
ms.openlocfilehash: 4ec5f7c8779e9d6b6709c8fc3311ec9c0e99b680
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754849"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a><span data-ttu-id="066bc-103">Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="066bc-103">Use DKIM to validate outbound email sent from your custom domain</span></span>

 <span data-ttu-id="066bc-104">**Resumen**: Este artículo describe cómo usa DomainKeys Identified Mail (DKIM) con Microsoft 365 para asegurarse de que los sistemas de correo electrónico de destino confían en los mensajes enviados desde su dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="066bc-104">**Summary:** This article describes how you use DomainKeys Identified Mail (DKIM) with Microsoft 365 to ensure that destination email systems trust messages sent outbound from your custom domain.</span></span>

<span data-ttu-id="066bc-105">Debería usar DKIM además de SPF y DMARC para ayudarle a evitar que los suplantadores de identidad envíen mensajes que parece que provienen de su dominio.</span><span class="sxs-lookup"><span data-stu-id="066bc-105">You should use DKIM in addition to SPF and DMARC to help prevent spoofers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="066bc-106">DKIM le permite agregar una firma digital a los mensajes de correo electrónico salientes en el encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="066bc-106">DKIM lets you add a digital signature to outbound email messages in the message header.</span></span> <span data-ttu-id="066bc-107">Puede sonar complicado, pero realmente no lo es.</span><span class="sxs-lookup"><span data-stu-id="066bc-107">It may sound complicated, but it's really not.</span></span> <span data-ttu-id="066bc-108">Cuando configura DKIM, autoriza su dominio para asociar, o firmar, su nombre a un mensaje de correo electrónico mediante la autenticación criptográfica.</span><span class="sxs-lookup"><span data-stu-id="066bc-108">When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message by using cryptographic authentication.</span></span> <span data-ttu-id="066bc-109">Los sistemas de correo electrónico que reciben correo electrónico desde el dominio pueden usar esta firma digital para ayudarles a determinar si el correo entrante que reciben es legítimo.</span><span class="sxs-lookup"><span data-stu-id="066bc-109">Email systems that receive email from your domain can use this digital signature to help determine if incoming email that they receive is legitimate.</span></span>

<span data-ttu-id="066bc-110">Básicamente, usa una clave privada para cifrar el encabezado del correo electrónico saliente del dominio.</span><span class="sxs-lookup"><span data-stu-id="066bc-110">Basically, you use a private key to encrypt the header in your domain's outgoing email.</span></span> <span data-ttu-id="066bc-111">Publica una clave pública en los registros DNS del dominio que los servidores de recepción pueden usar para descodificar la firma.</span><span class="sxs-lookup"><span data-stu-id="066bc-111">You publish a public key to your domain's DNS records that receiving servers can then use to decode the signature.</span></span> <span data-ttu-id="066bc-112">Usan la clave pública para comprobar que los mensajes proceden realmente de usted y no de alguien que está *suplantando la identidad* del dominio.</span><span class="sxs-lookup"><span data-stu-id="066bc-112">They use the public key to verify that the messages are really coming from you and not coming from someone *spoofing* your domain.</span></span>

<span data-ttu-id="066bc-113">Microsoft 365 configura automáticamente DKIM para sus dominios "onmicrosoft.com" iniciales.</span><span class="sxs-lookup"><span data-stu-id="066bc-113">Microsoft 365 automatically sets up DKIM for its initial 'onmicrosoft.com' domains.</span></span> <span data-ttu-id="066bc-114">Lo que significa que no es necesario realizar ninguna acción para configurar DKIM para un nombre de dominio inicial (por ejemplo, litware.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="066bc-114">That means you don't need to do anything to set up DKIM for any initial domain names (for example, litware.onmicrosoft.com).</span></span> <span data-ttu-id="066bc-115">Para más información sobre los dominios, vea [Preguntas más frecuentes de dominios](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="066bc-115">For more information about domains, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="066bc-116">También puede elegir no hacer nada acerca de DKIM para su dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="066bc-116">You can choose to do nothing about DKIM for your custom domain too.</span></span> <span data-ttu-id="066bc-117">Si usted no configura DKIM para su dominio personalizado, Microsoft 365 crea un par de claves privadas y públicas, que permiten que DKIM firme y configure la directiva predeterminada de Microsoft 365 para su dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="066bc-117">If you don't set up DKIM for your custom domain, Microsoft 365 creates a private and public key pair, enables DKIM signing, and then configures the Microsoft 365 default policy for your custom domain.</span></span> <span data-ttu-id="066bc-118">Aunque esto suponga una cobertura suficiente para la mayoría de los clientes, debería configurar manualmente DKIM para su dominio personalizado en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="066bc-118">While this is sufficient coverage for most customers, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>

- <span data-ttu-id="066bc-119">Tiene más de un dominio personalizado en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="066bc-119">You have more than one custom domain in Microsoft 365</span></span>

- <span data-ttu-id="066bc-120">También va a configurar DMARC (recomendado)</span><span class="sxs-lookup"><span data-stu-id="066bc-120">You're going to set up DMARC too (recommended)</span></span>

- <span data-ttu-id="066bc-121">Quiere tener el control sobre la clave privada</span><span class="sxs-lookup"><span data-stu-id="066bc-121">You want control over your private key</span></span>

- <span data-ttu-id="066bc-122">Quiere personalizar los registros CNAME</span><span class="sxs-lookup"><span data-stu-id="066bc-122">You want to customize your CNAME records</span></span>

- <span data-ttu-id="066bc-123">Quiere configurar claves de DKIM para los correos electrónicos que se originen en un dominio de terceros, por ejemplo, si usa un troyano de envío masivo de correo electrónico de terceros.</span><span class="sxs-lookup"><span data-stu-id="066bc-123">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>

<span data-ttu-id="066bc-124">En este artículo:</span><span class="sxs-lookup"><span data-stu-id="066bc-124">In this article:</span></span>

- [<span data-ttu-id="066bc-125">Cómo DKIM funciona mejor que SPF solo para evitar la suplantación de identidad malintencionada</span><span class="sxs-lookup"><span data-stu-id="066bc-125">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [<span data-ttu-id="066bc-126">Actualizar manualmente las claves de 1024 bits a claves de cifrado DKIM de 2048 bits</span><span class="sxs-lookup"><span data-stu-id="066bc-126">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [<span data-ttu-id="066bc-127">Pasos que necesita seguir para configurar manualmente DKIM</span><span class="sxs-lookup"><span data-stu-id="066bc-127">Steps you need to do to manually set up DKIM</span></span>](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [<span data-ttu-id="066bc-128">Configurar DKIM para más de un dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="066bc-128">To configure DKIM for more than one custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [<span data-ttu-id="066bc-129">Deshabilitar la directiva de firmas DKIM para un dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="066bc-129">Disabling the DKIM signing policy for a custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [<span data-ttu-id="066bc-130">Comportamiento predeterminado para DKIM y Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="066bc-130">Default behavior for DKIM and Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [<span data-ttu-id="066bc-131">Configurar DKIM para que un servicio de terceros pueda enviar, o suplantar, correo electrónico en nombre de su dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="066bc-131">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [<span data-ttu-id="066bc-132">Pasos siguientes: una vez configurado DKIM para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="066bc-132">Next steps: After you set up DKIM for Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a><span data-ttu-id="066bc-133">Cómo DKIM funciona mejor que SPF solo para evitar la suplantación de identidad malintencionada</span><span class="sxs-lookup"><span data-stu-id="066bc-133">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>
<span data-ttu-id="066bc-134"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="066bc-134"><a name="HowDKIMWorks"> </a></span></span>

<span data-ttu-id="066bc-135">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header.</span><span class="sxs-lookup"><span data-stu-id="066bc-135">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header.</span></span> <span data-ttu-id="066bc-136">When you forward a message, portions of that message's envelope can be stripped away by the forwarding server.</span><span class="sxs-lookup"><span data-stu-id="066bc-136">When you forward a message, portions of that message's envelope can be stripped away by the forwarding server.</span></span> <span data-ttu-id="066bc-137">Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span><span class="sxs-lookup"><span data-stu-id="066bc-137">Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>

![Diagrama que muestra un mensaje reenviado que pasa por la autenticación DKIM, donde se produce un error en la comprobación de SPF.](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

<span data-ttu-id="066bc-139">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result.</span><span class="sxs-lookup"><span data-stu-id="066bc-139">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result.</span></span> <span data-ttu-id="066bc-140">The addition of DKIM in this scenario reduces false positive spam reporting.</span><span class="sxs-lookup"><span data-stu-id="066bc-140">The addition of DKIM in this scenario reduces false positive spam reporting.</span></span> <span data-ttu-id="066bc-141">Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF.</span><span class="sxs-lookup"><span data-stu-id="066bc-141">Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF.</span></span> <span data-ttu-id="066bc-142">We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span><span class="sxs-lookup"><span data-stu-id="066bc-142">We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>

<span data-ttu-id="066bc-143">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers.</span><span class="sxs-lookup"><span data-stu-id="066bc-143">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers.</span></span> <span data-ttu-id="066bc-144">The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header.</span><span class="sxs-lookup"><span data-stu-id="066bc-144">The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header.</span></span> <span data-ttu-id="066bc-145">The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message.</span><span class="sxs-lookup"><span data-stu-id="066bc-145">The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message.</span></span> <span data-ttu-id="066bc-146">If the message is verified, the DKIM check passes.</span><span class="sxs-lookup"><span data-stu-id="066bc-146">If the message is verified, the DKIM check passes.</span></span>

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a><span data-ttu-id="066bc-147">Actualizar manualmente las claves de 1024 bits a claves de cifrado DKIM de 2048 bits</span><span class="sxs-lookup"><span data-stu-id="066bc-147">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>
<span data-ttu-id="066bc-148"><a name="1024to2048DKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="066bc-148"><a name="1024to2048DKIM"> </a></span></span>

<span data-ttu-id="066bc-149">Ya que ambos valores de bits, 1024 y 2048, son compatibles con las claves DKIM, estas instrucciones le indicarán cómo actualizar la clave de 1024 bits a 2048.</span><span class="sxs-lookup"><span data-stu-id="066bc-149">Since both 1024 and 2048 bitness are supported for DKIM keys, these directions will tell you how to upgrade your 1024-bit key to 2048.</span></span> <span data-ttu-id="066bc-150">Los pasos que se muestran a continuación son dos casos de uso distintos, elija el que mejor se ajuste a su configuración.</span><span class="sxs-lookup"><span data-stu-id="066bc-150">The steps below are for two use-cases, please choose the one that best fits your configuration.</span></span>

1. <span data-ttu-id="066bc-151">Cuando **ya tiene configuradas las DKIM**, cambie el valor de los bits de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="066bc-151">When you **already have DKIM configured**, you rotate bitness as follows:</span></span>

   1. <span data-ttu-id="066bc-152">[Conéctese con las cargas de trabajo de Office 365 a través de PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="066bc-152">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="066bc-153">(El cmdlet viene de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="066bc-153">(The cmdlet comes from Exchange Online.)</span></span>
   1. <span data-ttu-id="066bc-154">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="066bc-154">Run the following command:</span></span>

      ```powershell 
      Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
      ```

1. <span data-ttu-id="066bc-155">O para una **nueva implementación de DKIM**:</span><span class="sxs-lookup"><span data-stu-id="066bc-155">Or for a **new implementation of DKIM**:</span></span>

   1. <span data-ttu-id="066bc-156">[Conéctese con las cargas de trabajo de Office 365 a través de PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="066bc-156">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="066bc-157">(Este es un cmdlet de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="066bc-157">(This is an Exchange Online cmdlet.)</span></span>
   1. <span data-ttu-id="066bc-158">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="066bc-158">Run the following command:</span></span>

      ```powershell
      New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True
      ```

<span data-ttu-id="066bc-159">Manténgase conectado a Microsoft 365 para *verificar* la configuración.</span><span class="sxs-lookup"><span data-stu-id="066bc-159">Stay connected to Microsoft 365 to *verify* the configuration.</span></span>

1. <span data-ttu-id="066bc-160">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="066bc-160">Run the following command:</span></span>

   ```powershell
   Get-DkimSigningConfig -Identity {Domain for which the configuration was set} | Format-List
   ```

> [!TIP]
> <span data-ttu-id="066bc-161">Esta nueva clave de 2048 bits tendrá efecto en el RotateOnDate y mientras tanto enviará los mensajes de correo electrónico con la clave de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="066bc-161">This new 2048-bit key takes effect on the RotateOnDate, and will send emails with the 1024-bit key in the interim.</span></span> <span data-ttu-id="066bc-162">Después de cuatro días, puede volver a probar con la clave de 2048 bits (es decir, cuando la rotación surta efecto al segundo selector).</span><span class="sxs-lookup"><span data-stu-id="066bc-162">After four days, you can test again with the 2048-bit key (that is, once the rotation takes effect to the second selector).</span></span>

<span data-ttu-id="066bc-163">Si desea rotar hasta el segundo selector, las opciones son: a) dejar que el servicio de Microsoft 365 rote el selector y actualice al valor de 2048 bits en los próximos 6 meses, o b) después de 4 días y de confirmar que se está utilizando el valor de 2048 bits, rote manualmente la clave del segundo selector por usando el cmdlet apropiado de los que se enumeran arriba.</span><span class="sxs-lookup"><span data-stu-id="066bc-163">If you want to rotate to the second selector, your options are a) let the Microsoft 365 service rotate the selector and upgrade to 2048-bitness within the next 6 months, or b) after 4 days and confirming that 2048-bitness is in use, manually rotate the second selector key by using the appropriate cmdlet listed above.</span></span>

## <a name="steps-you-need-to-do-to-manually-set-up-dkim"></a><span data-ttu-id="066bc-164">Pasos que necesita seguir para configurar manualmente DKIM</span><span class="sxs-lookup"><span data-stu-id="066bc-164">Steps you need to do to manually set up DKIM</span></span>
<span data-ttu-id="066bc-165"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="066bc-165"><a name="SetUpDKIMO365"> </a></span></span>

<span data-ttu-id="066bc-166">Para configurar DKIM, deberá completar estos pasos:</span><span class="sxs-lookup"><span data-stu-id="066bc-166">To configure DKIM, you will complete these steps:</span></span>

- [<span data-ttu-id="066bc-167">Publicar dos registros CNAME para su dominio personalizado en DNS</span><span class="sxs-lookup"><span data-stu-id="066bc-167">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [<span data-ttu-id="066bc-168">Habilitar la firma DKIM para su dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="066bc-168">Enable DKIM signing for your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="066bc-169">Publicar dos registros CNAME para su dominio personalizado en DNS</span><span class="sxs-lookup"><span data-stu-id="066bc-169">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="066bc-170"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="066bc-170"><a name="Publish2CNAME"> </a></span></span>

<span data-ttu-id="066bc-171">Para cada dominio para el que quiera agregar una firma DKIM en DNS, necesita publicar dos registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="066bc-171">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span>

<span data-ttu-id="066bc-172">Ejecute los siguientes comandos para crear los registros del selector:</span><span class="sxs-lookup"><span data-stu-id="066bc-172">Run the following commands to create the selector records:</span></span>

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

<span data-ttu-id="066bc-173">Si ha aprovisionado dominios personalizados adicionales además del dominio inicial de Microsoft 365, debe publicar dos registros CNAME para cada dominio adicional.</span><span class="sxs-lookup"><span data-stu-id="066bc-173">If you have provisioned custom domains in addition to the initial domain in Microsoft 365, you must publish two CNAME records for each additional domain.</span></span> <span data-ttu-id="066bc-174">Por lo tanto, si tiene dos dominios, debe publicar dos registros CNAME adicionales, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="066bc-174">So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>

<span data-ttu-id="066bc-175">Use el formato siguiente para los registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="066bc-175">Use the following format for the CNAME records.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="066bc-176">Si es uno de nuestros clientes de GCC High, calcularemos _domainGuid_ de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="066bc-176">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="066bc-177">En lugar de buscar el registro MX para su _initialDomain_ para calcular _domainGuid_, lo calculamos directamente desde el dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="066bc-177">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="066bc-178">Por ejemplo, si su dominio personalizado es "contoso.com", su domainGuid se convierte en "contoso-com", los puntos se reemplazan por un guión.</span><span class="sxs-lookup"><span data-stu-id="066bc-178">For example, if your customized domain is "contoso.com" your domainGuid becomes "contoso-com", any periods are replaced with a dash.</span></span> <span data-ttu-id="066bc-179">Por lo tanto, independientemente del registro MX al que señale su initialDomain, siempre se usará el método anterior para calcular el domainGuid que se usará en sus registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="066bc-179">So, regardless of what MX record your initialDomain points to, you'll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

<span data-ttu-id="066bc-180">Donde:</span><span class="sxs-lookup"><span data-stu-id="066bc-180">Where:</span></span>

- <span data-ttu-id="066bc-181">Para Microsoft 365, los selectores siempre serán "selector1" o "selector2".</span><span class="sxs-lookup"><span data-stu-id="066bc-181">For Microsoft 365, the selectors will always be "selector1" or "selector2".</span></span>

- <span data-ttu-id="066bc-182">El _domainGUID_ es el mismo que el _domainGUID_ del registro MX personalizado para su dominio personalizado que aparece antes de mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="066bc-182">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com.</span></span> <span data-ttu-id="066bc-183">Por ejemplo, en el siguiente registro MX del dominio contoso.com, el _domainGUID_ es contoso-com:</span><span class="sxs-lookup"><span data-stu-id="066bc-183">For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span>

  > <span data-ttu-id="066bc-184">contoso.com.</span><span class="sxs-lookup"><span data-stu-id="066bc-184">contoso.com.</span></span>  <span data-ttu-id="066bc-185">3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="066bc-185">3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span></span>

- <span data-ttu-id="066bc-186">_initialDomain_ es el dominio que usó al registrarse en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="066bc-186">_initialDomain_ is the domain that you used when you signed up for Microsoft 365.</span></span> <span data-ttu-id="066bc-187">Los dominios iniciales siempre terminan en onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="066bc-187">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="066bc-188">Para obtener información sobre cómo determinar el dominio inicial, vea [Preguntas más frecuentes de dominios](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="066bc-188">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="066bc-189">Por ejemplo, si tiene un dominio inicial de cohovineyardandwinery.onmicrosoft.com y dos dominios personalizados cohovineyard.com y cohowinery.com, necesitará configurar dos registros CNAME para cada dominio adicional, un total de cuatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="066bc-189">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>

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
> <span data-ttu-id="066bc-190">Es importante crear el segundo registro, pero solo uno de los selectores puede estar disponible en el momento de la creación.</span><span class="sxs-lookup"><span data-stu-id="066bc-190">It's important to create the second record, but only one of the selectors may be available at the time of creation.</span></span> <span data-ttu-id="066bc-191">En esencia, el segundo selector podría apuntar a una dirección que aún no ha sido creada.</span><span class="sxs-lookup"><span data-stu-id="066bc-191">In essence, the second selector might point to an address that hasn't been created yet.</span></span> <span data-ttu-id="066bc-192">Aun así, recomendamos crear el segundo registro CNAME, ya que la rotación de las teclas será perfecta.</span><span class="sxs-lookup"><span data-stu-id="066bc-192">We still recommended that you create the second CNAME record, because your key rotation will be seamless.</span></span>

> [!CAUTION]
> <span data-ttu-id="066bc-193">La rotación automática de clave se ha deshabilitado temporalmente porque implementamos algunos cambios de diseño en cómo hemos creado claves.</span><span class="sxs-lookup"><span data-stu-id="066bc-193">Automatic key rotation has been temporarily disabled as we implement some design changes in how we create keys.</span></span> <span data-ttu-id="066bc-194">Es recomendable tener varias claves para que pueda rotarlas periódicamente.</span><span class="sxs-lookup"><span data-stu-id="066bc-194">It's a good practice to have multiple keys so that you can rotate them periodically.</span></span> <span data-ttu-id="066bc-195">Aunque es difícil de averiguar, sigue siendo una estrategia práctica para protegerse frente a cosas como la suplantación.</span><span class="sxs-lookup"><span data-stu-id="066bc-195">Although it's hard to crack, it's still a practical mitigation strategy to protect against things like impersonation.</span></span> <span data-ttu-id="066bc-196">Puede seguir el documento [Rotate-DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig) para aprender a hacerlo en su organización.</span><span class="sxs-lookup"><span data-stu-id="066bc-196">You can follow the [Rotate-DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig) document to help do this for your organization.</span></span> <span data-ttu-id="066bc-197">Esperamos que la rotación automática se vuelva a habilitar en agosto de 2020.</span><span class="sxs-lookup"><span data-stu-id="066bc-197">We expect that automatic rotation will be enabled again by August 2020.</span></span>

### <a name="enable-dkim-signing-for-your-custom-domain"></a><span data-ttu-id="066bc-198">Habilitar la firma DKIM para su dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="066bc-198">Enable DKIM signing for your custom domain</span></span>
<span data-ttu-id="066bc-199"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="066bc-199"><a name="EnableDKIMinO365"> </a></span></span>

<span data-ttu-id="066bc-200">Una vez que haya publicado los registros CNAME en DNS, está preparado para habilitar la firma DKIM mediante Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="066bc-200">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Microsoft 365.</span></span> <span data-ttu-id="066bc-201">Puede hacerlo a través del Centro de administración de Microsoft 365 o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="066bc-201">You can do this either through the Microsoft 365 admin center or by using PowerShell.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a><span data-ttu-id="066bc-202">Para habilitar la firma DKIM para su dominio personalizado a través del Centro de administración</span><span class="sxs-lookup"><span data-stu-id="066bc-202">To enable DKIM signing for your custom domain through the admin center</span></span>

1. <span data-ttu-id="066bc-203">[Inicie sesión en Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="066bc-203">[Sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="066bc-204">Seleccione el icono del iniciador de aplicaciones en la esquina superior izquierda y elija **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="066bc-204">Select the app launcher icon in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="066bc-205">En el panel de navegación inferior izquierdo, expanda **Administración** y elija **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="066bc-205">In the lower-left navigation, expand **Admin** and choose **Exchange**.</span></span>

4. <span data-ttu-id="066bc-206">Vaya a **Protección** \> **dkim**.</span><span class="sxs-lookup"><span data-stu-id="066bc-206">Go to **Protection** \> **dkim**.</span></span>

5. <span data-ttu-id="066bc-207">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**.</span><span class="sxs-lookup"><span data-stu-id="066bc-207">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**.</span></span> <span data-ttu-id="066bc-208">Repeat this step for each custom domain.</span><span class="sxs-lookup"><span data-stu-id="066bc-208">Repeat this step for each custom domain.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="066bc-209">Para habilitar la firma DKIM para su dominio personalizado mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="066bc-209">To enable DKIM signing for your custom domain by using PowerShell</span></span>

1. <span data-ttu-id="066bc-210">[Conéctese al PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="066bc-210">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="066bc-211">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="066bc-211">Run the following command:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity <domain> -Enabled $true
   ```

   <span data-ttu-id="066bc-212">Donde _domain_ es el nombre del dominio personalizado para el que quiere habilitar la firma DKIM.</span><span class="sxs-lookup"><span data-stu-id="066bc-212">Where _domain_ is the name of the custom domain that you want to enable DKIM signing for.</span></span>

   <span data-ttu-id="066bc-213">Por ejemplo, para el dominio contoso.com:</span><span class="sxs-lookup"><span data-stu-id="066bc-213">For example, for the domain contoso.com:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a><span data-ttu-id="066bc-214">Para confirmar que la firma DKIM está configurada correctamente en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="066bc-214">To Confirm DKIM signing is configured properly for Microsoft 365</span></span>

<span data-ttu-id="066bc-215">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM.</span><span class="sxs-lookup"><span data-stu-id="066bc-215">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM.</span></span> <span data-ttu-id="066bc-216">This allows time for the DKIM information about the domain to be spread throughout the network.</span><span class="sxs-lookup"><span data-stu-id="066bc-216">This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>

- <span data-ttu-id="066bc-217">Envíe un mensaje desde una cuenta dentro de su dominio habilitado para DKIM en Microsoft 365 a otra cuenta de correo electrónico como outlook.com o Hotmail.com.</span><span class="sxs-lookup"><span data-stu-id="066bc-217">Send a message from an account within your Microsoft 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>

- <span data-ttu-id="066bc-218">Do not use an aol.com account for testing purposes.</span><span class="sxs-lookup"><span data-stu-id="066bc-218">Do not use an aol.com account for testing purposes.</span></span> <span data-ttu-id="066bc-219">AOL may skip the DKIM check if the SPF check passes.</span><span class="sxs-lookup"><span data-stu-id="066bc-219">AOL may skip the DKIM check if the SPF check passes.</span></span> <span data-ttu-id="066bc-220">This will nullify your test.</span><span class="sxs-lookup"><span data-stu-id="066bc-220">This will nullify your test.</span></span>

- <span data-ttu-id="066bc-221">Open the message and look at the header.</span><span class="sxs-lookup"><span data-stu-id="066bc-221">Open the message and look at the header.</span></span> <span data-ttu-id="066bc-222">Instructions for viewing the header for the message will vary depending on your messaging client.</span><span class="sxs-lookup"><span data-stu-id="066bc-222">Instructions for viewing the header for the message will vary depending on your messaging client.</span></span> <span data-ttu-id="066bc-223">For instructions on viewing message headers in Outlook, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span><span class="sxs-lookup"><span data-stu-id="066bc-223">For instructions on viewing message headers in Outlook, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

  <span data-ttu-id="066bc-224">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries.</span><span class="sxs-lookup"><span data-stu-id="066bc-224">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries.</span></span> <span data-ttu-id="066bc-225">The message will look something like this example:</span><span class="sxs-lookup"><span data-stu-id="066bc-225">The message will look something like this example:</span></span>

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- <span data-ttu-id="066bc-226">Look for the Authentication-Results header.</span><span class="sxs-lookup"><span data-stu-id="066bc-226">Look for the Authentication-Results header.</span></span> <span data-ttu-id="066bc-227">While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span><span class="sxs-lookup"><span data-stu-id="066bc-227">While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span>

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a><span data-ttu-id="066bc-228">Configuración de DKIM para más de un dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="066bc-228">To configure DKIM for more than one custom domain</span></span>
<span data-ttu-id="066bc-229"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="066bc-229"><a name="DKIMMultiDomain"> </a></span></span>

<span data-ttu-id="066bc-230">Si en algún momento en el futuro decide agregar otro dominio personalizado y quiere habilitar DKIM para el dominio nuevo, debe completar los pasos de este artículo para cada dominio.</span><span class="sxs-lookup"><span data-stu-id="066bc-230">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain.</span></span> <span data-ttu-id="066bc-231">En concreto, complete todos los pasos de [Lo que necesita hacer para configurar manualmente DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span><span class="sxs-lookup"><span data-stu-id="066bc-231">Specifically, complete all steps in [What you need to do to manually set up DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a><span data-ttu-id="066bc-232">Deshabilitación de la directiva de firmas DKIM para un dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="066bc-232">Disabling the DKIM signing policy for a custom domain</span></span> 
<span data-ttu-id="066bc-233"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="066bc-233"><a name="DisableDKIMSigningPolicy"> </a></span></span>

<span data-ttu-id="066bc-234">Deshabilitar la directiva de firmas no deshabilita DKIM completamente.</span><span class="sxs-lookup"><span data-stu-id="066bc-234">Disabling the signing policy does not completely disable DKIM.</span></span> <span data-ttu-id="066bc-235">Después de un período de tiempo, Microsoft 365 aplicará automáticamente la directiva predeterminada para el dominio.</span><span class="sxs-lookup"><span data-stu-id="066bc-235">After a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span> <span data-ttu-id="066bc-236">Para más información sobre esta firma, consulte [Comportamiento predeterminado para DKIM y Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span><span class="sxs-lookup"><span data-stu-id="066bc-236">For more information, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="066bc-237">Para deshabilitar la directiva de firmas DKIM mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="066bc-237">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="066bc-238">[Conéctese al PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="066bc-238">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="066bc-239">Ejecute uno de los siguientes comandos para cada dominio para el que quiera deshabilitar la firma DKIM.</span><span class="sxs-lookup"><span data-stu-id="066bc-239">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity <domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="066bc-240">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="066bc-240">For example:</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="066bc-241">O bien</span><span class="sxs-lookup"><span data-stu-id="066bc-241">Or</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   <span data-ttu-id="066bc-242">Donde _number_ es el índice de la directiva.</span><span class="sxs-lookup"><span data-stu-id="066bc-242">Where _number_ is the index of the policy.</span></span> <span data-ttu-id="066bc-243">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="066bc-243">For example:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a><span data-ttu-id="066bc-244">Comportamiento predeterminado para DKIM y Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="066bc-244">Default behavior for DKIM and Microsoft 365</span></span>
<span data-ttu-id="066bc-245"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="066bc-245"><a name="DefaultDKIMbehavior"> </a></span></span>

<span data-ttu-id="066bc-246">Si no habilita DKIM, Microsoft 365 crea automáticamente una clave pública DKIM de 1024 bits para el dominio predeterminado y la clave privada asociada que se almacena internamente en nuestro centro de datos.</span><span class="sxs-lookup"><span data-stu-id="066bc-246">If you do not enable DKIM, Microsoft 365 automatically creates a 1024-bit DKIM public key for your default domain and the associated private key which we store internally in our datacenter.</span></span> <span data-ttu-id="066bc-247">De forma predeterminada, Microsoft 365 usa una configuración de firmas predeterminada para los dominios que no tienen una directiva local.</span><span class="sxs-lookup"><span data-stu-id="066bc-247">By default, Microsoft 365 uses a default signing configuration for domains that do not have a policy in place.</span></span> <span data-ttu-id="066bc-248">Esto significa que si no configura DKIM, Microsoft 365 usará su política predeterminada y se creará la clave para habilitar DKIM para el dominio.</span><span class="sxs-lookup"><span data-stu-id="066bc-248">This means that if you do not set up DKIM yourself, Microsoft 365 will use its default policy and keys it creates to enable DKIM for your domain.</span></span>

<span data-ttu-id="066bc-249">Además, si deshabilita la firma DKIM después de habilitarla, después de un período de tiempo, Microsoft 365 aplicará automáticamente la directiva predeterminada para el dominio.</span><span class="sxs-lookup"><span data-stu-id="066bc-249">Also, if you disable DKIM signing after enabling it, after a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span>

<span data-ttu-id="066bc-250">En el ejemplo siguiente, suponga que Microsoft 365 ha habilitado DKIM para fabrikam.com, no el administrador del dominio.</span><span class="sxs-lookup"><span data-stu-id="066bc-250">In the following example, suppose that DKIM for fabrikam.com was enabled by Microsoft 365, not by the administrator of the domain.</span></span> <span data-ttu-id="066bc-251">Esto significa que los CNAME necesarios no existen en DNS.</span><span class="sxs-lookup"><span data-stu-id="066bc-251">This means that the required CNAMEs do not exist in DNS.</span></span> <span data-ttu-id="066bc-252">Las firmas DKIM para el correo electrónico de este dominio tendrán un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="066bc-252">DKIM signatures for email from this domain will look something like this:</span></span>

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

<span data-ttu-id="066bc-253">En este ejemplo, el nombre de host y el dominio contienen los valores a los que señalaría el registro CNAME si el administrador del dominio hubiera habilitado la firma DKIM para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="066bc-253">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator.</span></span> <span data-ttu-id="066bc-254">Finalmente, cada mensaje enviado desde Microsoft 365 contendrá una firma DKIM.</span><span class="sxs-lookup"><span data-stu-id="066bc-254">Eventually, every single message sent from Microsoft 365 will be DKIM-signed.</span></span> <span data-ttu-id="066bc-255">Si habilita DKIM, el dominio será el mismo que el dominio de la dirección en el campo De:, en este caso, fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="066bc-255">If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com.</span></span> <span data-ttu-id="066bc-256">Si no lo hace, el dominio no se alineará y en su lugar se usará el dominio inicial de la organización.</span><span class="sxs-lookup"><span data-stu-id="066bc-256">If you don't, it will not align and instead will use your organization's initial domain.</span></span> <span data-ttu-id="066bc-257">Para obtener información sobre cómo determinar el dominio inicial, vea [Preguntas más frecuentes de dominios](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="066bc-257">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="066bc-258">Configurar DKIM para que un servicio de terceros pueda enviar, o suplantar, correo electrónico en nombre de su dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="066bc-258">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="066bc-259"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="066bc-259"><a name="SetUp3rdPartyspoof"> </a></span></span>

<span data-ttu-id="066bc-260">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service.</span><span class="sxs-lookup"><span data-stu-id="066bc-260">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service.</span></span> <span data-ttu-id="066bc-261">This requires coordination between yourself and the third-party in order to set up the necessary DNS records.</span><span class="sxs-lookup"><span data-stu-id="066bc-261">This requires coordination between yourself and the third-party in order to set up the necessary DNS records.</span></span> <span data-ttu-id="066bc-262">No two organizations do it exactly the same way.</span><span class="sxs-lookup"><span data-stu-id="066bc-262">No two organizations do it exactly the same way.</span></span> <span data-ttu-id="066bc-263">Instead, the process depends entirely on the organization.</span><span class="sxs-lookup"><span data-stu-id="066bc-263">Instead, the process depends entirely on the organization.</span></span>

<span data-ttu-id="066bc-264">Un mensaje de ejemplo que muestra un DKIM configurado correctamente para contoso.com y bulkemailprovider.com puede tener el aspecto siguiente:</span><span class="sxs-lookup"><span data-stu-id="066bc-264">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="066bc-265">En este ejemplo, para conseguir este resultado:</span><span class="sxs-lookup"><span data-stu-id="066bc-265">In this example, in order to achieve this result:</span></span>

1. <span data-ttu-id="066bc-266">El proveedor de correo electrónico masivo le ha proporcionado una clave DKIM pública a Contoso.</span><span class="sxs-lookup"><span data-stu-id="066bc-266">Bulk Email Provider gave Contoso a public DKIM key.</span></span>

2. <span data-ttu-id="066bc-267">Contoso ha publicado la clave DKIM en su registro DNS.</span><span class="sxs-lookup"><span data-stu-id="066bc-267">Contoso published the DKIM key to its DNS record.</span></span>

3. <span data-ttu-id="066bc-268">When sending email, Bulk Email Provider signs the key with the corresponding private key.</span><span class="sxs-lookup"><span data-stu-id="066bc-268">When sending email, Bulk Email Provider signs the key with the corresponding private key.</span></span> <span data-ttu-id="066bc-269">By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span><span class="sxs-lookup"><span data-stu-id="066bc-269">By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>

4. <span data-ttu-id="066bc-270">Los sistemas de correo electrónico de recepción realizan una comprobación DKIM mediante la autenticación del valor d=\<domain\> comparado con el dominio en el campo De: (5322.From) de la dirección del mensaje.</span><span class="sxs-lookup"><span data-stu-id="066bc-270">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message.</span></span> <span data-ttu-id="066bc-271">En este ejemplo, los valores coinciden:</span><span class="sxs-lookup"><span data-stu-id="066bc-271">In this example, the values match:</span></span>

   > <span data-ttu-id="066bc-272">sender@**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="066bc-272">sender@**contoso.com**</span></span>

   > <span data-ttu-id="066bc-273">d=**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="066bc-273">d=**contoso.com**</span></span>

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a><span data-ttu-id="066bc-274">Pasos siguientes: una vez configurado DKIM para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="066bc-274">Next steps: After you set up DKIM for Microsoft 365</span></span>
<span data-ttu-id="066bc-275"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="066bc-275"><a name="DKIMNextSteps"> </a></span></span>

<span data-ttu-id="066bc-276">Aunque DKIM está diseñado para ayudar a evitar la suplantación de identidad, DKIM funciona mejor con SPF y DMARC.</span><span class="sxs-lookup"><span data-stu-id="066bc-276">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="066bc-277">Cuando haya configurado DKIM, si todavía no ha configurado SPF, debería hacerlo.</span><span class="sxs-lookup"><span data-stu-id="066bc-277">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="066bc-278">Para obtener una introducción rápida a SPF y configurarlo rápidamente, consulte [Configuración de SPF en Microsoft 365 para evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="066bc-278">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="066bc-279">Para comprender en detalle cómo Microsoft 365 usa SPF, o para la solución de problemas o las implementaciones no estándar (por ejemplo, implementaciones híbridas), comience con [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md) (Cómo Microsoft 365 usa el marco de directivas permanente [SPF] para evitar la suplantación de identidad).</span><span class="sxs-lookup"><span data-stu-id="066bc-279">For a more in-depth understanding of how Microsoft 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="066bc-280">Después, consulte [Uso de DMARC para validar el correo electrónico](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="066bc-280">Next, see [Use DMARC to validate email](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="066bc-281">Los [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md) incluyen la sintaxis y los campos de encabezado que usa Microsoft 365 para efectuar comprobaciones de DKIM.</span><span class="sxs-lookup"><span data-stu-id="066bc-281">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for DKIM checks.</span></span>
