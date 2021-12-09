---
title: Cómo Exchange Online seguridad de la capa de transporte (TLS) para proteger las conexiones de correo electrónico
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
- M365-security-compliance
- Strat_O365_IP
description: Obtenga información sobre Exchange Online y Microsoft 365 seguridad de la capa de transporte (TLS) y el secreto de reenvío (FS) para proteger las comunicaciones de correo electrónico. Obtenga también información sobre el certificado emitido por Microsoft para Exchange Online.
ms.openlocfilehash: 1caf4a8425f4a8e7c340e8a52d785027e99a1618
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2021
ms.locfileid: "61371501"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>Cómo Exchange Online usa TLS para proteger las conexiones del correo electrónico

Obtenga información sobre Exchange Online y Microsoft 365 seguridad de la capa de transporte (TLS) y el secreto de reenvío (FS) para proteger las comunicaciones de correo electrónico. También proporciona información sobre el certificado emitido por Microsoft para Exchange Online.
  
## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>Conceptos básicos de TLS Microsoft 365 y Exchange Online

TLS (Seguridad de la capa de transporte) y SSL (antecesor de TLS) son protocolos criptográficos que protegen la comunicación por red con certificados de seguridad que cifran una conexión entre equipos. TLS reemplaza la capa de sockets seguros (SSL) y a menudo se conoce como SSL 3.1. Exchange Online TLS para cifrar las conexiones entre servidores Exchange y las conexiones entre servidores Exchange y otros servidores, como los servidores Exchange locales o los servidores de correo de los destinatarios. Una vez cifrada la conexión, todos los datos enviados a través de esa conexión se envían a través del canal cifrado. Sin embargo, si reenvía un mensaje que se envió a través de una conexión cifrada por TLS, ese mensaje no está necesariamente cifrado. TLS no cifra el mensaje, solo la conexión.
  
Si desea cifrar el mensaje, use una tecnología de cifrado que cifre el contenido del mensaje. Por ejemplo, puede usar Office cifrado de mensajes o S/MIME. Vea [Cifrado de correo electrónico en Office 365](email-encryption.md) y Cifrado de mensajes de Office 365 [(OME)](ome.md) para obtener información sobre el cifrado de mensajes en Office 365.
  
Use TLS en situaciones en las que desee configurar un canal seguro de correspondencia entre Microsoft y su organización local u otra organización, como un partner. Exchange Online intenta usar TLS primero para proteger el correo electrónico, pero no puede hacerlo si la otra parte no ofrece seguridad TLS. Siga leyendo para obtener información sobre cómo proteger todo el correo que va a los servidores locales o a asociados importantes con *conectores*.

Para proporcionar el mejor cifrado de su clase a nuestros clientes, Microsoft ha dejado de usar las versiones 1.0 y 1.1 de seguridad de la capa de transporte (TLS) en [Office 365](tls-1.0-and-1.1-deprecation-for-office-365.md) y [Office 365 GCC](tls-1-2-in-office-365-gcc.md). Sin embargo, puede seguir usando una conexión SMTP sin cifrar sin TLS. No recomendamos la transmisión de correo electrónico sin cifrado.  
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Empleo de TLS por parte de Exchange Online entre clientes de Exchange Online

Exchange Online siempre cifran las conexiones a otros servidores Exchange Online en nuestros centros de datos con TLS 1.2. Cuando envía un mensaje a un destinatario que está dentro de su organización, Exchange Online envía automáticamente el mensaje a través de una conexión cifrada mediante TLS. Exchange Online también envía correo electrónico que envía a otros clientes a través de conexiones cifradas mediante TLS protegidas mediante el secreto de reenvío.
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>Cómo Microsoft 365 TLS entre socios Microsoft 365 externos y de confianza

De forma predeterminada, Exchange Online siempre usa *TLS oportunista*. TLS oportunista significa que Exchange Online siempre intenta cifrar las conexiones con la versión más segura de TLS primero y, a continuación, trabaja en la lista de cifrados TLS hasta encontrar una en la que ambas partes puedan estar de acuerdo. A menos que haya configurado Exchange Online para asegurarse de que los mensajes a ese destinatario deben usar conexiones seguras, el mensaje se enviará de forma predeterminada sin cifrado si la organización de destinatarios no admite el cifrado TLS. TLS oportunista es suficiente para la mayoría de las empresas. Pero en las empresas que tienen requisitos de cumplimiento, como organizaciones médicas, bancarias o gubernamentales, puede configurar Exchange Online para que exija o fuerce TLS. Para obtener instrucciones, vea [Configure mail flow using connectors in Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).
  
Si decide configurar TLS entre su organización y una organización asociada de confianza, Exchange Online puede usar *TLS forzado* para crear canales de comunicación de confianza. TLS forzada requiere que la organización asociada se autentique Exchange Online con un certificado de seguridad para enviarle correo. Su partner tendrá que administrar sus propios certificados. Exchange Online conectores para proteger los mensajes que envía de acceso no autorizado antes de que lleguen al proveedor de correo electrónico del destinatario. Para obtener información sobre el uso de conectores para configurar el flujo de correo, vea [Configure mail flow using connectors in Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS e implementaciones híbridas de Exchange Server

Si está administrando una implementación híbrida de Exchange, el servidor de Exchange local debe autenticarse en Microsoft 365 mediante un certificado de seguridad para enviar correo a destinatarios cuyos buzones solo están en Office 365. Como resultado, debe administrar sus propios certificados de seguridad para los servidores Exchange locales. También tiene que almacenar y mantener de forma segura estos certificados de servidor. Para obtener más información acerca de la administración de certificados en implementaciones híbridas, vea [Certificate requirements for hybrid deployments](/exchange/certificate-requirements).
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Configurar TLS forzado para Exchange Online en Office 365

En el caso de los clientes de Exchange Online, para que TLS forzado pueda proteger todo el correo electrónico enviado y recibido, es necesario configurar más de un conector que exija TLS. Necesitará un conector para los mensajes enviados a buzones de usuario y otro conector para los mensajes enviados desde buzones de usuario. Cree esos conectores en el Centro de administración de Exchange en Office 365. Para obtener instrucciones, vea [Configure mail flow using connectors in Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

## <a name="tls-certificate-information-for-exchange-online"></a>Información de certificado TLS para Exchange Online

En la tabla siguiente se describe la información del certificado usada por Exchange Online. Si su socio comercial está configurando TLS forzada en su servidor de correo electrónico, tendrá que proporcionarles esta información. Por motivos de seguridad, nuestros certificados cambian de vez en cuando. El certificado actual es válido desde el 24 de septiembre de 2020.

### <a name="current-certificate-information-valid-from-september-24-2020"></a>Información de certificado actual válida desde el 24 de septiembre de 2020
  
| Atributo | Valor |
|:-----|:-----|
|Emisor raíz de la autoridad de certificado|DigiCert CA – 1|
|Nombre del certificado|mail.protection.outlook.com|
|Organización|Microsoft Corporation|
|Unidad de organización|www.digicert.com|
|Nivel de la clave de certificado|2048|

## <a name="get-more-information-about-tls-certificates-and-microsoft-365-and-download-certificates"></a>Obtenga más información sobre TLS, certificados y Microsoft 365 y descargar certificados

[Microsoft 365 cadenas de cifrado y descargas de certificados](encryption-office-365-certificate-chains.md)

[Microsoft 365 cadenas de cifrado y descargas de certificados: DOD y GCC High](encryption-office-365-certificate-chains-itar.md)

Para obtener una lista de conjuntos de cifrado admitidos, vea [Technical reference details about encryption](technical-reference-details-about-encryption.md).
  
[Configurar conectores para flujo de correo seguro con una organización asociada](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)
  
[Conectores con seguridad mejorada de correo electrónico](/previous-versions/exchange-server/exchange-150/dn942516(v=exchg.150))
  
[Cifrado en Microsoft 365](encryption.md)
