---
title: ¿Cuál es el objetivo del registro CNAME adicional para Office 365?
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Obtenga más información sobre el registro CNAME 'MSOID' en Office 365 que le dirige al mejor servidor para procesos de autenticación, de modo que obtenga una respuesta más rápida.
monikerRange: o365-21vianet
ms.openlocfilehash: a1d587abc9db03c9a1f7c5f66711fde3648a0e96
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914311"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a><span data-ttu-id="5623d-103">¿Cuál es el objetivo del registro CNAME adicional para Office 365?</span><span class="sxs-lookup"><span data-stu-id="5623d-103">What's the purpose of the Office 365 CNAME record for MSOID?</span></span>

 <span data-ttu-id="5623d-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="5623d-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
> [!NOTE]
> <span data-ttu-id="5623d-105">Lo siguiente solo se aplica a \*\*Office 365 operado por 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="5623d-105">The following only Applies to \*\*Office 365 operated by 21Vianet.</span></span>
  
<span data-ttu-id="5623d-p101">Puede preguntarse porqué tiene que agregar el "MSOID" registro CNAME en Office 365. Se trata de un registro que ha de agregarse para todos los dominios personalizados, independientemente de la suscripción que use. ¿Por qué es? Es un poco técnico, pero básicamente, es por lo que será dirigido a la mejor server para determinados procesos de autenticación, por lo que recibirá respuesta más rápida.</span><span class="sxs-lookup"><span data-stu-id="5623d-p101">You may wonder why you need to add the "MSOID" CNAME record in Office 365. This is a record that has to be added for all custom domains, no matter which subscription you use. Why do you need it? It's a little technical, but essentially, it's so that you'll be directed to the best server for certain authentication processes, so you'll get faster response.</span></span>
  
<span data-ttu-id="5623d-p102">Al ejecutar una aplicación cliente que funcione con Office 365, como Skype Empresarial Online, Outlook, Windows PowerShell o la herramienta de sincronización de Microsoft Azure Active Directory, deben autenticarse las credenciales. Office 365 usa un registro CNAME que apunta al extremo de autenticación correcto para su ubicación, lo que garantiza tiempos de respuesta de autenticación rápidos.</span><span class="sxs-lookup"><span data-stu-id="5623d-p102">Technical details: When you run a client application that works with Office 365 such as Skype for Business Online, Outlook, Windows PowerShell or Microsoft Azure Active Directory Sync tool, your credentials must be authenticated. Office 365 uses a CNAME record to point to the correct authentication endpoint for your location, which ensures rapid authentication response times.</span></span>
  
<span data-ttu-id="5623d-p103">Si en su dominio falta este registro CNAME, estas aplicaciones usarán un extremo de autenticación predeterminado que está ubicado en Estados Unidos, por lo que la autenticación puede ser más lenta. Si este registro CNAME no se configura correctamente (por ejemplo, si la **dirección de destino** contiene un error ortográfico), estas aplicaciones no podrán completar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="5623d-p103">If this CNAME record is missing for your domain, these applications will use a default authentication endpoint in the United States, which means authentication might be slower. If this CNAME record isn't configured properly—for example, if you have a typo in the **Points to address**—these applications won't be able to authenticate.</span></span>
  
 <span data-ttu-id="5623d-114">**Si Office 365 administra los registros DNS de su dominio,** Office 365 configura este registro CNAME automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5623d-114">**If Office 365 manages your domain's DNS records,** Office 365 sets up this CNAME record for you.</span></span> 
  
 <span data-ttu-id="5623d-115">**Si va a administrar registros DNS para su** dominio en el host DNS, cree este registro usted mismo siguiendo las instrucciones del host [DNS](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="5623d-115">**If you are managing DNS records for your domain at your DNS host,** you create this record yourself by [following the instructions for your DNS host](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>
  
<span data-ttu-id="5623d-116">Si está planeando una implementación de Office 365 y desea obtener más información sobre todos los registros DNS que puede que necesite agregar o actualizar, lea acerca de ellos en Referencia: Registros del sistema de nombres de dominio externos para [Office 365](../../enterprise/external-domain-name-system-records.md).</span><span class="sxs-lookup"><span data-stu-id="5623d-116">If you're planning an Office 365 deployment and want to learn more about all the DNS records that you may need to add or update, read about them in [Reference: External Domain Name System records for Office 365](../../enterprise/external-domain-name-system-records.md).</span></span>
