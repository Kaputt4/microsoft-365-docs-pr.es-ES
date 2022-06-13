---
title: Cómo la autenticación basada en DNS SMTP de entidades con nombre (DANE) protege las comunicaciones por correo electrónico
f1.keywords:
- NOCSH
ms.author: v-mathavale
author: v-mathavale
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo funciona la autenticación basada en DNS SMTP de entidades con nombre (DANE) para proteger las comunicaciones por correo electrónico entre los servidores de correo.
ms.openlocfilehash: 200dde9c62fb9825ce36eea7416304727bd6b598
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66015778"
---
# <a name="how-smtp-dns-based-authentication-of-named-entities-dane-works"></a>Funcionamiento de la autenticación basada en DNS SMTP de entidades con nombre (DANE)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

El protocolo SMTP es el protocolo principal que se usa para transferir mensajes entre servidores de correo y, de forma predeterminada, no es seguro. El protocolo seguridad de la capa de transporte (TLS) se introdujo hace años para admitir la transmisión cifrada de mensajes a través de SMTP. Se usa normalmente de forma oportunista en lugar de como requisito, dejando mucho tráfico de correo electrónico en texto no cifrado, vulnerable a la interceptación por parte de actores nefastos. Además, SMTP determina las direcciones IP de los servidores de destino a través de la infraestructura dns pública, que es susceptible a ataques de suplantación de identidad y ataques de tipo "Man in the Middle" (MITM). Esto ha llevado a crear muchos estándares nuevos para aumentar la seguridad para enviar y recibir correo electrónico, uno de ellos es la autenticación basada en DNS de entidades con nombre (DANE). 

DANE para SMTP [RFC 7672](https://tools.ietf.org/html/rfc7672) usa la presencia de un registro de autenticación de seguridad de la capa de transporte (TLSA) en el conjunto de registros DNS de un dominio para indicar un dominio y sus servidores de correo admiten DANE. Si no hay ningún registro TLSA presente, la resolución DNS para el flujo de correo funcionará como de costumbre sin que se intente realizar ninguna comprobación DANE. El registro TLSA indica de forma segura la compatibilidad con TLS y publica la directiva DANE para el dominio. Por lo tanto, el envío de servidores de correo puede autenticar correctamente servidores de correo receptor legítimos mediante SMTP DANE. Esto hace que sea resistente a los ataques de degradación y MITM. DANE tiene dependencias directas en DNSSEC, que funciona firmando digitalmente registros para búsquedas DNS mediante criptografía de clave pública. Las comprobaciones de DNSSEC se producen en los solucionadores DNS recursivos, los servidores DNS que realizan consultas DNS para los clientes. DNSSEC garantiza que los registros DNS no se manipulen y sean auténticos.

Una vez que los registros de recursos relacionados con MX, A/AAAA y DNSSEC para un dominio se devuelven al solucionador recursivo DNS como DNSSEC auténtico, el servidor de correo de envío solicitará el registro TLSA correspondiente a la entrada o entradas del host MX. Si el registro TLSA está presente y se ha comprobado que es auténtico mediante otra comprobación de DNSSEC, el solucionador recursivo de DNS devolverá el registro TLSA al servidor de correo de envío.

Después de recibir el registro TLSA auténtico, el servidor de correo de envío establece una conexión SMTP al host MX asociado al registro TLSA auténtico. El servidor de correo de envío intentará configurar TLS y comparar el certificado TLS del servidor con los datos del registro TLSA para validar que el servidor de correo de destino conectado al remitente es el servidor de correo receptor legítimo. El mensaje se transmitirá (mediante TLS) si la autenticación se realiza correctamente. Cuando se produce un error en la autenticación o si el servidor de destino no admite TLS, Exchange Online volverá a intentar todo el proceso de validación a partir de una consulta DNS para el mismo dominio de destino de nuevo después de 15 minutos y, después, 15 minutos después, cada hora durante las siguientes 24 horas. Si la autenticación sigue generando un error después de 24 horas de reintento, el mensaje expirará y se generará un NDR con detalles de error y se enviará al remitente.

## <a name="what-are-the-components-of-dane"></a>¿Cuáles son los componentes de DANE?

### <a name="tlsa-resource-record"></a>Registro de recursos TLSA

El registro de autenticación TLS (TLSA) se usa para asociar el certificado X.509 o el valor de clave pública de un servidor con el nombre de dominio que contiene el registro. Los registros TLSA solo pueden ser de confianza si DNSSEC está habilitado en el dominio. Si usa un proveedor de DNS para hospedar el dominio, puede ser una configuración que se ofrece al configurar un dominio con ellos. Para obtener más información sobre la firma de zona DNSSEC, visite este vínculo: [Introducción a DNSSEC | Microsoft Docs](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj200221(v=ws.11)).

Registro TLSA de ejemplo:

:::image type="content" source="../media/compliance-trial/example-TLSA-record.png" alt-text="Registro TLSA de ejemplo" lightbox="../media/compliance-trial/example-TLSA-record.png":::

Hay cuatro campos configurables únicos para el tipo de registro TLSA:

**Campo de uso de certificado**: especifica cómo el servidor de correo electrónico de envío debe comprobar el certificado del servidor de correo electrónico de destino.

|Valor|Acrónimo|Descripción|
|---|---|---|
|0<sup>1</sup>|PKIX-TA|El certificado usado es la entidad de certificación pública de anclaje de confianza de la cadena de confianza X.509.|
|1<sup>1</sup>|PKIX-EE|El certificado comprobado es el servidor de destino; Las comprobaciones de DNSSEC deben comprobar su autenticidad.|
|2|DANE-TA|Use la clave privada del servidor del árbol X.509 que debe validar un delimitador de confianza en la cadena de confianza. El registro TLSA especifica el delimitador de confianza que se usará para validar los certificados TLS para el dominio.|
|3|DANE-EE|Solo coincide con el certificado del servidor de destino.|

<sup>1</sup> Exchange Online sigue las instrucciones de implementación de RFC que indican que los valores del campo de uso de certificado de 0 o 1 no deben usarse cuando dane se implementa con SMTP. Cuando se devuelve un registro TLSA que tiene un valor de campo Uso de certificado de 0 o 1 a Exchange Online, Exchange Online lo tratará como no utilizable. Si se encuentran inutilizables todos los registros TLSA, Exchange Online no realizará los pasos de validación de DANE para 0 o 1 al enviar el correo electrónico. En su lugar, debido a la presencia de un registro TLSA, Exchange Online aplicará el uso de TLS para enviar el correo electrónico, enviar el correo electrónico si el servidor de correo electrónico de destino admite TLS o quitar el correo electrónico y generar un NDR si el servidor de correo electrónico de destino no admite TLS.

En el registro TLSA de ejemplo, el campo Uso del certificado se establece en "3", por lo que los datos de asociación de certificados ('abc123... xyz789') solo coincidiría con el certificado del servidor de destino.

**Campo selector**: indica qué partes del certificado del servidor de destino se deben comprobar.

|Valor|Acrónimo|Descripción|
|---|---|---|
|0|Cert|Use el certificado completo.|
|1|SPKI (información de clave pública del asunto)|Use la clave pública del certificado y el algoritmo con el que se identifica la clave pública que se va a usar.|

En el registro TLSA de ejemplo, el campo selector se establece en "1", por lo que los datos de asociación de certificados se coincidirían con la clave pública del certificado de servidor de destino y el algoritmo con el que se identifica la clave pública que se va a usar.

**Campo de tipo coincidente**: indica el formato en el que se representará el certificado en el registro TLSA.

|Valor|Acrónimo|Descripción|
|---|---|---|
|0|Full|Los datos del registro TSLA son el certificado completo o SPKI.|
|1|SHA-256|Los datos del registro TSLA son un hash SHA-256 del certificado o spki.|
|2|SHA-512|Los datos del registro TSLA son un hash SHA-512 del certificado o spki.|

En el registro TLSA de ejemplo, el campo De tipo coincidente se establece en "1", por lo que los datos de asociación de certificados son un hash SHA-256 de la información de clave pública del firmante del certificado de servidor de destino.

**Datos de asociación de** certificados: especifica los datos de certificado que se usan para la coincidencia con el certificado de servidor de destino. Estos datos dependen del valor del campo selector y del valor de tipo coincidente.

En el registro TLSA de ejemplo, los datos de la asociación de certificados se establecen en 'abc123.. xyz789'. Dado que el valor campo selector del ejemplo se establece en "1", haría referencia a la clave pública del certificado de servidor de destino y al algoritmo que se identifica para usarlo con él. Y dado que el valor del campo Tipo de coincidencia del ejemplo se establece en "1", haría referencia al hash SHA-256 de la información de clave pública del firmante desde el certificado de servidor de destino.

## <a name="how-can-exchange-online-customers-use-smtp-dane-outbound"></a>¿Cómo pueden Exchange Online clientes usar SMTP DANE Outbound?

Como cliente Exchange Online, no es necesario hacer nada para configurar esta seguridad de correo electrónico mejorada para el correo electrónico saliente. Esto es algo que hemos creado para usted y está activado de forma predeterminada para todos los clientes Exchange Online y se usa cuando el dominio de destino anuncia el soporte para DANE. Para aprovechar las ventajas del envío de correo electrónico con comprobaciones DNSSEC y DANE, póngase en contacto con sus socios empresariales con los que intercambia correo electrónico que necesitan para implementar DNSSEC y DANE para que puedan recibir correo electrónico con estos estándares.

## <a name="how-can-exchange-online-customers-use-smtp-dane-inbound"></a>¿Cómo pueden Exchange Online clientes usar SMTP DANE entrante?

Actualmente, smtp dane entrante no se admite para Exchange Online. Se prevé que el soporte técnico se publique a finales de 2022.

## <a name="what-is-the-recommended-tlsa-record-configuration"></a>¿Cuál es la configuración de registro TLSA recomendada?

Según las instrucciones de implementación de RFC para SMTP DANE, se recomienda un registro TLSA compuesto por el campo Uso de certificado establecido en 3, el campo Selector establecido en 1 y el campo Tipo de coincidencia establecido en 1.

## <a name="exchange-online-mail-flow-with-smtp-dane"></a>Exchange Online correo Flow con SMTP DANE

El proceso de flujo de correo para Exchange Online con SMTP DANE, que se muestra en el diagrama de flujo siguiente, valida la seguridad del registro de dominio y recursos a través de DNSSEC, la compatibilidad con TLS en el servidor de correo de destino y que el certificado del servidor de correo de destino coincide con lo que se espera en función de su registro TLSA asociado.

Solo hay dos escenarios en los que un error SMTP DANE hará que el correo electrónico se bloquee:

- El dominio de destino señaló compatibilidad con DNSSEC, pero uno o más registros se devolvieron como autenticados.

- Todos los registros MX del dominio de destino tienen registros TLSA y ninguno de los certificados del servidor de destino coincide con lo esperado según los datos de registro de TSLA, o bien el servidor de destino no admite una conexión TLS.

:::image type="content" source="../media/compliance-trial/mail-flow-smtp-dane.png" alt-text="Exchange flujo de correo en línea con SMTP DANE" lightbox="../media/compliance-trial/mail-flow-smtp-dane.png":::

## <a name="related-technologies"></a>Tecnologías relacionadas

|Tecnología|Información adicional|
|---|---|
|**Agente de transferencia de correo: la seguridad de transporte estricta (MTA-STS)** ayuda a frustrar los ataques de degradación y man-in-the-middle proporcionando un mecanismo para establecer directivas de dominio que especifican si el servidor de correo electrónico de destino admite TLS y qué hacer cuando no se puede negociar TLS, por ejemplo, detener la transmisión.|Más información sobre la próxima compatibilidad de Exchange Online con MTA-STS entrante y saliente se publicará a finales de este año. <br/><br/> [noticias de transporte de Exchange Online de Microsoft Ignite 2020: Microsoft Tech Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-online-transport-news-from-microsoft-ignite-2020/ba-p/1687699) <br/><br/> [rfc8461 (ietf.org)](https://datatracker.ietf.org/doc/html/rfc8461)|
|**Sender Policy Framework (SPF)** usa información de IP para asegurarse de que los sistemas de correo electrónico de destino confían en los mensajes enviados desde el dominio personalizado.|[Cómo el Marco de directivas de remitente (SPF) evita la suplantación de identidad Office 365 Microsoft Docs](/microsoft-365/security/office-365-security/how-office-365-uses-spf-to-prevent-spoofing)|
|**DomainKeys Identified Mail (DKIM)** usa información de certificado X.509 para asegurarse de que los sistemas de correo electrónico de destino confían en los mensajes enviados salientes desde el dominio personalizado.|[Cómo usar DKIM para el correo electrónico en el dominio personalizado Office 365 Microsoft Docs](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email)|
|**La autenticación de mensajes basada en dominio, informes y conformidad (DMARC)** funciona con el marco de directivas de remitente y el correo identificado DomainKeys para autenticar a los remitentes de correo y asegurarse de que los sistemas de correo electrónico de destino confían en los mensajes enviados desde el dominio.|[Use DMARC para validar el correo electrónico, los pasos de configuración Office 365 Microsoft Docs](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)|

## <a name="troubleshooting-sending-emails-with-smtp-dane"></a>Solución de problemas de envío de correos electrónicos con SMTP DANE

Actualmente, hay cuatro códigos de error para DANE al enviar correos electrónicos con Exchange Online. Microsoft está actualizando activamente esta lista de códigos de error. Los errores serán visibles en:

1. El portal Exchange Centro de administración a través de la vista Detalles del seguimiento de mensajes.
2. NDR generados cuando no se envía un mensaje debido a un error DANE o DNSSEC.
3. Herramienta Analizador de conectividad [remota Analizador de conectividad remota de Microsoft](https://testconnectivity.microsoft.com/tests/o365).

|Código NDR|Descripción|
|---|---|
|5.7.321|starttls-not-supported: el servidor de correo de destino debe admitir TLS para recibir correo.|
|5.7.322|certificado expirado: el certificado del servidor de correo de destino ha expirado.|
|5.7.323|tlsa-invalid: error de validación dane del dominio.|
|5.7.324|dnssec-invalid: el dominio de destino devolvió registros DNSSEC no válidos.|

> [!NOTE]
> Actualmente, cuando un dominio indica que admite DNSSEC pero produce un error en las comprobaciones de DNSSEC, Exchange Online no genera el error 4/5.7.324 dnssec-invalid. Genera un error DNS genérico:
> 
> `4/5.4.312 DNS query failed`
> 
> Estamos trabajando activamente para solucionar esta limitación conocida. Si recibe esta instrucción de error, vaya al Analizador de conectividad remota de Microsoft y realice la prueba de validación dane en el dominio que generó el error 4/5.4.312. Los resultados mostrarán si se trata de un problema DNSSEC o de otro problema de DNS.

### <a name="troubleshooting-57321-starttls-not-supported"></a>Solución de problemas 5.7.321 starttls-not-supported

Esto suele indicar un problema con el servidor de correo de destino. Después de recibir el mensaje:

1. Compruebe que la dirección de correo electrónico de destino se especificó correctamente.
2. Alerte al administrador de correo electrónico de destino de que ha recibido este código de error para que pueda determinar si el servidor de destino está configurado correctamente para recibir mensajes mediante TLS.
3. Vuelva a intentar enviar el correo electrónico y revise los detalles del seguimiento del mensaje en el portal de Exchange Centro de administración.

### <a name="troubleshooting-57322-certificate-expired"></a>Solución de problemas de la expiración del certificado 5.7.322

Se debe presentar un certificado X.509 válido que no haya expirado al servidor de correo electrónico de envío. Los certificados X.509 deben renovarse después de su expiración, normalmente anualmente. Después de recibir el mensaje:

1. Alerte al administrador de correo electrónico de destino de que ha recibido este código de error y proporcione la cadena de código de error.
2. Permita que se renueve el certificado de servidor de destino y que el registro TLSA se actualice para hacer referencia al nuevo certificado. A continuación, vuelva a intentar enviar el correo electrónico y revise los detalles del seguimiento del mensaje en el portal de Exchange Admin Center.

### <a name="troubleshooting-57323-tlsa-invalid"></a>Solución de problemas 5.7.323 tlsa-invalid

Este código de error está relacionado con una configuración incorrecta del registro TLSA y solo se puede generar después de que se haya devuelto un registro TLSA auténtico de DNSSEC. Hay muchos escenarios durante la validación dane que se producen después de que se haya devuelto el registro que puede dar lugar a que se genere el código. Microsoft está trabajando activamente en los escenarios cubiertos por este código de error, de modo que cada escenario tenga un código específico. Actualmente, uno o varios de estos escenarios podrían provocar la generación del código de error:

1. El certificado del servidor de correo de destino no coincide con lo que se espera según el registro TLSA auténtico.
2. El registro TLSA auténtico está mal configurado.
3. Se está atacando el dominio de destino.
4. Cualquier otro error de DANE.

Después de recibir el mensaje:

1. Alerte al administrador de correo electrónico de destino de que ha recibido este código de error y proporcione la cadena de código de error.
2. Espere tiempo para que el administrador de correo electrónico de destino revise la configuración dane y la validez del certificado de servidor de correo electrónico. A continuación, vuelva a intentar enviar el correo electrónico y revise los detalles del seguimiento del mensaje en el portal de Exchange Admin Center.

### <a name="troubleshooting-57324-dnssec-invalid"></a>Solución de problemas 5.7.324 dnssec-invalid

Este código de error se genera cuando el dominio de destino indicaba que era DNSSEC-authentic, pero Exchange Online no pudo comprobarlo como DNSSEC-authentic.

Después de recibir el mensaje:

1. Alerte al administrador de correo electrónico de destino de que ha recibido este código de error y proporcione la cadena de código de error.
2. Espere tiempo para que el administrador de correo electrónico de destino revise la configuración de DNSSEC de su dominio. A continuación, vuelva a intentar enviar el correo electrónico y revise los detalles del seguimiento del mensaje en el portal de Exchange Admin Center.

## <a name="troubleshooting-receiving-emails-with-smtp-dane"></a>Solución de problemas de recepción de correos electrónicos con SMTP DANE

Actualmente, hay dos métodos que un administrador de un dominio receptor puede usar para validar y solucionar problemas de su configuración de DNSSEC y DANE para recibir correo electrónico de Exchange Online mediante estos estándares.

1. Adopción de TLS-RPT SMTP (informes de seguridad de la capa de transporte) introducido en [RFC8460](https://datatracker.ietf.org/doc/html/rfc8460)
2. Uso de la herramienta Analizador de conectividad remota [Del Analizador de conectividad remota de Microsoft](https://testconnectivity.microsoft.com/tests/o365)

TLS-RPT [https://datatracker.ietf.org/doc/html/rfc8460](https://datatracker.ietf.org/doc/html/rfc8460) es un mecanismo de informes para que los remitentes proporcionen detalles a los administradores de dominio de destino sobre los éxitos y errores de DANE y MTA-STS con esos dominios de destino respectivos. Para recibir informes TLS-RPT, solo tiene que agregar un registro TXT en los registros DNS del dominio que incluya la dirección de correo electrónico o el URI al que desea que se envíen los informes. Exchange Online enviará informes TLS-RPT en formato JSON.

Registro de ejemplo:

:::image type="content" source="../media/compliance-trial/example-record.png" alt-text="Registro de ejemplo" lightbox="../media/compliance-trial/example-record.png":::

El segundo método consiste en usar el [Analizador de conectividad remota Analizador de conectividad remota de Microsoft Remote Connectivity Analyzer](https://testconnectivity.microsoft.com/tests/o365), que puede realizar las mismas comprobaciones DNSSEC y DANE en la configuración de DNS que Exchange Online hará al enviar correo electrónico fuera del servicio. Esta es la forma más directa de solucionar errores en la configuración para recibir correo electrónico de Exchange Online mediante estos estándares.

Al solucionar problemas, se pueden generar los siguientes códigos de error:

|Código NDR|Descripción|
|---|---|
|4/5.7.321|starttls-not-supported: el servidor de correo de destino debe admitir TLS para recibir correo.|
|4/5.7.322|certificado expirado: el certificado del servidor de correo de destino ha expirado.|
|4/5.7.323|tlsa-invalid: error de validación dane del dominio.|
|4/5.7.324|dnssec-invalid: el dominio de destino devolvió registros DNSSEC no válidos.|

> [!NOTE]
> Actualmente, cuando un dominio indica que admite DNSSEC pero produce un error en las comprobaciones de DNSSEC, Exchange Online no genera el error 4/5.7.324 dnssec-invalid. Genera un error DNS genérico:
> 
> `4/5.4.312 DNS query failed`
> 
> Estamos trabajando activamente para solucionar esta limitación conocida. Si recibe esta instrucción de error, vaya al Analizador de conectividad remota de Microsoft y realice la prueba de validación dane en el dominio que generó el error 4/5.4.312. Los resultados mostrarán si se trata de un problema DNSSEC o de otro problema de DNS.

### <a name="troubleshooting-57321-starttls-not-supported"></a>Solución de problemas 5.7.321 starttls-not-supported

> [!NOTE]
> Estos pasos son para los administradores de correo electrónico que solucionan problemas al recibir correo electrónico de Exchange Online mediante SMTP DANE.

Esto suele indicar un problema con el servidor de correo de destino. Servidor de correo con el que el Analizador de conectividad remota está probando la conexión. Por lo general, hay dos escenarios que generan este código:

1. El servidor de correo de destino no admite la comunicación segura en absoluto y se debe usar la comunicación no cifrada sin formato.
2. El servidor de destino está configurado incorrectamente y omite el comando STARTTLS.

Después de recibir el mensaje:

1. Compruebe la dirección de correo electrónico.
2. Busque la dirección IP asociada a la instrucción de error para que pueda identificar el servidor de correo al que está asociada la instrucción.
3. Compruebe la configuración del servidor de correo para asegurarse de que está configurado para escuchar el tráfico SMTP (normalmente los puertos 25 y 587).
4. Espere unos minutos y vuelva a intentar la prueba con la herramienta Analizador de conectividad remota.
5. Si todavía se produce un error, intente quitar el registro TLSA y vuelva a ejecutar la prueba con la herramienta Analizador de conectividad remota.
6. Si no hay errores, esto puede indicar que el servidor de correo que usa para recibir correo no admite STARTTLS y es posible que tenga que actualizar a uno que lo haga para usar DANE.

### <a name="troubleshooting-57322-certificate-expired"></a>Solución de problemas de la expiración del certificado 5.7.322

> [!NOTE]
> Estos pasos son para los administradores de correo electrónico que solucionan problemas al recibir correo electrónico de Exchange Online mediante SMTP DANE.

Se debe presentar un certificado X.509 válido que no haya expirado al servidor de correo electrónico de envío. Los certificados X.509 deben renovarse después de su expiración, normalmente anualmente. Después de recibir el mensaje:

1. Compruebe la dirección IP asociada a la instrucción de error para que pueda identificar el servidor de correo al que está asociado. Busque el certificado expirado en el servidor de correo electrónico que identificó.
2. Inicie sesión en el sitio web del proveedor de certificados.
3. Seleccione el certificado expirado y siga las instrucciones para renovar y pagar por la renovación.
4. Una vez que el proveedor haya comprobado la compra, puede descargar un nuevo certificado.
5. Instale el certificado renovado en su servidor de correo asociado.
6. Actualice el registro TLSA asociado del servidor de correo con los datos del nuevo certificado.
7. Después de esperar una cantidad de tiempo adecuada, vuelva a intentar la prueba con la herramienta Analizador de conectividad remota.

### <a name="troubleshooting-57323-tlsa-invalid"></a>Solución de problemas 5.7.323 tlsa-invalid

> [!NOTE]
> Estos pasos son para los administradores de correo electrónico que solucionan problemas al recibir correo electrónico de Exchange Online mediante SMTP DANE.

Este código de error está relacionado con una configuración incorrecta del registro TLSA y solo se puede generar después de que se haya devuelto un registro TSLA auténtico de DNSSEC. Sin embargo, hay muchos escenarios durante la validación dane que se producen después de que se haya devuelto el registro que puede dar lugar a que se genere el código. Microsoft está trabajando activamente en los escenarios cubiertos por este código de error, de modo que cada escenario tenga un código específico. Actualmente, uno o varios de estos escenarios podrían provocar la generación del código de error:

1. El registro TLSA auténtico está mal configurado.
2. El certificado aún no es válido o configurado para un período de tiempo futuro.
3. El dominio de destino está siendo atacado.
4. Cualquier otro error de DANE.

Después de recibir el mensaje:

1. Compruebe la dirección IP asociada a la instrucción de error para identificar el servidor de correo al que está asociado.
2. Identifique el registro TLSA asociado al servidor de correo identificado.
3. Compruebe la configuración del registro TLSA para asegurarse de que indica al remitente que realice las comprobaciones DANE preferidas y que los datos de certificado correctos se han incluido en el registro TLSA.
    1. Si tiene que realizar actualizaciones en el registro en busca de discrepancias, espere unos minutos y vuelva a ejecutar la prueba con la herramienta Analizador de conectividad remota.
4. Busque el certificado en el servidor de correo identificado.
5. Compruebe la ventana de tiempo para la que el certificado es válido. Si se establece para iniciar la validez en una fecha futura, debe renovarse para la fecha actual.
    1. Inicie sesión en el sitio web del proveedor de certificados.
    2. Seleccione el certificado expirado y siga las instrucciones para renovar y pagar por la renovación.
    3. Una vez que el proveedor haya comprobado la compra, puede descargar un nuevo certificado.
    4. Instale el certificado renovado en su servidor de correo asociado.

### <a name="troubleshooting-57324-dnssec-invalid"></a>Solución de problemas 5.7.324 dnssec-invalid

> [!NOTE]
> Estos pasos son para los administradores de correo electrónico que solucionan problemas al recibir correo electrónico de Exchange Online mediante SMTP DANE.

Este código de error se genera cuando el dominio de destino indica que es DNSSEC-authentic, pero Exchange Online no puede comprobarlo como DNSSEC-authentic. Esta sección no será completa para solucionar problemas de DNSSEC y se centra en escenarios en los que los dominios pasaron anteriormente la autenticación DNSSEC, pero no ahora.

Después de recibir el mensaje:

1. Si usa un proveedor dns, por ejemplo GoDaddy, alerte al proveedor de DNS del error para que puedan trabajar en la solución de problemas y el cambio de configuración.
2. Si va a administrar su propia infraestructura DNSSEC, hay muchas configuraciones incorrectas de DNSSEC que pueden generar este mensaje de error. Algunos problemas comunes para comprobar si la zona estaba pasando previamente la autenticación DNSSEC:
    1. Cadena de confianza rota, cuando la zona primaria contiene un conjunto de registros DS que apuntan a algo que no existe en la zona secundaria. Esto hace que la zona secundaria se marque como falsa mediante la validación de solucionadores.
        - Para resolverlo, revise los identificadores de clave de RRSIG de los dominios secundarios y asegúrese de que coinciden con los identificadores de clave de los registros DS publicados en la zona primaria.
    2. El registro de recursos de RRSIG para el dominio no es válido, ha expirado o su período de validez no ha comenzado.
        - Para resolverlo, genere nuevas firmas para el dominio mediante intervalos de tiempo válidos.

## <a name="frequently-asked-questions"></a>preguntas más frecuentes

### <a name="as-an-exchange-online-customer-can-i-opt-out-of-using-dnssec-andor-dane"></a>Como cliente Exchange Online, ¿puedo dejar de usar DNSSEC o DANE?

Creemos firmemente que DNSSEC y DANE aumentarán significativamente la posición de seguridad de nuestro servicio y beneficiarán a todos nuestros clientes. Hemos trabajado diligentemente durante el último año para reducir el riesgo y la gravedad del posible impacto que esta implementación podría tener para los clientes de M365. Supervisaremos y realizaremos un seguimiento activo de la implementación para garantizar que el impacto negativo se minimice a medida que se implemente. Por este motivo, las excepciones de nivel de inquilino o la exclusión no estarán disponibles.
Si experimenta algún problema relacionado con la habilitación de DNSSEC o DANE, los diferentes métodos para investigar los errores anotados en este documento le ayudarán a identificar el origen del error. En la mayoría de los casos, el problema será con la parte de destino externa y deberá comunicarse con estos asociados empresariales que necesitan configurar correctamente DNSSEC y DANE para recibir correo electrónico de Exchange Online mediante estos estándares.

### <a name="how-does-dnssec-relate-to-dane"></a>¿Cómo se relaciona DNSSEC con DANE?

DNSSEC agrega una capa de confianza a la resolución DNS aprovechando la infraestructura de clave pública para garantizar que los registros devueltos en respuesta a una consulta DNS sean auténticos. DANE garantiza que el servidor de correo receptor sea el servidor de correo legítimo y esperado para el registro MX auténtico.

### <a name="what-is-the-difference-between-mta-sts-and-dane-for-smtp"></a>¿Cuál es la diferencia entre MTA-STS y DANE para SMTP?

DANE y MTA-STS cumplen el mismo propósito, pero DANE requiere DNSSEC para la autenticación DNS, mientras que MTA-STS se basa en entidades de certificación.

### <a name="why-isnt-opportunistic-tls-sufficient"></a>¿Por qué tls oportunista no es suficiente?

TLS oportunista cifrará la comunicación entre dos puntos de conexión si ambos aceptan admitirla. Sin embargo, incluso si TLS cifra la transmisión, un dominio podría suplantarse durante la resolución DNS, de modo que apunte al punto de conexión de un actor malintencionado en lugar del punto de conexión real para el dominio. Se trata de una brecha en la seguridad del correo electrónico que se soluciona mediante la implementación de MTA-STS o SMTP DANE con DNSSEC.

### <a name="why-isnt-dnssec-sufficient"></a>¿Por qué DNSSEC no es suficiente?

DNSSEC no es totalmente resistente a los ataques man-in-the-middle y a los ataques de degradación (de TLS a texto no cifrado) para escenarios de flujo de correo. La adición de MTA-STS y DANE junto con DNSSEC proporciona un método de seguridad completo para frustrar los ataques MITM y de degradación.

## <a name="additional-links"></a>Vínculos adicionales

[Buscar y corregir problemas después de agregar el dominio o los registros DNS](/microsoft-365/admin/get-help-with-domains/find-and-fix-issues)

[Introducción a la | DNSSEC Microsoft Docs](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj200221(v=ws.11))

[Uso de DMARC para validar el correo electrónico y los pasos de configuración: Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)

[Cómo usar DKIM para el correo electrónico en el dominio personalizado: Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email)

[Cómo el marco de directivas de remitente (SPF) impide la suplantación de identidad: Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/how-office-365-uses-spf-to-prevent-spoofing)

[noticias de transporte de Exchange Online de Microsoft Ignite 2020: Microsoft Tech Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-online-transport-news-from-microsoft-ignite-2020/ba-p/1687699)

[rfc8461 (ietf.org)](https://datatracker.ietf.org/doc/html/rfc8461)
