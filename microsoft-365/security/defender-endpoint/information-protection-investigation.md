---
title: Usar etiquetas de confidencialidad para dar prioridad a una respuesta a incidentes
description: Aprenda a usar etiquetas de confidencialidad para priorizar e investigar incidentes
keywords: información, protección, datos, pérdida, prevención, etiquetas, dlp, incidente, investigación, investigación
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2 - EngageScoreSep2022
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 5dcc47dde921eb2e8c94fbb38b828bfc2f1c2d5b
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68646757"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a>Usar etiquetas de confidencialidad para dar prioridad a una respuesta a incidentes

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Un ciclo de vida de amenazas persistentes avanzado típico implica la filtración de datos. En un incidente de seguridad, es importante tener la capacidad de priorizar las investigaciones en las que los archivos confidenciales pueden estar en peligro para que se protejan los datos corporativos y la información.

Defender for Endpoint ayuda a simplificar la priorización de incidentes de seguridad con el uso de etiquetas de confidencialidad. Las etiquetas de confidencialidad identifican rápidamente incidentes que pueden implicar dispositivos con información confidencial, como información confidencial.

## <a name="investigate-incidents-that-involve-sensitive-data"></a>Investigación de incidentes que implican datos confidenciales

Obtenga información sobre cómo usar etiquetas de confidencialidad de datos para priorizar la investigación de incidentes.

> [!NOTE]
> Las etiquetas se detectan para Windows 10, versión 1809 o versiones posteriores y Windows 11.

1. En Microsoft 365 Defender portal, seleccione **Incidentes & alertas** \> **Incidentes**.

2. Desplácese a la derecha para ver la columna **Confidencialidad de** datos. Esta columna refleja las etiquetas de confidencialidad que se han observado en los dispositivos relacionados con los incidentes, lo que proporciona una indicación de si los archivos confidenciales pueden verse afectados por el incidente.

   :::image type="content" source="images/data-sensitivity-column.png" alt-text="La opción Altamente confidencial en la columna de confidencialidad de datos" lightbox="images/data-sensitivity-column.png":::

    También puede filtrar en función de **la confidencialidad de los datos**.

    :::image type="content" source="images/data-sensitivity-filter.png" alt-text="Filtro de confidencialidad de datos" lightbox="images/data-sensitivity-filter.png":::

3. Abra la página del incidente para investigar más a fondo.

   :::image type="content" source="images/incident-page.png" alt-text="Detalles de la página del incidente" lightbox="images/incident-page.png":::

4. Seleccione la pestaña **Dispositivos** para identificar los dispositivos que almacenan archivos con etiquetas de confidencialidad.

   :::image type="content" source="images/investigate-devices-tab.png" alt-text="Pestaña Dispositivo" lightbox="images/investigate-devices-tab.png":::

5. Seleccione los dispositivos que almacenan datos confidenciales y busque en la escala de tiempo para identificar qué archivos pueden verse afectados y, a continuación, realice las acciones adecuadas para asegurarse de que los datos están protegidos.

   Para restringir los eventos que se muestran en la escala de tiempo del dispositivo, busque etiquetas de confidencialidad de datos. Al hacerlo, solo se mostrarán los eventos asociados a los archivos que tienen dicho nombre de etiqueta.

   :::image type="content" source="images/machine-timeline-labels.png" alt-text="Escala de tiempo del dispositivo con resultados de búsqueda reducidos en función de la etiqueta" lightbox="images/machine-timeline-labels.png":::

> [!TIP]
> Estos puntos de datos también se exponen a través de "DeviceFileEvents" en la búsqueda avanzada, lo que permite que las consultas avanzadas y la detección de programación tenga en cuenta las etiquetas de confidencialidad y el estado de protección de archivos.
