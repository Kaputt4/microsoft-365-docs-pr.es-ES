---
title: Opciones de cumplimiento para Microsoft 365 Groups, Teams y SharePoint Collaboration
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Obtenga información sobre las opciones de cumplimiento para Microsoft 365 Groups, Teams y SharePoint Collaboration.
ms.openlocfilehash: 0383b0728d9b8ea12ce75de8bf0e250932d14ae5
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377538"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Opciones de cumplimiento para Microsoft 365 Groups, Teams y SharePoint Collaboration

Microsoft 365 ofrece un conjunto completo de herramientas para mantener el cumplimiento a medida que los usuarios colaboran. Revise estas opciones y considere cómo se asignan a las necesidades de su empresa, la confidencialidad de sus datos y el ámbito de las personas con las que deben colaborar los usuarios.

En la tabla siguiente se proporciona una referencia rápida para los controles de cumplimiento disponibles en Microsoft 365. En las siguientes secciones se proporciona información adicional.

|Categoría|Description|Referencia|
|:-------|:----------|:--------|
|Retención de la información|||
||Conservar los grupos de contenido de correo y SharePoint|[Más información sobre las directivas de retención para SharePoint y OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)|
||Conservar chat y mensajes|[Más información sobre las directivas de retención para Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)|
|Clasificación de la información|||
||Clasificación de grupos y equipos|[Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Clasificar automáticamente el contenido confidencial|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)|
||Cifrar contenido confidencial|[Restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad para aplicar el cifrado](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)|
|Protección de la información|||
||Evitar la pérdida de información confidencial|[Información general sobre la prevención de pérdida de datos](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|
||Proteger información confidencial en el chat.|[Prevención de pérdida de datos y Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)|
||Definir la información confidencial de la organización|[Tipos de información confidencial personalizados](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)|
|Segmentación de usuarios|||
||Restringir la comunicación entre segmentos de usuario|[Barreras de información](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)|

## <a name="information-retention"></a>Retención de la información

Las directivas de retención están disponibles para conservar o eliminar los elementos usados para la colaboración en grupos y equipos, incluidos archivos, mensajes y correo. Las directivas se pueden definir para retener y eliminar, sólo para retener o eliminar. La información que cubre una directiva de retención está protegida en el caso de que el grupo o el equipo expiren o se eliminen de otro modo.

La configuración de una directiva de retención para los grupos de Microsoft 365 cubre el buzón de grupo y los archivos y el sitio de SharePoint asociados.

- [Más información sobre las directivas de retención para SharePoint y OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)

Las directivas de retención para equipos retienen los mensajes de chat y de canal. Mientras los mensajes de chat y de canal se almacenan en buzones de Exchange, no se ven afectados por las directivas de retención de Exchange. Debe establecer las directivas de retención que se aplicarán a los chats de Microsoft Teams y los mensajes del canal de Teams:

- [Más información sobre las directivas de retención para Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

- [Directivas de retención en Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies)

Se puede configurar una única directiva de retención para aplicarla a los grupos de Microsoft 365, a los chats de Teams y a los mensajes de canal de Microsoft Teams. 

Recursos adicionales:

- [Información sobre las directivas de retención](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

- [Etiquetas de retención y directivas de retención](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) en Exchange

## <a name="information-classification"></a>Clasificación de la información

Puede usar las etiquetas de confidencialidad para controlar el acceso de invitado, privacidad de grupo y equipo, y tener acceso a los dispositivos no administrados de grupos y equipos. Mediante la aplicación de la etiqueta, estas opciones se configuran automáticamente según lo especificado en la configuración de las etiquetas.

- [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Puede configurar Microsoft 365 para aplicar automáticamente las etiquetas de confidencialidad a los archivos y los correos electrónicos en función de los criterios especificados, incluida la detección de tipos de información confidencial o la coincidencia de patrones con clasificadores que se puedan entrenar.

- [Aplicar una etiqueta de confidencialidad automáticamente al contenido](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

Puede usar las etiquetas de confidencialidad para cifrar archivos, lo que permite que solo los usuarios con permisos puedan descifrarlos y leerlos.

- [Restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad para aplicar el cifrado](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

- [Configuración de un equipo con aislamiento de seguridad](https://docs.microsoft.com/microsoft-365/solutions/secure-teams-security-isolation)

Recursos adicionales:

- [Más información sobre las etiquetas de confidencialidad](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)


## <a name="information-protection"></a>Protección de la información

Las directivas de DLP pueden impedir el uso compartido accidental de información confidencial a través de SharePoint, Exchange y Teams. Puede crear directivas que especifiquen las acciones que se van a realizar (como bloquear el acceso) basándose en un conjunto de reglas.

- [Información general sobre la prevención de pérdida de datos](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

DLP en Microsoft Teams puede ayudar a proteger la información confidencial en los mensajes de chat y canales del equipo al eliminar mensajes que contienen información confidencial.

- [Prevención de pérdida de datos y Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)

Si tiene información confidencial que es única para su organización, como los nombres de código de proyecto, puede crear sus propios tipos de información confidencial y aplicarlos a las directivas de DLP para proteger el contenido en grupos, equipos y SharePoint.

- [Tipos de información confidencial personalizados](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)

## <a name="user-segmentation"></a>Segmentación de usuarios

Con las barreras de la información, puede segmentar los datos y los usuarios para restringir la comunicación y la colaboración no deseadas entre grupos y evitar conflictos de intereses en la organización. Barreras de información le permite crear directivas para permitir o impedir la colaboración de archivos, el chat, las llamadas o las invitaciones a reuniones entre grupos de personas de su organización.

- [Barreras de información](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

- [Barreras de la información en Microsoft Teams](https://docs.microsoft.com/microsoftteams/information-barriers-in-teams)

- [Usar barreras de la información con SharePoint](https://docs.microsoft.com/sharepoint/information-barriers)

## <a name="related-topics"></a>Temas relacionados

[Seguridad y cumplimiento de Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance)

[Proteger la información](https://docs.microsoft.com/microsoft-365/compliance/protect-information)


