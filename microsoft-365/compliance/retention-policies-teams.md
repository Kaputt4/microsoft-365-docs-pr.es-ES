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
ms.openlocfilehash: 32656dc91350e5082171eb4fadd91d3a6287b9b7
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754066"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>Más información sobre la retención para Microsoft Teams

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

La información de este artículo complementa [Obtenga más información sobre la retención](retention.md) porque tiene información específica para los mensajes de Microsoft Teams.

Para otras cargas de trabajo, vea:

- [Obtenga más información sobre la retención de SharePoint y OneDrive](retention-policies-sharepoint.md)
- [Más información sobre la retención para Yammer](retention-policies-yammer.md)
- [Más información sobre las directivas de retención de Exchange](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>Qué se incluye para la retención y eliminación

Los siguientes elementos de Teams se pueden retener y eliminar mediante la retención para Teams: chats y mensajes de canal.

Los mensajes de Teams en canales privados no se incluyen y las reacciones de otras personas en forma de iconos gestuales no están incluidos.

Los mensajes de correo electrónico y los archivos que use con Teams no son incluidos en directivas de retención para Teams. Estos elementos tienen sus propias directivas de retención.

## <a name="how-retention-works-with-microsoft-teams"></a>Cómo funciona la retención con Microsoft Teams

Puede usar una directiva de retención para retener los chats y canalizar los mensajes en Teams. Los chats de Teams se almacenan en una carpeta oculta en el buzón de cada usuario incluido en el chat, y los mensajes de los canales de Teams se almacenan en una carpeta oculta similar en el buzón de correo del grupo del equipo.

Es importante entender que Teams utilizan un servicio de chat impulsado por Azure que también almacena estos datos, y por defecto este servicio almacena los datos indefinidamente. Por esta razón, le recomendamos que cree una directiva de retención que utilice las ubicaciones de Teams para conservar y eliminar los datos de Teams. Esta directiva de retención puede eliminar los datos de manera permanente tanto de los buzones de Exchange como del servicio subyacente de chat con tecnología Azure. Para obtener más información, consulte[Seguridad y cumplimiento en Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258)y específicamente, la sección [Arquitectura de protección de la información](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture).

Los chats de Teams y los mensajes de los canales no se ven afectados por las directivas de retención que se configuran para los buzones de los usuarios o grupos. Aunque los chats de Teams y los mensajes de los canales se almacenan en Exchange, estos datos de Teams se incluyen sólo por una directiva de retención que está configurada para los **mensajes de los canales de Teams** y las ubicaciones de los **chats de Teams** .

> [!NOTE]
> Si un usuario está incluido en una directiva de retención activa que retiene los datos de Teams y elimina el buzón de un usuario incluido en esta directiva, para retener los datos de Teams, el buzón se convierte en un [buzón inactivo](inactive-mailboxes-in-office-365.md). Si no necesita retener los datos de Teams para el usuario, excluye la cuenta del usuario de la directiva de retención antes de eliminar su buzón.

Una vez que se configura una directiva de retención para los mensajes del chat y de los canales, un trabajo de temporizador del servicio de Exchange evalúa de manera periódica los elementos de la carpeta oculta en la que se almacenan estos mensajes de Teams. El trabajo de temporizador tarda hasta siete días en ejecutarse. Cuando el período de retención de estos elementos caduca, se trasladan a la carpeta SubstrateHolds, otra carpeta oculta ubicada en cada buzón de usuario o grupo para almacenar los elementos "eliminados temporalmente" antes de que se eliminen de forma permanente.

Una vez que se configura una directiva de retención para los mensajes del chat y de los canales, las rutas que seguirá el contenido dependerán de si la directiva de retención se configura para retener y luego eliminar, solo retener, o solo eliminar.

Cuando la directiva de retención es retener y luego eliminar:

![Diagrama de flujo de retención para los mensajes del chat y de los canales de Teams](../media/teamsretentionlifecycle.png)

Para las dos rutas en el diagrama:

1. Si el usuario **edita o elimina un mensaje del chat o canal** durante el período de retención, el mensaje original se copia (si se edita) o se traslada (si se elimina) a la carpeta SubstrateHolds en un plazo de 21 días. El mensaje se almacena hasta que finaliza el período de retención y luego se elimina de forma permanente en 24 horas.

2. **Si no se elimina un mensaje del chat o canal** , o, en el caso de los mensajes actuales, después de editarlo, el mensaje se traslada a la carpeta SubstrateHolds después de que el período de retención caduque. Esta acción tarda hasta 7 días después de la fecha de expiración. Cuando el mensaje está en la carpeta SubstrateHolds, se elimina permanentemente dentro de las 24 horas siguientes. 

> [!NOTE]
> Los mensajes de la carpeta SubstrateHolds se pueden buscar con las herramientas de eDiscovery. Hasta que los mensajes se eliminen permanentemente de esta carpeta SubstrateHolds, las herramientas de eDiscovery pueden buscarlos.

Cuando la directiva de retención es de solo retención o de solo eliminación, las rutas de acceso de contenido son variaciones de retener y eliminar.

### <a name="content-paths-for-retain-only-retention-policy"></a>Rutas de contenido para la directiva de retención de solo retención

1. **Si se edita o elimina un mensaje del chat o canal** : se crea una copia del mensaje original en la carpeta SubstrateHolds en un plazo de 21 días y se retiene ahí hasta que caduque el periodo de retención. Luego, el mensaje se elimina de forma permanente de la carpeta SubstrateHolds en 24 horas.

2. **Si el elemento no se modifica o elimina** , o, en el caso de los mensajes actuales, después de su edición, durante el período de retención: no sucede nada antes ni después del período de retención. El mensaje permanece en su ubicación original.

### <a name="content-paths-for-delete-only-retention-policy"></a>Rutas de contenido para la directiva de retención de sólo eliminar

1. **Si el mensaje no se elimina** durante el período de retención: al final del período de retención, el mensaje se mueve a la carpeta SubstrateHolds. Esta acción tarda hasta siete días después de la fecha de expiración. Luego, el mensaje se elimina de forma permanente de la carpeta SubstrateHolds en 24 horas.

2. **Si el usuario elimina el elemento** durante el período, el elemento se mueve a la carpeta SubstrateHolds en un plazo de 21 días, donde se eliminará de forma permanente después de 24 horas.


## <a name="skype-for-business-and-teams-interop-chats"></a>Chat de Skype Empresarial e interoperabilidad de Teams

Cuando una conversación de Skype Empresarial llega a Teams, se convierte en un mensaje en un hilo de conversación de Teams y se ingiere en el buzón correspondiente. Las directivas de retención de Teams se aplicarán a estos mensajes del hilo de Teams. 

Sin embargo, si se activa el historial de conversaciones en Skype Empresarial y desde el lado del cliente de Skype Empresarial ese historial se guarda en un buzón de correo, los datos de las conversaciones no se manejan mediante una directiva de retención de Teams. Para este contenido, use una directiva de retención configurada para Skype Empresarial.

## <a name="meetings-and-external-users"></a>Reuniones y usuarios externos

Los mensajes de reunión del canal se almacenan de la misma manera que los mensajes del canal, así que para estos datos, seleccione la ubicación de los **mensajes del canal de Teams** cuando configure su directiva de retención.

Los mensajes de reuniones improvisadas se almacenan de la misma manera que los mensajes de chat del grupo, por lo que para estos datos, seleccione la ubicación de los **chats de Teams** cuando configure su directiva de retención.

Cuando se incluyen usuarios externos en una reunión que su organización organiza:

- Si un usuario externo se une utilizando una cuenta de invitado en su inquilino, este usuario tiene un buzón de correo en la sombra que puede estar sujeto a la directiva de retención de su organización para Teams. Los mensajes de la reunión se almacenan tanto en el correo de sus usuarios como en el correo paralelo. 

- Si un usuario externo se une mediante el uso de una cuenta de otra organización de Microsoft 365, sus directivas de retención no pueden eliminar los mensajes de este usuario porque están almacenados en el buzón de ese usuario en otro arrendatario. Sin embargo, para la misma reunión, sus directivas de retención pueden eliminar los mensajes de sus usuarios.

## <a name="when-a-user-leaves-the-organization"></a>Cuando un usuario deja la organización 

Si un usuario deja la organización y su cuenta de Microsoft 365 se elimina, los mensajes de chat que estén sujetos a la retención se almacenarán en un buzón inactivo. El contenido de los mensajes de chat seguirá sujeto a cualquier directiva de retención que se hubiera aplicado al buzón antes de que pasara a estado inactivo, y el contenido está disponible para una búsqueda de eDiscovery. Para obtener más información, consulte [Buzones de correo inactivos en Exchange Online](inactive-mailboxes-in-office-365.md). 

Si el usuario ha guardado archivos en Teams, consulte la [sección equivalente](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) para SharePoint y OneDrive.

## <a name="limitations"></a>Limitaciones

Estamos trabajando continuamente en la optimización de la funcionalidad de retención en Teams. Mientras tanto, estas son algunas de las limitaciones que debe tener en cuenta al usar la retención para los mensajes de canal y chats de Teams:

- **Problema de visualización incorrecta en Outlook** . Si crea directivas de retención para las ubicaciones de Skype o de Teams, una de esas directivas se muestra como la directiva de carpeta predeterminada cuando un usuario ve las propiedades de una carpeta del buzón en el cliente de escritorio de Outlook. Este es un problema de presentación incorrecto en Outlook y [un problema conocido](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies). Qué se debe mostrar como directiva predeterminada para carpetas es la Directiva de retención de buzón que se aplica a la carpeta. La Directiva de retención de Skype o de Teams no se aplica al buzón del usuario.

- **Problemas de configuración** : 
    - Al seleccionar **Elegir equipos** para la ubicación de los **mensajes del canal Teams** es posible que vea grupos de Office 365 que no son también equipos. No seleccione estos equipos
    
    - Al seleccionar **Elegir usuarios** para la ubicación de los **chats de Teams** puede que vea invitados y no usuarios del buzón. Las directivas de retención no están diseñadas para estos usuarios, así que no los seleccione.

## <a name="configuration-guidance"></a>Instrucciones de configuración

Si va a configurar la retención en Microsoft 365 por primera vez, consulte [Introducción a las directivas y etiquetas de retención](get-started-with-retention.md).

Si está listo para configurar una directiva de retención para Teams, consulte [Crear y configurar directivas de retención](create-retention-policies.md).
