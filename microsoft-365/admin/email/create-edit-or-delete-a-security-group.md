---
title: Crear, editar o eliminar un grupo de seguridad en el Centro Microsoft 365 administración
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Aprenda a crear, editar o eliminar un grupo de seguridad.
ms.openlocfilehash: 7887a6371287ebef3a91cc1a37f2ed696df1948d
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624006"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a>Crear, editar o eliminar un grupo de seguridad en el Centro Microsoft 365 administración

En la página Microsoft 365 **grupos,** puede crear grupos de cuentas de usuario que pueda usar para asignar los mismos permisos en SharePoint Online y CRM Online. Por ejemplo, un administrador puede crear un grupo de seguridad para conceder a un determinado grupo de personas acceso a un SharePoint web. Solo los administradores de administración global y de usuario tienen permisos para crear, editar o eliminar grupos de seguridad; para obtener más información acerca de los roles de administrador, vea [Assigning admin roles](../add-users/assign-admin-roles.md). 
  
También hay [Grupos de Exchange Online y SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) que puede usar para enviar correo electrónico o asignar permisos a un grupo de usuarios y [Grupos de Exchange Online y SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) que conceden a los usuarios permisos y acceso a sitios y colecciones de sitios. 
  
> [!IMPORTANT]
>  ¿Tiene previsto usar buzones del sitio? Todos los usuarios que se agreguen a un sitio de SharePoint mediante un grupo de seguridad en lugar de individualmente podrán usar únicamente el buzón del sitio de SharePoint. No podrán acceder al buzón del sitio de Outlook. Para obtener más información, vea [Use Microsoft 365 Groups en lugar de Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b). 
  
## <a name="manage-security-groups-in-the-admin-center"></a>Administrar grupos de seguridad en el Centro de administración

### <a name="add-a-security-group"></a>Agregar un grupo de seguridad

1. En el centro Microsoft 365 administración, vaya a la página **Grupos.**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a>
  
2. En la **página Grupos,** seleccione **Agregar un grupo**.
    
3. En la **página Elegir un tipo de grupo,** elija **Seguridad**. 
    
4. Siga los pasos para completar la creación del grupo. 
 
### <a name="add-members-to-a-security-group"></a>Agregar miembros a un grupo de seguridad
    
1. Seleccione el nombre del grupo de seguridad en la **página Grupos** y, en la pestaña **Miembros,** seleccione **Ver todos y administrar miembros.** 
    
2. En el panel  de grupos, seleccione Agregar miembros y elija la persona de la  lista o escriba el nombre de la persona que desea agregar en el cuadro Búsqueda y, a continuación, **seleccione Guardar**.
    
    Para quitar miembros, seleccione la X junto a su nombre. 
  
### <a name="edit-a-security-group"></a>Editar un grupo de seguridad

1. En el Centro de administración, vaya a la **página Grupos.** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a>
  
2. En la **página** Grupos, seleccione el nombre del grupo. 
    
3. En el panel de configuración, seleccione la **pestaña General** o la **pestaña** Miembros para editar los detalles del grupo o los miembros.

### <a name="delete-a-security-group"></a>Eliminar un grupo de seguridad

1. En el Centro de administración, vaya a la **página Grupos.**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a>
    
2. En la **página** Grupos, seleccione el nombre del grupo. 
    
3. Seleccione **Eliminar grupo** (icono wasetbin) y, a continuación, confirme **seleccionando Eliminar**.
    
    Seleccione **Cerrar una** vez eliminado el grupo. 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a>Grupos de Exchange Online y SharePoint Online

Si desea crear grupos de usuarios para que pueda enviarles correo electrónico a todos al mismo tiempo,  puede hacerlo en el Centro de administración de Exchange yendo Exchange Grupos de destinatarios \>  \>  \> . A continuación, **seleccione Nuevo** ![ agregar y seleccione el tipo de grupo que desea ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) crear: 
  
- **Grupo de distribución**: se usa para distribuir mensajes a un grupo de usuarios. También se denomina grupo de *distribución habilitado* para correo o, una lista *de distribución.* Para más información, vea [Administrar grupos de distribución](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).
    
- **Grupo de seguridad**: se puede usar para distribuir mensajes a un grupo de usuarios o para conceder permisos de acceso a recursos. Este grupo también se denomina grupo *de seguridad habilitado para correo*. Para obtener más información, consulte [Administrar grupos de seguridad habilitados para correo](/Exchange/recipients/mail-enabled-security-groups).
    
- **Grupo de distribución dinámico**: un tipo de grupo de distribución cuya lista de destinatarios se vuelve a calcular cada vez que se envía un mensaje en función de filtros y condiciones definidos. Para obtener más información, vea [Administrar grupos de distribución dinámica](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).
    
Después de crear grupos de distribución y grupos de seguridad habilitados para correo en el centro de administración de Exchange, sus nombres y listas de usuarios aparecen en la **página Grupos de** seguridad. Puede eliminar estos grupos en ambas ubicaciones, pero solamente puede modificarlos en el Centro de administración de Exchange. Los grupos de distribución dinámicos no se muestran en la **página Grupos de** seguridad. 
  
 Los grupos de SharePoint se crean automáticamente al crear una colección de sitios. Los grupos predeterminados usan los niveles de permisos predeterminados de SharePoint (a veces llamados roles de SharePoint) para conceder permisos y acceso a los usuarios. Para obtener más información, vea [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a>¿En qué se diferencia un grupo de seguridad de los grupos de seguridad que creo en SharePoint?

Los grupos de seguridad se pueden usar SharePoint, Exchange, MDM, Windows y mucho más. Un grupo de seguridad que cree en SharePoint solo lo reconoce esa SharePoint de sitios.
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a>¿Tengo que usar grupos de seguridad para que mi organización sea segura?

No. Esta es solo una forma más de administrar la seguridad de su organización. Siempre puede conceder permisos de usuario y acceso a los sitios individualmente. Pero con los grupos de seguridad, puede administrar fácilmente grupos de usuarios más grandes.
  
## <a name="can-i-send-email-to-a-security-group"></a>¿Puedo enviar correo electrónico a un grupo de seguridad?

Sí. Pero si desea usar grupos para correo electrónico y colaboración, le recomendamos que cree un grupo Microsoft 365 en su [lugar.](../create-groups/create-groups.md) 

## <a name="related-content"></a>Contenido relacionado

[Crear un grupo en el Centro Microsoft 365 administración](../create-groups/create-groups.md) (artículo)\
[Explicar los Microsoft 365 a los usuarios](../create-groups/explain-groups-knowledge-worker.md) (artículo)\
[Administrar un grupo en el centro Microsoft 365 administración](../create-groups/manage-groups.md) (artículo)