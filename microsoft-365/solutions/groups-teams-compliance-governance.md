---
title: Opciones de cumplimiento para grupos de Microsoft 365, Teams y colaboración de SharePoint
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Obtenga información sobre las opciones de cumplimiento para grupos de Microsoft 365, Teams y colaboración de SharePoint.
ms.openlocfilehash: 428413ce876a1718f1237d3bce0d543aa5d47c62
ms.sourcegitcommit: cbb9a89499d42f4a029e18780bee408946e1671d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68026279"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Opciones de cumplimiento para grupos de Microsoft 365, Teams y colaboración de SharePoint

Microsoft 365 ofrece un conjunto completo de herramientas para mantener el cumplimiento a medida que los usuarios colaboran. Revise estas opciones y considere cómo se asignan a sus necesidades empresariales, la confidencialidad de los datos y el ámbito de las personas con las que los usuarios deben colaborar.

En la tabla siguiente se proporciona una referencia rápida para los controles de cumplimiento disponibles en Microsoft 365. En las secciones siguientes se proporciona más información.

|Categoría|Descripción|Referencia|
|:-------|:----------|:--------|
|Retención de información|||
||Conservar el correo de grupos y el contenido de SharePoint|[Más información sobre las directivas de retención para SharePoint y OneDrive](../compliance/retention-policies-sharepoint.md)|
||Conservar chat y mensajes|[Más información sobre las directivas de retención para Microsoft Teams](../compliance/retention-policies-teams.md)|
|Clasificación de información|||
||Clasificación de grupos y equipos|[Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Clasificación automática del contenido confidencial|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](../compliance/apply-sensitivity-label-automatically.md)|
||Cifrado de contenido confidencial|[Restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad para aplicar el cifrado](../compliance/encryption-sensitivity-labels.md)|
|Protección de la información|||
||Evitar la pérdida de información confidencial|[Información sobre la prevención de pérdida de datos de Microsoft Purview](../compliance/dlp-learn-about-dlp.md)|
||Proteja la información confidencial en el chat.|[Prevención de pérdida de datos de Microsoft Purview y Microsoft Teams](../compliance/dlp-microsoft-teams.md)|
||Definición de la información confidencial de la organización|[Tipos de información confidencial personalizados](../compliance/sensitive-information-type-learn-about.md)|
|Segmentación de usuarios|||
||Restricción de la comunicación entre segmentos de usuario|[Barreras de información](../compliance/information-barriers.md)|
|Residencia de datos|||
||Almacenamiento de datos en ubicaciones geográficas específicas|[Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)|

## <a name="information-retention"></a>Retención de información

Las directivas de retención están disponibles para conservar o eliminar elementos usados para la colaboración en grupos y equipos, incluidos archivos, mensajes y correo. Las directivas se pueden establecer para conservar y eliminar, solo para conservar o eliminar. La información cubierta por una directiva de retención está protegida en caso de que el grupo o equipo expire o se elimine de otro modo.

La configuración de una directiva de retención para Grupos de Microsoft 365 cubre el buzón de grupo y el sitio y los archivos de SharePoint asociados.

- [Más información sobre las directivas de retención para SharePoint y OneDrive](../compliance/retention-policies-sharepoint.md)

Las directivas de retención de Teams conservan mensajes de chat y canal. Aunque los mensajes de chat y de canal se almacenan en buzones de Exchange, no se ven afectados por las directivas de retención de Exchange. Debe establecer las directivas de retención para que se apliquen a los chats de Teams y a los mensajes de canal de Teams. 

Los chats de usuario se conservan indefinidamente incluso si se elimina una cuenta de usuario. Si no desea conservar estos datos indefinidamente, considere la posibilidad de usar una directiva de retención para eliminar chats de usuario después de un tiempo especificado o incluir esta eliminación en el proceso de eliminación de usuarios.

- [Más información sobre las directivas de retención para Microsoft Teams](../compliance/retention-policies-teams.md)

- [Directivas de retención en Microsoft Teams](/microsoftteams/retention-policies)

Se puede establecer una única directiva de retención para que se aplique a los mensajes de chat de Teams y de canal de Teams (incluidos los mensajes de canal compartido). Los mensajes de canal privado de Teams deben estar contenidos en su propia directiva de retención.

Recursos adicionales:

- [Información sobre las directivas de retención](../compliance/retention.md)

- [Etiquetas de retención y directivas de retención](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) en Exchange

## <a name="information-classification"></a>Clasificación de información

Puede usar etiquetas de confidencialidad para controlar el acceso de invitado, la privacidad de grupos y equipos, y el acceso por dispositivos no administrados para grupos y equipos. Al aplicar la etiqueta, esta configuración se configura automáticamente según lo especificado por la configuración de etiqueta.

- [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)

Puede configurar Microsoft 365 para aplicar automáticamente etiquetas de confidencialidad a archivos y correos electrónicos en función de los criterios que especifique, incluida la detección de tipos de información confidencial o la coincidencia de patrones con clasificadores entrenables.

- [Aplicar una etiqueta de confidencialidad automáticamente al contenido](../compliance/apply-sensitivity-label-automatically.md)

Puede usar etiquetas de confidencialidad para cifrar archivos, lo que permite que solo aquellos con permisos los descifren y lean.

- [Restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad para aplicar el cifrado](../compliance/encryption-sensitivity-labels.md)

- [Configuración de un equipo con aislamiento de seguridad](./secure-teams-security-isolation.md)

Recursos adicionales:

- [Información sobre las etiquetas de confidencialidad](../compliance/sensitivity-labels.md)


## <a name="information-protection"></a>Protección de la información

Las directivas DLP pueden impedir el uso compartido accidental de información confidencial entre SharePoint, Exchange y Teams. Puede crear directivas que especifiquen las acciones que se van a realizar (como bloquear el acceso) en función de un conjunto de reglas.

- [Obtenga más información acerca de la prevención contra la pérdida de datos](../compliance/dlp-learn-about-dlp.md)

DLP en Teams puede ayudar a proteger la información confidencial en los mensajes de chat y canal de Teams mediante la eliminación de mensajes que contienen información confidencial.

- [Prevención de pérdida de datos y Microsoft Teams](../compliance/dlp-microsoft-teams.md).

Si tiene información confidencial exclusiva de su organización, como nombres de código de proyecto, puede crear sus propios tipos de información confidencial y aplicarlos a directivas DLP para proteger el contenido en grupos, equipos y SharePoint.

- [Tipos de información confidencial personalizados](../compliance/sensitive-information-type-learn-about.md)

## <a name="user-segmentation"></a>Segmentación de usuarios

Con las barreras de información, puede segmentar los datos y los usuarios para restringir la comunicación y la colaboración no deseadas entre grupos y evitar conflictos de interés en su organización. Las barreras de información permiten crear directivas para permitir o impedir la colaboración de archivos, el chat, las llamadas o las invitaciones a reuniones entre grupos de personas de la organización.

- [Barreras de información](../compliance/information-barriers.md)

- [Barreras de información en Microsoft Teams](/microsoftteams/information-barriers-in-teams)

- [Usar barreras de información con SharePoint](/sharepoint/information-barriers)

## <a name="data-residency"></a>Residencia de datos

Con Microsoft 365 Multi-Geo, puede aprovisionar y almacenar datos en reposo en las ubicaciones geográficas que ha elegido para cumplir los requisitos de residencia de datos. En un entorno multigeográfico, el inquilino de Microsoft 365 consta de una ubicación central (donde se aprovisionó originalmente la suscripción de Microsoft 365) y una o varias ubicaciones satélite donde puede almacenar datos.

- [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)

- [Plan para Microsoft 365 Multi-Geo](/microsoft-365/enterprise/plan-for-multi-geo)

## <a name="related-topics"></a>Temas relacionados

[Guía de seguridad y cumplimiento de Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

[Recomendaciones de planeamiento de gobernanza de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[Creación del plan de gobernanza de colaboración](collaboration-governance-first.md)

[Seguridad y cumplimiento de Exchange Online](/exchange/security-and-compliance/security-and-compliance)

[Proteger la información](../compliance/information-protection.md)
