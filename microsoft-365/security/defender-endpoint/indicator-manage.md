---
title: Administrar indicadores
ms.reviewer: ''
description: Administrar indicadores para un hash de archivo, dirección IP, direcciones URL o dominios que definen la detección, prevención y exclusión de entidades.
keywords: import, indicator, list, ioc, csv, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9fd36f63450335247bf57c4cc1f98d6f0d32a9d5
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185950"
---
# <a name="manage-indicators"></a><span data-ttu-id="f7a8a-104">Administrar indicadores</span><span class="sxs-lookup"><span data-stu-id="f7a8a-104">Manage indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f7a8a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f7a8a-105">**Applies to:**</span></span>
- [<span data-ttu-id="f7a8a-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f7a8a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f7a8a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7a8a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="f7a8a-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f7a8a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f7a8a-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. <span data-ttu-id="f7a8a-110">En el panel de navegación, **seleccione Configuración**  >  **Indicadores**.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-110">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="f7a8a-111">Seleccione la pestaña del tipo de entidad que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-111">Select the tab of the entity type you'd like to manage.</span></span>  

3. <span data-ttu-id="f7a8a-112">Actualice los detalles del indicador y  haga clic en **Guardar** o haga clic en el botón Eliminar si desea quitar la entidad de la lista.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-112">Update the details of the indicator and click **Save** or click the **Delete** button if you'd like to remove the entity from the list.</span></span>

## <a name="import-a-list-of-iocs"></a><span data-ttu-id="f7a8a-113">Importar una lista de iocs</span><span class="sxs-lookup"><span data-stu-id="f7a8a-113">Import a list of IoCs</span></span>

<span data-ttu-id="f7a8a-114">También puede elegir cargar un archivo CSV que defina los atributos de los indicadores, la acción que se va a realizar y otros detalles.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-114">You can also choose to upload a CSV file that defines the attributes of indicators, the action to be taken, and other details.</span></span>

<span data-ttu-id="f7a8a-115">Descargue el CSV de ejemplo para conocer los atributos de columna admitidos.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-115">Download the sample CSV to know the supported column attributes.</span></span>

1. <span data-ttu-id="f7a8a-116">En el panel de navegación, **seleccione Configuración**  >  **Indicadores**.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-116">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="f7a8a-117">Seleccione la pestaña del tipo de entidad para la que desea importar los indicadores.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-117">Select the tab of the entity type you'd like to import indicators for.</span></span>

3. <span data-ttu-id="f7a8a-118">Seleccione **Importar**  >  **elegir archivo**.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-118">Select **Import** > **Choose file**.</span></span> 

4. <span data-ttu-id="f7a8a-119">Seleccione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-119">Select **Import**.</span></span> <span data-ttu-id="f7a8a-120">Haga esto para todos los archivos que desea importar.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-120">Do this for all the files you'd like to import.</span></span> 

5. <span data-ttu-id="f7a8a-121">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-121">Select **Done**.</span></span>

<span data-ttu-id="f7a8a-122">En la tabla siguiente se muestran los parámetros admitidos.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-122">The following table shows the supported parameters.</span></span>

<span data-ttu-id="f7a8a-123">Parámetro</span><span class="sxs-lookup"><span data-stu-id="f7a8a-123">Parameter</span></span> | <span data-ttu-id="f7a8a-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="f7a8a-124">Type</span></span>    |   <span data-ttu-id="f7a8a-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7a8a-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="f7a8a-126">indicatorType</span><span class="sxs-lookup"><span data-stu-id="f7a8a-126">indicatorType</span></span> | <span data-ttu-id="f7a8a-127">Enum</span><span class="sxs-lookup"><span data-stu-id="f7a8a-127">Enum</span></span> | <span data-ttu-id="f7a8a-128">Tipo del indicador.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-128">Type of the indicator.</span></span> <span data-ttu-id="f7a8a-129">Los valores posibles son: "FileSha1", "FileSha256", "IpAddress", "DomainName" y "Url".</span><span class="sxs-lookup"><span data-stu-id="f7a8a-129">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="f7a8a-130">**Required**</span><span class="sxs-lookup"><span data-stu-id="f7a8a-130">**Required**</span></span>
<span data-ttu-id="f7a8a-131">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="f7a8a-131">indicatorValue</span></span> | <span data-ttu-id="f7a8a-132">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7a8a-132">String</span></span> | <span data-ttu-id="f7a8a-133">Identidad de la [entidad Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="f7a8a-133">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="f7a8a-134">**Required**</span><span class="sxs-lookup"><span data-stu-id="f7a8a-134">**Required**</span></span>
<span data-ttu-id="f7a8a-135">acción</span><span class="sxs-lookup"><span data-stu-id="f7a8a-135">action</span></span> | <span data-ttu-id="f7a8a-136">Enum</span><span class="sxs-lookup"><span data-stu-id="f7a8a-136">Enum</span></span> | <span data-ttu-id="f7a8a-137">La acción que se realizará si el indicador se detectará en la organización.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-137">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="f7a8a-138">Los valores posibles son: "Alert", "AlertAndBlock" y "Allowed".</span><span class="sxs-lookup"><span data-stu-id="f7a8a-138">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="f7a8a-139">**Required**</span><span class="sxs-lookup"><span data-stu-id="f7a8a-139">**Required**</span></span>
<span data-ttu-id="f7a8a-140">title</span><span class="sxs-lookup"><span data-stu-id="f7a8a-140">title</span></span> | <span data-ttu-id="f7a8a-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7a8a-141">String</span></span> | <span data-ttu-id="f7a8a-142">Título de alerta del indicador.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-142">Indicator alert title.</span></span> <span data-ttu-id="f7a8a-143">**Required**</span><span class="sxs-lookup"><span data-stu-id="f7a8a-143">**Required**</span></span>
<span data-ttu-id="f7a8a-144">description</span><span class="sxs-lookup"><span data-stu-id="f7a8a-144">description</span></span> | <span data-ttu-id="f7a8a-145">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7a8a-145">String</span></span> |  <span data-ttu-id="f7a8a-146">Descripción del indicador.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-146">Description of the indicator.</span></span> <span data-ttu-id="f7a8a-147">**Required**</span><span class="sxs-lookup"><span data-stu-id="f7a8a-147">**Required**</span></span>
<span data-ttu-id="f7a8a-148">expirationTime</span><span class="sxs-lookup"><span data-stu-id="f7a8a-148">expirationTime</span></span> | <span data-ttu-id="f7a8a-149">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="f7a8a-149">DateTimeOffset</span></span> | <span data-ttu-id="f7a8a-150">La hora de expiración del indicador con el siguiente formato YYYY-MM-DDTHH:MM:SS.0Z.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-150">The expiration time of the indicator in the following format YYYY-MM-DDTHH:MM:SS.0Z.</span></span> <span data-ttu-id="f7a8a-151">**Optional**</span><span class="sxs-lookup"><span data-stu-id="f7a8a-151">**Optional**</span></span>
<span data-ttu-id="f7a8a-152">severity</span><span class="sxs-lookup"><span data-stu-id="f7a8a-152">severity</span></span> | <span data-ttu-id="f7a8a-153">Enum</span><span class="sxs-lookup"><span data-stu-id="f7a8a-153">Enum</span></span> | <span data-ttu-id="f7a8a-154">Gravedad del indicador.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-154">The severity of the indicator.</span></span> <span data-ttu-id="f7a8a-155">Los valores posibles son: "Informational", "Low", "Medium" y "High".</span><span class="sxs-lookup"><span data-stu-id="f7a8a-155">Possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="f7a8a-156">**Optional**</span><span class="sxs-lookup"><span data-stu-id="f7a8a-156">**Optional**</span></span>
<span data-ttu-id="f7a8a-157">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="f7a8a-157">recommendedActions</span></span> | <span data-ttu-id="f7a8a-158">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7a8a-158">String</span></span> | <span data-ttu-id="f7a8a-159">Acciones recomendadas de alerta del indicador TI.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-159">TI indicator alert recommended actions.</span></span> <span data-ttu-id="f7a8a-160">**Optional**</span><span class="sxs-lookup"><span data-stu-id="f7a8a-160">**Optional**</span></span>
<span data-ttu-id="f7a8a-161">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="f7a8a-161">rbacGroupNames</span></span> | <span data-ttu-id="f7a8a-162">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7a8a-162">String</span></span> | <span data-ttu-id="f7a8a-163">Lista separada por comas de nombres de grupo RBAC a los que se aplicaría el indicador.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-163">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="f7a8a-164">**Optional**</span><span class="sxs-lookup"><span data-stu-id="f7a8a-164">**Optional**</span></span>
<span data-ttu-id="f7a8a-165">categoría</span><span class="sxs-lookup"><span data-stu-id="f7a8a-165">category</span></span> | <span data-ttu-id="f7a8a-166">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7a8a-166">String</span></span> | <span data-ttu-id="f7a8a-167">Categoría de la alerta.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-167">Category of the alert.</span></span> <span data-ttu-id="f7a8a-168">Algunos ejemplos son: Ejecución y acceso a credenciales.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-168">Examples include: Execution and credential access.</span></span> <span data-ttu-id="f7a8a-169">**Optional**</span><span class="sxs-lookup"><span data-stu-id="f7a8a-169">**Optional**</span></span>
<span data-ttu-id="f7a8a-170">mitretechniques</span><span class="sxs-lookup"><span data-stu-id="f7a8a-170">mitretechniques</span></span>| <span data-ttu-id="f7a8a-171">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7a8a-171">String</span></span> | <span data-ttu-id="f7a8a-172">Código/id de técnicas MITRE (separados por comas).</span><span class="sxs-lookup"><span data-stu-id="f7a8a-172">MITRE techniques code/id (comma separated).</span></span> <span data-ttu-id="f7a8a-173">Para obtener más información, [vea Enterprise tácticas](https://attack.mitre.org/tactics/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="f7a8a-173">For more information, see [Enterprise tactics](https://attack.mitre.org/tactics/enterprise/).</span></span> <span data-ttu-id="f7a8a-174">**Opcional** Se recomienda agregar un valor en categoría cuando se utiliza una técnica MITRE.</span><span class="sxs-lookup"><span data-stu-id="f7a8a-174">**Optional** It is recommended to add a value in category when a MITRE technique.</span></span>

<span data-ttu-id="f7a8a-175">Para obtener más información, vea Microsoft Defender para las categorías de alertas de punto de conexión ahora están alineadas con [MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).</span><span class="sxs-lookup"><span data-stu-id="f7a8a-175">For more information, see [Microsoft Defender for Endpoint alert categories are now aligned with MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).</span></span>


## <a name="see-also"></a><span data-ttu-id="f7a8a-176">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f7a8a-176">See also</span></span>
- [<span data-ttu-id="f7a8a-177">Crear indicadores</span><span class="sxs-lookup"><span data-stu-id="f7a8a-177">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="f7a8a-178">Crear indicadores para los archivos</span><span class="sxs-lookup"><span data-stu-id="f7a8a-178">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="f7a8a-179">Crear indicadores para direcciones IP y URL/dominios</span><span class="sxs-lookup"><span data-stu-id="f7a8a-179">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="f7a8a-180">Crear indicadores basados en certificados</span><span class="sxs-lookup"><span data-stu-id="f7a8a-180">Create indicators based on certificates</span></span>](indicator-certificates.md)
