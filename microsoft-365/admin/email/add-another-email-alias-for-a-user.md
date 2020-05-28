---
title: Agregar otro alias de correo electrónico para un usuario
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
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Obtenga más información acerca de cómo puede tener más de una dirección de correo electrónico, denominada alias de correo electrónico, asociada a su cuenta de Microsoft 365 para empresas. '
ms.openlocfilehash: 778d927d9ab830aea674b9bff72df250e6e430b1
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400189"
---
# <a name="add-another-email-alias-for-a-user"></a>Agregar otro alias de correo electrónico para un usuario

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
Este artículo está destinado a los administradores de Microsoft 365 que tienen suscripciones empresariales. No está dirigido a usuarios particulares.
  
Una dirección de correo electrónico principal en Microsoft 365 suele ser la dirección de correo electrónico que se asignó al usuario cuando se creó su cuenta. Cuando este envía un correo electrónico a un contacto, su dirección de correo electrónico principal es la que normalmente aparece en el campo  *De*  en las aplicaciones de correo electrónico. También pueden tener más de una dirección de correo electrónico asociada a su cuenta de Microsoft 365 para empresas. Estas direcciones adicionales se denominan "alias". 
  
Por ejemplo, supongamos que Jenna tiene la dirección de correo electrónico jenna@contosoco.com, pero también quiere recibir correo electrónico en jen@contosoco.com porque algunos usuarios hacen referencia a ella con ese nombre. Puede crear alias para que ambas direcciones de correo electrónico vayan a la bandeja de entrada de Jenna.
<br><br>  
  
Puede crear hasta 400 alias para un usuario. No se necesitan licencias o cargos adicionales.
  
> [!Tip]
> Si desea que varias personas administren el correo electrónico enviado a una sola dirección de correo electrónico como info@NodPublishers.com o sales@NodPublishers.com, cree un buzón compartido. Para obtener más información, consulte [crear un buzón compartido](create-a-shared-mailbox.md).
  
## <a name="add-email-aliases-to-a-user"></a>Agregar alias de correo electrónico a un usuario
<a name="AddEmailPreview"> </a>

Debe tener [permisos de administrador](../add-users/about-admin-roles.md) para hacer esto. 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. En la página **usuarios activos** , seleccione el usuario > **administrar alias de correo electrónico**. No verá esta opción si la persona no tiene una licencia asignada. 
    
3. Seleccione **+ Agregar un alias** y escriba un nuevo alias para el usuario.   
    
    > [!Important] 
    > Si recibe el mensaje de error "**no se encuentra un parámetro que coincida con el nombre de parámetro" EmailAddresses**", significa que está tardando un poco en finalizar la configuración del espacio empresarial o en su dominio personalizado si agregó uno recientemente. El proceso de configuración puede tardar hasta 4 horas en completarse. Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo. Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.
    
  
    > [!IMPORTANT]
    > Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal. 
  
    > [!TIP]
    > El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable. Para agregar otro nombre de dominio a la lista, vea [Agregar un dominio a Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain). 
  
     
5. Cuando haya terminado, elija **Guardar cambios**.
    
6. Espere 24 horas hasta que los alias nuevos se propaguen por Office 365.
    
    El usuario ahora tendrá una dirección principal y un alias. Por ejemplo, todo el correo enviado a la dirección principal de Naiara Hoffman, Eliza@NodPublishers.com y su alias, Sales@NodPublishers.com, irá a la bandeja de entrada de Naiara.
    
  
7. **Cuando el usuario responda, la dirección de será su alias *de* correo electrónico principal.** Por ejemplo, supongamos que se envía un mensaje a Sales@NodPublishers.com y que llega a la bandeja de entrada de Naiara. Cuando Naiara responda al mensaje, su dirección de correo electrónico principal se mostrará como el remitente, en lugar de ventas@NodPublishers.com. 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>. 
    
    
2. En la página **Usuarios activos**, seleccione el nombre de la persona que desea editar.

3. Junto a **alias de nombre de usuario/correo electrónico**, seleccione **Editar**.

    > [!Important] 
    > Si recibe el mensaje de error "**no se encuentra un parámetro que coincida con el nombre de parámetro" EmailAddresses**", significa que está tardando un poco en finalizar la configuración del espacio empresarial o en su dominio personalizado si agregó uno recientemente. El proceso de configuración puede tardar hasta 4 horas en completarse. Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo. Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.

4. En el cuadro de texto situado debajo de **alias**, escriba la primera parte del nuevo alias de correo electrónico. Si ha agregado su propio dominio a Office 365, puede elegir el dominio para el nuevo alias de correo electrónico mediante la lista desplegable. A continuación, seleccione **Aceptar**.

    > [!IMPORTANT]
    > Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal. 
  
    > [!TIP]
    > El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable. Para agregar otro nombre de dominio a la lista, vea [Agregar un dominio a Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain). 

5. Cuando haya terminado, seleccione **Guardar**.

6. Espere 24 horas hasta que los alias nuevos se propaguen por Office 365. 
    
    El usuario ahora tendrá una dirección principal y un alias. Por ejemplo, todo el correo enviado a la dirección principal de Naiara Hoffman, Eliza@NodPublishers.com y su alias, Sales@NodPublishers.com, irá a la bandeja de entrada de Naiara.
    
  
7. **Cuando el usuario responda, la dirección de será su alias *de* correo electrónico principal.** Por ejemplo, supongamos que se envía un mensaje a Sales@NodPublishers.com y que llega a la bandeja de entrada de Naiara. Cuando Naiara responda al mensaje, su dirección de correo electrónico principal se mostrará como el remitente, en lugar de ventas@NodPublishers.com. 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>. 

    
2. En la página **Usuarios activos**, seleccione el nombre de la persona que desea editar.

3. Junto a **alias de nombre de usuario/correo electrónico**, seleccione **Editar**.

    > [!Important] 
    > Si recibe el mensaje de error "**no se encuentra un parámetro que coincida con el nombre de parámetro" EmailAddresses**", significa que está tardando un poco en finalizar la configuración del espacio empresarial o en su dominio personalizado si agregó uno recientemente. El proceso de configuración puede tardar hasta 4 horas en completarse. Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo. Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.

4. En el cuadro de texto situado debajo de **alias**, escriba la primera parte del nuevo alias de correo electrónico. Si ha agregado su propio dominio a Office 365, puede elegir el dominio para el nuevo alias de correo electrónico mediante la lista desplegable. A continuación, seleccione **Aceptar**.

    > [!IMPORTANT]
    > Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal. 
  
    > [!TIP]
    > El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable. Para agregar otro nombre de dominio a la lista, vea [Agregar un dominio a Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain). 

5. Cuando haya terminado, seleccione **Guardar**.

6. Espere 24 horas hasta que los alias nuevos se propaguen por Office 365. 
    
    El usuario ahora tendrá una dirección principal y un alias. Por ejemplo, todo el correo enviado a la dirección principal de Naiara Hoffman, Eliza@NodPublishers.com y su alias, Sales@NodPublishers.com, irá a la bandeja de entrada de Naiara.
    
  
7. **Cuando el usuario responda, la dirección de será su alias *de* correo electrónico principal.** Por ejemplo, supongamos que se envía un mensaje a Sales@NodPublishers.com y que llega a la bandeja de entrada de Naiara. Cuando Naiara responda al mensaje, su dirección de correo electrónico principal se mostrará como el remitente, en lugar de ventas@NodPublishers.com. 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>¿Ha recibido "no se encuentra un parámetro que coincida con el nombre de parámetro EmailAddresses"?


Si recibe el mensaje de error "**no se encuentra un parámetro que coincida con el nombre de parámetro EmailAddresses**" significa que está tardando un poco más en finalizar la configuración de su espacio empresarial, o su dominio personalizado si agregó uno recientemente. El proceso de configuración puede tardar hasta 4 horas en completarse. Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo. Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>¿Ha adquirido la suscripción con GoDaddy u otro partner?


Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.
  
## <a name="related-articles"></a>Artículos relacionados

[Enviar correo electrónico desde otra dirección](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[Cambiar una dirección de correo electrónico y nombre de usuario](../add-users/change-a-user-name-and-email-address.md)
  

