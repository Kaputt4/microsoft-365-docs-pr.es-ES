---
title: Cambiar la dirección de correo electrónico para usar el dominio personalizado
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
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: Cambie su dirección de correo electrónico a una dirección de correo electrónico descriptivo como tom@fourthcoffee.com comprando un nombre de dominio y adición a Microsoft 365.
ms.openlocfilehash: d5e70856c9200cd7e5df0eded25b6ff460e5d1fe
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572098"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Cambiar la dirección de correo electrónico para usar el dominio personalizado

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
  
::: moniker range="o365-worldwide"

La dirección de correo electrónico inicial en Microsoft 365 incluye .onmicrosoft.com, como tom@fourthcoffee.onmicrosoft.com. Puede cambiarla por una más sencilla como tomas@fourthcoffee.com. Antes, necesitará su propio nombre de dominio, como fourthcoffee.com. Si ya tiene uno, ¡genial! Si no es así, puede obtener información sobre cómo [comprar uno en un registrador de dominios](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

La dirección de correo electrónico inicial en Office 365 Alemania incluye .onmicrosoft.de, como tom@fourthcoffee.onmicrosoft.de. Puedes cambiarla a una dirección más sencilla como tom@fourthcoffee.de. Necesitará su propio nombre de dominio, como fourthcoffee.de primero. Si ya tiene uno, ¡genial! Si no es así, puede obtener información sobre cómo [comprar uno en un registrador de dominios](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

La dirección de correo electrónico inicial en Office 365 operado por 21Vianet incluye partner.onmschina.cn, como tom@fourthcoffee.partner.onmschina.cn. Puedes cambiarla a una dirección más fácil como tom@fourthcoffee.cn. Necesitará su propio nombre de dominio, como fourthcoffee.cn primero. Si ya tiene uno, ¡genial! Si no es así, puede obtener información sobre cómo [comprar uno en un registrador de dominios](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

Cuando cambie el correo electrónico de su dominio para que llegue a Microsoft 365, al actualizar el registro MX del dominio durante la instalación, todo el correo electrónico enviado a ese dominio empezará a llegar a Microsoft 365. Asegúrese de que ha agregado usuarios y creado buzones en Microsoft 365 para todos los usuarios que tienen correo electrónico en su dominio ANTES de cambiar el registro MX. ¿No quiere mover el correo electrónico de todos los usuarios de su dominio a Microsoft 365? En su lugar, puede tomar [medidas para Microsoft 365 con solo unas cuantas](../misc/pilot-microsoft-365-from-my-custom-domain.md)direcciones de correo electrónico.
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Cambiar la dirección de correo electrónico para usar el dominio personalizado mediante el Centro Microsoft 365 administración

Debe tener una cuenta de administrador global para realizar estos pasos. 

::: moniker range="o365-worldwide"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al Centro <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>de administración en . 

::: moniker-end 

2. Vaya a la **página Dominios**  >  **de** instalación. 

3. En la página **Dominios**, seleccione **Agregar dominio**.
    
4. Siga los pasos para confirmar que es el dueño del dominio y para cambiar la dirección de correo electrónico.
    
Se te guiará para que todo se configure correctamente con tu dominio en Microsoft 365.

> [!NOTE]
> Si no usa una licencia Exchange, no puede usar el dominio para enviar o recibir correos electrónicos del Microsoft 365 inquilino.
  
## <a name="related-content"></a>Contenido relacionado

[Comprar un dominio personalizado mediante Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (artículo)
