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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Cree vínculos rápidos a su correo electrónico, documentos, aplicaciones, sitios de SharePoint, sitios externos y otros recursos agregando mosaicos personalizados al iniciador de aplicaciones. '
ms.openlocfilehash: 65c8da7aa0cdb68f4bf32a52b21140413a38a69a
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361985"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="0770a-103">Agregar iconos personalizados en el iniciador de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0770a-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="0770a-p101">En Office 365, puede obtener acceso de forma rápida y sencilla a su correo electrónico, calendarios, documentos y aplicaciones mediante el iniciador de aplicaciones de Office 365 ([más información](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). Estas son aplicaciones que se obtienen con Office 365, así como aplicaciones personalizadas que se agregan desde la [Tienda SharePoint](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) o [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span><span class="sxs-lookup"><span data-stu-id="0770a-p101">In Office 365, you can quickly and easily get to your email, calendars, documents, and apps using the Office 365 app launcher ([learn more](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). These are apps you get with Office 365 as well as custom apps that you add from the [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="0770a-p102">Puede agregar sus propios iconos en el iniciador de aplicaciones que apunten a sitios de SharePoint, sitios externos, aplicaciones heredadas y mucho más. El icono personalizado aparece en **Todas** las aplicaciones del iniciador de aplicaciones, pero puede anclarlo a las aplicaciones del **Inicio** e indicar a los usuarios que hagan lo mismo. Esto le facilitará la tarea de buscar los sitios, aplicaciones y recursos necesarios para realizar su trabajo. En el ejemplo siguiente, se usa un icono personalizado denominado "Contoso Portal" para obtener acceso a un sitio de intranet de SharePoint de la organización.</span><span class="sxs-lookup"><span data-stu-id="0770a-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Iniciador de aplicaciones de Office 365](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="0770a-111">Agregar un icono personalizado en el iniciador de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0770a-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="0770a-112">En el centro de administración, vaya a **configuración y elija la** > pestaña perfil**de la** **organización** .</span><span class="sxs-lookup"><span data-stu-id="0770a-112">In the admin center, go to the **Settings** > **Settings** and choose **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="0770a-113">En la pestaña Perfil de la **organización** , elija **ventanas del iniciador de aplicaciones personalizadas**.</span><span class="sxs-lookup"><span data-stu-id="0770a-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="0770a-114">Seleccione **Agregar un icono personalizado**.</span><span class="sxs-lookup"><span data-stu-id="0770a-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="0770a-115">Escriba un **nombre de icono** para el nuevo icono.</span><span class="sxs-lookup"><span data-stu-id="0770a-115">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="0770a-116">El nombre aparecerá en el mosaico.</span><span class="sxs-lookup"><span data-stu-id="0770a-116">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="0770a-117">Escriba la **dirección URL del sitio web** del icono.</span><span class="sxs-lookup"><span data-stu-id="0770a-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="0770a-118">Esta es la ubicación a la que quiere que vayan los usuarios cuando seleccionen el icono en el iniciador de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0770a-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="0770a-119">Use HTTPS en la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="0770a-119">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="0770a-120">Sugerencia: Si está creando un icono para un sitio de SharePoint, vaya a ese sitio, copie la dirección URL y péguelo aquí.</span><span class="sxs-lookup"><span data-stu-id="0770a-120">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="0770a-121">La dirección URL del sitio de grupo predeterminado tiene el siguiente aspecto:`https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="0770a-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="0770a-122">Escriba una **dirección URL de la imagen** para el icono.</span><span class="sxs-lookup"><span data-stu-id="0770a-122">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="0770a-123">La imagen aparece en la página Mis aplicaciones y en el iniciador de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0770a-123">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="0770a-124">Sugerencia: la imagen debe ser de 60x60 píxeles y estar disponible para todos los usuarios de la organización sin necesidad de autenticación.</span><span class="sxs-lookup"><span data-stu-id="0770a-124">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="0770a-125">Introduzca una **Descripción** para el icono.</span><span class="sxs-lookup"><span data-stu-id="0770a-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="0770a-126">Verá esto cuando seleccione el icono en la página Mis aplicaciones y seleccione detalles de la **aplicación**.</span><span class="sxs-lookup"><span data-stu-id="0770a-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="0770a-127">Seleccione **Guardar cambios** para crear el icono personalizado.</span><span class="sxs-lookup"><span data-stu-id="0770a-127">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="0770a-128">El icono personalizado aparece en el iniciador de aplicaciones en la pestaña **Todas** para sus usuarios y usted.</span><span class="sxs-lookup"><span data-stu-id="0770a-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="0770a-129">Subir el icono al iniciador de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0770a-129">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="0770a-130">Seleccione el icono del iniciador de aplicaciones y seleccione **todas las aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="0770a-130">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="0770a-131">Busque el nuevo icono de la aplicación, seleccione los puntos suspensivos y elija **anclar a iniciador**.</span><span class="sxs-lookup"><span data-stu-id="0770a-131">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="0770a-p108">Si no ve el icono personalizado que se creó en los pasos anteriores, asegúrese de que tiene un buzón de Exchange Online asignado a usted y de que ha iniciado sesión en su buzón al menos una vez. Estos pasos son necesarios para iconos personalizados en Office 365.</span><span class="sxs-lookup"><span data-stu-id="0770a-p108">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once. These steps are required for custom tiles in Office 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0770a-134">Tanto usted como sus usuarios deben realizar estos pasos para promover los iconos personalizados desde la página Mis aplicaciones al iniciador de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0770a-134">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="0770a-135">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="0770a-135">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="0770a-136">En el centro de administración, vaya a la página **configuración** > del perfil de la<a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">organización</a> .</span><span class="sxs-lookup"><span data-stu-id="0770a-136">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">Organization profile</a> page.</span></span>
    
2. <span data-ttu-id="0770a-137">En la página Perfil de la **organización** , junto a **Agregar iconos personalizados para la organización**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0770a-137">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="0770a-138">Actualice el valor de los campos **Nombre del icono**, **Dirección URL**, **Descripción** o **Dirección URL de la imagen** para el icono personalizado (consulte la [Agregar un icono personalizado en el iniciador de aplicaciones](#add-a-custom-tile-to-the-app-launcher)).</span><span class="sxs-lookup"><span data-stu-id="0770a-138">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="0770a-139">Seleccione \*\*\*\* \> **cerrar**actualización.</span><span class="sxs-lookup"><span data-stu-id="0770a-139">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="0770a-140">Para eliminar un icono personalizado, en la ventana **mosaicos personalizados** , seleccione el icono, seleccione **quitar** > **eliminación**de mosaico.</span><span class="sxs-lookup"><span data-stu-id="0770a-140">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="0770a-141">?Cu?l es el siguiente paso?</span><span class="sxs-lookup"><span data-stu-id="0770a-141">What's next?</span></span>

<span data-ttu-id="0770a-p109">Además de agregar iconos en el iniciador de aplicaciones, puede agregar iconos del iniciador de aplicaciones en la barra de navegación de Office 365 ([más información](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). Para personalizar la apariencia de Office 365 para que sea acorde a la marca de su organización, consulte [Personalizar el tema de Office 365](../setup/customize-your-organization-theme.md).</span><span class="sxs-lookup"><span data-stu-id="0770a-p109">In addition to adding tiles to the app launcher, you can add app launcher tiles to the Office 365 navigation bar ([learn more](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). To customize the look and feel of Office 365 to match your organization's brand, see [Customize the Office 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  

