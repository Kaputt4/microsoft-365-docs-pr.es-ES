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
description: 'Cambie su dirección de correo electrónico inicial a una dirección de correo electrónico descriptiva como tom@fourthcoffee.com. Para ello, debe comprar un nombre de dominio y agregarlo a Microsoft 365. '
ms.openlocfilehash: d23c612eecae0a0b58d844fbbe25392ffa682fde
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656836"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Cambiar la dirección de correo electrónico para usar el dominio personalizado

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
  
::: moniker range="o365-worldwide"

Su dirección de correo electrónico inicial en Microsoft 365 incluye. onmicrosoft.com, como tom@fourthcoffee.onmicrosoft.com. Puede cambiarla por una más sencilla como tomas@fourthcoffee.com. Antes, necesitará su propio nombre de dominio, como fourthcoffee.com. Si ya tiene uno, ¡genial! Si no es así, puede obtener información sobre cómo [comprar uno en un registrador de dominios](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

Su dirección de correo electrónico inicial en Office 365 Germany incluye. onmicrosoft.de, como tom@fourthcoffee.onmicrosoft.de. Puede cambiarlo a una dirección más agradable como tom@fourthcoffee.de. Necesitará su propio nombre de dominio, como fourthcoffee.de primero. Si ya tiene uno, ¡genial! Si no es así, puede obtener información sobre cómo [comprar uno en un registrador de dominios](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

Su dirección de correo electrónico inicial en Office 365 operado por 21Vianet incluye partner.onmschina.cn, como tom@fourthcoffee.partner.onmschina.cn. Puede cambiarlo a una dirección más agradable como tom@fourthcoffee.cn. Necesitará su propio nombre de dominio, como fourthcoffee.cn primero. Si ya tiene uno, ¡genial! Si no es así, puede obtener información sobre cómo [comprar uno en un registrador de dominios](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

Al cambiar el correo electrónico de su dominio para que llegue a Microsoft 365, al actualizar el registro MX del dominio durante la instalación, todo el correo electrónico enviado a ese dominio empezará a llegar a Microsoft 365. Asegúrese de que ha agregado usuarios y los buzones de correo creados en Microsoft 365 para todos los usuarios que tengan correo electrónico en su dominio antes de cambiar el registro MX. ¿No quiere mover el correo electrónico de todos los usuarios de su dominio a Microsoft 365? Puede seguir los pasos para probar [Microsoft 365 con unas pocas direcciones de correo electrónico en su lugar](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide).
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Cambiar la dirección de correo electrónico para usar el dominio personalizado mediante el centro de administración de 365 de Microsoft

Debe tener una cuenta de administrador global para realizar estos pasos. 

::: moniker range="o365-worldwide"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>. 

::: moniker-end 

2. Vaya a la página de **configuración** de  >  **dominios** . 

3. En la página **Dominios**, seleccione **Agregar dominio**.
    
4. Siga los pasos para confirmar que es el dueño del dominio y para cambiar la dirección de correo electrónico.
    
Se le guiará para que todo se configure correctamente con su dominio en Microsoft 365.

> [!NOTE]
> Si no usa una licencia de Exchange, no puede usar el dominio para enviar o recibir mensajes de correo electrónico del inquilino de Microsoft 365.
  
## <a name="related-articles"></a>Artículos relacionados

[Compre un dominio personalizado con Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)
 
