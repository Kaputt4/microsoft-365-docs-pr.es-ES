---
title: Administrar sus permitidos y bloques en la lista de inquilinos permitidos/bloqueados
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a configurar los permisos y los bloques en la lista de inquilinos permitidos o bloqueados en el portal de seguridad.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 103ddc9aa0858f9203582ac07a655fd7f5506cf3
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587592"
---
# <a name="manage-the-tenant-allowblock-list"></a>Administrar la lista de permitidos o bloqueados del espacio empresarial

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> No puede configurar elementos **permitidos** en la lista de inquilinos permitidos o bloqueados en este momento.

En organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, es posible que no esté de acuerdo con el veredicto de filtrado de EOP. Por ejemplo, un mensaje bueno puede marcarse como malo (un falso positivo) o un mensaje malo se puede permitir a través (un falso negativo).

La lista de inquilinos permitidos o bloqueados en el Centro de seguridad & cumplimiento le ofrece una forma de invalidar manualmente los veredictos de filtrado de Microsoft 365. La lista de inquilinos permitidos o bloqueados se usa durante el flujo de correo y en el momento de los clics del usuario. Puede especificar direcciones URL o archivos para bloquearlos siempre.

En este artículo se describe cómo configurar entradas en la lista de inquilinos permitidos o bloqueados en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página **Lista de inquilinos permitidos o bloqueados,** use <https://protection.office.com/tenantAllowBlockList> .

- Los archivos se especifican mediante el valor hash SHA256 del archivo. Para buscar el valor hash SHA256 de un archivo en Windows, ejecute el siguiente comando en un símbolo del sistema:

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Un valor de ejemplo es `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` . No se admiten valores de hash perceptual (pHash).

- Los valores de dirección URL disponibles se describen en la sintaxis url de la sección Lista de [inquilinos permitidos o](#url-syntax-for-the-tenant-allowblock-list) bloqueados más adelante en este artículo.

- La lista de inquilinos permitidos o bloqueados permite un máximo de 500 entradas para direcciones URL y 500 entradas para hashes de archivo.

- El número máximo de caracteres para cada entrada es:
  - Hashes de archivo = 64
  - URL = 250

- Una entrada debe estar activa en 30 minutos.

- De forma predeterminada, las entradas de la lista de inquilinos permitidos o bloqueados expirarán después de 30 días. Puede especificar una fecha o establecerla para que no expire nunca.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para agregar y quitar valores de la lista de inquilinos permitidos o bloqueados, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.
  - Para obtener acceso de solo lectura a la lista de inquilinos permitidos o bloqueados, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.

  Para obtener más información, vea los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  > 
  > - Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 la cual proporciona a los usuarios los permisos necesarios _y_ para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  > - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Usar el Centro de seguridad & cumplimiento para crear entradas de dirección URL en la lista de inquilinos permitidos o bloqueados

Para obtener más información acerca de la sintaxis de las entradas de dirección URL, vea la sintaxis de dirección URL de la sección Lista de [permitidos o](#url-syntax-for-the-tenant-allowblock-list) bloqueados del espacio empresarial más adelante en este artículo.

1. En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**

2. En la **página Lista de inquilinos permitidos o** bloqueados, compruebe que la pestaña **Direcciones** URL está seleccionada y, a continuación, haga clic en **Bloquear**

3. En el **menú desplegable Bloquear direcciones URL** que aparece, configure las siguientes opciones:

   - **Agregar direcciones URL para bloquear:** escriba una dirección URL por línea, hasta un máximo de 20.

   - **Nunca expire:** realice uno de los siguientes pasos:

     - Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Expira en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de las entradas. 

       o

     - Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren: ![Habilitar](../../media/scc-toggle-on.png).

   - **Nota opcional:** escriba texto descriptivo para las entradas.

4. Cuando haya terminado, haga clic en **Agregar**.

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a>Usar el Centro de & seguridad para crear entradas de archivo en la lista de inquilinos permitidos o bloqueados

1. En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**

2. En la **página Lista de inquilinos permitidos o** bloqueados, seleccione la **pestaña** Archivos y, a continuación, haga clic en **Bloquear**.

3. En el menú desplegable **Agregar archivos** para bloquear que aparece, configure las siguientes opciones:

   - **Agregar hash de archivo:** escriba un valor hash SHA256 por línea, hasta un máximo de 20.

   - **Nunca expire:** realice uno de los siguientes pasos:

     - Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Expira en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de las entradas. 

     o

     - Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren: ![Habilitar](../../media/scc-toggle-on.png).

   - **Nota opcional:** escriba texto descriptivo para las entradas.

4. Cuando haya terminado, haga clic en **Agregar**.

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Usar el Centro de seguridad & cumplimiento para ver entradas en la lista de inquilinos permitidos o bloqueados

1. En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**

2. Seleccione la **pestaña Direcciones URL** o la **pestaña** Archivos.

Haga clic en los siguientes encabezados de columna para ordenar en orden ascendente o descendente:

- **Valor:** la dirección URL o el hash del archivo.
- **Fecha de última actualización**
- **Fecha de expiración**
- **Nota**

Haga **clic en** Buscar, escriba todo o parte de un valor y, a continuación, presione ENTRAR para buscar un valor específico. Cuando haya terminado, haga clic en **Borrar búsqueda** Borrar icono ![ de ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) búsqueda.

Haga clic **en Filtrar**. En el **menú** desplegable Filtro que aparece, configure cualquiera de las siguientes opciones:

- **Never expire**: Select off: ![ Toggle off or ](../../media/scc-toggle-off.png) on: Toggle on ![ ](../../media/scc-toggle-on.png) .

- **Last updated**: Select a start date (**From**), an end date (**To**) or both.

- **Fecha de expiración:** seleccione una fecha de inicio (**From**), una fecha de finalización (**Para**) o ambas.

Cuando haya terminado, haga clic en **Aplicar**.

Para borrar los filtros existentes, haga clic **en Filtrar** y, en el **menú** desplegable Filtro que aparece, haga clic en **Borrar filtros**.

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a>Usar el Centro de seguridad & cumplimiento para modificar entradas de bloque en la lista de inquilinos permitidos o bloqueados

No puede modificar los valores de archivo o url bloqueados existentes dentro de una entrada. Para modificar estos valores, debe eliminar y volver a crear la entrada.

1. En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**

2. Seleccione la **pestaña Direcciones URL** o la **pestaña** Archivos.

3. Seleccione la entrada de bloque que desea modificar y, a continuación, haga clic **en Editar** icono ![ Editar ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .

4. En el menú desplegable que aparece, configure las siguientes opciones:

   - **Nunca expire:** realice uno de los siguientes pasos:

     - Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Expira en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de la entrada. 

       o

     - Mueva el botón de alternancia a la derecha para configurar la entrada para que no expire nunca: ![Habilitar](../../media/scc-toggle-on.png).

   - **Nota opcional:** escriba texto descriptivo para la entrada.

5. Cuando haya terminado, haga clic en **Guardar**.

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a>Usar el Centro de seguridad & cumplimiento para quitar entradas de bloque de la lista de inquilinos permitidos o bloqueados

1. En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**

2. Seleccione la **pestaña Direcciones URL** o la **pestaña** Archivos.

3. Seleccione la entrada de bloque que desea quitar y, a continuación, haga clic **en Eliminar** icono ![ Eliminar ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .

4. En el cuadro de diálogo de advertencia que aparece, haga clic **en Eliminar**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Usar PowerShell de Exchange Online o PowerShell EOP independiente para configurar la lista de inquilinos permitidos o bloqueados

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a>Usar PowerShell para agregar entradas de bloque a la lista de inquilinos permitidos o bloqueados

Para agregar entradas de bloque en la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

En este ejemplo se agrega una entrada de dirección URL de bloque para contoso.com y todos los subdominios (por ejemplo, contoso.com, www.contoso.com y xyz.abc.contoso.com). Dado que no usamos los parámetros ExpirationDate o NoExpiration, la entrada expira después de 30 días.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

En este ejemplo se agrega una entrada de archivo de bloque para los archivos especificados que nunca expiran.

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>Usar PowerShell para ver entradas en la lista de inquilinos permitidos o bloqueados

Para ver entradas en la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

En este ejemplo se devuelven todas las direcciones URL bloqueadas.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

En este ejemplo se devuelve información sobre el valor hash de archivo especificado.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a>Usar PowerShell para modificar entradas de bloque en la lista de inquilinos permitidos o bloqueados

No puede modificar los valores de dirección URL o archivo existentes dentro de una entrada de bloque. Para modificar estos valores, debe eliminar y volver a crear la entrada.

Para modificar las entradas de bloque en la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

En este ejemplo se cambia la fecha de expiración de la entrada de bloque especificada.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a>Usar PowerShell para quitar entradas de bloque de la lista de inquilinos permitidos o bloqueados

Para quitar entradas de bloque de la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

En este ejemplo se quita la entrada de dirección URL de bloque especificada de la lista de inquilinos permitidos o bloqueados.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>Sintaxis de dirección URL para la lista de inquilinos permitidos o bloqueados

- Las direcciones IP4v e IPv6 están permitidas, pero los puertos TCP/UDP no.

- No se permiten extensiones de nombre de archivo (por ejemplo, test.pdf).

- Unicode no es compatible, pero Punycode lo es.

- Los nombres de host se permiten si todas las instrucciones siguientes son verdaderas:
  - El nombre de host contiene un punto.
  - Hay al menos un carácter a la izquierda del punto.
  - Hay al menos dos caracteres a la derecha del punto.

  Por ejemplo, `t.co` se permite; `.com` o no `contoso.` se permite.

- Las subpaths no están implícitas.

  Por ejemplo, `contoso.com` no incluye `contoso.com/a` .

- Los caracteres comodín (*) se permiten en los siguientes escenarios:

  - Un comodín izquierdo debe ir seguido de un punto para especificar un subdominio.

    Por ejemplo, `*.contoso.com` está permitido; `*contoso.com` no está permitido.

  - Un comodín derecho debe seguir una barra diagonal (/) para especificar una ruta de acceso.

    Por ejemplo, `contoso.com/*` se permite; `contoso.com*` o no `contoso.com/ab*` se permite.

  - Todas las subpaths no están implícitas por un comodín derecho.

    Por ejemplo, `contoso.com/*` no incluye `contoso.com/a` .

  - `*.com*` no es válido (no es un dominio resolvible y el comodín derecho no sigue una barra diagonal).

  - Los caracteres comodín no están permitidos en las direcciones IP.

- El carácter tilde (~) está disponible en los siguientes escenarios:

  - Una tilde izquierda implica un dominio y todos los subdominios.

    Por `~contoso.com` ejemplo, incluye `contoso.com` y `*.contoso.com` .

- Se producirá un error en las entradas de dirección URL que contienen protocolos (por ejemplo, , o ) porque las entradas de dirección URL se `http://` aplican a todos los `https://` `ftp://` protocolos.

- No se admite ni se requiere un nombre de usuario o contraseña.

- Las comillas (' o ") son caracteres no válidos.

- Una dirección URL debe incluir todas las redirecciones siempre que sea posible.

### <a name="url-entry-scenarios"></a>Escenarios de entrada de dirección URL

Las entradas de dirección URL válidas y sus resultados se describen en las secciones siguientes.

#### <a name="scenario-no-wildcards"></a>Escenario: sin caracteres comodín

**Entrada**: `contoso.com`

- **Permitir coincidencia**: contoso.com

- **Permitir que no coincida**:

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Bloquear coincidencia**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Bloque no coincidente:** abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Escenario: comodín izquierdo (subdominio)

**Entrada**: `*.contoso.com`

- **Permitir coincidencia y** **Bloquear coincidencia:**

  - www.contoso.com
  - xyz.abc.contoso.com

- **Permitir no coincidente y** **Bloquear no coincidente**:

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Escenario: comodín derecho en la parte superior de la ruta de acceso

**Entrada**: `contoso.com/a/*`

- **Permitir coincidencia y** **Bloquear coincidencia:**

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Permitir no coincidente y** **Bloquear no coincidente**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Escenario: tilde izquierda

**Entrada**: `~contoso.com`

- **Permitir coincidencia y** **Bloquear coincidencia:**

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Permitir no coincidente y** **Bloquear no coincidente**:

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Escenario: sufijo comodín derecho

**Entrada**: `contoso.com/*`

- **Permitir coincidencia y** **Bloquear coincidencia:**

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Permitir no coincidente y** **Bloquear no coincidente:** contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Escenario: subdominio comodín izquierdo y sufijo comodín derecho

**Entrada**: `*.contoso.com/*`

- **Permitir coincidencia y** **Bloquear coincidencia:**

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Permitir no coincidente y** **Bloquear no coincidente:** contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Escenario: tilde izquierda y derecha

**Entrada**: `~contoso.com~`

- **Permitir coincidencia y** **Bloquear coincidencia:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Permitir no coincidente y** **Bloquear no coincidente**:

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Escenario: dirección IP

**Entrada**: `1.2.3.4`

- **Permitir coincidencia** y **Bloquear coincidencia**: 1.2.3.4

- **Permitir no coincidente y** **Bloquear no coincidente**:

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>Dirección IP con comodín derecho

**Entrada**: `1.2.3.4/*`

- **Permitir coincidencia y** **Bloquear coincidencia:**

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Ejemplos de entradas no válidas

Las siguientes entradas no son válidas:

- **Faltan valores de dominio o no son válidos:**

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **Comodín en el texto o sin caracteres de espaciado:**

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **Direcciones IP con puertos**:

  - contoso.com:443
  - abc.contoso.com:25

- **Caracteres comodín no descriptivos:**

  - \*
  - \*.\*

- **Caracteres comodín intermedios**:

  - conto \* so.com
  - conto~so.com

- **Caracteres comodín dobles**

  - contoso.com/\*\*
  - contoso.com/\*/\*
