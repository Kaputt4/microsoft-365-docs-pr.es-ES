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
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
ms.custom: seo-marvel-apr2020
description: El registro de auditoría de buzones de correo está activado de forma predeterminada en Microsoft 365 (también denominado auditoría de buzones de correo predeterminada o auditoría de buzones de correo de forma predeterminada). Esto significa que determinadas acciones realizadas por los propietarios de buzones de correo, los delegados y los administradores se registran automáticamente en un registro de auditoría de buzones de correo, donde puede buscar actividades realizadas en el buzón.
ms.openlocfilehash: 5b1aaab6db56d989c36cd977122d4e5843587aac
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817839"
---
# <a name="manage-mailbox-auditing"></a>Administrar la auditoría de buzones de correo

A partir de enero de 2019, Microsoft activa el registro de auditoría de buzones de correo de forma predeterminada para todas las organizaciones. Esto significa que se registran automáticamente determinadas acciones realizadas por los propietarios de buzones de correo, los delegados y los administradores, y los registros de auditoría de buzones correspondientes estarán disponibles cuando los busque en el registro de auditoría de buzones de correo. Antes de que se activara la auditoría de buzones de correo de forma predeterminada, tenía que habilitarla manualmente para cada buzón de usuario de la organización.

Estas son algunas de las ventajas de la auditoría de buzones de correo de forma predeterminada:

- La auditoría se habilita automáticamente cuando se crea un nuevo buzón de correo. No es necesario habilitarlo manualmente para los nuevos usuarios.

- No es necesario administrar las acciones de buzón de correo que se auditan. De forma predeterminada, se audita un conjunto predefinido de acciones de buzón para cada tipo de inicio de sesión (Administrador, delegado y propietario).

- Cuando Microsoft lanza una nueva acción de buzón (especialmente acciones que ayudan a proteger la organización y ayuda con las investigaciones forenses), la acción se agrega automáticamente a la lista de acciones de buzón de correo que se auditan de forma predeterminada. Esto significa que no es necesario supervisar agregar nuevas acciones en los buzones de correo.

- Tiene una directiva de auditoría de buzones de correo coherente en toda la organización (porque está auditando las mismas acciones para todos los buzones de correo).

> [!NOTE]
>* Lo importante que debe recordar sobre la publicación de la auditoría de buzones de forma predeterminada es: no es necesario realizar ninguna acción para administrar la auditoría de buzones de correo. Sin embargo, para obtener más información, personalizar la auditoría de buzones de correo de la configuración predeterminada o desactivarla a la vez, este tema puede ayudarle.
>- De forma predeterminada, solo los eventos de auditoría de buzones para los usuarios de E5 están disponibles en las búsquedas del registro de auditoría en el centro de seguridad & cumplimiento o a través de la API de actividad de administración 365 de Office. Para obtener más información, vea la sección [más información](#more-information) de este tema.

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>Comprobar que la auditoría de buzones de correo está activada de forma predeterminada

Para comprobar que la auditoría de buzones de correo está activada de forma predeterminada para su organización, ejecute el siguiente comando en [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

El valor **false** indica que la auditoría de buzones de correo está habilitada de forma predeterminada para la organización. Este valor de organización de activado de forma predeterminada invalida la configuración de auditoría de buzones de correo en determinados buzones. Por ejemplo, si la auditoría de buzones de correo está deshabilitada para un buzón de correo (la propiedad *AuditEnabled* es **false** en el buzón de correo), las acciones de buzón predeterminadas se auditarán para el buzón, ya que la auditoría de buzones está habilitada de forma predeterminada para la organización.

Para mantener la auditoría de buzones de correo deshabilitada para buzones específicos, configure el desvío de auditoría de buzón para el propietario del buzón y otros usuarios a los que se les ha delegado acceso al buzón. Para obtener más información, vea la sección [omitir el registro de auditoría de buzones](#bypass-mailbox-audit-logging) en este tema.

> [!NOTE]
> Cuando la auditoría de buzones de correo está activada de forma predeterminada para la organización, la propiedad *AuditEnabled* de los buzones afectados no cambiará de **falso** a **verdadero**. Es decir, la auditoría de buzones activada de forma predeterminada omite la propiedad *AuditEnabled* en los buzones de correo.

## <a name="supported-mailbox-types"></a>Tipos de buzones admitidos

En la siguiente tabla se muestran los tipos de buzones actualmente compatibles con la auditoría de buzones de correo de forma predeterminada:

|**Tipo de buzón**|**Admitido**|**No admitido**|
|:---------|:---------:|:---------:|
|Buzones de usuario|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|Buzones compartidos|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|Buzones de grupo de Microsoft 365|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|Buzones de recursos||![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Buzones de carpetas públicas||![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|

## <a name="logon-types-and-mailbox-actions"></a>Tipos de inicio de sesión y acciones de buzón

Los tipos de inicio de sesión clasifican al usuario que llevó a cabo las acciones auditadas en el buzón. En la siguiente lista se describen los tipos de inicio de sesión que se usan en el registro de auditoría de buzones:

- **Owner**: el propietario del buzón (la cuenta que está asociada con el buzón de correo).

- **Delegado**:

  - Un usuario al que se le haya asignado el permiso sendas, SendOnBehalf o FullAccess a otro buzón de correo.

  - Un administrador al que se haya asignado el permiso FullAccess en el buzón de un usuario.

- **Administrador**:

  - El buzón de correo se busca con una de las siguientes herramientas de eDiscovery de Microsoft:

    - Búsqueda de contenido en el centro de cumplimiento.

    - eDiscovery o exhibición avanzada de documentos electrónicos en el centro de cumplimiento.

    - Exhibición de documentos electrónicos local en Exchange Online.

  - Se obtiene acceso al buzón con Microsoft Exchange Server MAPI editor.

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>Acciones de buzón de correo para buzones de usuario y buzones compartidos

En la tabla siguiente se describen las acciones de buzón de correo que están disponibles en el registro de auditoría de buzones para buzones de usuario y buzones compartidos.

- Una marca de verificación ( ![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)) indica que la acción del buzón se puede registrar para el tipo de inicio de sesión (no todas las acciones están disponibles para todos los tipos de inicio de sesión).

- Un asterisco ( <sup>\*</sup> ) después de la marca de verificación indica que la acción del buzón se registra de forma predeterminada para el tipo de inicio de sesión.

- Recuerde que un administrador con permiso de acceso total a un buzón de correo se considera un delegado.

|**Acción del buzón**|**Descripción**|**Administrador**|**Delegado**|**Propietario**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**AddFolderPermissions**|**Nota**: aunque este valor se acepta como una acción de buzón de correo, ya está incluido en la acción **UpdateFolderPermissions** y no se audita por separado. Es decir, no use este valor.||||
|**ApplyRecord**|Un elemento se etiqueta como registro.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Copiar**|Un mensaje se copió en otra carpeta.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|**Crear**|Se ha creado un elemento en la carpeta calendario, contactos, notas o tareas del buzón de correo (por ejemplo, se crea una nueva convocatoria de reunión). No se audita la creación, el envío ni la recepción de un mensaje. Además, no se audita la creación de una carpeta del buzón.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Default**||![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**FolderBind**|A mailbox folder was accessed. This action is also logged when the admin or delegate opens the mailbox. <br/><br/> **Nota**: los registros de auditoría para las acciones de enlace de carpeta realizadas por los delegados están consolidados. Se genera un registro de auditoría para el acceso a la carpeta individual en un período de 24 horas.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|**HardDelete**|Un mensaje se purgó de la carpeta Elementos recuperables.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MailItemsAccessed**|Los protocolos de correo y los clientes tienen acceso a los datos de correo. Este valor solo está disponible para los usuarios de la suscripción del complemento de cumplimiento E5 o E5. Para obtener más información, consulte [acceso a eventos vitales para las investigaciones](advanced-audit.md#access-to-crucial-events-for-investigations).|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MailboxLogin**|El usuario ha iniciado sesión en su buzón. |||![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**MessageBind**|Un mensaje se vio en el panel de vista previa o se abrió por un administrador. **Nota**: aunque este valor se acepta como acción de buzón de correo, estas acciones ya no se registran.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|**ModifyFolderPermissions**|**Nota**: aunque este valor se acepta como una acción de buzón de correo, ya está incluido en la acción **UpdateFolderPermissions** y no se audita por separado. Es decir, no use este valor.||||
|**Mover**|Un mensaje se movió a otra carpeta.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**MoveToDeletedItems**|Un mensaje se eliminó y se movió a la carpeta Elementos eliminados.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**RecordDelete**|Un elemento etiquetado como registro se eliminó de forma Soft (se movió a la carpeta elementos recuperables). Los elementos etiquetados como registros no se pueden eliminar de forma permanente (se purgan de la carpeta elementos recuperables).|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**RemoveFolderPermissions**|**Nota**: aunque este valor se acepta como una acción de buzón de correo, ya está incluido en la acción **UpdateFolderPermissions** y no se audita por separado. Es decir, no use este valor.||||
|**SendAs**|A message was sent using the SendAs permission. This means another user sent the message as though it came from the mailbox owner.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SendOnBehalf**|A message was sent using the SendOnBehalf permission. This means another user sent the message on behalf of the mailbox owner. The message indicates to the recipient who the message was sent on behalf of and who actually sent the message.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SoftDelete**|A message was permanently deleted or deleted from the Deleted Items folder. Soft-deleted items are moved to the Recoverable Items folder.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**Actualización**|Se cambió un mensaje o sus propiedades.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|Se asignó una delegación de calendario a un buzón. La delegación de calendario otorga a otra persona en la misma organización permisos para administrar el calendario del propietario del buzón.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateComplianceTag**|Se aplica una etiqueta de retención diferente a un elemento de correo (un elemento solo puede tener una etiqueta de retención asignada).|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**UpdateFolderPermissions**|Un permiso de la carpeta se ha cambiado. Los permisos de carpeta controlan qué usuarios de su organización pueden tener acceso las carpetas de un buzón de correo y los mensajes que contienen.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateInboxRules**|Se ha agregado, quitado o cambiado una regla de bandeja de entrada. Las reglas de la bandeja de entrada se usan para procesar mensajes en la bandeja de entrada del usuario en función de las condiciones especificadas y emprender acciones cuando se cumplen las condiciones de una regla, como mover un mensaje a una carpeta especificada o eliminar un mensaje.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|

> [!IMPORTANT]
> Si ha personalizado las acciones de buzón de correo para auditar cualquier tipo de inicio de sesión *antes* de que la auditoría de buzones de correo esté habilitada de forma predeterminada en la organización, la configuración personalizada se conserva en el buzón y las acciones predeterminadas del buzón de correo no las sobrescriben como se describe en esta sección. Para revertir las acciones de auditoría del buzón a sus valores predeterminados (lo que puede hacer en cualquier momento), vea la sección [restaurar acciones del buzón predeterminado](#restore-the-default-mailbox-actions) más adelante en este tema.

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a>Acciones de buzón para buzones de grupo de Microsoft 365

La auditoría de buzones de correo de forma predeterminada incorpora el registro de auditoría de buzones a los buzones de grupo de Microsoft 365, pero no se puede personalizar lo que se está registrando (no se pueden agregar ni quitar acciones de buzón que se registran para cualquier tipo de inicio de sesión).

En la tabla siguiente se describen las acciones de buzón que se registran de forma predeterminada en los buzones de grupo de Microsoft 365 para cada tipo de inicio de sesión.

Recuerde que un administrador con permiso de acceso total a un buzón de grupo de Microsoft 365 se considera un delegado.

|**Acción del buzón**|**Descripción**|**Administrador**|**Delegado**|**Propietario**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**Crear**|Creación de un elemento de calendario. No se audita la creación, el envío ni la recepción de un mensaje.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**HardDelete**|Un mensaje se purgó de la carpeta Elementos recuperables.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MoveToDeletedItems**|Un mensaje se eliminó y se movió a la carpeta Elementos eliminados.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**SendAs**|Un mensaje se ha enviado con el permiso Enviar como.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SendOnBehalf**|Un mensaje se ha enviado con el permiso SendOnBehalf. |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SoftDelete**|A message was permanently deleted or deleted from the Deleted Items folder. Soft-deleted items are moved to the Recoverable Items folder.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**Actualización**|Se cambió un mensaje o sus propiedades.|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>Compruebe que se registran las acciones predeterminadas del buzón para cada tipo de inicio de sesión

La auditoría de buzones de correo en de forma predeterminada agrega una nueva propiedad *DefaultAuditSet* a todos los buzones. El valor de esta propiedad indica si las acciones del buzón de correo predeterminadas (administradas por Microsoft) se están auditando en el buzón.

Para mostrar el valor de los buzones de usuario o los buzones compartidos, reemplace \<MailboxIdentity\> por el nombre, el alias, la dirección de correo electrónico o el nombre principal del usuario (nombre de usuario) del buzón y ejecute el siguiente comando en Exchange Online PowerShell:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

Para mostrar el valor en los buzones de grupo de Microsoft 365, reemplace \<MailboxIdentity\> por el nombre, el alias o la dirección de correo electrónico del buzón compartido y ejecute el siguiente comando en Exchange Online PowerShell:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

El valor `Admin, Delegate, Owner` indica:

- Las acciones predeterminadas de buzón para los tres tipos de inicio de sesión se están auditando. Este es el único valor que verá en buzones de grupo de Microsoft 365.

- Un administrador *no ha* cambiado las acciones del buzón auditado para ningún tipo de inicio de sesión en un buzón de usuario o un buzón compartido. Nota: este es el estado predeterminado después de que la auditoría de buzones de correo está activada de forma predeterminada en la organización.

Si un administrador ha cambiado alguna vez las acciones de buzón de correo que se auditan para un tipo de inicio de sesión (mediante los parámetros *AuditAdmin*, *AuditDelegate*o *AuditOwner* en el cmdlet **set-Mailbox** ), el valor de la propiedad será diferente.

Por ejemplo, el valor `Owner` de la propiedad *DefaultAuditSet* en un buzón de usuario o un buzón compartido indica lo siguiente:

- Se están auditando las acciones predeterminadas del buzón para el propietario del buzón.

- Las acciones de buzón auditado para los `Delegate` tipos de inicio de sesión y y `Admin` se han cambiado de las acciones predeterminadas.

Un valor en blanco para la propiedad *DefaultAuditSet* indica que las acciones de buzón de los tres tipos de inicio de sesión se han cambiado en el buzón de usuario o en un buzón compartido.

Para obtener más información, vea la sección [cambiar o restaurar acciones del buzón registradas de forma predeterminada](#change-or-restore-mailbox-actions-logged-by-default) en este tema.

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>Mostrar las acciones del buzón que se registran en los buzones

Para ver las acciones de buzón de correo que se están registrando en ese momento en buzones de usuario o en buzones compartidos, reemplace \<MailboxIdentity\> con el nombre, el alias, la dirección de correo electrónico o el nombre principal de usuario (username) del buzón y ejecute uno o más de los siguientes comandos en Exchange Online PowerShell.

> [!NOTE]
> Aunque puede Agregar el `-GroupMailbox` conmutador a los siguientes comandos **Get-Mailbox** para buzones de grupo de Microsoft 365, no cree los valores que se devuelven. Las acciones de buzón predeterminadas y estáticas que se auditan para buzones de grupo de Microsoft 365 se describen en la sección [acciones de buzón para los buzones de grupo de microsoft 365](#mailbox-actions-for-microsoft-365-group-mailboxes) anteriormente en este tema.

#### <a name="owner-actions"></a>Acciones del propietario

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>Acciones de delegado

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>Acciones de administración

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>Cambiar o restaurar acciones de buzón registradas de forma predeterminada

Como se ha explicado anteriormente, una de las principales ventajas de tener la auditoría de buzones de correo activada de forma predeterminada es: no es necesario administrar las acciones de buzones de correo que se auditan. Microsoft hace esto por usted y se agregarán automáticamente nuevas acciones de buzón de correo para que se audirán de forma predeterminada a medida que se publican.

Sin embargo, es posible que se requiera que la organización audite un conjunto diferente de acciones de buzón de correo de los buzones de usuario y los buzones compartidos. Los procedimientos de esta sección muestran cómo cambiar las acciones de buzón de correo que se auditan para cada tipo de inicio de sesión y cómo volver a las acciones predeterminadas administradas por Microsoft.

> [!IMPORTANT]
> Si usa los procedimientos siguientes para personalizar las acciones de buzón de correo que han iniciado sesión en los buzones de usuario o los buzones compartidos, las nuevas acciones de buzón predeterminadas que Microsoft publica no se auditarán automáticamente en esos buzones. Tendrá que agregar manualmente las acciones de buzón de correo nuevas a la lista personalizada de acciones.

### <a name="change-the-mailbox-actions-to-audit"></a>Cambiar las acciones de buzón de correo para auditar

Puede usar los parámetros *AuditAdmin*, *AuditDelegate*o *AuditOwner* en el cmdlet **set-Mailbox** para cambiar las acciones de buzón de correo que se auditan para los buzones de usuario y los buzones compartidos (las acciones auditadas para los buzones de grupo de Microsoft 365 no se pueden personalizar).

Puede usar dos métodos diferentes para especificar las acciones del buzón:

- *Reemplace* (sobrescriba) las acciones de buzón existentes mediante esta sintaxis: `action1,action2,...actionN` .

- *Agregue o quite* acciones de buzón sin que ello afecte a otros valores existentes con esta sintaxis: `@{Add="action1","action2",..."actionN"}` o `@{Remove="action1","action2",..."actionN"}` .

En este ejemplo se cambian las acciones de buzón de administrador para el buzón denominado "Gabriela Laureano" al sobrescribir las acciones predeterminadas con SoftDelete y HardDelete.

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

En este ejemplo se agrega la acción de propietario MailboxLogin al buzón laura@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

En este ejemplo se quita la acción de delegado MoveToDeletedItems del buzón de discusión de grupo.

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

Independientemente del método que use, la personalización de las acciones de buzón auditado en los buzones de usuario o los buzones compartidos tiene los siguientes resultados:

- Para el tipo de inicio de sesión personalizado, Microsoft ya no administra las acciones del buzón auditado.

- El tipo de inicio de sesión que ha personalizado ya no se muestra en el valor de la propiedad *DefaultAuditSet* para el buzón como [se ha descrito anteriormente](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type).

### <a name="restore-the-default-mailbox-actions"></a>Restaurar las acciones del buzón predeterminadas

Si ha personalizado las acciones de buzón de correo que se auditan en un buzón de usuario o un buzón compartido, puede restaurar las acciones del buzón de correo predeterminadas para uno o todos los tipos de inicio de sesión con esta sintaxis:

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

Puede especificar varios valores de *DefaultAuditSet* separados por comas.

**Nota**: los siguientes procedimientos no se aplican a los buzones de grupo de Microsoft 365 (están limitados a las acciones predeterminadas como se describe [aquí](#mailbox-actions-for-microsoft-365-group-mailboxes)).

En este ejemplo se restauran las acciones predeterminadas del buzón auditado para todos los tipos de inicio de sesión en el buzón mark@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

En este ejemplo se restauran las acciones de buzón auditado predeterminadas para el tipo de inicio de sesión de administrador en el buzón chris@contoso.onmicrosoft.com, pero se conservan las acciones de buzón auditado personalizadas para los tipos de inicio de sesión de delegado y propietario.

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

La restauración de las acciones predeterminadas del buzón auditado para un tipo de inicio de sesión tiene los siguientes resultados:

- La lista actual de acciones del buzón se reemplaza por las acciones predeterminadas del buzón para el tipo de inicio de sesión.

- Las nuevas acciones de buzón de correo que Microsoft publica se agregan automáticamente a la lista de acciones auditadas para el tipo de inicio de sesión.

- El valor de la propiedad *DefaultAuditSet* del buzón se actualiza para incluir el tipo de inicio de sesión restaurado.

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>Desactivar la auditoría de buzones de correo en la organización de forma predeterminada

Puede desactivar la auditoría de buzones de correo de forma predeterminada para toda la organización ejecutando el siguiente comando en Exchange Online PowerShell:

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

La desactivación de la auditoría de buzones de correo de de forma predeterminada tiene los siguientes resultados:

- La auditoría de buzones de correo está deshabilitada para su organización.

- Desde el momento en que deshabilitó la auditoría de buzones de correo de forma predeterminada, no se audita ninguna acción de buzón, incluso si la auditoría está habilitada en un buzón (la propiedad *AuditEnabled* del buzón es **true**).

- La auditoría de buzones de correo no está habilitada para nuevos buzones y se omitirá la configuración de la propiedad *AuditEnabled* en un buzón nuevo o existente a **true** .

- Se omiten las opciones de Asociación de omisión de auditoría de buzones (configuradas mediante el cmdlet **set-MailboxAuditBypassAssociation** ).

- Los registros de auditoría de buzones de correo existentes se conservan hasta que expira el límite de antigüedad del registro de auditoría para el registro.

### <a name="turn-on-mailbox-auditing-on-by-default"></a>Activar la auditoría de buzones de correo de forma predeterminada

Para volver a activar la auditoría de buzones de correo para su organización, ejecute el siguiente comando en Exchange Online PowerShell:

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>Omisión del registro de auditoría de buzones

Actualmente, no puede deshabilitar la auditoría de buzones de correo específicos cuando la auditoría de buzones de correo está activada de forma predeterminada en la organización. Por ejemplo, se omite el establecimiento de la propiedad de buzón *AuditEnabled* en **false** .

Sin embargo, puede seguir usando el cmdlet **set-MailboxAuditBypassAssociation** de PowerShell de Exchange Online para *evitar que* se registren todas las acciones de buzón de correo de los usuarios especificados, independientemente de dónde se produzcan las acciones. Por ejemplo:

- No se registran las acciones del propietario del buzón realizadas por los usuarios omitidos.

- Las acciones de delegado realizadas por los usuarios omitidos en los buzones de otros usuarios (incluidos los buzones compartidos) no se registran.

- Las acciones de administración realizadas por los usuarios omitidos no se registran.

Para omitir el registro de auditoría de buzones de correo para un usuario específico, reemplace \<MailboxIdentity\> por el nombre, la dirección de correo electrónico, el alias o el nombre principal de usuario (username) del usuario y ejecute el siguiente comando:

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

Para comprobar que la auditoría se omite para el usuario especificado, ejecute el siguiente comando:

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

El valor **true** indica que el registro de auditoría de buzones de correo se omite para el usuario.

## <a name="more-information"></a>Más información

- Aunque el inicio de sesión de auditoría de buzones de forma predeterminada está habilitado para todas las organizaciones, solo los usuarios con licencias de E5 devolverán eventos de registro de auditoría de buzones de [Auditoría en el centro de seguridad & cumplimiento](search-the-audit-log-in-security-and-compliance.md) o a través de la [API de actividad de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) de **forma predeterminada**.

  Para recuperar las entradas del registro de auditoría de buzones de correo de los usuarios sin licencias de E5, puede:

  - Habilite manualmente la auditoría de buzones de correo en buzones individuales (ejecute el comando `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` ). Después de hacerlo, puede usar las búsquedas del registro de auditoría en el centro de seguridad & cumplimiento o a través de la API de actividad de administración de Office 365.
  
    > [!NOTE]
    > Si la auditoría de buzones de correo ya está habilitada en el buzón de correo, pero las búsquedas no devuelven resultados, cambie el valor del parámetro _AuditEnabled_ a `$false` y, a continuación, otra vez a `$true` .
  
  - Use los cmdlets siguientes en Exchange Online PowerShell:

    - [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) para buscar en el registro de auditoría de buzones de correo de determinados usuarios.

    - [New-MailboxAuditLogSearch](https://docs.microsoft.com/powershell/module/exchange/new-mailboxauditlogsearch) para buscar en el registro de auditoría de buzones de correo los usuarios específicos y para enviar los resultados por correo electrónico a los destinatarios especificados.

  - Use el centro de administración de Exchange (EAC) en Exchange Online para realizar las siguientes acciones:

    - [Exportar registros de auditoría de buzones](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)

    - [Ejecución de un informe de acceso al buzón de correo del que no se es propietario](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- De forma predeterminada, los registros de registro de auditoría de buzones se conservan durante 90 días antes de su eliminación. Puede cambiar el límite de antigüedad de las entradas del registro de auditoría mediante el uso del parámetro *AuditLogAgeLimit* en el cmdlet **set-Mailbox** de Exchange Online PowerShell. Sin embargo, el aumento de este valor no le permite buscar eventos que tengan más de 90 días en el registro de auditoría.

  Si aumenta el límite de antigüedad, debe usar el cmdlet [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) en Exchange Online PowerShell para buscar en el registro de auditoría del buzón del usuario registros de más de 90 días.

- Si ha cambiado la propiedad *AuditLogAgeLimit* de un buzón antes de auditar el buzón de correo activado de forma predeterminada para la organización, el límite de antigüedad del registro de auditoría existente del buzón no cambia. Es decir, la auditoría de buzones de correo de forma predeterminada no afecta al límite de antigüedad actual para los registros de auditoría de buzón.

- Para cambiar el valor de *AuditLogAgeLimit* en un buzón de grupo de Microsoft 365, debe incluir el `-GroupMailbox` conmutador en el comando **set-Mailbox** .

- Los registros de registro de auditoría de buzones de correo se almacenan en una subcarpeta (denominada *Audits*) en la carpeta elementos recuperables del buzón de correo de cada usuario. Tenga en cuenta lo siguiente en lo que se refiere a los registros de auditoría de buzones de correo y la carpeta elementos recuperables:

  - Los registros de auditoría de buzones de correo tienen en cuenta la cuota de almacenamiento de la carpeta elementos recuperables, que es 30 de manera predeterminada (la cuota de advertencia es de 20 GB). La cuota de almacenamiento aumenta automáticamente a 100 GB (con una cuota de advertencia de 90 GB) cuando:

    - Se guarda una retención en un buzón.

    - El buzón se asigna a una directiva de retención en el centro de cumplimiento.

  - Los registros de auditoría de buzón también cuentan en el [límite de carpetas de la carpeta elementos recuperables](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits). Se puede almacenar un máximo de 3 millones elementos (registros de auditoría) en la subcarpeta auditorías.

    > [!NOTE]
    > Es improbable que la auditoría de buzones de correo que se produzca de forma predeterminada afecte a la cuota de almacenamiento o el límite de la carpeta de elementos recuperables.

    - Puede ejecutar el siguiente comando en Exchange Online PowerShell para mostrar el tamaño y el número de elementos en la subcarpeta Audits de la carpeta elementos recuperables:

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - No se puede tener acceso directamente a un registro de auditoría en la carpeta elementos recuperables; en su lugar, use el cmdlet **Search-MailboxAuditLog** o busque en el registro de auditoría para buscar y ver registros de auditoría de buzón de correo.

- Si un buzón se coloca en suspensión o se asigna a una directiva de retención en el centro de cumplimiento, las entradas del registro de auditoría se conservan durante el tiempo definido por la propiedad *AuditLogAgeLimit* del buzón (90 días de forma predeterminada). Para conservar los registros de auditoría más largas para los buzones en retención, debe aumentar el valor de *AuditLogAgeLimit* del buzón.

- En un entorno multigeográfico, la auditoría de buzón multigeográfico no es compatible. Por ejemplo, si se asignan permisos a un usuario para tener acceso a un buzón compartido en una ubicación geográfica diferente, las acciones de buzón que realiza el usuario no se registran en el registro de auditoría del buzón de correo compartido.
