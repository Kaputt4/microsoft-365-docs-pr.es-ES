---
title: Uso de conexión de dominio
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: Obtenga información sobre cómo trabajar con los registradores habilitados de conexión de dominio y agregar su dominio a Microsoft 365.
ms.openlocfilehash: 70a30201d4b795c7458959b6b2eee14c9b3c7186
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399961"
---
# <a name="using-domain-connect"></a>Uso de conexión de dominio

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.
  
Los registradores habilitados para la [conexión de dominio](https://www.domainconnect.org/) le permiten agregar su dominio a Microsoft 365 en un proceso de tres pasos que tarda minutos. 
  
En el asistente, simplemente confirmaremos que es el propietario del dominio y, a continuación, configuraremos automáticamente los registros del dominio, por lo que el correo electrónico se entrega a Microsoft 365 y otros servicios de Microsoft 365, como Teams, funcionan con su dominio.
  
> [!NOTE]
> Asegúrese de desactivar los bloqueadores de ventanas emergente en el explorador antes de iniciar el Asistente de configuración.
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Registradores de conexión de dominio que se integran con Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer o WildWestDomains (revendedores de GoDaddy que usen el hospedaje de SecureServer DNS)
    - [Dominios de MadDog](https://www.maddogdomains.com/)
    - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>¿Qué ocurre con mi correo electrónico y el sitio web?

Una vez finalizada la instalación, el registro MX de su dominio se actualiza para que apunte a Microsoft 365 y todo el correo electrónico de su dominio empezará a ser de Microsoft 365. Asegúrese de que agregó usuarios y configuró los buzones en Office 365 para todos los usuarios que reciban correo electrónico en el dominio.
  
Si tiene un sitio web que usa con su empresa, seguirá funcionando como hasta ahora. Los pasos de configuración de conexión de dominio no afectan a su sitio Web.
