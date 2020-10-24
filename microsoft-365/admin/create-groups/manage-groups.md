---
title: Administrar un grupo en el centro de administración
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
ms.assetid: 74a1ef8b-3844-4d08-9980-9f8f7a36000f
description: Obtenga información sobre cómo administrar grupos de 365 de Microsoft, como agregar miembros de quitar grupos, editar la dirección de correo electrónico, el nombre de grupo o la descripción, y personalizar cómo funciona el grupo.
ms.openlocfilehash: 8216b80ba6cd6bffe470f4fe4ace43307afba5f2
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753306"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>Administrar un grupo en el centro de administración de 365 de Microsoft

Una vez que haya [creado un grupo de Microsoft 365](create-groups.md) y agregado miembros del grupo, puede configurar su grupo. Puede editar el nombre o la descripción del grupo, administrar propietarios o miembros y especificar si los remitentes externos pueden enviar un correo electrónico al grupo y si deben enviar copias de las conversaciones de grupo a los miembros.

Vaya al centro de administración de Microsoft 365 en [https://admin.microsoft.com](https://admin.microsoft.com) .

## <a name="edit-the-group-name-or-description"></a>Editar el nombre de grupo o la descripción

1. En el centro de administración, expanda **grupos**y, a continuación, haga clic en **grupos**.

2. Seleccione el grupo que desee editar y, a continuación, haga clic en **Editar nombre y descripción**.

3. Actualice el nombre y la descripción y, a continuación, seleccione **Guardar**.

## <a name="manage-group-owners-and-members"></a>Administrar miembros y propietarios de grupos

1. En el centro de administración, expanda **grupos**y, a continuación, haga clic en **grupos**.

2. Haga clic en el nombre del grupo que desea administrar para abrir el panel de configuración.

3. En la pestaña **miembros** , elija si desea administrar propietarios o miembros.

4. Elija **Agregar** para agregar a alguien o haga clic en **X** para quitar a alguien.

5. Haga clic en **Cerrar**.

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>Enviar copias de conversaciones a las bandejas de los miembros del grupo
  
Cuando se usa el centro de administración para crear un grupo, de forma predeterminada, los usuarios no obtienen copias de los correos electrónicos de grupo y las invitaciones a reuniones que se envían a sus bandejas de correo. Tendrá que ir al grupo para ver conversaciones y reuniones. Puede cambiar esta configuración en el centro de administración.

Al activar esta configuración, los miembros del grupo recibirán una copia de los correos electrónicos de grupo y las invitaciones a reuniones que se enviarán a la bandeja de entrada de Outlook. Pueden leer y eliminar dicha copia del correo electrónico sin afectar a otros usuarios. Se conserva una copia del correo electrónico en la bandeja de entrada del grupo.

Los miembros del grupo pueden optar por no recibir estos mensajes de correo electrónico si elige dejar de seguir el grupo en Outlook.

1. En el centro de administración, expanda **grupos**y, a continuación, haga clic en **grupos**.

2. Haga clic en el nombre del grupo que desea administrar para abrir el panel de configuración.

3. En la pestaña **configuración** , seleccione **enviar copias de conversaciones de grupo y eventos a miembros del grupo** si desea que los miembros reciban copias de los mensajes de grupo y los elementos de calendario en su propia bandeja de entrada.

4. Seleccione **Guardar**.

## <a name="let-people-outside-the-organization-email-the-group"></a>Permitir que los usuarios ajenos a la organización envíen un correo electrónico al grupo

Esta opción es fantástica si desea tener una dirección de correo electrónico de la compañía como info@contoso.com.
 
1. En el centro de administración, expanda **grupos**y, a continuación, haga clic en **grupos**.

2. Haga clic en el nombre del grupo que desea administrar para abrir el panel de configuración.

3. En la lista grupos del centro de administración, seleccione el nombre del grupo que desea cambiar y, a continuación, en la pestaña **configuración** , seleccione **permitir a los remitentes externos que envíen correo electrónico a este grupo**.
    
4. Seleccione **Guardar**.

## <a name="permanently-delete-a-microsoft-365-group"></a>Eliminar de forma permanente un grupo de 365 de Microsoft

A veces, es posible que desee purgar un grupo de forma permanente sin esperar a que expire el período de eliminación de software de 30 días. Para ello, inicie PowerShell y ejecute este comando para obtener el identificador de objeto del Grupo:
 
 ```powershell
`Get-AzureADMSDeletedGroup`
```

Anote el identificador de objeto del grupo o grupos que desea eliminar de forma permanente.
  
> [!CAUTION]
> Purgar el grupo elimina el grupo y sus datos para siempre. 
  
Para purgar el grupo, ejecute este comando en PowerShell:

```powershell
`Remove-AzureADMSDeletedDirectoryObject -Id <objectId>`
```

Para confirmar que el grupo se ha purgado correctamente, ejecute el cmdlet  *Get-AzureADMSDeletedGroup*  de nuevo para confirmar que el grupo ya no aparece en la lista de grupos eliminados temporalmente. En algunos casos, la eliminación permanente del grupo y todos sus datos puede tardar hasta 24 horas. 
  
## <a name="related-articles"></a>Artículos relacionados

[Crear un grupo de 365 de Microsoft](create-groups.md)

[Administrar el acceso de invitado a grupos de 365 de Microsoft](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Elegir el dominio que se va a usar al crear grupos de 365 de Microsoft](../../solutions/choose-domain-to-create-groups.md)

[Permitir que los miembros envíen como o envíen en nombre de un grupo de Microsoft 365](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[Actualizar listas de distribución a grupos de 365 de Microsoft](../manage/upgrade-distribution-lists.md)

[Administración de grupos de Microsoft 365 con PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
