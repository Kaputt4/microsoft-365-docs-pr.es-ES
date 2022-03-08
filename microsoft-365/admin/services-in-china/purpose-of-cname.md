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
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Obtenga más información sobre el registro CNAME 'MSOID' en Office 365 que le dirige al mejor servidor para procesos de autenticación, por lo que obtiene una respuesta más rápida.
monikerRange: o365-21vianet
ms.openlocfilehash: 1b053ac0df7cd770b5627b688e90641688f94141
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325129"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>¿Cuál es el objetivo del registro CNAME adicional para Office 365?

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
> [!NOTE]
> Lo siguiente solo se aplica a **Office 365 operado por 21Vianet.
  
Puede preguntarse porqué tiene que agregar el "MSOID" registro CNAME en Office 365. Se trata de un registro que ha de agregarse para todos los dominios personalizados, independientemente de la suscripción que use. ¿Por qué es? Es un poco técnico, pero básicamente, es por lo que será dirigido a la mejor server para determinados procesos de autenticación, por lo que recibirá respuesta más rápida.
  
Al ejecutar una aplicación cliente que funcione con Office 365, como Skype Empresarial Online, Outlook, Windows PowerShell o la herramienta de sincronización de Microsoft Azure Active Directory, deben autenticarse las credenciales. Office 365 usa un registro CNAME que apunta al extremo de autenticación correcto para su ubicación, lo que garantiza tiempos de respuesta de autenticación rápidos.
  
Si en su dominio falta este registro CNAME, estas aplicaciones usarán un extremo de autenticación predeterminado que está ubicado en Estados Unidos, por lo que la autenticación puede ser más lenta. Si este registro CNAME no se configura correctamente (por ejemplo, si la **dirección de destino** contiene un error ortográfico), estas aplicaciones no podrán completar la autenticación.
  
 **Si Office 365 los registros DNS** de su dominio, Office 365 configura este registro CNAME automáticamente. 
  
 **Si va a administrar registros DNS para su dominio en el host DNS,** cree este registro usted mismo siguiendo las instrucciones [del host DNS](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).
  
Si está planeando una implementación de Office 365 y desea obtener más información sobre todos los registros DNS que puede que necesite agregar o actualizar, lea acerca de ellos en Referencia: Registros del sistema de nombres de dominio externos [para Office 365](../../enterprise/external-domain-name-system-records.md).
