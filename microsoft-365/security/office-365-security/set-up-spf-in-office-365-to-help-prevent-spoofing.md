---
title: Configurar SPF para ayudar a evitar la suplantación de identidad
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Aprenda a actualizar un registro de Servicio de nombres de dominio (DNS) para usar el marco de directivas de remitente (SPF) con su dominio personalizado en Office 365.
ms.openlocfilehash: 93356799967932813252e7db27e7ac796e46cbc6
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936942"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a>Configurar SPF para ayudar a evitar la suplantación de identidad

 **Summary:** This article describes how to update a Domain Name Service (DNS) record so that you can use Sender Policy Framework (SPF) with your custom domain in Office 365. Using SPF helps to validate outbound email sent from your custom domain.

In order to use a custom domain, Office 365 requires that you add a Sender Policy Framework (SPF) TXT record to your DNS record to help prevent spoofing. SPF identifies which mail servers are allowed to send mail on your behalf. Basically, SPF, along with DKIM, DMARC, and other technologies supported by Office 365, help prevent spoofing and phishing. SPF is added as a TXT record that is used by DNS to identify which mail servers can send mail on behalf of your custom domain. Recipient mail systems refer to the SPF TXT record to determine whether a message from your custom domain comes from an authorized messaging server.

For example, let's say that your custom domain contoso.com uses Office 365. You add an SPF TXT record that lists the Office 365 messaging servers as legitimate mail servers for your domain. When the receiving messaging server gets a message from joe@contoso.com, the server looks up the SPF TXT record for contoso.com and finds out whether the message is valid. If the receiving server finds out that the message comes from a server other than the Office 365 messaging servers listed in the SPF record, the receiving mail server can choose to reject the message as spam.

Also, if your custom domain does not have an SPF TXT record, some receiving servers may reject the message outright. This is because the receiving server cannot validate that the message comes from an authorized messaging server.

If you've already set up mail for Office 365, then you have already included Microsoft's messaging servers in DNS as an SPF TXT record. However, there are some cases where you may need to update your SPF TXT record in DNS. For example:

- Previously, you had to add a different SPF TXT record to your custom domain if you were using SharePoint Online. This is no longer required. This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder. Update your SPF TXT record if you are hitting the 10 lookup limit and receiving errors that say things like, "exceeded the lookup limit" and "too many hops".

- Tiene un entorno híbrido con Office 365 y Exchange local.

- Quiere configurar DKIM y DMARC (recomendado).

## <a name="updating-your-spf-txt-record-for-office-365"></a>Actualizar el registro TXT de SPF para Office 365

Before you update the TXT record in DNS, you need to gather some information and determine the format of the record. This will help prevent you from generating DNS errors. For advanced examples and a more detailed discussion about supported SPF syntax, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

Recopile esta información:

- The current SPF TXT record for your custom domain. For instructions, see [Gather the information you need to create Office 365 DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).

- External IP addresses of all on-premises messaging servers. For example, **131.107.2.200**.

- Domain names to use for all third-party domains that you need to include in your SPF TXT record. Some bulk mail providers have set up subdomains to use for their customers. For example, the company MailChimp has set up **servers.mcsv.net**.

- Determine what enforcement rule you want to use for your SPF TXT record. We recommend **-all**. For detailed information about other syntax options, see [SPF TXT record syntax for Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).

### <a name="to-add-or-update-your-spf-txt-record"></a>Para agregar o actualizar el registro TXT de SPF

1. Asegúrese de que está familiarizado con la sintaxis SFP de la siguiente tabla.

   ||**Si usa...**|**¿Es común para los clientes?**|**Agregue esto...**|
   |:-----|:-----|:-----|:-----|
   |1|Cualquier sistema de correo electrónico (obligatorio)|Common. All SPF TXT records start with this value|v=spf1|
   |2|Exchange Online|Común|include:spf.protection.outlook.com|
   |3|Solo Exchange Online dedicado|No es común|ip4:23.103.224.0/19 ip4:206.191.224.0/19 ip4:40.103.0.0/16 include:spf.protection.outlook.com|
   |4|Solo para Office 365 Alemania y Microsoft Cloud Alemania|No es común|include:spf.protection.outlook.de|
   |5|Sistema de correo electrónico de terceros|No es común|incluye:\<domain name\>  <br/> Donde <domain name> es el nombre de dominio del sistema de correo electrónico de terceros.|
   |6|On-premises mail system. For example, Exchange Online Protection plus another mail system|No es común| Use uno de estos para cada sistema de correo adicional: <br> ip4:\<_IP address_\>  <br/>  ip6:\<_IP address_\>  <br/>  Incluye:\<_domain name_\>  <br/>  Donde el valor de \<_IP address_\> es la dirección IP del otro sistema de correo y \<_domain name_\> es el nombre de dominio del otro sistema de correo que envía correo en nombre de su dominio.|
   |7|Cualquier sistema de correo electrónico (obligatorio)|Common. All SPF TXT records end with this value|\<_enforcement rule_\>  <br/> This can be one of several values. We recommend that you use **-all**.|

2. Si todavía no lo ha hecho, para formar el registro TXT de SPF use la sintaxis de la tabla:

   Por ejemplo, si está completamente hospedado en Office 365, es decir, no tiene ningún servidor de correo local, el registro TXT de SPF incluiría las filas 1, 2 y 7 y tendría este aspecto:

   `v=spf1 include:spf.protection.outlook.com -all`

   Este es el registro TXT de SPF más común. Este registro funciona para casi todos los usuarios, independientemente de si su centro de datos de Microsoft se encuentra en los Estados Unidos, en Europa (incluyendo Alemania) o en otra ubicación.

   Sin embargo, si ha adquirido Office 365 Alemania, parte de la nube de Microsoft Alemania, debe utilizar la instrucción include de la línea 4 en lugar de la línea 2. Por ejemplo, si está completamente hospedado en Office 365 Alemania, es decir, no tiene ningún servidor de correo local, el registro TXT de SPF incluiría las filas 1, 4 y 7 y tendría este aspecto:

   `v=spf1 include:spf.protection.outlook.de -all`

   Si ya ha implementado Office 365 y ha configurado sus registros SPF TXT para su dominio personalizado y va a migrar a Office 365 Alemania, debe actualizar el registro SPF TXT. Para ello, cambie **include:spf.protection.outlook.com** por **include.spf.protection.outlook.de**.

3. Una vez que ha formado el registro TXT de SPF, debe actualizar el registro en DNS. Solo puede tener un registro TXT de SPF para un dominio. Si existe un registro TXT de SPF, en vez de agregar un registro nuevo, debe actualizar el registro existente. Vaya a [Crear registros DNS para Office 365 al administrar los registros DNS](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) y haga clic en el vínculo para su host DNS.

4. Pruebe el registro TXT de SPF

## <a name="more-information-about-spf"></a>Más información sobre SPF

Para obtener ejemplos avanzados y explicaciones más detalladas sobre la sintaxis admitida de SPF, la suplantación de identidad, la solución de problemas y la manera en que Office 365 admite SPF, vea [Cómo funciona SPF para evitar la suplantación de identidad en Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

## <a name="next-steps-after-you-set-up-spf-for-office-365"></a>Pasos siguientes: Una vez configurado SPF para Office 365

Having trouble with your SPF TXT record? Read [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).

 SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against. In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Office 365. To get started, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md). Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).
