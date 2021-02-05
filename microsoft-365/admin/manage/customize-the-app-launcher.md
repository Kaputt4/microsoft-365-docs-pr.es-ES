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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Cree vínculos rápidos a su correo electrónico, documentos, aplicaciones, sitios de SharePoint, sitios externos y otros recursos agregando iconos personalizados al iniciador de aplicaciones. '
ms.openlocfilehash: 96d059b252b63e48e20edb29861cf8233e220e34
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114194"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="85bac-103">Agregar iconos personalizados en el iniciador de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="85bac-103">Add custom tiles to the app launcher</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="85bac-104">El Centro de administración está cambiando.</span><span class="sxs-lookup"><span data-stu-id="85bac-104">The admin center is changing.</span></span> <span data-ttu-id="85bac-105">Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="85bac-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="85bac-106">En Microsoft 365, puede acceder rápida y fácilmente a su correo electrónico, calendarios, documentos y aplicaciones mediante el iniciador de aplicaciones[(más información).](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)</span><span class="sxs-lookup"><span data-stu-id="85bac-106">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="85bac-107">Estas son las aplicaciones que obtiene con Microsoft 365, así como las aplicaciones personalizadas que agrega desde la [Tienda SharePoint](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) o [Azure AD.](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)</span><span class="sxs-lookup"><span data-stu-id="85bac-107">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="85bac-p103">Puede agregar sus propios iconos en el iniciador de aplicaciones que apunten a sitios de SharePoint, sitios externos, aplicaciones heredadas y mucho más. El icono personalizado aparece en **Todas** las aplicaciones del iniciador de aplicaciones, pero puede anclarlo a las aplicaciones del **Inicio** e indicar a los usuarios que hagan lo mismo. Esto le facilitará la tarea de buscar los sitios, aplicaciones y recursos necesarios para realizar su trabajo. En el ejemplo siguiente, se usa un icono personalizado denominado "Contoso Portal" para obtener acceso a un sitio de intranet de SharePoint de la organización.</span><span class="sxs-lookup"><span data-stu-id="85bac-p103">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Iniciador de aplicaciones](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="85bac-113">Agregar un icono personalizado en el iniciador de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="85bac-113">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="85bac-114">Inicie sesión en el centro de administración como administrador global, vaya a Configuración de la organización y  >  elija la pestaña **Perfil de** la organización.</span><span class="sxs-lookup"><span data-stu-id="85bac-114">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="85bac-115">En la pestaña **Perfil de** organización, elija **Mosaicos personalizados del iniciador de aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="85bac-115">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="85bac-116">Seleccione **Agregar un icono personalizado.**</span><span class="sxs-lookup"><span data-stu-id="85bac-116">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="85bac-117">Escribe un **nombre de icono** para el nuevo icono.</span><span class="sxs-lookup"><span data-stu-id="85bac-117">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="85bac-118">El nombre aparecerá en el mosaico.</span><span class="sxs-lookup"><span data-stu-id="85bac-118">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="85bac-119">Escribe una **dirección URL del sitio web** para el icono.</span><span class="sxs-lookup"><span data-stu-id="85bac-119">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="85bac-120">Esta es la ubicación a la que quieres que vayan los usuarios cuando seleccionen el icono en el iniciador de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="85bac-120">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="85bac-121">Use HTTPS en la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="85bac-121">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="85bac-122">SUGERENCIA: Si va a crear un icono para un sitio de SharePoint, vaya a ese sitio, copie la dirección URL y péguela aquí.</span><span class="sxs-lookup"><span data-stu-id="85bac-122">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="85bac-123">La dirección URL del sitio de grupo predeterminado tiene este aspecto: `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="85bac-123">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="85bac-124">Escribe una **dirección URL de la imagen** para el icono.</span><span class="sxs-lookup"><span data-stu-id="85bac-124">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="85bac-125">La imagen aparece en la página Mis aplicaciones y en el iniciador de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="85bac-125">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="85bac-126">SUGERENCIA: La imagen debe ser de 60 x 60 píxeles y estar disponible para todos los usuarios de la organización sin necesidad de autenticación.</span><span class="sxs-lookup"><span data-stu-id="85bac-126">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="85bac-127">Introduzca una **Descripción** para el icono.</span><span class="sxs-lookup"><span data-stu-id="85bac-127">Enter a **Description** for the tile.</span></span> <span data-ttu-id="85bac-128">Verá esto cuando seleccione el icono en la página Mis aplicaciones y seleccione **Detalles de la aplicación.**</span><span class="sxs-lookup"><span data-stu-id="85bac-128">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="85bac-129">Selecciona **Guardar cambios** para crear el icono personalizado.</span><span class="sxs-lookup"><span data-stu-id="85bac-129">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="85bac-130">El icono personalizado aparece en el iniciador de aplicaciones en la pestaña **Todas** para sus usuarios y usted.</span><span class="sxs-lookup"><span data-stu-id="85bac-130">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="85bac-131">Promover el icono a la aplicación Selector</span><span class="sxs-lookup"><span data-stu-id="85bac-131">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="85bac-132">Seleccione el icono del iniciador de aplicaciones y seleccione **Todas las aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="85bac-132">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="85bac-133">Busque el nuevo icono de la aplicación, seleccione los puntos suspensivos y elija **Anclar al iniciador.**</span><span class="sxs-lookup"><span data-stu-id="85bac-133">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="85bac-134">Si no ve el icono personalizado que se creó en los pasos anteriores, asegúrese de que tiene un buzón de Exchange Online asignado a usted y de que ha iniciado sesión en su buzón al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="85bac-134">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="85bac-135">Estos pasos son necesarios para los iconos personalizados de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="85bac-135">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="85bac-136">Tanto usted como sus usuarios deben realizar estos pasos para promover los iconos personalizados desde la página Mis aplicaciones al iniciador de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="85bac-136">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="85bac-137">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="85bac-137">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="85bac-138">En el centro de administración, vaya a la **pestaña** Configuración del perfil de organización  >    >  **de configuración de la** </a> organización.</span><span class="sxs-lookup"><span data-stu-id="85bac-138">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile**</a> tab.</span></span>
    
2. <span data-ttu-id="85bac-139">En la **página Perfil de** la organización, junto a Agregar iconos   **personalizados para su organización,** seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="85bac-139">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="85bac-140">Actualice el valor de los campos **Nombre del icono**, **Dirección URL**, **Descripción** o **Dirección URL de la imagen** para el icono personalizado (consulte la [Agregar un icono personalizado en el iniciador de aplicaciones](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="85bac-140">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="85bac-141">Seleccione **Actualizar** \> **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="85bac-141">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="85bac-142">Para eliminar un icono personalizado, en la **ventana Mosaicos** personalizados, seleccione el icono, seleccione **Eliminar**  >  **icono.**</span><span class="sxs-lookup"><span data-stu-id="85bac-142">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="85bac-143">¿Cuál es el siguiente paso?</span><span class="sxs-lookup"><span data-stu-id="85bac-143">What's next?</span></span>

<span data-ttu-id="85bac-144">Además de agregar iconos al iniciador de aplicaciones, puedes agregar iconos del iniciador de aplicaciones a la barra de navegación[(más información).](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)</span><span class="sxs-lookup"><span data-stu-id="85bac-144">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="85bac-145">Para personalizar la apariencia de Microsoft 365 para que coincida con la marca de su organización, consulte Personalizar el tema [de Microsoft 365.](../setup/customize-your-organization-theme.md)</span><span class="sxs-lookup"><span data-stu-id="85bac-145">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  
