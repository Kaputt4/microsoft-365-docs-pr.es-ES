---
title: Cómo Exchange Online usa TLS para proteger las conexiones del correo electrónico
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/08/2021
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
ms.collection:
- purview-compliance
- tier1
description: Obtenga información sobre cómo Exchange Online y Microsoft 365 usan seguridad de la capa de transporte (TLS) y secreto de reenvío (FS) para proteger las comunicaciones por correo electrónico. Obtenga también información sobre el certificado emitido por Microsoft para Exchange Online.
ms.openlocfilehash: 1b3133cd9111531efa10f18cad15556fd4833a80
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68626564"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>Cómo Exchange Online usa TLS para proteger las conexiones del correo electrónico

Obtenga información sobre cómo Exchange Online y Microsoft 365 usan seguridad de la capa de transporte (TLS) y secreto de reenvío (FS) para proteger las comunicaciones por correo electrónico. También proporciona información sobre el certificado emitido por Microsoft para Exchange Online.
  
[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>Conceptos básicos de TLS para Microsoft 365 y Exchange Online

TLS (Seguridad de la capa de transporte) y SSL (antecesor de TLS) son protocolos criptográficos que protegen la comunicación por red con certificados de seguridad que cifran una conexión entre equipos. TLS reemplaza a Capa de sockets seguros (SSL) y a menudo se conoce como SSL 3.1. Exchange Online usa TLS para cifrar las conexiones entre los servidores de Exchange y las conexiones entre los servidores de Exchange y otros servidores, como los servidores de Exchange locales o los servidores de correo de los destinatarios. Una vez cifrada la conexión, todos los datos enviados a través de esa conexión se envían a través del canal cifrado. Sin embargo, si reenvía un mensaje que se envió a través de una conexión cifrada con TLS a una organización de destinatarios que no admite el cifrado TLS, ese mensaje no se cifra necesariamente. TLS no cifra el mensaje, solo la conexión.
  
Si desea cifrar el mensaje, use una tecnología de cifrado que cifre el contenido del mensaje. Por ejemplo, puede usar Cifrado de mensajes de Microsoft Purview o S/MIME. Consulte [Email cifrado en Office 365](email-encryption.md) y [Cifrado](ome.md) de mensajes para obtener información sobre el cifrado de mensajes en Office 365.
  
Use TLS en situaciones en las que quiera configurar un canal seguro de correspondencia entre Microsoft y su organización local u otra organización, como un asociado. Exchange Online siempre intenta usar TLS primero para proteger el correo electrónico, pero no puede hacerlo si la otra parte no ofrece seguridad TLS. Siga leyendo para obtener información sobre cómo proteger todo el correo que va a los servidores locales o a asociados importantes con *conectores*.

Para proporcionar el mejor cifrado de su clase a nuestros clientes, Microsoft ha dejado de usar las versiones 1.0 y 1.1 de seguridad de la capa de transporte (TLS) en [Office 365](tls-1.0-and-1.1-deprecation-for-office-365.md) y [Office 365 GCC](tls-1-2-in-office-365-gcc.md). Sin embargo, puede seguir usando una conexión SMTP sin cifrar sin tls. No se recomienda la transmisión de correo electrónico sin cifrado.  
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Empleo de TLS por parte de Exchange Online entre clientes de Exchange Online

Exchange Online servidores siempre cifran las conexiones a otros servidores de Exchange Online en nuestros centros de datos con TLS 1.2. Al enviar un mensaje a un destinatario que se encuentra dentro de su organización, Exchange Online envía automáticamente el mensaje a través de una conexión cifrada mediante TLS. Exchange Online también envía un correo electrónico que envía a otros clientes a través de conexiones cifradas mediante TLS que se protegen mediante el secreto de reenvío.
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>Cómo Microsoft 365 usa TLS entre Microsoft 365 y asociados externos de confianza

De forma predeterminada, Exchange Online siempre usa *TLS oportunista*. TLS oportunista significa que Exchange Online siempre intenta cifrar las conexiones con la versión más segura de TLS primero y, a continuación, funciona en su camino hacia abajo en la lista de cifrados TLS hasta que encuentra uno en el que ambas partes pueden estar de acuerdo. A menos que haya configurado Exchange Online para asegurarse de que los mensajes a ese destinatario deben usar conexiones seguras, el mensaje se enviará de forma predeterminada sin cifrado si la organización del destinatario no admite el cifrado TLS. TLS oportunista es suficiente para la mayoría de las empresas. Pero en las empresas que tienen requisitos de cumplimiento, como organizaciones médicas, bancarias o gubernamentales, puede configurar Exchange Online para que exija o fuerce TLS. Para obtener instrucciones, consulte [Configuración del flujo de correo mediante conectores en Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).
  
Si decide configurar TLS entre su organización y una organización asociada de confianza, Exchange Online puede usar *TLS forzado* para crear canales de comunicación de confianza. TLS forzado requiere que la organización asociada se autentique para Exchange Online con un certificado de seguridad para enviarle correo. El asociado tendrá que administrar sus propios certificados. Exchange Online usa conectores para proteger los mensajes que se envían desde el acceso no autorizado antes de que lleguen al proveedor de correo electrónico del destinatario. Para obtener información sobre el uso de conectores para configurar el flujo de correo, consulte [Configuración del flujo de correo mediante conectores en Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS e implementaciones híbridas de Exchange Server

Si va a administrar una implementación híbrida de Exchange, el servidor exchange local debe autenticarse en Microsoft 365 mediante un certificado de seguridad para enviar correo a los destinatarios cuyos buzones solo están en Office 365. Como resultado, debe administrar sus propios certificados de seguridad para los servidores de Exchange locales. También tiene que almacenar y mantener de forma segura estos certificados de servidor. Para obtener más información sobre cómo administrar certificados en implementaciones híbridas, consulte [Requisitos de certificados para implementaciones híbridas](/exchange/certificate-requirements).
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Configurar TLS forzado para Exchange Online en Office 365

En el caso de los clientes de Exchange Online, para que TLS forzado pueda proteger todo el correo electrónico enviado y recibido, es necesario configurar más de un conector que exija TLS. Necesitará un conector para los mensajes enviados a los buzones de usuario y otro conector para los mensajes enviados desde buzones de usuario. Cree esos conectores en el Centro de administración de Exchange en Office 365. Para obtener instrucciones, consulte [Configuración del flujo de correo mediante conectores en Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

## <a name="tls-certificate-information-for-exchange-online"></a>Información de certificado TLS para Exchange Online

En la tabla siguiente se describe la información del certificado usada por Exchange Online. Si el asociado de negocios está configurando TLS forzado en su servidor de correo electrónico, tendrá que proporcionarle esta información. Por motivos de seguridad, nuestros certificados cambian de vez en cuando. El certificado actual es válido desde el 24 de septiembre de 2020.

### <a name="current-certificate-information-valid-from-september-24-2020"></a>Información de certificado actual válida desde el 24 de septiembre de 2020
  
| Atributo | Valor |
|:-----|:-----|
|Emisor raíz de la autoridad de certificado|Ca de DigiCert: 1|
|Nombre del certificado|mail.protection.outlook.com|
|Organización|Microsoft Corporation|
|Unidad de organización|www.digicert.com|
|Nivel de la clave de certificado|2048|

## <a name="get-more-information-about-tls-certificates-and-microsoft-365-and-download-certificates"></a>Obtenga más información sobre TLS, certificados y Microsoft 365 y descargue certificados.

[Cadenas de cifrado y descargas de certificados de Microsoft 365](encryption-office-365-certificate-chains.md)

[Cadenas de cifrado y descargas de certificados de Microsoft 365: DOD y GCC High](encryption-office-365-certificate-chains-itar.md)

Para obtener una lista de conjuntos de cifrado admitidos, consulte [Detalles de referencia técnica sobre el cifrado](technical-reference-details-about-encryption.md).
  
[Configurar conectores para flujo de correo seguro con una organización asociada](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)
  
[Conectores con seguridad mejorada de correo electrónico](/previous-versions/exchange-server/exchange-150/dn942516(v=exchg.150))
  
[Cifrado en Microsoft 365](encryption.md)
