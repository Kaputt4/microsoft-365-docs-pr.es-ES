---
title: Recopilación de la información necesaria para crear registros DNS
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
- Adm_O365_Setup
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Recopile los valores o la información que necesita para crear registros DNS para conectar el dominio a su suscripción de Microsoft 365.
ms.openlocfilehash: d63252881fc40cad8dba9acbdc345871163354bc
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68729773"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>Recopilación de la información necesaria para crear registros DNS

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Paso 1: Buscar el valor del registro TXT y comprobar

::: moniker range="o365-worldwide"

1. En el Centro de administración de Microsoft 365, vaya a la página **Dominios de configuración**\>.<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a>

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">dominios</a>.

::: moniker-end
    
2. En la página **Dominios** , seleccione el dominio y, a continuación, seleccione **Iniciar configuración**. Volverá al asistente de configuración de dominios para ver el valor específico que debe agregar.
    
3. En la página **Comprobación del dominio** , seleccione **Agregar un registro TXT a los registros DNS del dominio** y, a continuación, seleccione **Continuar**.
    
4. Copie el **valor TXT** que se muestra. Tiene este aspecto: **MS=msXXXXXXXX**. 
    
5. Vaya a [Agregar registros DNS para conectar el dominio](create-dns-records-at-any-dns-hosting-provider.md) y siga los pasos para agregar registros en el sitio web del host DNS.
    
6. Siga los pasos para crear el registro TXT (o registro MX) en el host DNS y, a continuación, compruebe el dominio de nuevo en Microsoft 365.

7. Quite el registro TXT (o registro MX) del host DNS una vez comprobado el dominio en Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Paso 2: Buscar el valor del registro MX para el correo electrónico y mucho más

::: moniker range="o365-worldwide"

1. En el Centro de administración de Microsoft 365, vaya a la página **Dominios de configuración**\>.<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a>

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">dominios</a>.

::: moniker-end
    
2. En la página **Dominios**, seleccione su dominio.
    
3. Elija  **Administrar DNS**, seleccione **Más opciones** > **Agregar su propio DNS** y seleccione **Continuar** para ver los registros DNS que se van a agregar.
    
    Querrá mantener esta información disponible mientras realiza cambios en su host DNS, para poder copiar y pegar los valores.
    
    Los grupos de registros DNS que aparecen en esta página varían en función de las opciones que se seleccionan en **Finalidad del dominio**.
    
4. Vaya a [Agregar registros DNS para conectar el dominio](create-dns-records-at-any-dns-hosting-provider.md) y siga los pasos para agregar registros en el sitio web del host DNS.

5. Si el host DNS no tiene un vínculo en la página, puede seguir las instrucciones generales.

## <a name="related-content"></a>Contenido relacionado

[Preguntas más frecuentes sobre dominios](../setup/domains-faq.yml) (artículo)\
[Buscar y corregir problemas después de agregar el dominio o los registros DNS](find-and-fix-issues.md) (artículo)\
[Administrar dominios](/admin) (página de vínculo)