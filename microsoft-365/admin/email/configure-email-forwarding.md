---
title: Configurar el reenvío de correo electrónico
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Configure el reenvío de correo electrónico a una o más cuentas de correo electrónico con Office365.
ms.openlocfilehash: 5bbb7d4fa122051725418153e43f40aec370de61
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580620"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>Configurar el reenvío de correo electrónico en Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Como administrador de una organización, es posible que los requisitos de la compañía configuren el reenvío de correo electrónico para el buzón de un usuario. El reenvío de correo electrónico le permite reenviar mensajes de correo electrónico enviados al buzón de un usuario al buzón de otro usuario dentro o fuera de la organización.

> [!IMPORTANT]
> Puede usar las directivas de filtro de correo no deseado saliente para controlar el reenvío automático a los destinatarios externos. Para obtener más información, consulte [controlar el reenvío de correo externo automático en Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).

## <a name="configure-email-forwarding"></a>Configurar el reenvío de correo electrónico

Antes de configurar el reenvío de correo electrónico, tenga en cuenta lo siguiente:

- Una vez que haya configurado el reenvío de correo electrónico, solo se reenviarán los correos electrónicos **nuevos** que se envíen al buzón  *de*  .

- El reenvío de correo electrónico requiere que la cuenta  *de*  tiene una licencia. Si está configurando el reenvío de correo electrónico porque el usuario ha abandonado la organización, otra opción es [convertir su buzón en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md). De este modo, varias personas pueden tener acceso a ella. Sin embargo, un buzón compartido no puede superar los 50 GB.

Para realizar estos pasos, debe ser administrador de Exchange o administrador global en Microsoft 365. Para obtener más información, vea el tema [sobre los roles de administrador](../add-users/about-admin-roles.md).

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a **la página usuarios** \> **[activos](https://go.microsoft.com/fwlink/p/?linkid=834822)** .

2. Seleccione el nombre del usuario cuyo correo electrónico desea reenviar para abrir la página de propiedades.

3. En la pestaña **correo** , seleccione **administrar reenvío de correo electrónico**.

4. En la página reenvío de correo, seleccione **reenviar todos los correos electrónicos enviados a este buzón**, escriba la dirección de reenvío y elija si desea conservar una copia de los mensajes de correo electrónico reenviados. Si no ve esta opción, asegúrese de que se haya asignado una licencia a la cuenta de usuario. Seleccione **Guardar cambios**.

    **Para reenviar a varias direcciones de correo electrónico**, puede pedir al usuario que configure una regla en Outlook para que reenvíe a las direcciones. Para obtener más información, consulte [usar reglas para reenviar mensajes automáticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

     O bien, en el centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [Agréguele las direcciones](add-user-or-contact-to-distribution-list.md)y, a continuación, configure el reenvío para que apunte a la DL siguiendo las instrucciones de este artículo.

5. No elimine la cuenta del usuario que es el correo electrónico que está reenviando o quite su licencia.  Si lo hace, se detendrá el reenvío de correo electrónico.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a **la página usuarios** \> **[activos](https://go.microsoft.com/fwlink/p/?linkid=847686)** .

2. Seleccione el nombre del usuario cuyo correo electrónico desea reenviar para abrir la página de propiedades.

3. Expanda **configuración de correo** y, a continuación, en la sección **reenvío de correo electrónico** , seleccione **Editar**.

4. En la página reenvío de correo, establezca el botón de alternancia en **activado**, escriba la dirección de reenvío y elija si desea conservar una copia de los mensajes de correo electrónico reenviados. Si no ve esta opción, asegúrese de que se haya asignado una licencia a la cuenta de usuario. Seleccione **Guardar**.

   **Para reenviar a varias direcciones de correo electrónico**, puede pedir al usuario que configure una regla en Outlook para que reenvíe a las direcciones. Para obtener más información, consulte [usar reglas para reenviar mensajes automáticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

   O bien, en el centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [Agréguele las direcciones](add-user-or-contact-to-distribution-list.md)y, a continuación, configure el reenvío para que apunte a la DL siguiendo las instrucciones de este artículo.

5. No elimine la cuenta del usuario que es el correo electrónico que está reenviando o quite su licencia.  Si lo hace, se detendrá el reenvío de correo electrónico.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a **la página usuarios** \> **[activos](https://go.microsoft.com/fwlink/p/?linkid=850628)** .

2. Seleccione el nombre del usuario cuyo correo electrónico desea reenviar para abrir la página de propiedades.

3. Expanda **configuración de correo** y, a continuación, en la sección **reenvío de correo electrónico** , seleccione **Editar**.

4. En la página reenvío de correo, establezca el botón de alternancia en **activado**, escriba la dirección de reenvío y elija si desea conservar una copia de los mensajes de correo electrónico reenviados. Si no ve esta opción, asegúrese de que se haya asignado una licencia a la cuenta de usuario. Seleccione **Guardar**.

   **Para reenviar a varias direcciones de correo electrónico**, puede pedir al usuario que configure una regla en Outlook para que reenvíe a las direcciones. Para obtener más información, consulte [usar reglas para reenviar mensajes automáticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

   O bien, en el centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [Agréguele las direcciones](add-user-or-contact-to-distribution-list.md)y, a continuación, configure el reenvío para que apunte a la DL siguiendo las instrucciones de este artículo.

5. No elimine la cuenta del usuario que es el correo electrónico que está reenviando o quite su licencia.  Si lo hace, se detendrá el reenvío de correo electrónico.

::: moniker-end
