---
title: Usar DMARC para validar el correo electrónico
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo configurar Domain-based Message Authentication, Reporting, and Conformance (DMARC) para validar mensajes enviados desde la organización.
ms.openlocfilehash: adc213ec5c47184f997a812425e53a61d7ac2da3
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016331"
---
# <a name="use-dmarc-to-validate-email"></a>Usar DMARC para validar el correo electrónico

Domain-based Message Authentication, Reporting, and Conformance ([DMARC](https://dmarc.org)) trabaja con el marco de directivas de remitente (SPF) y DomainKeys Identified Mail (DKIM) para autenticar a los remitentes de los correos y garantizar que los sistemas de correo electrónico de destino confíen en los mensajes enviados desde su dominio. Implementar DMARC con SPF y DKIM ofrece protección adicional contra el correo electrónico de suplantación de identidad. DMARC permite a los sistemas que reciben los correos determinar qué hacer con los mensajes enviados desde su dominio que no superan las comprobaciones SPF o DKIM.

> [!TIP]
> Visite el catálogo de la [Asociación de seguridad inteligente de Microsoft (MISA)](https://www.microsoft.com/misapartnercatalog) para ver los proveedores que ofrecen informes DMARC para Microsoft 365.

## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-microsoft-365"></a>¿Cómo se coordinan SPF y DMARC para proteger el correo electrónico en Microsoft 365?

 Un mensaje de correo electrónico puede contener varias direcciones de remitentes, que se usan para distintos propósitos. Por ejemplo, observe las siguientes direcciones:

- **Dirección "Correo de"**: identifica al remitente y especifica dónde se deben enviar los avisos de devolución si se produce algún problema al entregar el mensaje (por ejemplo, un aviso de no entrega). Aparece en la zona del sobre de un mensaje de correo electrónico, aunque su aplicación de correo electrónico no suele mostrarla. A veces, recibe la denominación dirección 5321.MailFrom o dirección de ruta de acceso inversa.

- **Dirección «De»**: es la dirección que se muestra como dirección De en el cliente de correo de la aplicación. Esta dirección identifica al autor del correo electrónico. Es decir, el buzón de la persona o el sistema responsables de escribir el mensaje. A veces, recibe la denominación dirección 5322.From.

SPF uses a DNS TXT record to provide a list of authorized sending IP addresses for a given domain. Normally, SPF checks are only performed against the 5321.MailFrom address. This means that the 5322.From address is not authenticated when you use SPF by itself. This allows for a scenario where a user can receive a message which passes an SPF check but has a spoofed 5322.From sender address. For example, consider this SMTP transcript:

```text
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S:
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S:
S: https://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

En esta transcripción, las direcciones del remitente son las siguientes:

- Dirección MailFrom (5321.MailFrom): phish@phishing.contoso.com

- Dirección From (5322.From): security@woodgrovebank.com

If you configured SPF, then the receiving server performs a check against the Mail from address phish@phishing.contoso.com. If the message came from a valid source for the domain phishing.contoso.com then the SPF check passes. Since the email client only displays the From address, the user sees that this message came from security@woodgrovebank.com. With SPF alone, the validity of woodgrovebank.com was never authenticated.

When you use DMARC, the receiving server also performs a check against the From address. In the example above, if there is a DMARC TXT record in place for woodgrovebank.com, then the check against the From address fails.

## <a name="what-is-a-dmarc-txt-record"></a>¿Qué es un registro TXT de DMARC?

Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing. You publish DMARC TXT records in DNS. DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain. The DMARC TXT record identifies authorized outbound email servers. Destination email systems can then verify that messages they receive originate from authorized outbound email servers.

El registro TXT de DMARC de Microsoft es algo así:

```text
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1"
```

Microsoft envía sus informes DMARC a [Agari](https://agari.com), un tercero. Agari recoge y analiza los informes de la DMARC. Visite el [catálogo de MISA](https://www.microsoft.com/misapartnercatalog) para ver más proveedores que ofrecen informes DMARC para Microsoft 365.

## <a name="implement-dmarc-for-inbound-mail"></a>Implementar DMARC para el correo entrante

You don't have to do a thing to set up DMARC for mail that you receive in Microsoft 365. We've taken care of everything for you. If you want to learn what happens to mail that fails to pass our DMARC checks, see [How Microsoft 365 handles inbound email that fails DMARC](#how-microsoft-365-handles-inbound-email-that-fails-dmarc).

## <a name="implement-dmarc-for-outbound-mail-from-microsoft-365"></a>Implementar DMARC para el correo saliente de Microsoft 365

If you use Microsoft 365 but you aren't using a custom domain, that is, you use onmicrosoft.com, you don't need to do anything else to configure or implement DMARC for your organization. SPF is already set up for you and Microsoft 365 automatically generates a DKIM signature for your outgoing mail. For more information about this signature, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).

 If you have a custom domain or you are using on-premises Exchange servers in addition to Microsoft 365, you need to manually implement DMARC for your outbound mail. Implementing DMARC for your custom domain includes these steps:

- [Paso 1: Identificar orígenes válidos de correo para el dominio](#step-1-identify-valid-sources-of-mail-for-your-domain)

- [Paso 2: Configurar SPF para el dominio](#step-2-set-up-spf-for-your-domain)

- [Paso 3: Configurar DKIM para el dominio personalizado](#step-3-set-up-dkim-for-your-custom-domain)

- [Paso 4: Formular el registro TXT de DMARC para el dominio](#step-4-form-the-dmarc-txt-record-for-your-domain)

### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a>Paso 1: Identificar orígenes válidos de correo para el dominio

If you have already set up SPF then you have already gone through this exercise. However, for DMARC, there are additional considerations. When identifying sources of mail for your domain there are two questions you need to answer:

- ¿Qué direcciones IP envían mensajes desde mi dominio?

- En los correos electrónicos enviados por parte de terceros en mi nombre, ¿coincidirán los dominios 5321.MailFrom y 5322.From?

### <a name="step-2-set-up-spf-for-your-domain"></a>Paso 2: Configurar SPF para el dominio

Ahora que tiene una lista de todos los remitentes válidos, puede seguir los pasos para [Configurar SPF para evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md).

Por ejemplo, suponiendo que contoso.com envía correos desde Exchange Online, un servidor Exchange local cuya dirección IP fuera 192.168.0.1 y una aplicación web cuya dirección IP fuera 192.168.100.100, el registro TXT de SPF tendría este aspecto:

```text
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

Como práctica recomendada, asegúrese de que el registro TXT de SPF tenga en cuenta a los remitentes externos.

### <a name="step-3-set-up-dkim-for-your-custom-domain"></a>Paso 3: Configurar DKIM para el dominio personalizado

Once you have set up SPF, you need to set up DKIM. DKIM lets you add a digital signature to email messages in the message header. If you do not set up DKIM and instead allow Microsoft 365 to use the default DKIM configuration for your domain, DMARC may fail. This is because the default DKIM configuration uses your initial onmicrosoft.com domain as the 5322.From address, not your custom domain. This forces a mismatch between the 5321.MailFrom and the 5322.From addresses in all email sent from your domain.

If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email. To avoid this, you need to set up DKIM for your domain specifically with that third-party sender. This allows Microsoft 365 to authenticate email from this 3rd-party service. However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you. This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Microsoft 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.

Para ver las instrucciones sobre cómo configurar DKIM para el dominio, incluyendo cómo configurar DKIM para remitentes externos para que puedan suplantar la identidad de su dominio, consulte [Usar DKIM para validar el correo electrónico saliente enviado desde el dominio personalizado](use-dkim-to-validate-outbound-email.md).

### <a name="step-4-form-the-dmarc-txt-record-for-your-domain"></a>Paso 4: Formular el registro TXT de DMARC para el dominio

Although there are other syntax options that are not mentioned here, these are the most commonly used options for Microsoft 365. Form the DMARC TXT record for your domain in the format:

```text
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; p=policy; pct=100"
```

donde:

- *domain* es el dominio que quiere proteger. De forma predeterminada, el registro protege el correo del dominio y todos los subdominios. Por ejemplo, si especifica \_dmarc.contoso.com, DMARC protege correo del dominio y todos los subdominios, como housewares.contoso.com o plumbing.contoso.com.

- *TTL* should always be the equivalent of one hour. The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.

- *pct=100* indica que esta regla debe usarse para el 100 % del correo electrónico.

- *policy* specifies what policy you want the receiving server to follow if DMARC fails. You can set the policy to none, quarantine, or reject.

Para obtener información sobre las opciones que se usan, familiarícese con los conceptos en [Procedimientos recomendados para la implementación de DMARC en Microsoft 365](#best-practices-for-implementing-dmarc-in-microsoft-365).

Ejemplos:

- Directiva establecida en none

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- Directiva establecida en quarantine

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- Directiva establecida en reject

    ```text
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

Once you have formed your record, you need to update the record at your domain registrar. For instructions on adding the DMARC TXT record to your DNS records for Microsoft 365, see [Create DNS records for Microsoft 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

## <a name="best-practices-for-implementing-dmarc-in-microsoft-365"></a>Procedimientos recomendados para la implementación de DMARC en Microsoft 365

You can implement DMARC gradually without impacting the rest of your mail flow. Create and implement a roll out plan that follows these steps. Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.

1. Supervisar el impacto de implementar DMARC

    Start with a simple monitoring-mode record for a sub-domain or domain that requests that DMARC receivers send you statistics about messages that they see using that domain. A monitoring-mode record is a DMARC TXT record that has its policy set to none (p=none). Many companies publish a DMARC TXT record with p=none because they are unsure about how much email they may lose by publishing a more restrictive DMARC policy.

    You can do this even before you've implemented SPF or DKIM in your messaging infrastructure. However, you won't be able to effectively quarantine or reject mail by using DMARC until you also implement SPF and DKIM. As you introduce SPF and DKIM, the reports generated through DMARC will provide the numbers and sources of messages that pass these checks, and those that don't. You can easily see how much of your legitimate traffic is or isn't covered by them, and troubleshoot any problems. You'll also begin to see how many fraudulent messages are being sent, and from where.

2. Solicitar que los sistemas de correo externos pongan en cuarentena el correo que no supera las comprobaciones de DMARC

    When you believe that all or most of your legitimate traffic is protected by SPF and DKIM, and you understand the impact of implementing DMARC, you can implement a quarantine policy. A quarantine policy is a DMARC TXT record that has its policy set to quarantine (p=quarantine). By doing this, you are asking DMARC receivers to put messages from your domain that fail DMARC into the local equivalent of a spam folder instead of your customers' inboxes.

3. Solicitar que los sistemas de correo externos no aceptan mensajes que no superen las pruebas de DMARC

    The final step is implementing a reject policy. A reject policy is a DMARC TXT record that has its policy set to reject (p=reject). When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.

## <a name="how-microsoft-365-handles-outbound-email-that-fails-dmarc"></a>Cómo controla Microsoft 365 el correo electrónico saliente que no supera las comprobaciones de DMARC

Si un mensaje sale de Microsoft 365 y no supera las comprobaciones de DMARC, y ha establecido la directiva en p=quarantine o p=reject, el mensaje se enruta a través del [Grupo de entrega de alto riesgo para mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md). No hay ninguna invalidación para el correo saliente.

If you publish a DMARC reject policy (p=reject), no other customer in Microsoft 365 can spoof your domain because messages will not be able to pass SPF or DKIM for your domain when relaying a message outbound through the service. However, if you do publish a DMARC reject policy but don't have all of your email authenticated through Microsoft 365, some of it may be marked as spam for inbound email (as described above), or it will be rejected if you do not publish SPF and try to relay it outbound through the service. This happens, for example, if you forget to include some of the IP addresses for servers and apps that send mail on behalf of your domain when you form your DMARC TXT record.

## <a name="how-microsoft-365-handles-inbound-email-that-fails-dmarc"></a>Cómo controla Microsoft 365 el correo electrónico entrante que no supera las comprobaciones de DMARC

Si la directiva DMARC del servidor de envío es`p=reject`, EOP marca el mensaje como correo de suplantación de identidad en lugar de rechazarlo. En otras palabras, para el correo entrante, Microsoft 365 trata a `p=reject` y `p=quarantine` de la misma manera. Los administradores pueden definir la acción que debe realizarse sobre los mensajes clasificados como suplantación de identidad dentro de la [directiva contra la suplantación de identidad](set-up-anti-phishing-policies.md).

Microsoft 365 está configurado así porque algunos mensajes de correo legítimos pueden no superar las comprobaciones de DMARC. Por ejemplo, un mensaje podría no superar las pruebas DMARC si se envía a una lista de distribución que luego transmite el mensaje a todos los participantes de la lista. Si Microsoft 365 rechazara estos mensajes, las personas podrían perder el correo electrónico legítimo y no habría forma de recuperarlo. Es decir, estos mensajes seguirían provocando un error en DMARC, pero se marcarían como correo no deseado y no se rechazarían. Los usuarios que quisieran podrían colocar estos mensajes en la bandeja de entrada a través de estos métodos:

- Los usuarios agregan a los remitentes seguros de manera individual mediante el cliente de correo electrónico

- Los administradores pueden actualizar las notificaciones de [Inteligencia de suplantación de identidad](learn-about-spoof-intelligence.md) para permitir la suplantación de identidad.

- Los administradores crean una regla de flujo de correo (también conocida como regla de transporte) de Exchange para todos los usuarios que permite los mensajes de esos remitentes concretos.

Para obtener más información, consulte [Crear listas de remitentes seguros](create-safe-sender-lists-in-office-365.md).

## <a name="how-microsoft-365-utilizes-authenticated-received-chain-arc"></a>Cómo Microsoft 365 utiliza la cadena de recepción autenticada (ARC)

Todos los buzones hospedados en Microsoft 365 ahora tendrán la ventaja de ARC con una mejor entrega de mensajes y la protección mejorada contra la suplantación de identidad. ARC preserva los resultados de la autenticación de correo electrónico de todos los intermediarios participantes, o saltos, cuando un correo electrónico se enruta desde el servidor de origen hasta el buzón del destinatario. Antes de ARC, las modificaciones realizadas por intermediarios en el enrutamiento del correo electrónico, tales como las reglas de reenvío o las firmas automáticas, podían causar errores de DMARC al momento en que el correo electrónico llegaba al buzón del destinatario. Con ARC, la conservación criptográfica de los resultados de la autenticación permite a Microsoft 365 comprobar la autenticidad del remitente de un correo electrónico.

Actualmente, Microsoft 365 usa ARC para comprobar los resultados de la autenticación cuando Microsoft es el que proporciona el sello ARC, pero tiene previsto proporcionar soporte a terceros que proporcionan el sello ARS en el futuro.

## <a name="troubleshooting-your-dmarc-implementation"></a>Solución de problemas en la implementación de DMARC

Si configuró los registros MX de su dominio donde EOP no es la primera entrada, los errores de DMARC no se aplicarán en su dominio.

Si usted es cliente y el registro MX principal del dominio no apunta a EOP, no obtendrá las ventajas de DMARC. Por ejemplo, DMARC no funcionará si apunta el registro MX al servidor de correo local y luego enruta el correo electrónico a EOP usando un conector. En este escenario, el dominio receptor es uno de los dominios aceptados, pero EOP no es el MX principal. Por ejemplo, si contoso.com apunta su MX a sí mismo y usa EOP como registro MX secundario, el registro MX de contoso.com será así:

```text
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

Todo el correo electrónico o la mayor parte se enrutará primero a mail.contoso.com, ya que es el MX principal, y luego el correo se enrutará a EOP. En algunos casos, ni siquiera podría marcar EOP como registro MX y solo podría enlazar conectores para enrutar el correo electrónico. EOP no tiene por qué ser la primera entrada para que se realice la validación de DMARC. Solo garantiza la validación, ya que no podemos asegurarnos de que todos los servidores locales o que no sean de O365 harán las comprobaciones de DMARC.  Es posible aplicar DMARC a un dominio del cliente (no a un servidor) cuando configura el registro TXT de DMARC, pero el servidor receptor es el que realmente hace la exigencia.  Si configura EOP como servidor de recepción, EOP realiza la exigencia de DMARC.

:::image type="content" source="../../media/Tp_DMARCTroublehoot.png" alt-text="Un gráfico de solución de problemas para DMARC, cortesía de Daniel Mande":::

## <a name="for-more-information"></a>Más información

Want more information about DMARC? These resources can help.

- Los [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md) incluyen la sintaxis y los campos de encabezado que usa Microsoft 365 para efectuar comprobaciones de DMARC.

- Siga la [Serie de aprendizaje de DMARC](https://www.m3aawg.org/activities/training/dmarc-training-series) from M <sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).

- Use la lista de comprobación que verá en [dmarcian](https://space.dmarcian.com/deployment/).

- Vaya directamente al origen en [DMARC.org](https://dmarc.org).

## <a name="see-also"></a>Vea también

[Cómo Microsoft 365 usa el marco de directivas de remitente (SPF) para evitar la suplantación de identidad](how-office-365-uses-spf-to-prevent-spoofing.md)

[Configurar SPF en Microsoft 365 para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

[Usar DKIM para validar el correo electrónico saliente enviado desde el dominio personalizado en Microsoft 365](use-dkim-to-validate-outbound-email.md)
