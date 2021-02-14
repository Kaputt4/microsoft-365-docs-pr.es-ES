---
title: Cifrado en Microsoft Cloud
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: En este artículo, lea una introducción a las diversas formas de cifrado que se usan para mantener seguros los datos de los clientes en la nube de Microsoft.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e48cc4fc54f0bc4553bab655611900523e11bd4d
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214278"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Cifrado en Microsoft Cloud

Los datos de clientes dentro de los servicios en la nube empresariales de Microsoft están protegidos por una variedad de tecnologías y procesos, incluidas diversas formas de cifrado. (Los datos de cliente de este documento incluyen el contenido del buzón de Exchange Online, el cuerpo del correo electrónico, las entradas del calendario y el contenido de los datos adjuntos de correo electrónico y, si procede, el contenido de Skype Empresarial), el contenido del sitio de SharePoint Online y los archivos almacenados en los sitios y los archivos cargados en OneDrive para la Empresa o Skype Empresarial). Microsoft usa varios métodos de cifrado, protocolos y cifrados en sus productos y servicios para ayudar a proporcionar una ruta segura para que los datos de los clientes viajen a través de nuestros servicios en la nube y para ayudar a proteger la confidencialidad de los datos de los clientes que se almacenan en nuestros servicios en la nube. Microsoft usa algunos de los protocolos de cifrado más seguros y seguros disponibles para proporcionar barreras contra el acceso no autorizado a los datos de los clientes. Una administración adecuada de claves también es un elemento esencial de los procedimientos recomendados de cifrado y Microsoft trabaja para garantizar que todas las claves de cifrado administradas por Microsoft estén protegidas correctamente.

Independientemente de la configuración del cliente, los datos de los clientes almacenados en los servicios en la nube empresariales de Microsoft se protegen mediante una o más formas de cifrado. (La validación de nuestra directiva criptográfica y su aplicación es verificada de forma independiente por varios auditores externos, y los informes de esas auditorías están disponibles en el [Portal](https://aka.ms/stp)de confianza de servicios).

Microsoft proporciona tecnologías del lado del servicio que cifran los datos de los clientes en reposo y en tránsito. Por ejemplo, para los datos de clientes en reposo, Microsoft Azure usa [BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) y [DM-Crypt,](https://en.wikipedia.org/wiki/Dm-crypt)y Microsoft 365 usa BitLocker, [Azure Storage Service Encryption,](https://docs.microsoft.com/azure/) [Distributed Key Manager](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-secures-email-secrets) (DKM) y el cifrado de servicio de Microsoft 365. Para los datos de clientes en tránsito, Azure, Office 365, Soporte comercial de Microsoft, Microsoft Dynamics 365, Microsoft Power BI y Visual Studio Team Services usan protocolos de transporte seguro estándar del sector, como seguridad de protocolo de Internet (IPsec) y seguridad de la capa de transporte (TLS), entre centros de datos de Microsoft y entre dispositivos de usuario y centros de datos de Microsoft.

Además del nivel de línea base de seguridad criptográfica proporcionado por Microsoft, nuestros servicios en la nube también incluyen opciones de criptografía adicionales que puede administrar. Por ejemplo, puede habilitar el cifrado para el tráfico entre sus máquinas virtuales de Azure (VM) y sus usuarios. Con [Azure Virtual Networks,](https://azure.microsoft.com/services/virtual-network/)puede usar el protocolo IPsec estándar del sector para cifrar el tráfico entre la puerta de enlace VPN corporativa y Azure, así como entre las máquinas virtuales ubicadas en la red virtual. Además, las nuevas funcionalidades de cifrado de mensajes de [Office 365](set-up-new-message-encryption-capabilities.md) le permiten enviar correo cifrado a cualquier persona.

De acuerdo con el estándar de seguridad operativa de infraestructura de clave pública, que es un componente de la directiva de seguridad de [Microsoft, Microsoft](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)aprovecha las capacidades criptográficas incluidas en el sistema operativo Windows para certificados y mecanismos de autenticación, que incluye el uso de módulos criptográficos que cumplen con el estándar 140-2 de los Estándares Federales de Procesamiento de Información (FIPS) del gobierno de estados Unidos. [](https://csrc.nist.gov/publications/PubsFIPS.html) (Los números de certificado NIST relevantes para Microsoft se pueden encontrar en https://csrc.nist.gov/groups/STM/cmvp/documents/140-1/1401vend.htm.)

> [NOTA] Para acceder a la directiva de seguridad de Microsoft como recurso, debe iniciar sesión con su cuenta de trabajo o escuela. Si aún no tiene una suscripción, [puede registrarse para obtener una versión de prueba gratuita.](https://servicetrust.microsoft.com/Home/TrialSubscriptions)

FIPS 140-2 es un estándar diseñado específicamente para validar módulos de producto que implementan criptografía en lugar de los productos que los usan. Los módulos criptográficos que se implementan dentro de un servicio se pueden certificar como que cumplen los requisitos de seguridad de hash, administración de claves y otras características. Siempre que se empleen capacidades criptográficas para proteger la confidencialidad, integridad o disponibilidad de los datos en los servicios en la nube de Microsoft, los módulos y cifrados usados cumplen con el estándar FIPS 140-2.

Microsoft certifica los módulos criptográficos subyacentes usados en nuestros servicios en la nube con cada nueva versión del sistema operativo Windows:

- Azure y Azure U.S. Government
- Dynamics 365 y Dynamics 365 para la Administración Pública de Estados Unidos
- Office 365, Office 365 Administración Pública para Estados Unidos y Office 365 U.S. Government Defense

El cifrado de datos de clientes en reposo se proporciona mediante varias tecnologías del lado del servicio, como BitLocker, DKM, cifrado del servicio de almacenamiento de Azure y cifrado de servicio en Exchange Online, Skype Empresarial, OneDrive para la Empresa y SharePoint Online. El cifrado de servicio de Office 365 incluye una opción para usar claves de cifrado administradas por el cliente que se almacenan en Azure Key Vault. Esta opción de clave administrada por el cliente, denominada [Clave](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview)de cliente, está disponible para Exchange Online, SharePoint Online, Skype Empresarial y OneDrive para la Empresa.

Para los datos de clientes en tránsito, todos los servidores de Office 365 negocian sesiones seguras mediante TLS de forma predeterminada con equipos cliente para proteger los datos de los clientes.  Esto se aplica a protocolos en cualquier dispositivo usado por clientes, como Skype Empresarial, Outlook y Outlook en la Web, clientes móviles y exploradores web.

(Todos los servidores orientados al cliente negocian con TLS 1.2 de forma predeterminada, pero también se admite la negociación a un estándar inferior, si es necesario).

## <a name="related-links"></a>Vínculos relacionados

- [Cifrado en Azure](office-365-azure-encryption.md)
- [BitLocker y Administrador de claves distribuidas (DKM) para el cifrado](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Cifrado de servicio de Office 365](office-365-service-encryption.md)
- [Cifrado de Office 365 para Skype Empresarial, OneDrive para la Empresa, SharePoint Online y Exchange Online](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [Cifrado de datos en tránsito](office-365-encryption-for-data-in-transit.md)
- [Características de cifrado administradas por el cliente](office-365-customer-managed-encryption-features.md)
- [Riesgos y protección de cifrado](office-365-encryption-risks-and-protections.md)
- [Cifrado en Microsoft Dynamics 365](office-365-encryption-in-microsoft-dynamics-365.md)
