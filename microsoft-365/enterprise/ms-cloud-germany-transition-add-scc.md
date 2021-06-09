---
title: Información sobre la experiencia de exhibición de documentos electrónicos durante la migración desde Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumen: pasos de migración de exhibición de documentos electrónicos para la migración desde Microsoft Cloud Deutschland.'
ms.openlocfilehash: 0128c8563b2043e4ec41d2c5ab1b208bd3977511
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844255"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="b7846-103">Información sobre la experiencia de exhibición de documentos electrónicos durante la migración desde Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="b7846-103">Information about the eDiscovery experience during the migration from Microsoft Cloud Deutschland</span></span>
<span data-ttu-id="b7846-104">Las secciones siguientes proporcionan información adicional sobre la experiencia de exhibición de documentos electrónicos al pasar de Microsoft Cloud Germany (Microsoft Cloud Deutschland) a Office 365 servicios en la nueva región del centro de datos alemán.</span><span class="sxs-lookup"><span data-stu-id="b7846-104">The following sections provide additional information about the eDiscovery experience when moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="ediscovery-administration-until-phase-4"></a><span data-ttu-id="b7846-105">Administración de eDiscovery hasta la fase 4</span><span class="sxs-lookup"><span data-stu-id="b7846-105">eDiscovery administration until phase 4</span></span>
<span data-ttu-id="b7846-106">Hasta la fase 4, el Centro de seguridad y cumplimiento estará totalmente disponible.</span><span class="sxs-lookup"><span data-stu-id="b7846-106">Until phase 4, the Security and Compliance Center will be fully available.</span></span> <span data-ttu-id="b7846-107">Todo el contenido sigue estando en Microsoft Cloud Germany y es manejable por el Centro de seguridad y cumplimiento de Microsoft Cloud Germany ( https://protection.office.de/) .</span><span class="sxs-lookup"><span data-stu-id="b7846-107">All content still remains in the Microsoft Cloud Germany and is manageable by the Microsoft Cloud Germany Security and Compliance Center (https://protection.office.de/).</span></span>

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a><span data-ttu-id="b7846-108">Experiencia de exhibición de documentos electrónicos entre la fase 4 y el final de la fase 9</span><span class="sxs-lookup"><span data-stu-id="b7846-108">eDiscovery experience between phase 4 until the the end of phase 9</span></span>
<span data-ttu-id="b7846-109">Desde el principio de la fase 4 hasta que se complete la fase 9, las búsquedas de exhibición de documentos electrónicos producirán un error o devolverán 0 resultados para las ubicaciones de SharePoint Online, OneDrive para la Empresa y Exchange Online que se han migrado.</span><span class="sxs-lookup"><span data-stu-id="b7846-109">From the beginning of phase 4 until phase 9 is completed, eDiscovery searches will fail or return 0 results for SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated.</span></span>

> [!NOTE]
> <span data-ttu-id="b7846-110">Durante la migración, los clientes pueden seguir crear casos, retenciones, búsquedas y exportaciones en el Centro de seguridad [& cumplimiento,](/microsoft-365/compliance/manage-legal-investigations)incluida [la búsqueda de contenido.](/microsoft-365/compliance/search-for-content)</span><span class="sxs-lookup"><span data-stu-id="b7846-110">During migration, customers can continue to create cases, holds, searches, and exports in the [Security & Compliance Center](/microsoft-365/compliance/manage-legal-investigations), including [Content Search](/microsoft-365/compliance/search-for-content).</span></span> <span data-ttu-id="b7846-111">Sin embargo, las búsquedas en SharePoint Online, OneDrive para la Empresa y Exchange Online que se han migrado devolverán 0 resultados o producirán un error.</span><span class="sxs-lookup"><span data-stu-id="b7846-111">However, searches against SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated will either return 0 results or produce an error.</span></span>

<span data-ttu-id="b7846-112">En caso de que una búsqueda devuelva cero resultados o un error durante la migración, haga lo siguiente para SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="b7846-112">In the event that a search returns zero results or an error during migration, please take the following action for SharePoint Online:</span></span>

- <span data-ttu-id="b7846-113">Descargue los sitios directamente desde el sitio SharePoint Online o OneDrive para la Empresa siguiendo las instrucciones de Descargar archivos y carpetas de [OneDrive o SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05).</span><span class="sxs-lookup"><span data-stu-id="b7846-113">Download sites directly from the SharePoint Online or OneDrive for Business site by following the instructions in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05).</span></span> <span data-ttu-id="b7846-114">Este método requerirá permisos SharePoint administrador en línea o permisos de solo lectura en el sitio.</span><span class="sxs-lookup"><span data-stu-id="b7846-114">This method will require SharePoint Online administrator permissions or read-only permissions on the site.</span></span>
- <span data-ttu-id="b7846-115">Si se superan los límites, como se explica en Descargar archivos y carpetas de OneDrive o [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)los clientes pueden usar el cliente de sincronización de OneDrive para la Empresa siguiendo las instrucciones de Sincronizar SharePoint y [Teams](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)archivos con el equipo .</span><span class="sxs-lookup"><span data-stu-id="b7846-115">If limits are exceeded, as explained in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), customers can use the OneDrive for Business sync client by following the guidance in [Sync SharePoint and Teams files with your computer](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88).</span></span>

- <span data-ttu-id="b7846-116">Para obtener más información, [vea eDiscovery local en Exchange Server](/Exchange/policy-and-compliance/ediscovery/ediscovery).</span><span class="sxs-lookup"><span data-stu-id="b7846-116">For more information, see  [In-Place eDiscovery in Exchange Server](/Exchange/policy-and-compliance/ediscovery/ediscovery).</span></span>


## <a name="ediscovery-administration-after-phase-9"></a><span data-ttu-id="b7846-117">Administración de eDiscovery después de la fase 9</span><span class="sxs-lookup"><span data-stu-id="b7846-117">eDiscovery administration after phase 9</span></span>

<span data-ttu-id="b7846-118">**Se aplica a:** Todos los clientes que usan eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b7846-118">**Applies to:** All customers using eDiscovery</span></span>

<span data-ttu-id="b7846-119">En la fase 9, se completarán los pasos finales para pasar a la nueva región del centro de datos alemán.</span><span class="sxs-lookup"><span data-stu-id="b7846-119">In phase 9, the final steps for moving to the new German datacenter region will be completed.</span></span> <span data-ttu-id="b7846-120">En esta fase, se migrarán todos los componentes de servicio restantes.</span><span class="sxs-lookup"><span data-stu-id="b7846-120">In this phase, all remaining service components will be migrated.</span></span>
<span data-ttu-id="b7846-121">Después de la fase 9, ya no se admite el uso del Centro de seguridad y cumplimiento en Microsoft Cloud Germany (protection.office.de).</span><span class="sxs-lookup"><span data-stu-id="b7846-121">After phase 9, using the Security and Compliance Center in Microsoft Cloud Germany (protection.office.de) is no longer supported.</span></span> <span data-ttu-id="b7846-122">En su lugar, use el nuevo [Centro de seguridad](https://security.microsoft.com/) o centro de [cumplimiento.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="b7846-122">Please use the new [Security Center](https://security.microsoft.com/) or [Compliance Center](https://compliance.microsoft.com/) instead.</span></span> <span data-ttu-id="b7846-123">Todos los datos se han migrado a los nuevos portales de administración.</span><span class="sxs-lookup"><span data-stu-id="b7846-123">All data have been migrated to the new admin portals.</span></span>

| <span data-ttu-id="b7846-124">Pasos</span><span class="sxs-lookup"><span data-stu-id="b7846-124">Step(s)</span></span> | <span data-ttu-id="b7846-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7846-125">Description</span></span> | <span data-ttu-id="b7846-126">Impacto</span><span class="sxs-lookup"><span data-stu-id="b7846-126">Impact</span></span> |
|:-------|:-------|:-------|
|  <span data-ttu-id="b7846-127">Todas SharePoint online, OneDrive para la Empresa y Exchange Online se han migrado junto con el Centro de seguridad y cumplimiento (SCC).</span><span class="sxs-lookup"><span data-stu-id="b7846-127">All SharePoint Online, OneDrive for Business, and Exchange Online locations have been migrated along with the Security and Compliance Center (SCC).</span></span> | <span data-ttu-id="b7846-128">Toda la actividad de exhibición de documentos electrónicos debe ejecutarse desde el espacio empresarial mundial.</span><span class="sxs-lookup"><span data-stu-id="b7846-128">All eDiscovery activity should be run from the worldwide tenant.</span></span> <span data-ttu-id="b7846-129">Las búsquedas ahora serán 100% correctas.</span><span class="sxs-lookup"><span data-stu-id="b7846-129">Searches will now be 100% successful.</span></span> <span data-ttu-id="b7846-130">Cualquier error o error debe seguir los canales de soporte técnico normales.</span><span class="sxs-lookup"><span data-stu-id="b7846-130">Any failures or errors should follow normal support channels.</span></span> | <span data-ttu-id="b7846-131">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b7846-131">None</span></span> |
||||

### <a name="ediscovery-retention-policy"></a><span data-ttu-id="b7846-132">Directiva de retención de eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b7846-132">eDiscovery Retention Policy</span></span>
<span data-ttu-id="b7846-133">**Se aplica a:**  Todos los clientes que aplicaron una directiva de retención como parte de los pasos previos a la migración</span><span class="sxs-lookup"><span data-stu-id="b7846-133">**Applies to:**  All customers who applied a retention policy as part of the pre-migration steps</span></span>

| <span data-ttu-id="b7846-134">Pasos</span><span class="sxs-lookup"><span data-stu-id="b7846-134">Step(s)</span></span> | <span data-ttu-id="b7846-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7846-135">Description</span></span> | <span data-ttu-id="b7846-136">Impacto</span><span class="sxs-lookup"><span data-stu-id="b7846-136">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="b7846-137">Quitar directivas de retención de toda la organización que se crearon durante los pasos previos a la migración</span><span class="sxs-lookup"><span data-stu-id="b7846-137">Remove organization-wide retention policies that were created during pre-migration steps</span></span> | <span data-ttu-id="b7846-138">Los clientes pueden quitar las directivas de retención de toda la organización que se crearon durante el trabajo previo a la migración de los clientes.</span><span class="sxs-lookup"><span data-stu-id="b7846-138">Customers can remove the organization-wide retention policies that were created during the customers' pre-migration work.</span></span> | <span data-ttu-id="b7846-139">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b7846-139">None</span></span> |
||||
