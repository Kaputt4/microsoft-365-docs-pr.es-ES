---
title: Agregar iconos personalizados en el iniciador de aplicaciones
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Cree vínculos rápidos a su correo electrónico, documentos, aplicaciones, sitios de SharePoint, sitios externos y otros recursos agregando mosaicos personalizados al iniciador de aplicaciones. '
ms.openlocfilehash: 7220f0be8ad6605b7ad6d30000fde6411948c996
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780138"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="355b4-103">Agregar iconos personalizados en el iniciador de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="355b4-103">Add custom tiles to the app launcher</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="355b4-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="355b4-104">The admin center is changing.</span></span> <span data-ttu-id="355b4-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="355b4-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="355b4-106">En Microsoft 365, puede obtener acceso de forma rápida y sencilla a su correo electrónico, calendarios, documentos y aplicaciones mediante el iniciador de aplicaciones ([Obtenga más información](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span><span class="sxs-lookup"><span data-stu-id="355b4-106">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="355b4-107">Estas son aplicaciones que obtiene con Microsoft 365, así como aplicaciones personalizadas que se agregan desde la [tienda SharePoint](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) o [Azure ad](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span><span class="sxs-lookup"><span data-stu-id="355b4-107">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="355b4-108">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more.</span><span class="sxs-lookup"><span data-stu-id="355b4-108">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more.</span></span> <span data-ttu-id="355b4-109">The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same.</span><span class="sxs-lookup"><span data-stu-id="355b4-109">The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same.</span></span> <span data-ttu-id="355b4-110">This makes it easy to find the relevant sites, apps, and resources to do your job.</span><span class="sxs-lookup"><span data-stu-id="355b4-110">This makes it easy to find the relevant sites, apps, and resources to do your job.</span></span> <span data-ttu-id="355b4-111">In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span><span class="sxs-lookup"><span data-stu-id="355b4-111">In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Iniciador de aplicaciones](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="355b4-113">Agregar un icono personalizado en el iniciador de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="355b4-113">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="355b4-114">En el centro de administración, vaya a **configuración de**la  >  **Org Settings** organización y elija la pestaña Perfil de la **organización** .</span><span class="sxs-lookup"><span data-stu-id="355b4-114">In the admin center, go to the **Settings** > **Org Settings** and choose **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="355b4-115">En la pestaña Perfil de la **organización** , elija **ventanas del iniciador de aplicaciones personalizadas**.</span><span class="sxs-lookup"><span data-stu-id="355b4-115">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="355b4-116">Seleccione **Agregar un icono personalizado**.</span><span class="sxs-lookup"><span data-stu-id="355b4-116">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="355b4-117">Escriba un **nombre de icono** para el nuevo icono.</span><span class="sxs-lookup"><span data-stu-id="355b4-117">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="355b4-118">El nombre aparecerá en el mosaico.</span><span class="sxs-lookup"><span data-stu-id="355b4-118">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="355b4-119">Escriba la **dirección URL del sitio web** del icono.</span><span class="sxs-lookup"><span data-stu-id="355b4-119">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="355b4-120">Esta es la ubicación a la que quiere que vayan los usuarios cuando seleccionen el icono en el iniciador de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="355b4-120">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="355b4-121">Use HTTPS en la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="355b4-121">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="355b4-122">Sugerencia: Si está creando un icono para un sitio de SharePoint, vaya a ese sitio, copie la dirección URL y péguelo aquí.</span><span class="sxs-lookup"><span data-stu-id="355b4-122">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="355b4-123">La dirección URL del sitio de grupo predeterminado tiene el siguiente aspecto:`https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="355b4-123">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="355b4-124">Escriba una **dirección URL de la imagen** para el icono.</span><span class="sxs-lookup"><span data-stu-id="355b4-124">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="355b4-125">La imagen aparece en la página Mis aplicaciones y en el iniciador de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="355b4-125">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="355b4-126">Sugerencia: la imagen debe ser de 60x60 píxeles y estar disponible para todos los usuarios de la organización sin necesidad de autenticación.</span><span class="sxs-lookup"><span data-stu-id="355b4-126">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="355b4-127">Introduzca una **Descripción** para el icono.</span><span class="sxs-lookup"><span data-stu-id="355b4-127">Enter a **Description** for the tile.</span></span> <span data-ttu-id="355b4-128">Verá esto cuando seleccione el icono en la página Mis aplicaciones y seleccione detalles de la **aplicación**.</span><span class="sxs-lookup"><span data-stu-id="355b4-128">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="355b4-129">Seleccione **Guardar cambios** para crear el icono personalizado.</span><span class="sxs-lookup"><span data-stu-id="355b4-129">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="355b4-130">El icono personalizado aparece en el iniciador de aplicaciones en la pestaña **Todas** para sus usuarios y usted.</span><span class="sxs-lookup"><span data-stu-id="355b4-130">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="355b4-131">Subir el icono al iniciador de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="355b4-131">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="355b4-132">Seleccione el icono del iniciador de aplicaciones y seleccione **todas las aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="355b4-132">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="355b4-133">Busque el nuevo icono de la aplicación, seleccione los puntos suspensivos y elija **anclar a iniciador**.</span><span class="sxs-lookup"><span data-stu-id="355b4-133">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="355b4-134">Si no ve el icono personalizado que se creó en los pasos anteriores, asegúrese de que tiene un buzón de Exchange Online asignado a usted y de que ha iniciado sesión en su buzón al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="355b4-134">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="355b4-135">Estos pasos son necesarios para los mosaicos personalizados en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="355b4-135">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="355b4-136">Tanto usted como sus usuarios deben realizar estos pasos para promover los iconos personalizados desde la página Mis aplicaciones al iniciador de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="355b4-136">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="355b4-137">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="355b4-137">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="355b4-138">En el centro de administración, vaya a la pestaña **configuración**  >  **org configuración**de  >  **Perfil de organización** </a> .</span><span class="sxs-lookup"><span data-stu-id="355b4-138">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile**</a> tab.</span></span>
    
2. <span data-ttu-id="355b4-139">En la página Perfil de la **organización** , junto a **Agregar iconos personalizados para la organización**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="355b4-139">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="355b4-140">Actualice el valor de los campos **Nombre del icono**, **Dirección URL**, **Descripción** o **Dirección URL de la imagen** para el icono personalizado (consulte la [Agregar un icono personalizado en el iniciador de aplicaciones](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="355b4-140">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="355b4-141">Seleccione **Update** \> **cerrar**actualización.</span><span class="sxs-lookup"><span data-stu-id="355b4-141">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="355b4-142">Para eliminar un icono personalizado, en la ventana **mosaicos personalizados** , seleccione el icono, seleccione **quitar**  >  **eliminación**de mosaico.</span><span class="sxs-lookup"><span data-stu-id="355b4-142">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="355b4-143">¿Cuál es el siguiente paso?</span><span class="sxs-lookup"><span data-stu-id="355b4-143">What's next?</span></span>

<span data-ttu-id="355b4-144">Además de agregar mosaicos al iniciador de aplicaciones, puede Agregar mosaicos del iniciador de aplicaciones a la barra de navegación ([más información](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span><span class="sxs-lookup"><span data-stu-id="355b4-144">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="355b4-145">Para personalizar la apariencia de Microsoft 365 de manera que se ajuste a la marca de su organización, vea [customize the Microsoft 365 Theme](../setup/customize-your-organization-theme.md).</span><span class="sxs-lookup"><span data-stu-id="355b4-145">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  

