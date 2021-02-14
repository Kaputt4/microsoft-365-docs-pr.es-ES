---
title: Ver los informes de prevención de pérdida de datos
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Use los informes DLP de Office 365 para ver el número de coincidencias de directivas DLP, invalidaciones o falsos positivos y ver si son tendencias ascendentes o descendentes con el tiempo.
ms.openlocfilehash: 1ddcd60dc9314779ade2f7ceae02d336f902e483
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819000"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="6da4a-103">Ver los informes de prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="6da4a-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="6da4a-104">Después de crear las directivas de prevención de pérdida de datos (DLP), es posible que desee comprobar que funcionen según lo previsto y le ayudarán a cumplir las normativas.</span><span class="sxs-lookup"><span data-stu-id="6da4a-104">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant.</span></span> <span data-ttu-id="6da4a-105">Con los informes DLP en el Centro de &amp; cumplimiento de seguridad, puede ver rápidamente:</span><span class="sxs-lookup"><span data-stu-id="6da4a-105">With the DLP reports in the Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="6da4a-106">**Coincidencias de directiva DLP** Este informe muestra el recuento de coincidencias de directivas DLP con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="6da4a-106">**DLP policy matches** This report shows the count of DLP policy matches over time.</span></span> <span data-ttu-id="6da4a-107">Puede filtrar el informe por fecha, ubicación, directiva o acción.</span><span class="sxs-lookup"><span data-stu-id="6da4a-107">You can filter the report by date, location, policy, or action.</span></span> <span data-ttu-id="6da4a-108">Puede usar este informe para:</span><span class="sxs-lookup"><span data-stu-id="6da4a-108">You can use this report to:</span></span> 
    
  - <span data-ttu-id="6da4a-109">Ajuste o refine las directivas DLP a medida que las ejecuta en modo de prueba.</span><span class="sxs-lookup"><span data-stu-id="6da4a-109">Tune or refine your DLP policies as you run them in test mode.</span></span> <span data-ttu-id="6da4a-110">Puede ver la regla específica que coincidió con el contenido.</span><span class="sxs-lookup"><span data-stu-id="6da4a-110">You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="6da4a-111">Centrarse en períodos de tiempo específicos y comprender las causas de los picos y las tendencias.</span><span class="sxs-lookup"><span data-stu-id="6da4a-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="6da4a-112">Descubrir los procesos de negocio que infringen las directivas DLP de su organización.</span><span class="sxs-lookup"><span data-stu-id="6da4a-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="6da4a-113">Comprenda el impacto empresarial de las directivas DLP al ver qué acciones se aplican al contenido.</span><span class="sxs-lookup"><span data-stu-id="6da4a-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="6da4a-114">Comprobar el cumplimiento de una directiva DLP específica mostrando las coincidencias de dicha directiva.</span><span class="sxs-lookup"><span data-stu-id="6da4a-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="6da4a-115">Vea una lista de los principales usuarios y repita los usuarios que contribuyen a los incidentes de su organización.</span><span class="sxs-lookup"><span data-stu-id="6da4a-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="6da4a-116">Vea una lista de los tipos principales de información confidencial de su organización.</span><span class="sxs-lookup"><span data-stu-id="6da4a-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="6da4a-117">**Incidentes de DLP** Este informe también muestra coincidencias de directiva con el tiempo, como el informe de coincidencias de directiva.</span><span class="sxs-lookup"><span data-stu-id="6da4a-117">**DLP incidents** This report also shows policy matches over time, like the policy matches report.</span></span> <span data-ttu-id="6da4a-118">Sin embargo, el informe de coincidencias de directiva muestra coincidencias en un nivel de regla; por ejemplo, si un correo electrónico coincide con tres reglas diferentes, el informe de coincidencias de directiva muestra tres elementos de línea diferentes.</span><span class="sxs-lookup"><span data-stu-id="6da4a-118">However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items.</span></span> <span data-ttu-id="6da4a-119">Por el contrario, el informe de incidentes muestra coincidencias en un nivel de elemento; por ejemplo, si un correo electrónico coincide con tres reglas diferentes, el informe de incidentes muestra un único elemento de línea para ese elemento de contenido.</span><span class="sxs-lookup"><span data-stu-id="6da4a-119">By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="6da4a-120">Dado que los recuentos de informes se agregan de forma diferente, el informe de coincidencias de directivas es mejor para identificar coincidencias con reglas específicas y ajustar directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="6da4a-120">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies.</span></span> <span data-ttu-id="6da4a-121">El informe de incidentes es mejor para identificar partes específicas de contenido que son problemáticas para las directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="6da4a-121">The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="6da4a-122">**Falsos positivos e invalidaciones de DLP** Si la directiva DLP permite a los usuarios invalidarla o notificar un falso positivo, este informe muestra un recuento de esas instancias a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="6da4a-122">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time.</span></span> <span data-ttu-id="6da4a-123">Puede filtrar el informe por fecha, ubicación o directiva.</span><span class="sxs-lookup"><span data-stu-id="6da4a-123">You can filter the report by date, location, or policy.</span></span> <span data-ttu-id="6da4a-124">Puede usar este informe para:</span><span class="sxs-lookup"><span data-stu-id="6da4a-124">You can use this report to:</span></span> 
    
  - <span data-ttu-id="6da4a-125">Ajuste o refine las directivas DLP al ver qué directivas incurren en un gran número de falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="6da4a-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="6da4a-126">Vea las justificaciones enviadas por los usuarios cuando resuelven una sugerencia de directiva invalidando la directiva.</span><span class="sxs-lookup"><span data-stu-id="6da4a-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="6da4a-127">Descubra dónde están en conflicto las directivas DLP con procesos de negocio válidos al incurrir en un gran número de invalidaciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="6da4a-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="6da4a-128">Todos los informes DLP pueden mostrar datos del período de cuatro meses más reciente.</span><span class="sxs-lookup"><span data-stu-id="6da4a-128">All DLP reports can show data from the most recent four-month time period.</span></span> <span data-ttu-id="6da4a-129">Los datos más recientes pueden tardar hasta 24 horas en aparecer en los informes.</span><span class="sxs-lookup"><span data-stu-id="6da4a-129">The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="6da4a-130">Puede encontrar estos informes en el Panel de informes &amp; del Centro de cumplimiento \> **de** \> **seguridad.**</span><span class="sxs-lookup"><span data-stu-id="6da4a-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![Informe de coincidencias de directiva DLP](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="6da4a-132">Ver la justificación enviada por un usuario para una invalidación</span><span class="sxs-lookup"><span data-stu-id="6da4a-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="6da4a-133">Si la directiva DLP permite a los usuarios invalidarla, puede usar el informe de falsos positivos e invalidación para ver el texto enviado por los usuarios en la sugerencia de directiva.</span><span class="sxs-lookup"><span data-stu-id="6da4a-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![Campo de justificación en los detalles del informe de falso positivo e invalidación de DLP](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="6da4a-135">Tomar medidas sobre perspectivas y recomendaciones</span><span class="sxs-lookup"><span data-stu-id="6da4a-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="6da4a-136">Los informes pueden mostrar información y recomendaciones donde puede hacer clic en el icono de advertencia roja para ver detalles sobre posibles problemas y tomar posibles medidas correctivas.</span><span class="sxs-lookup"><span data-stu-id="6da4a-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![Hacer clic en un icono de información para ver los detalles y las acciones que se deben realizar](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a><span data-ttu-id="6da4a-138">Permisos para informes DLP</span><span class="sxs-lookup"><span data-stu-id="6da4a-138">Permissions for DLP reports</span></span>

<span data-ttu-id="6da4a-139">Para ver informes DLP en el Centro de & cumplimiento, debe tener asignado lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6da4a-139">To view DLP reports in the Security & Compliance Center, you have to be assigned the:</span></span>

- <span data-ttu-id="6da4a-140">**Rol Lector de** seguridad en el Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="6da4a-140">**Security Reader** role in the Exchange admin center.</span></span> <span data-ttu-id="6da4a-141">De forma predeterminada, este rol se asigna a los grupos de roles Administración de la organización y Lector de seguridad en el Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="6da4a-141">By default, this role is assigned to the Organization Management and Security Reader role groups in the Exchange admin center.</span></span>

- <span data-ttu-id="6da4a-142">**Rol Administración de cumplimiento DLP de solo** vista en el Centro de & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="6da4a-142">**View-Only DLP Compliance Management** role in the Security & Compliance Center.</span></span> <span data-ttu-id="6da4a-143">De forma predeterminada, este rol se asigna a los grupos de roles Administrador de cumplimiento, Administración de la organización, Administrador de seguridad y Lector de seguridad en el Centro de & Cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="6da4a-143">By default, this role is assigned to the Compliance Administrator, Organization Management, Security Administrator, and Security Reader role groups in the Security & Compliance Center.</span></span>

- <span data-ttu-id="6da4a-144">**Rol Destinatarios de solo vista** en el Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="6da4a-144">**View-Only Recipients** role in the Exchange admin center.</span></span> <span data-ttu-id="6da4a-145">De forma predeterminada, este rol se asigna a los grupos de roles Administración de cumplimiento, Administración de la organización y Administración View-Only organización en el Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="6da4a-145">By default, this role is assigned to the Compliance Management, Organization Management, and View-Only Organization Management role groups in the Exchange admin center.</span></span>

## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="6da4a-146">Buscar los cmdlets para los informes DLP</span><span class="sxs-lookup"><span data-stu-id="6da4a-146">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="6da4a-147">Para usar la mayoría de los cmdlets para el Centro de seguridad y cumplimiento, necesita:</span><span class="sxs-lookup"><span data-stu-id="6da4a-147">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="6da4a-148">Conectarse al Centro de &amp; cumplimiento de seguridad con PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="6da4a-148">Connect to the Security &amp; Compliance Center using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="6da4a-149">Usar cualquiera de estos [ &amp; cmdlets del Centro de cumplimiento de seguridad](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="6da4a-149">Use any of these [Security &amp; Compliance Center cmdlets](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="6da4a-150">Sin embargo, los informes de DLP necesitan extraer datos de todo Office 365, incluido Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6da4a-150">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="6da4a-151">Por este motivo, los cmdlets de los informes DLP están disponibles en Exchange Online Powershell, no en powershell del Centro de &amp; cumplimiento de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6da4a-151">For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell.</span></span> <span data-ttu-id="6da4a-152">Por lo tanto, para usar los cmdlets para los informes de DLP, debe:</span><span class="sxs-lookup"><span data-stu-id="6da4a-152">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="6da4a-153">Conectarse a Exchange Online mediante PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="6da4a-153">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. <span data-ttu-id="6da4a-154">Use cualquiera de estos cmdlets para los informes de DLP:</span><span class="sxs-lookup"><span data-stu-id="6da4a-154">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="6da4a-155">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="6da4a-155">Get-DlpDetectionsReport</span></span>](https://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [<span data-ttu-id="6da4a-156">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="6da4a-156">Get-DlpDetailReport</span></span>](https://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

