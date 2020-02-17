---
title: Implementación de equipos con tres niveles de protección de archivos
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
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
description: Cree y configure equipos con Microsoft Teams en distintos niveles de protección de archivos.
ms.openlocfilehash: 63a4b6763165f38e1de5331324e5a7b3573ea0f1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083359"
---
# <a name="deploy-teams-for-three-tiers-of-protection-for-files"></a><span data-ttu-id="7e735-103">Implementación de equipos con tres niveles de protección de archivos</span><span class="sxs-lookup"><span data-stu-id="7e735-103">Deploy teams for three tiers of protection for files</span></span>

<span data-ttu-id="7e735-104">Siga los pasos de este artículo para diseñar e implementar equipos de línea base, confidenciales y extremadamente confidenciales.</span><span class="sxs-lookup"><span data-stu-id="7e735-104">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential teams.</span></span> <span data-ttu-id="7e735-105">Para más información sobre estos tres niveles de protección, vea [Proteger archivos en Microsoft Teams](secure-files-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7e735-105">For more information about these three tiers of protection, see [Secure files in Microsoft Teams](secure-files-in-teams.md).</span></span>

## <a name="baseline-teams"></a><span data-ttu-id="7e735-106">Equipos de línea base</span><span class="sxs-lookup"><span data-stu-id="7e735-106">Baseline teams</span></span>

<span data-ttu-id="7e735-107">La protección de línea base incluye equipos tanto públicos como privados.</span><span class="sxs-lookup"><span data-stu-id="7e735-107">Baseline protection includes both public and private teams.</span></span> <span data-ttu-id="7e735-108">Los equipos públicos son aquellos visibles y accesibles por cualquier persona de la organización.</span><span class="sxs-lookup"><span data-stu-id="7e735-108">Public teams can be discovered and accessed by anybody in the organization.</span></span> <span data-ttu-id="7e735-109">Los equipos privados son aquellos que solo los miembros del grupo de Office 365 asociado al equipo en cuestión pueden detectar y acceder a ellos.</span><span class="sxs-lookup"><span data-stu-id="7e735-109">Private sites can only be discovered and accessed by members of the Office 365 group associated with the team.</span></span> <span data-ttu-id="7e735-110">Ambos tipos de equipos permiten a los miembros compartir el sitio con otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="7e735-110">Both of these types of teams allow members to share the site with others.</span></span>

### <a name="public"></a><span data-ttu-id="7e735-111">Público</span><span class="sxs-lookup"><span data-stu-id="7e735-111">Public</span></span>

<span data-ttu-id="7e735-112">Siga las instrucciones que se indican en [este artículo](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) para crear un Equipo de línea base con permisos y acceso públicos.</span><span class="sxs-lookup"><span data-stu-id="7e735-112">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline Team with public access and permissions.</span></span>

<span data-ttu-id="7e735-113">Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="7e735-113">Here is your resulting configuration.</span></span>

![Protección de nivel de línea base de un equipo público.](../../media/baseline-public-team.png)

### <a name="private"></a><span data-ttu-id="7e735-115">Private</span><span class="sxs-lookup"><span data-stu-id="7e735-115">Private</span></span>

<span data-ttu-id="7e735-116">Siga las instrucciones que se indican en [este artículo](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) para crear un Equipo de línea base con permisos y acceso privados.</span><span class="sxs-lookup"><span data-stu-id="7e735-116">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline Team with private access and permissions.</span></span>

<span data-ttu-id="7e735-117">Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="7e735-117">Here is your resulting configuration.</span></span>

![Protección de nivel de línea base de un equipo privado.](../../media/baseline-private-team.png)

## <a name="sensitive-teams"></a><span data-ttu-id="7e735-119">Equipos confidenciales</span><span class="sxs-lookup"><span data-stu-id="7e735-119">Sensitive teams</span></span>

<span data-ttu-id="7e735-120">Con un equipo confidencial, se empieza por [crear un equipo privado](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="7e735-120">For a sensitive team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="7e735-121">Después, hay que configurar el sitio de SharePoint subyacente para evitar que los miembros del equipo puedan compartirlo.</span><span class="sxs-lookup"><span data-stu-id="7e735-121">Next, you configure the underlying SharePoint site to prevent sharing by team members.</span></span>

1. <span data-ttu-id="7e735-122">En la barra de herramientas del equipo, haga clic en **Archivos**.</span><span class="sxs-lookup"><span data-stu-id="7e735-122">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="7e735-123">Haga clic en los puntos suspensivos y, luego, en **Abrir en SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="7e735-123">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="7e735-124">En la barra de herramientas, haga clic en el sitio de SharePoint subyacente, en el icono de configuración y, luego, en **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="7e735-124">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="7e735-125">En el panel **Permisos del sitio**, en **Configuración de uso compartido**, haga clic en **Cambiar configuración de uso compartido**.</span><span class="sxs-lookup"><span data-stu-id="7e735-125">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="7e735-126">En **Permisos de uso compartido**, seleccione **Solo los propietarios del sitio pueden compartir archivos, carpetas, además del sitio** y, luego, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7e735-126">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="7e735-127">Este es el resultado de la configuración.</span><span class="sxs-lookup"><span data-stu-id="7e735-127">Here is your resulting configuration.</span></span>

![Protección confidencial de un equipo.](../../media/sensitive-team.png)

## <a name="highly-confidential-teams"></a><span data-ttu-id="7e735-129">Equipos extremadamente confidenciales</span><span class="sxs-lookup"><span data-stu-id="7e735-129">Highly confidential teams</span></span>

<span data-ttu-id="7e735-130">Con un equipo extremadamente confidencial, se empieza por [crear un equipo privado](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="7e735-130">With a highly confidential team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="7e735-131">Después, hay que configurar el sitio de SharePoint subyacente para evitar que los miembros del equipo puedan compartirlo y que los usuarios no miembros del equipo puedan solicitar el acceso a este.</span><span class="sxs-lookup"><span data-stu-id="7e735-131">Next, you configure the underlying SharePoint site to prevent sharing by team members and the requesting of access by non-members of the team.</span></span>

1. <span data-ttu-id="7e735-132">En la barra de herramientas del equipo, haga clic en **Archivos**.</span><span class="sxs-lookup"><span data-stu-id="7e735-132">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="7e735-133">Haga clic en los puntos suspensivos y, luego, en **Abrir en SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="7e735-133">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="7e735-134">En la barra de herramientas, haga clic en el sitio de SharePoint subyacente, en el icono de configuración y, luego, en **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="7e735-134">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="7e735-135">En el panel **Permisos del sitio**, en **Configuración de uso compartido**, haga clic en **Cambiar configuración de uso compartido**.</span><span class="sxs-lookup"><span data-stu-id="7e735-135">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="7e735-136">En **Permisos de uso compartido**, seleccione **Solo los propietarios del sitio pueden compartir archivos, carpetas y el sitio**.</span><span class="sxs-lookup"><span data-stu-id="7e735-136">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>

6. <span data-ttu-id="7e735-137">Desactive **Permitir solicitudes de acceso** y, después, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7e735-137">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="7e735-138">Este es el resultado de la configuración.</span><span class="sxs-lookup"><span data-stu-id="7e735-138">Here is your resulting configuration.</span></span>

![Protección extremadamente confidencial de un equipo.](../../media/highly-confidential-team.png)

## <a name="next-step"></a><span data-ttu-id="7e735-140">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="7e735-140">Next step</span></span>

[<span data-ttu-id="7e735-141">Proteger los archivos de los equipos con etiquetas de retención y DLP</span><span class="sxs-lookup"><span data-stu-id="7e735-141">Protect files in teams with retention labels and DLP</span></span>](deploy-teams-retention-DLP.md)

## <a name="see-also"></a><span data-ttu-id="7e735-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e735-142">See also</span></span>

[<span data-ttu-id="7e735-143">Proteger los archivos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e735-143">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)

[<span data-ttu-id="7e735-144">Adopción de la nube y soluciones híbridas</span><span class="sxs-lookup"><span data-stu-id="7e735-144">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
