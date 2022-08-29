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
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre las directivas de retención de Microsoft 365 que se aplican a Microsoft Teams para que pueda administrar la retención automática o la eliminación de mensajes de Teams para su organización.
ms.openlocfilehash: da8275ff3a5792df3cbc72aea7b8e483a0a5f4f3
ms.sourcegitcommit: 031b3e963478f642a0d23be37a01f23a01cb3d84
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2022
ms.locfileid: "67441826"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>Más información sobre la retención para Microsoft Teams

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Si ve un mensaje en Teams que indica que los chats y los mensajes se han eliminado debido a una directiva de retención, vea [Mensajes de Teams sobre directivas de retención](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).
> 
> La información de esta página es para los administradores de TI que gestionan estas directivas de retención.

La información de este artículo complementa [Obtenga más información sobre la retención](retention.md) porque tiene información específica para los mensajes de Microsoft Teams.

Para otras cargas de trabajo, vea:

- [Obtenga más información sobre la retención de SharePoint y OneDrive](retention-policies-sharepoint.md)
- [Más información sobre la retención para Yammer](retention-policies-yammer.md)
- [Más información sobre las directivas de retención de Exchange](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>Qué se incluye para la retención y eliminación

> [!NOTE]
> Las directivas de retención admiten [ canales compartidos](/MicrosoftTeams/shared-channels). Los canales compartidos heredan la configuración de retención del canal primario.

Los mensajes de los chats de Teams, los mensajes de canal y los mensajes de canal privado se pueden eliminar mediante directivas de retención para Teams y, además del texto de los mensajes, se pueden conservar los elementos siguientes por motivos de cumplimiento: imágenes incrustadas, tablas, vínculos de hipertexto, vínculos a otros mensajes y archivos de Teams y [contenido de tarjetas](/microsoftteams/platform/task-modules-and-cards/what-are-cards). Los mensajes de chat y los mensajes de canal privado incluyen todos los nombres de las personas de la conversación, y los mensajes de canal incluyen el nombre del equipo y el título del mensaje (si se proporciona). 

Los fragmentos de código, notas de voz grabadas del cliente móvil de Teams, las miniaturas, las imágenes de anuncios y las reacciones de otros usuarios en forma de emoticonos no se conservan cuando usa las directivas de retención para Teams.

Los correos electrónicos y archivos que usa con Teams no se incluyen en las políticas de retención de Teams. Estos elementos tienen sus propias políticas de retención.

## <a name="how-retention-works-with-microsoft-teams"></a>Cómo funciona la retención con Microsoft Teams

Use esta sección para comprender cómo los procesos y el almacenamiento de backend cumplen sus requisitos de cumplimiento, y las herramientas de exhibición de documentos electrónicos deben verificarlos en lugar de los mensajes que están visibles actualmente en la aplicación Teams.

Puede usar una directiva de retención para conservar los datos de mensajes de canal y chats en Teams, y eliminar esos chats y mensajes. En segundo plano, se usan buzones de Exchange para almacenar datos copiados de estos mensajes. Los datos de los chats de Teams se almacenan en una carpeta oculta en el buzón de cada usuario incluido en el chat y se usa una carpeta oculta similar en un buzón de grupo para los mensajes del canal de Teams. Estas carpetas ocultas no están diseñadas para que los usuarios o administradores puedan acceder directamente a ellas, sino que almacenan datos que los administradores de cumplimiento pueden buscar con herramientas de exhibición de documentos electrónicos.

Estos buzones se muestran según su atributo RecipientTypeDetails:

- **UserMailbox**: estos buzones almacenan datos de mensajes para los usuarios de Teams basados en la nube.
- **MailUser**: estos buzones almacenan datos de mensajes para los [usuarios locales de Teams](search-cloud-based-mailboxes-for-on-premises-users.md).
- **GroupMailbox**: Estos buzones almacenan los datos de los mensajes de los canales estándar de los equipos.
- **SubstrateGroup**: estos buzones almacenan datos de mensajes para los canales de Teams compartidos.

Otros tipos de buzones, como RoomMailbox —que se usa en las salas de conferencias de Teams— no son compatibles con las directivas de retención de Teams.

Teams usa un servicio de chat con tecnología de Azure como almacenamiento principal para todos los mensajes (chats y mensajes de canal). Si necesita eliminar mensajes de Teams por motivos de cumplimiento, las políticas de retención de Teams pueden eliminar mensajes después de un período específico, según el momento en que se crearon. Luego, los mensajes se eliminan permanentemente de los buzones de correo de Exchange donde se almacenaron para las operaciones de cumplimiento y del almacenamiento principal que usa el servicio de chat subyacente con tecnología de Azure. Para más información sobre la arquitectura subyacente, consulte[Seguridad y cumplimiento en Microsoft Teams](/MicrosoftTeams/security-compliance-overview) y, específicamente, la sección [Arquitectura de protección de la información](/MicrosoftTeams/security-compliance-overview#information-protection-architecture).

Aunque los datos de los mensajes de canales y chats de Teams se almacenan en los buzones de correo, debe configurar una directiva de retención para los **mensajes de canal de Teams** y las ubicaciones de los **chats de Teams**. Los mensajes de canal y los chats de Teams no se incluyen en las políticas de retención configuradas para buzones de correo de usuarios o grupos de Exchange. De forma similar, las directivas de retención para Teams no afectan a otros elementos almacenados en los buzones de correo electrónico.

Si se agrega un usuario a un chat, se ingiere una copia de todos los mensajes compartidos con ellos en su buzón. La fecha de creación de esos mensajes no cambia para el nuevo usuario y sigue siendo la misma para todos los usuarios.

> [!NOTE]
> Si un usuario está incluido en una directiva de retención activa que retiene los mensajes de Teams y usted elimina el buzón de un usuario incluido en esta directiva, para retener los datos de Teams, el buzón se convierte en un [buzón inactivo](inactive-mailboxes-in-office-365.md). Si no necesita conservar estos datos de Teams para el usuario, excluya la cuenta de usuario de la directiva de retención y [espere a que este cambio surta efecto](create-retention-policies.md#how-long-it-takes-for-retention-policies-to-take-effect) antes de eliminar su buzón.

Una vez que se configura una directiva de retención para los mensajes del chat y de los canales, un trabajo de temporizador del servicio de Exchange evalúa de manera periódica los elementos de la carpeta oculta del buzón en la que se almacenan estos mensajes de Teams. El trabajo de temporizador tarda entre 1 y 7 días en ejecutarse. Cuando el período de retención de estos elementos caduca, se trasladan a la carpeta SubstrateHolds, otra carpeta oculta ubicada en cada buzón de usuario o grupo para almacenar los elementos "eliminados temporalmente" antes de que se eliminen de forma permanente. 

Los mensajes permanecen en la carpeta SubstrateHolds durante al menos 1 día y, luego, si son elegibles para su eliminación, el trabajo del temporizador los elimina, de forma permanente, la próxima vez que se ejecuta.

> [!IMPORTANT]
> Debido al [primer principio de retención](retention.md#the-principles-of-retention-or-what-takes-precedence) y dado que los mensajes de chat y del canal de Teams se almacenan en buzones de Exchange Online, la eliminación permanente de la carpeta SubstrateHolds siempre se suspenderá si el buzón se ve afectado por otra directiva de retención para la misma ubicación, suspensión por litigio, suspensión por retraso o si se aplica una retención de eDiscovery al buzón por motivos legales o de investigación.
>
> Aunque el buzón se incluya en una retención aplicable, los mensajes de chat y del canal de Teams que se hayan eliminado ya no estarán visibles en la aplicación de Teams, pero seguirán detectables con eDiscovery.

Una vez que se configura una directiva de retención para los mensajes del chat y de los canales, las rutas que seguirá el contenido dependerán de si la directiva de retención se configura para retener y luego eliminar, solo retener, o solo eliminar.

Cuando la directiva de retención es retener y luego eliminar:

![Diagrama de flujo de retención para los chat de Teams y mensajes de canal](../media/teamsretentionlifecycle.png)

Para las dos rutas en el diagrama:

1. **Si un usuario edita o elimina un mensaje de chat o canal** durante el período de retención, el mensaje original se copia (si se edita) o se mueve (si se elimina) a la carpeta SubstrateHolds. Cuando un usuario elimina un mensaje de Teams, aunque el mensaje desaparece de la aplicación Teams, el mensaje no va a la carpeta SubstrateHolds durante 21 días. El mensaje se almacena en la carpeta SubstrateHolds durante al menos 1 día. Cuando expira el período de retención, el mensaje se elimina de forma permanente la próxima vez que se ejecute el trabajo del temporizador (normalmente entre 1 y 7 días).

2. **Si no se elimina un mensaje del chat o de los canales**, o, en el caso de los mensajes actuales, después de editarlo, el mensaje se traslada a la carpeta SubstrateHolds después de que el período de retención caduca. Esta acción suele tardar entre 1 y 7 días a partir de la fecha de vencimiento. Cuando el mensaje está en la carpeta SubstrateHolds, se almacena allí durante al menos 1 día y, a continuación, el mensaje se elimina de forma permanente la próxima vez que se ejecuta el trabajo del temporizador (normalmente entre 1 y 7 días). 

> [!NOTE]
> Los mensajes almacenados en los buzones de correo, incluidas las carpetas ocultas, se pueden buscar mediante herramientas de eDiscovery. Hasta que los mensajes se eliminen permanentemente de la carpeta SubstrateHolds, las herramientas de eDiscovery pueden buscarlos.

Cuando el periodo de retención expira y mueve un mensaje a la carpeta SubstrateHolds, se comunica una operación de borrado al servicio de chat Azure backend, que a su vez retransmite la misma operación a la app cliente de Teams. Los retrasos en esta comunicación o almacenamiento en caché pueden explicar por qué, durante un breve período de tiempo, los usuarios siguen viendo estos mensajes en su aplicación de Teams.

En este escenario, en el que el servicio de chat de Azure recibe un comando de eliminación debido a una directiva de retención, el mensaje correspondiente en la aplicación cliente de Teams se elimina para todos los usuarios de la conversación. A veces, este [comportamiento puede parecer inesperado](/microsoftteams/troubleshoot/teams-im-presence/messages-unexpectedly-deleted-retention-policy) porque algunos de estos usuarios pueden ser de otra organización, tener una directiva de retención con un período de retención más largo o no tener asignada ninguna directiva de retención. Para estos usuarios, las copias de los mensajes aún se almacenan en sus buzones y permanecen disponibles para la búsqueda en eDiscovery hasta que otra directiva de retención elimine permanentemente los mensajes.

> [!IMPORTANT]
> Los mensajes visibles en la aplicación Teams no son un reflejo exacto de si se conservan o eliminan permanentemente para cumplir con los requisitos.

Cuando la directiva de retención es de solo retención, o solo eliminación, las rutas de acceso de contenido son variaciones de retener y eliminar.

### <a name="content-paths-for-retain-only-retention-policy"></a>Rutas de contenido para la directiva de retención de solo retención

1. **Si un usuario edita o elimina un mensaje de chat o canal** durante el período de retención: el mensaje original se copia (si se edita) o se mueve (si se elimina) a la carpeta SubstrateHolds. Cuando un usuario elimina un mensaje de Teams, aunque el mensaje desaparece de la aplicación Teams, el mensaje no va a la carpeta SubstrateHolds durante 21 días. El mensaje se almacena en la carpeta SubstrateHolds durante al menos 1 día. Si la política de retención está configurada para conservarse para siempre, el elemento permanece allí. Si la política de retención tiene una fecha de finalización para el período de retención y caduca, el mensaje se elimina de forma permanente la próxima vez que se ejecute el trabajo del temporizador (normalmente entre 1 y 7 días).

2. **Si el mensaje de chat o canal no es modificado o eliminado** por un usuario y para los mensajes actuales después de la edición durante el período de retención: No ocurre nada antes y después del período de retención; el mensaje permanece en su ubicación original.

### <a name="content-paths-for-delete-only-retention-policy"></a>Rutas de contenido para la directiva de retención de sólo eliminar

1. Si un usuario **edita o borra el mensaje de chat o canal** durante el período de retención: El mensaje original se copia (si se edita) o se mueve (si se borra) a la carpeta SubstrateHolds.  Cuando un usuario elimina un mensaje de Teams, aunque el mensaje desaparece de la aplicación Teams, el mensaje no va a la carpeta SubstrateHolds durante 21 días. El mensaje se almacena en la carpeta SubstrateHolds durante al menos 1 día y se elimina permanentemente la próxima vez que se ejecute el trabajo del temporizador (normalmente entre 1 y 7 días).

2. Si un usuario **no elimina un mensaje de chat o canal** durante el período de retención: Al final del período de retención, el mensaje se mueve a la carpeta SubstrateHolds. Esta acción suele tardar entre 1 y 7 días a partir de la fecha de vencimiento. El mensaje se conserva allí durante al menos 1 día y luego se elimina permanentemente la próxima vez que se ejecuta el trabajo del temporizador (generalmente entre 1 y 7 días).

#### <a name="example-flows-and-timings-for-retention-policies"></a>Ejemplos de flujos y tiempos para políticas de retención

Utilice los siguientes ejemplos para ver cómo los procesos y tiempos explicados en las secciones anteriores se aplican a las políticas de retención que tienen las siguientes configuraciones:

- [Ejemplo 1: solo retención durante 7 años](#example-1-retain-only-for-7-years)
- [Ejemplo 2: conservar durante 30 días y luego eliminar](#example-2-retain-for-30-days-and-then-delete)
- [Ejemplo 3: solo eliminar después de 1 día](#example-3-delete-only-after-1-day)

Para todos los ejemplos que hacen referencia a la eliminación permanente, debido a los [principios de retención](retention.md#the-principles-of-retention-or-what-takes-precedence), esta acción se suspende si el mensaje está sujeto a otra política de retención para retener el elemento o si está sujeto a una retención de eDiscovery.

##### <a name="example-1-retain-only-for-7-years"></a>Ejemplo 1: solo retención durante 7 años

El día 1, un usuario crea un mensaje de chat o canal.

El día 5, el usuario edita ese mensaje.

El día 30, el usuario elimina el mensaje actual.

Resultados de retención:

- Para el mensaje original:
    - El día 5, el mensaje se copia en la carpeta SubstrateHolds, donde aún se puede buscar con herramientas de eDiscovery durante un mínimo de 7 años a partir del día 1 (el período de retención).

- Para el mensaje actual (editado):
    - El día 30, el mensaje ya no se muestra en la aplicación Teams y se mueve a la carpeta SubstrateHolds después de 21 días, donde sigue permitiendo búsquedas con herramientas de exhibición de documentos electrónicos durante un mínimo de 7 años a partir del día 1 (el período de retención).

Si el usuario hubiera eliminado el mensaje actual después del período de retención especificado, en lugar de dentro del período de retención, el mensaje se seguiría moviendo a la carpeta SubstrateHolds después de 21 días. Sin embargo, ahora que ha expirado el período de retención, el mensaje se eliminaría permanentemente después del mínimo de 1 día y, por lo general, en un plazo de 1 a 7 días.

##### <a name="example-2-retain-for-30-days-and-then-delete"></a>Ejemplo 2: conservar durante 30 días y luego eliminar

El día 1, un usuario crea un mensaje de chat o canal.

El día 10, el usuario edita ese mensaje.

El usuario no realiza más modificaciones y no elimina el mensaje.

Resultados de retención:

- Para el mensaje original:
    - El día 10, el mensaje se copia en la carpeta SubstrateHolds, donde aún se puede buscar con herramientas de eDiscovery.
    - Al final del período de retención (30 días a partir del día 1), el mensaje se elimina permanentemente, por lo general, dentro de 1 a 7 días después del mínimo de 1 día, y luego no se devolverá con las búsquedas de eDiscovery.

- Para el mensaje actual (editado):
    - Al final del período de retención (30 días a partir del día 1), el mensaje se mueve a la carpeta SubstrateHolds normalmente dentro de 1 a 7 días, donde aún se puede buscar con herramientas de eDiscovery.
    - Luego, el mensaje se elimina permanentemente, por lo general, dentro de 1 a 7 días después del mínimo de 1 día, y luego no se devolverá con las búsquedas de exhibición de documentos electrónicos.

##### <a name="example-3-delete-only-after-1-day"></a>Ejemplo 3: solo eliminar después de 1 día

> [!NOTE]
> Debido a la corta duración de un día de esta configuración y los procesos de retención que operan dentro de un período de tiempo de 1 a 7 días, esta sección muestra ejemplos de tiempos que están dentro de los rangos de tiempo típicos.

El día 1, un usuario crea un mensaje de chat o canal.

Ejemplo de resultado de retención si el usuario no edita o elimina el mensaje:

- Día 5 (normalmente de 1 a 7 días después del inicio del período de retención el día 2):
    - El mensaje se mueve a la carpeta SubstrateHolds y permanece allí durante al menos 1 día donde aún se puede buscar con herramientas de eDiscovery.

- Día 9 (normalmente de 1 a 7 días después de un mínimo de 1 día en la carpeta SubstrateHolds):
    - Cuando un mensaje se elimina de forma permanente, no se mostrará en una búsqueda de eDiscovery.

Como muestra este ejemplo, aunque puede configurar una política de retención para eliminar mensajes después de solo un día, el servicio se somete a varios procesos para garantizar una eliminación compatible. Como resultado, una acción de eliminación después de 1 día podría tardar 16 días antes de que el mensaje se elimine permanentemente para que ya no se devuelva en las búsquedas de exhibición de documentos electrónicos.

## <a name="skype-for-business-and-teams-interop-chats"></a>Chat de Skype Empresarial e interoperabilidad de Teams

Cuando una conversación de Skype Empresarial llega a Teams, se convierte en un mensaje en un hilo de conversación de Teams y se ingiere en el buzón correspondiente. Las directivas de retención de Teams se aplicarán a estos mensajes del hilo de Teams. 

Sin embargo, si el historial de conversaciones está activado para Skype Empresarial y desde el lado del cliente de Skype Empresarial, ese historial se guarda en un buzón de correo, los datos de chat no se controlan mediante una directiva de retención de Teams. Para este contenido, use una directiva de retención configurada para Skype Empresarial.

## <a name="messages-and-external-users"></a>Mensajes y usuarios externos

Cuando se incluyen usuarios externos en una reunión o chat que la organización hospeda:

- Si un usuario externo se une mediante una cuenta de invitado en el inquilino, los mensajes de Teams se almacenan en el buzón de los usuarios y en un buzón de correo alternativo que se concede a la cuenta de invitado. Sin embargo, las directivas de retención no se admiten para los buzones de correo de sombras paralelas, aunque se puedan notificar como incluidas en una directiva de retención para toda la ubicación (a veces conocida como "directiva de toda la organización").

- Si un usuario externo se une mediante el uso de una cuenta de otra organización de Microsoft 365, sus directivas de retención no pueden eliminar los mensajes de este usuario porque están almacenados en el buzón de ese usuario en otro arrendatario. Sin embargo, para la misma reunión o chat, las directivas de retención pueden eliminar mensajes para los usuarios.

## <a name="when-a-user-leaves-the-organization"></a>Cuando un usuario deja la organización 

Si un usuario que tiene un buzón de correo en Exchange Online deja la organización y su cuenta de Microsoft 365 se elimina, los mensajes de chat que estén sujetos a la retención se almacenarán en un buzón inactivo. El contenido de los mensajes de chat seguirá sujeto a cualquier directiva de retención que se hubiera aplicado al buzón antes de que pasara a estado inactivo, y el contenido está disponible para una búsqueda de eDiscovery. Para obtener más información, consulte [Más información sobre buzones inactivos](inactive-mailboxes-in-office-365.md). 

Si el usuario ha guardado archivos en Teams, consulte la [sección equivalente](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) para SharePoint y OneDrive.

## <a name="configuration-guidance"></a>Instrucciones de configuración

Si va a configurar la retención en Microsoft 365 por primera vez, consulte [Introducción a la administración del ciclo de vida de los datos](get-started-with-data-lifecycle-management.md).

Si está listo para configurar una directiva de retención para Teams, consulte [Crear y configurar directivas de retención](create-retention-policies.md).
