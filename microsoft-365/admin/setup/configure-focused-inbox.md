---
title: Configurar la Bandeja de entrada Prioritarios para todos los usuarios de la organización
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 613a845c-4b71-41de-b331-acdcf5b6625d
description: 'Obtenga información acerca de cómo configurar la Bandeja de entrada Prioritarios para todos los usuarios específicos de su organización. '
ms.openlocfilehash: f56e85e79fcf17cde89ec3d6094ca757ccf0cc68
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779934"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a>Configurar la Bandeja de entrada Prioritarios para todos los usuarios de la organización

  Si es el responsable de configurar el modo en que el correo electrónico trabaja para todos los usuarios de la empresa, este artículo le interesa. En él se explica cómo personalizarlo o desactivarlo para su empresa y responde a temas sobre [Preguntas más frecuentes](#faq-for-focused-inbox).  <br/> Si quiere desactivar la Bandeja de entrada Prioritarios solo para usted, vea [Desactivar la Bandeja de entrada Prioritarios](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).  
   
If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view. You can also control whether users in your organization see the Focused Inbox in their mailbox.
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a>Activar o desactivar la Bandeja de entrada Prioritarios en su organización

Use PowerShell para activar o desactivar la Bandeja de entrada Prioritarios para todos los usuarios de la organización. ¿Quiere hacerlo en el Centro de administración de Microsoft 365? Informe a nuestro equipo de ingeniería. **[¡Vote aquí!](https://go.microsoft.com/fwlink/?linkid=862489)**
  
 **Para desactivar la Bandeja de entrada Prioritarios:**
  
The following PowerShell example turns Focused Inbox **Off** in your organization. However, it doesn't block the availability of the feature for your users. If they want, they can still re-enable Focused Inbox again on each of their clients. 
  
1. [Conectarse a Exchange Online mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).
    
3. Ejecute el cmdlet **Get-OrganizationConfig**. 
    
 ``` PowerShell
Get-OrganizationConfig
 ```

4. Busque **FocusedInboxOn** para ver la configuración actual: 
    
    ![Respuesta de PowerShell sobre el estado de la Bandeja de entrada Prioritarios.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Ejecute el cmdlet siguiente para desactivar la Bandeja de entrada Prioritarios.
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $false
 ```

6. Ejecute el cmdlet **Get-OrganizationConfig** y verá que FocusedInboxOn se establece en $false, lo que significa se ha desactivado. 
    
 **Para activar la Bandeja de entrada Prioritarios:**
  
- En el Paso 5 anterior, ejecute el cmdlet siguiente para activar la Bandeja de entrada Prioritarios.
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $true
 ```

## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a>¿Qué ven los usuarios después de que se active la Bandeja de entrada Prioritarios? 

Your users will see the Focused view only after they close and restart Outlook. When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.
  
![Imagen del aspecto de la Bandeja de entrada Prioritarios cuando un usuario abre por primera vez Outlook en la web.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature. If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one. The tip looks like this:
  
![Se vuelve a abrir una imagen del aspecto de la Bandeja de entrada Prioritarios cuando se implementa para los usuarios y Outlook.](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
When a user decides to start using Focused Inbox, Clutter gets disabled automatically. The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a>Activar o desactivar la Bandeja de entrada Prioritarios para usuarios específicos

This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization. However, it doesn't block the availability of the feature to him. If his wants, he can still re-enable Focused Inbox again on each of his clients. 
  
1. [Conectarse a Exchange Online mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.
    
3. Ejecute el cmdlet **Get-FocusedInbox**, por ejemplo: 
    
 ``` PowerShell
 Get-FocusedInbox -Identity <tim@contoso.com>
 ```

4. Busque FocusedInboxOn para ver la configuración actual:
    
    ![Respuesta de PowerShell sobre el estado de la Bandeja de entrada Prioritarios.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Ejecute el cmdlet siguiente para desactivar la Bandeja de entrada Prioritarios:
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
 ```

6. También puede ejecutar el cmdlet siguiente para activarlo:
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
 ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Usar la interfaz de usuario para crear reglas de transporte que dirijan los mensajes de correo electrónico hacia la vista Prioritarios de todos los usuarios

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.
    
2. Vaya a **flujo de correo** \> **Reglas**. Seleccione ![Agregar icono EAC](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) y, a continuación, seleccione **Crear una nueva regla...**. 
    
3. Cuando termine de crear la regla, seleccione **Guardar** para iniciarla. 
    
    En la siguiente imagen, se muestra un ejemplo en el que todos los mensajes del "Departamento de nóminas" se entregarán en la Bandeja de entrada Prioritarios.
    
    ![Bandeja de entrada Prioritarios de nóminas](../../media/focusedinbox-transport-rule.PNG)
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Usar PowerShell para crear reglas de transporte que dirijan los mensajes de correo electrónico hacia la vista Prioritarios de todos los usuarios

1. [Conectarse a Exchange Online mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).

3. Ejecute el comando siguiente para permitir que todos los mensajes del "Departamento de nóminas", por ejemplo, se entreguen en la Bandeja de entrada Prioritarios.
    
 ``` PowerShell
 New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
 ```

> [!IMPORTANT]
> En este ejemplo, tanto "X-MS-Exchange-Organization-BypassFocusedInbox" como "true" distinguen mayúsculas de minúsculas.
> Además, la Bandeja de entrada Prioritarios respetará el encabezado X que omite Otros correos, por lo que si usa esta configuración en Otros correos, se usará en la Bandeja de entrada Prioritarios. Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194).

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Puede comprobar los encabezados de los mensajes de correo electrónico para ver si los mensajes de correo electrónico están llegando a la Bandeja de entrada debido a la omisión de la regla de transporte de Bandeja de entrada Prioritarios. Seleccione un mensaje de correo electrónico de un buzón de la organización en el que se aplique la regla de transporte de la Bandeja de entrada Prioritarios. Compruebe los encabezados del mensaje. Debería ver el encabezado **X-MS-Exchange-Organization-BypassFocusedInbox: true**. Esto significa que la omisión está funcionando. Consulte el artículo [Ver la información de encabezado de Internet en un mensaje de correo electrónico](https://go.microsoft.com/fwlink/p/?LinkId=822530) para obtener información sobre cómo encontrar la información del encabezado. 
 
## <a name="turn-onoff-clutter"></a>Desactivar o activar Otros correos
 
We've received reports that Clutter suddenly stopped working for some users. If this happens, you can enable it again for specific users. See [Configure Clutter for your organization](../email/configure-clutter.md).
 
## <a name="faq-for-focused-inbox"></a>Preguntas más frecuentes sobre la Bandeja de entrada Prioritarios

Aquí encontrará respuestas a las preguntas más frecuentes sobre la Bandeja de entrada Prioritarios. 

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a>¿Puedo controlar la implementación de la Bandeja de entrada Prioritarios en mi organización?

Yes. You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users. See above.
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a>¿La característica Bandeja de entrada Prioritarios solo está disponible para los clientes de Office 2016?

Sí, solo los usuarios de Office 2016 se verán afectados. Esta característica no se incorporará a Outlook 2013 ni a las versiones anteriores.
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a>¿Cuánto tiempo tardan los cambios de la Bandeja de entrada Prioritarios en aplicarse en Outlook?

Cuando haya activado o desactivado la Bandeja de entrada Prioritarios, la configuración empezará a aplicarse cuando los usuarios cierren y reinicien Outlook.
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a>¿Qué pasa con Otros correos cuando activo la Bandeja de entrada Prioritarios?

After switching, you'll no longer receive less actionable email in the Clutter folder. Instead, email will be split between the Focused and Other tabs in your inbox. The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other. Any messages already in your Clutter folder will remain there until you decide to delete or move them.
  
Lea esta publicación de [Tony Redmond](https://www.petri.com/author/tony-redmond), MVP (Most Valuable Professional) de Microsoft: [La Bandeja de entrada Prioritarios sustituye a Otros correos en Office 365](https://www.petri.com/focused-inbox-office-365).
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a>¿Puedo mantener a los usuarios en Otros correos? ¿Cuál es la recomendación de Microsoft cuando se trata de usar Otros correos frente a Bandeja de entrada Prioritarios?

Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now. To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a>¿Si quiero cambiar toda la organización a la Bandeja de entrada Prioritarios, tendré que deshabilitar Otros correos para mis usuarios finales?

No. It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet. However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox. It's therefore best not to disable Clutter until the upgraded clients are available.
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a>¿Por qué hay dos cmdlets diferentes para administrar la Bandeja de entrada Prioritarios?

Hay dos estados asociados a la Bandeja de entrada Prioritarios.
  
- **Nivel de organización**: el estado de la Bandeja de entrada Prioritarios y una marca de tiempo de última actualización asociada. 
    
- **Nivel de buzón**: el estado de la Bandeja de entrada Prioritarios y una marca de tiempo de última actualización asociada. 
    
### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a>¿Cómo decide Outlook el estado con el que mostrar la experiencia de la Bandeja de entrada Prioritarios?

Outlook decides to show the experience by choosing which cmdlet has the latest time stamp. By default, both time stamps are "null" and in this case, the feature is enabled.
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a>¿Por qué el cmdlet Get-FocusedInbox devuelve “true” si he desactivado la Bandeja de entrada Prioritarios en la organización?

There are two cmdlets for controlling Focused Inbox. When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature. The experience in Outlook is chosen based on which cmdlet state was last modified.
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a>¿Puedo ejecutar un script para ver quién tiene activada la Bandeja de entrada Prioritarios?

No, and this is by design. Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience. It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.
