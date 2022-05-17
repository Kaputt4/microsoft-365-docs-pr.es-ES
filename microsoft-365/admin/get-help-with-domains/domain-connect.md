---
title: Uso de Conectar de dominio
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
description: Obtenga información sobre cómo trabajar con registradores habilitados para Conectar dominio y agregar el dominio a Microsoft 365.
ms.openlocfilehash: e20588181a5e9ca55d11844e2f31c3504a2bbfa0
ms.sourcegitcommit: 9255a7e8b398f92d8dae09886ae95dc8577bf29a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2022
ms.locfileid: "65437621"
---
# <a name="using-domain-connect-to-add-your-domain-to-microsoft-365"></a>Uso de Conectar de dominio para agregar el dominio a Microsoft 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

Los registradores habilitados para [Domain Connect](https://www.domainconnect.org/) le permiten agregar el dominio a Microsoft 365 en un proceso de tres pasos que tarda minutos.

En el asistente, solo confirmaremos que es el propietario del dominio y configuraremos automáticamente los registros del dominio, para lo que el correo electrónico que llega a Microsoft 365 y otros servicios de Microsoft 365, como Teams, funcione con su dominio.

> [!NOTE]
> Asegúrese de desactivar los bloqueadores de ventanas emergente en el explorador antes de iniciar el Asistente de configuración.

## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Registradores de Domain Connect que se integran con Microsoft 365

- [1&amp;1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer o WildWestDomains (revendedores de GoDaddy que usan el hospedaje DNS de SecureServer)
  - [Hospedaje web de MadDog](https://maddogwebhosting.com/domains/)
  - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>¿Qué ocurre con mi correo electrónico y mi sitio web?

Después de finalizar el proceso de configuración, el registro MX del dominio se actualizará para apuntar a Microsoft 365 y todo el correo electrónico del dominio empezará a llegar a Microsoft 365. Asegúrese de que agregó usuarios y configuró los buzones en Microsoft 365 para todos los usuarios que reciban correo electrónico en el dominio.

Si tiene un sitio web que usa con su empresa, seguirá funcionando como hasta ahora. Los pasos de configuración de Domain Connect no afectan al sitio web.
