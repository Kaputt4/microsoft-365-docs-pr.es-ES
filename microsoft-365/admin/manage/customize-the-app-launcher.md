---
title: Agregar iconos personalizados en el iniciador de aplicaciones
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: Cree vínculos rápidos a su correo electrónico, documentos, aplicaciones, sitios de SharePoint, sitios externos y otros recursos agregando iconos personalizados al iniciador de aplicaciones.
ms.openlocfilehash: b7e23f8f21ea99232f7051b0cbeaaad5ad699095
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68166755"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Agregar iconos personalizados en el iniciador de aplicaciones

En Microsoft 365, puede acceder rápida y fácilmente a su correo electrónico, calendarios, documentos y aplicaciones mediante el iniciador de aplicaciones ([más información](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)). Se trata de aplicaciones que se obtienen con Microsoft 365, así como aplicaciones personalizadas que se agregan desde la [Tienda SharePoint](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) o [Azure AD](/previous-versions/office/office-365-api/).
  
You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site. 
  
![Iniciador de aplicaciones](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Agregar un icono personalizado en el iniciador de aplicaciones

1. Inicie sesión en el centro de administración como administrador global, vaya a **Configuración** > **de la organización** y elija la pestaña **Perfil** de organización.
    
2. En la pestaña **Perfil de organización** , elija **Iconos del iniciador de aplicaciones personalizadas**.
  
3. Seleccione **Agregar un icono personalizado**. 
  
4. Escriba un **nombre de icono** para el nuevo icono. El nombre aparecerá en el mosaico. 
    
5. Escriba una **dirección URL del sitio web** para el icono. Esta es la ubicación a la que quiere que vayan los usuarios cuando seleccionen el icono en el iniciador de aplicaciones. Use HTTPS en la dirección URL.

    > [!TIP]
    > Si está creando un icono para un sitio de SharePoint, vaya a ese sitio, copie la dirección URL y péguela aquí. La dirección URL del sitio de equipo predeterminado tiene el siguiente aspecto: `https://<company_name>.sharepoint.com` 
  
6. Escriba una **dirección URL de la imagen** del icono. La imagen aparece en la página Mis aplicaciones y en el iniciador de aplicaciones.

    > [!TIP]
    > La imagen debe tener 60 x 60 píxeles y estar disponible para todos los usuarios de la organización sin necesidad de autenticación.

7. Introduzca una **Descripción** para el icono. Verá esto cuando seleccione el icono en la página Mis aplicaciones y seleccione **Detalles de la aplicación**. 
  
8. Seleccione **Guardar cambios** para crear el icono personalizado. 
    
    El icono personalizado aparecerá en las próximas 24 horas en el iniciador de aplicaciones de la pestaña **Todo** para usted y los usuarios. 

    > [!NOTE]
    > Si no ve el icono personalizado que se creó en los pasos anteriores, asegúrese de que tiene un buzón de Exchange Online asignado a usted y de que ha iniciado sesión en su buzón al menos una vez. Estos pasos son necesarios para los iconos personalizados de Microsoft 365. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. En el centro de administración, vaya a la pestaña **Configuración** > **de** >  la organización **Perfil de la organización**.
    
2. En la página **Perfil de la organización** , vaya a **Iconos del iniciador de aplicaciones personalizadas**, si selecciona los tres puntos junto al **icono personalizado** y seleccione **Editar icono personalizado**.

3. Actualice el valor de los campos **Nombre del icono**, **Dirección URL**, **Descripción** o **Dirección URL de la imagen** para el icono personalizado (consulte la [Agregar un icono personalizado en el iniciador de aplicaciones](#add-a-custom-tile-to-the-app-launcher)).
    
4. Seleccione **Actualizar** \> **cierre**. 
    
Para eliminar un icono personalizado, en la ventana **Iconos personalizados** , seleccione el icono y seleccione **Eliminar icono** > **Eliminar**. 
  
## <a name="next-steps"></a>Pasos siguientes

 Para personalizar la apariencia de Microsoft 365 para que coincida con la marca de su organización, consulte [Personalización del tema de Microsoft 365](../setup/customize-your-organization-theme.md).

## <a name="related-content"></a>Contenido relacionado

[Anclar aplicaciones al iniciador de aplicaciones de los usuarios](pin-apps-to-app-launcher.md) (artículo)\
[Actualice microsoft 365 para usuarios empresariales al cliente de Office más reciente](../setup/upgrade-users-to-latest-office-client.md) (artículo)\
[Administración de complementos en el Centro de administración](../manage/manage-addins-in-the-admin-center.md) (artículo)
