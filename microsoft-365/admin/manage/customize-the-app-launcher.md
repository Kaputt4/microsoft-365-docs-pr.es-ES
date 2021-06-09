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
description: Crea vínculos rápidos a tu correo electrónico, documentos, aplicaciones, sitios SharePoint, sitios externos y otros recursos agregando iconos personalizados al iniciador de aplicaciones.
ms.openlocfilehash: 47f871d66f180225e877a521ef159fc745960507
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623778"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="f3107-103">Agregar iconos personalizados en el iniciador de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f3107-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="f3107-104">En Microsoft 365, puedes acceder rápida y fácilmente a tu correo electrónico, calendarios, documentos y aplicaciones con el iniciador de aplicaciones ([más información](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span><span class="sxs-lookup"><span data-stu-id="f3107-104">In Microsoft 365, you can quickly and easily get to your email, calendars, documents, and apps using the App launcher ([learn more](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)).</span></span> <span data-ttu-id="f3107-105">Estas son aplicaciones que obtienes con Microsoft 365 aplicaciones personalizadas que agregas desde SharePoint [Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) o [Azure AD](/previous-versions/office/office-365-api/).</span><span class="sxs-lookup"><span data-stu-id="f3107-105">These are apps you get with Microsoft 365 as well as custom apps that you add from the [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) or [Azure AD](/previous-versions/office/office-365-api/).</span></span>
  
<span data-ttu-id="f3107-p102">Puede agregar sus propios iconos en el iniciador de aplicaciones que apunten a sitios de SharePoint, sitios externos, aplicaciones heredadas y mucho más. El icono personalizado aparece en **Todas** las aplicaciones del iniciador de aplicaciones, pero puede anclarlo a las aplicaciones del **Inicio** e indicar a los usuarios que hagan lo mismo. Esto le facilitará la tarea de buscar los sitios, aplicaciones y recursos necesarios para realizar su trabajo. En el ejemplo siguiente, se usa un icono personalizado denominado "Contoso Portal" para obtener acceso a un sitio de intranet de SharePoint de la organización.</span><span class="sxs-lookup"><span data-stu-id="f3107-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Iniciador de aplicaciones](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="f3107-111">Agregar un icono personalizado en el iniciador de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f3107-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="f3107-112">Inicie sesión en el Centro de administración como administrador global, vaya a Configuración Org Configuración y elija la pestaña  >   **Perfil de** la organización.</span><span class="sxs-lookup"><span data-stu-id="f3107-112">Sign in to the admin center as a Global Administrator, go to **Settings** > **Org Settings**, and choose the **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="f3107-113">En la **pestaña Perfil de** la organización, elija Iconos del **iniciador de aplicaciones personalizados.**</span><span class="sxs-lookup"><span data-stu-id="f3107-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="f3107-114">Seleccione **Agregar un icono personalizado**.</span><span class="sxs-lookup"><span data-stu-id="f3107-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="f3107-p103">Introduzca un **Nombre de icono** para que aparezca en el nuevo icono.</span><span class="sxs-lookup"><span data-stu-id="f3107-p103">Enter a **Tile name** for the new tile. The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="f3107-117">Escriba una **dirección URL del sitio web** para el icono.</span><span class="sxs-lookup"><span data-stu-id="f3107-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="f3107-118">Esta es la ubicación en la que quieres que los usuarios vayan cuando seleccionen el icono en el iniciador de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f3107-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="f3107-119">Use HTTPS en la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="f3107-119">Use HTTPS in the URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="f3107-120">Si está creando un icono para un sitio de SharePoint, vaya a ese sitio, copie la dirección URL y péguela aquí.</span><span class="sxs-lookup"><span data-stu-id="f3107-120">If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="f3107-121">La dirección URL del sitio de grupo predeterminado tiene este aspecto: `https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="f3107-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="f3107-122">Escriba una **dirección URL de la imagen** para el icono.</span><span class="sxs-lookup"><span data-stu-id="f3107-122">Enter a **URL of the image** for the tile.</span></span> <span data-ttu-id="f3107-123">La imagen aparece en la página Mis aplicaciones y en el iniciador de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f3107-123">The image appears on the My apps page and app launcher.</span></span>

    > [!TIP]
    > <span data-ttu-id="f3107-124">La imagen debe tener 60 x 60 píxeles y estar disponible para todos los usuarios de la organización sin necesidad de autenticación.</span><span class="sxs-lookup"><span data-stu-id="f3107-124">The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="f3107-125">Introduzca una **Descripción** para el icono.</span><span class="sxs-lookup"><span data-stu-id="f3107-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="f3107-126">Esto se ve cuando selecciona el icono en la página Mis aplicaciones y selecciona **Detalles de la aplicación.**</span><span class="sxs-lookup"><span data-stu-id="f3107-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="f3107-127">Seleccione **Guardar cambios** para crear el icono personalizado.</span><span class="sxs-lookup"><span data-stu-id="f3107-127">Select **Save changes** to create the custom tile.</span></span> 
    
    <span data-ttu-id="f3107-128">El icono personalizado aparece en el iniciador de aplicaciones en la pestaña **Todas** para sus usuarios y usted.</span><span class="sxs-lookup"><span data-stu-id="f3107-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="f3107-129">Si no ve el icono personalizado que se creó en los pasos anteriores, asegúrese de que tiene un buzón de Exchange Online asignado a usted y de que ha iniciado sesión en su buzón al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="f3107-129">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once.</span></span> <span data-ttu-id="f3107-130">Estos pasos son necesarios para los iconos personalizados de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3107-130">These steps are required for custom tiles in Microsoft 365.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="f3107-131">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="f3107-131">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="f3107-132">En el Centro de administración, vaya a la **pestaña Configuración**  >  **Organización Configuración** perfil de  >  **la** organización.</span><span class="sxs-lookup"><span data-stu-id="f3107-132">In the admin center, go to the **Settings** > **Org Settings** > **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="f3107-133">En la **página Perfil de** la organización, junto a Agregar iconos   **personalizados para su organización,** seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f3107-133">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="f3107-134">Actualice el valor de los campos **Nombre del icono**, **Dirección URL**, **Descripción** o **Dirección URL de la imagen** para el icono personalizado (consulte la [Agregar un icono personalizado en el iniciador de aplicaciones](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="f3107-134">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="f3107-135">Seleccione **Actualizar** \> **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f3107-135">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="f3107-136">Para eliminar un icono personalizado, en la ventana Iconos **personalizados,** seleccione el icono, seleccione **Quitar icono**  >  **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="f3107-136">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="f3107-137">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f3107-137">Next steps</span></span>

<span data-ttu-id="f3107-138">Además de agregar iconos al iniciador de aplicaciones, puedes agregar iconos del iniciador de aplicaciones a la barra de navegación ([más información](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span><span class="sxs-lookup"><span data-stu-id="f3107-138">In addition to adding tiles to the app launcher, you can add app launcher tiles to the navigation bar ([learn more](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)).</span></span> <span data-ttu-id="f3107-139">Para personalizar el aspecto de Microsoft 365 para que coincida con la marca de su [organización,](../setup/customize-your-organization-theme.md)vea Personalizar el Microsoft 365 tema .</span><span class="sxs-lookup"><span data-stu-id="f3107-139">To customize the look and feel of Microsoft 365 to match your organization's brand, see [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="f3107-140">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="f3107-140">Related content</span></span>

<span data-ttu-id="f3107-141">[Anclar aplicaciones al iniciador de aplicaciones](pin-apps-to-app-launcher.md) de los usuarios (artículo)</span><span class="sxs-lookup"><span data-stu-id="f3107-141">[Pin apps to your users' app launcher](pin-apps-to-app-launcher.md) (article)</span></span>\
<span data-ttu-id="f3107-142">[Actualice su Microsoft 365 usuarios empresariales al último Office cliente](../setup/upgrade-users-to-latest-office-client.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="f3107-142">[Upgrade your Microsoft 365 for business users to the latest Office client](../setup/upgrade-users-to-latest-office-client.md) (article)</span></span>\
<span data-ttu-id="f3107-143">[Administrar complementos en el Centro de administración](../manage/manage-addins-in-the-admin-center.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="f3107-143">[Manage add-ins in the admin center](../manage/manage-addins-in-the-admin-center.md) (article)</span></span>
