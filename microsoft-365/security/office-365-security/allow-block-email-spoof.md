---
title: Permitir o bloquear correos electrónicos mediante la lista de bloqueados y permitidos del espacio empresarial
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
description: Los administradores pueden aprender a permitir o bloquear correos electrónicos y entradas de remitente suplantados en la lista de permitidos o bloqueados de inquilinos en el portal de seguridad.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a16a8234b1d0ff2a3647d7f66923faa66784ea72
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66493229"
---
# <a name="allow-or-block-emails-using-the-tenant-allowblock-list"></a>Permitir o bloquear correos electrónicos mediante la lista de bloqueados y permitidos del espacio empresarial

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Puede usar el portal de Microsoft 365 Defender o PowerShell para permitir o bloquear correos electrónicos (incluidos los correos electrónicos de suplantación de identidad) mediante la lista de permitidos o bloqueados de inquilinos.

## <a name="create-block-sender-entries"></a>Creación de entradas de remitente de bloque 

### <a name="use-the-microsoft-365-defender-portal"></a>Uso del portal de Microsoft 365 Defender

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas De directivas** \> de amenazas sección \> **Reglas de directivas** de **amenazas** \> **Listas de permitidos o bloques de inquilinos**. O bien, para ir directamente a la página **Permitir o bloquear lista de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

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
> Los correos electrónicos de estos remitentes se bloquearán como _correo no deseado de alta confianza_ (SCL = 9).

### <a name="use-powershell"></a>Usar PowerShell

Para agregar entradas de remitente de bloque en la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
New-TenantAllowBlockListItems -ListType <Sender> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

En este ejemplo se agrega una entrada de remitente de bloque para el remitente especificado que expira en una fecha específica.

```powershell
New-TenantAllowBlockListItems -ListType Sender -Block -Entries "test@badattackerdomain.com", "test2@anotherattackerdomain.com" -ExpirationDate 8/20/2021
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

## <a name="create-allow-sender-entries"></a>Creación de entradas de permitir remitente 

### <a name="use-microsoft-365-defender"></a>Uso de Microsoft 365 Defender

Permitir remitentes (o dominios) en la página **Envíos** de Microsoft 365 Defender.

No puede modificar directamente la lista de permitidos o bloqueados de inquilinos para agregar entradas de permitido. En su lugar, use [envíos de administrador](admin-submission.md) para enviar el mensaje bloqueado. Esta acción agregará la dirección URL, el archivo, el par de dominio del remitente suplantado, el dominio suplantado (o el usuario) o el remitente correspondiente a la lista de permitidos o bloqueados de inquilinos. Si el elemento no se ha bloqueado, no se creará el permiso. En la mayoría de los casos en los que se determinó que el mensaje era un falso positivo que se bloqueó incorrectamente, la entrada permitida se quitará en la fecha de expiración especificada.

> [!IMPORTANT]
> - Dado que Microsoft administra las entradas permitidas automáticamente, se quitarán las entradas de permitir de archivo, dirección URL o remitente innecesarios que no sean necesarias. Este comportamiento protege su organización y ayuda a evitar entradas permitidas mal configuradas. Si no está de acuerdo con el veredicto, es posible que tenga que abrir un caso de soporte técnico para ayudar a determinar por qué un mensaje todavía se considera incorrecto.


1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Acciones & envíos envíos**\>. O bien, para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la página **Envíos** , compruebe que la pestaña **Correos electrónicos** está seleccionada y, a continuación, haga clic en ![el icono Enviar a Microsoft para análisis.](../../media/m365-cc-sc-create-icon.png) **Envíe a Microsoft para su análisis**.

3. Use el control flotante **Enviar a Microsoft para revisar** para enviar un mensaje agregando el identificador de mensaje de red o cargando el archivo de correo electrónico.

4. En la sección **Seleccionar un motivo para enviar a Microsoft**, seleccione **No debería haberse bloqueado (falso positivo).**

5. Active **Permitir mensajes como esta** opción.

6. En la lista desplegable **Quitar después** , especifique cuánto tiempo desea que funcione la opción permitir.

7. Agregue por qué va a agregar la opción allow mediante el cuadro **Nota opcional** . 

8. Cuando haya terminado, seleccione **Enviar**.

  :::image type="content" source="../../media/admin-submission-allow-messages.png" alt-text="Envíe malware a Microsoft para el ejemplo de análisis." lightbox="../../media/admin-submission-allow-messages.png":::

> [!NOTE]
>
> - Durante el flujo de correo, en función de los filtros que determinaron que el correo fuera malintencionado, se agregan las permite. Por ejemplo, se determina que el remitente y la dirección URL son incorrectos; se agregará un permiso para cada uno.
> - Cuando se vuelve a encontrar esa entidad (remitente, dominio, dirección URL, archivo), se omiten todos los filtros asociados a esa entidad.
> - Durante el flujo de correo, si el resto de los filtros encuentran que el correo electrónico que contiene esta entidad está limpio, se entregará el correo electrónico. Por ejemplo, un remitente permite (cuando se supera la autenticación) omitirá todos los veredictos excepto el malware y la suplantación de identidad de alta confianza asociadas a un archivo adjunto o una dirección URL.

## <a name="view-sender-entries"></a>Visualización de las entradas del remitente 

Para ver las entradas del remitente de bloques en la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
Get-TenantAllowBlockListItems -ListType <Sender> [-Entry <SenderValue | FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```
Para obtener información detallada sobre la sintaxis y los [parámetros, vea Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).

## <a name="modify-sender-entries"></a>Modificar entradas del remitente 

Para modificar las entradas de permitir o bloquear remitentes en la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
Set-TenantAllowBlockListItems -ListType <Sender> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).

## <a name="remove-sender-entries"></a>Quitar entradas del remitente 

Para quitar las entradas de permitir o bloquear remitentes de la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
Remove-TenantAllowBlockListItems -ListType <Sender> -Ids <"Id1","Id2",..."IdN">
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="domain-pair-syntax-for-spoofed-sender-entries"></a>Sintaxis de par de dominio para entradas de remitente suplantadas

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

El número máximo de entradas de remitente suplantadas es 1000.

Agregar un par de dominio solo permite o bloquea la *combinación* del usuario suplantado *y* la infraestructura de envío. No permite el correo electrónico del usuario suplantado de ningún origen ni permite el correo electrónico del origen de la infraestructura de envío para cualquier usuario suplantado.

Por ejemplo, agrega una entrada allow para el siguiente par de dominio:

- **Dominio**: gmail.com
- **Infraestructura**: tms.mx.com

Solo los mensajes de ese dominio _y_ el par de infraestructura de envío pueden suplantarse. No se permiten otros remitentes que intenten suplantar gmail.com. Los mensajes de remitentes de otros dominios que se originan en tms.mx.com se comprueban mediante inteligencia suplantada.

## <a name="create-blocked-spoofed-sender-entries"></a>Creación de entradas de remitente suplantadas bloqueadas

### <a name="use-microsoft-365-defender"></a>Uso de Microsoft 365 Defender

> [!NOTE]
> El correo electrónico de estos remitentes se bloqueará como _phish_.
>
> Solo se permite o bloquea específicamente la _combinación_ del usuario suplantado _y_ la infraestructura de envío tal como se define en el par de dominio.
>
> Al configurar una entrada de permitir o bloquear para un par de dominio, los mensajes de ese par de dominio ya no aparecen en la información de inteligencia de suplantación de identidad.
>
> Las entradas para remitentes suplantados nunca expiran.

1. En el portal de Microsoft 365 Defender, vaya a **Directivas & reglas De directivas** \> de amenazas sección **Reglas de directivas** \> de **amenazas** \> **Listas de permitidos o bloques de inquilinos**.

2. En la página **Lista de permitidos o bloqueados de inquilinos** , seleccione la pestaña **Suplantación** de identidad y, a continuación, haga clic en ![el icono Bloquear.](../../media/m365-cc-sc-create-icon.png) **Agregar**.

3. En el control flotante **Agregar nuevos pares de dominio** que aparece, configure los siguientes valores:
   - **Agregar nuevos pares de dominio con caracteres comodín**: escriba un par de dominio por línea, hasta un máximo de 20. Para obtener más información sobre la sintaxis de las entradas de remitente suplantadas, consulte [Administrar la lista de permitidos o bloques](tenant-allow-block-list.md) de inquilinos.
   - **Tipo de suplantación**: seleccione uno de los valores siguientes:
     - **Interno**: el remitente suplantado está en un dominio que pertenece a su organización (un [dominio aceptado](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).
     - **Externo**: el remitente suplantado está en un dominio externo.
   - **Acción**: seleccione **Bloquear**.

4. Cuando haya terminado, haga clic en **Agregar**.

> [!NOTE]
> Los correos electrónicos de estos remitentes se bloquearán como _phish_.

### <a name="use-powershell"></a>Usar PowerShell

Para agregar entradas de remitente suplantadas en la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).

## <a name="create-allowed-spoofed-sender-entries"></a>Creación de entradas de remitente suplantadas permitidas 

### <a name="use-the-tenant-allowblock-list-in-microsoft-365-defender"></a>Use la lista de permitidos o bloqueados de inquilinos en Microsoft 365 Defender

> [!NOTE]
>
> - Solo se permite o bloquea específicamente la _combinación_ del usuario suplantado _y_ la infraestructura de envío tal como se define en el par de dominio.
> - Al configurar una entrada de permitir o bloquear para un par de dominio, los mensajes de ese par de dominio ya no aparecen en la información de inteligencia de suplantación de identidad.
> - Las entradas para remitentes suplantados nunca expiran.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Correo electrónico &** directivas de colaboración \> **& reglas Directivas** \> de **amenazas** \> Listas de **inquilinos permitidos o bloqueados** en la sección **Reglas**. O bien, para ir directamente a la página **Permitir o bloquear listas de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. En la página **Lista de permitidos o bloqueados de inquilinos** , seleccione la pestaña **Suplantación** de identidad y, a continuación, haga clic en ![el icono Agregar.](../../media/m365-cc-sc-create-icon.png) **Agregar**.

3. En el control flotante **Agregar nuevos pares de dominio** que aparece, configure los siguientes valores:
   - **Agregar nuevos pares de dominio con caracteres comodín**: escriba un par de dominio por línea, hasta un máximo de 20. Para obtener más información sobre la sintaxis de las entradas de remitente suplantadas, consulte [Administrar la lista de permitidos o bloques](tenant-allow-block-list.md) de inquilinos.
   - **Tipo de suplantación**: seleccione uno de los valores siguientes:
     - **Interno**: el remitente suplantado está en un dominio que pertenece a su organización (un [dominio aceptado](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).
     - **Externo**: el remitente suplantado está en un dominio externo.
   - **Acción**: seleccione **Permitir**.

4. Cuando haya terminado, haga clic en **Agregar**.

### <a name="use-admin-submission-in-microsoft-365-defender"></a>Usar Administración envío en Microsoft 365 Defender

También puede permitir remitentes suplantados mediante la página **Envíos** de Microsoft 365 Defender.

Use [envíos de administrador](admin-submission.md) para enviar el mensaje bloqueado. Esta acción agregará la dirección URL, el archivo, el par de dominio del remitente suplantado, el dominio suplantado (o el usuario) o el remitente correspondiente a la lista de permitidos o bloqueados de inquilinos. Si el elemento no se ha bloqueado, no se creará el permiso. 

> [!IMPORTANT]
>
> - La suplantación de identidad permite encargarse de la suplantación de identidad entre organizaciones, organizaciones cruzadas y DMARC.
> - La nota opcional del envío del administrador no se aplica a la suplantación de identidad.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Acciones & envíos envíos**\>. O bien, para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la página **Envíos** , compruebe que la pestaña **Correos electrónicos** está seleccionada y, a continuación, haga clic en ![el icono Enviar a Microsoft para análisis.](../../media/m365-cc-sc-create-icon.png) **Envíe a Microsoft para su análisis**.

3. Use el control flotante **Enviar a Microsoft para revisar** para enviar un mensaje agregando el identificador de mensaje de red o cargando el archivo de correo electrónico.

4. En la sección **Seleccionar un motivo para enviar a Microsoft**, seleccione **No debería haberse bloqueado (falso positivo).**

5. Active **Permitir mensajes como esta** opción.

6. En la lista desplegable **Quitar después** de , especifique cuánto tiempo quiere que funcione la opción allow, aunque no se aplica a la suplantación de identidad, ya que nunca expiran.

7. Cuando haya terminado, seleccione **Enviar**.

  :::image type="content" source="../../media/admin-submission-allow-messages.png" alt-text="Envíe malware a Microsoft para el ejemplo de análisis." lightbox="../../media/admin-submission-allow-messages.png":::

> [!NOTE]
>
> - El par de dominio del remitente suplantado se creará y estará visible en la pestaña **Suplantado** en la página Lista de **permitidos o bloqueados de inquilinos** .


### <a name="use-powershell"></a>Usar PowerShell

Para agregar entradas de remitente suplantadas en la lista de permitidos o bloqueados de inquilinos en [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell), use la sintaxis siguiente:

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).

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

## <a name="modify-spoofed-sender-entries"></a>Modificación de entradas de remitente suplantadas 

Para modificar las entradas de remitente permitidas o bloqueadas en la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

En este ejemplo se cambia la entrada del remitente suplantado de allow a block.

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).

## <a name="remove-spoofed-sender-entries"></a>Eliminación de entradas de remitente suplantadas 

Para quitar las entradas de remitente de suplantación de identidad permitidas o bloqueadas de la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).

## <a name="create-impersonated-sender-entries"></a>Creación de entradas de remitente suplantadas

### <a name="use-admin-submission-in-microsoft-365-defender"></a>Usar Administración envío en Microsoft 365 Defender

También puede permitir remitentes suplantados mediante la página **Envíos** de Microsoft 365 Defender.

Use [envíos de administrador](admin-submission.md) para enviar el mensaje bloqueado. Esta acción agregará la dirección URL, el archivo, el par de dominio del remitente suplantado, el dominio suplantado (o el usuario) o el remitente correspondiente a la lista de permitidos o bloqueados de inquilinos. Si el elemento no se ha bloqueado, no se creará el permiso. 

> [!IMPORTANT]
>
> - La suplantación permite hacerse cargo de la suplantación de dominio y de usuario.
> - La suplantación de grafos no se tiene cuidado desde aquí por ahora.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Acciones & envíos envíos**\>. O bien, para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la página **Envíos** , compruebe que la pestaña **Correos electrónicos** está seleccionada y, a continuación, haga clic en ![el icono Enviar a Microsoft para análisis.](../../media/m365-cc-sc-create-icon.png) **Envíe a Microsoft para su análisis**.

3. Use el control flotante **Enviar a Microsoft para revisar** para enviar un mensaje agregando el identificador de mensaje de red o cargando el archivo de correo electrónico.

4. En la sección **Seleccionar un motivo para enviar a Microsoft**, seleccione **No debería haberse bloqueado (falso positivo).**

5. Active **Permitir mensajes como esta** opción.

6. En la lista desplegable **Quitar después** de , especifique cuánto tiempo quiere que funcione la opción allow, aunque no se aplica a los permitidos suplantados, ya que nunca expiran.

7. Cuando haya terminado, seleccione **Enviar**.

  :::image type="content" source="../../media/admin-submission-allow-messages.png" alt-text="Envíe malware a Microsoft para el ejemplo de análisis." lightbox="../../media/admin-submission-allow-messages.png":::

> [!NOTE]
> El dominio suplantado (o usuario) se creará y será visible en la sección **Remitentes y dominios de confianza** de la directiva contra suplantación de identidad en <https://security.microsoft.com/antiphishing>.

## <a name="related-articles"></a>Artículos relacionados

- [Envíos de administradores](admin-submission.md)
- [Notificar falsos positivos y falsos negativos](report-false-positives-and-false-negatives.md)
- [Administrar los bloques y los permitidos en la lista de permitidos o bloqueados de inquilinos](manage-tenant-allow-block-list.md)
- [Permitir o bloquear archivos en la lista de inquilinos permitidos o bloqueados](allow-block-files.md)
- [Permitir o bloquear direcciones URL en la lista de permitidos o bloqueados de inquilinos](allow-block-urls.md)
