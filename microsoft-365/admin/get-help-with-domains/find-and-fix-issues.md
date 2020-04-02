---
title: Buscar y corregir problemas después de agregar el dominio o los registros DNS en Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Aprenda a realizar un seguimiento de los problemas que se produzcan al configurar un dominio personalizado asegurándose de que los registros DNS están configurados correctamente.
ms.openlocfilehash: a93318d54b950b908319fe50a0cfedefe8586036
ms.sourcegitcommit: 8edad75338cf74712ca1ab5d6631b9b52ff54410
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "43115983"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records-in-office-365"></a><span data-ttu-id="2ec9d-103">Buscar y corregir problemas después de agregar el dominio o los registros DNS en Office 365</span><span class="sxs-lookup"><span data-stu-id="2ec9d-103">Find and fix issues after adding your domain or DNS records in Office 365</span></span>

 <span data-ttu-id="2ec9d-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="2ec9d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2ec9d-p101">Configurar su dominio para que funcione con Office 365 puede ser todo un reto. El sistema DNS puede ser un poco enrevesado y la configuración DNS de su dominio afecta a importantes actividades empresariales, como el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2ec9d-p101">Getting your domain set up to work with Office 365 can be challenging. The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="2ec9d-107">Puede comprobar si hay problemas en el dominio comprobando su estado.</span><span class="sxs-lookup"><span data-stu-id="2ec9d-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="2ec9d-108">Vaya a **configuración** > de**dominios** y vea las notificaciones en la columna **Estado** .</span><span class="sxs-lookup"><span data-stu-id="2ec9d-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="2ec9d-109">Si ve un problema, seleccione más acciones (tres puntos) y, a continuación, elija **comprobar estado**.</span><span class="sxs-lookup"><span data-stu-id="2ec9d-109">If you see an issue, select More actions (three dots), and then choose **Check health**.</span></span> <span data-ttu-id="2ec9d-110">El panel que se abre describirá los problemas que se produzcan en su dominio.</span><span class="sxs-lookup"><span data-stu-id="2ec9d-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="2ec9d-111">¿Qué sucede?</span><span class="sxs-lookup"><span data-stu-id="2ec9d-111">What's going on?</span></span>

- [<span data-ttu-id="2ec9d-112">¿No puede comprobar el dominio?</span><span class="sxs-lookup"><span data-stu-id="2ec9d-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="2ec9d-113">¿Outlook no funciona?</span><span class="sxs-lookup"><span data-stu-id="2ec9d-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="2ec9d-114">EL correo electrónico de todos se ha cambiado a Office 365 y solo quiere cambiar el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2ec9d-114">Everyone's email got switched to Office 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="2ec9d-115">¿No puede confirmar el estado de la cuenta sin ánimo de lucro o educativa?</span><span class="sxs-lookup"><span data-stu-id="2ec9d-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="2ec9d-116">¿Los servicios no funcionan con el dominio?</span><span class="sxs-lookup"><span data-stu-id="2ec9d-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="2ec9d-117">¿No funciona el acceso al sitio web?</span><span class="sxs-lookup"><span data-stu-id="2ec9d-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="2ec9d-118">¿No puede comprobar su dominio?</span><span class="sxs-lookup"><span data-stu-id="2ec9d-118">Can't verify your domain?</span></span>
<span data-ttu-id="2ec9d-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="2ec9d-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="2ec9d-120">Hay algunas razones comunes por las que la comprobación del dominio puede no funcionar según lo esperado:</span><span class="sxs-lookup"><span data-stu-id="2ec9d-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="2ec9d-p103">**El valor del registro de comprobación no es del todo correcto.** Compruebe que ha copiado y pegado el valor exacto en el registro de comprobación TXT en su host DNS. Uno de los problemas habituales es no incluir la parte de "MS=" del registro. ¡También la necesitamos!</span><span class="sxs-lookup"><span data-stu-id="2ec9d-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="2ec9d-p104">**No se ha guardado el registro.** En algunos hosts DNS, tiene que llevar a cabo un paso adicional para guardar el archivo de zona (donde se almacena el registro DNS), de modo que se actualice a través de Internet. Asegúrese de que haya guardado los cambios de manera que Office 365 pueda ver y comprobar el registro.</span><span class="sxs-lookup"><span data-stu-id="2ec9d-p104">**The record hasn't been saved.** At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet. Make sure you've saved your changes so Office 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="2ec9d-128">**El registro no se ha actualizado a través de Internet.**</span><span class="sxs-lookup"><span data-stu-id="2ec9d-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="2ec9d-129">Normalmente, solo se tarda unos minutos para poder ver el nuevo registro, pero en ocasiones puede tardar varias horas en realizarse.</span><span class="sxs-lookup"><span data-stu-id="2ec9d-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="2ec9d-130">¿Outlook no funciona?</span><span class="sxs-lookup"><span data-stu-id="2ec9d-130">Outlook isn't working?</span></span>
<span data-ttu-id="2ec9d-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="2ec9d-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="2ec9d-132">Si ha configurado correctamente el registro MX y otros registros DNS de su dominio pero el correo electrónico no funciona, podemos ayudarle a [solucionar los problemas relacionados con Outlook](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span><span class="sxs-lookup"><span data-stu-id="2ec9d-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span></span>
  
## <a name="everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="2ec9d-133">EL correo electrónico de todos se ha cambiado a Office 365 y solo quiere cambiar el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2ec9d-133">Everyone's email got switched to Office 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="2ec9d-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="2ec9d-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="2ec9d-135">Al agregar el dominio a Office 365, normalmente el registro MX de su dominio se actualiza (por usted u Office 365) para que apunte a Office 365, y todos los correos electrónicos que se envíen a ese dominio empezarán a llegar a Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ec9d-135">When you add your domain to Office 365, typically your domain's MX record is updated (by you or Office 365) to point to Office 365, and ALL email sent to that domain will start coming to Office 365.</span></span> <span data-ttu-id="2ec9d-136">Asegúrese de que ha creado buzones en Office 365 para todos los usuarios que tienen correo electrónico en su dominio antes de cambiar el registro MX.</span><span class="sxs-lookup"><span data-stu-id="2ec9d-136">Make sure you've created mailboxes in Office 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="2ec9d-137">¿Qué ocurre si no desea mover el correo electrónico de todos los usuarios de su dominio a Office 365?</span><span class="sxs-lookup"><span data-stu-id="2ec9d-137">What if you don't want to move email for everyone on your domain to Office 365?</span></span> <span data-ttu-id="2ec9d-138">También puede seguir los pasos para [probar Office 365 con solo algunas direcciones de correo electrónico](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).</span><span class="sxs-lookup"><span data-stu-id="2ec9d-138">You can take steps to [pilot Office 365 with just a few email addresses instead](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="2ec9d-139">¿No puede confirmar el estado de la cuenta sin ánimo de lucro o educativa?</span><span class="sxs-lookup"><span data-stu-id="2ec9d-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="2ec9d-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="2ec9d-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="2ec9d-141">Hay un par de escenarios en los que solo tiene que comprobar el dominio de la organización y no configurar ningún servicio.</span><span class="sxs-lookup"><span data-stu-id="2ec9d-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="2ec9d-142">Por ejemplo, para demostrar a Office 365 que su organización es apto para una suscripción escolar.</span><span class="sxs-lookup"><span data-stu-id="2ec9d-142">For example, to prove to Office 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="2ec9d-143">Consulte las instrucciones en [comprobar el dominio de Office 365 para demostrar la propiedad, el estado de ONG o de educación, o para activar Yammer](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590) para asegurarse de que ha completado todos los pasos necesarios.</span><span class="sxs-lookup"><span data-stu-id="2ec9d-143">Check out the guidance in [Verify your Office 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="2ec9d-144">Es un poco diferente para cada situación.</span><span class="sxs-lookup"><span data-stu-id="2ec9d-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="2ec9d-145">¿Los servicios no funcionan con su dominio?</span><span class="sxs-lookup"><span data-stu-id="2ec9d-145">Services not working with your domain?</span></span>
<span data-ttu-id="2ec9d-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="2ec9d-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="2ec9d-147">Podemos ayudarle a localizar los problemas de configuración DNS de su dominio.</span><span class="sxs-lookup"><span data-stu-id="2ec9d-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="2ec9d-148">El solucionador de problemas de dominios de Office 365 le indicará si debe corregirse algún registro y cómo hacerlo exactamente.</span><span class="sxs-lookup"><span data-stu-id="2ec9d-148">The domains troubleshooter in Office 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="2ec9d-p111">¿Ha configurado DNS correctamente pero el correo electrónico no funciona en la versión de escritorio de Outlook? Consulte los [distintos escenarios de flujo de correo que puede tener en Office 365](https://go.microsoft.com/fwlink/?LinkId=787530) para asegurarse de que ha configurado todo correctamente para su empresa. O bien, obtenga más ayuda para solucionar problemas con el correo electrónico aquí: [Solucionar problemas de Outlook](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span><span class="sxs-lookup"><span data-stu-id="2ec9d-p111">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop? Check out the [different mail flow scenarios you can have with Office 365](https://go.microsoft.com/fwlink/?LinkId=787530) to make sure you've got things set up correctly for your business. Or get more troubleshooting help with email here: [Fix Outlook problems](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="2ec9d-152">¿El acceso a su sitio web no funciona?</span><span class="sxs-lookup"><span data-stu-id="2ec9d-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="2ec9d-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="2ec9d-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="2ec9d-154">Si ha corregido cualquier problema de DNS y sigue teniendo dificultades, pruebe los siguientes procedimientos.</span><span class="sxs-lookup"><span data-stu-id="2ec9d-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="2ec9d-155">Los usuarios no pueden obtener acceso al sitio web en www.mydomain.com: [localizar problemas de sitio web](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)</span><span class="sxs-lookup"><span data-stu-id="2ec9d-155">People can't get to your website at www.mydomain.com: [Track down website issues](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)</span></span>
    
- <span data-ttu-id="2ec9d-156">No puede actualizar su registro A o un registro CNAME para señalar a su sitio web: [Actualizar registros DNS personalizados en Office 365](../dns/add-or-edit-custom-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="2ec9d-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Office 365](../dns/add-or-edit-custom-dns-records.md)</span></span>
    
