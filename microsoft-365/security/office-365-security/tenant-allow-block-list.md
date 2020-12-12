---
title: Administrar las direcciones URL permitidas y bloqueadas en la lista de permitidos/bloqueados del inquilino
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a configurar entradas de direcciones URL en la lista de permitidos y bloqueados del centro de seguridad & cumplimiento.
ms.openlocfilehash: 4bf5e2e29a9f48c434be527a2447ca4bf98c4208
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660003"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a>Administrar direcciones URL en la lista de permitidos y bloqueados del espacio empresarial

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Las características descritas en este artículo se encuentran en versión preliminar, están sujetas a cambios y no están disponibles en todas las organizaciones.

En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, es posible que no esté de acuerdo con el veredicto de filtrado de EOP. Por ejemplo, un buen mensaje puede marcarse como incorrecto (un falso positivo) o puede que se permita el acceso a un mensaje incorrecto (un falso negativo).

La lista de permitidos y bloqueados del centro de cumplimiento de & de seguridad ofrece una forma de reemplazar manualmente los veredictos de filtrado de 365 de Microsoft. La lista de permitidos/bloqueados del inquilino se usa durante el flujo de correo y en el momento en que el usuario hace clic. Puede especificar las direcciones URL que desea permitir o bloquear en la lista de permitidos/bloqueados del inquilino.

En este tema se describe cómo configurar entradas en la lista de permitidos/bloqueados del centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para Microsoft 365 organizaciones con buzones en Exchange Online; PowerShell de EOP independiente para las organizaciones sin buzones de correo de Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página de la **lista de permitidos/bloqueados de inquilino** , use <https://protection.office.com/tenantAllowBlockList> .

- Los valores de dirección URL disponibles se describen en la sintaxis de la [dirección URL de la sección lista de permitidos/bloqueados de inquilino](#url-syntax-for-the-tenant-allowblock-list) más adelante en este artículo.

- La lista de permitidos/bloqueados de inquilino permite un máximo de 500 entradas para las direcciones URL.

- Una entrada debe estar activa en 15 minutos.

- Las entradas de bloque tienen prioridad sobre las entradas de permitir.

- De forma predeterminada, las entradas de la lista de permitidos y bloqueados de inquilino expirarán transcurridos 30 días. Puede especificar una fecha o configurarlas para que no expiren nunca.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento de Office 365 antes de que pueda usar este cmdlet.
  - Para agregar y quitar valores de la lista de permitidos/bloqueados de inquilino, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** .
  - Para obtener acceso de solo lectura a la lista de permitidos/bloqueados de inquilino, debe ser miembro de los grupos de roles **lector global** o **lector de seguridad** .

  Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

  **Notas**:

  - Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Usar el centro de seguridad & cumplimiento para crear entradas de dirección URL en la lista de permitidos/bloqueados de espacio empresarial

Para obtener información detallada sobre la sintaxis de las entradas de dirección URL, vea la [Sintaxis de dirección URL para la sección lista de permitidos/bloqueados de inquilino](#url-syntax-for-the-tenant-allowblock-list) más adelante en este artículo.

1. En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** para \>  \> **las listas de permitidos y bloqueados del inquilino**.

2. En la página **lista de permitidos/bloqueados del inquilino** , compruebe que la ficha **direcciones URL** está seleccionada y, a continuación, haga clic en **Agregar** .

3. En el control flotante **Agregar nuevas direcciones URL** que aparece, configure las siguientes opciones:

   - **Agregar direcciones URL con caracteres comodín**: escriba una dirección URL por línea, hasta un máximo de 20.

   - **Bloquear o permitir**: Seleccione si desea **permitir** o **bloquear** las direcciones URL especificadas.

   - No **expira nunca**: siga uno de estos pasos:

     - Compruebe que la opción está desactivada (desactivar ![ ](../../media/scc-toggle-off.png) ) y use el cuadro **expira en** para especificar la fecha de caducidad de las entradas.

     o

     - Mueva el botón de alternancia a la derecha para configurar las entradas para que no expiren nunca: ![Habilitar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Opcional Nota**: escriba un texto descriptivo para las entradas.

4. Cuando haya terminado, haga clic en **Agregar**.

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Usar el centro de seguridad & cumplimiento para ver las entradas de la lista de permitidos y bloqueados del inquilino

1. En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** para \>  \> **las listas de permitidos y bloqueados del inquilino**.

2. Seleccione la ficha **direcciones URL** .

Haga clic en los siguientes encabezados de columna para ordenar en orden ascendente o descendente:

- **Valor**
- **Acción**: **bloquear** o **permitir**.
- **Fecha de la última actualización**
- **Fecha de expiración**
- **Nota**

Haga clic en **agrupar** para agrupar las entradas por **acción** (**bloquear** o **permitir**) o en **ninguna**.

Haga clic en **Buscar**, escriba todo o parte de un valor y, a continuación, presione Entrar para buscar un valor específico. Cuando haya terminado, haga clic en **Clear Search** ![ Clear Search Icon ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .

Haga clic en **filtro**. En el control flotante de **filtro** que aparece, configure cualquiera de las siguientes opciones:

- **Acción**: seleccione **permitir**, **bloquear** o ambos.

- **Nunca expire**: seleccione Desactivado (desactivado ![ ](../../media/scc-toggle-off.png) ) o activado ( ![ alternar en ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).

- **Última actualización**: Seleccione una fecha de inicio (desde), una fecha **de** finalización (**hasta**) o ambas.

- **Fecha de expiración**: Seleccione una fecha **de** Inicio (desde), una fecha de finalización (**hasta**) o ambas.

Cuando haya terminado, haga clic en **aplicar**.

Para borrar los filtros existentes, haga clic en **filtrar** y, en el control flotante de **filtro** que aparece, haga clic en **Borrar filtros**.

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>Usar el centro de seguridad & cumplimiento para modificar las entradas de la lista de permitidos y bloqueados del inquilino

El valor de la dirección URL no se puede modificar. En su lugar, debe eliminar la entrada y volver a crearla.

1. En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** para \>  \> **las listas de permitidos y bloqueados del inquilino**.

2. Seleccione la ficha **direcciones URL** .

3. Seleccione la entrada que desea modificar y, a continuación, haga clic en **Editar** ![ icono Editar ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .

4. En el control flotante que aparece, configure las siguientes opciones:

   - **Bloquear o permitir**: seleccione **permitir** o **bloquear**.

   - No **expira nunca**: siga uno de estos pasos:

     - Compruebe que la opción está desactivada (desactivar ![ ](../../media/scc-toggle-off.png) ) y use el cuadro **expira en** para especificar la fecha de caducidad de la entrada.

     o

     - Mueva el botón de alternancia a la derecha para configurar que la entrada nunca expire: ![Habilitar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Opcional Nota**: escriba un texto descriptivo para la entrada.

5. Cuando haya terminado, haga clic en **Guardar**.

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>Usar el centro de seguridad & cumplimiento para quitar entradas de la lista de permitidos y bloqueados del inquilino

1. En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** para \>  \> **las listas de permitidos y bloqueados del inquilino**.

2. Seleccione la ficha **direcciones URL** .

3. Seleccione la entrada que desee quitar y, a continuación, haga clic en **eliminar** ![ icono de eliminación ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .

4. En el cuadro de diálogo de advertencia que aparece, haga clic en **eliminar**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Usar Exchange Online PowerShell o PowerShell independiente de EOP para configurar la lista de permitidos/bloqueados del inquilino

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a>Usar PowerShell para agregar entradas en la lista de permitidos y bloqueados del inquilino

Para agregar entradas a la lista de permitidos/bloqueados de inquilino, use la siguiente sintaxis:

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

En este ejemplo se agrega una entrada de bloque de dirección URL para contoso.com y todos los subdominios (por ejemplo, contoso.com, www.contoso.com y xyz.abc.contoso.com). Como no se usaron los parámetros ExpirationDate o noexpiration, la entrada expira después de 30 días.

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>Usar PowerShell para ver las entradas de la lista de permitidos y bloqueados del inquilino

Para ver las entradas de la lista de permitidos/bloqueados de inquilino, use la siguiente sintaxis:

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

En este ejemplo se devuelven todas las direcciones URL bloqueadas.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a>Usar PowerShell para modificar entradas en la lista de permitidos y bloqueados del inquilino

El valor de la dirección URL no se puede modificar. En su lugar, debe eliminar la entrada y volver a crearla.

Para modificar las entradas de la lista de permitidos/bloqueados de inquilino, use la siguiente sintaxis:

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

En este ejemplo se cambia la fecha de caducidad de la entrada especificada.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a>Usar PowerShell para quitar entradas de la lista de permitidos y bloqueados del inquilino

Para quitar entradas de la lista de permitidos/bloqueados de inquilino, use la siguiente sintaxis:

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

En este ejemplo se quita la entrada de la dirección URL especificada de la lista de permitidos/bloqueados del inquilino.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>Sintaxis de dirección URL para la lista de permitidos/bloqueados del inquilino

- Se permiten las direcciones IP4v e IPv6, pero los puertos TCP/UDP no.

- No se permiten las extensiones de nombre de archivo (por ejemplo, test.pdf).

- No se admite Unicode, pero Punycode es.

- Los nombres de host se permiten si todas las instrucciones siguientes son verdaderas:

  - El nombre de host contiene un punto.
  - Hay al menos un carácter a la izquierda del punto.
  - Hay al menos dos caracteres a la derecha del punto.

  Por ejemplo, `t.co` está permitido; `.com` o `contoso.` no está permitido.

- Los subtrazados no son implícitos.

  Por ejemplo, `contoso.com` no incluye `contoso.com/a` .

- Los caracteres comodín (*) están permitidos en las siguientes situaciones:

  - Un comodín izquierdo debe ir seguido de un punto para especificar un subdominio.

    Por ejemplo, `*.contoso.com` está permitido; `*contoso.com` no está permitido.

  - Un comodín derecho debe ir seguido de una barra diagonal (/) para especificar una ruta de acceso.

    Por ejemplo, `contoso.com/*` está permitido; `contoso.com*` o `contoso.com/ab*` no está permitido.

  - Un comodín derecho no implica todos los subtrazados.

    Por ejemplo, `contoso.com/*` no incluye `contoso.com/a` .

  - `*.com*` no es válido (no es un dominio que se pueda resolver y el comodín derecho no sigue una barra diagonal).

  - No se permiten caracteres comodín en direcciones IP.

- El carácter tilde (~) está disponible en los siguientes escenarios:

  - Una tilde izquierda implica un dominio y todos los subdominios.

    Por ejemplo `~contoso.com` `contoso.com` , incluye y `*.contoso.com` .

- Las entradas de dirección URL que contienen protocolos (por ejemplo,, `http://` `https://` o) producirán `ftp://` un error porque las entradas de dirección URL se aplican a todos los protocolos.

- No se admite ni es necesario un nombre de usuario ni una contraseña.

- Las comillas (' o ") son caracteres no válidos.

- Una dirección URL debe incluir todas las redirecciones siempre que sea posible.

### <a name="url-entry-scenarios"></a>Escenarios de entrada de direcciones URL

En las siguientes secciones se describen las entradas de dirección URL válidas y sus resultados.

#### <a name="scenario-no-wildcards"></a>Escenario: sin caracteres comodín

**Entrada**: `contoso.com`

- **Permitir coincidencia**: contoso.com

- **Permitir sin coincidencia**:

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www. contoso. com/q = a@contoso. com

- **Coincidencia de bloque**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www. contoso. com/q = a@contoso. com

- **Bloque no coincidente**: ABC-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Escenario: comodín izquierdo (subdominio)

**Entrada**: `*.contoso.com`

- **Permitir** coincidencia de coincidencia y **bloqueo**:

  - www.contoso.com
  - xyz.abc.contoso.com

- **Permitir no coincidentes** y **no coincidentes**:

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Escenario: comodín derecho en la parte superior de la ruta de acceso

**Entrada**: `contoso.com/a/*`

- **Permitir** coincidencia de coincidencia y **bloqueo**:

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso. com/a/? q = joe@t. com

- **Permitir no coincidentes** y **no coincidentes**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www. contoso. com/q = a@contoso. com

#### <a name="scenario-left-tilde"></a>Escenario: tilde izquierda

**Entrada**: `~contoso.com`

- **Permitir** coincidencia de coincidencia y **bloqueo**:

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Permitir no coincidentes** y **no coincidentes**:

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Escenario: sufijo comodín derecho

**Entrada**: `contoso.com/*`

- **Permitir** coincidencia de coincidencia y **bloqueo**:

  - contoso. com/? q = whatever@fabrikam. com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Permitir no coincidentes** y **no coincidentes**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Escenario: subdominio comodín izquierdo y sufijo comodín derecho

**Entrada**: `*.contoso.com/*`

- **Permitir** coincidencia de coincidencia y **bloqueo**:

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Permitir no coincidentes** y **no coincidentes**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Escenario: tilde izquierda y derecha

**Entrada**: `~contoso.com~`

- **Permitir** coincidencia de coincidencia y **bloqueo**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Permitir no coincidentes** y **no coincidentes**:

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Escenario: dirección IP

**Entrada**: `1.2.3.4`

- **Permitir** coincidencia de coincidencia y **bloqueo**: 1.2.3.4

- **Permitir no coincidentes** y **no coincidentes**:

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>Dirección IP con comodín derecho

**Entrada**: `1.2.3.4/*`

- **Permitir** coincidencia de coincidencia y **bloqueo**:

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Ejemplos de entradas no válidas

Las siguientes entradas no son válidas:

- **Faltan valores de dominio o no son válidos**:

  - contoso
  - \*contoso.\*
  - \*. com
  - \*. pdf

- **Comodín en texto o sin caracteres de espaciado**:

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **Direcciones IP con puertos**:

  - contoso.com:443
  - abc.contoso.com:25

- **Caracteres comodín no descriptivos**:

  - \*
  - \*.\*

- **Caracteres comodín del segundo nombre**:

  - conto \* so.com
  - conto ~ so. com

- **Caracteres comodín dobles**

  - contoso.com/\*\*
  - contoso.com/\*/\*
