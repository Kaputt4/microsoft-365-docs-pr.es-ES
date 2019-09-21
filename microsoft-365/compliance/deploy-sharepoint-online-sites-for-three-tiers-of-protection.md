---
title: Implementar sitios de SharePoint Online con tres niveles de protección
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 'Resumen: Cree y configure sitios de grupo de SharePoint Online con distintos niveles de protección de la información.'
ms.openlocfilehash: 2ddf3de7180d384c387bdc335afda6214508e3c5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37070727"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a><span data-ttu-id="0ed73-103">Implementar sitios de SharePoint Online con tres niveles de protección</span><span class="sxs-lookup"><span data-stu-id="0ed73-103">Deploy SharePoint Online sites for three tiers of protection</span></span>

 <span data-ttu-id="0ed73-104">**Resumen:** Cree y configure sitios de grupo de SharePoint Online con distintos niveles de protección de la información.</span><span class="sxs-lookup"><span data-stu-id="0ed73-104">**Summary:** Create and configure SharePoint Online team sites for various levels of information protection.</span></span>
  
<span data-ttu-id="0ed73-p101">Siga los pasos de este artículo para diseñar e implementar sitios de grupo de base de referencia, confidenciales y extremadamente confidenciales de SharePoint Online. Para más información sobre estos tres niveles de protección, vea [Proteger sitios y archivos de SharePoint Online](/security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="0ed73-p101">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](/security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="baseline-sharepoint-online-team-sites"></a><span data-ttu-id="0ed73-107">Sitios de grupo de base de referencia de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0ed73-107">Baseline SharePoint Online team sites</span></span>

<span data-ttu-id="0ed73-p102">La protección de base de referencia incluye sitios de grupo públicos y privados. Todo el personal de la organización puede acceder a los sitios de grupo públicos. Solo los miembros del grupo de Office 365 asociado al sitio de grupo pueden detectar sitios privados y acceder a ellos. Ambos tipos de sitios de grupo permiten a los miembros compartir el sitio con otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="0ed73-p102">Baseline protection includes both public and private team sites. Public team sites can be discovered and accessed by anybody in the organization. Private sites can only be discovered and accessed by members of the Office 365 group associated with the team site. Both of these types of team sites allow members to share the site with others.</span></span>
  
### <a name="public"></a><span data-ttu-id="0ed73-112">Público</span><span class="sxs-lookup"><span data-stu-id="0ed73-112">Public</span></span>

<span data-ttu-id="0ed73-113">Para crear un sitio de grupo de SharePoint Online de línea base con acceso y permisos públicos, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ed73-113">To create a baseline SharePoint Online team site with public access and permissions, do the following:</span></span>
  
1. <span data-ttu-id="0ed73-114">Inicie sesión en el centro de administración con una cuenta que también se vaya a usar para administrar el sitio de grupo de SharePoint Online (un administrador de SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="0ed73-114">Sign in to the admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="0ed73-115">Para obtener ayuda, vea [Dónde iniciar sesión en Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="0ed73-115">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="0ed73-116">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-116">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="0ed73-117">En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-117">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="0ed73-118">En la página **Crear un sitio**, haga clic en **Sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-118">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="0ed73-119">En **Nombre del sitio**, escriba un nombre para el sitio de grupo público.</span><span class="sxs-lookup"><span data-stu-id="0ed73-119">In **Site name**, type a name for the public team site.</span></span> 
    
6. <span data-ttu-id="0ed73-120">En **Team site description** (Descripción del sitio de grupo), escriba una descripción de la finalidad del sitio.</span><span class="sxs-lookup"><span data-stu-id="0ed73-120">In **Team site description**, type a description of the purpose of the site.</span></span>
    
7. <span data-ttu-id="0ed73-121">En **Configuración de privacidad**, seleccione **Public – anyone in the organization can access this site** (Público: cualquier usuario de la organización tiene acceso a este sitio) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-121">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="0ed73-122">En el panel **Who do you want to add?** (Usuarios que quiere agregar), haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-122">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="0ed73-123">Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="0ed73-123">Here is your resulting configuration.</span></span>
  
![Protección de nivel de línea base de un sitio de grupo de SharePoint Online público.](media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a><span data-ttu-id="0ed73-125">Privado</span><span class="sxs-lookup"><span data-stu-id="0ed73-125">Private</span></span>

<span data-ttu-id="0ed73-126">Para crear un sitio de grupo de SharePoint Online de línea base con acceso y permisos privados, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ed73-126">To create a baseline SharePoint Online team site with private access and permissions, do the following:</span></span>
  
1. <span data-ttu-id="0ed73-127">Inicie sesión en el centro de administración con una cuenta que también se vaya a usar para administrar el sitio de grupo de SharePoint Online (un administrador de SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="0ed73-127">Sign in to the admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="0ed73-128">Para obtener ayuda, vea [Dónde iniciar sesión en Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="0ed73-128">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="0ed73-129">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-129">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="0ed73-130">En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-130">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="0ed73-131">En la página **Crear un sitio**, haga clic en **Sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-131">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="0ed73-132">En **Nombre del sitio**, escriba un nombre para el sitio de grupo privado.</span><span class="sxs-lookup"><span data-stu-id="0ed73-132">In **Site name**, type a name for the private team site.</span></span> 
    
6. <span data-ttu-id="0ed73-133">En **Team site description** (Descripción del sitio de grupo), escriba una descripción de la finalidad del sitio.</span><span class="sxs-lookup"><span data-stu-id="0ed73-133">In **Team site description,** type a description of the purpose of the site.</span></span>
    
7. <span data-ttu-id="0ed73-134">En **Configuración de privacidad**, seleccione **Private - only members can access this site** (Privado: solo los miembros tienen acceso a este sitio) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-134">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="0ed73-135">En el panel de **Who do you want to add?** (Usuarios que quiere agregar), en **Agregar miembros**, escriba los nombres de cuentas de usuario que tengan acceso a este sitio de grupo privado.</span><span class="sxs-lookup"><span data-stu-id="0ed73-135">On the **Who do you want to add?** pane, in **Add members**, type the names of user accounts that have access to this private team site.</span></span>
    
9. <span data-ttu-id="0ed73-136">Cuando haya terminado de agregar el conjunto inicial de miembros al sitio, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-136">When you are done adding the initial set of members to the site, click **Finish**</span></span>
    
<span data-ttu-id="0ed73-137">Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="0ed73-137">Here is your resulting configuration.</span></span>
  
![Protección de nivel de línea base de un sitio de grupo de SharePoint Online privado.](media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a><span data-ttu-id="0ed73-139">Sitios de grupo confidenciales de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0ed73-139">Sensitive SharePoint Online team sites</span></span>

<span data-ttu-id="0ed73-140">Un sitio de grupo de SharePoint Online confidencial es un sitio de grupo aislado, lo que significa que los permisos se controlan mediante la pertenencia a grupos de SharePoint en lugar de la pertenencia al grupo de Office 365 asociado al sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="0ed73-140">A sensitive SharePoint Online team site is an isolated team site, which means that permissions are controlled through membership in SharePoint groups instead of membership in the Office 365 group associated with the team site.</span></span>
  
<span data-ttu-id="0ed73-141">Para crear un sitio de grupo aislado, siga estos dos pasos principales.</span><span class="sxs-lookup"><span data-stu-id="0ed73-141">To create an isolated team site, there are two main steps.</span></span>
  
### <a name="step-1-design-your-isolated-site"></a><span data-ttu-id="0ed73-142">Paso 1: Diseñar el sitio aislado</span><span class="sxs-lookup"><span data-stu-id="0ed73-142">Step 1: Design your isolated site</span></span>

<span data-ttu-id="0ed73-143">Para diseñar el sitio de grupo aislado, debe determinar:</span><span class="sxs-lookup"><span data-stu-id="0ed73-143">To design your isolated team site, you need to determine:</span></span>
  
- <span data-ttu-id="0ed73-144">Los grupos y niveles de permisos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0ed73-144">Your SharePoint groups and permission levels.</span></span>
    
- <span data-ttu-id="0ed73-145">El conjunto de grupos de acceso que van a ser miembros de los grupos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0ed73-145">The set of access groups that will be members of your SharePoint groups.</span></span>
    
     <span data-ttu-id="0ed73-146">El conjunto recomendado de grupos de acceso es uno para miembros del sitio, otro para lectores del sitio y el último para administradores del sitio.</span><span class="sxs-lookup"><span data-stu-id="0ed73-146">The recommended set of access groups is one for site members, one for site viewers, and one for site administrators.</span></span>
    
- <span data-ttu-id="0ed73-147">Si va a usar grupos anidados dentro de los grupos de acceso.</span><span class="sxs-lookup"><span data-stu-id="0ed73-147">Whether you will use nested groups within your access groups.</span></span>
    
<span data-ttu-id="0ed73-148">Por ejemplo, la estructura del grupo y los niveles de permisos recomendados tienen este aspecto:</span><span class="sxs-lookup"><span data-stu-id="0ed73-148">For example, the recommended group structure and permission levels look like this:</span></span>
  
|<span data-ttu-id="0ed73-149">**Grupo de SharePoint**</span><span class="sxs-lookup"><span data-stu-id="0ed73-149">**SharePoint group**</span></span>|<span data-ttu-id="0ed73-150">**Nivel de permisos**</span><span class="sxs-lookup"><span data-stu-id="0ed73-150">**Permission level**</span></span>|<span data-ttu-id="0ed73-151">**Grupo de acceso (ejemplos)**</span><span class="sxs-lookup"><span data-stu-id="0ed73-151">**Access group (examples)**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0ed73-152">Miembros de [nombre del sitio]</span><span class="sxs-lookup"><span data-stu-id="0ed73-152">[site name] Members</span></span>  <br/> |<span data-ttu-id="0ed73-153">Editar</span><span class="sxs-lookup"><span data-stu-id="0ed73-153">Edit</span></span>  <br/> |<span data-ttu-id="0ed73-154">Miembros de [nombre del sitio]</span><span class="sxs-lookup"><span data-stu-id="0ed73-154">[site name] Members</span></span>  <br/> |
|<span data-ttu-id="0ed73-155">Visitantes de [nombre del sitio]</span><span class="sxs-lookup"><span data-stu-id="0ed73-155">[site name] Visitors</span></span>  <br/> |<span data-ttu-id="0ed73-156">Lectura</span><span class="sxs-lookup"><span data-stu-id="0ed73-156">Read</span></span>  <br/> |<span data-ttu-id="0ed73-157">Lectores de [nombre del sitio]</span><span class="sxs-lookup"><span data-stu-id="0ed73-157">[site name] Viewers</span></span>  <br/> |
|<span data-ttu-id="0ed73-158">Propietarios de [nombre del sitio]</span><span class="sxs-lookup"><span data-stu-id="0ed73-158">[site name] Owners</span></span>  <br/> |<span data-ttu-id="0ed73-159">Control total</span><span class="sxs-lookup"><span data-stu-id="0ed73-159">Full control</span></span>  <br/> |<span data-ttu-id="0ed73-160">Administradores de [nombre del sitio]</span><span class="sxs-lookup"><span data-stu-id="0ed73-160">[site name] Admins</span></span>  <br/> |
   
<span data-ttu-id="0ed73-p105">Los niveles de permisos y los grupos de SharePoint se crean de forma predeterminada para un sitio de grupo. Debe determinar los nombres de los grupos de acceso.</span><span class="sxs-lookup"><span data-stu-id="0ed73-p105">The SharePoint groups and permission levels are created by default for a team site. You need to determine the names of your access groups.</span></span>
  
<span data-ttu-id="0ed73-163">Para obtener los detalles del proceso de diseño, vea [Diseñar un sitio de grupo SharePoint Online aislado](/security/office-365-security/design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="0ed73-163">For the details of the design process, see [Design an isolated SharePoint Online team site](/security/office-365-security/design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
### <a name="step-2-deploy-your-isolated-site"></a><span data-ttu-id="0ed73-164">Paso 2: Implementar el sitio aislado</span><span class="sxs-lookup"><span data-stu-id="0ed73-164">Step 2: Deploy your isolated site</span></span>

<span data-ttu-id="0ed73-165">Para implementar el sitio aislado, primero debe:</span><span class="sxs-lookup"><span data-stu-id="0ed73-165">To deploy your isolated site, you first need to:</span></span>
  
- <span data-ttu-id="0ed73-166">Determinar las cuentas de usuario y los grupos que va a agregar a cada uno de los grupos de acceso.</span><span class="sxs-lookup"><span data-stu-id="0ed73-166">Determine the user accounts and groups to add to each of your access groups.</span></span>
    
- <span data-ttu-id="0ed73-167">Crear los grupos de acceso y agregar a miembros de grupos y usuarios.</span><span class="sxs-lookup"><span data-stu-id="0ed73-167">Create the access groups and add the user and group members.</span></span>
    
<span data-ttu-id="0ed73-168">Para obtener los pasos detallados, vea la **fase 1** de [Implementar un sitio de grupo aislado de SharePoint Online](/security/office-365-security/design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="0ed73-168">For the detailed steps, see **Phase 1** of [Deploy an isolated SharePoint Online team site](/security/office-365-security/design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
<span data-ttu-id="0ed73-169">Luego cree el sitio de grupo de SharePoint Online con estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0ed73-169">Next, you create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="0ed73-170">Inicie sesión en el centro de administración con una cuenta que también se vaya a usar para administrar el sitio de grupo de SharePoint Online (un administrador de SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="0ed73-170">Sign in to the admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="0ed73-171">Para obtener ayuda, vea [Dónde iniciar sesión en Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="0ed73-171">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="0ed73-172">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-172">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="0ed73-173">En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-173">In the new **SharePoint** tab of your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="0ed73-174">En la página **Crear un sitio**, haga clic en **Sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-174">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="0ed73-175">En **Nombre del sitio**, escriba un nombre para el sitio de grupo privado.</span><span class="sxs-lookup"><span data-stu-id="0ed73-175">In **Site name**, type a name for the private team site.</span></span>
    
6. <span data-ttu-id="0ed73-176">En **Team site description** (Descripción del sitio de grupo), escriba una descripción opcional.</span><span class="sxs-lookup"><span data-stu-id="0ed73-176">In **Team site description**, type an optional description.</span></span>
    
7. <span data-ttu-id="0ed73-177">En **Configuración de privacidad**, seleccione **Private - only members can access this site** (Privado: solo los miembros tienen acceso a este sitio) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-177">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="0ed73-178">En el panel **Who do you want to add?** (Usuarios que quiere agregar), haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-178">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="0ed73-179">Después, desde el nuevo sitio de grupo de SharePoint Online, configure los permisos con estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0ed73-179">Next, from the new SharePoint Online team site, configure permissions with these steps.</span></span>
  
1. <span data-ttu-id="0ed73-180">Determine el nombre principal de usuario (UPN) del administrador de TI o de otra persona que vaya a ser responsable de responder a las solicitudes de acceso al sitio y de dirigirlas (belindan@contoso.com es un ejemplo de UPN).</span><span class="sxs-lookup"><span data-stu-id="0ed73-180">Determine the User Principal Name (UPN) of the IT administrator or other person who will be responsible for responding to and addressing requests for access to the site (belindan@contoso.com is an example of a UPN).</span></span> 
    
2. <span data-ttu-id="0ed73-181">En la barra de herramientas, haga clic en el icono de configuración y, luego, en **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-181">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
3. <span data-ttu-id="0ed73-182">En el panel **Permisos del sitio**, haga clic en **Advanced permissions settings** (Configuración de permisos avanzada).</span><span class="sxs-lookup"><span data-stu-id="0ed73-182">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
4. <span data-ttu-id="0ed73-183">En la nueva pestaña **Permisos** del explorador, haga clic en **Configuración de solicitud de acceso**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-183">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
    
5. <span data-ttu-id="0ed73-184">En el cuadro de diálogo **Configuración de solicitud de acceso**:</span><span class="sxs-lookup"><span data-stu-id="0ed73-184">In the **Access Requests Settings** dialog box:</span></span>
    
  - <span data-ttu-id="0ed73-185">Desactive las casillas de verificación **Permitir que los miembros compartan el sitio y archivos y carpetas individuales** y **Permitir a los miembros invitar a otros al grupo de miembros del sitio**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-185">Clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes.</span></span>
    
  - <span data-ttu-id="0ed73-186">Escriba el UPN del administrador de TI del paso 1 en **Enviar todas las solicitudes de acceso**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-186">Type the UPN of your IT administrator from step 1 in **Send all requests for access**.</span></span>
    
  - <span data-ttu-id="0ed73-187">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-187">Click **OK**.</span></span>
    
6. <span data-ttu-id="0ed73-188">En la pestaña **Permisos** del explorador, haga clic en **Miembros de [nombre del sitio]** en la lista.</span><span class="sxs-lookup"><span data-stu-id="0ed73-188">On the **Permissions** tab of your browser, click **[site name] Members** in the list.</span></span>
    
7. <span data-ttu-id="0ed73-189">En **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-189">In **People and Groups**, click **New**.</span></span>
    
8. <span data-ttu-id="0ed73-190">En el cuadro de diálogo **Compartir**, escriba el nombre del grupo de acceso de miembros de sitio para este sitio, selecciónelo y luego haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-190">In the **Share** dialog box, type the name of your site members access group for this site, select it, and then click **Share**.</span></span>
    
9. <span data-ttu-id="0ed73-191">Haga clic en el botón Atrás del explorador.</span><span class="sxs-lookup"><span data-stu-id="0ed73-191">Click the back button on your browser.</span></span>
    
10. <span data-ttu-id="0ed73-192">Haga clic en **Propietarios de [nombre del sitio]** en la lista.</span><span class="sxs-lookup"><span data-stu-id="0ed73-192">Click **[site name] Owners** in the list.</span></span>
    
11. <span data-ttu-id="0ed73-193">En **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-193">In **People and Groups**, click **New**.</span></span>
    
12. <span data-ttu-id="0ed73-194">En el cuadro de diálogo **Compartir**, escriba el nombre del grupo de acceso de administradores de sitio para este sitio, selecciónelo y luego haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-194">In the **Share** dialog box, type the name of the site administrators access group for this site, select it, and then click **Share**.</span></span>
    
13. <span data-ttu-id="0ed73-195">Haga clic en el botón Atrás del explorador.</span><span class="sxs-lookup"><span data-stu-id="0ed73-195">Click the back button on your browser.</span></span>
    
14. <span data-ttu-id="0ed73-196">Haga clic en **Visitantes de [nombre del sitio]** en la lista.</span><span class="sxs-lookup"><span data-stu-id="0ed73-196">Click **[site name] Visitors** in the list.</span></span>
    
15. <span data-ttu-id="0ed73-197">En **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-197">In **People and Groups**, click **New**.</span></span>
    
16. <span data-ttu-id="0ed73-198">En el cuadro de diálogo **Compartir**, escriba el nombre del grupo de acceso de lectores de sitio para este sitio, selecciónelo y luego haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-198">In the **Share** dialog box, type the name of the site viewers access group for this site, select it, and then click **Share**.</span></span>
    
17. <span data-ttu-id="0ed73-199">Cierre la pestaña **Permisos** del explorador.</span><span class="sxs-lookup"><span data-stu-id="0ed73-199">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="0ed73-200">Los resultados de esta configuración de permisos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0ed73-200">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="0ed73-201">El grupo **Propietarios de [nombre del sitio]** de SharePoint contiene el grupo de acceso de administradores de sitio, en el que todos los miembros tienen el nivel de permisos **Control total**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-201">The **[site name] Owners** SharePoint group contains the site administrators access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="0ed73-202">El grupo de SharePoint **Miembros de [nombre del sitio]** contiene el grupo de acceso de miembros de sitio, en el que todos los miembros tienen el nivel de permisos **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-202">The **[site name] Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="0ed73-203">El grupo de SharePoint **Visitantes de [nombre del sitio]** contiene el grupo de acceso de lectores de sitio, en el que todos los miembros tienen el nivel de permisos **Leer**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-203">The **[site name] Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="0ed73-204">La capacidad de los miembros de invitar a otros miembros está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="0ed73-204">The ability for members to invite other members is disabled.</span></span>
    
- <span data-ttu-id="0ed73-205">La capacidad de los no miembros de solicitar acceso está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="0ed73-205">The ability for non-members to request access is enabled.</span></span>
    
<span data-ttu-id="0ed73-206">Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="0ed73-206">Here is your resulting configuration.</span></span>
  
![Protección de nivel confidencial de un sitio de grupo aislado de SharePoint Online.](media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
<span data-ttu-id="0ed73-208">Los miembros del sitio, a través de la pertenencia a grupos en uno de los grupos de acceso, ahora pueden colaborar de forma segura en los recursos del sitio.</span><span class="sxs-lookup"><span data-stu-id="0ed73-208">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a><span data-ttu-id="0ed73-209">Sitios de grupo de SharePoint Online extremadamente confidenciales</span><span class="sxs-lookup"><span data-stu-id="0ed73-209">Highly confidential SharePoint Online team sites</span></span>

<span data-ttu-id="0ed73-210">Un sitio de grupo de SharePoint Online extremadamente confidencial es un sitio de grupo aislado, lo que significa que los permisos se controlan mediante la pertenencia a grupos de SharePoint en lugar de la pertenencia al grupo de Office 365 asociado al sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="0ed73-210">A highly confidential SharePoint Online team site is an isolated team site, which means that permissions are controlled through membership in SharePoint groups instead of membership in the Office 365 group associated with the team site.</span></span>
  
<span data-ttu-id="0ed73-211">Para crear un sitio de grupo aislado para información y colaboración extremadamente confidenciales, hay dos pasos principales.</span><span class="sxs-lookup"><span data-stu-id="0ed73-211">To create an isolated team site for highly confidential information and collaboration, there are two main steps.</span></span>
  
### <a name="step-1-design-your-isolated-site"></a><span data-ttu-id="0ed73-212">Paso 1: Diseñar el sitio aislado</span><span class="sxs-lookup"><span data-stu-id="0ed73-212">Step 1: Design your isolated site</span></span>

<span data-ttu-id="0ed73-213">Para diseñar el sitio de grupo aislado, debe determinar:</span><span class="sxs-lookup"><span data-stu-id="0ed73-213">To design your isolated team site, you need to determine:</span></span>
  
- <span data-ttu-id="0ed73-214">Los grupos y niveles de permisos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0ed73-214">Your SharePoint groups and permission levels.</span></span>
    
- <span data-ttu-id="0ed73-215">El conjunto de grupos de acceso que van a ser miembros de los grupos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0ed73-215">The set of access groups that will be members of your SharePoint groups.</span></span>
    
     <span data-ttu-id="0ed73-216">El conjunto recomendado de grupos de acceso es uno para miembros del sitio, otro para lectores del sitio y el último para administradores del sitio.</span><span class="sxs-lookup"><span data-stu-id="0ed73-216">The recommended set of access groups is one for site members, one for site viewers, and one for site administrators.</span></span>
    
- <span data-ttu-id="0ed73-217">Si va a usar grupos anidados dentro de los grupos de acceso.</span><span class="sxs-lookup"><span data-stu-id="0ed73-217">Whether you will use nested groups within your access groups.</span></span>
    
<span data-ttu-id="0ed73-218">Por ejemplo, la estructura del grupo y los niveles de permisos recomendados tienen este aspecto:</span><span class="sxs-lookup"><span data-stu-id="0ed73-218">For example, the recommended group structure and permission levels look like this:</span></span>
  
|<span data-ttu-id="0ed73-219">**Grupo de SharePoint**</span><span class="sxs-lookup"><span data-stu-id="0ed73-219">**SharePoint group**</span></span>|<span data-ttu-id="0ed73-220">**Nivel de permisos**</span><span class="sxs-lookup"><span data-stu-id="0ed73-220">**Permission level**</span></span>|<span data-ttu-id="0ed73-221">**Grupo de acceso (ejemplos)**</span><span class="sxs-lookup"><span data-stu-id="0ed73-221">**Access group (examples)**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0ed73-222">Miembros de [nombre del sitio]</span><span class="sxs-lookup"><span data-stu-id="0ed73-222">[site name] Members</span></span>  <br/> |<span data-ttu-id="0ed73-223">Editar</span><span class="sxs-lookup"><span data-stu-id="0ed73-223">Edit</span></span>  <br/> |<span data-ttu-id="0ed73-224">Miembros de [nombre del sitio]</span><span class="sxs-lookup"><span data-stu-id="0ed73-224">[site name] Members</span></span>  <br/> |
|<span data-ttu-id="0ed73-225">Visitantes de [nombre del sitio]</span><span class="sxs-lookup"><span data-stu-id="0ed73-225">[site name] Visitors</span></span>  <br/> |<span data-ttu-id="0ed73-226">Lectura</span><span class="sxs-lookup"><span data-stu-id="0ed73-226">Read</span></span>  <br/> |<span data-ttu-id="0ed73-227">Lectores de [nombre del sitio]</span><span class="sxs-lookup"><span data-stu-id="0ed73-227">[site name] Viewers</span></span>  <br/> |
|<span data-ttu-id="0ed73-228">Propietarios de [nombre del sitio]</span><span class="sxs-lookup"><span data-stu-id="0ed73-228">[site name] Owners</span></span>  <br/> |<span data-ttu-id="0ed73-229">Control total</span><span class="sxs-lookup"><span data-stu-id="0ed73-229">Full control</span></span>  <br/> |<span data-ttu-id="0ed73-230">Administradores de [nombre del sitio]</span><span class="sxs-lookup"><span data-stu-id="0ed73-230">[site name] Admins</span></span>  <br/> |
   
<span data-ttu-id="0ed73-p107">Los niveles de permisos y los grupos de SharePoint se crean de forma predeterminada para un sitio de grupo. Debe determinar los nombres de los grupos de acceso.</span><span class="sxs-lookup"><span data-stu-id="0ed73-p107">The SharePoint groups and permission levels are created by default for a team site. You need to determine the names of your access groups.</span></span>
  
<span data-ttu-id="0ed73-233">Para obtener los detalles del proceso de diseño, vea [Diseñar un sitio de grupo SharePoint Online aislado](/security/office-365-security/design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="0ed73-233">For the details of the design process, see [Design an isolated SharePoint Online team site](/security/office-365-security/design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
### <a name="step-2-deploy-your-isolated-site"></a><span data-ttu-id="0ed73-234">Paso 2: Implementar el sitio aislado</span><span class="sxs-lookup"><span data-stu-id="0ed73-234">Step 2: Deploy your isolated site</span></span>

<span data-ttu-id="0ed73-235">Para implementar el sitio aislado, primero debe:</span><span class="sxs-lookup"><span data-stu-id="0ed73-235">To deploy your isolated site, you first need to:</span></span>
  
- <span data-ttu-id="0ed73-236">Determinar los miembros de grupos y usuarios de cada uno de los grupos de acceso</span><span class="sxs-lookup"><span data-stu-id="0ed73-236">Determine the user and group members of each of your access groups</span></span>
    
- <span data-ttu-id="0ed73-237">Crear los grupos de acceso y agregar los miembros de grupos y usuarios</span><span class="sxs-lookup"><span data-stu-id="0ed73-237">Create the access groups and add the user and group members</span></span>
    
- <span data-ttu-id="0ed73-238">Crear un sitio de grupo aislado que use los grupos de acceso.</span><span class="sxs-lookup"><span data-stu-id="0ed73-238">Create an isolated team site that uses your access groups</span></span>
    
<span data-ttu-id="0ed73-239">Para obtener los pasos detallados, vea [Implementar un sitio de grupo aislado de SharePoint Online](/security/office-365-security/design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="0ed73-239">For the detailed steps, see [Deploy an isolated SharePoint Online team site](/security/office-365-security/design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
<span data-ttu-id="0ed73-240">Los resultados de la configuración de permisos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0ed73-240">The results of the permission settings are:</span></span>
  
- <span data-ttu-id="0ed73-241">El grupo **Propietarios de [nombre del sitio]** de SharePoint contiene el grupo de acceso de administradores de sitio, en el que todos los miembros tienen el nivel de permisos **Control total**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-241">The **[site name] Owners** SharePoint group contains the site administrators access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="0ed73-242">El grupo de SharePoint **Miembros de [nombre del sitio]** contiene el grupo de acceso de miembros de sitio, en el que todos los miembros tienen el nivel de permisos **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-242">The **[site name] Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="0ed73-243">El grupo de SharePoint **Visitantes de [nombre del sitio]** contiene el grupo de acceso de lectores de sitio, en el que todos los miembros tienen el nivel de permisos **Leer**.</span><span class="sxs-lookup"><span data-stu-id="0ed73-243">The **[site name] Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="0ed73-244">La capacidad de los miembros de invitar a otros miembros está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="0ed73-244">The ability for members to invite other members is disabled.</span></span>
    
- <span data-ttu-id="0ed73-245">La capacidad de los no miembros de solicitar acceso está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="0ed73-245">The ability for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="0ed73-246">Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="0ed73-246">Here is your resulting configuration.</span></span>
  
![Protección de nivel Extremadamente confidencial de un sitio de grupo aislado de SharePoint Online.](media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
<span data-ttu-id="0ed73-248">Los miembros del sitio, a través de la pertenencia a grupos en uno de los grupos de acceso, ahora pueden colaborar de forma segura en los recursos del sitio.</span><span class="sxs-lookup"><span data-stu-id="0ed73-248">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="0ed73-249">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="0ed73-249">Next step</span></span>

[<span data-ttu-id="0ed73-250">Proteger archivos de SharePoint Online con DLP y etiquetas de Office 365</span><span class="sxs-lookup"><span data-stu-id="0ed73-250">Protect SharePoint Online files with Office 365 labels and DLP</span></span>](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a><span data-ttu-id="0ed73-251">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0ed73-251">See also</span></span>

[<span data-ttu-id="0ed73-252">Protección de archivos y sitios de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0ed73-252">Secure SharePoint Online sites and files</span></span>](/security/office-365-security/secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="0ed73-253">Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles</span><span class="sxs-lookup"><span data-stu-id="0ed73-253">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="0ed73-254">Adopción de la nube y soluciones híbridas</span><span class="sxs-lookup"><span data-stu-id="0ed73-254">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
