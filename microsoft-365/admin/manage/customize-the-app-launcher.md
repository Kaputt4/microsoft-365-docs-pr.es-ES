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
ms.localizationpriority: medium
ms.collection:
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
description: Crea vínculos rápidos a tu correo electrónico, documentos, aplicaciones, sitios SharePoint, sitios externos y otros recursos agregando iconos personalizados al iniciador de aplicaciones.
ms.openlocfilehash: 18438aa97cc8956a9d38ed3a5f3851a4c8c31e96
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60164397"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Agregar iconos personalizados en el iniciador de aplicaciones

En Microsoft 365, puedes acceder rápida y fácilmente a tu correo electrónico, calendarios, documentos y aplicaciones con el iniciador de aplicaciones ([más información](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)). Estas son aplicaciones que obtienes con Microsoft 365 aplicaciones personalizadas que agregas desde SharePoint [Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) o [Azure AD](/previous-versions/office/office-365-api/).
  
Puede agregar sus propios iconos en el iniciador de aplicaciones que apunten a sitios de SharePoint, sitios externos, aplicaciones heredadas y mucho más. El icono personalizado aparece en **Todas** las aplicaciones del iniciador de aplicaciones, pero puede anclarlo a las aplicaciones del **Inicio** e indicar a los usuarios que hagan lo mismo. Esto le facilitará la tarea de buscar los sitios, aplicaciones y recursos necesarios para realizar su trabajo. En el ejemplo siguiente, se usa un icono personalizado denominado "Contoso Portal" para obtener acceso a un sitio de intranet de SharePoint de la organización. 
  
![Iniciador de aplicaciones](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Agregar un icono personalizado en el iniciador de aplicaciones

1. Inicie sesión en el Centro de administración como administrador global, vaya a Configuración Org Configuración y elija la pestaña  >   **Perfil de** la organización.
    
2. En la **pestaña Perfil de** la organización, elija Iconos del **iniciador de aplicaciones personalizados.**
  
3. Seleccione **Agregar un icono personalizado**. 
  
4. Introduzca un **Nombre de icono** para que aparezca en el nuevo icono. 
    
5. Escriba una **dirección URL del sitio web** para el icono. Esta es la ubicación en la que quieres que los usuarios vayan cuando seleccionen el icono en el iniciador de aplicaciones. Use HTTPS en la dirección URL.

    > [!TIP]
    > Si está creando un icono para un sitio de SharePoint, vaya a ese sitio, copie la dirección URL y péguela aquí. La dirección URL del sitio de grupo predeterminado tiene este aspecto: `https://<company_name>.sharepoint.com` 
  
6. Escriba una **dirección URL de la imagen** para el icono. La imagen aparece en la página Mis aplicaciones y en el iniciador de aplicaciones.

    > [!TIP]
    > La imagen debe tener 60 x 60 píxeles y estar disponible para todos los usuarios de la organización sin necesidad de autenticación.

7. Introduzca una **Descripción** para el icono. Esto se ve cuando selecciona el icono en la página Mis aplicaciones y selecciona **Detalles de la aplicación.** 
  
8. Seleccione **Guardar cambios** para crear el icono personalizado. 
    
    El icono personalizado aparece en el iniciador de aplicaciones en la pestaña **Todas** para sus usuarios y usted. 

    > [!NOTE]
    > Si no ve el icono personalizado que se creó en los pasos anteriores, asegúrese de que tiene un buzón de Exchange Online asignado a usted y de que ha iniciado sesión en su buzón al menos una vez. Estos pasos son necesarios para los iconos personalizados de Microsoft 365. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. En el Centro de administración, vaya a la **pestaña Configuración**  >  **Organización Configuración** perfil de  >  **la** organización.
    
2. En la **página Perfil de** la organización, junto a Agregar iconos   **personalizados para su organización,** seleccione **Editar**.

3. Actualice el valor de los campos **Nombre del icono**, **Dirección URL**, **Descripción** o **Dirección URL de la imagen** para el icono personalizado (consulte la [Agregar un icono personalizado en el iniciador de aplicaciones](#add-a-custom-tile-to-the-app-launcher)).
    
4. Seleccione **Actualizar** \> **cerrar**. 
    
Para eliminar un icono personalizado, en la ventana Iconos **personalizados,** seleccione el icono, seleccione **Quitar icono**  >  **Eliminar**. 
  
## <a name="next-steps"></a>Siguientes pasos

Además de agregar iconos al iniciador de aplicaciones, puedes agregar iconos del iniciador de aplicaciones a la barra de navegación ([más información](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)). Para personalizar el aspecto de Microsoft 365 para que coincida con la marca de su [organización,](../setup/customize-your-organization-theme.md)vea Personalizar el Microsoft 365 tema .

## <a name="related-content"></a>Contenido relacionado

[Anclar aplicaciones al iniciador de aplicaciones](pin-apps-to-app-launcher.md) de los usuarios (artículo)\
[Actualice su Microsoft 365 usuarios empresariales al último Office cliente](../setup/upgrade-users-to-latest-office-client.md) (artículo)\
[Administrar complementos en el Centro de administración](../manage/manage-addins-in-the-admin-center.md) (artículo)
