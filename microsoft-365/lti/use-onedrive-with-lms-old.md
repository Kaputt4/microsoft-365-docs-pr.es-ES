---
title: Usar OneDrive Learning interoperabilidad de herramientas de OneDrive Learning
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Cree y cale las asignaciones, cree y cura el contenido del curso y colabore en archivos en tiempo real con la nueva OneDrive Learning Tools Interoperability App.
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53257049"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="5acc3-103">Usar Microsoft OneDrive LTI con Canvas</span><span class="sxs-lookup"><span data-stu-id="5acc3-103">Use Microsoft OneDrive LTI with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5acc3-104">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="5acc3-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5acc3-105">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="5acc3-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="integrate-with-canvas"></a><span data-ttu-id="5acc3-106">Integrar con Canvas</span><span class="sxs-lookup"><span data-stu-id="5acc3-106">Integrate with Canvas</span></span>

<span data-ttu-id="5acc3-107">La persona que realiza esta integración debe ser un administrador de Canvas y un administrador del Microsoft 365 inquilino.</span><span class="sxs-lookup"><span data-stu-id="5acc3-107">The person who performs this integration should be an admin of Canvas and an admin of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="5acc3-108">Inicie sesión en el portal Microsoft Azure con la cuenta de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="5acc3-108">Sign in to the Microsoft Azure portal with the tenant admin account.</span></span> <span data-ttu-id="5acc3-109">El administrador de inquilinos de Azure también debe tener el rol de administrador de grupo.</span><span class="sxs-lookup"><span data-stu-id="5acc3-109">The Azure tenant administrator should also have the Group administrator role.</span></span>

    ![administrador de grupo resaltado](../media/lti-media/lti-group-admin.png)

2. <span data-ttu-id="5acc3-111">Inicie sesión en el portal [OneDrive LTI de](https://odltiappnl.azurewebsites.net/admin)Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5acc3-111">Sign in to the Microsoft [OneDrive LTI portal](https://odltiappnl.azurewebsites.net/admin).</span></span>

3. <span data-ttu-id="5acc3-112">Acepte los permisos para completar el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5acc3-112">Accept the permissions to complete the sign-in.</span></span>

    ![aceptar permisos](../media/lti-media/lti-permissions.png)

4. <span data-ttu-id="5acc3-114">Seleccione **Agregar inquilino LTI**.</span><span class="sxs-lookup"><span data-stu-id="5acc3-114">Select **Add LTI Tenant**.</span></span>

     ![agregar inquilino de LTI](../media/lti-media/lti-add-tenant.png)

5. <span data-ttu-id="5acc3-116">Selecciona **Plataforma de consumidor de LTI** como **Lienzo** en el desplegable.</span><span class="sxs-lookup"><span data-stu-id="5acc3-116">Select **LTI Consumer Platform** as **Canvas** from the dropdown.</span></span>

6. <span data-ttu-id="5acc3-117">Seleccione **Dirección URL base de Canvas** y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5acc3-117">Select **Canvas Base URL** and then select **Next**.</span></span>

    ![seleccione Canvas y agregue la dirección URL base](../media/lti-media/lti-canvas-base-url.png)

   <span data-ttu-id="5acc3-119">En la siguiente pantalla se muestran los campos que son confidenciales para usted.</span><span class="sxs-lookup"><span data-stu-id="5acc3-119">The next screen shows fields that are confidential to you.</span></span>

7. <span data-ttu-id="5acc3-120">Seleccione **Siguiente** de ??</span><span class="sxs-lookup"><span data-stu-id="5acc3-120">Select **Next** from ??</span></span> <span data-ttu-id="5acc3-121">página.</span><span class="sxs-lookup"><span data-stu-id="5acc3-121">page.</span></span> <span data-ttu-id="5acc3-122">¿LOS REVISORES PUEDEN RELLENAR EL ESPACIO EN BLANCO AQUÍ?</span><span class="sxs-lookup"><span data-stu-id="5acc3-122">CAN REVIEWERS FILL IN THE BLANK HERE?</span></span>

8. <span data-ttu-id="5acc3-123">Seleccione **Siguiente** en la pantalla que muestra información confidencial para usted.</span><span class="sxs-lookup"><span data-stu-id="5acc3-123">Select **Next** in the screen that shows information that's confidential to you.</span></span>

   <span data-ttu-id="5acc3-124">La pantalla final de Azure Portal muestra los pasos siguientes para agregar la instancia de Canvas.</span><span class="sxs-lookup"><span data-stu-id="5acc3-124">The final screen of the Azure portal shows the next steps for adding your Canvas instance.</span></span>

9. <span data-ttu-id="5acc3-125">Copia las claves de desarrollador de esta pantalla.</span><span class="sxs-lookup"><span data-stu-id="5acc3-125">Copy the Developer Keys from this screen.</span></span> <span data-ttu-id="5acc3-126">Lo usarás al crear la instancia de Canvas.</span><span class="sxs-lookup"><span data-stu-id="5acc3-126">You'll use when you create the Canvas instance.</span></span>

## <a name="add-the-canvas-instance"></a><span data-ttu-id="5acc3-127">Agregar la instancia de Canvas</span><span class="sxs-lookup"><span data-stu-id="5acc3-127">Add the Canvas instance</span></span>

1. <span data-ttu-id="5acc3-128">En la instancia de Canvas, anule la selección de **Claves de desarrollador** de  >  **administración**.</span><span class="sxs-lookup"><span data-stu-id="5acc3-128">In your Canvas instance, deselect **Admin** > **Developer Keys**.</span></span>

2. <span data-ttu-id="5acc3-129">Elija **Clave LTI en** la lista desplegable en Clave de **desarrollador**.</span><span class="sxs-lookup"><span data-stu-id="5acc3-129">Choose **LTI Key** in the dropdown on **Developer Key**.</span></span>

   ![Obtener las claves de desarrollador de LTI](../media/lti-media/lti-developer-keys.png)

3. <span data-ttu-id="5acc3-131">Pegue las claves de desarrollador aquí.</span><span class="sxs-lookup"><span data-stu-id="5acc3-131">Paste the developer keys here.</span></span>

     ![Pegar las claves de desarrollador](../media/lti-media/lti-developer-keys.png)

   <span data-ttu-id="5acc3-133">La clave se crea en **modo OFF**</span><span class="sxs-lookup"><span data-stu-id="5acc3-133">The key gets created in **OFF** mode</span></span>

   ![Las claves de desarrollador creadas en modo desactivado](../media/lti-media/lti-copy-developer-keys.png)

4. <span data-ttu-id="5acc3-135">Copie el texto resaltado.</span><span class="sxs-lookup"><span data-stu-id="5acc3-135">Copy the highlighted text.</span></span>
    <span data-ttu-id="5acc3-136">Esto sirve como identificador de cliente en Microsoft OneDrive portal LTI.</span><span class="sxs-lookup"><span data-stu-id="5acc3-136">This serves as Client ID in Microsoft OneDrive LTI portal.</span></span>

5. <span data-ttu-id="5acc3-137">Pegue el texto en el **campo Id.** de cliente en Microsoft OneDrive portal LTI y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5acc3-137">Paste the text into the **Client ID** field in Microsoft OneDrive LTI portal, and then select **Next**.</span></span>

6. <span data-ttu-id="5acc3-138">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5acc3-138">Select **Save**.</span></span>

7. <span data-ttu-id="5acc3-139">Para ver la configuración, seleccione **Ver inquilinos de LTI**.</span><span class="sxs-lookup"><span data-stu-id="5acc3-139">View the settings by selecting **View LTI Tenants**.</span></span>
