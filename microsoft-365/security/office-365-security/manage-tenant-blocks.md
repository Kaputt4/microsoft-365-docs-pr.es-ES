---
title: Administrar los bloques en la lista de inquilinos permitidos o bloqueados
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a configurar bloques en la lista de inquilinos permitidos o bloqueados en el portal de seguridad.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38347850b66c2a83708df12aaa3233a0afe01444
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2021
ms.locfileid: "53544327"
---
# <a name="add-blocks-in-the-tenant-allowblock-list"></a>Agregar bloques en la lista de inquilinos permitidos o bloqueados

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="use-the-microsoft-365-defender-portal"></a>Uso del portal de Microsoft 365 Defender 

### <a name="create-block-url-entries-in-the-tenant-allowblock-list"></a>Crear entradas de dirección URL de bloque en la lista de inquilinos permitidos o bloqueados

1. En el portal Microsoft 365 Defender, vaya a **Directivas &** sección Reglas de directivas de amenazas sección Listas de \>  \>  \> **inquilinos permitidos o bloqueados.**

2. En la **página Lista de inquilinos permitidos o** bloqueados, compruebe que la pestaña **Direcciones** URL está seleccionada y, a continuación, haga clic en Bloquear ![ icono ](../../media/m365-cc-sc-create-icon.png) **Bloquear**.

3. En el **menú desplegable Bloquear direcciones URL** que aparece, configure las siguientes opciones:
   - **Agregar direcciones URL con caracteres comodín:** escriba una dirección URL por línea, hasta un máximo de 20. Para obtener más información acerca de la sintaxis de las entradas url, consulte la sección Sintaxis de dirección URL en Administrar la lista de [inquilinos permitidos o bloqueados.](tenant-allow-block-list.md)
   - **Nunca expire:** realice uno de los siguientes pasos:
     - Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Quitar en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de las entradas. 

       o

     - Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren: ![Habilitar](../../media/scc-toggle-on.png).
   - **Nota opcional:** escriba texto descriptivo para las entradas.

4. Cuando haya terminado, haga clic en **Agregar**.

### <a name="create-block-file-entries-in-the-tenant-allowblock-list"></a>Crear entradas de archivo de bloque en la lista de inquilinos permitidos o bloqueados

1. En el portal Microsoft 365 Defender, vaya a **Directivas &** sección Reglas de directivas de amenazas sección Listas de \>  \>  \> **inquilinos permitidos o bloqueados.**

2. En la **página Lista de inquilinos permitidos o** bloqueados, seleccione la **pestaña** Archivos y, a continuación, haga clic en Bloquear ![ icono ](../../media/m365-cc-sc-create-icon.png) **Bloquear**.

3. En el menú desplegable **Bloquear** archivos que aparece, configure las siguientes opciones:
   - **Agregar hash de archivo:** escriba un valor hash SHA256 por línea, hasta un máximo de 20.
   - **Nunca expire:** realice uno de los siguientes pasos:
     - Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Quitar en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de las entradas. 

     o

     - Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren: ![Habilitar](../../media/scc-toggle-on.png).
   - **Nota opcional:** escriba texto descriptivo para las entradas.

4. Cuando haya terminado, haga clic en **Agregar**.

### <a name="create-spoofed-sender-block-entries"></a>Crear entradas de bloque de remitente suplantadas

**Notas**:

- Solo se _permite o_ bloquea  específicamente la combinación del usuario suplantado y la infraestructura de envío definida en el par de dominio.
- Al configurar una entrada de permitir o bloquear para un par de dominio, los mensajes de ese par de dominio ya no aparecen en la información de inteligencia suplantación.
- Las entradas de remitentes suplantados nunca expiran.
- La suplantación admite permitir y bloquear. La dirección URL solo admite permitir.

1. En el portal Microsoft 365 Defender, vaya a **Directivas &** sección Reglas de directivas de amenazas sección Listas de \>  \>  \> **inquilinos permitidos o bloqueados.**

2. En la **página Lista de inquilinos permitidos o** bloqueados, seleccione la pestaña **Suplantación** y, a continuación, haga clic ![ en Bloquear icono ](../../media/m365-cc-sc-create-icon.png) **Agregar**.

3. En el **menú desplegable Agregar nuevos pares de** dominio que aparece, configure las siguientes opciones:
   - **Agregar nuevos pares de dominio con caracteres comodín:** escriba un par de dominio por línea, hasta un máximo de 20. Para obtener más información sobre la sintaxis de las entradas de remitente suplantadas, vea [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).
   - **Tipo de suplantación:** seleccione uno de los siguientes valores:
     - **Interno:** el remitente suplantado está en un dominio que pertenece a su organización (un [dominio aceptado).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
     - **Externo:** el remitente suplantado está en un dominio externo.
   - **Acción:** seleccione **Permitir** o **Bloquear**.

4. Cuando haya terminado, haga clic en **Agregar**.

## <a name="use-powershell"></a>Usar PowerShell

### <a name="add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a>Agregar entradas de archivo de bloque o dirección URL a la lista de inquilinos permitidos o bloqueados

Para agregar entradas de dirección URL o archivo de bloque en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

En este ejemplo se agrega una entrada de archivo de bloque para los archivos especificados que nunca expiran.

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

En este ejemplo se agrega una entrada de dirección URL de bloque para contoso.com y todos los subdominios (por ejemplo, contoso.com, www.contoso.com y xyz.abc.contoso.com). Dado que no usamos los parámetros ExpirationDate o NoExpiration, la entrada expira después de 30 días.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="add-spoofed-sender-block-entries"></a>Agregar entradas de bloque de remitente suplantadas 

Para agregar entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).