---
title: Copia de seguridad de datos antes de cambiar planes
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: a1da52c9-2167-4973-9e6d-492314a79b87
description: Copia de seguridad de contenido de Outlook, OneDrive, Yammer y SharePoint antes de cambiar los planes de Microsoft 365.
ms.openlocfilehash: ecfd17d779cbb39ff786b192f72621bc94677776
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860528"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Copia de seguridad de datos antes de cambiar los planes de Microsoft 365 para empresas

Si un usuario se cambia a otra suscripción que tiene menos servicios relacionados con datos o un usuario abandona la organización, se puede descargar una copia de sus datos almacenados en Microsoft 365 antes de cambiar a la nueva suscripción.

Si está moviendo un usuario a una suscripción que tiene los mismos o más servicios, no es necesario hacer una copia de seguridad de los datos de usuario. Consulta [Mover usuarios a una suscripción diferente.](./move-users-different-subscription.md)
  
## <a name="save-a-copy-of-outlook-information"></a>Guardar una copia de información de Outlook

Si los usuarios tienen Outlook, pueden exportar o hacer una copia de seguridad del correo electrónico, los contactos y el calendario a un archivo [.pst](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) de Outlook antes de cambiar su plan.
  
Una vez finalizado el cambio al nuevo plan, los usuarios pueden importar correo [electrónico, contactos y calendario desde un archivo .pst de Outlook.](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)
  
## <a name="save-files-stored-in-onedrive-for-business"></a>Guardar archivos almacenados en OneDrive para la Empresa

Antes de cambiar a una suscripción diferente, los usuarios pueden descargar archivos y carpetas de OneDrive o [SharePoint](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) en una ubicación diferente, como una carpeta en el disco duro de su equipo o un recurso compartido de archivos en la red de la organización.
  
## <a name="save-yammer-information"></a>Guardar información de Yammer

Los administradores pueden exportar todos los mensajes, notas, archivos, temas, usuarios y grupos a un archivo .zip. Para obtener más información, vea [Export data from Yammer Enterprise](/yammer/manage-security-and-compliance/export-yammer-enterprise-data). Los desarrolladores también pueden usar la API de [Yammer](https://go.microsoft.com/fwlink/p/?linkid=842495) para hacerlo.
  
## <a name="how-to-save-sharepoint-information"></a>Cómo guardar información de SharePoint

Si un usuario cambia de una suscripción que tiene SharePoint Online a una que no la tiene, el icono de **SharePoint** ya no aparecerá en su menú de Microsoft 365.
  
Sin embargo, mientras la nueva suscripción esté dentro de la misma organización desde la que se cambia, los usuarios podrán acceder al sitio de grupo de SharePoint. Pueden ver y actualizar blocs de notas, documentos, tareas y calendarios mediante la dirección URL directa al sitio de grupo.
  
> [!TIP]
> Se recomienda que los usuarios vayan al sitio de grupo antes de cambiar su suscripción y guarden la dirección URL como favorito o marcador en su explorador.
  
De forma predeterminada, la dirección URL del sitio web del equipo tiene este formato:
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

donde  _\<orgDomain\>_ está la dirección URL de la organización.
  
Por ejemplo, si el dominio de la organización contoso.onmicrosoft.com, la dirección URL directa al sitio de grupo sería `https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx` .
  
Por supuesto, los usuarios también pueden descargar documentos de SharePoint Online desde el sitio de grupo de SharePoint a su equipo local o a otra ubicación en cualquier momento.