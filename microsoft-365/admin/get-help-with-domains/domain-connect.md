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
ms.openlocfilehash: fb3f9315ed8ae056cadd2fd6a83f13f6713347f3
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079984"
---
# <a name="using-domain-connect"></a><span data-ttu-id="6bb6a-103">Uso de conexión de dominio</span><span class="sxs-lookup"><span data-stu-id="6bb6a-103">Using Domain Connect</span></span>

 <span data-ttu-id="6bb6a-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="6bb6a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="6bb6a-105">Los registradores habilitados para la [conexión de dominio](https://www.domainconnect.org/) le permiten agregar su dominio a Microsoft 365 en un proceso de tres pasos que tarda minutos.</span><span class="sxs-lookup"><span data-stu-id="6bb6a-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="6bb6a-106">En el asistente, simplemente confirmaremos que es el propietario del dominio y, a continuación, configuraremos automáticamente los registros del dominio, por lo que el correo electrónico se entrega a Microsoft 365 y otros servicios de Microsoft 365, como Teams, funcionan con su dominio.</span><span class="sxs-lookup"><span data-stu-id="6bb6a-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6bb6a-107">Asegúrese de desactivar los bloqueadores de ventanas emergente en el explorador antes de iniciar el Asistente de configuración.</span><span class="sxs-lookup"><span data-stu-id="6bb6a-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="6bb6a-108">Registradores de conexión de dominio que se integran con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6bb6a-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="6bb6a-109">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="6bb6a-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="6bb6a-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="6bb6a-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="6bb6a-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="6bb6a-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="6bb6a-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="6bb6a-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="6bb6a-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="6bb6a-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="6bb6a-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="6bb6a-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="6bb6a-115">SecureServer o WildWestDomains (revendedores de GoDaddy que usen el hospedaje de SecureServer DNS)</span><span class="sxs-lookup"><span data-stu-id="6bb6a-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="6bb6a-116">Dominios de MadDog</span><span class="sxs-lookup"><span data-stu-id="6bb6a-116">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="6bb6a-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="6bb6a-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="6bb6a-118">¿Qué ocurre con mi correo electrónico y el sitio web?</span><span class="sxs-lookup"><span data-stu-id="6bb6a-118">What happens to my email and website?</span></span>

<span data-ttu-id="6bb6a-119">Una vez finalizada la instalación, el registro MX de su dominio se actualiza para que apunte a Microsoft 365 y todo el correo electrónico de su dominio empezará a ser de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6bb6a-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="6bb6a-120">Asegúrese de que ha agregado usuarios y configurado los buzones en Microsoft 365 para todos los usuarios que obtienen correo electrónico en su dominio.</span><span class="sxs-lookup"><span data-stu-id="6bb6a-120">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="6bb6a-121">Si tiene un sitio web que usa con su empresa, seguirá funcionando como hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="6bb6a-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="6bb6a-122">Los pasos de configuración de conexión de dominio no afectan a su sitio Web.</span><span class="sxs-lookup"><span data-stu-id="6bb6a-122">The Domain Connect setup steps don't affect your website.</span></span>
