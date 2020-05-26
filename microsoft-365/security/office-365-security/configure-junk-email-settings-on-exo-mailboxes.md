---
title: Configurar la configuración del correo no deseado en buzones de Exchange Online
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a configurar las opciones de correo no deseado en los buzones de Exchange Online. Muchos de estos valores de configuración están disponibles para los usuarios en Outlook o en Outlook en la Web.
ms.openlocfilehash: 72b2680cb16e9d8d0f33ee3ec8a080206c68bf97
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352515"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Configurar la configuración del correo no deseado en buzones de Exchange Online

En Microsoft 365 organizaciones con buzones en Exchange Online, Exchange Online Protection (EOP) controla la configuración contra correo no deseado de la organización. Para obtener más información, vea [protección contra correo no deseado en EOP](anti-spam-protection.md).

Pero también hay opciones de Configuración antispam específicas que los administradores pueden configurar en buzones individuales en Exchange Online:

- **Habilitar o deshabilitar la regla de correo no deseado**: la regla de correo no deseado es una regla de bandeja de entrada oculta denominada regla de correo electrónico no deseado que está habilitada de forma predeterminada en todos los buzones. La regla de correo no deseado controla las siguientes características:

  - **Mover mensajes a la carpeta de correo no deseado en función de las directivas contra correo no**deseado: cuando una directiva contra correo electrónico no deseado se configura con la acción **mover mensaje a la carpeta de correo no deseado** para un veredicto de filtrado de correo no deseado, la regla de filtro de correo no deseado mueve el mensaje a la carpeta correo electrónico no deseado después de que el mensaje se entregue al buzón. Para obtener más información sobre el filtrado de correo no deseado en directivas contra correo electrónico no deseado, vea [configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md). De forma similar, si la depuración automática de cero horas (ZAP) determina que un mensaje entregado es correo no deseado o phish, la regla de filtro de correo no deseado mueve el mensaje a la carpeta correo no deseado para **mover el mensaje a la carpeta correo no deseado** acciones de veredicto filtrado de correo no deseado. Para obtener más información acerca de ZAP, consulte [Zero-Hour auto Purge (ZAP) in Exchange Online](zero-hour-auto-purge.md).
  
  - **Configuración del correo no deseado que los usuarios se configuran para sí mismos en Outlook o Outlook en la web**: la _colección de listas seguras_ es la lista de remitentes seguros, la lista de destinatarios seguros y la lista de remitentes bloqueados en cada buzón. Las entradas de estas listas determinan si la regla de correo electrónico no deseado mueve el mensaje a la bandeja de entrada o a la carpeta de correo electrónico no deseado. Los usuarios pueden configurar la colección de listas seguras para su propio buzón de correo en Outlook o en Outlook en la web (anteriormente conocido como Outlook Web App). Los administradores pueden configurar la colección de listas seguras en el buzón de cualquier usuario.

Cuando la regla de correo no deseado está habilitada en el buzón, EOP puede mover los mensajes a la carpeta de correo no deseado en función de la acción de veredicto **mover mensaje a la carpeta** de correo no deseado o la lista de remitentes bloqueados en el buzón y evitar que los mensajes se entreguen a la carpeta de correo no deseado (según la lista de remitentes seguros del buzón)

 Cuando la regla de correo no deseado está deshabilitada en el buzón, EOP no puede mover mensajes a la carpeta de correo electrónico no deseado en función de la acción de veredicto **mover mensaje a la carpeta de correo no deseado o a** la colección de listas seguras del buzón.

Los administradores pueden usar Exchange Online PowerShell para deshabilitar, habilitar y ver el estado de la regla de correo no deseado en los buzones. Los administradores también pueden usar Exchange Online PowerShell para configurar entradas en la colección de listas seguras de los buzones (la lista de remitentes seguros, la lista de destinatarios seguros y la lista de remitentes bloqueados).

> [!NOTE]
> Los mensajes de remitentes que los usuarios han agregado a sus propias listas de remitentes seguros omitirán el filtrado de EOP (el SCL es-1). Para evitar que los usuarios agreguen entradas a la lista de remitentes seguros en Outlook, use la Directiva de grupo tal y como se indica en la sección acerca de la [configuración del correo electrónico no deseado en Outlook](#about-junk-email-settings-in-outlook) más adelante en este tema.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Solo puede usar Exchange Online PowerShell para realizar estos procedimientos. Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

- Debe tener permisos asignados para poder realizar estos procedimientos. En concreto, necesita la función **destinatarios de correo** (que está asignada a los grupos de roles administración de la **organización**, **Administración de destinatarios**y **destinatarios de correo personalizados** ) o el rol opciones de **usuario** (que se asigna a los grupos de roles administración de la **organización** y **servicio de asistencia** de forma predeterminada). Para agregar usuarios a los grupos de roles de Exchange Online, vea [Modify role Groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups). Tenga en cuenta que un usuario con permisos predeterminados puede realizar estos mismos procedimientos en su propio buzón de correo, siempre que tengan [acceso a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

- En entornos de EOP independientes en los que EOP protege los buzones de Exchange locales, tiene que configurar las reglas de flujo de correo (también conocidas como reglas de transporte) en Exchange local para traducir el veredicto de filtro de correo no deseado de EOP para que la regla de correo no deseado pueda mover el mensaje a la carpeta de correo electrónico no deseado. Para obtener información, consulte [Configuración de un EOP independiente para entregar el correo no deseado en la carpeta de correo no deseado en entornos híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- Los remitentes seguros para buzones compartidos no se sincronizan con Azure AD y EOP por diseño.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Usar Exchange Online PowerShell para habilitar o deshabilitar la regla de correo no deseado en un buzón

> [!NOTE]
> El cmdlet **Set-MailboxJunkEmailConfiguration** solo se puede usar para deshabilitar la regla de correo no deseado en un buzón que se ha abierto en Outlook (en modo caché de Exchange) o en Outlook en la web. Si el buzón no se ha abierto, recibirá el error: `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` si desea suprimir este error en operaciones masivas, puede agregar `-ErrorAction SlientlyContinue` al comando **set-MailboxJunkEmailConfiguration** .

Use esta sintaxis para habilitar o deshabilitar la regla de correo no deseado en un buzón:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

En este ejemplo se deshabilita la regla de correo no deseado en el buzón de Ori Epstein.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

Y en este se deshabilita la regla de correo no deseado en todos los buzones de usuario de la organización.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
> 
> - Si el usuario nunca ha abierto su buzón de correo, es posible que reciba un error al ejecutar el comando anterior. Para suprimir este error en operaciones masivas, agregue `-ErrorAction SlientlyContinue` al comando **set-MailboxJunkEmailConfiguration** .
> 
> - Incluso si deshabilita la regla de correo electrónico no deseado, el filtro de correo electrónico no deseado de Outlook (según cómo esté configurado) también puede determinar si un mensaje es correo no deseado y puede mover mensajes a la bandeja de entrada o a la carpeta de correo electrónico no deseado en función de su propio veredicto de correo no deseado y de la colección de listas seguras del buzón. Para más información, vea la sección [Acerca de la configuración de correo no deseado en Outlook](#about-junk-email-settings-in-outlook) de este tema.

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Realice uno de los siguientes procedimientos para confirmar que la regla de correo no deseado se ha habilitado o deshabilitado correctamente en un buzón:

- Reemplace _ \< MailboxIdentity \> _ por el nombre, el alias o la dirección de correo electrónico del buzón y ejecute el siguiente comando para comprobar el valor de la propiedad **Enabled** :

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Usar Exchange Online PowerShell para configurar la colección de listas seguras de un buzón

La colección de listas seguras de un buzón engloba la lista de remitentes seguros, la lista de destinatarios seguros y la lista de remitentes bloqueados. De forma predeterminada, los usuarios pueden configurar la colección de listas seguras en su propio buzón de correo en Outlook o en Outlook en la Web. Los administradores pueden usar los parámetros correspondientes del cmdlet **Set-MailboxJunkEmailConfiguration** para configurar la colección de listas seguras del buzón de un usuario. Estos parámetros se describen en la siguiente tabla.

|||
|---|---|
|**Parámetro en Set-MailboxJunkEmailConfiguration**|**Configuración de Outlook en la web**|
|_BlockedSendersAndDomains_|**Mover el correo electrónico de estos remitentes o dominios a la carpeta de correo electrónico no deseado**|
|_ContactsTrusted_|**Confiar en correo electrónico de mis contactos**|
|_TrustedListsOnly_|**Confiar solo en correo electrónico de direcciones en la lista de remitentes seguros y dominios y listas de correo seguro**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**No mover correo electrónico de estos remitentes a mi carpeta de correo electrónico no deseado**|
|

<sup>\*</sup>**Notas**:

- En Exchange Online, las **entradas de dominio** de la lista de remitentes seguros o el parámetro _TrustedSendersAndDomains_ no se reconocen, por lo que solo use direcciones de correo electrónico. En EOP independiente con sincronización de directorios, las entradas de dominio no se sincronizan de forma predeterminada, pero puede habilitar la sincronización para los dominios. Para obtener más información, vea [KB3019657](https://support.microsoft.com/help/3019657/domains-on-the-outlook-safe-senders-list-aren-t-recognized-by-exchange).

- No se puede modificar directamente la lista de destinatarios seguros mediante el cmdlet **set-MailboxJunkEmailConfiguration** (el parámetro _TrustedRecipientsAndDomains_ no funciona). En su lugar, hay que modificar la lista de remitentes seguros y esos cambios se sincronizan con la lista de destinatarios seguros.

Use la siguiente sintaxis para configurar la colección de listas seguras de un buzón:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Para escribir varios valores y sobrescribir las entradas existentes para los parámetros _BlockedSendersAndDomains_ y _TrustedSendersAndDomains_ , use la siguiente sintaxis: `"<Value1>","<Value2>"...` . Para agregar o quitar uno o más valores sin que ello afecte a las entradas existentes, use la siguiente sintaxis:`@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

En este ejemplo se establecen las siguientes configuraciones de la colección de listas seguras en el buzón de Ori Epstein:

- Agregue el valor shopping@fabrikam.com a la lista de remitentes bloqueados.

- Quite el valor chris@fourthcoffee.com de la lista de remitentes seguros y de la lista de destinatarios seguros.

- Se configuran contactos en la carpeta Contactos para que se traten como remitentes de confianza.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

En este ejemplo se quita el dominio contoso.com de la lista de remitentes bloqueados de todos los buzones de usuario de la organización.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
> 
> - Si el usuario no ha abierto nunca su buzón de correo, es posible que reciba un error al ejecutar los comandos anteriores. Para suprimir este error en operaciones masivas, agregue `-ErrorAction SlientlyContinue` al comando **set-MailboxJunkEmailConfiguration** .
> 
> - Incluso si la regla de correo no deseado está deshabilitada en el buzón, todavía puede configurar la colección de listas seguras y el filtro de correo electrónico no deseado de Outlook puede mover mensajes a la bandeja de entrada o a la carpeta de correo electrónico no deseado. Para más información, vea la sección [Acerca de la configuración de correo no deseado en Outlook](#about-junk-email-settings-in-outlook) de este tema.
> 
> - El filtro de correo electrónico no deseado de Outlook tiene una configuración de recopilación de listas seguras adicional (por ejemplo, **Agregar automáticamente mis contactos por correo electrónico a la lista de remitentes seguros**). Para más información, vea [Usar los filtros de correo electrónico no deseado para controlar los mensajes que ve](https://support.office.com/article/274ae301-5db2-4aad-be21-25413cede077).

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Realice uno de los siguientes procedimientos para confirmar que los límites de colección de listas seguras se han configurado correctamente en un buzón:

- Reemplace _ \< MailboxIdentity \> _ por el nombre, el alias o la dirección de correo electrónico del buzón y ejecute el siguiente comando para comprobar los valores de la propiedad:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Si la lista de valores es demasiado larga, use esta sintaxis:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Acerca de la configuración de correo no deseado en Outlook

Use la directiva de grupo para habilitar, deshabilitar y establecer las opciones de configuración de filtro de correo no deseado del cliente disponibles en Outlook. Para obtener más información, consulte [archivos de plantilla administrativa (ADMX/ADML) y herramienta de personalización de Office para las aplicaciones de Microsoft 365 para empresas, office 2019 y office 2016](https://www.microsoft.com/download/details.aspx?id=49030) y [cómo implementar la configuración del correo electrónico no deseado, como la lista de remitentes seguros, mediante la Directiva de grupo](https://support.microsoft.com/help/2252421/how-to-deploy-junk-email-settings-such-as-the-safe-senders-list-by-usi).

Cuando el filtro de correo electrónico no deseado de Outlook está establecido en el valor predeterminado, **no hay ningún filtro automático** en opciones **principales** de correo no deseado \> **Junk** \> **Junk E-Mail Options** \> **Options**, Outlook no intenta clasificar los masaje como correo no deseado, pero sigue utilizando la colección de listas seguras (la lista de remitentes seguros, la lista de destinatarios seguros y la lista de remitentes bloqueados) para mover los mensajes a la carpeta Para obtener más información acerca de estas opciones, vea [información general sobre el filtro de correo no deseado](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

Cuando el filtro de correo no deseado de Outlook está establecido en **Bajo** o **Alto**, el filtro de correo no deseado de Outlook usará su propia tecnología de filtrado SmartScreen para identificar y mover el correo no deseado a la carpeta de correo no deseado. Esta clasificación de correo no deseado es independiente del nivel de confianza contra correo no deseado (SCL) que se determina mediante EOP. De hecho, Outlook pasa por alto el SCL de EOP (a menos que EOP Marque el mensaje para omitir el filtrado de correo no deseado) y utiliza sus propios criterios para determinar si el mensaje es correo no deseado. Por supuesto, es posible que el veredicto de correo no deseado de EOP y Outlook sea el mismo. Para obtener más información acerca de estas opciones, vea [cambiar el nivel de protección en el filtro de correo no deseado](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b).

> [!NOTE]
> En noviembre de 2016, Microsoft dejó de generar actualizaciones de definición de correo no deseado para los filtros SmartScreen en Exchange y Outlook. Las definiciones de correo no deseado de SmartScreen existentes se dejaron en su lugar, pero su eficacia probablemente se degradará con el tiempo. Para obtener más información, consulte la [compatibilidad para SmartScreen en Outlook y Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).

Por lo tanto, el filtro de correo electrónico no deseado de Outlook puede usar la colección de listas seguras del buzón y su propia clasificación de correo no deseado para mover los mensajes a la carpeta de correo no deseado, incluso si la regla de correo no deseado está deshabilitada en el buzón.

Outlook y Outlook en la web admiten la colección de listas seguras. La colección de listas seguras se guarda en el buzón de correo de Exchange Online, por lo que los cambios en la colección de listas seguras de Outlook aparecen en Outlook en la web y viceversa.

## <a name="limits-for-junk-email-settings"></a>Límites de configuración de correo no deseado

La colección de listas seguras (la lista de remitentes seguros, la lista de destinatarios seguros y la lista de remitentes bloqueados) que se almacena en el buzón del usuario también se sincroniza con EOP. Con la sincronización de directorios, la colección de listas seguras se sincroniza con Azure AD.

- La colección de listas seguras del buzón del usuario tiene un límite de 510 KB, que incluye todas las listas, además de la configuración adicional del filtro de correo no deseado. Si un usuario supera este límite, recibirá un error de Outlook similar al siguiente:

  > No se puede o no se puede Agregar a las listas de correo no deseado del servidor. Ha superado el tamaño permitido en el servidor. El filtro de correo electrónico no deseado en el servidor se deshabilitará hasta que las listas de correo no deseado se hayan reducido al tamaño permitido por el servidor.

  Para obtener más información acerca de este límite y de cómo cambiarlo, vea [KB2669081](https://support.microsoft.com/help/2669081/outlook-error-indicates-that-you-are-over-the-junk-e-mail-list-limit).

- La colección de listas seguras sincronizada en EOP tiene los siguientes límites de sincronización:

  - 1024 el total de entradas de la lista de remitentes seguros, la lista de destinatarios seguros y los contactos externos si está habilitada la opción **confiar en correo electrónico de mis contactos** .
  - 500 total de entradas en la lista de remitentes bloqueados y en la lista de dominios bloqueados.

  Cuando se alcanza el límite de entrada de 1024, ocurrirá lo siguiente:
  
  - La lista deja de aceptar entradas en PowerShell y Outlook en la web, pero no se muestra ningún error.

    Los usuarios de Outlook pueden seguir agregando más de 1024 entradas hasta que alcancen el límite de 510 KB de Outlook. Outlook puede usar estas entradas adicionales, siempre que un filtro de EOP no bloquee el mensaje antes de enviarlo al buzón (reglas de flujo de correo, contra la suplantación de identidad, etc.).

- Con la sincronización de directorios, las entradas se sincronizan con Azure AD en el orden siguiente:

  1. Contactos de correo si **la opción confiar en correo electrónico de mis contactos** está habilitada.
  2. La lista de remitentes seguros y la lista de destinatarios seguros se combinan, desduplican y ordenan alfabéticamente siempre que se realiza un cambio en las primeras 1024 entradas.

  Se usan las primeras 1024 entradas y se marca la información correspondiente en los encabezados del mensaje.
  
  Las entradas superiores a 1024 que no se sincronizaron con Azure AD son procesadas por Outlook (no por Outlook en la web) y no se ha estampado ninguna información en los encabezados del mensaje.

Como puede ver, si habilita la configuración **confiar en correo electrónico de mis contactos** , se reduce el número de remitentes seguros y destinatarios seguros que se pueden sincronizar. Si esto es un problema, le recomendamos usar la Directiva de grupo para desactivar esta característica:

- Nombre de archivo: outlk16. opax
- Configuración de directiva: **confiar en correo electrónico de contactos**
