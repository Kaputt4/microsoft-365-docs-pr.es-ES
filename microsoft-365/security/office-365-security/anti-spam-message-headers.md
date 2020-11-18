---
title: Encabezados de mensajes de correo no deseado
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden obtener información sobre los campos de encabezado que Exchange Online Protection (EOP) agrega a los mensajes. Estos campos de encabezado proporcionan información sobre el mensaje y cómo se ha procesado.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6f54ffad5107e0de00b0098d5f347ab37ae92d80
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123479"
---
# <a name="anti-spam-message-headers-in-microsoft-365"></a>Encabezados de mensajes de correo no deseado en Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En todas las organizaciones de Microsoft 365, Exchange Online Protection (EOP) analiza todos los mensajes entrantes para detectar spam, malware y otras amenazas. Los resultados de estos análisis se agregan a los siguientes campos de encabezado de los mensajes:

- **X-Forefront-antispam-Report**: contiene información sobre el mensaje y cómo se ha procesado.

- **X-Microsoft-antispam**: contiene información adicional sobre el correo masivo y el phishing.

- **Authentication-results**: contiene información sobre los resultados de SPF, DKIM y DMARC (autenticación de correo electrónico).

Este artículo describe lo que está disponible en estos campos de encabezado.

Para obtener información sobre cómo ver el encabezado del mensaje de un correo electrónico en distintos clientes de correo electrónico, vea [Analizador de encabezados de mensaje](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)

> [!TIP]
> Puede copiar y pegar el contenido del encabezado del mensaje en la herramienta [Analizador de encabezados de mensaje](https://mha.azurewebsites.net/). Esta herramienta le ayuda a analizar los encabezados y los convierte en un formato más legible.

## <a name="x-forefront-antispam-report-message-header-fields"></a>Campos del encabezado del mensaje X-Forefront-Antispam-Report

Cuando tenga la información del encabezado del mensaje, busque el encabezado **X-Forefront-Antispam-Report**. Habrá varios pares de campo-valor en este encabezado separados por punto y coma (;). Por ejemplo:

`...CTRY:;LANG:hr;SCL:1;SRV:;IPV:NLI;SFV:NSPM;PTR:;CAT:NONE;SFTY:;...`

Los campos y valores individuales se describen en la siguiente tabla.

> [!NOTE]
> El encabezado **X-Forefront-Antispam-Report** contiene muchos campos y valores de encabezado distintos. Los campos que no se describen en la tabla los usa exclusivamente el equipo de protección contra correo no deseado de Microsoft con fines de diagnóstico.

****

|Campo|Description|
|---|---|
|`ARC`|El protocolo `ARC` tiene los campos siguientes: <ul><li>`AAR`: registra el contenido del encabezado **Authentication-results** de DMARC.</li><li>`AMS`: incluye las firmas criptográficas del mensaje.</li><li>`AS`: incluye las firmas criptográficas de los encabezados del mensaje. Este campo contiene una etiqueta de una validación de cadena denominada `"cv="`, que incluye el resultado de la validación de la cadena como **none**, **pass** o **fail**.</li></ul>|
|`CAT:`|La categoría de la directiva de protección que se aplica al mensaje: <ul><li>`BULK`: Masivo</li><li>`DIMP`: Suplantación de dominio</li><li>`GIMP`: [Suplantación basada en la inteligencia de buzones](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>`HPHSH` o `HPHISH`: Phishing de alta confianza</li><li>`HSPM`: Correo no deseado de alta confianza</li><li>`MALW`: Malware</li><li>`PHSH`: Phishing</li><li>`SPM`: Spam</li><li>`SPOOF`: Suplantación electrónica</li><li>`UIMP`: Suplantación de usuario</li><li>`AMP`: Antimalware</li><li>`SAP`: Datos adjuntos seguros</li><li>`OSPM`: Correo no deseado saliente</li></ul><br/>Un mensaje entrante puede aparecer marcado por múltiples formas de protección y múltiples análisis de detección. Las directivas tienen diferentes prioridades y se aplica primero la que tenga la prioridad más alta. Para obtener más información, consulte [Qué directiva se aplica cuando se ejecutan varios métodos de protección y exámenes de detección en el correo electrónico](how-policies-and-protections-are-combined.md).|
|`CIP:[IP address]`|La dirección IP de conexión. Puede usar esta dirección IP en la Lista de direcciones IP permitidas o en la Lista de direcciones IP bloqueadas. Para obtener más información, consulte [Configurar filtrado de la conexión](configure-the-connection-filter-policy.md).|
|`CTRY`|El país o región de origen están determinados por la dirección IP de conexión, que puede no ser la misma que la dirección IP de envío original.|
|`H:[helostring]`|Cadenas HELO o EHLO del servidor de correo de conexión.|
|`IPV:CAL`|El mensaje fue omitido del filtrado de correo no deseado porque la dirección IP de origen aparecía en la Lista de direcciones IP permitidas. Para obtener más información, consulte [Configurar filtrado de la conexión](configure-the-connection-filter-policy.md).|
|`IPV:NLI`|La dirección IP no aparecía en ninguna lista de reputación de IP.|
|`LANG`|El idioma en que se redactó el mensaje, que está definido por el código de país (por ejemplo, ru_RU indica ruso).|
|`PTR:[ReverseDNS]`|El registro PTR (también conocido como la búsqueda inversa de DNS) de la dirección IP de la fuente.|
|`SCL`|Nivel de confianza de correo electrónico no deseado (SCL) del mensaje. Un valor superior indica que el mensaje tiene más posibilidades de ser correo no deseado. Para obtener más información, consulte [Nivel de confianza del correo no deseado (SCL)](spam-confidence-levels.md).|
|`SFTY`|El mensaje se identificó como suplantación de identidad (phishing) y también se marcará con uno de los siguientes valores: <ul><li>9.1: valor predeterminado. El mensaje contiene uno o varios de los siguientes elementos: una URL de suplantación de identidad (phishing), otro contenido de phishing o se marcó como "phishing" por Exchange local.</li><li>9.11: [Suplantación electrónica dentro de la organización o interna](anti-spoofing-protection.md#different-types-of-spoofing). La sugerencia de seguridad para la suplantación de identidad dentro de la organización se agregará al mensaje.</li><li>9.19: Suplantación de dominio. El dominio remitente está intentando [suplantar un dominio protegido](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). La sugerencia de seguridad para la suplantación del dominio se agrega al mensaje (si está habilitada).</li><li>9.20: Suplantación de usuario. El usuario remitente está intentando suplantar a un usuario en la organización del destinatario, o bien a un usuario protegido que se especificó en una directiva contra la suplantación de identidad en Microsoft Defender para Office 365. La sugerencia de seguridad para la suplantación del usuario se agrega al mensaje (si está habilitada).</li><li>9.21: [Suplantación electrónica entre dominios](anti-spoofing-protection.md#different-types-of-spoofing). El mensaje no pasó las comprobaciones contra la suplantación de identidad. El dominio de correo electrónico del remitente en el encabezado De no se autentica y es un dominio externo. Se usa en combinación con [autenticación compuesta](#authentication-results-message-header-fields).</li><li>9.22: Es lo mismo que el 9.21, pero el usuario tiene un remitente seguro que se reemplazó.</li><li>9.23: Es lo mismo que el 9.22, pero la organización tiene un remitente o un dominio permitido que se reemplazó.</li><li>9.24: Es lo mismo que el 9.23, pero el usuario tiene una regla de flujo de correo de Exchange (también denominada regla de transporte) que se reemplazó.</li></ul>|
|`SFV:BLK`|Se omitió el filtrado y se bloqueó el mensaje porque se envió desde una dirección de la lista de remitentes bloqueados de un usuario.<br/></br> Para más información sobre cómo los administradores pueden administrar la lista de Remitentes bloqueados de un usuario, consulte [Configurar las opciones de correo electrónico no deseado en buzones de Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).|
|`SFV:NSPM`|El filtrado de correo no deseado marcó el mensaje como deseado y se envió a los destinatarios correspondientes.|
|`SFV:SFE`|Se omitió el filtrado y el mensaje se permitió porque se envió desde una dirección de la lista de remitentes seguros de un usuario.<br/></br> Para más información sobre cómo los administradores pueden administrar la lista de Remitentes seguros de un usuario, consulte [Configurar las opciones de correo electrónico no deseado en buzones de Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).|
|`SFV:SKA`|El mensaje fue omitido del filtrado de correo electrónico no deseado y se entregó en la Bandeja de entrada porque el remitente estaba en una lista de remitentes permitidos o una lista de dominios permitidos de una directiva contra correo no deseado. Para más información, consulte [Configurar directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md).|
|`SFV:SKB`|El mensaje se marcó como correo no deseado porque coincidía con un remitente de una lista de remitentes bloqueados o una lista de dominios bloqueados de una directiva contra correo no deseado. Para más información, consulte [Configurar directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md).|
|`SFV:SKI`|Similar a SFV:SKN, el mensaje fue omitido del filtrado de correo electrónico no deseado por otra razón, por ejemplo, ser un mensaje de correo electrónico dentro un espacio empresarial de la organización.|
|`SFV:SKN`|El mensaje se marcó como correo seguro antes de que el filtro de correo no deseado lo procesara. Por ejemplo, el mensaje se marcó como SCL -1 u **Omitir el filtrado de correo no deseado** por una regla de flujo de correo.|
|`SFV:SKQ`|El mensaje fue publicado desde la cuarentena y se ha enviado a los destinatarios.|
|`SFV:SKS`|El mensaje se marcó como correo no deseado antes de que el filtro de correo no deseado lo procesara. Por ejemplo, el mensaje se marcó como SCL de 5 a 9 por una regla de flujo de correo.|
|`SFV:SPM`|El mensaje se marcó como correo no deseado por el filtro de correo no deseado.|
|`SRV:BULK`|El mensaje se identificó como correo electrónico masivo por el filtrado de correo no deseado y el umbral de nivel de queja de correo masivo (BCL). Cuando el parámetro _MarkAsSpamBulkMail_ está `On` (está activado de forma predeterminada), un mensaje de correo masivo se marca como correo no deseado de alta confianza (SCL 9). Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md).|
|`X-CustomSpam: [ASFOption]`|El mensaje coincide con una opción de Filtro de correo no deseado avanzado (ASF). Para ver el valor del encabezado X para cada opción de ASF, consulte [Configuración del Filtro de correo no deseado avanzado (ASF)](advanced-spam-filtering-asf-options.md).|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>Campos de encabezado de mensaje de X-Microsoft-Antispam

En la tabla siguiente se describen los campos más útiles del encabezado de mensaje **X-Microsoft-Antispam**. El resto de los campos de este encabezado los usa exclusivamente el equipo de Microsoft contra el correo no deseado con fines de diagnóstico.

****

|Campo|Description|
|---|---|
|`BCL`|Nivel de queja de correo masivo (BCL) del mensaje. Un BCL superior indica que es más probable que un mensaje de correo masivo generen quejas (y, por lo tanto, es más probable que sea correo no deseado). Para obtener más información, consulte [Nivel de queja de correo masivo (BCL)](bulk-complaint-level-values.md).|
|

## <a name="authentication-results-message-header"></a>Encabezado de mensaje Authentication-results

Los resultados de las comprobaciones de autenticación de correo electrónico para SPF, DKIM y DMARC se registran (marcan) en el encabezado de mensaje **Authentication-results** en mensajes entrantes.

La siguiente lista describe el texto que se agrega al encabezado **Authentication-Results** para cada tipo de comprobación de autenticación de correo electrónico:

- SPF usa la siguiente sintaxis:

  ```text
  spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
  ```

  Por ejemplo:

  ```text
  spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
  spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
  ```

- DKIM usa la siguiente sintaxis:

  ```text
  dkim=<pass|fail (reason)|none> header.d=<domain>
  ```

  Por ejemplo:

  ```text
  dkim=pass (signature was verified) header.d=contoso.com
  dkim=fail (body hash did not verify) header.d=contoso.com
  ```

- DMARC usa la siguiente sintaxis:

  ```text
  dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
  ```

  Por ejemplo:

  ```text
  dmarc=pass action=none header.from=contoso.com
  dmarc=bestguesspass action=none header.from=contoso.com
  dmarc=fail action=none header.from=contoso.com
  dmarc=fail action=oreject header.from=contoso.com
  ```

### <a name="authentication-results-message-header-fields"></a>Campos del encabezado del mensaje Authentication-results

En la siguiente tabla se describen los campos y los valores posibles para todas las comprobaciones de autenticación de correo electrónico.

****

|Campo|Descripción|
|---|---|
|`action`|Indica la acción efectuada por el filtro de correo no deseado en función de los resultados de la comprobación de DMARC. Por ejemplo: <ul><li>**oreject** u **o.reject**: significa invalidar el rechazo. En este caso, Microsoft 365 usa esta acción cuando recibe un mensaje que no supera la comprobación de DMARC desde un dominio cuyo registro TXT de DMARC tiene una directiva de p=reject. En lugar de eliminar o rechazar el mensaje, Microsoft 365 marca el mensaje como correo no deseado. Para obtener más información sobre por qué Microsoft 365 está configurado de esta forma, vea [Cómo controla Microsoft 365 el correo electrónico entrante que no supera las comprobaciones de DMARC](use-dmarc-to-validate-email.md#how-microsoft-365-handles-inbound-email-that-fails-dmarc).</li><li>**pct.quarantine**: indica que se entregará un porcentaje inferior al 100 % de los mensajes que no superen la validación por DMARC. Esto significa que el mensaje no superó la comprobación de DMARC y la directiva se estableció en cuarentena, pero el campo pct no se estableció en el 100 % y el sistema decidió, de forma aleatoria, no aplicar la acción de DMARC, de acuerdo con la directiva del dominio especificado.</li><li>**pct.reject**: indica que se entregará un porcentaje inferior al 100 % de los mensajes que no superen la validación por DMARC. Esto significa que el mensaje no superó la comprobación de DMARC y se estableció el rechazo de la directiva, pero el campo pct no se estableció en el 100 % y el sistema decidió, de forma aleatoria, no aplicar la acción de DMARC, de acuerdo con la directiva del dominio especificado.</li><li>**permerror**: se produjo un error permanente durante la evaluación por DMARC (por ejemplo, la detección de un registro TXT de DMARC con un formato incorrecto en DNS). Es probable que volver a enviar este mensaje no produzca un resultado diferente. Puede que deba ponerse en contacto con el propietario del dominio para intentar resolver el problema.</li><li>**temperror**: se produjo un error temporal durante la evaluación por DMARC. Puede solicitar al remitente que reenvíe el mensaje más tarde para procesar correctamente el correo electrónico.</li></ul>|
|`compauth`|Resultado de la autenticación compuesta. Microsoft 365 la utiliza para combinar varios tipos de autenticación como SPF, DKIM, DMARC o cualquier otra parte del mensaje para determinar si el mensaje se autentica o no. Usa el dominio De: como base de la evaluación.|
|`dkim`|Describe los resultados de la comprobación de DKIM del mensaje. Los valores posibles son: <ul><li>**pass**: indica que se superó la validación por DKIM del mensaje.</li><li>**fail (motivo)**: indica que no se superó la validación por DKIM del mensaje e incluye el motivo. Por ejemplo, si el mensaje no estaba firmado o no se verificó la firma.</li><li>**none**: indica que el mensaje no estaba firmado. Esto podría indicar que el dominio tiene un registro DKIM o que el registro DKIM no proporciona ningún resultado, solo indica que el mensaje no estaba firmado.</li></ul>|
|`dmarc`|Describe los resultados de la comprobación de DMARC del mensaje. Los valores posibles son: <ul><li>**pass**: indica que se superó la validación por DMARC del mensaje.</li><li>**fail**: indica que no se superó la validación por DMARC del mensaje.</li><li>**bestguesspass**: indica que no existe ningún registro TXT de DMARC para el dominio, pero si hubiera existido, el mensaje habría superado la validación por DMARC. Esto se debe a que el dominio de la dirección `5321.MailFrom` (también conocida como la dirección MAIL FROM, el remitente P1 o el remitente del sobre) coincide con el dominio de la dirección `5322.From` (también conocida como la dirección De o el remitente P2).</li><li>**none**: indica que no hay ningún registro TXT de DMARC para el dominio remitente en DNS.|
|`header.d`|Dominio identificado en la firma de DKIM, en caso de haber alguna. Se trata del dominio consultado para obtener la clave pública.|
|`header.from`|El dominio de la dirección `5322.From` del encabezado del mensaje de correo electrónico (también denominada dirección De o remitente P2). Destinatario consulte la dirección De en clientes de correo electrónico.|
|`reason`|El motivo por el que se ha producido un error en la autenticación compuesta. El valor es un código de 3 dígitos. Por ejemplo: <ul><li>**000**: el mensaje no se pudo autenticar explícitamente (`compauth=fail`). Por ejemplo, el mensaje ha recibido un error de DMARC con una acción de cuarentena o rechazo.</li><li>**001**: el mensaje no se pudo autenticar implícitamente (`compauth=fail`). Esto significa que el dominio remitente no ha publicado registros de autenticación de correo electrónico o, si los ha publicado, tenían una directiva de error más débil (errores recuperables de SPF o neutrales, directiva DMARC de `p=none`).</li><li>**002**: la organización tiene una directiva para el par de remitente y dominio que prohíbe explícitamente el envío de correos electrónicos falsificados. Esta configuración la establece manualmente un administrador.</li><li>**010**: el mensaje ha producido un error de DMARC con una acción de rechazo o cuarentena y el dominio es uno de los dominios aceptados de su organización (esto es parte de la suplantación de identidad interna o dentro de la organización).</li><li>**1xx** o **7xx**: el mensaje pasó la autenticación (`compauth=pass`). Los dos últimos dígitos son códigos internos utilizados por Microsoft 365.</li><li>**2xx**: el mensaje superó la autenticación implícita (`compauth=softpass`). Los dos últimos dígitos son códigos internos utilizados por Microsoft 365.</li><li>**3xx**: no se validó la autenticación compuesta del mensaje (`compauth=none`).</li><li>**4xx** o **9XX**: el mensaje ignoró la autenticación compuesta (`compauth=none`). Los dos últimos dígitos son códigos internos utilizados por Microsoft 365.</li><li>**6xx**: el mensaje ha producido un error de autenticación de correo electrónico implícita y el dominio es uno de los dominios aceptados de su organización (esto es parte de la suplantación de identidad interna o dentro de la organización).</li></ul>|
|`smtp.mailfrom`|El dominio de la dirección `5321.MailFrom` (también conocida como dirección MAIL FROM, remitente P1 o remitente del sobre). Esta es la dirección de correo electrónico que se usa para los informes de no entrega (también conocidos como NDR o mensajes de devolución).|
|`spf`|Describe los resultados de la comprobación de SPF del mensaje. Los valores posibles son: <ul><li>`pass (IP address)`: se superó la verificación de SPF del mensaje e incluye la dirección IP del remitente. El cliente tiene autorización para enviar o retransmitir un correo electrónico en nombre del dominio del remitente.</li><li>`fail (IP address)`: no se superó la verificación de SPF del mensaje e incluye la dirección IP del remitente. A veces, recibe la denominación _"error no recuperable"_.</li><li>`softfail (reason)`: el registro SPF determinó que el servidor no puede efectuar envíos, pero se encuentra en transición.</li><li>`neutral`: el registro SPF indica explícitamente que no garantiza que la dirección IP esté autorizada para el envío.</li><li>`none`: el dominio no tiene un registro SPF o el registro SPF no se evalúa como resultado.</li><li>`temperror`: se ha producido un error temporal. Por ejemplo, un error de DNS. Es posible la misma comprobación sea correcta más tarde.</li><li>`permerror`: se ha producido un error permanente. Por ejemplo, el dominio tiene un registro SPF con un formato incorrecto.</li></ul>|
|
