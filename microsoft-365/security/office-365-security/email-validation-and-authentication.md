---
title: Autenticación de correo electrónico en Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Los administradores pueden obtener información sobre cómo EOP usa la autenticación de correo electrónico (SPF, DKIM y DMARC) para ayudar a evitar la suplantación de identidad, el phishing y el correo no deseado.
ms.openlocfilehash: 7c196b68d88187da2890cc886f646c5416ef9a11
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131078"
---
# <a name="email-authentication-in-eop"></a>Autenticación de correo electrónico en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


La autenticación de correo electrónico (conocida también como validación de correo electrónico) es un grupo de normas que intentan detener la suplantación (mensajes de correo electrónico de remitentes falsos). En todas las organizaciones de Microsoft 365, EOP usa estos estándares para comprobar el correo electrónico entrante:

- [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

- [DKIM](use-dkim-to-validate-outbound-email.md)

- [DMARC](use-dmarc-to-validate-email.md)

La autenticación de correo electrónico comprueba que los mensajes de correo electrónico de un remitente (por ejemplo, laura@contoso.com) son legítimos y provienen de fuentes previstas para ese dominio de correo electrónico (por ejemplo, contoso.com).

En el resto de este artículo, se explica cómo funcionan estas tecnologías y cómo EOP las usa para comprobar el correo electrónico entrante.

## <a name="use-email-authentication-to-help-prevent-spoofing"></a>Uso de la autenticación de correo electrónico para ayudar a evitar la suplantación de identidad

DMARC impide la suplantación electrónica mediante el examen de la dirección **De** en mensajes. La dirección **De** es la dirección de correo electrónico del remitente que verán los usuarios en su cliente de correo electrónico. Las organizaciones de correo electrónico de destino también pueden comprobar que el dominio de correo electrónico ha pasado SPF o DKIM. Es decir, el dominio se ha autenticado y, por tanto, la dirección de correo del remitente no está suplantada.

Sin embargo, los registros DNS para SPF, DKIM y DMARC (denominados directivas de autenticación de correo electrónico) son opcionales. Los dominios con directivas de autenticación de correo electrónico seguras como microsoft.com y skype.com están protegidos frente a la suplantación electrónica.  Sin embargo, los dominios con directivas de autenticación de correo electrónico más débiles, o sin directivas, son los principales objetivos para la suplantación.

En marzo de 2018, sólo un 9 % de los dominios de las empresas en la Fortune 500 publicaron directivas de autenticación de correo electrónico seguras. Un atacante podría suplantar electrónicamente al 91 % restante de empresas. A no ser que haya otro mecanismo de filtrado de correo electrónico en contexto, el correo electrónico de los remitentes falsos de estos dominios podría entregarse a los usuarios.

![Directivas DMARC de las empresas en Fortune 500](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

La proporción de pequeñas y medianas empresas que publican directivas de autenticación de correo electrónico seguras es menor. Y el número es aún más pequeño para los dominios de correo electrónico fuera de Norteamérica y Europa occidental.

La falta de directivas de autenticación de correo electrónico seguras es un gran problema. Aunque es posible que las organizaciones no sepan cómo funciona la autenticación de correo electrónico, los atacantes si lo saben y se aprovechan de ello. Debido a preocupaciones con respecto al phishing y a una adopción de directivas de autenticación de correo electrónico seguras tan limitada, Microsoft usa *autenticación de correo electrónico implícita* para comprobar el correo electrónico entrante.

La autenticación de correo electrónico implícita es una extensión de las directivas de autenticación de correo electrónico habituales. Entre estas extensiones se incluyen: la reputación del remitente, el historial del remitente, el historial del destinatario, el análisis de comportamiento y otras técnicas avanzadas. En ausencia de otras señales de estas extensiones, los mensajes enviados desde dominios que no usan directivas de autenticación de correo electrónico se marcarán como suplantación electrónica.

Para ver el anuncio general de Microsoft, vea [Un mar de phishing, parte 2: Protección contra la suplantación de identidad mejorada en Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).

## <a name="composite-authentication"></a>Autenticación compuesta

Si un dominio no tiene registros de SPF, DKIM y DMARC tradicionales, esas comprobaciones de registro no comunican suficiente información de estado de autenticación. Por lo tanto, Microsoft ha desarrollado un algoritmo para la autenticación de correo electrónico implícita. Este algoritmo combina varias señales en un único valor denominado _autenticación compuesta_ (`compauth` para abreviar). El valor de `compauth` se marca en el encabezado **Authentication-Results** en los encabezados de mensaje.

```text
Authentication-Results:
   compauth=<fail | pass | softpass | none> reason=<yyy>
```

Estos valores se explican en [Encabezado de mensaje Authentication-results](anti-spam-message-headers.md#authentication-results-message-header).

Al examinar los encabezados de mensajes, los administradores o incluso los usuarios finales podrán determinar cómo Microsoft 365 determinó que el remitente está falsificado.

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>Por qué la autenticación de correo electrónico no siempre es suficiente para detener la suplantación de identidad

Depender solo de los registros de autenticación de correo electrónico para determinar si un mensaje entrante está falsificado tiene las siguientes limitaciones:

- Es posible que el dominio remitente carezca de los registros DNS necesarios o que los registros no estén configurados correctamente.

- El dominio de origen ha configurado correctamente los registros DNS, pero ese dominio no coincide con el dominio de la dirección De. SPF y DKIM no requieren que el dominio se use en la dirección De. Los intrusos y los servicios legítimos pueden registrar un dominio, configurar SPF y DKIM para el dominio, y usar un dominio completamente distinto en la dirección De. Los mensajes de los remitentes de este dominio pasarán SPF y DKIM.

Las autenticaciones compuestas pueden superar estas limitaciones pasando mensajes que, de otra forma, no superarían las comprobaciones de autenticación de correo electrónico.

Para simplificar, los ejemplos siguientes se centran en los resultados de la autenticación de correo electrónico. Otros factores de inteligencia de back-end podrían identificar mensajes que pasan la autenticación de correo electrónico como suplantados o mensajes que la pasan como legítimos.

Por ejemplo, el dominio fabrikam.com no tiene registros SPF, DKIM o DMARC. Los mensajes de los remitentes del dominio fabrikam.com pueden producir un error en la autenticación compuesta (tenga en cuenta que el valor  y razón de `compauth`):

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

Si fabrikam.com configura un SPF sin un registro DKIM, este mensaje no produciría un error de autenticación compuesta. El dominio que ha pasado comprobaciones de SPF está alineado con el dominio de la dirección De:

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

Si fabrikam.com configura un registro DKIM sin un registro SPF, este mensaje no produciría un error de autenticación compuesta. El dominio de la firma DKIM está alineado con el dominio de la dirección De:

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

Si el dominio en SPF o la firma DKIM no están alineados con el dominio de la dirección De, el mensaje puede producir un error de autenticación compuesta:

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a>Soluciones para remitentes legítimos que envían correo electrónico sin autenticar

Microsoft 365 realiza un seguimiento de quién está enviando correo sin autenticar en su organización. Si el servicio considera que el remitente no es legítimo, marcará los mensajes de este remitente como error de autenticación compuesta. Para evitar este veredicto, puede usar las recomendaciones de esta sección.

### <a name="configure-email-authentication-for-domains-you-own"></a>Configuración de la autenticación de correo electrónico para los dominios de su propiedad

Puede usar este método para resolver la suplantación de identidad dentro de la organización y entre dominios en caso de que es propietario o interactúa con varios espacios empresariales. También le ayuda a resolver la suplantación entre dominios donde envía a otros clientes de Microsoft 365 o servicios de terceros hospedados por otros proveedores.

- [Configure los registros de SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) para sus dominios.

- [Configure los registros de DKIM](use-dkim-to-validate-outbound-email.md) para sus dominios principales.

- [Puede configurar los registros DMARC](use-dmarc-to-validate-email.md) para su dominio para determinar la lista de remitentes legítimos.

Microsoft no proporciona instrucciones detalladas de implementación para los registros SPF, DKIM y DMARC. Sin embargo, hay una gran cantidad de información disponible en línea. También hay compañías de terceros dedicadas a ayudar a su organización a configurar los registros de autenticación de correo electrónico.

#### <a name="you-dont-know-all-sources-for-your-email"></a>No conoce todas las fuentes del correo electrónico

Muchos dominios no publican registros de SPF porque no conocen todos los orígenes de correo electrónico de los mensajes de su dominio. Debe empezar publicando un registro SPF que contenga las fuentes de correo que conoce, especialmente donde se encuentra el tráfico corporativo y publicar una directiva de SPF neutra, `?all`: Por ejemplo:

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

Este ejemplo significa que el correo electrónico de su infraestructura corporativa pasará la autenticación de correo electrónico, pero el correo electrónico procedente de fuentes desconocidas se revertirá a neutra.

Microsoft 365 considerará el correo electrónico entrante de su infraestructura corporativa como autenticado. El correo electrónico procedente de orígenes no identificados podría seguir marcándose como suplantación electrónica si falla la autenticación implícita. Pero, sigue siendo una mejora a que Microsoft 365 marque todo el correo electrónico como suplantación de identidad.

Una vez que haya empezado con una directiva de reserva SPF de `?all`, puede descubrir e incluir más orígenes de correo electrónico para los mensajes de forma gradual y, después, actualizar el registro SPF con una directiva más estricta.

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a>Uso de la inteligencia de suplantación de identidad para configurar los remitentes permitidos de correo electrónico sin autenticar

También puede usar la [inteligencia de suplantación de identidad](learn-about-spoof-intelligence.md) para que los remitentes puedan enviar correos electrónicos sin autenticar a su organización.

En el caso de los dominios externos, el usuario falso es el dominio de la dirección De, mientras que la infraestructura de envío es la dirección IP de origen (dividida en /24 rangos CIDR) o el dominio de la organización del registro de DNS (PTR) invertido.

En la siguiente captura de pantalla, la dirección IP de origen podría ser 131.107.18.4 con el registro PTR outbound.mail.protection.outlook.com. Esto se mostraría como outlook.com para la infraestructura de envío.

Para permitir que este remitente envíe correos electrónicos sin autenticar, cambie de **No** a **Sí**.

![Configurar remitentes permitidos en la protección contra la suplantación ](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a>Creación de una entrada de permiso para el par de remitente y destinatario

Para omitir el filtrado de correo no deseado, algunas partes del filtrado de phishing, pero no el filtrado de malware de remitentes específicos, consulte [Creación de listas de remitentes seguros en Microsoft 365](create-safe-sender-lists-in-office-365.md).

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a>Solicitar al remitente que configure de la autenticación de correo electrónico para los dominios que no son de su propiedad

Por el problema del correo no deseado y la suplantación de identidad, Microsoft recomienda la autenticación de correo electrónico para todas las organizaciones de correo electrónico. En lugar de configurar anulaciones manuales en la organización, puede solicitar a un administrador del dominio remitente que configure los registros de autenticación de correo electrónico.

- Aunque no tuviesen necesidad de publicar registros de autenticación de correo electrónico en el pasado, deben hacerlo si envían correo electrónico a Microsoft.

- Configure SPF para publicar direcciones IP de envío y configurar DKIM (si disponible) para firmar digitalmente los mensajes. También deberían considerar al configuración de los registros DMARC.

- Si usan remitentes en masa para enviar mensajes de correo electrónico en su nombre, compruebe que el dominio de la dirección De (si les pertenece) se alinee con el dominio que supera el SPF o el DMARC.

- Compruebe que las siguientes ubicaciones (si las usan) se incluyen en el registro de SPF:

  - Servidores de correo electrónico locales.
  - Correo electrónico enviado desde un proveedor de software como servicio (SaaS).
  - Correo electrónico enviado desde un servicio de hospedaje en la nube (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, etc.).

- Para los dominios pequeños alojados en un ISP, configure el registro de SPF según las instrucciones del ISP.

Aunque puede ser difícil empezar a enviar dominios para la autenticación, con el tiempo, como más filtros de correo electrónico comienzan a eliminar o incluso rechazan su correo electrónico, deberán configurar los registros adecuados para garantizar una mejor entrega. Asimismo, la participación puede ayudar a luchar contra la suplantación de identidad, y puede reducir la posibilidad de que se produzca suplantación de identidad en la organización u organizaciones a las que envíen correo.

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a>Información para proveedores de infraestructura (ISP, ESP o servicios de hospedaje en la nube)

Si hospeda un correo electrónico de un dominio o si proporciona una infraestructura de hospedaje que puede enviar correo electrónico, haga lo siguiente:

- Asegúrese de que los clientes tienen documentación en la que se explica cómo deben configurar sus registros de SPF.

- Considere añadir firmas DKIM en el correo electrónico saliente, incluso si el cliente no lo configura explícitamente (firma con un dominio predeterminado). Puede incluso añadir dos firmas DKIM en el correo electrónico (una con el dominio del cliente, si lo ha configurado, y otra con la firma DKIM de su empresa)

No se garantiza la capacidad de entrega a Microsoft aunque se autentique el correo electrónico que proviene de su plataforma, pero al menos se garantiza que Microsoft no marque el correo electrónico como no deseado por no estar autenticado.

## <a name="related-links"></a>Vínculos relacionados

Para más información sobre procedimientos recomendados de proveedores de servicio, consulte [Procedimientos recomendados de mensajería móvil de M3AAWG para proveedores de servicios](https://www.m3aawg.org/sites/default/files/m3aawg-mobile-messaging-best-practices-service-providers-2015-08_0.pdf).

Obtenga más información sobre cómo Office 365 usa SPF y admite la validación de DKIM:

- [Ver más información acerca de SPF](how-office-365-uses-spf-to-prevent-spoofing.md)

- [Ver más información acerca de DKIM](support-for-validation-of-dkim-signed-messages.md)
