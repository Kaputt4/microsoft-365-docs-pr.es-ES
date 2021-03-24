---
title: Usar etiquetas de confidencialidad para priorizar la respuesta a incidentes
description: Obtenga información sobre cómo usar etiquetas de confidencialidad para priorizar e investigar incidentes
keywords: información, protección, datos, pérdida, prevención, etiquetas, dlp, incidente, investigación, investigación
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d0c27ab2c6af8706e5e06a3c87b44e49c9185766
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073851"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a>Usar etiquetas de confidencialidad para priorizar la respuesta a incidentes  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


Un ciclo de vida de amenazas persistentes avanzado típico implica la exfiltración de datos. En un incidente de seguridad, es importante tener la capacidad de priorizar las investigaciones en las que los archivos confidenciales pueden estar en peligro para que los datos corporativos y la información estén protegidos.

Defender for Endpoint ayuda a que la priorización de incidentes de seguridad sea mucho más sencilla con el uso de etiquetas de confidencialidad. Las etiquetas de confidencialidad identifican rápidamente incidentes que pueden implicar dispositivos con información confidencial, como información confidencial. 

## <a name="investigate-incidents-that-involve-sensitive-data"></a>Investigar incidentes que implican datos confidenciales
Aprenda a usar etiquetas de confidencialidad de datos para priorizar la investigación de incidentes.

>[!NOTE]
>Las etiquetas se detectan para Windows 10, versión 1809 o posterior.

1. En el Centro de seguridad de Microsoft Defender, seleccione **Incidentes**. 

2. Desplácese a la derecha para ver la **columna Confidencialidad de** datos. Esta columna refleja las etiquetas de confidencialidad que se han observado en dispositivos relacionados con los incidentes, lo que indica si el incidente puede afectar a los archivos confidenciales.

    ![Imagen de la columna de confidencialidad de datos](images/data-sensitivity-column.png)

    También puede filtrar en función de la **confidencialidad de datos** 

    ![Imagen del filtro de confidencialidad de datos](images/data-sensitivity-filter.png)

3. Abra la página de incidentes para investigar más a fondo.

    ![Imagen de los detalles de la página de incidentes](images/incident-page.png)

4. Selecciona la **pestaña Dispositivos** para identificar los dispositivos que almacenan archivos con etiquetas de confidencialidad.

    ![Imagen de la pestaña del dispositivo](images/investigate-devices-tab.png)
   

5. Seleccione los dispositivos que almacenan datos confidenciales y busque en la escala de tiempo para identificar los archivos que se pueden ver afectados y, a continuación, tome las medidas adecuadas para asegurarse de que los datos están protegidos. 

   Puedes restringir los eventos que se muestran en la escala de tiempo del dispositivo buscando etiquetas de confidencialidad de datos. Al hacerlo, solo se mostrarán los eventos asociados con archivos que tengan dicho nombre de etiqueta.

    ![Imagen de la escala de tiempo del dispositivo con resultados de búsqueda limitados en función de la etiqueta](images/machine-timeline-labels.png)


>[!TIP]
>Estos puntos de datos también se exponen a través de "DeviceFileEvents" en búsqueda avanzada, lo que permite que las consultas avanzadas y la detección de programación tomen en cuenta las etiquetas de confidencialidad y el estado de protección de archivos. 
