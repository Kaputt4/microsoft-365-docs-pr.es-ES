---
title: Opciones de cumplimiento para grupos de Microsoft 365, teams y colaboración de SharePoint
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
ms.openlocfilehash: f68381ab45e74b9b7c8f44465387add82bd4150a
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838656"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Opciones de cumplimiento para grupos de Microsoft 365, teams y colaboración de SharePoint

Microsoft 365 ofrece un conjunto completo de herramientas para mantener el cumplimiento conforme colaboran los usuarios. Revisa estas opciones y considera cómo se asignan a las necesidades de tu empresa, la confidencialidad de los datos y el ámbito de las personas con las que los usuarios necesitan colaborar.

En la tabla siguiente se proporciona una referencia rápida para los controles de cumplimiento disponibles en Microsoft 365. Se proporciona más información en las secciones siguientes.

|Categoría|Description|Referencia|
|:-------|:----------|:--------|
|Retención de información|||
||Retener el correo de grupos y el contenido de SharePoint|[Más información sobre las directivas de retención para SharePoint y OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)|
||Retener chat y mensajes|[Más información sobre las directivas de retención para Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)|
|Clasificación de información|||
||Clasificar grupos y equipos|[Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Clasificar automáticamente contenido confidencial|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)|
||Cifrar contenido confidencial|[Restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad para aplicar el cifrado](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)|
|Protección de la información|||
||Evitar la pérdida de información confidencial|[Información general sobre la prevención de pérdida de datos](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|
||Proteger la información confidencial en el chat.|[Prevención de pérdida de datos y Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)|
||Definir la información confidencial de la organización|[Tipos de información confidencial personalizados](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)|
|Segmentación de usuarios|||
||Restringir la comunicación entre segmentos de usuario|[Barreras de información](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)|

## <a name="information-retention"></a>Retención de información

Las directivas de retención están disponibles para retener o eliminar elementos usados para la colaboración en grupos y equipos, incluidos archivos, mensajes y correo. Las directivas se pueden establecer para conservar y eliminar, para conservar solo o eliminar solo. La información cubierta por una directiva de retención está protegida en caso de que el grupo o equipo expire o se elimine de otro modo.

La configuración de una directiva de retención para grupos de Microsoft 365 abarca el buzón de grupo y el sitio y los archivos de SharePoint asociados.

- [Más información sobre las directivas de retención para SharePoint y OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)

Las directivas de retención de Teams retienen mensajes de chat y canal. Mientras que los mensajes de chat y canal se almacenan en buzones de Exchange, las directivas de retención de Exchange no les afectan. Debe establecer las directivas de retención para que se apliquen a los chats de Teams y los mensajes de canal de Teams. 

Los chats de usuario se conservan indefinidamente incluso si se elimina una cuenta de usuario. Si no desea conservar estos datos indefinidamente, considere la posibilidad de usar una directiva de retención para eliminar chats de usuario después de un tiempo especificado o incluir esta eliminación en el proceso de eliminación de usuarios.

- [Más información sobre las directivas de retención para Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

- [Directivas de retención en Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies)

Se puede establecer una única directiva de retención para que se aplique a los mensajes de canal de Microsoft 365, chat de Teams y Grupos de Microsoft 365. 

Recursos adicionales:

- [Información sobre las directivas de retención](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

- [Etiquetas de retención y directivas de retención](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) en Exchange

## <a name="information-classification"></a>Clasificación de información

Puede usar etiquetas de confidencialidad para administrar el acceso de invitados, la privacidad de grupos y equipos y el acceso mediante dispositivos no administrados para grupos y equipos. Al aplicar la etiqueta, estas opciones se configuran automáticamente según lo especificado por la configuración de la etiqueta.

- [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Puede configurar Microsoft 365 para aplicar automáticamente etiquetas de confidencialidad a archivos y correos electrónicos según los criterios que especifique, incluida la detección de tipos de información confidencial o la coincidencia de patrones con clasificadores entrenables.

- [Aplicar una etiqueta de confidencialidad automáticamente al contenido](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

Puede usar etiquetas de confidencialidad para cifrar archivos, lo que permite que solo los que tienen permisos los descifran y los lean.

- [Restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad para aplicar el cifrado](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

- [Configuración de un equipo con aislamiento de seguridad](https://docs.microsoft.com/microsoft-365/solutions/secure-teams-security-isolation)

Recursos adicionales:

- [Información sobre las etiquetas de confidencialidad](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)


## <a name="information-protection"></a>Protección de la información

Las directivas DLP pueden impedir el uso compartido accidental de información confidencial en SharePoint, Exchange y Teams. Puede crear directivas que especifiquen acciones que deben realizarse (como bloquear el acceso) en función de un conjunto de reglas.

- [Información general sobre la prevención de pérdida de datos](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

DLP en Teams puede ayudar a proteger la información confidencial en los mensajes de canal y chat de Teams mediante la eliminación de mensajes que contienen información confidencial.

- [Prevención de pérdida de datos y Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)

Si tiene información confidencial que es exclusiva de su organización, como nombres de código de proyecto, puede crear sus propios tipos de información confidencial y aplicarlos a directivas DLP para proteger el contenido en grupos, equipos y Sharepoint.

- [Tipos de información confidencial personalizados](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)

## <a name="user-segmentation"></a>Segmentación de usuarios

Con las barreras de información, puede segmentar los datos y los usuarios para restringir la comunicación no deseada y la colaboración entre grupos y evitar conflictos de interés en su organización. Las barreras de información le permiten crear directivas para permitir o impedir la colaboración de archivos, el chat, las llamadas o las invitaciones a reuniones entre grupos de personas de la organización.

- [Barreras de información](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

- [Barreras de información en Microsoft Teams](https://docs.microsoft.com/microsoftteams/information-barriers-in-teams)

- [Usar barreras de información con SharePoint](https://docs.microsoft.com/sharepoint/information-barriers)

## <a name="related-topics"></a>Temas relacionados

[Planeación paso a paso de gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear el plan de gobierno de colaboración](collaboration-governance-first.md)

[Seguridad y cumplimiento para Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance)

[Proteger la información](https://docs.microsoft.com/microsoft-365/compliance/protect-information)
