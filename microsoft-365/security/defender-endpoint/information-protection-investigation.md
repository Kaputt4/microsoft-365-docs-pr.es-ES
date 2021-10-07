---
title: Usar etiquetas de confidencialidad para dar prioridad a una respuesta a incidentes
description: Obtenga información sobre cómo usar etiquetas de confidencialidad para priorizar e investigar incidentes
keywords: información, protección, datos, pérdida, prevención, etiquetas, dlp, incidente, investigación, investigación
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fb21eb0d52f62c49a9406bd92697dccaff290d7e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60156287"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a>Usar etiquetas de confidencialidad para dar prioridad a una respuesta a incidentes

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Un ciclo de vida de amenazas persistentes avanzado típico implica la exfiltración de datos. En un incidente de seguridad, es importante tener la capacidad de priorizar las investigaciones en las que los archivos confidenciales pueden estar en peligro para que los datos corporativos y la información estén protegidos.

Defender for Endpoint ayuda a que la priorización de incidentes de seguridad sea mucho más sencilla con el uso de etiquetas de confidencialidad. Las etiquetas de confidencialidad identifican rápidamente incidentes que pueden implicar dispositivos con información confidencial, como información confidencial.

## <a name="investigate-incidents-that-involve-sensitive-data"></a>Investigar incidentes que implican datos confidenciales

Aprenda a usar etiquetas de confidencialidad de datos para priorizar la investigación de incidentes.

> [!NOTE]
> Las etiquetas se detectan Windows 10, versión 1809 o posterior.

1. En Microsoft 365 Defender portal, seleccione **Incidentes &** \> **alertas incidentes**.

2. Desplácese a la derecha para ver la **columna Confidencialidad de** datos. Esta columna refleja las etiquetas de confidencialidad que se han observado en dispositivos relacionados con los incidentes, lo que indica si el incidente puede afectar a los archivos confidenciales.

    ![Imagen de la columna de confidencialidad de datos.](images/data-sensitivity-column.png)

    También puede filtrar en función de la **confidencialidad de datos**

    ![Imagen del filtro de confidencialidad de datos.](images/data-sensitivity-filter.png)

3. Abra la página de incidentes para investigar más a fondo.

    ![Imagen de los detalles de la página de incidentes.](images/incident-page.png)

4. Selecciona la **pestaña Dispositivos** para identificar los dispositivos que almacenan archivos con etiquetas de confidencialidad.

    ![Imagen de la pestaña del dispositivo.](images/investigate-devices-tab.png)

5. Seleccione los dispositivos que almacenan datos confidenciales y busque en la escala de tiempo para identificar los archivos que se pueden ver afectados y, a continuación, tome las medidas adecuadas para asegurarse de que los datos están protegidos.

   Puedes restringir los eventos que se muestran en la escala de tiempo del dispositivo buscando etiquetas de confidencialidad de datos. Al hacerlo, solo se mostrarán los eventos asociados con archivos que tengan dicho nombre de etiqueta.

    ![Imagen de la escala de tiempo del dispositivo con resultados de búsqueda limitados en función de la etiqueta.](images/machine-timeline-labels.png)

> [!TIP]
> Estos puntos de datos también se exponen a través de "DeviceFileEvents" en búsqueda avanzada, lo que permite que las consultas avanzadas y la detección de programación tomen en cuenta las etiquetas de confidencialidad y el estado de protección de archivos.
