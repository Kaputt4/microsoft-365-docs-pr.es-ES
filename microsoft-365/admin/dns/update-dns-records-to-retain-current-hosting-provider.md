---
title: Actualizar registros DNS para conservar su sitio web con su proveedor de hospedaje actual
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Obtén información sobre cómo enrutar el tráfico a un sitio web público existente alojado fuera de Microsoft, si has establecido Microsoft para administrar registros DNS para tu dominio personalizado.
ms.openlocfilehash: 2a1559bbb902375bbc363180cdb4f98ec2b3a939
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572146"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Actualizar registros DNS para conservar su sitio web con su proveedor de hospedaje actual

 **Si administras los registros de Microsoft de tu dominio en tu proveedor de hospedaje de DNS,** no tienes que preocuparte por los pasos de este tema. El sitio web permanece en su ubicación y los usuarios pueden obtener acceso a él. 
  
 **Si Microsoft administra los registros DNS,** para enrutar el tráfico a un sitio web público existente hospedado fuera de Microsoft, después de agregar el dominio a Microsoft, haga lo siguiente: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Actualizar registros DNS en el centro de administración de Microsoft 365
1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.

1. En la página **Dominios,** seleccione el dominio y, a continuación, elija **Registros DNS**.

1. Seleccione **+ Agregar registro** e introduzca lo siguiente: 
    
   - Para **el tipo** enter: A **(Dirección)**
    
   - Como **Nombre de host o alias**, escriba " **@** ".
    
   - Como **Dirección IP**, escriba la dirección IP estática en la que se hospeda actualmente su sitio web (por ejemplo: 172.16.140.1). 
    
   Esta dirección IP debe ser  *estática*  , no puede ser  *dinámica*  . Consulte al proveedor donde se hospeda el sitio web para asegurarse de que puede obtener una dirección IP estática para su sitio web público. 
    
1. Seleccione **Guardar**. 
    
Además, puede crear un registro CNAME para ayudar a los clientes a encontrar su sitio web.
  
1. Seleccione **+ Agregar registro** e introduzca lo siguiente: 
    
   - Para **el tipo** enter: **CNAME (Alias)**
    
   - Como **Nombre de host o alias**, escriba " **www** ".
    
   - Como **Dirección de destino**, escriba el FQDN (nombre de dominio completo) de su sitio web (por ejemplo, contoso.com). 
    
2. Seleccione **Guardar**. 
    
Por último, haga lo siguiente:
  
[Actualiza los registros NS de tu dominio](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) para que apunten a Microsoft. 
  
Cuando los registros de NS se han actualizado para que apunten a Microsoft, el dominio está configurado. El correo electrónico se enrutará a Microsoft y el tráfico a la dirección de su sitio web seguirá siendo al host actual del sitio web.
