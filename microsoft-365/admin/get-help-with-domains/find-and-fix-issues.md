---
title: Buscar y corregir problemas después de agregar el dominio o los registros DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Aprenda a realizar un seguimiento de los problemas que se encuentran al configurar un dominio personalizado asegurándose de que los registros DNS estén configurados correctamente.
ms.openlocfilehash: 5959cae02b87cf481fc06edd941a6da284b71736
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537552"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a><span data-ttu-id="d9966-103">Buscar y corregir problemas después de agregar el dominio o los registros DNS</span><span class="sxs-lookup"><span data-stu-id="d9966-103">Find and fix issues after adding your domain or DNS records</span></span>

 <span data-ttu-id="d9966-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="d9966-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d9966-105">Configurar el dominio para que funcione con Microsoft 365 puede ser un desafío.</span><span class="sxs-lookup"><span data-stu-id="d9966-105">Getting your domain set up to work with Microsoft 365 can be challenging.</span></span> <span data-ttu-id="d9966-106">El sistema DNS puede ser un poco enrevesado y la configuración DNS de su dominio afecta a importantes actividades empresariales, como el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d9966-106">The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="d9966-107">Para comprobar si hay problemas con el dominio, compruebe su estado.</span><span class="sxs-lookup"><span data-stu-id="d9966-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="d9966-108">Vaya a **Configurar**  >  **dominios** y vea las notificaciones en la **columna** Estado.</span><span class="sxs-lookup"><span data-stu-id="d9966-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="d9966-109">Si ve un problema, seleccione los tres puntos (más acciones) y, a continuación, elija **Comprobar estado**.</span><span class="sxs-lookup"><span data-stu-id="d9966-109">If you see an issue, select the three dots (more actions), and then choose **Check health**.</span></span> <span data-ttu-id="d9966-110">El panel que se abre describirá los problemas que se produzcan con el dominio.</span><span class="sxs-lookup"><span data-stu-id="d9966-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="d9966-111">¿Qué sucede?</span><span class="sxs-lookup"><span data-stu-id="d9966-111">What's going on?</span></span>

- [<span data-ttu-id="d9966-112">¿No puede comprobar su dominio?</span><span class="sxs-lookup"><span data-stu-id="d9966-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="d9966-113">Outlook¿no funciona?</span><span class="sxs-lookup"><span data-stu-id="d9966-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="d9966-114">El correo electrónico de todos los usuarios se cambió a Microsoft 365 y solo querías que el correo electrónico cambiara.</span><span class="sxs-lookup"><span data-stu-id="d9966-114">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="d9966-115">¿No se puede confirmar el estado de la cuenta educativa o sin ánimo de lucro?</span><span class="sxs-lookup"><span data-stu-id="d9966-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="d9966-116">¿Los servicios no funcionan con su dominio?</span><span class="sxs-lookup"><span data-stu-id="d9966-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="d9966-117">¿El acceso a su sitio web no funciona?</span><span class="sxs-lookup"><span data-stu-id="d9966-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="d9966-118">¿No puede comprobar su dominio?</span><span class="sxs-lookup"><span data-stu-id="d9966-118">Can't verify your domain?</span></span>
<span data-ttu-id="d9966-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d9966-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d9966-120">Hay algunas razones comunes por las que la comprobación del dominio puede no funcionar según lo esperado:</span><span class="sxs-lookup"><span data-stu-id="d9966-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="d9966-p103">**El valor del registro de comprobación no es del todo correcto.** Compruebe que ha copiado y pegado el valor exacto en el registro de comprobación TXT en su host DNS. Uno de los problemas habituales es no incluir la parte de "MS=" del registro. ¡También la necesitamos!</span><span class="sxs-lookup"><span data-stu-id="d9966-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="d9966-125">**No se ha guardado el registro.**</span><span class="sxs-lookup"><span data-stu-id="d9966-125">**The record hasn't been saved.**</span></span> <span data-ttu-id="d9966-126">En algunos hosts DNS, tiene que llevar a cabo un paso adicional para guardar el archivo de zona (donde se almacena el registro DNS), de modo que se actualice a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="d9966-126">At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet.</span></span> <span data-ttu-id="d9966-127">Asegúrese de guardar los cambios para que Microsoft 365 pueda ver y comprobar el registro.</span><span class="sxs-lookup"><span data-stu-id="d9966-127">Make sure you've saved your changes so Microsoft 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="d9966-128">**El registro no se ha actualizado en Internet.**</span><span class="sxs-lookup"><span data-stu-id="d9966-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="d9966-129">Normalmente, solo nos lleva unos minutos poder ver el nuevo registro, pero de vez en cuando puede tardar unas horas.</span><span class="sxs-lookup"><span data-stu-id="d9966-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="d9966-130">¿Outlook no funciona?</span><span class="sxs-lookup"><span data-stu-id="d9966-130">Outlook isn't working?</span></span>
<span data-ttu-id="d9966-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="d9966-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="d9966-132">Si ha configurado correctamente el registro MX y otros registros DNS de su dominio pero el correo electrónico no funciona, podemos ayudarle a [solucionar los problemas relacionados con Outlook](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="d9966-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span>
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="d9966-133">El correo electrónico de todos los usuarios se cambió a Microsoft 365 y solo querías que el correo electrónico cambiara.</span><span class="sxs-lookup"><span data-stu-id="d9966-133">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="d9966-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="d9966-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="d9966-135">Al agregar el dominio a Microsoft 365, normalmente el registro MX del dominio se actualiza (por usted o Microsoft 365) para que apunte a Microsoft 365 y todo el correo electrónico enviado a ese dominio empezará a llegar a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9966-135">When you add your domain to Microsoft 365, typically your domain's MX record is updated (by you or Microsoft 365) to point to Microsoft 365, and ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="d9966-136">Asegúrese de que ha creado buzones en Microsoft 365 para todos los usuarios que tienen correo electrónico en su dominio ANTES de cambiar el registro MX.</span><span class="sxs-lookup"><span data-stu-id="d9966-136">Make sure you've created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="d9966-137">¿Qué sucede si no desea mover el correo electrónico de todos los usuarios de su dominio a Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="d9966-137">What if you don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="d9966-138">En su lugar, puede tomar [medidas para Microsoft 365 con solo unas cuantas](../setup/domains-faq.yml)direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d9966-138">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](../setup/domains-faq.yml).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="d9966-139">¿No se puede confirmar el estado de la cuenta educativa o sin ánimo de lucro?</span><span class="sxs-lookup"><span data-stu-id="d9966-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="d9966-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="d9966-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="d9966-141">Hay un par de escenarios en los que solo tiene que comprobar el dominio de su organización y no configurar ningún servicio.</span><span class="sxs-lookup"><span data-stu-id="d9966-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="d9966-142">Por ejemplo, para demostrar que Microsoft 365 que su organización cumple los requisitos para una suscripción a la escuela.</span><span class="sxs-lookup"><span data-stu-id="d9966-142">For example, to prove to Microsoft 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="d9966-143">Consulta las instrucciones de Comprobar tu dominio Microsoft 365 para probar la propiedad, la organización sin ánimo de lucro o el estado [educativo,](../setup/domains-faq.yml) o para activar Yammer para asegurarte de que has completado todos los pasos necesarios.</span><span class="sxs-lookup"><span data-stu-id="d9966-143">Check out the guidance in [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](../setup/domains-faq.yml) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="d9966-144">Es un poco diferente para cada situación.</span><span class="sxs-lookup"><span data-stu-id="d9966-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="d9966-145">¿Los servicios no funcionan con su dominio?</span><span class="sxs-lookup"><span data-stu-id="d9966-145">Services not working with your domain?</span></span>
<span data-ttu-id="d9966-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="d9966-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="d9966-147">Podemos ayudarle a localizar los problemas de configuración DNS de su dominio.</span><span class="sxs-lookup"><span data-stu-id="d9966-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="d9966-148">El solucionador de problemas de dominios Microsoft 365 le mostrará los registros que necesiten corregirse y exactamente en qué deben establecerse los registros.</span><span class="sxs-lookup"><span data-stu-id="d9966-148">The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="d9966-149">¿Ha configurado DNS correctamente pero el correo electrónico no funciona en la versión de escritorio de Outlook?</span><span class="sxs-lookup"><span data-stu-id="d9966-149">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop?</span></span> <span data-ttu-id="d9966-150">Consulte los [diferentes escenarios de](/exchange/mail-flow-best-practices/mail-flow-best-practices) flujo de correo que puede tener con Microsoft 365 para asegurarse de que las cosas están configuradas correctamente para su empresa.</span><span class="sxs-lookup"><span data-stu-id="d9966-150">Check out the [different mail flow scenarios you can have with Microsoft 365](/exchange/mail-flow-best-practices/mail-flow-best-practices) to make sure you've got things set up correctly for your business.</span></span> <span data-ttu-id="d9966-151">O bien, obtenga más ayuda para solucionar problemas con el correo electrónico aquí: [Solucionar problemas de Outlook](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="d9966-151">Or get more troubleshooting help with email here: [Fix Outlook problems](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="d9966-152">¿El acceso a su sitio web no funciona?</span><span class="sxs-lookup"><span data-stu-id="d9966-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="d9966-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="d9966-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="d9966-154">Si ha corregido cualquier problema de DNS y sigue teniendo dificultades, pruebe los siguientes procedimientos.</span><span class="sxs-lookup"><span data-stu-id="d9966-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="d9966-155">Los usuarios no pueden obtener acceso al sitio web en www.mydomain.com: [localizar problemas de sitio web](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="d9966-155">People can't get to your website at www.mydomain.com: [Track down website issues](../setup/add-domain.md)</span></span>
    
- <span data-ttu-id="d9966-156">No puede actualizar el registro A o el registro CNAME para que apunten a su sitio web: Actualice los [registros DNS personalizados en Microsoft 365](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="d9966-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../setup/add-domain.md)</span></span>

## <a name="related-content"></a><span data-ttu-id="d9966-157">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="d9966-157">Related content</span></span>

[<span data-ttu-id="d9966-158">Solución de problemas: auditar datos sobre el cambio de dominio comprobado</span><span class="sxs-lookup"><span data-stu-id="d9966-158">Troubleshoot: Audit data on verified domain change</span></span>](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

