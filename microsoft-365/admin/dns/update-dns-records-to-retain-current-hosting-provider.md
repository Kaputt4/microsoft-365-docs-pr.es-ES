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
description: Learn how to route traffic to an existing public website hosted outside of Microsoft, if you have set Microsoft to manage DNS records for your custom domain.
ms.openlocfilehash: 5d2bf23d4052815fae210d0fdf6635288ff46b57
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645568"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Actualizar registros DNS para conservar su sitio web con su proveedor de hospedaje actual

 **Si administra los registros de Microsoft** de su dominio en su proveedor de hospedaje DNS, no tiene que preocuparse por los pasos de este tema. El sitio web permanece en su ubicación y los usuarios pueden obtener acceso a él. 
  
 **Si Microsoft administra los** registros DNS, para enrutar el tráfico a un sitio web público existente hospedado fuera de Microsoft, después de agregar su dominio a Microsoft, haga lo siguiente: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Actualizar registros DNS en el Centro de administración de Microsoft 365
1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.

2. En la **página Dominios,** seleccione el dominio y, a continuación, elija **Registros DNS.**

3. En **Configuración dns,** seleccione **Registros personalizados.**

4. Seleccione **Nuevo registro personalizado** y escriba lo siguiente: 
    
   - Como **Tipo DNS**, escriba " **D (Dirección)** ".
    
   - Como **Nombre de host o alias**, escriba " **@** ".
    
   - Como **Dirección IP**, escriba la dirección IP estática en la que se hospeda actualmente su sitio web (por ejemplo: 172.16.140.1). 
    
   Esta dirección IP debe ser  *estática*  , no puede ser  *dinámica*  . Consulte al proveedor donde se hospeda el sitio web para asegurarse de que puede obtener una dirección IP estática para su sitio web público. 
    
5. Seleccione **Guardar**. 
    
Además, puede crear un registro CNAME para ayudar a los clientes a encontrar su sitio web.
  
1. Seleccione **Nuevo registro personalizado** y escriba lo siguiente: 
    
   - Como **Tipo DNS**, escriba " **CNAME (Alias)** ".
    
   - Como **Nombre de host o alias**, escriba " **www** ".
    
   - Como **Dirección de destino**, escriba el FQDN (nombre de dominio completo) de su sitio web (por ejemplo, contoso.com). 
    
2. Seleccione **Guardar**. 
    
Por último, haga lo siguiente:
  
[Actualice los registros NS de su dominio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) para que apunten a Microsoft. 
  
Cuando los registros NS se hayan actualizado para que apunten a Microsoft, el dominio está todo configurado. El correo electrónico se enruta a Microsoft y el tráfico a la dirección de su sitio web continuará en el host de su sitio web actual.
 
