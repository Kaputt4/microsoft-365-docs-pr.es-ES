---
title: Introducción al examinador de prevención de pérdida de datos de Microsoft 365 en el entorno local (versión preliminar)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
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
description: Configurar el examinador de prevención de pérdida de datos de Microsoft 365 en el entorno local
ms.openlocfilehash: 0390ac48b351b30b75109a3e3a5d18c80847c9d2
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289204"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="4880b-103">Introducción al examinador de prevención de pérdida de datos en el entorno local (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="4880b-103">Get started with the data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="4880b-104">Este artículo le guiará por los requisitos previos y la configuración para el examinador de prevención de pérdida de datos de Microsoft 365 en el entorno local.</span><span class="sxs-lookup"><span data-stu-id="4880b-104">This article walks you through the prerequisites and configuration for the Microsoft 365 data loss prevention on-premises scanner.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4880b-105">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="4880b-105">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="4880b-106">Licencias de SKU/suscripciones</span><span class="sxs-lookup"><span data-stu-id="4880b-106">SKU/subscriptions licensing</span></span>

<span data-ttu-id="4880b-107">Antes de empezar con el examinador de DLP local, debe confirmar su [Suscripción a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) y cualquier complemento.</span><span class="sxs-lookup"><span data-stu-id="4880b-107">Before you get started with DLP on-premises scanner, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="4880b-108">Para participar en la versión preliminar, la cuenta de administrador que configura las reglas de DLP debe tener asignada una de las siguientes licencias:</span><span class="sxs-lookup"><span data-stu-id="4880b-108">To participate in the preview the admin account that sets up the DLP rules must be assigned one of the following licenses:</span></span>

- <span data-ttu-id="4880b-109">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4880b-109">Microsoft 365 E5</span></span>
- <span data-ttu-id="4880b-110">Cumplimiento de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4880b-110">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="4880b-111">Gobernanza y protección de la información de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4880b-111">Microsoft 365 E5 Information Protection & Governance</span></span> 


<span data-ttu-id="4880b-112">Para más información sobre las licencias, vea: [Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span><span class="sxs-lookup"><span data-stu-id="4880b-112">For full licensing details see: [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span></span>

### <a name="permissions"></a><span data-ttu-id="4880b-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="4880b-113">Permissions</span></span>


<span data-ttu-id="4880b-114">Los datos del examinador DLP en el entorno local se pueden ver en el [Explorador de actividades](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="4880b-114">Data from DLP on-premises scanner can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="4880b-115">Hay cuatro roles que conceden permisos al explorador de actividad; la cuenta que use para acceder a los datos debe pertenecer a uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="4880b-115">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="4880b-116">Administrador global</span><span class="sxs-lookup"><span data-stu-id="4880b-116">Global administrator</span></span>
- <span data-ttu-id="4880b-117">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="4880b-117">Compliance administrator</span></span>
- <span data-ttu-id="4880b-118">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="4880b-118">Security administrator</span></span>
- <span data-ttu-id="4880b-119">Administrador de datos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="4880b-119">Compliance data administrator</span></span>

### <a name="dlp-on-premises-scanner-prerequisites"></a><span data-ttu-id="4880b-120">Requisitos previos del examinador de DLP en el entorno local</span><span class="sxs-lookup"><span data-stu-id="4880b-120">DLP on-premises scanner prerequisites</span></span>

- <span data-ttu-id="4880b-p103">El examinador de Azure Information Protection (AIP) implementa la coincidencia de directiva DLP y el cumplimiento de la directiva. El examinador se instala como parte del cliente de AIP, por lo que la instalación debe cumplir todos los requisitos previos para AIP, el cliente AIP y el examinador de etiquetas unificado de AIP.</span><span class="sxs-lookup"><span data-stu-id="4880b-p103">The Azure Information Protection (AIP) scanner implements DLP policy matching and policy enforcement. The scanner is installed as part of the AIP client so your installation must meet all the prerequisites  for AIP, the AIP client, and the AIP unified labeling scanner.</span></span>
- <span data-ttu-id="4880b-123">Implementar el examinador y el cliente de AIP.</span><span class="sxs-lookup"><span data-stu-id="4880b-123">Deploy the AIP  client and scanner.</span></span> <span data-ttu-id="4880b-124">Para obtener más información [Instale el cliente de etiquetas unificado de AIP](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) y [], vea [Configurar e instalar el examinador de etiquetas unificado de Azure Information Protection](/azure/information-protection/deploy-aip-scanner-configure-install).</span><span class="sxs-lookup"><span data-stu-id="4880b-124">For more information [Install the AIP unified labeling client](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) and [], see [Configuring and installing the Azure Information Protection unified labeling scanner](/azure/information-protection/deploy-aip-scanner-configure-install).</span></span>
- <span data-ttu-id="4880b-125">Debe haber al menos una etiqueta y una directiva publicadas en el espacio empresarial, incluso si todas sus reglas de detección se basan únicamente en tipos de información confidenciales.</span><span class="sxs-lookup"><span data-stu-id="4880b-125">There must be at least one label and policy published in the tenant, even if all your detection rules are based on sensitive information types only.</span></span>

## <a name="deploy-the-dlp-on-premises-scanner"></a><span data-ttu-id="4880b-126">Implementar el examinador local de DLP</span><span class="sxs-lookup"><span data-stu-id="4880b-126">Deploy the DLP on-premises scanner</span></span>

1. <span data-ttu-id="4880b-127">Siga los procedimientos descritos en [Instalar el cliente de etiquetas unificado de AIP](/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span><span class="sxs-lookup"><span data-stu-id="4880b-127">Follow the procedures in [Install the AIP unified labeling client](/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span></span> 
2. <span data-ttu-id="4880b-128">Siga los procedimientos descritos en [Configurar e instalar el examinador de etiquetas unificado de Azure Information Protection](/azure/information-protection/deploy-aip-scanner-configure-install) para completar la instalación del examinador.</span><span class="sxs-lookup"><span data-stu-id="4880b-128">Follow the procedures in [Configuring and installing the Azure Information Protection unified labeling scanner](/azure/information-protection/deploy-aip-scanner-configure-install) to complete the scanner installation.</span></span>
    1. <span data-ttu-id="4880b-129">La configuración de los trabajos de detección de red es un paso opcional.</span><span class="sxs-lookup"><span data-stu-id="4880b-129">Network discovery jobs configuration is an optional step.</span></span> <span data-ttu-id="4880b-130">Puede omitirlo y definir repositorios específicos que se examinarán en su trabajo de examen de contenido.</span><span class="sxs-lookup"><span data-stu-id="4880b-130">You can skip it and define specific repositories to be scanned in your content scan job.</span></span>
    2. <span data-ttu-id="4880b-131">Debe crear un trabajo de examen de contenido y especificar los repositorios que alojan archivos que deben ser evaluados por el motor de DLP.</span><span class="sxs-lookup"><span data-stu-id="4880b-131">You must create content scan job and specify the repositories that host files that need to be evaluated by the DLP engine.</span></span>
    3. <span data-ttu-id="4880b-132">Habilite las reglas de DLP en el trabajo de examen de contenido creado y establezca la opción **Aplicar** en **Desactivar**, a menos que desee avanzar directamente a la fase de aplicación de DLP.</span><span class="sxs-lookup"><span data-stu-id="4880b-132">Enable DLP rules in the created Content scan job, and set the **Enforce** option to **Off**, unless you want to proceed directly to the DLP enforcement stage.</span></span>
3. <span data-ttu-id="4880b-p106">Verifique que su trabajo de examen de contenido esté asignado al clúster correcto. Si aún no ha creado un trabajo de examen de contenido, cree uno nuevo y asígnelo al clúster que contenga los nodos del examinador que ejecutan la versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="4880b-p106">Verify that you content scan job is assigned to the right cluster. If you still did not create a content scan job create a new one and assign it to the cluster that contains the scanner nodes that run the public preview version.</span></span>

4. <span data-ttu-id="4880b-135">Conéctese a la [Extensión de Azure Information Protection en Azure Portal](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) y agregue sus repositorios al trabajo de examen de contenido que realizará el examen.</span><span class="sxs-lookup"><span data-stu-id="4880b-135">Connect to the [Azure Information Protection extension in Azure portal](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) and add your repositories to the content scan job that will perform the scan.</span></span>

5. <span data-ttu-id="4880b-136">Realice una de las siguientes acciones para ejecutar su examen:</span><span class="sxs-lookup"><span data-stu-id="4880b-136">Do one of the following to run your scan:</span></span>
    1. <span data-ttu-id="4880b-137">establezca la programación del examinador</span><span class="sxs-lookup"><span data-stu-id="4880b-137">set the scanner schedule</span></span>
    1. <span data-ttu-id="4880b-138">use la opción de **Examinar ahora** en el portal</span><span class="sxs-lookup"><span data-stu-id="4880b-138">use the manual **Scan Now** option in the portal</span></span>
    1. <span data-ttu-id="4880b-139">o ejecutar **Start-AIPScan** cmdlet de PowerShell</span><span class="sxs-lookup"><span data-stu-id="4880b-139">or run **Start-AIPScan** PowerShell cmdlet</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4880b-140">Recuerde que el examinador ejecuta un examen diferencial del repositorio de forma predeterminada y los archivos que ya se han examinado en el ciclo de examen anterior se omitirán a menos que se haya cambiado el archivo o que haya iniciado de nuevo un examen completo.</span><span class="sxs-lookup"><span data-stu-id="4880b-140">Remember that the scanner runs a delta scan of the repository by default and the files that were already scanned in the previous scan cycle will be skipped unless the file was changed or you initiated a full rescan.</span></span> <span data-ttu-id="4880b-141">Puede iniciarse un nuevo examen completo utilizando la opción **Volver a examinar todos los archivos** en la interfaz de usuario o ejecutando **Start-AIPScan-Reset**.</span><span class="sxs-lookup"><span data-stu-id="4880b-141">Full rescan can be initiated by using **Rescan all files** option in the UI or by running **Start-AIPScan-Reset**.</span></span>

6.  <span data-ttu-id="4880b-142">Abra la [página de prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies) en el Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4880b-142">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center.</span></span>

7. <span data-ttu-id="4880b-143">Elija **crear una directiva de** y crear una directiva DLP de prueba.</span><span class="sxs-lookup"><span data-stu-id="4880b-143">Choose **Create policy** and create a test DLP policy.</span></span> <span data-ttu-id="4880b-144">Vea [Crear una directiva DLP desde una plantilla](create-a-dlp-policy-from-a-template.md) si necesita ayuda para crear una directiva.</span><span class="sxs-lookup"><span data-stu-id="4880b-144">See [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md) if you need help creating a policy.</span></span> <span data-ttu-id="4880b-145">Asegúrese de ejecutarlo en prueba hasta que se sienta cómodo con esta característica.</span><span class="sxs-lookup"><span data-stu-id="4880b-145">Be sure to run it in test until you are comfortable with this feature.</span></span> <span data-ttu-id="4880b-146">Use estos parámetros para la directiva:</span><span class="sxs-lookup"><span data-stu-id="4880b-146">Use these parameters for your policy:</span></span>
    1. <span data-ttu-id="4880b-147">Especifique el ámbito de la regla del examen de la DLP local para ubicaciones específicas si es necesario.</span><span class="sxs-lookup"><span data-stu-id="4880b-147">Scope the DLP on-premises scanner rule to specific locations if needed.</span></span> <span data-ttu-id="4880b-148">Si especifica el ámbito de **ubicaciones** a **Todo**, todos los archivos examinados por el examinador estarán sujetos a la coincidencia y la aplicación de las reglas de DLP.</span><span class="sxs-lookup"><span data-stu-id="4880b-148">If you scope **locations** to **All**, all files scanned by the scanner will be subject to the DLP rule matching and enforcement.</span></span>
    1. <span data-ttu-id="4880b-149">Al especificar las ubicaciones, puede usar la lista de exclusiones o inclusión.</span><span class="sxs-lookup"><span data-stu-id="4880b-149">When specifying the locations, you can use either exclusion or inclusion list.</span></span> <span data-ttu-id="4880b-150">Durante la versión preliminar pública no se pueden configurar ambas.</span><span class="sxs-lookup"><span data-stu-id="4880b-150">During public preview you cannot set both of them.</span></span> <span data-ttu-id="4880b-151">Puede definir que la regla sea relevante solo para las rutas que coincidan con uno de los patrones enumerados en la lista de inclusión o, todos los archivos, excepto los que coincidan con el patrón enumerado en la lista de inclusión.</span><span class="sxs-lookup"><span data-stu-id="4880b-151">You can either define that the rule is relevant only to paths matching one of the patterns listed in inclusion list or, all files, except the files matching the pattern listed in inclusion list.</span></span> <span data-ttu-id="4880b-152">No se admiten rutas locales.</span><span class="sxs-lookup"><span data-stu-id="4880b-152">No local paths are supported.</span></span> <span data-ttu-id="4880b-153">Estos son algunos ejemplos de rutas válidas:</span><span class="sxs-lookup"><span data-stu-id="4880b-153">Here are some examples of valid paths:</span></span>
      - <span data-ttu-id="4880b-154">\\\servidor\recurso compartido</span><span class="sxs-lookup"><span data-stu-id="4880b-154">\\\server\share</span></span>
      - <span data-ttu-id="4880b-155">\\\server\share\folder1\subfolderabc</span><span class="sxs-lookup"><span data-stu-id="4880b-155">\\\server\share\folder1\subfolderabc</span></span>
      - <span data-ttu-id="4880b-156">\*\\carpeta1</span><span class="sxs-lookup"><span data-stu-id="4880b-156">\*\\folder1</span></span>
      - <span data-ttu-id="4880b-157">\*secreto\*.docx</span><span class="sxs-lookup"><span data-stu-id="4880b-157">\*secret\*.docx</span></span>
      - <span data-ttu-id="4880b-158">\*secreto\*.\*</span><span class="sxs-lookup"><span data-stu-id="4880b-158">\*secret\*.\*</span></span>
      - <span data-ttu-id="4880b-159"> https:// sp2010.local/sites/HR</span><span class="sxs-lookup"><span data-stu-id="4880b-159">https:// sp2010.local/sites/HR</span></span>
      - <span data-ttu-id="4880b-160"> https://\*/HR</span><span class="sxs-lookup"><span data-stu-id="4880b-160">https://\*/HR</span></span> 
    3. <span data-ttu-id="4880b-161">Estos son algunos ejemplos de uso de valores no aceptados:</span><span class="sxs-lookup"><span data-stu-id="4880b-161">Here are some examples of unacceptable values use:</span></span>
      - \*
      - <span data-ttu-id="4880b-162">\*\\Un</span><span class="sxs-lookup"><span data-stu-id="4880b-162">\*\\a</span></span>
      - <span data-ttu-id="4880b-163">Aaa</span><span class="sxs-lookup"><span data-stu-id="4880b-163">Aaa</span></span>
      - <span data-ttu-id="4880b-164">c:</span><span class="sxs-lookup"><span data-stu-id="4880b-164">c:</span></span>\
      - <span data-ttu-id="4880b-165">C:\test</span><span class="sxs-lookup"><span data-stu-id="4880b-165">C:\test</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4880b-166">La lista de exclusiones tiene prioridad sobre la lista de inclusiones.</span><span class="sxs-lookup"><span data-stu-id="4880b-166">The exclusion list takes precedence over the inclusions list.</span></span>

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="4880b-167">Ver las alertas del examinador local de DLP en el panel de administración de alertas de DLP</span><span class="sxs-lookup"><span data-stu-id="4880b-167">Viewing DLP on-premises scanner alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="4880b-168">Abra la [página sobre la prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies) en el Centro de cumplimiento de Microsoft 365 y seleccione **Alertas**.</span><span class="sxs-lookup"><span data-stu-id="4880b-168">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center and select **Alerts**.</span></span>

2. <span data-ttu-id="4880b-169">Vea los procedimientos descritos en [Cómo configurar y ver las alertas de las directivas DLP](dlp-configure-view-alerts-policies.md) para ver las alertas de las directivas DLP del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="4880b-169">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a><span data-ttu-id="4880b-170">Ver el examinador local de DLP en el explorador de actividades y el registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="4880b-170">Viewing DLP on-premises scanner in activity explorer and audit log</span></span>

> [!NOTE]
> <span data-ttu-id="4880b-171">El examinador local requiere que se habilite la auditoría.</span><span class="sxs-lookup"><span data-stu-id="4880b-171">The on-premises scanner requires that auditing be enabled.</span></span> <span data-ttu-id="4880b-172">En Microsoft 365 la auditoría está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4880b-172">In Microsoft 365 auditing is enabled by default.</span></span>

1. <span data-ttu-id="4880b-173">Abra la [Página clasificación de datos](https://compliance.microsoft.com/dataclassification?viewid=overview) de su dominio en el Centro de cumplimiento de Microsoft 365 y seleccione Explorador de actividad.</span><span class="sxs-lookup"><span data-stu-id="4880b-173">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and select Activity explorer.</span></span>

2. <span data-ttu-id="4880b-174">Vea los procedimientos descritos en [Introducción al explorador de actividad](data-classification-activity-explorer.md) para acceder y filtrar todos los datos de las ubicaciones de los examinadores locales.</span><span class="sxs-lookup"><span data-stu-id="4880b-174">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your on-premises scanner locations.</span></span>

3. <span data-ttu-id="4880b-175">Abra el Buscar el [Registro de auditoría en el Centro de cumplimiento](https://security.microsoft.com/auditlogsearch).</span><span class="sxs-lookup"><span data-stu-id="4880b-175">Open the [Audit log in the Compliance center](https://security.microsoft.com/auditlogsearch).</span></span> <span data-ttu-id="4880b-176">Durante la versión preliminar pública, las coincidencias de reglas de DLP están disponibles en la interfaz de usuario del registro del registro de auditoría o mediante el PowerShell [Search-UnifiedAudLog](/powershell/module/exchange/search-unifiedauditlog).</span><span class="sxs-lookup"><span data-stu-id="4880b-176">During the public preview the DLP rule matches are available in Audit log UI or accessible by [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell</span></span> 


## <a name="next-steps"></a><span data-ttu-id="4880b-177">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="4880b-177">Next steps</span></span>
<span data-ttu-id="4880b-178">Ahora que ha implementado una directiva de prueba para las ubicaciones locales de DLP y que puede ver los datos de actividad en el Explorador de actividades, está listo para pasar al siguiente paso, donde creará directivas DLP que protejan sus elementos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="4880b-178">Now that you have deployed a test policy for DLP on-premises locations and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="4880b-179">Usar DLP local (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="4880b-179">Using DLP on-premises (preview)</span></span>](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a><span data-ttu-id="4880b-180">Vea también</span><span class="sxs-lookup"><span data-stu-id="4880b-180">See also</span></span>

- [<span data-ttu-id="4880b-181">Obtener información acerca del examinador local de DLP (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="4880b-181">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="4880b-182">Usar el examinador local de DLP (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="4880b-182">Use DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-use.md)
- [<span data-ttu-id="4880b-183">Obtenga más información acerca de la prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="4880b-183">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="4880b-184">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="4880b-184">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="4880b-185">Introducción al explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="4880b-185">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="4880b-186">Suscripción a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4880b-186">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)