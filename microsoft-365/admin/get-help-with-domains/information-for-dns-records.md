---
title: Recopilar la información necesaria para crear los registros DNS
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Aprenda a encontrar los valores y la información que necesita para crear registros DNS para Microsoft 365. '
ms.openlocfilehash: eca9dbe4e40193f76538b639624b827177ff7772
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645316"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>Recopilar la información necesaria para crear los registros DNS

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Paso 1: buscar el valor del registro TXT y comprobar

::: moniker range="o365-worldwide"

1. En el centro de administración de Microsoft 365, vaya a la página de **configuración** de \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página de **configuración** de > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">dominios</a> .

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página de **configuración** de > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">dominios</a> .

::: moniker-end
    
2. En la página **dominios** , seleccione su dominio y, a continuación, seleccione **Iniciar configuración**. Volverá al asistente de configuración de dominios para ver el valor específico que debe agregar.
    
3. En la página **comprobar dominio** , seleccione **Agregar un registro TXT**y, a continuación, haga clic en **siguiente**.
    
4. Copie el **valor txt** que se muestra. Tiene este aspecto: **MS = msXXXXXXXX**. 
    
5. Vaya a [crear registros DNS en cualquier proveedor](create-dns-records-at-any-dns-hosting-provider.md)de host DNS y seleccione su host DNS de la lista de registradores para ver las instrucciones paso a paso.
    
6. Siga los pasos para crear el registro TXT (o registro MX) en su host DNS y, después, vuelva a comprobar el dominio en Microsoft 365.

7. Quite el registro TXT (o registro MX) de su host DNS una vez que se haya comprobado el dominio en Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Paso 2: buscar el valor del registro MX para el correo electrónico y más

::: moniker range="o365-worldwide"

1. En el centro de administración de Microsoft 365, vaya a la página de **configuración** de \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .

::: moniker-end
    
::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página de **configuración** de > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">dominios</a> .

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página de **configuración** de > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">dominios</a> .

::: moniker-end
    
2. En la página **Dominios**, seleccione su dominio. 
    
3. En **Configuración DNS requerida**, verá los registros DNS para agregar.
    
    Querrá mantener esta información disponible mientras realiza cambios en su host DNS, para poder copiar y pegar los valores.
    
    Los grupos de registros DNS que aparecen en esta página varían en función de las opciones que se seleccionan en **Finalidad del dominio**.
    
4. Vaya a [crear registros DNS en cualquier proveedor de host DNS](create-dns-records-at-any-dns-hosting-provider.md)y, a continuación, seleccione su host DNS de la lista de registradores para ver instrucciones paso a paso para agregar registros en el sitio web del host DNS.
    
5. Si el host DNS no tiene un vínculo en la página, puede seguir las instrucciones generales.
