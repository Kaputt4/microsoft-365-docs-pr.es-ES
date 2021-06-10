---
title: Recopilar la información que necesita para crear registros DNS
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Recopila los valores/información que necesita para crear registros DNS para conectar su dominio a su Microsoft 365 suscripción.
ms.openlocfilehash: e65d53269f5fb8625b12c4eb22f78516818045be
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635731"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>Recopilar la información que necesita para crear registros DNS

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Paso 1: Buscar el valor del registro TXT y comprobar

::: moniker range="o365-worldwide"

1. En el centro Microsoft 365 administración, vaya a la página **Dominios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">de instalación.</a>

::: moniker-end

::: moniker range="o365-germany"

1. En el Centro de administración, vaya a la página **Dominios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">de</a> instalación.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el Centro de administración, vaya a la página **Dominios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">de</a> instalación.

::: moniker-end
    
2. En la **página Dominios,** seleccione el dominio y, a continuación, **seleccione Iniciar instalación.** Volverá al asistente de configuración de dominios para ver el valor específico que debe agregar.
    
3. En la **página Comprobar dominio,** seleccione **Agregar un registro TXT** en su lugar y, a continuación, **seleccione Siguiente**.
    
4. Copie el **valor TXT que se** muestra. Tiene el siguiente aspecto: **MS=msXXXXXXXX**. 
    
5. Vaya a [Crear registros DNS en cualquier proveedor](create-dns-records-at-any-dns-hosting-provider.md)de hospedaje DNS y seleccione el host DNS de la lista de registradores para ver las instrucciones paso a paso.
    
6. Siga los pasos para crear el registro TXT (o registro MX) en el host DNS y, a continuación, compruebe el dominio de nuevo en Microsoft 365.

7. Quite el registro TXT (o registro MX) del host DNS una vez comprobado el dominio en Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Paso 2: Buscar el valor del registro MX para el correo electrónico y mucho más

::: moniker range="o365-worldwide"

1. En el centro Microsoft 365 administración, vaya a la página **Dominios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">de instalación.</a>

::: moniker-end
    
::: moniker range="o365-germany"

1. En el Centro de administración, vaya a la página **Dominios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">de</a> instalación.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el Centro de administración, vaya a la página **Dominios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">de</a> instalación.

::: moniker-end
    
2. En la página **Dominios**, seleccione su dominio. 
    
3. En **Configuración DNS requerida**, verá los registros DNS para agregar.
    
    Querrá mantener esta información disponible mientras realiza cambios en su host DNS, para poder copiar y pegar los valores.
    
    Los grupos de registros DNS que aparecen en esta página varían en función de las opciones que se seleccionan en **Finalidad del dominio**.
    
4. Vaya a Crear registros DNS en cualquier proveedor de hospedaje [DNS](create-dns-records-at-any-dns-hosting-provider.md)y, a continuación, seleccione el host DNS de la lista de registradores para ver instrucciones paso a paso para agregar registros en el sitio web del host DNS.
    
5. Si el host DNS no tiene un vínculo en la página, puede seguir las instrucciones generales.

## <a name="related-content"></a>Contenido relacionado

[Preguntas más frecuentes sobre dominios](../setup/domains-faq.yml) (artículo)\
[Buscar y corregir problemas después de agregar el dominio o los registros DNS](find-and-fix-issues.md) (artículo)\
[Administrar dominios](index.yml) (página de vínculo)