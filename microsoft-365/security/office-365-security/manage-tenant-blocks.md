---
title: Administrar los bloques en la lista de permitidos o bloqueados de inquilinos
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
description: Los administradores pueden aprender a configurar bloques en la lista de inquilinos permitidos o bloqueados en el portal de seguridad.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1ea87a29d93c43b89bcfb482d185bd4b397dcc5b
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2022
ms.locfileid: "64862464"
---
# <a name="add-blocks-in-the-tenant-allowblock-list"></a>Agregar bloques a la lista de bloqueados y permitidos del espacio empresarial

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="use-the-microsoft-365-defender-portal"></a>Uso del portal de Microsoft 365 Defender 

### <a name="create-block-sender-entries-in-the-tenant-allowblock-list"></a>Creación de entradas de remitente de bloques en la lista de permitidos o bloqueados de inquilinos

1. En el portal de Microsoft 365 Defender, vaya a **Directivas & reglas De directivas** \> de amenazas sección **Reglas de directivas** \> de **amenazas** \> **Listas de permitidos o bloques de inquilinos**.

2. En la página **Lista de permitidos o bloqueados de inquilinos** , compruebe que la pestaña **Remitentes** está seleccionada y, a continuación, haga clic en ![el icono Bloquear.](../../media/m365-cc-sc-create-icon.png) **Bloquear**.

3. En el control flotante **Bloquear remitentes** que aparece, configure los siguientes valores:
   - **Dominios o direcciones de correo electrónico del remitente**: escriba un remitente (dirección de correo electrónico o dominio) por línea, hasta un máximo de 20.
   - **Nunca expire**: realice uno de los pasos siguientes:
     - Compruebe que la configuración está desactivada (![desactivar)](../../media/scc-toggle-off.png) y use el cuadro **Quitar activado** para especificar la fecha de expiración de las entradas.

       o

     - Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren: ![Activar.](../../media/scc-toggle-on.png).
   - **Nota opcional**: escriba texto descriptivo para las entradas.

4. Cuando haya terminado, haga clic en **Agregar**.

> [!NOTE]
> Los correos electrónicos de estos remitentes se bloquearán como *correo no deseado de alta confianza (SCL = 9)*. 

### <a name="create-block-url-entries-in-the-tenant-allowblock-list"></a>Creación de entradas de dirección URL de bloque en la lista de permitidos o bloqueados de inquilinos

1. En el portal de Microsoft 365 Defender, vaya a **Directivas & reglas De directivas** \> de amenazas sección **Reglas de directivas** \> de **amenazas** \> **Listas de permitidos o bloques de inquilinos**.

2. En la página **Lista de permitidos o bloqueados de inquilinos** , compruebe que la pestaña **Direcciones URL** está seleccionada y, a continuación, haga clic en ![icono Bloquear.](../../media/m365-cc-sc-create-icon.png) **Bloquear**.

3. En el control flotante **Bloquear direcciones URL** que aparece, configure los siguientes valores:
   - **Agregar direcciones URL con caracteres comodín**: escriba una dirección URL por línea, hasta un máximo de 20. Para obtener más información sobre la sintaxis de las entradas de dirección URL, consulte la sección Sintaxis de dirección URL en [Administrar la lista de permitidos o bloqueados de inquilinos](tenant-allow-block-list.md).
   - **Nunca expire**: realice uno de los pasos siguientes:
     - Compruebe que la configuración está desactivada (![desactivar)](../../media/scc-toggle-off.png) y use el cuadro **Quitar activado** para especificar la fecha de expiración de las entradas.

       o

     - Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren: ![Activar.](../../media/scc-toggle-on.png).
   - **Nota opcional**: escriba texto descriptivo para las entradas.

4. Cuando haya terminado, haga clic en **Agregar**.

> [!NOTE]
> Los correos electrónicos que contienen estas direcciones URL se bloquearán como *phish*. 

### <a name="create-block-file-entries-in-the-tenant-allowblock-list"></a>Creación de entradas de archivo de bloque en la lista de inquilinos permitidos o bloqueados

1. En el portal de Microsoft 365 Defender, vaya a **Directivas & reglas De directivas** \> de amenazas sección **Reglas de directivas** \> de **amenazas** \> **Listas de permitidos o bloques de inquilinos**.

2. En la página **Lista de permitidos o bloqueados de inquilinos** , seleccione la pestaña **Archivos** y, a continuación, haga clic en ![el icono Bloquear.](../../media/m365-cc-sc-create-icon.png) **Bloquear**.

3. En el control flotante **Bloquear archivos** que aparece, configure los siguientes valores:
   - **Agregar hash de archivo**: escriba un valor hash SHA256 por línea, hasta un máximo de 20.
   - **Nunca expire**: realice uno de los pasos siguientes:
     - Compruebe que la configuración está desactivada (![desactivar)](../../media/scc-toggle-off.png) y use el cuadro **Quitar activado** para especificar la fecha de expiración de las entradas.

     o

     - Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren: ![Activar.](../../media/scc-toggle-on.png).
   - **Nota opcional**: escriba texto descriptivo para las entradas.

4. Cuando haya terminado, haga clic en **Agregar**.

> [!NOTE]
> Los correos electrónicos que contienen estos archivos se bloquearán como *malware*. 

### <a name="create-spoofed-sender-block-entries"></a>Creación de entradas de bloque de remitentes suplantados

**Notas**:

- Solo se permite o bloquea específicamente la _combinación_ del usuario suplantado _y_ la infraestructura de envío tal como se define en el par de dominio.
- Al configurar una entrada de permitir o bloquear para un par de dominio, los mensajes de ese par de dominio ya no aparecen en la información de inteligencia de suplantación de identidad.
- Las entradas para remitentes suplantados nunca expiran.
- La suplantación de identidad admite permitir y bloquear.

1. En el portal de Microsoft 365 Defender, vaya a **Directivas & reglas De directivas** \> de amenazas sección **Reglas de directivas** \> de **amenazas** \> **Listas de permitidos o bloques de inquilinos**.

2. En la página **Lista de permitidos o bloqueados de inquilinos** , seleccione la pestaña **Suplantación** de identidad y, a continuación, haga clic en ![el icono Bloquear.](../../media/m365-cc-sc-create-icon.png) **Agregar**.

3. En el control flotante **Agregar nuevos pares de dominio** que aparece, configure los siguientes valores:
   - **Agregar nuevos pares de dominio con caracteres comodín**: escriba un par de dominio por línea, hasta un máximo de 20. Para obtener más información sobre la sintaxis de las entradas de remitente suplantadas, consulte [Administrar la lista de permitidos o bloques](tenant-allow-block-list.md) de inquilinos.
   - **Tipo de suplantación**: seleccione uno de los valores siguientes:
     - **Interno**: el remitente suplantado está en un dominio que pertenece a su organización (un [dominio aceptado](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).
     - **Externo**: el remitente suplantado está en un dominio externo.
   - **Acción**: seleccione **Permitir** o **Bloquear**.

4. Cuando haya terminado, haga clic en **Agregar**.

## <a name="use-powershell"></a>Usar PowerShell

### <a name="add-block-sender-file-or-url-entries-to-the-tenant-allowblock-list"></a>Agregar entradas de remitente, archivo o dirección URL de bloque a la lista de permitidos o bloqueados de inquilinos

Para agregar entradas de remitente, archivo o dirección URL en la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
New-TenantAllowBlockListItems -ListType <Sender | FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

En este ejemplo se agrega una entrada de remitente de bloque para el remitente especificado que expira en una fecha específica.

```powershell
New-TenantAllowBlockListItems -ListType Sender -Block -Entries "test@badattackerdomain.com", "test2@anotherattackerdomain.com" -ExpirationDate 8/20/2021
```

En este ejemplo se agrega una entrada de archivo de bloque para los archivos especificados que nunca expiran.

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

En este ejemplo se agrega una entrada de dirección URL de bloque para contoso.com y todos los subdominios (por ejemplo, contoso.com, www.contoso.com y xyz.abc.contoso.com). Dado que no usamos los parámetros ExpirationDate o NoExpiration, la entrada expira después de 30 días.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="add-spoofed-sender-block-entries"></a>Adición de entradas de bloque de remitentes suplantados 

Para agregar entradas de remitente suplantadas en la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).
