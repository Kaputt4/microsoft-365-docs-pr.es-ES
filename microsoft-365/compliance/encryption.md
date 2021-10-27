---
title: Cifrado en Microsoft 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365solution-mip
- m365initiative-compliance
description: Con Office 365, el contenido se cifra en reposo y en tránsito con el cifrado, protocolos y tecnologías más fuertes disponibles. Obtenga información general sobre el cifrado en Office 365.
ms.openlocfilehash: a1ee73d7ded7a02cd7851081412d2403e0ca8f1d
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2021
ms.locfileid: "60587306"
---
# <a name="encryption"></a>Cifrado

El cifrado es una parte importante de la estrategia de protección de archivos y protección de la información. En este artículo se proporciona información general sobre el cifrado Office 365. Obtenga ayuda con tareas de cifrado como cómo configurar el cifrado para su organización y cómo proteger con contraseña Office documentos.
  
- Para obtener información sobre certificados y tecnologías como TLS, vea [Technical reference details about encryption in Office 365](technical-reference-details-about-encryption.md).

- Para obtener información sobre cómo configurar o configurar el cifrado para su organización, vea Configurar el cifrado [en Office 365 Enterprise](set-up-encryption.md).

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>¿Qué es el cifrado y cómo funciona en Office 365?

El proceso de cifrado codifica los datos (denominados texto sin formato) en texto cifrado. A diferencia del texto sin formato, las personas o los equipos no pueden usar el texto cifrado a menos que y hasta que se descifra el texto cifrado. El descifrado requiere una clave de cifrado que solo tienen los usuarios autorizados. El cifrado ayuda a garantizar que solo los destinatarios autorizados puedan descifrar el contenido. El contenido incluye archivos, mensajes de correo electrónico, entradas de calendario, entre otros.
  
El cifrado por sí mismo no impide la interceptación de contenido. El cifrado forma parte de una estrategia de protección de la información más grande para su organización. Al usar el cifrado, se ayuda a garantizar que solo las partes autorizadas puedan usar los datos cifrados.
  
Puede tener varias capas de cifrado en su lugar al mismo tiempo. Por ejemplo, puede cifrar mensajes de correo electrónico y también los canales de comunicación a través de los que fluye el correo electrónico. Con Office 365, los datos se cifran en reposo y en tránsito, con varios protocolos de cifrado seguros y tecnologías que incluyen Seguridad de la capa de transporte/Capa de sockets seguros (TLS/SSL), Seguridad de protocolos de Internet (IPSec) y Estándar de cifrado avanzado (AES).
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>Cifrado de datos en reposo y datos en tránsito

  Algunos ejemplos de datos en reposo incluyen archivos que ha cargado en una biblioteca de SharePoint, datos de Project Online, documentos que ha cargado en una reunión de Skype Empresarial, mensajes de correo electrónico y datos adjuntos que ha almacenado en carpetas del buzón y archivos que ha cargado en OneDrive para la Empresa.
  
 **Algunos ejemplos de datos en tránsito** son los mensajes de correo que están en proceso de entrega o las conversaciones que se están llevando a cabo en una reunión en línea. En Office 365, los datos están en tránsito cada vez que el dispositivo de un usuario se comunica con un servidor microsoft o cuando un servidor de Microsoft se comunica con otro servidor.
  
Con Office 365, varias capas y tipos de cifrado funcionan juntos para proteger los datos. En la tabla siguiente se incluyen algunos ejemplos, con vínculos a información adicional.
  
|**Tipos de contenido**|**Tecnologías de cifrado**|**Recursos para obtener más información**|
|:-----|:-----|:-----|
|Archivos en un dispositivo. Estos archivos pueden incluir mensajes de correo electrónico guardados en una carpeta, documentos Office guardados en un equipo, tableta o teléfono, o datos guardados en la nube de Microsoft.  <br/> |BitLocker en centros de datos de Microsoft. BitLocker también se puede usar en máquinas cliente, como Windows equipos y tabletas  <br/> Administrador de claves distribuidas (DKM) en centros de datos de Microsoft  <br/> Clave de cliente para Microsoft 365  <br/> |[Windows Centro de IT: BitLocker](/windows/device-security/bitlocker/bitlocker-overview) <br/> [Centro de confianza de Microsoft: cifrado](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [Serie de controles de seguridad en la nube: Cifrar datos en reposo](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Cómo Exchange Online protege su información confidencial de correo electrónico](exchange-online-secures-email-secrets.md) <br/> [Cifrado de servicio con clave de cliente](customer-key-overview.md) <br/> |
|Archivos en tránsito entre usuarios. Estos archivos pueden incluir documentos Office documentos o SharePoint elementos de lista compartidos entre usuarios.  <br/> |TLS para archivos en tránsito  <br/> |[Cifrado de datos en OneDrive para la Empresa y SharePoint Online](data-encryption-in-odb-and-spo.md) <br/> [Skype Empresarial En línea: Seguridad y archivado](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features) <br/> |
|Correo electrónico en tránsito entre destinatarios. Este correo electrónico incluye correo electrónico hospedado por Exchange Online.  <br/> |Cifrado de mensajes de Office 365 con Azure Rights Management, S/MIME y TLS para correo electrónico en tránsito  <br/> |[Cifrado de mensajes de Office 365 (OME)](ome.md) <br/> [Cifrado de correo electrónico en Office 365](email-encryption.md) <br/> [Cómo Exchange Online usa TLS para proteger las conexiones de correo electrónico en Office 365](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|Chats, mensajes y archivos en tránsito entre destinatarios mediante Microsoft Teams. <br/> |Teams TLS y MTLS para cifrar mensajes instantáneos. El tráfico multimedia se cifra mediante Secure RTP (SRTP). Teams algoritmos compatibles con FIPS (Federal Information Processing Standard) para intercambios de claves de cifrado. <br/> |[Cifrado para Teams](/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>¿Qué sucede si necesito más control sobre el cifrado para cumplir los requisitos de seguridad y cumplimiento?

Microsoft 365 soluciones administradas por Microsoft para el cifrado de volumen, el cifrado de archivos y el cifrado de buzones en Office 365. Además, Microsoft proporciona soluciones de cifrado que puede administrar y controlar. Estas soluciones de cifrado se han creado en Azure.
  
Para obtener más información, consulte los siguientes recursos:
  
- [¿Qué es Azure Rights Management?](/information-protection/understand-explore/what-is-azure-rms)

- [Activar Rights Management en el Centro de administración](../enterprise/activate-rms-in-microsoft-365.md)

- [Configurar Information Rights Management (IRM) en el Centro de administración de SharePoint](set-up-irm-in-sp-admin-center.md)

- [Cifrado de servicio con Clave de cliente de Office 365](customer-key-overview.md)

- [Cifrado de clave doble para Microsoft 365](double-key-encryption.md)

## <a name="how-do-i"></a>Cómo...

|**Para realizar esta tarea**|**Ver estos recursos**|
|:-----|:-----|
|Configurar el cifrado para mi organización|[Configurar el cifrado en Office 365 Enterprise](set-up-encryption.md)|
|Ver detalles sobre certificados, tecnologías y conjuntos de cifrado TLS|[Detalles técnicos sobre cifrado](technical-reference-details-about-encryption.md)|
|Trabajar con mensajes cifrados en un dispositivo móvil|[Ver mensajes cifrados en tu dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)Ver mensajes[cifrados en tu iPhone o iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)|
|Cifrar un documento con protección con contraseña. (La protección con contraseña no se admite en un explorador. Usar versiones de escritorio de Word, Excel y PowerPoint para la protección con contraseña). |[Agregar o quitar protección en el documento, libro o presentación](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826). Elija una **sección Agregar protección** y, a continuación, vea Cifrar con **contraseña**.|
|Quitar el cifrado de un documento|[Agregar o quitar protección en el documento, libro o presentación](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826). Elija una **sección Quitar protección** y, a continuación, vea Quitar cifrado de **contraseña.**  |

## <a name="related-topics"></a>Temas relacionados

[Plan for Microsoft 365 security and information protection capabilities](plan-for-security-and-compliance.md)

[Las 10 formas principales de proteger Microsoft 365 planes empresariales](/office365/admin/security-and-compliance/secure-your-business-data)

[Flujo de reproducción y cifrado de nivel de vídeo de Microsoft Stream](/stream/network-overview#video-level-encryption-and-playback-flow)