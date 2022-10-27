---
title: Usar etiquetas de confidencialidad Microsoft Defender para punto de conexión para proteger los datos y priorizar la respuesta a incidentes de seguridad
description: Obtenga información sobre cómo usar etiquetas de confidencialidad de Defender para punto de conexión para proteger, priorizar e investigar incidentes que implican loos de datos, dlp e incidentes de seguridad.
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
- ContentEngagementFY23
- tier2 - EngageScoreSep2022
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: cdb1d9eb306fd472690cc756fdbe0a1b412d7ab8
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68729949"
---
# <a name="microsoft-defender-for-endpoint-sensitivity-labels-protect-and-prioritize-incident-response"></a>Microsoft Defender para punto de conexión etiquetas de confidencialidad protegen y priorizan la respuesta ante incidentes

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Un ciclo de vida de amenazas persistentes avanzado típico (o APT) implica la filtración de datos, el punto en el que se *toman* datos de la organización. En esas situaciones, las etiquetas de confidencialidad pueden indicar a las operaciones de seguridad dónde empezar mediante la ortografía de qué datos es la prioridad más alta que se debe proteger.

Defender for Endpoint ayuda a simplificar la priorización de incidentes de seguridad con el uso de etiquetas de confidencialidad también. Por ejemplo, las etiquetas de confidencialidad identifican rápidamente incidentes que pueden implicar dispositivos con información confidencial sobre ellos (por ejemplo, información confidencial).

A continuación se muestra cómo usar etiquetas de confidencialidad en Defender para punto de conexión.

## <a name="investigate-incidents-that-involve-sensitive-data-on-devices-with-defender-for-endpoint"></a>Investigación de incidentes que implican datos confidenciales en dispositivos con Defender para punto de conexión

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

## <a name="related-information-about-sensitivity-labels"></a>Información relacionada sobre las etiquetas de confidencialidad

- [Obtenga información sobre las etiquetas de confidencialidad en Office 365](../../compliance/sensitivity-labels.md)
- [Aprenda a aplicar la etiqueta de confidencialidad dentro del correo electrónico u Office.](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
- [Aprenda a usar etiquetas de confidencialidad como condición al aplicar la prevención de pérdida de datos.](../../compliance/dlp-sensitivity-label-as-condition.md)