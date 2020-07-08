---
title: Quitar un dominio
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
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Obtenga información sobre cómo quitar un dominio antiguo de Microsoft 365 y mover usuarios y grupos a otro dominio.
ms.openlocfilehash: 6f5e36a897316c8cdc057a725957c54e7eb53edc
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079766"
---
# <a name="remove-a-domain"></a>Quitar un dominio

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
¿Está eliminando su dominio porque quiere agregarlo a un plan de suscripción de Microsoft 365 diferente? ¿O solo quiere cancelar su suscripción? Puede [cambiar su plan o suscripción](../../commerce/subscriptions/switch-to-a-different-plan.md), o bien [cancelar la suscripción](../../commerce/subscriptions/cancel-your-subscription.md).
  
### <a name="step-1-move-users-to-another-domain"></a>Paso 1: mover usuarios a otro dominio

#### <a name="move-users"></a>Mover usuarios

::: moniker range="o365-worldwide"

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración</a>.

2. Seleccione **usuarios** > **activos**.

3. Active las casillas situadas junto a los nombres de todos los usuarios que desee mover.

4. Seleccione **más opciones** (**...**), en la parte superior de la página y, a continuación, elija **cambiar dominios**.

5. En el panel **cambiar dominios** , seleccione un dominio diferente.

You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.

::: moniker-end

::: moniker range="o365-germany"

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>.  

2. Seleccione **usuarios** > **activos**.

3. Active las casillas situadas junto a los nombres de todos los usuarios que desee mover.

4. En la parte superior de la página, elija **más** > **dominios de edición**.

5. En el panel **Editar dominios** , seleccione un dominio diferente.
  
You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>.  

2. Seleccione **usuarios** > **activos**.

3. Active las casillas situadas junto a los nombres de todos los usuarios que desee mover.

4. En la parte superior de la página, elija **más** > **dominios de edición**.

5. En el panel **Editar dominios** , seleccione un dominio diferente.
  
You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.

::: moniker-end

#### <a name="move-yourself"></a>Desplazarse

::: moniker range="o365-worldwide"

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>.

2. Vaya a **usuarios** \> **activos**y seleccione su cuenta de la lista.

3. En la pestaña **cuenta** , seleccione **administrar nombre de usuario**y, a continuación, elija un dominio diferente.
  
4. En la parte superior, selecciona el nombre de la cuenta y, a continuación, selecciona **Cerrar sesión**.

5. Inicie sesión con el nuevo dominio y la misma contraseña.

También puede usar PowerShell para mover los usuarios a otro dominio. Vea [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para obtener más información. Para establecer el dominio predeterminado, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

::: moniker range="o365-germany"

1. Vaya a **usuarios** \> **activos**y seleccione su nombre en la lista.

2. En la sección **nombre de usuario/correo electrónico** , seleccione **Editar**y, a continuación, elija un dominio diferente.

3. Seleccione **establecer como principal** > **Guardar** > **cierre**.
  
4. En la parte superior, selecciona el nombre de la cuenta y, a continuación, selecciona **Cerrar sesión**.

5. Inicie sesión con el nuevo dominio y la misma contraseña.

También puede usar PowerShell para mover los usuarios a otro dominio. Vea [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para obtener más información. Para establecer el dominio predeterminado, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya a **usuarios** \> **activos**y seleccione su nombre en la lista.

2. En la sección **nombre de usuario/correo electrónico** , seleccione **Editar**y, a continuación, elija un dominio diferente.

3. Seleccione **establecer como principal** > **Guardar** > **cierre**.
  
4. En la parte superior, selecciona el nombre de la cuenta y, a continuación, selecciona **Cerrar sesión**.

5. Inicie sesión con el nuevo dominio y la misma contraseña.

También puede usar PowerShell para mover los usuarios a otro dominio. Vea [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para obtener más información. Para establecer el dominio predeterminado, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a>Paso 2: mover grupos a otro dominio

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a **la** página grupos de grupos \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .
  
2. Seleccione el nombre del grupo y, a continuación, en la pestaña **General** , en **dirección de correo electrónico,** haga clic en **Editar**.

3. Use la lista desplegable para elegir otro dominio.

4. Seleccione **Guardar** y, a continuación, **Cerrar**. Repita este proceso para todas las listas de distribución o grupos que estén asociados al dominio que quiere quitar.

::: moniker-end

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a **la** página grupos de grupos > **Groups** .

2. Seleccione el nombre del grupo y, a continuación, seleccione **Editar** junto a **nombre**.

3. Use la lista desplegable para elegir otro dominio.

4. Seleccione **Guardar** y, a continuación, **Cerrar**. Repita este proceso para todas las listas de distribución o grupos que estén asociados al dominio que quiere quitar.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a **la** página grupos de grupos > **Groups** .

2. Seleccione el nombre del grupo y, a continuación, seleccione **Editar** junto a **nombre**.

3. Use la lista desplegable para elegir otro dominio.

4. Seleccione **Guardar** y, a continuación, **Cerrar**. Repita este proceso para todas las listas de distribución o grupos que estén asociados al dominio que quiere quitar.

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a>Paso 3: quitar el dominio anterior

::: moniker range="o365-worldwide"

1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página de **configuración** de \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">dominios</a> .

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página de **configuración** de \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">dominios</a> .

::: moniker-end
  
2. En la página **dominios** , seleccione el dominio que quiera quitar.

3. En el panel derecho, seleccione **quitar**.

4. Siga los mensajes adicionales y, a continuación, seleccione **cerrar**.

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>¿Cuánto tiempo tarda un dominio en quitarse?

Microsoft 365 puede tardar hasta 5 minutos en quitar un dominio si no se hace referencia a él en muchos lugares como, por ejemplo, grupos de seguridad, listas de distribución, usuarios y grupos de Microsoft 365. Si hay muchas referencias que usan el dominio, el dominio puede tardar varias horas (o incluso un día) en quitarse.
  
If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).
  
## <a name="still-need-help"></a>¿Aún necesita ayuda?

::: moniker range="o365-worldwide"

> [!NOTE]
> No puede quitar el dominio [". onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) de su cuenta.
  
Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!
  
::: moniker-end

## <a name="related-articles"></a>Artículos relacionados

[Preguntas más frecuentes de dominios](../setup/domains-faq.md)

[Obtener ayuda con los dominios de 365 de Microsoft](get-help-with-domains.md)

[Cambiar a otro plan de Microsoft 365 para empresas](../../commerce/subscriptions/switch-to-a-different-plan.md)

[Cancelar la suscripción](../../commerce/subscriptions/cancel-your-subscription.md)
