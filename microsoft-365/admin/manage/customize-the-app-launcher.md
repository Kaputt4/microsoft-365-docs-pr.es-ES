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
ms.openlocfilehash: 2bbcf64b807754aed199c441f6df028d5fe20a97
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926239"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Agregar iconos personalizados en el iniciador de aplicaciones

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

En Microsoft 365, puede acceder rápida y fácilmente a su correo electrónico, calendarios, documentos y aplicaciones mediante el iniciador de aplicaciones[(más información).](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) Estas son las aplicaciones que obtiene con Microsoft 365, así como las aplicaciones personalizadas que agrega desde la [Tienda SharePoint](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) o [Azure AD.](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)
  
Puede agregar sus propios iconos en el iniciador de aplicaciones que apunten a sitios de SharePoint, sitios externos, aplicaciones heredadas y mucho más. El icono personalizado aparece en **Todas** las aplicaciones del iniciador de aplicaciones, pero puede anclarlo a las aplicaciones del **Inicio** e indicar a los usuarios que hagan lo mismo. Esto le facilitará la tarea de buscar los sitios, aplicaciones y recursos necesarios para realizar su trabajo. En el ejemplo siguiente, se usa un icono personalizado denominado "Contoso Portal" para obtener acceso a un sitio de intranet de SharePoint de la organización. 
  
![Iniciador de aplicaciones](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Agregar un icono personalizado en el iniciador de aplicaciones

1. Inicie sesión en el centro de administración como administrador global, vaya a Configuración de la organización  >  y elija la pestaña **Perfil de** la organización.
    
2. En la pestaña **Perfil de** organización, elija **Mosaicos personalizados del iniciador de aplicaciones.**
  
3. Seleccione **Agregar un icono personalizado.** 
  
4. Escribe un **nombre de icono** para el nuevo icono. El nombre aparecerá en el mosaico. 
    
5. Escribe una **dirección URL del sitio web** para el icono. Esta es la ubicación a la que quieres que vayan los usuarios cuando seleccionen el icono en el iniciador de aplicaciones. Use HTTPS en la dirección URL.<br/>SUGERENCIA: Si va a crear un icono para un sitio de SharePoint, vaya a ese sitio, copie la dirección URL y péguela aquí. La dirección URL del sitio de grupo predeterminado tiene este aspecto: `https://<company_name>.sharepoint.com` 
  
6. Escribe una **dirección URL de la imagen** para el icono. La imagen aparece en la página Mis aplicaciones y en el iniciador de aplicaciones.<br/>SUGERENCIA: La imagen debe ser de 60 x 60 píxeles y estar disponible para todos los usuarios de la organización sin necesidad de autenticación.

7. Introduzca una **Descripción** para el icono. Verá esto cuando seleccione el icono en la página Mis aplicaciones y seleccione **Detalles de la aplicación.** 
  
8. Selecciona **Guardar cambios** para crear el icono personalizado. 
    
El icono personalizado aparece en el iniciador de aplicaciones en la pestaña **Todas** para sus usuarios y usted. 
  
## <a name="promote-the-tile-to-app-launcher"></a>Promover el icono a la aplicación Selector

1. Seleccione el icono del iniciador de aplicaciones y seleccione **Todas las aplicaciones.** 
    
2. Busque el nuevo icono de la aplicación, seleccione los puntos suspensivos y elija **Anclar al iniciador.**
  
    > [!NOTE]
    > Si no ve el icono personalizado que se creó en los pasos anteriores, asegúrese de que tiene un buzón de Exchange Online asignado a usted y de que ha iniciado sesión en su buzón al menos una vez. Estos pasos son necesarios para los iconos personalizados de Microsoft 365. 
  
> [!IMPORTANT]
> Tanto usted como sus usuarios deben realizar estos pasos para promover los iconos personalizados desde la página Mis aplicaciones al iniciador de aplicaciones. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. En el centro de administración, vaya a la **pestaña** Configuración de la organización de  >  **configuración**  >  **de la organización.** </a>
    
2. En la **página Perfil de** la organización, junto a Agregar iconos   **personalizados para su organización,** seleccione **Editar**.

3. Actualice el valor de los campos **Nombre del icono**, **Dirección URL**, **Descripción** o **Dirección URL de la imagen** para el icono personalizado (consulte la [Agregar un icono personalizado en el iniciador de aplicaciones](#add-a-custom-tile-to-the-app-launcher)).
    
4. Seleccione **Actualizar** \> **cerrar**. 
    
Para eliminar un icono personalizado, en la **ventana Mosaicos** personalizados, seleccione el icono, **seleccione Eliminar**  >  **icono.** 
  
## <a name="whats-next"></a>¿Cuál es el siguiente paso?

Además de agregar iconos al iniciador de aplicaciones, puedes agregar iconos del iniciador de aplicaciones a la barra de navegación[(más información).](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985) Para personalizar la apariencia de Microsoft 365 para que coincida con la marca de su organización, consulte Personalizar el tema [de Microsoft 365.](../setup/customize-your-organization-theme.md)
  
