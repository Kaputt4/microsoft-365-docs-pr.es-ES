---
title: Actualizar registros DNS para conservar su sitio web con su proveedor de hospedaje actual
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Obtenga información sobre cómo enrutar el tráfico a un sitio web público existente hospedado fuera de Microsoft, si ha establecido que Microsoft administre los registros DNS para su dominio personalizado.
ms.openlocfilehash: 08a4e505f4e2a50b3e92cae00b62415e6d02551f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629124"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Actualizar registros DNS para conservar su sitio web con su proveedor de hospedaje actual

 **Si administra los registros de Microsoft de su dominio en su proveedor de host DNS**, no tendrá que preocuparse por los pasos que se indican en este tema. El sitio web permanece en su ubicación y los usuarios pueden obtener acceso a él. 
  
 **Si Microsoft administra los registros DNS**para enrutar el tráfico a un sitio web público existente hospedado fuera de Microsoft, haga lo siguiente después de agregar el dominio a Microsoft: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Actualizar registros DNS en el centro de administración de 365 de Microsoft
1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.

2. En la página **Dominios**, en la lista de dominios, seleccione el que use para su sitio web y, después, **Configuración de DNS** en el panel de administración. 
    
3. Seleccione **Nuevo registro personalizado** y escriba lo siguiente: 
    
  - Como **Tipo DNS**, escriba " **D (Dirección)** ".
    
  - Como **Nombre de host o alias**, escriba " **@** ".
    
  - Como **Dirección IP**, escriba la dirección IP estática en la que se hospeda actualmente su sitio web (por ejemplo: 172.16.140.1). 
    
    Esta dirección IP debe ser  *estática*  , no puede ser  *dinámica*  . Consulte al proveedor donde se hospeda el sitio web para asegurarse de que puede obtener una dirección IP estática para su sitio web público. 
    
3. Seleccione **Guardar**. 
    
Además, puede crear un registro CNAME para ayudar a los clientes a encontrar su sitio web.
  
1. Seleccione **Nuevo registro personalizado** y escriba lo siguiente: 
    
  - Como **Tipo DNS**, escriba " **CNAME (Alias)** ".
    
  - Como **Nombre de host o alias**, escriba " **www** ".
    
  - Como **Dirección de destino**, escriba el FQDN (nombre de dominio completo) de su sitio web (por ejemplo, contoso.com). 
    
2. Seleccione **Guardar**. 
    
Por último, haga lo siguiente:
  
[Actualice los registros NS de su dominio](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) para que apunten a Microsoft. 
  
Cuando se hayan actualizado los registros NS para que apunten a Microsoft, su dominio se habrá configurado. El correo electrónico se redirigirá a Microsoft y el tráfico a la dirección del sitio Web continuará a través de su host de sitio web actual.
 
