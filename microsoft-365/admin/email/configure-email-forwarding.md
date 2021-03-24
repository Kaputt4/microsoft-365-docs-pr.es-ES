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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Configurar el reenvío de correo electrónico a una o más cuentas de correo electrónico con Office 365.
ms.openlocfilehash: cdefab3df59f1c57abbc221943b58c978ff582a9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050719"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>Configurar el reenvío de correo electrónico en Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

Como administrador de una organización, es posible que tenga requisitos de la compañía para configurar el reenvío de correo electrónico para el buzón de un usuario. El reenvío de correo electrónico le permite reenviar los mensajes del buzón de correo enviados al buzón de un usuario dentro o fuera de la organización.

> [!IMPORTANT]
> Puede usar las directivas del filtro de correo no deseado saliente para controlar el reenvío automático a destinatarios externos. Para obtener más información, consulte [Controlar el reenvío automático de correo electrónico externo en Microsoft 365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).

## <a name="configure-email-forwarding"></a>Configurar el reenvío de correo electrónico

Antes de configurar el reenvío de correo electrónico, tenga en cuenta lo siguiente:

- Una vez configurado el reenvío de correo electrónico, solo se reenviarán los correos electrónicos **nuevos** enviados al buzón de  correo electrónico de *origen*.

- El reenvío de correo electrónico requiere que la cuenta de *origen*  tenga una licencia. Si está configurando el reenvío de correo electrónico porque el usuario ha dejado la organización, otra opción es [convertir su buzón en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md). De esta forma, varias personas podrán acceder a él. Sin embargo, un buzón compartido no puede superar los 50 GB.

Debe ser Administrador de Exchange o Administrador global en Microsoft 365 para poder realizar estos pasos. Para obtener más información, consulte el tema [Acerca de los roles de administrador](../add-users/about-admin-roles.md).

::: moniker range="o365-worldwide"

1. En el Centro de administración, vaya a la página **Usuarios** \> **[Usuarios activos](https://go.microsoft.com/fwlink/p/?linkid=834822)**.

2. Seleccione el nombre del usuario cuyo correo electrónico quiere reenviar para abrir la página de propiedades.

3. En la pestaña **Correo**, seleccione **Administrar el reenvío de correos**.

4. En la página de reenvío de correo electrónico, seleccione **Reenviar todos los mensajes enviados a este buzón**, escriba la dirección de reenvío y elija si desea conservar una copia de los correos electrónicos reenviados. Si no ve esta opción, asegúrese de tener asignada una licencia asignada a la cuenta del usuario. Seleccione **Guardar cambios**.

    **Para reenviar a varias direcciones de correo**, puede pedir al usuario que configure una regla en Outlook para que se reenvía a las direcciones. Para obtener más información, consulte [Usar reglas para reenviar mensajes automáticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

     O bien, en el Centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [agregue las direcciones](add-user-or-contact-to-distribution-list.md) y luego, configure el reenvío para que apunte a la DL con las instrucciones de este artículo.

5. No elimine la cuenta del usuario cuyo correo electrónico está reenviando ni le quite su licencia.  Si lo hace, se detendrá el reenvío de correo electrónico.

::: moniker-end

::: moniker range="o365-germany"

1. En el Centro de administración, vaya a la página **Usuarios** \> **[Usuarios activos](https://go.microsoft.com/fwlink/p/?linkid=847686)**.

2. Seleccione el nombre del usuario cuyo correo electrónico quiere reenviar para abrir la página de propiedades.

3. Expanda **Configuración de correo** y luego, en la sección **Reenvío de correo electrónico**, seleccione **Editar**.

4. En la página de reenvío de correo electrónico, establezca el botón de alternancia en **Activado**, escriba la dirección de reenvío y elija si quiere conservar una copia de los correos electrónicos reenviados. Si no ve esta opción, asegúrese de tener asignada una licencia asignada a la cuenta del usuario. Seleccione **Guardar**.

   **Para reenviar a varias direcciones de correo**, puede pedir al usuario que configure una regla en Outlook para que se reenvía a las direcciones. Para obtener más información, consulte [Usar reglas para reenviar mensajes automáticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

   O bien, en el Centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [agregue las direcciones](add-user-or-contact-to-distribution-list.md) y luego, configure el reenvío para que apunte a la DL con las instrucciones de este artículo.

5. No elimine la cuenta del usuario cuyo correo electrónico está reenviando ni le quite su licencia.  Si lo hace, se detendrá el reenvío de correo electrónico.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el Centro de administración, vaya a la página **Usuarios** \> **[Usuarios activos](https://go.microsoft.com/fwlink/p/?linkid=850628)**.

2. Seleccione el nombre del usuario cuyo correo electrónico quiere reenviar para abrir la página de propiedades.

3. Expanda **Configuración de correo** y luego, en la sección **Reenvío de correo electrónico**, seleccione **Editar**.

4. En la página de reenvío de correo electrónico, establezca el botón de alternancia en **Activado**, escriba la dirección de reenvío y elija si quiere conservar una copia de los correos electrónicos reenviados. Si no ve esta opción, asegúrese de tener asignada una licencia asignada a la cuenta del usuario. Seleccione **Guardar**.

   **Para reenviar a varias direcciones de correo**, puede pedir al usuario que configure una regla en Outlook para que se reenvía a las direcciones. Para obtener más información, consulte [Usar reglas para reenviar mensajes automáticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

   O bien, en el Centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [agregue las direcciones](add-user-or-contact-to-distribution-list.md) y luego, configure el reenvío para que apunte a la DL con las instrucciones de este artículo.

5. No elimine la cuenta del usuario cuyo correo electrónico está reenviando ni le quite su licencia.  Si lo hace, se detendrá el reenvío de correo electrónico.

::: moniker-end