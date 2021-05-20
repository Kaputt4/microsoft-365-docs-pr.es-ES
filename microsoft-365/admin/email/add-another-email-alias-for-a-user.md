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
description: 'Obtén información sobre cómo puedes tener más de una dirección de correo electrónico, llamada alias de correo electrónico, asociada a tu Microsoft 365 para la cuenta empresarial. '
ms.openlocfilehash: ec5bc69a42c5183413f11649b7d7ec6baaf40b01
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572110"
---
# <a name="add-another-email-alias-for-a-user"></a>Agregar otro alias de correo electrónico para un usuario
  
Este artículo es para administradores Microsoft 365 que tienen suscripciones empresariales. No está dirigido a usuarios particulares.
  
Una dirección de correo electrónico principal en Microsoft 365 suele ser la dirección de correo electrónico que se asignó a un usuario cuando se creó su cuenta. Cuando este envía un correo electrónico a un contacto, su dirección de correo electrónico principal es la que normalmente aparece en el campo  *De*  en las aplicaciones de correo electrónico. También pueden tener más de una dirección de correo electrónico asociada con su Microsoft 365 para la cuenta de negocios. Estas direcciones adicionales se denominan "alias". 
  
Por ejemplo, digamos que Jenna tiene la dirección de correo electrónico jenna@contosoco.com, pero también quiere recibir correo electrónico en jen@contosoco.com porque algunas personas se refieren a ella por ese nombre. Puedes crear alias para ella para que ambas direcciones de correo electrónico vayan a la bandeja de entrada de Jenna.
  
Puede crear hasta 400 alias para un usuario. No se necesitan licencias o cargos adicionales.
  
> [!Tip]
> Si desea que varias personas administren el correo electrónico enviado a una sola dirección de correo electrónico como info@NodPublishers.com o sales@NodPublishers.com, cree un buzón compartido. Para obtener más información, consulte [Crear un buzón compartido](create-a-shared-mailbox.md).
  
## <a name="add-email-aliases-to-a-user"></a>Agregar alias de correo electrónico a un usuario

Debe tener [permisos de administrador](../add-users/about-admin-roles.md) para hacerlo. 

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. En la página **Usuarios activos,** seleccione el usuario > **Administrar nombre de usuario y correo electrónico.** No verá esta opción si la persona no tiene una licencia asignada. 
    
3. Seleccione **+ Agregar un alias** e introduzca un nuevo alias para el usuario.   
    
    > [!Important] 
    > Si recibe el mensaje de error " No se puede encontrar un parámetro que coincida con el **nombre del parámetro 'EmailAddresses**", significa que está tardando un poco más en terminar de configurar el inquilino, o su dominio personalizado si agregó recientemente uno. El proceso de configuración puede tardar hasta 4 horas en completarse. Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo. Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.
    
  
    > [!IMPORTANT]
    > Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal. 
  
    > [!TIP]
    > El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable. Para agregar otro nombre de dominio a la lista, consulte [Agregar un dominio a Microsoft 365](../setup/add-domain.md). 
  
     
5. Cuando haya terminado, elija **Guardar cambios**.
    
6. Espere 24 horas para que los nuevos alias se rellene en toda Microsoft 365.
    
    El usuario ahora tendrá una dirección principal y un alias. Por ejemplo, todo el correo enviado a la dirección principal de Eliza Hoffman, Eliza@NodPublishers.com, y su alias, Sales@NodPublishers.com, irá a la Bandeja de entrada de Eliza.
    
  
7. **Cuando el usuario responde, la dirección From dependerá *de* su cliente Outlook. Outlook en la web usarán el alias en el que se recibió el correo electrónico (lo llamaremos el principio de ping-pong). Outlook escritorio usará su alias de correo electrónico principal.** Por ejemplo, supongamos que se envía un mensaje a Sales@NodPublishers.com y llega a la bandeja de entrada de Eliza. Cuando Eliza responde al mensaje usando Outlook escritorio, su dirección de correo electrónico principal aparecerá como Eliza@NodPublishers.com, no Sales@NodPublishers.com.
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>¿Obtuvo "No se puede encontrar un parámetro que coincida con el nombre de parámetro EmailAddresses"?

Si recibe el mensaje de error " No se puede encontrar un parámetro que coincida con el **nombre del parámetro EmailAddresses**" significa que está tardando un poco más en terminar de configurar el inquilino, o su dominio personalizado si agregó recientemente uno. El proceso de configuración puede tardar hasta 4 horas en completarse. Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo. Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>¿Ha adquirido la suscripción con GoDaddy u otro partner?


Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.

## <a name="sending-email-from-the-proxy-address-easily"></a>Enviar correo electrónico desde la dirección proxy fácilmente

Una nueva característica se está implementando en abril de 2021 que permite a los usuarios enviar desde sus alias fácilmente cuando se utilizan Outlook en la web. Cuando la característica se implementa en una tenencia donde el administrador de inquilinos usa el `Set-OrganizationConfig -SendFromAliasEnabled $true` cmdlet, los usuarios dentro de la tenencia tendrán acceso a una lista de casillas de verificación donde cada entrada corresponde a un alias en su configuración de Outlook. Al seleccionar un alias, aparecerá en el menú desplegable Desde del formulario Redactar.
  
## <a name="related-content"></a>Contenido relacionado

[Enviar correo electrónico desde una dirección diferente](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (artículo)

[Cambiar un nombre de usuario y una dirección de correo electrónico](../add-users/change-a-user-name-and-email-address.md) (artículo)

[Configurar el reenvío de correo electrónico en Microsoft 365](configure-email-forwarding.md) (artículo)
