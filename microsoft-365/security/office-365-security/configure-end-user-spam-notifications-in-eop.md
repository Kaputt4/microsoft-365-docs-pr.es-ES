---
title: Configurar notificaciones de correo no deseado para el usuario final en EOP
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
ms.collection:
- M365-security-compliance
description: Las notificaciones de correo no deseado para el usuario final se pueden configurar en la directiva de filtro de contenido de toda la compañía, o bien en las directivas de filtro de contenido personalizadas que se aplican a los dominios.
ms.openlocfilehash: 0fd58d1d59217fb25d29a550fba7e313bd53799a
ms.sourcegitcommit: 3f8957ddd04b8710bb5f314a0902fdee50c7c9b7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "41572726"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a><span data-ttu-id="9f21d-103">Configurar notificaciones de correo no deseado para el usuario final en EOP</span><span class="sxs-lookup"><span data-stu-id="9f21d-103">Configure end-user spam notifications in EOP</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9f21d-104">Este tema va dirigido a clientes independientes de Exchange Online Protection (EOP) que protegen buzones locales.</span><span class="sxs-lookup"><span data-stu-id="9f21d-104">This topic is for Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes.</span></span> <span data-ttu-id="9f21d-105">Los clientes de Exchange online que protegen buzones hospedados en la nube deben leer el siguiente tema en su lugar: [configurar notificaciones de correo no deseado para el usuario final en Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="9f21d-105">Exchange Online customers who are protecting cloud-hosted mailboxes should read the following topic instead: [Configure end-user spam notifications in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span></span> 
  
<span data-ttu-id="9f21d-106">Puede configurar notificaciones de correo no deseado para el usuario final para la directiva predeterminada de filtro de correo no deseado para toda la compañía o para directivas personalizadas de filtro de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="9f21d-106">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies.</span></span> <span data-ttu-id="9f21d-107">La habilitación de mensajes de notificación de correo no deseado para el usuario final permite a los usuarios administrar sus propios mensajes de correo no deseado en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="9f21d-107">Enabling end-user spam notification messages lets your users manage their own spam-quarantined messages.</span></span> 
  
<span data-ttu-id="9f21d-p103">Las notificaciones de correo no deseado para el usuario final contienen una lista de los mensajes de correo no deseado puestos en cuarentena que recibió el usuario final durante el período de tiempo que usted configure (puede especificar cualquier valor entre 1 y 15 días). También puede configurar el idioma en el que está escrito el mensaje de notificación.</span><span class="sxs-lookup"><span data-stu-id="9f21d-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="9f21d-110">Después de recibir un mensaje de notificación, los usuarios finales pueden elegir entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9f21d-110">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="9f21d-111">**Bloquear remitente** si desea que Office 365 agregue el remitente a la lista de remitentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="9f21d-111">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="9f21d-112">**Release** si el mensaje no es correo no deseado y desea que Office 365 envíe el mensaje al buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="9f21d-112">**Release** if the message isn't spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="9f21d-113">**Revise** para navegar al portal de cuarentena en el centro de seguridad y cumplimiento si desea realizar otras acciones, como la versión preliminar o la versión.</span><span class="sxs-lookup"><span data-stu-id="9f21d-113">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9f21d-114">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="9f21d-114">What do you need to know before you begin?</span></span>
<span data-ttu-id="9f21d-115"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="9f21d-115"></span></span>

<span data-ttu-id="9f21d-116">Tiempo estimado para finalizar: 5 minutos</span><span class="sxs-lookup"><span data-stu-id="9f21d-116">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="9f21d-p104">Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "Contra el correo electrónico no deseado" en el tema [Permisos de características en EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="9f21d-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
  
<span data-ttu-id="9f21d-119">Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="9f21d-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="9f21d-120">Usar el EAC para configurar las notificaciones de correo no deseado para el usuario final</span><span class="sxs-lookup"><span data-stu-id="9f21d-120">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="9f21d-121">En el centro de administración de Exchange (EAC), vaya al filtro de **protección** > de**correo no deseado**.</span><span class="sxs-lookup"><span data-stu-id="9f21d-121">In the Exchange Admin Center (EAC), navigate to **Protection** > **Spam filter**.</span></span>
    
2. <span data-ttu-id="9f21d-122">Seleccione la directiva de filtro de contenido para la que quiera habilitar notificaciones de correo no deseado para el usuario final (están deshabilitadas de forma predeterminada).</span><span class="sxs-lookup"><span data-stu-id="9f21d-122">Select the content filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="9f21d-123">En el panel derecho, donde aparece la información de resumen sobre la directiva, haga clic en el vínculo **Configurar notificaciones de correo no deseado para el usuario final**.</span><span class="sxs-lookup"><span data-stu-id="9f21d-123">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="9f21d-124">En el cuadro de diálogo siguiente, puede configurar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9f21d-124">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="9f21d-p105">**Habilitar las notificaciones de correo no deseado para el usuario final** Active esta casilla para habilitar las notificaciones de correo no deseado para el usuario final en esta directiva. (Y viceversa: si la directiva está habilitada, puede desactivar la casilla para deshabilitar las notificaciones de correo no deseado para el usuario final en esta directiva).</span><span class="sxs-lookup"><span data-stu-id="9f21d-p105">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="9f21d-p106">**Enviar notificaciones de correo no deseado para el usuario final cada (días)** Especifique la frecuencia con la que quiere que se envíen las notificaciones de correo no deseado para el usuario final. El valor predeterminado es 3 días. Puede especificar cualquier valor entre 1 y 15 días. Si especifica 7 días, por ejemplo, la notificación incluirá una lista de todos los mensajes destinados a ese usuario en los 7 últimos días que se enviaron, en lugar de al usuario, a la cuarentena de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="9f21d-p106">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="9f21d-131">**Idioma de notificación** En la lista desplegable, seleccione el idioma en el que se escribirán las notificaciones de correo no deseado para el usuario final en esta directiva.</span><span class="sxs-lookup"><span data-stu-id="9f21d-131">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="9f21d-p107">Haga clic en **Guardar**. Aparecerá un resumen de la configuración de la directiva de filtro de contenido, incluida la configuración de notificaciones de correo no deseado para el usuario final, en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="9f21d-p107">Click **save**. A summary of your content filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="9f21d-p108">Las notificaciones de correo no deseado para el usuario final funcionarán únicamente en las directivas de filtro de contenido en las que estén habilitadas. >  Las notificaciones de correo no deseado para el usuario final se envían solo una vez al día. La hora de envío de la notificación no es configurable y, como tal, no se puede confirmar para ningún cliente en concreto.</span><span class="sxs-lookup"><span data-stu-id="9f21d-p108">End-user spam notifications will only be functional for content filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="9f21d-137">**Sugerencia:** Si quiere probar las notificaciones de correo no deseado para el usuario final enviándolas a un conjunto limitado de usuarios antes de implementarlas totalmente, cree una directiva de filtro de contenido personalizada que habilite notificaciones de correo no deseado para el usuario final para los dominios en los que residen los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9f21d-137">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom content filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="9f21d-138">A continuación, en el EAC, en **reglas \> de flujo de correo**, cree una regla de flujo de correo (también denominada regla de transporte) para bloquear mensajes de Quarantine@messaging.microsoft.com (la dirección de correo electrónico que envía notificaciones) con excepciones para los usuarios que desea que reciban las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="9f21d-138">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="9f21d-139">La siguiente imagen es un ejemplo de cómo crear una excepción para dos usuarios (SaraD y AlexD) desde el dominio Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="9f21d-139">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Regla de transporte para probar las notificaciones de correo no deseado de usuario final](../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="9f21d-141">Más información</span><span class="sxs-lookup"><span data-stu-id="9f21d-141">For more information</span></span>

[<span data-ttu-id="9f21d-142">Configurar las directivas de filtro de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="9f21d-142">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
