---
title: Uso de dominio Conectar
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
description: Obtenga información sobre cómo trabajar con los registradores Conectar dominio habilitados y agregue su dominio a Microsoft 365.
ms.openlocfilehash: 1691d86ebd459ee69faca8d3a21d99b0caa89fca
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63316917"
---
# <a name="using-domain-connect"></a>Uso de dominio Conectar

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

[Los Conectar](https://www.domainconnect.org/) registradores habilitados permiten agregar el dominio a Microsoft 365 en un proceso de tres pasos que tarda minutos.

En el asistente, solo confirmaremos que es el propietario del dominio y, a continuación, configuraremos automáticamente los registros de su dominio, de modo que el correo electrónico llegue a Microsoft 365 y otros servicios de Microsoft 365, como Teams, trabajen con su dominio.

> [!NOTE]
> Asegúrese de desactivar los bloqueadores de ventanas emergente en el explorador antes de iniciar el Asistente de configuración.

## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Registradores Conectar de dominio que se integran con Microsoft 365

- [11&amp; IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer o WildWestDomains (revendedores de GoDaddy que usan el hospedaje DNS de SecureServer)
  - [Hospedaje web de MadDog](https://maddogwebhosting.com/domains/)
  - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>¿Qué sucede con mi correo electrónico y mi sitio web?

Después de finalizar la instalación, el registro MX del dominio se actualiza para que apunte a Microsoft 365 y todo el correo electrónico de su dominio empezará a llegar a Microsoft 365. Asegúrese de que ha agregado usuarios y configurado buzones en Microsoft 365 para todos los usuarios que reciban correo electrónico en su dominio.

Si tiene un sitio web que usa con su empresa, seguirá funcionando como hasta ahora. Los pasos Conectar configuración del dominio no afectan a su sitio web.
