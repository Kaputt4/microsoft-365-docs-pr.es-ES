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
- m365initiative-defender-office365
description: Obtenga información sobre cómo configurar Domain-based Message Authentication, Reporting, and Conformance (DMARC) para validar mensajes enviados desde la organización.
ms.openlocfilehash: 9dd97b1fc60f0b6198bb6c55af291c7dd103ac5d
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615341"
---
# <a name="use-dmarc-to-validate-email"></a>Usar DMARC para validar el correo electrónico

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Domain-based Message Authentication, Reporting, and Conformance ([DMARC](https://dmarc.org)) trabaja con el marco de directivas de remitente (SPF) y DomainKeys Identified Mail (DKIM) para autenticar a los remitentes de los correos y garantizar que los sistemas de correo electrónico de destino confíen en los mensajes enviados desde su dominio. Implementar DMARC con SPF y DKIM ofrece protección adicional contra el correo electrónico de suplantación de identidad. DMARC permite a los sistemas que reciben los correos determinar qué hacer con los mensajes enviados desde su dominio que no superan las comprobaciones SPF o DKIM.

> [!TIP]
> Visite el catálogo de la [Asociación de seguridad inteligente de Microsoft (MISA)](https://www.microsoft.com/misapartnercatalog) para ver los proveedores que ofrecen informes DMARC para Microsoft 365.

## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-microsoft-365"></a>¿Cómo se coordinan SPF y DMARC para proteger el correo electrónico en Microsoft 365?

 Un mensaje de correo electrónico puede contener varias direcciones de remitentes, que se usan para distintos propósitos. Por ejemplo, observe las siguientes direcciones:

- **Dirección "Correo de"**: identifica al remitente y especifica dónde se deben enviar los avisos de devolución si se produce algún problema al entregar el mensaje (por ejemplo, un aviso de no entrega). Aparece en la zona del sobre de un mensaje de correo electrónico, aunque su aplicación de correo electrónico no suele mostrarla. A veces, recibe la denominación dirección 5321.MailFrom o dirección de ruta de acceso inversa.

- **Dirección «De»**: es la dirección que se muestra como dirección De en el cliente de correo de la aplicación. Esta dirección identifica al autor del correo electrónico. Es decir, el buzón de la persona o el sistema responsables de escribir el mensaje. A veces, recibe la denominación dirección 5322.From.

SPF usa un registro TXT de DNS para proporcionar una lista de direcciones IP de envío autorizadas en un dominio dado. Normalmente, solo se realizan comprobaciones de SPF en la dirección 5321.MailFrom. Esto significa que la dirección de 5322.From no se autentica al usar solamente SPF. Esto habilita un escenario donde un usuario puede recibir un mensaje que pasa una comprobación de SPF, pero tiene una dirección de remitente 5322.From falsificada. Por ejemplo, veamos esta transcripción de SMTP:

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

Si configuró SPF, el servidor receptor realiza una comprobación en la dirección MailFrom phish@phishing.contoso.com. Si el mensaje procede de un origen válido para el dominio phishing.contoso.com, entonces pasa la comprobación de SPF. Como el cliente de correo electrónico muestra solo la dirección From, el usuario verá que este mensaje procede de security@woodgrovebank.com. Usando solo SPF, la validez de woodgrovebank.com nunca se autentica.

Cuando se usa DMARC, el servidor receptor también realiza una comprobación en la dirección From. En el ejemplo anterior, si no hay un registro TXT de DMARC para woodgrovebank.com, la comprobación de la dirección From da error.

## <a name="what-is-a-dmarc-txt-record"></a>¿Qué es un registro TXT de DMARC?

Al igual que los registros DNS para SPF, el registro para DMARC es un registro de texto (TXT) de DNS que ayuda a evitar la suplantación de identidad. Los registros TXT de DMARC se publican en DNS. Los registros TXT de DMARC validan el origen de los mensajes de correo electrónico contrastando la dirección IP del autor de un correo electrónico con el supuesto propietario del dominio de envío. El registro TXT de DMARC identifica los servidores de correo electrónico saliente autorizados. Así, los sistemas de correo electrónico de destino comprueban que los mensajes que reciben proceden de servidores de correo electrónico saliente autorizados.

El registro TXT de DMARC de Microsoft es algo así:

```console
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1"
```

Microsoft envía sus informes DMARC a [Agari](https://agari.com), un tercero. Agari recoge y analiza los informes de la DMARC. Visite el [catálogo de MISA](https://www.microsoft.com/misapartnercatalog) para ver más proveedores que ofrecen informes DMARC para Microsoft 365.

## <a name="implement-dmarc-for-inbound-mail"></a>Implementar DMARC para el correo entrante

No hay que hacer nada para configurar DMARC para el correo que se recibe en Microsoft 365. Nosotros nos hemos encargado de todo. Si quiere saber lo que ocurre con el correo que no pasa las comprobaciones de DMARC, consulte [Cómo gestiona Microsoft 365 el correo electrónico entrante que genera errores DMARC](#how-microsoft-365-handles-inbound-email-that-fails-dmarc).

## <a name="implement-dmarc-for-outbound-mail-from-microsoft-365"></a>Implementar DMARC para el correo saliente de Microsoft 365

Si usa Microsoft 365, pero no está usando un dominio personalizado (sino el dominio onmicrosoft.com), solo tiene que configurar o implementar DMARC para la organización. SPF ya está configurado y Microsoft 365 genera automáticamente una firma DKIM para el correo saliente. Para más información sobre esta firma, consulte [Comportamiento predeterminado para DKIM y Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).

 Si tiene un dominio personalizado o usa servidores de Exchange locales aparte de Microsoft 365, implemente manualmente DMARC para el correo saliente. La implementación de DMARC para el dominio personalizado incluye estos pasos:

- [Paso 1: Identificar orígenes válidos de correo para el dominio](#step-1-identify-valid-sources-of-mail-for-your-domain)

- [Paso 2: Configurar SPF para el dominio](#step-2-set-up-spf-for-your-domain)

- [Paso 3: Configurar DKIM para el dominio personalizado](#step-3-set-up-dkim-for-your-custom-domain)

- [Paso 4: Formular el registro TXT de DMARC para el dominio](#step-4-form-the-dmarc-txt-record-for-your-domain)

### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a>Paso 1: Identificar orígenes válidos de correo para el dominio

Si tiene configurado SPF, quiere decir que ya ha hecho este paso. Sin embargo, para DMARC, hay que tener en cuenta otras cosas. Al identificar los orígenes de correo para el dominio, debemos responder a dos preguntas:

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

Cuando haya configurado SPF, deberá configurar DKIM. DKIM le permite agregar una firma digital en el encabezado de los mensajes de correo electrónico. Si no configura DKIM pero permite a Microsoft 365 usar la configuración predeterminada de DKIM para el dominio, DMARC puede dar errores. Esto se debe a que la configuración predeterminada de DKIM usa el dominio onmicrosoft.com inicial como dirección 5322.From, es decir, no usa el dominio personalizado. Esto provoca una discrepancia entre las direcciones 5321.MailFrom y 5322.From en todos los correos electrónicos enviados desde su dominio.

Si hay remitentes externos que envían correo en su nombre y el correo que envían tiene direcciones 5321.MailFrom y 5322.From que no coinciden, se producirá un error de DMARC para ese correo electrónico. Para evitar esto, tendrá que configurar DKIM para el dominio específicamente con ese remitente externo. Esto permite a Microsoft 365 autenticar el correo electrónico desde el servicio externo. Sin embargo, también permite a otros usuarios, por ejemplo, Yahoo, Gmail y Comcast, comprobar la validez del correo electrónico enviado por terceros como si lo hubiera enviado usted. Esto es beneficioso porque permite a los clientes generar relaciones de confianza con el dominio independientemente del sitio donde se encuentre su buzón y, al mismo tiempo, Microsoft 365 no marcará un mensaje como correo no deseado por suplantación de identidad, ya que pasa las comprobaciones de autenticación para el dominio.

Para ver las instrucciones sobre cómo configurar DKIM para el dominio, incluyendo cómo configurar DKIM para remitentes externos para que puedan suplantar la identidad de su dominio, consulte [Usar DKIM para validar el correo electrónico saliente enviado desde el dominio personalizado](use-dkim-to-validate-outbound-email.md).

### <a name="step-4-form-the-dmarc-txt-record-for-your-domain"></a>Paso 4: Formular el registro TXT de DMARC para el dominio

Aunque existen otras opciones de sintaxis que no se mencionan aquí, estas son las opciones más usadas en Microsoft 365. Formule el registro TXT de DMARC para el dominio con el siguiente formato:

```console
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; p=policy; pct=100"
```

donde:

- *domain* es el dominio que quiere proteger. De forma predeterminada, el registro protege el correo del dominio y todos los subdominios. Por ejemplo, si especifica \_dmarc.contoso.com, DMARC protege correo del dominio y todos los subdominios, como housewares.contoso.com o plumbing.contoso.com.

- *TTL* siempre debe ser el equivalente a una hora. La unidad usada para el TTL, ya sean las horas (1 hora), los minutos (60 minutos) o los segundos (3600 segundos), variará en función del registrador del dominio.

- *pct=100* indica que esta regla debe usarse para el 100 % del correo electrónico.

- *policy* especifica qué directiva quiere que el servidor de recepción siga si se produce un error en DMARC. Puede establecer la directiva en none, quarantine o reject.

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

Una vez que haya formulado el registro, debe actualizarlo en el registrador del dominios. Para obtener instrucciones sobre cómo agregar el registro TXT de DMARC a los registros DNS para Microsoft 365, consulte [Crear registros DNS para Microsoft 365 al administrar los registros DNS](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

## <a name="best-practices-for-implementing-dmarc-in-microsoft-365"></a>Procedimientos recomendados para la implementación de DMARC en Microsoft 365

DMARC se puede implementar gradualmente sin que esto afecte al resto del flujo de correo. Cree e implemente un plan de distribución con estos pasos de implementación. Realice cada uno de estos pasos primero con un subdominio, luego con otros subdominios y, finalmente, con el dominio de nivel superior de la organización antes de continuar con el paso siguiente.

1. Supervisar el impacto de implementar DMARC

    Comience con un registro en modo de supervisión simple para un subdominio o dominio que solicita que los receptores DMARC le envíen estadísticas sobre los mensajes que usan ese dominio. Un registro en modo de supervisión es un registro TXT de DMARC con la directiva establecida en none (p=none). Muchas empresas publican un registro TXT de DMARC con p=none porque no saben cuánto correo electrónico se pueden perder al publicar una directiva de DMARC más restrictiva.

    Puede hacer esto incluso antes de implementar SPF o DKIM en la infraestructura de mensajería. Sin embargo, no podrá poner en cuarentena ni rechazar eficazmente el correo mediante DMARC hasta que no implemente también SPF y DKIM. Al introducir SPF y DKIM, los informes generados mediante DMARC indicarán los números y los orígenes de los mensajes que pasen estas comprobaciones y los que no. Se puede ver fácilmente qué cantidad del tráfico legítimo está cubierto o no por ellos, así como solucionar los problemas. También empezará a ver cuántos mensajes fraudulentos se envían y desde dónde.

2. Solicitar que los sistemas de correo externos pongan en cuarentena el correo que no supera las comprobaciones de DMARC

    Cuando cree que todo el tráfico legítimo o la mayor parte está protegido por SPF y DKIM, y sabe cuál es el impacto de implementar DMARC, puede implementar una directiva de cuarentena. Una directiva de cuarentena es un registro TXT de DMARC con una directiva establecida en quarantine (p=quarantine). Al hacer esto, pedimos a los receptores DMARC que pongan los mensajes de su dominio que no superen las pruebas de DMARC en el equivalente local a una carpeta de correo no deseado, en lugar de en las bandejas de entrada de los clientes.

3. Solicitar que los sistemas de correo externos no aceptan mensajes que no superen las pruebas de DMARC

    El último paso es implementar una directiva de rechazo. Una directiva de rechazo es un registro TXT de DMARC con una directiva establecida en reject (p=reject). Al hacerlo, pedimos a los receptores DMARC que no acepten los mensajes que no pasan las comprobaciones de DMARC.

4. ¿Cómo configuro DMARC para un subdominio?

DMARC se implementa al publicar una directiva como un registro TXT en DNS y es jerárquico (por ejemplo, una directiva publicada para contoso.com se aplicará a sub.domain.contoso.com a menos que se defina explícitamente una directiva diferente para el subdominio). Esto es útil para que las organizaciones puedan especificar un número más reducido de registros de DMARC de alto nivel para mayor alcance. Se debe prestar especial atención a la configuración de registros de DMARC de subdominios explícitos en los que no quiere que los subdominios hereden el registro de DMARC del dominio de nivel superior.

Asimismo, con el valor `sp=reject`, puede agregar una directiva de tipo comodín para DMARC cuando los subdominios no puedan enviar correos electrónicos. Por ejemplo:

```console
_dmarc.contoso.com. TXT "v=DMARC1; p=reject; sp=reject; ruf=mailto:authfail@contoso.com; rua=mailto:aggrep@contoso.com"
```

## <a name="how-microsoft-365-handles-outbound-email-that-fails-dmarc"></a>Cómo controla Microsoft 365 el correo electrónico saliente que no supera las comprobaciones de DMARC

Si un mensaje sale de Microsoft 365 y no supera las comprobaciones de DMARC, y ha establecido la directiva en p=quarantine o p=reject, el mensaje se enruta a través del [Grupo de entrega de alto riesgo para mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md). No hay ninguna invalidación para el correo saliente.

Si publica una directiva de rechazo de DMARC (p=reject), ningún otro cliente de Office 365 podrá suplantar la identidad del dominio porque los mensajes no podrán pasar las comprobaciones de SPF o DKIM para el dominio al retransmitir un mensaje saliente a través del servicio. Sin embargo, si publica una directiva de rechazo de DMARC, pero no dispone de todo el correo electrónico autenticado a través de Microsoft 365, una parte del correo entrante puede ser marcado como correo no deseado (como se describió anteriormente) o se rechazará si no publica SPF e intenta retransmitirlo para que salga a través del servicio. Esto sucede, por ejemplo, si se olvida de incluir algunas de las direcciones IP para servidores y aplicaciones que envían correo en nombre de su dominio al formular el registro TXT de DMARC.

## <a name="how-microsoft-365-handles-inbound-email-that-fails-dmarc"></a>Cómo controla Microsoft 365 el correo electrónico entrante que no supera las comprobaciones de DMARC

Si la directiva DMARC del servidor de envío es `p=reject`, [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) marca el mensaje como correo de suplantación de identidad en lugar de rechazarlo. En otras palabras, para el correo entrante, Microsoft 365 trata a `p=reject` y `p=quarantine` de la misma manera. Los administradores pueden definir la acción que debe realizarse sobre los mensajes clasificados como suplantación de identidad dentro de la [directiva contra la suplantación de identidad](set-up-anti-phishing-policies.md).

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

```console
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

Todo el correo electrónico o la mayor parte se enrutará primero a mail.contoso.com, ya que es el MX principal, y luego el correo se enrutará a EOP. En algunos casos, ni siquiera podría marcar EOP como registro MX y solo podría enlazar conectores para enrutar el correo electrónico. EOP no tiene por qué ser la primera entrada para que se realice la validación de DMARC. Solo garantiza la validación, ya que no podemos asegurarnos de que todos los servidores locales o que no sean de O365 harán las comprobaciones de DMARC.  Es posible aplicar DMARC a un dominio del cliente (no a un servidor) cuando configura el registro TXT de DMARC, pero el servidor receptor es el que realmente hace la exigencia.  Si configura EOP como servidor de recepción, EOP realiza la exigencia de DMARC.

![Un gráfico de solución de problemas para DMARC, cortesía de Daniel Mande](../../media/Tp_DMARCTroublehoot.png)

## <a name="for-more-information"></a>Más información

¿Quiere más información sobre DMARC? Estos recursos lo pueden ayudar.

- Los [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md) incluyen la sintaxis y los campos de encabezado que usa Microsoft 365 para efectuar comprobaciones de DMARC.

- Siga la [Serie de aprendizaje de DMARC](https://www.m3aawg.org/activities/training/dmarc-training-series) de M<sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).

- Use la lista de comprobación que verá en [dmarcian](https://space.dmarcian.com/deployment/).

- Vaya directamente al origen en [DMARC.org](https://dmarc.org).

## <a name="see-also"></a>Vea también

[Cómo Microsoft 365 usa el marco de directivas de remitente (SPF) para evitar la suplantación de identidad](how-office-365-uses-spf-to-prevent-spoofing.md)

[Configurar SPF en Microsoft 365 para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

[Usar DKIM para validar el correo electrónico saliente enviado desde el dominio personalizado en Microsoft 365](use-dkim-to-validate-outbound-email.md)
