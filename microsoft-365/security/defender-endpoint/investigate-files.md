---
title: Investigar archivos de Punto de conexión de Microsoft Defender
description: Use las opciones de investigación para obtener detalles sobre los archivos asociados con alertas, comportamientos o eventos.
keywords: investigar, investigar, archivo, actividad malintencionada, motivación de ataque, análisis profundo, informe de análisis profundo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: a801b6153cf3f273290721756440cfe974103e92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072608"
---
# <a name="investigate-a-file-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="daf6d-104">Investigar un archivo asociado a una alerta de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="daf6d-104">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="daf6d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="daf6d-105">**Applies to:**</span></span>
- [<span data-ttu-id="daf6d-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="daf6d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="daf6d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="daf6d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="daf6d-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="daf6d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="daf6d-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="daf6d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatefiles-abovefoldlink)

<span data-ttu-id="daf6d-110">Investigue los detalles de un archivo asociado a una alerta, comportamiento o evento específicos para determinar si el archivo muestra actividades malintencionadas, identificar la motivación del ataque y comprender el ámbito potencial de la infracción.</span><span class="sxs-lookup"><span data-stu-id="daf6d-110">Investigate the details of a file associated with a specific alert, behavior, or event to help determine if the file exhibits malicious activities, identify the attack motivation, and understand the potential scope of the breach.</span></span>

<span data-ttu-id="daf6d-111">Hay muchas maneras de obtener acceso a la página de perfil detallada de un archivo específico.</span><span class="sxs-lookup"><span data-stu-id="daf6d-111">There are many ways to access the detailed profile page of a specific file.</span></span> <span data-ttu-id="daf6d-112">Por ejemplo, puede usar la característica de búsqueda, hacer clic en un vínculo del árbol de proceso de **alerta,** gráfico de **incidentes,** escala de tiempo de artefactos o seleccionar un evento enumerado en la escala de tiempo **del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="daf6d-112">For example, you can  use the search feature, click on a link from the **Alert process tree**, **Incident graph**, **Artifact timeline**, or select an event listed in the **Device timeline**.</span></span>

<span data-ttu-id="daf6d-113">Una vez en la página de perfil detallada, puede cambiar entre los diseños de página nuevos y antiguos alternando la **nueva página Archivo**.</span><span class="sxs-lookup"><span data-stu-id="daf6d-113">Once on the detailed profile page, you can switch between the new and old page layouts by toggling **new File page**.</span></span> <span data-ttu-id="daf6d-114">El resto de este artículo describe el diseño de página más reciente.</span><span class="sxs-lookup"><span data-stu-id="daf6d-114">The rest of this article describes the newer page layout.</span></span>

<span data-ttu-id="daf6d-115">Puede obtener información de las siguientes secciones en la vista de archivos:</span><span class="sxs-lookup"><span data-stu-id="daf6d-115">You can get information from the following sections in the file view:</span></span>

- <span data-ttu-id="daf6d-116">Detalles del archivo, Detección de malware, Prevalencia de archivos</span><span class="sxs-lookup"><span data-stu-id="daf6d-116">File details, Malware detection, File prevalence</span></span>
- <span data-ttu-id="daf6d-117">Análisis profundo</span><span class="sxs-lookup"><span data-stu-id="daf6d-117">Deep analysis</span></span>
- <span data-ttu-id="daf6d-118">Alertas</span><span class="sxs-lookup"><span data-stu-id="daf6d-118">Alerts</span></span>
- <span data-ttu-id="daf6d-119">Observado en la organización</span><span class="sxs-lookup"><span data-stu-id="daf6d-119">Observed in organization</span></span>
- <span data-ttu-id="daf6d-120">Análisis profundo</span><span class="sxs-lookup"><span data-stu-id="daf6d-120">Deep analysis</span></span>
- <span data-ttu-id="daf6d-121">Nombres de archivo</span><span class="sxs-lookup"><span data-stu-id="daf6d-121">File names</span></span>

<span data-ttu-id="daf6d-122">También puede realizar acciones en un archivo de esta página.</span><span class="sxs-lookup"><span data-stu-id="daf6d-122">You can also take action on a file from this page.</span></span>

## <a name="file-actions"></a><span data-ttu-id="daf6d-123">Acciones de archivo</span><span class="sxs-lookup"><span data-stu-id="daf6d-123">File actions</span></span>

<span data-ttu-id="daf6d-124">En la parte superior de la página de perfil, encima de las tarjetas de información del archivo.</span><span class="sxs-lookup"><span data-stu-id="daf6d-124">Along the top of the profile page, above the file information cards.</span></span> <span data-ttu-id="daf6d-125">Las acciones que puede realizar aquí incluyen:</span><span class="sxs-lookup"><span data-stu-id="daf6d-125">Actions you can perform here include:</span></span>

- <span data-ttu-id="daf6d-126">Detener y poner en cuarentena</span><span class="sxs-lookup"><span data-stu-id="daf6d-126">Stop and quarantine</span></span>
- <span data-ttu-id="daf6d-127">Indicador Agregar o editar</span><span class="sxs-lookup"><span data-stu-id="daf6d-127">Add/edit indicator</span></span>
- <span data-ttu-id="daf6d-128">Descargar archivo</span><span class="sxs-lookup"><span data-stu-id="daf6d-128">Download file</span></span>
- <span data-ttu-id="daf6d-129">Consultar a un experto en amenazas</span><span class="sxs-lookup"><span data-stu-id="daf6d-129">Consult a threat expert</span></span>
- <span data-ttu-id="daf6d-130">Centro de actividades</span><span class="sxs-lookup"><span data-stu-id="daf6d-130">Action center</span></span>

<span data-ttu-id="daf6d-131">Para obtener más información sobre estas acciones, vea [Realizar acción de respuesta en un archivo](respond-file-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="daf6d-131">For more information on these actions, see [Take response action on a file](respond-file-alerts.md).</span></span>

## <a name="file-details-malware-detection-and-file-prevalence"></a><span data-ttu-id="daf6d-132">Detalles del archivo, detección de malware y prevalencia de archivos</span><span class="sxs-lookup"><span data-stu-id="daf6d-132">File details, Malware detection, and File prevalence</span></span>

<span data-ttu-id="daf6d-133">Los detalles del archivo, incidentes, detección de malware y tarjetas de prevalencia de archivos muestran varios atributos sobre el archivo.</span><span class="sxs-lookup"><span data-stu-id="daf6d-133">The file details, incident, malware detection, and file prevalence cards display various attributes about the file.</span></span>

<span data-ttu-id="daf6d-134">Verá detalles como MD5 del archivo, la relación de detección total de virus y la detección de antivirus de Microsoft Defender si está disponible y la prevalencia del archivo.</span><span class="sxs-lookup"><span data-stu-id="daf6d-134">You'll see details such as the file’s MD5, the Virus Total detection ratio, and Microsoft Defender AV detection if available, and the file’s prevalence.</span></span>

<span data-ttu-id="daf6d-135">La tarjeta de prevalencia de archivos muestra dónde se ha visto el archivo en dispositivos de la organización y en todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="daf6d-135">The file prevalence card shows where the file was seen in devices in the organization and worldwide.</span></span> 

> [!NOTE] 
> <span data-ttu-id="daf6d-136">Los diferentes usuarios pueden ver valores distintos en los dispositivos *de la* sección de organización de la tarjeta de prevalencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="daf6d-136">Different users may see dissimilar values in the *devices in organization* section of the file prevalence card.</span></span> <span data-ttu-id="daf6d-137">Esto se debe a que la tarjeta muestra información basada en el ámbito RBAC que tiene un usuario.</span><span class="sxs-lookup"><span data-stu-id="daf6d-137">This is because the card displays information based on the RBAC scope that a user has.</span></span> <span data-ttu-id="daf6d-138">Es decir, si a un usuario se le ha concedido visibilidad en un conjunto específico de dispositivos, solo verá la prevalencia organizativa de archivos en esos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="daf6d-138">Meaning, if a user has been granted visibility on a specific set of devices, they will only see the file organizational prevalence on those devices.</span></span>

![Imagen de información de archivo](images/atp-file-information.png)

## <a name="alerts"></a><span data-ttu-id="daf6d-140">Alertas</span><span class="sxs-lookup"><span data-stu-id="daf6d-140">Alerts</span></span>

<span data-ttu-id="daf6d-141">La **pestaña** Alertas proporciona una lista de alertas asociadas con el archivo.</span><span class="sxs-lookup"><span data-stu-id="daf6d-141">The **Alerts** tab provides a list of alerts that are associated with the file.</span></span> <span data-ttu-id="daf6d-142">Esta lista cubre gran parte de la misma información que la cola de alertas, excepto para el grupo de dispositivos, si existe, al que pertenece el dispositivo afectado.</span><span class="sxs-lookup"><span data-stu-id="daf6d-142">This list covers much of the same information as the Alerts queue, except for the device group, if any, the affected device belongs to.</span></span> <span data-ttu-id="daf6d-143">Puede elegir qué tipo de información se muestra seleccionando Personalizar columnas **de** la barra de herramientas encima de los encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="daf6d-143">You can choose what kind of information is shown by selecting **Customize columns** from the toolbar above the column headers.</span></span>

![Imagen de alertas relacionadas con la sección de archivos](images/atp-alerts-related-to-file.png)

## <a name="observed-in-organization"></a><span data-ttu-id="daf6d-145">Observado en la organización</span><span class="sxs-lookup"><span data-stu-id="daf6d-145">Observed in organization</span></span>

<span data-ttu-id="daf6d-146">La **pestaña Observed in organization** le permite especificar un intervalo de fechas para ver qué dispositivos se han observado con el archivo.</span><span class="sxs-lookup"><span data-stu-id="daf6d-146">The **Observed in organization** tab allows you to specify a date range to see which devices have been observed with the file.</span></span>

>[!NOTE]
><span data-ttu-id="daf6d-147">Esta pestaña mostrará un número máximo de 100 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="daf6d-147">This tab will show a maximum number of 100 devices.</span></span> <span data-ttu-id="daf6d-148">Para ver _todos los_ dispositivos con el archivo, exporte la pestaña a un archivo CSV **seleccionando Exportar** en el menú de acciones encima de los encabezados de columna de la pestaña.</span><span class="sxs-lookup"><span data-stu-id="daf6d-148">To see _all_ devices with the file, export the tab to a CSV file, by selecting **Export** from the action menu above the tab's column headers.</span></span>

![Imagen del dispositivo observado más reciente con el archivo](images/atp-observed-machines.png)

<span data-ttu-id="daf6d-150">Use el control deslizante o el selector de intervalos para especificar rápidamente un período de tiempo que desea comprobar si hay eventos relacionados con el archivo.</span><span class="sxs-lookup"><span data-stu-id="daf6d-150">Use the slider or the range selector to quickly specify a time period that you want to check for events involving the file.</span></span> <span data-ttu-id="daf6d-151">Puede especificar una ventana de tiempo tan pequeña como un solo día.</span><span class="sxs-lookup"><span data-stu-id="daf6d-151">You can specify a time window as small as a single day.</span></span> <span data-ttu-id="daf6d-152">Esto le permitirá ver solo los archivos que se comunicaron con esa dirección IP en ese momento, lo que reduce drásticamente el desplazamiento y la búsqueda innecesarios.</span><span class="sxs-lookup"><span data-stu-id="daf6d-152">This will allow you to see only files that communicated with that IP Address at that time, drastically reducing unnecessary scrolling and searching.</span></span>

## <a name="deep-analysis"></a><span data-ttu-id="daf6d-153">Análisis profundo</span><span class="sxs-lookup"><span data-stu-id="daf6d-153">Deep analysis</span></span>

<span data-ttu-id="daf6d-154">La **pestaña Análisis** profundo le permite enviar el archivo para un análisis profundo, para descubrir más detalles sobre el comportamiento del archivo, así como el efecto que está teniendo dentro de sus organizaciones. [](respond-file-alerts.md#deep-analysis)</span><span class="sxs-lookup"><span data-stu-id="daf6d-154">The **Deep analysis** tab allows you to [submit the file for deep analysis](respond-file-alerts.md#deep-analysis), to uncover more details about the file's behavior, as well as the effect it is having within your organizations.</span></span> <span data-ttu-id="daf6d-155">Después de enviar el archivo, el informe de análisis profundo aparecerá en esta pestaña una vez que estén disponibles los resultados.</span><span class="sxs-lookup"><span data-stu-id="daf6d-155">After you submit the file, the deep analysis report will appear in this tab once results are available.</span></span> <span data-ttu-id="daf6d-156">Si el análisis profundo no encontró nada, el informe estará vacío y el espacio de resultados permanecerá en blanco.</span><span class="sxs-lookup"><span data-stu-id="daf6d-156">If deep analysis did not find anything, the report will be empty and the results space will remain blank.</span></span>

![Imagen de la pestaña análisis profundo](images/submit-file.png)

## <a name="file-names"></a><span data-ttu-id="daf6d-158">Nombres de archivo</span><span class="sxs-lookup"><span data-stu-id="daf6d-158">File names</span></span>

<span data-ttu-id="daf6d-159">La **pestaña Nombres de** archivo enumera todos los nombres que se ha observado que el archivo debe usar en las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="daf6d-159">The **File names** tab lists all names the file has been observed to use, within your organizations.</span></span>

![Ficha Imagen de nombres de archivo](images/atp-file-names.png)

## <a name="related-topics"></a><span data-ttu-id="daf6d-161">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="daf6d-161">Related topics</span></span>

- [<span data-ttu-id="daf6d-162">Ver y organizar la cola de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="daf6d-162">View and organize the Microsoft Defender for Endpoint queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="daf6d-163">Administrar alertas de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="daf6d-163">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="daf6d-164">Investigar alertas de punto de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="daf6d-164">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="daf6d-165">Investigar dispositivos en la lista Microsoft Defender para dispositivos de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="daf6d-165">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="daf6d-166">Investigar una dirección IP asociada a una alerta de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="daf6d-166">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="daf6d-167">Investigar un dominio asociado a una alerta de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="daf6d-167">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="daf6d-168">Investigar una cuenta de usuario en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="daf6d-168">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="daf6d-169">Realizar acciones de respuesta en un archivo</span><span class="sxs-lookup"><span data-stu-id="daf6d-169">Take response actions on a file</span></span>](respond-file-alerts.md)
