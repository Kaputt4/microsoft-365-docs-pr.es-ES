---
title: Permitir o bloquear direcciones URL mediante la lista de permitidos o bloqueados de inquilinos
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
- MET150manage-tenant-allows.md
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a permitir o bloquear direcciones URL en la lista de inquilinos permitidos o bloqueados en el portal de seguridad.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 72183614b8d74dad5e173b5db51ab35e4d2e6a49
ms.sourcegitcommit: b0b1be67de8f40b199bb9b51eb3568e59377e93a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2022
ms.locfileid: "66159979"
---
# <a name="allow-or-block-urls-using-the-tenant-allowblock-list"></a>Permitir o bloquear direcciones URL mediante la lista de permitidos o bloqueados de inquilinos

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Puede usar el portal de Microsoft 365 Defender o PowerShell para permitir o bloquear direcciones URL en la lista de permitidos o bloqueados de inquilinos.

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

  - Un carácter comodín izquierdo debe ir seguido de un punto para especificar un subdominio. (solo se aplica a bloques)

    Por ejemplo, `*.contoso.com` se permite; `*contoso.com` no se permite.

  - Un carácter comodín derecho debe seguir una barra diagonal (/) para especificar una ruta de acceso.

    Por ejemplo, `contoso.com/*` se permite; `contoso.com*` o `contoso.com/ab*` no se permiten.

  - `*.com*` no es válido (no es un dominio que se puede resolver y el carácter comodín derecho no sigue una barra diagonal).

  - No se permiten caracteres comodín en las direcciones IP.

- El carácter de tilde (~) está disponible en los escenarios siguientes:

  - Una tilde izquierda implica un dominio y todos los subdominios.

    Por ejemplo `~contoso.com` , incluye `contoso.com` y `*.contoso.com`.

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
  - contoso.com
  - contoso.com/q=a@contoso.com

- **Coincidencia de bloques**:
  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - contoso.com
  - contoso.com/q=a@contoso.com

- **Bloque no coincidente**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Escenario: Carácter comodín izquierdo (subdominio)

> [!NOTE]
> Este escenario solo se aplica a bloques.

**Entrada**: `*.contoso.com`

- **Coincidencia de bloques**:
  - contoso.com
  - xyz.abc.contoso.com

- **Bloque no coincidente**:
  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Escenario: Carácter comodín derecho en la parte superior de la ruta de acceso

**Entrada**: `contoso.com/a/*`

- **Permitir coincidencia** y **Bloquear coincidencia**:
  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Permitir no coincidente** y **Bloquear no coincidente**:
  - contoso.com
  - contoso.com/a
  - contoso.com
  - contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Escenario: tilde izquierda

**Entrada**: `~contoso.com`

- **Permitir coincidencia** y **Bloquear coincidencia**:
  - contoso.com
  - contoso.com
  - xyz.abc.contoso.com

- **Permitir no coincidente** y **Bloquear no coincidente**:
  - 123contoso.com
  - contoso.com/abc
  - contoso.com/abc

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

> [!NOTE]
> Este escenario solo se aplica a bloques.

**Entrada**: `*.contoso.com/*`

- **Coincidencia de bloques**:
  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - contoso.com/a
  - contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Bloquear no coincidente**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Escenario: tilde izquierda y derecha

**Entrada**: `~contoso.com~`

- **Permitir coincidencia** y **Bloquear coincidencia**:

  - contoso.com
  - contoso.com/a
  - contoso.com
  - contoso.com/b
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

  - conto\*so.com
  - conto~so.com

- **Caracteres comodín dobles**

  - contoso.com/\*\*
  - contoso.com/\*/\*

## <a name="create-block-url-entries-in-the-tenant-allowblock-list"></a>Creación de entradas de dirección URL de bloque en la lista de permitidos o bloqueados de inquilinos

### <a name="use-microsoft-365-defender"></a>Uso de Microsoft 365 Defender

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas De directivas** \> de amenazas sección \> **Reglas de directivas** de **amenazas** \> **Listas de permitidos o bloques de inquilinos**. O bien, para ir directamente a la página **Permitir o bloquear lista de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

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
> Los correos electrónicos que contienen estas direcciones URL se bloquearán como _phish_.

### <a name="use-powershell"></a>Usar PowerShell

Para agregar entradas de dirección URL de bloque en la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
New-TenantAllowBlockListItems -ListType <Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

En este ejemplo se agrega una entrada de dirección URL de bloque para contoso.com y todos los subdominios (por ejemplo, contoso.com y xyz.abc.contoso.com). Dado que no usamos los parámetros ExpirationDate o NoExpiration, la entrada expira después de 30 días.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

## <a name="create-allow-url-entries"></a>Creación de entradas de direcciones URL permitidas

### <a name="use-microsoft-365-defender"></a>Uso de Microsoft 365 Defender

Permitir direcciones URL en la página **Envíos** de Microsoft 365 Defender.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Acciones & envíos envíos**\>. O bien, para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la página **Envíos** , seleccione la pestaña **Direcciones URL** y, a continuación, haga clic en ![el icono Enviar a Microsoft para análisis.](../../media/m365-cc-sc-create-icon.png) **Envíe a Microsoft para su análisis**.

3. Use el control flotante **Enviar a Microsoft para revisar** para enviar un mensaje agregando la dirección URL.

4. En la sección **Seleccionar un motivo para enviar a Microsoft**, seleccione **No debería haberse bloqueado (falso positivo).**

5. Active la opción **Permitir direcciones URL como esta** .

6. En la lista desplegable **Quitar después**, especifique cuánto tiempo desea que funcione la opción Permitir.

7. Cuando haya terminado, haga clic en el botón **Enviar** .

    :::image type="content" source="../../media/submit-url-for-analysis.png" alt-text="Enviar dirección URL para el análisis" lightbox="../../media/submit-url-for-analysis.png":::

> [!NOTE]
>
> - Cuando se vuelve a encontrar la dirección URL, la dirección URL no se envía para las comprobaciones de detonación o reputación y se omiten todos los demás filtros basados en direcciones URL.
> - Por lo tanto, para un correo electrónico (que contiene esta dirección URL), durante el flujo de correo, si el resto de los filtros encuentran que el correo electrónico está limpio, se entregará el correo electrónico.

## <a name="view-url-entries"></a>Ver entradas de dirección URL

Para ver las entradas de direcciones URL de bloque en la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
Get-TenantAllowBlockListItems -ListType <URL> [-Entry <SenderValue | FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

En este ejemplo se devuelven todas las direcciones URL bloqueadas.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).

## <a name="modify-url-entries"></a>Modificar entradas de dirección URL 

Para modificar las entradas de dirección URL de permitir o bloquear en la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
Set-TenantAllowBlockListItems -ListType <URL> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

En este ejemplo se cambia la fecha de expiración de la entrada de dirección URL de bloque especificada.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).

## <a name="remove-url-entries"></a>Quitar entradas de dirección URL 

Para quitar las entradas de dirección URL de permitir o bloquear de la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
Remove-TenantAllowBlockListItems -ListType <URL> -Ids <"Id1","Id2",..."IdN">
```
En este ejemplo se quita la entrada de dirección URL de bloque especificada de la lista de permitidos o bloques de inquilinos.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="related-articles"></a>Artículos relacionados

- [Envíos de administradores](admin-submission.md)
- [Notificar falsos positivos y falsos negativos](report-false-positives-and-false-negatives.md)
- [Administrar los bloques y los permitidos en la lista de permitidos o bloqueados de inquilinos](manage-tenant-allow-block-list.md)
- [Permitir o bloquear archivos en la lista de inquilinos permitidos o bloqueados](allow-block-files.md)
- [Permitir o bloquear correos electrónicos en la lista de permitidos o bloqueados de inquilinos](allow-block-email-spoof.md)