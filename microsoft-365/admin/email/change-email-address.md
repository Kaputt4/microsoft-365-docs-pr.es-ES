---
title: Cambiar la dirección de correo electrónico para usar el dominio personalizado
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
description: Cambie su dirección de correo electrónico a una dirección de correo electrónico descriptivo como tom@fourthcoffee.com comprando un nombre de dominio y añadiéndolo a Microsoft 365.
ms.openlocfilehash: 8439689d8006d400cf2ef3f8498e1a9b80d455df
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68719016"
---
# <a name="change-your-microsoft-365-email-address-to-use-your-custom-domain"></a>Cambiar la dirección de correo electrónico de Microsoft 365 para usar el dominio personalizado

Consulte [ayuda de Microsoft 365 para pequeñas empresas](https://go.microsoft.com/fwlink/?linkid=2197659) en YouTube.

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
  
::: moniker range="o365-worldwide"

La dirección de correo electrónico inicial de Microsoft 365 incluye .onmicrosoft.com, como tom@fourthcoffee.onmicrosoft.com. Puede cambiarla por una más sencilla como tomas@fourthcoffee.com. Antes, necesitará su propio nombre de dominio, como fourthcoffee.com. Si ya tiene uno, ¡genial! Si no es así, puede obtener información sobre cómo [comprar uno en un registrador de dominios](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

Su dirección de correo electrónico inicial en Office 365 operada por 21Vianet incluye partner.onmschina.cn, como tom@fourthcoffee.partner.onmschina.cn. Puede cambiarla a una dirección más amigable como tom@fourthcoffee.cn. Necesitará su propio nombre de dominio, como fourthcoffee.cn primero. Si ya tiene uno, ¡genial! Si no es así, puede obtener información sobre cómo [comprar uno en un registrador de dominios](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

Al cambiar el correo electrónico del dominio para que llegue a Microsoft 365, actualizando el registro MX del dominio durante la instalación, todo el correo electrónico enviado a ese dominio comenzará a llegar a Microsoft 365. Asegúrese de haber agregado usuarios y creado buzones en Microsoft 365 para todos los usuarios que tengan correo electrónico en su dominio ANTES de cambiar el registro MX. ¿No quieres mover el correo electrónico de todos los usuarios de tu dominio a Microsoft 365? En su lugar, puede realizar pasos para [probar Microsoft 365 con solo algunas direcciones de correo electrónico](../misc/pilot-microsoft-365-from-my-custom-domain.md).
  
## <a name="set-up-business-email-with-a-new-domain"></a>Configuración del correo electrónico empresarial con un nuevo dominio

Consulte este vídeo y otros en nuestro [canal de YouTube](https://go.microsoft.com/fwlink/?linkid=2198215).

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyVVA?autoplay=false]

Compre un nuevo nombre de dominio para su dirección de correo electrónico y configure las direcciones de correo electrónico con Microsoft 365.

1. Compre un nuevo nombre de dominio para su dirección de correo electrónico proporcionando su información de contacto para el nuevo nombre de dominio, eligiendo el método de pago y, a continuación, realizando el pedido.
1. Cambie la primera parte de la dirección (antes del signo @ ) o déjela tal como está. 
1. Cierre la sesión de Microsoft 365 y vuelva a iniciar sesión con su nueva dirección de correo electrónico. Las direcciones de correo electrónico de los empleados se actualizan con el nuevo dominio. 

## <a name="set-up-business-email-with-an-existing-domain"></a>Configuración del correo electrónico empresarial con un dominio existente

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxApu?autoplay=false]

Use un nombre de dominio que ya posea si lo usa para una dirección de sitio web o una dirección de correo electrónico en otro proveedor.

1. Inicie sesión en el sitio web que hospeda el dominio. Haga clic en un botón para comprobar automáticamente o actualizar el dominio manualmente. 
1. Personalice la dirección de correo electrónico o déjela tal como está.
1. Cierre la sesión de Microsoft 365 y vuelva a iniciar sesión con su nueva dirección de correo electrónico. Las direcciones de correo electrónico de los empleados se actualizan con el nuevo dominio.

## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Cambie la dirección de correo electrónico para usar el dominio personalizado mediante el Centro de administración de Microsoft 365

Para poder realizar estos pasos, debe ser Administrador global.

::: moniker range="o365-worldwide"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>.

::: moniker-end

2. Vaya a la página **Dominios** **de instalación** > .

3. En la página **Dominios**, seleccione **Agregar dominio**.

4. Siga los pasos para confirmar que es propietario de su dominio. Se le guiará para que todo esté configurado correctamente con su dominio en Microsoft 365.

5. Vaya a **Usuarios** > **usuarios activos**.

6. Seleccione un usuario para editar su nombre de usuario y cambiarlo al dominio que acaba de agregar.

> [!NOTE]
> Si no usa una licencia de Exchange, no puede usar el dominio para enviar o recibir correos electrónicos del inquilino de Microsoft 365.
  
## <a name="related-content"></a>Contenido relacionado

[Comprar un dominio personalizado con Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (artículo)\
[Administrar dominios](/admin) (página de vínculo)\
[Preguntas más frecuentes sobre dominios](../setup/domains-faq.yml) (artículo)