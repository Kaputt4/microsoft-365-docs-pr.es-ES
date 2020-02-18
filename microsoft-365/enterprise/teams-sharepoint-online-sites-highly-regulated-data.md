---
title: Sitios de SharePoint para datos altamente regulados
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- SPO_Content
ms.custom: ''
description: Cree un sitio de grupo de SharePoint seguro para almacenar los archivos más importantes y confidenciales.
ms.openlocfilehash: c74a2bc59a6ef9d16ecd0dfbed06d577bd98649b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085069"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="e52a7-103">Sitios de SharePoint para datos altamente regulados</span><span class="sxs-lookup"><span data-stu-id="e52a7-103">SharePoint sites for highly regulated data</span></span>

<span data-ttu-id="e52a7-104">*Este escenario se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="e52a7-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="e52a7-p101">Microsoft 365 Enterprise incluye una serie completa de servicios basados en la nube para que pueda crear, almacenar, proteger y administrar los datos altamente regulados almacenados en archivos de. Se incluyen datos que:</span><span class="sxs-lookup"><span data-stu-id="e52a7-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, secure, and manage your highly regulated data stored in files. This includes data that is:</span></span>

- <span data-ttu-id="e52a7-107">Datos sujetos a regulaciones regionales.</span><span class="sxs-lookup"><span data-stu-id="e52a7-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="e52a7-108">Los datos más importantes para su organización, como pueden ser secretos comerciales, información de recursos humanos o financiera y estrategias de la organización.</span><span class="sxs-lookup"><span data-stu-id="e52a7-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

>[!Note]
> <span data-ttu-id="e52a7-109">Un escenario similar usando equipos de Microsoft Teams está [aqui](secure-teams-highly-regulated-data-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="e52a7-109">A similar scenario using Microsoft Teams is [here](secure-teams-highly-regulated-data-scenario.md).</span></span>
>

<span data-ttu-id="e52a7-110">Un escenario basado en la nube de Microsoft 365 Enterprise que cumpla estas necesidades de negocio requiere que usted:</span><span class="sxs-lookup"><span data-stu-id="e52a7-110">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="e52a7-111">Almacenar archivos de (documentos, presentaciones de diapositivas, hojas de cálculo, etc.) en un sitio de grupo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e52a7-111">Store files (documents, slide decks, spreadsheets, etc.) in a SharePoint team site.</span></span>
- <span data-ttu-id="e52a7-112">Bloquee el sitio para evitar:</span><span class="sxs-lookup"><span data-stu-id="e52a7-112">Lock down the site to prevent:</span></span>
  - <span data-ttu-id="e52a7-113">Acceso a los usuarios que no sean miembros del grupo de Office 365 para el sitio.</span><span class="sxs-lookup"><span data-stu-id="e52a7-113">Access to users who are not members of the Office 365 group for the site.</span></span>
  - <span data-ttu-id="e52a7-114">Que miembros del sitio concedan acceso a terceros.</span><span class="sxs-lookup"><span data-stu-id="e52a7-114">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="e52a7-115">Que aquellos que no sean miembros del sitio soliciten acceso.</span><span class="sxs-lookup"><span data-stu-id="e52a7-115">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="e52a7-116">Configure una etiqueta de retención de Office 365 para los sitios de SharePoint de forma predeterminada para impedir que los usuarios envíen archivos fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="e52a7-116">Configure an Office 365 retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="e52a7-117">Cifre la mayoría de los archivos confidenciales del sitio con un método de cifrado que se desplaza con el archivo.</span><span class="sxs-lookup"><span data-stu-id="e52a7-117">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="e52a7-118">Agregue permisos a los archivos más confidenciales de modo que, incluso si se comparten fuera del sitio, aún se requieran las credenciales válidas de una cuenta de usuario para abrir el archivo.</span><span class="sxs-lookup"><span data-stu-id="e52a7-118">Add permissions to the most sensitive files so that if even if they get shared outside of the site, opening the file still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="e52a7-119">En la tabla siguiente se asignan los requisitos de este escenario a una característica de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e52a7-119">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="e52a7-120">**Requisito**</span><span class="sxs-lookup"><span data-stu-id="e52a7-120">**Requirement**</span></span> | <span data-ttu-id="e52a7-121">**Característica de Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="e52a7-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="e52a7-122">Almacenar archivos</span><span class="sxs-lookup"><span data-stu-id="e52a7-122">Store files</span></span> | <span data-ttu-id="e52a7-123">Sitios de grupo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="e52a7-123">SharePoint team sites</span></span> |
| <span data-ttu-id="e52a7-124">Bloquear el sitio</span><span class="sxs-lookup"><span data-stu-id="e52a7-124">Lock down the site</span></span> | <span data-ttu-id="e52a7-125">Permisos para grupos de Office 365 y para el sitio de grupo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="e52a7-125">Office 365 groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="e52a7-126">Etiquetar los archivos del sitio</span><span class="sxs-lookup"><span data-stu-id="e52a7-126">Label the files of the site</span></span> | <span data-ttu-id="e52a7-127">Etiquetas de retención de Office 365</span><span class="sxs-lookup"><span data-stu-id="e52a7-127">Office 365 retention labels</span></span> |
| <span data-ttu-id="e52a7-128">Bloquear a los usuarios cuando envían archivos fuera de la organización</span><span class="sxs-lookup"><span data-stu-id="e52a7-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="e52a7-129">Directivas de prevención de pérdida de datos (DLP) en Office 365</span><span class="sxs-lookup"><span data-stu-id="e52a7-129">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="e52a7-130">Cifrar todos los archivos del sitio</span><span class="sxs-lookup"><span data-stu-id="e52a7-130">Encrypt all of the files of the site</span></span> | <span data-ttu-id="e52a7-131">Etiquetas o sub-etiquetas de confidencialidad de Office 365</span><span class="sxs-lookup"><span data-stu-id="e52a7-131">Office 365 sensitivity labels or sublabels</span></span> |
| <span data-ttu-id="e52a7-132">Añadir permisos a los archivos del sitio</span><span class="sxs-lookup"><span data-stu-id="e52a7-132">Add permissions to the files of the site</span></span> | <span data-ttu-id="e52a7-133">Etiquetas o sub-etiquetas de confidencialidad de Office 365</span><span class="sxs-lookup"><span data-stu-id="e52a7-133">Office 365 sensitivity labels or sublabels</span></span> |
|||

<span data-ttu-id="e52a7-134">Aquí tiene un ejemplo de configuración para un sitio de SharePoint seguro.</span><span class="sxs-lookup"><span data-stu-id="e52a7-134">Here is an example configuration for a secure SharePoint site.</span></span>

![Sitios de SharePoint para un escenario de datos altamente regulados](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="e52a7-136">Este escenario requiere que ya haya implementado:</span><span class="sxs-lookup"><span data-stu-id="e52a7-136">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="e52a7-137">La fase de [identidad](identity-infrastructure.md) y los pasos 1 y 2 de la fase de [protección de la información](infoprotect-infrastructure.md) de la infraestructura de base.</span><span class="sxs-lookup"><span data-stu-id="e52a7-137">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="e52a7-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span><span class="sxs-lookup"><span data-stu-id="e52a7-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span></span>

<span data-ttu-id="e52a7-139">Las siguientes fases le guiarán a través del diseño, la configuración y el impulso de la adopción de los sitios altamente regulados de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e52a7-139">The following phases step you through designing, configuring, and driving adoption for SharePoint sites for highly regulated data.</span></span>

<a name="poster"></a> <span data-ttu-id="e52a7-140">Para obtener un resumen de una página de este escenario, vea el [póster Sitios de SharePoint para datos altamente regulados](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf).</span><span class="sxs-lookup"><span data-stu-id="e52a7-140">For a 1-page summary of this scenario, see the [SharePoint sites for highly regulated data poster](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf).</span></span>

<span data-ttu-id="e52a7-141">[![Póster Sitios de SharePoint para datos altamente regulados](../media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)</span><span class="sxs-lookup"><span data-stu-id="e52a7-141">[![SharePoint sites for highly regulated data poster](../media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)</span></span>

<span data-ttu-id="e52a7-142">También puede descargar este póster en formato [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf) o [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx) e imprimirlo en tamaño carta, legal o tabloide (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="e52a7-142">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx) formats and print it on letter, legal, or tabloid (11 x 17)-sized paper.</span></span>


## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="e52a7-143">Requisitos previos de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="e52a7-143">Identity and device access prerequisites</span></span>

<span data-ttu-id="e52a7-144">Para proteger el acceso a los sitios de SharePoint, asegúrese de que configuró las [directivas de acceso a dispositivos e identidades](identity-access-policies.md) y las [directivas de acceso recomendadas de SharePoint](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e52a7-144">To protect access to the SharePoint site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="e52a7-145">Fase 1: Diseño</span><span class="sxs-lookup"><span data-stu-id="e52a7-145">Phase 1: Design</span></span>

<span data-ttu-id="e52a7-146">Para crear un sitio de SharePoint para datos altamente regulados, en primer lugar debe identificar su propósito.</span><span class="sxs-lookup"><span data-stu-id="e52a7-146">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="e52a7-147">Por ejemplo, el departamento de investigación y desarrollo de una compañía de fabricación necesita un sitio de SharePoint para almacenar las especificaciones de diseño actuales para los productos existentes y un lugar para colaborar en nuevos productos.</span><span class="sxs-lookup"><span data-stu-id="e52a7-147">For example, the research and development department of a manufacturing organization needs a SharePoint site to store current design specifications for existing products and a place to collaborate on new products.</span></span> <span data-ttu-id="e52a7-148">Solo podrán acceder al sitio los miembros del Departamento de Investigación y Desarrollo y los ejecutivos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="e52a7-148">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="e52a7-149">Ese propósito impulsará la determinación de los elementos de configuración esenciales, como:</span><span class="sxs-lookup"><span data-stu-id="e52a7-149">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="e52a7-150">La etiqueta de retención de Office 365 para asignar a la parte de Documentos del sitio y las directivas DLP para la etiqueta</span><span class="sxs-lookup"><span data-stu-id="e52a7-150">The Office 365 retention label to assign to the Documents portion of the site and DLP policies for the label</span></span>
- <span data-ttu-id="e52a7-151">La configuración de una sub-etiqueta de confidencialidad de Office 365 que los usuarios aplican a los archivos altamente confidenciales almacenados en el sitio</span><span class="sxs-lookup"><span data-stu-id="e52a7-151">The settings of an Office 365 sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="e52a7-152">Una vez determinados, use estos ajustes para configurar el sitio en la fase 2.</span><span class="sxs-lookup"><span data-stu-id="e52a7-152">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="e52a7-153">Paso 1 Etiquetas de retención de Office 365 y directivas DLP</span><span class="sxs-lookup"><span data-stu-id="e52a7-153">Step 1 Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="e52a7-154">Cuando se aplican a la parte de Documentos de un sitio de grupo de SharePoint, las etiquetas de retención de Office 365 proporcionan un método predeterminado de clasificación para todos los archivos almacenados en el sitio.</span><span class="sxs-lookup"><span data-stu-id="e52a7-154">When applied to the Documents portion of a SharePoint team site, Office 365 retention labels provide a default method of classifying all files stored on the site.</span></span>
 
<span data-ttu-id="e52a7-155">En los sitios de SharePoint para datos altamente regulados, debe determinar qué etiqueta de retención de Office 365 usará.</span><span class="sxs-lookup"><span data-stu-id="e52a7-155">For SharePoint sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="e52a7-156">Para conocer las consideraciones de diseño de las etiquetas de Office 365, consulte [Etiquetas y clasificación de Office 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="e52a7-156">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="e52a7-p103">Use directivas DLP para proteger la información confidencial y evitar su divulgación accidental o intencionada. Para obtener más información, consulte esta [introducción](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span><span class="sxs-lookup"><span data-stu-id="e52a7-p103">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="e52a7-159">En los sitios de SharePoint, debe configurar una directiva DLP para la etiqueta de retención de Office 365 asignada al sitio para bloquear a los usuarios cuando intenten compartir archivos con usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="e52a7-159">For SharePoint sites, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share files with external users.</span></span> 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a><span data-ttu-id="e52a7-160">Paso 2: Su sub-etiqueta de confidencialidad de Office 365</span><span class="sxs-lookup"><span data-stu-id="e52a7-160">Step 2: Your Office 365 sensitivity sublabel</span></span>

<span data-ttu-id="e52a7-161">Para proporcionar cifrado y un conjunto de permisos a los archivos más confidenciales, los usuarios deben aplicar una etiqueta o subetiqueta de confidencialidad de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e52a7-161">To provide encryption and a set of permissions to your most sensitive files, users must apply an Office 365 sensitivity label or sublabel.</span></span> <span data-ttu-id="e52a7-162">Crear una sub-etiqueta bajo una etiqueta existente.</span><span class="sxs-lookup"><span data-stu-id="e52a7-162">A sublabel exists under an existing label.</span></span> 

<span data-ttu-id="e52a7-163">Use una etiqueta de confidencialidad cuando necesite, un número reducido de etiquetas tanto para los equipos de uso global como para los individuales privados.</span><span class="sxs-lookup"><span data-stu-id="e52a7-163">Use a sensitivity label when you need is a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="e52a7-164">Utilice una subetiqueta de confidencialidad cuando tenga un gran número de etiquetas o cuando desee organizar las etiquetas para sitios seguros bajo su etiqueta altamente regulada.</span><span class="sxs-lookup"><span data-stu-id="e52a7-164">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for secure sites the under your highly regulated label.</span></span> 

<span data-ttu-id="e52a7-165">La configuración de la etiqueta o subetiqueta aplicada se desplaza con el archivo.</span><span class="sxs-lookup"><span data-stu-id="e52a7-165">The settings of the applied label or sublabel travel with the file.</span></span> <span data-ttu-id="e52a7-166">Incluso si se filtra fuera del sitio, solo las cuentas de usuario autenticadas que tengan permisos podrán abrir el archivo.</span><span class="sxs-lookup"><span data-stu-id="e52a7-166">Even if it is leaked outside the site, only authenticated user accounts that have permissions can open it.</span></span>

### <a name="design-results"></a><span data-ttu-id="e52a7-167">Resultados de diseño</span><span class="sxs-lookup"><span data-stu-id="e52a7-167">Design results</span></span>

<span data-ttu-id="e52a7-168">Ha decidido lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e52a7-168">You have determined the following:</span></span>

- <span data-ttu-id="e52a7-169">La etiqueta de retención adecuada de Office 365 y la directiva DLP que tiene asociada</span><span class="sxs-lookup"><span data-stu-id="e52a7-169">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="e52a7-170">La configuración de la sub-etiqueta de confidencialidad de Office 365 que incluye el cifrado y los permisos</span><span class="sxs-lookup"><span data-stu-id="e52a7-170">The settings of the Office 365 sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="e52a7-171">Fase 2: Configurar</span><span class="sxs-lookup"><span data-stu-id="e52a7-171">Phase 2: Configure</span></span>

<span data-ttu-id="e52a7-172">En esta fase, debe tomar la configuración determinada en la Fase 1 e implementarla para crear un sitio de SharePoint para datos altamente regulados.</span><span class="sxs-lookup"><span data-stu-id="e52a7-172">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a><span data-ttu-id="e52a7-173">Paso 1: Crear un sitio de grupo de SharePoint privado con propietarios y miembros del grupo de Office 365 correspondiente</span><span class="sxs-lookup"><span data-stu-id="e52a7-173">Step 1: Create a private SharePoint team site with owners and members of the corresponding Office 365 group</span></span>

<span data-ttu-id="e52a7-174">Siga [estas instrucciones]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) para crear un sitio de grupo de SharePoint privado.</span><span class="sxs-lookup"><span data-stu-id="e52a7-174">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="e52a7-175">Paso 2: Configurar ajustes de permisos adicionales para el sitio de grupo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="e52a7-175">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="e52a7-176">Desde el sitio de SharePoint, configure estos ajustes de permisos.</span><span class="sxs-lookup"><span data-stu-id="e52a7-176">From the SharePoint site, configure these permission settings.</span></span>

1. <span data-ttu-id="e52a7-177">En la barra de herramientas, haga clic en el icono de configuración y, luego, en **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="e52a7-177">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="e52a7-178">En el panel **Permisos del sitio**, en **Configuración de uso compartido**, haga clic en **Cambiar configuración de uso compartido**.</span><span class="sxs-lookup"><span data-stu-id="e52a7-178">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="e52a7-179">En **Permisos de uso compartido**, seleccione **Solo los propietarios del sitio pueden compartir archivos, carpetas y el sitio**.</span><span class="sxs-lookup"><span data-stu-id="e52a7-179">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="e52a7-180">Desactive **Permitir solicitudes de acceso** y, después, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e52a7-180">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="e52a7-181">Con estas ajustes de configuración, se deshabilita la posibilidad de que los miembros del grupo de sitio compartan el sitio con otros miembros o que los usuarios que no son miembros soliciten el acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="e52a7-181">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="e52a7-182">Paso 3: Configurar el sitio para una etiqueta de retención de Office 365</span><span class="sxs-lookup"><span data-stu-id="e52a7-182">Step 3: Configure the site for an Office 365 retention label</span></span>

<span data-ttu-id="e52a7-183">Siga las instrucciones de [Proteger archivos de SharePoint con DLP y etiquetas de Office 365](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) para:</span><span class="sxs-lookup"><span data-stu-id="e52a7-183">Use the instructions in [Protect SharePoint files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="e52a7-184">Crear y publicar una etiqueta de retención para datos altamente regulados (si es necesario).</span><span class="sxs-lookup"><span data-stu-id="e52a7-184">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="e52a7-185">Configurar el sitio para la etiqueta de retención que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="e52a7-185">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="e52a7-186">Crear una directiva DLP para datos altamente regulados que usen la etiqueta de retención creada en el paso 2 y bloquee el envío de archivos fuera de la organización por parte de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e52a7-186">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="e52a7-187">Paso 4: Crear una sub-etiqueta de confidencialidad de Office 365 para el sitio</span><span class="sxs-lookup"><span data-stu-id="e52a7-187">Step 4: Create an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="e52a7-188">A diferencia de una etiqueta de confidencialidad para datos altamente regulados que cualquier persona puede aplicar a cualquier archivo, un sitio seguro necesita su propia sub-etiqueta para que los archivos con la sub-etiqueta asignada:</span><span class="sxs-lookup"><span data-stu-id="e52a7-188">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="e52a7-189">Se cifren y el cifrado se desplace con el archivo.</span><span class="sxs-lookup"><span data-stu-id="e52a7-189">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="e52a7-190">Contengan permisos personalizados para que solo los miembros del grupo de sitio puedan abrirlo.</span><span class="sxs-lookup"><span data-stu-id="e52a7-190">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="e52a7-191">Para lograr este nivel de seguridad adicional para los archivos almacenados en el sitio, debe configurar una nueva etiqueta de confidencialidad o una subetiqueta de la etiqueta general para archivos altamente regulados.</span><span class="sxs-lookup"><span data-stu-id="e52a7-191">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label or a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="e52a7-192">Solo los miembros del grupo del sitio la verán en la lista de sub-etiquetas para la etiqueta altamente regulada.</span><span class="sxs-lookup"><span data-stu-id="e52a7-192">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="e52a7-193">Siga las instrucciones de [aquí](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para configurar una etiqueta o sub-etiqueta de la etiqueta que está usando para archivos altamente regulados con los siguientes ajustes:</span><span class="sxs-lookup"><span data-stu-id="e52a7-193">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a label or a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="e52a7-194">El nombre de la etiqueta o sub-etiqueta contiene el nombre del sitio para facilitar la asociación al asignar la etiqueta o subetiqueta a un archivo.</span><span class="sxs-lookup"><span data-stu-id="e52a7-194">The name of the label or sublabel contains the name of the site for easy association when assigning the label or sublabel to a file.</span></span>
- <span data-ttu-id="e52a7-195">El cifrado está habilitado.</span><span class="sxs-lookup"><span data-stu-id="e52a7-195">Encryption is enabled.</span></span>
- <span data-ttu-id="e52a7-196">El grupo del sitio tiene permisos de Coautor.</span><span class="sxs-lookup"><span data-stu-id="e52a7-196">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="e52a7-197">Resultados de la configuración</span><span class="sxs-lookup"><span data-stu-id="e52a7-197">Configuration results</span></span>

<span data-ttu-id="e52a7-198">Ha configurado lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e52a7-198">You have configured the following:</span></span>

- <span data-ttu-id="e52a7-199">Configuraciones de permisos más restrictivas en el sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="e52a7-199">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="e52a7-200">Una etiqueta de retención de Office 365 asignada a la parte de Documentos del sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="e52a7-200">An Office 365 retention label assigned to the Documents portion of the SharePoint site</span></span>
- <span data-ttu-id="e52a7-201">Una directiva DLP para la etiqueta de retención de Office 365</span><span class="sxs-lookup"><span data-stu-id="e52a7-201">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="e52a7-202">Una etiqueta o sub-etiqueta de confidencialidad de Office 365 que los usuarios pueden aplicar a los archivos más confidenciales almacenados en el sitio, el cual cifra el archivo y solo permite el acceso de coautoría a los miembros del grupo de sitio del equipo</span><span class="sxs-lookup"><span data-stu-id="e52a7-202">An Office 365 sensitivity label or sublabel that users can apply to the most sensitive files stored in the site, which encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="e52a7-203">Aquí está la configuración resultante que utiliza una sub-etiqueta de la etiqueta altamente regulada.</span><span class="sxs-lookup"><span data-stu-id="e52a7-203">Here is the resulting configuration that uses a sublabel of the Highly regulated label.</span></span>

![Los sitios de SharePoint para un escenario de datos altamente regulados](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="e52a7-205">Este es un ejemplo de un usuario que ha aplicado la sub-etiqueta a un archivo almacenado en el sitio.</span><span class="sxs-lookup"><span data-stu-id="e52a7-205">Here is an example of a user that has applied the sublabel to a file stored in the site.</span></span>

![Sitios de SharePoint para un escenario de datos altamente regulados](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="e52a7-207">Fase 3: Adopción por parte de los usuarios</span><span class="sxs-lookup"><span data-stu-id="e52a7-207">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="e52a7-208">Un sitio de SharePoint para datos altamente regulados solo puede proteger los datos si se usan de forma consistente para almacenar y acceder a archivos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="e52a7-208">A SharePoint site for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive files.</span></span> <span data-ttu-id="e52a7-209">Esta es la fase más difícil, ya que depende de que los usuarios cambien sus hábitos y preferencias.</span><span class="sxs-lookup"><span data-stu-id="e52a7-209">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="e52a7-210">Por ejemplo, los empleados acostumbrados a guardar archivos confidenciales en unidades USB o en soluciones de almacenamiento personal basadas en la nube, ahora tendrán que almacenarlos de forma exclusiva en el sitio de SharePoint para datos altamente regulados.</span><span class="sxs-lookup"><span data-stu-id="e52a7-210">For example, employees that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="e52a7-211">Paso 1: formar a los usuarios</span><span class="sxs-lookup"><span data-stu-id="e52a7-211">Step 1: Train your users</span></span>

<span data-ttu-id="e52a7-212">Tras completar su configuración, tome un conjunto de usuarios que sean miembros del sitio:</span><span class="sxs-lookup"><span data-stu-id="e52a7-212">After completing your configuration, train the set of users who are members of the site:</span></span>

- <span data-ttu-id="e52a7-213">La importancia de usar el nuevo sitio para proteger archivos valiosos y las consecuencias de la filtración de datos altamente regulados, como las repercusiones legales, las multas, el ramsonware o la pérdida de ventaja frente a la competencia.</span><span class="sxs-lookup"><span data-stu-id="e52a7-213">On the importance of using the new site to protect valuable files and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="e52a7-214">Cómo obtener acceso al sitio y a sus recursos.</span><span class="sxs-lookup"><span data-stu-id="e52a7-214">How to access the site and its files.</span></span>
- <span data-ttu-id="e52a7-215">Cómo crear archivos nuevos en el sitio o cargar archivos nuevos almacenados de forma local.</span><span class="sxs-lookup"><span data-stu-id="e52a7-215">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="e52a7-216">Cómo la directiva DLP les impide compartir archivos de forma externa.</span><span class="sxs-lookup"><span data-stu-id="e52a7-216">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="e52a7-217">Cómo etiquetar los archivos más confidenciales con la etiqueta o sub-etiqueta del sitio.</span><span class="sxs-lookup"><span data-stu-id="e52a7-217">How to label the most sensitive files with the label or sublabel for the site.</span></span>
- <span data-ttu-id="e52a7-218">Cómo la etiqueta o sub-etiqueta protege un archivo incluso cuando se filtra el sitio.</span><span class="sxs-lookup"><span data-stu-id="e52a7-218">How the label or sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="e52a7-219">Esta formación debe incluir ejercicios prácticos para que los usuarios puedan experimentar con estas operaciones y sus resultados.</span><span class="sxs-lookup"><span data-stu-id="e52a7-219">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="e52a7-220">Paso 2: Realizar revisiones periódicas de uso y archivos</span><span class="sxs-lookup"><span data-stu-id="e52a7-220">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="e52a7-221">En las semanas posteriores a la formación, el administrador del servicio de SharePoint para el sitio de SharePoint puede:</span><span class="sxs-lookup"><span data-stu-id="e52a7-221">In the weeks after training, the SharePoint administrator for the SharePoint site can:</span></span>

- <span data-ttu-id="e52a7-222">Analizar el uso del sitio y compararlo con las expectativas de uso.</span><span class="sxs-lookup"><span data-stu-id="e52a7-222">Analyze usage for the site and compare it with usage expectations.</span></span>
- <span data-ttu-id="e52a7-223">Comprobar que los archivos más confidenciales se han etiquetado de forma correcta con la etiqueta o sub-etiqueta de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="e52a7-223">Verify that highly sensitive files have been properly labeled with the sensitivity label or sublabel.</span></span>

  <span data-ttu-id="e52a7-224">Puede ver qué archivos tienen una etiqueta asignada viendo una carpeta en SharePoint y añadiendo la columna **Confidencialidad** a través de la opción **Mostrar/ocultar columnas** que está en **Añadir columna**.</span><span class="sxs-lookup"><span data-stu-id="e52a7-224">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>


<span data-ttu-id="e52a7-225">Volver a dar formación a los usuarios que lo necesiten.</span><span class="sxs-lookup"><span data-stu-id="e52a7-225">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="e52a7-226">Resultados de la adopción de usuarios</span><span class="sxs-lookup"><span data-stu-id="e52a7-226">User adoption results</span></span>

<span data-ttu-id="e52a7-227">Los archivos altamente regulados se almacenan exclusivamente en sitios de SharePoint para datos altamente regulados y los archivos más confidenciales tienen la etiqueta o sub-etiqueta de confidencialidad para el sitio aplicado.</span><span class="sxs-lookup"><span data-stu-id="e52a7-227">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity label or sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-used-a-sharepoint-site-for-highly-regulated-data"></a><span data-ttu-id="e52a7-228">Cómo la empresa Contoso usó un sitio de SharePoint para datos altamente regulados</span><span class="sxs-lookup"><span data-stu-id="e52a7-228">How the Contoso Corporation used a SharePoint site for highly regulated data</span></span>

<span data-ttu-id="e52a7-229">Contoso Corporation es un conglomerado industrial a nivel mundial que es ficticio y representativo a la vez.</span><span class="sxs-lookup"><span data-stu-id="e52a7-229">The Contoso Corporation is a fictional but representative global manufacturing conglomerate.</span></span> <span data-ttu-id="e52a7-230">Vea cómo Contoso diseñó, configuró e impulsó la adopción de un [sitio de SharePoint Online seguro](contoso-sharepoint-online-site-for-highly-confidential-assets.md) para sus equipos de investigación en París, Moscú, Nueva York, Beijing y Bengaluru (Bangalore).</span><span class="sxs-lookup"><span data-stu-id="e52a7-230">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="e52a7-231">Vea también</span><span class="sxs-lookup"><span data-stu-id="e52a7-231">See also</span></span>

[<span data-ttu-id="e52a7-232">Teams para datos altamente regulados</span><span class="sxs-lookup"><span data-stu-id="e52a7-232">Teams for highly regulated data</span></span>](secure-teams-highly-regulated-data-scenario.md)

[<span data-ttu-id="e52a7-233">Cargas de trabajo y escenarios de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e52a7-233">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="e52a7-234">[Biblioteca de productividad de Microsoft 365](https://aka.ms/productivitylibrary)(https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="e52a7-234">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="e52a7-235">Guía de implementación</span><span class="sxs-lookup"><span data-stu-id="e52a7-235">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
