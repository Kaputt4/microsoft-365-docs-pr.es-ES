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
ms.openlocfilehash: ad6ef53a4a75f6ab8eb8bb66af4858c80fbc4596
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254985"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Agregar iconos personalizados en el iniciador de aplicaciones

En Office 365, puede obtener acceso de forma rápida y sencilla a su correo electrónico, calendarios, documentos y aplicaciones mediante el iniciador de aplicaciones de Office 365 ([más información](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). Estas son aplicaciones que se obtienen con Office 365, así como aplicaciones personalizadas que se agregan desde la [Tienda SharePoint](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) o [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).
  
Puede agregar sus propios iconos en el iniciador de aplicaciones que apunten a sitios de SharePoint, sitios externos, aplicaciones heredadas y mucho más. El icono personalizado aparece en **Todas** las aplicaciones del iniciador de aplicaciones, pero puede anclarlo a las aplicaciones del **Inicio** e indicar a los usuarios que hagan lo mismo. Esto le facilitará la tarea de buscar los sitios, aplicaciones y recursos necesarios para realizar su trabajo. En el ejemplo siguiente, se usa un icono personalizado denominado "Contoso Portal" para obtener acceso a un sitio de intranet de SharePoint de la organización. 
  
![Iniciador de aplicaciones de Office 365](../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Agregar un icono personalizado en el iniciador de aplicaciones

1. En el centro de administración, vaya a **configuración y elija la** > pestaña perfil**de la** **organización** .
    
2. En la pestaña Perfil de la **organización** , elija **ventanas del iniciador de aplicaciones personalizadas**.
  
3. Seleccione **Agregar un icono personalizado**. 
  
4. Escriba un **nombre de icono** para el nuevo icono. El nombre aparecerá en el mosaico. 
    
5. Escriba la **dirección URL del sitio web** del icono. Esta es la ubicación a la que quiere que vayan los usuarios cuando seleccionen el icono en el iniciador de aplicaciones. Use HTTPS en la dirección URL.<br/>Sugerencia: Si está creando un icono para un sitio de SharePoint, vaya a ese sitio, copie la dirección URL y péguelo aquí. La dirección URL del sitio de grupo predeterminado tiene el siguiente aspecto:`https://<company_name>.sharepoint.com` 
  
6. Escriba una **dirección URL de la imagen** para el icono. La imagen aparece en la página Mis aplicaciones y en el iniciador de aplicaciones.<br/>Sugerencia: la imagen debe ser de 60x60 píxeles y estar disponible para todos los usuarios de la organización sin necesidad de autenticación.

7. Introduzca una **Descripción** para el icono. Verá esto cuando seleccione el icono en la página Mis aplicaciones y seleccione detalles de la **aplicación**. 
  
8. Seleccione **Guardar cambios** para crear el icono personalizado. 
    
El icono personalizado aparece en el iniciador de aplicaciones en la pestaña **Todas** para sus usuarios y usted. 
  
## <a name="promote-the-tile-to-app-launcher"></a>Subir el icono al iniciador de aplicaciones

1. Seleccione el icono del iniciador de aplicaciones y seleccione **todas las aplicaciones**. 
    
2. Busque el nuevo icono de la aplicación, seleccione los puntos suspensivos y elija **anclar a iniciador**.
  
    > [!NOTE]
    > Si no ve el icono personalizado que se creó en los pasos anteriores, asegúrese de que tiene un buzón de Exchange Online asignado a usted y de que ha iniciado sesión en su buzón al menos una vez. Estos pasos son necesarios para iconos personalizados en Office 365. 
  
> [!IMPORTANT]
> Tanto usted como sus usuarios deben realizar estos pasos para promover los iconos personalizados desde la página Mis aplicaciones al iniciador de aplicaciones. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. En el centro de administración, vaya a la página **configuración** > del perfil de la<a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">organización</a> .
    
2. En la página Perfil de la **organización** , junto a **Agregar iconos personalizados para la organización**, seleccione **Editar**.

3. Actualice el valor de los campos **Nombre del icono**, **Dirección URL**, **Descripción** o **Dirección URL de la imagen** para el icono personalizado (consulte la [Agregar un icono personalizado en el iniciador de aplicaciones](#add-a-custom-tile-to-the-app-launcher)).
    
4. Seleccione **** \> **cerrar**actualización. 
    
Para eliminar un icono personalizado, en la ventana **mosaicos personalizados** , seleccione el icono, seleccione **quitar** > **eliminación**de mosaico. 
  
## <a name="whats-next"></a>?Cu?l es el siguiente paso?

Además de agregar iconos en el iniciador de aplicaciones, puede agregar iconos del iniciador de aplicaciones en la barra de navegación de Office 365 ([más información](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). Para personalizar la apariencia de Office 365 para que sea acorde a la marca de su organización, consulte [Personalizar el tema de Office 365](../setup/customize-your-organization-theme.md).
  

