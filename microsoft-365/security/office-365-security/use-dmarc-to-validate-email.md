---
title: Pasos de configuración para usar DMARC para validar el correo electrónico
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/10/2021
ms.localizationpriority: high
search.appverid:
- MET150
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- m365-security
- m365initiative-defender-office365
description: Obtenga información sobre cómo configurar Domain-based Message Authentication, Reporting, and Conformance (DMARC) para validar mensajes enviados desde la organización.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: f6f460e0a0252f938e351ead0f44e0987fa78359
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68536420"
---
# <a name="use-dmarc-to-validate-email"></a>Usar DMARC para validar el correo electrónico

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

La autenticación, los informes y la conformidad de mensajes basados en dominio ([DMARC](https://dmarc.org)) funcionan con el marco de directivas de remitente (SPF) y DomainKeys Identified Mail (DKIM) para autenticar a los remitentes de correo.

DMARC garantiza que los sistemas de correo electrónico de destino confían en los mensajes enviados desde su dominio. El uso de DMARC con SPF y DKIM ofrece a las organizaciones más protección contra la suplantación de identidad y el correo electrónico de suplantación de identidad. DMARC permite a los sistemas que reciben los correos decidir qué hacer con los mensajes de su dominio que no superan las comprobaciones SPF o DKIM.

> [!TIP]
> Visite el catálogo de la [Asociación de seguridad inteligente de Microsoft (MISA)](https://www.microsoft.com/misapartnercatalog) para ver los proveedores que ofrecen informes DMARC para Microsoft 365.

> [!TIP]
> **¿Has visto nuestras guías paso a paso?** Configuración 1-2-3s y sin lujos, para administradores con prisa. Visite los pasos para *[habilitar DMARC Reporting for Microsoft Online Email Routing Addresses (MOERA) and parked Domains (DmARC Reporting for Microsoft Online Email Routing Addresses (MOERA) and parked Domains (DmARC Reporting for Microsoft Online Email Routing Addresses (MOERA) and parked Domains (DmARC Reporting for Microsoft Online Email Routing Addresses (MO](step-by-step-guides/how-to-enable-dmarc-reporting-for-microsoft-online-email-routing-address-moera-and-parked-domains.md)*

## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-microsoft-365"></a>¿Cómo se coordinan SPF y DMARC para proteger el correo electrónico en Microsoft 365?

 Un mensaje de correo electrónico puede contener varias direcciones de remitentes que se usan para distintos propósitos. Por ejemplo, observe las siguientes direcciones:

- Dirección **"Correo de"**: identifica al remitente e indica dónde enviar notificaciones de devolución si se produce algún problema con la entrega del mensaje (por ejemplo, avisos de no entrega). *Dirección Correo de* aparece en la parte del sobre de un mensaje de correo electrónico y no se muestra en la aplicación de correo electrónico y, a veces, se denomina *dirección 5321.MailFrom* o *dirección de ruta de acceso inversa*.

- **Dirección «De»**: es la dirección que se muestra como dirección De en el cliente de correo de la aplicación. *Dirección De* identifica al autor del correo electrónico. Es decir, el buzón de la persona o el sistema responsables de escribir el mensaje. *Dirección De* también recibe el nombre de *dirección 5322.From*.

SPF usa un registro TXT de DNS para enumerar las direcciones IP de envío autorizadas para un dominio determinado. Normalmente, solo se realizan comprobaciones de SPF en la dirección 5321.MailFrom. La dirección 5322.From no se autentica cuando se usa SPF por sí mismo, lo que permite un escenario en el que un usuario obtiene un mensaje que ha superado las comprobaciones de SPF pero tiene una dirección de remitente 5322.From suplantada. Por ejemplo, veamos esta transcripción de SMTP:

```console
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
S: Please click the following link to verify that Microsoft has the right information for your account.
S:
S: https://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

En esta transcripción, las direcciones del remitente son las siguientes:

- Dirección Correo de (5321.MailFrom): phish@phishing.contoso.com

- Dirección From (5322.From): security@woodgrovebank.com

Si ha configurado SPF, el servidor receptor realiza una comprobación en la dirección Correo de phish@phishing.contoso.com. Si el mensaje procede de un origen válido para el dominio phishing.contoso.com, entonces pasa la comprobación de SPF. Como el cliente de correo electrónico muestra solo la dirección De, el usuario verá que este mensaje procede de security@woodgrovebank.com. Usando solo SPF, la validez de woodgrovebank.com nunca se autentica.

Cuando se usa DMARC, el servidor receptor también realiza una comprobación en la dirección From. En el ejemplo anterior, si no hay un registro TXT de DMARC para woodgrovebank.com, la comprobación de la dirección De produce un error.

## <a name="what-is-a-dmarc-txt-record"></a>¿Qué es un registro TXT de DMARC?

Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing. You publish DMARC TXT records in DNS. DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain. The DMARC TXT record identifies authorized outbound email servers. Destination email systems can then verify that messages they receive originate from authorized outbound email servers.

El registro TXT de DMARC de Microsoft es algo así:

```console
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.contoso.com; ruf=mailto:d@ruf.contoso.com; fo=1"
```

Para ver más proveedores que ofrecen informes DMARC para Microsoft 365, visite el [catálogo de MISA](https://www.microsoft.com/misapartnercatalog?IntegratedProducts=DMARCReportingforOffice365).

## <a name="set-up-dmarc-for-inbound-mail"></a>Configurar DMARC para el correo entrante

No hay que hacer nada para configurar DMARC para el correo que se recibe en Microsoft 365. Ya está todo hecho. Si quiere saber lo que ocurre con el correo que no pasa las comprobaciones de DMARC, vea [Cómo controla Microsoft 365 el correo electrónico entrante que no supera las comprobaciones de DMARC](#how-microsoft-365-handles-inbound-email-that-fails-dmarc).

## <a name="set-up-dmarc-for-outbound-mail-from-microsoft-365"></a>Configurar DMARC para el correo saliente de Microsoft 365

Si usa Microsoft 365 pero no usa un dominio personalizado (usa onmicrosoft.com), SPF ya está configurado para usted y Microsoft 365 genera automáticamente una firma DKIM para su correo saliente (para obtener más información acerca de esta firma, consulte [ Comportamiento predeterminado para DKIM y Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)). Para configurar DMARC para su organización, debe [formar el registro TXT de DMARC](#step-4-form-the-dmarc-txt-record-for-your-domain) para el dominio onmicrosoft.com y publicarlo en DNS a través del Centro de administración de [Office 365](https://admin.microsoft.com) > Configuración > Dominios > haga clic en onmicrosoft.com dominio > Agregar registro.

 Si tiene un dominio personalizado o usa servidores de Exchange locales junto con Microsoft 365, debe configurar manualmente DMARC para el correo saliente. La implementación de DMARC para el dominio personalizado incluye estos pasos:

- [Paso 1: Identificar orígenes válidos de correo para el dominio](#step-1-identify-valid-sources-of-mail-for-your-domain)

- [Paso 2: Configurar SPF para el dominio](#step-2-set-up-spf-for-your-domain)

- [Paso 3: Configurar DKIM para el dominio personalizado](#step-3-set-up-dkim-for-your-custom-domain)

- [Paso 4: Formular el registro TXT de DMARC para el dominio](#step-4-form-the-dmarc-txt-record-for-your-domain)

### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a>Paso 1: Identificar orígenes válidos de correo para el dominio

Si ya ha configurado SPF, ya ha realizado este ejercicio. Hay algunas consideraciones adicionales para DMARC. Al identificar orígenes de correo para su dominio, responda a estas dos preguntas:

- ¿Qué direcciones IP envían mensajes desde mi dominio?

- En los correos electrónicos enviados por parte de terceros en mi nombre, ¿coincidirán los dominios 5321.MailFrom y 5322.From?

### <a name="step-2-set-up-spf-for-your-domain"></a>Paso 2: Configurar SPF para el dominio

Ahora que tiene una lista de todos los remitentes válidos, puede seguir los pasos para [Configurar SPF para evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md).

Por ejemplo, suponiendo que contoso.com envía correos desde Exchange Online, un servidor Exchange local cuya dirección IP fuera 192.168.0.1 y una aplicación web cuya dirección IP fuera 192.168.100.100, el registro TXT de SPF tendría este aspecto:

```console
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

Como práctica recomendada, asegúrese de que el registro TXT de SPF tenga en cuenta a los remitentes externos.

### <a name="step-3-set-up-dkim-for-your-custom-domain"></a>Paso 3: Configurar DKIM para el dominio personalizado

Cuando haya configurado SPF, deberá configurar DKIM. DKIM le permite agregar una firma digital a los mensajes de correo electrónico en el encabezado del mensaje. Si no configura DKIM pero permite a Microsoft 365 usar la configuración predeterminada de DKIM en el dominio, DMARC puede dar errores. Este error puede producirse porque la configuración predeterminada de DKIM usa el dominio de *onmicrosoft.com* original como la dirección *5321.MailFrom*, no el dominio *personalizado*. Esto provoca una discrepancia entre las direcciones *5321.MailFrom* y *5322.From* en todos los correos electrónicos enviados desde su dominio.

If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email. To avoid this, you need to set up DKIM for your domain specifically with that third-party sender. This allows Microsoft 365 to authenticate email from this 3rd-party service. However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you. This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Microsoft 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.

Para ver las instrucciones sobre cómo configurar DKIM para el dominio, incluyendo cómo configurar DKIM para remitentes externos para que puedan suplantar la identidad de su dominio, consulte [Usar DKIM para validar el correo electrónico saliente enviado desde el dominio personalizado](use-dkim-to-validate-outbound-email.md).

### <a name="step-4-form-the-dmarc-txt-record-for-your-domain"></a>Paso 4: Formular el registro TXT de DMARC para el dominio

Aunque existen otras opciones de sintaxis que no se mencionan aquí, estas son las opciones de sintaxis más usadas en Microsoft 365. Formule el registro TXT de DMARC para el dominio con el siguiente formato:

```console
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; p=policy; pct=100"
```

Donde:

- *domain* is the domain you want to protect. By default, the record protects mail from the domain and all subdomains. For example, if you specify \_dmarc.contoso.com, then DMARC protects mail from the domain and all subdomains, such as housewares.contoso.com or plumbing.contoso.com.

- *TTL* should always be the equivalent of one hour. The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.

- *pct=100* indica que esta regla debe usarse para el 100 % del correo electrónico.

- *policy* specifies what policy you want the receiving server to follow if DMARC fails. You can set the policy to none, quarantine, or reject.

Para obtener información sobre las opciones que se usan, familiarícese con los conceptos en [Procedimientos recomendados para la implementación de DMARC en Microsoft 365](#best-practices-for-implementing-dmarc-in-microsoft-365).

Ejemplos:

- Directiva establecida en none

    ```console
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- Directiva establecida en quarantine

    ```console
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- Directiva establecida en reject

    ```console
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

Una vez que formule el registro, debe actualizarlo en el registrador del dominio.

## <a name="dmarc-mail-public-preview-feature"></a>Correo electrónico de DMARC (característica en vista previa pública)

> [!CAUTION]
> Es posible que los correos no se envíen a diario y que el informe en sí cambie durante la versión preliminar pública. Pueden esperarse correos electrónicos del informe agregado DMARC de las cuentas de consumidores (como hotmail.com, outlook.com o live.com).

En este ejemplo de registro TXT de DMARC: `dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1"`, puede ver la dirección *rua*, en este caso, procesada por la empresa Agrari de terceros. Esta dirección se usa para enviar "comentarios agregados" para su análisis y para generar un informe.

> [!TIP]
> Visite el [catálogo de MISA](https://www.microsoft.com/misapartnercatalog) para ver más proveedores de terceros que ofrecen informes DMARC para Microsoft 365. Vea [Domain-based Message Authentication, Reporting, and Conformance (DMARC) de IETF.org](https://datatracker.ietf.org/doc/html/rfc7489) para obtener más información sobre las direcciones "rua" de DMARC.

## <a name="best-practices-for-implementing-dmarc-in-microsoft-365"></a>Procedimientos recomendados para la implementación de DMARC en Microsoft 365

You can implement DMARC gradually without impacting the rest of your mail flow. Create and implement a roll-out plan that follows these steps. Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.

1. Supervisar el impacto de implementar DMARC

    Comience con un registro en modo de supervisión simple para un subdominio o dominio que solicita que los receptores DMARC le envíen estadísticas sobre los mensajes que usan ese dominio. Un registro en modo de supervisión es un registro TXT de DMARC con la directiva establecida en none (p=none). Muchas empresas publican un registro TXT de DMARC con p=none porque no saben cuánto correo electrónico pueden perder al publicar una directiva de DMARC más restrictiva.

    Puede hacer esto incluso antes de implementar SPF o DKIM en la infraestructura de mensajería. Sin embargo, no podrá poner en cuarentena ni rechazar eficazmente el correo mediante DMARC hasta que no implemente también SPF y DKIM. Al introducir SPF y DKIM, los informes generados a través de DMARC proporcionarán los números y orígenes de mensajes que pasan estas comprobaciones, frente a los que no. Se puede ver fácilmente qué cantidad del tráfico legítimo está cubierto o no por ellos, así como solucionar los problemas. También empezará a ver cuántos mensajes fraudulentos se envían y desde dónde se envían.

2. Solicitar que los sistemas de correo externos pongan en cuarentena el correo que no supera las comprobaciones de DMARC

    Cuando cree que todo el tráfico legítimo o la mayor parte está protegido por SPF y DKIM, y sabe cuál es el impacto de implementar DMARC, puede implementar una directiva de cuarentena. Una directiva de cuarentena es un registro TXT de DMARC con una directiva establecida en quarantine (p=quarantine). Al hacer esto, pedimos a los receptores DMARC que pongan los mensajes de su dominio que no superen las pruebas de DMARC en el equivalente local a una carpeta de correo no deseado, en lugar de en las bandejas de entrada de los clientes.

3. Solicitar que los sistemas de correo externos no aceptan mensajes que no superen las pruebas de DMARC

    The final step is implementing a reject policy. A reject policy is a DMARC TXT record that has its policy set to reject (p=reject). When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.

4. ¿Cómo configuro DMARC para un subdominio?

   DMARC se implementa mediante la publicación de una directiva como un registro TXT en DNS y es jerárquica (por ejemplo, una directiva publicada para contoso.com se aplicará a sub.domain.contoso.com a menos que se defina explícitamente una directiva diferente para el subdominio). Esto es útil para que las organizaciones puedan especificar un número más reducido de registros de DMARC de alto nivel para un mayor alcance. Se debe prestar especial atención a la configuración de registros de DMARC de subdominios explícitos en los que no quiera que los subdominios hereden el registro de DMARC del dominio de nivel superior.

   Asimismo, con el valor `sp=reject`, puede agregar una directiva de tipo comodín para DMARC cuando los subdominios no puedan enviar correos electrónicos. Por ejemplo:

   ```text
   _dmarc.contoso.com. TXT "v=DMARC1; p=reject; sp=reject; ruf=mailto:authfail@contoso.com; rua=mailto:aggrep@contoso.com"
   ```

## <a name="how-microsoft-365-handles-outbound-email-that-fails-dmarc"></a>Cómo controla Microsoft 365 el correo electrónico saliente que no supera las comprobaciones de DMARC

Si un mensaje sale de Microsoft 365 y no supera las comprobaciones de DMARC, y ha establecido la directiva en p=quarantine o p=reject, el mensaje se enruta a través del [Grupo de entrega de alto riesgo para mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md). No hay ninguna invalidación para el correo saliente.

Si publica una directiva de rechazo de DMARC (p=reject), ningún otro cliente de Microsoft 365 podrá suplantar la identidad de su dominio porque los mensajes no podrán pasar las comprobaciones de SPF o DKIM para el dominio al retransmitir un mensaje saliente a través del servicio. Sin embargo, si publica una directiva de rechazo de DMARC, pero no dispone de todo el correo electrónico autenticado a través de Microsoft 365, una parte del correo entrante se puede marcar como correo no deseado (como se describe más arriba) o se rechazará si no publica SPF e intenta retransmitirlo para que salga a través del servicio. Esto sucede, por ejemplo, si se olvida de incluir algunas de las direcciones IP para servidores y aplicaciones que envían correo en nombre de su dominio al formular el registro TXT de DMARC.

## <a name="how-microsoft-365-handles-inbound-email-that-fails-dmarc"></a>Cómo controla Microsoft 365 el correo electrónico entrante que no supera las comprobaciones de DMARC

Si la directiva DMARC del servidor de envío es `p=reject`, [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) marca el mensaje como correo de suplantación de identidad en lugar de rechazarlo. En otras palabras, para el correo entrante, Microsoft 365 trata a `p=reject` y `p=quarantine` de la misma manera. Los administradores pueden definir la acción que debe realizarse sobre los mensajes clasificados como suplantación de identidad dentro de la [directiva contra la suplantación de identidad](set-up-anti-phishing-policies.md).

Microsoft 365 está configurado así porque algunos mensajes de correo legítimos pueden no superar las comprobaciones de DMARC. Por ejemplo, un mensaje podría no superar las pruebas DMARC si se envía a una lista de distribución que luego transmite el mensaje a todos los participantes de la lista. Si Microsoft 365 rechazara estos mensajes, las personas podrían perder el correo electrónico legítimo y no habría forma de recuperarlo. Es decir, estos mensajes seguirían provocando un error en DMARC, pero se marcarían como correo no deseado y no se rechazarían. Los usuarios que quisieran podrían colocar estos mensajes en la bandeja de entrada a través de estos métodos:

- Los usuarios agregan a los remitentes seguros de manera individual mediante el cliente de correo electrónico

- Los administradores pueden usar la [Información de la inteligencia contra la suplantación de identidad](learn-about-spoof-intelligence.md) o la [Lista de bloqueados y permitidos de espacio empresarial](manage-tenant-allow-block-list.md) para permitir los mensajes del remitente al que le han suplantado la identidad.

- Los administradores crean una regla de flujo de correo (también conocida como regla de transporte) de Exchange para todos los usuarios que permite los mensajes de esos remitentes concretos.

Para obtener más información, consulte [Crear listas de remitentes seguros](create-safe-sender-lists-in-office-365.md).

## <a name="how-microsoft-365-utilizes-authenticated-received-chain-arc"></a>Cómo Microsoft 365 utiliza la cadena de recepción autenticada (ARC)

Todos los buzones hospedados en Microsoft 365 ahora tendrán la ventaja de ARC con una mejor entrega de mensajes y la protección mejorada contra la suplantación de identidad. ARC preserva los resultados de la autenticación de correo electrónico de todos los intermediarios participantes, o saltos, cuando un correo electrónico se enruta desde el servidor de origen hasta el buzón del destinatario. Antes de ARC, las modificaciones realizadas por intermediarios en el enrutamiento del correo electrónico, tales como las reglas de reenvío o las firmas automáticas, podían causar errores de DMARC al momento en que el correo electrónico llegaba al buzón del destinatario. Con ARC, la conservación criptográfica de los resultados de la autenticación permite a Microsoft 365 comprobar la autenticidad del remitente de un correo electrónico.

Actualmente, Microsoft 365 usa ARC para comprobar los resultados de la autenticación cuando Microsoft es el que proporciona el sello ARC, pero, en el futuro, tiene previsto proporcionar soporte a terceros que proporcionan el sello ARS.

## <a name="troubleshooting-your-dmarc-implementation"></a>Solución de problemas en la implementación de DMARC

Si ha configurado los registros MX de su dominio donde EOP no es la primera entrada, los errores de DMARC no se aplicarán en su dominio.

Si usted es cliente y el registro MX principal del dominio no apunta a EOP, no obtendrá las ventajas de DMARC. Por ejemplo, DMARC no funcionará si apunta el registro MX al servidor de correo local y luego enruta el correo electrónico a EOP usando un conector. En este escenario, el dominio receptor es uno de los dominios aceptados, pero EOP no es el MX principal. Por ejemplo, si contoso.com apunta su MX a sí mismo y usa EOP como registro MX secundario, el registro MX de contoso.com será así:

```console
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

Todo el correo electrónico o la mayor parte se enrutará primero a mail.contoso.com, ya que es el MX principal, y luego el correo se enrutará a EOP. En algunos casos, ni siquiera podría marcar EOP como registro MX y solo podría enlazar conectores para enrutar el correo electrónico. EOP no tiene por qué ser la primera entrada para que se realice la validación de DMARC. Solo garantiza la validación para asegurarse de que todos los servidores locales o que no sean de O365 realizarán comprobaciones DMARC.  Es posible aplicar DMARC a un dominio del cliente (no a un servidor) cuando configura el registro TXT de DMARC, pero el servidor receptor es el que realmente hace la exigencia.  Si configura EOP como servidor de recepción, EOP realiza la exigencia de DMARC.

:::image type="content" source="../../media/Tp_DMARCTroublehoot.png" alt-text="Gráfico de solución de problemas de DMARC" lightbox="../../media/Tp_DMARCTroublehoot.png":::

## <a name="for-more-information"></a>Más información

Want more information about DMARC? These resources can help.

- Los [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md) incluyen la sintaxis y los campos de encabezado que usa Microsoft 365 para efectuar comprobaciones de DMARC.

- Siga la [Serie de aprendizaje de DMARC](https://www.m3aawg.org/activities/training/dmarc-training-series) de M<sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).

- Use la lista de comprobación que verá en [dmarcian](https://space.dmarcian.com/deployment/).

- Vaya directamente al origen en [DMARC.org](https://dmarc.org).

## <a name="see-also"></a>Vea también

[Cómo Microsoft 365 usa el marco de directivas de remitente (SPF) para evitar la suplantación de identidad](how-office-365-uses-spf-to-prevent-spoofing.md)

[**Configurar SPF en Microsoft 365 para ayudar a evitar la suplantación de identidad**](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

[**Usar DKIM para validar el correo electrónico saliente enviado desde el dominio personalizado en Microsoft 365**](use-dkim-to-validate-outbound-email.md)

[Use remitentes ARC de confianza para los flujos de correo legítimos](/microsoft-365/security/office-365-security/use-arc-exceptions-to-mark-trusted-arc-senders?view=o365-21vianet&preserve-view=true)
