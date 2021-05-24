---
title: Configurar Microsoft Viva Learning (versión preliminar) en el Centro Teams administración
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
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
ms.openlocfilehash: e5af676752064738e26f9b934a60973cb9b0200d
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625314"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a><span data-ttu-id="a5f15-103">Configurar Microsoft Viva Learning (versión preliminar) en el Centro Teams administración</span><span class="sxs-lookup"><span data-stu-id="a5f15-103">Set up Microsoft Viva Learning (Preview) in the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="a5f15-104">La información de este artículo se refiere a un producto de vista previa que puede modificarse considerablemente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="a5f15-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="a5f15-105">El Teams instala Viva Learning (versión preliminar) y aplica directivas de permisos a través del centro Teams administración.</span><span class="sxs-lookup"><span data-stu-id="a5f15-105">The Teams admin installs Viva Learning (Preview) and applies permission policies through the Teams admin center.</span></span>

1. <span data-ttu-id="a5f15-106">Para Public Preview, primero debe establecer la directiva Update.</span><span class="sxs-lookup"><span data-stu-id="a5f15-106">For Public Preview, you must first set the Update policy.</span></span> <span data-ttu-id="a5f15-107">Para obtener más información, vea el Teams de Microsoft Teams [Public Preview](/MicrosoftTeams/public-preview-doc-updates).</span><span class="sxs-lookup"><span data-stu-id="a5f15-107">For more details, see the Teams site [Microsoft Teams Public Preview](/MicrosoftTeams/public-preview-doc-updates).</span></span>

    1. <span data-ttu-id="a5f15-108">Inicie sesión en el Centro Teams administración.</span><span class="sxs-lookup"><span data-stu-id="a5f15-108">Sign in to the Teams admin center.</span></span>

    2. <span data-ttu-id="a5f15-109">Seleccione **Teams**  >  **actualizar directivas**.</span><span class="sxs-lookup"><span data-stu-id="a5f15-109">Select **Teams** > **Update policies**.</span></span>

    3. <span data-ttu-id="a5f15-110">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a5f15-110">Select **Add**.</span></span> 

    4. <span data-ttu-id="a5f15-111">Asigne un nombre a la directiva de actualización, agregue una directiva y active **Mostrar características de vista previa.**</span><span class="sxs-lookup"><span data-stu-id="a5f15-111">Name the update policy, add a policy, and turn on **Show preview features**.</span></span>

2. <span data-ttu-id="a5f15-112">El administrador debe notificar a los usuarios la actualización de directivas para que muevan su compilación a Public Preview para Teams.</span><span class="sxs-lookup"><span data-stu-id="a5f15-112">The admin must notify users of the policy update so that they move their build into Public Preview for Teams.</span></span> 

    1. <span data-ttu-id="a5f15-113">El usuario debe seleccionar su imagen de perfil --> Acerca de --> vista previa pública.</span><span class="sxs-lookup"><span data-stu-id="a5f15-113">User must select their profile image --> About --> Public Preview.</span></span>
   
        ![Navegación superior en la Teams que muestra el perfil del usuario](../media/learning/learning-app-select-profile-teams.png)
    
    2. <span data-ttu-id="a5f15-115">El usuario debe aceptar los términos de versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="a5f15-115">User must accept terms of Public Preview.</span></span>

        ![Cambiar a la compilación de vista previa pública](../media/learning/learning-app-switch-to-public-preview.png)
 
3. <span data-ttu-id="a5f15-117">Para las organizaciones que tienen directivas restrictivas y necesitan habilitar Viva Learning, siga el proceso en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="a5f15-117">For organizations that have restrictive policies and need to enable Viva Learning, follow the process in the next section.</span></span>

## <a name="manage-settings-for-viva-learning-preview"></a><span data-ttu-id="a5f15-118">Administrar la configuración de Viva Learning (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="a5f15-118">Manage settings for Viva Learning (Preview)</span></span>

<span data-ttu-id="a5f15-119">Debe ser administrador en el centro de administración Teams para realizar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="a5f15-119">You must be an administrator in the Teams admin center to perform these tasks.</span></span>

<span data-ttu-id="a5f15-120">Para que Viva Learning (versión preliminar) esté disponible para los usuarios de su organización, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a5f15-120">To make Viva Learning (Preview) available for users in your organization, follow these steps:</span></span>

1. <span data-ttu-id="a5f15-121">En la navegación izquierda del Centro Teams administración, ve a **Teams aplicaciones Administrar**  >  **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a5f15-121">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Navegación izquierda en el Centro Teams administración que muestra Teams aplicaciones y administrar aplicaciones.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="a5f15-123">En la **página Administrar aplicaciones,** en el cuadro de búsqueda, escriba *Viva learning* y, a continuación, seleccione Viva **Learning (vista previa).**</span><span class="sxs-lookup"><span data-stu-id="a5f15-123">On the **Manage apps** page, in the search box, type *Viva learning*, and then select **Viva Learning (Preview)**.</span></span>

   ![Página Administrar aplicaciones en el centro Teams administración que muestra el cuadro de búsqueda.](../media/learning/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="a5f15-125">En la **página Viva Learning (versión preliminar):**</span><span class="sxs-lookup"><span data-stu-id="a5f15-125">On the **Viva Learning (Preview)** page:</span></span>

   1. <span data-ttu-id="a5f15-126">En **Estado**, seleccione **Permitido** activar Viva Learning (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="a5f15-126">Under **Status**, select **Allowed** to turn on Viva Learning (Preview).</span></span>

   2. <span data-ttu-id="a5f15-127">En la **Configuración,** en Configuración de la **aplicación,** vaya al Centro de administración de Microsoft 365 para configurar orígenes [de contenido de aprendizaje.](content-sources-365-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="a5f15-127">On the **Settings** tab, under **App settings**, go to the Microsoft 365 admin center to [configure learning content sources](content-sources-365-admin-center.md).</span></span>

   ![Página de aprendizaje en el Centro Teams administración que muestra la sección Estado y configuración de la aplicación.](../media/learning/learning-app-teams-learning-page.png)

4. <span data-ttu-id="a5f15-129">Después **de** administrar la  configuración  de la aplicación, ve a Directivas de permisos y directivas de configuración para conceder permiso a los empleados que deben tener acceso a Viva Learning (versión preliminar) como parte de la participación de la organización en la versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="a5f15-129">After **Manage app** settings, go to **Permission policies** and **Setup policies** to grant permission to employees who should have access to Viva Learning (Preview) as part of your organization's participation in the preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="a5f15-130">Si su organización está en ring 4.0 como parte del programa TAP100 de Teams, es posible que necesite habilitar a los usuarios aprobados en ring 3.0 para tener acceso a Viva Learning (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="a5f15-130">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to enable approved users in Ring 3.0 to access Viva Learning (Preview).</span></span> <br><br><span data-ttu-id="a5f15-131">Como parte de la vista previa, Viva Learning (versión preliminar) se publica en Ring 3.0.</span><span class="sxs-lookup"><span data-stu-id="a5f15-131">As part of the preview, Viva Learning (Preview) is released in Ring 3.0.</span></span> <span data-ttu-id="a5f15-132">Si su organización está en anillo 4.0, no verá Viva Learning (versión preliminar) en la **página Administrar aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="a5f15-132">If your organization is in Ring 4.0, you won’t see Viva Learning (Preview) on the **Manage apps** page.</span></span> <span data-ttu-id="a5f15-133">Para probar la aplicación, debes crear una directiva de permisos de aplicaciones personalizadas, establecerla en **Permitir** todas las aplicaciones y asignarla a los usuarios aprobados de Ring 3.0.</span><span class="sxs-lookup"><span data-stu-id="a5f15-133">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span> <br><br>   <span data-ttu-id="a5f15-134">![Página TAP-AppsPermission-Plcy que muestra Permitir todas las aplicaciones seleccionadas.](../media/learning/learning-app-tap-appspermission-plcy.png)</span><span class="sxs-lookup"><span data-stu-id="a5f15-134">![TAP-AppsPermission-Plcy page showing Allow all apps selected.](../media/learning/learning-app-tap-appspermission-plcy.png)</span></span>

## <a name="next-step"></a><span data-ttu-id="a5f15-135">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="a5f15-135">Next step</span></span>

[<span data-ttu-id="a5f15-136">Configurar orígenes de contenido de aprendizaje para Viva Learning (versión preliminar) en el Centro Microsoft 365 administración</span><span class="sxs-lookup"><span data-stu-id="a5f15-136">Configure learning content sources for Viva Learning (Preview) in the Microsoft 365 admin center</span></span>](content-sources-365-admin-center.md)
