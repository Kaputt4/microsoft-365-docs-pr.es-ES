---
title: Actualizar registros DNS para conservar su sitio web con su proveedor de hospedaje actual
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- highpri
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- VSBFY23
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Obtenga información sobre cómo enrutar el tráfico a un sitio web público existente hospedado fuera de Microsoft, si ha establecido Microsoft para administrar registros DNS para su dominio personalizado.
ms.openlocfilehash: ec6d62f5de7b4fdd6f06b482c818c8a6fbb1533f
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68729113"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Actualizar registros DNS para conservar su sitio web con su proveedor de hospedaje actual

 **Si administra los registros de Microsoft de su dominio en el proveedor de hospedaje DNS**, no tiene que preocuparse por los pasos descritos en este tema. El sitio web permanece en su ubicación y los usuarios pueden obtener acceso a él. 
  
 **Si Microsoft administra los registros DNS**, para enrutar el tráfico a un sitio web público existente hospedado fuera de Microsoft, después de agregar el dominio a Microsoft, haga lo siguiente: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Actualizar registros DNS en el Centro de administración de Microsoft 365
1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.

1. En la página **Dominios** , seleccione el dominio y, a continuación, elija **Registros DNS**.

1. Seleccione **+ Agregar registro** y escriba lo siguiente: 
    
   - Para **el tipo** , escriba: **A (Dirección)**
    
   - Como **Nombre de host o alias**, escriba " **@** ".
    
   - Como **Dirección IP**, escriba la dirección IP estática en la que se hospeda actualmente su sitio web (por ejemplo: 172.16.140.1). 
    
   This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website. 
    
1. Seleccione **Guardar**. 
    
Además, puede crear un registro CNAME para ayudar a los clientes a encontrar su sitio web.
  
1. Seleccione **+ Agregar registro** y escriba lo siguiente: 
    
   - Para **el tipo** , escriba: **CNAME (alias)**
    
   - Como **Nombre de host o alias**, escriba " **www** ".
    
   - Como **Dirección de destino**, escriba el FQDN (nombre de dominio completo) de su sitio web (por ejemplo, contoso.com). 
    
2. Seleccione **Guardar**. 
    
Por último, haga lo siguiente:
  
[Actualice los registros NS del dominio](../setup/add-domain.md) para que apunten a Microsoft. 
  
Cuando se han actualizado los registros NS para que apunten a Microsoft, todo el dominio está configurado. Email se enrutarán a Microsoft y el tráfico a la dirección del sitio web continuará hasta el host del sitio web actual.
