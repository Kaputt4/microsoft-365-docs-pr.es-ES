---
title: Permitir o bloquear direcciones URL mediante la lista de bloqueados y permitidos del espacio empresarial
f1.keywords:
- NOCSH
ms.author: chrisda
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
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: f29e410a6457a4810bf98436f912a57866978241
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67495113"
---
# <a name="allow-or-block-urls-using-the-tenant-allowblock-list"></a>Permitir o bloquear direcciones URL mediante la lista de bloqueados y permitidos del espacio empresarial

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En este artículo se describe cómo crear y administrar direcciones URL para permitir y bloquear entradas que están disponibles en la lista de permitidos o bloqueados de inquilinos. Para obtener más información sobre la lista de permitidos o bloqueados de inquilinos, vea [Administrar los bloques y permitidos en la lista de permitidos o bloques de inquilinos](manage-tenant-allow-block-list.md).

Puede administrar las entradas de permitir y bloquear para las direcciones URL en Microsoft 365 Defender Portal o en Exchange Online PowerShell.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Permitir o bloquear lista de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>. Para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Para ver la sintaxis de entrada de dirección URL, consulte la [sección Sintaxis de dirección URL para la lista de permitidos o bloqueados](#url-syntax-for-the-tenant-allowblock-list) de inquilinos más adelante en este artículo.

- En el caso de las direcciones URL, el número máximo de entradas permitidas es 500 y el número máximo de entradas de bloque es 500 (1000 entradas url en total).

- Puede escribir un máximo de 250 caracteres en una entrada de dirección URL.

- Una entrada debe estar activa en un plazo de 30 minutos, pero la entrada puede tardar hasta 24 horas en estar activa.

- Debe tener permisos asignados en Exchange Online antes de poder realizar los procedimientos de este artículo:
  - Para agregar y quitar valores de la lista de permitidos o bloqueados de inquilinos, debe ser miembro de uno de los siguientes grupos de roles:
    - **Grupo de roles Administración de la organización** o **Administrador de seguridad** (**rol administrador de seguridad**)
    - **Grupo de roles Operador de seguridad** (**Administrador de listas de permitidos de inquilinos**).
  - Para obtener acceso de solo lectura a la lista de permitidos o bloqueados de inquilinos, debe ser miembro de uno de los siguientes grupos de roles:
    - **Grupo de roles lector global**
    - **Grupo de roles lector de seguridad**
    - **Grupo de roles de configuración de solo vista**

  Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - La adición de usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios *y* los permisos para otras características de Microsoft 365. Para obtener más información, consulte [Acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

## <a name="create-block-entries-for-urls"></a>Creación de entradas de bloque para direcciones URL

Tiene las siguientes opciones para crear entradas de bloque para direcciones URL:

- [Página Envíos del portal de Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-block-entries-for-urls-in-the-submissions-portal)
- Lista de inquilinos permitidos o bloqueados en [el portal de Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-block-entries-for-urls-in-the-tenant-allowblock-list) o en [PowerShell](#use-powershell-to-create-block-entries-for-urls-in-the-tenant-allowblock-list)

### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-urls-in-the-submissions-portal"></a>Use el portal de Microsoft 365 Defender para crear entradas de bloque para direcciones URL en el portal envíos.

Cuando use el portal Envíos en <https://security.microsoft.com/reportsubmission> para notificar direcciones URL como **Debería haberse bloqueado (Falso negativo),** puede seleccionar **Bloquear este archivo** para agregar una entrada de bloque para la dirección URL en la Lista de inquilinos permitidos o bloqueados.

Para obtener instrucciones, consulte [Notificar direcciones URL cuestionables a Microsoft](admin-submission.md#report-questionable-urls-to-microsoft).

### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-urls-in-the-tenant-allowblock-list"></a>Use el portal de Microsoft 365 Defender para crear entradas de bloque para direcciones URL en la lista de permitidos o bloques de inquilinos.

Puede crear entradas de bloque para direcciones URL directamente en la lista de permitidos o bloqueados de inquilinos.

Email mensajes que contienen estas direcciones URL bloqueadas se bloquean como *suplantación de identidad de alta confianza*.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas De directivas** \> de amenazas sección \> **Reglas de directivas** de **amenazas** \> **Listas de permitidos o bloques de inquilinos**. O bien, para ir directamente a la página **Permitir o bloquear lista de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. En la página **Lista de permitidos o bloqueados de inquilinos** , seleccione la pestaña **Direcciones URL** .

3. En la pestaña **Direcciones URL** , haga clic en ![el icono Bloquear.](../../media/m365-cc-sc-create-icon.png) **Bloquear**.

4. En el control flotante **Bloquear direcciones URL** que aparece, configure los siguientes valores:

   - **Agregar direcciones URL con caracteres comodín**: escriba una dirección URL por línea, hasta un máximo de 20. Para obtener más información sobre la sintaxis de las entradas de dirección URL, consulte la sección [Sintaxis de dirección URL de la lista de permitidos o bloques](#url-syntax-for-the-tenant-allowblock-list) de inquilinos más adelante en este artículo.

   - **Quitar entrada de bloque después**: El valor predeterminado es **30 días**, pero puede seleccionar entre los siguientes valores:
     - **Nunca expirar**
     - **1 día**
     - **7 días**
     - **30 días**
     - **Fecha específica**: el valor máximo es de 90 días a partir de hoy.

   - **Nota opcional**: escriba texto descriptivo para las entradas.

5. Cuando haya terminado, haga clic en **Agregar**.

#### <a name="use-powershell-to-create-block-entries-for-urls-in-the-tenant-allowblock-list"></a>Uso de PowerShell para crear entradas de bloque para direcciones URL en la lista de inquilinos permitidos o bloqueados

En [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), use la sintaxis siguiente:

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate <Date> | -NoExpiration> [-Notes <String>]
```

En este ejemplo se agrega una entrada de dirección URL de bloque para contoso.com y todos los subdominios (por ejemplo, contoso.com y xyz.abc.contoso.com). Dado que no usamos los parámetros ExpirationDate o NoExpiration, la entrada expira después de 30 días.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-entries-for-urls-in-the-submissions-portal"></a>Use el portal de Microsoft 365 Defender para crear entradas permitidas para direcciones URL en el portal envíos.

No se pueden crear entradas de permitir direcciones URL directamente en la lista de permitidos o bloqueados de inquilinos. En su lugar, use el portal Envíos en <https://security.microsoft.com/reportsubmission> para notificar el mensaje como falso positivo. Para obtener más información sobre los envíos de administradores, consulte [Uso del portal envíos para enviar sospechas de correo no deseado, fish, direcciones URL, bloqueo de correo electrónico legítimo y datos adjuntos de correo electrónico a Microsoft](admin-submission.md).

Al notificar la dirección URL como un falso positivo en la página Envíos, se agrega una entrada allow para la dirección URL en la lista de **permitidos o bloqueados** de inquilinos.

> [!IMPORTANT]
> Dado que Microsoft administra las entradas permitidas automáticamente, se quitarán las entradas permitidas de direcciones URL innecesarias. Este comportamiento protege su organización y ayuda a evitar entradas permitidas mal configuradas. Si no está de acuerdo con el veredicto, es posible que tenga que abrir un caso de soporte técnico para ayudar a determinar por qué una dirección URL todavía se considera incorrecta.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Envíos** en **Acciones & envíos** \> **.** Para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la página **Envíos** , seleccione la pestaña **Direcciones URL** .

3. En la pestaña **Direcciones URL** , haga clic en ![el icono Enviar a Microsoft para análisis.](../../media/m365-cc-sc-create-icon.png) **Envíe a Microsoft para su análisis**.

4. En el control flotante **Enviar a Microsoft para análisis** que aparece, escriba la siguiente información:

   - **Seleccione el tipo de envío**: compruebe que la **dirección URL** del valor está seleccionada.

   - **DIRECCIÓN URL**: escriba la dirección URL completa (por ejemplo, ) y selecciónela `https://www.fabrikam.com/marketing.html`en el cuadro que aparece.

   - **Seleccione un motivo para enviar a Microsoft**: Seleccione **No se debería haber bloqueado (Falso positivo)** y, a continuación, configure los siguientes valores:

     - **Permitir esta dirección URL**: active esta opción ![Activar.](../../media/scc-toggle-on.png)

         - **Quitar permitir entrada después**: El valor predeterminado es **de 30 días**, pero puede seleccionar entre los siguientes valores:
           - **1 día**
           - **7 días**
           - **30 días**
           - **Fecha específica**: el valor máximo es de 30 días a partir de hoy.

         - **Permitir nota de entrada**: escriba información opcional sobre por qué está permitiendo esta dirección URL.

   Cuando haya terminado, haga clic en **Enviary**, a continuación, haga clic en **Listo**.

   :::image type="content" source="../../media/admin-submission-url-allow.png" alt-text="Envíe una dirección URL falsa positiva (buena) a Microsoft para su análisis en la página Envíos del portal de Defender." lightbox="../../media/admin-submission-url-allow.png":::

5. Transcurridos unos instantes, la entrada url allow aparecerá en la pestaña **URL** de la página **Lista de permitidos o bloqueados de inquilinos** .

> [!NOTE]
>
> - Cuando se detecta de nuevo la dirección URL, no se envía para las comprobaciones de reputación de url o de detonación de [vínculos seguros](safe-links.md) , y se omiten todos los demás filtros basados en direcciones URL.
> - Durante el flujo de correo, si los mensajes que contienen la dirección URL pasan otras comprobaciones que no son de dirección URL en la pila de filtrado, se entregarán los mensajes.

## <a name="use-the-microsoft-365-defender-portal-to-view-allow-or-block-entries-for-urls-in-the-tenant-allowblock-list"></a>Use el portal de Microsoft 365 Defender para ver las entradas de permitir o bloquear las direcciones URL en la lista de permitidos o bloqueados de inquilinos

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas** \> **Directivas** \> de amenazas Listas **de inquilinos permitidos o bloqueados** en la sección **Reglas**. O bien, para ir directamente a la página **Permitir o bloquear listas de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. Seleccione la pestaña **URL** . Las columnas siguientes están disponibles:

   - **Valor**: la dirección URL.
   - **Acción**: el valor **Permitir** o **Bloquear**.
   - **Modificado por**
   - **Actualizado por última vez**
   - **Quitar en**: fecha de expiración.
   - **Notas**

   Haga clic en un encabezado de columna para ordenar en orden ascendente o descendente.

   Haga clic en ![Icono de grupo.](../../media/m365-cc-sc-group-icon.png) **Agrupar** para agrupar los resultados por **Ninguno** o **Acción**.

   Haga clic en el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Busque**, escriba todo o parte de un valor y, a continuación, presione ENTRAR para buscar un valor específico. Cuando haya terminado, haga clic en ![el icono Borrar búsqueda.](../../media/m365-cc-sc-close-icon.png) para borrar la búsqueda.

   Haga clic en ![Icono de filtro.](../../media/m365-cc-sc-filter-icon.png) **Filtre** para filtrar los resultados. Los siguientes valores están disponibles en el control flotante **Filtro** que aparece:

   - **Acción**: **Permitir** y **bloquear**.
   - **Nunca expirar**: ![activar.](../../media/scc-toggle-on.png) o ![desactivar.](../../media/scc-toggle-off.png)
   - **Última actualización**: seleccione **Las** fechas De y **A** .
   - **Quitar en**: seleccione **Las** fechas De y **A** .

   Cuando haya terminado, haga clic en **Aplicar**. Para borrar los filtros existentes, haga clic en ![el icono](../../media/m365-cc-sc-clear-filters-icon.png) Borrar filtros **Borrar filtros** en el control flotante **Filtro** .

### <a name="use-powershell-to-view-allow-or-block-entries-for-urls-in-the-tenant-allowblock-list"></a>Use PowerShell para ver las entradas de permitir o bloquear para direcciones URL en la lista de permitidos o bloqueados de inquilinos.

En [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), use la sintaxis siguiente:

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Allow] [-Block] [-Entry <URLValue>] [<-ExpirationDate <Date> | -NoExpiration>]
```

En este ejemplo se devuelven todas las direcciones URL permitidas y bloqueadas.

```powershell
Get-TenantAllowBlockListItems -ListType Url
```

En este ejemplo se filtran los resultados mediante direcciones URL bloqueadas.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).

## <a name="use-the-microsoft-365-defender-portal-to-modify-allow-or-block-entries-for-urls-in-the-tenant-allowblock-list"></a>Use el portal de Microsoft 365 Defender para modificar las entradas de permitir o bloquear para las direcciones URL en la lista de permitidos o bloqueados de inquilinos.

Al modificar una entrada de dirección URL de permitir o bloquear en la lista Permitir o bloquear inquilinos, solo puede modificar la fecha de expiración y las notas.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas De directivas** \> de amenazas sección \> **Reglas de directivas** de **amenazas** \> **Listas de permitidos o bloques de inquilinos**. O bien, para ir directamente a la página **Permitir o bloquear lista de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. Seleccione la pestaña **Direcciones URL.**

3. En la pestaña **Direcciones URL** , active la casilla de la entrada que desea modificar y, a continuación, haga clic en el ![icono Editar.](../../media/m365-cc-sc-edit-icon.png) **Botón Editar** que aparece.

4. Los siguientes valores están disponibles en el control flotante **Editar dirección URL** que aparece:

   - **Quite allow entry after (Permitir entrada) o** **Remove block entry after (Quitar entrada de bloque) después de**:
     - Puede ampliar las entradas permitidas durante un máximo de 30 días después de la fecha de creación.
     - Puede ampliar las entradas de bloque durante un máximo de 90 días después de la fecha de creación o establecerlas en **Nunca expirar**.

   - **Nota opcional**

   Cuando haya terminado, haga clic en **Guardar**.

> [!NOTE]
> Para permitir solo entradas, si selecciona la entrada haciendo clic en cualquier lugar de la fila que no sea la casilla, puede seleccionar ![Ver icono de envío.](../../media/m365-cc-sc-view-submission-icon.png) **Vea el envío** en el control flotante de detalles que parece ir a la página **Envíos** en <https://security.microsoft.com/reportsubmission>.

### <a name="use-powershell-to-modify-allow-or-block-entries-for-urls-in-the-tenant-allowblock-list"></a>Uso de PowerShell para modificar entradas de permitir o bloquear para direcciones URL en la lista de permitidos o bloqueados de inquilinos

En [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), use la sintaxis siguiente:

```powershell
Set-TenantAllowBlockListItems -ListType Url <-Ids <Identity value> | -Entries <Value value>> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

En este ejemplo se cambia la fecha de expiración de la entrada de dirección URL de bloque especificada.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Entries "~contoso.com" -ExpirationDate "9/1/2022"
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).

## <a name="use-the-microsoft-365-defender-portal-to-remove-allow-or-block-entries-for-urls-from-the-tenant-allowblock-list"></a>Use el portal de Microsoft 365 Defender para quitar entradas de permitir o bloquear para direcciones URL de la lista de permitidos o bloqueados de inquilinos

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas De directivas** \> de amenazas sección \> **Reglas de directivas** de **amenazas** \> **Listas de permitidos o bloques de inquilinos**. O bien, para ir directamente a la página **Permitir o bloquear lista de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. Seleccione la pestaña **Direcciones URL** .

3. En la pestaña **Direcciones URL** , realice uno de los pasos siguientes:

   - Active la casilla de la entrada que desea quitar y, a continuación, haga clic en el ![icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Icono de eliminación** que aparece.
   - Seleccione la entrada que desea quitar haciendo clic en cualquier lugar de la fila que no sea la casilla. En el control flotante de detalles que aparece, haga clic en ![el icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Eliminar**.

4. En el cuadro de diálogo de advertencia que aparece, haga clic en **Eliminar**.

> [!NOTE]
> Para seleccionar varias entradas, active cada casilla o seleccione todas las entradas seleccionando la casilla situada junto al encabezado **de columna Valor** .

### <a name="use-powershell-to-remove-allow-or-block-entries-for-urls-from-the-tenant-allowblock-list"></a>Uso de PowerShell para quitar entradas de permitir o bloquear para direcciones URL de la lista de permitidos o bloqueados de inquilinos

En [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), use la sintaxis siguiente:

```powershell
Remove-TenantAllowBlockListItems -ListType Url <-Ids <Identity value> | -Entries <Value value>>
```

En este ejemplo se quita la entrada de dirección URL de bloque especificada de la lista de permitidos o bloques de inquilinos.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Entries "~cohovineyard.com
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).

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

## <a name="related-articles"></a>Artículos relacionados

- [Use el portal envíos para enviar sospechas de correo no deseado, mensajes no deseados, direcciones URL, bloqueo de correo electrónico legítimo y datos adjuntos de correo electrónico a Microsoft.](admin-submission.md)
- [Notificar falsos positivos y falsos negativos](report-false-positives-and-false-negatives.md)
- [Administrar los bloques y los permitidos en la lista de permitidos o bloqueados de inquilinos](manage-tenant-allow-block-list.md)
- [Permitir o bloquear archivos en la lista de inquilinos permitidos o bloqueados](allow-block-files.md)
- [Permitir o bloquear correos electrónicos en la lista de permitidos o bloqueados de inquilinos](allow-block-email-spoof.md)
