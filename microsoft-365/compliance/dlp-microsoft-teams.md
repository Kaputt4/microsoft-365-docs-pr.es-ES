---
title: Prevención de pérdida de datos y Microsoft Teams
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
description: Ahora puede aplicar directivas DLP a los chats y canales de Microsoft Teams. Lea este artículo para obtener más información sobre cómo funciona.
ms.openlocfilehash: a34a094a3c0440933a3d44e0125939a02b4ae202
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840587"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>Prevención de pérdida de datos y Microsoft Teams

> [!NOTE]
> Las capacidades de prevención de pérdida de datos se agregaron recientemente al chat y los mensajes de canal de Microsoft Teams para usuarios con licencia para Office 365 E5/A5, Microsoft 365 E5/A5, Protección y gobierno de la información de Microsoft 365 u Cumplimiento avanzado de Office 365. Office 365 y Microsoft 365 E3 incluyen protección DLP para SharePoint Online, OneDrive y Exchange Online. Esto también incluye los archivos que se comparten a través de Teams porque Teams usa SharePoint Online y OneDrive para compartir archivos.
La compatibilidad con la protección DLP en el chat de Teams requiere E5.
Para obtener más información sobre los requisitos de licencias, consulte [Instrucciones de licencias de Microsoft 365 del nivel de espacio empresarial](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).

> [!IMPORTANT]
> DLP para Teams solo se admite cuando el usuario tiene un buzón que está en Exchange Online

## <a name="overview-of-dlp-for-microsoft-teams"></a>Información general sobre DLP para Microsoft Teams

Recientemente, [las capacidades de](data-loss-prevention-policies.md) prevención de pérdida de datos (DLP) se ampliaron para incluir mensajes de canal y chat de Microsoft Teams, **incluidos los mensajes de canal privado.**


Si su organización tiene DLP, ahora puede definir directivas que impidan que los usuarios compartan información confidencial en un canal o sesión de chat de Microsoft Teams. Estos son algunos ejemplos de cómo funciona esta protección:

- **Ejemplo 1: Protección de información confidencial en mensajes**. Supongamos que alguien intenta compartir información confidencial en un chat o canal de Teams con invitados (usuarios externos). Si tiene una directiva DLP definida para evitarlo, se eliminarán los mensajes con información confidencial que se envían a usuarios externos. Esto sucede automáticamente y en segundos, de acuerdo con la configuración de la directiva DLP.

    > [!NOTE]
    > DLP para Microsoft Teams bloquea el contenido confidencial cuando se comparte con usuarios de Microsoft Teams que tienen:<br/>- [acceso de invitado](https://docs.microsoft.com/MicrosoftTeams/guest-access) en equipos y canales; o<br/>- [acceso externo en](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) reuniones y sesiones de chat. <p>DLP para sesiones de chat externo solo funcionará si tanto el remitente como el receptor están en modo de solo Teams y usan la federación [nativa de Microsoft Teams.](https://docs.microsoft.com/microsoftteams/manage-external-access) DLP para Teams no bloquea los mensajes en [interoperabilidad](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) con Skype Empresarial o sesiones de chat federadas no nativas.

- **Ejemplo 2: Protección de información confidencial en documentos**. Supongamos que alguien intenta compartir un documento con invitados en un canal o chat de Microsoft Teams, y el documento contiene información confidencial. Si tiene una directiva DLP definida para evitarlo, el documento no se abrirá para esos usuarios. Tenga en cuenta que en este caso, la directiva DLP debe incluir SharePoint y OneDrive para que la protección esté en su lugar. (Este es un ejemplo de DLP para SharePoint que se muestra en Microsoft Teams y, por lo tanto, requiere que los usuarios tienen licencia para DLP de Office 365 (incluido en Office 365 E3), pero no requiere que los usuarios estén autorizados para el Cumplimiento avanzado de Office 365).

## <a name="policy-tips-help-educate-users"></a>Las sugerencias de directiva ayudan a formar a los usuarios

De forma similar a cómo funciona DLP en [Exchange, Outlook, Outlook en la Web,](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web) [SharePoint Online,](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)sitios de OneDrive para la Empresa y clientes de escritorio de [Office,](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)las sugerencias de directiva aparecen cuando una acción entra en conflicto con una directiva DLP. Este es un ejemplo de una sugerencia de directiva:

![Notificación de mensajes bloqueados en Teams](../media/dlp-teams-blockedmessage-notification.png)

En este caso, el remitente intentó compartir un número de la seguridad social en un canal de Microsoft Teams. El **vínculo ¿Qué puedo hacer?** abre un cuadro de diálogo que proporciona opciones para que el remitente resuelva el problema. Tenga en cuenta que, en este caso, el remitente puede optar por invalidar la directiva o notificar a un administrador que la revise y resuelva.

![Opciones para resolver mensajes bloqueados](../media/dlp-teams-blockedmessage-possibleactions.png)

En su organización, puede elegir permitir a los usuarios invalidar una directiva DLP. Además, al configurar las directivas DLP, puede usar las sugerencias de directiva predeterminadas o personalizar las sugerencias de [directiva](#to-customize-policy-tips) para su organización.

Volviendo a nuestro ejemplo, donde un remitente compartió un número de la seguridad social en un canal de Teams, esto es lo que vio el destinatario:

![Mensaje bloqueado](../media/dlp-teams-blockedmessage-notification-to-user.png)

El **vínculo ¿Qué es esto?** abre un [artículo](data-loss-prevention-policies.md) sobre las directivas DLP, que ayuda a explicar por qué se bloqueó el mensaje.

### <a name="to-customize-policy-tips"></a>Para personalizar las sugerencias de directiva

Para realizar esta tarea, debe tener asignado un rol que tenga permisos para editar directivas DLP. Para obtener más información vea [Permisos](data-loss-prevention-policies.md#permissions).

1. Vaya al Centro de seguridad & cumplimiento ( [https://protection.office.com](https://protection.office.com) ) e inicie sesión.

2. Elija **Directiva de prevención de pérdida de**  >  **datos.**

3. Seleccione una directiva y, junto a **Configuración de directiva,** elija **Editar**.

4. Cree una regla nueva o edite una regla existente para la directiva.<br/>![Edición de una regla para una directiva](../media/dlp-teams-editrule.png)<br/>

5. En la **pestaña Notificaciones de** usuario, seleccione Personalizar **el** texto del correo electrónico o Personalizar las opciones de texto de **sugerencia de** directiva.<br/>![Personalizar las notificaciones de usuario y las sugerencias de directiva](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. Especifique el texto que desea usar para notificaciones por correo electrónico o sugerencias de directiva y, a continuación, elija **Guardar**.

7. En la **pestaña Configuración de** directiva, elija **Guardar**.

Espere aproximadamente una hora para que los cambios funcionen en el centro de datos y se sincronicen con las cuentas de usuario.
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Agregar Microsoft Teams como ubicación a las directivas DLP existentes

Para realizar esta tarea, debe tener asignado un rol que tenga permisos para editar directivas DLP. Para obtener más información vea [Permisos](data-loss-prevention-policies.md#permissions).

1. Vaya al Centro de seguridad & cumplimiento ( [https://protection.office.com](https://protection.office.com) ) e inicie sesión.

2. Elija **Directiva de prevención de pérdida de**  >  **datos.**

3. Seleccione una directiva y busque los valores en **Ubicaciones**. Si ve mensajes **de canal y chat de Teams,** está todo configurado. Si no lo hace, haga clic en **Editar**.<br/>![Ubicaciones de la directiva existente](../media/dlp-teams-editexistingpolicy.png)<br/>

4. En la **columna Estado,** active la directiva para los mensajes **de canal y chat de Teams.**<br/>![DLP para chats y canales de Teams](../media/dlp-teams-addteamschatschannels.png)<br/>

5. En la **pestaña Elegir ubicaciones,** mantenga la configuración  predeterminada de todas las cuentas o seleccione Permitir que elija ubicaciones específicas y especifique qué cuentas incluir o excluir. A continuación, elija **Siguiente**.

6. Haga clic en **Guardar**.

Espere aproximadamente una hora para que los cambios funcionen en el centro de datos y se sincronicen con las cuentas de usuario.
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Definir una nueva directiva DLP para Microsoft Teams

Para realizar esta tarea, debe tener asignado un rol que tenga permisos para editar directivas DLP. Para obtener más información vea [Permisos](data-loss-prevention-policies.md#permissions).

1. Vaya al Centro de seguridad & cumplimiento ( [https://protection.office.com](https://protection.office.com) ) e inicie sesión.

2. Elija **Directiva de prevención de pérdida de**  >  **datos**+ Crear una  >  **directiva.**

3. Elija una [plantilla](data-loss-prevention-policies.md#dlp-policy-templates)y, a continuación, **elija Siguiente**.<br/>En nuestro ejemplo, elegimos la plantilla de datos de información de identificación personal de Estados Unidos.<br/>![Plantilla de privacidad para la directiva DLP](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. En la **pestaña Nombre de la** directiva, especifique un nombre y una descripción para la directiva y, a continuación, elija **Siguiente**.

5. En la **pestaña Elegir ubicaciones,** mantenga la configuración  predeterminada de todas las cuentas o seleccione Permitir que elija ubicaciones específicas y especifique qué cuentas incluir o excluir. A continuación, elija **Siguiente**.

![Ubicaciones de directivas DLP](../media/dlp-teams-selectlocationsnewpolicy.png)

> [!NOTE]
> Si desea asegurarse de que los documentos que contienen información confidencial no se comparten de forma inadecuada en Teams, asegúrese de que los sitios de **SharePoint** y las cuentas de **OneDrive** están activados, junto con los mensajes de canal y chat de **Teams.**


6. En la pestaña **Configuración de** directiva, en Personalizar el tipo de contenido que desea **proteger,** mantenga la configuración sencilla predeterminada o elija Usar configuración avanzada y, a continuación, elija **Siguiente**. Si elige la configuración avanzada, puede crear o editar reglas para la directiva. (Para obtener ayuda con esto, vea [Configuración simple frente a configuración avanzada).](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)

7.  En la **pestaña Configuración de** directiva, en ¿Qué desea hacer si se detecta información **confidencial?**, revise la configuración. (Aquí es donde puede elegir mantener las sugerencias de directiva [predeterminadas](use-notifications-and-policy-tips.md)y las notificaciones por correo electrónico, o personalizarlas).<br/>![Configuración de directiva DLP con sugerencias y notificaciones](../media/dlp-teams-policysettings-tipsemails.png)<br/>Cuando haya terminado de revisar o editar la configuración, elija **Siguiente**.

8. En  la pestaña Configuración de directiva, en ¿Desea activar la directiva o probar las cosas **primero?**, elija si desea activar la [directiva,](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)probarla primero o mantenerla desactivada por ahora y, a continuación, elija Siguiente **.**<br/>![Especificar si se debe activar la directiva](../media/dlp-teams-policysettings-turnonnow.png)<br/>

9. En la **pestaña Revisar la configuración,** revisa la configuración de la nueva directiva. Elija **Editar para** realizar cambios. Cuando haya terminado, elija **Crear**.

Espere aproximadamente una hora para que la nueva directiva funcione en su centro de datos y se sincronice con las cuentas de usuario.

## <a name="prevent-external-access-to-sensitive-documents"></a>Impedir el acceso externo a documentos confidenciales

Para asegurarse de que los invitados externos no puedan tener acceso de forma predeterminada a los documentos de SharePoint que contienen información confidencial desde SharePoint o Teams, seleccione lo siguiente:

- Puede asegurarse de que los documentos están protegidos hasta que DLP los examina y los marca como seguros para compartir marcando los archivos nuevos como confidenciales [de forma predeterminada.](https://docs.microsoft.com/sharepoint/sensitive-by-default)
- Estructura de directiva DLP recomendada
    - **Condiciones**
        - El contenido contiene cualquiera de estos tipos de información confidencial: [Seleccionar todo lo que se aplica]
        - El contenido se comparte desde Microsoft 365 con personas de fuera de mi organización
        <br/>![Condiciones dlp para detectar el uso compartido externo de contenido confidencial](../media/dlp-teams-external-sharing/external-condition.png)<br/>


    - **Acciones**
        - Restringir el acceso al contenido para usuarios externos
        - Notificar a los usuarios con sugerencias de directivas y correo electrónico
        - Enviar informes de incidentes al administrador    
        <br/>![Acción DLP para bloquear el uso compartido externo de contenido confidencial](../media/dlp-teams-external-sharing/external-action.png)<br/>

Directiva DLP en acción al intentar compartir un documento en SharePoint que contiene información confidencial con un invitado externo:
<br/>![Uso compartido externo bloqueado](../media/dlp-teams-external-sharing/external-sharing-blocked.png)<br/>


Directiva DLP en acción cuando el invitado intenta abrir un documento en Teams con bloqueo externo:
<br/>![Acceso externo bloqueado](../media/dlp-teams-external-sharing/external-access-blocked.png)<br/>

## <a name="related-articles"></a>Artículos relacionados

[Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)

[Enviar notificaciones de email y mostrar sugerencias para directivas DLP](use-notifications-and-policy-tips.md)
