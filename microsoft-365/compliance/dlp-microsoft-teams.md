---
title: Prevención de pérdida de datos y Microsoft Teams.
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Los chats y canales de Microsoft Teams admiten directivas de prevención de pérdida de datos (DLP).
ms.openlocfilehash: ae9f7b273dc84d16c499a13f4c491d517d804cd2
ms.sourcegitcommit: 6d86713c3b1da2db338c78fa60bd7d93e24aa6f4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2022
ms.locfileid: "67639622"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>Prevención de pérdida de datos y Microsoft Teams.

Si su organización tiene Prevención de pérdida de datos de Microsoft Purview (DLP), puede definir directivas que impidan que los usuarios compartan información confidencial en un canal de Microsoft Teams o una sesión de chat. Estos son algunos ejemplos de cómo funciona esta protección:

- **Ejemplo 1: Protección de la información confidencial en los mensajes**. Supongamos que alguien intenta compartir información confidencial en un chat o canal de Teams con invitados (usuarios externos). Si tiene definida una directiva DLP para evitarlo, se eliminan los mensajes con información confidencial que se envían a usuarios externos. Esto sucede automáticamente y en cuestión de segundos, según cómo se configura la directiva DLP.

    > [!NOTE]
    > DLP para Microsoft Teams bloquea el contenido confidencial cuando se comparte con usuarios de Microsoft Teams que tienen:<br/>- [acceso de invitado](/MicrosoftTeams/guest-access) en equipos y canales; O<br/>- [acceso externo](/MicrosoftTeams/manage-external-access) en reuniones y sesiones de chat. <p>DLP para sesiones de chat externas solo funcionará si tanto el remitente como el receptor están en modo Solo teams y mediante [la federación nativa de Microsoft Teams](/microsoftteams/manage-external-access). DLP para Teams no bloquea los mensajes en [interoperabilidad](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) con sesiones de chat federadas Skype Empresarial o no nativas.

- **Ejemplo 2: Protección de información confidencial en documentos**. Supongamos que alguien intenta compartir un documento con invitados en un canal o chat de Microsoft Teams y que el documento contiene información confidencial. Si tiene una directiva DLP definida para evitarlo, el documento no se abrirá para esos usuarios. La directiva DLP debe incluir SharePoint y OneDrive para poder establecer la protección. Este es un ejemplo de DLP para SharePoint que se muestra en Microsoft Teams y, por lo tanto, requiere que los usuarios tienen licencia para Office 365 DLP (incluido en Office 365 E3), pero no requiere que los usuarios tengan licencia para Cumplimiento avanzado de Office 365. 
   
Puede ampliar la directiva DLP de Teams para cubrir SharePoint Online y OneDrive para la Empresa seleccionando **Protección automática de archivos** del banner en **Directivas** **DLP** > . Esto habilitará la protección DLP para todos los archivos compartidos en chats y canales de Teams con las mismas reglas que se aplican a los mensajes de Teams. Una vez habilitada, la extensión se aplicará a todas las directivas DLP de Teams existentes y futuras, por lo que no es necesario crear directivas independientes para SharePoint y OneDrive para la protección de archivos. 

> [!NOTE]
> Solo las directivas de Teams que tengan reglas con condiciones o excepciones de **contenido que contengan** o **contenido se compartan desde Microsoft 365** se pueden ampliar para la protección automática de archivos. Si la configuración de condición o excepción tiene **Sender es**, **el dominio del remitente es**, **el destinatario es** y **el dominio del destinatario está** presente, se producirá un error en la acción de extensión porque estas condiciones no se aplican a SharePoint y OneDrive.

- **Ejemplo 3: Protección de las comunicaciones en canales compartidos de Teams**. En el caso de los canales compartidos, se aplica la directiva DLP del equipo host de Teams. Por ejemplo, supongamos que hay un canal compartido propiedad de TeamA de Contoso. TeamA tiene una directiva DLP P1. Hay tres maneras de compartir un canal:
    - **Compartir con un miembro**: invita a user1 de Contoso a unirse al canal compartido sin convertirlo en miembro de TeamA. Todos los usuarios de este canal compartido, incluido user1, estarán cubiertos por P1.
    - **Compartir con el equipo (internamente):** el canal se comparte con otro equipo de TeamB en Contoso. Que otro equipo puede tener una directiva DLP diferente, pero eso no importa. P1 se aplicará a todos los usuarios de este canal compartido, incluidos los usuarios de TeamA y TeamB.
    - **Compartir con el equipo (entre inquilinos):** el canal se comparte con un equipo TeamF en Fabrikam. Fabrikam puede tener su propia directiva DLP, pero eso no importa. P1 se aplicará a todos los usuarios de este canal compartido, incluidos los usuarios de TeamA (Contoso) y TeamF (Fabrikam).
 
## <a name="dlp-licensing-for-microsoft-teams"></a>Licencias DLP para Microsoft Teams

Las funcionalidades de [prevención de pérdida de datos](dlp-learn-about-dlp.md) incluyen mensajes de canal y chat de Microsoft Teams, **incluidos los mensajes de canal privado** para:

- Office 365 E5/A5/G5
- Microsoft 365 E5/A5/G5
- Microsoft 365 E5/A5/G5 Information Protection y gobernanza
- Cumplimiento de Microsoft 365 E5/A5/G5/F5 y cumplimiento de & de seguridad de F5

Office 365 y Microsoft 365 E3 incluyen protección DLP para SharePoint Online, OneDrive y Exchange Online. Esto también incluye los archivos que se comparten a través de Teams porque Teams usa SharePoint Online y OneDrive para compartir archivos.

La compatibilidad con la protección DLP en el chat de Teams requiere E5.

Para obtener más información sobre los requisitos de licencias, consulte [Instrucciones de licencias de Microsoft 365 del nivel de espacio empresarial](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

> [!IMPORTANT]
> DLP solo se aplica a los mensajes reales en el subproceso de chat o canal. Las notificaciones de actividad, que incluyen una vista previa de mensajes breves y aparecen en función de la configuración de notificación de un usuario, **no** se incluyen en DLP de Teams. Cualquier información confidencial presente en la parte del mensaje que aparece en la vista previa permanecerá visible en la notificación incluso después de que se haya aplicado la directiva DLP y se haya quitado la información confidencial del propio mensaje.

## <a name="scope-of-dlp-protection"></a>Ámbito de la protección DLP

La protección DLP se aplica de forma diferente a las entidades de Teams.

|Cuando la directiva tiene el ámbito |Estas entidades de Teams |Tendrá la protección DLP disponible|
|---------|---------|---------|
|Cuentas de usuario individuales     |1:1/n chats         |Yes         |
|     |Mensajes de canal estándar y compartidos         |No         |
|     |Mensajes de canal privado         |Sí         |
|Grupos de seguridad o listas de distribución  | 1:1/n chats         |Yes         |
|     |Mensajes de canal estándar y compartidos  |No         |
|     |Mensajes de canal privado         |Sí        |
|Grupo de Microsoft 365    |1:1/n chats          |No         |
|     |Mensajes de canal estándar y compartidos          |Yes        |
|     |Mensajes de canal privado|No| 


## <a name="policy-tips-help-educate-users"></a>Las sugerencias de directiva ayudan a educar a los usuarios

De forma similar al funcionamiento de DLP en [Exchange, Outlook, Outlook en la Web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, sitios OneDrive para la Empresa](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites) y [clientes de escritorio de Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), las sugerencias de directiva aparecen cuando se desencadena una acción con una directiva DLP. Este es un ejemplo de una sugerencia de directiva:

![Notificación de mensajes bloqueados en Teams.](../media/dlp-teams-blockedmessage-notification.png)

Aquí, el remitente intentó compartir un número de seguro social en un canal de Microsoft Teams. El vínculo **¿Qué puedo hacer?** abre un cuadro de diálogo que proporciona opciones para que el remitente resuelva el problema. Tenga en cuenta que el remitente puede optar por invalidar la directiva o notificar a un administrador que la revise y resuelva.

![Opciones para resolver el mensaje bloqueado.](../media/dlp-teams-blockedmessage-possibleactions.png)

En su organización, puede optar por permitir que los usuarios invaliden una directiva DLP. Al configurar las directivas DLP, puede usar las sugerencias de directiva predeterminadas o [personalizar las sugerencias de directiva](#to-customize-policy-tips) para su organización.

Volviendo a nuestro ejemplo, donde un remitente compartió un número de seguro social en un canal de Teams, esto es lo que vio el destinatario:

> [!div class="mx-imgBorder"]
> ![Mensaje bloqueado.](../media/dlp-teams-blockedmessage-notification-to-user.png)

### <a name="to-customize-policy-tips"></a>Personalizar sugerencias de directiva

Para llevar a cabo esta tarea, debe tener asignado un rol de administración que tenga permisos para editar directivas DLP. Para obtener más información vea [Permisos](data-loss-prevention-policies.md#permissions).

1. Vaya al Centro de cumplimiento de Purview ([https://compliance.microsoft.com](https://compliance.microsoft.com)) e inicie sesión.

2. Haga clic en **Prevención de pérdida de datos** > **Directiva**.

3. Seleccione una directiva y, junto a **Configuración de directiva**, elija **Editar**.

4. Cree una nueva regla o edite una regla existente para la directiva.

5. En la pestaña **Notificaciones de usuario** , seleccione **Personalizar el texto del correo electrónico** o **Personalizar las opciones de texto de sugerencia de directiva** .

6. Especifique el texto que desea usar para las notificaciones por correo electrónico o las sugerencias de directiva y, a continuación, elija **Guardar**.

7. En la pestaña **Configuración de** directiva, elija **Guardar**.

Espere aproximadamente una hora para que los cambios funcionen a través del centro de datos y sincronicen con las cuentas de usuario.
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Agregar Microsoft Teams como una ubicación a las directivas DLP existentes

Para llevar a cabo esta tarea, debe tener asignado un rol de administración que tenga permisos para editar directivas DLP. Para obtener más información vea [Permisos](data-loss-prevention-policies.md#permissions).

1. Vaya al Centro de cumplimiento ([https://compliance.microsoft.com](https://compliance.microsoft.com)) e inicie sesión.

2. Haga clic en **Prevención de pérdida de datos** > **Directiva**.

3. Seleccione una directiva y examine los valores en **Ubicaciones**. Si ve **mensajes de chat y canal de Teams**, ya está listo. Si no lo hace, haga clic en **Editar**.

4. En la columna **Estado** , active la directiva para mensajes de **chat y canal de Teams**.

5. En la pestaña **Elegir ubicaciones** , mantenga la configuración predeterminada de todas las cuentas o seleccione **Permitirme elegir ubicaciones específicas**. Puede especificar lo siguiente:

    1. Hasta 1000 cuentas individuales para incluir o excluir
    1. Listas de distribución y grupos de seguridad que se van a incluir o excluir. 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. A continuación, elija **Siguiente**.

7. Haga clic en **Guardar**.

Espere aproximadamente una hora para que los cambios funcionen a través del centro de datos y sincronicen con las cuentas de usuario.
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Crear una directiva DLP con Microsoft Teams

Para llevar a cabo esta tarea, debe tener asignado un rol de administración que tenga permisos para editar directivas DLP. Para obtener más información vea [Permisos](data-loss-prevention-policies.md#permissions).

1. Vaya al Centro de cumplimiento ([https://compliance.microsoft.com](https://compliance.microsoft.com)) e inicie sesión.

2. Elija **Prevención de pérdida de datos** > **Directiva** > **+ Crear una directiva**.

3. Elija una [plantilla](data-loss-prevention-policies.md#dlp-policy-templates) y, a continuación, elija **Siguiente**.

    En nuestro ejemplo, elegimos la plantilla Datos de información de identificación personal de EE. UU.

4. En la pestaña **Nombre de la directiva** , especifique un nombre y una descripción para la directiva y, a continuación, elija **Siguiente**.

5. En la pestaña **Elegir ubicaciones** , mantenga la configuración predeterminada de todas las cuentas o seleccione **Permitirme elegir ubicaciones específicas**. Puede especificar lo siguiente:

    1. Hasta 1000 cuentas individuales para incluir o excluir
    1. Listas de distribución y grupos de seguridad que se van a incluir o excluir. **Se trata de una característica de versión preliminar pública.**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

 
    > [!NOTE]
    > Si desea asegurarse de que los documentos que contienen información confidencial no se comparten de forma inapropiada en Teams, asegúrese de que los **sitios de SharePoint** y **las cuentas de OneDrive** están activados, junto con **mensajes de chat y canales de Teams**.

6. En la pestaña **Configuración** de directiva, en **Personalizar el tipo de contenido que desea proteger**, mantenga la configuración simple predeterminada o elija **Usar configuración avanzada** y, a continuación, elija **Siguiente**. Si elige la configuración avanzada, puede crear o editar reglas para la directiva. Para obtener ayuda con esto, consulte [Configuración sencilla frente a configuración avanzada](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).

7.  En la pestaña **Configuración de** directiva, en **¿Qué desea hacer si detectamos información confidencial?**, revise la configuración. Aquí es donde puede elegir mantener [sugerencias de directiva predeterminadas y notificaciones por correo electrónico](use-notifications-and-policy-tips.md), o personalizarlas.



    Cuando haya terminado de revisar o editar la configuración, elija **Siguiente**.

8. En la pestaña **Configuración** de directiva, en **¿Desea activar primero la directiva o probar las cosas?**, elija si desea activarla, [probarla primero](dlp-overview-plan-for-dlp.md#policy-deployment) o mantenerla desactivada por ahora y, a continuación, elija **Siguiente**.

9. En la pestaña **Revisar la configuración** , revise la configuración de la nueva directiva. Elija **Editar** para realizar cambios. Cuando haya terminado, elija **Crear**.

Espere aproximadamente una hora para que la nueva directiva funcione a través del centro de datos y sincronice con las cuentas de usuario.

## <a name="prevent-external-access-to-sensitive-documents"></a>Evitar el acceso externo a documentos confidenciales

Para asegurarse de que los invitados externos no puedan acceder a los documentos de SharePoint que contienen información confidencial desde SharePoint o Teams de forma predeterminada, seleccione lo siguiente:

- Puede asegurarse de que los documentos están protegidos hasta que los exámenes DLP y los marca como seguros para compartir [marcando los nuevos archivos como confidenciales de forma predeterminada](/sharepoint/sensitive-by-default).

- Estructura recomendada de directiva DLP

    - **Condiciones**
        - El contenido contiene cualquiera de estos tipos de información confidencial: [Seleccionar todo lo que se aplica]
        
        - El contenido se comparte desde Microsoft 365 con personas ajenas a mi organización
        
          > [!div class="mx-imgBorder"]
          > ![Condiciones DLP para detectar el uso compartido externo de contenido confidencial.](../media/dlp-teams-external-sharing/external-condition.png)

    - **Acciones**
        - Restringir el acceso de usuarios externos al contenido
        
        - Notificar a los usuarios con sugerencias de directiva y correo electrónico
        
        - Enviar informes de incidentes al administrador
        
        > [!div class="mx-imgBorder"]
        > ![Acción DLP para bloquear el uso compartido externo de contenido confidencial.](../media/dlp-teams-external-sharing/external-action.png)

Directiva DLP en acción al intentar compartir un documento en SharePoint que contiene información confidencial con un invitado externo:

> [!div class="mx-imgBorder"]
> ![Uso compartido externo bloqueado.](../media/dlp-teams-external-sharing/external-sharing-blocked.png)

<!--DLP policy in action when guest attempts to open a document in Teams with block external:
can't use the below image it contains a non-approved name.
> [!div class="mx-imgBorder"]
> ![External access blocked.](../media/dlp-teams-external-sharing/external-access-blocked.png)-->

## <a name="related-articles"></a>Artículos relacionados

- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Enviar notificaciones de email y mostrar sugerencias para directivas DLP](use-notifications-and-policy-tips.md)
