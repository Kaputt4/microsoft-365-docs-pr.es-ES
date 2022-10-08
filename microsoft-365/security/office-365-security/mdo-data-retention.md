---
title: Microsoft Defender para Office 365 retención de datos
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 09/14/2022
audience: ITPro
ms.topic: article
ms.service: microsoft-365-security
ms.subservice: mdo
ms.localizationpriority: medium
ms.collection:
- m365-security
ms.custom: ''
description: Microsoft Defender para Office 365 información de retención de datosTreat Explorer/Real-Time detecciones
search.appverid: met150
ms.openlocfilehash: 2bb7b03b87f090723c073cae103405c1902ba278
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68092388"
---
# <a name="data-retention-information-for-microsoft-defender-for-office-365"></a>Información de retención de datos para Microsoft Defender para Office 365

De forma predeterminada, los datos de distintas características se conservan durante un máximo de 30 días. Sin embargo, para algunas de las características, puede especificar el período de retención en función de la directiva. Consulte la tabla siguiente para ver los distintos períodos de retención de cada característica.

> [!NOTE]
> Microsoft Defender para Office 365 tiene dos tipos de planes diferentes. Si tiene "Detecciones en tiempo real", tiene el **Plan 1** y, si tiene el Explorador de amenazas, tiene el **Plan 2**. El plan que tenga influirá en las herramientas que pueda ver, de modo que asegúrese de saber cuál es su plan mientras aprende.

## <a name="defender-for-office-365-plan-1"></a>Defender para Office 365 Plan 1

|Característica|Período de retención|
|---|---|
|Detalles de metadatos de alerta (Microsoft Defender para alertas de Office) | 90 días |
|Detalles de metadatos de entidad (correos electrónicos) | 30 días |
|Detalles de alertas de actividad (registros de auditoría) | 7 días |
|Página de la entidad de correo electrónico | 30 días |
|Quarantine | 30 días (configurable hasta un máximo de 30 días) |
|Informes | 90 días (para todos los datos agregados) <br>30 días (para toda la información detallada excepto a continuación) <br> 10 días (para detalles del informe de estado de protección contra amenazas y detalles del informe de correo de suplantación de identidad) <br> 7 días (para detalles del informe de protección de direcciones URL) <br>
|Envíos | 30 días |
|Detecciones del Explorador de amenazas o Real-Time | 30 días |

## <a name="defender-for-office-365-plan-2"></a>Defender para Office 365 Plan 2

Defender para Office 365 funcionalidades del plan 1, además de:

|Característica|Período de retención|
|---|---|
|Centro de actividades | 180 días, 30 días (Centro de acción de Office)   |
|Búsqueda avanzada | 30 días |
|AIR (investigación y respuesta automatizadas) | 60 días (para los metadatos de las investigaciones)<br> 30 días (para metadatos de correo electrónico)  |
|Datos de simulación de ataques | 18 meses |
|Campañas | 30 días |
|Incidentes | 30 días|
|Remediación | 30 días |
|Análisis de amenazas | 30 días |
|Rastreadores de amenazas | 30 días |
