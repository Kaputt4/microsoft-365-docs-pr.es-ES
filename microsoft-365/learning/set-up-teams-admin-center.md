---
title: Configurar Microsoft Viva Learning (versión preliminar) en el Centro Teams administración
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: ''
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Obtenga información sobre cómo configurar Microsoft Viva Learning (versión preliminar) en el centro Teams administración.
ms.openlocfilehash: 860f16bee7d93f2212072c5d738263402704272f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789236"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="98dd1-103">Configurar Microsoft Viva Learning (versión preliminar) en el Centro Teams administración</span><span class="sxs-lookup"><span data-stu-id="98dd1-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="98dd1-104">La información de este artículo se refiere a un producto de vista previa que puede modificarse considerablemente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="98dd1-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="98dd1-105">El Teams debe realizar determinados pasos para habilitar Viva Learning (versión preliminar) para sus usuarios en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="98dd1-105">The Teams administrator needs to perform certain steps to enable Viva Learning (Preview) for their users in the tenant.</span></span> <span data-ttu-id="98dd1-106">Estos pasos varían en función de cómo se habilita el espacio empresarial: [*Vista previa*](set-up-teams-admin-center.md#public-preview-tenants) pública o Vista [ *previa privada* (o Beta).](set-up-teams-admin-center.md#private-preview-tenants)</span><span class="sxs-lookup"><span data-stu-id="98dd1-106">These steps vary based on how the tenant is enabled:  [*Public Preview*](set-up-teams-admin-center.md#public-preview-tenants) or [*Private Preview* (or Beta)](set-up-teams-admin-center.md#private-preview-tenants).</span></span>

## <a name="public-preview-tenants"></a><span data-ttu-id="98dd1-107">Inquilinos de vista previa pública</span><span class="sxs-lookup"><span data-stu-id="98dd1-107">Public Preview tenants</span></span>

### <a name="administrator-steps-for-public-preview-tenants"></a><span data-ttu-id="98dd1-108">Pasos de administrador para inquilinos de vista previa pública</span><span class="sxs-lookup"><span data-stu-id="98dd1-108">Administrator steps for Public Preview tenants</span></span>

<span data-ttu-id="98dd1-109">Dado que Viva Learning (versión preliminar) todavía no está disponible en general, se requieren ciertos pasos para habilitar las características y establecer permisos para usuarios o grupos específicos.</span><span class="sxs-lookup"><span data-stu-id="98dd1-109">Because the Viva Learning (Preview) is not yet generally available, certain steps are required to enable the features and set permissions for specific users or groups.</span></span> 

1. <span data-ttu-id="98dd1-110">Habilitar las características de vista previa pública para los usuarios de Viva Learning (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="98dd1-110">Enable Public Preview features for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="98dd1-111">a.</span><span class="sxs-lookup"><span data-stu-id="98dd1-111">a.</span></span> <span data-ttu-id="98dd1-112">Modifique Teams de actualización para habilitar las características de Vista previa pública.</span><span class="sxs-lookup"><span data-stu-id="98dd1-112">Modify Teams update policy to enable Public Preview features.</span></span> <span data-ttu-id="98dd1-113">Vea [Microsoft Teams Public Preview](/microsoftteams/public-preview-doc-updates).</span><span class="sxs-lookup"><span data-stu-id="98dd1-113">See [Microsoft Teams Public Preview](/microsoftteams/public-preview-doc-updates).</span></span>

    <span data-ttu-id="98dd1-114">b.</span><span class="sxs-lookup"><span data-stu-id="98dd1-114">b.</span></span> <span data-ttu-id="98dd1-115">Habilite la directiva de actualización para los usuarios o grupos que realizarán las pruebas de Viva Learning (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="98dd1-115">Enable the update policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="98dd1-116">Vea [Asignar directivas a usuarios y grupos.](/microsoftteams/assign-policies-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="98dd1-116">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

2. <span data-ttu-id="98dd1-117">Modifique la directiva de permisos de la aplicación para los usuarios de Viva Learning (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="98dd1-117">Modify the app permission policy for Viva Learning (Preview) users.</span></span>

    <span data-ttu-id="98dd1-118">a.</span><span class="sxs-lookup"><span data-stu-id="98dd1-118">a.</span></span> <span data-ttu-id="98dd1-119">A menos que actualmente forma parte de la directiva global, permita todas las aplicaciones de Microsoft en la directiva de permisos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98dd1-119">Unless it's currently part of the global policy, allow all Microsoft apps in the app permission policy.</span></span> <span data-ttu-id="98dd1-120">Consulta [Administrar directivas de permisos de aplicaciones en Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="98dd1-120">See [Manage app permission policies in Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span></span> 

    <span data-ttu-id="98dd1-121">b.</span><span class="sxs-lookup"><span data-stu-id="98dd1-121">b.</span></span> <span data-ttu-id="98dd1-122">Habilite la directiva de permisos de la aplicación para los usuarios o grupos que realizarán las pruebas de Viva Learning (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="98dd1-122">Enable the app permission policy for users or groups who will perform Viva Learning (Preview) testing.</span></span> <span data-ttu-id="98dd1-123">Vea [Asignar directivas a usuarios y grupos.](/microsoftteams/assign-policies-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="98dd1-123">See [Assign policies to users and groups](/microsoftteams/assign-policies-users-and-groups).</span></span>

3.  <span data-ttu-id="98dd1-124">Notifique a los usuarios que probarán Viva Learning (versión preliminar) para cambiar su cliente [de compilación](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants)a Public Preview para Teams .</span><span class="sxs-lookup"><span data-stu-id="98dd1-124">Notify users who will test Viva Learning (Preview) to [switch their build client to Public Preview for Teams](set-up-teams-admin-center.md#user-steps-for-public-preview-tenants).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="98dd1-125">Para los inquilinos de Vista previa pública, Viva  Learning (versión preliminar) no se mostrará en aplicaciones administradas en el centro de administración de Teams hasta la versión final del producto.</span><span class="sxs-lookup"><span data-stu-id="98dd1-125">For Public Preview tenants, Viva Learning (Preview) will not be displayed in **Managed apps** in the Teams admin center until final product release.</span></span> <span data-ttu-id="98dd1-126">Sin embargo, los usuarios habilitados para la vista previa pública pueden encontrar Viva Learning (versión preliminar) en el almacén de aplicaciones de Teams y usarlo, una vez configuradas las directivas y permisos correctos.</span><span class="sxs-lookup"><span data-stu-id="98dd1-126">However, enabled Public Preview users can find Viva Learning (Preview) in the Teams app store and use it, once the correct policies and permissions have been set up.</span></span>

### <a name="user-steps-for-public-preview-tenants"></a><span data-ttu-id="98dd1-127">Pasos de usuario para inquilinos de vista previa pública</span><span class="sxs-lookup"><span data-stu-id="98dd1-127">User steps for Public Preview tenants</span></span>

<span data-ttu-id="98dd1-128">Los usuarios que se han habilitado para las pruebas de vista previa pública (habilitando las directivas descritas [anteriormente)](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) deben cambiar a [Public Preview](/microsoftteams/public-preview-doc-updates#enable-public-preview) en su Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="98dd1-128">Users who have been enabled for Public Preview testing — by enabling the [policies previously described](set-up-teams-admin-center.md#administrator-steps-for-public-preview-tenants) — need to [switch to Public Preview](/microsoftteams/public-preview-doc-updates#enable-public-preview) in their Teams client.</span></span>

1. <span data-ttu-id="98dd1-129">Los usuarios deben seleccionar su imagen de perfil > **Acerca de** la vista  >  **previa pública**.</span><span class="sxs-lookup"><span data-stu-id="98dd1-129">Users must select their profile image > **About** > **Public Preview**.</span></span>
   
    ![Navegación superior en la Teams que muestra el perfil del usuario](../media/learning/learning-app-select-profile-teams.png)
    
2. <span data-ttu-id="98dd1-131">Los usuarios deben aceptar los términos y condiciones de Public Preview.</span><span class="sxs-lookup"><span data-stu-id="98dd1-131">Users must accept the Public Preview terms and conditions.</span></span>

    ![Cambiar a la compilación de vista previa pública](../media/learning/learning-app-switch-to-public-preview.png)
 
3. <span data-ttu-id="98dd1-133">Los usuarios ahora pueden encontrar Viva Learning (versión preliminar) en la Teams de aplicaciones y empezar a usarlo.</span><span class="sxs-lookup"><span data-stu-id="98dd1-133">Users can now find Viva Learning (Preview) in the Teams app store and start using it.</span></span>

## <a name="private-preview-tenants"></a><span data-ttu-id="98dd1-134">Inquilinos de vista previa privada</span><span class="sxs-lookup"><span data-stu-id="98dd1-134">Private Preview tenants</span></span>

### <a name="administrator-steps-for-private-preview-or-beta-tenants"></a><span data-ttu-id="98dd1-135">Pasos de administrador para inquilinos de versión preliminar privada (o beta)</span><span class="sxs-lookup"><span data-stu-id="98dd1-135">Administrator steps for Private Preview (or Beta) tenants</span></span>

<span data-ttu-id="98dd1-136">Para los inquilinos de versión preliminar privada, no hay directivas adicionales que deba habilitarse.</span><span class="sxs-lookup"><span data-stu-id="98dd1-136">For Private Preview tenants, there are no additional policies that need to be enabled.</span></span> <span data-ttu-id="98dd1-137">Sin embargo, Viva Learning (versión preliminar) debe estar disponible para los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="98dd1-137">However, Viva Learning (Preview) must be made available for users in your organization.</span></span>

1. <span data-ttu-id="98dd1-138">En la navegación izquierda del Centro Teams administración, ve a **Teams aplicaciones Administrar**  >  **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="98dd1-138">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Navegación izquierda en el Centro Teams administración que muestra Teams aplicaciones y administrar aplicaciones.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="98dd1-140">En la **página Administrar aplicaciones,** en el cuadro de búsqueda, escriba *Viva Learning* y, a continuación, seleccione Viva **Learning (vista previa).**</span><span class="sxs-lookup"><span data-stu-id="98dd1-140">On the **Manage apps** page, in the search box, type *Viva Learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![Página Administrar aplicaciones en el centro Teams administración que muestra el cuadro de búsqueda.](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="98dd1-142">En la **página Viva Learning (versión preliminar),** en **Estado,** seleccione **Permitido** activar Viva Learning (vista previa).</span><span class="sxs-lookup"><span data-stu-id="98dd1-142">On the **Viva Learning (Preview)** page, under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   ![Página de aprendizaje en el Centro Teams administración que muestra la sección Estado y configuración de la aplicación.](../media/learning/learning-app-teams-learning-page.png)


<!---
The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.

1. For Viva Learning (Preview), you must first set the Update policy in Teams. For more information, see [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).

    1. Sign in to the Teams admin center.

    2. Select **Teams** > **Update policies**.

    3. Select **Add**. 

    4. Name the update policy, add a policy, and turn on **Show preview features**.

2. The admin must notify users of the policy update so that they move their build into the Public Preview for Teams. 

    1. Users must select their profile image > **About** > **Public Preview**.
   
        ![Upper navigation in the Teams application showing user's profile](../media/learning/learning-app-select-profile-teams.png)
    
    2. Users must accept the **Public preview** terms and conditions.

        ![Switch to public preview build](../media/learning/learning-app-switch-to-public-preview.png)
 
3. For organizations that have restrictive policies and need to enable Viva Learning (Preview), follow the process in the next section.

## Manage settings for Viva Learning (Preview)

You must be an administrator in the Teams admin center to perform these tasks.

To make Viva Learning (Preview) available for users in your organization, follow these steps:

1. In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.

   ![Left navigation in the Teams admin center showing Teams apps and Manage apps section.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.

   ![Manage apps page in the Teams admin center showing the search box.](../media/learning/learning-app-teams-manage-apps-page.png)

3. On the **Viva Learning (Preview)** page:

   1. Under **Status**, select **Allowed** to turn on Viva Learning (Preview).

   2. On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).

   ![Learning page in the Teams admin center showing Status and App settings section.](../media/learning/learning-app-teams-learning-page.png)

4. After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.

> [!NOTE]
>  If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview). <br><br>As part of the preview, Viva Learning (Preview) is released in Ring 3.0. If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page. To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users. <br><br>   ![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)

--->

## <a name="next-step"></a><span data-ttu-id="98dd1-144">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="98dd1-144">Next step</span></span>

[<span data-ttu-id="98dd1-145">Configurar orígenes de contenido de aprendizaje para Viva Learning (versión preliminar) en el Centro Microsoft 365 administración</span><span class="sxs-lookup"><span data-stu-id="98dd1-145">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
