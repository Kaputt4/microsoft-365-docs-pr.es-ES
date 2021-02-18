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
description: Los administradores pueden aprender a configurar las opciones de correo no deseado en los buzones de Exchange Online. Muchas de estas opciones de configuración están disponibles para los usuarios en Outlook o Outlook en la Web.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 31f247ec74f1780d05aaeb79753abd0075401d9a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290122"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Configurar la configuración del correo no deseado en buzones de Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

En las organizaciones de Microsoft 365 con buzones en Exchange Online, la configuración contra correo no deseado de la organización se controla mediante Exchange Online Protection (EOP). Para obtener más información, vea [Protección contra correo no deseado en EOP.](anti-spam-protection.md)

Pero también hay opciones específicas contra correo no deseado que los administradores pueden configurar en buzones individuales en Exchange Online:

- **Habilitar o deshabilitar la** regla de correo no deseado: la regla de correo no deseado es una regla de bandeja de entrada oculta denominada Regla de correo electrónico no deseado que está habilitada de forma predeterminada en todos los buzones. La regla de correo no deseado controla las siguientes características:

  - Mover mensajes a la carpeta correo no deseado en función de las directivas  contra correo no **deseado:** cuando se configura una directiva contra correo no deseado con la acción Mover mensaje a la carpeta Correo no deseado para un veredicto de filtrado de correo no deseado, la regla de filtro de correo no deseado mueve el mensaje a la carpeta Correo no deseado después de entregar el mensaje al buzón. Para obtener más información acerca de los veredictos de filtrado de correo no deseado en las directivas contra correo no deseado, vea Configurar directivas contra correo no deseado [en EOP.](configure-your-spam-filter-policies.md) De forma similar, si la purga automática (ZAP) de cero horas determina que un mensaje entregado es  correo no deseado o phishing, la regla de filtro de correo no deseado mueve el mensaje a la carpeta correo no deseado para mover el mensaje a la carpeta correo no deseado acciones de veredicto de filtrado de correo no deseado. Para obtener más información acerca de ZAP, consulte Purga automática de cero horas [(ZAP) en Exchange Online.](zero-hour-auto-purge.md)

  - Configuración de correo no deseado que los usuarios configuran  por sí mismos en Outlook o **Outlook en la Web:** la colección de listas seguras es la lista de remitentes seguros, la lista de destinatarios seguros y la lista de remitentes bloqueados en cada buzón. Las entradas de estas listas determinan si la regla de correo no deseado mueve el mensaje a la bandeja de entrada o a la carpeta correo no deseado. Los usuarios pueden configurar la colección de listas seguras para su propio buzón en Outlook o Outlook en la Web (anteriormente conocido como Outlook Web App). Los administradores pueden configurar la colección de listas seguras en el buzón de cualquier usuario.

Cuando la regla de correo no deseado está habilitada en el buzón, EOP puede mover  mensajes a la carpeta de correo no deseado en función de la acción de veredicto de filtrado de correo no deseado Mover mensaje a la carpeta de correo no deseado o la lista de remitentes bloqueados del buzón, e impedir que los mensajes se entreguen a la carpeta correo no deseado (según la lista de remitentes seguros del buzón).

 Cuando la regla de correo no deseado está deshabilitada en el buzón, EOP no  puede mover mensajes a la carpeta de correo no deseado en función de la acción de veredicto de filtrado de correo no deseado Mover mensaje a la carpeta De correo no deseado o la colección de listas seguras del buzón.

Los administradores pueden usar Exchange Online PowerShell para deshabilitar, habilitar y ver el estado de la regla de correo no deseado en los buzones. Los administradores también pueden usar Exchange Online PowerShell para configurar las entradas de la colección de listas seguras en los buzones (la lista de remitentes seguros, la lista de destinatarios seguros y la lista de remitentes bloqueados).

> [!NOTE]
> Los mensajes de remitentes que los usuarios han agregado a sus propias listas de remitentes seguros omitirán el filtrado de conexiones como parte de EOP (el SCL es -1). Para evitar que los usuarios agreguen entradas a su lista de remitentes seguros en Outlook, use la directiva de grupo como se mencionó en la sección Acerca de la configuración de correo no deseado en  [Outlook](#about-junk-email-settings-in-outlook) más adelante en este artículo. El filtrado de directivas, el filtrado de contenido y las comprobaciones de Defender para Office 365 se seguirán aplicando a los mensajes.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Solo puede usar Exchange Online PowerShell para realizar los procedimientos descritos en este artículo. Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Deberá tener asignados permisos en Exchange Online antes de poder realizar los procedimientos descritos en este artículo. Específicamente, necesita  la función Destinatarios de correo (que se asigna a los grupos de roles Administración  de la **organización,** Administración  de  destinatarios y Destinatarios de correo **personalizados** de forma predeterminada) o la función Opciones de usuario (que se asigna a los grupos de roles Administración de la organización y Servicio de ayuda de forma predeterminada).  Para agregar usuarios a grupos de roles en Exchange Online, consulte [Modificar grupos de roles en Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) Tenga en cuenta que los usuarios con permisos predeterminados pueden realizar estos mismos procedimientos en su propio buzón, siempre y cuando tengan acceso a [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell).

- En entornos de EOP independientes en los que EOP protege los buzones de Exchange locales, tiene que configurar las reglas de flujo de correo (también conocidas como reglas de transporte) en Exchange local para traducir el veredicto de filtro de correo no deseado de EOP para que la regla de correo no deseado pueda mover el mensaje a la carpeta de correo electrónico no deseado. Para obtener información, consulte [Configuración de un EOP independiente para entregar el correo no deseado en la carpeta de correo no deseado en entornos híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- Los remitentes seguros para buzones compartidos no se sincronizan con Azure AD y EOP por diseño.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Usar Exchange Online PowerShell para habilitar o deshabilitar la regla de correo no deseado en un buzón

> [!NOTE]
> El cmdlet **Set-MailboxJunkEmailConfiguration** solo se puede usar para deshabilitar la regla de correo no deseado en un buzón que se ha abierto en Outlook (en modo caché de Exchange) o en Outlook en la web. Si el buzón no se ha abierto, recibirá el error: Si desea suprimir este error para operaciones masivas, puede agregarlo al comando `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration.**

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

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
>
> - Si el usuario nunca ha abierto su buzón, es posible que reciba un error al ejecutar el comando anterior. Para suprimir este error en operaciones masivas, agregue `-ErrorAction SilentlyContinue` al **comando Set-MailboxJunkEmailConfiguration.**
>
> - Incluso si deshabilita la regla de correo no deseado, el filtro de correo no deseado de Outlook (según cómo esté configurado) también puede determinar si un mensaje es correo no deseado y puede mover mensajes a la carpeta Bandeja de entrada o correo no deseado según su propio veredicto de correo no deseado y la colección de listas seguras del buzón. Para obtener más información, vea la sección Acerca [de la configuración de correo no deseado en Outlook](#about-junk-email-settings-in-outlook) en este artículo.

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Realice uno de los siguientes procedimientos para confirmar que la regla de correo no deseado se ha habilitado o deshabilitado correctamente en un buzón:

- Reemplace por el nombre, alias o dirección de correo electrónico del buzón y ejecute el siguiente comando _\<MailboxIdentity\>_ para comprobar el valor de la propiedad **Enabled:**

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Usar Exchange Online PowerShell para configurar la colección de listas seguras en un buzón

La colección de listas seguras de un buzón engloba la lista de remitentes seguros, la lista de destinatarios seguros y la lista de remitentes bloqueados. De forma predeterminada, los usuarios pueden configurar la colección de listas seguras en su propio buzón en Outlook o Outlook en la Web. Los administradores pueden usar los parámetros correspondientes del cmdlet **Set-MailboxJunkEmailConfiguration** para configurar la colección de listas seguras del buzón de un usuario. Estos parámetros se describen en la siguiente tabla.

****

|Parámetro en Set-MailboxJunkEmailConfiguration|Configuración de Outlook en la Web|
|---|---|
|_BlockedSendersAndDomains_|**Mover el correo electrónico de estos remitentes o dominios a la carpeta de correo electrónico no deseado**|
|_ContactsTrusted_|**Confiar en correo electrónico de mis contactos**|
|_TrustedListsOnly_|**Solo confiar en el correo electrónico de las direcciones de mis listas de dominios y remitentes seguros y listas de correo seguro**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**No mover el correo electrónico de estos remitentes a mi carpeta de correo no deseado**|
|

<sup>\*</sup>**Notas:**

- En Exchange Online, las entradas **de** dominio de la lista de remitentes seguros o del parámetro _TrustedSendersAndDomains_ no se reconocen, por lo que solo se usan direcciones de correo electrónico. En EOP independiente con sincronización de directorios, las entradas de dominio no se sincronizan de forma predeterminada, pero puede habilitar la sincronización para dominios. Para obtener más información, [vea KB3019657](https://support.microsoft.com/help/3019657).

- No puede modificar directamente la lista de destinatarios seguros mediante el cmdlet **Set-MailboxJunkEmailConfiguration** (el parámetro _TrustedRecipientsAndDomains_ no funciona). En su lugar, hay que modificar la lista de remitentes seguros y esos cambios se sincronizan con la lista de destinatarios seguros.

Use la siguiente sintaxis para configurar la colección de listas seguras de un buzón:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Para escribir varios valores y sobrescribir las entradas existentes para los parámetros _BlockedSendersAndDomains_ y _TrustedSendersAndDomains,_ use la siguiente sintaxis: `"<Value1>","<Value2>"...` . Para agregar o quitar uno o varios valores sin que ello afecte a otras entradas existentes, use la siguiente sintaxis: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

En este ejemplo se establecen las siguientes configuraciones de la colección de listas seguras en el buzón de Ori Epstein:

- Agregue el valor shopping@fabrikam.com a la lista de remitentes bloqueados.

- Quite el valor chris@fourthcoffee.com de la lista de remitentes seguros y la lista de destinatarios seguros.

- Se configuran contactos en la carpeta Contactos para que se traten como remitentes de confianza.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

En este ejemplo se quita el dominio contoso.com de la lista de remitentes bloqueados de todos los buzones de usuario de la organización.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
>
> - Si el usuario nunca ha abierto su buzón, es posible que reciba un error al ejecutar los comandos anteriores. Para suprimir este error en operaciones masivas, agregue `-ErrorAction SilentlyContinue` al **comando Set-MailboxJunkEmailConfiguration.**
>
> - Incluso si la regla de correo no deseado está deshabilitada en el buzón, aún puede configurar la colección de listas seguras y el filtro de correo no deseado de Outlook puede mover mensajes a la bandeja de entrada o a la carpeta correo no deseado. Para obtener más información, vea la sección Acerca [de la configuración de correo no deseado en Outlook](#about-junk-email-settings-in-outlook) en este artículo.
>
> - El filtro de correo no deseado de Outlook tiene configuraciones de recopilación de listas seguras adicionales (por ejemplo, agregar automáticamente personas a la lista **de remitentes seguros).** Para más información, vea [Usar los filtros de correo electrónico no deseado para controlar los mensajes que ve](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Realice uno de los siguientes procedimientos para confirmar que los límites de colección de listas seguras se han configurado correctamente en un buzón:

- Reemplace por el nombre, el alias o la dirección de correo electrónico del buzón y ejecute _\<MailboxIdentity\>_ el siguiente comando para comprobar los valores de propiedad:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Si la lista de valores es demasiado larga, use esta sintaxis:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Acerca de la configuración de correo no deseado en Outlook

Use la directiva de grupo para habilitar, deshabilitar y establecer las opciones de configuración de filtro de correo no deseado del cliente disponibles en Outlook. Para obtener más información, vea archivos de plantilla administrativa (ADMX/ADML) y la Herramienta de personalización de Office para Aplicaciones de [Microsoft 365 para empresas, Office 2019 y Office 2016,](https://www.microsoft.com/download/details.aspx?id=49030) y cómo implementar la configuración de correo no deseado, como la lista de [remitentes seguros,](https://support.microsoft.com/help/2252421)mediante la directiva de grupo.

Cuando el filtro de correo no deseado de  Outlook se establece en el valor predeterminado **No** hay filtrado automático en opciones de correo electrónico no deseado en el hogar, Outlook no intenta clasificar los mensajes como correo no deseado, pero sigue utilizando la colección de listas seguras (la lista de remitentes seguros, la lista de destinatarios seguros y la lista de \>  \>  \> remitentes bloqueados) para mover los mensajes a la carpeta de correo no deseado después de la entrega. Para obtener más información acerca de esta configuración, vea [Información general sobre el filtro de correo no deseado.](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)

Cuando el filtro de correo no deseado de Outlook está establecido en **Bajo** o **Alto**, el filtro de correo no deseado de Outlook usará su propia tecnología de filtrado SmartScreen para identificar y mover el correo no deseado a la carpeta de correo no deseado. Esta clasificación de correo no deseado es independiente del nivel de confianza contra correo no deseado (SCL) que determina EOP. De hecho, Outlook omite el SCL de EOP (a menos que EOP marque el mensaje para omitir el filtrado de correo no deseado) y usa sus propios criterios para determinar si el mensaje es correo no deseado. Por supuesto, es posible que el veredicto de correo no deseado de EOP y Outlook sea el mismo. Para obtener más información acerca de esta configuración, vea [Cambiar el nivel de protección en el filtro de correo no deseado.](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)

> [!NOTE]
> En noviembre de 2016, Microsoft dejó de producir actualizaciones de definición de correo no deseado para los filtros smartScreen en Exchange y Outlook. Las definiciones de correo no deseado de SmartScreen existentes se dejaron en su lugar, pero es probable que su eficacia se degrade con el tiempo. Para obtener más información, consulte la [compatibilidad para SmartScreen en Outlook y Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).

Por lo tanto, el filtro de correo no deseado de Outlook puede usar la colección de listas seguras del buzón y su propia clasificación de correo no deseado para mover mensajes a la carpeta correo no deseado, incluso si la regla de correo no deseado está deshabilitada en el buzón.

Outlook y Outlook en la web admiten la colección de listas seguras. La colección de listas seguras se guarda en el buzón de Exchange Online, por lo que los cambios en la colección de listas seguras de Outlook aparecen en Outlook en la Web y viceversa.

## <a name="limits-for-junk-email-settings"></a>Límites para la configuración de correo no deseado

La colección de listas seguras (la lista de remitentes seguros, la lista de destinatarios seguros y la lista de remitentes bloqueados) que se almacena en el buzón del usuario también se sincroniza con EOP. Con la sincronización de directorios, la colección de listas seguras se sincroniza con Azure AD.

- La colección de listas seguras del buzón del usuario tiene un límite de 510 KB, que incluye todas las listas, además de la configuración adicional del filtro de correo no deseado. Si un usuario supera este límite, recibirá un error de Outlook similar al siguiente:

  > No se puede agregar al servidor listas de correo electrónico no deseado. Supera el tamaño permitido en el servidor. El filtro de correo electrónico no deseado del servidor se deshabilitará hasta que las listas de correo electrónico no deseado se hayan reducido al tamaño permitido por el servidor.

  Para obtener más información acerca de este límite y cómo cambiarlo, vea [KB2669081](https://support.microsoft.com/help/2669081).

- La colección de listas seguras sincronizadas en EOP tiene los siguientes límites de sincronización:

  - 1024 entradas totales en la lista de remitentes seguros, la lista de destinatarios seguros y los contactos externos si el correo electrónico de confianza de mis contactos **está** habilitado.
  - 500 entradas totales en la lista de remitentes bloqueados y en la lista dominios bloqueados.

  Cuando se alcanza el límite de entrada 1024, sucede lo siguiente:

  - La lista deja de aceptar entradas en PowerShell y Outlook en la Web, pero no se muestra ningún error.

    Los usuarios de Outlook pueden seguir agregando más de 1024 entradas hasta que alcancen el límite de Outlook de 510 KB. Outlook puede usar estas entradas adicionales, siempre y cuando un filtro de EOP no bloquee el mensaje antes de entregarlo al buzón (reglas de flujo de correo, anti-spoofing, etc.).

- Con la sincronización de directorios, las entradas se sincronizan con Azure AD en el siguiente orden:

  1. Contactos de correo si **el correo electrónico de confianza de mis contactos** está habilitado.
  2. La lista de remitentes seguros y la lista de destinatarios seguros se combinan, desduplican y ordenan alfabéticamente siempre que se realiza un cambio para las primeras 1024 entradas.

  Se usan las primeras 1024 entradas y se marca la información relevante en los encabezados del mensaje.

  Outlook procesa las entradas de más de 1024 que no se sincronizaron con Azure AD (no outlook en la web) y no se marca información en los encabezados del mensaje.

Como puede ver,  la habilitación de la opción Confiar correo electrónico desde mis contactos reduce el número de remitentes seguros y destinatarios seguros que se pueden sincronizar. Si esto es un problema, te recomendamos usar la directiva de grupo para desactivar esta característica:

- Nombre de archivo: outlk16.opax
- Configuración de directiva: **confiar en el correo electrónico de los contactos**
