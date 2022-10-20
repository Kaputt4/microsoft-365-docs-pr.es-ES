---
title: Cómo usar DKIM para el correo electrónico en su dominio personalizado
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: high
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- m365-security
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Más información sobre cómo usar DomainKeys Identified Mail (DKIM) con Microsoft 365 para asegurarse de que los mensajes que se envían desde su dominio personalizado sean de confianza para los sistemas de correo electrónico de destino.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 31eca37a3fa2b8fd47ad2628f940b4938c34c509
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68640024"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a>Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

 Este artículo muestra los pasos para usar DomainKeys Identified Mail (DKIM) con Microsoft 365 para asegurarse de que los sistemas de correo electrónico de destino confían en los mensajes enviados desde su dominio personalizado.

En este artículo:

- [Cómo DKIM funciona mejor que SPF solo para evitar la suplantación de identidad malintencionada](#how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing)
- [Pasos para crear, habilitar y deshabilitar DKIM desde el portal de Microsoft 365 Defender](#steps-to-create-enable-and-disable-dkim-from-microsoft-365-defender-portal)
- [Pasos para actualizar manualmente las claves de 1024 bits a claves de cifrado DKIM de 2048 bits](#steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys)
- [Pasos para configurar manualmente DKIM](#steps-to-manually-set-up-dkim)
- [Pasos para configurar DKIM para más de un dominio personalizado](#to-configure-dkim-for-more-than-one-custom-domain)
- [Deshabilitar la directiva de firmas DKIM para un dominio personalizado](#disabling-the-dkim-signing-policy-for-a-custom-domain)
- [Comportamiento predeterminado para DKIM y Microsoft 365](#default-behavior-for-dkim-and-microsoft-365)
- [Configurar DKIM para que un servicio de terceros pueda enviar, o suplantar, correo electrónico en nombre de su dominio personalizado](#set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain)
- [Pasos siguientes: una vez configurado DKIM para Microsoft 365](#next-steps-after-you-set-up-dkim-for-microsoft-365)

> [!NOTE]
> Microsoft 365 configura automáticamente DKIM para sus dominios "onmicrosoft.com" iniciales. Lo que significa que no es necesario realizar ninguna acción para configurar DKIM para un nombre de dominio inicial (por ejemplo, litware.onmicrosoft.com). Para más información sobre los dominios, vea [Preguntas más frecuentes de dominios](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

DKIM es uno de los tres métodos de autenticación (SPF, KIM y DMARC) que ayudan a evitar que los atacantes envíen mensajes que parecen procedentes de su dominio.

DKIM lets you add a digital signature to outbound email messages in the message header. When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message using cryptographic authentication. Email systems that get email from your domain can use this digital signature to help verify whether incoming email is legitimate.

Básicamente, una clave privada cifra el encabezado en un correo electrónico saliente del dominio. La clave pública se publica en los registros DNS del dominio, y los servidores de recepción pueden usar esa clave para descodificar la firma. La verificación de DKIM ayuda a los servidores de recepción a confirmar que el correo realmente procede de su dominio y no se trata de alguien que está *suplantando* su dominio.

> [!TIP]
>You can choose to do nothing about DKIM for your custom domain too. If you don't set up DKIM for your custom domain, Microsoft 365 creates a private and public key pair, enables DKIM signing, and then configures the Microsoft 365 default policy for your custom domain.

 Microsoft-365's built-in DKIM configuration is sufficient coverage for most customers. However, you should manually configure DKIM for your custom domain in the following circumstances:

- Tiene más de un dominio personalizado en Microsoft 365
- También va a configurar DMARC (**recomendado**)
- Quiere tener el control sobre la clave privada
- Quiere personalizar los registros CNAME
- Quiere configurar claves de DKIM para los correos electrónicos que se originen en un dominio de terceros, por ejemplo, si usa un troyano de envío masivo de correo electrónico de terceros.

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a>Cómo DKIM funciona mejor que SPF solo para evitar la suplantación de identidad malintencionada
<a name="HowDKIMWorks"> </a>

SPF adds information to a message envelope but DKIM *encrypts* a signature within the message header. When you forward a message, portions of that message's envelope can be stripped away by the forwarding server. Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.

![Diagrama que muestra un mensaje reenviado que pasa por la autenticación DKIM, donde se produce un error en la comprobación de SPF.](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result. **The addition of DKIM in this scenario reduces *false positive* spam reporting.** Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF. We recommend using both SPF and DKIM, as well as DMARC in your deployment.

> [!TIP]
> DKIM uses a private key to insert an encrypted signature into the message headers. The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header. The verifying domain, or recipient's domain, then uses the **d=** field to look up the public key from DNS, and authenticate the message. If the message is verified, the DKIM check passes.

## <a name="steps-to-create-enable-and-disable-dkim-from-microsoft-365-defender-portal"></a>Pasos para crear, habilitar y deshabilitar DKIM desde el portal de Microsoft 365 Defender

Todos los dominios aceptados de su espacio empresarial se mostrarán en el portal Microsoft 365 Defender en la página DKIM. Si no lo ve, agregue el dominio aceptado desde la [página dominios](/microsoft-365/admin/setup/add-domain#add-a-domain).
Una vez agregado el dominio, siga los pasos que se muestran a continuación para configurar DKIM.

Paso 1: Haga clic en el dominio en el que quiere configurar DKIM en la página de DKIM (https://security.microsoft.com/dkimv2 o https://protection.office.com/dkimv2).

:::image type="content" source="../../media/126996261-2d331ec1-fc83-4a9d-a014-bd7e1854eb07.png" alt-text="Página DKIM en el portal de Microsoft 365 Defender con un dominio seleccionado" lightbox="../../media/126996261-2d331ec1-fc83-4a9d-a014-bd7e1854eb07.png":::

Paso 2: Deslice el botón de alternancia a **Habilitar**. Verá una ventana emergente que indica que necesita agregar registros CNAME.

:::image type="content" source="../../media/127001645-4ccf89e6-6310-4a91-85d6-aaedbfd501d3.png" alt-text="Control flotante de detalles del dominio con el botón Crear claves DKIM" lightbox="../../media/127001645-4ccf89e6-6310-4a91-85d6-aaedbfd501d3.png":::

Paso 3: Copiar los CNAMES que se muestran en la ventana emergente.

:::image type="content" source="../../media/127001787-3cce2c29-e0e4-4712-af53-c51dcba33c46.png" alt-text="Ventana emergente Publicar CNAME que contiene los dos registros CNAME que se van a copiar" lightbox="../../media/127001787-3cce2c29-e0e4-4712-af53-c51dcba33c46.png":::

Paso 4: Publicar los registros CNAME copiados en el proveedor de servicios DNS.

En el sitio web del proveedor de DNS, agregue registros CNAME para DKIM que quiera habilitar. Asegúrese de configurar los campos con los siguientes valores para cada uno:

```text
Record Type: CNAME (Alias)
> Host: Paste the values you copy from DKIM page.
Points to address: Copy the value from DKIM page.
TTL: 3600 (or your provider default)
```

Paso 5: volver a la página DKIM para habilitar DKIM

:::image type="content" source="../../media/126995186-9b3fdefa-a3a9-4f5a-9304-1099a2ce7cef.png" alt-text="Botón de alternancia para habilitar DKIM" lightbox="../../media/126995186-9b3fdefa-a3a9-4f5a-9304-1099a2ce7cef.png":::

Si ve el error El registro CNAME no existe, es posible que se deba a:

1. Sincronización con el servidor DNS, que puede tardar de unos segundos a horas, si el problema persiste, repita los pasos de nuevo.
2. Compruebe si hay errores de copiar y pegar, como espacio adicional o pestañas, etc.

Si desea deshabilitar DKIM, vuelva al modo de deshabilitación.

## <a name="steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a>Pasos para actualizar manualmente las claves de 1024 bits a claves de cifrado DKIM de 2048 bits
<a name="1024to2048DKIM"> </a>

> [!NOTE]
> Microsoft 365 configura automáticamente DKIM para los dominios *"onmicrosoft.com"*. No es necesario seguir ningún paso para usar DKIM para los nombres de dominio iniciales (como litware.*onmicrosoft.com*). Para más información sobre los dominios, vea [Preguntas más frecuentes de dominios](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

Ya que ambos valores de bits, 1024 y 2048, son compatibles con las claves DKIM, estas instrucciones le indicarán cómo actualizar la clave de 1024 bits a 2048 en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Los pasos que se muestran a continuación son dos casos de uso distintos, elija el que mejor se ajuste a su configuración.

- Cuando **ya tenga DKIM configurado**, cambie el valor de los bits ejecutando el siguiente comando:

  ```powershell
  Rotate-DkimSigningConfig -KeySize 2048 -Identity <DkimSigningConfigIdParameter>
  ```

  **o bien**

- Para una **implementación nueva de DKIM**, ejecute el siguiente comando:

  ```powershell
  New-DkimSigningConfig -DomainName <Domain for which config is to be created> -KeySize 2048 -Enabled $true
  ```

Permanezca conectado a Exchange Online PowerShell para *comprobar* la configuración ejecutando el comando siguiente:

```powershell
Get-DkimSigningConfig -Identity <Domain for which the configuration was set> | Format-List
```

> [!TIP]
> Esta nueva clave de 2048 bits tendrá efecto en el RotateOnDate y mientras tanto enviará los mensajes de correo electrónico con la clave de 1024 bits. Después de cuatro días, puede volver a probar con la clave de 2048 bits (es decir, cuando la rotación surta efecto al segundo selector).

Si desea girar al segundo selector, después de cuatro días y confirmando que el valor de 2048 bits está en uso, gire manualmente la segunda clave de selector mediante el cmdlet adecuado indicado anteriormente.

Para obtener información detallada sobre la sintaxis y los parámetros, vea los siguientes artículos: [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig), [New-DkimSigningConfig](/powershell/module/exchange/new-dkimsigningconfig) y [Get-DkimSigningConfig](/powershell/module/exchange/get-dkimsigningconfig).

## <a name="steps-to-manually-set-up-dkim"></a>Pasos que necesita seguir para configurar manualmente DKIM
<a name="SetUpDKIMO365"> </a>

Para configurar DKIM, deberá completar estos pasos:

- [Publicar dos registros CNAME para su dominio personalizado en DNS](use-dkim-to-validate-outbound-email.md#Publish2CNAME)
- [Habilitar la firma DKIM para su dominio personalizado](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>Publicar dos registros CNAME para su dominio personalizado en DNS
<a name="Publish2CNAME"> </a>

Para cada dominio para el que quiera agregar una firma DKIM en DNS, necesita publicar dos registros CNAME.

> [!NOTE]
> Si no ha leído el artículo completo, es posible que se haya perdido esta información de conexión de PowerShell para ahorrar tiempo: [Conectarse a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

Ejecute los siguientes comandos de Exchange Online PowerShell para crear los registros del selector:

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

If you have provisioned custom domains in addition to the initial domain in Microsoft 365, you must publish two CNAME records for each additional domain. So, if you have two domains, you must publish two additional CNAME records, and so on.

Use el formato siguiente para los registros CNAME.

> [!IMPORTANT]
> Si es uno de nuestros clientes de GCC High, calcularemos _customDomainIdentifier_ de forma diferente. En lugar de buscar el registro MX para su _initialDomain_ para calcular _customDomainIdentifier,_ lo calculamos directamente desde el dominio personalizado. Por ejemplo, si el dominio personalizado es "contoso.com", su _customDomainIdentifier_ se convierte en "contoso-com", los puntos se reemplazan por un guión. Por lo tanto, independientemente del registro MX al que señale su _initialDomain_, siempre se usará el método anterior para calcular el _customDomainIdentifier_ que se usará en los registros CNAME.

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<customDomainIdentifier>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<customDomainIdentifier>._domainkey.<initialDomain>
TTL:                3600
```

Donde:

- Para Microsoft 365, los selectores siempre serán "selector1" o "selector2".
- El _customDomainIdentifier_ es el mismo que el _customDomainIdentifier_ del registro MX personalizado para su dominio personalizado que aparece antes de mail.protection.outlook.com. Por ejemplo, en el siguiente registro MX para el dominio contoso.com, el _customDomainIdentifier_ es contoso-com:

  > contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com

- _initialDomain_ is the domain that you used when you signed up for Microsoft 365. Initial domains always end in onmicrosoft.com. For information about determining your initial domain, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

Por ejemplo, si tiene un dominio inicial de cohovineyardandwinery.onmicrosoft.com y dos dominios personalizados cohovineyard.com y cohowinery.com, necesitará configurar dos registros CNAME para cada dominio adicional, un total de cuatro registros CNAME.

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
> Es importante crear el segundo registro, pero solo uno de los selectores puede estar disponible en el momento de la creación. En esencia, el segundo selector podría apuntar a una dirección que aún no ha sido creada. Aun así, recomendamos crear el segundo registro CNAME, ya que la rotación de las teclas será perfecta.

### <a name="steps-to-enable-dkim-signing-for-your-custom-domain"></a>Pasos para habilitar la firma DKIM para su dominio personalizado
<a name="EnableDKIMinO365"> </a>

Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Microsoft 365. You can do this either through the Microsoft 365 admin center or by using PowerShell.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-in-the-microsoft-365-defender-portal"></a>Para habilitar la firma DKIM para el dominio personalizado en el portal de Microsoft 365 Defender

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **Directivas contra amenazas** \> **Configuración de autenticación de correo** en la sección **Reglas** \>**DKIM**. Para ir directamente a la página de DKIM, use <https://security.microsoft.com/dkimv2>.

2. En la página **DKIM**, haga clic en el nombre para seleccionar el dominio.

3. En el control flotante de detalles que aparece, cambie el ajuste **Firmar mensajes para este dominio con firmas DKIM** a **Habilitado** (![activar).](../../media/scc-toggle-on.png)

   Cuando haya terminado, haga clic en **Girar claves DKIM**.

4. Repita estos pasos para cada dominio personalizado.

5. Si va a configurar DKIM por primera vez y ve el error "No hay claves DKIM guardadas para este dominio", tendrá que usar Windows PowerShell para habilitar la firma DKIM, como se explica en el paso siguiente.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>Para habilitar la firma DKIM para su dominio personalizado mediante PowerShell

> [!IMPORTANT]
> :::image type="content" source="../../media/dkim.png" alt-text="Error &quot;No hay claves DKIM guardadas para este dominio&quot;" lightbox="../../media/dkim.png":::
> Si va a configurar DKIM por primera vez y ve el error "No hay claves DKIM guardadas para este dominio", complete el comando del paso 2 siguiente (por ejemplo, `Set-DkimSigningConfig -Identity contoso.com -Enabled $true`) para ver la clave.

1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Utilice la siguiente sintaxis:

   ```powershell
   Set-DkimSigningConfig -Identity <Domain> -Enabled $true
   ```

   \<Domain\> es el nombre del dominio personalizado para el que quiere habilitar la firma DKIM.

   En este ejemplo se habilita la firma DKIM para el dominio contoso.com:

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a>Para confirmar que la firma DKIM está configurada correctamente en Microsoft 365

Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM. This allows time for the DKIM information about the domain to be spread throughout the network.

- Envíe un mensaje desde una cuenta dentro de su dominio habilitado para DKIM en Microsoft 365 a otra cuenta de correo electrónico como outlook.com o Hotmail.com.
- Do not use an aol.com account for testing purposes. AOL may skip the DKIM check if the SPF check passes. This will nullify your test.
- Open the message and look at the header. Instructions for viewing the header for the message will vary depending on your messaging client. For instructions on viewing message headers in Outlook, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

  The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries. The message will look something like this example:

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- Look for the Authentication-Results header. While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a>Configuración de DKIM para más de un dominio personalizado
<a name="DKIMMultiDomain"> </a>

If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain. Specifically, complete all steps in [What you need to do to manually set up DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a>Deshabilitación de la directiva de firmas DKIM para un dominio personalizado
<a name="DisableDKIMSigningPolicy"> </a>

Deshabilitar la directiva de firmas no deshabilita DKIM completamente. Después de un período de tiempo, Microsoft 365 aplicará automáticamente la directiva predeterminada para el dominio, si la directiva predeterminada sigue en estado habilitado. Si desea deshabilitar completamente DKIM, debe deshabilitar DKIM en los dominios personalizados y predeterminados. Para más información sobre esta firma, consulte [Comportamiento predeterminado para DKIM y Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>Para deshabilitar la directiva de firmas DKIM mediante Windows PowerShell

1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute uno de los siguientes comandos para cada dominio para el que quiera deshabilitar la firma DKIM.

   ```powershell
   $p = Get-DkimSigningConfig -Identity <Domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   Por ejemplo:

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   O bien

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   Where _number_ is the index of the policy. For example:

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a>Comportamiento predeterminado para DKIM y Microsoft 365
<a name="DefaultDKIMbehavior"> </a>

If you do not enable DKIM, Microsoft 365 automatically creates a 2048-bit DKIM public key for your Microsoft Online Email Routing Address (MOERA)/initial domain and the associated private key which we store internally in our datacenter. By default, Microsoft 365 uses a default signing configuration for domains that do not have a policy in place. This means that if you do not set up DKIM yourself, Microsoft 365 will use its default policy and keys it creates to enable DKIM for your domain.

Además, si deshabilita la firma DKIM en el dominio personalizado después de habilitarlo, después de un período de tiempo, Microsoft 365 aplicará automáticamente la directiva de dominio inicial o MOERA para el dominio personalizado.

In the following example, suppose that DKIM for fabrikam.com was enabled by Microsoft 365, not by the administrator of the domain. This means that the required CNAMEs do not exist in DNS. DKIM signatures for email from this domain will look something like this:

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator. Eventually, every single message sent from Microsoft 365 will be DKIM-signed. If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com. If you don't, it will not align and instead will use your organization's initial domain. For information about determining your initial domain, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>Configurar DKIM para que un servicio de terceros pueda enviar, o suplantar, correo electrónico en nombre de su dominio personalizado
<a name="SetUp3rdPartyspoof"> </a>

Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service. This requires coordination between yourself and the third-party in order to set up the necessary DNS records. Some third-party servers can have their own CNAME records with different selectors. No two organizations do it exactly the same way. Instead, the process depends entirely on the organization.

Un mensaje de ejemplo que muestra un DKIM configurado correctamente para contoso.com y bulkemailprovider.com puede tener el aspecto siguiente:

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

En este ejemplo, para conseguir este resultado:

1. El proveedor de correo electrónico masivo le ha proporcionado una clave DKIM pública a Contoso.

2. Contoso ha publicado la clave DKIM en su registro DNS.

3. When sending email, Bulk Email Provider signs the key with the corresponding private key. By doing so, Bulk Email Provider attached the DKIM signature to the message header.

4. Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message. In this example, the values match:

   > sender@**contoso.com**

   > d=**contoso.com**

## <a name="identify-domains-that-do-not-send-email"></a>Identificar dominios que no envían correos electrónicos

Las organizaciones deben indicar explícitamente si un dominio no envía correos electrónicos especificando `v=DKIM1; p=` en el registro DKIM de estos dominios. Esto aconseja rechazar la recepción de servidores de correo electrónico que no tengan claves públicas válidas para el dominio y cualquier correo electrónico que declare ser de ese dominio. Debe hacerlo para cada dominio y subdominio mediante un carácter comodín DKIM.

Por ejemplo, el registro DKIM tendría el siguiente aspecto:

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a>Pasos siguientes: una vez configurado DKIM para Microsoft 365
<a name="DKIMNextSteps"> </a>

**Aunque DKIM está diseñado para ayudar a evitar la suplantación de identidad, DKIM funciona mejor con SPF y DMARC.**

Once you have set up DKIM, if you have not already set up SPF you should do so. For a quick introduction to SPF and to get it configured quickly, see [**Set up SPF in Microsoft 365 to help prevent spoofing**](set-up-spf-in-office-365-to-help-prevent-spoofing.md). For a more in-depth understanding of how Microsoft 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

Next, see [**Use DMARC to validate email**](use-dmarc-to-validate-email.md). [Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for DKIM checks.

**Esta prueba validará** que la configuración de firma DKIM se ha configurado correctamente y que se han publicado las entradas DNS adecuadas.

> [!NOTE]
> Esta función requiere una cuenta de administrador de Microsoft 365. Esta característica no está disponible para Microsoft 365 Gobierno, Microsoft 365 operado por 21Vianet o Microsoft 365 Alemania.

<div class="nextstepaction">
<p><a href="https://admin.microsoft.com/AdminPortal/?searchSolutions=DKIM#/homepage" data-linktype="external">Ejecutar pruebas: DKIM</a></p>
</div>

## <a name="more-information"></a>Más información

Rotación de clave mediante PowerShell: [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig)

[Usar DMARC para validar el correo electrónico](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)

[Use remitentes ARC de confianza para los flujos de correo legítimos](/microsoft-365/security/office-365-security/use-arc-exceptions-to-mark-trusted-arc-senders)
