---
title: Obtenga información sobre el panel de alertas de prevención de pérdida de datos
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre las alertas de prevención de pérdida de datos y el panel de alertas.
ms.openlocfilehash: b6fd698e535e006149f6ce3a2a5bc57d0c92c7e2
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760778"
---
# <a name="learn-about-the-data-loss-prevention-alerts-dashboard"></a>Obtenga información sobre el panel de alertas de prevención de pérdida de datos

Cuando los criterios de una directiva de prevención de pérdida de datos (DLP) coinciden con las acciones que un usuario está llevando a cabo en un elemento confidencial, la directiva puede generar una alerta. Esto puede provocar un gran volumen de alertas. Las alertas DLP se recopilan en el panel de alertas. El panel de alertas le ofrece un único lugar donde ir para realizar una investigación exhaustiva de todos los detalles relacionados con la coincidencia de directiva.  

<!-- [Microsoft 365 compliance center](https://compliance.microsoft.com/)-->

## <a name="workloads"></a>Cargas de trabajo

El [panel de administración de alertas DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts), en el centro de Microsoft 365 [cumplimiento,](https://compliance.microsoft.com/)muestra alertas para directivas DLP en estas cargas de trabajo:

- Exchange
- SharePoint
- OneDrive
- Teams
- Dispositivos con Windows 10 

> [!TIP]
> Los clientes que usan [DLP](endpoint-dlp-learn-about.md) de extremo que son elegibles para [Teams DLP](dlp-microsoft-teams.md) verán sus alertas de directiva DLP de punto de conexión y Teams de directivas DLP en el panel de administración de alertas dlp.

## <a name="single-alert-and-aggregate-alert"></a>Alerta única y alerta agregada

Hay dos tipos de alertas que se pueden configurar en directivas DLP.

 Las alertas de evento único suelen usarse en directivas que supervisan eventos altamente confidenciales que se producen en un volumen bajo, como un solo correo electrónico con 10 o más números de tarjeta de crédito de cliente que se envían fuera de la organización.

**Normalmente, las alertas** de eventos agregados se usan en directivas que supervisan eventos que se producen en un volumen mayor durante un período de tiempo. Por ejemplo, se puede desencadenar una alerta agregada cuando 10 correos electrónicos individuales cada uno con un número de tarjeta de crédito de cliente se envían fuera de su organización durante 48 horas.

## <a name="types-of-events"></a>Tipos de eventos

Estos son algunos de los eventos asociados con una alerta. En la interfaz de usuario, puedes elegir un evento en particular para ver sus detalles. 

### <a name="event-details"></a>Detalles del evento

|Nombre de propiedad  |Descripción  |Tipos de eventos  |
|---------|---------|---------|
|ID |id. único asociado con el evento |todos los eventos |
|Ubicación |carga de trabajo donde se detectó el evento|todos los eventos |
|tiempo de actividad     |tiempo de la actividad del usuario que coincide con los criterios de la directiva DLP |

### <a name="impacted-entities"></a>Entidades afectadas

|Nombre de propiedad |Descripción| Tipos de eventos|
|---------|---------|---------|
|Usuario | usuario que realizó la acción que causó la coincidencia de la directiva | todos los eventos|
|nombre de host | nombre de host del equipo donde se produjo la coincidencia de directiva DLP | eventos de dispositivo|
|Dirección IP | Dirección IP del equipo donde se produjo la coincidencia de directiva DLP | eventos de dispositivo|
|sha1 |Hash SHA-1 del archivo | eventos de dispositivo|
|sha256 | Hash SHA-256 del archivo | eventos de dispositivo|
|MDATP de dispositivo | identificador de dispositivo de MDATP extremo|
|tamaño de archivo | tamaño del archivo| SharePoint, OneDrive y eventos de dispositivo|
|ruta de acceso del archivo | la ruta de acceso absoluta del elemento implicado con la coincidencia de directiva DLP | SharePoint, OneDrive y eventos de dispositivos|
|destinatarios de correo electrónico |si un correo electrónico era el elemento confidencial que coincidía con la directiva DLP, este campo incluye los destinatarios de ese correo electrónico| Exchange eventos|
|asunto del correo electrónico |asunto del correo electrónico que coincide con la directiva DLP |Exchange eventos|
|datos adjuntos de correo electrónico | nombres de los datos adjuntos del correo electrónico que coinciden con la directiva DLP| Exchange eventos|
|propietario del sitio |nombre del propietario del sitio| SharePoint y OneDrive eventos|
|URL del sitio |completa de la dirección URL del sitio SharePoint o OneDrive donde se produjo la coincidencia de directiva DLP |SharePoint y OneDrive eventos|
|archivo creado |tiempo de creación del archivo que coincide con la directiva DLP |SharePoint y OneDrive eventos|
|archivo modificado por última vez | la última vez que se cambió el archivo que coincidía con la directiva DLP | SharePoint y OneDrive eventos|
|tamaño de archivo | tamaño del archivo que coincide con la directiva DLP |SharePoint y OneDrive eventos|
|propietario del archivo |propietario del archivo que coincide con la directiva DLP |SharePoint y OneDrive eventos|  

### <a name="policy-details"></a>Detalles de la directiva

|Nombre de propiedad |Descripción |Tipos de eventos |
|---------|---------|---------|
|Directiva DLP coincidente |nombre de la directiva DLP coincidente |todos los eventos|
|regla coincidente |nombre de la regla de directiva DLP coincidente |todos los eventos|
|tipos de información confidencial (SIT) detectados|SIT detectados como parte de la coincidencia de directiva DLP |todos los eventos|
|acciones realizadas |acciones realizadas que provocaron la coincidencia de la directiva DLP| todos los eventos|
|acción de vulneración | acción en el dispositivo de extremo que ha elevado la alerta DLP| eventos de dispositivo | 
|directiva de sobreestrobado de usuarios |¿Invalidó el usuario la directiva a través de una sugerencia de directiva? | todos los eventos|
|usar justificación de invalidación |el texto del motivo proporcionado por el usuario para la invalidación | todos los eventos|   

## <a name="see-also"></a>Consulte también

- [Introducción al panel de alertas de prevención de pérdida de datos](dlp-alerts-dashboard-get-started.md)
- [Dónde empezar con la prevención de pérdida de datos](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)