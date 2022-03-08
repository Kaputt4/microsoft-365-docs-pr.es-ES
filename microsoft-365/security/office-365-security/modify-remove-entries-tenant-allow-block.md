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
ms.openlocfilehash: f1ab3f815cc64af6d1383df228ef7961c3afdcec
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330193"
---
# <a name="modify-and-remove-entries-in-the-tenant-allowblock-list"></a>Modificar y quitar entradas a la lista de bloqueados y permitidos del espacio empresarial

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Puede usar el portal de Microsoft 365 Defender o PowerShell para modificar y quitar entradas en la lista de inquilinos permitidos o bloqueados.

## <a name="use-the-microsoft-365-defender-portal"></a>Uso del portal de Microsoft 365 Defender

### <a name="modify-entries-in-the-tenant-allowblock-list"></a>Modificar entradas en la lista de inquilinos permitidos o bloqueados

1. En el portal de Microsoft 365 Defender, vaya a **Directivas &** \>  \>  \> reglas de amenazas Sección Reglas de directivas de amenazas.

2. Seleccione la pestaña que contiene el tipo de entrada que desea modificar:
   - **Remitentes**
   - **Spoofing**
   - **DIRECCIONES URL**
   - **Files**


3. Seleccione la entrada que desea modificar y, a continuación, haga clic en ![Editar icono.](../../media/m365-cc-sc-edit-icon.png) **Edición**. Los valores que puede modificar en el control desplegable que aparece dependen de la pestaña seleccionada en el paso anterior:
   - **Remitentes**
     - **No expire nunca** ni la fecha de expiración.
     - **Nota opcional**
   - **Spoofing**
     - **Acción**: puede cambiar el valor a **Permitir** o **Bloquear**.
   - **DIRECCIONES URL**
     - **No expire nunca** ni la fecha de expiración.
     - **Nota opcional**
   - **Files**
     - **No expire nunca** ni la fecha de expiración.
     - **Nota opcional**

4. Cuando haya terminado, haga clic en **Guardar**.

> [!NOTE]
> Solo puede ampliar permite un máximo de 30 días después de la fecha de creación. Los bloques se pueden extender hasta 90 días, pero a diferencia de lo que permite, también se pueden establecer en Nunca expirar.

### <a name="remove-entries-from-the-tenant-allowblock-list"></a>Quitar entradas de la lista de inquilinos permitidos o bloqueados

1. En el portal de Microsoft 365 Defender, vaya a **Directivas &** \>  \>  \> reglas de amenazas Sección Reglas de directivas de amenazas.

2. Seleccione la pestaña que contiene el tipo de entrada que desea quitar:
   - **Remitentes**
   - **Spoofing**
   - **DIRECCIONES URL**
   - **Files**
 
3. Seleccione la entrada que desea quitar y, a continuación, haga clic en ![Eliminar icono.](../../media/m365-cc-sc-delete-icon.png) **Eliminar**.

4. En el cuadro de diálogo de advertencia que aparece, haga clic en **Eliminar**.

## <a name="use-powershell"></a>Usar PowerShell

### <a name="modify-allow-or-block-sender-file-and-url-entries-in-the-tenant-allowblock-list"></a>Modificar permitir o bloquear entradas de remitente, archivo y dirección URL en la lista de inquilinos permitidos o bloqueados

Para modificar permitir o bloquear entradas de remitente, archivo y dirección URL en la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
Set-TenantAllowBlockListItems -ListType <Sender | FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

En este ejemplo se cambia la fecha de expiración de la entrada de dirección URL de bloque especificada.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).

### <a name="remove-allow-or-block-sender-url-or-file-entries-from-the-tenant-allowblock-list"></a>Quitar permitir o bloquear entradas de remitente, dirección URL o archivo de la lista de inquilinos permitidos o bloqueados

Para quitar o bloquear entradas de remitente, archivo y dirección URL de la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:

```powershell
Remove-TenantAllowBlockListItems -ListType <Sender | FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

En este ejemplo se quita la entrada de dirección URL de bloque especificada de la lista de inquilinos permitidos o bloqueados.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).

### <a name="modify-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a>Modificar permitir o bloquear entradas de remitente suplantadas de la lista de inquilinos permitidos o bloqueados

Para modificar permitir o bloquear entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

En este ejemplo se cambia la entrada de remitente suplantada de permitir a bloquear.

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).

### <a name="remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a>Quitar entradas de remitente suplantados de identidad de la lista de permitidos o bloqueados del inquilino
 
Para quitar entradas de remitente de suplantación de identidad de la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).
