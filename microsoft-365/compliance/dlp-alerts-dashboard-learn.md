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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
description: Obtenga información sobre las alertas de prevención de pérdida de datos y el panel de alertas.
ms.openlocfilehash: 375b16a3072f40ef8f366f7c1c4e8f714f195d63
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754378"
---
# <a name="learn-about-the-data-loss-prevention-alerts-dashboard"></a>Obtenga información sobre el panel de alertas de prevención de pérdida de datos

Cuando los criterios de una directiva de prevención de pérdida de datos (DLP) coinciden con las acciones que un usuario está llevando a cabo en un elemento confidencial, la directiva puede generar una alerta. Esta situación puede provocar un gran volumen de alertas. Las alertas DLP se recopilan en el panel de alertas. El panel de alertas le ofrece un único lugar para realizar una investigación exhaustiva de todos los detalles sobre la coincidencia de directivas.  

<!-- [Microsoft 365 compliance center](https://compliance.microsoft.com/)-->

## <a name="workloads"></a>Cargas de trabajo

El [panel de administración de alertas DLP,](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Centro de cumplimiento de Microsoft 365</a>, muestra alertas para directivas DLP en estas cargas de trabajo:

- Exchange
- SharePoint
- OneDrive
- Teams
- Dispositivos con Windows 10 

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

### <a name="affected-entities"></a>Entidades afectadas

|Nombre de propiedad |Descripción| Tipos de eventos|
|---------|---------|---------|
|usuario | usuario que realizó la acción que causó la coincidencia de la directiva | todos los eventos|
|nombre de host | nombre de host del equipo donde se produjo la coincidencia de directiva DLP | eventos de dispositivo|
|Dirección IP | Dirección IP del equipo donde se produjo la coincidencia de directiva DLP | eventos de dispositivo|
|sha1 |Hash SHA-1 del archivo | eventos de dispositivo|
|sha256 | Hash SHA-256 del archivo | eventos de dispositivo|
|Id. de dispositivo MDATP | Id. MDATP del dispositivo de extremo|
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
