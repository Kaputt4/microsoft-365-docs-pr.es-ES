---
title: Sitios de SharePoint para datos altamente regulados
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/04/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Cree un sitio de grupo de SharePoint seguro para almacenar los archivos más importantes y confidenciales.
ms.openlocfilehash: dc604870826075cee645dd466b82f908e1571339
ms.sourcegitcommit: e1ffb98ac8159d1dc814930fe388d3e37cbdc7e2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2019
ms.locfileid: "37403197"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="2c47f-103">Sitios de SharePoint para datos altamente regulados</span><span class="sxs-lookup"><span data-stu-id="2c47f-103">Microsoft Teams and SharePoint Online sites for highly regulated data</span></span>

<span data-ttu-id="2c47f-104">*Este escenario se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="2c47f-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="2c47f-p101">Microsoft 365 Enterprise incluye un conjunto completo de servicios basados en la nube para crear, guardar y proteger sus datos altamente regulados almacenados en archivos. Esto incluye:</span><span class="sxs-lookup"><span data-stu-id="2c47f-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data. This includes data that is:</span></span>

- <span data-ttu-id="2c47f-107">Datos sujetos a regulaciones regionales.</span><span class="sxs-lookup"><span data-stu-id="2c47f-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="2c47f-108">Los datos más importantes para su organización, como pueden ser secretos comerciales, información de recursos humanos o financiera y estrategias de la organización.</span><span class="sxs-lookup"><span data-stu-id="2c47f-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

<span data-ttu-id="2c47f-109">Un escenario basado en la nube de Microsoft 365 Enterprise que cumpla estas necesidades de negocio requiere que usted:</span><span class="sxs-lookup"><span data-stu-id="2c47f-109">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="2c47f-110">Almacenar archivos de (documentos, presentaciones de diapositivas, hojas de cálculo, etc.) en un sitio de grupo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2c47f-110">Store digital assets (documents, slide decks, spreadsheets, etc.) in a SharePoint Online team site or in the Files tab of a Microsoft Teams team.</span></span>
- <span data-ttu-id="2c47f-111">Bloquee el sitio para evitar:</span><span class="sxs-lookup"><span data-stu-id="2c47f-111">Lock down the site or team to prevent:</span></span>
  - <span data-ttu-id="2c47f-112">Acceso a los usuarios que no sean miembros del grupo de Office 365 para el sitio.</span><span class="sxs-lookup"><span data-stu-id="2c47f-112">Access to users who are not members of the Office 365 group for the site.</span></span>
  - <span data-ttu-id="2c47f-113">Que miembros del sitio concedan acceso a terceros.</span><span class="sxs-lookup"><span data-stu-id="2c47f-113">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="2c47f-114">Que aquellos que no sean miembros del sitio soliciten acceso.</span><span class="sxs-lookup"><span data-stu-id="2c47f-114">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="2c47f-115">Configure una etiqueta de retención de Office 365 para los sitios de SharePoint de forma predeterminada para impedir que los usuarios envíen archivos fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="2c47f-115">Configure an Office 365 retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="2c47f-116">Cifre la mayoría de los archivos confidenciales del sitio con un método de cifrado que se desplaza con el archivo.</span><span class="sxs-lookup"><span data-stu-id="2c47f-116">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="2c47f-117">Agregue permisos a los archivos más confidenciales de modo que, incluso si se comparten fuera del sitio, aún se requieran las credenciales válidas de una cuenta de usuario para abrir el archivo.</span><span class="sxs-lookup"><span data-stu-id="2c47f-117">Add permissions to the most sensitive digital assets so that if even if they get shared outside of the site, opening the asset still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="2c47f-118">En la tabla siguiente se asignan los requisitos de este escenario a una característica de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2c47f-118">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="2c47f-119">**Requisito**</span><span class="sxs-lookup"><span data-stu-id="2c47f-119">**Requirement**</span></span> | <span data-ttu-id="2c47f-120">**Característica de Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="2c47f-120">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="2c47f-121">Almacenar archivos</span><span class="sxs-lookup"><span data-stu-id="2c47f-121">4. Store files online</span></span> | <span data-ttu-id="2c47f-122">Sitios de grupo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="2c47f-122">Sensitive SharePoint Online team sites</span></span> |
| <span data-ttu-id="2c47f-123">Bloquear el sitio</span><span class="sxs-lookup"><span data-stu-id="2c47f-123">Lock down the site</span></span> | <span data-ttu-id="2c47f-124">Permisos de sitios de grupo de SharePoint y grupos de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="2c47f-124">Azure Active Directory (Azure AD) groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="2c47f-125">Etiquetar los archivos del sitio</span><span class="sxs-lookup"><span data-stu-id="2c47f-125">Label the digital assets of the site</span></span> | <span data-ttu-id="2c47f-126">Etiquetas de retención de Office 365</span><span class="sxs-lookup"><span data-stu-id="2c47f-126">Office 365 retention labels</span></span> |
| <span data-ttu-id="2c47f-127">Bloquear a los usuarios cuando envían archivos fuera de la organización</span><span class="sxs-lookup"><span data-stu-id="2c47f-127">Block users when sending files outside the organization</span></span> | <span data-ttu-id="2c47f-128">Directivas de prevención de pérdida de datos (DLP) en Office 365</span><span class="sxs-lookup"><span data-stu-id="2c47f-128">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="2c47f-129">Cifrar todos los archivos del sitio</span><span class="sxs-lookup"><span data-stu-id="2c47f-129">Encrypt all of the digital assets of the site</span></span> | <span data-ttu-id="2c47f-130">Sub-etiquetas de confidencialidad de Office 365</span><span class="sxs-lookup"><span data-stu-id="2c47f-130">Office 365 sensitivity sublabels</span></span> |
| <span data-ttu-id="2c47f-131">Añadir permisos a los archivos del sitio</span><span class="sxs-lookup"><span data-stu-id="2c47f-131">Add permissions to the digital assets of the site</span></span> | <span data-ttu-id="2c47f-132">Sub-etiquetas de confidencialidad de Office 365</span><span class="sxs-lookup"><span data-stu-id="2c47f-132">Office 365 sensitivity sublabels</span></span> |
|||

<span data-ttu-id="2c47f-133">Esta es la configuración para un sitio seguro de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2c47f-133">Here is the configuration for a SharePoint Online site.</span></span>

![Sitios de SharePoint para un escenario de datos altamente regulados](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="2c47f-135">Este escenario requiere que ya haya implementado:</span><span class="sxs-lookup"><span data-stu-id="2c47f-135">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="2c47f-136">La fase de [identidad](identity-infrastructure.md) y los pasos 1 y 2 de la fase de [protección de la información](infoprotect-infrastructure.md) de la infraestructura de base.</span><span class="sxs-lookup"><span data-stu-id="2c47f-136">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="2c47f-137">[SharePoint](sharepoint-online-onedrive-workload.md).</span><span class="sxs-lookup"><span data-stu-id="2c47f-137">SharePoint</span></span>

<span data-ttu-id="2c47f-138">Las siguientes fases le guiarán a través del diseño, la configuración y el impulso de la adopción de los sitios altamente regulados de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2c47f-138">The following phases step you through designing, configuring, and driving adoption for SharePoint Online sites and teams for highly regulated data.</span></span>

<span data-ttu-id="2c47f-139">Para ver cómo Contoso Corporation, una organización multinacional ficticia pero representativa, diseñó un sitio de SharePoint para los equipos de investigación, vea esta [configuración de ejemplo](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span><span class="sxs-lookup"><span data-stu-id="2c47f-139">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint Online site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>

## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="2c47f-140">Requisitos previos de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="2c47f-140">Identity and device access prerequisites</span></span>

<span data-ttu-id="2c47f-141">Para proteger el acceso a los sitios de SharePoint, asegúrese de que configuró las [directivas de acceso a dispositivos e identidades](identity-access-policies.md) y las [directivas de acceso recomendadas de SharePoint](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2c47f-141">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="2c47f-142">Fase 1: Diseño</span><span class="sxs-lookup"><span data-stu-id="2c47f-142">Phase 1: Design</span></span>

<span data-ttu-id="2c47f-143">Para crear un sitio de SharePoint para datos altamente regulados, en primer lugar debe identificar su propósito.</span><span class="sxs-lookup"><span data-stu-id="2c47f-143">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="2c47f-144">Por ejemplo, el departamento de investigación y desarrollo de una compañía de fabricación necesita un sitio de SharePoint para almacenar las especificaciones de diseño actuales para los productos existentes y un lugar para colaborar en nuevos productos.</span><span class="sxs-lookup"><span data-stu-id="2c47f-144">To create a SharePoint Online site or team for highly regulated data, you must first identify its purpose. For example, the research and development department of a manufacturing organization needs a SharePoint Online site to store current design specifications for existing products and a place to collaborate on new products. Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span> <span data-ttu-id="2c47f-145">Solo podrán acceder al sitio los miembros del Departamento de Investigación y Desarrollo y los ejecutivos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="2c47f-145">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="2c47f-146">Ese propósito impulsará la determinación de los elementos de configuración esenciales, como:</span><span class="sxs-lookup"><span data-stu-id="2c47f-146">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="2c47f-147">La etiqueta de retención de Office 365 para asignar a la parte de Documentos del sitio y las directivas DLP para la etiqueta</span><span class="sxs-lookup"><span data-stu-id="2c47f-147">The Office 365 retention label to assign to the site and the set of DLP policies for the label</span></span>
- <span data-ttu-id="2c47f-148">La configuración de una sub-etiqueta de confidencialidad de Office 365 que los usuarios aplican a los archivos altamente confidenciales almacenados en el sitio</span><span class="sxs-lookup"><span data-stu-id="2c47f-148">The settings of an Office 365 sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="2c47f-149">Una vez determinados, use estos ajustes para configurar el sitio en la fase 2.</span><span class="sxs-lookup"><span data-stu-id="2c47f-149">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="2c47f-150">Paso 1 Etiquetas de retención de Office 365 y directivas DLP</span><span class="sxs-lookup"><span data-stu-id="2c47f-150">Step 2: Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="2c47f-151">Cuando se aplican a la parte de Documentos de un sitio de grupo de SharePoint, las etiquetas de retención de Office 365 proporcionan un método predeterminado de clasificación para todos los archivos almacenados en el sitio.</span><span class="sxs-lookup"><span data-stu-id="2c47f-151">When applied to a SharePoint Online team site, Office 365 retention labels provide a default method of classifying all digital assets stored on the site.</span></span>
 
<span data-ttu-id="2c47f-152">En los sitios de SharePoint para datos altamente regulados, debe determinar qué etiqueta de retención de Office 365 usará.</span><span class="sxs-lookup"><span data-stu-id="2c47f-152">For SharePoint Online sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="2c47f-153">Para conocer las consideraciones de diseño de las etiquetas de Office 365, consulte [Etiquetas y clasificación de Office 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="2c47f-153">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="2c47f-p103">Use directivas DLP para proteger la información confidencial y evitar su divulgación accidental o intencionada. Para obtener más información, consulte esta [introducción](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span><span class="sxs-lookup"><span data-stu-id="2c47f-p103">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="2c47f-156">En los sitios de SharePoint, debe configurar una directiva DLP para la etiqueta de retención de Office 365 asignada al sitio para bloquear a los usuarios cuando intenten compartir archivos con usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="2c47f-156">For SharePoint Online sites for highly regulated data, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share digital assets with external users.</span></span> 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a><span data-ttu-id="2c47f-157">Paso 2: Su sub-etiqueta de confidencialidad de Office 365</span><span class="sxs-lookup"><span data-stu-id="2c47f-157">Step 2: Your Office 365 sensitivity sublabel</span></span>

<span data-ttu-id="2c47f-158">Para proporcionar el cifrado y un conjunto de permisos para los archivos más confidenciales, los usuarios deben aplicar una sub-etiqueta de confidencialidad de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2c47f-158">To provide encryption and a set of permissions to your most sensitive files, users must apply an Office 365 sensitivity sublabel.</span></span>

<span data-ttu-id="2c47f-159">Crear una sub-etiqueta bajo una etiqueta existente.</span><span class="sxs-lookup"><span data-stu-id="2c47f-159">A sublabel exists under an existing label.</span></span> <span data-ttu-id="2c47f-160">Por ejemplo, puede crear la sub-etiqueta Investigación y Desarrollo en la etiqueta Altamente Regulado.</span><span class="sxs-lookup"><span data-stu-id="2c47f-160">For example, you can create a Research & Development sublabel under the Highly Regulated label.</span></span> <span data-ttu-id="2c47f-161">Para los sitios de SharePoint para datos altamente regulados, configure los permisos para que solo los miembros del sitio puedan abrir y cambiar el archivo al que está asociada la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="2c47f-161">For SharePoint sites for highly regulated data, you configure the permissions so that only site members can open and change the file to which the sublabel is attached.</span></span>

<span data-ttu-id="2c47f-162">La configuración de la sub-etiqueta aplicada se desplaza con el archivo.</span><span class="sxs-lookup"><span data-stu-id="2c47f-162">The settings of the applied sublabel travel with the file.</span></span> <span data-ttu-id="2c47f-163">Incluso si se filtra fuera del sitio, solo las cuentas de usuario autenticadas que tengan permisos podrán abrir el archivo.</span><span class="sxs-lookup"><span data-stu-id="2c47f-163">The settings of the applied sub-label travel with the asset. Even if it is downloaded and shared outside the site, only authenticated user accounts that have permissions can open it.</span></span>


### <a name="design-results"></a><span data-ttu-id="2c47f-164">Resultados de diseño</span><span class="sxs-lookup"><span data-stu-id="2c47f-164">Design results</span></span>

<span data-ttu-id="2c47f-165">Ha decidido lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c47f-165">You have determined the following:</span></span>

- <span data-ttu-id="2c47f-166">La etiqueta de retención adecuada de Office 365 y la directiva DLP que tiene asociada</span><span class="sxs-lookup"><span data-stu-id="2c47f-166">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="2c47f-167">La configuración de la sub-etiqueta de confidencialidad de Office 365 que incluye el cifrado y los permisos</span><span class="sxs-lookup"><span data-stu-id="2c47f-167">The settings of the Office 365 sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="2c47f-168">Fase 2: Configurar</span><span class="sxs-lookup"><span data-stu-id="2c47f-168">Phase 2: Configure</span></span>

<span data-ttu-id="2c47f-169">En esta fase, debe tomar la configuración determinada en la Fase 1 e implementarla para crear un sitio de SharePoint para datos altamente regulados.</span><span class="sxs-lookup"><span data-stu-id="2c47f-169">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint Online site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a><span data-ttu-id="2c47f-170">Paso 1: Crear un sitio de grupo de SharePoint privado con propietarios y miembros del grupo de Office 365 correspondiente</span><span class="sxs-lookup"><span data-stu-id="2c47f-170">Step 1: Create a private SharePoint team site with owners and members of the corresponding Office 365 group</span></span>

<span data-ttu-id="2c47f-171">Siga [estas instrucciones]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) para crear un sitio de grupo de SharePoint privado.</span><span class="sxs-lookup"><span data-stu-id="2c47f-171">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="2c47f-172">Paso 2: Configurar ajustes de permisos adicionales para el sitio de grupo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="2c47f-172">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="2c47f-173">Desde el sitio de SharePoint, configure estos ajustes de permisos.</span><span class="sxs-lookup"><span data-stu-id="2c47f-173">From the SharePoint site, configure these permission settings.</span></span>

1.  <span data-ttu-id="2c47f-174">En la barra de herramientas, haga clic en el icono de configuración y, luego, en **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="2c47f-174">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="2c47f-175">En el panel **Permisos del sitio**, haga clic en **Advanced permissions settings** (Configuración de permisos avanzada).</span><span class="sxs-lookup"><span data-stu-id="2c47f-175">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
3.  <span data-ttu-id="2c47f-176">En la nueva pestaña **Permisos** del explorador, haga clic en **Configuración de solicitud de acceso**.</span><span class="sxs-lookup"><span data-stu-id="2c47f-176">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
4.  <span data-ttu-id="2c47f-177">En el cuadro de diálogo **Configuración de solicitud de acceso**, desactive **Permitir que los miembros compartan el sitio y archivos y carpetas individuales** y **Permitir solicitudes de acceso** (de modo que las tres casillas estén desactivadas) y después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2c47f-177">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

<span data-ttu-id="2c47f-178">Con estas ajustes de configuración, se deshabilita la posibilidad de que los miembros del grupo de sitio compartan el sitio con otros miembros o que los usuarios que no son miembros soliciten el acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="2c47f-178">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="2c47f-179">Paso 3: Configurar el sitio para una etiqueta de retención de Office 365</span><span class="sxs-lookup"><span data-stu-id="2c47f-179">Step 2: Configure the site for an Office 365 retention label</span></span>

<span data-ttu-id="2c47f-180">Siga las instrucciones de [Proteger archivos de SharePoint con DLP y etiquetas de Office 365](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) para:</span><span class="sxs-lookup"><span data-stu-id="2c47f-180">Use the instructions in [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="2c47f-181">Crear y publicar una etiqueta de retención para datos altamente regulados (si es necesario).</span><span class="sxs-lookup"><span data-stu-id="2c47f-181">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="2c47f-182">Configurar el sitio para la etiqueta de retención que creó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="2c47f-182">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="2c47f-183">Crear una directiva DLP para datos altamente regulados que usen la etiqueta de retención creada en el paso 2 y bloquee el envío de archivos fuera de la organización por parte de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2c47f-183">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="2c47f-184">Paso 4: Crear una sub-etiqueta de confidencialidad de Office 365 para el sitio</span><span class="sxs-lookup"><span data-stu-id="2c47f-184">Step 4: Create an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="2c47f-185">A diferencia de una etiqueta de confidencialidad para datos altamente regulados que cualquier persona puede aplicar a cualquier archivo, un sitio seguro necesita su propia sub-etiqueta para que los archivos con la sub-etiqueta asignada:</span><span class="sxs-lookup"><span data-stu-id="2c47f-185">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="2c47f-186">Se cifren y el cifrado se desplace con el archivo.</span><span class="sxs-lookup"><span data-stu-id="2c47f-186">Are encrypted and the encryption travels with the file.</span></span>
-   <span data-ttu-id="2c47f-187">Contengan permisos personalizados para que solo los miembros del grupo de sitio puedan abrirlo.</span><span class="sxs-lookup"><span data-stu-id="2c47f-187">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="2c47f-188">Para lograr este nivel adicional de seguridad para los archivos almacenados en el sitio, debe configurar una nueva etiqueta de confidencialidad que sea una sub-etiqueta de la etiqueta general para archivos altamente regulados.</span><span class="sxs-lookup"><span data-stu-id="2c47f-188">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="2c47f-189">Solo los miembros del grupo del sitio la verán en la lista de sub-etiquetas para la etiqueta altamente regulada.</span><span class="sxs-lookup"><span data-stu-id="2c47f-189">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="2c47f-190">Siga las instrucciones [aquí](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para configurar una sub-etiqueta de la etiqueta que está usando para archivos altamente regulados con los siguientes ajustes:</span><span class="sxs-lookup"><span data-stu-id="2c47f-190">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="2c47f-191">El nombre de la sub-etiqueta contiene el nombre del sitio para su fácil asociación cuando se asigna la sub-etiqueta a un archivo.</span><span class="sxs-lookup"><span data-stu-id="2c47f-191">The name of the sublabel contains the name of the site for easy association when assign the sublabel to a file.</span></span>
- <span data-ttu-id="2c47f-192">El cifrado está habilitado.</span><span class="sxs-lookup"><span data-stu-id="2c47f-192">Encryption is enabled.</span></span>
- <span data-ttu-id="2c47f-193">El grupo del sitio tiene permisos de Coautor.</span><span class="sxs-lookup"><span data-stu-id="2c47f-193">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="2c47f-194">Resultados de la configuración</span><span class="sxs-lookup"><span data-stu-id="2c47f-194">Configuration results</span></span>

<span data-ttu-id="2c47f-195">Ha configurado lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c47f-195">You have configured the following:</span></span>

- <span data-ttu-id="2c47f-196">Configuraciones de permisos más restrictivas en el sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="2c47f-196">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="2c47f-197">Una etiqueta de retención de Office 365 asignada a la parte de Documentos del sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="2c47f-197">An Office 365 retention label assigned to the SharePoint Online isolated site</span></span>
- <span data-ttu-id="2c47f-198">Una directiva DLP para la etiqueta de retención de Office 365</span><span class="sxs-lookup"><span data-stu-id="2c47f-198">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="2c47f-199">Una sub-etiqueta de confidencialidad de Office 365 que los usuarios pueden aplicar en los archivos más confidenciales almacenados en el sitio que cifra el archivo y solo permite el acceso de Coautor a los miembros del equipo de sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="2c47f-199">An Office 365 sensitivity sublabel that users can apply to the most sensitive files stored in the site that encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="2c47f-200">Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="2c47f-200">Here is the resulting configuration.</span></span>

![Sitios de SharePoint para un escenario de datos altamente regulados](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)


<span data-ttu-id="2c47f-202">Este es un ejemplo de un usuario que ha aplicado la sub-etiqueta de confidencialidad a un archivo almacenado en el sitio.</span><span class="sxs-lookup"><span data-stu-id="2c47f-202">Here is an example of a user that has applied the sensitivity sublabel to a file stored in the site.</span></span>

![Sitios de SharePoint para un escenario de datos altamente regulados](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="2c47f-204">Fase 3: Adopción por parte de los usuarios</span><span class="sxs-lookup"><span data-stu-id="2c47f-204">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="2c47f-205">Un sitio de SharePoint para datos altamente regulados solo puede proteger los datos si se usan de forma consistente para almacenar y acceder a archivos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="2c47f-205">A SharePoint Online site or team for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive digital assets. This is the hardest phase because it relies on users changing their ways.</span></span> <span data-ttu-id="2c47f-206">Esta es la fase más difícil, ya que depende de que los usuarios cambien sus hábitos y preferencias.</span><span class="sxs-lookup"><span data-stu-id="2c47f-206">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="2c47f-207">Por ejemplo, los empleados acostumbrados a guardar archivos confidenciales en unidades USB o en soluciones de almacenamiento personal basadas en la nube, ahora tendrán que almacenarlos de forma exclusiva en el sitio de SharePoint para datos altamente regulados.</span><span class="sxs-lookup"><span data-stu-id="2c47f-207">For example, executives that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint Online site or team for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="2c47f-208">Paso 1: formar a los usuarios</span><span class="sxs-lookup"><span data-stu-id="2c47f-208">Step 1: Train your users</span></span>

<span data-ttu-id="2c47f-209">Tras completar su configuración, tome un conjunto de usuarios que pertenezcan a los grupos de acceso del sitio y fórmelos sobre los siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c47f-209">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="2c47f-210">La importancia de usar el nuevo sitio para proteger archivos valiosos y las consecuencias de la filtración de datos altamente regulados, como las repercusiones legales, las multas, el ramsonware o la pérdida de ventaja frente a la competencia.</span><span class="sxs-lookup"><span data-stu-id="2c47f-210">On the importance of using the new site or team to protect valuable assets and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="2c47f-211">Cómo obtener acceso al sitio y a sus recursos.</span><span class="sxs-lookup"><span data-stu-id="2c47f-211">How to access the site and its assets.</span></span>
- <span data-ttu-id="2c47f-212">Cómo crear archivos nuevos en el sitio o cargar archivos nuevos almacenados de forma local.</span><span class="sxs-lookup"><span data-stu-id="2c47f-212">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="2c47f-213">Cómo la directiva DLP les impide compartir archivos de forma externa.</span><span class="sxs-lookup"><span data-stu-id="2c47f-213">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="2c47f-214">Cómo etiquetar los archivos más confidenciales con la sub-etiqueta del sitio.</span><span class="sxs-lookup"><span data-stu-id="2c47f-214">How to label the most sensitive files with the sublabel for the site.</span></span>
- <span data-ttu-id="2c47f-215">Cómo la sub-etiqueta protege un archivo incluso cuando se filtra el sitio.</span><span class="sxs-lookup"><span data-stu-id="2c47f-215">How the sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="2c47f-216">Esta formación debe incluir ejercicios prácticos para que los usuarios puedan experimentar con estas operaciones y sus resultados.</span><span class="sxs-lookup"><span data-stu-id="2c47f-216">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="2c47f-217">Paso 2: Realizar revisiones periódicas de uso y archivos</span><span class="sxs-lookup"><span data-stu-id="2c47f-217">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="2c47f-218">En las semanas posteriores a la formación, el administrador del servicio de SharePoint para el sitio de SharePoint puede:</span><span class="sxs-lookup"><span data-stu-id="2c47f-218">In the weeks after training, the SharePoint administrator for the SharePoint Online site or team can:</span></span>

- <span data-ttu-id="2c47f-219">Analizar el uso del sitio y compararlo con las expectativas de uso.</span><span class="sxs-lookup"><span data-stu-id="2c47f-219">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="2c47f-220">Comprobar que los archivos más confidenciales se han etiquetado de forma correcta con la sub-etiqueta de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="2c47f-220">Verify that highly sensitive files have been properly labeled with the Azure Information Protection sub-label.</span></span>

<span data-ttu-id="2c47f-221">Volver a dar formación a los usuarios que lo necesiten.</span><span class="sxs-lookup"><span data-stu-id="2c47f-221">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="2c47f-222">Resultados de la adopción de usuarios</span><span class="sxs-lookup"><span data-stu-id="2c47f-222">User adoption results</span></span>

<span data-ttu-id="2c47f-223">Los archivos altamente regulados se almacenan exclusivamente en sitios de SharePoint para datos altamente regulados y los archivos más confidenciales tienen la sub-etiqueta de sensibilidad para el sitio aplicada.</span><span class="sxs-lookup"><span data-stu-id="2c47f-223">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="2c47f-224">Cómo Contoso Corporation implementó Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2c47f-224">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="2c47f-225">Contoso Corporation es un conglomerado industrial a nivel mundial ficticio pero representativo, con sede central en París, Francia.</span><span class="sxs-lookup"><span data-stu-id="2c47f-225">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris, France.</span></span> <span data-ttu-id="2c47f-226">Vea cómo Contoso diseñó, configuró e impulsó la adopción de un [sitio de SharePoint Online seguro](contoso-sharepoint-online-site-for-highly-confidential-assets.md) para sus equipos de investigación en París, Moscú, Nueva York, Beijing y Bengaluru (Bangalore).</span><span class="sxs-lookup"><span data-stu-id="2c47f-226">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint Online site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="2c47f-227">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c47f-227">See also</span></span>

[<span data-ttu-id="2c47f-228">Guía de implementación</span><span class="sxs-lookup"><span data-stu-id="2c47f-228">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="2c47f-229">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="2c47f-229">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

