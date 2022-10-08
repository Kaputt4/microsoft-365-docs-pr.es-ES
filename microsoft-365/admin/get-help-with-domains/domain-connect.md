---
title: Uso de Domain Connect
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: Obtenga información sobre cómo trabajar con registradores habilitados para Domain Connect y agregar su dominio a Microsoft 365.
ms.openlocfilehash: e20588181a5e9ca55d11844e2f31c3504a2bbfa0
ms.sourcegitcommit: c757f434da78bae71d4b476e14836fdf4da9f31e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2022
ms.locfileid: "67884402"
---
# <a name="using-domain-connect-to-add-your-domain-to-microsoft-365"></a>Uso de Domain Connect para agregar el dominio a Microsoft 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

Los registradores habilitados para [Domain Connect](https://www.domainconnect.org/) le permiten agregar el dominio a Microsoft 365 en un proceso de tres pasos que tarda minutos.

En el asistente, solo confirmaremos que es el propietario del dominio y configuraremos automáticamente los registros del dominio, para lo que el correo electrónico que llega a Microsoft 365 y otros servicios de Microsoft 365, como Teams, funcione con su dominio.

> [!NOTE]
> Asegúrese de desactivar los bloqueadores de ventanas emergente en el explorador antes de iniciar el Asistente de configuración.

## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Registradores de Domain Connect que se integran con Microsoft 365

- [1&amp;1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [Wordpress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer o WildWestDomains (revendedores de GoDaddy que usan el hospedaje DNS de SecureServer)
  - [Hospedaje web de MadDog](https://maddogwebhosting.com/domains/)
  - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>¿Qué ocurre con mi correo electrónico y mi sitio web?

After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365. Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!

If you have a website that you use with your business, it will keep working where it is. The Domain Connect setup steps don't affect your website.
