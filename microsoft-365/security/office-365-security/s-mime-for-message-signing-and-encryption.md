---
title: S/MIME para el cifrado en Exchange Online - Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: Los administradores pueden aprender a usar S/MIME (Extensiones seguras multipropósito al correo de Internet) en Exchange Online para cifrar correos electrónicos y firmarlos digitalmente.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 35266b4ceefe161b907ddbc955fd234b716792a6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288578"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME para la firma y el cifrado de mensajes en Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


S/MIME (Extensiones seguras multipropósito al correo de Internet) es un método ampliamente aceptado (o más exactamente, un protocolo) para enviar mensajes cifrados y firmados digitalmente. S/MIME permite cifrar mensajes de correo electrónico y firmarlos digitalmente. Cuando se usa S/MIME con un mensaje de correo electrónico, ayuda a las personas que reciben ese mensaje a estar seguros de que lo que ven en su bandeja de entrada es el mensaje exacto que se inició con el remitente. También ayudará a las personas que reciben mensajes a estar seguras de que el mensaje provenía del remitente específico y no de alguien que pretende ser el remitente. Para ello, S/MIME proporciona servicios de seguridad criptográfica como autenticación, integridad de mensajes y no rechazo de origen (usando firmas digitales). También ayuda a mejorar la privacidad y la seguridad de los datos (mediante cifrado) para la mensajería electrónica. Para obtener más información sobre la historia y la arquitectura de S/MIME en el contexto del correo electrónico, consulte [Descripción de S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)).

Como administrador de Exchange Online, puede habilitar la seguridad basada en S/MIME para los buzones de la organización. Use las instrucciones de los temas vinculados aquí junto con Exchange Online PowerShell para configurar S/MIME. Para usar S/MIME en clientes de correo electrónico compatibles, los usuarios de la organización deben tener certificados emitidos para fines de firma y cifrado y datos publicados en el servicio de dominio de Active Directory (AD DS) local. Su AD DS debe estar ubicado en equipos en una ubicación física que controle y no en una instalación remota o un servicio basado en la nube en algún lugar de Internet. Para obtener más información acerca de AD DS, vea [Información general sobre los Servicios de dominio de Active Directory.](https://docs.microsoft.com/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)

## <a name="supported-scenarios-and-technical-considerations"></a>Escenarios admitidos y consideraciones técnicas

Puede configurar S/MIME para trabajar con cualquiera de los siguientes extremos:

- Outlook 2010 o posterior
- Outlook en la web (anteriormente conocida como Outlook Web App)
- Exchange ActiveSync (EAS)

Los pasos que siga para configurar S/MIME con cada uno de estos puntos finales son ligeramente diferentes. Por lo general, deberá realizar los siguientes pasos:

1. Instale una entidad de certificación (CA) basada en Windows y configure una infraestructura de clave pública para emitir certificados S/MIME. También se admiten los certificados emitidos por proveedores de certificados de terceros. Para obtener más información, consulte [Información general de Servicios de certificados de Active Directory](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11)).

   **Notas**:

   - Los certificados emitidos por una CA de terceros tienen la ventaja de que todos los clientes y dispositivos confían automáticamente en ellos. Los certificados emitidos por una CA interna y privada no son de confianza automáticamente para clientes y dispositivos, y no todos los dispositivos (por ejemplo, teléfonos) se pueden configurar para confiar en certificados privados.

   - Considere la posibilidad de usar un certificado intermedio en lugar del certificado raíz para emitir certificados a los usuarios. De este modo, si alguna vez necesitas revocar y volver a emitir certificados, el certificado raíz sigue intacto.

2. Publique el certificado de usuario en una cuenta de AD DS local en los atributos **UserSMIMECertificate** o **UserCertificate.**

3. Para las organizaciones de Exchange Online, sincronice los certificados de usuario de AD DS con Azure Active Directory mediante una versión adecuada de Azure AD Connect. A continuación, estos certificados se sincronizarán de Azure Active Directory con el directorio de Exchange Online y se usarán al cifrar un mensaje para un destinatario.

4. Crear una colección virtual de certificados para validar S/MIME. Outlook en la web usa esta información para validar la firma de un correo electrónico y garantizar que se ha firmado con un certificado de confianza.

5. Configurar el extremo de Outlook o EAS para usar S/MIME.

> [!NOTE]
> No puede instalar el control S/MIME en Outlook en la Web en Mac, iOS, Android u otros dispositivos que no son windows. Para obtener más información, vea [Cifrar mensajes mediante S/MIME en Outlook en la Web.](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480)

## <a name="set-up-smime-with-outlook-on-the-web"></a>Configurar S/MIME con Outlook en la web

La configuración de S/MIME para Exchange Online con Outlook en la Web implica los siguientes pasos clave:

1. [Configurar S/MIME para Outlook en la Web](configure-s-mime-settings-for-outlook-web-app.md)
2. [Configurar una colección de certificados virtuales para validar S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [Sincronizar certificados de usuario con Office 365 para S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>Tecnologías de cifrado de mensajes relacionadas

A medida que la seguridad de los mensajes se vuelve más importante, los administradores necesitan comprender los principios y conceptos de la mensajería segura. Este conocimiento es especialmente importante debido a la creciente variedad de tecnologías relacionadas con la protección (incluido S/MIME) que están disponibles. Para obtener más información sobre S/MIME y cómo funciona en el contexto del correo electrónico, consulte [Descripción de S/MIME.](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)) Varias tecnologías de cifrado funcionan juntas para proporcionar protección para los mensajes en reposo y en tránsito. S/MIME puede funcionar simultáneamente con las siguientes tecnologías, pero no depende de ellas:

- Seguridad de la capa de **transporte (TLS)** cifra el túnel o la ruta entre los servidores de correo electrónico para ayudar a evitar el espionaje y la interceptación.

- **La Capa de sockets seguros (SSL)** cifra la conexión entre los clientes de correo electrónico y los servidores de Microsoft 365.

- **BitLocker** cifra los datos en una unidad de disco duro de un centro de datos para que, si alguien obtiene acceso no autorizado, no pueda leerlo.

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME en comparación con el cifrado de mensajes de Office 365

S/MIME requiere una infraestructura de certificados y publicación que suele usarse en situaciones de negocio a negocio y de negocio a consumidor. El usuario controla las claves criptográficas en S/MIME y puede elegir si desea usarlas para cada mensaje que envíe. Los programas de correo electrónico como Outlook buscan una ubicación de entidades de certificación raíz de confianza para llevar a cabo la firma digital y la comprobación de la firma. Cifrado de mensajes de Office 365 es un servicio de cifrado basado en directivas que puede configurar un administrador, y no un usuario individual, para cifrar el correo enviado a cualquier persona dentro o fuera de la organización. Es un servicio en línea que se basa en Azure Rights Management (RMS) y no se basa en una infraestructura de clave pública. El cifrado de mensajes de Office 365 también proporciona capacidades adicionales, como la capacidad de personalizar el correo con la marca de la organización. Para obtener más información acerca del cifrado de mensajes de Office 365, vea [Cifrado en Office 365.](../../compliance/encryption.md)

## <a name="more-information"></a>Más información

[Outlook en la Web](https://docs.microsoft.com/exchange/exchange-admin-center)

[Correo seguro (2000)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))
