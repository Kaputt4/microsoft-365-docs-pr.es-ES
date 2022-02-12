---
title: Quitar un dominio
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
- AdminSurgePortfolio
- AdminTemplateSet
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Obtenga información sobre cómo quitar un dominio antiguo de Microsoft 365 y mover usuarios y grupos a otro dominio o cancelar la suscripción.
ms.openlocfilehash: 875858804912ab75d0a5a0bab45c9bb1614c82ca
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2022
ms.locfileid: "62765161"
---
# <a name="remove-a-domain"></a>Quitar un dominio

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

¿Está quitando el dominio porque desea agregarlo a un plan de Microsoft 365 suscripción diferente? ¿O solo quiere cancelar su suscripción? Puede [cambiar su plan o suscripción](../../commerce/subscriptions/switch-to-a-different-plan.md), o bien [cancelar la suscripción](../../commerce/subscriptions/cancel-your-subscription.md).

> [!TIP]
> Si necesita ayuda con los pasos de este tema, considere la posibilidad de [trabajar con un especialista en pequeñas empresas de Microsoft](https://go.microsoft.com/fwlink/?linkid=2186871). Con Business Assist, usted y sus empleados obtienen acceso diario a los especialistas de pequeñas empresas a medida que crece su negocio, desde la incorporación hasta el uso diario.

### <a name="step-1-move-users-to-another-domain"></a>Paso 1: Mover usuarios a otro dominio

#### <a name="move-users"></a>Mover usuarios

::: moniker range="o365-worldwide"

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Centro de administración</a>.

::: moniker-end

2. Seleccione **UsuariosActivos** > .

3. Seleccione los cuadros junto a los nombres de todos los usuarios que desea mover.

4. En la parte superior de la página y, a continuación, elija **Cambiar dominios**.

5. En el **panel Cambiar dominios** , seleccione un dominio diferente.

Tendrá que realizar esta acción también para su propio usuario si se encuentra en el dominio que quiere quitar. Al editar el dominio para su cuenta, tendrá que cerrar sesión y volver a iniciarla con el dominio nuevo que eligió para continuar.

#### <a name="move-yourself"></a>Muévete

::: moniker range="o365-worldwide"

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Centro de administración</a>.

::: moniker-end

2. Vaya a **Usuarios** \> **usuarios activos** y seleccione su cuenta en la lista.

3. En la **pestaña Cuenta** , seleccione **Administrar nombre de usuario** y, a continuación, elija un dominio diferente.

4. En la parte superior, seleccione el nombre de la cuenta y, a continuación, seleccione **Cerrar sesión**.

5. Inicie sesión con el nuevo dominio y la misma contraseña.

También puede usar PowerShell para mover los usuarios a otro dominio. Vea [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname) para obtener más información. Para establecer el dominio predeterminado, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).

### <a name="step-2-move-groups-to-another-domain"></a>Paso 2: Mover grupos a otro dominio

::: moniker range="o365-worldwide"

1. En el Centro de administración, vaya a la **página Grupos**\>.<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a>

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Centro de administración</a>, vaya a la **página Grupos**>.

::: moniker-end

2. Seleccione el nombre del grupo y, a continuación, en la **pestaña General** , en **Dirección de correo electrónico,** Principal, seleccione **Editar**.

3. Use la lista desplegable para elegir otro dominio.

4. Seleccione **Guardar** y, a continuación, **Cerrar**. Repita este proceso para todas las listas de distribución o grupos que estén asociados al dominio que quiere quitar.

### <a name="step-3-remove-the-old-domain"></a>Paso 3: Quitar el dominio antiguo

::: moniker range="o365-worldwide"

1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el Centro de administración, vaya a la página **Dominios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">de</a> instalación.

::: moniker-end

2. En la **página Dominios** , seleccione el dominio que desea quitar.

3. En el panel derecho, seleccione **Quitar**.

4. Siga los avisos adicionales y, a continuación, **seleccione Cerrar**.

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>¿Cuánto tiempo tarda un dominio en quitarse?

Puede tardar hasta 5 minutos en Microsoft 365 quitar un dominio si no se hace referencia a él en muchos lugares, como grupos de seguridad, listas de distribución, usuarios y grupos Microsoft 365 usuario. Si hay muchas referencias que usan el dominio, el dominio puede tardar varias horas (o incluso un día) en quitarse.

Si tiene cientos o miles de usuarios, use PowerShell para consultar todos los usuarios y moverlos a otro dominio. En caso contrario, es posible que falten usuarios en la interfaz y que, cuando vaya a quitar el dominio, no pueda y no sepa por qué. Vea [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname) para obtener más información. Para establecer el dominio predeterminado, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).

## <a name="still-need-help"></a>¿Aún necesita ayuda?

::: moniker range="o365-worldwide"

> [!NOTE]
> No puede quitar el dominio [". onmicrosoft.com"](../setup/domains-faq.yml) de su cuenta. Al quitar un dominio, las cuentas de usuario volverán a la dirección ".onmicrosoft.com" como SMTP principal/UserprincipalName.

¿Todavía no funciona? Puede que su dominio necesite quitarse manualmente. [Llámenos](../../business-video/get-help-support.md) y le ayudaremos.

::: moniker-end

::: moniker range="o365-21vianet"

> [!NOTE]
> No puede quitar el dominio [".partner.onmschina.cn"](../setup/domains-faq.yml) de su cuenta. Al quitar un dominio, las cuentas de usuario volverán a la dirección ".partner.onmschina.cn" como SMTP principal/UserprincipalName.

¿Todavía no funciona? Puede que su dominio necesite quitarse manualmente. [Llámenos](../../business-video/get-help-support.md?view=o365-21vianet&preserve-view=true) y le ayudaremos.

::: moniker-end

## <a name="related-content"></a>Contenido relacionado

[Preguntas más frecuentes sobre dominios](../setup/domains-faq.yml) (artículo)

[Cambiar a otro plan Microsoft 365 para empresas](../../commerce/subscriptions/switch-to-a-different-plan.md) (artículo)

[Cancelar la suscripción](../../commerce/subscriptions/cancel-your-subscription.md) (artículo)
