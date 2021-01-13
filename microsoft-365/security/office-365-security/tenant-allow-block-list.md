---
title: Administrar los bloques y las permitidos en la lista de permitidos o bloqueados del espacio empresarial
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
description: Los administradores pueden aprender a configurar los permisos y bloques en la lista de permitidos o bloqueados del espacio empresarial en el portal de seguridad.
ms.openlocfilehash: c789b09224d00f5bb41ae29d6d2a6efa64d23a8d
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799718"
---
# <a name="managing-allows-and-blocks-in-the-tenant-allowblock-list"></a>Administración de permitidos y bloques en la lista de permitidos o bloqueados del espacio empresarial

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Las características descritas en este artículo están en versión preliminar, están sujetas a cambios y no están disponibles en todas las organizaciones.

En organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, es posible que no esté de acuerdo con el veredicto de filtrado de EOP. Por ejemplo, un mensaje bueno puede marcarse como falso positivo o un mensaje no seguro (un falso negativo).

La lista de permitidos/bloqueados del Centro de seguridad y cumplimiento de & le ofrece una forma de invalidar manualmente los veredictos de filtrado de Microsoft 365. La lista de permitidos/bloqueados del espacio empresarial se usa durante el flujo de correo y en el momento de los clics del usuario. Puede especificar direcciones URL para permitir o bloquear en la lista de permitidos o bloqueados del espacio empresarial.

En este tema se describe cómo configurar entradas en la lista de permitidos o bloqueados de inquilinos en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; EOP PowerShell independiente para organizaciones sin buzones de Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página **Permitir o bloquear lista de** inquilinos, use <https://protection.office.com/tenantAllowBlockList> .

- Los valores de dirección URL disponibles se describen en la sintaxis [de la dirección URL de la](#url-syntax-for-the-tenant-allowblock-list) sección Lista de permitidos o bloqueados del espacio empresarial más adelante en este artículo.

- La lista de permitidos o bloqueados del espacio empresarial permite un máximo de 500 entradas para las direcciones URL.

- Una entrada debe estar activa en un plazo de 15 minutos.

- Las entradas de bloque tienen prioridad sobre las entradas de permitidos.

- De forma predeterminada, las entradas de la lista de permitidos o bloqueados del espacio empresarial expirarán después de 30 días. Puede especificar una fecha o establecerla para que nunca expire.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:
  - Para agregar y quitar valores de la lista de permitidos  o bloqueados de inquilinos, debe ser miembro de los grupos de roles Administración de la organización o Administrador **de** seguridad.
  - Para obtener acceso de solo lectura a la lista de permitidos o bloqueados del espacio empresarial, debe ser miembro de los grupos de roles Lector **global** o **Lector de** seguridad.

  Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

  **Notas**:

  - Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Usar el Centro de seguridad & cumplimiento para crear entradas de dirección URL en la lista de permitidos o bloqueados del espacio empresarial

Para obtener más información sobre la sintaxis de las entradas de dirección [URL,](#url-syntax-for-the-tenant-allowblock-list) vea la sintaxis de la dirección URL de la sección Lista de permitidos o bloqueados del espacio empresarial más adelante en este artículo.

1. En el Centro de & cumplimiento, vaya **a** Listas de bloqueados o permitidos de \>  \> **inquilinos de la directiva de administración de amenazas.**

2. En la página Lista de direcciones URL **permitidas o** bloqueadas del espacio empresarial, compruebe que la pestaña **Direcciones** URL esté seleccionada y, a continuación, haga clic en **Agregar.**

3. En el **menú desplegable Agregar nuevas** direcciones URL que aparece, configure las siguientes opciones:

   - **Agregar direcciones URL con caracteres comodín:** escriba una dirección URL por línea, hasta un máximo de 20.

   - **Bloquear/Permitir:** seleccione si desea **permitir** o **bloquear** las direcciones URL especificadas.

   - **Nunca expira:** realice uno de los siguientes pasos:

     - Compruebe que la configuración esté desactivada ( Alternar desactivada) y use el cuadro Expira en para especificar la fecha de ![ ](../../media/scc-toggle-off.png) expiración de las entradas. 

     o

     - Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren: ![Habilitar](../../media/scc-toggle-on.png).

   - **Nota opcional:** escriba texto descriptivo para las entradas.

4. Cuando haya terminado, haga clic en **Agregar**.

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Usar el Centro de seguridad & cumplimiento para ver las entradas de la lista de permitidos o bloqueados del espacio empresarial

1. En el Centro de & cumplimiento, vaya **a** Listas de bloqueados o permitidos de \>  \> **inquilinos de la directiva de administración de amenazas.**

2. Seleccione la **pestaña Direcciones** URL.

Haga clic en los siguientes encabezados de columna para ordenar en orden ascendente o descendente:

- **Valor**
- **Acción:** **Bloquear** o **Permitir**.
- **Fecha de la última actualización**
- **Fecha de expiración**
- **Nota**

Haga **clic en** Grupo para agrupar las entradas por **Acción** (**Bloquear** o **Permitir**) o **Ninguno**.

Haga **clic en** Buscar, escriba todo o parte de un valor y, a continuación, presione ENTRAR para buscar un valor específico. Cuando haya terminado, haga clic en **Borrar búsqueda** Borrar icono ![ de ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) búsqueda.

Haga clic **en Filtro**. En el **menú** desplegable Filtro que aparece, configure cualquiera de las siguientes opciones:

- **Acción:** seleccione **Permitir,** **Bloquear** o ambos.

- **Nunca expira**: Seleccionar: Desactivar ![ o ](../../media/scc-toggle-off.png) activar: Activar o ![ ](../../media/scc-toggle-on.png) desactivar.

- **Last updated**: Select a start date (**From**), an end date (**To**) or both.

- **Fecha de** expiración: seleccione una fecha de inicio (**De**), una fecha de finalización (**Para**) o ambas.

Cuando haya terminado, haga clic **en Aplicar**.

Para borrar los filtros existentes, haga clic **en Filtro** y, en el **menú** desplegable Filtro que aparece, haga clic en **Borrar filtros.**

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>Usar el Centro de seguridad & cumplimiento para modificar las entradas de la lista de permitidos o bloqueados del espacio empresarial

No puede modificar el valor de la dirección URL en sí. En su lugar, debe eliminar la entrada y volver a crearla.

1. En el Centro de & cumplimiento, vaya **a** Listas de bloqueados o permitidos de \>  \> **inquilinos de la directiva de administración de amenazas.**

2. Seleccione la **pestaña Direcciones** URL.

3. Seleccione la entrada que desea modificar y, a continuación, haga clic **en el icono** Editar ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) edición.

4. En el menú desplegable que aparece, configura las siguientes opciones:

   - **Block/Allow**: Select **Allow** or **Block**.

   - **Nunca expira:** realice uno de los siguientes pasos:

     - Compruebe que la configuración esté desactivada (desactivar) y use el cuadro Expira en para especificar la fecha de ![ ](../../media/scc-toggle-off.png) expiración de la entrada. 

     o

     - Mueva el botón de alternancia a la derecha para configurar la entrada para que nunca expire: ![Habilitar](../../media/scc-toggle-on.png).

   - **Nota opcional:** escriba texto descriptivo para la entrada.

5. Cuando haya terminado, haga clic en **Guardar**.

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>Usar el Centro de seguridad & cumplimiento para quitar entradas de la lista de permitidos o bloqueados del espacio empresarial

1. En el Centro de & cumplimiento, vaya **a** Listas de bloqueados o permitidos de \>  \> **inquilinos de la directiva de administración de amenazas.**

2. Seleccione la **pestaña Direcciones** URL.

3. Seleccione la entrada que desea quitar y, a continuación, haga clic **en eliminar** icono ![ eliminar ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .

4. En el cuadro de diálogo de advertencia que aparece, haga clic **en Eliminar**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Usar Exchange Online PowerShell o EOP PowerShell independiente para configurar la lista de permitidos o bloqueados de inquilinos

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a>Usar PowerShell para agregar entradas a la lista de permitidos o bloqueados de inquilinos

Para agregar entradas a la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

En este ejemplo se agrega una entrada de bloque de dirección URL para contoso.com y todos los subdominios (por ejemplo, contoso.com, www.contoso.com y xyz.abc.contoso.com). Dado que no usamos los parámetros ExpirationDate o NoExpiration, la entrada expira después de 30 días.

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>Usar PowerShell para ver entradas en la lista de permitidos o bloqueados de inquilinos

Para ver entradas en la lista de permitidos o bloqueados de inquilinos, use la siguiente sintaxis:

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

En este ejemplo se devuelven todas las direcciones URL bloqueadas.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a>Usar PowerShell para modificar entradas en la lista de permitidos o bloqueados del espacio empresarial

No puede modificar el valor de la dirección URL en sí. En su lugar, debe eliminar la entrada y volver a crearla.

Para modificar las entradas de la lista de permitidos o bloqueados de inquilinos, use la siguiente sintaxis:

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

En este ejemplo se cambia la fecha de expiración de la entrada especificada.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a>Usar PowerShell para quitar entradas de la lista de permitidos o bloqueados de inquilinos

Para quitar entradas de la lista de permitidos o bloqueados de inquilinos, use la siguiente sintaxis:

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

En este ejemplo se quita la entrada de dirección URL especificada de la lista de permitidos o bloqueados del espacio empresarial.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>Sintaxis de dirección URL para la lista de permitidos o bloqueados del espacio empresarial

- Se permiten direcciones IP4v e IPv6, pero los puertos TCP/UDP no.

- No se permiten extensiones de nombre de archivo (por ejemplo, test.pdf).

- No se admite Unicode, pero Punycode sí.

- Los nombres de host se permiten si se cumplen todas las instrucciones siguientes:

  - El nombre de host contiene un punto.
  - Hay al menos un carácter a la izquierda del punto.
  - Hay al menos dos caracteres a la derecha del punto.

  Por ejemplo, `t.co` se permite; `.com` o no `contoso.` se permite.

- Las subpaths no están implícitas.

  Por ejemplo, `contoso.com` no incluye `contoso.com/a` .

- Se permiten caracteres comodín (*) en los siguientes escenarios:

  - Un carácter comodín izquierdo debe ir seguido de un punto para especificar un subdominio.

    Por ejemplo, `*.contoso.com` está permitido; `*contoso.com` no está permitido.

  - Un carácter comodín derecho debe seguir una barra diagonal (/) para especificar una ruta de acceso.

    Por ejemplo, `contoso.com/*` se permite; `contoso.com*` o no `contoso.com/ab*` se permite.

  - Todas las subpaths no están implicadas por un comodín derecho.

    Por ejemplo, `contoso.com/*` no incluye `contoso.com/a` .

  - `*.com*` no es válido (no es un dominio que se puede resolver y el comodín derecho no sigue una barra diagonal).

  - No se permiten caracteres comodín en las direcciones IP.

- El carácter de tilde (~) está disponible en los siguientes escenarios:

  - Una tilde izquierda implica un dominio y todos los subdominios.

    Por `~contoso.com` ejemplo, incluye `contoso.com` y `*.contoso.com` .

- Se producirá un error en las entradas de dirección URL que contienen protocolos (por ejemplo, , o ) porque las entradas de dirección URL se `http://` aplican a todos los `https://` `ftp://` protocolos.

- No se admite ni se requiere un nombre de usuario o contraseña.

- Las comillas (' o ") son caracteres no válidos.

- Una dirección URL debe incluir todos los redireccionamientos siempre que sea posible.

### <a name="url-entry-scenarios"></a>Escenarios de entrada de dirección URL

Las entradas url válidas y sus resultados se describen en las secciones siguientes.

#### <a name="scenario-no-wildcards"></a>Escenario: sin caracteres comodín

**Entrada:**`contoso.com`

- **Permitir coincidencia:** contoso.com

- **Permitir no coincidir:**

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Bloquear coincidencia:**

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Bloque no coincidente:** abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Escenario: Comodín izquierdo (subdominio)

**Entrada:**`*.contoso.com`

- **Permitir coincidencia** y **bloquear coincidencia:**

  - www.contoso.com
  - xyz.abc.contoso.com

- **Permitir no coincidentes** y **Bloquear no coincidentes:**

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Escenario: Comodín derecho en la parte superior de la ruta de acceso

**Entrada:**`contoso.com/a/*`

- **Permitir coincidencia** y **bloquear coincidencia:**

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Permitir no coincidentes** y **Bloquear no coincidentes:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Escenario: tilde izquierda

**Entrada:**`~contoso.com`

- **Permitir coincidencia** y **bloquear coincidencia:**

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Permitir no coincidentes** y **Bloquear no coincidentes:**

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Escenario: sufijo comodín derecho

**Entrada:**`contoso.com/*`

- **Permitir coincidencia** y **bloquear coincidencia:**

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Permitir no coincidentes** y **Bloquear no coincidentes:** contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Escenario: Subdominio comodín izquierdo y sufijo comodín derecho

**Entrada:**`*.contoso.com/*`

- **Permitir coincidencia** y **bloquear coincidencia:**

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Permitir no coincidentes** y **Bloquear no coincidentes:** contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Escenario: tilde izquierda y derecha

**Entrada:**`~contoso.com~`

- **Permitir coincidencia** y **bloquear coincidencia:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Permitir no coincidentes** y **Bloquear no coincidentes:**

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Escenario: dirección IP

**Entrada:**`1.2.3.4`

- **Permitir coincidencia** y **bloquear** coincidencia: 1.2.3.4

- **Permitir no coincidentes** y **Bloquear no coincidentes:**

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>Dirección IP con comodín derecho

**Entrada:**`1.2.3.4/*`

- **Permitir coincidencia** y **bloquear coincidencia:**

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Ejemplos de entradas no válidas

Las siguientes entradas no son válidas:

- **Valores de dominio que faltan o no son válidos:**

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **Comodín en texto o sin caracteres de espaciado:**

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **Direcciones IP con puertos:**

  - contoso.com:443
  - abc.contoso.com:25

- **Caracteres comodín no descriptivos:**

  - \*
  - \*.\*

- **Caracteres comodín intermedios:**

  - conto \* so.com
  - conto~so.com

- **Caracteres comodín dobles**

  - contoso.com/\*\*
  - contoso.com/\*/\*
