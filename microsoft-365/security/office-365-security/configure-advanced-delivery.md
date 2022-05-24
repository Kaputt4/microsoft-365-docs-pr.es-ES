---
title: Configurar la entrega de simulaciones de suplantación de identidad de terceros a usuarios y mensajes sin filtrar a buzones de SecOps
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
ms.custom: ''
description: Los administradores pueden aprender a usar la directiva de entrega avanzada en Exchange Online Protection (EOP) para identificar los mensajes que no se deben filtrar en escenarios admitidos específicos (simulaciones de suplantación de identidad de terceros y mensajes entregados a buzones de operaciones de seguridad (SecOps).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d9a959e70408af80567d1daed140e0642870b975
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2022
ms.locfileid: "65647807"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>Configurar la entrega de simulaciones de suplantación de identidad de terceros a usuarios y mensajes sin filtrar a buzones de SecOps

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Para mantener su organización [segura de forma predeterminada](secure-by-default.md), Exchange Online Protection (EOP) no permite listas seguras ni omisión de filtrado para los mensajes que se identifican como malware o suplantación de identidad de alta confianza. Sin embargo, hay escenarios específicos que requieren la entrega de mensajes sin filtrar. Por ejemplo:

- **Simulaciones de suplantación de identidad de terceros**: los ataques simulados pueden ayudarle a identificar usuarios vulnerables antes de que un ataque real afecte a su organización.
- **Buzones de operaciones de seguridad (SecOps**): buzones dedicados que usan los equipos de seguridad para recopilar y analizar mensajes sin filtrar (buenos y malos).

La directiva de _entrega avanzada_ se usa en Microsoft 365 para evitar que se filtren los mensajes _entrantes en estos escenarios específicos_.<sup>\*</sup> La directiva de entrega avanzada garantiza que los mensajes de estos escenarios alcancen los siguientes resultados:

- Los filtros de EOP y Microsoft Defender para Office 365 no realizan ninguna acción en estos mensajes.<sup>\*</sup>
- [La purga de cero horas (ZAP)](zero-hour-auto-purge.md) para el correo no deseado y la suplantación de identidad no realizan ninguna acción en estos mensajes.<sup>\*\*</sup>
- [Las alertas predeterminadas del sistema](/microsoft-365/compliance/alert-policies#default-alert-policies) no se desencadenan para estos escenarios.
- [AIR y los clústeres de Defender para Office 365](office-365-air.md) omiten estos mensajes.
- Específicamente para simulaciones de suplantación de identidad de terceros:
  - [Administración envíos](admin-submission.md) genera una respuesta automática que indica que el mensaje forma parte de una campaña de simulación de suplantación de identidad (phishing) y no es una amenaza real. Las alertas y AIR no se desencadenarán. La experiencia de envíos de administradores mostrará estos mensajes como una amenaza simulada.
  - Cuando un usuario informa de un mensaje de simulación de suplantación de identidad mediante el mensaje de informe [o los complementos de suplantación de identidad](enable-the-report-message-add-in.md) de informe, el sistema no generará una alerta, una investigación o un incidente. Los vínculos o archivos no se detonarán, pero el mensaje también se mostrará en la pestaña **Mensajes notificados** por el usuario de la página **Envíos** .
  - [Caja fuerte Vínculos en Defender para Office 365](safe-links.md) no bloquea ni detona las direcciones URL específicamente identificadas en estos mensajes al hacer clic. Las direcciones URL siguen encapsuladas, pero no se bloquean.
  - [Caja fuerte Datos adjuntos en Defender para Office 365](safe-attachments.md) no detona los datos adjuntos en estos mensajes.

<sup>\*</sup> No se puede omitir el filtrado de malware.

<sup>\*\*</sup> Puede omitir ZAP para malware mediante la creación de una directiva antimalware para el buzón de SecOps donde zap para malware está desactivado. Para obtener instrucciones, consulte [Configuración de directivas antimalware en EOP](configure-anti-malware-policies.md).

Los mensajes identificados por la directiva de entrega avanzada no son amenazas de seguridad, por lo que los mensajes se marcan con invalidaciones del sistema. Administración experiencias mostrarán estos mensajes como debido a una invalidación del sistema de **simulación de suplantación de identidad (phishing)** o a una invalidación del sistema de **buzones de SecOps**. Los administradores pueden filtrar y analizar estas invalidaciones del sistema en las siguientes experiencias:

- [Explorador de amenazas/Detecciones en tiempo real en Defender para Office 365 plan 2](threat-explorer.md): Administración puede filtrar por **el origen de invalidación del sistema** y seleccionar **simulación de suplantación de identidad** o **Buzón de SecOps**.
- La [página Entidad de correo electrónico del Explorador de amenazas/Detecciones en tiempo real](mdo-email-entity-page.md): Administración puede ver un mensaje permitido por la directiva de la organización mediante **el buzón de SecOps** o **la simulación de suplantación de identidad** en **Invalidación de inquilinos** en la sección **Invalidaciones**.
- El [informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report): Administración puede filtrar por **ver los datos por invalidación del sistema** en el menú desplegable y seleccionar para ver los mensajes permitidos debido a una invalidación del sistema de simulación de suplantación de identidad (phishing). Para ver los mensajes permitidos por la invalidación del buzón de SecOps, puede seleccionar **desglose del gráfico por ubicación de entrega** en el menú desplegable **desglose del gráfico por motivo** .
- [Búsqueda avanzada en Microsoft Defender para punto de conexión](../defender-endpoint/advanced-hunting-overview.md): la simulación de suplantación de identidad y las invalidaciones del sistema de buzones de SecOps se mostrarán como opciones dentro de OrgLevelPolicy en EmailEvents.
- [Vistas de campaña](campaigns.md): Administración puede filtrar por **el origen de invalidación del sistema** y seleccionar **simulación de suplantación de identidad (Phishing)** o **Buzón de SecOps**.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Entrega avanzada** , abra <https://security.microsoft.com/advanceddelivery>.

- Para conectarse a PowerShell del Centro de seguridad y cumplimiento, vea [Conectarse a PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell).

- Debe tener asignados permisos para poder realizar los procedimientos de este artículo:
  - Para crear, modificar o quitar la configuración configurada en la directiva de entrega avanzada, debe ser miembro del grupo de roles **Administrador de seguridad** en el **portal de Microsoft 365 Defender** y miembro del grupo de roles Administración de la **organización** en **Exchange Online**.
  - Para el acceso de solo lectura a la directiva de entrega avanzada, debe ser miembro de los grupos de roles **Lector global** o **Lector de seguridad** .

  Para obtener más información, vea [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md) y [Permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  > Agregar usuarios al rol de Azure Active Directory correspondiente proporciona a los usuarios los permisos necesarios en el portal de Microsoft 365 Defender _y_ permisos para otras características de Microsoft 365. Para más información, consulte[Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Uso del portal de Microsoft 365 Defender para configurar buzones de SecOps en la directiva de entrega avanzada

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Correo electrónico &** Directivas de colaboración \> **& Directivas de amenazas**  \> de reglas \> **Entrega avanzada** en la sección **Reglas**. Para ir directamente a la página **Entrega avanzada** , use <https://security.microsoft.com/advanceddelivery>.

2. En la página **Entrega avanzada** , compruebe que la pestaña **Buzón de SecOps** está seleccionada y, a continuación, realice uno de los pasos siguientes:
   - Haga clic en ![el icono Editar.](../../media/m365-cc-sc-edit-icon.png) **Edición**.
   - Si no hay simulaciones de suplantación de identidad configuradas, haga clic en **Agregar**.

3. En el control flotante **Editar buzones de SecOps** que se abre, escriba un buzón de Exchange Online existente que quiera designar como buzón de SecOps mediante uno de los pasos siguientes:
   - Haga clic en el cuadro , deje que la lista de buzones se resuelva y, a continuación, seleccione el buzón.
   - Haga clic en el cuadro para empezar a escribir un identificador para el buzón (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de cuenta, etc.) y seleccione el buzón (nombre para mostrar) de los resultados.

     Repita este paso tantas veces como sea necesario. No se permiten grupos de distribución.

     Para quitar un valor existente, haga clic en Quitar ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

4. Cuando haya terminado, haga clic en **Guardar**.

Las entradas de buzón de SecOps que configuró se muestran en la pestaña **buzón de SecOps** . Para realizar cambios, haga clic en ![el icono Editar.](../../media/m365-cc-sc-edit-icon.png) **Edite** en la pestaña .

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Uso del portal de Microsoft 365 Defender para configurar simulaciones de suplantación de identidad de terceros en la directiva de entrega avanzada

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Correo electrónico &** Directivas de colaboración \> **& Directivas de amenazas**  \> de reglas \> **Entrega avanzada** en la sección **Reglas**. Para ir directamente a la página **Entrega avanzada** , use <https://security.microsoft.com/advanceddelivery>.

2. En la página **Entrega avanzada** , seleccione la pestaña **Simulación de suplantación de identidad** y, a continuación, realice uno de los pasos siguientes:
   - Haga clic en ![el icono Editar.](../../media/m365-cc-sc-edit-icon.png) **Edición**.
   - Si no hay simulaciones de suplantación de identidad configuradas, haga clic en **Agregar**.

3. En el control flotante **Editar simulación de suplantación de identidad de terceros** que se abre, configure los siguientes valores:

   - **Dominio**: expanda esta configuración y escriba al menos un dominio de dirección de correo electrónico (por ejemplo, contoso.com) haciendo clic en el cuadro, escribiendo un valor y, a continuación, presionando Entrar o seleccionando el valor que se muestra debajo del cuadro. Repita este paso tantas veces como sea necesario. Puede agregar hasta 20 entradas.

     > [!NOTE]
     > Use el dominio de la `5321.MailFrom` dirección (también conocida como dirección **MAIL FROM** , remitente P1 o remitente de sobre) que se usa en la transmisión SMTP del mensaje **o** un dominio de Correo identificado con DomainKeys (DKIM) según lo especificado por el proveedor de simulación de suplantación de identidad (phishing). 

   - **Enviar IP**: expanda esta configuración y escriba al menos una dirección IPv4 válida haciendo clic en el cuadro, escribiendo un valor y, a continuación, presionando Entrar o seleccionando el valor que se muestra debajo del cuadro. Repita este paso tantas veces como sea necesario. Puede agregar hasta 10 entradas. Los valores admitidos son:
     - Ip única: por ejemplo, 192.168.1.1.
     - Intervalo IP: por ejemplo, 192.168.0.1-192.168.0.254.
     - IP CIDR: por ejemplo, 192.168.0.1/25.
   - **Direcciones URL de simulación que se van a permitir**: expanda esta configuración y, opcionalmente, escriba direcciones URL específicas que formen parte de la campaña de simulación de suplantación de identidad (phishing) que no se deben bloquear ni detonar haciendo clic en el cuadro, especificando un valor y, a continuación, presionando Entrar o seleccionando el valor que se muestra debajo del cuadro. Puede agregar hasta 10 entradas. Para obtener el formato de sintaxis de dirección URL, consulte [Sintaxis de dirección URL para la lista de permitidos o bloques de inquilinos](tenant-allow-block-list.md#url-syntax-for-the-tenant-allowblock-list). Estas direcciones URL se encapsulan en el momento de hacer clic, pero no se bloquean.

   Para quitar un valor existente, haga clic en Quitar ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

   > [!NOTE]
   > Para configurar una simulación de suplantación de identidad (phishing) de terceros en Entrega avanzada, debe mostrar la siguiente información:
   > 
   > - Al menos un **dominio** de cualquiera de los siguientes orígenes:
   >   - La `5321.MailFrom` dirección (también conocida como dirección MAIL FROM, remitente P1 o remitente del sobre).
   >   - Dominio DKIM.
   > - Al menos una **dirección IP de envío**.
   > 
   > Opcionalmente, puede incluir **direcciones URL de simulación para asegurarse** de que las direcciones URL de los mensajes de simulación no están bloqueadas.
   > Puede especificar hasta 10 entradas para cada campo.
   > Debe haber una coincidencia en al menos un **dominio** y una **dirección IP de envío**, pero no se mantiene ninguna asociación entre los valores.

4. Cuando haya terminado, realice uno de los pasos siguientes:
   - **Primera vez**: haga clic en **Agregary**, a continuación, haga clic en **Cerrar**.
   - **Editar existente**: haga clic en **Guardar** y, a continuación, haga clic en **Cerrar**.

Las entradas de simulación de suplantación de identidad de terceros que configuró se muestran en la pestaña **Simulación de suplantación de identidad (Phishing).** Para realizar cambios, haga clic en ![el icono Editar.](../../media/m365-cc-sc-edit-icon.png) **Edite** en la pestaña .

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Escenarios adicionales que requieren omisión de filtrado

Además de los dos escenarios con los que la directiva de entrega avanzada puede ayudarle, hay otros escenarios que pueden requerir la omisión del filtrado:

- **Filtros de terceros**: si el registro MX del dominio *no* apunta a Office 365 (los mensajes se enrutan primero a otro lugar), [seguro de forma predeterminada](secure-by-default.md) *no está disponible*. Si desea agregar protección, deberá habilitar el filtrado mejorado para conectores (también conocido como *omitir lista*). Para obtener más información, consulte [Administración del flujo de correo mediante un servicio en la nube de terceros con Exchange Online](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud). Si no desea el filtrado mejorado para conectores, use reglas de flujo de correo (también conocidas como reglas de transporte) para omitir el filtrado de Microsoft para los mensajes que ya se han evaluado mediante el filtrado de terceros. Para obtener más información, consulte [Uso de reglas de flujo de correo para establecer la SCL en los mensajes](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

- **Falsos positivos en revisión**: es posible que quiera permitir temporalmente que determinados mensajes que Microsoft sigue analizando a través de [envíos de administradores](admin-submission.md) informen de mensajes buenos conocidos que se marcan incorrectamente como incorrectos para Microsoft (falsos positivos). Al igual que con todas las invalidaciones, **_se recomienda encarecidamente_** que estas asignaciones sean temporales.

## <a name="security--compliance-center-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a>Procedimientos de PowerShell del Centro de cumplimiento de & seguridad para buzones de SecOps en la directiva de entrega avanzada

En PowerShell de Security & Compliance Center, los elementos básicos de los buzones de SecOps de la directiva de entrega avanzada son:

- **Directiva de invalidación de SecOps**: controlada por los **\*cmdlets -SecOpsOverridePolicy** .
- **Regla de invalidación de SecOps**: controlada por los **\*cmdlets -SecOpsOverrideRule** .

Este comportamiento tiene los siguientes resultados:

- Primero se crea la directiva y, a continuación, se crea la regla que identifica la directiva a la que se aplica la regla.
- Al quitar una directiva de PowerShell, también se quita la regla correspondiente.
- Al quitar una regla de PowerShell, no se quita la directiva correspondiente. Debe quitar manualmente la directiva correspondiente.

### <a name="use-powershell-to-configure-secops-mailboxes"></a>Uso de PowerShell para configurar buzones de SecOps

La configuración de un buzón de SecOps en la directiva de entrega avanzada en PowerShell es un proceso de dos pasos:

1. Cree la directiva de invalidación de SecOps.
2. Cree la regla de invalidación de SecOps que especifique la directiva a la que se aplica la regla.

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a>Paso 1: Uso de PowerShell para crear la directiva de invalidación de SecOps

Para crear la directiva de invalidación de SecOps, use la sintaxis siguiente:

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

> [!NOTE]
> Independientemente del valor name que especifique, el nombre de la directiva será _SecOpsOverridePolicy_, por lo que también podría usar ese valor.

En este ejemplo se crea la directiva de buzón de SecOps.

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a>Paso 2: Uso de PowerShell para crear la regla de invalidación de SecOps

En este ejemplo se crea la regla de buzón de SecOps con la configuración especificada.

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

> [!NOTE]
> Independientemente del valor name que especifique, el nombre de la regla será _SecOpsOverrideRule_\<GUID\> , donde \<GUID\> es un valor GUID único (por ejemplo, 6fed4b63-3563-495d-a481-b24a311f8329).

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).

### <a name="use-powershell-to-view-the-secops-override-policy"></a>Uso de PowerShell para ver la directiva de invalidación de SecOps

En este ejemplo se devuelve información detallada sobre la directiva de buzón de uno y solo SecOps.

```powershell
Get-SecOpsOverridePolicy
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy).

### <a name="use-powershell-to-view-secops-override-rules"></a>Uso de PowerShell para ver las reglas de invalidación de SecOps

En este ejemplo se devuelve información detallada sobre las reglas de invalidación de SecOps.

```powershell
Get-SecOpsOverrideRule
```

Aunque el comando anterior solo debe devolver una regla, las reglas que están pendientes de eliminación también se pueden incluir en los resultados.

En este ejemplo se identifica la regla válida (una) y las reglas no válidas.

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

Después de identificar las reglas no válidas, puede quitarlas mediante el cmdlet **Remove-SecOpsOverrideRule** , como se describe [más adelante en este artículo](#use-powershell-to-remove-secops-override-rules).

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule).

### <a name="use-powershell-to-modify-the-secops-override-policy"></a>Uso de PowerShell para modificar la directiva de invalidación de SecOps

Para modificar la directiva de invalidación de SecOps, use la sintaxis siguiente:

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

En este ejemplo se agrega `secops2@contoso.com` a la directiva de invalidación de SecOps.

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

> [!NOTE]
> Si existe una regla de invalidación de SecOps asociada y válida, también se actualizarán las direcciones de correo electrónico de la regla.

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy).

### <a name="use-powershell-to-modify-a-secops-override-rule"></a>Uso de PowerShell para modificar una regla de invalidación de SecOps

El cmdlet **Set-SecOpsOverrideRule** no modifica las direcciones de correo electrónico en la regla de invalidación de SecOps. Para modificar las direcciones de correo electrónico en la regla de invalidación de SecOps, use el cmdlet **Set-SecOpsOverridePolicy** .

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule).

### <a name="use-powershell-to-remove-the-secops-override-policy"></a>Uso de PowerShell para quitar la directiva de invalidación de SecOps

En este ejemplo se quita la directiva de buzón de SecOps y la regla correspondiente.

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).

### <a name="use-powershell-to-remove-secops-override-rules"></a>Uso de PowerShell para quitar reglas de invalidación de SecOps

Para quitar una regla de invalidación de SecOps, use la sintaxis siguiente:

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

En este ejemplo se quita la regla de invalidación de SecOps especificada.

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).

## <a name="security--compliance-center-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Procedimientos de PowerShell del Centro de cumplimiento de seguridad & para simulaciones de suplantación de identidad de terceros en la directiva de entrega avanzada

En PowerShell del Centro de cumplimiento de seguridad &, los elementos básicos de las simulaciones de suplantación de identidad de terceros en la directiva de entrega avanzada son:

- **Directiva de invalidación de simulación de suplantación de identidad**: controlada por los **\*cmdlets -PhishSimOverridePolicy** .
- **Regla de invalidación de simulación de suplantación de identidad**: controlada por los **\*cmdlets -PhishSimOverrideRule** .
- **Las direcciones URL de simulación de suplantación de identidad permitidas (desbloqueadas**): controladas por los **\*cmdlets -TenantAllowBlockListItems** .

Este comportamiento tiene los siguientes resultados:

- Primero se crea la directiva y, a continuación, se crea la regla que identifica la directiva a la que se aplica la regla.
- Modifique la configuración de la directiva y la regla por separado.
- Al quitar una directiva de PowerShell, también se quita la regla correspondiente.
- Al quitar una regla de PowerShell, no se quita la directiva correspondiente. Debe quitar manualmente la directiva correspondiente.

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a>Uso de PowerShell para configurar simulaciones de suplantación de identidad de terceros

La configuración de una simulación de suplantación de identidad de terceros en PowerShell es un proceso de varios pasos:

1. Cree la directiva de invalidación de simulación de suplantación de identidad (phishing).
2. Cree la regla de invalidación de simulación de suplantación de identidad (phishing) que especifique:
   - Directiva a la que se aplica la regla.
   - Dirección IP de origen de los mensajes de simulación de suplantación de identidad (phishing).
3. Opcionalmente, puede identificar las direcciones URL de simulación de suplantación de identidad que deben permitirse (es decir, no bloqueadas ni examinadas).

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a>Paso 1: Uso de PowerShell para crear la directiva de invalidación de simulación de suplantación de identidad

En este ejemplo se crea la directiva de invalidación de simulación de suplantación de identidad (phishing).

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

**Nota**: Independientemente del valor name que especifique, el nombre de la directiva será _PhishSimOverridePolicy_, por lo que también podría usar ese valor.

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a>Paso 2: Uso de PowerShell para crear la regla de invalidación de simulación de suplantación de identidad

Utilice la siguiente sintaxis:

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -Domains <Domain1>,<Domain2>,...<Domain10> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntry10>
```

Independientemente del valor name que especifique, el nombre de la regla será _PhishSimOverrideRule_\<GUID\> , donde \<GUID\> es un valor GUID único (por ejemplo, a0eae53e-d755-4a42-9320-b9c6b55c5011).

Una entrada de dirección IP válida es uno de los siguientes valores:

- Ip única: por ejemplo, 192.168.1.1.
- Intervalo IP: por ejemplo, 192.168.0.1-192.168.0.254.
- IP CIDR: por ejemplo, 192.168.0.1/25.

En este ejemplo se crea la regla de invalidación de simulación de suplantación de identidad (phishing) con la configuración especificada.

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -Domains fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).

#### <a name="step-3-optional-use-powershell-to-identify-the-phishing-simulation-urls-to-allow"></a>Paso 3: (Opcional) Uso de PowerShell para identificar las direcciones URL de simulación de suplantación de identidad para permitir

Utilice la siguiente sintaxis:

```powershell
New-TenantAllowBlockListItems -Allow -ListType Url -ListSubType AdvancedDelivery -Entries "<URL1>","<URL2>",..."<URL10>" <[-NoExpiration] | [-ExpirationDate <DateTime>]>
```

Para obtener más información sobre la sintaxis de dirección URL, consulte [Sintaxis de direcciones URL para la lista de permitidos o bloqueados de inquilinos](tenant-allow-block-list.md#url-syntax-for-the-tenant-allowblock-list).

En este ejemplo se agrega una entrada de permiso de dirección URL para la dirección URL de simulación de suplantación de identidad de terceros especificada sin expiración.

```powershell
New-TenantAllowBlockListItems -Allow -ListType Url -ListSubType AdvancedDelivery -Entries *.fabrikam.com -NoExpiration
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a>Uso de PowerShell para ver la directiva de invalidación de simulación de suplantación de identidad

En este ejemplo se devuelve información detallada sobre la única directiva de invalidación de simulación de suplantación de identidad (phishing).

```powershell
Get-PhishSimOverridePolicy
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy).

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a>Uso de PowerShell para ver las reglas de invalidación de simulación de suplantación de identidad

En este ejemplo se devuelve información detallada sobre las reglas de invalidación de simulación de suplantación de identidad (phishing).

```powershell
Get-PhishSimOverrideRule
```

Aunque el comando anterior solo debe devolver una regla, las reglas que están pendientes de eliminación también se pueden incluir en los resultados.

En este ejemplo se identifica la regla válida (una) y las reglas no válidas.

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

Después de identificar las reglas no válidas, puede quitarlas mediante el cmdlet **Remove-PhishSimOverrideRule** , como se describe [más adelante en este artículo](#use-powershell-to-remove-phishing-simulation-override-rules).

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule).

### <a name="use-powershell-to-view-the-allowed-phishing-simulation-url-entries"></a>Uso de PowerShell para ver las entradas de url de simulación de suplantación de identidad permitidas

Para ver las direcciones URL de simulación de suplantación de identidad permitidas, ejecute el siguiente comando:

```powershell
Get-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a>Uso de PowerShell para modificar la directiva de invalidación de simulación de suplantación de identidad

Para modificar la directiva de invalidación de simulación de suplantación de identidad (phishing), use la sintaxis siguiente:

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

En este ejemplo se deshabilita la directiva de invalidación de simulación de suplantación de identidad (phishing).

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy).

### <a name="use-powershell-to-modify-phishing-simulation-override-rules"></a>Uso de PowerShell para modificar las reglas de invalidación de simulación de suplantación de identidad

Para modificar la regla de invalidación de simulación de suplantación de identidad (phishing), use la sintaxis siguiente:

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

En este ejemplo se modifica la regla de invalidación de simulación de suplantación de identidad especificada con la siguiente configuración:

- Agregue la entrada de dominio blueyonderairlines.com.
- Quite la entrada de dirección IP 192.168.1.55.

Tenga en cuenta que estos cambios no afectan a las entradas existentes.

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule).

### <a name="use-powershell-to-modify-the-allowed-phishing-simulation-url-entries"></a>Uso de PowerShell para modificar las entradas de url de simulación de suplantación de identidad permitidas

No se pueden modificar los valores de dirección URL directamente. Puede [quitar las entradas de dirección URL existentes](#use-powershell-to-remove-the-allowed-phishing-simulation-url-entries) y [agregar nuevas entradas de dirección URL](#step-3-optional-use-powershell-to-identify-the-phishing-simulation-urls-to-allow) , como se describe en este artículo.

Para modificar otras propiedades de una entrada url de simulación de suplantación de identidad permitida (por ejemplo, la fecha de expiración o los comentarios), use la sintaxis siguiente:

```powershell
Set-TenantAllowBlockListItems <-Entries "<URL1>","<URL2>",..."<URLN>" | -Ids <Identity>> -ListType URL -ListSubType AdvancedDelivery <[-NoExpiration] | [-ExpirationDate <DateTime>]> [-Notes <String>]
```

Identifica la entrada que se va a modificar por sus valores de dirección URL (el parámetro _Entries_ ) o el valor identity de la salida del cmdlet **Get-TenantAllowBlockListItems** (el parámetro _Ids_ ).

En este ejemplo se modificó la fecha de expiración de la entrada especificada.

```powershell
Set-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery -Entries "*.fabrikam.com" -ExpirationDate 9/11/2021
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a>Uso de PowerShell para quitar una directiva de invalidación de simulación de suplantación de identidad

En este ejemplo se quita la directiva de invalidación de simulación de suplantación de identidad (phishing) y la regla correspondiente.

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a>Uso de PowerShell para quitar reglas de invalidación de simulación de suplantación de identidad

Para quitar una regla de invalidación de simulación de suplantación de identidad (phishing), use la sintaxis siguiente:

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

En este ejemplo se quita la regla de invalidación de simulación de suplantación de identidad especificada.

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).

### <a name="use-powershell-to-remove-the-allowed-phishing-simulation-url-entries"></a>Uso de PowerShell para quitar las entradas de url de simulación de suplantación de identidad permitidas

Para quitar una entrada de dirección URL de simulación de suplantación de identidad existente, use la sintaxis siguiente:

```powershell
Remove-TenantAllowBlockListItems <-Entries "<URL1>","<URL2>",..."<URLN>" | -Ids <Identity>> -ListType URL -ListSubType AdvancedDelivery
```

Identifica la entrada que se va a modificar por sus valores de dirección URL (el parámetro _Entries_ ) o el valor identity de la salida del cmdlet **Get-TenantAllowBlockListItems** (el parámetro _Ids_ ).

En este ejemplo se modificó la fecha de expiración de la entrada especificada.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery -Entries "*.fabrikam.com" -ExpirationDate 9/11/2021
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).
