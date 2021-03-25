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
ms.openlocfilehash: bff490edcc79bc8f96e65c8b27586ca8b54e5bce
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186130"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a><span data-ttu-id="140b7-104">Usar etiquetas de confidencialidad para priorizar la respuesta a incidentes</span><span class="sxs-lookup"><span data-stu-id="140b7-104">Use sensitivity labels to prioritize incident response</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="140b7-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="140b7-105">**Applies to:**</span></span>
- [<span data-ttu-id="140b7-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="140b7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="140b7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="140b7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="140b7-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="140b7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="140b7-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="140b7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="140b7-110">Un ciclo de vida de amenazas persistentes avanzado típico implica la exfiltración de datos.</span><span class="sxs-lookup"><span data-stu-id="140b7-110">A typical advanced persistent threat lifecycle involves data exfiltration.</span></span> <span data-ttu-id="140b7-111">En un incidente de seguridad, es importante tener la capacidad de priorizar las investigaciones en las que los archivos confidenciales pueden estar en peligro para que los datos corporativos y la información estén protegidos.</span><span class="sxs-lookup"><span data-stu-id="140b7-111">In a security incident, it's important to have the ability to prioritize investigations where sensitive files may be jeopardy so that corporate data and information are protected.</span></span>

<span data-ttu-id="140b7-112">Defender for Endpoint ayuda a que la priorización de incidentes de seguridad sea mucho más sencilla con el uso de etiquetas de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="140b7-112">Defender for Endpoint helps to make the prioritization of security incidents much simpler with the use of sensitivity labels.</span></span> <span data-ttu-id="140b7-113">Las etiquetas de confidencialidad identifican rápidamente incidentes que pueden implicar dispositivos con información confidencial, como información confidencial.</span><span class="sxs-lookup"><span data-stu-id="140b7-113">Sensitivity labels quickly identify incidents that may involve devices with sensitive information such as confidential information.</span></span> 

## <a name="investigate-incidents-that-involve-sensitive-data"></a><span data-ttu-id="140b7-114">Investigar incidentes que implican datos confidenciales</span><span class="sxs-lookup"><span data-stu-id="140b7-114">Investigate incidents that involve sensitive data</span></span>
<span data-ttu-id="140b7-115">Aprenda a usar etiquetas de confidencialidad de datos para priorizar la investigación de incidentes.</span><span class="sxs-lookup"><span data-stu-id="140b7-115">Learn how to use data sensitivity labels to prioritize incident investigation.</span></span>

>[!NOTE]
><span data-ttu-id="140b7-116">Las etiquetas se detectan para Windows 10, versión 1809 o posterior.</span><span class="sxs-lookup"><span data-stu-id="140b7-116">Labels are detected for Windows 10, version 1809 or later.</span></span>

1. <span data-ttu-id="140b7-117">En el Centro de seguridad de Microsoft Defender, seleccione **Incidentes**.</span><span class="sxs-lookup"><span data-stu-id="140b7-117">In Microsoft Defender Security Center, select **Incidents**.</span></span> 

2. <span data-ttu-id="140b7-118">Desplácese a la derecha para ver la **columna Confidencialidad de** datos.</span><span class="sxs-lookup"><span data-stu-id="140b7-118">Scroll to the right to see the **Data sensitivity** column.</span></span> <span data-ttu-id="140b7-119">Esta columna refleja las etiquetas de confidencialidad que se han observado en dispositivos relacionados con los incidentes, lo que indica si el incidente puede afectar a los archivos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="140b7-119">This column reflects sensitivity labels that have been observed on devices related to the incidents providing an indication of whether sensitive files may be impacted by the incident.</span></span>

    ![Imagen de la columna de confidencialidad de datos](images/data-sensitivity-column.png)

    <span data-ttu-id="140b7-121">También puede filtrar en función de la **confidencialidad de datos**</span><span class="sxs-lookup"><span data-stu-id="140b7-121">You can also filter based on **Data sensitivity**</span></span> 

    ![Imagen del filtro de confidencialidad de datos](images/data-sensitivity-filter.png)

3. <span data-ttu-id="140b7-123">Abra la página de incidentes para investigar más a fondo.</span><span class="sxs-lookup"><span data-stu-id="140b7-123">Open the incident page to further investigate.</span></span>

    ![Imagen de los detalles de la página de incidentes](images/incident-page.png)

4. <span data-ttu-id="140b7-125">Selecciona la **pestaña Dispositivos** para identificar los dispositivos que almacenan archivos con etiquetas de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="140b7-125">Select the **Devices** tab to identify devices storing files with sensitivity labels.</span></span>

    ![Imagen de la pestaña del dispositivo](images/investigate-devices-tab.png)
   

5. <span data-ttu-id="140b7-127">Seleccione los dispositivos que almacenan datos confidenciales y busque en la escala de tiempo para identificar los archivos que se pueden ver afectados y, a continuación, tome las medidas adecuadas para asegurarse de que los datos están protegidos.</span><span class="sxs-lookup"><span data-stu-id="140b7-127">Select the devices that store sensitive data and search through the timeline to identify which files may be impacted then take appropriate action to ensure that data is protected.</span></span> 

   <span data-ttu-id="140b7-128">Puedes restringir los eventos que se muestran en la escala de tiempo del dispositivo buscando etiquetas de confidencialidad de datos.</span><span class="sxs-lookup"><span data-stu-id="140b7-128">You can narrow down the events shown on the device timeline by searching for data sensitivity labels.</span></span> <span data-ttu-id="140b7-129">Al hacerlo, solo se mostrarán los eventos asociados con archivos que tengan dicho nombre de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="140b7-129">Doing this will show only events associated with files that have said label name.</span></span>

    ![Imagen de la escala de tiempo del dispositivo con resultados de búsqueda limitados en función de la etiqueta](images/machine-timeline-labels.png)


>[!TIP]
><span data-ttu-id="140b7-131">Estos puntos de datos también se exponen a través de "DeviceFileEvents" en búsqueda avanzada, lo que permite que las consultas avanzadas y la detección de programación tomen en cuenta las etiquetas de confidencialidad y el estado de protección de archivos.</span><span class="sxs-lookup"><span data-stu-id="140b7-131">These data points are also exposed through the ‘DeviceFileEvents’ in advanced hunting, allowing advanced queries and schedule detection to take into account sensitivity labels and file protection status.</span></span> 
