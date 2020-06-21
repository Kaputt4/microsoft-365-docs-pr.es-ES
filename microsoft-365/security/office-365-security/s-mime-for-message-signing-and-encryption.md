---
title: S/MIME para cifrado en Exchange Online-Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: Los administradores pueden aprender a usar S/MIME (extensiones seguras multipropósito al correo de Internet) en Exchange Online para cifrar los correos electrónicos y firmarlos digitalmente.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 95bbab5161f9e4133223a247f8937c68f29c0590
ms.sourcegitcommit: 7a59d83a8660c2344ebdb92e0ea0171c9c2d9498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44811019"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME para la firma y el cifrado de mensajes en Exchange Online

S/MIME (extensiones seguras multipropósito al correo de Internet) es un método ampliamente aceptado (o más exactamente, un protocolo) para enviar mensajes cifrados y firmados digitalmente. S/MIME permite cifrar mensajes de correo electrónico y firmarlos digitalmente. Cuando se usa S/MIME con un mensaje de correo electrónico, ayuda a las personas que reciben el mensaje a tener la certeza de que lo que ven en la bandeja de entrada es el mensaje exacto que comenzó con el remitente. También ayudará a las personas que reciben mensajes a fin de asegurarse de que el mensaje proviene del remitente específico y no de alguien que pretende ser el remitente. Para ello, S/MIME proporciona servicios de seguridad criptográfica como autenticación, integridad de mensajes y no rechazo de origen (usando firmas digitales). También ayuda a mejorar la privacidad y la seguridad de los datos (mediante cifrado) para la mensajería electrónica. Para obtener más información sobre la historia y la arquitectura de S/MIME en el contexto del correo electrónico, consulte [Descripción de S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)).

Como administrador de Exchange Online, puede habilitar la seguridad basada en S/MIME para los buzones de la organización. Use las instrucciones de los temas que se vinculan aquí junto con Exchange Online PowerShell para configurar S/MIME. Para usar S/MIME en clientes de correo electrónico admitidos, los usuarios de la organización deben tener certificados emitidos con fines de firma y cifrado, así como datos publicados en el servicio de dominio de Active Directory (AD DS) local. AD DS debe estar ubicado en equipos en una ubicación física que usted controle y no en una instalación remota o un servicio basado en la nube en cualquier lugar de Internet. Para obtener más información acerca de AD DS, consulte [Introducción a los servicios de dominio de Active Directory](https://docs.microsoft.com/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview).

## <a name="supported-scenarios-and-technical-considerations"></a>Consideraciones técnicas y escenarios admitidos

Puede configurar S/MIME para trabajar con cualquiera de los siguientes extremos:

- Outlook 2010 o posterior

- Outlook en la web (anteriormente conocida como Outlook Web App)

- Exchange ActiveSync (EAS)

Los pasos que debe seguir para configurar S/MIME con cada uno de estos extremos son ligeramente diferentes. Por lo general, deberá realizar los pasos siguientes:

1. Instale una entidad emisora de certificados basada en Windows y configure una infraestructura de clave pública para emitir certificados S/MIME. También se admiten los certificados emitidos por proveedores de certificados de terceros. Para obtener más información, consulte [Información general de Servicios de certificados de Active Directory](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11)).

2. Publique el certificado de usuario en una cuenta local de AD DS en los atributos **UserSMIMECertificate** y **UserCertificate** .

3. Para las organizaciones de Exchange Online, sincronice los certificados de usuario de AD DS a Azure Active Directory mediante una versión adecuada de Azure AD Connect. Estos certificados se sincronizarán desde Azure Active Directory a directorio de Exchange Online y se usarán al cifrar un mensaje a un destinatario.

4. Set up a virtual certificate collection in order to validate S/MIME. This information is used by Outlook on the web when validating the signature of an email and ensuring that it was signed by a trusted certificate.

5. Configurar el extremo de Outlook o EAS para usar S/MIME.

> [!NOTE]
> No puede instalar el control S/MIME en Outlook en la web en Mac, iOS, Android u otros dispositivos que no son Windows. Para obtener más información, vea [cifrar mensajes mediante S/MIME en Outlook en la web](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480).

## <a name="setup-smime-with-outlook-on-the-web"></a>Configuración de S/MIME con Outlook en la web

La configuración de S/MIME para Exchange Online con Outlook en la web implica los siguientes pasos clave:

1. [Configurar S/MIME para Outlook en la Web](configure-s-mime-settings-for-outlook-web-app.md)

2. [Configurar una colección de certificados virtuales para validar S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)

3. [Sincronizar certificados de usuario con Office 365 para S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>Tecnologías de cifrado de mensajes relacionadas

A medida que la seguridad de los mensajes se vuelve más importante, los administradores deben comprender los principios y conceptos de la mensajería segura. Esta comprensión es especialmente importante debido a la creciente variedad de tecnologías relacionadas con la protección (incluido S/MIME) que están disponibles. Para obtener más información acerca de S/MIME y cómo funciona en el contexto del correo electrónico, consulte [Understanding s/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)). Una variedad de tecnologías de cifrado funcionan en conjunto para proporcionar protección a los mensajes en reposo y en tránsito. S/MIME puede funcionar simultáneamente con las siguientes tecnologías, pero no depende de ellas:

- **Seguridad de la capa de transporte (TLS)** cifra el túnel o la ruta entre los servidores de correo electrónico para ayudar a evitar la supervisión y el espionaje.

- La **capa de sockets seguros (SSL)** cifra la conexión entre los clientes de correo electrónico y los servidores de Microsoft 365.

- **BitLocker** cifra los datos de un disco duro en un centro de datos para que si alguien obtiene acceso no autorizado, no pueda leerlo.

### <a name="smime-compared-with-office-365-message-encryption"></a>Comparación de S/MIME con el cifrado de mensajes de 365 de Office

S/MIME requiere una infraestructura de certificados y publicación que suele usarse en situaciones de negocio a negocio y de negocio a consumidor. El usuario controla las claves criptográficas en S/MIME y puede elegir si desea usarlas para cada mensaje que envíe. Los programas de correo electrónico como Outlook buscan una ubicación de entidades de certificación raíz de confianza para llevar a cabo la firma digital y la comprobación de la firma. El cifrado de mensajes de Office 365 es un servicio de cifrado basado en directivas que puede configurar un administrador, y no un usuario individual, para cifrar el correo enviado a cualquier persona dentro o fuera de la organización. Es un servicio en línea que se basa en Azure Rights Management (RMS) y no depende de una infraestructura de clave pública. El cifrado de mensajes de Office 365 también proporciona funciones adicionales, como la capacidad de personalizar el correo con la marca de la organización. Para obtener más información sobre el cifrado de mensajes de Office 365, vea [cifrado en office 365](https://docs.microsoft.com/microsoft-365/compliance/encryption).

## <a name="more-information"></a>Más información

[Outlook en la Web](https://docs.microsoft.com/exchange/exchange-admin-center)

[Correo seguro (2000)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))
