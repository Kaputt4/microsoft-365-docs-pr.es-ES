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
> Las capacidades de prevención de pérdida de datos se agregaron recientemente Microsoft Teams mensajes de chat y canal para usuarios con licencia para Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance o Cumplimiento avanzado de Office 365. Office 365 y Microsoft 365 E3 protección DLP para SharePoint Online, OneDrive y Exchange Online. Esto también incluye archivos que se comparten a través de Teams porque Teams usa SharePoint Online y OneDrive para compartir archivos.
La compatibilidad con la protección DLP en Teams chat requiere E5.
Para obtener más información sobre los requisitos de licencias, consulte [Instrucciones de licencias de Microsoft 365 del nivel de espacio empresarial](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).

## <a name="overview-of-dlp-for-microsoft-teams"></a>Información general sobre las llamadas de Microsoft Teams

Recientemente, [las capacidades de](dlp-learn-about-dlp.md) prevención de pérdida de datos se ampliaron para incluir Microsoft Teams chat y mensajes de canal, **incluidos los mensajes de canal privado.** 

> [!IMPORTANT]
> DLP actualmente solo se aplica a los mensajes reales en el subproceso de chat o canal. Las notificaciones de actividad , que incluyen una vista previa de  mensaje breve y aparecen según la configuración de notificación de un usuario, no se incluyen en Teams DLP en este momento. Cualquier información confidencial presente en la parte del mensaje que aparece en la vista previa permanecerá visible en la notificación incluso después de que se haya aplicado la directiva DLP y se haya quitado la información confidencial del mensaje en sí.

Si su organización tiene DLP, ahora puede definir directivas que impidan que las personas compartan información confidencial en un canal Microsoft Teams sesión de chat. Estos son algunos ejemplos de cómo funciona esta protección:

- **Ejemplo 1: Protección de información confidencial en mensajes**. Supongamos que alguien intenta compartir información confidencial en un Teams chat o canal con invitados (usuarios externos). Si tiene una directiva DLP definida para evitarlo, se eliminan los mensajes con información confidencial que se envían a usuarios externos. Esto sucede automáticamente y en segundos, según cómo se configura la directiva DLP.

    > [!NOTE]
    > DLP para Microsoft Teams bloquea el contenido confidencial cuando se comparte con Microsoft Teams usuarios que tienen:<br/>- [acceso de invitado](/MicrosoftTeams/guest-access) en equipos y canales; o<br/>- [acceso externo en](/MicrosoftTeams/manage-external-access) reuniones y sesiones de chat. <p>DLP para sesiones de chat externas solo funcionará si el remitente y el receptor están en modo de solo Teams y usando Microsoft Teams [federación nativa](/microsoftteams/manage-external-access). DLP para Teams no bloquea los [](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) mensajes en interoperabilidad con Skype Empresarial o sesiones de chat federadas no nativas.

- **Ejemplo 2: Protección de información confidencial en documentos**. Supongamos que alguien intenta compartir un documento con invitados en un canal Microsoft Teams chat y que el documento contiene información confidencial. Si tiene una directiva DLP definida para evitarlo, el documento no se abrirá para esos usuarios. Tenga en cuenta que, en este caso, la directiva DLP debe incluir SharePoint y OneDrive para que la protección esté en su lugar. (Este es un ejemplo de DLP para SharePoint que se muestra en Microsoft Teams y, por lo tanto, requiere que los usuarios tienen licencia para dlp de Office 365 (incluido en Office 365 E3), pero no requiere que los usuarios tienen licencia para Cumplimiento avanzado de Office 365).

## <a name="policy-tips-help-educate-users"></a>Las sugerencias de directiva ayudan a educar a los usuarios

De forma similar a cómo funciona DLP en [Exchange, Outlook, Outlook](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)en la web, [SharePoint Online,](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)sitios de OneDrive para la Empresa y clientes de escritorio de [Office,](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)aparecen sugerencias de directiva cuando una acción entra en conflicto con una directiva DLP. Este es un ejemplo de una sugerencia de directiva:

![Notificación de mensaje bloqueado en Teams](../media/dlp-teams-blockedmessage-notification.png)

En este caso, el remitente intentó compartir un número de seguridad social en un canal Microsoft Teams. El **vínculo ¿Qué puedo hacer?** abre un cuadro de diálogo que proporciona opciones para que el remitente resuelva el problema. Tenga en cuenta que, en este caso, el remitente puede optar por invalidar la directiva o notificar a un administrador que la revise y resuelva.

![Opciones para resolver el mensaje bloqueado](../media/dlp-teams-blockedmessage-possibleactions.png)

En su organización, puede elegir permitir que los usuarios invalide una directiva DLP. Además, al configurar las directivas DLP, puede usar las sugerencias de directiva predeterminadas o personalizar las [sugerencias de directiva](#to-customize-policy-tips) para su organización.

Volviendo a nuestro ejemplo, donde un remitente compartió un número de seguridad social en un canal de Teams, esto es lo que vio el destinatario:

> [!div class="mx-imgBorder"]
> ![Mensaje bloqueado](../media/dlp-teams-blockedmessage-notification-to-user.png)

### <a name="to-customize-policy-tips"></a>Personalizar sugerencias de directiva

Para llevar a cabo esta tarea, debe tener asignado un rol de administración que tenga permisos para editar directivas DLP. Para obtener más información vea [Permisos](data-loss-prevention-policies.md#permissions).

1. Vaya al Centro de seguridad & cumplimiento ( [https://protection.office.com](https://protection.office.com) ) e inicie sesión.

2. Haga clic en **Prevención de pérdida de datos** > **Directiva**.

3. Seleccione una directiva y, junto a **Configuración de directiva,** elija **Editar**.

4. Cree una nueva regla o edite una regla existente para la directiva.

    > [!div class="mx-imgBorder"]
    > ![Edición de una regla para una directiva](../media/dlp-teams-editrule.png)

5. En la **pestaña Notificaciones de usuario,** seleccione **Personalizar el** texto del correo electrónico o Personalizar las opciones de texto de **sugerencia de** directiva.

    > [!div class="mx-imgBorder"]
    > ![Personalizar notificaciones de usuario y sugerencias de directivas](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. Especifique el texto que desea usar para notificaciones por correo electrónico o sugerencias de directiva y, a continuación, **elija Guardar**.

7. En la **pestaña Configuración de** directiva, elija **Guardar**.

Espere aproximadamente una hora para que los cambios funcionen en su centro de datos y se sincronicen con cuentas de usuario.
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Agregar Microsoft Teams como una ubicación a las directivas DLP existentes

Para llevar a cabo esta tarea, debe tener asignado un rol de administración que tenga permisos para editar directivas DLP. Para obtener más información vea [Permisos](data-loss-prevention-policies.md#permissions).

1. Vaya al Centro de seguridad & cumplimiento ( [https://protection.office.com](https://protection.office.com) ) e inicie sesión.

2. Haga clic en **Prevención de pérdida de datos** > **Directiva**.

3. Seleccione una directiva y vea los valores en **Ubicaciones**. Si ves **Teams chat y mensajes de canal,** estás todo configurado. Si no lo hace, haga clic en **Editar**.

    > [!div class="mx-imgBorder"]
    > ![Ubicaciones de la directiva existente](../media/dlp-teams-editexistingpolicy.png)

4. En la **columna Estado,** active la directiva para los **mensajes Teams chat y canal**.

    > [!div class="mx-imgBorder"]
    > ![DLP para Teams chats y canales](../media/dlp-teams-addteamschatschannels.png)

5. En la **pestaña Elegir ubicaciones,** mantenga la configuración predeterminada de todas las cuentas o seleccione **Permitirme elegir ubicaciones específicas.** Puede especificar lo siguiente:

    1. hasta 1000 cuentas individuales para incluir o excluir
    1. listas de distribución y grupos de seguridad para incluir o excluir. 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. A continuación, elija **Siguiente**.

7. Haga clic en **Guardar**.

Espere aproximadamente una hora para que los cambios funcionen en su centro de datos y se sincronicen con cuentas de usuario.
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Crear una directiva DLP con Microsoft Teams

Para llevar a cabo esta tarea, debe tener asignado un rol de administración que tenga permisos para editar directivas DLP. Para obtener más información vea [Permisos](data-loss-prevention-policies.md#permissions).

1. Vaya al Centro de seguridad & cumplimiento ( [https://protection.office.com](https://protection.office.com) ) e inicie sesión.

2. Elija **Prevención de pérdida de datos** > **Directiva** > **+ Crear una directiva**.

3. Elija una [plantilla](data-loss-prevention-policies.md#dlp-policy-templates)y, a continuación, **elija Siguiente**.

    En nuestro ejemplo, elegimos la plantilla Datos de información de identificación personal de Estados Unidos.

    > [!div class="mx-imgBorder"]
    > ![Plantilla de privacidad para la directiva DLP](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. En la **pestaña Nombre de la directiva,** especifique un nombre y una descripción para la directiva y, a continuación, elija **Siguiente**.

5. En la **pestaña Elegir ubicaciones,** mantenga la configuración predeterminada de todas las cuentas o seleccione **Permitirme elegir ubicaciones específicas.** Puede especificar lo siguiente:

    1. hasta 1000 cuentas individuales para incluir o excluir
    1. listas de distribución y grupos de seguridad para incluir o excluir. **Se trata de una característica de vista previa pública.**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![Ubicaciones de directivas DLP](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > Si desea asegurarse de que los documentos que contienen información confidencial no  se compartan de forma inadecuada en Teams, asegúrese de que SharePoint sitios y cuentas **de OneDrive** estén activados, junto con los mensajes de **chat** y canal Teams .

6. En la **pestaña Configuración de** directiva, en Personalizar el tipo de contenido que desea proteger, mantenga la configuración sencilla predeterminada o elija Usar configuración avanzada y, a continuación, elija **Siguiente**.   Si elige la configuración avanzada, puede crear o editar reglas para la directiva. (Para obtener ayuda con esto, vea [Configuración sencilla frente a configuración avanzada](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)).)

7.  En la **pestaña Configuración de** directiva, en ¿Qué desea hacer si detectamos información **confidencial?**, revise la configuración. (Aquí es donde puede elegir mantener las sugerencias de directiva [predeterminadas](use-notifications-and-policy-tips.md)y las notificaciones de correo electrónico, o personalizarlas).

    > [!div class="mx-imgBorder"]
    > ![Configuración de directiva DLP con sugerencias y notificaciones](../media/dlp-teams-policysettings-tipsemails.png)

    Cuando haya terminado de revisar o editar la configuración, elija **Siguiente**.

8. En la **pestaña** Configuración de directiva, en ¿Desea activar la directiva o probar primero **las cosas?**, elija si desea activar la [directiva,](dlp-overview-plan-for-dlp.md#policy-deployment)probarla primero o mantenerla desactivada por ahora y, a continuación, elija **Siguiente**.

    > [!div class="mx-imgBorder"]
    > ![Especificar si se debe activar la directiva](../media/dlp-teams-policysettings-turnonnow.png)

9. En la **pestaña Revisar la configuración,** revisa la configuración de la nueva directiva. Elija **Editar** para realizar cambios. Cuando haya terminado, elija **Crear**.

Espere aproximadamente una hora para que la nueva directiva funcione en su centro de datos y se sincronice con cuentas de usuario.

## <a name="prevent-external-access-to-sensitive-documents"></a>Evitar el acceso externo a documentos confidenciales

Para asegurarse de que SharePoint documentos que contienen información confidencial no puedan tener acceso los invitados externos desde SharePoint o Teams de forma predeterminada, seleccione lo siguiente:

- Puede asegurarse de que los documentos están protegidos hasta que DLP los examina y los marca como seguros para compartir marcando los nuevos archivos [como confidenciales de forma predeterminada.](/sharepoint/sensitive-by-default)

- Estructura recomendada de directiva DLP

    - **Condiciones**
        - El contenido contiene cualquiera de estos tipos de información confidencial: [Seleccionar todo lo que se aplica]
        
        - El contenido se comparte Microsoft 365 con personas de fuera de mi organización
        
          > [!div class="mx-imgBorder"]
          > ![Condiciones dlp para detectar el uso compartido externo de contenido confidencial](../media/dlp-teams-external-sharing/external-condition.png)

    - **Actions**
        - Restringir el acceso de usuarios externos al contenido
        
        - Notificar a los usuarios con sugerencias de directiva y correo electrónico
        
        - Enviar informes de incidentes al administrador
        
        > [!div class="mx-imgBorder"]
        > ![Acción DLP para bloquear el uso compartido externo de contenido confidencial](../media/dlp-teams-external-sharing/external-action.png)

Directiva DLP en acción al intentar compartir un documento en SharePoint que contiene información confidencial con un invitado externo:

> [!div class="mx-imgBorder"]
> ![Uso compartido externo bloqueado](../media/dlp-teams-external-sharing/external-sharing-blocked.png)


Directiva DLP en acción cuando el invitado intenta abrir un documento en Teams con bloqueo externo:

> [!div class="mx-imgBorder"]
> ![Acceso externo bloqueado](../media/dlp-teams-external-sharing/external-access-blocked.png)

## <a name="related-articles"></a>Artículos relacionados

[Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)

[Enviar notificaciones de email y mostrar sugerencias para directivas DLP](use-notifications-and-policy-tips.md)
