---
title: Copia de seguridad de datos antes de cambiar de plan
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: mijeffer, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Copia de seguridad de contenido Outlook, OneDrive, Yammer y SharePoint antes de cambiar los planes de Microsoft 365.
ms.date: 03/17/2021
ms.openlocfilehash: fd5239deb88fbf9b87df7e62d85a3d2cc18e1df7
ms.sourcegitcommit: 3b194dd6f9ce531ae1b33d617ab45990d48bd3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "66102512"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Copia de seguridad de datos antes de cambiar Microsoft 365 para planes empresariales

Si un usuario cambiará a otra suscripción que tenga menos servicios relacionados con datos o un usuario deje la organización, se puede descargar una copia de sus datos almacenados en Microsoft 365 antes de cambiar a la nueva suscripción.

Si va a mover un usuario a una suscripción que tenga los mismos o más servicios, no es necesario realizar una copia de seguridad de los datos de usuario. Consulte [Traslado de usuarios a una suscripción diferente](./move-users-different-subscription.md).
  
## <a name="save-a-copy-of-outlook-information"></a>Guardar una copia de Outlook información

Si los usuarios tienen Outlook, pueden [exportar o hacer copias de seguridad de correo electrónico, contactos y calendario a un archivo .pst Outlook](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) antes de cambiar su plan.
  
Una vez finalizado el cambio al nuevo plan, los usuarios pueden [importar correo electrónico, contactos y calendario desde un archivo .pst Outlook](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac).
  
## <a name="save-files-stored-in-onedrive-for-business"></a>Guardar archivos almacenados en OneDrive para la Empresa

Antes de cambiar a una suscripción diferente, los usuarios pueden [descargar archivos y carpetas de OneDrive o SharePoint](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) a una ubicación diferente, como una carpeta en el disco duro de su equipo o un recurso compartido de archivos en la red de la organización.
  
## <a name="save-yammer-information"></a>Guardar información de Yammer

Los administradores pueden exportar todos los mensajes, notas, archivos, temas, usuarios y grupos a un archivo .zip. Para obtener más información, consulte [Exportación de datos desde Yammer Enterprise](/yammer/manage-security-and-compliance/export-yammer-enterprise-data). Los desarrolladores también pueden usar la [API de Yammer](https://go.microsoft.com/fwlink/p/?linkid=842495) para hacerlo.
  
## <a name="how-to-save-sharepoint-information"></a>Cómo guardar SharePoint información

Si un usuario cambia de una suscripción que tiene SharePoint En línea a una que no la tiene, el icono **de SharePoint** ya no aparecerá en su menú de Microsoft 365.
  
Sin embargo, siempre y cuando la nueva suscripción esté dentro de la misma organización de la que se ha cambiado, los usuarios podrán acceder al sitio de SharePoint equipo. Pueden ver y actualizar cuadernos, documentos, tareas y calendarios mediante la dirección URL directa al sitio del equipo.
  
> [!TIP]
> Se recomienda que los usuarios vayan al sitio del equipo antes de cambiar su suscripción y guarden la dirección URL como favorito o marcador en su explorador.
  
De forma predeterminada, la dirección URL del sitio web del equipo tiene este formato:
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

donde  _\<orgDomain\>_ es la dirección URL de la organización.
  
Por ejemplo, si el dominio de la organización está contoso.onmicrosoft.com, la dirección URL directa al sitio del equipo sería `https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx`.
  
Por supuesto, los usuarios también pueden descargar SharePoint documentos en línea desde el sitio del equipo SharePoint a su equipo local o a otra ubicación en cualquier momento.
