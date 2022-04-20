---
title: Administrar la auditoría de buzones de correo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
description: El registro de auditoría de buzones está activado de forma predeterminada en Microsoft 365 (también denominado "auditoría predeterminada de buzones" o "auditoría de buzones de correo de forma predeterminada"). Esta configuración significa que ciertas acciones realizadas por propietarios, delegados y administradores de buzones de correo se registran automáticamente en un registro de auditoría de buzones, donde puede buscar actividades realizadas en el buzón.
ms.openlocfilehash: d5d966cf4d5b7c58c15df4ce8d4039331ebca8c4
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64972637"
---
# <a name="manage-mailbox-auditing"></a>Administrar la auditoría de buzones de correo

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

A partir de enero de 2019, Microsoft activa el registro de auditoría de buzones de forma predeterminada para todas las organizaciones. Esto significa que ciertas acciones realizadas por los propietarios, delegados y administradores del buzón de correo se registran automáticamente y los registros de auditoría de buzón correspondientes estarán disponibles al buscarlos en el registro de auditoría del buzón. Antes de que la auditoría de buzones se activara de forma predeterminada, tenía que habilitarla manualmente para cada buzón de correo de usuario de la organización.

Estas son algunas ventajas de la auditoría de buzones de correo en de forma predeterminada:

- La auditoría se habilita automáticamente al crear un nuevo buzón. No es necesario habilitarlo manualmente para los nuevos usuarios.
- No es necesario administrar las acciones de buzón que se auditan. De forma predeterminada, se audita un conjunto predefinido de acciones de buzón para cada tipo de inicio de sesión (administrador, delegado y propietario).
- Cuando Microsoft publica una nueva acción de buzón de correo, la acción podría agregarse automáticamente a la lista de acciones de buzón auditadas de forma predeterminada (siempre que el usuario tenga la licencia adecuada). Esto significa que no es necesario supervisar la incorporación de nuevas acciones en buzones de correo.
- Tiene una directiva de auditoría de buzones coherente en toda la organización (porque está auditando las mismas acciones para todos los buzones).

> [!NOTE]
>
> - Lo importante que debe recordar sobre la versión de auditoría de buzones de correo en de forma predeterminada es: no es necesario hacer nada para administrar la auditoría de buzones. Sin embargo, para obtener más información, personalizar la auditoría de buzones de correo desde la configuración predeterminada o desactivarla por completo, este artículo puede ayudarle.
> - De forma predeterminada, solo los eventos de auditoría de buzones de correo para los usuarios de E5 están disponibles en las búsquedas de registros de auditoría en el portal de cumplimiento de Microsoft Purview o a través de la API de actividad de administración de Office 365. Para obtener más información, consulte la sección [Más información](#more-information) de este artículo.

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>Comprobar que la auditoría del buzón está activada de forma predeterminada

Para comprobar que la auditoría de buzones activada de forma predeterminada está activada para su organización, ejecute el siguiente comando en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

El valor **False** indica que la auditoría de buzones de correo está habilitada de forma predeterminada para la organización. De forma predeterminada, el valor de la organización invalida la configuración de auditoría de buzones en buzones específicos. Por ejemplo, si la auditoría del buzón de correo está deshabilitada para un buzón (la propiedad *AuditEnabled* es **False** en el buzón), las acciones predeterminadas del buzón se seguirán auditando para el buzón, ya que la auditoría del buzón está habilitada de forma predeterminada para la organización.

Para mantener deshabilitada la auditoría de buzones para buzones específicos, configure la omisión de auditoría de buzones para el propietario del buzón y otros usuarios a los que se ha delegado el acceso al buzón. Para obtener más información, vea la sección [Omitir registro de auditoría de buzones](#bypass-mailbox-audit-logging) más adelante en este artículo.

> [!NOTE]
> Cuando la auditoría de buzones activada de forma predeterminada está activada para la organización, la propiedad *AuditEnabled* de los buzones afectados no cambiará de **False** a **True**. En otras palabras, la auditoría de buzones en omite de forma predeterminada la propiedad *AuditEnabled* en los buzones.

## <a name="supported-mailbox-types"></a>Tipos de buzón admitidos

En la tabla siguiente se muestran los tipos de buzón admitidos actualmente por la auditoría de buzones de correo de forma predeterminada:

|Tipo de buzón|Compatible|
|---|:---:|
|Buzones de usuario|![Marca de verificación.](../media/checkmark.png)|
|Buzones compartidos|![Marca de verificación.](../media/checkmark.png)|
|buzones de Microsoft 365 group|![Marca de verificación.](../media/checkmark.png)|
|Buzones de recursos||
|Buzones de carpetas públicas||

## <a name="logon-types-and-mailbox-actions"></a>Tipos de inicio de sesión y acciones de buzón

Los tipos de inicio de sesión clasifican al usuario que realizó las acciones auditadas en el buzón. En la lista siguiente se describen los tipos de inicio de sesión que se usan en el registro de auditoría de buzones:

- **Propietario**: propietario del buzón (la cuenta asociada al buzón).
- **Delegado**:
  - Usuario al que se ha asignado el permiso SendAs, SendOnBehalf o FullAccess a otro buzón.
  - Un administrador al que se ha asignado el permiso FullAccess al buzón de un usuario.
- **Administrador**:
  - El buzón de correo se busca con una de las siguientes herramientas de Exhibición de documentos electrónicos de Microsoft:
    - Búsqueda de contenido en el Centro de cumplimiento.
    - eDiscovery o eDiscovery (Premium) en el Centro de cumplimiento.
    - In-Place eDiscovery en Exchange Online.
  - Se obtiene acceso al buzón mediante el editor de MAPI de Microsoft Exchange Server.

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>Acciones de buzón para buzones de usuario y buzones compartidos

En la tabla siguiente se describen las acciones de buzón que están disponibles en el registro de auditoría de buzones de correo para buzones de usuario y buzones compartidos.

- Una marca de verificación (![Marca de verificación.](../media/checkmark.png)) indica que la acción de buzón se puede registrar para el tipo de inicio de sesión (no todas las acciones están disponibles para todos los tipos de inicio de sesión).
- Un asterisco ( <sup>\*</sup> ) después de la marca de verificación indica que la acción del buzón se registra de forma predeterminada para el tipo de inicio de sesión.
- Recuerde que un administrador con permiso de acceso completo a un buzón se considera un delegado.

|Acción buzón|Descripción|Admin|Delegado|Owner|
|---|---|:---:|:---:|:---:|
|**AddFolderPermissions**|Aunque este valor se acepta como una acción de buzón de correo, ya se incluye en la acción **UpdateFolderPermissions** y no se audita por separado. En otras palabras, no use este valor.||||
|**ApplyRecord**|Un elemento se etiqueta como un registro.|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|
|**Copiar**|Un mensaje se copió en otra carpeta.|![Marca de verificación.](../media/checkmark.png)|||
|**Create**|Se creó un elemento en la carpeta Calendario, Contactos, Borrador, Notas o Tareas del buzón (por ejemplo, se crea una nueva convocatoria de reunión). No se audita la creación, el envío ni la recepción de un mensaje. Además, no se audita la creación de una carpeta del buzón.|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación.](../media/checkmark.png)|
|**FolderBind**|Se tuvo acceso a una carpeta de buzón de correo. Esta acción también se registra cuando el administrador o un delegado abren el buzón de correo.<br/><br/> **Nota**: Se consolidan los registros de auditoría de las acciones de enlace de carpeta realizadas por los delegados. Se genera un registro de auditoría para el acceso a carpetas individuales en un período de 24 horas.|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)||
|**HardDelete**|Un mensaje se purgó de la carpeta Elementos recuperables.|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|
|**MailboxLogin**|El usuario ha iniciado sesión en su buzón de correo.|||![Marca de verificación](../media/checkmark.png)|
|**MailItemsAccessed**|**Nota**: Este valor solo está disponible para los usuarios con licencias E5/A5/G5. Para obtener más información, vea [Configurar microsoft Purview Audit (Premium)](set-up-advanced-audit.md). <br/><br/> Los clientes y protocolos de correo acceden a los datos de correo.|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|
|**MessageBind**|**Nota**: Este valor solo está disponible para los usuarios *sin* licencias E5/A5/G5. <br/><br/> Un administrador ha visto un mensaje en el panel de vista previa o lo ha abierto.|![Marca de verificación](../media/checkmark.png)|||
|**ModifyFolderPermissions**|Aunque este valor se acepta como una acción de buzón de correo, ya se incluye en la acción **UpdateFolderPermissions** y no se audita por separado. En otras palabras, no use este valor.||||
|**Mover**|Un mensaje se movió a otra carpeta.|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|
|**MoveToDeletedItems**|Un mensaje se eliminó y se movió a la carpeta Elementos eliminados.|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|
|**RecordDelete**|Un elemento etiquetado como registro se eliminó temporalmente (se movió a la carpeta Elementos recuperables). Los elementos etiquetados como registros no se pueden eliminar permanentemente (se purgan de la carpeta Elementos recuperables).|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|
|**RemoveFolderPermissions**|Aunque este valor se acepta como una acción de buzón de correo, ya se incluye en la acción **UpdateFolderPermissions** y no se audita por separado. En otras palabras, no use este valor.||||
|**SearchQueryInitiated**|**Nota**: Este valor solo está disponible para los usuarios con licencias E5/A5/G5. Para obtener más información, vea [Configurar microsoft Purview Audit (Premium)](set-up-advanced-audit.md). <br/><br/> Una persona usa Outlook (Windows, Mac, iOS, Android o Outlook en la Web) o la aplicación Mail para Windows 10 para buscar elementos en un buzón.|||![Marca de verificación](../media/checkmark.png)|
|**Send**|**Nota**: Este valor solo está disponible para los usuarios con licencias E5/A5/G5. Para obtener más información, vea [Configurar microsoft Purview Audit (Premium)](set-up-advanced-audit.md). <br/><br/> El usuario envía un mensaje de correo electrónico, responde a un mensaje de correo electrónico o reenvía un mensaje de correo electrónico.|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>||![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|Un mensaje se envió mediante el permiso SendAs. Esto significa que otro usuario envió el mensaje como si procediera del propietario del buzón.|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|Un mensaje se envió mediante el permiso SendOnBehalf. Esto significa que otro usuario envió el mensaje en nombre del propietario del buzón. El mensaje indica el destinatario en nombre de quien se envió el mensaje y quién lo envió realmente.|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|Un mensaje se eliminó permanentemente o se eliminó de la carpeta Elementos eliminados. Los elementos eliminados de forma temporal se mueven a la carpeta Elementos recuperables.|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|
|**Actualización**|Se ha cambiado un mensaje o cualquiera de sus propiedades.|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|Se asignó una delegación de calendario a un buzón de correo. La delegación de calendario otorga a otra persona en la misma organización permisos para administrar el calendario del propietario del buzón.|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>||![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|
|**UpdateComplianceTag**|Se aplica una etiqueta de retención diferente a un elemento de correo (un elemento solo puede tener una etiqueta de retención asignada).|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|![Marca de verificación](../media/checkmark.png)|
|**UpdateFolderPermissions**|Un permiso de la carpeta se ha cambiado. Los permisos de carpeta controlan qué usuarios de su organización pueden tener acceso las carpetas de un buzón de correo y los mensajes que contienen.|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|
|**UpdateInboxRules**|Se agregó, quitó o cambió una regla de bandeja de entrada. Las reglas de bandeja de entrada se usan para procesar mensajes en la Bandeja de entrada del usuario en función de las condiciones especificadas y realizar acciones cuando se cumplen las condiciones de una regla, como mover un mensaje a una carpeta especificada o eliminar un mensaje.|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|

> [!IMPORTANT]
> Si personalizó las acciones del buzón para auditar cualquier tipo de inicio de sesión *antes* de que la auditoría del buzón se habilitara de forma predeterminada en su organización, la configuración personalizada se conservará en el buzón y no se sobrescribirá mediante las acciones predeterminadas del buzón, como se describe en esta sección. Para revertir las acciones del buzón de auditoría a sus valores predeterminados (que puede hacer en cualquier momento), consulte la sección [Restaurar las acciones predeterminadas del buzón](#restore-the-default-mailbox-actions) más adelante en este artículo.

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a>Acciones de buzón de correo para buzones de Microsoft 365 grupo

La auditoría de buzones en de forma predeterminada lleva el registro de auditoría del buzón a Microsoft 365 buzones de grupo, pero no puede personalizar lo que se registra (no puede agregar ni quitar acciones de buzón que se registran para cualquier tipo de inicio de sesión).

En la tabla siguiente se describen las acciones de buzón que se registran de forma predeterminada en Microsoft 365 buzones de grupo para cada tipo de inicio de sesión.

Recuerde que un administrador con permiso de acceso completo a un buzón de Microsoft 365 grupo se considera un delegado.

|Acción buzón|Descripción|Admin|Delegado|Owner|
|---|---|:---:|:---:|:---:|
|**Create**|Creación de un elemento de calendario. No se audita la creación, el envío ni la recepción de un mensaje.|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>||
|**HardDelete**|Un mensaje se purgó de la carpeta Elementos recuperables.|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|
|**MoveToDeletedItems**|Un mensaje se eliminó y se movió a la carpeta Elementos eliminados.|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|Un mensaje se ha enviado con el permiso Enviar como.|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|Un mensaje se ha enviado con el permiso SendOnBehalf.|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|Un mensaje se eliminó permanentemente o se eliminó de la carpeta Elementos eliminados. Los elementos eliminados de forma temporal se mueven a la carpeta Elementos recuperables.|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|
|**Actualización**|Se ha cambiado un mensaje o cualquiera de sus propiedades.|![Marca de verificación.](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../media/checkmark.png)<sup>\*</sup>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>Compruebe que las acciones predeterminadas del buzón de correo se registran para cada tipo de inicio de sesión.

La auditoría de buzones en agrega de forma predeterminada una nueva propiedad *DefaultAuditSet* a todos los buzones. El valor de esta propiedad indica si las acciones predeterminadas del buzón (administradas por Microsoft) se auditan en el buzón.

Para mostrar el valor en buzones de usuario o buzones compartidos, reemplace por \<MailboxIdentity\> el nombre, alias, dirección de correo electrónico o nombre principal de usuario (nombre de usuario) del buzón y ejecute el siguiente comando en Exchange Online PowerShell:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

Para mostrar el valor en los buzones de Microsoft 365 grupo, reemplace por \<MailboxIdentity\> el nombre, el alias o la dirección de correo electrónico del buzón compartido y ejecute el siguiente comando en Exchange Online PowerShell:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

El valor `Admin, Delegate, Owner` indica:

- Se auditan las acciones predeterminadas de buzón de los tres tipos de inicio de sesión. Este es el único valor que verá en los buzones de Microsoft 365 grupo.
- Un administrador *no ha* cambiado las acciones del buzón auditado para ningún tipo de inicio de sesión en un buzón de usuario o un buzón compartido. Tenga en cuenta que este es el estado predeterminado después de que la auditoría de buzones activada de forma predeterminada esté activada inicialmente en su organización.

Si un administrador ha cambiado alguna vez las acciones de buzón que se auditan para un tipo de inicio de sesión (mediante los parámetros *AuditAdmin*, *AuditDelegate* o *AuditOwner* en el cmdlet **Set-Mailbox** ), el valor de la propiedad será diferente.

Por ejemplo, el valor `Owner` de la propiedad *DefaultAuditSet* en un buzón de usuario o buzón compartido indica lo siguiente:

- Se auditan las acciones predeterminadas del buzón de correo para el propietario del buzón.
- Las acciones de buzón auditadas para los `Delegate` tipos de inicio de sesión y `Admin` se han cambiado de las acciones predeterminadas.

Un valor en blanco para la propiedad *DefaultAuditSet* indica que las acciones de buzón de los tres tipos de inicio de sesión se han cambiado en el buzón de usuario o en un buzón compartido.

Para obtener más información, vea la sección [Cambiar o restaurar acciones de buzón registradas de forma predeterminada](#change-or-restore-mailbox-actions-logged-by-default) en este artículo.

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>Mostrar las acciones de buzón que se registran en los buzones

Para ver las acciones de buzón que están iniciando sesión actualmente en buzones de usuario o buzones compartidos, reemplace por \<MailboxIdentity\> el nombre, el alias, la dirección de correo electrónico o el nombre principal de usuario (nombre de usuario) del buzón y ejecute uno o varios de los siguientes comandos en Exchange Online PowerShell.

> [!NOTE]
> Aunque puede agregar el `-GroupMailbox` modificador a los siguientes comandos **Get-Mailbox** para los buzones de Microsoft 365 Group, no crea los valores que se devuelven. Las acciones predeterminadas y estáticas de buzón de correo que se auditan para los buzones de Microsoft 365 grupo se describen en la sección [Acciones de buzón de correo para Microsoft 365 Buzones de grupo](#mailbox-actions-for-microsoft-365-group-mailboxes) anteriormente en este artículo.

#### <a name="owner-actions"></a>Acciones de propietario

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>Acciones de delegación

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>Acciones de administrador

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>Cambiar o restaurar acciones de buzón registradas de forma predeterminada

Como se explicó anteriormente, una de las principales ventajas de la auditoría de buzones de correo de forma predeterminada es: no es necesario administrar las acciones de buzones que se auditan. Microsoft lo hace automáticamente y agregaremos automáticamente nuevas acciones de buzón que se auditarán de forma predeterminada a medida que se publiquen.

Sin embargo, es posible que sea necesario que su organización audite un conjunto diferente de acciones de buzón de correo para buzones de usuario y buzones compartidos. Los procedimientos de esta sección muestran cómo cambiar las acciones de buzón que se auditan para cada tipo de inicio de sesión y cómo revertir a las acciones predeterminadas administradas por Microsoft.

> [!IMPORTANT]
> Si usa los procedimientos siguientes para personalizar las acciones de buzón que han iniciado sesión en buzones de usuario o buzones compartidos, las nuevas acciones predeterminadas de buzón publicadas por Microsoft no se auditarán automáticamente en esos buzones. Tendrá que agregar manualmente las nuevas acciones de buzón a la lista personalizada de acciones.

### <a name="change-the-mailbox-actions-to-audit"></a>Cambiar las acciones del buzón de correo para auditar

Puede usar los parámetros *AuditAdmin*, *AuditDelegate* o *AuditOwner* en el cmdlet **Set-Mailbox** para cambiar las acciones de buzón que se auditan para buzones de usuario y buzones compartidos (las acciones auditadas para Microsoft 365 buzones de grupo no se pueden personalizar).

Puede usar dos métodos diferentes para especificar las acciones del buzón:

- *Reemplace* (sobrescriba) las acciones de buzón existentes mediante esta sintaxis: `action1,action2,...actionN`.
- *Agregue o quite* acciones de buzón sin afectar a otros valores existentes mediante esta sintaxis: `@{Add="action1","action2",..."actionN"}` o `@{Remove="action1","action2",..."actionN"}`.

En este ejemplo se cambian las acciones del buzón de administración para el buzón denominado "Gabriela Laureano" al sobrescribir las acciones predeterminadas con SoftDelete y HardDelete.

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

En este ejemplo se agrega la acción de propietario MailboxLogin al buzón de correo laura@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

En este ejemplo se quita la acción de delegado MoveToDeletedItems para el buzón de team discussion.

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

Independientemente del método que use, la personalización de las acciones de buzón auditadas en buzones de usuario o buzones compartidos tiene los siguientes resultados:

- Para el tipo de inicio de sesión que ha personalizado, Microsoft ya no administra las acciones de buzón auditadas.
- El tipo de inicio de sesión que ha personalizado ya no se muestra en el valor de la propiedad *DefaultAuditSet* del buzón, como [se describió anteriormente](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type).

### <a name="restore-the-default-mailbox-actions"></a>Restauración de las acciones predeterminadas del buzón

> [!NOTE]
> Los procedimientos siguientes no se aplican a los buzones de Microsoft 365 Grupo (se limitan a las acciones predeterminadas, como se describe [aquí](#mailbox-actions-for-microsoft-365-group-mailboxes)).

Si personalizó las acciones de buzón de correo que se auditan en un buzón de usuario o un buzón compartido, puede restaurar las acciones predeterminadas de buzón de correo para uno o todos los tipos de inicio de sesión mediante esta sintaxis:

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

Puede especificar varios valores *DefaultAuditSet* separados por comas

En este ejemplo se restauran las acciones predeterminadas del buzón auditado para todos los tipos de inicio de sesión en el buzón mark@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

En este ejemplo se restauran las acciones de buzón auditadas predeterminadas para el tipo de inicio de sesión Admin en el buzón de correo chris@contoso.onmicrosoft.com, pero deja las acciones de buzón auditadas personalizadas para los tipos de inicio de sesión Delegado y Propietario.

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

La restauración de las acciones predeterminadas del buzón auditado para un tipo de inicio de sesión tiene los siguientes resultados:

- La lista actual de acciones de buzón se reemplaza por las acciones de buzón predeterminadas para el tipo de inicio de sesión.
- Las nuevas acciones de buzón publicadas por Microsoft se agregan automáticamente a la lista de acciones auditadas para el tipo de inicio de sesión.
- El valor de la propiedad *DefaultAuditSet* del buzón se actualiza para incluir el tipo de inicio de sesión restaurado.

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>Desactivar la auditoría de buzones de correo activada de forma predeterminada para la organización

Puede desactivar la auditoría de buzones de correo de forma predeterminada para toda la organización ejecutando el siguiente comando en Exchange Online PowerShell:

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

La desactivación de la auditoría de buzones activada de forma predeterminada tiene los siguientes resultados:

- La auditoría de buzones está deshabilitada para su organización.
- Desde el momento en que deshabilitó la auditoría de buzones de correo de forma predeterminada, no se audita ninguna acción de buzón, incluso si la auditoría está habilitada en un buzón (la propiedad *AuditEnabled* del buzón es **True**).
- La auditoría de buzones no está habilitada para los buzones nuevos y se omitirá la configuración de la propiedad *AuditEnabled* en un buzón nuevo o existente en **True** .
- Cualquier configuración de asociación de omisión de auditoría de buzón (configurada mediante el cmdlet **Set-MailboxAuditBypassAssociation** ) se omite.
- Los registros de auditoría de buzones existentes se conservan hasta que expire el límite de antigüedad del registro de auditoría para el registro.

### <a name="turn-on-mailbox-auditing-on-by-default"></a>Activar la auditoría del buzón de correo de forma predeterminada

Para volver a activar la auditoría de buzones para su organización, ejecute el siguiente comando en Exchange Online PowerShell:

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>Omita el registro de auditoría de buzones de correo

Actualmente, no puede deshabilitar la auditoría de buzones de correo para buzones específicos cuando la auditoría de buzones está activada de forma predeterminada en la organización. Por ejemplo, se omite establecer la propiedad de buzón *AuditEnabled* en **False** .

Sin embargo, todavía puede usar el cmdlet **Set-MailboxAuditBypassAssociation** en Exchange Online PowerShell para evitar que se *registren todas y cada una* de las acciones de buzón de correo de los usuarios especificados, independientemente de dónde se produzcan las acciones. Por ejemplo:

- Las acciones de propietario del buzón realizadas por los usuarios omitidos no se registran.
- Las acciones de delegación realizadas por los usuarios omitidos en los buzones de otros usuarios (incluidos los buzones compartidos) no se registran.
- Las acciones de administración realizadas por los usuarios omitidos no se registran.

Para omitir el registro de auditoría del buzón de un usuario específico, reemplace \<MailboxIdentity\> por el nombre, la dirección de correo electrónico, el alias o el nombre principal de usuario (nombre de usuario) del usuario y ejecute el siguiente comando:

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

Para comprobar que se omite la auditoría para el usuario especificado, ejecute el siguiente comando:

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

El valor **True** indica que el registro de auditoría del buzón se omite para el usuario.

## <a name="more-information"></a>Más información

- Aunque el registro de auditoría de buzones de correo está habilitado de forma predeterminada para todas las organizaciones, solo los usuarios con licencias E5 devolverán eventos de registro de auditoría de buzones en [las búsquedas de registros de auditoría en el portal de cumplimiento de Microsoft Purview](search-the-audit-log-in-security-and-compliance.md) o a través de [la API de actividad de administración de Office 365](/office/office-365-management-api/office-365-management-activity-api-reference) **de forma predeterminada**.

  Para recuperar entradas de registro de auditoría de buzones para usuarios sin licencias E5/A5/G5, puede usar cualquiera de las siguientes soluciones alternativas:

  - Habilite manualmente la auditoría de buzones en buzones individuales (ejecute el comando , `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true`). Después de hacerlo, puede usar búsquedas de registros de auditoría en el portal de cumplimiento de Microsoft Purview o a través de la API de actividad de administración de Office 365.

    > [!NOTE]
    > Si la auditoría de buzones ya parece estar habilitada en el buzón de correo, pero las búsquedas no devuelven resultados, cambie el valor del parámetro *AuditEnabled* a `$false` y vuelva a `$true`.

  - Use los siguientes cmdlets en Exchange Online PowerShell:
    - [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) para buscar usuarios específicos en el registro de auditoría del buzón.
    - [New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) para buscar usuarios específicos en el registro de auditoría del buzón y enviar los resultados por correo electrónico a los destinatarios especificados.

  - Use el Centro de administración de Exchange (EAC) en Exchange Online para realizar las siguientes acciones:
    - [Exportar registros de auditoría de buzones](/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)
    - [Ejecutar un informe de acceso al buzón de correo del que no se es propietario](/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- De forma predeterminada, los registros de auditoría de buzones se conservan durante 90 días antes de que se eliminen. Puede cambiar el límite de edad de los registros de auditoría mediante el parámetro *AuditLogAgeLimit* en el cmdlet **Set-Mailbox** en Exchange Online PowerShell. Sin embargo, el aumento de este valor no permite buscar eventos que tengan más de 90 días en el registro de auditoría.

  Si aumenta el límite de edad, debe usar el cmdlet [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) en Exchange Online PowerShell para buscar registros de auditoría del buzón de correo del usuario en busca de registros que tengan más de 90 días.

- Si ha cambiado la propiedad *AuditLogAgeLimit* de un buzón antes de que la auditoría del buzón esté activada de forma predeterminada para la organización, el límite de antigüedad del registro de auditoría existente del buzón no cambia. En otras palabras, la auditoría de buzones de correo activada de forma predeterminada no afecta al límite de edad actual para los registros de auditoría de buzones.

- Para cambiar el valor *AuditLogAgeLimit* en un buzón de Microsoft 365 Grupo, debe incluir el `-GroupMailbox` modificador en el comando **Set-Mailbox**.

- Los registros de auditoría de buzones se almacenan en una subcarpeta (denominada *Auditorías*) en la carpeta Elementos recuperables del buzón de cada usuario. Tenga en cuenta lo siguiente sobre los registros de auditoría del buzón y la carpeta Elementos recuperables:

  - Los registros de auditoría de buzones cuentan con la cuota de almacenamiento de la carpeta Elementos recuperables, que es de 30 GB de forma predeterminada (la cuota de advertencia es de 20 GB). La cuota de almacenamiento se aumenta automáticamente a 100 GB (con una cuota de advertencia de 90 GB) cuando:
    - Se coloca una suspensión en un buzón.
    - El buzón se asigna a una directiva de retención en el Centro de cumplimiento.

  - Los registros de auditoría de buzones también cuentan con el [límite de carpetas de la carpeta Elementos recuperables](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits). Se puede almacenar un máximo de 3 millones de elementos (registros de auditoría) en la subcarpeta Auditorías.

    > [!NOTE]
    > Es poco probable que la auditoría de buzones en de forma predeterminada afecte a la cuota de almacenamiento o al límite de carpetas de la carpeta Elementos recuperables.

    - Puede ejecutar el siguiente comando en Exchange Online PowerShell para mostrar el tamaño y el número de elementos en la subcarpeta Auditorías de la carpeta Elementos recuperables:

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - No puede acceder directamente a un registro de auditoría en la carpeta Elementos recuperables; en su lugar, use el cmdlet **Search-MailboxAuditLog** o busque en el registro de auditoría para buscar y ver los registros de auditoría del buzón.

- Si un buzón se coloca en espera o se asigna a una directiva de retención en el Centro de cumplimiento, los registros de auditoría se conservan durante la duración definida por la propiedad *AuditLogAgeLimit* del buzón (90 días de forma predeterminada). Para conservar los registros de auditoría durante más tiempo para los buzones en espera, debe aumentar el valor *AuditLogAgeLimit* del buzón.

- En un entorno multigeográfico, la auditoría de buzón multigeográfico no es compatible. Por ejemplo, si se asignan permisos a un usuario para tener acceso a un buzón compartido en una ubicación geográfica diferente, las acciones de buzón que realiza el usuario no se registran en el registro de auditoría del buzón de correo compartido. Exchange eventos de auditoría de administrador solo están disponibles actualmente para la ubicación predeterminada.
