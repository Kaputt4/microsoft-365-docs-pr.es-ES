---
title: Modificar y quitar entradas a la lista de bloqueados y permitidos del espacio empresarial
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a modificar y quitar entradas en la lista de inquilinos permitidos o bloqueados en el portal de seguridad.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac612b51cab9069e50c4eec05948b3aa840b9cc9
ms.sourcegitcommit: 4d6a8e9d69a421d6c293b2485a8aa5e806b71616
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "65182703"
---
# <a name="modify-and-remove-entries-in-the-tenant-allowblock-list"></a>Modificar y quitar entradas a la lista de bloqueados y permitidos del espacio empresarial

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Puede usar el portal de Microsoft 365 Defender o PowerShell para modificar y quitar entradas en la lista de permitidos o bloqueados de inquilinos.

## <a name="use-the-microsoft-365-defender-portal"></a>Uso del portal de Microsoft 365 Defender

### <a name="modify-entries-in-the-tenant-allowblock-list"></a>Modificar entradas en la lista de permitidos o bloqueados de inquilinos

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas De directivas** \> de amenazas sección \> **Reglas de directivas** de **amenazas** \> **Listas de permitidos o bloques de inquilinos**. O bien, para ir directamente a la página **Permitir o bloquear lista de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. Seleccione la pestaña que contiene el tipo de entrada que desea modificar:
   - **Remitentes**
   - **Spoofing**
   - **Url**
   - **Files**

3. Seleccione la entrada que desea modificar y, a continuación, haga clic en ![el icono Editar.](../../media/m365-cc-sc-edit-icon.png) **Edición**. Los valores que puede modificar en el control flotante que aparece dependen de la pestaña seleccionada en el paso anterior:
   - **Remitentes**
     - **Nunca expire** ni la fecha de expiración.
     - **Nota opcional**
   - **Spoofing**
     - **Acción**: puede cambiar el valor a **Permitir** o **Bloquear**.
   - **Url**
     - **Nunca expire** ni la fecha de expiración.
     - **Nota opcional**
   - **Files**
     - **Nunca expire** ni la fecha de expiración.
     - **Nota opcional**

4. Cuando haya terminado, haga clic en **Guardar**.

> [!NOTE]
> Solo puede ampliar los plazos durante un máximo de 30 días después de la fecha de creación. Los bloques se pueden extender hasta 90 días, pero a diferencia de lo que permite, también se pueden establecer en Nunca expirar.

### <a name="remove-entries-from-the-tenant-allowblock-list"></a>Eliminación de entradas de la lista de permitidos o bloqueados de inquilinos

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas De directivas** \> de amenazas sección \> **Reglas de directivas** de **amenazas** \> **Listas de permitidos o bloques de inquilinos**. O bien, para ir directamente a la página **Permitir o bloquear lista de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. Seleccione la pestaña que contiene el tipo de entrada que desea quitar:
   - **Remitentes**
   - **Spoofing**
   - **Url**
   - **Files**

3. Seleccione la entrada que desea quitar y, a continuación, haga clic en ![el icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Delete**.

4. En el cuadro de diálogo de advertencia que aparece, haga clic en **Eliminar**.

## <a name="use-powershell"></a>Usar PowerShell

### <a name="modify-allow-or-block-sender-file-and-url-entries-in-the-tenant-allowblock-list"></a>Modificar entradas de permitir o bloquear remitentes, archivos y direcciones URL en la lista de permitidos o bloqueados de inquilinos

Para modificar las entradas de permitir o bloquear remitentes, archivos y direcciones URL en la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
Set-TenantAllowBlockListItems -ListType <Sender | FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

En este ejemplo se cambia la fecha de expiración de la entrada de dirección URL de bloque especificada.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).

### <a name="remove-allow-or-block-sender-url-or-file-entries-from-the-tenant-allowblock-list"></a>Quitar entradas de permitir o bloquear remitentes, direcciones URL o archivos de la lista de permitidos o bloqueados de inquilinos

Para quitar entradas de permitir o bloquear remitentes, archivos y direcciones URL de la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
Remove-TenantAllowBlockListItems -ListType <Sender | FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

En este ejemplo se quita la entrada de dirección URL de bloque especificada de la lista de permitidos o bloques de inquilinos.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).

### <a name="modify-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a>Modificación de entradas de remitente permitidas o bloqueadas de la lista de permitidos o bloqueados de inquilinos

Para modificar las entradas de remitente permitidas o bloqueadas en la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

En este ejemplo se cambia la entrada del remitente suplantado de allow a block.

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).

### <a name="remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a>Quitar entradas de remitente permitidas o bloqueadas de la lista de permitidos o bloqueados de inquilinos

Para quitar las entradas de remitente de suplantación de identidad permitidas o bloqueadas de la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).
