---
title: Configurar la configuración del correo no deseado en buzones de Exchange Online
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a configurar las opciones de correo no deseado en los buzones de Exchange Online. Muchas de estas opciones de configuración están disponibles para los usuarios en Outlook o Outlook en la web.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: debd07b1195c2122c8e5042a30097c377bd1c803
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906509"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Configurar la configuración del correo no deseado en buzones de Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

En las organizaciones de Microsoft 365 con buzones en Exchange Online, la configuración de la organización contra correo no deseado está controlada por Exchange Online Protection (EOP). Para obtener más información, vea [Protección contra correo no deseado en EOP](anti-spam-protection.md).

Sin embargo, también hay opciones específicas contra correo no deseado que los administradores pueden configurar en buzones individuales en Exchange Online:

- **Habilitar o deshabilitar la regla** de correo no deseado: la regla de correo no deseado es una regla de bandeja de entrada oculta denominada Regla de correo electrónico no deseado que está habilitada de forma predeterminada en cada buzón. La regla de correo no deseado controla las siguientes características:

  - Mover mensajes a la carpeta correo no deseado según directivas contra correo no  **deseado:** cuando se configura una directiva contra correo no deseado con la acción Mover mensaje a la carpeta correo no deseado para un veredicto de filtrado de correo no deseado, la regla de filtro de correo no deseado mueve el mensaje a la carpeta Correo no deseado después de entregar el mensaje al buzón. Para obtener más información acerca de los veredictos de filtrado de correo no deseado en directivas contra correo no deseado, vea [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md). Del mismo modo, si la purga automática de cero horas (ZAP) determina que un mensaje entregado es  correo no deseado o phish, la regla de filtro de correo no deseado mueve el mensaje a la carpeta correo no deseado para mover el mensaje a la carpeta de correo no deseado acciones de veredicto de filtrado de correo no deseado. Para obtener más información acerca de ZAP, vea [Zero-hour auto purge (ZAP) in Exchange Online](zero-hour-auto-purge.md).

  - Configuración de correo no deseado que los usuarios configuran para sí mismos en Outlook o Outlook en la **web:** la colección _de_ listas seguras es la lista remitentes seguros, la lista de destinatarios seguros y la lista remitentes bloqueados en cada buzón. Las entradas de estas listas determinan si la regla de correo no deseado mueve el mensaje a la bandeja de entrada o a la carpeta Correo no deseado. Los usuarios pueden configurar la colección de listas seguras para su propio buzón en Outlook o Outlook en la web (anteriormente conocido como Outlook Web App). Los administradores pueden configurar la colección de listas seguras en el buzón de cualquier usuario.

Cuando la regla de correo no deseado está habilitada en el buzón, EOP puede mover  mensajes a la carpeta correo no deseado en función de la acción de veredicto de filtrado de correo no deseado Mover el mensaje a la carpeta Correo no deseado o la lista Remitentes bloqueados en el buzón e impedir que los mensajes se entreguen a la carpeta correo no deseado (según la lista Remitentes seguros del buzón).

 Cuando la regla de correo no deseado está deshabilitada en el buzón, EOP no  puede mover mensajes a la carpeta correo no deseado en función de la acción de veredicto de filtrado de correo no deseado Mover el mensaje a la carpeta correo no deseado o a la colección de listas seguras del buzón.

Los administradores pueden usar Exchange Online PowerShell para deshabilitar, habilitar y ver el estado de la regla de correo no deseado en los buzones. Los administradores también pueden usar Exchange Online PowerShell para configurar las entradas de la colección de listas seguras en los buzones (la lista Remitentes seguros, la lista Destinatarios seguros y la lista Remitentes bloqueados).

> [!NOTE]
> Los mensajes de remitentes que los usuarios han agregado a sus propias listas de remitentes seguros omitirán el filtrado de conexiones como parte de EOP (el SCL es -1). Para evitar que los usuarios agreguen entradas a su lista de remitentes seguros en Outlook, use la directiva de grupo como se mencionó en la sección Acerca de la configuración del correo no deseado en  [Outlook](#about-junk-email-settings-in-outlook) más adelante en este artículo. El filtrado de directivas, el filtrado de contenido y las comprobaciones de Defender para Office 365 se seguirán aplicando a los mensajes.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Solo puede usar Exchange Online PowerShell para realizar los procedimientos descritos en este artículo. Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Debe tener asignados permisos en Exchange Online antes de poder realizar los procedimientos descritos en este artículo. En concreto, necesita  el rol Destinatarios de correo (que está asignado a los grupos de roles  Administración de la **organización,**  Administración de  destinatarios y Destinatarios de correo **personalizados** de forma predeterminada) o el rol Opciones de usuario (que se asigna de forma predeterminada a los grupos de roles Administración de la organización y Servicio de ayuda).  Para agregar usuarios a grupos de roles en Exchange Online, vea [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups). Tenga en cuenta que los usuarios con permisos predeterminados pueden realizar estos mismos procedimientos en su propio buzón, siempre que tengan acceso a [Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell).

- En entornos de EOP independientes en los que EOP protege los buzones de Exchange locales, tiene que configurar las reglas de flujo de correo (también conocidas como reglas de transporte) en Exchange local para traducir el veredicto de filtro de correo no deseado de EOP para que la regla de correo no deseado pueda mover el mensaje a la carpeta de correo electrónico no deseado. Para obtener información, consulte [Configuración de un EOP independiente para entregar el correo no deseado en la carpeta de correo no deseado en entornos híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- Los remitentes seguros para buzones compartidos no se sincronizan con Azure AD y EOP por diseño.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Usar Exchange Online PowerShell para habilitar o deshabilitar la regla de correo no deseado en un buzón

> [!NOTE]
> El cmdlet **Set-MailboxJunkEmailConfiguration** solo se puede usar para deshabilitar la regla de correo no deseado en un buzón que se ha abierto en Outlook (en modo caché de Exchange) o en Outlook en la web. Si el buzón no se ha abierto, recibirá el error: si desea suprimir este error para operaciones masivas, puede agregar al comando `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration.**

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

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
>
> - Si el usuario nunca ha abierto su buzón, es posible que reciba un error al ejecutar el comando anterior. Para suprimir este error para operaciones masivas, agregue `-ErrorAction SilentlyContinue` al **comando Set-MailboxJunkEmailConfiguration.**
>
> - Incluso si deshabilita la regla de correo no deseado, el filtro de correo no deseado de Outlook (según cómo esté configurado) también puede determinar si un mensaje es correo no deseado y puede mover mensajes a la carpeta Bandeja de entrada o correo no deseado en función de su propio veredicto de correo no deseado y de la colección de listas seguras del buzón. Para obtener más información, vea la [sección Acerca de](#about-junk-email-settings-in-outlook) la configuración del correo no deseado en Outlook en este artículo.

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Realice uno de los siguientes procedimientos para confirmar que la regla de correo no deseado se ha habilitado o deshabilitado correctamente en un buzón:

- Reemplace por el nombre, alias o dirección de correo electrónico del buzón y ejecute el _\<MailboxIdentity\>_ siguiente comando para comprobar el valor de la propiedad **Enabled:**

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Usar Exchange Online PowerShell para configurar la colección de listas seguras en un buzón

La colección de listas seguras de un buzón engloba la lista de remitentes seguros, la lista de destinatarios seguros y la lista de remitentes bloqueados. De forma predeterminada, los usuarios pueden configurar la colección de listas seguras en su propio buzón en Outlook o Outlook en la web. Los administradores pueden usar los parámetros correspondientes del cmdlet **Set-MailboxJunkEmailConfiguration** para configurar la colección de listas seguras del buzón de un usuario. Estos parámetros se describen en la siguiente tabla.

****

|Parámetro en Set-MailboxJunkEmailConfiguration|Configuración de Outlook en la web|
|---|---|
|_BlockedSendersAndDomains_|**Mover el correo electrónico de estos remitentes o dominios a la carpeta de correo electrónico no deseado**|
|_ContactsTrusted_|**Confiar en correo electrónico de mis contactos**|
|_TrustedListsOnly_|**Solo confiar en el correo electrónico de las direcciones de mi lista remitentes y dominios seguros y listas de correo seguro**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**No mover el correo electrónico de estos remitentes a mi carpeta correo no deseado**|
|

<sup>\*</sup>**Notas:**

- En Exchange Online, las entradas **de** dominio de la lista Remitentes seguros o el parámetro _TrustedSendersAndDomains_ no se reconocen, por lo que solo se usan direcciones de correo electrónico. En EOP independiente con sincronización de directorios, las entradas de dominio no se sincronizan de forma predeterminada, pero puede habilitar la sincronización para dominios. Para obtener más información, [vea KB3019657](https://support.microsoft.com/help/3019657).

- No puede modificar directamente la lista de destinatarios seguros mediante el cmdlet **Set-MailboxJunkEmailConfiguration** (el parámetro _TrustedRecipientsAndDomains_ no funciona). En su lugar, hay que modificar la lista de remitentes seguros y esos cambios se sincronizan con la lista de destinatarios seguros.

Use la siguiente sintaxis para configurar la colección de listas seguras de un buzón:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Para escribir varios valores y sobrescribir las entradas existentes para los parámetros _BlockedSendersAndDomains_ y _TrustedSendersAndDomains,_ use la sintaxis siguiente: `"<Value1>","<Value2>"...` . Para agregar o quitar uno o varios valores sin afectar a otras entradas existentes, use la sintaxis siguiente: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

En este ejemplo se establecen las siguientes configuraciones de la colección de listas seguras en el buzón de Ori Epstein:

- Agregue el valor shopping@fabrikam.com a la lista Remitentes bloqueados.

- Quite el valor chris@fourthcoffee.com de la lista Remitentes seguros y de la lista Destinatarios seguros.

- Se configuran contactos en la carpeta Contactos para que se traten como remitentes de confianza.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

En este ejemplo se quita el dominio contoso.com de la lista de remitentes bloqueados de todos los buzones de usuario de la organización.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
>
> - Si el usuario nunca ha abierto su buzón, es posible que reciba un error al ejecutar los comandos anteriores. Para suprimir este error para operaciones masivas, agregue `-ErrorAction SilentlyContinue` al **comando Set-MailboxJunkEmailConfiguration.**
>
> - Incluso si la regla de correo no deseado está deshabilitada en el buzón, puede configurar la colección de listas seguras y el filtro de correo no deseado de Outlook puede mover mensajes a la Bandeja de entrada o a la carpeta Correo no deseado. Para obtener más información, vea la [sección Acerca de](#about-junk-email-settings-in-outlook) la configuración del correo no deseado en Outlook en este artículo.
>
> - El filtro de correo no deseado de Outlook tiene una configuración de colección de listas seguras adicional (por ejemplo, Agregar automáticamente personas que envíe por correo electrónico **a la lista Remitentes seguros**). Para más información, vea [Usar los filtros de correo electrónico no deseado para controlar los mensajes que ve](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Realice uno de los siguientes procedimientos para confirmar que los límites de colección de listas seguras se han configurado correctamente en un buzón:

- Reemplace por el nombre, alias o dirección de correo electrónico del buzón _\<MailboxIdentity\>_ y ejecute el siguiente comando para comprobar los valores de propiedad:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Si la lista de valores es demasiado larga, use esta sintaxis:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Acerca de la configuración de correo no deseado en Outlook

Use la directiva de grupo para habilitar, deshabilitar y establecer las opciones de configuración de filtro de correo no deseado del cliente disponibles en Outlook. Para obtener más información, vea [Administrative Template files (ADMX/ADML) and Office Customization Tool for Microsoft 365 Apps for enterprise, Office 2019, and Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) and [How to deploy junk email settings, such as the Safe Senders list, by using Group Policy](https://support.microsoft.com/help/2252421).

Cuando el filtro de correo no deseado de  Outlook se establece en el valor predeterminado **No** hay filtrado automático en Opciones de opciones de correo no deseado hogar, Outlook no intenta clasificar los mensajes como correo no deseado, pero sigue utilizando la colección de listas \>  \>  \> seguras (lista remitentes seguros, lista de destinatarios seguros y remitentes bloqueados) para mover los mensajes a la carpeta correo no deseado después de la entrega. Para obtener más información acerca de esta configuración, vea [Overview of the Junk Email Filter](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

Cuando el filtro de correo no deseado de Outlook está establecido en **Bajo** o **Alto**, el filtro de correo no deseado de Outlook usará su propia tecnología de filtrado SmartScreen para identificar y mover el correo no deseado a la carpeta de correo no deseado. Esta clasificación de correo no deseado es independiente del nivel de confianza de correo no deseado (SCL) que determina EOP. De hecho, Outlook omite el SCL de EOP (a menos que EOP marque el mensaje para omitir el filtrado de correo no deseado) y usa sus propios criterios para determinar si el mensaje es correo no deseado. Por supuesto, es posible que el veredicto de correo no deseado de EOP y Outlook sea el mismo. Para obtener más información acerca de esta configuración, vea [Cambiar el nivel de protección en el filtro de correo no deseado](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b).

> [!NOTE]
> En noviembre de 2016, Microsoft dejó de producir actualizaciones de definición de correo no deseado para los filtros SmartScreen en Exchange y Outlook. Las definiciones de correo no deseado de SmartScreen existentes se dejaron en su lugar, pero es probable que su eficacia se degrade con el tiempo. Para obtener más información, consulte la [compatibilidad para SmartScreen en Outlook y Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).

Por lo tanto, el filtro de correo no deseado de Outlook puede usar la colección de listas seguras del buzón y su propia clasificación de correo no deseado para mover mensajes a la carpeta correo no deseado, incluso si la regla de correo no deseado está deshabilitada en el buzón.

Outlook y Outlook en la web admiten la colección de listas seguras. La colección de listas seguras se guarda en el buzón de Exchange Online, por lo que los cambios en la colección de listas seguras en Outlook aparecen en Outlook en la web y viceversa.

## <a name="limits-for-junk-email-settings"></a>Límites para la configuración de correo no deseado

La colección de listas seguras (lista remitentes seguros, lista de destinatarios seguros y lista de remitentes bloqueados) que se almacena en el buzón del usuario también se sincroniza con EOP. Con la sincronización de directorios, la colección de listas seguras se sincroniza con Azure AD.

- La colección de listas seguras en el buzón del usuario tiene un límite de 510 KB, que incluye todas las listas, además de la configuración de filtro de correo no deseado adicional. Si un usuario supera este límite, recibirá un error de Outlook similar al siguiente:

  > No se puede agregar a las listas de correo no deseado del servidor. Supera el tamaño permitido en el servidor. El filtro de correo electrónico no deseado del servidor se deshabilitará hasta que las listas de correo no deseado se reduzcan al tamaño permitido por el servidor.

  Para obtener más información acerca de este límite y cómo cambiarlo, vea [KB2669081](https://support.microsoft.com/help/2669081).

- La colección de listas seguras sincronizadas en EOP tiene los siguientes límites de sincronización:

  - 1024 entradas totales en la lista Remitentes seguros, la lista Destinatarios seguros y los contactos externos si el correo electrónico de confianza de **mis** contactos está habilitado.
  - 500 entradas totales en la lista Remitentes bloqueados y en la lista Dominios bloqueados.

  Cuando se alcanza el límite de entrada 1024, sucede lo siguiente:

  - La lista deja de aceptar entradas en PowerShell y Outlook en la web, pero no se muestra ningún error.

    Los usuarios de Outlook pueden seguir agregando más de 1024 entradas hasta que alcancen el límite de Outlook de 510 KB. Outlook puede usar estas entradas adicionales, siempre que un filtro de EOP no bloquee el mensaje antes de la entrega al buzón (reglas de flujo de correo, anti suplantación, etc.).

- Con la sincronización de directorios, las entradas se sincronizan con Azure AD en el siguiente orden:

  1. Mail contacts if **Trust email from my contacts** is enabled.
  2. La lista de remitentes seguros y la lista de destinatarios seguros se combinan, desduplican y ordenan alfabéticamente siempre que se realiza un cambio para las primeras 1024 entradas.

  Se usan las primeras 1024 entradas y la información relevante se marca en los encabezados del mensaje.

  Outlook procesa las entradas de más de 1024 que no se sincronizaron con Azure AD (no Outlook en la web) y no se marca ninguna información en los encabezados del mensaje.

Como puede ver, habilitar la configuración Confiar en el **correo** electrónico de mis contactos reduce el número de remitentes seguros y destinatarios seguros que se pueden sincronizar. Si esto es un problema, se recomienda usar la directiva de grupo para desactivar esta característica:

- Nombre de archivo: outlk16.opax
- Configuración de directiva: **confiar en el correo electrónico de los contactos**