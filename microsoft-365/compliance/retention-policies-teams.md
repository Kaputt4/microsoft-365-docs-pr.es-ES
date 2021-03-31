---
title: Más información sobre la retención para Teams
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Más información sobre las directivas de retención que se aplican a Microsoft Teams.
ms.openlocfilehash: cc17f89da743afce0d64b45f96493c050e61e343
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408365"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>Más información sobre la retención para Microsoft Teams

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Si ve un mensaje en Teams que indica que los chats y los mensajes se han eliminado debido a una directiva de retención, vea [Mensajes de Teams sobre directivas de retención](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).
> 
> La información de esta página es para los administradores de TI que gestionan estas directivas de retención.

La información de este artículo complementa [Obtenga más información sobre la retención](retention.md) porque tiene información específica para los mensajes de Microsoft Teams.

Para otras cargas de trabajo, vea:

- [Obtenga más información sobre la retención de SharePoint y OneDrive](retention-policies-sharepoint.md)
- [Más información sobre la retención para Yammer](retention-policies-yammer.md)
- [Más información sobre las directivas de retención de Exchange](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>Qué se incluye para la retención y eliminación

Los mensajes de chat y de canal de Teams se pueden eliminar mediante directivas de retención para Teams y, además del texto de los mensajes, se pueden conservar los elementos siguientes por motivos de cumplimiento: imágenes incrustadas, tablas, vínculos de hipertexto, vínculos a otros mensajes y archivos de Teams y [contenido de tarjetas](/microsoftteams/platform/task-modules-and-cards/what-are-cards). Los mensajes de chat incluyen todos los nombres de los usuarios en el chat y los mensajes de canal incluyen el nombre del equipo y el título del mensaje (si se proporcionó). 

> [!NOTE]
> Incluir contenido de tarjetas es una adición reciente y ahora se ha lanzado completamente a los inquilinos. Para obtener más información, consulte las [funcionalidades de cumplimiento de Microsoft 365 para contenido de tarjetas adaptables en las aplicaciones de Teams que están disponibles ahora](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869).

Los mensajes de Teams en canales privados no son compatibles actualmente con las directivas de retención. Los fragmentos de código, notas de voz grabadas del cliente móvil de Teams, las miniaturas, las imágenes de anuncios y las reacciones de otros usuarios en forma de emoticonos no se conservan cuando usa las directivas de retención para Teams.

Los mensajes de correo electrónico y los archivos que use con Teams no son incluidos en directivas de retención para Teams. Estos elementos tienen sus propias directivas de retención.

## <a name="how-retention-works-with-microsoft-teams"></a>Cómo funciona la retención con Microsoft Teams

Puede usar una directiva de retención para conservar los datos de mensajes de canal y chats en Teams, y eliminar esos chats y mensajes. En segundo plano, se usan buzones de Exchange para almacenar datos de estos mensajes. Los datos de los chats de Teams se almacenan en una carpeta oculta en el buzón de cada usuario incluido en el chat y se usa una carpeta oculta similar en un buzón de grupo para los mensajes del canal de Teams.

Estos buzones se muestran según su atributo RecipientTypeDetails:

- **MailUser**: estos buzones almacenan datos de mensajes para los usuarios de Teams basados en la nube.
- **UserMailbox**: estos buzones almacenan datos de mensajes para los [usuarios locales de Teams](search-cloud-based-mailboxes-for-on-premises-users.md).
- **GroupMailbox**: estos buzones almacenan datos de mensajes para los canales de Teams.

Otros tipos de buzones, como RoomMailbox —que se usa en las salas de conferencias de Teams— no son compatibles con las directivas de retención de Teams.

Es importante comprender que Teams usa un servicio de chat con tecnología de Azure como almacenamiento principal para todos los mensajes (mensajes de chats y de canal) y, de forma predeterminada, este servicio almacena los datos de forma indefinida. Por este motivo, si necesita eliminar mensajes de Teams por motivos de cumplimiento, le recomendamos que use directivas de retención para Teams que puedan eliminar mensajes después de un período específico, en función de cuándo se crearon. Después, los mensajes se eliminan permanentemente de los buzones de Exchange y del servicio de chat subyacente con tecnología de Azure. Para más información sobre la arquitectura subyacente, consulte[Seguridad y cumplimiento en Microsoft Teams](/MicrosoftTeams/security-compliance-overview) y, específicamente, la sección [Arquitectura de protección de la información](/MicrosoftTeams/security-compliance-overview#information-protection-architecture).

Aunque los datos de los mensajes de canales y chats de Teams se almacenan en los buzones de correo, estos datos se incluyen solo por una directiva de retención que está configurada para las ubicaciones de los **mensajes de canal de Teams** y **chats de Teams**. Los chats de Teams y los mensajes de los canales no se ven afectados por las directivas de retención que se configuran para los buzones de los usuarios o grupos de Exchange.

> [!NOTE]
> Si un usuario está incluido en una directiva de retención activa que retiene los mensajes de Teams y elimina el buzón de un usuario incluido en esta directiva, para retener los datos de Teams, el buzón se convierte en un [buzón inactivo](inactive-mailboxes-in-office-365.md). Si no necesita retener los datos de Teams para el usuario, excluye la cuenta del usuario de la directiva de retención antes de eliminar su buzón.

Una vez que se configura una directiva de retención para los mensajes del chat y de los canales, un trabajo de temporizador del servicio de Exchange evalúa de manera periódica los elementos de la carpeta oculta en la que se almacenan estos mensajes de Teams. El trabajo de temporizador tarda hasta siete días en ejecutarse. Cuando el período de retención de estos elementos caduca, se trasladan a la carpeta SubstrateHolds, otra carpeta oculta ubicada en cada buzón de usuario o grupo para almacenar los elementos "eliminados temporalmente" antes de que se eliminen de forma permanente.

Una vez que se configura una directiva de retención para los mensajes del chat y de los canales, las rutas que seguirá el contenido dependerán de si la directiva de retención se configura para retener y luego eliminar, solo retener, o solo eliminar.

Cuando la directiva de retención es retener y luego eliminar:

![Diagrama de flujo de retención para los mensajes del chat y de los canales de Teams](../media/teamsretentionlifecycle.png)

Para las dos rutas en el diagrama:

1. Si el usuario **edita o elimina un mensaje del chat o canal** durante el período de retención, el mensaje original se copia (si se edita) o se traslada (si se elimina) a la carpeta SubstrateHolds en un plazo de 21 días. El mensaje se almacena hasta que finaliza el período de retención y, luego, se elimina de forma permanente en 24 horas.

2. **Si no se elimina un mensaje del chat o de los canales**, o, en el caso de los mensajes actuales, después de editarlo, el mensaje se traslada a la carpeta SubstrateHolds después de que el período de retención caduca. Esta acción tarda hasta 7 días después de la fecha de expiración. El mensaje se elimina de forma permanente durante las 24 horas siguientes después de que se traslada a la carpeta SubstrateHolds. 

> [!NOTE]
> Los mensajes de la carpeta SubstrateHolds se pueden buscar con las herramientas de eDiscovery. Hasta que los mensajes se eliminen permanentemente de esta carpeta SubstrateHolds, las herramientas de eDiscovery pueden buscarlos.

Cuando la directiva de retención es de solo retención, o solo eliminación, las rutas de acceso de contenido son variaciones de retener y eliminar.

### <a name="content-paths-for-retain-only-retention-policy"></a>Rutas de contenido para la directiva de retención de solo retención

1. **Si se edita o elimina un mensaje del chat o canal**: se crea una copia del mensaje original en la carpeta SubstrateHolds en un plazo de 21 días y se retiene ahí hasta que caduque el periodo de retención. Luego, el mensaje se elimina de forma permanente de la carpeta SubstrateHolds en 24 horas.

2. **Si el elemento no se modifica o elimina**, o, en el caso de los mensajes actuales, después de su edición, durante el período de retención: no sucede nada antes ni después del período de retención. El mensaje permanece en su ubicación original.

### <a name="content-paths-for-delete-only-retention-policy"></a>Rutas de contenido para la directiva de retención de sólo eliminar

1. **Si el mensaje no se elimina** durante el período de retención: al final del período de retención, el mensaje se mueve a la carpeta SubstrateHolds. Esta acción tarda hasta siete días después de la fecha de expiración. Luego, el mensaje se elimina de forma permanente de la carpeta SubstrateHolds en 24 horas.

2. **Si el usuario elimina el elemento** durante el período, el elemento se mueve a la carpeta SubstrateHolds en un plazo de 21 días, donde se eliminará de forma permanente después de 24 horas.


## <a name="skype-for-business-and-teams-interop-chats"></a>Chat de Skype Empresarial e interoperabilidad de Teams

Cuando una conversación de Skype Empresarial llega a Teams, se convierte en un mensaje en un hilo de conversación de Teams y se ingiere en el buzón correspondiente. Las directivas de retención de Teams se aplicarán a estos mensajes del hilo de Teams. 

Sin embargo, si se activa el historial de conversaciones en Skype Empresarial y desde el lado del cliente de Skype Empresarial ese historial se guarda en un buzón de correo, los datos de las conversaciones no se manejan mediante una directiva de retención de Teams. Para este contenido, use una directiva de retención configurada para Skype Empresarial.

## <a name="meetings-and-external-users"></a>Reuniones y usuarios externos

Los mensajes de reunión del canal se almacenan de la misma manera que los mensajes del canal, así que para estos datos, seleccione la ubicación de los **mensajes del canal de Teams** cuando configure su directiva de retención.

Los mensajes de reuniones improvisadas y programadas se almacenan de la misma manera que los mensajes de chat del grupo, por lo que para estos datos, seleccione la ubicación de los **chats de Teams** cuando configure su directiva de retención.

Cuando se incluyen usuarios externos en una reunión que su organización organiza:

- Si un usuario externo se une utilizando una cuenta de invitado en su inquilino, este usuario tiene un buzón de correo en la sombra que puede estar sujeto a la directiva de retención de su organización para Teams. Los mensajes de la reunión se almacenan tanto en el correo de sus usuarios como en el correo paralelo. 

- Si un usuario externo se une mediante el uso de una cuenta de otra organización de Microsoft 365, sus directivas de retención no pueden eliminar los mensajes de este usuario porque están almacenados en el buzón de ese usuario en otro arrendatario. Sin embargo, para la misma reunión, sus directivas de retención pueden eliminar los mensajes de sus usuarios.

## <a name="when-a-user-leaves-the-organization"></a>Cuando un usuario deja la organización 

Si un usuario que tiene un buzón de correo en Exchange Online deja la organización y su cuenta de Microsoft 365 se elimina, los mensajes de chat que estén sujetos a la retención se almacenarán en un buzón inactivo. El contenido de los mensajes de chat seguirá sujeto a cualquier directiva de retención que se hubiera aplicado al buzón antes de que pasara a estado inactivo, y el contenido está disponible para una búsqueda de eDiscovery. Para obtener más información, consulte [Buzones de correo inactivos en Exchange Online](inactive-mailboxes-in-office-365.md). 

Si el usuario ha guardado archivos en Teams, consulte la [sección equivalente](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) para SharePoint y OneDrive.

## <a name="limitations"></a>Limitaciones

Estamos trabajando continuamente en la optimización de la funcionalidad de retención en Teams. Mientras tanto, estas son algunas de las limitaciones que debe tener en cuenta al usar la retención para los mensajes de canal y chats de Teams:

- **Problema de visualización incorrecta en Outlook**. Si crea directivas de retención para las ubicaciones de Skype o de Teams, una de esas directivas se muestra como la directiva de carpeta predeterminada cuando un usuario ve las propiedades de una carpeta del buzón en el cliente de escritorio de Outlook. Este es un problema de presentación incorrecto en Outlook y [un problema conocido](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies). Qué se debe mostrar como directiva predeterminada para carpetas es la Directiva de retención de buzón que se aplica a la carpeta. La Directiva de retención de Skype o de Teams no se aplica al buzón del usuario.

- **Problemas de configuración**: 
    - Al seleccionar **Elegir equipos** para la ubicación de los **mensajes del canal Teams** es posible que vea grupos de Office 365 que no son también equipos. No seleccione estos equipos
    
    - Al seleccionar **Elegir usuarios** para la ubicación de los **chats de Teams** puede que vea invitados y no usuarios del buzón. Las directivas de retención no están diseñadas para estos usuarios, así que no los seleccione.

## <a name="configuration-guidance"></a>Instrucciones de configuración

Si va a configurar la retención en Microsoft 365 por primera vez, consulte [Introducción a las directivas y etiquetas de retención](get-started-with-retention.md).

Si está listo para configurar una directiva de retención para Teams, consulte [Crear y configurar directivas de retención](create-retention-policies.md).