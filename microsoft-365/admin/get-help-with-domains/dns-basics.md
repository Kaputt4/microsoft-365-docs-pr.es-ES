---
title: Conceptos básicos sobre DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: Obtenga información sobre los dominios y sus registros DNS asociados para ayudarle a administrar los dominios.
ms.openlocfilehash: a69f6a34585f7ff033a30e10254f29b89d978d3e
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079996"
---
# <a name="dns-basics"></a>Conceptos básicos sobre DNS

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
::: moniker range="o365-worldwide"

Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases. The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment. An understanding of DNS and domain registrar basics can help you manage domains.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases. The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment. An understanding of DNS and domain registrar basics can help you manage domains.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

Los nombres de dominio, como contoso.com, se administran con un sistema mundial de bases de datos y registradores de dominios. El Sistema de nombres de dominio (DNS) proporciona una asignación entre nombres de hosts de equipos legibles y las direcciones IP que usan los dispositivos de red. Comprender los conceptos básicos de DNS y los registradores de dominios ayudará a administrar dominios.
  
::: moniker-end

## <a name="what-are-domain-names"></a>¿Qué son los nombres de dominio?

Domain names are used in URLs and email addresses, and they have different levels. For example, mail.contoso.com is a domain name with the following three levels:
  
- **.com** es el dominio de primer nivel. 
    
- **contoso** es el dominio de segundo nivel. 
    
- **correo** es el dominio de tercer nivel. 
    
Why use a third-level domain? You might want to have different domain names for marketing or a blog. For example, blog.contoso.com. You typically add a second-level domain, like contoso.com, to use with Microsoft but you can also use third-level domains if you like.
  
Obtenga más información sobre qué puede hacer con los dominios para cada tipo de oferta en la [descripción del servicio de la plataforma de Office 365 y Microsoft 365](https://go.microsoft.com/fwlink/?LinkId=402693).
  
## <a name="understand-dns-record-types"></a>Comprender los tipos de registros DNS

DNS records stored at a DNS host for your domain are used to direct traffic for your domain. The following table describes frequently used DNS records and how they're used.
  
|**Registro NS (servidor de nombres)**|**Identifica los servidores de nombres que son los "servidores de nombres autoritativos" de un dominio. Al cambiar los servidores de nombres del dominio, cambia dónde se administran los registros DNS y el lugar en el que el sistema DNS busca información sobre los servidores de correo, etc. Microsoft cuenta con sus propios servidores de nombres, pero también puede optar por usar los servidores de nombres que ya estén configurados en su dominio.**|
|:-----|:-----|
|Registro A (registro de dirección)  <br/> |Asocia un nombre de dominio a una dirección IP.  <br/> |
|Registro CNAME (alias o nombre canónico)  <br/> |Redirects one domain to another in the DNS system. When a name server looks up a domain and finds that it has a CNAME record, the server replaces the first domain name with the CNAME, and then looks up the new name.  <br/> |
|Registro MX (intercambiador de correo)  <br/> |Points to where your email should be sent. It also has a priority field so that you can send mail to different servers in a priority order.  <br/> |
|Registro SPF (marco de directivas de remitente)  <br/> |Registro TXT que ayuda a evitar la suplantación de identidad (spoofing y phishing) a través del correo electrónico.  <br/> |
|Registro SRV (servicio)  <br/> |Used by Skype for Business Online and Exchange Online to coordinate the flow of information between Microsoft services. For example, the SRV records are required to see presence in Outlook Web App, and to use Skype for Business Online, Skype, or other instant messaging tools with people in other companies.  <br/> |
|TTL (período de vida)  <br/> |La cantidad de tiempo que un servidor de nombre guarda un registro DNS antes de que el servidor busque una versión actualizada.  <br/> |
   
## <a name="how-does-dns-work"></a>¿Cómo funciona el sistema DNS?

Part of setting up your domain with a cloud service like Microsoft 365 includes changing or adding [DNS records](dns-basics.md) for the domain. These changes are required because of how the Internet works with the DNS, Domain Name System, and domain names, to know where to send or find things, like email and websites. 
  
The Internet is set up to use DNS, or Domain Name System, which lets us use familiar names, like contoso.com, to locate specific Internet locations that are actually, under the covers, labeled with hard-to-remember numbers called IP (Internet Protocol) addresses. IP addresses look something like 70.42.241.42, so you can see it's much easier to use a domain name to identify locations like email hosts and websites.
  
So that's the short answer: DNS records tell the Internet where to send email (like joe@contoso.com) or find websites (like www.contoso.com) that use your domain name. When you put the right information into the right DNS records for your domain, the DNS system routes everything correctly so your email, for example, arrives in Microsoft 365 instead of somewhere else.
  
A domain's DNS records can be helpful in other ways, too. For example, Exchange checks a DNS record that lets Outlook automatically set up a connection to the right Exchange server.
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a>Los registros DNS ayudan a Internet a enviar el correo electrónico a la ubicación adecuada

As you read above, DNS essentially directs traffic around the Internet, mapping friendly domain names to those hard-to-remember IP addresses. One DNS record, called the MX record, is specifically for sending email to the right host.
  
DNS records are like a database of information about your domain. The records and their values are kept in something called a zone file, which includes a list of each record for your domain and what its value is. Domain registrars and other DNS hosting companies provide a UI on their websites so you can edit the records in your domain's zone file. And that's where you update the MX record for your domain, to send email messages to Microsoft 365.
  
 *When you change your email to Microsoft 365, by updating your domain's MX record in the next step, ALL email sent to that domain will start coming to Microsoft 365.*  If other people use your domain for email, you must set up Microsoft 365 mailboxes for each of those people. 
  
Sound complicated? Well, it can be, but we walk you through each step in the Microsoft domain setup.
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a>El sistema DNS también indica a Internet dónde debe buscar sitios web

When you type in a website address, for example, www.contoso.com, the Internet first checks with one of the DNS servers for something called a name server (NS) record for (in this case) contoso.com. The NS record tells the Internet where it should look for the zone file that has all the other DNS record values for that domain. There are lots of DNS servers, all connected to each other. The servers work together to keep track of all registered domain names, which have to be unique, and where the domain's zone files are.
  
::: moniker range="o365-worldwide"

Let's say that the NS record for contoso.com says "godaddy.com." Now the Internet knows that GoDaddy.com is where to look for the zone file listing all the other DNS records for contoso.com. Those DNS records include the MX record that says where to send emails for contoso.com and other records. If the MX record has a value that says (but in technical terms) "send email to Microsoft 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent. Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.

::: moniker-end

::: moniker range="o365-germany"

Let's say that the NS record for contoso.com says "godaddy.com." Now the Internet knows that GoDaddy.com is where to look for the zone file listing all the other DNS records for contoso.com. Those DNS records include the MX record that says where to send emails for contoso.com and other records. If the MX record has a value that says (but in technical terms) "send email to Microsoft 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent. Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.

::: moniker-end

::: moniker range="o365-21vianet"

Supongamos que el registro NS para contoso.com dice "hichina.com.". Ahora, Internet sabe que hichina.com es donde debe buscar el archivo de zona en el que se enumeran los demás registros de DNS para contoso.com. Estos registros DNS incluyen el registro MX que dice dónde deben enviarse los correos electrónicos de contoso.com y otros registros. Si el registro MX tiene un valor que indica (en términos técnicos) "enviar correo electrónico a Microsoft 365", aquí es donde se enviarán todos los mensajes de correo electrónico enviados a una dirección de correo electrónico contoso.com (como joe@contoso.com). Y siempre que haya un buzón llamado "joe" en esa ubicación, el correo electrónico se entregará.

::: moniker-end

The actual values that you must enter for all of this to work with Microsoft 365 are listed for you when you're setting up your domain, in the domain setup steps. If you're doing the set up manually, you copy and paste the values into the correct DNS records (MX record, CNAME records, and so on) at your DNS host, which might be your domain registrar but doesn't have to be.
  
::: moniker range="o365-worldwide"

Why might your domain's zone file be somewhere besides at your domain registrar? Well, you might register your domain name at a domain registrar like GoDaddy, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company. The NS records for your domain store that information so all the DNS servers know where to look.

::: moniker-end

::: moniker range="o365-germany"

Why might your domain's zone file be somewhere besides at your domain registrar? Well, you might register your domain name at a domain registrar like GoDaddy, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company. The NS records for your domain store that information so all the DNS servers know where to look.

::: moniker-end

::: moniker range="o365-21vianet"

¿Por qué es posible que el archivo de zona de su dominio esté en otro lugar aparte del registrador de dominios? Bueno, es posible que registre su nombre de dominio en un registrador de dominios como HiChina, pero que los registros DNS se administren en otra ubicación, en una empresa de hospedaje DNS independiente o una compañía de hospedaje de sitios web. Los registros NS de su dominio almacenan esta información para que todos los servidores DNS sepan dónde buscar.

::: moniker-end

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-microsoft-365"></a>¿Por qué agregar un dominio a Microsoft 365?


Adding a custom domain, like fourthcoffee.com, to Microsoft 365 lets you use a shorter, more familiar email address and userID with the service. You're [given a domain to use](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) when you sign up for a Microsoft 365 account, but it includes "onmicrosoft.com." Many people prefer to add their organization or business domain if they plan to use Microsoft 365 for email. 
  
> [!NOTE]
> Si solo desea descargar y usar aplicaciones de Microsoft, como Outlook o Word, no deberá agregar un dominio: [Instalar Office en su PC o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
Puede usar su nombre de dominio en Microsoft 365 con su correo electrónico, sitio web público y dirección de mensajería instantánea.
  
- **Email:** Your domain name lets you customize your email, so you can use a shorter, easier-to-remember address than [the initial onmicrosoft.com email address](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) that comes with your account. So instead of joe@contoso.onmicrosoft.com, the email address (which is also the work account that you use to sign in to Microsoft 365) could be joe@contoso.com. 
    
- **Sitio web:** si dispone de una suscripción a Microsoft 365 que incluye un sitio web público de SharePoint Online (ya no está disponible para la compra), la dirección inicial de dicho sitio web es de este tipo: contoso-public.sharepoint.com. Si configura un sitio web para su empresa, puede usar un nombre de dominio personalizado para cambiar el nombre de la dirección del sitio web por algo como, por ejemplo, www.contoso.com. 
    
- **Mensajería instantánea:** la dirección de Skype Empresarial Online también puede personalizarse para usar el nombre del dominio, de modo que las personas de la organización puedan conectarse entre ellas en Skype Empresarial Online usando una dirección más corta y fácil de recordar (por ejemplo, joe@contoso.com). 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-microsoft-365"></a>¿Por qué agregar un dominio a Microsoft 365?


Adding a custom domain, like fourthcoffee.com, to Microsoft 365 lets you use a shorter, more familiar email address and userID with the service. You're [given a domain to use](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) when you sign up for a Microsoft 365 account, but it includes "onmicrosoft.com." Many people prefer to add their organization or business domain if they plan to use Microsoft 365 for email. 
  
> [!NOTE]
> Si solo quiere descargar y usar aplicaciones de Microsoft 365, como Outlook o Word, no deberá agregar un dominio: [Instalar Office en su PC o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
Puede usar su nombre de dominio en Microsoft 365 con su correo electrónico, sitio web público y dirección de mensajería instantánea.
  
- **Email:** Your domain name lets you customize your email, so you can use a shorter, easier-to-remember address than [the initial onmicrosoft.com email address](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) that comes with your account. So instead of joe@contoso.onmicrosoft.com, the email address (which is also the work account that you use to sign in to Microsoft 365) could be joe@contoso.com. 
    
- **Sitio web:** si dispone de una suscripción que incluye un sitio web público de SharePoint Online (ya no está disponible para la compra), la dirección inicial de dicho sitio web es de este tipo: contoso-public.sharepoint.com. Si configura un sitio web para su empresa, puede usar un nombre de dominio personalizado para cambiar el nombre de la dirección del sitio web por algo como, por ejemplo, www.contoso.com. 
    
- **Mensajería instantánea:** la dirección de Skype Empresarial Online también puede personalizarse para usar el nombre del dominio, de modo que las personas de la organización puedan conectarse entre ellas en Skype Empresarial Online usando una dirección más corta y fácil de recordar (por ejemplo, joe@contoso.com). 
    
::: moniker-end

## <a name="the-dns-records-required-for-microsoft-365"></a>Registros DNS necesarios para Microsoft 365

There are a number of DNS records required for Microsoft 365 to work with your domain. In addition to setting up your domain's MX record so email will be sent to Microsoft 365, there are records to help with tasks like making sure Outlook can automatically connect to the right Exchange server, setting up instant messaging, and helping to prevent spam email.
  
You can [find a list of values](information-for-dns-records.md) to set up your domain. They're included right in the Microsoft 365 admin center. 
  
Si está planificando una implementación, tal vez quiera revisar una lista de todos los registros DNS necesarios para Microsoft 365, sus funciones y valores de ejemplo. Consulte [Registros externos del sistema de nombres de dominio para Microsoft 365](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).
  
## <a name="how-can-i-learn-more"></a>¿Cómo puedo obtener más información?

Consulte uno de estos procedimientos: 
  
- ¿No sabe dónde está registrado su dominio? [Obtenga ayuda para encontrar su registrador de dominios](find-your-domain-registrar.md).
- Averigüe [por qué tiene que completar los pasos del asistente](../setup/add-domain.md) para poder usar su dominio con Microsoft 365.
