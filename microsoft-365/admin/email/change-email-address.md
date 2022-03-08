---
title: Cambiar la dirección de correo electrónico para usar el dominio personalizado
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
- adminvideo
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: Cambie su dirección de correo electrónico a una dirección de correo electrónico descriptivo como tom@fourthcoffee.com comprando un nombre de dominio y adición a Microsoft 365.
ms.openlocfilehash: 4630b3df4719611440e92801235fde20d7bd95f4
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63316427"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Cambiar la dirección de correo electrónico para usar el dominio personalizado

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
  
::: moniker range="o365-worldwide"

La dirección de correo electrónico inicial en Microsoft 365 incluye .onmicrosoft.com, como tom@fourthcoffee.onmicrosoft.com. Puede cambiarla por una más sencilla como tomas@fourthcoffee.com. Antes, necesitará su propio nombre de dominio, como fourthcoffee.com. Si ya tiene uno, ¡genial! Si no es así, puede obtener información sobre cómo [comprar uno en un registrador de dominios](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

La dirección de correo electrónico inicial en Office 365 operado por 21Vianet incluye partner.onmschina.cn, como tom@fourthcoffee.partner.onmschina.cn. Puedes cambiarla a una dirección más fácil como tom@fourthcoffee.cn. Necesitará su propio nombre de dominio, como fourthcoffee.cn primero. Si ya tiene uno, ¡genial! Si no es así, puede obtener información sobre cómo [comprar uno en un registrador de dominios](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

Cuando cambie el correo electrónico de su dominio para que llegue a Microsoft 365, al actualizar el registro MX del dominio durante la instalación, todo el correo electrónico enviado a ese dominio empezará a llegar a Microsoft 365. Asegúrese de que ha agregado usuarios y creado buzones en Microsoft 365 para todos los usuarios que tienen correo electrónico en su dominio ANTES de cambiar el registro MX. ¿No desea mover el correo electrónico de todos los usuarios de su dominio a Microsoft 365? En su lugar, puede tomar [medidas para Microsoft 365 con solo unas cuantas direcciones de correo electrónico](../misc/pilot-microsoft-365-from-my-custom-domain.md).
  
## <a name="set-up-business-email-with-a-new-domain"></a>Configurar el correo electrónico empresarial con un nuevo dominio

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyVVA?autoplay=false]

Compre un nuevo nombre de dominio para su dirección de correo electrónico y configure las direcciones de correo electrónico con Microsoft 365.

1. Compre un nuevo nombre de dominio para su dirección de correo electrónico proporcionando su información de contacto para el nuevo nombre de dominio, eligiendo el método de pago y, a continuación, realizando el pedido.
1. Cambie la primera parte de la dirección (antes del signo @) o déjela tal como está. 
1. Cerrar sesión Microsoft 365 y, a continuación, volver a iniciar sesión con la nueva dirección de correo electrónico. Las direcciones de correo electrónico de los empleados se actualizan con el nuevo dominio. 

## <a name="set-up-business-email-with-an-existing-domain"></a>Configurar el correo electrónico empresarial con un dominio existente

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxApu?autoplay=false]

Use un nombre de dominio que ya posee si lo está usando para una dirección de sitio web o una dirección de correo electrónico en otro proveedor.

1. Inicie sesión en el sitio web que hospeda el dominio. Haga clic en un botón para comprobar automáticamente o actualizar el dominio manualmente. 
1. Personalice la dirección de correo electrónico o déjela tal como está.
1. Cerrar sesión Microsoft 365 y, a continuación, volver a iniciar sesión con la nueva dirección de correo electrónico. Las direcciones de correo electrónico de los empleados se actualizan con el nuevo dominio.

## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Cambie su dirección de correo electrónico para usar su dominio personalizado mediante el Centro de administración de Microsoft 365

Para poder realizar estos pasos, debe ser Administrador global.

::: moniker range="o365-worldwide"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>.

::: moniker-end

2. Vaya a la **página** **SetupDomains** > .

3. En la página **Dominios**, seleccione **Agregar dominio**.

4. Siga los pasos para confirmar que es el propietario de su dominio. Se te guiará para que todo se configure correctamente con tu dominio en Microsoft 365.

5. Vaya a **UsuariosActivos** > .

6. Seleccione un usuario para editar su nombre de usuario y cambiarlo al dominio que acaba de agregar.

> [!NOTE]
> Si no usa una licencia Exchange, no puede usar el dominio para enviar o recibir correos electrónicos del Microsoft 365 inquilino.
  
## <a name="related-content"></a>Contenido relacionado

[Comprar un dominio personalizado con Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (artículo)\
[Administrar dominios](/admin) (página de vínculos)\
[Preguntas más frecuentes sobre dominios](../setup/domains-faq.yml) (artículo)