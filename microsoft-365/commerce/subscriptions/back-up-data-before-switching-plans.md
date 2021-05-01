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
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
- PPM_jmueller
ms.reviewer: jkinma
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Copia Outlook, OneDrive, Yammer y SharePoint contenido antes de cambiar Microsoft 365 planes.
ms.date: 03/17/2021
ms.openlocfilehash: cdbeb7267105742082358dcd985e8fd1052a5679
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107429"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Copia de seguridad de datos antes de cambiar Microsoft 365 para planes empresariales

Si un usuario se cambia a otra suscripción que tiene menos servicios relacionados con datos o un usuario abandona la organización, se puede descargar una copia de sus datos almacenados en Microsoft 365 antes de cambiar a la nueva suscripción.

Si está moviendo un usuario a una suscripción que tiene los mismos o más servicios, no es necesario hacer una copia de seguridad de los datos de usuario. Consulta [Mover usuarios a una suscripción diferente.](./move-users-different-subscription.md)
  
## <a name="save-a-copy-of-outlook-information"></a>Guardar una copia de Outlook información

Si los usuarios Outlook, pueden exportar o hacer una copia de seguridad del correo electrónico, los contactos y el calendario en un archivo [.pst](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) Outlook antes de cambiar su plan.
  
Una vez finalizado el cambio al nuevo plan, los usuarios pueden importar correo electrónico, contactos y calendario desde un [Outlook archivo .pst](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac).
  
## <a name="save-files-stored-in-onedrive-for-business"></a>Guardar archivos almacenados en OneDrive para la Empresa

Antes de cambiar a una suscripción diferente, los usuarios pueden descargar archivos y carpetas de OneDrive o [SharePoint](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) en una ubicación diferente, como una carpeta en el disco duro del equipo o un recurso compartido de archivos en la red de la organización.
  
## <a name="save-yammer-information"></a>Guardar Yammer información

Los administradores pueden exportar todos los mensajes, notas, archivos, temas, usuarios y grupos a un .zip archivo. Para obtener más información, vea [Export data from Yammer Enterprise](/yammer/manage-security-and-compliance/export-yammer-enterprise-data). Los desarrolladores [también pueden usar Yammer API](https://go.microsoft.com/fwlink/p/?linkid=842495) para hacerlo.
  
## <a name="how-to-save-sharepoint-information"></a>Cómo guardar la SharePoint información

Si un usuario cambia de una suscripción que tiene SharePoint Online a una que no la tiene, el icono **de** SharePoint ya no aparecerá en su menú Microsoft 365 usuario.
  
Sin embargo, siempre y cuando la nueva suscripción esté dentro de la misma organización desde la que se cambia, los usuarios podrán acceder al sitio de SharePoint grupo. Pueden ver y actualizar blocs de notas, documentos, tareas y calendarios mediante la dirección URL directa al sitio de grupo.
  
> [!TIP]
> Se recomienda que los usuarios vayan al sitio de grupo antes de cambiar su suscripción y guarden la dirección URL como favorito o marcador en su explorador.
  
De forma predeterminada, la dirección URL del sitio web del equipo tiene este formato:
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

donde  _\<orgDomain\>_ está la dirección URL de la organización.
  
Por ejemplo, si el dominio de la organización contoso.onmicrosoft.com, la dirección URL directa al sitio de grupo sería `https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx` .
  
Por supuesto, los usuarios también pueden descargar SharePoint en línea desde el SharePoint de grupo a su equipo local o a otra ubicación en cualquier momento.