---
title: Administración de un grupo en el centro de administración
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.custom: admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 74a1ef8b-3844-4d08-9980-9f8f7a36000f
description: Aprenda a administrar Grupos de Microsoft 365, incluida la adición de quitar miembros del grupo, la edición de la dirección de correo electrónico, el nombre del grupo o la descripción y la personalización del funcionamiento del grupo.
ms.openlocfilehash: 89acd3c8b4935b4b57873d9d8b2cf7786a430e78
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68206969"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>Administración de un grupo en el Centro de administración de Microsoft 365

Después de [crear un grupo de Microsoft 365](create-groups.md) y agregar miembros del grupo, puede configurarlo. Puede editar el nombre o la descripción del grupo, administrar propietarios o miembros y especificar si los remitentes externos pueden enviar por correo electrónico al grupo y si enviar copias de las conversaciones del grupo a los miembros.

Vaya a la Centro de administración de Microsoft 365 en [https://admin.microsoft.com](https://admin.microsoft.com).

## <a name="edit-the-group-name-or-description"></a>Editar el nombre o la descripción del grupo

1. En el Centro de administración, expanda **Gruposy**, a continuación, haga clic en <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**Grupos**</a>.

2. Seleccione el grupo que desea editar y, a continuación, haga clic en **Editar nombre y descripción**.

3. Actualice el nombre y la descripción y, a continuación, seleccione **Guardar**.

## <a name="manage-group-owners-and-members"></a>Administración de propietarios y miembros del grupo

1. En el Centro de administración, expanda **Gruposy**, a continuación, haga clic en <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**Grupos**</a>.

2. Haga clic en el nombre del grupo que desea administrar para abrir el panel de configuración.

3. En la pestaña **Miembros** , elija si desea administrar propietarios o miembros.

4. Elija **Agregar** para agregar a alguien o haga clic en **X** para quitar a alguien.

5. Haga clic en **Cerrar**.

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>Envío de copias de conversaciones a las bandejas de entrada de los miembros del grupo
  
Cuando se usa el Centro de administración para crear un grupo, de forma predeterminada los usuarios no obtienen copias de los correos electrónicos de grupo enviados a sus bandejas de entrada, aunque los usuarios reciben copias de invitaciones a reuniones de grupo enviadas a sus bandejas de entrada. Tendrán que ir al grupo para ver las conversaciones. Puede cambiar esta configuración en el Centro de administración.

Al activar esta configuración, los miembros del grupo recibirán una copia de los correos electrónicos del grupo y las invitaciones a reuniones enviadas a su Bandeja de entrada de Outlook. Pueden leer y eliminar dicha copia del correo electrónico sin afectar a otros usuarios. Se conserva una copia del correo electrónico en la bandeja de entrada del grupo.

Los miembros del grupo pueden optar por no recibir estos correos electrónicos si deciden dejar de seguir el grupo en Outlook.

1. En el Centro de administración, expanda **Gruposy**, a continuación, haga clic en <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**Grupos**</a>.

2. Haga clic en el nombre del grupo que desea administrar para abrir el panel de configuración.

3. En la pestaña **Configuración** , seleccione **Enviar copias de conversaciones y eventos de grupo a los miembros del grupo** si desea que los miembros reciban copias de mensajes de grupo y elementos de calendario en su propia bandeja de entrada.

4. Seleccione **Guardar**.

## <a name="let-people-outside-the-organization-email-the-group"></a>Permitir que personas ajenas a la organización envíe un correo electrónico al grupo

Esta opción es excelente si desea tener una dirección de correo electrónico de la empresa, como info@contoso.com.
 
1. En el Centro de administración, expanda **Gruposy**, a continuación, haga clic en <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**Grupos**</a>.

2. Haga clic en el nombre del grupo que desea administrar para abrir el panel de configuración.

3. En la lista de grupos del Centro de administración, seleccione el nombre del grupo que desea cambiar y, a continuación, en la pestaña **Configuración** , seleccione **Permitir que los remitentes externos envíe un correo electrónico a este grupo**.
    
4. Seleccione **Guardar**.

> [!NOTE]
> Los usuarios externos a la organización pueden enviar un correo electrónico al grupo hasta 30 minutos.

## <a name="permanently-delete-a-microsoft-365-group"></a>Eliminación permanente de un grupo de Microsoft 365

En ocasiones, es posible que desee purgar permanentemente un grupo sin esperar a que expire el período de eliminación temporal de 30 días. Para ello, inicie PowerShell y ejecute este comando para obtener el identificador de objeto del grupo:
 
 ```powershell
Get-AzureADMSDeletedGroup
```

Tome nota del identificador de objeto del grupo o grupos que desea eliminar permanentemente.
  
> [!CAUTION]
> Purgar el grupo elimina el grupo y sus datos para siempre. 
  
Para purgar el grupo, ejecute este comando en PowerShell:

```powershell
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted. 
  
## <a name="related-articles"></a>Artículos relacionados

[Crear un Grupo de Microsoft 365 ](create-groups.md)

[Administración del acceso de invitado a Grupos de Microsoft 365](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Elija el dominio que se va a usar al crear Grupos de Microsoft 365](../../solutions/choose-domain-to-create-groups.md)

[Permitir que los miembros envíen como o envíen en nombre de un grupo de Microsoft 365](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[Actualizar listas de distribución a Grupos de Microsoft 365](../manage/upgrade-distribution-lists.md)

[Administración de Grupos de Microsoft 365 con PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
