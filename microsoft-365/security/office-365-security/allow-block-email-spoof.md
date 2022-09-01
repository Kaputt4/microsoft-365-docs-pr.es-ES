---
title: Permitir o bloquear correos electrónicos mediante la lista de bloqueados y permitidos del espacio empresarial
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
description: Los administradores pueden aprender a permitir o bloquear correos electrónicos y entradas de remitente suplantados en la lista de permitidos o bloqueados de inquilinos en el portal de seguridad.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 1537b32d56046da776024cef3acbd9eb2d8a4da3
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67497569"
---
# <a name="allow-or-block-emails-using-the-tenant-allowblock-list"></a>Permitir o bloquear correos electrónicos mediante la lista de bloqueados y permitidos del espacio empresarial

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En este artículo se describe cómo crear y administrar entradas de permitir y bloquear para dominios y direcciones de correo electrónico (incluidos los remitentes suplantados) que están disponibles en la lista de permitidos o bloqueados de inquilinos. Para obtener más información sobre la lista de permitidos o bloqueados de inquilinos, vea [Administrar los bloques y permitidos en la lista de permitidos o bloques de inquilinos](manage-tenant-allow-block-list.md).

Puede administrar las entradas de permitir y bloquear para el correo electrónico en el Portal de Microsoft 365 Defender o en Exchange Online PowerShell.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Permitir o bloquear lista de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>. Para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Para dominios y direcciones de correo electrónico, el número máximo de entradas permitidas es 500 y el número máximo de entradas de bloque es 500 (1000 entradas de dominio y dirección de correo electrónico en total).

- Para los remitentes suplantados, el número máximo de entradas es 1024.

- Las entradas para remitentes suplantados nunca expiran.

- Para obtener más información sobre la sintaxis de las entradas de remitente suplantadas, consulte la sección [Sintaxis de par de dominio para entradas de remitente suplantadas](#domain-pair-syntax-for-spoofed-sender-entries) más adelante en este artículo.

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

## <a name="domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Dominios y direcciones de correo electrónico en la lista de inquilinos permitidos o bloqueados

### <a name="create-block-entries-for-domains-and-email-addresses"></a>Creación de entradas de bloque para dominios y direcciones de correo electrónico

Tiene las siguientes opciones para crear entradas de bloque para dominios y direcciones de correo electrónico:

- [Página Envíos del portal de Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-block-entries-for-domains-and-email-addresses-in-the-submissions-portal)
- Lista de inquilinos permitidos o bloqueados en [el portal de Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list) o en [PowerShell](#use-powershell-to-create-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list)

Para crear entradas de bloque para remitentes suplantados, consulte [la sección Uso del portal de Microsoft 365 Defender para ver entradas de permitidos o bloqueados para remitentes suplantados en la sección Lista de permitidos o bloqueados de inquilinos](#use-the-microsoft-365-defender-portal-to-view-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list) más adelante en este artículo.

#### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-domains-and-email-addresses-in-the-submissions-portal"></a>Use el portal de Microsoft 365 Defender para crear entradas de bloque para dominios y direcciones de correo electrónico en el portal envíos.

Cuando use el portal Envíos en <https://security.microsoft.com/reportsubmission> para notificar mensajes de correo electrónico como **Debería haberse bloqueado (Falso negativo),** puede seleccionar **Bloquear todos los correos electrónicos de este destinatario** para agregar una entrada de bloque para el dominio o el remitente en la Lista de inquilinos permitidos o bloqueados.

Para obtener instrucciones, consulte [Informe de correo electrónico cuestionable a Microsoft](admin-submission.md#report-questionable-email-to-microsoft).

#### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Use el portal de Microsoft 365 Defender para crear entradas de bloque para dominios y direcciones de correo electrónico en la lista de permitidos o bloqueados de inquilinos.

Puede crear entradas de bloque para dominios y direcciones de correo electrónico directamente en la lista de permitidos o bloqueados de inquilinos.

Email mensajes de estos remitentes se marcan como *spam de alta confianza* (SCL = 9). Lo que sucede con los mensajes viene determinado por la [directiva antispam](configure-your-spam-filter-policies.md) que detectó el mensaje para el destinatario. En la directiva de antispam predeterminada y en las nuevas directivas personalizadas, los mensajes marcados como correo no deseado de alta confianza se entregan de forma predeterminada a la carpeta Junk Email. En las [directivas de seguridad preestablecidas](preset-security-policies.md) Estándar y Estricta, los mensajes de spam de alta confianza se ponen en cuarentena.

> [!NOTE]
> Los usuarios de la organización no pueden enviar correo electrónico a estos dominios y direcciones bloqueados. Recibirán el siguiente informe de no entrega (también conocido como NDR o mensaje de devolución): `5.7.1  Your message can't be delivered because one or more recipients are blocked by your organization's tenant allow/block list policy.`

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas De directivas** \> de amenazas sección \> **Reglas de directivas** de **amenazas** \> **Listas de permitidos o bloques de inquilinos**. O bien, para ir directamente a la página **Permitir o bloquear lista de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. En la página **Lista de permitidos o bloqueados de inquilinos** , compruebe que la pestaña **Dominios & direcciones** está seleccionada.

3. En la pestaña **Dominios & direcciones** , haga clic en ![el icono Bloquear.](../../media/m365-cc-sc-create-icon.png) **Bloquear**.

4. En el control flotante **Bloquear dominios & direcciones** que aparece, configure los siguientes valores:

   - **Dominios & direcciones**: escriba una dirección de correo electrónico o dominio por línea, hasta un máximo de 20.

   - **Quitar entrada de bloque después**: El valor predeterminado es **30 días**, pero puede seleccionar entre los siguientes valores:
     - **1 día**
     - **7 días**
     - **30 días**
     - **Nunca expirar**
     - **Fecha específica**: el valor máximo es de 90 días a partir de hoy.

   - **Nota opcional**: escriba texto descriptivo para las entradas.

5. Cuando haya terminado, haga clic en **Agregar**.

##### <a name="use-powershell-to-create-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Uso de PowerShell para crear entradas de bloque para dominios y direcciones de correo electrónico en la lista de permitidos o bloqueados de inquilinos

En [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), use la sintaxis siguiente:

```powershell
New-TenantAllowBlockListItems -ListType Sender -Block -Entries "DomainOrEmailAddress1","DomainOrEmailAddress1",..."DomainOrEmailAddressN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

En este ejemplo se agrega una entrada de bloque para la dirección de correo electrónico especificada que expira en una fecha específica.

```powershell
New-TenantAllowBlockListItems -ListType Sender -Block -Entries "test@badattackerdomain.com","test2@anotherattackerdomain.com" -ExpirationDate 8/20/2022
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal"></a>Use el portal de Microsoft 365 Defender para crear entradas permitidas para dominios y direcciones de correo electrónico en el portal envíos.

No puede crear entradas permitidas para dominios y direcciones de correo electrónico directamente en la lista de permitidos o bloqueados de inquilinos. En su lugar, use el portal Envíos en <https://security.microsoft.com/reportsubmission> para notificar el mensaje como falso positivo. Para obtener más información sobre los envíos de administradores, consulte [Uso del portal envíos para enviar sospechas de correo no deseado, fish, direcciones URL, bloqueo de correo electrónico legítimo y datos adjuntos de correo electrónico a Microsoft](admin-submission.md).

> [!NOTE]
> Dado que Microsoft administra las entradas permitidas automáticamente, se quitarán las entradas permitidas innecesarias para dominios y direcciones de correo electrónico. Este comportamiento protege su organización y ayuda a evitar entradas permitidas mal configuradas. Si no está de acuerdo con el veredicto, es posible que tenga que abrir un caso de soporte técnico para ayudar a determinar por qué un mensaje todavía se considera incorrecto.
>
> Si aún no se ha bloqueado el dominio o la dirección de correo electrónico, no se creará una entrada de permiso para el dominio o la dirección de correo electrónico.
>
> En la mayoría de los casos en los que se determinó que el mensaje era un falso positivo que se bloqueó incorrectamente, la entrada permitida se quitará en la fecha de expiración especificada.
>
> Para crear entradas permitidas para remitentes suplantados, consulte la sección [Creación de entradas permitidas para remitentes suplantados](#create-allow-entries-for-spoofed-senders) más adelante en este artículo.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a la página **Envíos** en **Acciones & envíos** \> **.** Para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la página **Envíos** , compruebe que la pestaña **Correos electrónicos** está seleccionada.

3. En la pestaña **Correos electrónicos** , haga clic en ![el icono Enviar a Microsoft para análisis.](../../media/m365-cc-sc-create-icon.png) **Envíe a Microsoft para su análisis**.

4. En el control flotante **Enviar a Microsoft para análisis** que aparece, escriba la siguiente información:

   - **Seleccione el tipo de envío**: compruebe que el valor **Email** está seleccionado.

   - **Agregue el identificador de mensaje de red o cargue el archivo de correo electrónico**: seleccione una de las siguientes opciones:

     - **Agregar el identificador de mensaje de red de correo electrónico**: se trata de un valor GUID que está disponible en el encabezado **X-MS-Exchange-Organization-Network-Message-Id** en el mensaje o en el encabezado **X-MS-Office365-Filtering-Correlation-Id** en los mensajes en cuarentena.

     - **Cargar el archivo de correo electrónico (.msg o .eml):** haga clic en **Examinar archivos**. En el cuadro de diálogo que se abre, busque y seleccione el archivo .eml o .msg y, a continuación, haga clic en **Abrir**.

   - **Elija un destinatario que tenga un problema**: especifique el destinatario en el que desea ejecutar una comprobación de directiva. La comprobación de directiva determinará si el correo electrónico se bloqueó debido a directivas de usuario u organización.

   - **Seleccione un motivo para enviar a Microsoft**: Seleccione **No se debería haber bloqueado (Falso positivo)** y, a continuación, configure los siguientes valores:

     - **Permitir correos electrónicos con atributos similares (URL, remitente, etc.):** active esta opción ![Activar.](../../media/scc-toggle-on.png)

         - **Quitar permitir entrada después**: El valor predeterminado es **de 30 días**, pero puede seleccionar entre los siguientes valores:
           - **1 día**
           - **7 días**
           - **30 días**
           - **Fecha específica**: el valor máximo es de 30 días a partir de hoy.

         - **Permitir nota de entrada**: escriba información opcional sobre por qué está permitiendo este correo electrónico.

   Cuando haya terminado, haga clic en **Enviary**, a continuación, haga clic en **Listo**.

   :::image type="content" source="../../media/admin-submission-email-allow.png" alt-text="Envíe un correo electrónico falso positivo (correcto) a Microsoft para su análisis en la página Envíos del portal de Defender." lightbox="../../media/admin-submission-email-allow.png":::

5. Transcurridos unos instantes, la entrada allow aparecerá en la pestaña **Dominios & direcciones** de la página **Lista de inquilinos permitidos o bloqueados** .

> [!NOTE]
>
> - Las permite se agregan durante el flujo de correo, en función de los filtros que determinaron que el mensaje era malintencionado. Por ejemplo, si se ha determinado que el remitente y una dirección URL del mensaje son incorrectos, se crea una entrada allow para el remitente y se crea una entrada allow para la dirección URL.
> - Cuando se vuelve a encontrar esa entidad (dirección de dominio o correo electrónico, dirección URL, archivo), se omiten todos los filtros asociados a esa entidad.
> - Durante el flujo de correo, si los mensajes del dominio o la dirección de correo electrónico pasan otras comprobaciones en la pila de filtrado, se entregarán los mensajes. Por ejemplo, si se supera la [autenticación por correo electrónico](email-validation-and-authentication.md) , se entregará un mensaje de un remitente en la entrada allow.

### <a name="use-the-microsoft-365-defender-portal-to-view-allow-or-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Use el portal de Microsoft 365 Defender para ver las entradas de permitir o bloquear para dominios y direcciones de correo electrónico en la lista de permitidos o bloqueados de inquilinos.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas** \> **Directivas** \> de amenazas Listas **de inquilinos permitidos o bloqueados** en la sección **Reglas**. O bien, para ir directamente a la página **Permitir o bloquear listas de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. Compruebe que la pestaña **Dominios & direcciones** está seleccionada. Las columnas siguientes están disponibles:

   - **Valor**: dominio o dirección de correo electrónico.
   - **Acción**: el valor **Permitir** o **Bloquear**.
   - **Modificado por**
   - **Actualizado por última vez**
   - **Quitar en**: fecha de expiración.
   - **Notas**

   Puede hacer clic en un encabezado de columna para ordenar en orden ascendente o descendente.

   Haga clic en ![Icono de grupo.](../../media/m365-cc-sc-group-icon.png) **Agrupar** para agrupar los resultados por **Ninguno** o **Acción**.

   Haga clic en el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Busque**, escriba todo o parte de un valor y, a continuación, presione ENTRAR para buscar un valor específico. Cuando haya terminado, haga clic en ![el icono Borrar búsqueda.](../../media/m365-cc-sc-close-icon.png) **Borrar búsqueda**.

   Haga clic en ![Icono de filtro.](../../media/m365-cc-sc-filter-icon.png) **Filtre** para filtrar los resultados. Los siguientes valores están disponibles en el control flotante **Filtro** que aparece:

   - **Acción**: **Permitir** y **bloquear**.
   - **Nunca expirar**: ![activar.](../../media/scc-toggle-on.png) o ![desactivar.](../../media/scc-toggle-off.png)
   - **Última actualización**: seleccione **Las** fechas De y **A** .
   - **Quitar en**: seleccione **Las** fechas De y **A** .

   Cuando haya terminado, haga clic en **Aplicar**. Para borrar los filtros existentes, haga clic en ![el icono](../../media/m365-cc-sc-clear-filters-icon.png) Borrar filtros **Borrar filtros** en el control flotante **Filtro** .

#### <a name="use-powershell-to-view-allow-or-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Uso de PowerShell para ver entradas de permitir o bloquear para dominios y direcciones de correo electrónico en la lista de permitidos o bloqueados de inquilinos

En [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), use la sintaxis siguiente:

```powershell
Get-TenantAllowBlockListItems -ListType Sender [-Allow] [-Block] [-Entry <Domain or Email address value>] [<-ExpirationDate Date | -NoExpiration>]
```

En este ejemplo se devuelven todas las entradas allow y block para dominios y direcciones de correo electrónico.

```powershell
Get-TenantAllowBlockListItems -ListType Sender
```

En este ejemplo se filtran los resultados de las entradas de bloque para dominios y direcciones de correo electrónico.

```powershell
Get-TenantAllowBlockListItems -ListType Sender -Block
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).

### <a name="use-the-microsoft-365-defender-portal-to-modify-allow-or-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Use el portal de Microsoft 365 Defender para modificar las entradas de permitir o bloquear para dominios y direcciones de correo electrónico en la lista de permitidos o bloqueados de inquilinos.

Al modificar una entrada de permitir o bloquear para dominios y direcciones de correo electrónico en la lista Permitir o bloquear inquilinos, solo puede modificar la fecha de expiración y las notas.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas De directivas** \> de amenazas sección \> **Reglas de directivas** de **amenazas** \> **Listas de permitidos o bloques de inquilinos**. O bien, para ir directamente a la página **Permitir o bloquear lista de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. Compruebe que la pestaña **Dominios & direcciones** está seleccionada.

3. En la pestaña **Dominios & direcciones** , active la casilla de la entrada que desea modificar y, a continuación, haga clic en el ![icono Editar.](../../media/m365-cc-sc-edit-icon.png) **Botón Editar** que aparece.

4. La siguiente configuración está disponible en el control flotante **Editar dominio & direcciones** que aparece:

   - **Quite allow entry after (Permitir entrada) o** **Remove block entry after (Quitar entrada de bloque) después de**:
     - Puede ampliar las entradas permitidas durante un máximo de 30 días después de la fecha de creación.
     - Puede ampliar las entradas de bloque durante un máximo de 90 días después de la fecha de creación o establecerlas en **Nunca expirar**.

   - **Nota opcional**

   Cuando haya terminado, haga clic en **Guardar**.

> [!NOTE]
> Para permitir solo entradas, si selecciona la entrada haciendo clic en cualquier lugar de la fila que no sea la casilla, puede seleccionar ![Ver icono de envío.](../../media/m365-cc-sc-view-submission-icon.png) **Vea el envío** en el control flotante de detalles que parece ir a la página **Envíos** en <https://security.microsoft.com/reportsubmission>.

#### <a name="use-powershell-to-modify-allow-or-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Uso de PowerShell para modificar entradas de permitir o bloquear para dominios y direcciones de correo electrónico en la lista de permitidos o bloqueados de inquilinos

En [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), use la sintaxis siguiente:

```powershell
Set-TenantAllowBlockListItems -ListType Sender <-Ids <Identity value> | -Entries <Value value>> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

En este ejemplo se cambia la fecha de expiración de la entrada de bloque especificada para dominios y direcciones de correo electrónico.

```powershell
Set-TenantAllowBlockListItems -ListType Sender -Entries "julia@fabrikam.com" -ExpirationDate "9/1/2022"
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).

### <a name="use-the-microsoft-365-defender-portal-to-remove-allow-or-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Use el portal de Microsoft 365 Defender para quitar entradas de permitir o bloquear para dominios y direcciones de correo electrónico en la lista de permitidos o bloqueados de inquilinos.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas De directivas** \> de amenazas sección \> **Reglas de directivas** de **amenazas** \> **Listas de permitidos o bloques de inquilinos**. O bien, para ir directamente a la página **Permitir o bloquear lista de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. Compruebe que la pestaña **Dominios & direcciones** está seleccionada.

3. En la pestaña **Dominios & direcciones** , realice uno de los pasos siguientes:

   - Active la casilla de la entrada que desea quitar y, a continuación, haga clic en el ![icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Icono de eliminación** que aparece.
   - Seleccione la entrada que desea quitar haciendo clic en cualquier lugar de la fila que no sea la casilla. En el control flotante de detalles que aparece, haga clic en ![el icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Eliminar**.

4. En el cuadro de diálogo de advertencia que aparece, haga clic en **Eliminar**.

> [!NOTE]
> Para seleccionar varias entradas, active cada casilla o seleccione todas las entradas seleccionando la casilla situada junto al encabezado **de columna Valor** .

#### <a name="use-powershell-to-remove-allow-or-block-entries-for-domains-and-email-addresses-from-the-tenant-allowblock-list"></a>Uso de PowerShell para quitar entradas de permitir o bloquear para dominios y direcciones de correo electrónico de la lista de permitidos o bloqueados de inquilinos

En [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), use la sintaxis siguiente:

```powershell
Remove-TenantAllowBlockListItems -ListType Sender <-Ids <Identity value> | -Entries <Value value>>
```

En este ejemplo se quita la entrada de bloque especificada para dominios y direcciones de correo electrónico de la lista de permitidos o bloqueados de inquilinos.

```powershell
Remove-TenantAllowBlockListItems -ListType Sender -Entries "adatum.com"
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="spoofed-senders-in-the-tenant-allowblock-list"></a>Remitentes suplantados en la lista de permitidos o bloqueados de inquilinos

### <a name="create-allow-entries-for-spoofed-senders"></a>Creación de entradas permitidas para remitentes suplantados

Tiene las siguientes opciones para crear entradas de bloque para remitentes suplantados:

- [Página Envíos del portal de Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal)
- Lista de inquilinos permitidos o bloqueados en [el portal de Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-spoofed-senders-in-the-tenant-allowblock-list) o en [PowerShell](#use-powershell-to-create-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list)

> [!NOTE]
> Permitir entradas para remitentes suplantados se encargan de la suplantación de identidad entre organizaciones, organizaciones y DMARC.
>
> Solo se permite suplantar la combinación del usuario suplantado *y* la infraestructura de envío tal como se define en el [par de dominio](#domain-pair-syntax-for-spoofed-sender-entries) .
>
> Al configurar una entrada allow para un par de dominio, los mensajes de ese par de dominio ya no aparecen en la [información de inteligencia de suplantación de identidad](learn-about-spoof-intelligence.md).
>
> Permitir entradas para remitentes suplantados nunca expira.

#### <a name="use-the-microsoft-365-defender-portal-to-create-allow-entries-for-spoofed-senders-in-the-submissions-portal"></a>Use el portal de Microsoft 365 Defender para crear entradas permitidas para remitentes suplantados en el portal envíos.

Al enviar mensajes bloqueados por [inteligencia de suplantación](learn-about-spoof-intelligence.md) de identidad a Microsoft desde la página **Envíos** , se agrega el remitente como una entrada de permitido en la pestaña **Remitentes suplantados en Lista de permitidos o bloqueados de inquilinos** .

> [!NOTE]
> Al invalidar el veredicto en la información de inteligencia sobre suplantación de identidad, el remitente suplantado se convierte en una entrada de bloqueo o permiso manual que solo aparece en la pestaña **Remitentes suplantados de la lista de permitidos o bloqueados de inquilinos** .
>
> Si la inteligencia de suplantación de identidad no ha bloqueado al remitente, el envío del mensaje de correo electrónico a Microsoft no creará una entrada permitida en la lista de permitidos o bloqueados de inquilinos.

Las instrucciones para informar del mensaje son casi idénticas a los pasos descritos en [Uso del portal de Microsoft 365 Defender para crear entradas permitidas para dominios y direcciones de correo electrónico en el portal Envíos](#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal).

Las únicas diferencias son:

- La **opción Remove allow entry after** setting in Step 4 (Quitar permitir entrada después de la configuración del paso 4) no tiene sentido, ya que las entradas de los remitentes suplantados nunca expiran.
- La opción **Permitir nota de entrada** del paso 4 no se aplica a las entradas de remitentes suplantados en la lista de permitidos o bloqueados de inquilinos.

#### <a name="use-the-microsoft-365-defender-portal-to-create-allow-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Use el portal de Microsoft 365 Defender para crear entradas permitidas para remitentes suplantados en la lista de permitidos o bloqueados de inquilinos.

En la Lista de permitidos o bloqueados de inquilinos, puede crear entradas de permiso para remitentes suplantados antes de que se detecten y bloqueen mediante [la inteligencia de suplantación de identidad](learn-about-spoof-intelligence.md).

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas De directivas** \> de amenazas sección \> **Reglas de directivas** de **amenazas** \> **Listas de permitidos o bloques de inquilinos**. O bien, para ir directamente a la página **Permitir o bloquear lista de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. En la página **Lista de permitidos o bloqueados de inquilinos** , seleccione la pestaña **Remitentes suplantados** y, a continuación, haga clic en ![el icono Agregar.](../../media/m365-cc-sc-create-icon.png) **Agregar**.

3. En el control flotante **Agregar nuevos pares de dominio** que aparece, configure los siguientes valores:

   - **Agregar pares de dominio con caracteres comodín**: escriba el par de dominios por línea, hasta un máximo de 20. Para obtener más información sobre la sintaxis de las entradas de remitente suplantadas, consulte la sección [Sintaxis de par de dominio para entradas de remitente suplantadas](#domain-pair-syntax-for-spoofed-sender-entries) más adelante en este artículo.

   - **Tipo de suplantación**: seleccione uno de los valores siguientes:
     - **Interno**: el remitente suplantado está en un dominio que pertenece a su organización (un [dominio aceptado](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).
     - **Externo**: el remitente suplantado está en un dominio externo.

   - **Acción**: seleccione **Permitir** o **Bloquear**.

   Cuando haya terminado, haga clic en **Agregar**.

##### <a name="use-powershell-to-create-allow-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Uso de PowerShell para crear entradas permitidas para remitentes suplantados en la lista de permitidos o bloqueados de inquilinos

En [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), use la sintaxis siguiente:

```powershell
New-TenantAllowBlockListSpoofItems -Identity Default -Action Allow -SpoofedUser <Domain | EmailAddress> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal>
```

En este ejemplo se crea una entrada allow para el remitente bob@contoso.com desde el contoso.com de origen.

```powershell
New-TenantAllowBlockListSpoofItems -Identity Default -Action Allow -SendingInfrastructure contoso.com -SpoofedUser bob@contoso.com -SpoofType External
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).

### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Use el portal de Microsoft 365 Defender para crear entradas de bloque para remitentes suplantados en la lista de permitidos o bloqueados de inquilinos.

Las entradas de bloque se crean para remitentes suplantados directamente en la lista de permitidos o bloqueados de inquilinos.

> [!NOTE]
> Email mensajes de estos remitentes se bloquean como *phishing*.
>
> Solo la combinación del usuario suplantado y la infraestructura de envío, tal *como* se define en el [par de dominios](#domain-pair-syntax-for-spoofed-sender-entries) , está bloqueada para la suplantación de identidad.
>
> Al configurar una entrada de bloque para un par de dominio, los mensajes de ese par de dominio ya no aparecen en la [información de inteligencia de suplantación](learn-about-spoof-intelligence.md).
>
> Las entradas de bloque para remitentes suplantados nunca expiran.

Las instrucciones para informar del mensaje son casi idénticas a los pasos descritos en [Uso del portal de Microsoft 365 Defender para crear entradas permitidas para dominios y direcciones de correo electrónico en el portal Envíos](#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal).

La única diferencia es: para el valor **Acción** del paso 4, elija **Bloquear** en lugar de **Permitir**.

#### <a name="use-powershell-to-create-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Uso de PowerShell para crear entradas de bloque para remitentes suplantados en la lista de permitidos o bloqueados de inquilinos

En [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), use la sintaxis siguiente:

```powershell
New-TenantAllowBlockListSpoofItems -Identity Default -Action Block -SpoofedUser <Domain | EmailAddress> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal>
```

En este ejemplo se crea una entrada de bloque para el remitente laura@adatum.com desde el origen 172.17.17.17/24.

```powershell
New-TenantAllowBlockListSpoofItems -Identity Default -Action Allow -SendingInfrastructure 172.17.17.17/24 -SpoofedUser laura@adatum.com -SpoofType External
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).

### <a name="use-the-microsoft-365-defender-portal-to-view-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Use el portal de Microsoft 365 Defender para ver las entradas de permitir o bloquear para remitentes suplantados en la lista de permitidos o bloqueados de inquilinos.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas** \> **Directivas** \> de amenazas Listas **de inquilinos permitidos o bloqueados** en la sección **Reglas**. O bien, para ir directamente a la página **Permitir o bloquear listas de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. Compruebe que la pestaña **Remitentes suplantados** esté seleccionada. Las columnas siguientes están disponibles:

   - **Usuario con identidad suplantada**
   - **Infraestructura de envío**
   - **Tipo de suplantación:** el valor **Interno** o **Externo**.
   - **Acción**: el valor **Bloquear** o **Permitir**.

   Puede hacer clic en un encabezado de columna para ordenar en orden ascendente o descendente.

   Haga clic en ![Icono de grupo.](../../media/m365-cc-sc-group-icon.png) **Agrupe** los resultados por **tipo None**, **Action** o **Spoof**.

   Haga clic en el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Busque**, escriba todo o parte de un valor y, a continuación, presione ENTRAR para buscar un valor específico. Cuando haya terminado, haga clic en ![el icono Borrar búsqueda.](../../media/m365-cc-sc-close-icon.png) **Borrar búsqueda**.

   Haga clic en ![Icono de filtro.](../../media/m365-cc-sc-filter-icon.png) **Filtre** para filtrar los resultados. Los siguientes valores están disponibles en el control flotante **Filtro** que aparece:

   - **Acción**: **Permitir** y **bloquear**.
   - **Tipo de suplantación**: **Interno** y **Externo**.

   Cuando haya terminado, haga clic en **Aplicar**. Para borrar los filtros existentes, haga clic en ![el icono](../../media/m365-cc-sc-clear-filters-icon.png) Borrar filtros **Borrar filtros** en el control flotante **Filtro** .

#### <a name="use-powershell-to-view-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Uso de PowerShell para ver las entradas de permitir o bloquear para remitentes suplantados en la lista de permitidos o bloqueados de inquilinos

En [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), use la sintaxis siguiente:

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

### <a name="use-the-microsoft-365-defender-portal-to-modify-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Use el portal de Microsoft 365 Defender para modificar las entradas de permitir o bloquear para remitentes suplantados en la lista de permitidos o bloqueados de inquilinos.

Al modificar una entrada de permitir o bloquear para remitentes suplantados en la lista Permitir o bloquear inquilinos, solo puede cambiar la entrada de **Permitir** a **Bloquear**, o viceversa.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas De directivas** \> de amenazas sección \> **Reglas de directivas** de **amenazas** \> **Listas de permitidos o bloques de inquilinos**. O bien, para ir directamente a la página **Permitir o bloquear lista de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. Seleccione la pestaña **Remitentes suplantados** .

3. En la pestaña **Remitentes suplantados** , seleccione la entrada que desea modificar y, a continuación, haga clic en el ![icono Editar.](../../media/m365-cc-sc-edit-icon.png) **Botón Editar** que aparece.

4. En el control flotante **Editar remitente suplantado** que aparece, elija **Permitir** o **Bloquear**.

5. Cuando haya terminado, haga clic en **Guardar**.

#### <a name="use-powershell-to-modify-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Uso de PowerShell para modificar entradas de permitir o bloquear para remitentes suplantados en la lista de permitidos o bloqueados de inquilinos

En [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), use la sintaxis siguiente:

```powershell
Set-TenantAllowBlockListSpoofItems -Identity Default -Ids <Identity value> -Action <Allow | Block>
```

En este ejemplo se cambia la entrada del remitente suplantado de allow a block.

```powershell
Set-TenantAllowBlockListItems -Identity Default -Ids 3429424b-781a-53c3-17f9-c0b5faa02847 -Action Block
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).

### <a name="use-the-microsoft-365-defender-portal-to-remove-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Use el portal de Microsoft 365 Defender para quitar entradas de permitir o bloquear para remitentes suplantados en la lista de permitidos o bloqueados de inquilinos.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas De directivas** \> de amenazas sección \> **Reglas de directivas** de **amenazas** \> **Listas de permitidos o bloques de inquilinos**. O bien, para ir directamente a la página **Permitir o bloquear lista de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. Seleccione la pestaña **Remitentes suplantados** .

3. En la pestaña **Remitentes suplantados** , seleccione la entrada que desea quitar y, a continuación, haga clic en el ![icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Icono de eliminación** que aparece.

4. En el cuadro de diálogo de advertencia que aparece, haga clic en **Eliminar**.

> [!NOTE]
> Puede seleccionar varias entradas seleccionando cada casilla o seleccionando todas las entradas seleccionando la casilla situada junto al encabezado de columna **Spoofed user(Spoofed user** column).

#### <a name="use-powershell-to-remove-allow-or-block-entries-for-spoofed-senders-from-the-tenant-allowblock-list"></a>Uso de PowerShell para quitar entradas de permitir o bloquear para remitentes suplantados de la lista de permitidos o bloqueados de inquilinos

En [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), use la sintaxis siguiente:

```powershell
Remove-TenantAllowBlockListSpoofItems -Identity domain.com\Default -Ids <Identity value>
```

```powershell
Remove-TenantAllowBlockListSpoofItems -Identity domain.com\Default -Ids d86b3b4b-e751-a8eb-88cc-fe1e33ce3d0c
```

En este ejemplo se quita el remitente suplantado especificado. El valor del parámetro Ids se obtiene de la propiedad Identity en la salida del comando Get-TenantAllowBlockListSpoofItems.

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).

### <a name="domain-pair-syntax-for-spoofed-sender-entries"></a>Sintaxis de par de dominio para entradas de remitente suplantadas

Un par de dominios para un remitente suplantado en la lista de permitidos o bloqueados de inquilinos usa la sintaxis siguiente: `<Spoofed user>, <Sending infrastructure>`.

- **Usuario suplantado**: este valor implica la dirección de correo electrónico del usuario suplantado que se muestra en el cuadro **De** en los clientes de correo electrónico. Esta dirección también se conoce como dirección `5322.From` . Los valores válidos son:
  - Una dirección de correo electrónico individual (por ejemplo, chris@contoso.com).
  - Un dominio de correo electrónico (por ejemplo, contoso.com).
  - Carácter comodín (por ejemplo, \*).

- **Infraestructura de envío**: este valor indica el origen de los mensajes del usuario suplantado. Los valores válidos son:
  - Dominio que se encuentra en una búsqueda dns inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen (por ejemplo, fabrikam.com).
  - Si la dirección IP de origen no tiene ningún registro PTR, la infraestructura de envío se identifica como \<source IP\>/24 (por ejemplo, 192.168.100.100/24).
  - Un dominio DKIM comprobado.

Estos son algunos ejemplos de pares de dominio válidos para identificar remitentes suplantados:

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

Agregar un par de dominio solo permite o bloquea la *combinación* del usuario suplantado *y* la infraestructura de envío. No permite el correo electrónico del usuario suplantado de ningún origen ni permite el correo electrónico del origen de la infraestructura de envío para cualquier usuario suplantado.

Por ejemplo, agrega una entrada allow para el siguiente par de dominio:

- **Dominio**: gmail.com
- **Infraestructura de envío**: tms.mx.com

Solo los mensajes de ese dominio *y* el par de infraestructura de envío pueden suplantarse. No se permiten otros remitentes que intenten suplantar gmail.com. Los mensajes de remitentes de otros dominios que se originan en tms.mx.com se comprueban mediante inteligencia suplantada.

> [!NOTE]
> Puede especificar caracteres comodín en la infraestructura de envío o en el usuario suplantado, pero no en ambos al mismo tiempo. Por ejemplo, `*, *` no se permite.

## <a name="about-impersonated-domains-or-senders"></a>Acerca de los dominios o remitentes suplantados

En las organizaciones con Microsoft Defender para Office 365, no puede crear entradas permitidas en la lista de inquilinos, permitidos o bloqueados para los mensajes detectados como suplantación por [la protección de suplantación de dominio o remitente](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

La notificación de un mensaje que se bloqueó incorrectamente como suplantación en el portal envíos en <https://security.microsoft.com/reportsubmission>  no agrega el remitente o dominio como una entrada permitida en la lista de permitidos o bloqueados de inquilinos.

En su lugar, el dominio o el remitente se agrega a la **sección Remitentes y dominios de confianza** de la [directiva anti-phishing](configure-mdo-anti-phishing-policies.md#use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies) que detectó el mensaje.

Las instrucciones para informar del mensaje son idénticas a los pasos descritos en [Uso del portal de Microsoft 365 Defender para crear entradas permitidas para dominios y direcciones de correo electrónico en el portal Envíos](#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal).

> [!NOTE]
> Actualmente, la suplantación de grafos no se cuida desde aquí.

## <a name="related-articles"></a>Artículos relacionados

- [Use el portal envíos para enviar sospechas de correo no deseado, mensajes no deseados, direcciones URL, bloqueo de correo electrónico legítimo y datos adjuntos de correo electrónico a Microsoft.](admin-submission.md)
- [Notificar falsos positivos y falsos negativos](report-false-positives-and-false-negatives.md)
- [Administrar los bloques y los permitidos en la lista de permitidos o bloqueados de inquilinos](manage-tenant-allow-block-list.md)
- [Permitir o bloquear archivos en la lista de inquilinos permitidos o bloqueados](allow-block-files.md)
- [Permitir o bloquear direcciones URL en la lista de permitidos o bloqueados de inquilinos](allow-block-urls.md)
