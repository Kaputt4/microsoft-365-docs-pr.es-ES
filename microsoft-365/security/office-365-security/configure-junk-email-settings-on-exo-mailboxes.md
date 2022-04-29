---
title: Configurar las opciones del correo no deseado en buzones de Exchange Online
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a configurar los valores de correo no deseado en Exchange Online buzones. Muchos de estos valores están disponibles para los usuarios en Outlook o Outlook en la Web.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac7ac0f40c24c81cf916917b1b87626e032f8055
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "65130897"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Configurar las opciones del correo no deseado en buzones de Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En Microsoft 365 organizaciones con buzones en Exchange Online, la configuración de la organización contra correo no deseado se controla mediante Exchange Online Protection (EOP). Para obtener más información, consulte [Protección contra correo no deseado en EOP](anti-spam-protection.md).

Pero también hay configuraciones específicas de antispam que los administradores pueden configurar en buzones individuales en Exchange Online:

> [!NOTE]
> EOP ahora usa su propio agente de entrega de flujo de correo para enrutar mensajes a la carpeta Correo no deseado en lugar de usar la regla de correo electrónico no deseado. El parámetro _Enabled_ en el cmdlet **Set-MailboxJunkEmailConfiguration** ya no tiene ningún efecto en el flujo de correo. EOP enruta los mensajes en función de las acciones establecidas en las directivas contra correo no deseado. La lista de remitentes Caja fuerte del usuario y la lista de remitentes bloqueados seguirán funcionando como de costumbre.

- **Mover mensajes a la carpeta Correo no deseado en función de las directivas de correo no deseado**: cuando se configura una directiva antispam con la acción **Mover mensaje a la carpeta Correo electrónico no deseado** para un veredicto de filtrado de correo no deseado, el mensaje se mueve a la carpeta Correo no deseado después de que el mensaje se entregue al buzón. Para obtener más información sobre los veredictos de filtrado de correo no deseado en las directivas contra correo no deseado, consulte [Configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md). De forma similar, si la purga automática de cero horas (ZAP) determina que un mensaje entregado es spam o phish, el mensaje se mueve a la carpeta Correo electrónico no deseado para **mover el mensaje a la carpeta correo no deseado** filtrando acciones de veredicto. Para obtener más información sobre ZAP, vea [Purga automática de hora cero (ZAP) en Exchange Online](zero-hour-auto-purge.md).

- **Configuración de correo electrónico no deseado que los usuarios configuran por sí mismos en Outlook o Outlook en la Web**: la _colección de listas seguras_ es la lista de remitentes Caja fuerte, la lista de destinatarios Caja fuerte y la lista Remitentes bloqueados en cada buzón. Las entradas de estas listas determinan si el mensaje se mueve a la bandeja de entrada o a la carpeta Correo no deseado. Los usuarios pueden configurar la colección de listas seguras para su propio buzón en Outlook o Outlook en la Web (anteriormente conocida como Outlook Web App). Los administradores pueden configurar la colección de listas seguras en el buzón de cualquier usuario.

EOP puede mover mensajes a la carpeta Correo electrónico no deseado en función de la acción de filtrado de correo no deseado **Mover mensaje a la carpeta Correo no deseado** o a la lista Remitentes bloqueados en el buzón, e impedir que los mensajes se entreguen a la carpeta Correo electrónico no deseado (en función de la lista de remitentes Caja fuerte del buzón).

Los administradores pueden usar Exchange Online PowerShell para configurar entradas en la colección de listas seguras en buzones (la lista de remitentes Caja fuerte, la lista de destinatarios Caja fuerte y la lista Remitentes bloqueados).

> [!NOTE]
> Los mensajes de remitentes que los usuarios hayan agregado a sus propias listas de remitentes Caja fuerte omitirán el filtrado de contenido como parte de EOP (la SCL es -1). Para evitar que los usuarios agreguen entradas a su lista de remitentes de Caja fuerte en Outlook, use directiva de grupo como se mencionó en la sección Acerca de la [configuración del correo no deseado en Outlook](#about-junk-email-settings-in-outlook) sección más adelante en este artículo. El filtrado de directivas, el filtrado de contenido y las comprobaciones de Defender para Office 365 se seguirán aplicando a los mensajes.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Solo puede usar Exchange Online PowerShell para realizar los procedimientos de este artículo. Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Debe tener asignados permisos en Exchange Online para poder realizar los procedimientos de este artículo. En concreto, necesita el rol **Destinatarios de correo** (que se asigna a los grupos de roles Administración de la **organización**, **Administración de destinatarios** y **Destinatarios de correo personalizado** de forma predeterminada) o el rol Opciones de **usuario** (que se asigna a los grupos de roles **Administración de la organización** y Departamento de **soporte técnico** de forma predeterminada). Para agregar usuarios a grupos de roles en Exchange Online, consulte [Modificar grupos de roles en Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups). Tenga en cuenta que los usuarios con permisos predeterminados pueden realizar estos mismos procedimientos en su propio buzón, siempre y cuando tengan [acceso a Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell).

- En los entornos híbridos en los que EOP protege los buzones de correo de Exchange local, es necesario configurar las reglas de flujo de correo (también conocidas como reglas de transporte) en Exchange local. Estas reglas de flujos de correo traducen el veredicto de filtrado de correo no deseado de EOP para que la regla de correo no deseado pueda mover el mensaje a la carpeta de correo no deseado. Para más detalles, consulte [Configurar EOP para enviar correo no deseado a la carpeta de Correo no deseado en entornos híbridos](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).

- Caja fuerte remitentes de buzones compartidos no se sincronizan con Azure AD y EOP por diseño.

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Usar Exchange Online PowerShell para configurar la colección safelist en un buzón

La colección de listas seguras de un buzón engloba la lista de remitentes seguros, la lista de destinatarios seguros y la lista de remitentes bloqueados. De forma predeterminada, los usuarios pueden configurar la colección safelist en su propio buzón en Outlook o Outlook en la Web. Los administradores pueden usar los parámetros correspondientes del cmdlet **Set-MailboxJunkEmailConfiguration** para configurar la colección de listas seguras del buzón de un usuario. Estos parámetros se describen en la siguiente tabla.

|Parámetro en Set-MailboxJunkEmailConfiguration|configuración de Outlook en la Web|
|---|---|
|_BlockedSendersAndDomains_|**Mover el correo electrónico de estos remitentes o dominios a la carpeta de correo electrónico no deseado**|
|_ContactsTrusted_|**Confiar en correo electrónico de mis contactos**|
|_TrustedListsOnly_|**Solo confiar en el correo electrónico de las direcciones de mi lista de remitentes y dominios de Caja fuerte y Caja fuerte listas de correo**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**No mueva el correo electrónico de estos remitentes a mi carpeta correo no deseado**|

<sup>\*</sup>**Notas**:

- En Exchange Online, **las entradas de dominio** de la lista de remitentes de Caja fuerte o el parámetro _TrustedSendersAndDomains_ no se reconocen, por lo que solo se usan direcciones de correo electrónico. En EOP independiente con sincronización de directorios, las entradas de dominio no se sincronizan de forma predeterminada, pero puede habilitar la sincronización para dominios. Para obtener más información, vea [KB3019657](https://support.microsoft.com/help/3019657).
- No se puede modificar directamente la lista de destinatarios de Caja fuerte mediante el cmdlet **Set-MailboxJunkEmailConfiguration** (el parámetro _TrustedRecipientsAndDomains_ no funciona). En su lugar, hay que modificar la lista de remitentes seguros y esos cambios se sincronizan con la lista de destinatarios seguros.

Use la siguiente sintaxis para configurar la colección de listas seguras de un buzón:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Para escribir varios valores y sobrescribir las entradas existentes para los _parámetros BlockedSendersAndDomains_ y _TrustedSendersAndDomains_ , use la sintaxis siguiente: `"<Value1>","<Value2>"...`. Para agregar o quitar uno o varios valores sin afectar a otras entradas existentes, use la sintaxis siguiente: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

En este ejemplo se establecen las siguientes configuraciones de la colección de listas seguras en el buzón de Ori Epstein:

- Agregue el valor shopping@fabrikam.com a la lista Remitentes bloqueados.
- Quite el valor chris@fourthcoffee.com de la lista remitentes de Caja fuerte y la lista destinatarios de Caja fuerte.
- Se configuran contactos en la carpeta Contactos para que se traten como remitentes de confianza.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

En este ejemplo se quita el dominio contoso.com de la lista de remitentes bloqueados de todos los buzones de usuario de la organización.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
>
> - Si el usuario nunca ha abierto su buzón de correo, es posible que reciba un error al ejecutar los comandos anteriores. Para suprimir este error para operaciones masivas, agregue `-ErrorAction SilentlyContinue` al comando **Set-MailboxJunkEmailConfiguration** .
> - El filtro de correo electrónico no deseado Outlook tiene una configuración adicional de recopilación de listas seguras (por ejemplo, **agregar automáticamente las personas que envié por correo electrónico a la lista de remitentes de Caja fuerte**). Para más información, vea [Usar los filtros de correo electrónico no deseado para controlar los mensajes que ve](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Realice uno de los siguientes procedimientos para confirmar que los límites de colección de listas seguras se han configurado correctamente en un buzón:

- Reemplace por _\<MailboxIdentity\>_ el nombre, el alias o la dirección de correo electrónico del buzón de correo y ejecute el siguiente comando para comprobar los valores de propiedad:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Si la lista de valores es demasiado larga, use esta sintaxis:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Acerca de la configuración de correo no deseado en Outlook

Use la directiva de grupo para habilitar, deshabilitar y establecer las opciones de configuración de filtro de correo no deseado del cliente disponibles en Outlook. Para obtener más información, vea [Archivos de plantilla administrativa (ADMX/ADML) y Office Herramienta de personalización para Aplicaciones Microsoft 365 para empresas, Office 2019 y Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) y [Cómo implementar la configuración de correo no deseado, como la lista de remitentes de Caja fuerte, mediante el uso de directiva de grupo](https://support.microsoft.com/help/2252421).

Cuando el filtro de correo no deseado de Outlook se establece en el valor predeterminado **Sin filtrado automático** en **Opciones**\> de **correo no deseado**  \> de **inicio**\>, Outlook no intenta clasificar los mensajes como correo no deseado, pero sigue usando la colección de listas seguras (la lista de remitentes Caja fuerte, Caja fuerte  Lista de destinatarios y lista de remitentes bloqueados) para mover mensajes a la carpeta Correo no deseado después de la entrega. Para obtener más información sobre esta configuración, vea [Información general sobre el filtro de correo no deseado](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

> [!NOTE]
> En Microsoft 365 organizaciones, se recomienda dejar el filtro de correo no deseado en Outlook establecido en **Sin filtrado automático** para evitar conflictos innecesarios (positivos y negativos) con los veredictos de filtrado de correo no deseado de EOP.

Cuando el filtro de correo no deseado de Outlook está establecido en **Bajo** o **Alto**, el filtro de correo no deseado de Outlook usará su propia tecnología de filtrado SmartScreen para identificar y mover el correo no deseado a la carpeta de correo no deseado. Esta clasificación de correo no deseado es independiente del nivel de confianza de correo no deseado (SCL) que determina EOP. De hecho, Outlook omite el SCL de EOP (a menos que EOP marcase el mensaje para omitir el filtrado de correo no deseado) y usa sus propios criterios para determinar si el mensaje es correo no deseado. Por supuesto, es posible que el veredicto de correo no deseado de EOP y Outlook sea el mismo. Para obtener más información sobre esta configuración, vea [Cambiar el nivel de protección en el Filtro de correo electrónico no deseado](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b).

> [!NOTE]
> En noviembre de 2016, Microsoft dejó de producir actualizaciones de definición de correo no deseado para los filtros SmartScreen en Exchange y Outlook. Las definiciones de correo no deseado de SmartScreen existentes se dejaron en su lugar, pero su eficacia probablemente se degradará con el tiempo. Para obtener más información, consulte la [compatibilidad para SmartScreen en Outlook y Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).

Por lo tanto, el Outlook filtro de correo no deseado puede usar la colección de listas seguras del buzón y su propia clasificación de correo no deseado para mover los mensajes a la carpeta Correo no deseado.

Outlook y Outlook en la web admiten la colección de listas seguras. La colección safelist se guarda en el buzón de Exchange Online, por lo que los cambios en la colección safelist de Outlook aparecen en Outlook en la Web y viceversa.

## <a name="limits-for-junk-email-settings"></a>Límites de la configuración del correo no deseado

La colección safelist (la lista de remitentes de Caja fuerte, Caja fuerte lista destinatarios y la lista de remitentes bloqueados) que se almacena en el buzón del usuario también se sincroniza con EOP. Con la sincronización de directorios, la colección safelist se sincroniza con Azure AD.

- La colección de listas seguras en el buzón del usuario tiene un límite de 510 KB, que incluye todas las listas, además de una configuración adicional de filtro de correo no deseado. Si un usuario supera este límite, recibirá un error Outlook similar al siguiente:

  > No se puede o no se puede agregar a las listas de correo electrónico no deseado del servidor. Está por encima del tamaño permitido en el servidor. El filtro correo electrónico no deseado del servidor se deshabilitará hasta que las listas de correo no deseado se hayan reducido al tamaño permitido por el servidor.

  Para obtener más información sobre este límite y cómo cambiarlo, consulte [KB2669081](https://support.microsoft.com/help/2669081).

- La colección de listas seguras sincronizadas en EOP tiene los siguientes límites de sincronización:
  - 1024 entradas totales en la lista de remitentes de Caja fuerte, la lista de destinatarios Caja fuerte y contactos externos si el **correo electrónico de confianza de mis contactos** está habilitado.
  - 500 entradas totales en la lista Remitentes bloqueados y en la lista Dominios bloqueados.

  Cuando se alcanza el límite de entrada 1024, sucede lo siguiente:

  - La lista deja de aceptar entradas en PowerShell y Outlook en la Web, pero no se muestra ningún error.

    Outlook los usuarios pueden seguir agregando más de 1024 entradas hasta que alcancen el límite de Outlook de 510 KB. Outlook puede usar estas entradas adicionales, siempre y cuando un filtro EOP no bloquee el mensaje antes de la entrega al buzón (reglas de flujo de correo, anti-suplantación, etc.).

- Con la sincronización de directorios, las entradas se sincronizan con Azure AD en el orden siguiente:
  1. Contactos de correo si **el correo electrónico de confianza de mis contactos** está habilitado.
  2. La lista de remitentes Caja fuerte y Caja fuerte lista de destinatarios se combinan, desduplican y ordenan alfabéticamente cada vez que se realiza un cambio para las primeras 1024 entradas.

  Se usan las primeras 1024 entradas y se marca la información pertinente en los encabezados del mensaje.

  Las entradas de más de 1024 que no se sincronizaron con Azure AD se procesan mediante Outlook (no Outlook en la Web) y no se marca ninguna información en los encabezados del mensaje.

Como puede ver, al habilitar la opción **Confiar en el correo electrónico de mis contactos** se reduce el número de remitentes de Caja fuerte y Caja fuerte destinatarios que se pueden sincronizar. Si esto es un problema, se recomienda usar directiva de grupo para desactivar esta característica:

- Nombre de archivo: outlk16.opax
- Configuración de directiva: **Confiar en el correo electrónico de los contactos**
