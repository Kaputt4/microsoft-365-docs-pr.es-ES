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
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: En este artículo, lea una introducción a las distintas formas de cifrado que se usan para mantener seguros los datos de los clientes en la nube de Microsoft.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3105da5d17b1656ffa0d29da4f4aa02c9a9f9064
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66633925"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Cifrado en Microsoft Cloud

Los datos de los clientes de los servicios en la nube empresarial de Microsoft están protegidos por varias tecnologías y procesos, incluidas varias formas de cifrado. (Los datos del cliente de este documento incluyen Exchange Online contenido del buzón, el cuerpo del correo electrónico, las entradas de calendario y el contenido de los datos adjuntos de correo electrónico y, si procede, Skype Empresarial contenido), el contenido del sitio de SharePoint Online y los archivos almacenados dentro de los sitios, y los archivos cargados en OneDrive para la Empresa o Skype Empresarial.) Microsoft usa varios métodos de cifrado, protocolos y cifrados en sus productos y servicios para ayudar a proporcionar una ruta segura para que los datos de los clientes viajen a través de nuestros servicios en la nube y para ayudar a proteger la confidencialidad de los datos de los clientes almacenados en nuestros servicios en la nube. Microsoft usa algunos de los protocolos de cifrado más seguros y seguros disponibles para proporcionar barreras contra el acceso no autorizado a los datos de los clientes. La administración correcta de claves también es un elemento esencial de los procedimientos recomendados de cifrado y Microsoft trabaja para asegurarse de que todas las claves de cifrado administradas por Microsoft están protegidas correctamente.

Los datos de los clientes almacenados en los servicios en la nube empresariales de Microsoft están protegidos mediante una o varias formas de cifrado. (La validación de nuestra directiva criptográfica y su aplicación es verificada de forma independiente por varios auditores de terceros, y los informes de esas auditorías están disponibles en el [Portal de confianza](https://aka.ms/stp) de servicios).

Microsoft proporciona tecnologías del lado del servicio que cifran los datos de los clientes en reposo y en tránsito. Por ejemplo, para los datos del cliente en reposo, Microsoft Azure usa [BitLocker](/windows/device-security/bitlocker/bitlocker-overview) y [DM-Crypt](https://en.wikipedia.org/wiki/Dm-crypt), y Microsoft 365 usa BitLocker, [Azure Storage Service Encryption](/azure/), [Distributed Key Manager](./exchange-online-secures-email-secrets.md) (DKM) y el cifrado de servicio de Microsoft 365. Para los datos de los clientes en tránsito, Azure, Office 365, Soporte técnico comercial de Microsoft, Microsoft Dynamics 365, Microsoft Power BI y Visual Studio Team Services usan protocolos de transporte seguro estándar del sector, como Seguridad de protocolos de Internet (IPsec) y Seguridad de la capa de transporte (TLS), entre centros de datos de Microsoft y entre dispositivos de usuario y centros de datos de Microsoft.

Además del nivel de línea base de seguridad criptográfica proporcionado por Microsoft, nuestros servicios en la nube también incluyen opciones de criptografía que puede administrar. Por ejemplo, puede habilitar el cifrado para el tráfico entre sus máquinas virtuales (VM) de Azure y sus usuarios. Con [Azure Virtual Networks](https://azure.microsoft.com/services/virtual-network/), puede usar el protocolo IPsec estándar del sector para cifrar el tráfico entre la puerta de enlace de VPN corporativa y Azure. También puede cifrar el tráfico entre las máquinas virtuales de la red virtual. Además, [las nuevas funcionalidades de cifrado de mensajes Office 365](set-up-new-message-encryption-capabilities.md) permiten enviar correo cifrado a cualquier usuario.

Siguiendo el estándar de seguridad operativa de infraestructura de clave pública, que es un componente de la [directiva de seguridad de Microsoft](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers), Microsoft usa las funcionalidades criptográficas incluidas en el sistema operativo Windows para certificados y mecanismos de autenticación. Estos mecanismos incluyen el uso de módulos criptográficos que cumplen el estándar 140-2 de [los Estándares Federales de Procesamiento de Información](https://csrc.nist.gov/publications/PubsFIPS.html) (FIPS) del gobierno de Ee. UU. Puede buscar los números de certificado NIST pertinentes para Microsoft mediante [cmvp del programa de validación de módulos criptográficos](https://csrc.nist.gov/projects/cryptographic-module-validation-program/validated-modules/search).

> [NOTA] Para acceder a la directiva de seguridad de Microsoft como recurso, debe iniciar sesión con su cuenta profesional o educativa. Si aún no tiene una suscripción, [puede registrarse para obtener una evaluación gratuita](https://servicetrust.microsoft.com/Home/TrialSubscriptions).

FIPS 140-2 es un estándar diseñado específicamente para validar módulos de productos que implementan criptografía en lugar de los productos que los usan. Los módulos criptográficos que se implementan dentro de un servicio se pueden certificar como que cumplen los requisitos de intensidad de hash, administración de claves y similares. Los módulos criptográficos y los cifrados que se usan para proteger la confidencialidad, integridad o disponibilidad de los datos de los servicios en la nube de Microsoft cumplen el estándar FIPS 140-2.

Microsoft certifica los módulos criptográficos subyacentes usados en nuestros servicios en la nube con cada nueva versión del sistema operativo Windows:

- Azure y Azure U.S. Government
- Dynamics 365 y Dynamics 365 para la Administración Pública de Estados Unidos
- Office 365, Office 365 Administración Pública para Estados Unidos y Office 365 U.S. Government Defense

El cifrado de datos de cliente en reposo lo proporcionan varias tecnologías del lado del servicio, como BitLocker, DKM, Azure Storage Service Encryption y cifrado de servicios en Exchange Online, Skype Empresarial, OneDrive para la Empresa y SharePoint Online. Office 365 cifrado de servicio incluye una opción para usar claves de cifrado administradas por el cliente que se almacenan en Azure Key Vault. Esta opción de clave administrada por el cliente, denominada [Clave de cliente](./customer-key-overview.md), está disponible para Exchange Online, SharePoint Online, Skype Empresarial y OneDrive para la Empresa.

En el caso de los datos de clientes en tránsito, todos los servidores Office 365 negocian sesiones seguras mediante TLS de forma predeterminada con máquinas cliente para proteger los datos de los clientes. Por ejemplo, Office 365 negociará sesiones seguras para Skype Empresarial, Outlook y Outlook en la Web, clientes móviles y exploradores web.

(Todos los servidores orientados al cliente negocian con TLS 1.2 de forma predeterminada).

## <a name="related-links"></a>Vínculos relacionados

- [Cifrado en Azure](office-365-azure-encryption.md)
- [BitLocker y Administrador de claves distribuidas (DKM) para el cifrado](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Cifrado de servicio de Office 365](office-365-service-encryption.md)
- [cifrado de Office 365 para Skype Empresarial, OneDrive para la Empresa, SharePoint Online y Exchange Online](/compliance/assurance/assurance-encryption-for-microsoft-365-services) 
- [Cifrado de datos en tránsito](/compliance/assurance/assurance-encryption-in-transit)
- [Características de cifrado administradas por el cliente](office-365-customer-managed-encryption-features.md)
- [Riesgos y protección de cifrado](office-365-encryption-risks-and-protections.md)
- [Cifrado en Microsoft Dynamics 365](office-365-encryption-in-microsoft-dynamics-365.md)
