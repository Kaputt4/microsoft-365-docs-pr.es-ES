---
title: Detección de señales de canal con cumplimiento de comunicaciones
description: Obtenga más información sobre la detección de señales de canal con cumplimiento de comunicaciones.
keywords: Microsoft 365, Microsoft Purview, cumplimiento, cumplimiento de comunicaciones
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 51cf52c4729a543130eac676b8732ccd2fe0a388
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "65319086"
---
# <a name="detect-channel-signals-with-communication-compliance"></a>Detección de señales de canal con cumplimiento de comunicaciones

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Con las directivas de cumplimiento de comunicaciones, puede elegir examinar los mensajes en una o varias de las siguientes plataformas de comunicación como un grupo o como orígenes independientes. Los mensajes originales capturados en estas plataformas se conservan en la ubicación de la plataforma original de acuerdo con las [directivas de retención y retención](/microsoft-365/compliance/information-governance) de su organización. Las copias de los mensajes utilizados por las directivas de cumplimiento de comunicaciones para el análisis y la investigación se conservan mientras la directiva esté en vigor, incluso si los usuarios abandonan la organización y se eliminan sus buzones. Cuando se elimina una directiva de comunicación, también se eliminan copias de los mensajes asociados a la directiva.

## <a name="microsoft-teams"></a>Microsoft Teams

Las comunicaciones de chat en canales de Microsoft Teams públicos y privados y chats individuales se pueden examinar. Cuando los usuarios se asignan a una directiva de cumplimiento de comunicaciones con Microsoft Teams cobertura seleccionada, las comunicaciones de chat para los usuarios se supervisan automáticamente en todos los Microsoft Teams donde los usuarios son miembros. Microsoft Teams cobertura se incluye automáticamente para las plantillas de directiva predefinidas y se selecciona de forma predeterminada en la plantilla de directiva personalizada. Teams chats que coincidan con las condiciones de la directiva de cumplimiento de comunicaciones pueden tardar hasta 48 horas en procesarse.

Para chat privado y canales privados, las directivas de cumplimiento de comunicaciones admiten [canales compartidos](/MicrosoftTeams/shared-channels) y análisis de datos adjuntos modernos. La compatibilidad con canales compartidos en Teams se controla automáticamente y no requiere cambios adicionales en la configuración de cumplimiento de comunicaciones. En la tabla siguiente se resume el comportamiento de cumplimiento de la comunicación al compartir Teams canales con grupos y usuarios:

|**Escenario**|**Comportamiento de cumplimiento de comunicaciones**|
|:-----------|:------------------------------------|
| **Compartir un canal con un equipo interno** | Las directivas de cumplimiento de comunicaciones se aplican a los usuarios en el ámbito y a todos los mensajes del canal compartido |
| **Compartir un canal con un equipo externo** | Las directivas de cumplimiento de comunicaciones se aplican a los usuarios internos del ámbito y a los mensajes del canal compartido de la organización interna |

Los datos adjuntos modernos son archivos procedentes de [sitios OneDrive](/onedrive/plan-onedrive-enterprise#modern-attachments) o [SharePoint](/sharepoint/dev/solution-guidance/modern-experience-customizations) que se incluyen en Teams mensajes. El texto se extrae automáticamente de estos datos adjuntos para el procesamiento automatizado y posibles coincidencias con las condiciones y clasificadores de directivas de cumplimiento de comunicaciones activas. No hay ninguna configuración adicional necesaria para la detección y el procesamiento de datos adjuntos modernos. El texto solo se extrae para los datos adjuntos que coinciden con las condiciones de la directiva. El texto no se extrae para los datos adjuntos de los mensajes con coincidencias de directiva, incluso si los datos adjuntos también tienen una coincidencia de directiva.

El examen de datos adjuntos modernos es compatible con los siguientes tipos de archivo:

- Microsoft Word (.docx)
- Microsoft Excel (.xlsx)
- Microsoft PowerPoint (.pptx)
- Texto (.txt)
- Portable Document Format (.pdf)

El texto extraído de los datos adjuntos modernos se incluye con el mensaje asociado en el panel **Alertas pendientes** de una directiva. El texto extraído de un archivo adjunto se denomina nombre de archivo adjunto (y extensión de formato) y la extensión de .txt. Por ejemplo, el texto extraído de un archivo adjunto denominado *ContosoBusinessPlan.docx* aparecería como *ContosoBusinessPlan.docx.txt* en el panel **Alertas pendientes** de una directiva.

Seleccione el texto de datos adjuntos extraído para ver los detalles en las vistas *De origen* y *Texto sin formato* . Después de revisar, puede resolver o tomar medidas en el texto de datos adjuntos mediante los controles de la barra de comandos. También tiene la opción de descargar los datos adjuntos para su revisión fuera del proceso de revisión de cumplimiento de comunicaciones.

Use las siguientes configuraciones de administración de grupos para supervisar los chats de usuarios individuales y las comunicaciones de canal en Teams:

- **Para Teams comunicaciones de chat:** asigne usuarios individuales o asigne un grupo de [distribución](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) a la directiva de cumplimiento de comunicaciones. Esta configuración es para relaciones de usuario/chat de uno a uno o de uno a varios.
- **Para las comunicaciones de Teams canal:** asigne cada canal Microsoft Teams o grupo de Microsoft 365 que quiera examinar que contenga un usuario específico a la directiva de cumplimiento de comunicaciones. Si agrega el mismo usuario a otros canales de Microsoft Teams o grupos de Microsoft 365, asegúrese de agregar estos nuevos canales y grupos a la directiva de cumplimiento de comunicaciones. Si algún miembro del canal es un usuario supervisado dentro de una directiva y la dirección *de entrada* está configurada en una directiva, todos los mensajes enviados dentro del canal están sujetos a revisión y posibles coincidencias de directivas (incluso para los usuarios del canal que no están supervisados explícitamente). Por ejemplo, el usuario A es el propietario o miembro de un canal. El usuario B y el usuario C son miembros del mismo canal y usan un idioma que coincide con la directiva de contenido inadecuado que supervisa solo al usuario A. El usuario B y el usuario C crean coincidencias de directivas para las conversaciones dentro del canal, aunque no estén supervisadas directamente en la directiva de contenido inadecuado. Teams conversaciones entre el usuario B y el usuario C que están fuera del canal que incluye el usuario A no estarían sujetas a la directiva de contenido inadecuado que incluye al usuario A. Para excluir a los miembros del canal de la supervisión cuando otros miembros del canal se supervisan explícitamente, desactive la configuración Dirección de comunicación *entrante* en la directiva de cumplimiento de comunicaciones aplicable.
- **Para Teams comunicaciones de chat con entornos de correo electrónico híbridos**: el cumplimiento de la comunicación puede supervisar los mensajes de chat de los usuarios de las organizaciones con una implementación local de Exchange o un proveedor de correo electrónico externo que haya habilitado Microsoft Teams. Debe crear un grupo de distribución para que los usuarios con buzones locales o externos supervisen. Al crear una directiva de cumplimiento de comunicaciones, asignará este grupo de distribución como la selección **Usuarios y grupos supervisados** en el Asistente para directivas. Para obtener más información sobre los requisitos y las limitaciones para habilitar el almacenamiento basado en la nube y Teams compatibilidad con los usuarios locales, consulte [Búsqueda de datos de chat de Teams para usuarios locales](search-cloud-based-mailboxes-for-on-premises-users.md).

## <a name="exchange-email"></a>Correo electrónico de Exchange

Los buzones hospedados en Exchange Online como parte de la suscripción Microsoft 365 o Office 365 son aptos para el examen de mensajes. Exchange mensajes de correo electrónico y datos adjuntos que coinciden con las condiciones de la directiva de cumplimiento de comunicaciones pueden procesarse aproximadamente 24 horas. Los tipos de datos adjuntos admitidos para el cumplimiento de comunicaciones son los mismos que los [tipos de archivo admitidos en las inspecciones de contenido de reglas de flujo de correo de Exchange](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).

## <a name="yammer"></a>Yammer

Los mensajes privados y las conversaciones públicas y los datos adjuntos asociados en Yammer comunidades se pueden examinar. Cuando se agrega un usuario a la directiva de cumplimiento de comunicaciones que incluye Yammer como un canal definido, las comunicaciones entre todas las comunidades Yammer de las que el usuario es miembro se incluyen en el proceso de examen. Yammer chats y datos adjuntos que coinciden con las condiciones de la directiva de cumplimiento de comunicaciones pueden tardar hasta 24 horas en procesarse. 

Yammer debe estar en [modo nativo](/yammer/configure-your-yammer-network/overview-native-mode) para que las directivas de cumplimiento de comunicaciones supervisen las comunicaciones Yammer y los datos adjuntos. En el modo nativo, todos los usuarios de Yammer están en Azure Active Directory (AAD), todos los grupos son Grupos de Office 365 y todos los archivos se almacenan en SharePoint Online.

## <a name="skype-for-business-online"></a>Skype Empresarial Online

Las comunicaciones de chat y los datos adjuntos asociados en Skype Empresarial Online se pueden supervisar. Los chats de Skype Empresarial Online que coincidan con las condiciones de directiva de cumplimiento de comunicaciones pueden tardar hasta 24 horas en procesarse. Las conversaciones de chat supervisadas proceden de [conversaciones anteriores guardadas en Skype Empresarial Online](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2).  

Use la siguiente configuración de administración de grupos para supervisar las comunicaciones de chat de usuarios en Skype Empresarial Online:

- **Para Skype Empresarial comunicaciones de chat en línea**: asigne usuarios individuales o asigne un [grupo de distribución](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) a la directiva de cumplimiento de comunicaciones. Esta configuración es para relaciones de usuario/chat de uno a uno o de uno a varios.

## <a name="third-party-sources"></a>Orígenes de terceros.

Puede examinar las comunicaciones en busca de datos importados en buzones de su organización de Microsoft 365 desde orígenes de terceros, como [Instant Bloomberg](archive-instant-bloomberg-data.md), [Slack](archive-slack-data.md), [Zoom](archive-zoommeetings-data.md), SMS y muchos otros. Para obtener una lista completa de los conectores admitidos en el cumplimiento de comunicaciones, consulte [Archivo de datos de terceros](archiving-third-party-data.md).

Debe configurar un conector de terceros para la organización de Microsoft 365 antes de poder asignar el conector a una directiva de cumplimiento de comunicaciones. La sección **Orígenes de terceros** del Asistente para directivas de cumplimiento de comunicaciones solo muestra los conectores de terceros configurados actualmente.
