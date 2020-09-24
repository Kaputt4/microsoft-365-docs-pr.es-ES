---
title: Cómo funcionan los vínculos seguros de ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: La característica de vínculos seguros proporciona la comprobación del tiempo de clic de los hipervínculos en los documentos de Office y en los mensajes de correo electrónico. Lea este artículo para obtener información sobre cómo funciona el vínculo seguro ATP.
ms.openlocfilehash: e19d3a1f93d11cd9873e6b5fad9952b018e0a481
ms.sourcegitcommit: 1522a6471e0c5254a6d0f592e1f4dfacd1dd473a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "48245886"
---
# <a name="how-atp-safe-links-works"></a><span data-ttu-id="67f8d-104">Cómo funcionan los vínculos seguros de ATP</span><span class="sxs-lookup"><span data-stu-id="67f8d-104">How ATP Safe Links works</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT] 
> <span data-ttu-id="67f8d-105">Para que los vínculos seguros de Office 365 ATP funcionen correctamente, todos los servicios deben estar en la misma versión.</span><span class="sxs-lookup"><span data-stu-id="67f8d-105">For Office 365 ATP Safe Links to operate correctly, all of the services need to be at the same version.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="67f8d-106">Cómo funciona el vínculo seguro ATP con direcciones URL en el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="67f8d-106">How ATP Safe Links works with URLs in email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]
 <span data-ttu-id="67f8d-107">con direcciones URL en el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="67f8d-107">with URLs in email</span></span>

<span data-ttu-id="67f8d-108">En un nivel alto, aquí se muestra cómo funciona la protección de [vínculos seguros de ATP](atp-safe-links.md) para las direcciones URL en el correo electrónico (hospedado en Office 365, no en local):</span><span class="sxs-lookup"><span data-stu-id="67f8d-108">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="67f8d-109">Los usuarios reciben mensajes de correo electrónico, algunos de los cuales contienen direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="67f8d-109">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="67f8d-110">Todo el correo electrónico se envía a través de Exchange Online Protection, donde se aplican los filtros de protocolo de Internet (IP) y sobre, protección contra malware basada en firmas, filtros de correo no deseado y antimalware.</span><span class="sxs-lookup"><span data-stu-id="67f8d-110">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="67f8d-111">El correo electrónico llega a las bandejas de entrada de las personas.</span><span class="sxs-lookup"><span data-stu-id="67f8d-111">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="67f8d-112">Un usuario inicia sesión en Office 365 y se dirige a su bandeja de entrada de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="67f8d-112">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="67f8d-113">El usuario abre un mensaje de correo electrónico y hace clic en una dirección URL en el mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="67f8d-113">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="67f8d-114">La característica de vínculos seguros de ATP comprueba inmediatamente la dirección URL antes de abrir el sitio Web.</span><span class="sxs-lookup"><span data-stu-id="67f8d-114">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="67f8d-115">La dirección URL se identifica como bloqueada, malintencionada o segura.</span><span class="sxs-lookup"><span data-stu-id="67f8d-115">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="67f8d-116">Si la dirección URL es un sitio web que se incluye en la [lista de direcciones URL bloqueadas personalizadas](set-up-a-custom-blocked-urls-list-atp.md)de la organización, se abre una [Página de advertencia](atp-safe-links-warning-pages.md) .</span><span class="sxs-lookup"><span data-stu-id="67f8d-116">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="67f8d-117">Si la dirección URL es un sitio web que se ha determinado que es malintencionado, se abre una [Página de advertencia](atp-safe-links-warning-pages.md) .</span><span class="sxs-lookup"><span data-stu-id="67f8d-117">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="67f8d-118">Si la dirección URL va a un archivo descargable y las [directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) de la organización están configuradas para analizar dicho contenido, se comprueba el archivo descargable.</span><span class="sxs-lookup"><span data-stu-id="67f8d-118">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="67f8d-119">Si se determina que la dirección URL es segura, se abrirá el sitio Web.</span><span class="sxs-lookup"><span data-stu-id="67f8d-119">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="67f8d-120">Cómo funciona el vínculo seguro ATP con direcciones URL en documentos de Office</span><span class="sxs-lookup"><span data-stu-id="67f8d-120">How ATP Safe Links works with URLs in Office documents</span></span>

<span data-ttu-id="67f8d-121">En un nivel alto, aquí se muestra cómo funciona la protección de [vínculos seguros de ATP](atp-safe-links.md) para las direcciones URL en las aplicaciones de Microsoft 365 apps for Enterprise o Business Premium (versiones actuales de Word, Excel y PowerPoint en Windows, Mac o en un explorador, aplicaciones de Office en dispositivos iOS o Android, Visio en Windows, OneNote en un explorador):</span><span class="sxs-lookup"><span data-stu-id="67f8d-121">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Microsoft 365 Apps for enterprise or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="67f8d-122">Los usuarios han instalado Microsoft 365 apps for Enterprise o Business Premium en su equipo, smartphone o tableta.</span><span class="sxs-lookup"><span data-stu-id="67f8d-122">People have installed Microsoft 365 Apps for enterprise or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="67f8d-123">(O bien, usan Office en su explorador).</span><span class="sxs-lookup"><span data-stu-id="67f8d-123">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="67f8d-124">Un usuario abre una palabra, Excel, PowerPoint, OneNote (en el explorador) o Visio (en el escritorio) e inicia sesión en Office 365 Enterprise con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="67f8d-124">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="67f8d-125">El documento contiene direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="67f8d-125">The document contains URLs.</span></span>
    
3. <span data-ttu-id="67f8d-126">Cuando el usuario hace clic en una dirección URL del documento, el servicio de vínculos seguros de ATP comprueba el vínculo.</span><span class="sxs-lookup"><span data-stu-id="67f8d-126">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="67f8d-127">Si la dirección URL se redirigirá a un sitio web que se incluye en la [lista de direcciones URL bloqueadas personalizadas](set-up-a-custom-blocked-urls-list-atp.md)de la organización, se dirigirá al usuario a una [Página de advertencia](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="67f8d-127">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="67f8d-128">Si la dirección URL es un sitio web que se ha determinado que es malintencionado, se le dirigirá a una [Página de advertencia](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="67f8d-128">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="67f8d-129">Si la dirección URL va a un archivo descargable y las [directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) están configuradas para analizar tales descargas, se comprueba el archivo descargable.</span><span class="sxs-lookup"><span data-stu-id="67f8d-129">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="67f8d-130">Si la dirección URL se considera segura, el usuario se dirigirá al sitio Web.</span><span class="sxs-lookup"><span data-stu-id="67f8d-130">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="67f8d-131">Si se produce un error en la comprobación de la dirección URL, la protección de vínculos seguros no se activará.</span><span class="sxs-lookup"><span data-stu-id="67f8d-131">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="67f8d-132">En los clientes de escritorio, el usuario recibirá una advertencia antes de continuar con el sitio.</span><span class="sxs-lookup"><span data-stu-id="67f8d-132">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="67f8d-133">Puede tardar varios segundos al principio de cada sesión para comprobar que el usuario tiene vínculos seguros ATP para Office habilitados.</span><span class="sxs-lookup"><span data-stu-id="67f8d-133">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      
