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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Obtenga información sobre cómo puede tener más de una dirección de correo electrónico, denominada alias de correo electrónico, asociada con su cuenta de Microsoft 365 para empresas. '
ms.openlocfilehash: 3c97640f4bb16876ec028a1af2b361a21a0decab
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126410"
---
# <a name="add-another-email-alias-for-a-user"></a>Agregar otro alias de correo electrónico para un usuario

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end
  
Este artículo está para administradores de Microsoft 365 que tienen suscripciones empresariales. No está dirigido a usuarios particulares.
  
Una dirección de correo electrónico principal en Microsoft 365 suele ser la dirección de correo electrónico que se asignó a un usuario cuando se creó su cuenta. Cuando este envía un correo electrónico a un contacto, su dirección de correo electrónico principal es la que normalmente aparece en el campo  *De*  en las aplicaciones de correo electrónico. También pueden tener más de una dirección de correo electrónico asociada a su cuenta de Microsoft 365 para empresas. Estas direcciones adicionales se denominan "alias". 
  
Por ejemplo, supongamos que Ellana tiene la dirección de correo electrónico jenna@contosoco.com, pero también quiere recibir correo electrónico en jen@contosoco.com porque algunas personas hacen referencia a ella con ese nombre. Puedes crear alias para ella para que ambas direcciones de correo electrónico vayan a la bandeja de entrada de Ellana.
<br><br>  
  
Puede crear hasta 400 alias para un usuario. No se necesitan licencias o cargos adicionales.
  
> [!Tip]
> Si desea que varias personas administren el correo electrónico enviado a una única dirección de correo electrónico como info@NodPublishers.com o sales@NodPublishers.com, cree un buzón compartido. Para obtener más información, consulte [Crear un buzón compartido.](create-a-shared-mailbox.md)
  
## <a name="add-email-aliases-to-a-user"></a>Agregar alias de correo electrónico a un usuario
<a name="AddEmailPreview"> </a>

Debe tener permisos [de administrador](../add-users/about-admin-roles.md) para hacerlo. 

  
::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. En la **página Usuarios activos,** seleccione el usuario que > **alias de correo electrónico.** No verá esta opción si la persona no tiene asignada una licencia. 
    
3. Seleccione **+ Agregar un alias** y escriba un nuevo alias para el usuario.   
    
    > [!Important] 
    > Si recibe el mensaje de error "No se puede encontrar un parámetro que coincida con el nombre de parámetro **'EmailAddresses",** significa que está tardando un poco más en finalizar la configuración del espacio empresarial o del dominio personalizado si agregó uno recientemente. El proceso de configuración puede tardar hasta 4 horas en completarse. Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo. Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.
    
  
    > [!IMPORTANT]
    > Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal. 
  
    > [!TIP]
    > El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable. Para agregar otro nombre de dominio a la lista, vea [Agregar un dominio a Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain). 
  
     
5. Cuando haya terminado, elija **Guardar cambios.**
    
6. Espere 24 horas para que los nuevos alias se rellenen en Microsoft 365.
    
    El usuario tendrá ahora una dirección principal y un alias. Por ejemplo, todo el correo enviado a la dirección principal de Eliza Sele, Eliza@NodPublishers.com, y su alias, Sales@NodPublishers.com, irán a la Bandeja de entrada de Eliza.
    
  
7. **Cuando el usuario responda, la dirección *De*  será su alias de correo electrónico principal.** Por ejemplo, supongamos que se envía un mensaje a Sales@NodPublishers.com y llega a la bandeja de entrada de Eliza. Cuando Naiara responda al mensaje, su dirección de correo electrónico principal se mostrará como el remitente, en lugar de ventas@NodPublishers.com. 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>. 
    
    
2. En la página **Usuarios activos**, seleccione el nombre de la persona que desea editar.

3. Junto a **Nombre de usuario /Alias de correo** electrónico, seleccione **Editar**.

    > [!Important] 
    > Si recibe el mensaje de error "No se puede encontrar un parámetro que coincida con el nombre de parámetro **'EmailAddresses",** significa que está tardando un poco más en finalizar la configuración del espacio empresarial o del dominio personalizado si agregó uno recientemente. El proceso de configuración puede tardar hasta 4 horas en completarse. Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo. Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.

4. En el cuadro de texto en **Alias**, escriba la primera parte del nuevo alias de correo electrónico. Si ha agregado su propio dominio a Microsoft 365, puede elegir el dominio para el nuevo alias de correo electrónico mediante la lista desplegable. A continuación, seleccione **Aceptar**.

    > [!IMPORTANT]
    > Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal. 
  
    > [!TIP]
    > El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable. Para agregar otro nombre de dominio a la lista, vea [Agregar un dominio a Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain). 

5. Cuando haya acabado, seleccione **Guardar**.

6. Espere 24 horas para que los nuevos alias se rellenen en Microsoft 365. 
    
    El usuario tendrá ahora una dirección principal y un alias. Por ejemplo, todo el correo enviado a la dirección principal de Eliza Aldán, Eliza@NodPublishers.com y su alias, Sales@NodPublishers.com, irán a la Bandeja de entrada de Eliza.
    
  
7. **Cuando el usuario responda, la dirección *De*  será su alias de correo electrónico principal.** Por ejemplo, supongamos que se envía un mensaje a Sales@NodPublishers.com y llega a la bandeja de entrada de Eliza. Cuando Naiara responda al mensaje, su dirección de correo electrónico principal se mostrará como el remitente, en lugar de ventas@NodPublishers.com. 

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>. 

    
2. En la página **Usuarios activos**, seleccione el nombre de la persona que desea editar.

3. Junto a **Nombre de usuario /Alias de correo** electrónico, seleccione **Editar**.

    > [!Important] 
    > Si recibe el mensaje de error "No se puede encontrar un parámetro que coincida con el nombre de parámetro **'EmailAddresses",** significa que está tardando un poco más en finalizar la configuración del espacio empresarial o del dominio personalizado si agregó uno recientemente. El proceso de configuración puede tardar hasta 4 horas en completarse. Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo. Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.

4. En el cuadro de texto en **Alias**, escriba la primera parte del nuevo alias de correo electrónico. Si ha agregado su propio dominio a Microsoft 365, puede elegir el dominio para el nuevo alias de correo electrónico mediante la lista desplegable. A continuación, seleccione **Aceptar**.

    > [!IMPORTANT]
    > Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal. 
  
    > [!TIP]
    > El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable. Para agregar otro nombre de dominio a la lista, vea [Agregar un dominio a Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain). 

5. Cuando haya acabado, seleccione **Guardar**.

6. Espere 24 horas para que los nuevos alias se rellenen en Microsoft 365. 
    
    El usuario tendrá ahora una dirección principal y un alias. Por ejemplo, todo el correo enviado a la dirección principal de Eliza Aldán, Eliza@NodPublishers.com y su alias, Sales@NodPublishers.com, irán a la Bandeja de entrada de Eliza.
    
  
7. **Cuando el usuario responda, la dirección *De*  será su alias de correo electrónico principal.** Por ejemplo, supongamos que se envía un mensaje a Sales@NodPublishers.com y llega a la bandeja de entrada de Eliza. Cuando Naiara responda al mensaje, su dirección de correo electrónico principal se mostrará como el remitente, en lugar de ventas@NodPublishers.com. 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>¿Ha recibido "No se encuentra un parámetro que coincida con el nombre de parámetro EmailAddresses"?


Si recibe el mensaje de error " No se puede encontrar un parámetro que coincida con el nombre de parámetro **EmailAddresses**" significa que está tardando un poco más en terminar de configurar el inquilino o el dominio personalizado si agregó uno recientemente. El proceso de configuración puede tardar hasta 4 horas en completarse. Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo. Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>¿Ha adquirido la suscripción con GoDaddy u otro partner?


Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.
  
## <a name="related-articles"></a>Artículos relacionados

[Enviar correo electrónico desde otra dirección](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[Cambiar una dirección de correo electrónico y nombre de usuario](../add-users/change-a-user-name-and-email-address.md)
  

