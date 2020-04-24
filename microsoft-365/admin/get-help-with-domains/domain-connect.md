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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: Obtenga información sobre cómo trabajar con los registradores habilitados de conexión de dominio y agregar su dominio a Microsoft 365.
ms.openlocfilehash: 6a86783ca880f6cb4ea833e4c2b659de4da5e5c1
ms.sourcegitcommit: 72e43b9bf85dbf8f5cf2040ea6a4750d6dc867c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "43800016"
---
# <a name="using-domain-connect"></a><span data-ttu-id="9ccda-103">Uso de conexión de dominio</span><span class="sxs-lookup"><span data-stu-id="9ccda-103">Using Domain Connect</span></span>

 <span data-ttu-id="9ccda-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="9ccda-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="9ccda-105">Los registradores habilitados para la [conexión de dominio](https://www.domainconnect.org/) le permiten agregar su dominio a Microsoft 365 en un proceso de tres pasos que tarda minutos.</span><span class="sxs-lookup"><span data-stu-id="9ccda-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="9ccda-106">En el asistente, simplemente confirmaremos que es el propietario del dominio y, a continuación, configuraremos automáticamente los registros del dominio, por lo que el correo electrónico se entrega a Microsoft 365 y otros servicios de Microsoft 365, como Teams, funcionan con su dominio.</span><span class="sxs-lookup"><span data-stu-id="9ccda-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9ccda-107">Asegúrese de desactivar los bloqueadores de ventanas emergente en el explorador antes de iniciar el Asistente de configuración.</span><span class="sxs-lookup"><span data-stu-id="9ccda-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="9ccda-108">Registradores de conexión de dominio que se integran con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9ccda-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="9ccda-109">1&amp;1 IONOS</span><span class="sxs-lookup"><span data-stu-id="9ccda-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="9ccda-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="9ccda-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="9ccda-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="9ccda-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="9ccda-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="9ccda-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="9ccda-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="9ccda-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="9ccda-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="9ccda-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="9ccda-115">SecureServer o WildWestDomains (revendedores de GoDaddy que usen el hospedaje de SecureServer DNS)</span><span class="sxs-lookup"><span data-stu-id="9ccda-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="9ccda-116">Dominios de MadDog</span><span class="sxs-lookup"><span data-stu-id="9ccda-116">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="9ccda-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="9ccda-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="9ccda-118">¿Qué ocurre con mi correo electrónico y el sitio web?</span><span class="sxs-lookup"><span data-stu-id="9ccda-118">What happens to my email and website?</span></span>

<span data-ttu-id="9ccda-119">Una vez finalizada la instalación, el registro MX de su dominio se actualiza para que apunte a Microsoft 365 y todo el correo electrónico de su dominio empezará a ser de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9ccda-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="9ccda-120">Asegúrese de que agregó usuarios y configuró los buzones en Office 365 para todos los usuarios que reciban correo electrónico en el dominio.</span><span class="sxs-lookup"><span data-stu-id="9ccda-120">Make sure you've added users and set up mailboxes in Office 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="9ccda-121">Si tiene un sitio web que usa con su empresa, seguirá funcionando como hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="9ccda-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="9ccda-122">Los pasos de configuración de conexión de dominio no afectan a su sitio Web.</span><span class="sxs-lookup"><span data-stu-id="9ccda-122">The Domain Connect setup steps don't affect your website.</span></span>
