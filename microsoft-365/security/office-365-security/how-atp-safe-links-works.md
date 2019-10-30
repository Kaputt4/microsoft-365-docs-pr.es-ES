---
title: Funcionamiento de los vínculos seguros de Office 365 ATP
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/19/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: La característica de vínculos seguros proporciona la comprobación del tiempo de clic de los hipervínculos en los documentos de Office y en los mensajes de correo electrónico. Lea este artículo para obtener información sobre cómo funciona el vínculo seguro ATP.
ms.openlocfilehash: bb60d57a422d908b013caf7267f21f390769cfb4
ms.sourcegitcommit: 333ecfb8bfeb34f9f08d82d295b40d37de6ba8b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772204"
---
# <a name="how-office-365-atp-safe-links-works"></a><span data-ttu-id="758b9-104">Funcionamiento de los vínculos seguros de Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="758b9-104">How Office 365 ATP Safe Links works</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="758b9-105">Cómo funciona el vínculo seguro ATP con direcciones URL en el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="758b9-105">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="758b9-106">En un nivel alto, aquí se muestra cómo funciona la protección de [vínculos seguros de ATP](atp-safe-links.md) para las direcciones URL en el correo electrónico (hospedado en Office 365, no en local):</span><span class="sxs-lookup"><span data-stu-id="758b9-106">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="758b9-107">Los usuarios reciben mensajes de correo electrónico, algunos de los cuales contienen direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="758b9-107">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="758b9-108">Todo el correo electrónico se envía a través de Exchange Online Protection, donde se aplican los filtros de protocolo de Internet (IP) y sobre, protección contra malware basada en firmas, filtros de correo no deseado y antimalware.</span><span class="sxs-lookup"><span data-stu-id="758b9-108">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="758b9-109">El correo electrónico llega a las bandejas de entrada de las personas.</span><span class="sxs-lookup"><span data-stu-id="758b9-109">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="758b9-110">Un usuario inicia sesión en Office 365 y se dirige a su bandeja de entrada de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="758b9-110">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="758b9-111">El usuario abre un mensaje de correo electrónico y hace clic en una dirección URL en el mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="758b9-111">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="758b9-112">La característica de vínculos seguros de ATP comprueba inmediatamente la dirección URL antes de abrir el sitio Web.</span><span class="sxs-lookup"><span data-stu-id="758b9-112">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="758b9-113">La dirección URL se identifica como bloqueada, malintencionada o segura.</span><span class="sxs-lookup"><span data-stu-id="758b9-113">The URL is identified as blocked, malicious, or safe.</span></span>
    
    - <span data-ttu-id="758b9-114">Si la dirección URL se refiere a un sitio web que se incluye en una [lista de direcciones URL "no reescribir" personalizada](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) para una directiva que se aplica al usuario, se abre el sitio Web.</span><span class="sxs-lookup"><span data-stu-id="758b9-114">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, the website opens.</span></span> 
    
    - <span data-ttu-id="758b9-115">Si la dirección URL es un sitio web que se incluye en la [lista de direcciones URL bloqueadas personalizadas](set-up-a-custom-blocked-urls-list-wtih-atp.md)de la organización, se abre una [Página de advertencia](atp-safe-links-warning-pages.md) .</span><span class="sxs-lookup"><span data-stu-id="758b9-115">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="758b9-116">Si la dirección URL es un sitio web que se ha determinado que es malintencionado, se abre una [Página de advertencia](atp-safe-links-warning-pages.md) .</span><span class="sxs-lookup"><span data-stu-id="758b9-116">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="758b9-117">Si la dirección URL va a un archivo descargable y las [directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) de la organización están configuradas para analizar dicho contenido, se comprueba el archivo descargable.</span><span class="sxs-lookup"><span data-stu-id="758b9-117">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
    - <span data-ttu-id="758b9-118">Si se determina que la dirección URL es segura, se abrirá el sitio Web.</span><span class="sxs-lookup"><span data-stu-id="758b9-118">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="758b9-119">Cómo funciona el vínculo seguro ATP con direcciones URL en documentos de Office</span><span class="sxs-lookup"><span data-stu-id="758b9-119">How ATP Safe Links works with URLs in Office documents</span></span>

<span data-ttu-id="758b9-120">En un nivel alto, aquí se muestra cómo funciona la protección de [vínculos seguros de ATP](atp-safe-links.md) para las direcciones URL en Office 365 ProPlus o en las aplicaciones de empresa Premium (versiones actuales de Word, Excel y PowerPoint en Windows, Mac o en un explorador, aplicaciones de Office en dispositivos iOS o Android, Visio on Windows, OneNote en un explorador):</span><span class="sxs-lookup"><span data-stu-id="758b9-120">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Office 365 ProPlus or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="758b9-121">Los usuarios tienen instalado Office 365 ProPlus o Business Premium en su equipo, smartphone o tableta.</span><span class="sxs-lookup"><span data-stu-id="758b9-121">People have installed Office 365 ProPlus or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="758b9-122">(O bien, usan Office en su explorador).</span><span class="sxs-lookup"><span data-stu-id="758b9-122">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="758b9-123">Un usuario abre una palabra, Excel, PowerPoint, OneNote (en la web) o Visio (en el escritorio) e inicia sesión en Office 365 Enterprise con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="758b9-123">A user opens a Word, Excel, PowerPoint, OneNote (on the web), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="758b9-124">El documento contiene direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="758b9-124">The document contains URLs.</span></span>
    
3. <span data-ttu-id="758b9-125">Cuando el usuario hace clic en una dirección URL del documento, el servicio de vínculos seguros de ATP comprueba el vínculo.</span><span class="sxs-lookup"><span data-stu-id="758b9-125">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
      - <span data-ttu-id="758b9-126">Si la dirección URL se refiere a un sitio web que se incluye en una [lista de direcciones URL "no reescribir" personalizada](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) para una directiva que se aplica al usuario, dicho usuario se dirigirá al sitio Web.</span><span class="sxs-lookup"><span data-stu-id="758b9-126">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, that user is taken to the website.</span></span> 
    
      - <span data-ttu-id="758b9-127">Si la dirección URL se redirigirá a un sitio web que se incluye en la [lista de direcciones URL bloqueadas personalizadas](set-up-a-custom-blocked-urls-list-wtih-atp.md)de la organización, se dirigirá al usuario a una [Página de advertencia](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="758b9-127">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
      - <span data-ttu-id="758b9-128">Si la dirección URL es un sitio web que se ha determinado que es malintencionado, se le dirigirá a una [Página de advertencia](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="758b9-128">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
      - <span data-ttu-id="758b9-129">Si la dirección URL va a un archivo descargable y las [directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) están configuradas para analizar tales descargas, se comprueba el archivo descargable.</span><span class="sxs-lookup"><span data-stu-id="758b9-129">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
      - <span data-ttu-id="758b9-130">Si la dirección URL se considera segura, el usuario se dirigirá al sitio Web.</span><span class="sxs-lookup"><span data-stu-id="758b9-130">If the URL is considered safe, the user is taken to the website.</span></span>
      
      - <span data-ttu-id="758b9-131">Si se produce un error en la comprobación de la dirección URL, la protección de vínculos seguros no se activará.</span><span class="sxs-lookup"><span data-stu-id="758b9-131">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="758b9-132">En los clientes de escritorio, el usuario recibirá una advertencia antes de continuar con el sitio.</span><span class="sxs-lookup"><span data-stu-id="758b9-132">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>

