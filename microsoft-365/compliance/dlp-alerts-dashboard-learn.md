---
title: Más información sobre el panel de alertas DLP
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
ms.openlocfilehash: 1551b247e3302af6dc8ed9af62a88f2c24415122
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66636169"
---
# <a name="learn-about-the-data-loss-prevention-alerts-dashboard"></a>Obtenga información sobre el panel de alertas de prevención de pérdida de datos

Cuando los criterios de una directiva de Prevención de pérdida de datos de Microsoft Purview (DLP) coinciden con las acciones que un usuario está realizando en un elemento confidencial, la directiva puede generar una alerta. Esta situación puede dar lugar a un gran volumen de alertas. Las alertas DLP se recopilan en el panel de alertas. El panel de alertas le proporciona un único lugar donde ir para realizar una investigación profunda de todos los detalles sobre la coincidencia de directiva.  

<!-- [Microsoft Purview compliance portal](https://compliance.microsoft.com/)-->

## <a name="workloads"></a>Cargas de trabajo

El [panel de administración de alertas DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts), en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a>, muestra alertas para directivas DLP en estas cargas de trabajo:

- Exchange
- SharePoint
- OneDrive
- Teams
- Dispositivos con Windows 10 

> [!TIP]
> Los clientes que usan [DLP de punto de conexión](endpoint-dlp-learn-about.md) que son aptos para DLP de [Teams](dlp-microsoft-teams.md) verán sus alertas de directiva DLP de punto de conexión y las alertas de directiva DLP de Teams en el panel de administración de alertas DLP.

## <a name="single-alert-and-aggregate-alert"></a>Alerta única y alerta de agregado

Hay dos tipos de alertas que se pueden configurar en las directivas DLP.

**Las alertas de evento único** se usan normalmente en directivas que supervisan eventos altamente confidenciales que se producen en un volumen bajo, como un solo correo electrónico con 10 o más números de tarjeta de crédito de cliente que se envían fuera de la organización.

**Las alertas de eventos agregados** se usan normalmente en directivas que supervisan los eventos que se producen en un volumen superior durante un período de tiempo. Por ejemplo, se puede desencadenar una alerta agregada cuando se envían 10 correos electrónicos individuales cada uno con un número de tarjeta de crédito de cliente fuera de su organización durante 48 horas.

## <a name="types-of-events"></a>Tipos de eventos

Estos son algunos de los eventos asociados a una alerta. En la interfaz de usuario, puede elegir un evento determinado para ver sus detalles. 

### <a name="event-details"></a>Detalles del evento

|Nombre de propiedad  |Description  |Tipos de eventos  |
|---------|---------|---------|
|ID |identificador único asociado al evento |todos los eventos |
|Ubicación |carga de trabajo donde se detectó el evento|todos los eventos |
|tiempo de actividad     |hora de la actividad del usuario que coincidió con los criterios de la directiva DLP |

### <a name="affected-entities"></a>Entidades afectadas

|Nombre de propiedad |Description| Tipos de eventos|
|---------|---------|---------|
|usuario | usuario que realizó la acción que provocó la coincidencia de directiva | todos los eventos|
|Host | nombre de host del equipo donde se produjo la coincidencia de directiva DLP | eventos de dispositivo|
|Dirección IP | Dirección IP del equipo donde se produjo la coincidencia de directiva DLP | eventos de dispositivo|
|sha1 |Hash SHA-1 del archivo | eventos de dispositivo|
|sha256 | Hash SHA-256 del archivo | eventos de dispositivo|
|Id. de dispositivo MDATP | id. MDATP del dispositivo de punto de conexión|
|tamaño de archivo | tamaño del archivo| Eventos de SharePoint, OneDrive y dispositivo|
|ruta de acceso del archivo | la ruta de acceso absoluta del elemento implicado en la coincidencia de directiva DLP | Eventos de SharePoint, OneDrive y dispositivos|
|destinatarios de correo electrónico |si un correo electrónico era el elemento confidencial que coincidía con la directiva DLP, este campo incluye a los destinatarios de ese correo electrónico.| Eventos de Exchange|
|asunto del correo electrónico |asunto del correo electrónico que coincidió con la directiva DLP |Eventos de Exchange|
|datos adjuntos de correo electrónico | nombres de los datos adjuntos del correo electrónico que coincidieron con la directiva DLP| Eventos de Exchange|
|propietario del sitio |nombre del propietario del sitio| Eventos de SharePoint y OneDrive|
|dirección URL del sitio |lleno de la dirección URL del sitio de SharePoint o OneDrive donde se produjo la coincidencia de directiva DLP |Eventos de SharePoint y OneDrive|
|archivo creado |hora de creación del archivo que coincidió con la directiva DLP |Eventos de SharePoint y OneDrive|
|archivo modificado por última vez | la última vez que se cambió el archivo que coincidía con la directiva DLP | Eventos de SharePoint y OneDrive|
|tamaño de archivo | tamaño del archivo que coincidió con la directiva DLP |Eventos de SharePoint y OneDrive|
|propietario del archivo |propietario del archivo que coincidió con la directiva DLP |Eventos de SharePoint y OneDrive|  

### <a name="policy-details"></a>Detalles de la directiva

|Nombre de propiedad |Description |Tipos de eventos |
|---------|---------|---------|
|Directiva DLP coincidente |nombre de la directiva DLP coincidente |todos los eventos|
|regla coincidente |nombre de la regla de directiva DLP coincidente |todos los eventos|
|tipos de información confidencial (SIT) detectados|SIT que se detectaron como parte de la coincidencia de directiva DLP |todos los eventos|
|acciones realizadas |acciones que se realizaron que provocaron la coincidencia de la directiva DLP| todos los eventos|
|violación de la acción | acción en el dispositivo de punto de conexión que generó la alerta DLP| eventos de dispositivo | 
|directiva de superada por el usuario |el usuario invalidó la directiva a través de una sugerencia de directiva | todos los eventos|
|usar justificación de invalidación |el texto de la razón proporcionada por el usuario para la invalidación | todos los eventos|   

## <a name="see-also"></a>Consulta también

- [Introducción al panel de alertas de prevención de pérdida de datos](dlp-alerts-dashboard-get-started.md)
- [Dónde empezar con la prevención de pérdida de datos](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)
