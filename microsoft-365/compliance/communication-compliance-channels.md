---
title: Detección de señales de canal con cumplimiento de comunicaciones
description: Obtenga más información sobre cómo detectar señales de canal con el cumplimiento de la comunicación.
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
ms.openlocfilehash: 940454e95a89748c0b4cfa985a624abd66fb840c
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2021
ms.locfileid: "60703468"
---
# <a name="detect-channel-signals-with-communication-compliance"></a>Detección de señales de canal con cumplimiento de comunicaciones

Con las directivas de cumplimiento de comunicaciones, puede elegir examinar mensajes en una o varias de las siguientes plataformas de comunicación como un grupo o como orígenes independientes. Las comunicaciones capturadas en estas plataformas se conservan durante siete años para cada directiva de forma predeterminada, incluso si los usuarios abandonan su organización y sus buzones se eliminan.

## <a name="microsoft-teams"></a>Microsoft Teams

Se pueden examinar las comunicaciones de chat en canales Microsoft Teams y chats individuales. Cuando los usuarios se asignan a una directiva de cumplimiento de comunicaciones con una cobertura Microsoft Teams seleccionada, las comunicaciones de chat para los usuarios se supervisan automáticamente en todos los Microsoft Teams donde los usuarios son miembros. Microsoft Teams cobertura se incluye automáticamente para las plantillas de directiva predefinidas y se selecciona de forma predeterminada en la plantilla de directiva personalizada. Teams chats que coincidan con las condiciones de la directiva de cumplimiento de comunicaciones pueden tardar hasta 48 horas en procesarse.

Para los canales privados y de chat privado, las directivas de cumplimiento de comunicación admiten el examen de datos adjuntos modernos. Los datos adjuntos modernos son archivos procedentes [OneDrive](/onedrive/plan-onedrive-enterprise#modern-attachments) o [SharePoint](/sharepoint/dev/solution-guidance/modern-experience-customizations) que se incluyen en Teams mensajes. El texto se extrae automáticamente de estos datos adjuntos para el procesamiento automatizado y posibles coincidencias con las condiciones y clasificadores de directivas de cumplimiento de comunicaciones activas. No hay ninguna configuración adicional necesaria para la detección y procesamiento de datos adjuntos modernos. El texto solo se extrae para datos adjuntos que coincidan con las condiciones de la directiva. El texto no se extrae para datos adjuntos de mensajes con coincidencias de directiva, incluso si los datos adjuntos también tienen una coincidencia de directiva.

El examen de datos adjuntos modernos es compatible con los siguientes tipos de archivo:

- Microsoft Word (.docx)
- Microsoft Excel (.xlsx)
- Microsoft PowerPoint (.pptx)
- Texto (.txt)
- Portable Document Format (.pdf)

El texto extraído para los datos adjuntos modernos se incluye con el mensaje asociado en el panel **de** alertas pendientes de una directiva. El texto extraído de un archivo adjunto se denomina nombre de archivo adjunto (y extensión de formato) y la extensión .txt datos adjuntos. Por ejemplo, el texto extraído de un archivo adjunto  denominado *ContosoBusinessPlan.docx* aparecería comoContosoBusinessPlan.docx.txten el panel de alertas pendientes de una directiva. 

Seleccione el texto de datos adjuntos extraído para ver los detalles en las vistas *Origen,* *Texto sin* formato o *Anotación.* Después de revisar, puede resolver o realizar acciones en el texto de datos adjuntos mediante los controles de la barra de comandos. También tiene la opción de descargar los datos adjuntos para su revisión fuera del proceso de revisión de cumplimiento de comunicaciones.

Use las siguientes configuraciones de administración de grupos para supervisar los chats de usuarios individuales y las comunicaciones de canal en Teams:

- **Para Teams de chat:** Asignar usuarios individuales o asignar un [grupo de distribución](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) a la directiva de cumplimiento de comunicaciones. Esta configuración es para relaciones de usuario/chat de uno a uno o de uno a varios.
- **Para Teams de canal:** Asigne cada Microsoft Teams canal o Microsoft 365 grupo que desee examinar que contenga un usuario específico a la directiva de cumplimiento de comunicaciones. Si agrega el mismo usuario a otros canales de Microsoft Teams o grupos de Microsoft 365, asegúrese de agregar estos nuevos canales y grupos a la directiva de cumplimiento de comunicaciones. Si algún miembro del canal es un usuario  supervisado dentro de una directiva y la dirección de entrada está configurada en una directiva, todos los mensajes enviados dentro del canal están sujetos a revisión y posibles coincidencias de directiva (incluso para los usuarios del canal que no están supervisados explícitamente). Por ejemplo, el usuario A es el propietario o miembro de un canal. Los usuarios B y C son miembros del mismo canal y usan un lenguaje que coincide con la directiva de contenido inadecuado que supervisa solo al usuario A. El usuario B y el usuario C crean coincidencias de directiva para las conversaciones dentro del canal aunque no estén supervisadas directamente en la directiva de contenido inadecuado. Teams conversaciones entre el usuario B y el usuario C que están fuera del canal que incluye el usuario A no estarían sujetas a la directiva de contenido inadecuado que incluye al usuario A. Para excluir a los miembros del canal de la supervisión cuando  otros miembros del canal se supervisan explícitamente, desactive la configuración Dirección de comunicación entrante en la directiva de cumplimiento de comunicaciones aplicable.
- Para Teams de chat con entornos de correo electrónico **híbridos:** el cumplimiento de las comunicaciones puede supervisar los mensajes de chat de los usuarios de organizaciones con una implementación local de Exchange o un proveedor de correo electrónico externo que haya Microsoft Teams. Debe crear un grupo de distribución para que los usuarios con buzones locales o externos supervisen. Al crear una directiva de cumplimiento de comunicaciones, asignará este grupo de distribución como la selección de usuarios y grupos supervisados en el asistente para directivas.  Para obtener más información acerca de los requisitos y limitaciones para habilitar el almacenamiento basado en la nube y la compatibilidad Teams para los usuarios locales, vea [Search for Teams chat data for on-premises users](search-cloud-based-mailboxes-for-on-premises-users.md).

## <a name="exchange-email"></a>Correo electrónico de Exchange

Los buzones hospedados en Exchange Online como parte de la Microsoft 365 o Office 365 suscripción son aptos para el examen de mensajes. Exchange mensajes de correo electrónico y datos adjuntos que coincidan con las condiciones de la directiva de cumplimiento de comunicaciones pueden tardar hasta 24 horas en procesarse. Los tipos de datos adjuntos admitidos para el cumplimiento de comunicaciones son los mismos que los [tipos de archivo admitidos en las inspecciones de contenido de reglas de flujo de correo de Exchange](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).

## <a name="yammer"></a>Yammer

Los mensajes privados y las conversaciones públicas y los datos adjuntos asociados en Yammer comunidades pueden examinarse. Cuando se agrega un usuario a la directiva de cumplimiento de comunicaciones que incluye Yammer como un canal definido, las comunicaciones en todas las comunidades de Yammer de las que el usuario es miembro se incluyen en el proceso de examen. Yammer chats y datos adjuntos que coincidan con las condiciones de la directiva de cumplimiento de comunicaciones pueden tardar hasta 24 horas en procesarse. 

Yammer estar en modo nativo para [que](/yammer/configure-your-yammer-network/overview-native-mode) las directivas de cumplimiento de comunicaciones supervisen Yammer comunicaciones y datos adjuntos. En el modo nativo, todos los usuarios de Yammer están en Azure Active Directory (AAD), todos los grupos son Grupos de Office 365 y todos los archivos se almacenan en SharePoint Online.

## <a name="skype-for-business-online"></a>Skype Empresarial Online

Las comunicaciones de chat y los datos adjuntos asociados en Skype Empresarial Online se pueden supervisar. Los chats de Skype Empresarial Online que coincidan con las condiciones de directiva de cumplimiento de comunicaciones pueden tardar hasta 24 horas en procesarse. Las conversaciones de chat supervisadas se orígenes de [conversaciones anteriores guardadas en Skype Empresarial Online](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2).  

Use la siguiente configuración de administración de grupos para supervisar las comunicaciones de chat de usuario en Skype Empresarial Online:

- **Para Skype Empresarial de chat** en línea: asigne usuarios individuales o asigne [un](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) grupo de distribución a la directiva de cumplimiento de comunicaciones. Esta configuración es para relaciones de usuario/chat de uno a uno o de uno a varios.

## <a name="third-party-sources"></a>Orígenes de terceros.

Puede examinar las comunicaciones en busca de datos importados en buzones de correo de su organización de Microsoft 365 desde orígenes de terceros como [Instant Bloomberg](archive-instant-bloomberg-data.md), [Slack,](archive-slack-data.md) [Zoom,](archive-zoommeetings-data.md)SMS y muchos otros. Para obtener una lista completa de conectores compatibles con el cumplimiento de comunicaciones, vea [Archivar datos de terceros](archiving-third-party-data.md).

Debe configurar un conector de terceros para su Microsoft 365 para poder asignar el conector a una directiva de cumplimiento de comunicaciones. La **sección Orígenes de terceros** del Asistente para directivas de cumplimiento de comunicaciones solo muestra los conectores de terceros configurados actualmente.
