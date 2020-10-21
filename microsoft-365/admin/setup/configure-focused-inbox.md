---
title: Configurar la Bandeja de entrada Prioritarios para todos los usuarios de la organización
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
ms.openlocfilehash: eaf2c7623c81b24670a7b512c6311f0af036b255
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644608"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a>Configurar la Bandeja de entrada Prioritarios para todos los usuarios de la organización

  Si es el responsable de configurar el modo en que el correo electrónico trabaja para todos los usuarios de la empresa, este artículo le interesa. En él se explica cómo personalizarlo o desactivarlo para su empresa y responde a temas sobre [Preguntas más frecuentes](#faq-for-focused-inbox).  <br/> Si quiere desactivar la Bandeja de entrada Prioritarios solo para usted, vea [Desactivar la Bandeja de entrada Prioritarios](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).  
   
Si quiere asegurarse de que los usuarios reciben mensajes de correo electrónico específicos de un aspecto de la empresa como, por ejemplo, los recursos humanos o las nóminas, puede configurar la Bandeja de entrada Prioritarios para que estos mensajes se muestren en la vista Prioritarios. También puede controlar si los usuarios de su organización pueden ver la Bandeja de entrada Prioritarios en su buzón.
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a>Activar o desactivar la Bandeja de entrada Prioritarios en su organización

Use PowerShell para activar o desactivar la Bandeja de entrada Prioritarios para todos los usuarios de la organización. ¿Quiere hacerlo en el Centro de administración de Microsoft 365? Informe a nuestro equipo de ingeniería. **[¡Vote aquí!](https://go.microsoft.com/fwlink/?linkid=862489)**
  
 **Para desactivar la Bandeja de entrada Prioritarios:**
  
En el siguiente ejemplo de PowerShell se **desactiva** la Bandeja de entrada Prioritarios de la organización. Sin embargo, no se bloquea la disponibilidad de la característica para los usuarios. Si quieren, pueden volver a habilitar la Bandeja de entrada Prioritarios en cada uno de sus clientes.  
  
1. [Conectarse a Exchange Online mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Debe tener permisos asignados para poder realizar estos procedimientos. Para ver qué permisos necesita, consulte la entrada "Reglas de transporte" de [Permisos de directivas de mensajería y conformidad](https://go.microsoft.com/fwlink/p/?LinkId=829796).
    
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

Los usuarios verán la vista Prioritarios solo tras cerrar y reiniciar Outlook. Cuando reinicien Outlook, verán una sugerencia en la interfaz de usuario de Outlook, en la que se les dará la opción de usar la nueva Bandeja de entrada Prioritarios. 
  
![Imagen del aspecto de la Bandeja de entrada Prioritarios cuando un usuario abre por primera vez Outlook en la web.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
Si va a cambiar de Otros correos a Bandeja de entrada Prioritarios, los usuarios podrán decidir si habilitan (en "Probar") o si descartan la característica. Si el usuario tiene varios clientes (compatibles), puede habilitar o deshabilitar la Bandeja de entrada Prioritarios de forma individual para cada uno de ellos. La sugerencia tiene un aspecto similar a este:
  
![Se vuelve a abrir una imagen del aspecto de la Bandeja de entrada Prioritarios cuando se implementa para los usuarios y Outlook.](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
Cuando un usuario decide empezar a usar la Bandeja de entrada Prioritarios, Otros correos se deshabilita automáticamente. La carpeta Otros correos se convierte en una carpeta estándar que el usuario puede renombrar o eliminar.
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a>Activar o desactivar la Bandeja de entrada Prioritarios para usuarios específicos

En este ejemplo se **desactiva** la Bandeja de entrada Prioritarios para Íker Arteaga en la organización de Contoso. Sin embargo, no bloquea la disponibilidad de la característica para él. Si quiere, puede volver a habilitar la Bandeja de entrada Prioritarios en cada uno de sus clientes. 
  
1. [Conectarse a Exchange Online mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Debe tener permisos asignados antes de poder realizar estos procedimientos. Para ver qué permisos necesita, consulte la entrada "Reglas de transporte" del tema Permisos de directivas de mensajería y conformidad.
    
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
    
2. Debe tener permisos asignados para poder realizar estos procedimientos. Para ver qué permisos necesita, consulte la entrada "Reglas de transporte" de [Permisos de directivas de mensajería y conformidad](https://go.microsoft.com/fwlink/p/?LinkId=829796).

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
 
Hemos recibido informes en los que se indica que Otros correos dejó de funcionar para algunos usuarios. Si esto ocurre, puede volver a habilitar la carpeta para usuarios específicos. Vea [Configurar Otros correos para su organización](../email/configure-clutter.md).
 
## <a name="faq-for-focused-inbox"></a>Preguntas más frecuentes sobre la Bandeja de entrada Prioritarios

Aquí encontrará respuestas a las preguntas más frecuentes sobre la Bandeja de entrada Prioritarios. 

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a>¿Puedo controlar la implementación de la Bandeja de entrada Prioritarios en mi organización?

Sí. Puede activar o desactivar la Bandeja de entrada Prioritarios para toda la organización. También puede activarla o desactivarla para usuarios específicos. Vea la información que aparece más arriba.
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a>¿La característica Bandeja de entrada Prioritarios solo está disponible para los clientes de Office 2016?

Sí, solo los usuarios de Office 2016 se verán afectados. Esta característica no se incorporará a Outlook 2013 ni a las versiones anteriores.
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a>¿Cuánto tiempo tardan los cambios de la Bandeja de entrada Prioritarios en aplicarse en Outlook?

Cuando haya activado o desactivado la Bandeja de entrada Prioritarios, la configuración empezará a aplicarse cuando los usuarios cierren y reinicien Outlook.
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a>¿Qué pasa con Otros correos cuando activo la Bandeja de entrada Prioritarios?

Después de cambiar, ya no recibirá el correo electrónico que requiere menos acciones en la carpeta Otros correos. En su lugar, el correo electrónico se dividirá entre las pestañas Prioritarios y Otros de la bandeja de entrada. La Bandeja de entrada Prioritarios usa el mismo algoritmo que movía elementos a la carpeta Otros correos, por lo que los mensajes que antes se movían a Otros correos se moverán ahora a Otros. Los mensajes que ya están en la carpeta Otros correos permanecerán en ella hasta que decida moverlos o eliminarlos.
  
Lea esta publicación de [Tony Redmond](https://www.petri.com/author/tony-redmond), MVP (Most Valuable Professional) de Microsoft: [La Bandeja de entrada Prioritarios sustituye a Otros correos en Office 365](https://www.petri.com/focused-inbox-office-365).
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a>¿Puedo mantener a los usuarios en Otros correos? ¿Cuál es la recomendación de Microsoft cuando se trata de usar Otros correos frente a Bandeja de entrada Prioritarios?

Sí, puede mantener a los usuarios en Otros correos y deshabilitar la Bandeja de entrada Prioritarios. Sin embargo, la Bandeja de entrada Prioritarios sustituirá a Otros correos tarde o temprano, por lo que Microsoft recomienda cambiar a la Bandeja de entrada Prioritarios. Para obtener más información sobre cuándo usar Otros correos con Exchange Online, consulte la entrada de blog: [Actualización de la Bandeja de entrada Prioritarios y planes para Otros correos](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a>¿Si quiero cambiar toda la organización a la Bandeja de entrada Prioritarios, tendré que deshabilitar Otros correos para mis usuarios finales?

No. Puede deshabilitar Otros correos para un buzón específico ejecutando el cmdlet Set-Clutter. Sin embargo, si lo hace, el propietario del buzón verá que los mensajes previamente redirigidos a la carpeta Otros correos se quedan en la bandeja de entrada, y deberá procesarlos hasta que se actualice su cliente a una versión compatible con la Bandeja de entrada Prioritarios. Por tanto, es mejor no deshabilitar Otros correos hasta que los clientes actualizados están disponibles.
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a>¿Por qué hay dos cmdlets diferentes para administrar la Bandeja de entrada Prioritarios?

Hay dos estados asociados a la Bandeja de entrada Prioritarios.
  
- **Nivel de organización**: el estado de la Bandeja de entrada Prioritarios y una marca de tiempo de última actualización asociada. 
    
- **Nivel de buzón**: el estado de la Bandeja de entrada Prioritarios y una marca de tiempo de última actualización asociada. 
    
### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a>¿Cómo decide Outlook el estado con el que mostrar la experiencia de la Bandeja de entrada Prioritarios?

Outlook decide mostrar la experiencia seleccionando el cmdlet con la marca de tiempo más reciente. De forma predeterminada, ambas marcas de tiempo son "null" y, en ese caso, la característica está inhabilitada.
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a>¿Por qué el cmdlet Get-FocusedInbox devuelve “true” si he desactivado la Bandeja de entrada Prioritarios en la organización?

Existen dos cmdlets para controlar la Bandeja de entrada Prioritarios. Al ejecutar el cmdlet Get-FocusedInbox para un buzón, devuelve el estado de nivel de buzón de la característica. La experiencia de Outlook se elige según el estado de cmdlet que se modificó por última vez.
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a>¿Puedo ejecutar un script para ver quién tiene activada la Bandeja de entrada Prioritarios?

No, y no se puede cambiar. La habilitación de la Bandeja de entrada Prioritarios es una configuración del lado del cliente, por lo que los cmdlets solo pueden decirle si el buzón del usuario puede activar o no la experiencia del cliente. Es posible que esté habilitada en algunos clientes y en otros deshabilitada, por ejemplo, habilitada en la aplicación Outlook y Outlook Mobile, pero deshabilitada en Outlook en la Web.
