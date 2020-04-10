---
title: Buscar el registrador de dominios para Office 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Aprenda a encontrar su registrador de dominios y su proveedor de host DNS utilizando la búsqueda InterNIC.
ms.openlocfilehash: 71af74a0f94f2cdc251dab78fd59e9bdd90da5ce
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210397"
---
# <a name="find-your-domain-registrar-for-office-365"></a>Buscar el registrador de dominios para Office 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
## <a name="domain-registrar"></a>Registrador de dominios
  
### <a name="find-your-domain-name-registrar"></a>Buscar el registrador de nombre de dominio

>[!NOTE]
> Solo los dominios que terminen en *.COM*, *.NET* y *.EDU* funcionarán con esta herramienta.
  
1. En la página [búsqueda de InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770), en el cuadro **Búsqueda de Whois**, escriba el nombre de su dominio. Por ejemplo, *contoso.com.* 
    
2. Seleccione la opción **Dominio** y, a continuación, seleccione **Enviar**.
    
3. En la página **Whois Search Results** (Resultados de la búsqueda de Whois), busque la entrada **Registrar** (Registrador). En esta entrada se indica la organización que proporciona el servicio de registrador para su dominio. 
    
## <a name="dns-hosting-provider"></a>Proveedor de host DNS
  
### <a name="find-your-dns-hosting-provider"></a>Buscar su proveedor de host DNS

>[!NOTE]
> Solo los dominios que terminen en *.COM*, *.NET* y *.EDU* funcionarán con esta herramienta.
  
1. En la página [búsqueda de InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770), en el cuadro **Búsqueda de Whois**, escriba el nombre de su dominio. Por ejemplo, contoso.com. 
    
2. Seleccione la opción **Dominio** y, a continuación, seleccione **Enviar**.
    
3. En la página **Whois Search Results** (Resultados de la búsqueda de Whois), busque la primera entrada de **Name Server** (Servidor DNS). 
    
4. Copie la información del servidor DNS que aparece después de los dos puntos (:) y, después, péguela en el cuadro de **búsqueda** que hay en la parte superior de la página. Seleccione **Nameserver** y, a continuación, seleccione **Enviar**.
    
5. En la página **Resultados de la búsqueda de Whois**, busque la entrada **Registrador**, en la que se indica su proveedor de hospedaje de DNS, que es propietario del servidor DNS para su dominio. 
    
---

