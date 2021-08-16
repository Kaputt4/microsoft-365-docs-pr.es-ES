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
description: Los administradores pueden aprender a administrar los permisos y los bloques en la lista de inquilinos permitidos o bloqueados en el portal de seguridad.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 09a710a5fb1518b819704e881534efda15236520
ms.sourcegitcommit: 99817013bcb26b7ed051e011c8addb716cc91d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58349973"
---
# <a name="manage-the-tenant-allowblock-list"></a>Administrar la lista de bloqueados y permitidos del espacio empresarial

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> Algunas de las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y no están disponibles en todas las organizaciones.
> 
> Si su organización no tiene las características de suplantación de identidad como se describe en este artículo, vea la experiencia de administración de suplantación de identidad anterior en [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).

En Microsoft 365 organizaciones con buzones de correo en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, es posible que no esté de acuerdo con el veredicto de filtrado de EOP. Por ejemplo, un mensaje bueno puede marcarse como malo (un falso positivo) o un mensaje malo se puede permitir a través (un falso negativo).

La lista de inquilinos permitidos o bloqueados en el portal de Microsoft 365 Defender le ofrece una forma de invalidar manualmente los Microsoft 365 de filtrado. La lista de inquilinos permitidos o bloqueados se usa durante el flujo de correo para los mensajes entrantes (no se aplica a los mensajes dentro de la organización) y en el momento de los clics del usuario. Puede especificar los siguientes tipos de invalidaciones:

- Direcciones URL que se bloquearán.
- Archivos que se va a bloquear.
- Mensajes de correo electrónico o dominios del remitente que se bloquearán.
- Remitentes suplantados para permitir o bloquear. Si invalida el veredicto permitir o bloquear en la información de inteligencia suplantada, el remitente  suplantado se convierte en una entrada manual de permitir o bloquear que solo aparece en la pestaña Suplantación de identidad de la lista de permitidos o bloqueados del inquilino. [](learn-about-spoof-intelligence.md) También puede crear entradas de permitir o bloquear manualmente para remitentes suplantados aquí antes de que los detecte la inteligencia de suplantación de identidad.
- Direcciones URL que se permiten.
- Archivos que se permiten.
- Mensajes de correo electrónico o dominios del remitente que se permitirán.

En este artículo se describe cómo configurar entradas en la lista de inquilinos permitidos o bloqueados en el portal de Microsoft 365 Defender o en PowerShell (PowerShell de Exchange Online para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com/>. Para ir directamente a la página **Listas de inquilinos permitidos o** bloqueados, use <https://security.microsoft.com/tenantAllowBlockList> .

- Los archivos se especifican mediante el valor hash SHA256 del archivo. Para buscar el valor hash SHA256 de un archivo en Windows, ejecute el siguiente comando en un símbolo del sistema:

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Un valor de ejemplo es `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` . No se admiten valores de hash perceptual (pHash).

- Los valores de dirección URL disponibles se describen en la sintaxis url de la sección Lista de [inquilinos permitidos o](#url-syntax-for-the-tenant-allowblock-list) bloqueados más adelante en este artículo.

- La lista de inquilinos permitidos o bloqueados permite un máximo de 500 entradas para remitentes, 500 entradas para direcciones URL y 500 entradas para hashes de archivo.

- El número máximo de caracteres para cada entrada es:
  - Hashes de archivo = 64
  - URL = 250

- Una entrada debe estar activa en 30 minutos.

- De forma predeterminada, las entradas de la lista de inquilinos permitidos o bloqueados expirarán después de 30 días. Puede especificar una fecha o establecerla para que no expire nunca.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener permisos asignados en Exchange Online antes de poder realizar los procedimientos de este artículo:
  - **Remitentes, direcciones URL y archivos:**
    - Para agregar y quitar valores de la lista de inquilinos permitidos o bloqueados, debe ser miembro de los grupos de roles Administración de la **organización,** Administrador de seguridad o Operador de seguridad o se le asigna el rol Administrador de **allowBlockList** de inquilino. 
    - Para obtener acceso de solo lectura a la lista de inquilinos permitidos o bloqueados, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.
  - **Suplantación:** una de las siguientes combinaciones:
    - **Administración de organizaciones**
    - **Administrador de seguridad** <u>y</u> **Configuración de solo vista** o Administración de la organización de solo **vista**.

  Para obtener más información, vea los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 la cual proporciona a los usuarios los permisos necesarios _y_ para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  >
  > - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

## <a name="configure-the-tenant-allowblock-list"></a>Configurar la lista de inquilinos permitidos o bloqueados

### <a name="use-the-microsoft-365-defender-portal"></a>Uso del portal de Microsoft 365 Defender

En el portal Microsoft 365 Defender, vaya a **Directivas &** sección Reglas de directivas de amenazas sección Listas de \>  \>  \> **inquilinos permitidos o bloqueados.**

Para agregar todos los bloques, vea [Add blocks in the Tenant Allow/Block List](manage-tenant-blocks.md).

Para agregar todos los permitidos, vea [Agregar permite en la lista de inquilinos permitidos o bloqueados.](manage-tenant-allows.md)

Para modificar y quitar todos los bloques y permitir, vea Modificar y quitar entradas en la lista de [inquilinos permitidos o bloqueados.](modify-remove-entries-tenant-allow-block.md)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell"></a>Usar Exchange Online PowerShell o PowerShell independiente de EOP

Para administrar todas las permitidos y bloques, vea Agregar bloques en la lista de inquilinos [permitidos/bloqueados](manage-tenant-blocks.md), Agregar permite en la lista de inquilinos [permitir/bloquear](manage-tenant-allows.md)y Modificar y quitar entradas en la lista de inquilinos permitidos [o bloqueados.](modify-remove-entries-tenant-allow-block.md)

## <a name="view-entries-in-the-tenant-allowblock-list"></a>Ver entradas en la lista de inquilinos permitidos o bloqueados

1. En el portal Microsoft 365 Defender, vaya a **Directivas &** sección Reglas de directivas de amenazas sección Listas de \>  \>  \> **inquilinos permitidos o bloqueados.**

2. Seleccione la pestaña que desee. Las columnas disponibles dependen de la pestaña seleccionada:

   - **Remitentes**:
     - **Valor:** el dominio del remitente o la dirección de correo electrónico.
     - **Action:** el valor **Allow** o **Block**.
     - **Actualizado por última vez**
     - **Quitar en**
     - **Notas**
   - **DIRECCIONES URL:**
     - **Value**: La dirección URL.
     - **Action:** el valor **Allow** o **Block**.
     - **Actualizado por última vez**
     - **Quitar en**
     - **Notas**
   - **Files**
     - **Valor:** hash de archivo.
     - **Action:** el valor **Allow** o **Block**.
     - **Actualizado por última vez**
     - **Quitar en**
     - **Notas**
   - **Spoofing**
     - **Usuario suplantado**
     - **Infraestructura de envío**
     - **Tipo de suplantación:** el **valor Interno** o **Externo**.
     - **Action:** el valor **Block** o **Allow**.

   Puede hacer clic en un encabezado de columna para ordenar en orden ascendente o descendente.

   Puede hacer clic **en Grupo** para agrupar los resultados. Los valores disponibles dependen de la pestaña seleccionada:

   - **Remitentes:** puede agrupar los resultados por **Acción**.
   - **DIRECCIONES URL:** puede agrupar los resultados por **Acción**.
   - **Archivos:** puede agrupar los resultados por **Acción**.
   - **Suplantación:** puede agrupar los resultados por **tipo Action** o **Spoof**.

   Haga **clic en** Buscar, escriba todo o parte de un valor y, a continuación, presione ENTRAR para buscar un valor específico. Cuando haya terminado, haga clic en ![ Borrar icono de búsqueda Borrar ](../../media/m365-cc-sc-close-icon.png) **búsqueda.**

   Haga **clic en** Filtrar para filtrar los resultados. Los valores que están disponibles en **el** control desplegable Filtro que aparece dependen de la pestaña seleccionada:

   - **Remitentes**
     - **Action**
     - **No expirar nunca**
     - **Fecha de última actualización**
     - **Quitar en**
   - **DIRECCIONES URL**
     - **Action**
     - **No expirar nunca**
     - **Fecha de última actualización**
     - **Quitar en**
   - **Files**
     - **Action**
     - **No expirar nunca**
     - **Actualizado por última vez**
     - **Quitar en**
   - **Spoofing**
     - **Action**
     - **Tipo de suplantación**

   Cuando haya terminado, haga clic en **Aplicar**. Para borrar los filtros existentes, haga clic **en Filtrar** y, en el **menú** desplegable Filtro que aparece, haga clic en **Borrar filtros**.

4. Cuando haya terminado, haga clic en **Agregar**.

## <a name="view-sender-file-or-url-entries-in-the-tenant-allowblock-list"></a>Ver entradas de remitente, archivo o dirección URL en la lista de inquilinos permitidos o bloqueados

Para ver entradas de remitente, archivo o dirección URL de bloque en la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:

```powershell
Get-TenantAllowBlockListItems -ListType <Sender | FileHash | URL> [-Entry <SenderValue | FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

En este ejemplo se devuelve información sobre el valor hash de archivo especificado.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

En este ejemplo se devuelven todas las direcciones URL bloqueadas.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).

## <a name="view-spoofed-sender-entries"></a>Ver entradas de remitente suplantadas

Para ver entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

En este ejemplo se devuelven todas las entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados.

```powershell
Get-TenantAllowBlockListSpoofItems
```

En este ejemplo se devuelven todas las entradas de remitente suplantadas que son internas.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

En este ejemplo se devuelven todas las entradas de remitente suplantadas bloqueadas que son externas.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).

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

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Sintaxis de par de dominio para entradas de remitente suplantadas en la lista de inquilinos permitidos/bloqueados

Un par de dominio para un remitente suplantado en la lista de inquilinos permitidos o bloqueados usa la siguiente sintaxis: `<Spoofed user>, <Sending infrastructure>` .

- **Usuario suplantado:** este valor implica la dirección de correo electrónico del usuario  suplantado que se muestra en el cuadro De de los clientes de correo electrónico. Esta dirección también se conoce como `5322.From` la dirección. Los valores válidos son:
  - Una dirección de correo electrónico individual (por ejemplo, chris@contoso.com).
  - Un dominio de correo electrónico (por ejemplo, contoso.com).
  - El carácter comodín (por ejemplo, \* ).

- **Infraestructura de** envío: este valor indica el origen de los mensajes del usuario suplantado. Los valores válidos son:
  - El dominio encontrado en una búsqueda dns inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen (por ejemplo, fabrikam.com).
  - Si la dirección IP de origen no tiene ningún registro PTR, la infraestructura de envío se identifica como \<source IP\> /24 (por ejemplo, 192.168.100.100/24).

Estos son algunos ejemplos de pares de dominio válidos para identificar remitentes suplantados:

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

El número máximo de entradas de remitente suplantadas es 1000.

Agregar un par de dominio solo permite o bloquea *la* combinación del usuario suplantado *y la* infraestructura de envío. No permite el correo electrónico del usuario suplantado de ningún origen, ni permite el correo electrónico del origen de la infraestructura de envío para ningún usuario suplantado. 

Por ejemplo, agrega una entrada allow para el siguiente par de dominio:

- **Dominio**: gmail.com
- **Infraestructura**: tms.mx.com

Solo los mensajes de ese dominio *y* el par de infraestructura de envío pueden suplantación. Otros remitentes que intentan suplantar gmail.com no están permitidos. Los mensajes de remitentes de otros dominios que se originaron tms.mx.com se comprueban mediante la inteligencia de suplantación de identidad.
