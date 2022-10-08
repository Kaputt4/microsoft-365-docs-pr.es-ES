---
title: Agregar otro alias de correo electrónico para un usuario
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Obtenga información sobre cómo puede tener más de una dirección de correo electrónico, denominada alias de correo electrónico, asociada a su cuenta de Microsoft 365 para empresas. '
ms.openlocfilehash: 01c2871c2918dc9be9f1eb29f44bbede19ea0afb
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68197995"
---
# <a name="add-another-email-alias-for-a-microsoft-365-business-subscription-user"></a>Agregar otro alias de correo electrónico para un usuario de suscripción empresarial de Microsoft 365
  
Este artículo está destinado a administradores de Microsoft 365 que tienen suscripciones empresariales. No está dirigido a usuarios particulares.
  
Una dirección de correo electrónico principal en Microsoft 365 suele ser la dirección de correo electrónico que se asignó a un usuario cuando se creó su cuenta. Cuando este envía un correo electrónico a un contacto, su dirección de correo electrónico principal es la que normalmente aparece en el campo  *De*  en las aplicaciones de correo electrónico. También pueden tener más de una dirección de correo electrónico asociada a su cuenta de Microsoft 365 para empresas. Estas direcciones adicionales se denominan "alias". 
  
Por ejemplo, supongamos que Jenna tiene la dirección de correo electrónico jenna@contosoco.com, pero también quiere recibir correo electrónico en jen@contosoco.com porque algunas personas hacen referencia a ella con ese nombre. Puede crear alias para ella para que ambas direcciones de correo electrónico vayan a la bandeja de entrada de Jenna.
  
Puede crear hasta 400 alias para un usuario. No se necesitan licencias o cargos adicionales.
  
> [!Tip]
> Si desea que varias personas administren el correo electrónico enviado a una única dirección de correo electrónico, como info@NodPublishers.com o sales@NodPublishers.com, cree un buzón compartido. Para más información, consulte [Creación de un buzón compartido](create-a-shared-mailbox.md).

> [!TIP]
> Si necesita ayuda con los pasos que se describen en este tema, considere la posibilidad de [trabajar con un especialista en pequeñas empresas de Microsoft](https://go.microsoft.com/fwlink/?linkid=2186871). Con Business Assist, usted y sus empleados obtienen acceso de forma ininterrumpida a especialistas de pequeñas empresas a medida que hace crecer su negocio, desde la incorporación hasta el uso diario.
  
## <a name="add-email-aliases-to-a-user"></a>Agregar alias de correo electrónico a un usuario

Debe tener derechos de Administración globales para agregar alias de correo electrónico a un usuario.

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. En la página **Usuarios activos** , seleccione el usuario > **Administrar nombre de usuario y correo electrónico**. No verá esta opción si la persona no tiene una licencia asignada. 
    
3. Seleccione **+ Agregar un alias** y escriba un nuevo alias para el usuario.   
    
    > [!Important] 
    > Si recibe el mensaje de error "**No se puede encontrar un parámetro que coincida con el nombre de parámetro "EmailAddresses**", significa que se tarda un poco más en finalizar la configuración del inquilino o el dominio personalizado si agregó uno recientemente. El proceso de configuración puede tardar hasta 4 horas en completarse. Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo. Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.
    
  
    > [!IMPORTANT]
    > Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal. 


   > [!IMPORTANT]
   >  Si recibe el mensaje de error **Este usuario está sincronizado con su Active Directory local. Algunos detalles solo se pueden editar a través de la instancia local de Active Directory**, lo que significa que Active Directory es autoritativo para los atributos de los usuarios sincronizados, por lo que debe modificar los atributos de la Active Directory local.
  
    > [!TIP]
    > El alias de correo electrónico tiene que terminar con un dominio de la lista desplegable. Para agregar otro nombre de dominio a la lista, consulte [Agregar un dominio a Microsoft 365](../setup/add-domain.md). 
  
     
5. Cuando haya terminado, elija **Guardar cambios**.
    
6. Espere 24 horas para que los nuevos alias se rellenen en Microsoft 365.
    
    El usuario ahora tendrá una dirección principal y un alias. Por ejemplo, todo el correo enviado a la dirección principal de Eliza Hoffman, Eliza@NodPublishers.com, y su alias, Sales@NodPublishers.com, irán a la Bandeja de entrada de Eliza.
    
  
7. **Cuando el usuario responde, la dirección *De* dependerá de su cliente de Outlook. Outlook en la Web usará el alias en el que se recibió el correo electrónico (lo llamaremos principio de ping-pong). El escritorio de Outlook usará su alias de correo electrónico principal.** Por ejemplo, supongamos que se envía un mensaje a Sales@NodPublishers.com y llega a la bandeja de entrada de Eliza. Cuando Eliza responde al mensaje mediante el escritorio de Outlook, su dirección de correo electrónico principal aparecerá como Eliza@NodPublishers.com, no como Sales@NodPublishers.com.
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>¿Obtuvo "No se encontró un parámetro que coincida con el nombre de parámetro EmailAddresses"?

Si recibe el mensaje de error "**No se puede encontrar un parámetro que coincida con el nombre de parámetro EmailAddresses**", significa que se tarda un poco más en finalizar la configuración del inquilino o en el dominio personalizado si ha agregado uno recientemente. El proceso de configuración puede tardar hasta 4 horas en completarse. Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo. Si el problema continúa, llame al soporte técnico, que realizará una sincronización completa.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>¿Ha adquirido la suscripción con GoDaddy u otro partner?


Si adquirió su suscripción con GoDaddy u otro partner, tendrá que usar la consola de administración del proveedor para establecer el nuevo alias como el principal.

## <a name="sending-email-from-the-proxy-address-easily"></a>Envío de correo electrónico desde la dirección de proxy fácilmente

En julio de 2021 se implementa una nueva característica que permite a los usuarios enviar desde sus alias fácilmente al usar Outlook en la Web. Cuando la característica se implementa en un inquilino en el que el administrador de inquilinos usa el `Set-OrganizationConfig -SendFromAliasEnabled $true` cmdlet , los usuarios del inquilino tendrán acceso a una lista de casillas donde cada entrada corresponde a un alias en su configuración de Outlook. Al seleccionar un alias, aparecerá en la lista desplegable Desde del formulario Redactar.
  
## <a name="related-content"></a>Contenido relacionado

[Enviar correo electrónico desde una dirección diferente](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (artículo)

[Cambiar un nombre de usuario y una dirección de correo electrónico](../add-users/change-a-user-name-and-email-address.md) (artículo)

[Configurar el reenvío de correo electrónico en Microsoft 365](configure-email-forwarding.md) (artículo)
