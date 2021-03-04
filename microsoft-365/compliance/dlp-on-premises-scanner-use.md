---
title: Usar el examinador de prevención de pérdida de datos locales de Microsoft 365 (versión preliminar)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Obtenga información sobre cómo usar el examinador local de prevención de pérdida de datos de Microsoft 365 para examinar los datos almacenados e implementar las acciones de protección para los recursos compartidos de archivos locales y las carpetas y bibliotecas de documentos de SharePoint local.
ms.openlocfilehash: 34be93f5c9980a7f8ea8ad31b708af14a8725f73
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2021
ms.locfileid: "50417393"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="69678-103">Usar el examinador de prevención de pérdida de datos locales de Microsoft 365 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="69678-103">Use the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="69678-104">Para ayudarle a familiarizarse con las características de DLP locales y la forma en la que se muestran en las directivas DLP, hemos recopilado algunos escenarios que puede seguir.</span><span class="sxs-lookup"><span data-stu-id="69678-104">To help familiarize you with DLP on-premises features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69678-105">Estos escenarios DLP locales no son los procedimientos oficiales para crear y optimizar directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="69678-105">These DLP on-premises scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="69678-106">Consulte los temas siguientes cuando necesite trabajar con directivas DLP en situaciones generales:</span><span class="sxs-lookup"><span data-stu-id="69678-106">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="69678-107">Información general sobre la prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="69678-107">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="69678-108">Introducción a la directiva predeterminada de DLP</span><span class="sxs-lookup"><span data-stu-id="69678-108">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="69678-109">Crear una directiva DLP a partir de una plantilla</span><span class="sxs-lookup"><span data-stu-id="69678-109">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="69678-110">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="69678-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a><span data-ttu-id="69678-111">Escenario: Descubrir los archivos que coinciden con las reglas DLP</span><span class="sxs-lookup"><span data-stu-id="69678-111">Scenario: Discover files matching DLP rules</span></span>

<span data-ttu-id="69678-112">Los datos del examinador de DLP local aparecen en varias áreas</span><span class="sxs-lookup"><span data-stu-id="69678-112">Data from DLP on-premises scanner surfaces in several areas</span></span>

#### <a name="activity-explorer"></a><span data-ttu-id="69678-113">Explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="69678-113">Activity explorer</span></span>

 <span data-ttu-id="69678-114">Microsoft DLP para el entorno local detecta coincidencias de reglas DLP e informa de ellas en [Explorador de actividad](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).</span><span class="sxs-lookup"><span data-stu-id="69678-114">Microsoft DLP for on-premises detects DLP rule matches and reports them to [Activity Explorer](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).</span></span> 
 
#### <a name="microsoft-365-audit-log"></a><span data-ttu-id="69678-115">Registro de auditoría de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69678-115">Microsoft 365 Audit log</span></span>

<span data-ttu-id="69678-116">Durante la versión preliminar pública, las coincidencias de reglas DLP están disponibles en la interfaz de usuario del registro de auditoría. Vea [Buscar en el registro de auditoría del Centro de cumplimiento](search-the-audit-log-in-security-and-compliance.md) o use [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69678-116">During the public preview the DLP rule matches are available in Audit log UI, see [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md)  or accessible by [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell.</span></span>

#### <a name="aip"></a><span data-ttu-id="69678-117">AIP</span><span class="sxs-lookup"><span data-stu-id="69678-117">AIP</span></span>

<span data-ttu-id="69678-118">Los datos de descubrimiento legal están disponibles en un informe local en formato CSV que se almacena en:</span><span class="sxs-lookup"><span data-stu-id="69678-118">Discovery data is available in a local report in csv format which is stored under:</span></span>

<span data-ttu-id="69678-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span><span class="sxs-lookup"><span data-stu-id="69678-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span></span>

 <span data-ttu-id="69678-120">Busque las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="69678-120">Look for the following columns:</span></span>
- <span data-ttu-id="69678-121">Modo de DLP</span><span class="sxs-lookup"><span data-stu-id="69678-121">DLP Mode</span></span>
- <span data-ttu-id="69678-122">Estado de DLP</span><span class="sxs-lookup"><span data-stu-id="69678-122">DLP Status</span></span>
- <span data-ttu-id="69678-123">Comentario de DLP</span><span class="sxs-lookup"><span data-stu-id="69678-123">DLP Comment</span></span>
- <span data-ttu-id="69678-124">Acciones de DLP de nombre de regla DLP</span><span class="sxs-lookup"><span data-stu-id="69678-124">DLP Rule Name DLP Actions</span></span>
- <span data-ttu-id="69678-125">Propietario</span><span class="sxs-lookup"><span data-stu-id="69678-125">Owner</span></span>
- <span data-ttu-id="69678-126">Permisos NTFS actuales (SDDL)</span><span class="sxs-lookup"><span data-stu-id="69678-126">Current NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="69678-127">Permisos NTFS aplicados (SDDL)</span><span class="sxs-lookup"><span data-stu-id="69678-127">Applied NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="69678-128">Tipo de permisos NTFS</span><span class="sxs-lookup"><span data-stu-id="69678-128">NTFS permissions type</span></span>
 
### <a name="scenario-enforce-dlp-rule"></a><span data-ttu-id="69678-129">Escenario: exigir regla DLP</span><span class="sxs-lookup"><span data-stu-id="69678-129">Scenario: Enforce DLP rule</span></span> 

<span data-ttu-id="69678-130">Si quiere exigir las reglas DLP en los archivos examinados, debe habilitarse la obligación de aplicarlas en el trabajo de análisis de contenido en AIP y a nivel de directiva en DLP.</span><span class="sxs-lookup"><span data-stu-id="69678-130">If you want to enforce DLP rules on the scanned files, enforcement must be enabled on both the content scan job in AIP and at the policy level in DLP.</span></span>


#### <a name="configure-dlp-to-enforce-policy-actions"></a><span data-ttu-id="69678-131">Configurar DLP para obligar a aplicar acciones de directiva</span><span class="sxs-lookup"><span data-stu-id="69678-131">Configure DLP to enforce policy actions</span></span>

1. <span data-ttu-id="69678-132">Abra la página [Prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies) y seleccione la directiva DLP dirigida a los repositorios de ubicación locales que haya configurado en AIP.</span><span class="sxs-lookup"><span data-stu-id="69678-132">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) and select the DLP policy that is targeted to the on-premises location repositories you have configured in AIP.</span></span> 
2. <span data-ttu-id="69678-133">Edite la directiva.</span><span class="sxs-lookup"><span data-stu-id="69678-133">Edit the policy.</span></span>
3. <span data-ttu-id="69678-134">En la página **Probar o habilitar la directiva**, seleccione **Sí, activar inmediatamente**.</span><span class="sxs-lookup"><span data-stu-id="69678-134">On the **Test or turn on the policy** page, select **Yes, turn it on right away**.</span></span> 

## <a name="see-also"></a><span data-ttu-id="69678-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="69678-135">See also</span></span>

- [<span data-ttu-id="69678-136">Obtener información acerca del examinador local DLP (vista previa)</span><span class="sxs-lookup"><span data-stu-id="69678-136">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="69678-137">Introducción al examinador local DLP (vista previa)</span><span class="sxs-lookup"><span data-stu-id="69678-137">Get started with  DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-get-started.md)
- [<span data-ttu-id="69678-138">Información general sobre la prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="69678-138">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="69678-139">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="69678-139">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="69678-140">Introducción al explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="69678-140">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
