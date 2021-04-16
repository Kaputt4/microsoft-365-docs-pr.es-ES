---
title: Uso de La conexión de dominio
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
description: Obtenga información sobre cómo trabajar con registradores habilitados para Conectar dominio y agregar su dominio a Microsoft 365.
ms.openlocfilehash: 5dec69f70273e6a9430ce5926ed07888e197adcd
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860660"
---
# <a name="using-domain-connect"></a>Uso de La conexión de dominio

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.
  
[Los registradores ](https://www.domainconnect.org/) habilitados para Conectar dominio permiten agregar el dominio a Microsoft 365 en un proceso de tres pasos que tarda minutos. 
  
En el asistente, solo confirmaremos que es el propietario del dominio y, a continuación, configuraremos automáticamente los registros de su dominio, por lo que el correo electrónico llega a Microsoft 365 y otros servicios de Microsoft 365, como Teams, a trabajar con su dominio.
  
> [!NOTE]
> Asegúrese de desactivar los bloqueadores de ventanas emergente en el explorador antes de iniciar el Asistente de configuración.
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Registradores de Domain Connect que se integran con Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer o WildWestDomains (revendedores de GoDaddy que usan el hospedaje DNS de SecureServer)
    - [Hospedaje web de MadDog](https://maddogwebhosting.com/domains/)
    - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>¿Qué sucede con mi correo electrónico y mi sitio web?

Después de finalizar la configuración, el registro MX del dominio se actualiza para que apunte a Microsoft 365 y todo el correo electrónico de su dominio empezará a llegar a Microsoft 365. Asegúrese de agregar usuarios y configurar buzones en Microsoft 365 para todos los usuarios que reciban correo electrónico en su dominio.
  
Si tiene un sitio web que usa con su empresa, seguirá funcionando como hasta ahora. Los pasos de configuración de Conexión de dominio no afectan al sitio web.
