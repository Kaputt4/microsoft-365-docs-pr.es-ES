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
description: Obtenga más información sobre el registro CNAME "MSOID" en Office 365 que le dirige al mejor servidor para los procesos de autenticación, de modo que obtenga una respuesta más rápida.
monikerRange: o365-21vianet
ms.openlocfilehash: aea04391768993c40978d94b50817244cd77405c
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655489"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>¿Cuál es el objetivo del registro CNAME adicional para Office 365?

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
> [!NOTE]
> Lo siguiente solo se aplica a **Office 365 operado por 21Vianet.
  
Puede preguntarse porqué tiene que agregar el "MSOID" registro CNAME en Office 365. Se trata de un registro que ha de agregarse para todos los dominios personalizados, independientemente de la suscripción que use. ¿Por qué es? Es un poco técnico, pero básicamente, es por lo que será dirigido a la mejor server para determinados procesos de autenticación, por lo que recibirá respuesta más rápida.
  
Al ejecutar una aplicación cliente que funcione con Office 365, como Skype Empresarial Online, Outlook, Windows PowerShell o la herramienta de sincronización de Microsoft Azure Active Directory, deben autenticarse las credenciales. Office 365 usa un registro CNAME que apunta al extremo de autenticación correcto para su ubicación, lo que garantiza tiempos de respuesta de autenticación rápidos.
  
Si en su dominio falta este registro CNAME, estas aplicaciones usarán un extremo de autenticación predeterminado que está ubicado en Estados Unidos, por lo que la autenticación puede ser más lenta. Si este registro CNAME no se configura correctamente (por ejemplo, si la **dirección de destino** contiene un error ortográfico), estas aplicaciones no podrán completar la autenticación.
  
 **Si Office 365 administra los registros DNS de su dominio,** Office 365 configura este registro CNAME automáticamente. 
  
 **Si está administrando registros DNS para su** dominio en el host DNS, cree este registro usted mismo siguiendo las instrucciones para su host [DNS.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)
  
Si está planeando una implementación de Office 365 y desea obtener más información sobre todos los registros DNS que puede que necesite agregar o actualizar, lea acerca de ellos en Referencia: Registros externos del sistema de nombres de dominio para [Office 365](https://go.microsoft.com/fwlink/?LinkId=579013).
  

