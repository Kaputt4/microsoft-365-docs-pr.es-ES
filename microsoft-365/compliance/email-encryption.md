---
title: Cifrado de correo electrónico en Microsoft 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
ms.collection:
- purview-compliance
- tier1
- m365solution-mip
- m365initiative-compliance
- highpri
description: Compare las opciones de cifrado de Microsoft 365, incluido el Cifrado de mensajes de Microsoft Purview, S/MIME e Information Rights Management (IRM), y obtenga más información sobre la Seguridad de capa de transporte (TLS).
ms.openlocfilehash: df17096146308c2f391653bc5013f66128bea91a
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68634704"
---
# <a name="email-encryption"></a>Cifrado de correo electrónico

Este articulo compara las opciones de cifrado en Microsoft 365, incluido el Cifrado de mensajes de Microsoft Purview, S/MIME e Information Rights Management (IRM), y presenta la Seguridad de capa de transporte (TLS).
  
Microsoft 365 le ofrece varias opciones de cifrado para ayudar a satisfacer las necesidades que tiene su empresa para la seguridad del correo electrónico. Este artículo contiene tres formas de cifrar el correo electrónico en Office 365. Si quiere obtener más información acerca de todas las características de seguridad en Office 365, visite el [Centro de confianza de Office 365](https://go.microsoft.com/fwlink/p/?LinkID=282470). Este artículo presenta los tres tipos de cifrado disponibles para los administradores de Microsoft 365 con el propósito de ayudar a proteger el correo electrónico en Office 365:
  
- Cifrado de mensajes de Microsoft Purview.

- Extensiones seguras multipropósito al correo de Internet (S/MIME).

- Information Rights Management (IRM).

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="how-microsoft-365-uses-email-encryption"></a>Cómo Microsoft 365 usa el cifrado de correo electrónico

Encryption is the process by which information is encoded so that only an authorized recipient can decode and consume the information. Microsoft 365 uses encryption in two ways: in the service, and as a customer control. In the service, encryption is used in Microsoft 365 by default; you don't have to configure anything. For example, Microsoft 365 uses Transport Layer Security (TLS) to encrypt the connection, or session, between two servers. 
  
Así es cómo funciona normalmente el cifrado de correo electrónico:
  
- Un mensaje está cifrado, o se transforma de texto sin formato en texto cifrado ilegible, ya sea en el equipo del remitente, o mediante un servidor central mientras el mensaje está en tránsito.

- El mensaje permanece como texto cifrado mientras está en tránsito para protegerlo y que no sea leído en caso de que se intercepte.

- Cuando el destinatario recibe el mensaje, este se transforma nuevamente en texto sin formato legible de una de estas dos maneras:

  - El equipo del destinatario usa una clave para descifrar el mensaje, o

  - Un servidor central descifra el mensaje en nombre del destinatario, después de validar la identidad del destinatario.

Para obtener más información sobre cómo Microsoft 365 protege la comunicación entre servidores, entre organizaciones dentro de Microsoft 365 o entre Microsoft 365 y un socio comercial de confianza fuera de Microsoft 365, puede consultar [Cómo Exchange Online usa TLS para proteger las conexiones de correo electrónico en Office 365](exchange-online-uses-tls-to-secure-email-connections.md).
    
## <a name="comparing-email-encryption-options-available-in-office-365"></a>Comparación de las opciones de cifrado de correo electrónico disponibles en Office 365 

|Tecnología de cifrado de correo electrónico|![Ilustración conceptual que describe OME.](../media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)|![Ilustración conceptual que describe IRM](../media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)|![Ilustración conceptual que describe SMIME](../media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)|
|:-----|:-----|:-----|:-----|
|¿Qué es?|El cifrado de mensajes es un servicio basado en Azure Rights Management (Azure RMS) que permite enviar correo electrónico cifrado a otras personas dentro o fuera de la organización, independientemente de la dirección de correo electrónico de destino (Gmail, Yahoo! Mail, Outlook.com, etc.). <br/> As an admin, you can set up transport rules that define the conditions for encryption. When a user sends a message that matches a rule, encryption is applied automatically. <br/> To view encrypted messages, recipients can either get a one-time passcode, sign in with a Microsoft account, or sign in with a work or school account associated with Office 365. Recipients can also send encrypted replies. They don't need a Microsoft 365 subscription to view encrypted messages or send encrypted replies.|IRM is an encryption solution that also applies usage restrictions to email messages. It helps prevent sensitive information from being printed, forwarded, or copied by unauthorized people. <br/> Las capacidades IRM de Microsoft 365 usan Azure Rights Management (Azure RMS).|S/MIME is a certificate-based encryption solution that allows you to both encrypt and digitally sign a message. The message encryption helps ensure that only the intended recipient can open and read the message. A digital signature helps the recipient validate the identity of the sender. <br/> Las firmas digitales y el cifrado de mensajes son posibles gracias al uso exclusivo de certificados digitales que contienen las claves para comprobar las firmas digitales y cifrar o descifrar mensajes. <br/> To use S/MIME, you must have public keys on file for each recipient. Recipients have to maintain their own private keys, which must remain secure. If a recipient's private keys are compromised, the recipient needs to get a new private key and redistribute public keys to all potential senders.|
|¿Qué hace?|OME: <br/> Cifra los mensajes enviados a destinatarios internos o externos. <br/>  Allows users to send encrypted messages to any email address, including Outlook.com, Yahoo! Mail, and Gmail. <br/>  Le permite, como administrador, personalizar el portal de visualización de correo electrónico para reflejar la marca de su organización. <br/> Microsoft administra y almacena de forma segura las claves, por lo que no es necesario que usted lo haga. <br/> No se necesita ningún software de cliente especial siempre y cuando el mensaje cifrado (enviado como datos adjuntos HTML) pueda abrirse en un explorador.|IRM: <br/> Usa cifrado y restricciones de uso para proporcionar protección en línea y sin conexión para los mensajes de correo electrónico y datos adjuntos. <br/> Ofrece, como administrador, la capacidad de configurar reglas de transporte o reglas de protección de Outlook para aplicar automáticamente IRM a mensajes seleccionados. <br/> Le permite a los usuarios aplicar plantillas manualmente en Outlook o en Outlook en la Web (anteriormente denominado Outlook Web App).|S/MIME aborda la autenticación de remitentes con firmas digitales y la confidencialidad de mensajes con cifrado.|
|¿Qué no hace?|OME doesn't let you apply usage restrictions to messages. For example, you can't use it to stop a recipient from forwarding or printing an encrypted message.|Some applications may not support IRM emails on all devices. For more information about these and other products that support IRM email, see [Client device capabilities](/azure/information-protection/requirements#BKMK_ClientCapabilities).|S/MIME no permite analizar los mensajes cifrados en búsqueda de malware, correo no deseado o directivas.|
|Recomendaciones y escenarios de ejemplo|We recommend using OME when you want to send sensitive business information to people outside your organization, whether they're consumers or other businesses. For example:  <br/>  Un empleado bancario que envía extractos de tarjeta de crédito a los clientes  <br/>  Un consultorio que envía registros médicos a un paciente  <br/>  Un abogado que envía información legal confidencial a otro abogado|We recommend using IRM when you want to apply usage restrictions as well as encryption. For example:  <br/>  Un administrador que envía detalles confidenciales a su equipo sobre un nuevo producto aplica la opción “No reenviar”.  <br/>  Un ejecutivo necesita compartir una propuesta de oferta con otra compañía, que incluye datos adjuntos de un socio que usa Office 365, y requieren que el correo electrónico y los datos adjuntos estén protegidos.|Se recomienda usar S/MIME cuando su organización o la organización del destinatario requieran un auténtico cifrado de punto a punto.  <br/>  Normalmente se usa S/MIME en los siguientes escenarios:  <br/>  Autoridades gubernamentales que se comunican con otras autoridades gubernamentales  <br/>  Una empresa que se comunica con una autoridad gubernamental|
||

## <a name="what-encryption-options-are-available-for-my-microsoft-365-subscription"></a>¿Qué opciones de cifrado están disponibles para mi suscripción de Microsoft 365?

For information about email encryption options for your Microsoft 365 subscription see the [Exchange Online service description](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Here, you can find information about the following encryption features:
  
- Azure RMS, incluidas las funcionalidades de IRM y el Cifrado de mensajes de Microsoft Purview

- S/MIME

- TLS

- Cifrado de datos en reposo (mediante BitLocker)

También puede usar herramientas de cifrado de terceros con Microsoft 365, por ejemplo, PGP (Pretty Good Privacy). Microsoft 365 no admite PGP/MIME y solo se puede usar PGP/Inline para enviar y recibir correos electrónicos cifrados con PGP.

## <a name="what-about-encryption-for-data-at-rest"></a>¿Qué sucede con el cifrado de datos en reposo?

"Data at rest" refers to data that isn't actively in transit. In Microsoft 365, email data at rest is encrypted using BitLocker Drive Encryption. BitLocker encrypts the hard drives in Microsoft datacenters to provide enhanced protection against unauthorized access. To learn more, see [BitLocker Overview](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831713(v=ws.11)).
  
## <a name="more-information-about-email-encryption-options"></a>Más información sobre opciones de cifrado de correo electrónico

Para obtener más información sobre las opciones de cifrado de correo electrónico en este artículo, así como TLS, consulte los siguientes artículos:
  
**Cifrado de mensajes de Microsoft Purview**
  
[Cifrado de mensajes](ome.md)
  
**IRM**
  
[Information Rights Management en Exchange Online](./information-rights-management-in-exchange-online.md)
  
[¿Qué es Azure Rights Management?](/azure/information-protection/what-is-azure-rms)
  
**S/MIME**
  
[S/MIME para la firma y cifrado de mensajes](/Exchange/policy-and-compliance/smime/smime)
  
[Información sobre S/MIME](/previous-versions/tn-archive/aa995740(v=exchg.65))
  
[Descripción de la criptografía mediante claves públicas](/previous-versions/tn-archive/aa998077(v=exchg.65)) 
  
**TLS**
  
[Configurar un flujo de correo personalizado mediante conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
