---
title: Quitar un dominio
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
ms.openlocfilehash: 76b64bc8e937a83ab4333cdd6ff774525f7ddd99
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68731357"
---
# <a name="remove-a-domain"></a>Quitar un dominio

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

¿Está quitando el dominio porque quiere agregarlo a otro plan de suscripción de Microsoft 365? ¿O solo quiere cancelar su suscripción? Puede [cambiar su plan o suscripción](../../commerce/subscriptions/switch-to-a-different-plan.md), o bien [cancelar la suscripción](../../commerce/subscriptions/cancel-your-subscription.md).

> [!TIP]
> Si necesita ayuda con los pasos que se describen en este tema, considere la posibilidad de [trabajar con un especialista en pequeñas empresas de Microsoft](https://go.microsoft.com/fwlink/?linkid=2186871). Con Business Assist, usted y sus empleados obtienen acceso de forma ininterrumpida a especialistas de pequeñas empresas a medida que hace crecer su negocio, desde la incorporación hasta el uso diario.

### <a name="step-1-move-users-to-another-domain"></a>Paso 1: Mover usuarios a otro dominio

#### <a name="move-users"></a>Mover usuarios

::: moniker range="o365-worldwide"

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Centro de administración</a>.

::: moniker-end

2. Seleccione **Usuarios** > **usuarios activos**.

3. Seleccione los cuadros situados junto a los nombres de todos los usuarios que desea mover.

4. En la parte superior de la página y, a continuación, elija **Cambiar dominios**.

5. En el panel **Cambiar dominios** , seleccione un dominio diferente.

You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.

#### <a name="move-yourself"></a>Moverse a sí mismo

::: moniker range="o365-worldwide"

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Centro de administración</a>.

::: moniker-end

2. Vaya a **Usuarios** \> **activos y** seleccione su cuenta en la lista.

3. En la pestaña **Cuenta** , seleccione **Administrar nombre de usuario** y, a continuación, elija un dominio diferente.

4. En la parte superior, seleccione el nombre de la cuenta y, a continuación, seleccione **Cerrar sesión**.

5. Inicie sesión con el nuevo dominio y la misma contraseña.

También puede usar PowerShell para mover los usuarios a otro dominio. Vea [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname) para obtener más información. Para establecer el dominio predeterminado, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).

### <a name="step-2-move-groups-to-another-domain"></a>Paso 2: Mover grupos a otro dominio

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Grupos de grupos**\>.<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a>

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **Grupos de grupos**>.

::: moniker-end

2. Seleccione el nombre del grupo y, a continuación, en la pestaña **General** en **Email dirección, Principal**, seleccione **Editar**.

3. Use la lista desplegable para elegir otro dominio.

4. Seleccione **Guardar** y, a continuación, **Cerrar**. Repita este proceso para todas las listas de distribución o grupos que estén asociados al dominio que quiere quitar.

### <a name="step-3-remove-the-old-domain"></a>Paso 3: Quitar el dominio antiguo

::: moniker range="o365-worldwide"

> [!NOTE]
> Si va a quitar un dominio personalizado, consulte [Eliminación de un dominio personalizado](#remove-a-custom-domain) antes de continuar.

1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Dominios</a> **de instalación**\>.

::: moniker-end

2. En la página **Dominios** , seleccione el dominio que desea quitar.

3. En el panel derecho, seleccione **Quitar**.

4. Siga las indicaciones adicionales y, a continuación, seleccione **Cerrar**.




### <a name="remove-a-custom-domain"></a>Eliminación de un dominio personalizado

Si va a cancelar la suscripción y usa un dominio personalizado, hay algunos pasos adicionales que debe realizar para poder cancelar la suscripción. 

#### <a name="change-your-domain-nameserver-records-if-needed"></a>Cambiar los registros del servidor de nombres de su dominio (si es necesario)

If you set up a custom domain, you added DNS records so the domain would work with Microsoft 365 services. Before you remove your domain, be sure to update the DNS records, such as your domain MX record, at your DNS host.

For example, change the MX record at your DNS host. Email sent to your domain stops coming to your Microsoft address and goes to your new email provider instead. (An MX record determines where email for your domain is sent.)

- Si los registros de su servidor de nombres (NS) [apuntan a servidores de nombres de Microsoft 365](../../admin/setup/add-domain.md), el cambio del registro MX no surtirá efecto hasta que no cambie dichos registros NS para que apunten al nuevo host DNS (consulte el paso 2).

- Antes de actualizar el registro MX, informe a sus usuarios la fecha en que planea cambiar su correo electrónico y el nuevo proveedor de correo electrónico que pretende usar. Además, si los usuarios desean mover su correo electrónico existente de Microsoft al nuevo proveedor, deben realizar pasos adicionales.

- El día que cambie el registro MX, asegúrese de [guardar los datos](/microsoft-365/commerce/subscriptions/cancel-your-subscription#save-your-data) y [desinstalar Office si es necesario](/microsoft-365/commerce/subscriptions/cancel-your-subscription#uninstall-office-optional).

#### <a name="update-your-domain-mx-and-other-dns-records-if-youre-using-a-custom-domain"></a>Actualizar el registro MX y otros registros DNS de su dominio (si usa un dominio personalizado)

Si cambió los registros del servidor de nombres (NS) a Microsoft 365 al configurar su dominio, deberá configurar o actualizar el registro MX y el resto de los registros DNS del host DNS que planea usar, y después, cambiar el registro NS a dicho host DNS.

Si no cambió los registros NS cuando configuró su dominio, al modificar el registro MX, el correo empezará a redirigirse inmediatamente a la nueva dirección.

Para cambiar los registros NS, consulte [Cambio de servidores de nombres para configurar Microsoft 365 con cualquier registrador de dominios](../../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md).



## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>¿Cuánto tiempo tarda un dominio en quitarse?

Microsoft 365 puede tardar hasta cinco minutos en quitar un dominio si no se hace referencia a él en muchos lugares, como grupos de seguridad, listas de distribución, usuarios, alias, buzones compartidos, buzones de recursos y grupos de Microsoft 365. Si hay muchas referencias que usan el dominio, el dominio puede tardar varias horas (o incluso un día) en quitarse.

If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname) for more information. To set the default domain, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).

## <a name="still-need-help"></a>¿Aún necesita ayuda?

::: moniker range="o365-worldwide"

> [!NOTE]
> No puede quitar el dominio [". onmicrosoft.com"](../setup/domains-faq.yml) de su cuenta. Al quitar un dominio, las cuentas de usuario volverán a la dirección ".onmicrosoft.com" como SMTP/UserprincipalName principal.

¿Todavía no funciona? Puede que su dominio necesite quitarse manualmente. [Llámenos](../../business-video/get-help-support.md) y le ayudaremos.

::: moniker-end

::: moniker range="o365-21vianet"

> [!NOTE]
> No puede quitar el dominio [".partner.onmschina.cn"](../setup/domains-faq.yml) de su cuenta. Al quitar un dominio, las cuentas de usuario volverán a la dirección ".partner.onmschina.cn" como SMTP/UserprincipalName principal.

¿Todavía no funciona? Puede que su dominio necesite quitarse manualmente. [Llámenos](../../business-video/get-help-support.md?view=o365-21vianet&preserve-view=true) y le ayudaremos.

::: moniker-end

## <a name="related-content"></a>Contenido relacionado

[Preguntas más frecuentes sobre dominios](../setup/domains-faq.yml) (artículo)

[Cambiar a otro plan de Microsoft 365 para empresas](../../commerce/subscriptions/switch-to-a-different-plan.md) (artículo)

[Cancelar la suscripción](../../commerce/subscriptions/cancel-your-subscription.md) (artículo)
