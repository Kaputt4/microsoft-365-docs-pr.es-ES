---
title: Sitios de Microsoft Teams y SharePoint Online para datos altamente regulados
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/03/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Cree un sitio de grupo de SharePoint Online o un equipo de Microsoft Teams para almacenar los recursos digitales más valiosos y confidenciales.
ms.openlocfilehash: 04984be44ddb2cc1aabc2032970f92e71899b268
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047351"
---
# <a name="microsoft-teams-and-sharepoint-online-sites-for-highly-regulated-data"></a><span data-ttu-id="1f4df-103">Sitios de Microsoft Teams y SharePoint Online para datos altamente regulados</span><span class="sxs-lookup"><span data-stu-id="1f4df-103">Microsoft Teams and SharePoint Online sites for highly regulated data</span></span>

<span data-ttu-id="1f4df-104">*Este escenario se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="1f4df-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="1f4df-p101">Microsoft 365 Enterprise incluye un conjunto completo de servicios en la nube para crear, guardar y proteger sus datos altamente regulados. Esto incluye:</span><span class="sxs-lookup"><span data-stu-id="1f4df-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data. This includes data that is:</span></span>

- <span data-ttu-id="1f4df-107">Datos sujetos a regulaciones regionales.</span><span class="sxs-lookup"><span data-stu-id="1f4df-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="1f4df-108">Los datos más importantes para su organización, como pueden ser secretos comerciales, información de recursos humanos o financiera y estrategias de la organización.</span><span class="sxs-lookup"><span data-stu-id="1f4df-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

<span data-ttu-id="1f4df-109">Un escenario basado en la nube de Microsoft 365 Enterprise que cumpla estas necesidades de negocio requiere que usted:</span><span class="sxs-lookup"><span data-stu-id="1f4df-109">A Microsoft 365 Enterprise cloud-based solution that meets this business need requires that you:</span></span>

- <span data-ttu-id="1f4df-110">Almacene los activos digitales (documentos, diapositivas, hojas de cálculo, etc.) en un sitio de grupo de SharePoint Online o en la pestaña **Archivos** de un equipo de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1f4df-110">Store digital assets (documents, slide decks, spreadsheets, etc.) in a SharePoint Online team site or in the **Files** tab of a Microsoft Teams team.</span></span>
- <span data-ttu-id="1f4df-111">Bloquee el sitio o equipo para evitar:</span><span class="sxs-lookup"><span data-stu-id="1f4df-111">Lock down the site or team to prevent:</span></span>
   - <span data-ttu-id="1f4df-112">El acceso únicamente a un conjunto específico de cuentas a través de la pertenencia a grupos, lo que incluye aquellas que pueden acceder al sitio de grupo de SharePoint Online y el nivel de permiso con el que cuentan, además de aquellas que pueden administrarlo.</span><span class="sxs-lookup"><span data-stu-id="1f4df-112">Access to only a specific set of user accounts through group membership, which includes those who can access the SharePoint Online team site and at what level of permission, and those who can administer it.</span></span>
   - <span data-ttu-id="1f4df-113">Que miembros del sitio concedan acceso a terceros.</span><span class="sxs-lookup"><span data-stu-id="1f4df-113">Members of the site from granting access to others.</span></span>
   - <span data-ttu-id="1f4df-114">Que aquellos que no sean miembros del sitio soliciten acceso.</span><span class="sxs-lookup"><span data-stu-id="1f4df-114">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="1f4df-115">Configure una etiqueta de retención de Office 365 para los sitios de SharePoint Online o equipos de forma predeterminada para definir directivas de retención en los documentos del sitio o equipo.</span><span class="sxs-lookup"><span data-stu-id="1f4df-115">Configure an Office 365 retention label for your SharePoint Online sites or teams as a default way to define retention policies on the documents in the site or team.</span></span>
- <span data-ttu-id="1f4df-116">Bloquea la capacidad de los usuarios de enviar archivos fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="1f4df-116">Block users from sending files outside the organization.</span></span>
- <span data-ttu-id="1f4df-117">Cifre los recursos digitales confidenciales del sitio o grupo.</span><span class="sxs-lookup"><span data-stu-id="1f4df-117">Encrypt the most sensitive digital assets of the site or team.</span></span>
- <span data-ttu-id="1f4df-118">Agregue permisos a los recursos digitales más confidenciales de modo que requieran las credenciales válidas de una cuenta de usuario para abrirse si se comparten fuera del sitio.</span><span class="sxs-lookup"><span data-stu-id="1f4df-118">Add permissions to the most sensitive digital assets so that if even if they get shared outside of the site, opening the asset still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="1f4df-119">En la tabla siguiente se asignan los requisitos de este escenario a una característica de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1f4df-119">The following table maps the requirements of this solution to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="1f4df-120">**Requisito**</span><span class="sxs-lookup"><span data-stu-id="1f4df-120">**Requirement**</span></span> | <span data-ttu-id="1f4df-121">**Característica de Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="1f4df-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="1f4df-122">Almacenar recursos digitales</span><span class="sxs-lookup"><span data-stu-id="1f4df-122">Store digital assets</span></span> | <span data-ttu-id="1f4df-123">Sitios de grupo de SharePoint Online y equipos en Office 365</span><span class="sxs-lookup"><span data-stu-id="1f4df-123">SharePoint Online team sites and teams in Office 365</span></span> |
| <span data-ttu-id="1f4df-124">Bloquear el sitio</span><span class="sxs-lookup"><span data-stu-id="1f4df-124">Lock down the site</span></span> | <span data-ttu-id="1f4df-125">Permisos de sitios de grupo de SharePoint Online y grupos de Azure AD</span><span class="sxs-lookup"><span data-stu-id="1f4df-125">Azure AD groups and SharePoint Online team site permissions</span></span> |
| <span data-ttu-id="1f4df-126">Etiquetar los recursos digitales del sitio</span><span class="sxs-lookup"><span data-stu-id="1f4df-126">Label the digital assets of the site</span></span> | <span data-ttu-id="1f4df-127">Etiquetas de retención de Office 365</span><span class="sxs-lookup"><span data-stu-id="1f4df-127">Office 365 retention labels</span></span> |
| <span data-ttu-id="1f4df-128">Bloquear a los usuarios cuando envían archivos fuera de la organización</span><span class="sxs-lookup"><span data-stu-id="1f4df-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="1f4df-129">Directivas de prevención de pérdida de datos (DLP) en Office 365</span><span class="sxs-lookup"><span data-stu-id="1f4df-129">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="1f4df-130">Cifrar todos los recursos digitales del sitio</span><span class="sxs-lookup"><span data-stu-id="1f4df-130">Encrypt all of the digital assets of the site</span></span> | <span data-ttu-id="1f4df-131">Etiquetas secundarias de Azure Information Protection en Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="1f4df-131">Azure Information Protection sub-labels in Enterprise Mobility + Security (EMS)</span></span> |
| <span data-ttu-id="1f4df-132">Añadir permisos a los recursos digitales del sitio</span><span class="sxs-lookup"><span data-stu-id="1f4df-132">Add permissions to the digital assets of the site</span></span> | <span data-ttu-id="1f4df-133">Etiquetas secundarias de Azure Information Protection en EMS</span><span class="sxs-lookup"><span data-stu-id="1f4df-133">Azure Information Protection sub-labels in EMS</span></span> |
|||

<span data-ttu-id="1f4df-134">Esta es la configuración para un sitio de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1f4df-134">Here is the configuration for a SharePoint Online site.</span></span>

![Sitios de Microsoft Teams y SharePoint Online para escenarios de datos altamente regulados](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="1f4df-136">Este escenario requiere que ya haya implementado:</span><span class="sxs-lookup"><span data-stu-id="1f4df-136">This solution requires that you have already deployed:</span></span>

- <span data-ttu-id="1f4df-137">La fase de [identidad](identity-infrastructure.md) y los pasos 1 y 2 de la fase de [protección de la información](infoprotect-infrastructure.md) de la infraestructura de base.</span><span class="sxs-lookup"><span data-stu-id="1f4df-137">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="1f4df-138">Para datos altamente regulados en sitios de grupo de SharePoint Online, [SharePoint Online](sharepoint-online-onedrive-workload.md).</span><span class="sxs-lookup"><span data-stu-id="1f4df-138">For highly regulated data in SharePoint Online team sites, [SharePoint Online](sharepoint-online-onedrive-workload.md).</span></span>
- <span data-ttu-id="1f4df-139">Para datos altamente regulados en equipos de Microsoft Teams, [Microsoft Teams](teams-workload.md).</span><span class="sxs-lookup"><span data-stu-id="1f4df-139">For highly regulated data in Microsoft Teams teams, [Microsoft Teams](teams-workload.md).</span></span>

<span data-ttu-id="1f4df-140">Las siguientes fases le guiarán a través del diseño, la configuración y la adopción de impulso de los sitios y grupos de datos altamente regulados de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1f4df-140">The following phases step you through the design, configuration, and driving adoption for SharePoint Online sites and teams for highly regulated data.</span></span>

<span data-ttu-id="1f4df-141">Para ver cómo Contoso Corporation, una organización multinacional ficticia pero representativa, diseñó un sitio de SharePoint Online para los equipos de investigación, vea esta [configuración de ejemplo](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span><span class="sxs-lookup"><span data-stu-id="1f4df-141">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint Online site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>

<span data-ttu-id="1f4df-p102">Un grupo de datos altamente regulados requiere crear primero un sitio de grupo de SharePoint Online para datos altamente regulados. A continuación, se debe crear un equipo que use el grupo de Office 365 del sitio de grupo de SharePoint Online. Consulte el paso 4 de la fase 2 para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1f4df-p102">A team for highly regulated data requires that you first create a SharePoint Online team site for highly regulated data. You then create a new team that uses the Office 365 group of the SharePoint Online team site. See Phase 2, Step 4 for more information.</span></span>

<span data-ttu-id="1f4df-145">Esta es la configuración de un equipo.</span><span class="sxs-lookup"><span data-stu-id="1f4df-145">Here is the configuration for a team.</span></span>

![Sitios de Microsoft Teams y SharePoint Online para escenarios de datos altamente regulados](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-team.png)


## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="1f4df-147">Requisitos previos de acceso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="1f4df-147">Identity and device access prerequisites</span></span>

<span data-ttu-id="1f4df-148">Para proteger el acceso al sitio o grupo de SharePoint Online, asegúrese de haber configurado [directivas de acceso de identidades y dispositivos](identity-access-policies.md) y [directivas de acceso recomendadas de SharePoint Online](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1f4df-148">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="1f4df-149">Fase 1: Diseño</span><span class="sxs-lookup"><span data-stu-id="1f4df-149">Phase 1: Design</span></span>

<span data-ttu-id="1f4df-p103">Para crear un sitio o grupo de SharePoint Online para datos altamente regulados, primero debe identificar su propósito. Por ejemplo, el departamento de investigación y desarrollo de una empresa de fabricación tiene un sitio de SharePoint Online para almacenar las especificaciones de diseño actuales de los productos existentes y un sitio para colaborar en nuevos productos. Solo los miembros del departamento de investigación y desarrollo y determinados directivos podrán tener acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="1f4df-p103">To create a SharePoint Online site or team for highly regulated data, you must first identify its purpose. For example, the research and development department of a manufacturing organization needs a SharePoint Online site to store current design specifications for existing products and a place to collaborate on new products. Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="1f4df-153">Ese propósito impulsará la determinación de los elementos de configuración esenciales, como:</span><span class="sxs-lookup"><span data-stu-id="1f4df-153">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="1f4df-154">Los conjuntos de permisos de SharePoint Online y los grupos de SharePoint</span><span class="sxs-lookup"><span data-stu-id="1f4df-154">The set of SharePoint Online permission sets and SharePoint groups</span></span>
- <span data-ttu-id="1f4df-155">El conjunto de grupos de acceso, los grupos de seguridad de Azure AD y sus miembros que se agregarán a los grupos de SharePoint</span><span class="sxs-lookup"><span data-stu-id="1f4df-155">The set of access groups, the Azure AD security groups and their members to add to the SharePoint groups</span></span>
- <span data-ttu-id="1f4df-156">La etiqueta de retención de Office 365 para asignar al sitio y el conjunto de directivas DLP para la etiqueta</span><span class="sxs-lookup"><span data-stu-id="1f4df-156">The Office 365 retention label to assign to the site and the set of DLP policies for the label</span></span>
- <span data-ttu-id="1f4df-157">La configuración de una etiqueta secundaria de Azure Information Protection que los usuarios aplican a los recursos digitales más confidenciales almacenados en el sitio</span><span class="sxs-lookup"><span data-stu-id="1f4df-157">The settings of an Azure Information Protection sub-label that users apply to highly sensitive digital assets stored in the site</span></span>

<span data-ttu-id="1f4df-158">Una vez determinadas, use estas opciones para configurar el sitio en la fase 2.</span><span class="sxs-lookup"><span data-stu-id="1f4df-158">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-an-isolated-sharepoint-online-site"></a><span data-ttu-id="1f4df-159">Paso 1: Sitio de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="1f4df-159">Step 1: An isolated SharePoint Online site</span></span>

<span data-ttu-id="1f4df-p104">La versión bloqueada de un sitio de grupo de SharePoint Online recibe el nombre de sitio aislado. A diferencia de la configuración predeterminada de los sitios de grupo privados, los sitios aislados están configurados para impedir:</span><span class="sxs-lookup"><span data-stu-id="1f4df-p104">The locked-down version of a SharePoint Online team site is known as an isolated site. Unlike the default settings of private team sites, isolated sites are configured to prevent:</span></span>

- <span data-ttu-id="1f4df-162">El acceso a los usuarios que no son miembros de grupos específicos.</span><span class="sxs-lookup"><span data-stu-id="1f4df-162">Access to those who are not members of specified groups.</span></span>
- <span data-ttu-id="1f4df-163">La solicitud de acceso.</span><span class="sxs-lookup"><span data-stu-id="1f4df-163">The requesting of access.</span></span>
- <span data-ttu-id="1f4df-164">La concesión de acceso no autorizado por parte de los miembros actuales de grupos específicos.</span><span class="sxs-lookup"><span data-stu-id="1f4df-164">The unauthorized granting of access by current members of specified groups.</span></span>
- <span data-ttu-id="1f4df-165">La administración del sitio por parte de miembros con acceso al grupo.</span><span class="sxs-lookup"><span data-stu-id="1f4df-165">Administration of the site by access group members.</span></span>

<span data-ttu-id="1f4df-166">La seguridad de los sitios de grupo de SharePoint Online que contienen recursos altamente regulados no cambia a menos que lo haga un administrador de SharePoint del sitio.</span><span class="sxs-lookup"><span data-stu-id="1f4df-166">The security of SharePoint Online team sites that contain highly regulated assets do not change unless done by a SharePoint administrator for the site.</span></span>

<span data-ttu-id="1f4df-167">Consulte [Diseñar un sitio de grupo de SharePoint Online aislado](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site) para obtener los detalles que determinan el conjunto de niveles de permisos, grupos de SharePoint, grupos de acceso y miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="1f4df-167">See [Design an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site) for the details to determine the set of permission levels, SharePoint groups, access groups, and group members.</span></span>

### <a name="step-2-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="1f4df-168">Paso 2: Etiquetas de retención de Office 365 y directivas DLP</span><span class="sxs-lookup"><span data-stu-id="1f4df-168">Step 2: Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="1f4df-169">Cuando se aplican a un sitio de grupo de SharePoint Online, las etiquetas de retención de Office 365 proporcionan un método predeterminado de clasificación para todos los recursos digitales almacenados en el sitio.</span><span class="sxs-lookup"><span data-stu-id="1f4df-169">When applied to a SharePoint Online team site, Office 365 retention labels provide a default method of classifying all digital assets stored on the site.</span></span>
 
<span data-ttu-id="1f4df-170">En los sitios de SharePoint Online para datos altamente regulados, debe determinar qué etiqueta de retención de Office 365 usar.</span><span class="sxs-lookup"><span data-stu-id="1f4df-170">For SharePoint Online sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="1f4df-171">Para conocer las consideraciones de diseño de las etiquetas de Office 365, consulte [Etiquetas y clasificación de Office 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="1f4df-171">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="1f4df-p105">Use directivas DLP para proteger la información confidencial y evitar su divulgación accidental o intencionada. Para obtener más información, consulte esta [introducción](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span><span class="sxs-lookup"><span data-stu-id="1f4df-p105">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="1f4df-174">En los sitios de SharePoint Online con datos altamente regulados, debe configurar una directiva DLP para la etiqueta de retención de Office 365 asignada al sitio; esta directiva deberá bloquear a los usuarios cuando intenten compartir recursos digitales con usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="1f4df-174">For SharePoint Online sites for highly regulated data, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share digital assets with external users.</span></span> 

### <a name="step-3-your-azure-information-protection-sub-label"></a><span data-ttu-id="1f4df-175">Paso 3: Etiqueta secundaria de Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="1f4df-175">Step 3: Your Azure Information Protection sub-label</span></span>

<span data-ttu-id="1f4df-p106">Para cifrar los recursos digitales más sensibles y establecer en ellos un conjunto de permisos, los usuarios deben aplicar una etiqueta de Azure Information Protection. Para usar las etiquetas de Azure Information Protection en sitios de SharePoint Online para datos altamente regulados, debe configurar una etiqueta secundaria de Azure Information Protection en una directiva con ámbito.</span><span class="sxs-lookup"><span data-stu-id="1f4df-p106">To provide encryption and a set of permissions to your most sensitive digital assets, users must apply an Azure Information Protection label using the Azure Information Protection client. To use Azure Information Protection labels for SharePoint Online sites for highly regulated data, you must configure an Azure Information Protection sub-label in a scoped policy.</span></span> 

<span data-ttu-id="1f4df-p107">Las etiquetas secundarias se encuentran bajo etiquetas existentes. Por ejemplo, puede crear la etiqueta secundaria Investigación y desarrollo en la etiqueta Muy confidencial. Una directiva con ámbito es aquella que se aplica únicamente a un subconjunto de usuarios. Para los sitios de SharePoint Online para datos altamente regulados, el ámbito es el conjunto de usuarios que sean miembros de los grupos de acceso del sitio.</span><span class="sxs-lookup"><span data-stu-id="1f4df-p107">A sub-label exists under an existing label. For example, you can create a Research & Development sub-label under the Highly Confidential label. A scoped policy is one that applies only to a subset of users. For SharePoint Online sites for highly regulated data, the scope is the set of users that are members of the access groups for the site.</span></span>

<span data-ttu-id="1f4df-p108">La configuración de la etiqueta secundaria aplicada se asocia al recurso. Aunque se descargue y comparta fuera del sitio, solo las cuentas de usuario autenticadas que tengan permisos podrán abrirlo.</span><span class="sxs-lookup"><span data-stu-id="1f4df-p108">The settings of the applied sub-label travel with the asset. Even if it is downloaded and shared outside the site, only authenticated user accounts that have permissions can open it.</span></span>

### <a name="design-results"></a><span data-ttu-id="1f4df-184">Resultados de diseño</span><span class="sxs-lookup"><span data-stu-id="1f4df-184">Design results</span></span>

<span data-ttu-id="1f4df-185">Ha decidido lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1f4df-185">You have determined the following:</span></span>

- <span data-ttu-id="1f4df-186">El conjunto de grupos de SharePoint y los niveles de permisos</span><span class="sxs-lookup"><span data-stu-id="1f4df-186">The set of SharePoint groups and permission levels</span></span>
- <span data-ttu-id="1f4df-187">El conjunto de grupos de acceso y sus miembros en cada nivel de permisos</span><span class="sxs-lookup"><span data-stu-id="1f4df-187">The set of access groups and their members for each permission level</span></span>
- <span data-ttu-id="1f4df-188">La etiqueta de retención adecuada de Office 365 y la directiva DLP que tiene asociada</span><span class="sxs-lookup"><span data-stu-id="1f4df-188">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="1f4df-189">La configuración de la etiqueta secundaria de Azure Information Protection que incluye cifrado y permisos</span><span class="sxs-lookup"><span data-stu-id="1f4df-189">The settings of the Azure Information Protection sub-label that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="1f4df-190">Fase 2: Configurar</span><span class="sxs-lookup"><span data-stu-id="1f4df-190">Phase 2: Configure</span></span>

<span data-ttu-id="1f4df-191">En esta fase, debe tomar la configuración determinada en la fase 1 e implementarla para crear un sitio de SharePoint Online para datos altamente regulados.</span><span class="sxs-lookup"><span data-stu-id="1f4df-191">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint Online site for highly regulated data.</span></span>

### <a name="step-1-create-and-configure-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="1f4df-192">Paso 1: Crear y configurar un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="1f4df-192">Step 1: Create and configure an isolated SharePoint Online team site</span></span>

<span data-ttu-id="1f4df-193">Siga las instrucciones de [Implementar un sitio de grupo aislado de SharePoint Online](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site) para:</span><span class="sxs-lookup"><span data-stu-id="1f4df-193">Use the instructions in [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site) to:</span></span>

- <span data-ttu-id="1f4df-194">Crear y rellenar los grupos de acceso para cada nivel de permiso de SharePoint usado en el sitio.</span><span class="sxs-lookup"><span data-stu-id="1f4df-194">Create and populate the access groups for each SharePoint permission level used on the site.</span></span>
- <span data-ttu-id="1f4df-195">Crear y configurar el sitio de grupo aislado.</span><span class="sxs-lookup"><span data-stu-id="1f4df-195">Create and configure the isolated team site.</span></span>

### <a name="step-2-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="1f4df-196">Paso 2: configurar el sitio para una etiqueta de retención de Office 365</span><span class="sxs-lookup"><span data-stu-id="1f4df-196">Step 2: Configure the site for an Office 365 retention label DLP policy</span></span>

<span data-ttu-id="1f4df-197">Siga las instrucciones de [Proteger archivos de SharePoint Online con DLP y etiquetas de Office 365](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) para:</span><span class="sxs-lookup"><span data-stu-id="1f4df-197">Use the instructions in [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

- <span data-ttu-id="1f4df-198">Identificar o crear la etiqueta de retención de Office 365 y aplicarla a su sitio de SharePoint Online aislado.</span><span class="sxs-lookup"><span data-stu-id="1f4df-198">Identify or create the Office 365 retention label and apply it to your isolated SharePoint Online site.</span></span>
- <span data-ttu-id="1f4df-199">Crear y configurar la directiva DLP que bloquee a los usuarios cuando intenten compartir un recurso digital de su sitio de SharePoint Online fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="1f4df-199">Create and configure the DLP policy that blocks users when they attempt to share a digital asset on your SharePoint Online site outside the organization.</span></span>

### <a name="step-3-create-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="1f4df-200">Paso 3: Crear una etiqueta secundaria de Azure Information Protection para el sitio</span><span class="sxs-lookup"><span data-stu-id="1f4df-200">Step 3: Create an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="1f4df-201">Siga las instrucciones de [Proteger archivos de SharePoint Online con Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection) para:</span><span class="sxs-lookup"><span data-stu-id="1f4df-201">Use the instructions in [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection) to:</span></span> 

- <span data-ttu-id="1f4df-202">Crear y configurar una etiqueta secundaria de Azure Information Protection en una directiva con ámbito.</span><span class="sxs-lookup"><span data-stu-id="1f4df-202">Create and configure an Azure Information Protection sub-label in a scoped policy.</span></span>
- <span data-ttu-id="1f4df-203">Implementar el cliente de Azure Information Protection en los equipos usuarios.</span><span class="sxs-lookup"><span data-stu-id="1f4df-203">Deploy the Azure Information Protection client to user computers.</span></span>

### <a name="step-4-optional-create-a-team-for-the-highly-regulated-data"></a><span data-ttu-id="1f4df-204">Paso 4 (opcional): Crear un grupo para los datos altamente regulados</span><span class="sxs-lookup"><span data-stu-id="1f4df-204">Step 4 (optional): Create a team for the highly regulated data</span></span>

<span data-ttu-id="1f4df-p109">Si desea un grupo para datos altamente regulados, primero debe crear un sitio de SharePoint Online para datos altamente regulados. Al crear el sitio de grupo de SharePoint Online privado inicial, especifique un nombre de grupo de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1f4df-p109">If you want a team for highly regulated data, you first create a SharePoint Online site for highly regulated data. When you create the initial private SharePoint Online team site, you specify an Office 365 group name.</span></span>

<span data-ttu-id="1f4df-207">Cuando el sitio de SharePoint Online para datos altamente regulados esté completamente configurado, siga estos pasos para convertirlo en un equipo para datos altamente regulados:</span><span class="sxs-lookup"><span data-stu-id="1f4df-207">After the SharePoint Online site for highly regulated data is fully configured, use these steps to convert it into a team for highly regulated data:</span></span>

1. <span data-ttu-id="1f4df-208">Inicie sesión en Office 365.</span><span class="sxs-lookup"><span data-stu-id="1f4df-208">Sign in to Office 365.</span></span>
2. <span data-ttu-id="1f4df-209">En la pestaña **Página principal de Microsoft Office**, haga clic en **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="1f4df-209">From the **Microsoft Office Home** tab, click **Teams**.</span></span>
3. <span data-ttu-id="1f4df-210">Desde la pestaña **Microsoft Teams**, en el panel **Unirse o crear un equipo**, haga clic en **Crear equipo**.</span><span class="sxs-lookup"><span data-stu-id="1f4df-210">From the **Microsoft Teams** tab, in the **Join or create a team** pane, click **Create team**.</span></span>
4. <span data-ttu-id="1f4df-211">En el panel **Crear su equipo**, haga clic en **Crear un equipo de un grupo existente de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="1f4df-211">In the **Create your team** pane, click **Create a team from an existing Office 365 group**.</span></span>
5. <span data-ttu-id="1f4df-212">En la lista de grupos de Office 365, seleccione el nombre del grupo de Office 365 correspondiente al sitio de SharePoint Online para datos altamente regulados y, a continuación, haga clic en **Elegir equipo**.</span><span class="sxs-lookup"><span data-stu-id="1f4df-212">In the list of Office 365 groups, select the name of the Office 365 group corresponding to the SharePoint Online site for highly regulated data, and then click **Choose team**.</span></span>

<span data-ttu-id="1f4df-p110">La pestaña **Archivos** del equipo nuevo incluye el contenido de la carpeta **General** del área **Documentos** del sitio de SharePoint Online correspondiente. Para ver el resto de los recursos del sitio de SharePoint Online para el equipo, haga clic en los puntos suspensivos y, a continuación, haga clic en **Abrir en SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="1f4df-p110">The **Files** tab of the new team lists the contents of the **General** folder of the **Documents** area of the corresponding SharePoint Online site. To see the rest of the resources of the SharePoint Online site for the team, click the ellipsis, and then click **Open in SharePoint**.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="1f4df-215">Resultados de la configuración</span><span class="sxs-lookup"><span data-stu-id="1f4df-215">Configuration results</span></span>

<span data-ttu-id="1f4df-216">Ha configurado lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1f4df-216">You have configured the following:</span></span>

- <span data-ttu-id="1f4df-217">Un sitio de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="1f4df-217">A SharePoint Online isolated site</span></span>
- <span data-ttu-id="1f4df-218">Una etiqueta de retención de Office 365 asignada al sitio de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="1f4df-218">An Office 365 retention label assigned to the SharePoint Online isolated site</span></span>
- <span data-ttu-id="1f4df-219">Una directiva DLP para la etiqueta de retención de Office 365</span><span class="sxs-lookup"><span data-stu-id="1f4df-219">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="1f4df-220">Una etiqueta secundaria de Azure Information Protection de una directiva con ámbito que los usuarios pueden aplicar a los recursos digitales más confidenciales almacenados en el sitio que cifra el recurso y exige permisos</span><span class="sxs-lookup"><span data-stu-id="1f4df-220">An Azure Information Protection sub-label of a scoped policy that users can apply to the most sensitive digital assets stored in the site that encrypts the asset and enforces permissions</span></span>
- <span data-ttu-id="1f4df-221">Si es necesario, un equipo para datos altamente regulados basado en el sitio de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1f4df-221">If needed, a team for highly regulated data based on the SharePoint Online site</span></span>

## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="1f4df-222">Fase 3: Adopción por parte de los usuarios de la unidad</span><span class="sxs-lookup"><span data-stu-id="1f4df-222">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="1f4df-p111">Un sitio o grupo de SharePoint Online para datos altamente regulados solo puede proteger esos datos si siempre se usa para el almacenamiento y el acceso de recursos digitales confidenciales. Esta es la fase más difícil porque depende de que los usuarios cambien sus hábitos.</span><span class="sxs-lookup"><span data-stu-id="1f4df-p111">A SharePoint Online site or team for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive digital assets. This is the hardest phase because it relies on users changing their ways.</span></span> 

<span data-ttu-id="1f4df-225">Por ejemplo, los directivos acostumbrados a almacenar archivos confidenciales en unidades USB o en almacenamiento personal basado en la nube, ahora tendrán que almacenarlos de forma exclusiva en el sitio o grupo de SharePoint Online para datos altamente regulados.</span><span class="sxs-lookup"><span data-stu-id="1f4df-225">For example, executives that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint Online site or team for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="1f4df-226">Paso 1: Entrenar a los usuarios</span><span class="sxs-lookup"><span data-stu-id="1f4df-226">Step 1: Train your users</span></span>

<span data-ttu-id="1f4df-227">Tras completar su configuración, tome un conjunto de usuarios que pertenezcan a los grupos de acceso del sitio y fórmelos sobre los siguiente:</span><span class="sxs-lookup"><span data-stu-id="1f4df-227">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="1f4df-228">La importancia de usar el nuevo sitio o equipo para proteger recursos valiosos y las consecuencias de la filtración de datos altamente regulados, como las repercusiones legales, las multas, el ramsonware o la pérdida de ventaja frente a la competencia.</span><span class="sxs-lookup"><span data-stu-id="1f4df-228">On the importance of using the new site or team to protect valuable assets and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="1f4df-229">Cómo obtener acceso al sitio y a sus recursos.</span><span class="sxs-lookup"><span data-stu-id="1f4df-229">How to access the site and its assets.</span></span>
- <span data-ttu-id="1f4df-230">Cómo crear archivos nuevos en el sitio o cargar archivos nuevos almacenados de forma local.</span><span class="sxs-lookup"><span data-stu-id="1f4df-230">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="1f4df-231">Cómo la directiva DLP les impide compartir archivos de forma externa.</span><span class="sxs-lookup"><span data-stu-id="1f4df-231">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="1f4df-232">Cómo usar el cliente de Azure Information Protection para etiquetar los recursos digitales más confidenciales con la etiqueta secundaria configurada.</span><span class="sxs-lookup"><span data-stu-id="1f4df-232">How to use the Azure Information Protection client to label the most sensitive digital assets with the configured sub-label.</span></span>
- <span data-ttu-id="1f4df-233">Cómo la etiqueta secundaria de Azure Information Protection protege un recurso incluso tras su filtración fuera del sitio o equipo.</span><span class="sxs-lookup"><span data-stu-id="1f4df-233">How the Azure Information Protection sub-label protects an asset even when it is leaked off the site or team.</span></span>

<span data-ttu-id="1f4df-234">Esta formación debe incluir ejercicios prácticos para que los usuarios puedan experimentar con estas operaciones y sus resultados.</span><span class="sxs-lookup"><span data-stu-id="1f4df-234">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="1f4df-235">Paso 2: Realizar revisiones periódicas de uso y archivos</span><span class="sxs-lookup"><span data-stu-id="1f4df-235">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="1f4df-236">En las semanas posteriores a la formación, el administrador de SharePoint del sitio o grupo de SharePoint Online puede:</span><span class="sxs-lookup"><span data-stu-id="1f4df-236">In the weeks after training, the SharePoint administrator for the SharePoint Online site or team can:</span></span>

- <span data-ttu-id="1f4df-237">Analizar el uso del sitio o grupo y compararlo con las expectativas de uso.</span><span class="sxs-lookup"><span data-stu-id="1f4df-237">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="1f4df-238">Comprobar que los archivos más confidenciales se han etiquetado de forma correcta con la etiqueta secundaria de Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="1f4df-238">Verify that highly sensitive files have been properly labeled with the Azure Information Protection sub-label.</span></span>

<span data-ttu-id="1f4df-239">Volver a dar formación a los usuarios que lo necesiten.</span><span class="sxs-lookup"><span data-stu-id="1f4df-239">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="1f4df-240">Resultados de la adopción de usuarios</span><span class="sxs-lookup"><span data-stu-id="1f4df-240">User adoption results</span></span>

<span data-ttu-id="1f4df-241">Los recursos digitales confidenciales se almacenan de forma exclusiva en sitios o grupos de SharePoint Online para datos altamente regulados y los datos más confidenciales tienen aplicada la etiqueta secundaria de Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="1f4df-241">Sensitive digital assets are stored exclusively on SharePoint Online sites or teams for highly regulated data and that the most sensitive assets have the configured Azure Information Protection sub-label applied.</span></span>

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="1f4df-242">Cómo Contoso Corporation implementó Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1f4df-242">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="1f4df-243">Contoso Corporation es un conglomerado industrial a nivel mundial ficticio pero representativo, con sede central en París, Francia.</span><span class="sxs-lookup"><span data-stu-id="1f4df-243">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris, France.</span></span> <span data-ttu-id="1f4df-244">Vea cómo Contoso diseñó, configuró y, después, impulsó la adopción de un [sitio de SharePoint Online seguro](contoso-sharepoint-online-site-for-highly-confidential-assets.md) para sus equipos de investigación en París, Moscú, Nueva York, Beijing y Bengaluru (Bangalore).</span><span class="sxs-lookup"><span data-stu-id="1f4df-244">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint Online site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="1f4df-245">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f4df-245">See also</span></span>

[<span data-ttu-id="1f4df-246">Guía de implementación</span><span class="sxs-lookup"><span data-stu-id="1f4df-246">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="1f4df-247">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="1f4df-247">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="1f4df-248">Proteger sitios de SharePoint Online en un entorno de desarrollo y pruebas</span><span class="sxs-lookup"><span data-stu-id="1f4df-248">Secure SharePoint Online sites in a dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-in-a-dev-test-environment)
