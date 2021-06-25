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
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Los administradores pueden aprender a usar la directiva de entrega avanzada en Exchange Online Protection (EOP) para identificar mensajes que no deben filtrarse en escenarios compatibles específicos (simulaciones de suplantación de identidad de terceros y mensajes entregados a buzones de operaciones de seguridad (SecOps).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01d35c1f0c7abc7b6ce34fc9c2ec4d5fd5b228ae
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137744"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>Configurar la entrega de simulaciones de suplantación de identidad de terceros a usuarios y mensajes sin filtrar a buzones de SecOps

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> La característica que se describe en este artículo está en Versión preliminar, no está disponible para todos y está sujeta a cambios.

Para mantener la organización segura de forma [predeterminada,](secure-by-default.md)Exchange Online Protection (EOP) no permite listas seguras ni omitir el filtrado de mensajes identificados como malware o phishing de elevada confianza. Sin embargo, hay escenarios específicos que requieren la entrega de mensajes sin filtrar. Por ejemplo:

- **Simulaciones de suplantación** de identidad de terceros: los ataques simulados pueden ayudarle a identificar usuarios vulnerables antes de que un ataque real impacte en su organización.
- Buzones de operaciones de seguridad **(SecOps):** buzones dedicados que usan los equipos de seguridad para recopilar y analizar mensajes sin filtrar (tanto buenos como malos).

Use la directiva _de entrega avanzada_ en Microsoft 365 para evitar que estos mensajes en estos _escenarios específicos_ se filtren. <sup>\*</sup> La directiva de entrega avanzada garantiza que los mensajes en estos escenarios consigan los siguientes resultados:

- Los filtros de EOP y Microsoft Defender Office 365 realizar ninguna acción en estos mensajes.<sup>\*</sup>
- [La purga de hora cero (ZAP)](zero-hour-auto-purge.md) para correo no deseado y suplantación de identidad (phishing) no toma ninguna acción en estos mensajes.<sup>\*</sup>
- [Las alertas predeterminadas](alerts.md) del sistema no se desencadenan para estos escenarios.
- [AIR y la agrupación en clústeres en Defender para Office 365](office-365-air.md) omite estos mensajes.
- Específicamente para simulaciones de suplantación de identidad de terceros:
  - [Los envíos de](admin-submission.md) administrador generan una respuesta automática que indica que el mensaje forma parte de una campaña de simulación de suplantación de identidad (phishing) y no es una amenaza real. Las alertas y AIR no se desencadenarán.
  - [Caja fuerte vínculos en Defender para Office 365](safe-links.md) no bloquea ni detona las direcciones URL identificadas específicamente en estos mensajes.
  - [Caja fuerte datos adjuntos en Defender para Office 365](safe-attachments.md) no detonan datos adjuntos en estos mensajes.

<sup>\*</sup> No puede omitir el filtrado de malware o ZAP para malware.

Los mensajes identificados por la directiva de entrega avanzada no son amenazas de seguridad, por lo que los mensajes se marcan como invalidaciones del sistema. Los administradores pueden filtrar y analizar estas invalidaciones del sistema en las siguientes experiencias:

- [Explorador de amenazas/detecciones en tiempo real en Defender para Office 365 plan 2](threat-explorer.md)
- La [entidad Email Page en el Explorador de amenazas/Detecciones en tiempo real](mdo-email-entity-page.md)
- Informe [de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
- [Búsqueda avanzada en Microsoft Defender para endpoint](../defender-endpoint/advanced-hunting-overview.md)
- [Vistas de campañas](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la **página Entrega avanzada,** abra <https://security.microsoft.com/advanceddelivery> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Debe tener asignados permisos antes de poder realizar los procedimientos descritos en este artículo:
  - Para crear, modificar o quitar la configuración de la directiva de  entrega avanzada, debe ser miembro del grupo de  roles Administrador de seguridad en el **portal de Microsoft 365 Defender** y miembro del grupo de roles Administración de la organización en **Exchange Online**.
  - Para obtener acceso de solo lectura a la directiva de entrega avanzada, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.

  Para obtener más información, vea [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  > Agregar usuarios al rol de Azure Active Directory correspondiente proporciona a los usuarios los permisos necesarios en el _portal_ de Microsoft 365 Defender y permisos para otras características de Microsoft 365. Para más información, consulte [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Usar el portal Microsoft 365 Defender para configurar buzones de SecOps en la directiva de entrega avanzada

1. En el portal Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Reglas de amenazas sección \>  \>  Reglas de entrega \>  \> **avanzada**.

2. En la **página Entrega avanzada,** compruebe que la pestaña buzón **de SecOps** está seleccionada y, a continuación, siga uno de los pasos siguientes:
   - Haga ![ clic en Editar icono ](../../media/m365-cc-sc-edit-icon.png) **Editar**.
   - Si no hay simulaciones de suplantación de identidad configuradas, haga clic en **Agregar**.

3. En el control desplegable Editar buzones de SecOps que se abre, escriba un buzón de Exchange Online existente que desee designar como buzón de **SecOps** siguiendo uno de los pasos siguientes:
   - Haga clic en el cuadro, deje que se resuelva la lista de buzones y, a continuación, seleccione el buzón.
   - Haga clic en el cuadro para empezar a escribir un identificador para el buzón (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de cuenta, etc.) y seleccione el buzón (nombre para mostrar) de los resultados.

     Repita este paso tantas veces como sea necesario. Los grupos de distribución no están permitidos.

     Para quitar un valor existente, haga clic en Quitar ![Icono de quitar](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

4. Cuando haya terminado, haga clic en **Guardar**.

Las entradas de buzón de SecOps que configuró se muestran en la **pestaña Buzón de SecOps.** Para realizar cambios, haga clic ![ en Editar icono ](../../media/m365-cc-sc-edit-icon.png) **Editar** en la pestaña.

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Use el portal Microsoft 365 Defender para configurar simulaciones de suplantación de identidad de terceros en la directiva de entrega avanzada

1. En el portal Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Reglas de amenazas sección \>  \>  Reglas de entrega \>  \> **avanzada**.

2. En la **página Entrega avanzada,** seleccione la pestaña **Simulación de suplantación** de identidad y, a continuación, realice uno de los siguientes pasos:
   - Haga ![ clic en Editar icono ](../../media/m365-cc-sc-edit-icon.png) **Editar**.
   - Si no hay simulaciones de suplantación de identidad configuradas, haga clic en **Agregar**.

3. En el **control desplegable Editar simulación de suplantación** de identidad de terceros que se abre, configure las siguientes opciones:

   - **Dominio** de envío: expanda esta configuración y escriba al menos un dominio de dirección de correo electrónico (por ejemplo, contoso.com) haciendo clic en el cuadro, especificando un valor y presionando Entrar o seleccionando el valor que se muestra debajo del cuadro. Repita este paso tantas veces como sea necesario. Puede agregar hasta 10 entradas.
   - **Enviar IP:** expanda esta configuración y escriba al menos una dirección IPv4 válida haciendo clic en el cuadro, especificando un valor y presionando Entrar o seleccionando el valor que se muestra debajo del cuadro. Repita este paso tantas veces como sea necesario. Puede agregar hasta 10 entradas. Los valores admitidos son:
     - IP única: por ejemplo, 192.168.1.1.
     - Intervalo IP: por ejemplo, 192.168.0.1-192.168.0.254.
     - IP cidr: por ejemplo, 192.168.0.1/25.
   - Direcciones **URL** de simulación para permitir: expanda esta configuración y, opcionalmente, escriba direcciones URL específicas que forman parte de la campaña de simulación de suplantación de identidad que no se deben bloquear ni detonar haciendo clic en el cuadro, especificando un valor y presionando Entrar o seleccionando el valor que se muestra debajo del cuadro. Puede agregar hasta 10 entradas.

   Para quitar un valor existente, haga clic en Quitar ![Icono de quitar](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

4. Cuando haya terminado, siga uno de los pasos siguientes:
   - **Primera vez:** haga clic **en Agregar** y, a continuación, en **Cerrar**.
   - **Editar existente:** haga clic **en Guardar** y, a continuación, en **Cerrar**.

Las entradas de simulación de suplantación de identidad de terceros que configuró se muestran en la pestaña **Simulación de suplantación de** identidad. Para realizar cambios, haga clic ![ en Editar icono ](../../media/m365-cc-sc-edit-icon.png) **Editar** en la pestaña.

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Escenarios adicionales que requieren la omisión de filtrado

Además de los dos escenarios con los que la directiva de entrega avanzada puede ayudarle, hay otros escenarios que pueden requerir omitir el filtrado:

- **Filtros de terceros:** si el registro  MX de su dominio no apunta a Office 365 (los mensajes se enruta en otro lugar primero), [la](secure-by-default.md) seguridad de forma predeterminada no *está disponible*. Si quieres agregar protección, tendrás que habilitar el filtrado mejorado para conectores (también conocido como *listado de omitir*). Para obtener más información, vea [Manage mail flow using a third-party cloud service with Exchange Online](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud). Si no desea el filtrado mejorado para conectores, use reglas de flujo de correo (también conocidas como reglas de transporte) para omitir el filtrado de Microsoft para los mensajes que ya han sido evaluados por el filtrado de terceros. Para obtener más información, vea [Usar reglas de flujo de correo para establecer el SCL en mensajes](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).

- **Falsos positivos** en revisión: es posible que desee permitir temporalmente que determinados mensajes que Microsoft sigue analizando a través de [envíos](admin-submission.md) de administrador informen de mensajes buenos conocidos que se marcan incorrectamente como incorrectos para Microsoft (falsos positivos). Al igual que con todas las invalidaciones, se **_recomienda encarecidamente_** que estas asignaciones sean temporales.

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a>Exchange Online Procedimientos de PowerShell para buzones de SecOps en la directiva de entrega avanzada

En Exchange Online PowerShell, los elementos básicos de los buzones de SecOps en la directiva de entrega avanzada son:

- **La directiva de invalidación de SecOps:** controlada por los **\* cmdlets -SecOpsOverridePolicy.**
- **La regla de invalidación de SecOps**: Controlada por los **\* cmdlets -SecOpsOverrideRule.**

Este comportamiento tiene los siguientes resultados:

- Primero se crea la directiva y, a continuación, se crea la regla que identifica la directiva a la que se aplica la regla.
- Al quitar una directiva de PowerShell, también se quita la regla correspondiente.
- Al quitar una regla de PowerShell, no se quita la directiva correspondiente. Debe quitar la directiva correspondiente manualmente.

### <a name="use-powershell-to-configure-secops-mailboxes"></a>Usar PowerShell para configurar buzones de SecOps

Configurar un buzón de SecOps en la directiva de entrega avanzada en PowerShell es un proceso de dos pasos:

1. Cree la directiva de invalidación de SecOps.
2. Cree la regla de invalidación de SecOps que especifica la directiva a la que se aplica la regla.

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a>Paso 1: Usar PowerShell para crear la directiva de invalidación de SecOps

Para crear la directiva de invalidación de SecOps, use la siguiente sintaxis:

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

**Nota:** Independientemente del valor name que especifique, el nombre de la directiva será SecOpsOverridePolicy, por lo que también puede usar ese valor.

En este ejemplo se crea la directiva de buzón de SecOps.

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SendTo secops@contoso.com
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a>Paso 2: Usar PowerShell para crear la regla de invalidación de SecOps

En este ejemplo se crea la regla de buzón de SecOps con la configuración especificada.

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

**Nota:****Independientemente del valor name que especifique, el nombre de la regla será SecOpsOverrideRule donde es un valor GUID único \<GUID\> \<GUID\> (por ejemplo, 6fed4b63-3563-495d-a481-b24a311f8329).

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).

### <a name="use-powershell-to-view-the-secops-override-policy"></a>Usar PowerShell para ver la directiva de invalidación de SecOps

En este ejemplo se devuelve información detallada sobre la única directiva de buzón de SecOps.

```powershell
Get-SecOpsOverridePolicy
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy).

### <a name="use-powershell-to-view-secops-override-rules"></a>Usar PowerShell para ver reglas de invalidación de SecOps

En este ejemplo se devuelve información detallada acerca de las reglas de invalidación de SecOps.

```powershell
Get-SecOpsOverrideRule
```

Aunque el comando anterior debe devolver solo una regla, las reglas pendientes de eliminación también pueden incluirse en los resultados.

En este ejemplo se identifica la regla válida (una) y las reglas no válidas.

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

Después de identificar las reglas no válidas, puede quitarlas mediante el cmdlet **Remove-SecOpsOverrideRule,** tal como se describe [más adelante en este artículo](#use-powershell-to-remove-secops-override-rules).

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)

### <a name="use-powershell-to-modify-the-secops-override-policy"></a>Usar PowerShell para modificar la directiva de invalidación de SecOps

Para modificar la directiva de invalidación de SecOps, use la siguiente sintaxis:

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

En este ejemplo se secops2@contoso.com a la directiva de invalidación de SecOps.

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

**Nota:** Si existe una regla de invalidación de SecOps asociada y válida, también se actualizarán las direcciones de correo electrónico de la regla.

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy).

### <a name="use-powershell-to-modify-a-secops-override-rule"></a>Usar PowerShell para modificar una regla de invalidación de SecOps

El cmdlet **Set-SecOpsOverrideRule** no modifica las direcciones de correo electrónico de la regla de invalidación de SecOps. Para modificar las direcciones de correo electrónico de la regla de invalidación de SecOps, use el cmdlet **Set-SecOpsOverridePolicy.**

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule).

### <a name="use-powershell-to-remove-the-secops-override-policy"></a>Usar PowerShell para quitar la directiva de invalidación de SecOps

En este ejemplo se quita la directiva de buzón de SecOps y la regla correspondiente.

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).

### <a name="use-powershell-to-remove-secops-override-rules"></a>Usar PowerShell para quitar reglas de invalidación de SecOps

Para quitar una regla de invalidación de SecOps, use la siguiente sintaxis:

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

En este ejemplo se quita la regla de invalidación de SecOps especificada.

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Exchange Online Procedimientos de PowerShell para simulaciones de suplantación de identidad de terceros en la directiva de entrega avanzada

En Exchange Online PowerShell, los elementos básicos de las simulaciones de suplantación de identidad de terceros en la directiva de entrega avanzada son:

- **La directiva de invalidación de simulación de suplantación de** identidad : controlada por los **\* cmdlets -PhishSimOverridePolicy.**
- **La regla de invalidación de simulación de** suplantación de identidad : controlada por los **\* cmdlets -PhishSimOverrideRule.**

Este comportamiento tiene los siguientes resultados:

- Primero se crea la directiva y, a continuación, se crea la regla que identifica la directiva a la que se aplica la regla.
- Puede modificar la configuración de la directiva y la regla por separado.
- Al quitar una directiva de PowerShell, también se quita la regla correspondiente.
- Al quitar una regla de PowerShell, no se quita la directiva correspondiente. Debe quitar la directiva correspondiente manualmente.

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a>Usar PowerShell para configurar simulaciones de suplantación de identidad de terceros

Configurar una simulación de suplantación de identidad de terceros en la directiva de entrega avanzada en PowerShell es un proceso de dos pasos:

1. Crear la directiva de invalidación de simulación de suplantación de identidad.
2. Cree la regla de invalidación de simulación de suplantación de identidad (phishing) que especifica la directiva a la que se aplica la regla.

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a>Paso 1: Usar PowerShell para crear la directiva de invalidación de simulación de suplantación de identidad

En este ejemplo se crea la directiva de invalidación de simulación de suplantación de identidad.

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

**Nota:** Independientemente del valor name que especifique, el nombre de la directiva será PhishSimOverridePolicy, por lo que también puede usar ese valor.

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a>Paso 2: Usar PowerShell para crear la regla de invalidación de simulación de suplantación de identidad

Utilice la siguiente sintaxis:

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

Independientemente del valor name que especifique, el nombre de la regla será PhishSimOverrideRule donde es un valor GUID único \<GUID\> \<GUID\> (por ejemplo, a0eae53e-d755-4a42-9320-b9c6b55c5011).

Una entrada de dirección IP válida es uno de los siguientes valores:

- IP única: por ejemplo, 192.168.1.1.
- Intervalo IP: por ejemplo, 192.168.0.1-192.168.0.254.
- IP cidr: por ejemplo, 192.168.0.1/25.

En este ejemplo se crea la regla de invalidación de simulación de suplantación de identidad con la configuración especificada.

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a>Usar PowerShell para ver la directiva de invalidación de simulación de suplantación de identidad

En este ejemplo se devuelve información detallada sobre la única directiva de invalidación de simulación de suplantación de identidad.

```powershell
Get-PhishSimOverridePolicy
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy).

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a>Usar PowerShell para ver reglas de invalidación de simulación de suplantación de identidad

En este ejemplo se devuelve información detallada acerca de las reglas de invalidación de simulación de suplantación de identidad.

```powershell
Get-PhishSimOverrideRule
```

Aunque el comando anterior debe devolver solo una regla, las reglas pendientes de eliminación también pueden incluirse en los resultados.

En este ejemplo se identifica la regla válida (una) y las reglas no válidas.

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

Después de identificar las reglas no válidas, puede quitarlas mediante el cmdlet **Remove-PhisSimOverrideRule,** tal como se describe [más adelante en este artículo](#use-powershell-to-remove-phishing-simulation-override-rules).

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule).

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a>Usar PowerShell para modificar la directiva de invalidación de simulación de suplantación de identidad

Para modificar la directiva de invalidación de simulación de suplantación de identidad,use la siguiente sintaxis:

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

En este ejemplo se deshabilita la directiva de invalidación de simulación de suplantación de identidad.

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy).

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a>Usar PowerShell para modificar una regla de invalidación de simulación de suplantación de identidad

Para modificar la regla de invalidación de simulación de suplantación de identidad, use la siguiente sintaxis:

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

En este ejemplo se modifica la regla de invalidación de simulación de suplantación de identidad (phishing) especificada con la siguiente configuración:

- Agregue la entrada de dominio blueyonderairlines.com.
- Quite la entrada de dirección IP 192.168.1.55.

Tenga en cuenta que estos cambios no afectan a las entradas existentes.

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule).

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a>Usar PowerShell para quitar una directiva de invalidación de simulación de suplantación de identidad

En este ejemplo se quita la directiva de invalidación de simulación de suplantación de identidad (phishing) y la regla correspondiente.

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a>Usar PowerShell para quitar reglas de invalidación de simulación de suplantación de identidad

Para quitar una regla de invalidación de simulación de suplantación de identidad,use la siguiente sintaxis:

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

En este ejemplo se quita la regla de invalidación de simulación de suplantación de identidad especificada.

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).
