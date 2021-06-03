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
description: El reenvío de correo electrónico le permite reenviar los mensajes de correo electrónico enviados a un buzón Microsoft 365 de usuario a otro buzón dentro o fuera de la organización.
ms.openlocfilehash: dfea738f5d786b6e476dd02dc92fd0aef452d62f
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730143"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>Configurar el reenvío de correo electrónico en Microsoft 365

Como administrador de una organización, es posible que tenga requisitos de la compañía para configurar el reenvío de correo electrónico para el buzón de un usuario. El reenvío de correo electrónico le permite reenviar los mensajes del buzón de correo enviados al buzón de un usuario dentro o fuera de la organización.

> [!IMPORTANT]
> Puede usar las directivas del filtro de correo no deseado saliente para controlar el reenvío automático a destinatarios externos. Para obtener más información, consulte [Controlar el reenvío automático de correo electrónico externo en Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).

## <a name="configure-email-forwarding"></a>Configurar el reenvío de correo electrónico

Antes de configurar el reenvío de correo electrónico, tenga en cuenta lo siguiente:

- Permitir que los mensajes reenviados automáticamente se envíen a personas en el dominio remoto. Consulta [Administrar dominios remotos](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) para obtener más información.

- Una vez configurado el reenvío de correo electrónico, solo se reenviarán los correos electrónicos **nuevos** enviados al buzón de  correo electrónico de *origen*.

- El reenvío de correo electrónico requiere que la cuenta de *origen*  tenga una licencia. Si está configurando el reenvío de correo electrónico porque el usuario ha dejado la organización, otra opción es [convertir su buzón en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md). De esta forma, varias personas podrán acceder a él. Sin embargo, un buzón compartido no puede superar los 50 GB.

Debe ser Administrador de Exchange o Administrador global en Microsoft 365 para poder realizar estos pasos. Para obtener más información, consulte el tema [Acerca de los roles de administrador](../add-users/about-admin-roles.md).

1. En el Centro de administración, vaya a la página **Usuarios** \> **[Usuarios activos](https://go.microsoft.com/fwlink/p/?linkid=834822)**.

2. Seleccione el nombre del usuario cuyo correo electrónico desea reenviar y, a continuación, abra la página de propiedades.

3. En la pestaña **Correo**, seleccione **Administrar el reenvío de correos**.

4. En la página de reenvío de correo electrónico, seleccione **Reenviar todos los mensajes enviados a este buzón**, escriba la dirección de reenvío y elija si desea conservar una copia de los correos electrónicos reenviados. Si no ve esta opción, asegúrese de tener asignada una licencia asignada a la cuenta del usuario. Seleccione **Guardar cambios**.

    **Para reenviar a varias direcciones de correo**, puede pedir al usuario que configure una regla en Outlook para que se reenvía a las direcciones. 
    
    1.  Abrir **reglas de**  >    >   **inicio de** outlook > Seleccionar administrar reglas & **alertas**
    1. Seleccione **Nueva regla** Seleccione Aplicar regla en el mensaje que recibo ubicado cerca de la parte inferior de la lista y, a continuación, haga clic en  >   **Siguiente**.
    1. Haga **clic en Sí** cuando se le pida Esta regla se aplicará a todos los mensajes que reciba. 
    1. En la lista siguiente, seleccione las acciones que **redirigen a personas** o grupos públicos y detenga el procesamiento de más **reglas**
    1. Haga clic en la frase subrayada **personas o grupo público** en la parte inferior de la ventana.
    1. Escriba la **dirección de correo electrónico a** la que se reenviará el correo en el campo Para y, a continuación, haga clic en **Aceptar**.
    1. Seleccionar **finalizar**
    

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

5. No elimine la cuenta del usuario cuyo correo electrónico está reenviando ni le quite su licencia. Si lo hace, se detendrá el reenvío de correo electrónico.

::: moniker-end

## <a name="related-content"></a>Contenido relacionado 

[Crear un buzón compartido](../email/create-a-shared-mailbox.md) (artículo)\
[Enviar correo electrónico desde una dirección](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) diferente (artículo)\
[Cambiar un nombre de usuario y una dirección de correo electrónico](../add-users/change-a-user-name-and-email-address.md) (artículo)
