---
title: Configurar el reenvío de correo electrónico en Office 365
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Configure el reenvío de correo electrónico a una o más cuentas de correo electrónico con Office365.
ms.openlocfilehash: 963256aedb52ae0adf31790a74fbdb77ad2bb27e
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43142532"
---
# <a name="configure-email-forwarding-in-office-365"></a>Configurar el reenvío de correo electrónico en Office 365
  
Como administrador de una organización de Office 365, es posible que tenga requisitos de la compañía para configurar el reenvío de correo electrónico para el buzón de un usuario. El reenvío de correo electrónico le permite reenviar mensajes de correo electrónico enviados al buzón de un usuario al buzón de otro usuario dentro o fuera de la organización.

  
## <a name="configure-email-forwarding"></a>Configurar el reenvío de correo electrónico

 Antes de configurar el reenvío de correo electrónico, tenga en cuenta lo siguiente: 

- Una vez que haya configurado el reenvío de correo electrónico, solo se reenviarán los correos electrónicos **nuevos** que se envíen al buzón *de* . 
    
- El reenvío de correo electrónico requiere que la cuenta *de* tiene una licencia. Si está configurando el reenvío de correo electrónico porque el usuario ha abandonado la organización, otra opción es [convertir su buzón en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md). De este modo, varias personas pueden tener acceso a ella. Sin embargo, un buzón compartido no puede superar los 50 GB. 
    
Debe ser administrador de Exchange o administrador global de Office 365 para realizar estos pasos. Para obtener más información, vea el tema [sobre los roles de administrador](../add-users/about-admin-roles.md).

::: moniker range="o365-worldwide"

> [!NOTE]
> Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
    
2. Seleccione el nombre del usuario cuyo correo electrónico desea reenviar para abrir la página de propiedades. 
 
3. En la pestaña **correo** , seleccione **administrar reenvío de correo electrónico**. 
  
4. En la página reenvío de correo, seleccione **reenviar todos los correos electrónicos enviados a este buzón**, escriba la dirección de reenvío y elija si desea conservar una copia de los mensajes de correo electrónico reenviados. Si no ve esta opción, asegúrese de que se haya asignado una licencia a la cuenta de usuario. Seleccione **Guardar cambios**.
    
    *Para reenviar a varias direcciones de correo electrónico*, puede pedir al usuario que configure una regla en Outlook para que reenvíe a las direcciones. Para obtener más información, consulte [usar reglas para reenviar mensajes automáticamente](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746). 
    
     O bien, en el centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [Agréguele las direcciones](add-user-or-contact-to-distribution-list.md)y, a continuación, configure el reenvío para que apunte a la DL siguiendo las instrucciones de este artículo.
    
5. No elimine la cuenta del usuario que es el correo electrónico que está reenviando o quite su licencia.  Si lo hace, se detendrá el reenvío de correo electrónico. 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>. 
    
2. Seleccione el nombre del usuario cuyo correo electrónico desea reenviar para abrir la página de propiedades. 

3. Expanda **configuración de correo**y, a continuación, en la sección **reenvío de correo electrónico** , seleccione **Editar**.

4. En la página reenvío de correo, establezca el botón de alternancia en **activado**, escriba la dirección de reenvío y elija si desea conservar una copia de los mensajes de correo electrónico reenviados. Si no ve esta opción, asegúrese de que se haya asignado una licencia a la cuenta de usuario. Haga clic en **Guardar**.
    
    **Para reenviar a varias direcciones de correo electrónico**, puede pedir al usuario que configure una regla en Outlook para que reenvíe a las direcciones. Para obtener más información, consulte [usar reglas para reenviar mensajes automáticamente](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746). 
    
     O bien, en el centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [Agréguele las direcciones](add-user-or-contact-to-distribution-list.md)y, a continuación, configure el reenvío para que apunte a la DL siguiendo las instrucciones de este artículo.
    
5. No elimine la cuenta del usuario que es el correo electrónico que está reenviando o quite su licencia.  Si lo hace, se detendrá el reenvío de correo electrónico.    

::: moniker-end

::: moniker range="o365-21vianet"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>. 
    
2. Seleccione el nombre del usuario cuyo correo electrónico desea reenviar para abrir la página de propiedades. 

3. Expanda **configuración de correo**y, a continuación, en la sección **reenvío de correo electrónico** , seleccione **Editar**.

4. En la página reenvío de correo, establezca el botón de alternancia en **activado**, escriba la dirección de reenvío y elija si desea conservar una copia de los mensajes de correo electrónico reenviados. Si no ve esta opción, asegúrese de que se haya asignado una licencia a la cuenta de usuario. Haga clic en **Guardar**.
    
    **Para reenviar a varias direcciones de correo electrónico**, puede pedir al usuario que configure una regla en Outlook para que reenvíe a las direcciones. Para obtener más información, consulte [usar reglas para reenviar mensajes automáticamente](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746). 
    
     O bien, en el centro de administración, [cree un grupo de distribución](../setup/create-distribution-lists.md), [Agréguele las direcciones](add-user-or-contact-to-distribution-list.md)y, a continuación, configure el reenvío para que apunte a la DL siguiendo las instrucciones de este artículo.
    
5. No elimine la cuenta del usuario que es el correo electrónico que está reenviando o quite su licencia.  Si lo hace, se detendrá el reenvío de correo electrónico. 

::: moniker-end 
