---
title: Usar DKIM para el correo electrónico en su dominio personalizado en Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/27/2019, 10/8/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
description: 'Resumen: Este artículo describe cómo usa DomainKeys Identified Mail (DKIM) con Office 365 para asegurarse de que los sistemas de correo electrónico de destino confían en los mensajes enviados desde su dominio personalizado.'
ms.openlocfilehash: bebbc355e6d16d5571733295ce0e48b91332f863
ms.sourcegitcommit: 0d423b50d2f1f4eccd64e35e00f67313244efba9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "37424236"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain-in-office-365"></a><span data-ttu-id="2df0f-103">Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365</span><span class="sxs-lookup"><span data-stu-id="2df0f-103">Use DKIM to validate outbound email sent from your custom domain in Office 365</span></span>

 <span data-ttu-id="2df0f-104">**Resumen:** Este artículo describe cómo usa DomainKeys Identified Mail (DKIM) con Office 365 para asegurarse de que los sistemas de correo electrónico de destino confían en los mensajes enviados desde su dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="2df0f-104">**Summary:** This article describes how you use DomainKeys Identified Mail (DKIM) with Office 365 to ensure that destination email systems trust messages sent from your custom domain.</span></span>
  
<span data-ttu-id="2df0f-105">Debería usar DKIM además de SPF y DMARC para ayudarle a evitar que los suplantadores de identidad envíen mensajes que parece que provienen de su dominio.</span><span class="sxs-lookup"><span data-stu-id="2df0f-105">You should use DKIM in addition to SPF and DMARC to help prevent spoofers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="2df0f-106">DKIM le permite agregar una firma digital a los mensajes de correo electrónico salientes en el encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2df0f-106">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="2df0f-107">Puede sonar complicado, pero realmente no lo es.</span><span class="sxs-lookup"><span data-stu-id="2df0f-107">It may sound complicated, but it's really not.</span></span> <span data-ttu-id="2df0f-108">Cuando configura DKIM, autoriza su dominio para asociar, o firmar, su nombre a un mensaje de correo electrónico mediante la autenticación criptográfica.</span><span class="sxs-lookup"><span data-stu-id="2df0f-108">When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message by using cryptographic authentication.</span></span> <span data-ttu-id="2df0f-109">Los sistemas de correo electrónico que reciben correo electrónico desde el dominio pueden usar esta firma digital para ayudarles a determinar si el correo entrante que reciben es legítimo.</span><span class="sxs-lookup"><span data-stu-id="2df0f-109">Email systems that receive email from your domain can use this digital signature to help determine if incoming email that they receive is legitimate.</span></span>
  
<span data-ttu-id="2df0f-110">Básicamente, usa una clave privada para cifrar el encabezado del correo electrónico saliente del dominio.</span><span class="sxs-lookup"><span data-stu-id="2df0f-110">Basically, you use a private key to encrypt the header in your domain's outgoing email.</span></span> <span data-ttu-id="2df0f-111">Publica una clave pública en los registros DNS del dominio que los servidores de recepción pueden usar para descodificar la firma.</span><span class="sxs-lookup"><span data-stu-id="2df0f-111">You publish a public key to your domain's DNS records that receiving servers can then use to decode the signature.</span></span> <span data-ttu-id="2df0f-112">Usan la clave pública para comprobar que los mensajes proceden realmente de usted y no de alguien que está *suplantando la identidad* del dominio.</span><span class="sxs-lookup"><span data-stu-id="2df0f-112">They use the public key to verify that the messages are really coming from you and not coming from someone spoofing your domain.</span></span>
  
<span data-ttu-id="2df0f-113">Office 365 configura automáticamente DKIM para sus dominios "onmicrosoft.com" iniciales.</span><span class="sxs-lookup"><span data-stu-id="2df0f-113">Office 365 automatically sets up DKIM for initial domains.</span></span> <span data-ttu-id="2df0f-114">Eso significa que no es necesario hacer nada para configurar DKIM para ningún nombre de dominio inicial. (ex.</span><span class="sxs-lookup"><span data-stu-id="2df0f-114">That means you don't need to do anything to set up DKIM for any initial domain names (ex.</span></span> <span data-ttu-id="2df0f-115">litware.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="2df0f-115">litware.onmicrosoft.com).</span></span> <span data-ttu-id="2df0f-116">Para más información sobre los dominios, vea [Preguntas más frecuentes de dominios](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span><span class="sxs-lookup"><span data-stu-id="2df0f-116">For more information about domains, see [Domains FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span></span>

<span data-ttu-id="2df0f-117">También puede elegir no hacer nada acerca de DKIM para su dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="2df0f-117">You can choose to do nothing about DKIM for your custom domain too.</span></span> <span data-ttu-id="2df0f-118">Si usted no configura DKIM para su dominio personalizado, Office 365 crea un par de claves privadas y públicas, que permiten que DKIM firme y configure la directiva predeterminada de Office 365 para su dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="2df0f-118">If you do not set up DKIM for your custom domain, Office 365 creates a private and public key pair, enables DKIM signing, and then configures the Office 365 default policy for your custom domain.</span></span> <span data-ttu-id="2df0f-119">Aunque esto suponga una cobertura suficiente para la mayoría de los clientes de Office 365, debería configurar manualmente DKIM para su dominio personalizado en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="2df0f-119">While this is sufficient coverage for most Office 365 customers, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>
  
- <span data-ttu-id="2df0f-120">Tiene más de un dominio personalizado en Office 365</span><span class="sxs-lookup"><span data-stu-id="2df0f-120">You have more than one custom domain in Office 365</span></span>

- <span data-ttu-id="2df0f-121">También va a configurar DMARC (recomendado)</span><span class="sxs-lookup"><span data-stu-id="2df0f-121">You're going to set up DMARC too (recommended)</span></span>

- <span data-ttu-id="2df0f-122">Quiere tener el control sobre la clave privada</span><span class="sxs-lookup"><span data-stu-id="2df0f-122">You want control over your private key</span></span>

- <span data-ttu-id="2df0f-123">Quiere personalizar los registros CNAME</span><span class="sxs-lookup"><span data-stu-id="2df0f-123">You want to customize your CNAME records</span></span>

- <span data-ttu-id="2df0f-124">Quiere configurar claves de DKIM para los correos electrónicos que se originen en un dominio de terceros, por ejemplo, si usa un troyano de envío masivo de correo electrónico de terceros.</span><span class="sxs-lookup"><span data-stu-id="2df0f-124">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>

<span data-ttu-id="2df0f-125">En este artículo:</span><span class="sxs-lookup"><span data-stu-id="2df0f-125">In this article:</span></span>
  
- [<span data-ttu-id="2df0f-126">Cómo DKIM funciona mejor que SPF solo para evitar la suplantación de identidad malintencionada en Office 365</span><span class="sxs-lookup"><span data-stu-id="2df0f-126">How DKIM works better than SPF alone to prevent malicious spoofing in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [<span data-ttu-id="2df0f-127">Actualizar manualmente las claves de 1024 bits a claves de cifrado DKIM de 2048 bits</span><span class="sxs-lookup"><span data-stu-id="2df0f-127">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [<span data-ttu-id="2df0f-128">Pasos que necesita seguir para configurar manualmente DKIM en Office 365</span><span class="sxs-lookup"><span data-stu-id="2df0f-128">What you need to do to manually set up DKIM in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [<span data-ttu-id="2df0f-129">Configurar DKIM para más de un dominio personalizado en Office 365</span><span class="sxs-lookup"><span data-stu-id="2df0f-129">To configure DKIM for more than one custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [<span data-ttu-id="2df0f-130">Deshabilitar la directiva de firmas DKIM para un dominio personalizado en Office 365</span><span class="sxs-lookup"><span data-stu-id="2df0f-130">Disabling the DKIM signing policy for a custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [<span data-ttu-id="2df0f-131">Comportamiento predeterminado para DKIM y Office 365</span><span class="sxs-lookup"><span data-stu-id="2df0f-131">Default behavior for DKIM and Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [<span data-ttu-id="2df0f-132">Configurar DKIM para que un servicio de terceros pueda enviar, o suplantar, correo electrónico en nombre de su dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="2df0f-132">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [<span data-ttu-id="2df0f-133">Pasos siguientes: Después de configurar DKIM para Office 365</span><span class="sxs-lookup"><span data-stu-id="2df0f-133">Next steps: After you set up DKIM for Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

> [!NOTE]
> <span data-ttu-id="2df0f-134">Microsoft 365 es compatible con el usuario de 1024 bits ó DKIM de 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="2df0f-134">Microsoft 365 supports the user of either 1024- or 2048-bit DKIM.</span></span> <span data-ttu-id="2df0f-135">Si utiliza 1024 y quiere configurar DKIM de 2048 bits, no se pierda los pasos para rotar la configuración de firma DKIM en este artículo.</span><span class="sxs-lookup"><span data-stu-id="2df0f-135">If you're using 1024- and want to configure 2048-bit DKIM stay tuned for steps to rotate your DKIM signing configuration in this article.</span></span> <span data-ttu-id="2df0f-136">A finales de 2019, Microsoft será compatible con claves de 2048 bits de forma predeterminada para todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="2df0f-136">By the end of 2019, Microsoft will support 2048-bit keys by default, for all customers.</span></span> 

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing-in-office-365"></a><span data-ttu-id="2df0f-137">Cómo DKIM funciona mejor que solo SPF para evitar la suplantación de identidad malintencionada en Office 365</span><span class="sxs-lookup"><span data-stu-id="2df0f-137">How DKIM works better than SPF alone to prevent malicious spoofing in Office 365</span></span>
<span data-ttu-id="2df0f-138"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="2df0f-138"></span></span>

<span data-ttu-id="2df0f-p106">SPF agrega información a un sobre del mensaje pero DKIM cifra realmente una firma dentro del encabezado del mensaje. Cuando reenvía un mensaje, el servidor de reenvío puede quitar partes de ese sobre del mensaje. Como la firma digital permanece en el mensaje de correo electrónico porque forma parte del encabezado del correo, DKIM funciona incluso cuando un mensaje se ha reenviado como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2df0f-p106">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header. When you forward a message, portions of that message's envelope can be stripped away by the forwarding server. Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>
  
![Diagrama que muestra un mensaje reenviado que pasa por la autenticación DKIM, donde se produce un error en la comprobación de SPF.](../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)
  
<span data-ttu-id="2df0f-p107">En este ejemplo, si solo había publicado un registro TXT de SPF en su dominio, el servidor de correo del destinatario podría haber marcado el correo electrónico como correo no deseado y generar un resultado de falso positivo. La adición de DKIM en este escenario reduce los informes de correo no deseado de falso positivo. Debido a que DKIM se basa en la criptografía de clave pública para autenticar y no solo en las direcciones IP, DKIM se considera una forma mucho más segura de autenticación que SPF. Se recomienda usar SPF y DKIM, así como DMARC, en la implementación.</span><span class="sxs-lookup"><span data-stu-id="2df0f-p107">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result. The addition of DKIM in this scenario reduces false positive spam reporting. Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF. We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>
  
<span data-ttu-id="2df0f-p108">Información esencial: DKIM usa una clave privada para insertar una firma cifrada en los encabezados del mensaje. El dominio de firma, o el dominio saliente, se inserta como el valor del campo **d=** en el encabezado. El dominio de comprobación, o dominio del destinatario, usa entonces el campo **=d** para buscar la clave pública desde DNS y autenticar el mensaje. Si el mensaje se comprueba, supera la comprobación DKIM.</span><span class="sxs-lookup"><span data-stu-id="2df0f-p108">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers. The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header. The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message. If the message is verified, the DKIM check passes.</span></span> 

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a><span data-ttu-id="2df0f-151">Actualizar manualmente las claves de 1024 bits a claves de cifrado DKIM de 2048 bits</span><span class="sxs-lookup"><span data-stu-id="2df0f-151">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>
<span data-ttu-id="2df0f-152"><a name="1024to2048DKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="2df0f-152"></span></span>

<span data-ttu-id="2df0f-153">Ya que ambos valores de bits, 1024 y 2048, son compatibles con las claves DKIM, estas instrucciones le indicarán cómo actualizar la clave de 1024 bits a 2048.</span><span class="sxs-lookup"><span data-stu-id="2df0f-153">Since both 1024 and 2048 bitness are supported for DKIM keys, these directions will tell you how to upgrade your 1024-bit key to 2048.</span></span> <span data-ttu-id="2df0f-154">Los pasos que se muestran a continuación son dos casos de uso distintos, elija el que mejor se ajuste a su configuración.</span><span class="sxs-lookup"><span data-stu-id="2df0f-154">The steps below are for two use-cases, please choose the one that best fits your configuration.</span></span>

1. <span data-ttu-id="2df0f-155">Cuando **ya tiene configuradas las DKIM**, cambie el valor de los bits de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="2df0f-155">When you **already have DKIM configured**, you rotate bitness as follows:</span></span>
    1. <span data-ttu-id="2df0f-156">[Conéctese con las cargas de trabajo de Office 365 a través de PowerShell](https://docs.microsoft.com/es-ES/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="2df0f-156">[Connect to Office 365 PowerShell](https://docs.microsoft.com/es-ES/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)</span></span> <span data-ttu-id="2df0f-157">(El cmdlet viene de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="2df0f-157">(The cmdlet comes from Exchange Online.)</span></span>
    1. <span data-ttu-id="2df0f-158">Y luego ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2df0f-158">And then execute the following cmdlet:</span></span>

<span data-ttu-id="2df0f-159">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}`</span><span class="sxs-lookup"><span data-stu-id="2df0f-159"></span></span>

1. <span data-ttu-id="2df0f-160">O para una **nueva implementación de DKIM**:</span><span class="sxs-lookup"><span data-stu-id="2df0f-160">Or for a **new implementation of DKIM**:</span></span>
    1. <span data-ttu-id="2df0f-161">[Conéctese con las cargas de trabajo de Office 365 a través de PowerShell](https://docs.microsoft.com/es-ES/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="2df0f-161">[Connect to Office 365 PowerShell](https://docs.microsoft.com/es-ES/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)</span></span> <span data-ttu-id="2df0f-162">(Este es un cmdlet de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="2df0f-162">(This is an Exchange Online cmdlet.)</span></span>
    1. <span data-ttu-id="2df0f-163">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2df0f-163">Run the following cmdlet:</span></span>

<span data-ttu-id="2df0f-164">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True`</span><span class="sxs-lookup"><span data-stu-id="2df0f-164"></span></span>

<span data-ttu-id="2df0f-165">Manténgase conectado a Office 365 para *verificar* la configuración.</span><span class="sxs-lookup"><span data-stu-id="2df0f-165">Stay connected to Office 365 to *verify* the configuration.</span></span>

2. <span data-ttu-id="2df0f-166">Ejecute el cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2df0f-166">Execute the cmdlet:</span></span>

<span data-ttu-id="2df0f-167">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `Get-DkimSigningConfig | fl`</span><span class="sxs-lookup"><span data-stu-id="2df0f-167"></span></span>

> [!TIP]
><span data-ttu-id="2df0f-168">Esta nueva clave de 2048 bits tendrá efecto en el RotateOnDate y mientras tanto enviará los mensajes de correo electrónico con la clave de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="2df0f-168">This new 2048-bit key takes effect on the RotateOnDate, and will send emails with the 1024-bit key in the interim.</span></span> <span data-ttu-id="2df0f-169">Después de cuatro días, puede volver a probar con la clave de 2048 bits (es decir, cuando la rotación surta efecto al segundo selector).</span><span class="sxs-lookup"><span data-stu-id="2df0f-169">After four days, you can test again with the 2048-bit key (that is, once the rotation takes effect to the second selector).</span></span> 

<span data-ttu-id="2df0f-170">Si desea rotar hasta el segundo selector, las opciones son: a) dejar que el servicio de Office 365 rote el selector y actualice al valor de 2048 bits en los próximos 6 meses, o b) después de cuatro días y de confirmar que se está utilizando el valor de 2048 bits, rote manualmente la clave del segundo selector por usando el cmdlet apropiado de los que se enumeran arriba.</span><span class="sxs-lookup"><span data-stu-id="2df0f-170">If you want to rotate to the second selector, your options are a) let the Office 365 service rotate the selector and upgrade to 2048-bitness within the next 6 months, or b) after 4 days and confirming that 2048-bitness is in use, manually rotate the second selector key by using the appropriate cmdlet listed above.</span></span>

## <a name="steps-you-need-to-do-to-manually-set-up-dkim-in-office-365"></a><span data-ttu-id="2df0f-171">Pasos que necesita seguir para configurar manualmente DKIM en Office 365</span><span class="sxs-lookup"><span data-stu-id="2df0f-171">What you need to do to manually set up DKIM in Office 365</span></span>
<span data-ttu-id="2df0f-172"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="2df0f-172"></span></span>

<span data-ttu-id="2df0f-173">Para configurar DKIM, deberá completar estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2df0f-173">To configure DKIM, you will complete these steps:</span></span>
  
- [<span data-ttu-id="2df0f-174">Publicar dos registros CNAME para su dominio personalizado en DNS</span><span class="sxs-lookup"><span data-stu-id="2df0f-174">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [<span data-ttu-id="2df0f-175">Habilitar la firma DKIM para su dominio personalizado en Office 365</span><span class="sxs-lookup"><span data-stu-id="2df0f-175">Enable DKIM signing for your custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="2df0f-176">Publicar dos registros CNAME para su dominio personalizado en DNS</span><span class="sxs-lookup"><span data-stu-id="2df0f-176">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="2df0f-177"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="2df0f-177"></span></span>

<span data-ttu-id="2df0f-178">Para cada dominio para el que quiera agregar una firma DKIM en DNS, necesita publicar dos registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="2df0f-178">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span> 

<span data-ttu-id="2df0f-179">Ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2df0f-179">Run the following commands:</span></span>

```powershell
    New-DkimSigningConfig -DomainName <domain> -Enabled $false   
    Get-DkimSigningConfig -Identity <domain> | fl Selector1CNAME, Selector2CNAME
```

<span data-ttu-id="2df0f-180">Cree registros CNAME a los que se hace referencia en los resultados de Get-DkimSigningConfig</span><span class="sxs-lookup"><span data-stu-id="2df0f-180">Create CNAMEs referenced in Get-DkimSigningConfig output</span></span>

```powershell
    Set-DkimSigningConfig -Identity <domain> -Enabled $true
```
<span data-ttu-id="2df0f-181">Los registros CNAME que aparecen en el DNS señalarán a registros A ya creados que existan en los servidores DNS de Microsoft para Office 365.</span><span class="sxs-lookup"><span data-stu-id="2df0f-181">The CNAME records in your DNS will point to already created A records that exist in DNS on the Microsoft DNS servers for Office 365.</span></span>
  
<span data-ttu-id="2df0f-p113">Office 365 realiza la rotación de claves automática mediante los dos registros que establezca. Si ha aprovisionado dominios personalizados adicionales además del dominio inicial de Office 365, debe publicar dos registros CNAME para cada dominio adicional. Por lo tanto, si tiene dos dominios, debe publicar dos registros CNAME adicionales, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="2df0f-p113">Office 365 performs automatic key rotation using the two records that you establish. If you have provisioned custom domains in addition to the initial domain in Office 365, you must publish two CNAME records for each additional domain. So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>
  
<span data-ttu-id="2df0f-185">Use el formato siguiente para los registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="2df0f-185">Use the following format for the CNAME records:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2df0f-186">Si es uno de nuestros clientes de GCC High, calcularemos _domainGuid_ de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="2df0f-186">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="2df0f-187">En lugar de buscar el registro MX para su _initialDomain_ para calcular _domainGuid_, lo calculamos directamente desde el dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="2df0f-187">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="2df0f-188">Por ejemplo, si su dominio personalizado es "contoso.com", su domainGuid se convierte en "contoso-com", los puntos se reemplazan por un guión.</span><span class="sxs-lookup"><span data-stu-id="2df0f-188">For example, if your customized domain is "contoso.com" your domainGuid becomes "contoso-com", any periods are replaced with a dash.</span></span> <span data-ttu-id="2df0f-189">Por lo tanto, independientemente del registro MX al que señala su initialDomain, siempre se usará el método anterior para calcular el domainGuid que se usará en sus registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="2df0f-189">So, regardless of what MX record your initialDomain points to, you’ll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

```text
Host name:          selector1._domainkey
Points to address or value: selector1-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600
```

<span data-ttu-id="2df0f-190">Donde:</span><span class="sxs-lookup"><span data-stu-id="2df0f-190">Where:</span></span>
  
- <span data-ttu-id="2df0f-191">Para Office 365, los selectores siempre serán "selector1" o "selector2".</span><span class="sxs-lookup"><span data-stu-id="2df0f-191">For Office 365, the selectors will always be "selector1" or "selector2".</span></span>

- <span data-ttu-id="2df0f-192">El _domainGUID_ es el mismo que el _domainGUID_ del registro MX personalizado para su dominio personalizado que aparece antes de mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="2df0f-192">_domainGUID_ is the same as the  _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com.</span></span> <span data-ttu-id="2df0f-193">Por ejemplo, en el siguiente registro MX del dominio contoso.com, el _domainGUID_ es contoso-com:</span><span class="sxs-lookup"><span data-stu-id="2df0f-193">For example, in the following MX record for the domain contoso.com, the  _domainGUID_ is contoso-com:</span></span> 
    
    ```text
    contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com
    ```

- <span data-ttu-id="2df0f-194">_initialDomain_ es el dominio que usó al registrarse en Office 365.</span><span class="sxs-lookup"><span data-stu-id="2df0f-194">_initialDomain_ is the domain that you used when you signed up for Office 365.</span></span> <span data-ttu-id="2df0f-195">Los dominios iniciales siempre terminan en onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2df0f-195">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="2df0f-196">Para obtener información sobre cómo determinar el dominio inicial, vea [Preguntas más frecuentes de dominios](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span><span class="sxs-lookup"><span data-stu-id="2df0f-196">For information about determining your initial domain, see [Domains FAQ](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span></span>

<span data-ttu-id="2df0f-197">Por ejemplo, si tiene un dominio inicial de cohovineyardandwinery.onmicrosoft.com y dos dominios personalizados cohovineyard.com y cohowinery.com, necesitará configurar dos registros CNAME para cada dominio adicional, un total de cuatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="2df0f-197">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>
  
```text
Host name:          selector1._domainkey
Points to address or value: selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector1._domainkey
Points to address or value: selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600
```

### <a name="enable-dkim-signing-for-your-custom-domain-in-office-365"></a><span data-ttu-id="2df0f-198">Habilitar la firma DKIM para su dominio personalizado en Office 365</span><span class="sxs-lookup"><span data-stu-id="2df0f-198">Enable DKIM signing for your custom domain in Office 365</span></span>
<span data-ttu-id="2df0f-199"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="2df0f-199"></span></span>

<span data-ttu-id="2df0f-200">Una vez que haya publicado los registros CNAME en DNS, está preparado para habilitar la firma DKIM mediante Office 365.</span><span class="sxs-lookup"><span data-stu-id="2df0f-200">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Office 365.</span></span> <span data-ttu-id="2df0f-201">Puede hacerlo a través del Centro de administración de Microsoft 365 o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2df0f-201">You can do this either through the Office 365 admin center or by using PowerShell.</span></span>
  
#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a><span data-ttu-id="2df0f-202">Para habilitar la firma DKIM para su dominio personalizado a través del Centro de administración</span><span class="sxs-lookup"><span data-stu-id="2df0f-202">To enable DKIM signing for your custom domain through the Office 365 admin center</span></span>

1. <span data-ttu-id="2df0f-203">[Inicie sesión en Office 365](https://support.office.microsoft.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="2df0f-203">[Sign in to Office 365](https://support.office.microsoft.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span> 

2. <span data-ttu-id="2df0f-204">Seleccione el icono del iniciador de aplicaciones en la esquina superior izquierda y elija **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="2df0f-204">Select the app launcher icon in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="2df0f-205">En el panel de navegación inferior izquierdo, expanda **Administración** y elija **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="2df0f-205">In the lower-left navigation, expand **Admin** and choose **Exchange**.</span></span>

4. <span data-ttu-id="2df0f-206">Vaya a **Protección** \> **dkim**.</span><span class="sxs-lookup"><span data-stu-id="2df0f-206">Go to **Protection** \> **dkim**.</span></span>

5. <span data-ttu-id="2df0f-p118">Seleccione el dominio para el que quiere habilitar DKIM y, después, en **Firmar los mensajes de este dominio con firmas DKIM**, elija **Habilitar**. Repita este paso para cada dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="2df0f-p118">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**. Repeat this step for each custom domain.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="2df0f-209">Para habilitar la firma DKIM para su dominio personalizado mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="2df0f-209">To enable DKIM signing for your custom domain by using PowerShell</span></span>

1. <span data-ttu-id="2df0f-210">[Conéctese al PowerShell de Exchange Online](https://technet.microsoft.com/library/jj984289.aspx).</span><span class="sxs-lookup"><span data-stu-id="2df0f-210">[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx).</span></span>

2. <span data-ttu-id="2df0f-211">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2df0f-211">Run the following command:</span></span>

    ```powershell
    Set-DkimSigningConfig -Identity <domain> -Enabled $true
    ```

   <span data-ttu-id="2df0f-212">Donde _domain_ es el nombre del dominio personalizado para el que quiere habilitar la firma DKIM.</span><span class="sxs-lookup"><span data-stu-id="2df0f-212">Where  _domain_ is the name of the custom domain for which you want to enable DKIM signing.</span></span> 

   <span data-ttu-id="2df0f-213">Por ejemplo, para el dominio contoso.com:</span><span class="sxs-lookup"><span data-stu-id="2df0f-213">For example, for the domain contoso.com:</span></span>
   
   ```powershell
    Set-DkimSigningConfig -Identity contoso.com -Enabled $true
    ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-office-365"></a><span data-ttu-id="2df0f-214">Para confirmar que la firma DKIM está configurada correctamente en Office 365</span><span class="sxs-lookup"><span data-stu-id="2df0f-214">To Confirm DKIM signing is configured properly for Office 365</span></span>

<span data-ttu-id="2df0f-p119">Espere unos minutos antes de seguir estos pasos para confirmar que ha configurado correctamente DKIM. Esto proporciona tiempo para que la información DKIM acerca del dominio se reparta por toda la red.</span><span class="sxs-lookup"><span data-stu-id="2df0f-p119">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM. This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>
  
- <span data-ttu-id="2df0f-217">Envíe un mensaje desde una cuenta dentro de su dominio habilitado para DKIM en Office 365 a otra cuenta de correo electrónico como outlook.com o Hotmail.com.</span><span class="sxs-lookup"><span data-stu-id="2df0f-217">Send a message from an account within your Office 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>

- <span data-ttu-id="2df0f-p120">No use una cuenta de aol.com con fines de prueba. AOL puede omitir la comprobación DKIM si se supera la comprobación SPF. Esto anulará la prueba.</span><span class="sxs-lookup"><span data-stu-id="2df0f-p120">Do not use an aol.com account for testing purposes. AOL may skip the DKIM check if the SPF check passes. This will nullify your test.</span></span>

- <span data-ttu-id="2df0f-p121">Abra el mensaje y observe el encabezado. Las instrucciones para ver el encabezado del mensaje variarán según el cliente de mensajería. Para obtener instrucciones acerca de cómo ver los encabezados de los mensajes en Outlook, consulte [Ver encabezados de mensajes de correo electrónico](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).</span><span class="sxs-lookup"><span data-stu-id="2df0f-p121">Open the message and look at the header. Instructions for viewing the header for the message will vary depending on your messaging client. For instructions on viewing message headers in Outlook, see [View e-mail message headers](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).</span></span>

  <span data-ttu-id="2df0f-p122">El mensaje con firma DKIM contendrá el nombre de host y el dominio que definió cuando publicó las entradas CNAME. El mensaje tendrá un aspecto similar al de este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2df0f-p122">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries. The message will look something like this example:</span></span>
    
    ```text
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
    ```

- <span data-ttu-id="2df0f-p123">Busque el encabezado Authentication-Results. Aunque cada servicio de recepción usa un formato ligeramente diferente para estampar el correo entrante, el resultado debe incluir algo como **DKIM=pass** o **DKIM=OK**.</span><span class="sxs-lookup"><span data-stu-id="2df0f-p123">Look for the Authentication-Results header. While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span>

## <a name="to-configure-dkim-for-more-than-one-custom-domain-in-office-365"></a><span data-ttu-id="2df0f-228">Configurar DKIM para más de un dominio personalizado en Office 365</span><span class="sxs-lookup"><span data-stu-id="2df0f-228">To configure DKIM for more than one custom domain in Office 365</span></span>
<span data-ttu-id="2df0f-229"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="2df0f-229"></span></span>

<span data-ttu-id="2df0f-p124">Si en algún momento en el futuro decide agregar otro dominio personalizado y quiere habilitar DKIM para el dominio nuevo, debe completar los pasos de este artículo para cada dominio. En concreto, complete todos los pasos de [Lo que necesita hacer para configurar manualmente DKIM en Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span><span class="sxs-lookup"><span data-stu-id="2df0f-p124">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain. Specifically, complete all steps in [What you need to do to manually set up DKIM in Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>
  
## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain-in-office-365"></a><span data-ttu-id="2df0f-232">Deshabilitar la directiva de firmas DKIM para un dominio personalizado en Office 365</span><span class="sxs-lookup"><span data-stu-id="2df0f-232">Disabling the DKIM signing policy for a custom domain in Office 365</span></span>
<span data-ttu-id="2df0f-233"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="2df0f-233"></span></span>

<span data-ttu-id="2df0f-p125">Deshabilitar la directiva de firmas no deshabilita DKIM completamente. Después de un período de tiempo, Office 365 aplicará automáticamente la directiva de Office 365 predeterminada para el dominio. Para obtener más información, consulte [Comportamiento predeterminado para DKIM y Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span><span class="sxs-lookup"><span data-stu-id="2df0f-p125">Disabling the signing policy does not completely disable DKIM. After a period of time, Office 365 will automatically apply the default Office 365 policy for your domain. For more information, see [Default behavior for DKIM and Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>
  
### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="2df0f-237">Para deshabilitar la directiva de firmas DKIM mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2df0f-237">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="2df0f-238">[Conéctese al PowerShell de Exchange Online](https://technet.microsoft.com/library/jj984289.aspx).</span><span class="sxs-lookup"><span data-stu-id="2df0f-238">[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx).</span></span>

2. <span data-ttu-id="2df0f-239">Ejecute uno de los siguientes comandos para cada dominio para el que quiera deshabilitar la firma DKIM.</span><span class="sxs-lookup"><span data-stu-id="2df0f-239">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>
    
    ```powershell
    $p = Get-DkimSigningConfig -Identity <domain>
    $p[0] | Set-DkimSigningConfig -Enabled $false
    ```
   
   <span data-ttu-id="2df0f-240">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2df0f-240">For example:</span></span>
    
    ```powershell
    $p = Get-DkimSigningConfig -Identity contoso.com
    $p[0] | Set-DkimSigningConfig -Enabled $false
    ```

   <span data-ttu-id="2df0f-241">O bien</span><span class="sxs-lookup"><span data-stu-id="2df0f-241">Or</span></span>
    
    ```powershell
    Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
    ```

    <span data-ttu-id="2df0f-242">Donde _number_ es el índice de la directiva.</span><span class="sxs-lookup"><span data-stu-id="2df0f-242">Where  _number_ is the index of the policy.</span></span> <span data-ttu-id="2df0f-243">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2df0f-243">For example:</span></span>
    
    ```powershell
    Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
    ```

## <a name="default-behavior-for-dkim-and-office-365"></a><span data-ttu-id="2df0f-244">Comportamiento predeterminado para DKIM y Office 365</span><span class="sxs-lookup"><span data-stu-id="2df0f-244">Default behavior for DKIM and Office 365</span></span>
<span data-ttu-id="2df0f-245"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="2df0f-245"></span></span>

<span data-ttu-id="2df0f-246">Si no habilita DKIM, Office 365 crea automáticamente una clave pública DKIM de 1024 bits para el dominio predeterminado y la clave privada asociada que se almacena internamente en nuestro centro de datos.</span><span class="sxs-lookup"><span data-stu-id="2df0f-246">If you do not enable DKIM, Office 365 automatically creates a 1024-bit DKIM public key for your custom domain and the associated private key which we store internally in our datacenter.</span></span> <span data-ttu-id="2df0f-247">De forma predeterminada, Office 365 usa una configuración de firmas predeterminada para los dominios que no tienen una directiva local.</span><span class="sxs-lookup"><span data-stu-id="2df0f-247">By default, Office 365 uses a default signing configuration for domains that do not have a policy in place.</span></span> <span data-ttu-id="2df0f-248">Esto significa que si no configura DKIM, Office 365 usará su política predeterminada y se creará la clave para habilitar DKIM para el dominio.</span><span class="sxs-lookup"><span data-stu-id="2df0f-248">This means that if you do not set up DKIM yourself, Office 365 will use its default policy and keys it creates in order to enable DKIM for your domain.</span></span>
  
<span data-ttu-id="2df0f-249">Además, si deshabilita la firma DKIM después de habilitarla, después de un período de tiempo, Office 365 aplicará automáticamente la directiva predeterminada de Office 365 para el dominio.</span><span class="sxs-lookup"><span data-stu-id="2df0f-249">Also, if you disable DKIM signing after enabling it, after a period of time, Office 365 will automatically apply the Office 365 default policy for your domain.</span></span>
  
<span data-ttu-id="2df0f-p128">En el ejemplo siguiente, suponga que Office 365 ha habilitado DKIM para fabrikam.com, no el administrador del dominio. Esto significa que los CNAME necesarios no existen en DNS. Las firmas DKIM para el correo electrónico de este dominio tendrán un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="2df0f-p128">In the following example, suppose that DKIM for fabrikam.com was enabled by Office 365, not by the administrator of the domain. This means that the required CNAMEs do not exist in DNS. DKIM signatures for email from this domain will look something like this:</span></span>
  
```text
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

<span data-ttu-id="2df0f-p129">En este ejemplo, el nombre de host y el dominio contienen los valores a los que señalaría el registro CNAME si el administrador del dominio hubiera habilitado la firma DKIM para fabrikam.com. Finalmente, todos los mensajes enviados desde Office 365 contendrán una firma DKIM. Si habilita DKIM, el dominio será el mismo que el dominio que figura en la dirección del campo De:, en este caso, fabrikam.com. Si no lo hace, el dominio no se alineará y en su lugar se usará el dominio inicial de la organización. Para obtener información sobre cómo determinar el dominio inicial, vea [Preguntas más frecuentes de dominios](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span><span class="sxs-lookup"><span data-stu-id="2df0f-p129">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator. Eventually, every single message sent from Office 365 will be DKIM-signed. If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com. If you don't, it will not align and instead will use your organization's initial domain. For information about determining your initial domain, see [Domains FAQ](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span></span>
  
## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="2df0f-258">Configurar DKIM para que un servicio de terceros pueda enviar, o suplantar, correo electrónico en nombre de su dominio personalizado</span><span class="sxs-lookup"><span data-stu-id="2df0f-258">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="2df0f-259"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="2df0f-259"></span></span>

<span data-ttu-id="2df0f-p130">Algunos proveedores de servicio de correo electrónico masivo o proveedores de software como servicio, le permiten configurar claves DKIM para el correo electrónico que se origina de su servicio. Esto requiere la coordinación entre el usuario y el servicio de terceros para configurar los registros DNS necesarios. No existen dos organizaciones que lo hagan exactamente de la misma manera. En su lugar, el proceso depende completamente de la organización.</span><span class="sxs-lookup"><span data-stu-id="2df0f-p130">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service. This requires coordination between yourself and the third-party in order to set up the necessary DNS records. No two organizations do it exactly the same way. Instead, the process depends entirely on the organization.</span></span>
  
<span data-ttu-id="2df0f-264">Un mensaje de ejemplo que muestra un DKIM configurado correctamente para contoso.com y bulkemailprovider.com puede tener el aspecto siguiente:</span><span class="sxs-lookup"><span data-stu-id="2df0f-264">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>
  
```text
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="2df0f-265">En este ejemplo, para conseguir este resultado:</span><span class="sxs-lookup"><span data-stu-id="2df0f-265">In this example, in order to achieve this result:</span></span>
  
1. <span data-ttu-id="2df0f-266">El proveedor de correo electrónico masivo le ha proporcionado una clave DKIM pública a Contoso.</span><span class="sxs-lookup"><span data-stu-id="2df0f-266">Bulk Email Provider gave Contoso a public DKIM key.</span></span>

2. <span data-ttu-id="2df0f-267">Contoso ha publicado la clave DKIM en su registro DNS.</span><span class="sxs-lookup"><span data-stu-id="2df0f-267">Contoso published the DKIM key to its DNS record.</span></span>

3. <span data-ttu-id="2df0f-p131">Al enviar el correo electrónico, el proveedor de correo electrónico masivo ha firmado la clave con la clave privada correspondiente. Al hacer esto, el proveedor de correo electrónico masivo ha adjuntado la firma DKIM al encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2df0f-p131">When sending email, Bulk Email Provider signs the key with the corresponding private key. By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>

4. <span data-ttu-id="2df0f-p132">Los sistemas de correo electrónico de recepción realizan una comprobación DKIM mediante la autenticación del valor d=\<dominio\> de la firma DKIM contra el dominio del campo De: (5322.From) dirección del mensaje. En este ejemplo, los valores coinciden:</span><span class="sxs-lookup"><span data-stu-id="2df0f-p132">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message. In this example, the values match:</span></span>

    <span data-ttu-id="2df0f-272">sender@**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="2df0f-272">sender@**contoso.com**</span></span>

    <span data-ttu-id="2df0f-273">d=**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="2df0f-273">d=**contoso.com**</span></span>

## <a name="next-steps-after-you-set-up-dkim-for-office-365"></a><span data-ttu-id="2df0f-274">Pasos siguientes: una vez configurado DKIM para Office 365</span><span class="sxs-lookup"><span data-stu-id="2df0f-274">Next steps: After you set up DKIM for Office 365</span></span>
<span data-ttu-id="2df0f-275"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="2df0f-275"></span></span>

<span data-ttu-id="2df0f-276">Aunque DKIM está diseñado para ayudar a evitar la suplantación de identidad, DKIM funciona mejor con SPF y DMARC.</span><span class="sxs-lookup"><span data-stu-id="2df0f-276">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="2df0f-277">Cuando haya configurado DKIM, si todavía no ha configurado SPF, debería hacerlo.</span><span class="sxs-lookup"><span data-stu-id="2df0f-277">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="2df0f-278">Para obtener una introducción rápida a SPF y configurarlo rápidamente, vea [Configurar SPF en Office 365 para evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="2df0f-278">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="2df0f-279">Para comprender en detalle cómo Office 365 usa SPF, o para la solución de problemas o las implementaciones no estándar (por ejemplo, implementaciones híbridas), comience con [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="2df0f-279">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="2df0f-280">A continuación, consulte [Usar DMARC para validar el correo electrónico en Office 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="2df0f-280">Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="2df0f-281">Los [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md) incluyen la sintaxis y los campos de encabezado que usa Office 365 para efectuar las comprobaciones de DKIM.</span><span class="sxs-lookup"><span data-stu-id="2df0f-281">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for DKIM checks.</span></span>
