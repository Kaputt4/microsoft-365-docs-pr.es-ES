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
ms.openlocfilehash: 598cfeb75fc811c87519c4479fa8fcab450466c3
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327215"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="df9c3-103">Agregar iconos personalizados en el iniciador de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="df9c3-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="df9c3-104">En Microsoft 365, puedes acceder rápida y fácilmente a tu correo electrónico, calendarios, documentos y aplicaciones con el iniciador de aplicaciones ([más información](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span><span class="sxs-lookup"><span data-stu-id="df9c3-104">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="df9c3-105">Se trata de aplicaciones que obtiene con Microsoft 365, así como aplicaciones personalizadas que se agregan desde la [Tienda SharePoint](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) o [Azure AD.](/previous-versions/office/office-365-api/)</span><span class="sxs-lookup"><span data-stu-id="df9c3-105">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](/previous-versions/office/office-365-api/).</span></span>
  
<span data-ttu-id="df9c3-p102">Puede agregar sus propios iconos en el iniciador de aplicaciones que apunten a sitios de SharePoint, sitios externos, aplicaciones heredadas y mucho más. El icono personalizado aparece en **Todas** las aplicaciones del iniciador de aplicaciones, pero puede anclarlo a las aplicaciones del **Inicio** e indicar a los usuarios que hagan lo mismo. Esto le facilitará la tarea de buscar los sitios, aplicaciones y recursos necesarios para realizar su trabajo. En el ejemplo siguiente, se usa un icono personalizado denominado "Contoso Portal" para obtener acceso a un sitio de intranet de SharePoint de la organización.</span><span class="sxs-lookup"><span data-stu-id="df9c3-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Iniciador de aplicaciones](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="df9c3-111">Agregar un icono personalizado en el iniciador de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="df9c3-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="df9c3-112">Inicie sesión en el Centro de administración como administrador global, vaya a Configuración de la organización  >  **Configuración** y elija la pestaña **Perfil de** la organización.</span><span class="sxs-lookup"><span data-stu-id="df9c3-112">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="df9c3-113">En la **pestaña Perfil de** la organización, elija Iconos del **iniciador de aplicaciones personalizados.**</span><span class="sxs-lookup"><span data-stu-id="df9c3-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="df9c3-114">Seleccione **Agregar un icono personalizado**.</span><span class="sxs-lookup"><span data-stu-id="df9c3-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="df9c3-p103">Introduzca un **Nombre de icono** para que aparezca en el nuevo icono.</span><span class="sxs-lookup"><span data-stu-id="df9c3-p103">Enter a **Tile name** for the new tile. The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="df9c3-117">Escriba una **dirección URL del sitio web** para el icono.</span><span class="sxs-lookup"><span data-stu-id="df9c3-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="df9c3-118">Esta es la ubicación en la que quieres que los usuarios vayan cuando seleccionen el icono en el iniciador de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="df9c3-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="df9c3-119">Use HTTPS en la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="df9c3-119">Use HTTPS in the URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="df9c3-120">Si está creando un icono para un sitio de SharePoint, vaya a ese sitio, copie la dirección URL y péguela aquí.</span><span class="sxs-lookup"><span data-stu-id="df9c3-120">If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="df9c3-121">La dirección URL del sitio de grupo predeterminado tiene este aspecto: `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="df9c3-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="df9c3-122">Escriba una **dirección URL de la imagen** para el icono.</span><span class="sxs-lookup"><span data-stu-id="df9c3-122">Enter a **URL of the image** for the tile.</span></span> <span data-ttu-id="df9c3-123">La imagen aparece en la página Mis aplicaciones y en el iniciador de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="df9c3-123">The image appears on the My apps page and app launcher.</span></span>

    > [!TIP]
    > <span data-ttu-id="df9c3-124">La imagen debe tener 60 x 60 píxeles y estar disponible para todos los usuarios de la organización sin necesidad de autenticación.</span><span class="sxs-lookup"><span data-stu-id="df9c3-124">The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="df9c3-125">Introduzca una **Descripción** para el icono.</span><span class="sxs-lookup"><span data-stu-id="df9c3-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="df9c3-126">Esto se ve cuando selecciona el icono en la página Mis aplicaciones y selecciona **Detalles de la aplicación.**</span><span class="sxs-lookup"><span data-stu-id="df9c3-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="df9c3-127">Seleccione **Guardar cambios** para crear el icono personalizado.</span><span class="sxs-lookup"><span data-stu-id="df9c3-127">Select **Save changes** to create the custom tile.</span></span> 
    
    <span data-ttu-id="df9c3-128">El icono personalizado aparece en el iniciador de aplicaciones en la pestaña **Todas** para sus usuarios y usted.</span><span class="sxs-lookup"><span data-stu-id="df9c3-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="df9c3-129">Si no ve el icono personalizado que se creó en los pasos anteriores, asegúrese de que tiene un buzón de Exchange Online asignado a usted y de que ha iniciado sesión en su buzón al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="df9c3-129">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="df9c3-130">Estos pasos son necesarios para iconos personalizados en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="df9c3-130">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="df9c3-131">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="df9c3-131">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="df9c3-132">En el Centro de administración, vaya a la pestaña **Configuración**  >  **de la organización** Configuración del perfil de  >  **la** organización.</span><span class="sxs-lookup"><span data-stu-id="df9c3-132">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="df9c3-133">En la **página Perfil de** la organización, junto a Agregar iconos   **personalizados para su organización,** seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="df9c3-133">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="df9c3-134">Actualice el valor de los campos **Nombre del icono**, **Dirección URL**, **Descripción** o **Dirección URL de la imagen** para el icono personalizado (consulte la [Agregar un icono personalizado en el iniciador de aplicaciones](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="df9c3-134">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="df9c3-135">Seleccione **Actualizar** \> **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="df9c3-135">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="df9c3-136">Para eliminar un icono personalizado, en la ventana Iconos **personalizados,** seleccione el icono, seleccione **Quitar icono**  >  **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="df9c3-136">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="df9c3-137">¿Cuál es el siguiente paso?</span><span class="sxs-lookup"><span data-stu-id="df9c3-137">What's next?</span></span>

<span data-ttu-id="df9c3-138">Además de agregar iconos al iniciador de aplicaciones, puedes agregar iconos del iniciador de aplicaciones a la barra de navegación ([más información](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span><span class="sxs-lookup"><span data-stu-id="df9c3-138">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="df9c3-139">Para personalizar la apariencia de Microsoft 365 para que coincida con la marca de su organización, vea Personalizar el tema [de Microsoft 365](../setup/customize-your-organization-theme.md).</span><span class="sxs-lookup"><span data-stu-id="df9c3-139">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>
