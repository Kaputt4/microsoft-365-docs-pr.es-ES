---
title: Directivas de cuarentena
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Los administradores pueden aprender a usar directivas de cuarentena para controlar lo que los usuarios pueden hacer con sus mensajes en cuarentena.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 581b465ddc8197e2f029b149c57d5d83aacf7a15
ms.sourcegitcommit: 6c342a956b2dbc32be33bac1a23a5038490f1b40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58533476"
---
# <a name="quarantine-policies"></a>Directivas de cuarentena

> [!NOTE]
> Las características que se describen en este artículo están actualmente en Versión preliminar, no están disponibles para todos y están sujetas a cambios.

Las directivas de cuarentena (anteriormente conocidas como etiquetas de _cuarentena)_ en Exchange Online Protection (EOP) y Microsoft Defender para Office 365 permiten a los administradores controlar lo que los usuarios pueden hacer con sus mensajes en cuarentena en función del motivo por el que el mensaje se ha puesto en cuarentena.

Tradicionalmente, los usuarios se han permitido o [](find-and-release-quarantined-messages-as-a-user.md) denegado niveles de interactividad para mensajes en cuarentena y en notificaciones [de correo no deseado del usuario final.](use-spam-notifications-to-release-and-report-quarantined-messages.md) Por ejemplo, los usuarios pueden ver y liberar mensajes que fueron puestos en cuarentena por el filtrado contra correo no deseado como correo no deseado o masivo, pero no pueden ver ni liberar mensajes que se han puesto en cuarentena como phishing de elevada confianza (solo los administradores pueden hacerlo).

Para [las características de protección admitidas,](#step-2-assign-a-quarantine-policy-to-supported-features)las directivas de cuarentena especifican lo que los usuarios pueden hacer en los mensajes de notificación de correo no deseado del usuario final y en cuarentena (mensajes donde el usuario es un destinatario). Las directivas de cuarentena predeterminadas se asignan automáticamente para aplicar las capacidades históricas de los usuarios en mensajes en cuarentena. O bien, puede crear y asignar directivas de cuarentena personalizadas para permitir o impedir que los usuarios finales realicen acciones específicas en mensajes en cuarentena.

Los permisos individuales se combinan en los siguientes grupos de permisos preestablecidos:

- Sin acceso
- Acceso limitado
- Acceso completo

Los permisos individuales disponibles y lo que se incluye o no en los grupos de permisos preestablecidos se describen en la tabla siguiente:

<br>

****

|Permiso|Sin acceso|Acceso limitado|Acceso completo|
|---|:---:|:---:|:---:|
|**Bloquear remitente** (_PermissionToBlockSender_)||![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|**Delete** (_PermissionToDelete_)||![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|**Vista** previa (_PermissionToPreview_)||![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|**Permitir que los destinatarios liberen un mensaje de cuarentena** (_PermissionToRelease_)|||![Marca de verificación](../../media/checkmark.png)|
|**Permitir que los destinatarios soliciten la puesta en** cuarentena de un mensaje (_PermissionToRequestRelease_)||![Marca de verificación](../../media/checkmark.png)||
|

Las directivas de cuarentena predeterminadas y sus grupos de permisos asociados se describen en la tabla siguiente:

<br>

|Directiva de cuarentena predeterminada|Grupo de permisos usado|
|---|---|
|AdminOnlyAccessPolicy|Sin acceso|
|DefaultFullAccessPolicy|Acceso completo|
|

Si no le gustan los permisos predeterminados en los grupos de permisos preestablecidos, puede usar permisos personalizados al crear o modificar directivas de cuarentena personalizadas. Para obtener más información acerca de lo que hace cada permiso, vea la sección Detalles de permisos de directiva [de cuarentena](#quarantine-policy-permission-details) más adelante en este artículo.

Puede crear y asignar directivas de cuarentena en el portal de Microsoft 365 Defender o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones de correo de Exchange Online; PowerShell de EOP independiente en organizaciones de EOP sin Exchange Online buzones).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. O bien, para ir directamente a la página **Directivas de** cuarentena, abra <https://security.microsoft.com/quarantinePolicies> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Para ver, crear, modificar o quitar directivas de cuarentena, debe ser miembro  de los roles Administración de la **organización,** Administrador de seguridad o Administrador de cuarentena en el portal Microsoft 365 Defender cuarentena. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

## <a name="step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Paso 1: Crear directivas de cuarentena en el portal de Microsoft 365 Defender web

1. En el portal Microsoft 365 Defender, vaya a Correo electrónico **&** sección Directivas de amenazas Sección Directivas de cuarentena y, a continuación, \>  \>  \>  seleccione Directivas **de cuarentena**.

2. En la **página Directiva de** cuarentena, haga clic en Agregar icono de directiva personalizada Agregar directiva ![ ](../../media/m365-cc-sc-create-icon.png) **personalizada.**

3. Se **abrirá el Asistente para nueva** directiva. En la **página Nombre de** directiva, escriba un nombre breve pero único en el cuadro Nombre **de** directiva. Deberá identificar y seleccionar la directiva de cuarentena por su nombre en los próximos pasos. Cuando termine, haga clic en **Siguiente**.

4. En la **página Acceso a mensajes de** destinatario, seleccione uno de los siguientes valores:
   - **Acceso limitado:** los permisos individuales que se incluyen en este grupo de permisos se describen anteriormente en este artículo.
   - **Establecer acceso específico (avanzado):** use este valor para especificar permisos personalizados. Configure las siguientes opciones que aparecen:
     - **Seleccionar preferencia de acción de lanzamiento:** seleccione uno de los siguientes valores:
       - **Sin acción de lanzamiento:** este es el valor predeterminado.
       - **Permitir que los destinatarios liberen un mensaje de cuarentena**
       - **Permitir que los destinatarios soliciten un mensaje que se liberará de la cuarentena**
     - **Seleccionar acciones adicionales que los** destinatarios pueden realizar en mensajes en cuarentena: seleccione algunos, todos o ninguno de los siguientes valores:
       - **Eliminar**
       - **Versión preliminar**
       - **Bloquear remitente**

   Estos permisos y su efecto en los mensajes en cuarentena y en las notificaciones de correo no deseado del usuario final se describen en la sección [Detalles](#quarantine-policy-permission-details) de permisos de directiva de cuarentena más adelante en este artículo.

   Cuando termine, haga clic en **Siguiente**.

5. En la página Notificación de correo no deseado del usuario **final,** puede activar la casilla para habilitar la notificación.

6. En la **página Revisar directiva** que aparece, revisa la configuración. Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Enviar**.

7. En la página de confirmación que aparece, haga clic en **Listo**.

Ahora ya está listo para asignar la directiva de cuarentena a una característica de cuarentena, tal como se describe en la [sección Paso 2.](#step-2-assign-a-quarantine-policy-to-supported-features)

### <a name="create-quarantine-policies-in-powershell"></a>Crear directivas de cuarentena en PowerShell

Si prefiere usar PowerShell para crear directivas de cuarentena, conéctese Exchange Online PowerShell o Exchange Online Protection PowerShell y use el cmdlet **New-QuarantineTag.** Tiene dos métodos diferentes entre los que elegir:

- [Use el _parámetro EndUserQuarantinePermissionsValue_](#use-the-enduserquarantinepermissionsvalue-parameter).
- [Use el _parámetro EndUserQuarantinePermissions_](#use-the-enduserquarantinepermissions-parameter).

Estos métodos se describen en las secciones siguientes.

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a>Usar el parámetro EndUserQuarantinePermissionsValue

Para crear una directiva de cuarentena mediante el _parámetro EndUserQuarantinePermissionsValue,_ use la siguiente sintaxis:

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

El _parámetro EndUserQuarantinePermissionsValue_ usa un valor decimal que se convierte a partir de un valor binario. El valor binario corresponde a los permisos de cuarentena de usuario final disponibles en un orden específico. Para cada permiso, el valor 1 es True y el valor 0 es False.

El orden y los valores necesarios para cada permiso individual en grupos de permisos preestablecidos se describen en la tabla siguiente:

<br>

****

|Permiso|Acceso limitado|
|---|:---:|
|PermissionToBlockSender|1|
|PermissionToDelete|1|
|PermissionToDownload<sup>\*</sup>|0|
|PermissionToPreview|1|
|PermissionToRelease<sup>\*\*</sup>|0|
|PermissionToRequestRelease<sup>\*\*</sup>|1|
|PermissionToViewHeader<sup>\*</sup>|0|
|Valor binario|01101010|
|Valor decimal que se usará|106|
|

<sup>\*</sup> Actualmente, este valor es siempre 0. Para PermissionToViewHeader, el valor 0  no oculta el botón Ver encabezado del mensaje en los detalles del mensaje en cuarentena (el botón siempre está disponible).

<sup>\*\*</sup> No establezca ambos valores en 1. Establezca uno en 1 y el otro en 0, o establezca ambos en 0.

En este ejemplo se crea un nuevo nombre de directiva de cuarentena LimitedAccess que asigna los permisos de acceso limitado como se describe en la tabla anterior.

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissionsValue 106
```

Para los permisos personalizados, use la tabla anterior para obtener el valor binario que corresponde a los permisos que desea. Convierta el valor binario en un valor decimal y use el valor decimal para el parámetro _EndUserQuarantinePermissionsValue._

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).

#### <a name="use-the-enduserquarantinepermissions-parameter"></a>Usar el parámetro EndUserQuarantinePermissions

Para crear una directiva de cuarentena mediante el _parámetro EndUserQuarantinePermissionsValue,_ siga estos pasos:

R. Almacene un objeto de permisos de cuarentena en una variable mediante el cmdlet **New-QuarantinePermissions.**

<p>

B. Use la variable como el _valor EndUserQuarantinePermissions_ en el **comando New-QuarantineTag.**

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a>Paso A: Almacenar un objeto de permisos de cuarentena en una variable

Utilice la siguiente sintaxis:

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

El valor predeterminado de los parámetros no usados es , por lo que solo necesita usar los parámetros donde desea establecer `$false` el valor en `$true` .

En el ejemplo siguiente se muestra cómo crear objetos de permisos que corresponden al **grupo De** permisos preestablecidos de acceso limitado:

```powershell
$LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
```

Para ver los valores que ha establecido, ejecute el nombre de la variable como un comando (por ejemplo, ejecute el comando `$LimitedAccess` ).

Para los permisos personalizados, no establezca los parámetros _PermissionToRelease_ y _PermissionToRequestRelease en_ `$true` . Establezca uno en `$true` y deje el otro como , o deje ambos como `$false` `$false` .

También puede modificar una variable de objeto permissions existente después de crearla, pero antes de usarla mediante el cmdlet **Set-QuarantinePermissions.**

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) y [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a>Paso B: Usar la variable en el New-QuarantineTag comando

Después de crear y almacenar el objeto permissions en una variable, use la variable para el valor del parámetro _EndUserQuarantinePermission_ en el siguiente comando **New-QuarantineTag:**

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

En este ejemplo se crea una nueva directiva de cuarentena denominada LimitedAccess mediante el objeto permissions que se describió y `$LimitedAccess` creó en el paso anterior.

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).

## <a name="step-2-assign-a-quarantine-policy-to-supported-features"></a>Paso 2: Asignar una directiva de cuarentena a las características compatibles

En _las características_ de protección admitidas que ponen en cuarentena mensajes o archivos (automáticamente o como una acción configurable), puede asignar una directiva de cuarentena a las acciones de cuarentena disponibles. En la tabla siguiente se describen las características que ponen en cuarentena los mensajes y la disponibilidad de las directivas de cuarentena:

<br>

****

|Característica|¿Se admiten directivas de cuarentena?|Directivas de cuarentena predeterminadas usadas|
|---|:---:|---|
|[Directivas contra correo no deseado:](configure-your-spam-filter-policies.md) <ul><li>**Correo no deseado** (_SpamAction_)</li><li>**Correo no deseado de elevada** confianza (_HighConfidenceSpamAction_)</li><li>**Phishing** (_PhishSpamAction_)</li><li>**Phishing de elevada confianza** (_HighConfidencePhishAction_)</li><li>**Bulk** (_BulkSpamAction_)</li></ul>|Sí|<ul><li>DefaultFullAccessPolicy (acceso completo)</li><li>DefaultFullAccessPolicy (acceso completo)</li><li>DefaultFullAccessPolicy (acceso completo)</li><li>AdminOnlyAccessPolicy (sin acceso)</li><li>DefaultFullAccessPolicy (acceso completo)</li></ul>|
|Directivas contra suplantación de identidad: <ul><li>[Protección de inteligencia suplantada](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</li><li>[Protección de suplantación en Defender para Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<ul><li>**Si se detecta message como un usuario suplantado** (_TargetedUserProtectionAction_)</li><li>**Si el mensaje se detecta como un dominio suplantado** (_TargetedDomainProtectionAction_)</li><li>**Si la inteligencia de buzones detecta y suplanta al usuario** (_MailboxIntelligenceProtectionAction_)</li></ul></li></ul>|Sí|<ul><li>DefaultFullAccessPolicy (acceso completo)</li><li>Protección de suplantación:<ul><li>DefaultFullAccessPolicy (acceso completo)</li><li>DefaultFullAccessPolicy (acceso completo)</li><li>DefaultFullAccessPolicy (acceso completo)</li></ul></li></ul>|
|[Directivas antimalware:](configure-anti-malware-policies.md)todos los mensajes detectados siempre se ponen en cuarentena.|Sí|AdminOnlyAccessPolicy (sin acceso)|
|[Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md) (Defender para Office 365)|Sí|AdminOnlyAccessPolicy (sin acceso)|
|[Reglas de flujo de](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) correo (también conocidas como reglas de transporte) con la acción: Entregar el mensaje a la cuarentena **hospedada** (_Cuarentena_).|No|No aplicable|
|

Si está satisfecho con los permisos predeterminados del usuario final proporcionados por las directivas de cuarentena predeterminadas, no necesita hacer nada. Si desea agregar o quitar funcionalidades de usuario final (botones disponibles) en notificaciones de correo no deseado del usuario final o en detalles de mensajes en cuarentena, puede asignar una directiva de cuarentena personalizada.

## <a name="assign-quarantine-policies-in-supported-polices-in-the-microsoft-365-defender-portal"></a>Asignar directivas de cuarentena en las directivas admitidas en el portal Microsoft 365 Defender web

### <a name="anti-spam-policies"></a>Directivas contra correo no deseado

1. En el portal Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & reglas de amenazas Directivas contra correo no deseado en \>  \>  \>  la **sección** Reglas.

   O bien, para ir directamente a la **página Directivas de correo no** deseado de ant, use <https://security.microsoft.com/antispam> .

2. En la **página Directivas contra correo** no deseado, siga uno de estos pasos:
   - Busque y seleccione una directiva **contra** correo no deseado entrante existente.
   - Cree una nueva **directiva contra** correo no deseado entrante.

3. Realice uno de los pasos siguientes:
   - **Editar existente:** seleccione la directiva haciendo clic en el nombre de la directiva. En el control desplegable de detalles de la directiva, vaya a la **sección Acciones** y, a continuación, haga clic en **Editar acciones**.
   - **Crear nuevo:** en el asistente para nueva directiva, acceda a la **página** Acciones.

4. En la **página Acciones,** cada  veredicto que  tenga la acción Mensaje de cuarentena también tendrá el cuadro Aplicar directiva de cuarentena para que seleccione una directiva de cuarentena correspondiente.

   **Nota:** Al crear una nueva directiva, se usa un valor de directiva de cuarentena **Select** en blanco que indica la directiva de cuarentena predeterminada para ese veredicto. Cuando más adelante edite la directiva, los valores en blanco se reemplazan por los nombres de directiva de cuarentena predeterminados reales, como se describe en la tabla anterior.

   ![Selecciones de directivas de cuarentena en una directiva contra correo no deseado](../../media/quarantine-tags-in-anti-spam-policies.png)

Las instrucciones completas para crear y modificar directivas contra correo no deseado se describen en [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

#### <a name="anti-spam-policies-in-powershell"></a>Directivas contra correo no deseado en PowerShell

Si prefiere usar PowerShell para asignar directivas de cuarentena en directivas contra correo no deseado, conéctese a Exchange Online PowerShell o Exchange Online Protection PowerShell y use la siguiente sintaxis:

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>"> [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

**Notas**:

- El valor predeterminado de los parámetros _PhishSpamAction_ y _HighConfidencePhishAction_ es Quarantine, por lo que no es necesario usar estos parámetros al crear nuevas policías de filtro de correo no deseado en PowerShell. Para los parámetros _SpamAction,_ _HighConfidenceSpamAction_ y _BulkSpamAction_ en directivas contra correo no deseado nuevas o existentes, la directiva de cuarentena solo es eficaz si el valor es Quarantine.

  Para ver los valores de parámetros importantes en las directivas contra correo no deseado existentes, ejecute el siguiente comando:

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*SpamAction,HighConfidencePhishAction,*QuarantineTag
  ```

  Para obtener información sobre los valores de acción predeterminados y los valores de acción recomendados para Standard y Strict, consulte [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).

- Un veredicto de filtrado de correo no deseado sin un parámetro de directiva de cuarentena correspondiente significa que se usa la directiva de [cuarentena](#step-2-assign-a-quarantine-policy-to-supported-features) predeterminada para ese veredicto.

  Debe reemplazar una directiva de cuarentena predeterminada por una directiva de cuarentena personalizada solo si desea cambiar las capacidades predeterminadas del usuario final en los mensajes en cuarentena para ese veredicto en particular.

- Una nueva directiva contra correo no deseado en PowerShell requiere una directiva de filtro de correo no deseado (configuración) mediante el cmdlet **New-HostedContentFilterPolicy** y una regla de filtro de correo no deseado exclusivo (filtros de destinatarios) mediante el cmdlet **New-HostedContentFilterRule.** Para obtener instrucciones, [vea Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).

En este ejemplo se crea una nueva directiva de filtro de correo no deseado denominada Departamento de investigación con la siguiente configuración:

- La acción de todos los veredictos de filtrado de correo no deseado se establece en Cuarentena.
- La directiva de cuarentena personalizada denominada NoAccess que asigna **ningún** permiso de acceso reemplaza a las directivas de cuarentena predeterminadas que aún **no** asignan permisos de acceso de forma predeterminada.

```powershell
New-HostedContentFilterPolicy -Name "Research Department" -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).

En este ejemplo se modifica la directiva de filtro de correo no deseado existente denominada Recursos humanos. La acción del veredicto de cuarentena de correo no deseado se establece en Cuarentena y se asigna la directiva de cuarentena personalizada denominada NoAccess.

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).

### <a name="anti-phishing-policies"></a>Directivas de protección contra phishing

La inteligencia de suplantación está disponible en EOP y Defender para Office 365. La protección de suplantación de usuario, la protección de suplantación de dominio y la inteligencia de buzones de correo solo están disponibles en Defender para Office 365. Para obtener más información, consulte [Directivas contra la suplantación de identidad en Microsoft 365 ](set-up-anti-phishing-policies.md).

1. En el portal de Microsoft 365 Defender, vaya a Correo electrónico **y** & directivas de colaboración & reglas de amenazas Directivas contra suplantación de identidad en \>  \>  \>  la **sección** Reglas.

   O bien, para ir directamente a la **página Directivas de correo no** deseado de ant, use <https://security.microsoft.com/antiphishing> .

2. En la **página Anti-phishing,** siga uno de los pasos siguientes:
   - Busque y seleccione una directiva anti-phishing existente.
   - Crear una nueva directiva contra suplantación de identidad.

3. Realice uno de los pasos siguientes:
   - **Editar existente:** seleccione la directiva haciendo clic en el nombre de la directiva. En el control desplegable de detalles de la directiva, vaya a la **sección Configuración de** protección y, a continuación, haga clic en Editar configuración de **protección.**
   - **Crear nuevo:** en el asistente para nueva directiva, acceda a la **página** Acciones.

4. En la **página Configuración de** protección, compruebe que las siguientes opciones de configuración estén activadas y configuradas según sea necesario:
   - **Usuarios habilitados para proteger**: Especificar usuarios.
   - **Dominios habilitados para proteger:** seleccione Incluir dominios de mi **propiedad** o Incluir dominios **personalizados** y especifique los dominios.
   - **Habilitar la inteligencia de buzones**
   - **Habilitar la inteligencia para la protección de suplantación**
   - **Habilitar la inteligencia de suplantación**

5. Realice uno de los pasos siguientes:
   - **Editar existente:** en el control desplegable de detalles de la directiva, vaya a la **sección** Acciones y, a continuación, haga clic **en Editar acciones**.
   - **Crear nuevo:** en el asistente para nueva directiva, acceda a la **página** Acciones.

6. En la **página** Acciones, cada  veredicto que tenga la acción Cuarentena del mensaje también tendrá el cuadro **Aplicar** directiva de cuarentena para que seleccione una directiva de cuarentena correspondiente.

   **Nota:** Al crear una nueva directiva, se usa un valor de directiva de cuarentena **Apply** en blanco que indica la directiva de cuarentena predeterminada para esa acción. Cuando más adelante edite la directiva, los valores en blanco se reemplazan por los nombres de directiva de cuarentena predeterminados reales, como se describe en la tabla anterior.

   ![Selecciones de directivas de cuarentena en una directiva contra correo no deseado](../../media/quarantine-tags-in-anti-phishing-policies.png)

Las instrucciones completas para crear y modificar las policías contra suplantación de identidad están disponibles en los siguientes temas:

- [Configuración de directivas contra phishing en EOP](configure-anti-phishing-policies-eop.md)
- [Configurar directivas contra suplantación de identidad en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md)

#### <a name="anti-phishing-policies-in-powershell"></a>Directivas contra suplantación de identidad en PowerShell

Si prefiere usar PowerShell para asignar directivas de cuarentena en directivas contra suplantación de identidad, conéctese a Exchange Online PowerShell o Exchange Online Protection PowerShell y use la siguiente sintaxis:

```powershell
<New-AntiPhishPolicy -Name "<Unique name>" | Set-AntiPhishPolicy -Identity "<Policy name>"> [-EnableSpoofIntelligence $true] [-AuthenticationFailAction Quarantine] [-SpoofQuarantineTag <QuarantineTagName>] [-EnableMailboxIntelligence $true] [-EnableMailboxIntelligenceProtection $true] [-MailboxIntelligenceProtectionAction Quarantine] [-MailboxIntelligenceQuarantineTag <QuarantineTagName>] [-EnableOrganizationDomainsProtection $true] [-EnableTargetedDomainsProtection $true] [-TargetedDomainProtectionAction Quarantine] [-TargetedDomainQuarantineTag <QuarantineTagName>] [-EnableTargetedUserProtection $true] [-TargetedUserProtectionAction Quarantine] [-TargetedUserQuarantineTag <QuarantineTagName>] ...
```

**Notas**:

- Los _\* parámetros Enable_ son necesarios para activar las características de protección específicas. El valor predeterminado de los parámetros _EnableMailboxIntelligence_ y _EnableSpoofIntelligence_ es $true, por lo que no es necesario usar estos parámetros al crear nuevas directivas contra suplantación de identidad en PowerShell. Todos los _demás parámetros Enable \*_ necesitan tener el valor $true para _\*_ poder establecer el valor Cuarentena en los parámetros action correspondientes para asignar una directiva de cuarentena. Ninguno de los _parámetros *\Action_ tiene el valor predeterminado Quarantine.

  Para ver los valores de parámetros importantes en las directivas anti phish existentes, ejecute el siguiente comando:

  ```powershell
  Get-AntiPhishPolicy | Format-List Name,Enable*Intelligence,Enable*Protection,*Action,*QuarantineTag
  ```

  Para obtener información sobre los valores de acción predeterminados y los valores de acción recomendados para Standard y Strict, consulte [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) and [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

- Una acción contra la suplantación de identidad sin un parámetro de directiva de cuarentena correspondiente significa que se usa la directiva de [cuarentena](#step-2-assign-a-quarantine-policy-to-supported-features) predeterminada para ese veredicto.

  Debe reemplazar una directiva de cuarentena predeterminada por una directiva de cuarentena personalizada solo si desea cambiar las capacidades predeterminadas del usuario final en los mensajes en cuarentena para ese veredicto en particular.

- Una nueva directiva contra suplantación de identidad (phishing) en PowerShell requiere una directiva contra suplantación de identidad (configuración) con el cmdlet **New-AntiPhishPolicy** y una regla anti phishing exclusiva (filtros de destinatarios) mediante el cmdlet **New-AntiPhishRule.** Para obtener instrucciones, consulte los temas siguientes:
  - [Usar PowerShell para configurar directivas contra suplantación de identidad en EOP](configure-anti-phishing-policies-eop.md#use-exchange-online-powershell-to-configure-anti-phishing-policies)
  - [Usar Exchange Online PowerShell para configurar directivas contra suplantación de identidad](configure-mdo-anti-phishing-policies.md#use-exchange-online-powershell-to-configure-anti-phishing-policies)

En este ejemplo se crea una nueva directiva contra phishing denominada Departamento de investigación con la siguiente configuración:

- La acción de todos los veredictos de filtrado de correo no deseado se establece en Cuarentena.
- La directiva de cuarentena personalizada denominada NoAccess que asigna **ningún** permiso de acceso reemplaza a las directivas de cuarentena predeterminadas que aún **no** asignan permisos de acceso de forma predeterminada.

```powershell
New-AntiPhishPolicy -Name "Research Department" -AuthenticationFailAction Quarantine -SpoofQuarantineTag NoAccess -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -MailboxIntelligenceQuarantineTag NoAccess -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainProtectionAction Quarantine -TargetedDomainQuarantineTag NoAccess -EnableTargetedUserProtection $true -TargetedUserProtectionAction Quarantine -TargetedUserQuarantineTag NoAccess
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-AntiPhishPolicy](/powershell/module/exchange/new-antiphishpolicy).

En este ejemplo se modifica la directiva anti-phish existente denominada Recursos humanos. La acción para los mensajes detectados por la suplantación de usuario y la suplantación de dominio se establece en Cuarentena y se asigna la directiva de cuarentena personalizada denominada NoAccess.

```powershell
Set-AntiPhishPolicy -Identity "Human Resources" -EnableTargetedDomainsProtection $true -TargetedDomainProtectionAction Quarantine -TargetedDomainQuarantineTag NoAccess -EnableTargetedUserProtection $true -TargetedUserProtectionAction Quarantine -TargetedUserQuarantineTag NoAccess
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-AntiPhishPolicy](/powershell/module/exchange/set-antiphishpolicy).

### <a name="anti-malware-policies"></a>Directivas antimalware

1. En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de \> **colaboración &** Reglas de amenazas Directivas \>  \> **antimalware** en la **sección** Reglas.

   O bien, para ir directamente a la **página Antimalware,** use <https://security.microsoft.com/antimalwarev2> .

2. En la **página Antimalware,** realice uno de los siguientes pasos:
   - Busque y seleccione una directiva antimalware existente.
   - Crear una nueva directiva antimalware.

3. Realice uno de los pasos siguientes:
   - **Editar existente:** seleccione la directiva haciendo clic en el nombre de la directiva. En el control desplegable de detalles de la directiva, vaya a la **sección Configuración de** protección y, a continuación, haga clic en Editar configuración de **protección.**
   - **Crear nuevo:** en el asistente para nueva directiva, acceda a la **página** Acciones.

4. En la **página Configuración de** protección, seleccione una directiva de cuarentena en el cuadro Directiva **de** cuarentena.

   **Nota:** Al crear una nueva  directiva, un valor de directiva de cuarentena en blanco indica la directiva de cuarentena predeterminada para que se utilice. Cuando más adelante edite la directiva, el valor en blanco se reemplaza por el nombre de directiva de cuarentena predeterminado real, tal como se describe en la tabla anterior.

#### <a name="anti-malware-policies-in-powershell"></a>Directivas antimalware en PowerShell

Si prefiere usar PowerShell para asignar directivas de cuarentena en directivas antimalware, conéctese a Exchange Online PowerShell o Exchange Online Protection PowerShell y use la siguiente sintaxis:

```powershell
<New-AntiMalwarePolicy -Name "<Unique name>" | Set-AntiMalwarePolicy -Identity "<Policy name>"> [-QuarantineTag <QuarantineTagName>]
```

**Notas**:

- Debe reemplazar la directiva de cuarentena predeterminada por una directiva de cuarentena personalizada solo si desea cambiar las capacidades predeterminadas del usuario final en los mensajes que se han puesto en cuarentena para malware.

  Para ver los valores de parámetros importantes en las directivas anti phish existentes, ejecute el siguiente comando:

  ```powershell
  Get-MalwareFilterPolicy | Format-Table Name,QuarantineTag
  ```

- Una nueva directiva antimalware en PowerShell requiere una directiva de filtro de malware (configuración) con el cmdlet **New-MalwareFilterPolicy** y una regla de filtro de malware exclusiva (filtros de destinatarios) mediante el cmdlet **New-MalwareFilterRule.** Para obtener instrucciones, [vea Use Exchange Online PowerShell o standalone EOP PowerShell to configure anti-malware policies](configure-anti-malware-policies.md#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-malware-policies).

En este ejemplo se crea una directiva de filtro de malware denominada Departamento de investigación que usa la directiva de cuarentena personalizada denominada NoAccess que asigna **permisos sin** acceso.

```powershell
New-MalwareFilterPolicy -Name "Research Department" -QuarantineTag NoAccess
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-MalwareFilterPolicy](/powershell/module/exchange/new-malwarefilterpolicy).

En este ejemplo se modifica la directiva de filtro de malware existente denominada Recursos humanos mediante la asignación de la directiva de cuarentena personalizada denominada NoAccess que asigna **permisos sin** acceso.

```powershell
New-MalwareFilterPolicy -Identity "Human Resources" -QuarantineTag NoAccess
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-MalwareFilterPolicy](/powershell/module/exchange/set-malwarefilterpolicy).

### <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams

Por lo general, la protección de los datos adjuntos de Caja fuerte para SharePoint, OneDrive y Microsoft Teams no requiere la pertenencia a una directiva de datos adjuntos de Caja fuerte (se activa o desactiva la protección en la configuración **global** de las directivas de datos adjuntos de Caja fuerte). Sin embargo, para asignar una directiva de cuarentena para los mensajes que se han puesto en cuarentena mediante datos adjuntos de Caja fuerte para SharePoint, OneDrive y Microsoft Teams, los usuarios afectados deben asignarse en una directiva de cuarentena.

1. En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & reglas De amenazas Caja fuerte datos adjuntos en \>  \>  \>  la **sección** Reglas.

   O bien, para ir directamente a la **página Caja fuerte datos adjuntos,** use <https://security.microsoft.com/safeattachmentv2> .

2. En la **Caja fuerte datos adjuntos,** siga uno de los pasos siguientes:
   - Busque y seleccione una directiva Caja fuerte datos adjuntos existente.
   - Cree una nueva directiva Caja fuerte datos adjuntos.

3. Realice uno de los pasos siguientes:
   - **Editar existente:** seleccione la directiva haciendo clic en el nombre de la directiva. En el control desplegable de detalles de la directiva, vaya a la Configuración y, **a** continuación, haga clic **en Editar configuración.**
   - **Crear nuevo:** en el asistente para nueva directiva, acceda a la **página Configuración** directiva.

4. En la **Configuración,** seleccione una directiva de cuarentena en el **cuadro Directiva de** cuarentena.

   **Nota:** Al crear una nueva  directiva, un valor de directiva de cuarentena en blanco indica que se usa la directiva de cuarentena predeterminada. Cuando más adelante edite la directiva, el valor en blanco se reemplaza por el nombre de directiva de cuarentena predeterminado real, tal como se describe en la tabla anterior.

Las instrucciones completas para crear y modificar directivas Caja fuerte datos adjuntos se describen en Configurar Caja fuerte de datos adjuntos en [Microsoft Defender para Office 365](set-up-safe-attachments-policies.md).

#### <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-in-powershell"></a>Caja fuerte Datos adjuntos SharePoint, OneDrive y Microsoft Teams en PowerShell

Si prefiere usar PowerShell para asignar directivas de cuarentena para datos adjuntos de Caja fuerte para SharePoint, OneDrive y Microsoft Teams, conéctese Exchange Online PowerShell o PowerShell de Exchange Online Protection y use la sintaxis siguiente:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
<New-SafeAttachmentPolicy -Name "<Unique name>" | Set-SafeAttachmentPolicy -Identity "<Policy name>"> [-QuarantineTag <QuarantineTagName>]
```

**Notas**:

- Debe reemplazar la directiva de cuarentena predeterminada por una directiva de cuarentena personalizada solo si desea cambiar las funcionalidades predeterminadas del usuario final en los archivos que se han puesto en cuarentena por Caja fuerte Attachments for SharePoint, OneDrive y Microsoft Teams.

  Para ver los valores de parámetros importantes, ejecute el siguiente comando:

  ```powershell
  Get-AtpPolicyForO365 | Format-Table EnableATPForSPOTeamsODB; Get-SafeAttachmentPolicy | Format-Table Name,QuarantineTag
  ```

- Para activar Caja fuerte datos adjuntos de SharePoint, OneDrive y Microsoft Teams, vea Activar datos adjuntos de Caja fuerte para [SharePoint, OneDrive y Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).

- Una nueva directiva de datos adjuntos de Caja fuerte en PowerShell requiere una directiva de datos adjuntos seguros (configuración) mediante el cmdlet **New-SafeAttachmentPolicy** y una regla de datos adjuntos seguros exclusiva (filtros de destinatarios) mediante el cmdlet **New-SafeAttachmentRule.** Para obtener instrucciones, vea [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Caja fuerte Attachments policies](set-up-safe-attachments-policies.md#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies).

En este ejemplo se activa Caja fuerte Attachments for SharePoint, OneDrive y Microsoft Teams y, a continuación, se crea una directiva de datos **adjuntos** segura denominada Research Department que usa la directiva de cuarentena personalizada denominada NoAccess que no asigna permisos de acceso.

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
New-SafeAttachmentPolicy -Name "Research Department" -QuarantineTag NoAccess
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-MalwareFilterPolicy](/powershell/module/exchange/new-malwarefilterpolicy).

En este ejemplo se modifica la directiva de datos adjuntos seguros existente denominada Recursos humanos mediante la asignación de la directiva de cuarentena personalizada denominada NoAccess que asigna **permisos sin** acceso.

```powershell
New-SafeAttachmentPolicy -Identity "Human Resources" -QuarantineTag NoAccess
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-MalwareFilterPolicy](/powershell/module/exchange/set-malwarefilterpolicy).

## <a name="configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal"></a>Configurar las opciones de notificación de cuarentena global en el portal de Microsoft 365 Defender web

La configuración global de las directivas de cuarentena permite personalizar las notificaciones de correo no deseado del usuario final que se envían a los destinatarios de los mensajes que se han puesto en cuarentena. Para obtener más información acerca de estas notificaciones, vea [Notificaciones de correo no deseado del usuario final.](use-spam-notifications-to-release-and-report-quarantined-messages.md)

1. En el portal Microsoft 365 Defender, vaya a Correo electrónico **&** sección Directivas de amenazas Sección Directivas de cuarentena y, a continuación, \>  \>  \>  seleccione Directivas **de cuarentena**.

2. En la **página Directiva de** cuarentena, seleccione Configuración **global**.

3. En el **control desplegable De** notificaciones de cuarentena que se abre, configure algunas o todas las opciones siguientes:

   - **Nombre para mostrar:** personalice el nombre para mostrar del remitente que se usa en las notificaciones de correo no deseado del usuario final.

     Para cada idioma que haya agregado, seleccione el idioma del segundo cuadro de idioma (no haga clic en la X) y escriba el valor de texto que desee en el cuadro Nombre **para** mostrar.

     La siguiente captura de pantalla muestra el nombre para mostrar personalizado en una notificación de correo no deseado del usuario final:

     ![Un nombre para mostrar del remitente personalizado en una notificación de correo no deseado del usuario final](../../media/quarantine-tags-esn-customization-display-name.png)

   - **Aviso** de declinación de responsabilidades: agregue un aviso de declinación de responsabilidades personalizado a la parte inferior de las notificaciones de correo no deseado del usuario final. El texto localizado, **Un aviso de declinación de responsabilidades de su organización:** siempre se incluye primero, seguido del texto que especifique.

     Para cada idioma que haya agregado, seleccione el idioma del segundo cuadro de idioma (no haga clic en la X) y escriba el valor de texto que desee en el cuadro **Declinación de** responsabilidades.

     La siguiente captura de pantalla muestra el aviso de declinación de responsabilidades personalizado en una notificación de correo no deseado del usuario final:

     ![Un aviso de declinación de responsabilidades personalizado en la parte inferior de una notificación de correo no deseado para el usuario final](../../media/quarantine-tags-esn-customization-disclaimer.png)

   - **Elegir idioma:** las notificaciones de correo no deseado del usuario final ya están localizadas en función de la configuración de idioma del destinatario. Puede especificar texto personalizado en diferentes idiomas para los valores **Nombre para mostrar** y **Declinación de** responsabilidades.

     Seleccione al menos un idioma en el primer cuadro de idioma y, a continuación, haga clic **en Agregar**. Puede seleccionar varios idiomas haciendo clic **en Agregar** después de cada uno. Un cuadro de idioma de sección muestra todos los idiomas que ha seleccionado:

     ![Idiomas seleccionados en el segundo cuadro de idioma de la configuración de notificación de cuarentena global de directivas de cuarentena](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - **Usar el logotipo de mi** empresa: seleccione esta opción para reemplazar el logotipo predeterminado de Microsoft que se usa en la parte superior de las notificaciones de correo no deseado del usuario final. Antes de hacerlo, debes seguir las instrucciones de Personalizar el [tema Microsoft 365 de](../../admin/setup/customize-your-organization-theme.md) la organización para cargar el logotipo personalizado.

     La siguiente captura de pantalla muestra un logotipo personalizado en una notificación de correo no deseado del usuario final:

     ![Logotipo personalizado en una notificación de correo no deseado del usuario final](../../media/quarantine-tags-esn-customization-logo.png)

   - Enviar notificación de correo no deseado del usuario final **cada (días):** seleccione la frecuencia con la que desea que la notificación del usuario final salga.

## <a name="view-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Ver directivas de cuarentena en el Microsoft 365 Defender web

1. En el portal Microsoft 365 Defender, vaya a Correo electrónico **&** sección Directivas de amenazas Sección Directivas de cuarentena y, a continuación, \>  \>  \>  seleccione Directivas **de cuarentena**.

2. La **página Directiva de** cuarentena muestra la lista de directivas por **Nombre** y Última **fecha actualizada.**

3. Para ver la configuración de directivas de cuarentena integradas o personalizadas, seleccione la directiva de cuarentena de la lista haciendo clic en el nombre.

4. Para ver la configuración global, haga clic **en Configuración global**

### <a name="view-quarantine-policies-in-powershell"></a>Ver directivas de cuarentena en PowerShell

Si prefiere usar PowerShell para ver directivas de cuarentena, siga estos pasos:

- Para ver una lista resumida de todas las directivas integradas o personalizadas, ejecute el siguiente comando:

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- Para ver la configuración de directivas de cuarentena integradas o personalizadas, reemplace por el nombre de la directiva de cuarentena y \<QuarantinePolicyName\> ejecute el siguiente comando:

  ```powershell
  Get-QuarantineTag -Identity "<QuarantinePolicyName>"
  ```

- Para ver la configuración global de las notificaciones de correo no deseado del usuario final, ejecute el siguiente comando:

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).

## <a name="modify-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Modificar directivas de cuarentena en el portal Microsoft 365 Defender web

1. En el portal Microsoft 365 Defender, vaya a Correo electrónico **&** sección Directivas de amenazas Sección Directivas de cuarentena y, a continuación, \>  \>  \>  seleccione Directivas **de cuarentena**.

2. En la **página Directivas de** cuarentena, seleccione la directiva haciendo clic en el nombre.

3. Después de seleccionar la directiva, haga clic en el icono Editar directiva ![ ](../../media/m365-cc-sc-edit-icon.png) **Editar** icono de directiva que aparece.

4. El **Asistente para editar** directivas que  se abre es prácticamente idéntico al Asistente para nueva directiva, tal como se describe en la sección Crear directivas de cuarentena en la sección del portal [de Microsoft 365 Defender](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal) anteriormente en este artículo.

   La diferencia principal es que no se puede cambiar el nombre de una directiva existente.

5. Cuando haya terminado de modificar la directiva, vaya a la página **Resumen y** haga clic en **Enviar**.

### <a name="modify-quarantine-policies-in-powershell"></a>Modificar directivas de cuarentena en PowerShell

Si prefiere usar PowerShell para modificar una directiva de cuarentena personalizada, reemplace por el nombre de la directiva de cuarentena y \<QuarantinePolicyName\> use la sintaxis siguiente:

```powershell
Set-QuarantineTag -Identity "<QuarantinePolicyName>" [Settings]
```

La configuración disponible es la misma que se describe para crear directivas de cuarentena anteriormente en este artículo.

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-QuarantineTag](/powershell/module/exchange/set-quarantinetag).

## <a name="remove-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Quitar directivas de cuarentena en el Microsoft 365 Defender web

**Notas**:

- No puede quitar directivas de cuarentena integradas.
- Antes de quitar una directiva de cuarentena personalizada, compruebe que no se está utilizando. Por ejemplo, ejecute el siguiente comando en PowerShell:

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  Si se usa la directiva de cuarentena, [reemplace la directiva](#step-2-assign-a-quarantine-policy-to-supported-features) de cuarentena asignada antes de quitarla.

1. En el portal Microsoft 365 Defender, vaya a Correo electrónico **&** sección Directivas de amenazas Sección Directivas de cuarentena y, a continuación, \>  \>  \>  seleccione Directivas **de cuarentena**.

2. En la **página Directiva de** cuarentena, seleccione la directiva de cuarentena personalizada que desea quitar haciendo clic en el nombre.

3. Después de seleccionar la directiva, haga clic en el icono Eliminar directiva ![ ](../../media/m365-cc-sc-delete-icon.png) **Eliminar** icono de directiva que aparece.

4. Haga **clic en Quitar** directiva en el cuadro de diálogo de confirmación que aparece.

### <a name="remove-quarantine-policies-in-powershell"></a>Quitar directivas de cuarentena en PowerShell

Si prefiere usar PowerShell para quitar una directiva de cuarentena personalizada, reemplace por el nombre de la directiva de cuarentena y \<QuarantinePolicyName\> ejecute el siguiente comando:

```powershell
Remove-QuarantineTag -Identity "<QuarantinePolicyName>"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).

## <a name="system-alerts-for-quarantine-release-requests"></a>Alertas del sistema para solicitudes de lanzamiento de cuarentena

De forma predeterminada, la  directiva de alerta predeterminada denominada Usuario solicitado para liberar un mensaje en cuarentena genera automáticamente una alerta de gravedad media y envía mensajes de notificación a los miembros de los siguientes grupos de roles siempre que un usuario solicite la publicación de un mensaje en cuarentena:

- Administrador de cuarentena
- Administrador de seguridad
- Administración de la organización (administrador global)

Los administradores pueden personalizar los destinatarios de notificaciones por correo electrónico o crear una directiva de alerta personalizada para opciones adicionales.

Para obtener más información sobre las directivas de alerta, consulte [Directivas de alerta en Microsoft 365](../../compliance/alert-policies.md).

## <a name="quarantine-policy-permission-details"></a>Detalles de permisos de directiva de cuarentena

En las secciones siguientes se describen los efectos de los grupos de permisos preestablecidos y los permisos individuales en los detalles de los mensajes en cuarentena y en las notificaciones de correo no deseado del usuario final.

### <a name="preset-permissions-groups"></a>Grupos de permisos preestablecidos

Los permisos individuales que se incluyen en grupos de permisos preestablecidos se enumeran en la tabla al principio de este artículo.

#### <a name="no-access"></a>Sin acceso

Si la directiva de cuarentena asigna los permisos **Sin** acceso (solo acceso de administrador), los usuarios no podrán ver los mensajes que están en cuarentena:

- **Detalles del mensaje en cuarentena:** no se mostrará ningún mensaje en la vista de usuario final.
- **Notificaciones de correo no deseado del** usuario final: no se enviará ninguna notificación para esos mensajes.

#### <a name="limited-access"></a>Acceso limitado

Si la directiva de cuarentena asigna los **permisos de** acceso limitado, los usuarios obtienen las siguientes funcionalidades:

- **Detalles del mensaje en cuarentena:** los botones siguientes están disponibles:
  - **Versión de solicitud**
  - **Ver encabezados de mensaje**
  - **Vista previa de mensaje**
  - **Quitar de cuarentena**
  - **Bloquear remitente**

  ![Botones disponibles en los detalles del mensaje en cuarentena si la directiva de cuarentena concede al usuario permisos de acceso limitado](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- **Notificaciones de correo no deseado del** usuario final: los botones siguientes están disponibles:
  - **Bloquear remitente**
  - **Versión de solicitud**
  - **Revisar**

  ![Botones disponibles en la notificación de correo no deseado del usuario final si la directiva de cuarentena concede al usuario permisos de acceso limitado](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a>Acceso completo

Si la directiva de cuarentena asigna los **permisos de** acceso completo (todos los permisos disponibles), los usuarios obtienen las siguientes funcionalidades:

- **Detalles del mensaje en cuarentena:** los botones siguientes están disponibles:
  - **Mensaje de versión**
  - **Ver encabezados de mensaje**
  - **Vista previa de mensaje**
  - **Quitar de cuarentena**
  - **Bloquear remitente**

  ![Botones disponibles en los detalles del mensaje en cuarentena si la directiva de cuarentena concede al usuario permisos de acceso total](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- **Notificaciones de correo no deseado del** usuario final: los botones siguientes están disponibles:
  - **Bloquear remitente**
  - **Liberar**
  - **Revisar**

  ![Botones disponibles en la notificación de correo no deseado del usuario final si la directiva de cuarentena concede al usuario permisos de acceso completo](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a>Permisos individuales

#### <a name="block-sender-permission"></a>Bloquear el permiso del remitente

El **permiso bloquear remitente** (_PermissionToBlockSender_) controla el acceso al botón que permite a los usuarios agregar cómodamente el remitente del mensaje en cuarentena a su lista de remitentes bloqueados.

- **Detalles del mensaje en cuarentena:**
  - **Bloquear permiso de** remitente habilitado: el **botón Bloquear remitente** está disponible.
  - **Bloquear el permiso** del remitente deshabilitado: **el botón Bloquear remitente** no está disponible.

- **Notificaciones de correo no deseado del usuario final:**
  - **Bloquear permiso de** remitente habilitado: el **botón Bloquear remitente** está disponible.
  - **Bloquear el permiso** del remitente deshabilitado: **el botón Bloquear remitente** no está disponible.

Para obtener más información acerca de la lista Remitentes bloqueados, vea [Bloquear](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) mensajes de alguien y Usar Exchange Online PowerShell para configurar la colección de listas seguras [en un buzón.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)

#### <a name="delete-permission"></a>Permiso de eliminación

El **permiso Delete** (_PermissionToDelete_) controla la capacidad de los usuarios para eliminar sus mensajes (mensajes donde el usuario es un destinatario) de la cuarentena.

- **Detalles del mensaje en cuarentena:**
  - **Permisos** de eliminación habilitados: **el botón Quitar de cuarentena** está disponible.
  - **Eliminar** permiso deshabilitado: el **botón Quitar de cuarentena** no está disponible.

- **Notificaciones de correo no deseado del usuario final:** Sin efecto.

#### <a name="preview-permission"></a>Permiso de vista previa

El **permiso Vista** previa (_PermissionToPreview_) controla la capacidad de los usuarios para obtener una vista previa de sus mensajes en cuarentena.

- **Detalles del mensaje en cuarentena:**
  - **Permiso** de vista previa habilitado: **el botón Vista previa del** mensaje está disponible.
  - **Permiso** de vista previa deshabilitado: **el botón Vista previa del** mensaje no está disponible.

- **Notificaciones de correo no deseado del usuario final:** Sin efecto.

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a>Permitir que los destinatarios liberen un mensaje del permiso de cuarentena

Allow **recipients to release a message from quarantine** permission (_PermissionToRelease_) controla la capacidad de los usuarios para liberar sus mensajes en cuarentena directamente y sin la aprobación de un administrador.

- **Detalles del mensaje en cuarentena:**
  - Permiso habilitado: el **botón Liberar mensaje** está disponible.
  - Permiso deshabilitado: el **botón Liberar mensaje** no está disponible.

- **Notificaciones de correo no deseado del usuario final:**
  - Permiso habilitado: el **botón Liberar** está disponible.
  - Permiso deshabilitado: el **botón Liberar** no está disponible.

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a>Permitir que los destinatarios soliciten un mensaje que se liberará del permiso de cuarentena

Allow **recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages. El mensaje solo se libera después de que un administrador apruebe la solicitud.

- **Detalles del mensaje en cuarentena:**
  - Permiso habilitado: el **botón Solicitar versión** está disponible.
  - Permiso deshabilitado: el **botón Solicitar versión** no está disponible.

- **Notificaciones de correo no deseado del usuario final:**
  - Permiso habilitado: el **botón Solicitar versión** está disponible.
  - Permiso deshabilitado: el **botón Solicitar versión** no está disponible.
