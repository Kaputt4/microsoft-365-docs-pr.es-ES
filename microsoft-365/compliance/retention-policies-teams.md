---
title: Más información sobre las directivas de retención de Teams
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
ms.openlocfilehash: 709d4414ebb01081172aff932899146c06d05a19
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268286"
---
# <a name="learn-about-retention-policies-for-microsoft-teams"></a>Más información sobre las directivas de retención para Microsoft Teams

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

La información de este artículo complementa el[Más información sobre las directivas de retención](retention-policies.md) porque tiene información específica de Microsoft Teams.

## <a name="how-a-retention-policy-works-with-microsoft-teams"></a>Cómo funciona una directiva de retención con Microsoft Teams

Puede usar una directiva de retención para retener los chats y canalizar los mensajes en Teams. Los chats de Teams se almacenan en una carpeta oculta en el buzón de cada usuario incluido en el chat, y los mensajes de los canales de Teams se almacenan en una carpeta oculta similar en el buzón de correo del grupo del equipo. 

Es importante entender que Teams utilizan un servicio de chat impulsado por Azure que también almacena estos datos, y por defecto este servicio almacena los datos indefinidamente. Por esta razón, recomendamos encarecidamente que utilicen las ubicaciones de Teams para conservar y eliminar los datos de Teams. Usando las ubicaciones de Teams se borrarán permanentemente los datos tanto de los buzones de Exchange como del subyacente servicio de chat impulsado por Azure. Para obtener más información, consulte[Seguridad y cumplimiento en Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258)y específicamente, la sección [Arquitectura de protección de la información](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture).

Los chats de Teams y los mensajes de los canales no se ven afectados por las directivas de retención que se configuran para los buzones de los usuarios o grupos. Aunque los chats de Teams y los mensajes de los canales se almacenan en Exchange, estos datos de Teams se incluyen sólo por una directiva de retención que está configurada para los **mensajes de los canales de Teams** y las ubicaciones de los **chats de Teams**.

> [!NOTE]
> Si un usuario está incluido en una directiva de retención activa que retiene los datos de Teams y elimina el buzón de un usuario incluido en esta directiva, para retener los datos de Teams, el buzón se convierte en un [buzón inactivo](inactive-mailboxes-in-office-365.md). Si no necesita retener los datos de Teams para el usuario, excluye la cuenta del usuario de la directiva de retención antes de eliminar su buzón.

Una vez que se configura una directiva de retención para los mensajes de chat y de canal, los caminos que toma el contenido dependen de si la directiva de retención es para retener y eliminar, sólo para retener o sólo para eliminar.

Cuando la directiva de retención es retener y eliminar:

![Diagrama de flujo de retención para los chat de Teams y mensajes de canal](../media/TeamsRetentionLifecycle.png)

1. **Si el usuario modifica o elimina un mensaje de una conversación o un canal** durante el período de retención, el mensaje se mueve (o copia, en el caso de edición) a la carpeta SubstrateHolds (que es una carpeta oculta en cada buzón de usuario o grupo) y se almacena en esta carpeta hasta que finalice el período de retención. Los mensajes se eliminan permanentemente el día en que expire el período de retención.

2. **Si un mensaje de canal o de chat no se elimina** durante el período de retención, el mensaje se mueve a la carpeta SubstrateHolds en un plazo de un día después de que expire el período de retención (tarda de 0 a 24 horas). El mensaje se elimina permanentemente un día después de que se mueva a la carpeta SubstrateHolds. 

> [!NOTE]
> Los mensajes de la carpeta SubstrateHolds se pueden buscar en las herramientas de eDiscovery. Cuando un mensaje se elimina de forma permanente, no se mostrará en una búsqueda de eDiscovery.

Cuando la directiva de retención es de solo retención, o solo eliminación, las rutas de acceso de contenido son variaciones de retener y eliminar:

### <a name="content-paths-for-retain-only-retention-policy"></a>Rutas de contenido para la directiva de retención de solo retención

1. **Si un mensaje de chat o de un canal se modifica o se elimina** durante el período de retención: se crea una copia del mensaje original en la carpeta SubstrateHolds y se conserva hasta el final del período de retención, cuando la copia en la carpeta SubstrateHolds se elimina permanentemente un día después de que el elemento expire. 

2. ** Si el artículo no se modifica o elimina** durante el período de retención: no sucede nada antes y después del período de retención; el mensaje permanece en su ubicación original.

#### <a name="content-paths-for-delete-only-retention-policy"></a>Rutas de contenido para la directiva de retención de sólo eliminar

1. **Si el mensaje no se elimina**durante el período de retención: al final del período de retención, el mensaje se mueve a la carpeta SubstrateHolds. 

2. **Si el elemento es eliminado por el usuario** durante el período, el elemento se mueve inmediatamente a la carpeta SubstrateHolds. Si un usuario elimina el mensaje de allí o vacía la carpeta SubstrateHolds, el elemento se elimina de forma permanente. De lo contrario, el mensaje se borra permanentemente un día después de estar en la carpeta SubstrateHolds.


## <a name="skype-for-business-and-teams-interop-chats"></a>Chat de Skype Empresarial e interoperabilidad de Teams

El mismo flujo funciona para los chats interoperativos de Skype Empresarial y Teams. Cuando una conversación de Skype Empresarial llega a Teams, se convierte en un mensaje en un hilo de conversación de Teams y se ingiere en el buzón correspondiente. Las directivas de retención de Teams eliminarán estos mensajes del hilo de Teams. 

Sin embargo, si se activa el historial de conversaciones en Skype Empresarial y desde el lado del cliente de Skype Empresarial ese historial se guarda en un buzón de correo, los datos de las conversaciones no se manejan mediante una directiva de retención de Teams.

## <a name="files-in-teams"></a>Archivos en Teams.

En Teams, los archivos que se comparten en el chat se almacenan en la cuenta de OneDrive del usuario que compartió el archivo. Los archivos que se suben a los canales se almacenan en el sitio de SharePoint para el equipo. Esto significa que para retener o eliminar archivos en Teams, debe configurar una o más directivas de retención que se aplican a las**cuentas de OneDrive** y **sitios de SharePoint** además de cualquier directiva de retención que configure para Teams. Para obtener más información sobre cómo funcionan las directivas de retención para estas ubicaciones, consulte [Más información sobre las directivas de retención para SharePoint y OneDrive](retention-policies-sharepoint.md).

> [!NOTE]
> Una directiva de retención que incluya los mensajes del canal de Teams o los chats de Teams sólo puede incluir las ubicaciones de Teams. Por lo tanto, para retener o eliminar estos archivos en Teams, debe crear una directiva de retención separada.
> 
> Si desea aplicar una directiva de retención a los archivos de un equipo en específico, puede elegir el sitio de SharePoint del equipo y las cuentas de OneDrive de los usuarios del equipo.

Es posible que una directiva de retención que se aplique a SharePoint o OneDrive pueda eliminar un archivo al que se haga referencia en un chat o mensaje de canal de Teams antes de que esos mensajes sean eliminados. En este escenario, el archivo seguirá apareciendo en el mensaje de Teams, pero cuando los usuarios hagan clic en el archivo, obtendrán un error de "Archivo no encontrado". Este comportamiento no es específico de las directivas de retención y también podría ocurrir si un usuario elimina manualmente un archivo de SharePoint o OneDrive.

## <a name="meetings-and-external-users"></a>Reuniones y usuarios externos

Los mensajes de reunión del canal se almacenan de la misma manera que los mensajes del canal, así que para estos datos, seleccione la ubicación de los**mensajes del canal de Teams**cuando configure su directiva de retención.

Los mensajes de reuniones improvisadas se almacenan de la misma manera que los mensajes de chat del grupo, por lo que para estos datos, seleccione la ubicación de los** chats de Teams** cuando configure su directiva de retención.

Cuando se incluyen usuarios externos en una reunión que su organización organiza:

- Si un usuario externo se une utilizando una cuenta de invitado en su inquilino, este usuario tiene un buzón de correo en la sombra que puede estar sujeto a la directiva de retención de su organización para Teams. Los mensajes de la reunión se almacenan tanto en el correo de sus usuarios como en el correo paralelo. 

- Si un usuario externo se une mediante el uso de una cuenta de otra organización de Microsoft 365, sus directivas de retención no pueden eliminar los mensajes de este usuario porque están almacenados en el buzón de ese usuario en otro arrendatario. Sin embargo, para la misma reunión, sus directivas de retención pueden eliminar los mensajes de sus usuarios.


## <a name="limitations"></a>Limitaciones

Estamos trabajando continuamente en la optimización de la funcionalidad de retención en Teams. Por el momento, tenga en cuenta algunas de las limitaciones actuales:
  
- **Teams requiere una directiva de retención separada ** Cuando cree una directiva de retención y activa las ubicaciones de Teams, todas las demás ubicaciones se desactivan. Una directiva de retención que incluya Teams puede comprender solo su ubicación y ninguna más. 
    
- **Teams no está incluido en una directiva de toda la organización.**. Si crea una directiva para toda la organización, Teams no es incluida porque requiere una directiva de retención separada. 
    
- **Teams no es compatible con la retención avanzada**. Cuando creas una directiva de retención, si elige la [Configuración avanzada para identificar el contenido que cumple con condiciones específicas](create-retention-policies.md#advanced-settings-to-identify-content-that-meets-specific-conditions), las ubicaciones de Teams no están disponibles. Actualmente, la retención en Teams se aplica a todo el contenido de los mensajes de chat y de los canales cuando se seleccionan esas ubicaciones. 

- **Los mensajes de Teams en los canales privados no se incluyen cuando se configura una directiva de retención de los mensajes de los canales de Teams.**. En cambio, los mensajes de los canales privados se incluyen para los usuarios como chats de grupo con la opción de**chats de Teams **. 
    
- **Teams puede tardar un máximo de tres días en limpiar los mensajes caducados**. Cuando expire el período de retención, las directivas de retención aplicadas a Teams se eliminarán. Sin embargo, puede que tarde hasta tres días limpiar estos mensajes y eliminarlos permanentemente. Asimismo, los mensajes de chat y canales se podrán buscar con las herramientas de eDiscovery durante el tiempo que transcurra durante el período de retención y cuando los mensajes se eliminan de forma permanente.
    
   > [!NOTE]
   > Se ha usado para ser verdadera que una directiva de retención no pudo eliminar el contenido de Teams que tiene menos de 30 días, pero hemos quitado esta limitación. Ahora, el período de retención de contenido de Teams puede ser el número de días que elija y tan breve como un día. Si tiene un período de retención de un día, se tardará hasta tres días después de que expire el período de retención antes de que se eliminen de forma permanente los mensajes.

- **Problema de visualización incorrecta en Outlook**. Si crea directivas de retención para las ubicaciones de Skype o de Teams, una de esas directivas se muestra como la directiva de carpeta predeterminada cuando un usuario ve las propiedades de una carpeta del buzón en el cliente de escritorio de Outlook. Este es un problema de presentación incorrecto en Outlook y [un problema conocido](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies). Qué se debe mostrar como directiva predeterminada para carpetas es la Directiva de retención de buzón que se aplica a la carpeta. La Directiva de retención de Skype o de Teams no se aplica al buzón del usuario.

- **Problemas de configuración**: 
    - Al seleccionar **Elegir equipos** para la ubicación de los**mensajes del canal Teams** es posible que vea grupos de Office 365 que no son también equipos. No seleccione estos equipos
    
    - Al seleccionar **Elegir usuarios** para la ubicación de los**chats de Teams** puede que vea invitados y no usuarios del buzón. Las directivas de retención no están diseñadas para estos usuarios, así que no los seleccione.


## <a name="how-to-configure-a-retention-policy-for-microsoft-teams"></a>Cómo configurar una directiva de retención para Microsoft Teams

Consulte[Crear y configurar directivas de retención](create-retention-policies.md).

En la página**Elegir ubicaciones **del asistente, seleccione las siguientes opciones:

- **Permitirme elegir ubicaciones específicas** > **Mensajes de canal de Teams** y **chats de Teams**

Una directiva de retención que se aplica a Teams puede utilizar el[Bloqueo de conservación](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements), que puede ser requerido por razones regulatorias.

## <a name="related-information"></a>Información relacionada

[Directivas de retención en Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies)
