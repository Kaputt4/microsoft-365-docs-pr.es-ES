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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Ahora puede aplicar directivas DLP a Microsoft Teams chats y canales. Lea este artículo para obtener más información sobre cómo funciona.
ms.openlocfilehash: 9fdce86473dcfbb7ec75b9d371b8782d4141ef57
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572470"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>Prevención de pérdida de datos y Microsoft Teams.

> [!NOTE]
> Recientemente se agregaron capacidades de prevención de pérdida de datos a Microsoft Teams mensajes de chat y canal para usuarios con licencia para Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Protección de la Información y Gobernanza o Cumplimiento avanzado de Office 365. Office 365 y Microsoft 365 E3 incluyen protección DLP para SharePoint en línea, OneDrive y Exchange Online. Esto también incluye archivos que se comparten a través de Teams porque Teams utiliza SharePoint en línea y OneDrive para compartir archivos.
La compatibilidad con la protección DLP en Teams Chat requiere E5.
Para obtener más información sobre los requisitos de licencias, consulte [Instrucciones de licencias de Microsoft 365 del nivel de espacio empresarial](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).

## <a name="overview-of-dlp-for-microsoft-teams"></a>Información general sobre las llamadas de Microsoft Teams

Recientemente, las capacidades de [prevención de pérdida de datos](dlp-learn-about-dlp.md) se ampliaron para incluir Microsoft Teams mensajes de chat y canal, incluidos los mensajes de canal **privado.** 

> [!IMPORTANT]
> DLP se aplica actualmente solo a los mensajes reales en el hilo de chat o canal. Las notificaciones de actividad , que incluyen una vista previa de mensajes corta y aparecen en función de la configuración de notificación de un usuario , **no** se incluyen en Teams DLP en este momento. Cualquier información confidencial presente en la parte del mensaje que aparece en la vista previa permanecerá visible en la notificación incluso después de que se haya aplicado la directiva DLP y se haya quitado la información confidencial del propio mensaje.

Si su organización tiene DLP, ahora puede definir directivas que impidan a las personas compartir información confidencial en una sesión de canal o chat Microsoft Teams. Estos son algunos ejemplos de cómo funciona esta protección:

- **Ejemplo 1: Protección de información confidencial en mensajes**. Supongamos que alguien intenta compartir información confidencial en un chat o canal Teams con invitados (usuarios externos). Si tiene una directiva DLP definida para evitarlo, se eliminan los mensajes con información confidencial que se envían a usuarios externos. Esto sucede automáticamente, y en cuestión de segundos, de acuerdo con cómo se configura la directiva DLP.

    > [!NOTE]
    > DLP para Microsoft Teams bloquea el contenido confidencial cuando se comparte con usuarios de Microsoft Teams que tienen:<br/>- [acceso de invitados](/MicrosoftTeams/guest-access) en equipos y canales; o<br/>- [acceso externo](/MicrosoftTeams/manage-external-access) en reuniones y sesiones de chat. <p>DLP para sesiones de chat externas solo funcionará si tanto el remitente como el receptor están en modo solo Teams y utilizando [Microsoft Teams federación nativa.](/microsoftteams/manage-external-access) DLP para Teams no bloquea los mensajes en [interoperabilidad](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) con sesiones de chat federadas Skype Empresarial o no nativas.

- **Ejemplo 2: Protección de información confidencial en documentos**. Supongamos que alguien intenta compartir un documento con invitados en un canal o chat Microsoft Teams, y el documento contiene información confidencial. Si tiene una directiva DLP definida para evitar esto, el documento no se abrirá para esos usuarios. Tenga en cuenta que, en este caso, la directiva DLP debe incluir SharePoint y OneDrive para que la protección esté en su lugar. (Este es un ejemplo de DLP para SharePoint que aparece en Microsoft Teams y, por lo tanto, requiere que los usuarios tengan licencia para Office 365 DLP (incluido en Office 365 E3), pero no requiere que los usuarios tengan licencia para Cumplimiento avanzado de Office 365.)

## <a name="policy-tips-help-educate-users"></a>Consejos de políticas ayudan a educar a los usuarios

De forma similar a cómo funciona DLP en [Exchange, Outlook, Outlook en la web,](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web) [SharePoint en línea, sitios de OneDrive para la Empresa](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)y clientes de escritorio [Office,](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)las sugerencias de directivas aparecen cuando una acción entra en conflicto con una directiva DLP. Este es un ejemplo de un consejo de política:

![Notificación de mensaje bloqueado en Teams](../media/dlp-teams-blockedmessage-notification.png)

En este caso, el remitente intentó compartir un número de seguro social en un canal Microsoft Teams. El vínculo **¿Qué puedo hacer?** abre un cuadro de diálogo que proporciona opciones para que el remitente resuelva el problema. Tenga en cuenta que, en este caso, el remitente puede optar por invalidar la directiva o notificar a un administrador que la revise y resuelva.

![Opciones para resolver el mensaje bloqueado](../media/dlp-teams-blockedmessage-possibleactions.png)

En su organización, puede elegir permitir que los usuarios invaliden una directiva DLP. Además, al configurar las directivas DLP, puede usar las sugerencias de directiva predeterminadas o [personalizar sugerencias de directiva](#to-customize-policy-tips) para su organización.

Volviendo a nuestro ejemplo, donde un remitente compartió un número de seguro social en un canal de Teams, esto es lo que vio el destinatario:

> [!div class="mx-imgBorder"]
> ![Mensaje bloqueado](../media/dlp-teams-blockedmessage-notification-to-user.png)

### <a name="to-customize-policy-tips"></a>Personalizar sugerencias de directiva

Para llevar a cabo esta tarea, debe tener asignado un rol de administración que tenga permisos para editar directivas DLP. Para obtener más información vea [Permisos](data-loss-prevention-policies.md#permissions).

1. Vaya al Centro de cumplimiento de & de seguridad ( [https://protection.office.com](https://protection.office.com) ) e inicie sesión.

2. Haga clic en **Prevención de pérdida de datos** > **Directiva**.

3. Seleccione una directiva y, junto a **Configuración de directiva,** elija **Editar**.

4. Cree una nueva regla o edite una regla existente para la directiva.

    > [!div class="mx-imgBorder"]
    > ![Edición de una regla para una directiva](../media/dlp-teams-editrule.png)

5. En la pestaña **Notificaciones de usuario,** seleccione **Personalizar el texto del correo electrónico** o Personalizar las opciones de texto de sugerencia de **directiva.**

    > [!div class="mx-imgBorder"]
    > ![Personalizar las notificaciones de usuario y consejos de políticas](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. Especifique el texto que desea usar para notificaciones por correo electrónico y/o sugerencias de directiva y, a continuación, elija **Guardar**.

7. En la pestaña **Configuración de directiva,** elija **Guardar**.

Espere aproximadamente una hora para que los cambios se abren paso a través de su centro de datos y sincronicen con las cuentas de usuario.
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Agregar Microsoft Teams como una ubicación a las directivas DLP existentes

Para llevar a cabo esta tarea, debe tener asignado un rol de administración que tenga permisos para editar directivas DLP. Para obtener más información vea [Permisos](data-loss-prevention-policies.md#permissions).

1. Vaya al Centro de cumplimiento de & de seguridad ( [https://protection.office.com](https://protection.office.com) ) e inicie sesión.

2. Haga clic en **Prevención de pérdida de datos** > **Directiva**.

3. Seleccione una directiva y examine los valores en **Ubicaciones**. Si ves **Teams mensajes de chat y canal,** estás listo. Si no lo hace, haga clic en **Editar**.

    > [!div class="mx-imgBorder"]
    > ![Ubicaciones para la política existente](../media/dlp-teams-editexistingpolicy.png)

4. En la columna **Estado,** active la directiva para **Teams mensajes de chat y canal.**

    > [!div class="mx-imgBorder"]
    > ![DLP para chats y canales de Teams](../media/dlp-teams-addteamschatschannels.png)

5. En la pestaña **Elegir ubicaciones,** mantenga la configuración predeterminada de todas las cuentas o seleccione **Déjame elegir ubicaciones específicas.** Puede especificar lo siguiente:

    1. hasta 1000 cuentas individuales para incluir o excluir
    1. listas de distribución y grupos de seguridad para incluir o excluir. 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. A continuación, elija **Siguiente**.

7. Haga clic en **Guardar**.

Espere aproximadamente una hora para que los cambios se abren paso a través de su centro de datos y sincronicen con las cuentas de usuario.
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Crear una directiva DLP con Microsoft Teams

Para llevar a cabo esta tarea, debe tener asignado un rol de administración que tenga permisos para editar directivas DLP. Para obtener más información vea [Permisos](data-loss-prevention-policies.md#permissions).

1. Vaya al Centro de cumplimiento de & de seguridad ( [https://protection.office.com](https://protection.office.com) ) e inicie sesión.

2. Elija **Prevención de pérdida de datos** > **Directiva** > **+ Crear una directiva**.

3. Elija una [plantilla](data-loss-prevention-policies.md#dlp-policy-templates)y, a continuación, elija **Next**.

    En nuestro ejemplo, elegimos la plantilla datos de información de identificación personal de EE. UU.

    > [!div class="mx-imgBorder"]
    > ![Plantilla de privacidad para la política de DLP](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. En la pestaña **Nombre de la directiva,** especifique un nombre y una descripción para la directiva y, a continuación, elija **Siguiente**.

5. En la pestaña **Elegir ubicaciones,** mantenga la configuración predeterminada de todas las cuentas o seleccione **Déjame elegir ubicaciones específicas.** Puede especificar lo siguiente:

    1. hasta 1000 cuentas individuales para incluir o excluir
    1. listas de distribución y grupos de seguridad para incluir o excluir. **Esta es una función de vista previa pública.**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![Ubicaciones de directivas de DLP](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > Si desea asegurarse de que los documentos que contienen información confidencial no se compartan de forma inapropiada en Teams, asegúrese de que **SharePoint sitios** y cuentas **de OneDrive** estén activados, junto con Teams mensajes de chat **y canal.**

6. En la pestaña **Configuración de directiva,** en **Personalizar el tipo de contenido que desea proteger,** mantenga la configuración simple predeterminada o elija **Usar configuración avanzada** y, a continuación, elija **Siguiente**. Si elige la configuración avanzada, puede crear o editar reglas para su directiva. (Para obtener ayuda con esto, consulte [Configuración simple frente a configuración avanzada](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)

7.  En la pestaña **Configuración de directiva,** en **¿Qué desea hacer si detectamos información confidencial?**, revise la configuración. (Aquí es donde puede elegir mantener los consejos de [política predeterminados y las notificaciones por correo electrónico,](use-notifications-and-policy-tips.md)o personalizarlos.)

    > [!div class="mx-imgBorder"]
    > ![Configuración de directivas de DLP con sugerencias y notificaciones](../media/dlp-teams-policysettings-tipsemails.png)

    Cuando haya terminado de revisar o editar la configuración, elija **Siguiente**.

8. En la pestaña **Configuración de directiva,** en **¿Desea activar primero la directiva o probar las cosas?**, elija si desea activar la directiva, [probarla primero](dlp-overview-plan-for-dlp.md#policy-deployment)o mantenerla desactivada por ahora y, a continuación, elija **Siguiente**.

    > [!div class="mx-imgBorder"]
    > ![Especifique si desea activar la directiva](../media/dlp-teams-policysettings-turnonnow.png)

9. En la pestaña **Revisar la configuración,** revise la configuración de la nueva directiva. Elija **Editar** para realizar cambios. Cuando haya terminado, elija **Create**.

Espere aproximadamente una hora para que la nueva directiva funcione a través de su centro de datos y sincronice con las cuentas de usuario.

## <a name="prevent-external-access-to-sensitive-documents"></a>Evitar el acceso externo a documentos confidenciales

Para asegurarse de que los huéspedes externos no pueden acceder a los documentos SharePoint que contienen información confidencial, ya sea desde SharePoint o Teams de forma predeterminada, seleccione lo siguiente:

- Puede asegurarse de que los documentos están protegidos hasta que DLP los es examina y los marca como seguros para compartir [marcando los nuevos archivos como confidenciales de forma predeterminada.](/sharepoint/sensitive-by-default)

- Estructura recomendada de directiva DLP

    - **Condiciones**
        - El contenido contiene cualquiera de estos tipos de información confidencial: [Seleccionar todo lo que se aplica]
        
        - El contenido se comparte desde Microsoft 365 con personas ajenas a mi organización
        
          > [!div class="mx-imgBorder"]
          > ![Condiciones DLP para detectar el uso compartido externo de contenido confidencial](../media/dlp-teams-external-sharing/external-condition.png)

    - **Actions**
        - Restringir el acceso de usuarios externos al contenido
        
        - Notificar a los usuarios con sugerencias de directiva y correo electrónico
        
        - Enviar informes de incidentes al administrador
        
        > [!div class="mx-imgBorder"]
        > ![Acción DLP para bloquear el uso compartido externo de contenido confidencial](../media/dlp-teams-external-sharing/external-action.png)

Directiva DLP en acción al intentar compartir un documento en SharePoint que contiene información confidencial con un invitado externo:

> [!div class="mx-imgBorder"]
> ![Reparto externo bloqueado](../media/dlp-teams-external-sharing/external-sharing-blocked.png)


Directiva DLP en acción cuando el invitado intenta abrir un documento en Teams con bloque externo:

> [!div class="mx-imgBorder"]
> ![Acceso externo bloqueado](../media/dlp-teams-external-sharing/external-access-blocked.png)

## <a name="related-articles"></a>Artículos relacionados

[Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)

[Enviar notificaciones de email y mostrar sugerencias para directivas DLP](use-notifications-and-policy-tips.md)
