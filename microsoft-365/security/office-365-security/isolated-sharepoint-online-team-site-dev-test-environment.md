---
title: Sitio de grupo de SharePoint Online aislado en su entorno para desarrollo y pruebas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 'Resumen: configure un sitio de grupo de SharePoint Online que esté aislado del resto de la organización en su entorno de desarrollo y pruebas de Microsoft 365.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 103ba1ddb2b5123db80be91f40c4fce8c6e2eb3d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286614"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="20a6d-103">Sitio de grupo de SharePoint Online aislado en su entorno para desarrollo y pruebas</span><span class="sxs-lookup"><span data-stu-id="20a6d-103">Isolated SharePoint Online team site dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="20a6d-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="20a6d-104">**Applies to**</span></span>
- [<span data-ttu-id="20a6d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="20a6d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="20a6d-106">Plan 1 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="20a6d-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="20a6d-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="20a6d-107">SharePoint Online</span></span> 


 <span data-ttu-id="20a6d-108">**Resumen:** Configure un sitio de grupo de SharePoint Online aislado del resto de la organización en su entorno de desarrollo y pruebas de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="20a6d-108">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Microsoft 365 dev/test environment.</span></span>

<span data-ttu-id="20a6d-109">Los sitios de grupo de SharePoint Online en Microsoft 365 son ubicaciones para colaboración mediante una biblioteca de documentos común, un bloc de notas de OneNote y otros servicios.</span><span class="sxs-lookup"><span data-stu-id="20a6d-109">SharePoint Online team sites in Microsoft 365 are locations for collaboration using a common document library, a OneNote notebook, and other services.</span></span> <span data-ttu-id="20a6d-110">En muchos casos, deseará contar con un acceso amplio y una colaboración entre departamentos u organizaciones.</span><span class="sxs-lookup"><span data-stu-id="20a6d-110">In many cases, you want wide access and collaboration across departments or organizations.</span></span> <span data-ttu-id="20a6d-111">Sin embargo, en algunos casos, desea controlar estrechamente el acceso y los permisos de colaboración entre un pequeño grupo de personas.</span><span class="sxs-lookup"><span data-stu-id="20a6d-111">However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>

<span data-ttu-id="20a6d-112">El acceso a los sitios de grupo de SharePoint Online y lo que los usuarios pueden hacer se controla mediante grupos de SharePoint y niveles de permisos.</span><span class="sxs-lookup"><span data-stu-id="20a6d-112">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels.</span></span> <span data-ttu-id="20a6d-113">De forma predeterminada, los sitios de SharePoint Online cuentan con tres niveles de acceso:</span><span class="sxs-lookup"><span data-stu-id="20a6d-113">By default, SharePoint Online sites have three levels of access:</span></span>

- <span data-ttu-id="20a6d-114">**Miembros**, que pueden ver, crear y modificar los recursos del sitio.</span><span class="sxs-lookup"><span data-stu-id="20a6d-114">**Members**, who can view, create, and modify resources on the site.</span></span>
- <span data-ttu-id="20a6d-115">**Propietarios**, que tienen un control total sobre el sitio y pueden cambiar los permisos.</span><span class="sxs-lookup"><span data-stu-id="20a6d-115">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>
- <span data-ttu-id="20a6d-116">**Visitantes**, que únicamente pueden ver los recursos del sitio.</span><span class="sxs-lookup"><span data-stu-id="20a6d-116">**Visitors**, who only can view resources on the site.</span></span>

<span data-ttu-id="20a6d-117">En este artículo, se indican los pasos que se deben seguir para configurar un sitio de grupo de SharePoint Online aislado para un proyecto de investigación secreto, que llamaremos ProyectoX.</span><span class="sxs-lookup"><span data-stu-id="20a6d-117">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX.</span></span> <span data-ttu-id="20a6d-118">Los requisitos de acceso son:</span><span class="sxs-lookup"><span data-stu-id="20a6d-118">The access requirements are:</span></span>

- <span data-ttu-id="20a6d-119">Solo los miembros del proyecto pueden acceder al sitio y a su contenido (documentos, Bloc de notas de OneNote y páginas), con niveles de permiso de SharePoint de edición y visualización controlados a través de la pertenencia al grupo.</span><span class="sxs-lookup"><span data-stu-id="20a6d-119">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>

- <span data-ttu-id="20a6d-120">Únicamente el creador del sitio y los miembros de un grupo de administradores del sitio pueden llevar a cabo tareas relacionadas con la administración, lo que incluye la modificación de los permisos del sitio.</span><span class="sxs-lookup"><span data-stu-id="20a6d-120">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>

<span data-ttu-id="20a6d-121">Hay tres fases para configurar un sitio de grupo de SharePoint Online aislado en el entorno de desarrollo y pruebas de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="20a6d-121">There are three phases to setting up an isolated SharePoint Online team site in your Microsoft 365 dev/test environment:</span></span>

1. <span data-ttu-id="20a6d-122">Cree el entorno de desarrollo y pruebas de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="20a6d-122">Create the Microsoft 365 dev/test environment.</span></span>

2. <span data-ttu-id="20a6d-123">Crear los usuarios y los grupos de ProyectoX.</span><span class="sxs-lookup"><span data-stu-id="20a6d-123">Create the users and groups for ProjectX.</span></span>

3. <span data-ttu-id="20a6d-124">Crear un sitio de grupo de SharePoint Online para ProyectoX y aislarlo.</span><span class="sxs-lookup"><span data-stu-id="20a6d-124">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>

> [!TIP]
> <span data-ttu-id="20a6d-125">Haga clic [aquí](https://aka.ms/catlgstack) para ver un mapa visual de todos los artículos en la pila de la Guía del entorno de pruebas de One Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="20a6d-125">Click [here](https://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a><span data-ttu-id="20a6d-126">Fase 1: Crear un entorno de desarrollo y pruebas ligero o simulado de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="20a6d-126">Phase 1: Build out your lightweight or simulated enterprise Microsoft 365 dev/test environment</span></span>

<span data-ttu-id="20a6d-127">Si solo desea crear un sitio de grupo aislado de SharePoint Online de forma ligera con los requisitos mínimos, siga las instrucciones de las fases 2 y 3 de la configuración [básica ligera.](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="20a6d-127">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [The lightweight base configuration](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="20a6d-128">Si desea crear un sitio de grupo aislado de SharePoint Online en una configuración empresarial simulada, siga las instrucciones de sincronización de hash de contraseña para su entorno de prueba de [Microsoft 365.](../../enterprise/password-hash-sync-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="20a6d-128">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [Password hash synchronization for your Microsoft 365 test environment](../../enterprise/password-hash-sync-m365-ent-test-environment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="20a6d-129">La creación de un sitio aislado de SharePoint Online no requiere el entorno de desarrollo y pruebas empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="20a6d-129">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="20a6d-130">Se proporciona aquí como opción para que pueda probar un sitio de SharePoint Online aislado y experimentar con él en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="20a6d-130">It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="20a6d-131">Fase 2: Crear cuentas de usuario y grupos de acceso</span><span class="sxs-lookup"><span data-stu-id="20a6d-131">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="20a6d-132">Siga las instrucciones de Conectarse a PowerShell de [Office 365](../../enterprise/connect-to-microsoft-365-powershell.md) para conectarse a su suscripción de prueba con su cuenta de administrador global desde:</span><span class="sxs-lookup"><span data-stu-id="20a6d-132">Use the instructions in [Connect to Office 365 PowerShell](../../enterprise/connect-to-microsoft-365-powershell.md) to connect to your trial subscription with your global administrator account from:</span></span>

- <span data-ttu-id="20a6d-133">Su equipo (para el entorno ligero de desarrollo y pruebas de Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="20a6d-133">Your computer (for the lightweight Microsoft 365 dev/test environment).</span></span>

- <span data-ttu-id="20a6d-134">La máquina virtual CLIENT1 (para el entorno de desarrollo y pruebas de una empresa simulada de Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="20a6d-134">The CLIENT1 virtual machine (for the simulated enterprise Microsoft 365 dev/test environment).</span></span>

<span data-ttu-id="20a6d-135">Para crear los nuevos grupos de acceso para el sitio de grupo de SharePoint Online de ProjectX, ejecute estos comandos desde el símbolo del sistema del módulo Windows Azure Active Directory para Windows PowerShell usuario:</span><span class="sxs-lookup"><span data-stu-id="20a6d-135">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

<span data-ttu-id="20a6d-136">Rellene el nombre de la organización (ejemplo: contosotoycompany), el código de país de dos caracteres para su ubicación y, después, ejecute los comandos siguientes desde el símbolo del sistema de Módulo Microsoft Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="20a6d-136">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="20a6d-137">En la pantalla del comando **New-MsolUser**, anote la contraseña generada para la cuenta del responsable de diseño y guárdela en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="20a6d-137">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>

<span data-ttu-id="20a6d-138">Ejecute los siguientes comandos desde el símbolo del sistema del Módulo de Windows Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="20a6d-138">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="20a6d-139">En la pantalla del comando **New-MsolUser**, anote la contraseña generada para la cuenta del responsable de investigación y guárdela en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="20a6d-139">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>

<span data-ttu-id="20a6d-140">Ejecute los siguientes comandos desde el símbolo del sistema del Módulo de Windows Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="20a6d-140">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="20a6d-141">En la pantalla del comando **New-MsolUser**, anote la contraseña generada para la cuenta del vicepresidente de investigación y guárdela en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="20a6d-141">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>

<span data-ttu-id="20a6d-142">A continuación, para agregar las nuevas cuentas a los nuevos grupos de acceso, ejecute estos comandos de PowerShell desde el Windows Azure módulo de Active Directory para Windows PowerShell solicitud:</span><span class="sxs-lookup"><span data-stu-id="20a6d-142">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

<span data-ttu-id="20a6d-143">Resultados:</span><span class="sxs-lookup"><span data-stu-id="20a6d-143">Results:</span></span>

- <span data-ttu-id="20a6d-144">El ProjectX-Members de acceso contiene las cuentas de usuario diseñador de clientes potenciales e investigador principal</span><span class="sxs-lookup"><span data-stu-id="20a6d-144">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>

- <span data-ttu-id="20a6d-145">El ProjectX-Admins de acceso de prueba contiene la cuenta de administrador global de la suscripción de prueba.</span><span class="sxs-lookup"><span data-stu-id="20a6d-145">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>

- <span data-ttu-id="20a6d-146">El ProjectX-Viewers de acceso contiene la cuenta de usuario del vicepresidente de desarrollo</span><span class="sxs-lookup"><span data-stu-id="20a6d-146">The ProjectX-Viewers access group contains the Development VP user account</span></span>

<span data-ttu-id="20a6d-147">La figura 1 muestra los grupos de acceso y su pertenencia.</span><span class="sxs-lookup"><span data-stu-id="20a6d-147">Figure 1 shows the access groups and their membership.</span></span>

<span data-ttu-id="20a6d-148">**Figura 1:**</span><span class="sxs-lookup"><span data-stu-id="20a6d-148">**Figure 1**:</span></span>

![Los grupos de Microsoft 365 y su pertenencia a un sitio de grupo de SharePoint Online aislado](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="20a6d-150">Fase 3: Crear un sitio de grupo de SharePoint Online para ProyectoX y aislarlo</span><span class="sxs-lookup"><span data-stu-id="20a6d-150">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="20a6d-151">Para crear un sitio de grupo de SharePoint Online para ProyectoX, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="20a6d-151">To create a SharePoint Online team site for ProjectX, do the following:</span></span>

1. <span data-ttu-id="20a6d-152">Con un explorador en el equipo local (configuración ligera) o en CLIENT1 (configuración empresarial simulada), inicie sesión en el Centro de administración de Microsoft 365 ( ) con su cuenta de administrador <https://admin.microsoft.com> global.</span><span class="sxs-lookup"><span data-stu-id="20a6d-152">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="20a6d-153">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-153">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="20a6d-154">En la nueva pestaña de SharePoint del explorador, haga clic en **+ Crear sitio**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-154">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="20a6d-155">En **Nombre del sitio de grupo**, escriba **ProyectoX**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-155">In **Team site name**, type **ProjectX**.</span></span> <span data-ttu-id="20a6d-156">En **configuración de privacidad,** seleccione **Privado: solo los miembros pueden acceder a este sitio.**</span><span class="sxs-lookup"><span data-stu-id="20a6d-156">In **Privacy settings**, select **Private - only members can access this site**.</span></span>

5. <span data-ttu-id="20a6d-157">En **Descripción del sitio de grupo**, escriba **Sitio de SharePoint para ProyectoX** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-157">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>

6. <span data-ttu-id="20a6d-158">En el panel **¿A quién quiere agregar?**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-158">On the **Who do you want to add**? pane, click **Finish**.</span></span>

7. <span data-ttu-id="20a6d-159">En la nueva pestaña **ProyectoX-Inicio** del explorador, en la barra de herramientas, haga clic en el icono de configuración y, a continuación, en **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-159">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

8. <span data-ttu-id="20a6d-160">En el panel **Permisos del sitio**, haga clic en **Configuración avanzada de permisos**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-160">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

9. <span data-ttu-id="20a6d-161">En la nueva pestaña **Permisos: ProyectoX** del explorador, haga clic en **Configuración de solicitud de acceso**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-161">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>

10. <span data-ttu-id="20a6d-162">En el cuadro de diálogo **Configuración de solicitud de acceso**, desactive **Permitir que los miembros compartan el sitio y archivos y carpetas individuales** y **Permitir solicitudes de acceso** (de modo que las tres casillas estén desactivadas) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-162">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

11. <span data-ttu-id="20a6d-163">Haga clic en la opción **Miembros del ProyectoX** de la lista.</span><span class="sxs-lookup"><span data-stu-id="20a6d-163">Click **ProjectX Members** in the list.</span></span>

12. <span data-ttu-id="20a6d-164">En la página **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-164">On the **People and Groups** page, click **New**.</span></span>

13. <span data-ttu-id="20a6d-165">En el cuadro de diálogo **Compartir**, escriba **Miembros del ProyectoX**, seleccione esta opción y, a continuación, haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-165">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="20a6d-166">Haga clic en el botón Atrás del explorador.</span><span class="sxs-lookup"><span data-stu-id="20a6d-166">Click the back button on your browser.</span></span>

15. <span data-ttu-id="20a6d-167">Haga clic en la opción **Propietarios del ProyectoX** de la lista.</span><span class="sxs-lookup"><span data-stu-id="20a6d-167">Click **ProjectX Owners** in the list.</span></span>

16. <span data-ttu-id="20a6d-168">En la página **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-168">On the **People and Groups** page, click **New**.</span></span>

17. <span data-ttu-id="20a6d-169">En el cuadro de diálogo **Compartir**, escriba **Administradores del ProyectoX**, seleccione esta opción y, a continuación, haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-169">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="20a6d-170">Haga clic en el botón Atrás del explorador.</span><span class="sxs-lookup"><span data-stu-id="20a6d-170">Click the back button on your browser.</span></span>

19. <span data-ttu-id="20a6d-171">Haga clic en la opción **Visitantes del ProyectoX** de la lista.</span><span class="sxs-lookup"><span data-stu-id="20a6d-171">Click **ProjectX Visitors** in the list.</span></span>

20. <span data-ttu-id="20a6d-172">En la página **Personas y grupos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-172">On the **People and Groups** page, click **New**.</span></span>

21. <span data-ttu-id="20a6d-173">En el cuadro de diálogo **Compartir**, escriba **Lectores del ProyectoX**, seleccione esta opción y, a continuación, haga clic en **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-173">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>

22. <span data-ttu-id="20a6d-174">Cierre la pestaña **Personas y grupos** del explorador, haga clic en la pestaña **Inicio del ProyectoX** del explorador y, a continuación, cierre el panel **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-174">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="20a6d-175">A continuación se indican los resultados de la configuración de permisos:</span><span class="sxs-lookup"><span data-stu-id="20a6d-175">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="20a6d-176">El grupo de SharePoint Miembros de ProjectX contiene solo el grupo de acceso ProjectX-Members (que contiene solo las cuentas de usuario Diseñador de clientes potenciales e Investigador principal) y el grupo ProjectX (que contiene solo la cuenta de usuario de administrador global).</span><span class="sxs-lookup"><span data-stu-id="20a6d-176">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="20a6d-177">El grupo de SharePoint Propietarios de ProjectX contiene solo el grupo ProjectX-Admins acceso (que contiene solo la cuenta de usuario de administrador global).</span><span class="sxs-lookup"><span data-stu-id="20a6d-177">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="20a6d-178">El grupo de SharePoint De visitantes de ProjectX contiene solo el ProjectX-Viewers de acceso (que contiene solo la cuenta de usuario del vicepresidente de desarrollo).</span><span class="sxs-lookup"><span data-stu-id="20a6d-178">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>

- <span data-ttu-id="20a6d-179">Los miembros no pueden modificar los permisos del nivel del sitio (solo los miembros del grupo “Administradores del ProyectoX” pueden realizar esta acción).</span><span class="sxs-lookup"><span data-stu-id="20a6d-179">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>

- <span data-ttu-id="20a6d-180">El resto de cuentas de usuario no pueden tener acceso al sitio ni a sus recursos, y tampoco pueden solicitar acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="20a6d-180">Other user accounts cannot access the site or its resources or request access to the site.</span></span>

<span data-ttu-id="20a6d-181">En la figura 2 se muestran los grupos de SharePoint y su pertenencia.</span><span class="sxs-lookup"><span data-stu-id="20a6d-181">Figure 2 shows the SharePoint groups and their membership.</span></span>

<span data-ttu-id="20a6d-182">**Figura 2**</span><span class="sxs-lookup"><span data-stu-id="20a6d-182">**Figure 2**</span></span>

![Los grupos de SharePoint Online y su pertenencia a un sitio de grupo de SharePoint Online aislado](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

<span data-ttu-id="20a6d-184">Ahora vamos a demostrar el acceso con la cuenta de usuario del diseñador de responsables:</span><span class="sxs-lookup"><span data-stu-id="20a6d-184">Now let's demonstrate access using the Lead Designer user account:</span></span>

1. <span data-ttu-id="20a6d-185">Cierre la pestaña **Inicio del ProyectoX** del explorador y, a continuación, haga clic en la pestaña **Página principal de Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-185">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>

2. <span data-ttu-id="20a6d-186">Haga clic en el nombre de su administrador global y, a continuación, en **Cerrar sesión**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-186">Click the name of your global administrator, and then click **Sign out**.</span></span>

3. <span data-ttu-id="20a6d-187">Inicie sesión en el Centro de administración de Microsoft 365 ( ) con el nombre de la cuenta del diseñador de clientes potenciales <https://admin.microsoft.com> y su contraseña.</span><span class="sxs-lookup"><span data-stu-id="20a6d-187">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Lead Designer account name and its password.</span></span>

4. <span data-ttu-id="20a6d-188">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-188">In the list of tiles, click **SharePoint**.</span></span>

5. <span data-ttu-id="20a6d-p106">En la nueva pestaña **SharePoint** del explorador, escriba **ProyectoX** en el cuadro de búsqueda, active la búsqueda y, a continuación, haga clic en el sitio de grupo de **ProyectoX**. Debería ver una nueva pestaña para el sitio de grupo de ProyectoX en el explorador.</span><span class="sxs-lookup"><span data-stu-id="20a6d-p106">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site. You should see a new tab in your browser for the ProjectX team site.</span></span>

6. <span data-ttu-id="20a6d-p107">Haga clic en el icono de configuración. Fíjese en que no hay ninguna opción para **Permisos del sitio**. Esto es correcto, ya que solo los miembros del grupo Administradores del ProyectoX pueden modificar los permisos del sitio.</span><span class="sxs-lookup"><span data-stu-id="20a6d-p107">Click the settings icon. Notice that there is no option for **Site Permissions**. This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>

7. <span data-ttu-id="20a6d-194">Abra el Bloc de notas o el editor de texto que prefiera.</span><span class="sxs-lookup"><span data-stu-id="20a6d-194">Open Notepad or a text editor of your choice.</span></span>

8. <span data-ttu-id="20a6d-195">Copie la dirección URL del sitio de grupo de ProyectoX y péguela en una nueva línea del Bloc de notas o su editor de texto.</span><span class="sxs-lookup"><span data-stu-id="20a6d-195">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>

9. <span data-ttu-id="20a6d-196">En la pestaña **Inicio de ProyectoX** del explorador, haga clic en **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-196">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>

10. <span data-ttu-id="20a6d-197">Copie la dirección URL de la carpeta de documentos del ProyectoX y péguela en una nueva línea del Bloc de notas o del editor de texto.</span><span class="sxs-lookup"><span data-stu-id="20a6d-197">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>

11. <span data-ttu-id="20a6d-198">En la pestaña **Documentos del ProyectoX** del explorador, haga clic en **Nuevo > Documento de Word**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-198">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>

12. <span data-ttu-id="20a6d-199">Escriba texto en la página, espere a que el estado indique **Guardado,** haga clic en el botón Atrás en el explorador y, a continuación, actualice la página.</span><span class="sxs-lookup"><span data-stu-id="20a6d-199">Type some text on the page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page.</span></span> <span data-ttu-id="20a6d-200">Debería ver un nuevo **Documento.docx** en la carpeta **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-200">You should see a new **Document.docx** in the **Documents** folder.</span></span>

13. <span data-ttu-id="20a6d-201">Haga clic en el botón de puntos suspensivos del archivo **Documento.docx** y, a continuación, en **Obtener un vínculo**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-201">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>

14. <span data-ttu-id="20a6d-202">Copie la dirección URL en el cuadro de diálogo **Compartir "Document.docx",** péguela en una nueva línea del Bloc de notas o del editor de texto y, a continuación, cierre el cuadro de diálogo Compartir **"Document.docx".**</span><span class="sxs-lookup"><span data-stu-id="20a6d-202">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>

15. <span data-ttu-id="20a6d-203">Cierre las pestañas **Documentos del ProyectoX** y **SharePoint** del explorador y, a continuación, haga clic en la pestaña **Página principal de Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-203">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>

16. <span data-ttu-id="20a6d-204">Haga clic en el nombre del **responsable de diseño** y, a continuación, en **Cerrar sesión**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-204">Click the **Lead Designer** name, and then click **Sign out**.</span></span>

<span data-ttu-id="20a6d-205">Ahora vamos a demostrar el acceso con la cuenta de usuario del vicepresidente de desarrollo:</span><span class="sxs-lookup"><span data-stu-id="20a6d-205">Now let's demonstrate access using the Development VP user account:</span></span>

1. <span data-ttu-id="20a6d-206">Inicie sesión en el Centro de administración de Microsoft 365 ( ) con el nombre de la cuenta del vicepresidente de desarrollo <https://admin.microsoft.com> y su contraseña.</span><span class="sxs-lookup"><span data-stu-id="20a6d-206">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Development VP account name and its password.</span></span>

2. <span data-ttu-id="20a6d-207">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-207">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="20a6d-p109">En la nueva pestaña **SharePoint** del explorador, escriba **ProyectoX** en el cuadro de búsqueda, active la búsqueda y, a continuación, haga clic en el sitio de grupo de **ProyectoX**. Debería ver una nueva pestaña para el sitio de grupo de ProyectoX en el explorador.</span><span class="sxs-lookup"><span data-stu-id="20a6d-p109">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site. You should see a new tab in your browser for the ProjectX team site.</span></span>

4. <span data-ttu-id="20a6d-210">Haga clic en **Documentos** y, a continuación, en el archivo **Documento.docx**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-210">Click **Documents**, and then click the **Document.docx** file.</span></span>

5. <span data-ttu-id="20a6d-p110">En la pestaña **Documento.docx** del explorador, intente modificar el texto. Debería ver un mensaje con el texto **El documento es de solo lectura**. Esto ocurre porque la cuenta de usuario de vicepresidente de desarrollo solo tiene permisos de visualización en el sitio.</span><span class="sxs-lookup"><span data-stu-id="20a6d-p110">In the **Document.docx** tab in your browser, try to modify the text. You should see a message stating **This document is read-only.** This is expected because the Development VP user account only has view permissions for the site.</span></span>

6. <span data-ttu-id="20a6d-214">Cierre las pestañas **Documento.docx**, **Documentos del ProyectoX** y **SharePoint** del explorador.</span><span class="sxs-lookup"><span data-stu-id="20a6d-214">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>

7. <span data-ttu-id="20a6d-215">En la pestaña **Página principal de Microsoft Office**, haga clic en el nombre del **vicepresidente de desarrollo** y, a continuación, en **Cerrar sesión**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-215">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>

<span data-ttu-id="20a6d-216">Ahora vamos a demostrar el acceso con una cuenta de usuario que no tiene permisos:</span><span class="sxs-lookup"><span data-stu-id="20a6d-216">Now let's demonstrate access with a user account that has no permissions:</span></span>

1. <span data-ttu-id="20a6d-217">Inicie sesión en el Centro de administración de Microsoft 365 ( ) con el nombre de la cuenta usuario <https://admin.microsoft.com> 3 y su contraseña.</span><span class="sxs-lookup"><span data-stu-id="20a6d-217">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the User 3 account name and its password.</span></span>

2. <span data-ttu-id="20a6d-218">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-218">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="20a6d-p111">	En la nueva pestaña *\*SharePoint** del explorador, escriba *\*ProyectoX** en el cuadro de búsqueda y, a continuación, active la búsqueda. Debería ver el mensaje *\*No se encontró nada que coincida con la búsqueda*\*.</span><span class="sxs-lookup"><span data-stu-id="20a6d-p111">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search. You should see the message **Nothing here matches your search.**</span></span>

4. <span data-ttu-id="20a6d-p112">Desde la instancia abierta del Bloc de notas o el editor de texto, copie la dirección URL del sitio del ProyectoX en la barra de direcciones del explorador y presione **Entrar**. Debería ver una página con el título **Acceso denegado**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-p112">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

5. <span data-ttu-id="20a6d-p113">Desde la instancia abierta del Bloc de notas o el editor de texto, copie la dirección URL de la carpeta de documentos del ProyectoX en la barra de direcciones del explorador y presione **Entrar**. Debería ver una página con el título **Acceso denegado**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-p113">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

6. <span data-ttu-id="20a6d-p114">Desde la instancia abierta del Bloc de notas o el editor de texto, copie la dirección URL del archivo Documentos.docx en la barra de direcciones del explorador y presione **Entrar**. Debería ver una página con el título **Acceso denegado**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-p114">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

7. <span data-ttu-id="20a6d-227">Desde la pestaña **SharePoint** de su explorador, haga clic en la pestaña **Página principal de Microsoft Office**, haga clic en el nombre **Usuario 3** y, a continuación, en **Cerrar sesión**.</span><span class="sxs-lookup"><span data-stu-id="20a6d-227">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>

<span data-ttu-id="20a6d-228">El sitio aislado de SharePoint Online ya está listo para los experimentos adicionales.</span><span class="sxs-lookup"><span data-stu-id="20a6d-228">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>

## <a name="next-step"></a><span data-ttu-id="20a6d-229">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="20a6d-229">Next Step</span></span>

<span data-ttu-id="20a6d-230">Cuando esté preparado para implementar un sitio de grupo de SharePoint Online aislado en producción, vea las consideraciones de diseño paso a paso en [Diseñar un sitio de grupo aislado de SharePoint Online](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="20a6d-230">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="20a6d-231">Vea también</span><span class="sxs-lookup"><span data-stu-id="20a6d-231">See Also</span></span>

[<span data-ttu-id="20a6d-232">Sitios de grupo de SharePoint Online aislados</span><span class="sxs-lookup"><span data-stu-id="20a6d-232">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="20a6d-233">Guías del entorno de pruebas de adopción de la nube (TLG)</span><span class="sxs-lookup"><span data-stu-id="20a6d-233">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="20a6d-234">Configuración básica empresarial simulada</span><span class="sxs-lookup"><span data-stu-id="20a6d-234">The simulated enterprise base configuration</span></span>](../../enterprise/simulated-ent-base-configuration-microsoft-365-enterprise.md)

[<span data-ttu-id="20a6d-235">Configuración básica ligera</span><span class="sxs-lookup"><span data-stu-id="20a6d-235">The lightweight base configuration</span></span>](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

[<span data-ttu-id="20a6d-236">Centro de soluciones y arquitectura de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="20a6d-236">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)