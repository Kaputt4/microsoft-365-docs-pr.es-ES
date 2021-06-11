---
title: Opciones de cumplimiento para Microsoft 365 grupos, Teams y SharePoint colaboración
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
recommendations: false
description: Obtenga información sobre las opciones de cumplimiento para Microsoft 365 grupos, Teams y SharePoint colaboración.
ms.openlocfilehash: 236b977b22066830e1b36bc87676fd5fa2c9d3f5
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538128"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Opciones de cumplimiento para Microsoft 365 grupos, Teams y SharePoint colaboración

Microsoft 365 ofrece un conjunto completo de herramientas para mantener el cumplimiento conforme colaboran los usuarios. Revisa estas opciones y considera cómo se asignan a las necesidades de tu empresa, la confidencialidad de los datos y el ámbito de las personas con las que los usuarios necesitan colaborar.

En la tabla siguiente se proporciona una referencia rápida para los controles de cumplimiento disponibles en Microsoft 365. Se proporciona más información en las secciones siguientes.

|Categoría|Descripción|Referencia|
|:-------|:----------|:--------|
|Retención de información|||
||Retener el correo de grupos y SharePoint contenido|[Más información sobre las directivas de retención para SharePoint y OneDrive](../compliance/retention-policies-sharepoint.md)|
||Retener chat y mensajes|[Más información sobre las directivas de retención para Microsoft Teams](../compliance/retention-policies-teams.md)|
|Clasificación de información|||
||Clasificar grupos y equipos|[Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Clasificar automáticamente contenido confidencial|[Aplicar una etiqueta de confidencialidad automáticamente al contenido](../compliance/apply-sensitivity-label-automatically.md)|
||Cifrar contenido confidencial|[Restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad para aplicar el cifrado](../compliance/encryption-sensitivity-labels.md)|
|Protección de la información|||
||Evitar la pérdida de información confidencial|[Obtenga más información acerca de la prevención contra la pérdida de datos](../compliance/dlp-learn-about-dlp.md)|
||Proteger la información confidencial en el chat.|[Prevención de pérdida de datos y Microsoft Teams](../compliance/dlp-microsoft-teams.md).|
||Definir la información confidencial de la organización|[Tipos de información confidencial personalizados](../compliance/sensitive-information-type-learn-about.md)|
|Segmentación de usuarios|||
||Restringir la comunicación entre segmentos de usuario|[Barreras de información](../compliance/information-barriers.md)|
|Residencia de datos|||
||Almacenar datos en ubicaciones geográficas específicas|[Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)|

## <a name="information-retention"></a>Retención de información

Las directivas de retención están disponibles para retener o eliminar elementos usados para la colaboración en grupos y equipos, incluidos archivos, mensajes y correo. Las directivas se pueden establecer para conservar y eliminar, para conservar solo o eliminar solo. La información cubierta por una directiva de retención está protegida en caso de que el grupo o equipo expire o se elimine de otro modo.

La configuración de una directiva de retención para grupos Microsoft 365 incluye el buzón de grupo y los archivos SharePoint sitio y archivos asociados.

- [Más información sobre las directivas de retención para SharePoint y OneDrive](../compliance/retention-policies-sharepoint.md)

Las directivas de retención Teams mensajes de chat y canal. Mientras que los mensajes de chat y canal se almacenan Exchange buzones de correo, no se ven afectados por las directivas Exchange retención. Debe establecer las directivas de retención para que se apliquen a Teams chats y Teams mensajes de canal. 

Los chats de usuario se conservan indefinidamente incluso si se elimina una cuenta de usuario. Si no desea conservar estos datos indefinidamente, considere la posibilidad de usar una directiva de retención para eliminar chats de usuario después de un tiempo especificado o incluir esta eliminación en el proceso de eliminación de usuarios.

- [Más información sobre las directivas de retención para Microsoft Teams](../compliance/retention-policies-teams.md)

- [Directivas de retención en Microsoft Teams](/microsoftteams/retention-policies)

Se puede establecer una única directiva de retención para que se aplique Teams chat y Teams mensajes de canal. 

Recursos adicionales:

- [Información sobre las directivas de retención](../compliance/retention.md)

- [Etiquetas de retención y directivas de](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) retención en Exchange

## <a name="information-classification"></a>Clasificación de información

Puede usar etiquetas de confidencialidad para administrar el acceso de invitados, la privacidad de grupos y equipos y el acceso mediante dispositivos no administrados para grupos y equipos. Al aplicar la etiqueta, estas opciones se configuran automáticamente según lo especificado por la configuración de la etiqueta.

- [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)

Puede configurar Microsoft 365 para aplicar automáticamente etiquetas de confidencialidad a archivos y correos electrónicos en función de los criterios que especifique, incluida la detección de tipos de información confidencial o la coincidencia de patrones con clasificadores entrenables.

- [Aplicar una etiqueta de confidencialidad automáticamente al contenido](../compliance/apply-sensitivity-label-automatically.md)

Puede usar etiquetas de confidencialidad para cifrar archivos, lo que permite que solo los que tienen permisos los descifran y los lean.

- [Restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad para aplicar el cifrado](../compliance/encryption-sensitivity-labels.md)

- [Configurar un equipo con aislamiento de seguridad](./secure-teams-security-isolation.md)

Recursos adicionales:

- [Información sobre las etiquetas de confidencialidad](../compliance/sensitivity-labels.md)


## <a name="information-protection"></a>Protección de la información

Las directivas DLP pueden impedir el uso compartido accidental de información confidencial entre SharePoint, Exchange y Teams. Puede crear directivas que especifiquen acciones que deben realizarse (como bloquear el acceso) en función de un conjunto de reglas.

- [Obtenga más información acerca de la prevención contra la pérdida de datos](../compliance/dlp-learn-about-dlp.md)

DLP en Teams puede ayudar a proteger la información confidencial en Teams mensajes de chat y canal mediante la eliminación de mensajes que contienen información confidencial.

- [Prevención de pérdida de datos y Microsoft Teams](../compliance/dlp-microsoft-teams.md).

Si tiene información confidencial que es exclusiva de su organización, como nombres de código de proyecto, puede crear sus propios tipos de información confidencial y aplicarlos a directivas DLP para proteger el contenido en grupos, equipos y Sharepoint.

- [Tipos de información confidencial personalizados](../compliance/sensitive-information-type-learn-about.md)

## <a name="user-segmentation"></a>Segmentación de usuarios

Con las barreras de información, puede segmentar los datos y los usuarios para restringir la comunicación no deseada y la colaboración entre grupos y evitar conflictos de interés en su organización. Las barreras de información le permiten crear directivas para permitir o impedir la colaboración de archivos, el chat, las llamadas o las invitaciones a reuniones entre grupos de personas de la organización.

- [Barreras de información](../compliance/information-barriers.md)

- [Barreras de información en Microsoft Teams](/microsoftteams/information-barriers-in-teams)

- [Usar barreras de información con SharePoint](/sharepoint/information-barriers)

## <a name="data-residency"></a>Residencia de datos

Con Microsoft 365 Multi-Geo, puede aprovisionar y almacenar datos en reposo en las ubicaciones geográficas que haya elegido para cumplir los requisitos de residencia de datos. En un entorno multigeómico, el inquilino de Microsoft 365 consta de una ubicación central (donde se aprovisionó originalmente la suscripción Microsoft 365) y una o más ubicaciones satélite donde puede almacenar datos.

- [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)

- [Plan para Microsoft 365 Multi-Geo](/microsoft-365/enterprise/plan-for-multi-geo)

## <a name="related-topics"></a>Temas relacionados

[Planeación paso a paso de gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear el plan de gobierno de colaboración](collaboration-governance-first.md)

[Seguridad y cumplimiento de Exchange Online](/exchange/security-and-compliance/security-and-compliance)

[Proteger la información](../compliance/information-protection.md)
