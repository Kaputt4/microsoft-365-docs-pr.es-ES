---
title: Cómo Exchange Online usa TLS para proteger las conexiones del correo electrónico
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Obtenga información sobre cómo Exchange Online y Microsoft 365 usan seguridad de la capa de transporte (TLS) y secreto de reenvío (FS) para proteger las comunicaciones de correo electrónico. Obtenga también información sobre el certificado emitido por Microsoft para Exchange Online.
ms.openlocfilehash: 67be87bc07399af9469728383af1caf604bf1372
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066833"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>Cómo Exchange Online usa TLS para proteger las conexiones del correo electrónico

Obtenga información sobre cómo Exchange Online y Microsoft 365 usan seguridad de la capa de transporte (TLS) y secreto de reenvío (FS) para proteger las comunicaciones de correo electrónico. También proporciona información sobre el certificado emitido por Microsoft para Exchange Online.
  
## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>Conceptos básicos de TLS para Microsoft 365 y Exchange Online

TLS (Seguridad de la capa de transporte) y SSL (antecesor de TLS) son protocolos criptográficos que protegen la comunicación por red con certificados de seguridad que cifran una conexión entre equipos. TLS reemplaza la Capa de sockets seguros (SSL) y se suele denominar SSL 3.1. Para Exchange Online, usamos TLS para cifrar las conexiones entre nuestros servidores de Exchange y las conexiones entre nuestros servidores de Exchange y otros servidores, como los servidores de Exchange locales o los servidores de correo de los destinatarios. Una vez cifrada la conexión, todos los datos enviados a través de esa conexión se envían a través del canal cifrado. Sin embargo, si reenvía un mensaje que se envió a través de una conexión cifrada con TLS, ese mensaje no se cifra necesariamente. Esto se debe a que, en términos simples, TLS no cifra el mensaje, solo la conexión.
  
Si quiere cifrar el mensaje, necesita usar una tecnología de cifrado que cifre el contenido del mensaje (por ejemplo, Cifrado de mensajes de Office). Vea [Email encryption in Office 365](email-encryption.md) y [Office 365 Message Encryption (OME)](ome.md) para más información sobre las opciones de cifrado de mensajes de Office 365. 
  
Se recomienda usar TLS en situaciones en las que desee configurar un canal seguro de correspondencia entre Microsoft y su organización local u otra organización, como un partner. Exchange Online siempre intenta usar primero TLS para proteger el correo electrónico, pero no siempre es posible si la otra parte no proporciona seguridad TLS. Siga leyendo para averiguar cómo puede proteger todo el correo a los servidores locales o a socios importantes mediante *conectores.* 

Para proporcionar el mejor cifrado de su clase a nuestros clientes, Microsoft ha dejado de usar las versiones 1.0 y 1.1 de Seguridad de la capa de transporte (TLS) en [Office 365](tls-1.0-and-1.1-deprecation-for-office-365.md) y [Office 365 GCC.](tls-1-2-in-office-365-gcc.md) Sin embargo, puedes seguir usando una conexión SMPT sin cifrar sin TLS. No recomendamos la transmisión de correo electrónico sin ningún cifrado.  
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Empleo de TLS por parte de Exchange Online entre clientes de Exchange Online

Los servidores de Exchange Online siempre cifran las conexiones con otros servidores de Exchange Online de nuestros centros de datos con TLS 1.2. Cuando envía correo a un destinatario que está dentro de su organización, ese correo electrónico se envía automáticamente a través de una conexión cifrada mediante TLS. Además, todo el correo electrónico que envíe a otros clientes se envía a través de conexiones cifradas con TLS y protegidas con secreto hacia delante.
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>Cómo Usa Microsoft 365 TLS entre Microsoft 365 y socios externos y de confianza

De forma predeterminada, Exchange Online siempre usa TLS oportunista. Esto significa que Exchange Online siempre intenta cifrar primero las conexiones con la versión más segura de TLS y, luego, va bajando por la lista de cifrado TLS hasta que encuentra uno que puedan aceptar ambas partes. A menos que haya configurado Exchange Online para asegurarse de que los mensajes a ese destinatario solo se envían a través de conexiones seguras, el mensaje se enviará de forma predeterminada sin cifrar si la organización del destinatario no admite el cifrado TLS. TLS oportunista es suficiente para la mayoría de las empresas. Sin embargo, para las empresas que tienen requisitos de cumplimiento como organizaciones médicas, bancarias o gubernamentales, puede configurar Exchange Online para requerir o forzar TLS. Para obtener instrucciones, vea [Configurar el flujo de correo mediante conectores en Office 365.](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)
  
Si decide configurar TLS entre su organización y una organización asociada de confianza, Exchange Online puede usar TLS forzado para crear canales de comunicación de confianza. TLS forzado necesita que la organización asociada autentique a Exchange Online con un certificado de seguridad para enviarle correo. Para hacerlo, el asociado tiene que administrar sus propios certificados. En Exchange Online, usamos conectores para proteger los mensajes que envía desde un acceso no autorizado antes de que lleguen al proveedor de correo electrónico del destinatario. Para obtener información sobre el uso de conectores para configurar el flujo de correo, vea Configurar el flujo de correo [mediante conectores en Office 365.](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS e implementaciones híbridas de Exchange Server

Si administra una implementación híbrida de Exchange, el servidor exchange local debe autenticarse en Microsoft 365 con un certificado de seguridad para enviar correo a los destinatarios cuyos buzones solo están en Office 365. Como resultado, debe administrar sus propios certificados de seguridad para los servidores de Exchange locales. También tiene que almacenar y mantener de forma segura estos certificados de servidor. Para obtener más información acerca de la administración de certificados en implementaciones híbridas, vea [Requisitos de certificados para implementaciones híbridas.](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx)
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Configurar TLS forzado para Exchange Online en Office 365

En el caso de los clientes de Exchange Online, para que TLS forzado pueda proteger todo el correo electrónico enviado y recibido, es necesario configurar más de un conector que exija TLS. Necesitará un conector para el correo electrónico enviado a los buzones de los usuarios y otro conector para el correo electrónico enviado desde los buzones de usuario. Cree esos conectores en el Centro de administración de Exchange en Office 365. Para obtener instrucciones, vea [Configurar el flujo de correo mediante conectores en Office 365.](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)
  
## <a name="tls-certificate-information-for-exchange-online"></a>Información de certificado TLS para Exchange Online

En la tabla siguiente se describe la información del certificado usada por Exchange Online. Si su socio comercial configura TLS forzado en su servidor de correo electrónico, necesitará proporcionarle esta información. Tenga en cuenta que, por motivos de seguridad, nuestros certificados cambian ocasionalmente. Hemos lanzado una actualización de nuestro certificado dentro de nuestros centros de datos. El nuevo certificado es válido a partir del 3 de septiembre de 2018.
  
 **Información de certificado actual válida desde el 3 de septiembre de 2018**
  
| Atributo | Valor |
|:-----|:-----|
|Emisor raíz de la autoridad de certificado  <br/> |GlobalSign Root CA – R1 <br/> |
|Nombre del certificado  <br/> |mail.protection.outlook.com  <br/> |
|Organización  <br/> |Microsoft Corporation  <br/> |
|Unidad de organización  <br/> |  <br/> |
|Nivel de la clave de certificado  <br/> |2048  <br/> |
   
 **Información de certificado en desuso válida hasta el 3 de septiembre de 2018**
  
Para ayudar a garantizar una transición sin problemas, seguiremos proporcionando la información del certificado antiguo para su referencia durante algún tiempo, pero debe usar la información del certificado actual a partir de ahora.
  
****

| Atributo | Valor |
|:-----|:-----|
|Emisor raíz de la autoridad de certificado  <br/> |Baltimore CyberTrust Root  <br/> |
|Nombre del certificado  <br/> |mail.protection.outlook.com  <br/> |
|Organización  <br/> |Microsoft Corporation  <br/> |
|Unidad de organización  <br/> |Microsoft Corporation  <br/> |
|Nivel de la clave de certificado  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>Prepararse para el nuevo certificado de Exchange Online

El nuevo certificado lo emite una entidad de certificación (CA) diferente del certificado anterior usado por Exchange Online. Como resultado, es posible que deba realizar algunas acciones para usar el nuevo certificado.

El nuevo certificado requiere conectarse a los extremos de la nueva CA como parte de la validación del certificado. Si no lo hace, el flujo de correo se verá afectado negativamente. Si protege los servidores de correo con firewalls que solo permiten que los servidores de correo se conecten con determinados destinos, debe comprobar si el servidor puede validar el nuevo certificado. Para confirmar que el servidor puede usar el nuevo certificado, siga estos pasos:

1. Conéctese a la Exchange Server local mediante Windows PowerShell y, a continuación, ejecute el siguiente comando:  
  `certutil -URL https://crl.globalsign.com/gsorganizationvalsha2g3.crl`

1. En la ventana que aparece, elija **Recuperar**.

1. Cuando la utilidad finaliza la comprobación, devuelve un estado. Si el estado muestra **Correcto,** el servidor de correo puede validar correctamente el nuevo certificado. Si no es así, debe determinar qué está provocando errores en las conexiones. Lo más probable es que necesite actualizar la configuración de un firewall. La lista completa de puntos de conexión a los que se debe tener acceso incluye:
    - ocsp.globalsign.com
    - crl.globalsign.com
    - secure.globalsign.com   

Normalmente, recibes actualizaciones de los certificados raíz automáticamente a través de Windows Update. Sin embargo, algunas implementaciones tienen seguridad adicional que impide que estas actualizaciones se produzcan automáticamente. En estas implementaciones bloqueadas en las que Windows Update no puede actualizar automáticamente los certificados raíz, debes asegurarte de que el certificado de ca raíz correcto esté instalado completando estos pasos:
1.  Conéctese a la Exchange Server local mediante Windows PowerShell y, a continuación, ejecute el siguiente comando:  
  `certmgr.msc`

2. En Certificados o entidad de certificación raíz **de confianza,** confirme que se muestra el nuevo certificado.

## <a name="get-more-information-about-tls-and-microsoft-365"></a>Obtener más información sobre TLS y Microsoft 365

Para obtener una lista de conjuntos de cifrado admitidos, vea [los detalles de referencia técnica sobre el cifrado.](technical-reference-details-about-encryption.md)
  
[Configurar conectores para flujo de correo seguro con una organización asociada](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[Conectores con seguridad mejorada de correo electrónico](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[Cifrado en Microsoft 365](encryption.md)
  

