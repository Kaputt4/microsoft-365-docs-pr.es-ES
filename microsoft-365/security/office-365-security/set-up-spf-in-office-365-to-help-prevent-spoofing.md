---
title: Configurar SPF para ayudar a evitar la suplantación de identidad
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
ms.localizationpriority: high
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- m365-security
ms.custom:
- seo-marvel-apr2020
description: Aprenda a actualizar un registro de Servicio de nombres de dominio (DNS) para usar el marco de directivas de remitente (SPF) con su dominio personalizado en Office 365.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 506e23b7dd3441da49fdd48b6772eb280caafd70
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68072227"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a>Configurar SPF para ayudar a evitar la suplantación de identidad

- [Requisitos previos](#prerequisites)
- [Crear o actualizar el registro TXT de SPF](#create-or-update-your-spf-txt-record)
- [¿Cómo se tratan los subdominios?](#how-to-handle-subdomains)
- [Solución de problemas con SPF](#troubleshooting-spf)

<!--
[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Applies to**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 plan 1 and plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
-->

En este artículo se describe cómo actualizar un registro del servicio de nombres de dominio (DNS) para que pueda usar la autenticación de correo electrónico del Marco de directivas de remitente (SPF)  con su dominio personalizado en Office 365.

SPF ayuda a *validar* el correo electrónico saliente enviado desde su dominio personalizado (si proviene de quien dice ser). Es un primer paso para configurar los métodos completos de autenticación de correo electrónico recomendados de SPF, [DKIM](use-dkim-to-validate-outbound-email.md)y [DMARC](use-dmarc-to-validate-email.md).

- [Requisitos previos](#prerequisites)
- [Crear o actualizar el registro TXT de SPF](#create-or-update-your-spf-txt-record)
  - [¿Cómo se tratan los subdominios?](#how-to-handle-subdomains)
- [¿Qué hace realmente la autenticación de correo electrónico SPF?](#what-does-spf-email-authentication-actually-do)
  - [Solucionar problemas relacionados con SPF](#troubleshooting-spf)
- [Más información sobre SPF](#more-information-about-spf)

## <a name="prerequisites"></a>Requisitos previos

> [!IMPORTANT]
> Si es administrador de una **pequeña empresa** o está familiarizado con las direcciones IP o la configuración de DNS, llame a su registrador de dominios de Internet (p. ej. GoDaddy, Bluehost,web.com) y solicitar ayuda con la *configuración de DNS de SPF* (y cualquier otro método de autenticación de correo electrónico). <p> **Si no usa una dirección URL personalizada** (y la dirección URL que se usa para Office 365 termina en **onmicrosoft.com**), SPF ya se ha configurado para usted en el servicio de Office 365.

Comencemos.

El registro TXT de SPF para Office 365 se hará en un DNS externo para cualquier dominio o subdominio personalizado. Necesita cierta información para realizar el registro. Recopile esta información:

- The SPF TXT record for your custom domain, if one exists. For instructions, see [Gather the information you need to create Office 365 DNS records](../../admin/get-help-with-domains/information-for-dns-records.md).

- Go to your messaging server(s) and find out the External IP addresses (needed from all on-premises messaging servers). For example, **131.107.2.200**.

- Domain names to use for all third-party domains that you need to include in your SPF TXT record. Some bulk mail providers have set up subdomains to use for their customers. For example, the company MailChimp has set up **servers.mcsv.net**.

- Figure out what enforcement rule you want to use for your SPF TXT record. The **-all** rule is recommended. For detailed information about other syntax options, see [SPF TXT record syntax for Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).

> [!IMPORTANT]
> Para poder utilizar un dominio personalizado, Office 365 requiere que agregue un registro TXT de marco de directivas de remitente (SPF) en su registro DNS para ayudar a evitar la suplantación de identidad.

## <a name="create-or-update-your-spf-txt-record"></a>Crear o actualizar el registro TXT de SPF

1. Asegúrese de que está familiarizado con la sintaxis SFP de la siguiente tabla.

    |Elemento|Si usa...|¿Es común para los clientes?|Agregue esto...|
    |---|---|---|---|
    |1|Cualquier sistema de correo electrónico (obligatorio)|Common. All SPF TXT records start with this value|`v=spf1`|
    |2|Exchange Online|Común|`include:spf.protection.outlook.com`|
    |3|Solo Exchange Online dedicado|No es común|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
    |4|Solo para Office 365 Alemania y Microsoft Cloud Alemania|No es común|`include:spf.protection.outlook.de`|
    |5|Sistema de correo electrónico de terceros|No es común|`include:<domain_name>` <p> \<domain_name\> es el dominio del sistema de correo electrónico de terceros.|
    |6|On-premises email system. For example, Exchange Online Protection plus another email system|No es común|Use uno de estos para cada sistema de correo adicional: <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> \<IP_address\> y \<domain_name\> son la dirección IP y el dominio del otro sistema de correo que envía correos en nombre de su dominio.|
    |7 |Cualquier sistema de correo electrónico (obligatorio)|Common. All SPF TXT records end with this value|`<enforcement rule>` <p> This can be one of several values. We recommend the value `-all`.|

2. Si todavía no lo ha hecho, para formar el registro TXT de SPF, use la sintaxis de la tabla.

   Por ejemplo, si está hospedado por completo en Office 365, es decir, no tiene ningún servidor de correo local, el registro TXT de SPF incluiría las filas 1, 2 y 7, y tendría este aspecto:

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   **The example above is the most common SPF TXT record**. This record works for just about everyone, regardless of whether your Microsoft datacenter is located in the United States, or in Europe (including Germany), or in another location.

   Sin embargo, si ha adquirido Office 365 Alemania, parte de la nube de Microsoft Alemania, debe utilizar la instrucción incluir de la línea 4 en lugar de la línea 2. Por ejemplo, si está completamente hospedado en Office 365 Alemania, es decir, no tiene ningún servidor de correo local, el registro TXT de SPF incluiría las filas 1, 4 y 7, y tendría este aspecto:

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   If you're already deployed in Office 365 and have set up your SPF TXT records for your custom domain, and you're migrating to Office 365 Germany, you need to update your SPF TXT record. To do this, change `include:spf.protection.outlook.com` to `include:spf.protection.outlook.de`.

3. Once you have formed your SPF TXT record, you need to update the record in DNS. **You can only have one SPF TXT record for a domain.** If an SPF TXT record exists, instead of adding a new record, you need to update the existing record. Go to [Create DNS records for Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md), and then select the link for your DNS host.

4. Pruebe el registro TXT de SPF

## <a name="how-to-handle-subdomains"></a>¿Cómo se tratan los subdominios?

Es importante tener en cuenta que *necesita crear un registro independiente para cada subdominio, ya que los subdominios no heredan el registro SPF de su dominio de nivel superior*.

A wildcard SPF record (`*.`) is required for every domain and subdomain to prevent attackers from sending email claiming to be from non-existent subdomains. For example:

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a>Solucionar problemas relacionados con SPF

Having trouble with your SPF TXT record? Read [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).

## <a name="what-does-spf-email-authentication-actually-do"></a>¿Qué hace realmente la autenticación de correo electrónico SPF?

SPF identifies which mail servers are allowed to send mail on your behalf. Basically, SPF, along with DKIM, DMARC, and other technologies supported by Office 365, help prevent spoofing and phishing. SPF is added as a TXT record that is used by DNS to identify which mail servers can send mail on behalf of your custom domain. Recipient mail systems refer to the SPF TXT record to determine whether a message from your custom domain comes from an authorized messaging server.

For example, let's say that your custom domain contoso.com uses Office 365. You add an SPF TXT record that lists the Office 365 messaging servers as legitimate mail servers for your domain. When the receiving messaging server gets a message from joe@contoso.com, the server looks up the SPF TXT record for contoso.com and finds out whether the message is valid. If the receiving server finds out that the message comes from a server other than the Office 365 messaging servers listed in the SPF record, the receiving mail server can choose to reject the message as spam.

Also, if your custom domain does not have an SPF TXT record, some receiving servers may reject the message outright. This is because the receiving server cannot validate that the message comes from an authorized messaging server.

If you've already set up mail for Office 365, then you have already included Microsoft's messaging servers in DNS as an SPF TXT record. However, there are some cases where you may need to update your SPF TXT record in DNS. For example:

- Previously, you had to add a different SPF TXT record to your custom domain if you were using SharePoint Online. This is no longer required. This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder. Update your SPF TXT record if you are hitting the 10 lookup limit and receiving errors that say things like, "exceeded the lookup limit" and "too many hops".

- Tiene un entorno híbrido con Office 365 y Exchange local.

- Quiere configurar DKIM y DMARC (recomendado).

## <a name="more-information-about-spf"></a>Más información sobre SPF

Para obtener ejemplos avanzados y explicaciones más detalladas sobre la sintaxis admitida de SPF, la suplantación de identidad, la solución de problemas y la manera en que Office 365 admite SPF, vea [Cómo funciona SPF para evitar la suplantación de identidad en Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

## <a name="next-steps-dkim-and-dmarc"></a>Pasos siguientes: DKIM y DMARC

 SPF está diseñado para ayudar a evitar la suplantación de identidad, pero existen técnicas de suplantación de identidad contra las que SPF no puede protegerlo. Para defenderse de estos, una vez que haya configurado SPF, debe configurar DKIM y DMARC para Office 365.

El objetivo de la autenticación de correo electrónico [**DKIM**](use-dkim-to-validate-outbound-email.md) es demostrar que el contenido del correo no haya sido manipulado.

El objetivo de la autenticación de correo electrónico [**DMARC**](use-dmarc-to-validate-email.md) es asegurarse de que la información de SPF y DKIM coincida con la dirección De.

 Para obtener ejemplos avanzados y explicaciones más detalladas sobre la sintaxis admitida de SPF, consulte [Cómo funciona SPF para evitar la suplantación de identidad y el phishing en Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

[Use remitentes ARC de confianza para los flujos de correo legítimos](/microsoft-365/security/office-365-security/use-arc-exceptions-to-mark-trusted-arc-senders)

*Seleccione "Esta página" en "Comentarios" si tiene comentarios sobre esta documentación.*
