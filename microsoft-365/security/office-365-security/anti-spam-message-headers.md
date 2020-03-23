---
title: Encabezados de mensajes de correo no deseado
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
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
description: Obtenga más información sobre los campos de encabezado y los valores que se agregan a los mensajes mediante Exchange Online Protection.
ms.openlocfilehash: 55ba5435b181506cd39314275a9d8c8c6b459b28
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894187"
---
# <a name="anti-spam-message-headers-in-office-365"></a>Encabezados de mensajes de correo no deseado en Office 365

Cuando Exchange Online Protection (EOP) examina un mensaje de correo entrante, inserta el encabezado **X-Forefront-Antispam-Report** en cada mensaje. Los campos de este encabezado pueden dar a los administradores información sobre el mensaje y la forma en que se procesó. Los campos del encabezado **X-Microsoft-Antispam** proporcionan información adicional sobre el correo masivo y la suplantación de identidad. Además de estos dos encabezados, Exchange Online Protection también inserta resultados de autenticación de correo electrónico para cada mensaje que procesa en el encabezado **Authentication-results**.

Para obtener información sobre cómo ver el encabezado del mensaje de un correo electrónico en distintos clientes de correo electrónico, vea [Analizador de encabezados de mensaje](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)

> [!TIP]
> Puede copiar y pegar el contenido del encabezado de un mensaje en la herramienta [Analizador de mensaje](https://testconnectivity.microsoft.com/?tabid=mha). Esta herramienta le ayuda a analizar los encabezados y los convierte en un formato más legible.

## <a name="x-forefront-antispam-report-message-header-fields"></a>Campos del encabezado del mensaje X-Forefront-Antispam-Report

Al obtener acceso a la información del encabezado del mensaje, busque **X-Forefront-Antispam-Report** y, a continuación, busque los siguientes campos. El resto de los campos de este encabezado los usa exclusivamente el equipo de Microsoft contra el correo no deseado con fines de diagnóstico.

|||
|---|---|
|**Campo de encabezado**|**Descripción**|
|ARC|El protocolo ARC tiene los encabezados siguientes: <ul><li>AAR: registra el contenido del encabezado de resultados de Autenticación de DMARC.</li><li>AMS: este encabezado incluye las firmas criptográficas del mensaje.</li><li>AS: incluye las firmas criptográficas de los encabezados del mensaje. Este encabezado contiene una etiqueta de una validación de cadena denominada "cv=", que incluye el resultado de la validación de la cadena como **none**, **pass**o **fail**.</li></ul>|
|CAT:|La categoría de la directiva de protección que se aplica al mensaje: <ul><li>BULK: masivo</li><li>DIMP: suplantación de dominio</li><li>GIMP: inteligencia de buzón</li><li>HPHSH o HPHISH: suplantación de identidad de alta confianza </li><li>HSPM: correo no deseado de confianza elevada</li><li>MALW: malware</li><li>PHSH: phishing</li><li>SPM: correo no deseado</li><li>SPOOF: suplantación de identidad</li><li>UIMP: suplantación de usuario</li></ul><br/>Un mensaje entrante puede aparecer marcado por múltiples formas de protección y múltiples análisis de detección. Las directivas tienen diferentes prioridades y se aplica primero la que tenga la prioridad más alta. Para obtener más información, consulte [Qué directiva se aplica cuando se ejecutan varios métodos de protección y exámenes de detección en el correo electrónico](how-policies-and-protections-are-combined.md).|
|CIP: \[dirección IP\]|La dirección IP de conexión. Puede usar esta dirección IP en la Lista de direcciones IP permitidas o en la Lista de direcciones IP bloqueadas. Para obtener más información, consulte [Configurar filtrado de la conexión en Office 365 ](configure-the-connection-filter-policy.md).|
|CTRY|El país o región de origen están determinados por la dirección IP de conexión, que puede no ser la misma que la dirección IP de envío original.|
|H:\[helostring\]|Cadenas HELO o EHLO del servidor de correo de conexión.|
|IPV:CAL|El mensaje fue omitido del filtrado de correo no deseado porque la dirección IP de origen aparecía en la Lista de direcciones IP permitidas. Para obtener más información, consulte [Configurar filtrado de la conexión en Office 365 ](configure-the-connection-filter-policy.md).|
|IPV:NLI|La dirección IP no aparecía en ninguna lista de reputación de IP.|
|LANG|El idioma en que se redactó el mensaje, que está definido por el código de país (por ejemplo, ru_RU indica ruso).|
|PTR:\[ReverseDNS\]|Registro PTR (también denominado registro de marcador o dirección DNS inversa) de la dirección IP de origen.|
|SCL|Nivel de confianza de correo electrónico no deseado (SCL) del mensaje. Un valor superior indica que el mensaje tiene más posibilidades de ser correo no deseado. Para obtener más información, consulte [Nivel de confianza del correo no deseado (SCL) en Office 365 ](spam-confidence-levels.md).|
|SFTY|El mensaje se identificó como suplantación de identidad (phishing) y también se marcará con uno de los siguientes valores: <ul><li>9.1: valor predeterminado. El mensaje contiene una dirección URL de suplantación de identidad (phishing), puede tener otro contenido de suplantación de identidad (phishing) o se ha marcado como suplantación de identidad por otro filtro de correo, como una versión local de Exchange Server, antes de transmitir el mensaje a Office 365.</li><li>9.11: el mensaje no ha superado las comprobaciones de suplantación de identidad donde el dominio de envío en el encabezado De: es el mismo, o se alinea con, o es parte de la misma organización que el dominio de recepción. Esto indica que se agregará una sugerencia de seguridad sobre la suplantación de la organización al mensaje.</li><li>9.19: La suplantación del dominio del mensaje falló cuando el dominio remitente intentó hacerse pasar por un dominio que es propiedad del receptor o un dominio personalizado protegido por la directiva de protección contra la suplantación de identidad (anti-phishing). Esto indica que se agregará una sugerencia de seguridad de suplantación al mensaje si se habilitó a través de la directiva de protección contra la suplantación de identidad.</li><li>9.20: El mensaje no superó las comprobaciones de suplantación del usuario cuando el usuario remitente intenta hacerse pasar por un usuario que pertenece a la organización del receptor o un usuario personalizado protegido por la directiva de protección contra la suplantación de identidad (anti-phishing). Esto indica que se agregará una sugerencia de seguridad de suplantación al mensaje si se habilitó a través de la directiva de protección contra la suplantación de identidad.</li><li>9.21: El mensaje no superó las comprobaciones contra suplantaciones y el dominio remitente en el encabezado De: no se autentica y procede de un dominio externo. Se utiliza en combinación con un CompAuth (consulte Authentication-Results).</li><li>9.22: Es lo mismo que el 9.21, pero el usuario tiene un remitente seguro que se reemplazó.</li><li>9.23: Es lo mismo que el 9.22, pero la organización tiene un remitente o un dominio permitido que se reemplazó.</li><li>9.24: Es lo mismo que el 9.23, pero el usuario tiene una regla de flujo de correo de Exchange (también denominada regla de transporte) que se reemplazó.</li></ul>|
|SFV:BLK|Se omitió el filtrado y se bloqueó el mensaje porque se envió desde una dirección de Remitentes bloqueados de Outlook del usuario (la lista de Remitentes bloqueados del usuario).<br/></br> Para obtener más información sobre cómo los administradores pueden administrar la lista de Remitentes bloqueados de un usuario, consulte [Configurar el correo electrónico no deseado en buzones de Exchange Online en Office 365](configure-junk-email-settings-on-exo-mailboxes.md).|
|SFV:NSPM|El filtrado de correo no deseado marcó el mensaje como deseado y se envió a los destinatarios correspondientes.|
|SFV:SFE|Se omitió el filtrado y el mensaje se envió porque se envió desde una dirección Remitentes seguros de Outlook del usuario (la lista de Remitentes seguros del usuario).<br/></br> Para obtener más información sobre cómo los administradores pueden administrar la lista de Remitentes seguros de un usuario, consulte [Configurar el correo electrónico no deseado en buzones de Exchange Online en Office 365](configure-junk-email-settings-on-exo-mailboxes.md).|
|SFV:SKA|El mensaje fue omitido del filtrado de correo electrónico no deseado y se entregó en la Bandeja de entrada porque coincidía con una entrada de una lista de remitentes permitidos o una lista de dominios permitidos de una directiva contra correo no deseado. Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado en Office 365 ](configure-your-spam-filter-policies.md).|
|SFV:SKB|El mensaje se marcó como correo no deseado porque coincidía con una entrada de una lista de remitentes bloqueados o una lista de dominios bloqueados de una directiva contra correo no deseado. Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado en Office 365 ](configure-your-spam-filter-policies.md).|
|SFV:SKI|Similar a SFV:SKN, el mensaje fue omitido del filtrado de correo electrónico no deseado por otra razón, por ejemplo, ser un mensaje de correo electrónico dentro un espacio empresarial de la organización.|
|SFV:SKN|El mensaje se marcó como correo deseado antes de ser procesado por el filtrado de correo no deseado (por ejemplo, el mensaje se marcó como SCL -1 o **Omitir el filtrado de correo no deseado** por una regla de flujo de correo).|
|SFV:SKQ|El mensaje fue publicado desde la cuarentena y se ha enviado a los destinatarios.|
|SFV:SKS|El mensaje se marcó como correo no deseado antes de ser procesado por el filtro de correo no deseado (por ejemplo, el mensaje se marcó como SCL de 5 a 9 por una regla de flujo de correo).|
|SFV:SPM|El mensaje se marcó como correo no deseado por el filtro de correo no deseado.|
|SRV:BULK|El mensaje se identificó como correo electrónico masivo por el filtrado de correo no deseado y el umbral de nivel de queja de correo masivo (BCL). Cuando el parámetro _MarkAsSpamBulkMail_ está `On` (está activado de forma predeterminada), un mensaje de correo masivo se marca como correo no deseado de alta confianza (SCL 9). Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado en Office 365 ](configure-your-spam-filter-policies.md).|
|X-CustomSpam: \[ASFOption\]|El mensaje coincide con una opción de Filtro de correo no deseado avanzado (ASF). Para ver el valor del encabezado X para cada opción de ASF, consulte [Configuración del Filtro de correo no deseado avanzado (ASF) en Office 365](advanced-spam-filtering-asf-options.md).|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>Campos de encabezado de mensaje de X-Microsoft-Antispam

En la tabla siguiente se describen los campos más útiles del encabezado de mensaje **X-Microsoft-Antispam**. El resto de los campos de este encabezado los usa exclusivamente el equipo de Microsoft contra el correo no deseado con fines de diagnóstico.

|||
|---|---|
|**Campo de encabezado**|**Descripción**|
|BCL|Nivel de queja de correo masivo (BCL) del mensaje. Un BCL superior indica que es más probable que un mensaje de correo masivo (también denominado _correo gris_) generen quejas (y, por lo tanto, es más probable que sea correo no deseado). Para obtener más información, consulte [Nivel de queja de correo masivo (BCL) en Office 365)](bulk-complaint-level-values.md).|
|

## <a name="authentication-results-message-header"></a>Encabezado de mensaje Authentication-results

Office 365 graba los resultados de las comprobaciones de SPF, DKIM y DMARC en el encabezado de mensaje **Authentication-results** cuando nuestros servidores de correo reciben un mensaje de correo electrónico.

### <a name="check-stamp-syntax-and-examples"></a>Comprobar sintaxis y ejemplos de las marcas de verificación

En los siguientes ejemplos de sintaxis se muestra una parte del texto de la marca que Office 365 aplica al encabezado del mensaje por cada correo electrónico que se somete a una comprobación de autenticación de correo electrónico cuando lo recibimos en nuestros servidores de correo. Esta marca se agrega al encabezado **Authentication-Results**.

#### <a name="syntax-spf-check-stamp"></a>Sintaxis: marca de verificación de SPF

En cuanto a SPF, se aplica la siguiente sintaxis:

```text
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

##### <a name="examples-spf-check-stamp"></a>Ejemplos: marca de verificación de SPF

```text
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

#### <a name="syntax-dkim-check-stamp"></a>Sintaxis: marca de verificación de DKIM

En cuanto a DKIM, se aplica la siguiente sintaxis:

```text
dkim=<pass|fail (reason)|none> header.d=<domain>
```

##### <a name="examples-dkim-check-stamp"></a>Ejemplos: marca de verificación de DKIM

```text
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

#### <a name="syntax-dmarc-check-stamp"></a>Sintaxis: marca de verificación de DMARC

En cuanto a DMARC, se aplica la siguiente sintaxis:

```text
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

##### <a name="examples-dmarc-check-stamp"></a>Ejemplos: marca de verificación de DMARC

```text
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-office-365-email-authentication"></a>Campos del encabezado de mensaje Authentication-results usados por la autenticación de correo electrónico de Office 365

En esta tabla se describen los campos y los valores posibles para todas las comprobaciones de autenticación de correo electrónico.

|||
|---|---|
|**Campo de encabezado**|**Descripción**|
|acción|Indica la acción efectuada por el filtro de correo no deseado en función de los resultados de la comprobación de DMARC. Por ejemplo: <ul><li>**oreject** u **o.reject**: significa invalidar el rechazo. En este caso, Office 365 usa esta acción cuando recibe un mensaje que no supera la comprobación de DMARC desde un dominio cuyo registro TXT de DMARC tiene una directiva de p=reject. En lugar de eliminar o rechazar el mensaje, Office 365 marca el mensaje como correo no deseado. Para obtener más información sobre por qué Office 365 está configurado de esta forma, vea [Cómo controla Office 365 el correo electrónico entrante que no supera las comprobaciones de DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail).</li><li>**pct.quarantine**: indica que se entregará un porcentaje inferior al 100 % de los mensajes que no superen la validación por DMARC. Esto significa que el mensaje no superó la comprobación de DMARC y la directiva se estableció en cuarentena, pero el campo pct no se estableció en el 100 % y el sistema decidió, de forma aleatoria, no aplicar la acción de DMARC, de acuerdo con la directiva del dominio especificado.</li><li>**pct.reject**: indica que se entregará un porcentaje inferior al 100 % de los mensajes que no superen la validación por DMARC. Esto significa que el mensaje no superó la comprobación de DMARC y se estableció el rechazo de la directiva, pero el campo pct no se estableció en el 100 % y el sistema decidió, de forma aleatoria, no aplicar la acción de DMARC, de acuerdo con la directiva del dominio especificado.</li><li>**permerror**: se produjo un error permanente durante la evaluación por DMARC (por ejemplo, la detección de un registro TXT de DMARC con un formato incorrecto en DNS). Es probable que volver a enviar este mensaje no produzca un resultado diferente. Puede que deba ponerse en contacto con el propietario del dominio para intentar resolver el problema.</li><li>**temperror**: se produjo un error temporal durante la evaluación por DMARC. Puede solicitar al remitente que reenvíe el mensaje más tarde para procesar correctamente el correo electrónico.</li></ul>|
|compauth|Resultado de la autenticación compuesta. Office 365 la utiliza para combinar varios tipos de autenticación como SPF, DKIM, DMARC o cualquier otra parte del mensaje para determinar si el mensaje se autentica o no. Usa el dominio De: como base de la evaluación.|
|dkim|Describe los resultados de la comprobación de DKIM del mensaje. Los valores posibles son: <ul><li>**pass**: indica que se superó la validación por DKIM del mensaje.</li><li>**fail (motivo)**: indica que no se superó la validación por DKIM del mensaje e incluye el motivo. Por ejemplo, si el mensaje no estaba firmado o no se verificó la firma.</li><li>**none**: indica que el mensaje no estaba firmado. Esto podría indicar que el dominio tiene un registro DKIM o que el registro DKIM no proporciona ningún resultado, solo indica que el mensaje no estaba firmado.</li></ul>|
|dmarc|Describe los resultados de la comprobación de DMARC del mensaje. Los valores posibles son: <ul><li>**pass**: indica que se superó la validación por DMARC del mensaje.</li><li>**fail**: indica que no se superó la validación por DMARC del mensaje.</li><li>**bestguesspass**: indica que no existe ningún registro TXT de DMARC para el dominio, pero si hubiera existido, el mensaje habría superado la validación por DMARC. Esto se debe a que el dominio de la dirección `5321.MailFrom` (también conocida como la dirección MAIL FROM, el remitente P1 o el remitente del sobre) coincide con el dominio de la dirección `5322.From` (también conocida como la dirección De o el remitente P2).</li><li>**none**: indica que no hay ningún registro TXT de DKIM para el dominio remitente en DNS.|
|header.d|Dominio identificado en la firma de DKIM, en caso de haber alguna. Se trata del dominio consultado para obtener la clave pública.|
|header.from|El dominio de la dirección `5322.From` del encabezado del mensaje de correo electrónico (también denominada dirección De o remitente P2). Destinatario consulte la dirección De en clientes de correo electrónico.|
|motivo|El motivo por el que se ha producido un error en la autenticación compuesta. El valor del motivo está formado por tres dígitos: <ul><li>**000**: el mensaje no se pudo autenticar explícitamente. Por ejemplo, el mensaje ha recibido un error de DMARC con una acción de cuarentena o rechazo.</li><li>**001**: el mensaje no se pudo autenticar explícitamente, y el domino remitente no publicó las directivas de autenticación. Por ejemplo, una directiva DMARC de p=none.</li><li>**1xx** o **7xx**: el mensaje pasó la autenticación. Los dos últimos dígitos son códigos internos utilizados por Office 365.</li><li>**2xx**: el mensaje superó la autenticación. Los dos últimos dígitos son códigos internos utilizados por Office 365.</li><li>**3xx**: no se validó la autenticación compuesta del mensaje.</li><li>**4xx** o **9XX**: el mensaje ignoró la autenticación compuesta. Los dos últimos dígitos son códigos internos utilizados por Office 365.</li></ul>|
|smtp.mailfrom|El dominio de la dirección `5321.MailFrom` (también conocida como dirección MAIL FROM, remitente P1 o remitente del sobre). Esta es la dirección de correo electrónico que se usa para los informes de no entrega (también conocidos como NDR o mensajes de devolución).|
|spf|Describe los resultados de la comprobación de SPF del mensaje. Los valores posibles son: <ul><li>**pass (dirección IP)**: indica que se superó la verificación de SPF del mensaje e incluye la dirección IP del remitente. El cliente tiene autorización para enviar o retransmitir un correo electrónico en nombre del dominio del remitente.</li><li>**fail (dirección IP)**: indica que no se superó la verificación de SPF del mensaje e incluye la dirección IP del remitente A veces, recibe la denominación _"error no recuperable"_.</li><li>**softfail (motivo)**: indica que el registro SPF determinó que el servidor no puede efectuar envíos, pero se encuentra en transición.</li><li>**neutral**: indica que el registro SPF declaró explícitamente que no afirma si la dirección IP tiene autorización o no.</li><li>**none**: indica que el dominio no tiene ningún registro SPF o que el registro SPF no proporciona ningún resultado.</li><li>**temperror**: indica que se produjo un error que puede ser de carácter temporal (por ejemplo, un error de DNS). Volverlo a intentar más tarde puede que lo resuelva sin la intervención de ningún administrador.</li><li>**permerror**: indica que se produjo un error permanente. Sucede cuando, por ejemplo, el dominio tiene un registro SPF con un formato incorrecto.</li></ul>|
|
