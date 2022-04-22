---
title: Administrar los bloques y los permitidos en la lista de permitidos o bloqueados de inquilinos
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Los administradores pueden aprender a administrar permisos y bloques en la lista de permitidos o bloqueados de inquilinos en el portal de seguridad.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0ed23cf7bfe8db25ed216859c434e86f14710db8
ms.sourcegitcommit: 363bdc517bd2564c6420cf21f352e97079f950e0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2022
ms.locfileid: "65031849"
---
# <a name="manage-the-tenant-allowblock-list"></a>Administrar la lista de bloqueados y permitidos del espacio empresarial

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> Algunas de las características descritas en este artículo están en versión preliminar, están sujetas a cambios y no están disponibles en todas las organizaciones.
>
> Si su organización no tiene las características de suplantación como se describe en este artículo, consulte la experiencia de administración de suplantación anterior en [Administración de remitentes suplantados mediante la directiva de inteligencia sobre suplantación de identidad y la información de inteligencia sobre suplantación de identidad en EOP](walkthrough-spoof-intelligence-insight.md).

En Microsoft 365 organizaciones con buzones de correo en organizaciones Exchange Online o independientes de Exchange Online Protection (EOP) sin Exchange Online buzones, es posible que no esté de acuerdo con el veredicto de filtrado de EOP. Por ejemplo, un buen mensaje podría marcarse como incorrecto (un falso positivo) o un mensaje incorrecto podría permitirse a través de (un falso negativo).

La lista de permitidos o bloqueados de inquilinos del portal de Microsoft 365 Defender proporciona una manera de invalidar manualmente los veredictos de filtrado de Microsoft 365. La lista de permitidos o bloqueados de inquilinos se usa durante el flujo de correo para los mensajes entrantes (no se aplica a los mensajes dentro de la organización) y en el momento en que el usuario hace clic. Puede especificar los siguientes tipos de invalidaciones:

- Direcciones URL que se van a bloquear.
- Archivos que se van a bloquear.
- Correos electrónicos o dominios del remitente que se van a bloquear.
- Remitentes suplantados para permitir o bloquear. Si invalida el veredicto de permitir o bloquear en la [información de inteligencia](learn-about-spoof-intelligence.md) sobre suplantación de identidad, el remitente suplantado se convierte en una entrada de bloqueo o permiso manual que solo aparece en la pestaña **Suplantación** de identidad de la lista de permitidos o bloqueados de inquilinos. También puede crear manualmente entradas de permitir o bloquear para remitentes suplantados aquí antes de que se detecten mediante inteligencia de suplantación de identidad.
- Direcciones URL que se van a permitir.
- Archivos que se van a permitir.
- Dominios o correos electrónicos del remitente que se van a permitir.

En este artículo se describe cómo configurar entradas en la lista de inquilinos permitidos o bloqueados en el portal de Microsoft 365 Defender o en PowerShell (Exchange Online PowerShell para organizaciones Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin Exchange Online buzones).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Permitir o bloquear listas de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

- Los archivos se especifican mediante el valor hash SHA256 del archivo. Para buscar el valor hash SHA256 de un archivo en Windows, ejecute el siguiente comando en un símbolo del sistema:

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Un valor de ejemplo es `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`. No se admiten los valores de hash perceptual (pHash).

- Los valores de dirección URL disponibles se describen en la [sintaxis de dirección URL de la sección Lista de permitidos o bloqueados](#url-syntax-for-the-tenant-allowblock-list) de inquilinos más adelante en este artículo.

- La lista de permitidos o bloqueados de inquilinos permite un máximo de 500 entradas para remitentes, 500 entradas para direcciones URL, 500 entradas para hashes de archivo y 1024 entradas para suplantación de identidad (remitentes suplantados).

- El número máximo de caracteres para cada entrada es:
  - Hash de archivo = 64
  - URL = 250

- Una entrada debe estar activa en un plazo de 30 minutos.

- De forma predeterminada, las entradas de la lista de inquilinos permitidos o bloqueados expirarán después de 30 días. Puede especificar una fecha o establecerla para que nunca expire.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener permisos asignados en el portal de Microsoft 365 Defender para poder realizar los procedimientos de este artículo:
  - **Remitentes, direcciones URL y archivos**:
    - Para agregar y quitar valores de la lista de permitidos o bloqueados de inquilinos, debe ser miembro de 
      -   **Grupo de roles Administración de la organización** o **Administrador de seguridad** (**rol administrador de seguridad**)
      -    **Grupo de roles Operador de seguridad** (**Administrador de listas de permitidos de inquilinos**).
    - Para obtener acceso de solo lectura a la lista de permitidos o bloqueados de inquilinos, debe ser miembro de 
      - **Grupo de roles lector global**
      - **Grupo de roles lector de seguridad**
  - **Suplantación de identidad**: una de las siguientes combinaciones:
    - **Administración de organizaciones**
    - **Administrador de seguridad** <u>y</u> **Configuración de solo vista** o **Administración de la organización de solo vista**.

  Para obtener más información, vea los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - La adición de usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365. Para obtener más información, consulte [Acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).
  >
  > - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

## <a name="configure-the-tenant-allowblock-list"></a>Configuración de la lista de permitidos o bloqueados de inquilinos

### <a name="use-the-microsoft-365-defender-portal"></a>Uso del portal de Microsoft 365 Defender

En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas** \> **Directivas** \> de amenazas Listas **de inquilinos permitidos o bloqueados** en la sección **Reglas**. Para ir directamente a la página **Permitir o bloquear listas de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

Para agregar todos los bloques, consulte [Agregar bloques en la lista de permitidos o bloques de inquilinos](manage-tenant-blocks.md).

Para agregar todos los permitidos, consulte [Agregar permite en la lista de permitidos o bloqueados de inquilinos](manage-tenant-allows.md).

Para modificar y quitar todos los bloques y permite, consulte [Modificación y eliminación de entradas en la lista de permitidos o bloques](modify-remove-entries-tenant-allow-block.md) de inquilinos.

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell"></a>Uso Exchange Online PowerShell o PowerShell de EOP independiente

Para administrar todos los bloques y permitidos, vea [Agregar bloques en la lista de permitidos o bloques](manage-tenant-blocks.md) de inquilinos, [Agregar permite en la lista de permitidos o bloques](manage-tenant-allows.md) de inquilinos y [Modificar y quitar entradas en la lista de permitidos o bloques de inquilinos](modify-remove-entries-tenant-allow-block.md).

## <a name="view-entries-in-the-tenant-allowblock-list"></a>Visualización de entradas en la lista de permitidos o bloqueados de inquilinos

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas** \> **Directivas** \> de amenazas Listas **de inquilinos permitidos o bloqueados** en la sección **Reglas**. Para ir directamente a la página **Permitir o bloquear listas de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. Seleccione la pestaña que desee. Las columnas que están disponibles dependen de la pestaña seleccionada:

   - **Remitentes**:
     - **Valor**: dominio o dirección de correo electrónico del remitente.
     - **Acción**: el valor **Permitir** o **Bloquear**.
     - **Modificado por**
     - **Actualizado por última vez**
     - **Quitar activado**
     - **Notas**
   - **Direcciones URL**:
     - **Valor**: la dirección URL.
     - **Acción**: el valor **Permitir** o **Bloquear**.
     - **Modificado por**
     - **Actualizado por última vez**
     - **Quitar activado**
     - **Notas**
   - **Files**
     - **Valor**: el hash de archivo.
     - **Acción**: el valor **Permitir** o **Bloquear**.
     - **Modificado por**
     - **Actualizado por última vez**
     - **Quitar activado**
     - **Notas**
   - **Spoofing**
     - **Usuario suplantado**
     - **Infraestructura de envío**
     - **Tipo de suplantación:** el valor **Interno** o **Externo**.
     - **Acción**: el valor **Bloquear** o **Permitir**.

   Puede hacer clic en un encabezado de columna para ordenar en orden ascendente o descendente.

   Puede hacer clic en **Agrupar** para agrupar los resultados. Los valores que están disponibles dependen de la pestaña seleccionada:

   - **Remitentes**: puede agrupar los resultados por **acción**.
   - **Direcciones URL**: puede agrupar los resultados por **acción**.
   - **Archivos**: puede agrupar los resultados por **acción**.
   - **Suplantación de identidad**: puede agrupar los resultados por **tipo de acción** o **suplantación de identidad**.

   Haga clic en **Buscar**, escriba todo o parte de un valor y, a continuación, presione ENTRAR para buscar un valor específico. Cuando haya terminado, haga clic en ![el icono Borrar búsqueda.](../../media/m365-cc-sc-close-icon.png) **Borrar búsqueda**.

   Haga clic en **Filtrar** para filtrar los resultados. Los valores que están disponibles en el control flotante **Filtro** que aparece dependen de la pestaña seleccionada:

   - **Remitentes**
     - **Action**
     - **Nunca expirar**
     - **Fecha de última actualización**
     - **Quitar activado**
   - **Url**
     - **Action**
     - **Nunca expirar**
     - **Fecha de última actualización**
     - **Quitar activado**
   - **Files**
     - **Action**
     - **Nunca expirar**
     - **Actualizado por última vez**
     - **Quitar activado**
   - **Spoofing**
     - **Action**
     - **Tipo de suplantación de identidad**

   Cuando haya terminado, haga clic en **Aplicar**. Para borrar los filtros existentes, haga clic en **Filtrar** y, en el control flotante **Filtro** que aparece, haga clic en **Borrar filtros**.

4. Cuando haya terminado, haga clic en **Agregar**.

## <a name="view-sender-file-or-url-entries-in-the-tenant-allowblock-list"></a>Visualización de entradas de remitente, archivo o dirección URL en la lista de permitidos o bloqueados de inquilinos

Para ver las entradas de remitente de bloque, archivo o dirección URL en la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
Get-TenantAllowBlockListItems -ListType <Sender | FileHash | URL> [-Entry <SenderValue | FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

En este ejemplo se devuelve información del valor hash de archivo especificado.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

En este ejemplo se devuelven todas las direcciones URL bloqueadas.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).

## <a name="view-spoofed-sender-entries"></a>Visualización de entradas de remitente suplantadas

Para ver las entradas de remitente suplantadas en la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

En este ejemplo se devuelven todas las entradas de remitente suplantadas en la lista de permitidos o bloqueados de inquilinos.

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

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>Sintaxis de dirección URL para la lista de permitidos o bloqueados de inquilinos

- Se permiten direcciones IPv4 e IPv6, pero los puertos TCP/UDP no.

- No se permiten extensiones de nombre de archivo (por ejemplo, test.pdf).

- Unicode no se admite, pero Punycode sí.

- Los nombres de host se permiten si se cumplen todas las instrucciones siguientes:
  - El nombre de host contiene un punto.
  - Hay al menos un carácter a la izquierda del punto.
  - Hay al menos dos caracteres a la derecha del punto.

  Por ejemplo, `t.co` se permite; `.com` o `contoso.` no se permiten.

- Las rutas secundarias no están implícitas para permitir.

  Por ejemplo, `contoso.com` no incluye `contoso.com/a`.

- Se permiten caracteres comodín (*) en los siguientes escenarios:

  - Un carácter comodín izquierdo debe ir seguido de un punto para especificar un subdominio.

    Por ejemplo, `*.contoso.com` se permite; `*contoso.com` no se permite.

  - Un carácter comodín derecho debe seguir una barra diagonal (/) para especificar una ruta de acceso.

    Por ejemplo, `contoso.com/*` se permite; `contoso.com*` o `contoso.com/ab*` no se permiten.

  - `*.com*` no es válido (no es un dominio que se puede resolver y el carácter comodín derecho no sigue una barra diagonal).

  - No se permiten caracteres comodín en las direcciones IP.

- El carácter de tilde (~) está disponible en los escenarios siguientes:

  - Una tilde izquierda implica un dominio y todos los subdominios.

    Por ejemplo `~contoso.com` , incluye `contoso.com` y `*.contoso.com`.

- Se producirá un error en las entradas de dirección URL que contienen protocolos (por ejemplo, `http://`, `https://`o `ftp://`), porque las entradas de dirección URL se aplican a todos los protocolos.

- No se admite ni se requiere un nombre de usuario o contraseña.

- Las comillas (' o ") son caracteres no válidos.

- Una dirección URL debe incluir todas las redirecciones siempre que sea posible.

### <a name="url-entry-scenarios"></a>Escenarios de entrada de dirección URL

Las entradas url válidas y sus resultados se describen en las secciones siguientes.

#### <a name="scenario-no-wildcards"></a>Escenario: Sin caracteres comodín

**Entrada**: `contoso.com`

- **Permitir coincidencia**: contoso.com

- **Permitir no coincidente**:

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Coincidencia de bloques**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Bloque no coincidente**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Escenario: Carácter comodín izquierdo (subdominio)

**Entrada**: `*.contoso.com`

- **Permitir coincidencia** y **Bloquear coincidencia**:

  - www.contoso.com
  - xyz.abc.contoso.com

- **Permitir no coincidente** y **Bloquear no coincidente**:

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Escenario: Carácter comodín derecho en la parte superior de la ruta de acceso

**Entrada**: `contoso.com/a/*`

- **Permitir coincidencia** y **Bloquear coincidencia**:

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Permitir no coincidente** y **Bloquear no coincidente**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Escenario: tilde izquierda

**Entrada**: `~contoso.com`

- **Permitir coincidencia** y **Bloquear coincidencia**:

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Permitir no coincidente** y **Bloquear no coincidente**:

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Escenario: Sufijo comodín derecho

**Entrada**: `contoso.com/*`

- **Permitir coincidencia** y **Bloquear coincidencia**:

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Permitir no coincidente** y **Bloquear no coincidente**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Escenario: Subdominio de caracteres comodín izquierdos y sufijo comodín derecho

**Entrada**: `*.contoso.com/*`

- **Permitir coincidencia** y **Bloquear coincidencia**:

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Permitir no coincidente** y **Bloquear no coincidente**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Escenario: tilde izquierda y derecha

**Entrada**: `~contoso.com~`

- **Permitir coincidencia** y **Bloquear coincidencia**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Permitir no coincidente** y **Bloquear no coincidente**:

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Escenario: dirección IP

**Entrada**: `1.2.3.4`

- **Permitir coincidencia** y **Bloquear coincidencia**: 1.2.3.4

- **Permitir no coincidente** y **Bloquear no coincidente**:

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>Dirección IP con carácter comodín derecho

**Entrada**: `1.2.3.4/*`

- **Permitir coincidencia** y **Bloquear coincidencia**:

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Ejemplos de entradas no válidas

Las siguientes entradas no son válidas:

- **Valores de dominio que faltan o no son válidos**:

  - Contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **Carácter comodín en texto o sin caracteres de espaciado**:

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

- **Caracteres comodín intermedios**:

  - conto\* so.com
  - conto~so.com

- **Caracteres comodín dobles**

  - contoso.com/\*\*
  - contoso.com/\*/\*

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Sintaxis de par de dominio para entradas de remitente suplantadas en la lista de permitidos o bloqueados de inquilinos

Un par de dominios para un remitente suplantado en la lista de permitidos o bloqueados de inquilinos usa la sintaxis siguiente: `<Spoofed user>, <Sending infrastructure>`.

- **Usuario suplantado**: este valor implica la dirección de correo electrónico del usuario suplantado que se muestra en el cuadro **De** en los clientes de correo electrónico. Esta dirección también se conoce como dirección `5322.From` . Los valores válidos son:
  - Una dirección de correo electrónico individual (por ejemplo, chris@contoso.com).
  - Un dominio de correo electrónico (por ejemplo, contoso.com).
  - Carácter comodín (por ejemplo, \*).

- **Infraestructura de envío**: este valor indica el origen de los mensajes del usuario suplantado. Los valores válidos son:
  - Dominio que se encuentra en una búsqueda dns inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen (por ejemplo, fabrikam.com).
  - Si la dirección IP de origen no tiene ningún registro PTR, la infraestructura de envío se identifica como \<source IP\>/24 (por ejemplo, 192.168.100.100/24).

Estos son algunos ejemplos de pares de dominio válidos para identificar remitentes suplantados:

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

El número máximo de entradas de remitente suplantadas es 1000.

Agregar un par de dominio solo permite o bloquea la *combinación* del usuario suplantado *y* la infraestructura de envío. No permite el correo electrónico del usuario suplantado de ningún origen ni permite el correo electrónico del origen de la infraestructura de envío para cualquier usuario suplantado. 

Por ejemplo, agrega una entrada allow para el siguiente par de dominio:

- **Dominio**: gmail.com
- **Infraestructura**: tms.mx.com

Solo los mensajes de ese dominio *y* el par de infraestructura de envío pueden suplantarse. No se permiten otros remitentes que intenten suplantar gmail.com. Los mensajes de remitentes de otros dominios que se originan en tms.mx.com se comprueban mediante inteligencia suplantada.
