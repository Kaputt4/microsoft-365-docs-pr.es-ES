---
title: 'Crear sitios de grupo: entorno de desarrollo de campaña política'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/21/2018
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 'Resumen: Cree sitios de grupo de SharePoint Online públicos, privados, confidenciales o extremadamente confidenciales en el entorno de desarrollo y prueba de una campaña política.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ba0eb1e3ff0539f9aec6993fb25fe576f08f84d5
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028780"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="53ac2-103">Crear sitios de grupo en un entorno de desarrollo y prueba de campaña política</span><span class="sxs-lookup"><span data-stu-id="53ac2-103">Create team sites in a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="53ac2-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="53ac2-104">**Applies to**</span></span>

- [<span data-ttu-id="53ac2-105">Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="53ac2-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

 <span data-ttu-id="53ac2-106">**Resumen:** Cree sitios de grupo de SharePoint Online públicos, privados, confidenciales o extremadamente confidenciales en un entorno de desarrollo y prueba para una campaña política.</span><span class="sxs-lookup"><span data-stu-id="53ac2-106">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span> 
   
<span data-ttu-id="53ac2-p101">Siga las instrucciones de este artículo para crear un entorno de desarrollo y prueba que incluya los cuatro tipos distintos de sitios de grupo de SharePoint Online para la solución de [Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md). Estos sitios se describen en detalle en el tema 10, titulado **SharePoint y OneDrive para la Empresa**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-p101">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution. These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>

## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="53ac2-109">Fase 1: Crear un entorno de desarrollo y prueba de campaña política</span><span class="sxs-lookup"><span data-stu-id="53ac2-109">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="53ac2-110">En primer lugar, siga las instrucciones de [Configurar grupos y usuarios en un entorno de desarrollo y prueba de campaña política](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) para crear las suscripciones, los usuarios y los grupos.</span><span class="sxs-lookup"><span data-stu-id="53ac2-110">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>

## <a name="phase-2-create-labels"></a><span data-ttu-id="53ac2-111">Fase 2: Crear etiquetas</span><span class="sxs-lookup"><span data-stu-id="53ac2-111">Phase 2: Create labels</span></span>

<span data-ttu-id="53ac2-112">En esta fase se crean las etiquetas para los diferentes niveles de seguridad de las carpetas de documentos de sitios de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="53ac2-112">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>

1. <span data-ttu-id="53ac2-p102">Si es necesario, inicie sesión en el Centro de administración con las credenciales de la cuenta de administrador global de la suscripción de evaluación. Para obtener ayuda, vea [Dónde iniciar sesión en Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="53ac2-p102">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription. For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="53ac2-115">En la pestaña **Inicio de Microsoft Office**, haga clic en el icono **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-115">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>

3. <span data-ttu-id="53ac2-116">En la nueva pestaña **Centro de administración de Microsoft 365** del explorador, haga clic en **Centros de administración > Seguridad y Cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-116">From the new **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>

4. <span data-ttu-id="53ac2-117">En la nueva pestaña **Inicio - Seguridad y cumplimiento** del explorador, haga clic en **Clasificaciones > Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-117">From the new **Home - Security & Compliance** tab of your browser, click **Classifications > Labels**.</span></span>

5. <span data-ttu-id="53ac2-118">En el panel **Inicio > Etiquetas**, haga clic en **Crear una etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-118">From the **Home > Labels** pane, click **Create a label**.</span></span>

6. <span data-ttu-id="53ac2-119">En el panel **Asignar un nombre a la etiqueta**, escriba **Interna** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-119">On the **Name your label** pane, type **Internal**, and then click **Next**.</span></span>

7. <span data-ttu-id="53ac2-120">En el panel **Configuración de etiquetas**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-120">On the **Label settings** pane, click **Next**.</span></span>

8. <span data-ttu-id="53ac2-121">En el panel **Revise su configuración**, haga clic en **Crear esta etiqueta** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-121">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>

9. <span data-ttu-id="53ac2-122">Repita los pasos del 5 al 8 para estas etiquetas adicionales:</span><span class="sxs-lookup"><span data-stu-id="53ac2-122">Repeat steps 5-8 for these additional labels:</span></span>

   - <span data-ttu-id="53ac2-123">Private</span><span class="sxs-lookup"><span data-stu-id="53ac2-123">Private</span></span>
   - <span data-ttu-id="53ac2-124">Confidencial</span><span class="sxs-lookup"><span data-stu-id="53ac2-124">Sensitive</span></span>
   - <span data-ttu-id="53ac2-125">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="53ac2-125">Highly Confidential</span></span>

10. <span data-ttu-id="53ac2-126">En el panel **Inicio > Etiquetas**, haga clic para **Publish labels** (Publicar etiquetas).</span><span class="sxs-lookup"><span data-stu-id="53ac2-126">From the **Home > Labels** pane, click **Publish labels**.</span></span>

11. <span data-ttu-id="53ac2-127">En el panel **Elegir etiquetas para publicar**, haga clic en **Elegir etiquetas para publicar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-127">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>

12. <span data-ttu-id="53ac2-128">En el panel de **elección de etiquetas**, haga clic en **Agregar** y seleccione las cuatro etiquetas.</span><span class="sxs-lookup"><span data-stu-id="53ac2-128">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>

13. <span data-ttu-id="53ac2-129">Haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-129">Click **Done**.</span></span>

14. <span data-ttu-id="53ac2-130">En el panel **Elegir etiquetas para publicar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-130">On the **Choose labels to publish** pane, click **Next**.</span></span>

15. <span data-ttu-id="53ac2-131">En el panel **Elegir ubicaciones**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-131">On the **Choose locations** pane, click **Next**.</span></span>

16. <span data-ttu-id="53ac2-132">En el panel **Escriba un nombre para la directiva**, escriba **Campaña** en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-132">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>

17. <span data-ttu-id="53ac2-133">En el panel **Revise su configuración**, haga clic en **Publicar etiquetas** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-133">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="53ac2-134">Fase 3: Crear los sitios de grupo de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="53ac2-134">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="53ac2-135">En esta fase se crean y configuran los sitios de grupo de SharePoint Online para la campaña política correspondientes a los cuatro tipos de sitios de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="53ac2-135">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>

### <a name="campaign-wide-team-site"></a><span data-ttu-id="53ac2-136">Sitio de grupo de toda la campaña</span><span class="sxs-lookup"><span data-stu-id="53ac2-136">Campaign wide team site</span></span>

<span data-ttu-id="53ac2-137">Para crear un sitio de grupo público de línea base de SharePoint Online, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="53ac2-137">To create a baseline public SharePoint Online team site, do the following:</span></span>

1. <span data-ttu-id="53ac2-138">Si es necesario, use un explorador en el equipo local e inicie sesión en el Centro de administración (<https://admin.microsoft.com>) con la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="53ac2-138">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="53ac2-139">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-139">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="53ac2-140">En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-140">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="53ac2-141">En la página **Crear un sitio**, haga clic en **Sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-141">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="53ac2-142">En **Nombre del sitio**, escriba **Toda la campaña**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-142">In **Site name**, type **Campaign wide**.</span></span>

6. <span data-ttu-id="53ac2-143">En **Team site description** (Descripción del sitio de grupo), escriba **Sitio de SharePoint para toda la campaña**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-143">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>

7. <span data-ttu-id="53ac2-144">En **Configuración de privacidad**, seleccione **Public – anyone in the organization can access this site** (Público: cualquier usuario de la organización tiene acceso a este sitio) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-144">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="53ac2-145">En el panel **Who do you want to add?** (Usuarios que quiere agregar), haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-145">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="53ac2-146">Después, configure la carpeta de documentos del sitio de grupo Toda la campaña con la etiqueta Interna.</span><span class="sxs-lookup"><span data-stu-id="53ac2-146">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>

1. <span data-ttu-id="53ac2-147">En la pestaña **Toda la campaña-Inicio** del explorador, haga clic en **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-147">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="53ac2-148">Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-148">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="53ac2-149">En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).</span><span class="sxs-lookup"><span data-stu-id="53ac2-149">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="53ac2-150">En **Configuración-Aplicar etiqueta**, seleccione **Interna** y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-150">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>

### <a name="campaign-project-1-team-site"></a><span data-ttu-id="53ac2-151">Sitio de grupo del proyecto de campaña 1</span><span class="sxs-lookup"><span data-stu-id="53ac2-151">Campaign project 1 team site</span></span>

<span data-ttu-id="53ac2-152">Para crear un sitio de grupo privado de línea base de SharePoint Online para un proyecto dentro de la organización, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="53ac2-152">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>

1. <span data-ttu-id="53ac2-153">Si es necesario, use un explorador en el equipo local e inicie sesión en el Centro de administración (<https://admin.microsoft.com>) con la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="53ac2-153">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="53ac2-154">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-154">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="53ac2-155">En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-155">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="53ac2-156">En la página **Crear un sitio**, haga clic en **Sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-156">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="53ac2-157">En **Nombre del sitio**, escriba **Proyecto de campaña 1**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-157">In **Site name**, type **Campaign project 1**.</span></span>

6. <span data-ttu-id="53ac2-158">En **Team site description** (Descripción del sitio de grupo), escriba **Sitio de SharePoint para el proyecto de campaña 1**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-158">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>

7. <span data-ttu-id="53ac2-159">En **Configuración de privacidad**, seleccione **Private - only members can access this site** (Privado: solo los miembros tienen acceso a este sitio) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-159">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="53ac2-160">En el panel **Who do you want to add?** (Usuarios que quiere agregar), haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-160">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="53ac2-161">Después, configure la carpeta de documentos del sitio de grupo Proyecto de campaña 1 con la etiqueta Privada.</span><span class="sxs-lookup"><span data-stu-id="53ac2-161">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>

1. <span data-ttu-id="53ac2-162">En la pestaña **Proyecto de campaña 1-Inicio** del explorador, haga clic en **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-162">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="53ac2-163">Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-163">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="53ac2-164">En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).</span><span class="sxs-lookup"><span data-stu-id="53ac2-164">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="53ac2-165">En **Configuración-Aplicar etiqueta**, seleccione **Privado** y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-165">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>

### <a name="campaign-marketing-team-site"></a><span data-ttu-id="53ac2-166">Sitio de grupo Marketing de la campaña</span><span class="sxs-lookup"><span data-stu-id="53ac2-166">Campaign marketing team site</span></span>

<span data-ttu-id="53ac2-167">Para crear un sitio de grupo aislado de SharePoint Online de nivel confidencial para recursos de marketing de la campaña, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="53ac2-167">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>

1. <span data-ttu-id="53ac2-168">Abra un explorador en el equipo local e inicie sesión en el Centro de administración (<https://admin.microsoft.com>) con la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="53ac2-168">Using a browser on your local computer, sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="53ac2-169">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-169">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="53ac2-170">En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-170">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="53ac2-171">En la página **Crear un sitio**, haga clic en **Sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-171">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="53ac2-172">En **Team site name** (Nombre del sitio de grupo), escriba **Marketing de la campaña**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-172">In **Team site name**, type **Campaign marketing**.</span></span>

6. <span data-ttu-id="53ac2-173">En **Team site description** (Descripción del sitio de grupo), escriba **Sitio de SharePoint para marketing de la campaña (confidencial)**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-173">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>

7. <span data-ttu-id="53ac2-174">En **Configuración de privacidad**, seleccione **Private - only members can access this site** (Privado: solo los miembros tienen acceso a este sitio) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-174">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="53ac2-175">En el panel **Who do you want to add?** (Usuarios que quiere agregar), haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-175">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="53ac2-176">En la barra de herramientas de la nueva pestaña **Campaign marketing** (Marketing de la campaña) del explorador, haga clic en el icono de configuración y luego en **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-176">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="53ac2-177">En el panel **Permisos del sitio**, haga clic en **Advanced permissions settings** (Configuración de permisos avanzada).</span><span class="sxs-lookup"><span data-stu-id="53ac2-177">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="53ac2-178">En la nueva pestaña **Permisos** del explorador, haga clic en **Configuración de solicitud de acceso**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-178">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="53ac2-179">En el cuadro de diálogo **Configuración de solicitud de acceso**, desactive **Permitir que los miembros compartan el sitio y archivos y carpetas individuales** y **Permitir a los miembros invitar a otros al grupo de miembros del sitio**, escriba **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** en **Enviar todas las solicitudes de acceso** y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-179">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>

13. <span data-ttu-id="53ac2-180">Haga clic en **Marketing de la campaña-Miembros** en la lista.</span><span class="sxs-lookup"><span data-stu-id="53ac2-180">Click **Campaign marketing Members** in the list.</span></span>

14. <span data-ttu-id="53ac2-181">En la página **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-181">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="53ac2-182">En el cuadro de diálogo **Compartir**, escriba **Personal directivo y estratégico**, selecciónelo y haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-182">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="53ac2-183">Repita los pasos 14 y 15 para grupo **Personal de Análisis** y la cuenta de usuario **Regular1**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-183">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>

17. <span data-ttu-id="53ac2-184">Haga clic en el botón Atrás del explorador.</span><span class="sxs-lookup"><span data-stu-id="53ac2-184">Click the back button on your browser.</span></span>

18. <span data-ttu-id="53ac2-185">Haga clic en **Marketing de la campaña-Propietarios** en la lista.</span><span class="sxs-lookup"><span data-stu-id="53ac2-185">Click **Campaign marketing Owners** in the list.</span></span>

19. <span data-ttu-id="53ac2-186">En la página **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-186">On the **People and Groups** page, click **New**.</span></span>

20. <span data-ttu-id="53ac2-187">En el cuadro de diálogo **Compartir**, escriba **Personal de TI**, selecciónelo y haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-187">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

21. <span data-ttu-id="53ac2-188">Haga clic en el botón Atrás del explorador.</span><span class="sxs-lookup"><span data-stu-id="53ac2-188">Click the back button on your browser.</span></span>

22. <span data-ttu-id="53ac2-189">Cierre la pestaña **Personas y grupos** del explorador, haga clic en la pestaña **Marketing de la campaña-Inicio** del explorador y cierre el panel **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-189">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="53ac2-190">Estos son los resultados de la configuración de los permisos:</span><span class="sxs-lookup"><span data-stu-id="53ac2-190">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="53ac2-191">El grupo **Marketing de la campaña-Miembros** de SharePoint solo contiene el grupo **Personal directivo y estratégico** (que contiene las cuentas de usuario Candidate, ChiefOfStaff y Strategic1), el grupo **Marketing de la campaña** (que contiene la cuenta de usuario de administrador global), el grupo **Personal de Análisis** (que contiene la cuenta de usuario DataScientist1) y la cuenta de usuario **Regular1**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-191">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>

- <span data-ttu-id="53ac2-192">El grupo **Marketing de la campaña-Propietarios** de SharePoint solo contiene el grupo **Personal de TI** (que solo contiene las cuentas de usuario ITAdmin1 y ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="53ac2-192">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="53ac2-193">El grupo **Marketing de la campaña-Visitantes** de SharePoint no contiene grupos ni cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="53ac2-193">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="53ac2-194">Los miembros no pueden modificar los permisos de nivel de sitio (esto solo pueden hacerlo los miembros del grupo **Marketing de la campaña-Propietarios**).</span><span class="sxs-lookup"><span data-stu-id="53ac2-194">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>

- <span data-ttu-id="53ac2-195">Otras cuentas de usuario no pueden acceder al sitio ni a sus recursos, pero pueden pedir acceso al sitio, que enviará un correo electrónico al buzón de la cuenta de usuario ITAdmin1.</span><span class="sxs-lookup"><span data-stu-id="53ac2-195">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>

<span data-ttu-id="53ac2-196">Después, configure la carpeta de documentos del sitio de grupo Marketing de la campaña con la etiqueta Confidencial.</span><span class="sxs-lookup"><span data-stu-id="53ac2-196">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>

1. <span data-ttu-id="53ac2-197">En la pestaña **Marketing de la campaña-Inicio** del explorador, haga clic en **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-197">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="53ac2-198">Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-198">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="53ac2-199">En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).</span><span class="sxs-lookup"><span data-stu-id="53ac2-199">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="53ac2-200">En **Configuración-Aplicar etiqueta**, seleccione **Confidencial** y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-200">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>

<span data-ttu-id="53ac2-p103">Después, configure una directiva de prevención de pérdida de datos (DLP) que notifique a los usuarios cada vez que compartan un documento en un sitio de grupo de SharePoint Online con la etiqueta Confidencial fuera de la organización. Esta directiva DLP se aplicará a los recursos del sitio Marketing de la campaña.</span><span class="sxs-lookup"><span data-stu-id="53ac2-p103">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization. This DLP policy will apply to resources in the Campaign marketing site.</span></span>

1. <span data-ttu-id="53ac2-203">En la pestaña **Inicio de Microsoft Office** del explorador, haga clic en el icono **Seguridad y cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-203">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

2. <span data-ttu-id="53ac2-204">En la nueva pestaña **Seguridad y cumplimiento** del explorador, haga clic en **Prevención de pérdida de datos > Directiva**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-204">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

3. <span data-ttu-id="53ac2-205">En el panel **Prevención de pérdida de datos**, haga clic en **+ Crear una directiva**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-205">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

4. <span data-ttu-id="53ac2-206">En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-206">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

5. <span data-ttu-id="53ac2-207">En el panel **Escriba un nombre para la directiva**, escriba **Sitios de grupo de SharePoint Online de etiqueta Confidencial** en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-207">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

6. <span data-ttu-id="53ac2-208">En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-208">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

7. <span data-ttu-id="53ac2-209">En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange** y **Cuentas de OneDrive** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-209">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

8. <span data-ttu-id="53ac2-210">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-210">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

9. <span data-ttu-id="53ac2-211">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-211">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

10. <span data-ttu-id="53ac2-212">En el panel **Etiquetas**, haga clic en **+ Agregar**, seleccione la etiqueta **Confidencial**, haga clic en **Agregar** y luego en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-212">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>

11. <span data-ttu-id="53ac2-213">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-213">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

12. <span data-ttu-id="53ac2-214">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-214">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="53ac2-215">En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="53ac2-215">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

14. <span data-ttu-id="53ac2-216">En el panel **Customize policy tips and email notifications** (Personalizar sugerencias de directiva y notificaciones de correo electrónico), haga clic en **Customize the policy tip text** (Personalizar el texto de la sugerencia de directiva).</span><span class="sxs-lookup"><span data-stu-id="53ac2-216">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

15. <span data-ttu-id="53ac2-217">En el cuadro de texto, escriba o pegue lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="53ac2-217">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="53ac2-p104">Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en Archivo, Proteger documento y Cifrar con contraseña y, luego, especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.</span><span class="sxs-lookup"><span data-stu-id="53ac2-p104">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

16. <span data-ttu-id="53ac2-221">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-221">Click **OK**.</span></span>

17. <span data-ttu-id="53ac2-222">En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), desactive la casilla **Block people from sharing, and restrict access to shared content** (Evitar que los usuarios puedan compartir y restringir el acceso al contenido compartido) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-222">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>

18. <span data-ttu-id="53ac2-223">En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Yes, turn it on right away** (Sí, activarla inmediatamente) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-223">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

19. <span data-ttu-id="53ac2-224">En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-224">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

### <a name="campaign-strategy-team-site"></a><span data-ttu-id="53ac2-225">Sitio de grupo Estrategia de la campaña</span><span class="sxs-lookup"><span data-stu-id="53ac2-225">Campaign strategy team site</span></span>

<span data-ttu-id="53ac2-226">Para crear un sitio de grupo aislado de SharePoint Online de nivel extremadamente confidencial para recursos estratégicos de la campaña, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="53ac2-226">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>

1. <span data-ttu-id="53ac2-227">Si es necesario, use un explorador en el equipo local e inicie sesión en el Centro de administración (<https://admin.microsoft.com>) con la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="53ac2-227">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="53ac2-228">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-228">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="53ac2-229">En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-229">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="53ac2-230">En la página **Crear un sitio**, haga clic en **Sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-230">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="53ac2-231">En **Team site name** (Nombre del sitio de grupo), escriba **Estrategia de la campaña**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-231">In **Team site name**, type **Campaign strategy**.</span></span>

6. <span data-ttu-id="53ac2-232">En **Team site description** (Descripción de sitio de grupo), escriba **Sitio de SharePoint para la estrategia de la campaña (extremadamente confidencial)**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-232">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>

7. <span data-ttu-id="53ac2-233">En **Configuración de privacidad**, seleccione **Private - only members can access this site** (Privado: solo los miembros tienen acceso a este sitio) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-233">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="53ac2-234">En el panel **Who do you want to add?** (Usuarios que quiere agregar), haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-234">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="53ac2-235">En la barra de herramientas de la nueva pestaña **Estrategia de la campaña** del explorador, haga clic en el icono de configuración y luego en **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-235">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="53ac2-236">En el panel **Permisos del sitio**, haga clic en **Advanced permissions settings** (Configuración de permisos avanzada).</span><span class="sxs-lookup"><span data-stu-id="53ac2-236">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="53ac2-237">En la nueva pestaña **Permisos** del explorador, haga clic en **Configuración de solicitud de acceso**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-237">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="53ac2-238">En el cuadro de diálogo **Configuración de solicitud de acceso**, desactive **Permitir que los miembros compartan el sitio y archivos y carpetas individuales** y **Permitir a los miembros invitar a otros al grupo de miembros del sitio** (de forma que las tres casillas estén desactivadas) y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-238">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>

13. <span data-ttu-id="53ac2-239">Haga clic en **Estrategia de la campaña-Miembros** en la lista.</span><span class="sxs-lookup"><span data-stu-id="53ac2-239">Click **Campaign strategy Members** in the list.</span></span>

14. <span data-ttu-id="53ac2-240">En la página **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-240">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="53ac2-241">En el cuadro de diálogo **Compartir**, escriba **Personal directivo y estratégico**, selecciónelo y haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-241">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="53ac2-242">Haga clic en **Estrategia de la campaña-Propietarios** en la lista.</span><span class="sxs-lookup"><span data-stu-id="53ac2-242">Click **Campaign strategy Owners** in the list.</span></span>

17. <span data-ttu-id="53ac2-243">En la página **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-243">On the **People and Groups** page, click **New**.</span></span>

18. <span data-ttu-id="53ac2-244">En el cuadro de diálogo **Compartir**, escriba **Personal de TI**, selecciónelo y haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-244">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

19. <span data-ttu-id="53ac2-245">Haga clic en el botón Atrás del explorador.</span><span class="sxs-lookup"><span data-stu-id="53ac2-245">Click the back button on your browser.</span></span>

20. <span data-ttu-id="53ac2-246">Cierre la pestaña **Personas y grupos** del explorador, haga clic en la pestaña **-Inicio** del explorador y cierre el panel **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-246">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="53ac2-247">Estos son los resultados de la configuración de los permisos:</span><span class="sxs-lookup"><span data-stu-id="53ac2-247">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="53ac2-248">El grupo **Estrategia de la campaña-Miembros** de SharePoint solo contiene el grupo **Personal directivo y estratégico** [Directivos] \(que solo contiene las cuentas de usuario Candidate, ChiefOfStaff, and Strategic1) y el grupo **Estrategia de la campaña** (que solo contiene la cuenta de usuario de administrador global).</span><span class="sxs-lookup"><span data-stu-id="53ac2-248">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="53ac2-249">El grupo **Estrategia de la campaña-Propietarios** de SharePoint solo contiene el grupo **Personal de TI** (que solo contiene las cuentas de usuario ITAdmin1 y ITAdmin2).</span><span class="sxs-lookup"><span data-stu-id="53ac2-249">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="53ac2-250">El grupo **Estrategia de la campaña-Visitantes** de SharePoint no contiene grupos ni cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="53ac2-250">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="53ac2-251">Los miembros no pueden modificar los permisos de nivel de sitio (esto solo pueden hacerlo los miembros del grupo **Estrategia de la campaña-Propietarios**).</span><span class="sxs-lookup"><span data-stu-id="53ac2-251">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>

- <span data-ttu-id="53ac2-p105">Otras cuentas de usuario no tienen acceso al sitio o a sus recursos ni pedir acceso al sitio. Los permisos adicionales para el sitio deben ser asignados por el administrador global o por un miembro del grupo **Estrategia de la campaña-Propietarios**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-p105">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>

<span data-ttu-id="53ac2-254">Después, configure la carpeta de documentos del sitio de grupo Estrategia de la campaña con la etiqueta Extremadamente confidencial.</span><span class="sxs-lookup"><span data-stu-id="53ac2-254">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>

1. <span data-ttu-id="53ac2-255">En la pestaña **Estrategia de la campaña-Inicio** del explorador, haga clic en **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-255">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="53ac2-256">Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-256">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="53ac2-257">En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).</span><span class="sxs-lookup"><span data-stu-id="53ac2-257">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="53ac2-258">En **Configuración-Aplicar etiqueta**, seleccione **Extremadamente confidencial** y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-258">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>

<span data-ttu-id="53ac2-p106">Después, configure una directiva DLP que bloquee a los usuarios cuando compartan un documento en un sitio de grupo de SharePoint Online con la etiqueta Extremadamente confidencial fuera de la organización. Esta directiva DLP se aplicará a los recursos del sitio Estrategia de la campaña.</span><span class="sxs-lookup"><span data-stu-id="53ac2-p106">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization. This DLP policy will apply to resources in the Campaign strategy site.</span></span>

1. <span data-ttu-id="53ac2-261">Si fuera necesario, use un explorador en el equipo local e inicie sesión en el centro de administración (<https://admin.microsoft.com>) con una cuenta que tenga el rol Administrador de seguridad o Administrador de la compañía.</span><span class="sxs-lookup"><span data-stu-id="53ac2-261">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) with an account that has the Security Administrator or Company Administrator role.</span></span>

2. <span data-ttu-id="53ac2-262">En la pestaña **Inicio de Microsoft Office** del explorador, haga clic en el icono **Seguridad y cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-262">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

3. <span data-ttu-id="53ac2-263">En la nueva pestaña **Seguridad y cumplimiento** del explorador, haga clic en **Prevención de pérdida de datos > Directiva**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-263">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

4. <span data-ttu-id="53ac2-264">En el panel **Prevención de pérdida de datos**, haga clic en **+ Crear una directiva**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-264">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

5. <span data-ttu-id="53ac2-265">En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-265">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

6. <span data-ttu-id="53ac2-266">En el panel **Escriba un nombre para la directiva**, escriba **Sitios de grupo de SharePoint Online de etiqueta Extremadamente confidencial** en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-266">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

7. <span data-ttu-id="53ac2-267">En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-267">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

8. <span data-ttu-id="53ac2-268">En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange** y **Cuentas de OneDrive** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-268">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

9. <span data-ttu-id="53ac2-269">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-269">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

10. <span data-ttu-id="53ac2-270">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-270">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

11. <span data-ttu-id="53ac2-271">En el panel **Etiquetas**, haga clic en **+ Agregar**, seleccione la etiqueta **Extremadamente confidencial**, haga clic en **Agregar** y luego en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-271">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>

12. <span data-ttu-id="53ac2-272">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-272">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

13. <span data-ttu-id="53ac2-273">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-273">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

14. <span data-ttu-id="53ac2-274">En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="53ac2-274">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

15. <span data-ttu-id="53ac2-275">En el panel **Customize policy tips and email notifications** (Personalizar sugerencias de directiva y notificaciones de correo electrónico), haga clic en **Customize the policy tip text** (Personalizar el texto de la sugerencia de directiva).</span><span class="sxs-lookup"><span data-stu-id="53ac2-275">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

16. <span data-ttu-id="53ac2-276">En el cuadro de texto, escriba o pegue lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="53ac2-276">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="53ac2-p107">Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en Archivo, Proteger documento y Cifrar con contraseña y, luego, especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.</span><span class="sxs-lookup"><span data-stu-id="53ac2-p107">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

17. <span data-ttu-id="53ac2-280">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-280">Click **OK**.</span></span>

18. <span data-ttu-id="53ac2-281">En el panel **What do you want to do if we detect sensitive info?** (¿Qué desea hacer si se detecta información confidencial?), seleccione **Require a business justification to override** (Exigir una justificación de empresa para invalidar) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-281">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>

19. <span data-ttu-id="53ac2-282">En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Yes, turn it on right away** (Sí, activarla inmediatamente) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-282">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

20. <span data-ttu-id="53ac2-283">En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-283">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="53ac2-284">Siga las instrucciones de [Activate Azure RMS with the Microsoft 365 admin center](/information-protection/deploy-use/activate-office365) (Activación de Azure RMS con el Centro de administración de Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="53ac2-284">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](/information-protection/deploy-use/activate-office365).</span></span>

<span data-ttu-id="53ac2-285">Después, siga estos pasos para configurar Azure Information Protection con una nueva directiva con ámbito y la subetiqueta de protección y permisos:</span><span class="sxs-lookup"><span data-stu-id="53ac2-285">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>

1. <span data-ttu-id="53ac2-p108">Inicie sesión en el Centro de administración con una cuenta que tenga el rol Administrador de seguridad o Administrador de la compañía. Para obtener ayuda, vea [Dónde iniciar sesión en Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="53ac2-p108">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role. For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="53ac2-288">En una pestaña independiente del explorador, vaya a Azure Portal (<https://portal.azure.com>).</span><span class="sxs-lookup"><span data-stu-id="53ac2-288">In a separate tab of your browser, go to the Azure portal (<https://portal.azure.com>).</span></span>

3. <span data-ttu-id="53ac2-289">En el panel de Búsqueda, escriba **información**, y luego haga clic en **Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-289">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

4. <span data-ttu-id="53ac2-290">Haga clic en **Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-290">Click **Labels**.</span></span>

5. <span data-ttu-id="53ac2-291">Haga clic con el botón derecho en la etiqueta **Extremadamente confidencial** y después seleccione **Agregar una subetiqueta**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-291">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>

6. <span data-ttu-id="53ac2-292">Escriba **Estrategia de la campaña** en **Nombre** y **Etiqueta para los documentos del sitio de grupo de estrategia de la campaña** en **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-292">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>

7. <span data-ttu-id="53ac2-293">En **Establecer permisos para documentos y correos electrónicos que contengan esta etiqueta**, haga clic en **Proteger**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-293">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>

8. <span data-ttu-id="53ac2-294">En la sección **Protección**, haga clic en **Azure (clave de nube)**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-294">In the **Protection** section, click **Azure (cloud key)**.</span></span>

9. <span data-ttu-id="53ac2-295">En la hoja **Protección**, en **Configuración de protección**, haga clic en **+ Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-295">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>

10. <span data-ttu-id="53ac2-296">En la hoja **Agregar permisos**, en **Especificar usuarios y grupos**, haga clic en **+ Examinar directorio**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-296">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>

11. <span data-ttu-id="53ac2-297">En el panel **Usuarios y grupos de AAD**, seleccione **Personal directivo y estratégico** y haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-297">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>

12. <span data-ttu-id="53ac2-298">En **Seleccionar permisos del conjunto predefinido o personalizado**, haga clic en **Personalizar** y después active las casillas **Ver derechos**, **Editar contenido**, **Guardar**, **Responder** y **Responder a todos**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-298">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>

13. <span data-ttu-id="53ac2-299">Haga clic en **Aceptar** dos veces.</span><span class="sxs-lookup"><span data-stu-id="53ac2-299">Click **OK** twice.</span></span>

14. <span data-ttu-id="53ac2-300">En la hoja **Subetiqueta**, haga clic en **Guardar** y, después, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-300">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

15. <span data-ttu-id="53ac2-301">En la hoja **Azure Information Protection**, haga clic en **Directivas > + Agregar una directiva**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-301">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>

16. <span data-ttu-id="53ac2-302">Escriba **Estrategia de la campaña** en **Nombre** y **Documentos del sitio de grupo de estrategia de la campaña** en **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-302">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>

17. <span data-ttu-id="53ac2-303">Haga clic en **Seleccionar a qué usuarios o grupos se aplica esta directiva > Usuarios o grupos** y seleccione **Personal directivo y estratégico**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-303">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>

18. <span data-ttu-id="53ac2-304">Haga clic en **Seleccionar \> Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-304">Click **Select \> OK**.</span></span>

19. <span data-ttu-id="53ac2-p109">Haga clic en **Agregar o quitar etiquetas**. En el panel **Directiva: Agregar o quitar etiquetas**, seleccione **Estrategia de la campaña** y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-p109">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>

20. <span data-ttu-id="53ac2-307">Haga clic en **Guardar** y después en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="53ac2-307">Click **Save**, and then click **OK**.</span></span>

<span data-ttu-id="53ac2-308">Ahora ya puede crear documentos en estos cuatro sitios y probar el acceso a ellos con diferentes cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="53ac2-308">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span>

<span data-ttu-id="53ac2-309">Para proteger un documento con Azure Information Protection y esta nueva etiqueta, debe [instalar el cliente de Azure Information Protection](/information-protection/rms-client/install-client-app) en un equipo de prueba, instalar Office desde el Centro de administración y luego iniciar sesión desde Microsoft Word con una cuenta del grupo **Personal directivo y estratégico** de la suscripción de evaluación.</span><span class="sxs-lookup"><span data-stu-id="53ac2-309">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>

## <a name="see-also"></a><span data-ttu-id="53ac2-310">Vea también</span><span class="sxs-lookup"><span data-stu-id="53ac2-310">See Also</span></span>

[<span data-ttu-id="53ac2-311">Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles</span><span class="sxs-lookup"><span data-stu-id="53ac2-311">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="53ac2-312">Configurar grupos y usuarios en un entorno de desarrollo y prueba de campaña política</span><span class="sxs-lookup"><span data-stu-id="53ac2-312">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="53ac2-313">Guías del entorno de pruebas de adopción de la nube (TLG)</span><span class="sxs-lookup"><span data-stu-id="53ac2-313">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="53ac2-314">Centro de soluciones y arquitectura de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="53ac2-314">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)