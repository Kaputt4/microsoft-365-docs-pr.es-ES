---
title: ¿Cuál es el objetivo del registro CNAME adicional para Office 365?
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- scotvorg
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ms.service: microsoft-365-business
ms.localizationpriority: medium
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Obtenga más información sobre el registro CNAME "MSOID" en Office 365 que le dirige al mejor servidor para los procesos de autenticación, por lo que obtendrá una respuesta más rápida.
monikerRange: o365-21vianet
ms.openlocfilehash: fa9858f9bcbf92078fdedf539f27ade437e824c9
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68192583"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>¿Cuál es el objetivo del registro CNAME adicional para Office 365?

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
> [!NOTE]
> Lo siguiente solo se aplica a **Office 365 operado por 21Vianet.
  
You may wonder why you need to add the "MSOID" CNAME record in Office 365. This is a record that has to be added for all custom domains, no matter which subscription you use. Why do you need it? It's a little technical, but essentially, it's so that you'll be directed to the best server for certain authentication processes, so you'll get faster response.
  
Technical details: When you run a client application that works with Office 365 such as Skype for Business Online, Outlook, Windows PowerShell or Microsoft Azure Active Directory Sync tool, your credentials must be authenticated. Office 365 uses a CNAME record to point to the correct authentication endpoint for your location, which ensures rapid authentication response times.
  
If this CNAME record is missing for your domain, these applications will use a default authentication endpoint in the United States, which means authentication might be slower. If this CNAME record isn't configured properly—for example, if you have a typo in the **Points to address**—these applications won't be able to authenticate.
  
 **Si Office 365 administra los registros DNS del dominio,** Office 365 configura este registro CNAME automáticamente. 
  
 **Si va a administrar registros DNS para su dominio en el host DNS,** cree este registro usted mismo [siguiendo las instrucciones del host DNS](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).
  
Si está planeando una implementación de Office 365 y desea obtener más información sobre todos los registros DNS que puede que necesite agregar o actualizar, lea referencia[: Registros del sistema de nombres de dominio externo para Office 365](../../enterprise/external-domain-name-system-records.md).
