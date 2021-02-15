---
title: Opciones de cumplimiento para grupos de Microsoft 365, Teams y colaboración de SharePoint
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
description: Obtenga información sobre las opciones de cumplimiento para grupos de Microsoft 365, Teams y colaboración de SharePoint.
ms.openlocfilehash: e1ca6e638b2d44ae3b04e2a0f13222424e89714d
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613635"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Opciones de cumplimiento para grupos de Microsoft 365, Teams y colaboración de SharePoint

Microsoft 365 ofrece un conjunto completo de herramientas para mantener el cumplimiento a medida que los usuarios colaboran. Revise estas opciones y tenga en cuenta cómo se asignan a sus necesidades empresariales, la confidencialidad de los datos y el ámbito de las personas con las que los usuarios necesitan colaborar.

En la tabla siguiente se proporciona una referencia rápida para los controles de cumplimiento disponibles en Microsoft 365. En las secciones siguientes se proporciona más información.

|Categoría|Description|Referencia|
|:-------|:----------|:--------|
|Retención de información|||
||Conservar el correo de grupos y el contenido de SharePoint|[Más información sobre las directivas de retención para SharePoint y OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)|
||Conservar el chat y los mensajes|[Más información sobre las directivas de retención para Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)|
|Clasificación de la información|||
||Clasificar grupos y equipos|[Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Clasificar automáticamente contenido confidencial|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)|
||Cifrar contenido confidencial|[Restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad para aplicar el cifrado](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)|
|Protección de la información|||
||Evitar la pérdida de información confidencial|[Información general sobre la prevención de pérdida de datos](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|
||Proteger la información confidencial en el chat.|[Prevención de pérdida de datos y Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)|
||Definir la información confidencial de su organización|[Tipos de información confidencial personalizados](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)|
|Segmentación de usuarios|||
||Restringir la comunicación entre segmentos de usuario|[Barreras de información](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)|

## <a name="information-retention"></a>Retención de información

Las directivas de retención están disponibles para retener o eliminar elementos usados para la colaboración en grupos y equipos, incluidos archivos, mensajes y correo. Las directivas se pueden establecer para retener y eliminar, solo retener o eliminar solo. La información cubierta por una directiva de retención está protegida en caso de que el grupo o equipo expire o se elimine de otro modo.

La configuración de una directiva de retención para Grupos de Microsoft 365 abarca el buzón de grupo y el sitio y los archivos de SharePoint asociados.

- [Más información sobre las directivas de retención para SharePoint y OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)

Las directivas de retención para Teams conservan los mensajes de canal y chat. Aunque los mensajes de chat y canal se almacenan en buzones de Exchange, no se ven afectados por las directivas de retención de Exchange. Debe establecer las directivas de retención para que se apliquen a los chats de Teams y a los mensajes de canal de Teams:

- [Más información sobre las directivas de retención para Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

- [Directivas de retención en Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies)

Se puede establecer una única directiva de retención para que se aplique a los mensajes de los grupos de Microsoft 365, el chat de Teams y el canal de Teams. 

Recursos adicionales:

- [Información sobre las directivas de retención](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

- [Etiquetas de retención y directivas de retención](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) en Exchange

## <a name="information-classification"></a>Clasificación de la información

Puede usar etiquetas de confidencialidad para gobernar el acceso de invitados, la privacidad de grupos y equipos, y el acceso mediante dispositivos no administrados para grupos y equipos. Al aplicar la etiqueta, estas opciones se configuran automáticamente según lo especificado por la configuración de la etiqueta.

- [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Puede configurar Microsoft 365 para aplicar automáticamente etiquetas de confidencialidad a archivos y correos electrónicos según los criterios que especifique, incluida la detección de tipos de información confidencial o la coincidencia de patrones con clasificadores que se pueden entrenar.

- [Aplicar una etiqueta de confidencialidad automáticamente al contenido](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

Puede usar etiquetas de confidencialidad para cifrar archivos, lo que permite que solo los usuarios con permisos los descifren y lean.

- [Restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad para aplicar el cifrado](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

- [Configurar un equipo con aislamiento de seguridad](https://docs.microsoft.com/microsoft-365/solutions/secure-teams-security-isolation)

Recursos adicionales:

- [Información sobre las etiquetas de confidencialidad](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)


## <a name="information-protection"></a>Protección de la información

Las directivas DLP pueden evitar el uso compartido accidental de información confidencial en SharePoint, Exchange y Teams. Puede crear directivas que especifiquen acciones que se deben realizar (como bloquear el acceso) en función de un conjunto de reglas.

- [Información general sobre la prevención de pérdida de datos](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

DLP en Teams puede ayudar a proteger la información confidencial en los mensajes de canal y chat de Teams mediante la eliminación de mensajes que contienen información confidencial.

- [Prevención de pérdida de datos y Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)

Si tiene información confidencial exclusiva de su organización, como nombres de código de proyecto, puede crear sus propios tipos de información confidencial y aplicarlos a las directivas DLP para proteger el contenido en grupos, equipos y SharePoint.

- [Tipos de información confidencial personalizados](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)

## <a name="user-segmentation"></a>Segmentación de usuarios

Con las barreras de información, puede segmentar los datos y los usuarios para restringir la comunicación no deseada y la colaboración entre grupos y evitar conflictos de interés en su organización. Las barreras de información le permiten crear directivas para permitir o impedir la colaboración de archivos, chatear, llamar o invitar a reuniones entre grupos de personas de su organización.

- [Barreras de información](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

- [Barreras de información en Microsoft Teams](https://docs.microsoft.com/microsoftteams/information-barriers-in-teams)

- [Usar barreras de información con SharePoint](https://docs.microsoft.com/sharepoint/information-barriers)

## <a name="related-topics"></a>Temas relacionados

[Planeación paso a paso de gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear un plan de gobierno de colaboración](collaboration-governance-first.md)

[Seguridad y cumplimiento de Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance)

[Proteger la información](https://docs.microsoft.com/microsoft-365/compliance/protect-information)
