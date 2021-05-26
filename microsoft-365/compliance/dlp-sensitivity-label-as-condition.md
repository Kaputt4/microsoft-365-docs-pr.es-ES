---
title: Usar etiquetas de confidencialidad como condiciones en las directivas de DLP
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga más información sobre los servicios y los tipos de elementos en los que puede usar etiquetas de confidencialidad como condiciones en directivas DLP
ms.openlocfilehash: b33e6704a3311740c1e386f77f1c751382ee6958
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651097"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a>Usar etiquetas de confidencialidad como condiciones en las directivas de DLP

Puede usar [etiquetas de confidencialidad](sensitivity-labels.md) como condiciones en las directivas DLP para estas ubicaciones:

- Mensajes de correo electrónico de Exchange Online
- SharePoint Online
- Sitios de OneDrive para la Empresa
- Dispositivos con Windows 10

Las etiquetas de confidencialidad aparecen como una opción en la lista de **Contenido**.

> [!div class="mx-imgBorder"]
> ![etiqueta de confidencialidad como una condición](../media/dlp-sensitivity-label-as-a-condition.png)

> [!IMPORTANT]
> **Las etiquetas de confidencialidad** como una condición no estarán disponibles si ha seleccionado **mensajes de canal y de chat de Teams** como una ubicación para aplicar la directiva DLP.


## <a name="supported-items-scenarios-and-policy-tips"></a>Elementos compatibles, escenarios y sugerencias de directiva

Puede usar etiquetas de confidencialidad como condiciones para estos elementos y en estos escenarios.

### <a name="supported-items"></a>Elementos compatibles

|Servicio  |Tipo de elemento  |Disponible para sugerencia de directiva  |Aplicable  |
|---------|---------|---------|---------|
|Exchange    |mensaje de correo electrónico         |sí         |sí         |
|Exchange    |datos adjuntos de correo electrónico         |no         |sí *         |
|SharePoint Online     |elementos en SharePoint Online         |sí         |sí         |
|OneDrive para la Empresa     |elementos         |sí         |sí         |
|Teams     |Mensajes de canal y de Teams         |no aplicable         |no aplicable         |
|Teams     |datos adjuntos         |sí **         |sí **         |
|Dispositivos con Windows 10     |elementos         |sí         |sí         |
|MCAS (vista previa) |elementos         |sí         |sí         |

\* La detección DLP de etiquetas de confidencialidad en los datos adjuntos de correo electrónico solo es compatible con tipos de archivo de Office.

\** Los datos adjuntos enviados en Teams sobre chats o canales 1:1 son cargados automáticamente en OneDrive para la Empresa y SharePoint. De modo que si SharePoint Online o OneDrive para la Empresa están incluidos como ubicaciones en su directiva de DLP, entonces los adjuntos etiquetados enviados en Teams serán incluidos de forma automática en el alcance de esta condición. No es necesario seleccionar Teams como una ubicación en la Directiva DLP.

### <a name="supported-scenarios"></a>Escenarios admitidos

- El administrador de DLP podrá ver una lista de todas las etiquetas de confidencialidad en el espacio empresarial cuando decida incluir una o más etiquetas de confidencialidad como condición.

- El uso de las etiquetas de confidencialidad como condición se admite en todas las cargas de trabajo, como se indica en la matriz de soporte más arriba.

- Las sugerencias de directiva DLP se seguirán mostrando en las cargas de trabajo (excepto Outlook Win32) para las directivas DLP que contienen la etiqueta de confidencialidad como condición.

- Las etiquetas de sensibilidad también aparecerán como parte del correo del informe de incidentes si se cumple una directiva DLP con la etiqueta de confidencialidad como condición.

- Los detalles de la etiqueta de confidencialidad también se mostrarán en el registro de auditoría de coincidencia de regla DLP para una coincidencia de directiva DLP que contiene la etiqueta de confidencialidad como condición.


### <a name="support-policy-tips"></a>Sugerencias de directivas compatibles


|Carga de trabajo  |Sugerencias sobre las directivas compatibles / no compatibles  |
|---------|---------|
|OWA |    compatible     |
|Outlook Win 32    |  no compatible       |
|SharePoint   |   compatible      |
|OneDrive para la Empresa    |    compatible     |
|dispositivos de punto de conexión   |  no compatible       |
