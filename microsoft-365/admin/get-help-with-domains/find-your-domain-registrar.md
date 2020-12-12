---
title: Buscar su registrador de dominios
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Aprenda a encontrar su registrador de dominios y su proveedor de host DNS utilizando la búsqueda InterNIC.
ms.openlocfilehash: 434e30709b112cf591159a1692540b8ef2b6bb65
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655547"
---
# <a name="find-your-domain-registrar"></a>Buscar su registrador de dominios

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
  
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

