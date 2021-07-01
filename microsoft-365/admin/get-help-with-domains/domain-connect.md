---
title: Uso de dominios Conectar
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
description: Obtenga información sobre cómo trabajar con registradores Conectar habilitados y agregar su dominio a Microsoft 365.
ms.openlocfilehash: 12e1f227c0a157414b56fd04f99e5460a1eb05d4
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228019"
---
# <a name="using-domain-connect"></a><span data-ttu-id="b801b-103">Uso de dominios Conectar</span><span class="sxs-lookup"><span data-stu-id="b801b-103">Using Domain Connect</span></span>

 <span data-ttu-id="b801b-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="b801b-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="b801b-105">[Los Conectar](https://www.domainconnect.org/) registradores habilitados permiten agregar el dominio a Microsoft 365 en un proceso de tres pasos que tarda minutos.</span><span class="sxs-lookup"><span data-stu-id="b801b-105">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span>

<span data-ttu-id="b801b-106">En el asistente, solo confirmaremos que es el propietario del dominio y, a continuación, configuraremos automáticamente los registros de su dominio, de modo que el correo electrónico llegue a Microsoft 365 y otros servicios de Microsoft 365, como Teams, trabajen con su dominio.</span><span class="sxs-lookup"><span data-stu-id="b801b-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>

> [!NOTE]
> <span data-ttu-id="b801b-107">Asegúrese de desactivar los bloqueadores de ventanas emergente en el explorador antes de iniciar el Asistente de configuración.</span><span class="sxs-lookup"><span data-stu-id="b801b-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>

## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="b801b-108">Registradores Conectar de dominio que se integran con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b801b-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="b801b-109">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="b801b-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="b801b-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="b801b-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="b801b-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="b801b-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="b801b-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="b801b-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="b801b-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="b801b-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="b801b-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="b801b-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="b801b-115">SecureServer o WildWestDomains (revendedores de GoDaddy que usan el hospedaje DNS de SecureServer)</span><span class="sxs-lookup"><span data-stu-id="b801b-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
  - [<span data-ttu-id="b801b-116">Hospedaje web de MadDog</span><span class="sxs-lookup"><span data-stu-id="b801b-116">MadDog Web Hosting</span></span>](https://maddogwebhosting.com/domains/)
  - [<span data-ttu-id="b801b-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="b801b-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="b801b-118">¿Qué sucede con mi correo electrónico y mi sitio web?</span><span class="sxs-lookup"><span data-stu-id="b801b-118">What happens to my email and website?</span></span>

<span data-ttu-id="b801b-119">Después de finalizar la instalación, el registro MX del dominio se actualiza para que apunte a Microsoft 365 y todo el correo electrónico de su dominio empezará a llegar a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b801b-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="b801b-120">Asegúrese de que ha agregado usuarios y configurado buzones en Microsoft 365 para todos los usuarios que reciban correo electrónico en su dominio.</span><span class="sxs-lookup"><span data-stu-id="b801b-120">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>

<span data-ttu-id="b801b-121">Si tiene un sitio web que usa con su empresa, seguirá funcionando como hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="b801b-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="b801b-122">Los pasos Conectar configuración del dominio no afectan al sitio web.</span><span class="sxs-lookup"><span data-stu-id="b801b-122">The Domain Connect setup steps don't affect your website.</span></span>
