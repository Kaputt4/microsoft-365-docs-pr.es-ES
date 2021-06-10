---
title: Crear alertas de actividad
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/7/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- BCS160
- MET150
ms.assetid: 72bbad69-035b-4d33-b8f4-549a2743e97d
ROBOTS: NOINDEX, NOFOLLOW
description: Agregar y administrar alertas de actividad en el Centro de seguridad & cumplimiento para que Microsoft 365 le envíe notificaciones por correo electrónico cuando los usuarios realicen actividades específicas
ms.openlocfilehash: 0d5133bd46be6a5a548f2b733bae202f3a611646
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052098"
---
# <a name="create-activity-alerts"></a>Crear alertas de actividad

Puede crear una alerta de actividad que le enviará una notificación por correo electrónico cuando los usuarios realicen actividades específicas en Office 365. Las alertas de actividad son similares a la búsqueda de eventos en el registro de auditoría, excepto que se te enviará un mensaje de correo electrónico cuando se produce un evento para una actividad para la que has creado una alerta. 
  
 **¿Por qué usar alertas de actividad en lugar de buscar en el registro de auditoría?** Puede haber ciertos tipos de actividad o actividad realizadas por usuarios específicos que realmente quieras conocer. En lugar de tener que recordar buscar en el registro de auditoría esas actividades, puede usar alertas de actividad para Microsoft 365 enviar un mensaje de correo electrónico cuando los usuarios realizan esas actividades. Por ejemplo, puede crear una alerta de actividad para notificarle cuándo un usuario elimina archivos en SharePoint o puede crear una alerta para notificarle cuando un usuario elimina permanentemente mensajes de su buzón. La notificación de correo electrónico que se le envió incluye información sobre qué actividad se realizó y el usuario que la realizó.

> [!NOTE]
> Las alertas de actividad están en desuso. Se recomienda empezar a usar directivas de alerta en el centro de seguridad y cumplimiento en lugar de crear nuevas alertas de actividad. Las directivas de alertas proporcionan funciones adicionales, como la capacidad de crear una directiva de  alerta que desencadena una alerta cuando un usuario realiza una actividad especificada y muestra alertas en la página Ver alertas en el Centro de seguridad y cumplimiento. Para obtener más información, vea [Directivas de alerta](alert-policies.md).
  
## <a name="confirm-roles-and-configure-audit-logging"></a>Confirmar roles y configurar el registro de auditoría

- Debe tener asignado el rol Configuración de la organización en el Centro de seguridad & cumplimiento para administrar alertas de actividad. De forma predeterminada, este rol se asigna a los grupos de roles Administrador de cumplimiento y Administración de la organización. Para obtener más información acerca de cómo agregar miembros a grupos de roles, vea Dar acceso a los usuarios al Centro de [seguridad & cumplimiento](../security/defender-365-security/grant-access-to-the-security-and-compliance-center.md).
    
- Usted (u otro administrador) primero debe activar el registro de auditoría para su organización antes de poder empezar a usar alertas de actividad. Para ello, solo tienes que hacer clic **en Iniciar la grabación de** la actividad de usuario y administrador en la página **Alertas de** actividad. (Si no ve este vínculo, la auditoría ya se ha activado para su organización). También puede activar la auditoría  en la página Búsqueda del registro de auditoría en el Centro de seguridad y & cumplimiento (vaya a **Búsqueda** de registro \> **de auditoría de búsqueda).** Solo tiene que hacerlo una vez para su organización.
  
- Puede crear alertas para las mismas actividades que puede buscar en el registro de auditoría. Consulta la [sección Más información](#more-information) para obtener una lista de escenarios comunes (y la actividad específica que se va a supervisar) para la que puedes crear alertas. 
    
- Puede usar la página **Alertas de** actividad del Centro de seguridad y cumplimiento de & para crear alertas solo para la actividad realizada por los usuarios que aparecen en la libreta de direcciones de su organización. No puede usar esta página para crear alertas de actividad realizadas por usuarios externos que no aparecen en la libreta de direcciones. 
    
## <a name="create-an-activity-alert"></a>Crear una alerta de actividad

1. Vaya a [https://protection.office.com/managealerts](https://protection.office.com/managealerts).
    
2. Inicie sesión con su cuenta profesional o educativa.
    
3. En la **página Alertas de** actividad, haga clic ![ en Agregar icono ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Nuevo**.

   Se muestra la página desplegable para crear una alerta de actividad.

    
    ![Crear una alerta de actividad](../media/53888bd5-9fa2-4398-8ccc-1a9dc72517ac.png)
  
4. Complete los siguientes campos para crear una alerta de actividad:
    
    a. **Nombre:** escriba un nombre para la alerta. Los nombres de alerta deben ser únicos en la organización.
    
    b. **Descripción** (opcional): describa la alerta, como las actividades y los usuarios a los que se realiza un seguimiento, y los usuarios a los que se envían las notificaciones por correo electrónico. Las descripciones proporcionan una forma rápida y sencilla de describir el propósito de la alerta a otros administradores.
    
    c. **Tipo de alerta:** asegúrese de que **la opción** Personalizado está seleccionada. 

    d. **Enviar esta alerta cuando:** haga clic **en Enviar esta alerta cuando** y, a continuación, configure estos dos campos:
    
    - **Actividades:** haga clic en la lista desplegable para mostrar las actividades para las que puede crear una alerta. Esta es la misma lista de actividades que se muestra al buscar en el registro de auditoría. Puede seleccionar una o más actividades específicas o hacer clic en el nombre del grupo de actividades para seleccionar todas las actividades del grupo. Para obtener una descripción de estas actividades, vea la sección "Actividades auditadas" [en Buscar en el registro de auditoría.](search-the-audit-log-in-security-and-compliance.md#audited-activities) Cuando un usuario realiza cualquiera de las actividades que ha agregado a la alerta, se envía una notificación por correo electrónico. 
    
     - **Usuarios:** haga clic en este cuadro y, a continuación, seleccione uno o varios usuarios. Si los usuarios de este cuadro realizan las  actividades que agregó al cuadro Actividades, se enviará una alerta. Deje el **cuadro Usuarios** en blanco para enviar una alerta cuando cualquier usuario de la organización realice las actividades especificadas por la alerta. 

    e. Enviar esta alerta  **a:** haga clic en  Enviar esta alerta y, a continuación, haga clic en el cuadro Destinatarios y escriba un nombre para  agregar un usuario que recibirá una notificación por correo electrónico cuando un usuario (especificado en el cuadro Usuarios) realice una actividad (especificada en el cuadro Actividades).  Tenga en cuenta que se le agrega a la lista de destinatarios de forma predeterminada. Puede quitar el nombre de esta lista.
    
5. Haga **clic en Guardar** para crear la alerta. 
    
    La nueva alerta se muestra en la lista de la página **Alertas de** actividad. 
    
    ![Se muestra una lista de alertas en la página Alertas de actividad](../media/02b774f2-1719-41de-bbc9-5e5b7576f335.png)
  
    El estado de la alerta se establece en **On**. Tenga en cuenta que también aparecen los destinatarios que recibirán una notificación por correo electrónico cuando se envíe una alerta. 
  
## <a name="turn-off-an-activity-alert"></a>Desactivar una alerta de actividad

Puedes desactivar una alerta de actividad para que no se envíe una notificación por correo electrónico. Después de desactivar la alerta de actividad, aún se muestra en la lista de alertas de actividad de la organización y aún puede ver sus propiedades.
  
1. Vaya a Ir a [https://protection.office.com/managealerts](https://protection.office.com/managealerts) .
    
2. Inicie sesión con su cuenta profesional o educativa.
    
3. En la lista de alertas de actividad de su organización, haga clic en la alerta que desea desactivar.
    
4. En la **página Editar alerta,** haga clic en el modificador **de** alternancia Activar para cambiar el estado a **Desactivado** y, a continuación, haga clic en **Guardar**.
    
    El estado de la alerta en las páginas **Alertas de** actividad está establecido en **Desactivado**. 
    
Para volver a activar una alerta de actividad, repita estos pasos y haga clic en el modificador de **alternancia** Desactivar para cambiar el estado a **On**.
  
## <a name="more-information"></a>Más información

- Este es un ejemplo de la notificación de correo electrónico que se envía a los usuarios que  se especifican en el campo Enviar esta alerta a (y que aparece en Destinatarios en la página **Alertas** de actividad) en el Centro de seguridad & cumplimiento. 
    
    ![Ejemplo de notificación de correo electrónico enviado para una alerta de actividad](../media/a5f91611-fae6-4fe9-82f5-58521a2e2541.png)
  
- Estas son algunas actividades comunes de documentos y correo electrónico para las que puede crear alertas de actividad. Las tablas describen la actividad, el nombre de la actividad para la que se va a  crear una alerta y el nombre del grupo de actividades en el que se muestra la actividad en la lista desplegable Actividades. Para ver una lista completa de las actividades para las que puede crear alertas de actividad, consulte la sección "Actividades auditadas" en [Buscar en el registro de auditoría.](search-the-audit-log-in-security-and-compliance.md#audited-activities)
    
    > [!TIP]
    > Es posible que desee crear una alerta de actividad para una sola actividad que realice cualquier usuario. O puede que desee crear una alerta de actividad que realice un seguimiento de varias actividades realizadas por uno o varios usuarios. 
  
    En la tabla siguiente se enumeran algunas actividades comunes relacionadas con documentos SharePoint o OneDrive para la Empresa.
    
    |**Cuando un usuario hace esto...**|**Crear una alerta para esta actividad**|**Grupo de actividades**|
    |:-----|:-----|:-----|
    |Ve un documento en un sitio.  <br/> |Archivo al que se tiene acceso  <br/> |Actividades de archivos y carpetas  <br/> |
    |Edita o cambia un documento.  <br/> |Archivo modificado  <br/> |Actividades de archivos y carpetas  <br/> |
    |Comparte un documento con un usuario fuera de la organización.  <br/> |Compartir archivo, carpeta o sitio  <br/> And  <br/> Invitación de uso compartido creada  <br/> Para obtener más información, consulte [Usar la auditoría de uso compartido en el registro de auditoría](use-sharing-auditing.md).  <br/> |Actividades de solicitud de acceso y uso compartido  <br/> |
    |Carga o descarga un documento.  <br/> |Archivo cargado  <br/> And/or  <br/> Archivo descargado  <br/> |Actividades de archivos y carpetas  <br/> |
    |Cambia los permisos de acceso a un sitio.  <br/> |Permisos de sitio modificados  <br/> |Actividades de administración del sitio  <br/> |

    En la tabla siguiente se enumeran algunas actividades comunes relacionadas con el correo electrónico Exchange Online.

    |**Cuando un usuario hace esto...**|**Crear una alerta para esta actividad**|**Grupo de actividades**|
    |:-----|:-----|:-----|
    |Elimina permanentemente (purga) un mensaje de correo electrónico de su buzón.  <br/> |Mensajes purgados del buzón  <br/> | Actividades de buzón de Exchange  <br/> |
    |Envía un mensaje de correo electrónico desde un buzón compartido.  <br/> |Mensaje enviado mediante los permisos de Enviar como  <br/> And  <br/> Mensaje enviado mediante los permisos en nombre de  <br/> | Actividades de buzón de Exchange  <br/> |
   
- También puede usar los cmdlets **New-ActivityAlert** y **Set-ActivityAlert** en PowerShell del Centro de seguridad & cumplimiento para crear y editar alertas de actividad. Tenga en cuenta lo siguiente si usa estos cmdlets para crear o editar alertas de actividad: 
    
  - Si usa un cmdlet para agregar una actividad a la  alerta que no aparece en la lista desplegable Actividades, se muestra un mensaje en la página de propiedades de la alerta que dice: "Esta alerta tiene operaciones personalizadas que no aparecen en el selector". 
    
  - Un buen motivo para usar los cmdlets para crear o editar una alerta de actividad es enviar notificaciones por correo electrónico a alguien fuera de su organización. Este usuario externo aparecerá en la lista de destinatarios de la alerta. Pero si quita este usuario externo de la alerta, no se puede volver a agregar a la alerta mediante la página **Editar alerta.** Tendrá que volver a agregar el usuario externo mediante el cmdlet **Set-ActivityAlert** o usar el cmdlet **New-ActivityAlert** para agregar el mismo usuario externo (o diferente) a una nueva alerta. 
