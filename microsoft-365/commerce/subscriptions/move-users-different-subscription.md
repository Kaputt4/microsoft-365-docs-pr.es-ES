---
title: Mover usuarios a una suscripción diferente
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: shegu, nicholak
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
- AdminSurgePortfolio
- manage_licenses
search.appverid: MET150
description: Obtenga información sobre cómo mover usuarios entre suscripciones.
ms.date: 05/12/2022
ms.openlocfilehash: 230996448d333076d150a0ff051f268e72d55363
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68719456"
---
# <a name="move-users-to-a-different-subscription"></a>Mover usuarios a una suscripción diferente

Si tiene más de un producto, tiene usuarios con una licencia para un producto, pero quiere moverlos a otro producto, puede reemplazar su licencia existente por otra diferente.

## <a name="before-you-begin"></a>Antes de empezar

Debe ser un administrador global, de licencia o de usuarios para asignar licencias. Para obtener más información, consulte [Acerca de los roles de administrador de Microsoft 365](../../admin/add-users/about-admin-roles.md).

## <a name="move-users-to-a-different-subscription"></a>Mover usuarios a una suscripción diferente

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

2. Active las casillas situadas junto a los nombres de los usuarios para los que desea reemplazar las licencias existentes.

3. En la parte superior, seleccione **Administrar licencias de producto**.

4. En el panel **Administrar licencias de producto** , seleccione **Reemplazar**  y seleccione las licencias que desea asignar a los usuarios.

5. En la parte inferior, seleccione **Guardar cambios** \> **Cerrar**.

## <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Copia de seguridad de datos antes de cambiar Microsoft 365 para planes empresariales

Si un usuario cambiará a otra suscripción que tenga menos servicios relacionados con datos o un usuario deje la organización, puede descargar una copia de sus datos almacenados en Microsoft 365 antes de cambiar a la nueva suscripción.

Si va a mover un usuario a una suscripción que tenga los mismos o más servicios, no es necesario realizar una copia de seguridad de los datos de usuario.
  
### <a name="save-a-copy-of-outlook-information"></a>Guardar una copia de la información de Outlook

Si los usuarios tienen Outlook, pueden [exportar o hacer copias de seguridad de correo electrónico, contactos y calendario a un archivo .pst de Outlook](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) antes de cambiar su plan.
  
Una vez finalizado el cambio al nuevo plan, los usuarios pueden [importar correo electrónico, contactos y calendario desde un archivo .pst de Outlook](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac).
  
### <a name="save-files-stored-in-onedrive-for-business"></a>Guardar archivos almacenados en OneDrive para la Empresa

Antes de cambiar a una suscripción diferente, los usuarios pueden [descargar archivos y carpetas de OneDrive o SharePoint](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) en una ubicación diferente, como una carpeta en el disco duro de su equipo o un recurso compartido de archivos en la red de la organización.
  
### <a name="save-yammer-information"></a>Guardar información de Yammer

Los administradores pueden exportar todos los mensajes, notas, archivos, temas, usuarios y grupos a un archivo .zip. Para obtener más información, consulte [Exportación de datos desde Yammer Enterprise](/yammer/manage-security-and-compliance/export-yammer-enterprise-data). Los desarrolladores también pueden usar la [API de Yammer](https://go.microsoft.com/fwlink/p/?linkid=842495) para hacerlo.
  
### <a name="how-to-save-sharepoint-information"></a>Cómo guardar información de SharePoint

Si un usuario cambia de una suscripción que tiene SharePoint Online a una que no la tiene, el icono de **SharePoint** ya no aparece en su menú de Microsoft 365.
  
Sin embargo, siempre que la nueva suscripción esté dentro de la misma organización de la que se cambia, los usuarios pueden acceder al sitio del equipo de SharePoint. Pueden ver y actualizar cuadernos, documentos, tareas y calendarios mediante la dirección URL directa al sitio del equipo.
  
> [!TIP]
> Se recomienda que los usuarios vayan al sitio del equipo antes de cambiar su suscripción y guarden la dirección URL como favorito o marcador en su explorador.
  
De forma predeterminada, la dirección URL del sitio web del equipo tiene este formato:
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

donde  _\<orgDomain\>_ es la dirección URL de la organización.
  
Por ejemplo, si el dominio de la organización está contoso.onmicrosoft.com, la dirección URL directa al sitio del equipo sería `https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx`.
  
Por supuesto, los usuarios también pueden descargar documentos de SharePoint Online desde el sitio del equipo de SharePoint a su equipo local o a otra ubicación en cualquier momento.

## <a name="next-steps"></a>Pasos siguientes

Si no va a [reasignar las licencias sin usar a otros usuarios](../../managed-desktop/get-started/assign-licenses.md), considere la posibilidad [de quitar las licencias de la suscripción](../../commerce/licenses/buy-licenses.md) para que no pague más licencias de las que necesita.

## <a name="related-content"></a>Contenido relacionado

[Asignar licencias a los usuarios](../../admin/manage/assign-licenses-to-users.md) (artículo)\
[Quitar licencias de la suscripción](../licenses/buy-licenses.md) (artículo)\
[Cambiar los planes manualmente](change-plans-manually.md) (artículo)\
[Descripción de las suscripciones y licencias en Microsoft 365 para empresas](../licenses/subscriptions-and-licenses.md) (artículo)\
[Comprar otra suscripción de Microsoft 365 para empresas](../try-or-buy-microsoft-365.md) (artículo)
