---
title: Administrar un grupo en el Centro de administración
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
ms.custom: admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 74a1ef8b-3844-4d08-9980-9f8f7a36000f
description: Aprenda a administrar grupos Microsoft 365, incluida la adición de miembros de grupo de eliminación, la edición de la dirección de correo electrónico, el nombre del grupo o la descripción, y la personalización del funcionamiento del grupo.
ms.openlocfilehash: 8b9e3492409322b77d7a64c73bd90f09a0f4daad
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774957"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>Administrar un grupo en el Centro de administración de Microsoft 365

Después de crear [un grupo Microsoft 365 y](create-groups.md) agregar miembros del grupo, puede configurar el grupo. Puede editar el nombre o la descripción del grupo, administrar propietarios o miembros y especificar si los remitentes externos pueden enviar un correo electrónico al grupo y si deben enviar copias de conversaciones de grupo a los miembros.

Vaya a la Centro de administración de Microsoft 365 en [https://admin.microsoft.com](https://admin.microsoft.com) .

## <a name="edit-the-group-name-or-description"></a>Editar el nombre o la descripción del grupo

1. En el Centro de administración, expanda **Grupos** y, a continuación, haga clic en <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**Grupos**</a>.

2. Seleccione el grupo que desea editar y, a continuación, haga clic **en Editar nombre y descripción.**

3. Actualice el nombre y la descripción y, a continuación, **seleccione Guardar**.

## <a name="manage-group-owners-and-members"></a>Administrar miembros y propietarios de grupos

1. En el Centro de administración, expanda **Grupos** y, a continuación, haga clic en <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**Grupos**</a>.

2. Haga clic en el nombre del grupo que desea administrar para abrir el panel de configuración.

3. En la **pestaña Miembros,** elija si desea administrar propietarios o miembros.

4. Elija **Agregar para** agregar a alguien o haga clic en **X** para quitar a alguien.

5. Haga clic en **Cerrar**.

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>Enviar copias de conversaciones a las bandejas de entrada de los miembros del grupo
  
Cuando se usa el Centro de administración para crear un grupo, de forma predeterminada los usuarios no obtienen copias de los correos electrónicos de grupo enviados a sus bandejas de entrada, aunque los usuarios obtienen copias de las invitaciones a reuniones de grupo enviadas a sus bandejas de entrada. Necesitarán ir al grupo para ver conversaciones. Puedes cambiar esta configuración en el Centro de administración.

Al activar esta configuración, los miembros del grupo recibirán una copia de los correos electrónicos de grupo y las invitaciones a reuniones enviadas a Outlook Bandeja de entrada. Pueden leer y eliminar dicha copia del correo electrónico sin afectar a otros usuarios. Se conserva una copia del correo electrónico en la bandeja de entrada del grupo.

Los miembros del grupo pueden optar por no recibir estos correos electrónicos si deciden dejar de seguir al grupo en Outlook.

1. En el Centro de administración, expanda **Grupos** y, a continuación, haga clic en <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**Grupos**</a>.

2. Haga clic en el nombre del grupo que desea administrar para abrir el panel de configuración.

3. En la **pestaña Configuración,** seleccione Enviar copias de conversaciones de grupo y eventos a miembros del grupo si desea que los miembros reciban copias de mensajes de grupo y elementos de calendario en su propia bandeja de entrada. 

4. Seleccione **Guardar**.

## <a name="let-people-outside-the-organization-email-the-group"></a>Permitir que personas externas a la organización envíe un correo electrónico al grupo

Esta opción es excelente si desea tener una dirección de correo electrónico de la empresa como info@contoso.com.
 
1. En el Centro de administración, expanda **Grupos** y, a continuación, haga clic en <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**Grupos**</a>.

2. Haga clic en el nombre del grupo que desea administrar para abrir el panel de configuración.

3. En la lista Grupos del centro de administración, seleccione el nombre del grupo que desea cambiar y, a continuación, en la pestaña **Configuración,** seleccione Permitir que los **remitentes externos** envíen un correo electrónico a este grupo.
    
4. Seleccione **Guardar**.

## <a name="permanently-delete-a-microsoft-365-group"></a>Eliminar permanentemente un Microsoft 365 grupo

A veces es posible que desee purgar permanentemente un grupo sin esperar a que expire el período de eliminación temporal de 30 días. Para ello, inicie PowerShell y ejecute este comando para obtener el identificador de objeto del grupo:
 
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

Para confirmar que el grupo se ha purgado correctamente, ejecute el cmdlet  *Get-AzureADMSDeletedGroup*  de nuevo para confirmar que el grupo ya no aparece en la lista de grupos eliminados temporalmente. En algunos casos, la eliminación permanente del grupo y todos sus datos puede tardar hasta 24 horas. 
  
## <a name="related-articles"></a>Artículos relacionados

[Crear un Grupo de Microsoft 365 ](create-groups.md)

[Administrar el acceso de invitado a Microsoft 365 grupos](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Elegir el dominio que se usará al crear Microsoft 365 grupos](../../solutions/choose-domain-to-create-groups.md)

[Permitir que los miembros envíen como o envíen en nombre de un Microsoft 365 grupo](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[Actualizar listas de distribución a Microsoft 365 grupos](../manage/upgrade-distribution-lists.md)

[Administrar Microsoft 365 grupos con PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
