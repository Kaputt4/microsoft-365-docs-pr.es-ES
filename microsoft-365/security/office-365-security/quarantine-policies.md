---
title: Directivas de cuarentena
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: null
ms.date: null
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
  - MET150
ms.assetid: null
ms.collection:
  - M365-security-compliance
ms.custom: null
description: Los administradores pueden aprender a usar directivas de cuarentena para controlar lo que los usuarios pueden hacer con los mensajes en cuarentena.
ms.technology: mdo
ms.prod: m365-security
---

# <a name="quarantine-policies"></a>Directivas de cuarentena

Las directivas de cuarentena (anteriormente conocidas como etiquetas de _cuarentena) en_ Exchange Online Protection (EOP) y Microsoft Defender para Office 365 permiten a los administradores controlar lo que los usuarios pueden hacer con los mensajes en cuarentena en función del motivo por el que el mensaje se ha puesto en cuarentena.

Tradicionalmente, los usuarios se han permitido o denegado niveles de interactividad para los mensajes en cuarentena en función del motivo por el que el mensaje se ha puesto en cuarentena. Por ejemplo, los usuarios pueden ver y liberar mensajes que fueron puestos en cuarentena por el filtrado contra correo no deseado como correo no deseado o masivo, pero no pueden ver ni liberar mensajes que se han puesto en cuarentena como phishing o malware de elevada confianza.

Para [las características de](#step-2-assign-a-quarantine-policy-to-supported-features) protección admitidas, las directivas de cuarentena especifican lo que los usuarios pueden hacer con sus propios mensajes (mensajes donde son destinatarios) en cuarentena y en notificaciones _de cuarentena_. [Las notificaciones en cuarentena](use-spam-notifications-to-release-and-report-quarantined-messages.md) son el reemplazo de las notificaciones de correo no deseado del usuario final. Estas notificaciones ahora están controladas por directivas de cuarentena y contienen información sobre los mensajes en cuarentena para todas las características de protección admitidas (no solo directivas contra correo no deseado y veredictos de directivas contra suplantación de identidad).

Las directivas de cuarentena predeterminadas que aplican las capacidades históricas del usuario se asignan automáticamente a las acciones de las características de protección admitidas que ponen en cuarentena los mensajes. O bien, puede crear directivas de cuarentena personalizadas y asignarlas a las características de protección admitidas para permitir o impedir que los usuarios realicen acciones específicas en esos tipos de mensajes en cuarentena.

Los permisos de directiva de cuarentena individuales se combinan en los siguientes grupos de permisos preestablecidos:

- Sin acceso
- Acceso limitado
- Acceso completo

Los permisos de directiva de cuarentena individuales contenidos en los grupos de permisos preestablecidos se describen en la tabla siguiente:

|Permiso|Sin acceso|Acceso limitado|Acceso completo|
|---|:---:|:---:|:---:|
|**Bloquear remitente** (_PermissionToBlockSender_)||![Marca de verificación.](../../media/checkmark.png)|![Marca de verificación.](../../media/checkmark.png)|
|**Delete** (_PermissionToDelete_)||![Marca de verificación.](../../media/checkmark.png)|![Marca de verificación.](../../media/checkmark.png)|
|**Vista** previa (_PermissionToPreview_)||![Marca de verificación.](../../media/checkmark.png)|![Marca de verificación.](../../media/checkmark.png)|
|**Permitir que los destinatarios liberen un mensaje de cuarentena** (_PermissionToRelease_)|||![Marca de verificación.](../../media/checkmark.png)|
|**Permitir que los destinatarios soliciten que un mensaje se ponga en cuarentena** (_PermissionToRequestRelease_)||![Marca de verificación](../../media/checkmark.png)||

Las directivas de cuarentena predeterminadas, sus grupos de permisos asociados y si las notificaciones de cuarentena están habilitadas se describen en la tabla siguiente:

|Directiva de cuarentena predeterminada|Grupo de permisos usado|¿Notificaciones en cuarentena habilitadas?|
|---|---|---|
|AdminOnlyAccessPolicy|Sin acceso|No|
|DefaultFullAccessPolicy|Acceso completo|No|
|NotificationEnabledPolicy<sup>\*</sup>|Acceso completo|Sí|

Si no le gustan los permisos predeterminados en los grupos de permisos preestablecidos o si desea habilitar las notificaciones de cuarentena, cree y use directivas de cuarentena personalizadas. Para obtener más información acerca de lo que hace cada permiso, vea la sección Detalles de permisos de directiva [de cuarentena](#quarantine-policy-permission-details) más adelante en este artículo.

Puede crear y asignar directivas de cuarentena en el portal de Microsoft 365 Defender o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones de correo de Exchange Online; PowerShell de EOP independiente en organizaciones EOP sin Exchange Online buzones de correo).

> [!NOTE]
> El tiempo durante el que los mensajes en cuarentena se mantienen en cuarentena antes de que expiren se controla mediante la conservación del **correo** no deseado en cuarentena durante estos muchos días (_QuarantineRetentionPeriod_) en directivas contra correo no deseado. Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).
>
> Si cambia la directiva de cuarentena asignada a una característica de protección compatible, el cambio afecta a los mensajes que se ponen en cuarentena  después de realizar el cambio. La configuración de la nueva asignación de directivas de cuarentena no afecta a los mensajes que anteriormente estaban en cuarentena por esa característica de protección.

## <a name="full-access-permissions-and-quarantine-notifications"></a>Permisos de acceso completo y notificaciones de cuarentena

<sup>\*</sup> La directiva de cuarentena denominada NotificationEnabledPolicy no está presente en todos los entornos. Tendrás la directiva de cuarentena NotificationEnabledPolicy si tu organización cumple los dos requisitos siguientes:

- La organización existía antes de que se haya activado la característica de directiva de cuarentena (finales de julio o principios de agosto de 2021).
- Tenías una o varias directivas contra correo no [deseado (la](configure-your-spam-filter-policies.md) directiva contra correo no deseado predeterminada o directivas **personalizadas** contra correo no deseado) donde la configuración Habilitar notificaciones de correo no deseado del usuario final estaba activada.

Como se describió anteriormente, las notificaciones de cuarentena en directivas de cuarentena reemplazan las notificaciones de correo no deseado del usuario final que usó para activar o desactivar en directivas contra correo no deseado. La directiva de cuarentena integrada denominada DefaultFullAccessPolicy duplica los permisos _históricos_ para los mensajes en cuarentena, pero las notificaciones de cuarentena no están _activadas_ en la directiva de cuarentena. Además, como no puede modificar la directiva integrada, no puede activar las notificaciones en cuarentena en DefaultFullAccessPolicy.

Para proporcionar los permisos de DefaultFullAccessPolicy pero con las notificaciones en cuarentena activadas, creamos la directiva denominada NotificationEnabledPolicy para usarla en lugar de DefaultFullAccessPolicy para aquellas organizaciones que lo necesitaban (organizaciones donde se activaron las notificaciones de correo no deseado del usuario final).

Para las organizaciones nuevas o las organizaciones anteriores que nunca tenían habilitadas las notificaciones de correo no deseado del usuario final en directivas contra correo no deseado, no tendrá la directiva de cuarentena denominada NotificationEnabledPolicy. La forma de activar las notificaciones de cuarentena es crear y usar directivas de cuarentena personalizadas en las que se activen las notificaciones de cuarentena.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Directivas de** cuarentena, use <https://security.microsoft.com/quarantinePolicies>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Para ver, crear, modificar o quitar directivas de cuarentena, debe ser miembro de los roles Administración de la **organización, Administrador** de seguridad o  Administrador de cuarentena en el portal de Microsoft 365 Defender cuarentena.  Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

## <a name="step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Paso 1: Crear directivas de cuarentena en el portal Microsoft 365 Defender cuarentena

1. En el [portal Microsoft 365 Defender](https://security.microsoft.com), vaya a Correo electrónico **y &** \> directivas de colaboración **& Directivas** \> de amenazas **de** \> reglas en la **sección** Reglas.

2. En la **página Directiva de** cuarentena, haga clic en ![Agregar icono de directiva personalizada.](../../media/m365-cc-sc-create-icon.png) **Agregar directiva personalizada**.

3. Se **abrirá el Asistente para nueva** directiva. En la **página Nombre de** directiva, escriba un nombre breve pero único en el **cuadro Nombre de** directiva. Deberá identificar y seleccionar la directiva de cuarentena por su nombre en los próximos pasos. Cuando termine, haga clic en **Siguiente**.

4. En la **página Acceso a mensajes de** destinatario, seleccione uno de los siguientes valores:
   - **Acceso limitado**: los permisos individuales que se incluyen en este grupo de permisos se describen anteriormente en este artículo.
   - **Establecer acceso específico (avanzado):** Use este valor para especificar permisos personalizados. Configure las siguientes opciones que aparecen:
     - **Seleccionar preferencia de acción de lanzamiento**: seleccione uno de los siguientes valores:
       - En blanco: este es el valor predeterminado.
       - **Permitir que los destinatarios liberen un mensaje de cuarentena**
       - **Permitir que los destinatarios soliciten un mensaje que se liberará de la cuarentena**
     - **Seleccionar acciones adicionales que los destinatarios pueden realizar en mensajes en** cuarentena: seleccione algunos, todos o ninguno de los siguientes valores:
       - **Eliminar**
       - **Versión preliminar**
       - **Bloquear remitente**

   Estos permisos y su efecto en los mensajes en cuarentena y en las notificaciones de cuarentena se describen en la sección [Detalles](#quarantine-policy-permission-details) de permisos de directiva de cuarentena más adelante en este artículo.

   Cuando termine, haga clic en **Siguiente**.

5. En la **página Notificación de correo no** deseado del usuario final, seleccione **Habilitar** para habilitar las notificaciones de cuarentena (anteriormente conocidas como notificaciones de correo no deseado del usuario final). Cuando termine, haga clic en **Siguiente**.

   > [!NOTE]
   > Como se explicó anteriormente, las directivas integradas (AdminOnlyAccessPolicy o DefaultFullAccessPolicy) no tienen notificaciones en cuarentena activadas y no puede modificar las directivas.

6. En la **página Revisar directiva** , revisa la configuración. Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Enviar**.

7. En la página de confirmación que aparece, haga clic en **Listo**.

Ahora ya está listo para asignar la directiva de cuarentena a una característica de cuarentena, tal como se describe en la [sección Paso 2](#step-2-assign-a-quarantine-policy-to-supported-features) .

### <a name="create-quarantine-policies-in-powershell"></a>Crear directivas de cuarentena en PowerShell

Si prefiere usar PowerShell para crear directivas de cuarentena, conéctese Exchange Online PowerShell o Exchange Online Protection PowerShell y use el cmdlet **New-QuarantinePolicy**.

> [!NOTE]
> Si no usa el parámetro _ESNEnabled_ `$true`y el valor , las notificaciones de cuarentena se desactivarán.

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a>Usar el parámetro EndUserQuarantinePermissionsValue

Para crear una directiva de cuarentena mediante el _parámetro EndUserQuarantinePermissionsValue_ , use la siguiente sintaxis:

```powershell
New-QuarantinePolicy -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236> [-EsnEnabled $true]
```

El _parámetro EndUserQuarantinePermissionsValue_ usa un valor decimal que se convierte a partir de un valor binario. El valor binario corresponde a los permisos de cuarentena de usuario final disponibles en un orden específico. Para cada permiso, el valor 1 es True y el valor 0 es False.

El orden y los valores necesarios para cada permiso individual se describen en la tabla siguiente:

|Permiso|Valor decimal|Valor binario|
|---|:---:|:---:|
|PermissionToViewHeader<sup>\*</sup>|128|10000000|
|PermissionToDownload<sup>\*\*</sup>|64|01000000|
|PermissionToAllowSender<sup>\*\*</sup>|32|00100000|
|PermissionToBlockSender|16|00010000|
|PermissionToRequestRelease<sup>\*\*\*</sup>|8 |00001000|
|PermissionToRelease<sup>\*\*\*</sup>|4|00000100|
|PermissionToPreview|2|00000010|
|PermissionToDelete|1|00000001|

<sup>\*</sup>El valor 0 no oculta el botón Ver encabezado  del mensaje en los detalles del mensaje en cuarentena (el botón siempre está disponible).

<sup>\*\*</sup> Esta configuración no se usa (el valor 0 o 1 no hace nada).

<sup>\*\*\*</sup> No establezca ambos valores en 1. Establezca uno en 1 y el otro en 0, o establezca ambos en 0.

Para los permisos de acceso limitado, los valores requeridos son:

|Permiso|Acceso limitado|
|---|:--:|
|PermissionToViewHeader|0|
|PermissionToDownload|0|
|PermissionToAllowSender|0|
|PermissionToBlockSender|1|
|PermissionToRequestRelease|1|
|PermissionToRelease|0|
|PermissionToPreview|1|
|PermissionToDelete|1|
|Valor binario|00011011|
|Valor decimal que se usará|27|

En este ejemplo se crea una nueva directiva de cuarentena denominada LimitedAccess con notificaciones de cuarentena activadas que asigna los permisos de acceso limitado, tal como se describe en la tabla anterior.

```powershell
New-QuarantinePolicy -Name LimitedAccess -EndUserQuarantinePermissionsValue 27 -EsnEnabled $true
```

Para los permisos personalizados, use la tabla anterior para obtener el valor binario que corresponde a los permisos que desea. Convierta el valor binario en un valor decimal y use el valor decimal para el parámetro _EndUserQuarantinePermissionsValue_ . No use el valor binario para el valor del parámetro.

Para obtener información detallada sobre la sintaxis y los parámetros, [consulte New-QuarantinePolicy](/powershell/module/exchange/new-quarantinepolicy).

## <a name="step-2-assign-a-quarantine-policy-to-supported-features"></a>Paso 2: Asignar una directiva de cuarentena a las características compatibles

En _las características de_ protección admitidas que ponen en cuarentena los mensajes de correo electrónico, puede asignar una directiva de cuarentena a las acciones de cuarentena disponibles. En la tabla siguiente se describen las características que ponen en cuarentena los mensajes y la disponibilidad de las directivas de cuarentena:

|Característica|¿Se admiten directivas de cuarentena?|Directivas de cuarentena predeterminadas usadas|
|---|:---:|---|
|[Directivas contra correo no deseado](configure-your-spam-filter-policies.md): <ul><li>**Correo no** deseado (_SpamAction_)</li><li>**Correo no deseado de elevada** confianza (_HighConfidenceSpamAction_)</li><li>**Phishing** (_PhishSpamAction_)</li><li>**Phishing de elevada confianza** (_HighConfidencePhishAction_)</li><li>**Bulk** (_BulkSpamAction_)</li></ul>|Sí|<ul><li>DefaultFullAccessPolicy<sup>\*</sup> (acceso completo)</li><li>DefaultFullAccessPolicy<sup>\*</sup> (acceso completo)</li><li>DefaultFullAccessPolicy<sup>\*</sup> (acceso completo)</li><li>AdminOnlyAccessPolicy (sin acceso)</li><li>DefaultFullAccessPolicy<sup>\*</sup> (acceso completo)</li></ul>|
|Directivas de protección contra phishing: <ul><li>[Protección de inteligencia suplantada](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</li><li>[Protección de suplantación en Defender para Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<ul><li>**Si el mensaje se detecta como un usuario suplantado** (_TargetedUserProtectionAction_)</li><li>**Si el mensaje se detecta como un dominio suplantado** (_TargetedDomainProtectionAction_)</li><li>**Si la inteligencia de buzones detecta y suplanta al usuario** (_MailboxIntelligenceProtectionAction_)</li></ul></li></ul>|Sí|<ul><li>DefaultFullAccessPolicy<sup>\*</sup> (acceso completo)</li><li>Protección de suplantación:<ul><li>DefaultFullAccessPolicy<sup>\*</sup> (acceso completo)</li><li>DefaultFullAccessPolicy<sup>\*</sup> (acceso completo)</li><li>DefaultFullAccessPolicy<sup>\*</sup> (acceso completo)</li></ul></li></ul>|
|[Directivas antimalware](configure-anti-malware-policies.md): todos los mensajes detectados siempre se ponen en cuarentena.|Sí|AdminOnlyAccessPolicy (sin acceso)|
|[Caja fuerte de datos adjuntos](safe-attachments.md): <ul><li>Mensajes de correo electrónico con datos adjuntos que se ponen en cuarentena como malware Caja fuerte directivas de datos adjuntos (_Habilitar_ y _acción_)</li><li>Archivos en cuarentena como malware [por Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li></ul>|<ul><li>Sí</li><li>No</li></ul>|<ul><li>AdminOnlyAccessPolicy (sin acceso)</li><li>N/D</li></ul>|
|[Reglas de flujo de](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) correo (también conocidas como reglas de transporte) con la acción: **Entregar el mensaje a la cuarentena** hospedada (_cuarentena_).|No|N/D|

<sup>\*</sup> Como [se describió anteriormente en este artículo](#full-access-permissions-and-quarantine-notifications), su organización podría usar NotificationEnabledPolicy en lugar de DefaultFullAccessPolicy. La única diferencia entre estas dos directivas de cuarentena es que las notificaciones de cuarentena se activarán en NotificationEnabledPolicy y se desactivarán en DefaultFullAccessPolicy.

Las directivas de cuarentena predeterminadas, los grupos de permisos preestablecidos y los permisos se describen al [principio de este artículo](#quarantine-policies) y [más adelante en este artículo](#preset-permissions-groups).

> [!NOTE]
> Si está satisfecho con los permisos predeterminados del usuario final y las notificaciones de cuarentena que proporcionan (o no se proporcionan) las directivas de cuarentena predeterminadas, no necesita hacer nada. Si desea agregar o quitar funcionalidades de usuario final (los botones disponibles) para los mensajes en cuarentena del usuario, o habilitar las notificaciones de cuarentena y agregar o quitar las mismas capacidades en las notificaciones de cuarentena, puede asignar una directiva de cuarentena diferente a la acción de cuarentena.

## <a name="assign-quarantine-policies-in-supported-policies-in-the-microsoft-365-defender-portal"></a>Asignar directivas de cuarentena en directivas admitidas en el portal Microsoft 365 Defender web

### <a name="anti-spam-policies"></a>Directivas contra correo no deseado

1. En el [portal de Microsoft 365 Defender](https://security.microsoft.com), vaya a Correo electrónico **&** \> directivas de **colaboración &** \> **reglas de** \> amenazas Directivas contra correo no deseado en la **sección** Directivas.

   O bien, para ir directamente a la **página Directivas de correo no** deseado de ant, use <https://security.microsoft.com/antispam>.

2. En la **página Directivas contra correo** no deseado, siga uno de estos pasos:
   - Busque y seleccione una directiva **contra** correo no deseado entrante existente.
   - Cree una nueva **directiva contra** correo no deseado entrante.

3. Realice uno de los pasos siguientes:
   - **Editar existente**: seleccione la directiva haciendo clic en el nombre de la directiva. En el control desplegable de detalles de la directiva, vaya a la **sección Acciones** y, a continuación, haga clic **en Editar acciones**.
   - **Crear nuevo**: en el asistente para nueva directiva, acceda a la **página** Acciones.

4. En la **página** Acciones, cada veredicto que  tenga la acción Mensaje de cuarentena también tendrá el cuadro **Seleccionar** directiva de cuarentena para que seleccione una directiva de cuarentena correspondiente.

   **Nota**: Al crear una nueva directiva, se usa un valor de directiva de cuarentena **Select** en blanco que indica la directiva de cuarentena predeterminada para ese veredicto. Cuando más adelante edite la directiva, los valores en blanco se reemplazan por los nombres de directiva de cuarentena predeterminados reales, como se describe en la tabla anterior.

   :::image type="content" source="../../media/quarantine-tags-in-anti-spam-policies.png" alt-text="Selecciones de directiva de cuarentena en una directiva contra correo no deseado" lightbox="../../media/quarantine-tags-in-anti-spam-policies.png":::

Las instrucciones completas para crear y modificar directivas contra correo no deseado se describen en [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

#### <a name="anti-spam-policies-in-powershell"></a>Directivas contra correo no deseado en PowerShell

Si prefiere usar PowerShell para asignar directivas de cuarentena en directivas contra correo no deseado, conéctese a Exchange Online PowerShell o Exchange Online Protection PowerShell y use la siguiente sintaxis:

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>"> [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

**Notas**:

- El valor predeterminado de los parámetros _PhishSpamAction_ y _HighConfidencePhishAction_ es Quarantine, por lo que no es necesario usar esos parámetros al crear nuevas directivas de filtro de correo no deseado en PowerShell. Para los parámetros _SpamAction_, _HighConfidenceSpamAction_ y _BulkSpamAction_ en directivas contra correo no deseado nuevas o existentes, la directiva de cuarentena solo es eficaz si el valor es Quarantine.

  Para ver los valores de parámetros importantes en las directivas contra correo no deseado existentes, ejecute el siguiente comando:

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*SpamAction,HighConfidencePhishAction,*QuarantineTag
  ```

  Para obtener información sobre los valores de acción predeterminados y los valores de acción recomendados para Standard y Strict, consulte [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).

- Al crear nuevas directivas contra correo no deseado, se usa un veredicto de filtrado de correo no deseado [](#step-2-assign-a-quarantine-policy-to-supported-features) sin un parámetro de directiva de cuarentena correspondiente.

  Debe reemplazar una directiva de cuarentena predeterminada por una directiva de cuarentena personalizada solo si desea cambiar las funcionalidades predeterminadas del usuario final en los mensajes en cuarentena para ese veredicto de filtrado de correo no deseado en particular.

- Una nueva directiva contra correo no deseado en PowerShell requiere una directiva de filtro de correo no deseado (configuración) mediante el cmdlet **New-HostedContentFilterPolicy** y una regla de filtro de correo no deseado exclusivo (filtros de destinatarios) mediante el cmdlet **New-HostedContentFilterRule** . Para obtener instrucciones, [vea Usar PowerShell para crear directivas contra correo no deseado](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).

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

La inteligencia de suplantación está disponible en EOP y Defender para Office 365. La protección de suplantación de usuario, la protección de suplantación de dominio y la inteligencia de buzones solo están disponibles en Defender para Office 365. Para obtener más información, consulte [Directivas contra la suplantación de identidad en Microsoft 365 ](set-up-anti-phishing-policies.md).

1. En el [portal de Microsoft 365 Defender](https://security.microsoft.com), vaya a Correo electrónico **y &** \> directivas de **colaboración &** \> **reglas de** \> amenazas **Directivas contra suplantación** de identidad en la **sección** Directivas.

   O bien, para ir directamente a la **página Directivas de correo no** deseado de ant, use <https://security.microsoft.com/antiphishing>.

2. En la **página Anti-phishing** , siga uno de los pasos siguientes:
   - Busque y seleccione una directiva anti-phishing existente.
   - Crear una nueva directiva contra suplantación de identidad.

3. Realice uno de los pasos siguientes:
   - **Editar existente**: seleccione la directiva haciendo clic en el nombre de la directiva. En el control desplegable de detalles de la directiva, vaya a la **sección Configuración de protección** y, a continuación, haga clic **en Editar configuración de protección**.
   - **Crear nuevo**: en el asistente para nueva directiva, acceda a la **página** Acciones.

4. En la **página Configuración de** protección, compruebe que las siguientes opciones de configuración estén activadas y configuradas según sea necesario:
   - **Usuarios habilitados para proteger**: especifique usuarios.
   - **Dominios habilitados para proteger**: seleccione **Incluir dominios de mi propiedad** o Incluir dominios **personalizados** y especifique los dominios.
   - **Habilitar la inteligencia de buzones**
   - **Habilitar la inteligencia para la protección de suplantación**
   - **Habilitar la inteligencia de suplantación**

5. Realice uno de los pasos siguientes:
   - **Editar existente**: en el control desplegable de detalles de la directiva, vaya a la **sección** Acciones y, a continuación, haga clic **en Editar acciones**.
   - **Crear nuevo**: en el asistente para nueva directiva, acceda a la **página** Acciones.

6. En la **página** Acciones, cada veredicto que  tenga la acción Cuarentena del mensaje también tendrá el cuadro **Aplicar** directiva de cuarentena para que seleccione una directiva de cuarentena correspondiente.

   **Nota**: Al crear una nueva directiva, se usa un valor de directiva de cuarentena **Apply** en blanco que indica la directiva de cuarentena predeterminada para esa acción. Cuando más adelante edite la directiva, los valores en blanco se reemplazan por los nombres de directiva de cuarentena predeterminados reales, como se describe en la tabla anterior.

   :::image type="content" source="../../media/quarantine-tags-in-anti-phishing-policies.png" alt-text="Selecciones de directiva de cuarentena en una directiva contra suplantación de identidad" lightbox="../../media/quarantine-tags-in-anti-phishing-policies.png":::

Las instrucciones completas para crear y modificar directivas contra suplantación de identidad están disponibles en los siguientes temas:

- [Configuración de directivas contra phishing en EOP](configure-anti-phishing-policies-eop.md)
- [Configurar directivas contra suplantación de identidad en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md)

#### <a name="anti-phishing-policies-in-powershell"></a>Directivas contra suplantación de identidad en PowerShell

Si prefiere usar PowerShell para asignar directivas de cuarentena en directivas contra suplantación de identidad, conéctese a Exchange Online PowerShell o Exchange Online Protection PowerShell y use la siguiente sintaxis:

```powershell
<New-AntiPhishPolicy -Name "<Unique name>" | Set-AntiPhishPolicy -Identity "<Policy name>"> [-EnableSpoofIntelligence $true] [-AuthenticationFailAction Quarantine] [-SpoofQuarantineTag <QuarantineTagName>] [-EnableMailboxIntelligence $true] [-EnableMailboxIntelligenceProtection $true] [-MailboxIntelligenceProtectionAction Quarantine] [-MailboxIntelligenceQuarantineTag <QuarantineTagName>] [-EnableOrganizationDomainsProtection $true] [-EnableTargetedDomainsProtection $true] [-TargetedDomainProtectionAction Quarantine] [-TargetedDomainQuarantineTag <QuarantineTagName>] [-EnableTargetedUserProtection $true] [-TargetedUserProtectionAction Quarantine] [-TargetedUserQuarantineTag <QuarantineTagName>] ...
```

**Notas**:

- Los _parámetros Enable\*_ son necesarios para activar las características de protección específicas. El valor predeterminado de los parámetros _EnableMailboxIntelligence_ y _EnableSpoofIntelligence_ es $true, por lo que no es necesario usar estos parámetros al crear nuevas directivas contra suplantación de identidad en PowerShell. Todos los _demás parámetros Enable\*_ necesitan tener el valor $true para poder establecer el valor Quarantine _\*_ en los parámetros action correspondientes para asignar una directiva de cuarentena. Ninguno de los _parámetros *\Action_ tiene el valor predeterminado Quarantine.

  Para ver los valores de parámetros importantes en las directivas anti phish existentes, ejecute el siguiente comando:

  ```powershell
  Get-AntiPhishPolicy | Format-List Name,Enable*Intelligence,Enable*Protection,*Action,*QuarantineTag
  ```

  Para obtener información sobre los valores de acción predeterminados y los valores de acción recomendados para Standard y Strict, consulte [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) and [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

- Al crear directivas contra suplantación de identidad (phishing), se usa una acción contra suplantación de identidad [](#step-2-assign-a-quarantine-policy-to-supported-features) sin un parámetro de directiva de cuarentena correspondiente.

  Debe reemplazar una directiva de cuarentena predeterminada por una directiva de cuarentena personalizada solo si desea cambiar las capacidades predeterminadas del usuario final en los mensajes en cuarentena para ese veredicto en particular.

- Una nueva directiva contra suplantación de identidad (phishing) en PowerShell requiere una directiva contra suplantación de identidad (configuración) con el cmdlet **New-AntiPhishPolicy** y una regla anti phishing exclusiva (filtros de destinatarios) mediante el cmdlet **New-AntiPhishRule** . Para obtener instrucciones, consulte los temas siguientes:
  - [Usar PowerShell para configurar directivas contra suplantación de identidad en EOP](configure-anti-phishing-policies-eop.md#use-exchange-online-powershell-to-configure-anti-phishing-policies)
  - [Usar Exchange Online PowerShell para configurar directivas contra suplantación de identidad](configure-mdo-anti-phishing-policies.md#use-exchange-online-powershell-to-configure-anti-phishing-policies)

En este ejemplo se crea una nueva directiva contra phishing denominada Departamento de investigación con la siguiente configuración:

- La acción de todos los veredictos de filtrado de correo no deseado se establece en Cuarentena.
- La directiva de cuarentena personalizada denominada NoAccess que asigna **ningún** permiso de acceso reemplaza a las directivas de cuarentena predeterminadas que aún **no** asignan permisos de acceso de forma predeterminada.

```powershell
New-AntiPhishPolicy -Name "Research Department" -AuthenticationFailAction Quarantine -SpoofQuarantineTag NoAccess -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -MailboxIntelligenceQuarantineTag NoAccess -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainProtectionAction Quarantine -TargetedDomainQuarantineTag NoAccess -EnableTargetedUserProtection $true -TargetedUserProtectionAction Quarantine -TargetedUserQuarantineTag NoAccess
```

Para obtener información detallada sobre la sintaxis y los parámetros, [consulte New-AntiPhishPolicy](/powershell/module/exchange/new-antiphishpolicy).

En este ejemplo se modifica la directiva anti-phish existente denominada Recursos humanos. La acción para los mensajes detectados por la suplantación de usuario y la suplantación de dominio se establece en Cuarentena y se asigna la directiva de cuarentena personalizada denominada NoAccess.

```powershell
Set-AntiPhishPolicy -Identity "Human Resources" -EnableTargetedDomainsProtection $true -TargetedDomainProtectionAction Quarantine -TargetedDomainQuarantineTag NoAccess -EnableTargetedUserProtection $true -TargetedUserProtectionAction Quarantine -TargetedUserQuarantineTag NoAccess
```

Para obtener información detallada sobre la sintaxis y los parámetros, [consulte Set-AntiPhishPolicy](/powershell/module/exchange/set-antiphishpolicy).

### <a name="anti-malware-policies"></a>Directivas antimalware

1. En el [portal Microsoft 365 Defender](https://security.microsoft.com), vaya a Correo electrónico **&** \> directivas de **colaboración &** \> **reglas de** \> amenazas **Directivas antimalware** en la **sección** Directivas.

   O bien, para ir directamente a la **página Antimalware** , use <https://security.microsoft.com/antimalwarev2>.

2. En la **página Antimalware** , realice uno de los siguientes pasos:
   - Busque y seleccione una directiva antimalware existente.
   - Crear una nueva directiva antimalware.

3. Realice uno de los pasos siguientes:
   - **Editar existente**: seleccione la directiva haciendo clic en el nombre de la directiva. En el control desplegable de detalles de la directiva, vaya a la **sección Configuración de protección** y, a continuación, haga clic **en Editar configuración de protección**.
   - **Crear nuevo**: en el asistente para nueva directiva, acceda a la **página** Acciones.

4. En la **página Configuración de** protección, seleccione una directiva de cuarentena en el **cuadro Directiva de** cuarentena.

   **Nota**: Al crear una nueva directiva, se usa un  valor de directiva de cuarentena en blanco que indica la directiva de cuarentena predeterminada. Cuando más adelante edite la directiva, el valor en blanco se reemplaza por el nombre de directiva de cuarentena predeterminado real, tal como se describe en la tabla anterior.

#### <a name="anti-malware-policies-in-powershell"></a>Directivas antimalware en PowerShell

Si prefiere usar PowerShell para asignar directivas de cuarentena en directivas antimalware, conéctese a Exchange Online PowerShell o Exchange Online Protection PowerShell y use la siguiente sintaxis:

```powershell
<New-AntiMalwarePolicy -Name "<Unique name>" | Set-AntiMalwarePolicy -Identity "<Policy name>"> [-QuarantineTag <QuarantineTagName>]
```

**Notas**:

- Al crear nuevas directivas antimalware sin usar el parámetro QuarantineTag al crear una nueva directiva antimalware, se usa la directiva de cuarentena predeterminada para detecciones de malware (AdminOnlyAccessPolicy).

  Debe reemplazar la directiva de cuarentena predeterminada por una directiva de cuarentena personalizada solo si desea cambiar las capacidades predeterminadas del usuario final en los mensajes que se ponen en cuarentena como malware.

  Para ver los valores de parámetros importantes en las directivas anti phish existentes, ejecute el siguiente comando:

  ```powershell
  Get-MalwareFilterPolicy | Format-Table Name,QuarantineTag
  ```

- Una nueva directiva antimalware en PowerShell requiere una directiva de filtro de malware (configuración) con el cmdlet **New-MalwareFilterPolicy** y una regla de filtro de malware exclusiva (filtros de destinatarios) mediante el cmdlet **New-MalwareFilterRule** . Para obtener instrucciones, [vea Use Exchange Online PowerShell o standalone EOP PowerShell para configurar directivas antimalware](configure-anti-malware-policies.md#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-malware-policies).

En este ejemplo se crea una directiva de filtro de malware denominada Departamento de investigación que usa la directiva de cuarentena personalizada denominada NoAccess que asigna **permisos sin** acceso a los mensajes en cuarentena.

```powershell
New-MalwareFilterPolicy -Name "Research Department" -QuarantineTag NoAccess
```

Para obtener información detallada sobre la sintaxis y los parámetros, [consulte New-MalwareFilterPolicy](/powershell/module/exchange/new-malwarefilterpolicy).

En este ejemplo se modifica la directiva de filtro de malware existente denominada Recursos humanos mediante la asignación de la directiva de cuarentena personalizada denominada NoAccess que asigna **permisos sin** acceso a los mensajes en cuarentena.

```powershell
New-MalwareFilterPolicy -Identity "Human Resources" -QuarantineTag NoAccess
```

Para obtener información detallada sobre la sintaxis y los parámetros, [consulte Set-MalwareFilterPolicy](/powershell/module/exchange/set-malwarefilterpolicy).

### <a name="safe-attachments-policies-in-defender-for-office-365"></a>Caja fuerte de datos adjuntos en Defender para Office 365

1. En el [portal de Microsoft 365 Defender](https://security.microsoft.com), vaya a Correo electrónico **&** \> directivas de **colaboración** \> & **reglas de** \> amenazas Directivas de **amenazas Caja fuerte datos** adjuntos en la **sección** Directivas.

   O bien, para ir directamente a la **página Caja fuerte datos adjuntos**, use <https://security.microsoft.com/safeattachmentv2>.

2. En la **Caja fuerte datos adjuntos**, siga uno de los pasos siguientes:
   - Busque y seleccione una directiva Caja fuerte datos adjuntos existente.
   - Cree una nueva directiva Caja fuerte datos adjuntos.

3. Realice uno de los pasos siguientes:
   - **Editar existente**: seleccione la directiva haciendo clic en el nombre de la directiva. En el control desplegable de detalles de la directiva, vaya a la **Configuración** y, a continuación, haga clic **en Editar configuración**.
   - **Crear nuevo**: en el asistente para nueva directiva, llegue a la **página Configuración** directiva.

4. En la **Configuración**, siga estos pasos:
   1. **Caja fuerte datos adjuntos respuesta de malware desconocido**: Seleccione **Bloquear**, **Reemplazar** o **Entrega dinámica**.
   2. Seleccione una directiva de cuarentena en el **cuadro Directiva de** cuarentena.

   **Nota**: Al crear una nueva directiva, un valor de  directiva de cuarentena en blanco indica que se usa la directiva de cuarentena predeterminada. Cuando más adelante edite la directiva, el valor en blanco se reemplaza por el nombre de directiva de cuarentena predeterminado real, tal como se describe en la tabla anterior.

Las instrucciones completas para crear y modificar Caja fuerte de datos adjuntos se describen en Configurar Caja fuerte de datos adjuntos en [Microsoft Defender para Office 365](set-up-safe-attachments-policies.md).

#### <a name="safe-attachments-policies-in-powershell"></a>Caja fuerte de datos adjuntos en PowerShell

Si prefiere usar PowerShell para asignar directivas de cuarentena en directivas de datos adjuntos de Caja fuerte, conéctese a Exchange Online PowerShell o Exchange Online Protection PowerShell y use la siguiente sintaxis:

```powershell
<New-SafeAttachmentPolicy -Name "<Unique name>" | Set-SafeAttachmentPolicy -Identity "<Policy name>"> -Enable $true -Action <Block | Replace | DynamicDelivery> [-QuarantineTag <QuarantineTagName>]
```

**Notas**:

- Los _valores del_ parámetro Action Block, Replace o DynamicDelivery pueden dar como resultado mensajes en cuarentena (el valor Allow no pone en cuarentena los mensajes). El valor del _parámetro Action_ solo es significativo cuando el valor del _parámetro Enable_ es `$true`.

- Al crear nuevas directivas de datos adjuntos de Caja fuerte sin usar el parámetro QuarantineTag, se usa la directiva de cuarentena predeterminada para las detecciones de datos adjuntos de Caja fuerte en el correo electrónico (AdminOnlyAccessPolicy).

  Debe reemplazar la directiva de cuarentena predeterminada por una directiva de cuarentena personalizada solo si desea cambiar las capacidades predeterminadas del usuario final en los mensajes de correo electrónico que están en cuarentena mediante directivas de datos adjuntos Caja fuerte datos adjuntos.

  Para ver los valores de parámetros importantes, ejecute el siguiente comando:

  ```powershell
  Get-SafeAttachmentPolicy | Format-List Name,Enable,Action,QuarantineTag
  ```

- Una nueva directiva de datos adjuntos de Caja fuerte en PowerShell requiere una directiva de datos adjuntos seguros (configuración) mediante el cmdlet **New-SafeAttachmentPolicy** y una regla de datos adjuntos seguros exclusiva (filtros de destinatarios) mediante el cmdlet **New-SafeAttachmentRule**. Para obtener instrucciones, [vea Use Exchange Online PowerShell o standalone EOP PowerShell para configurar Caja fuerte de datos adjuntos](set-up-safe-attachments-policies.md#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies).

En este ejemplo se crea una directiva de datos adjuntos segura denominada Departamento de investigación que bloquea los mensajes detectados y usa la directiva de cuarentena personalizada denominada NoAccess que asigna **ningún** permiso de acceso a los mensajes en cuarentena.

```powershell
New-SafeAttachmentPolicy -Name "Research Department" -Enable $true -Action Block -QuarantineTag NoAccess
```

Para obtener información detallada sobre la sintaxis y los parámetros, [consulte New-MalwareFilterPolicy](/powershell/module/exchange/new-malwarefilterpolicy).

En este ejemplo se modifica la directiva de datos adjuntos seguros existente denominada Recursos humanos mediante la asignación de la directiva de cuarentena personalizada denominada NoAccess que asigna **permisos sin** acceso.

```powershell
Set-SafeAttachmentPolicy -Identity "Human Resources" -QuarantineTag NoAccess
```

Para obtener información detallada sobre la sintaxis y los parámetros, [consulte Set-MalwareFilterPolicy](/powershell/module/exchange/set-malwarefilterpolicy).

## <a name="configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal"></a>Configurar las opciones de notificación de cuarentena global en el portal Microsoft 365 Defender web

La configuración global de las directivas de cuarentena le permite personalizar las notificaciones de cuarentena que se envían a los destinatarios de mensajes en cuarentena si las notificaciones de cuarentena están activadas en la directiva de cuarentena. Para obtener más información acerca de estas notificaciones, consulte [Quarantine notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).

1. En el portal Microsoft 365 Defender, vaya a Correo electrónico **y &** \> **directivas de colaboración &** \> **reglas Directivas de** \> amenazas Directivas de cuarentena en la **sección** Reglas.

2. En la **página Directiva de** cuarentena, seleccione **Configuración global**.

3. En el **control desplegable De notificaciones de** cuarentena que se abre, configure algunas o todas las opciones siguientes:

   - **Nombre para mostrar**: personalizar el nombre para mostrar del remitente que se usa en las notificaciones de cuarentena.

     Para cada idioma que haya agregado, seleccione el idioma del segundo cuadro de idioma (no haga clic en la X) y escriba el valor de texto que desee en el cuadro Nombre **para** mostrar.

     La siguiente captura de pantalla muestra el nombre para mostrar personalizado en una notificación de cuarentena:

     :::image type="content" source="../../media/quarantine-tags-esn-customization-display-name.png" alt-text="Un nombre para mostrar del remitente personalizado en una notificación de cuarentena" lightbox="../../media/quarantine-tags-esn-customization-display-name.png":::

   - **Aviso** de declinación de responsabilidades: agregue un aviso de declinación de responsabilidades personalizado a la parte inferior de las notificaciones de cuarentena. El texto localizado, **Un aviso de declinación de responsabilidades de su organización:** siempre se incluye primero, seguido del texto que especifique.

     Para cada idioma que haya agregado, seleccione el idioma del segundo cuadro de idioma (no haga clic en la X) y escriba el valor de texto que desee en el cuadro **Declinación de** responsabilidades.

     La siguiente captura de pantalla muestra el aviso de declinación de responsabilidades personalizado en una notificación de cuarentena:

     :::image type="content" source="../../media/quarantine-tags-esn-customization-disclaimer.png" alt-text="Un aviso de declinación de responsabilidades personalizado en la parte inferior de una notificación de cuarentena" lightbox="../../media/quarantine-tags-esn-customization-disclaimer.png":::

   - **Elegir idioma**: las notificaciones de cuarentena ya están localizadas en función de la configuración de idioma del destinatario. Puede especificar texto personalizado en diferentes idiomas para los valores **Nombre para mostrar** y **Declinación de** responsabilidades.

     Seleccione al menos un idioma en el primer cuadro de idioma y, a continuación, haga clic en **Agregar**. Puede seleccionar varios idiomas haciendo clic **en Agregar** después de cada uno. Un cuadro de idioma de sección muestra todos los idiomas que ha seleccionado:

     :::image type="content" source="../../media/quarantine-tags-esn-customization-selected-languages.png" alt-text="Los idiomas seleccionados en el segundo cuadro de idioma de la configuración de notificación de cuarentena global de las directivas de cuarentena" lightbox="../../media/quarantine-tags-esn-customization-selected-languages.png":::

   - **Usar el logotipo de mi** empresa: seleccione esta opción para reemplazar el logotipo predeterminado de Microsoft que se usa en la parte superior de las notificaciones de cuarentena. Antes de hacerlo, debes seguir las instrucciones de [Personalizar el tema Microsoft 365 de](../../admin/setup/customize-your-organization-theme.md) la organización para cargar el logotipo personalizado.

     La siguiente captura de pantalla muestra un logotipo personalizado en una notificación de cuarentena:

     :::image type="content" source="../../media/quarantine-tags-esn-customization-logo.png" alt-text="Un logotipo personalizado en una notificación de cuarentena" lightbox="../../media/quarantine-tags-esn-customization-logo.png":::

   - **Enviar notificación de correo no deseado del usuario final cada (días):** Seleccione la frecuencia de las notificaciones en cuarentena.

## <a name="view-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Ver directivas de cuarentena en el portal de Microsoft 365 Defender web

1. En el portal Microsoft 365 Defender, vaya a Correo electrónico **y &** \> **directivas de colaboración &** \> **reglas Directivas de** \> amenazas Directivas de cuarentena en la **sección** Reglas.

2. La **página Directiva de** cuarentena muestra la lista de directivas por **Nombre** y **Última fecha actualizada** .

3. Para ver la configuración de directivas de cuarentena integradas o personalizadas, seleccione la directiva de cuarentena de la lista haciendo clic en el nombre.

4. Para ver la configuración global, haga clic **en Configuración global**

### <a name="view-quarantine-policies-in-powershell"></a>Ver directivas de cuarentena en PowerShell

Si prefiere usar PowerShell para ver directivas de cuarentena, siga estos pasos:

- Para ver una lista resumida de todas las directivas integradas o personalizadas, ejecute el siguiente comando:

  ```powershell
  Get-QuarantinePolicy | Format-Table Name
  ```

- Para ver la configuración de directivas de cuarentena integradas o personalizadas, reemplace \<QuarantinePolicyName\> por el nombre de la directiva de cuarentena y ejecute el siguiente comando:

  ```powershell
  Get-QuarantinePolicy -Identity "<QuarantinePolicyName>"
  ```

- Para ver la configuración global de las notificaciones en cuarentena, ejecute el siguiente comando:

  ```powershell
  Get-QuarantinePolicy -QuarantinePolicyType GlobalQuarantinePolicy
  ```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).

## <a name="modify-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Modificar directivas de cuarentena en el portal Microsoft 365 Defender web

No puede modificar las directivas de cuarentena integradas denominadas AdminOnlyAccessPolicy o DefaultFullAccessPolicy. Puede modificar la directiva integrada denominada NotificationEnabledPolicy ([si la tiene](#full-access-permissions-and-quarantine-notifications)) y las directivas de cuarentena personalizadas.

1. En el portal Microsoft 365 Defender, vaya a Correo electrónico **y &** \> **directivas de colaboración &** \> **reglas Directivas de** \> amenazas Directivas de cuarentena en la **sección** Reglas.

2. En la **página Directivas de** cuarentena, seleccione la directiva haciendo clic en el nombre.

3. Después de seleccionar la directiva, haga clic en el icono ![Editar directiva.](../../media/m365-cc-sc-edit-icon.png) **Editar icono de** directiva que aparece.

4. El **Asistente para editar** directivas que se abre es prácticamente idéntico al  Asistente para nueva directiva, tal como se describe en la sección Crear directivas de cuarentena en la [sección del portal de Microsoft 365 Defender](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal) anteriormente en este artículo.

   La diferencia principal es que no se puede cambiar el nombre de una directiva existente.

5. Cuando haya terminado de modificar la directiva, vaya a la página **Resumen y** haga clic en **Enviar**.

### <a name="modify-quarantine-policies-in-powershell"></a>Modificar directivas de cuarentena en PowerShell

Si prefiere usar PowerShell para modificar una directiva de cuarentena personalizada, \<QuarantinePolicyName\> reemplace por el nombre de la directiva de cuarentena y use la sintaxis siguiente:

```powershell
Set-QuarantinePolicy -Identity "<QuarantinePolicyName>" [Settings]
```

La configuración disponible es la misma que se describe para crear directivas de cuarentena anteriormente en este artículo.

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-QuarantinePolicy](/powershell/module/exchange/set-quarantinepolicy).

## <a name="remove-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Quitar directivas de cuarentena en el Microsoft 365 Defender web

**Notas**:

- No puede quitar las directivas de cuarentena integradas denominadas AdminOnlyAccessPolicy o DefaultFullAccessPolicy. Puede quitar la directiva integrada denominada NotificationEnabledPolicy ([si la tiene](#full-access-permissions-and-quarantine-notifications)) y las directivas de cuarentena personalizadas.
- Antes de quitar una directiva de cuarentena, compruebe que no se está utilizando. Por ejemplo, ejecute el siguiente comando en PowerShell:

  ```powershell
  Write-Output -InputObject "Anti-spam policies","----------------------";Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag; Write-Output -InputObject "Anti-phishing policies","----------------------";Get-AntiPhishPolicy | Format-List Name,*QuarantineTag; Write-Output -InputObject "Anti-malware policies","----------------------";Get-MalwareFilterPolicy | Format-List Name,QuarantineTag; Write-Output -InputObject "Safe Attachments policies","---------------------------";Get-SafeAttachmentPolicy | Format-List Name,QuarantineTag
  ```

  Si se usa la directiva de cuarentena, [reemplace la directiva de cuarentena asignada](#step-2-assign-a-quarantine-policy-to-supported-features) antes de quitarla.

1. En el portal Microsoft 365 Defender, vaya a Correo electrónico **y &** \> **directivas de colaboración &** \> **reglas Directivas de** \> amenazas Directivas de cuarentena en la **sección** Reglas.

2. En la **página Directiva de** cuarentena, seleccione la directiva de cuarentena personalizada que desea quitar haciendo clic en el nombre.

3. Después de seleccionar la directiva, haga clic en el ![icono Eliminar directiva.](../../media/m365-cc-sc-delete-icon.png) **Eliminar icono de** directiva que aparece.

4. Haga **clic en Quitar** directiva en el cuadro de diálogo de confirmación que aparece.

### <a name="remove-quarantine-policies-in-powershell"></a>Quitar directivas de cuarentena en PowerShell

Si prefiere usar PowerShell para quitar una directiva de cuarentena personalizada, reemplace \<QuarantinePolicyName\> por el nombre de la directiva de cuarentena y ejecute el siguiente comando:

```powershell
Remove-QuarantinePolicy -Identity "<QuarantinePolicyName>"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [consulte Remove-QuarantinePolicy](/powershell/module/exchange/remove-quarantinepolicy).

## <a name="system-alerts-for-quarantine-release-requests"></a>Alertas del sistema para solicitudes de lanzamiento de cuarentena

De forma predeterminada, la directiva de alerta predeterminada denominada Usuario solicitado para liberar un mensaje en cuarentena genera automáticamente una alerta informativo y envía mensajes de notificación **a** los miembros de los siguientes grupos de roles siempre que un usuario solicite la publicación de un mensaje en cuarentena:

- Administrador de cuarentena
- Administrador de seguridad
- Administración de la organización (administrador global)

Los administradores pueden personalizar los destinatarios de notificaciones por correo electrónico o crear una directiva de alerta personalizada para obtener más opciones.

Para obtener más información sobre las directivas de alerta, consulte [Directivas de alerta en Microsoft 365](../../compliance/alert-policies.md).

## <a name="quarantine-policy-permission-details"></a>Detalles de permisos de directiva de cuarentena

En las secciones siguientes se describen los efectos de los grupos de permisos preestablecidos y los permisos individuales en los detalles de los mensajes en cuarentena y en las notificaciones de cuarentena.

### <a name="preset-permissions-groups"></a>Grupos de permisos preestablecidos

Los permisos individuales que se incluyen en grupos de permisos preestablecidos se enumeran en la tabla al principio de este artículo.

#### <a name="no-access"></a>Sin acceso

Si la directiva de cuarentena asigna los permisos **Sin** acceso (solo acceso de administrador), los usuarios no podrán ver los mensajes que están en cuarentena:

- **Detalles del mensaje en cuarentena**: no se mostrará ningún mensaje en la vista del usuario final.
- **Notificaciones en cuarentena**: no se enviarán notificaciones para esos mensajes.

#### <a name="limited-access"></a>Acceso limitado

Si la directiva de cuarentena asigna los **permisos de** acceso limitado, los usuarios obtienen las siguientes funcionalidades:

- **Detalles del mensaje en cuarentena**: los botones siguientes están disponibles:
  - **Versión de solicitud**
  - **Ver encabezados de mensaje**
  - **Vista previa de mensaje**
  - **Quitar de cuarentena**
  - **Bloquear remitente**

  :::image type="content" source="../../media/quarantine-tags-quarantined-message-details-limited-access.png" alt-text="Los botones disponibles en los detalles del mensaje en cuarentena si la directiva de cuarentena concede al usuario permisos de acceso limitados" lightbox="../../media/quarantine-tags-quarantined-message-details-limited-access.png":::

- **Notificaciones de cuarentena: los botones** siguientes están disponibles:
  - **Bloquear remitente**
  - **Versión de solicitud**
  - **Revisar**

  :::image type="content" source="../../media/quarantine-tags-esn-limited-access.png" alt-text="Los botones disponibles en la notificación de cuarentena si la directiva de cuarentena concede al usuario permisos de acceso limitados" lightbox="../../media/quarantine-tags-esn-limited-access.png":::

#### <a name="full-access"></a>Acceso completo

Si la directiva de cuarentena asigna los **permisos de** acceso completo (todos los permisos disponibles), los usuarios obtienen las siguientes funcionalidades:

- **Detalles del mensaje en cuarentena**: los botones siguientes están disponibles:
  - **Mensaje de versión**
  - **Ver encabezados de mensaje**
  - **Vista previa de mensaje**
  - **Quitar de cuarentena**
  - **Bloquear remitente**

  :::image type="content" source="../../media/quarantine-tags-quarantined-message-details-full-access.png" alt-text="Los botones disponibles en los detalles del mensaje en cuarentena si la directiva de cuarentena concede al usuario permisos de acceso completos" lightbox="../../media/quarantine-tags-quarantined-message-details-full-access.png":::

- **Notificaciones de cuarentena: los botones** siguientes están disponibles:
  - **Bloquear remitente**
  - **Release**
  - **Revisar**

  :::image type="content" source="../../media/quarantine-tags-esn-full-access.png" alt-text="Los botones disponibles en la notificación de cuarentena si la directiva de cuarentena concede al usuario permisos de acceso completos" lightbox="../../media/quarantine-tags-esn-full-access.png":::

### <a name="individual-permissions"></a>Permisos individuales

#### <a name="block-sender-permission"></a>Bloquear el permiso del remitente

El **permiso Bloquear remitente** (_PermissionToBlockSender_) controla el acceso al botón que permite a los usuarios agregar cómodamente el remitente del mensaje en cuarentena a su lista de remitentes bloqueados.

- **Detalles del mensaje en cuarentena**:
  - **Bloquear permiso de** remitente habilitado: el **botón Bloquear remitente** está disponible.
  - **Bloquear el permiso** del remitente deshabilitado: **el botón Bloquear remitente** no está disponible.

- **Notificaciones en cuarentena**:
  - **Bloquear permiso de** remitente habilitado: el **botón Bloquear remitente** está disponible.
  - **Bloquear el permiso** del remitente deshabilitado: **el botón Bloquear remitente** no está disponible.

Para obtener más información acerca de la lista Remitentes bloqueados, vea [Bloquear](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) mensajes de alguien y Usar Exchange Online PowerShell para configurar la colección de listas seguras [en un buzón](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).

#### <a name="delete-permission"></a>Permiso de eliminación

El **permiso Eliminar** (_PermissionToDelete_) controla la capacidad de los usuarios para eliminar sus mensajes (mensajes donde el usuario es un destinatario) de la cuarentena.

- **Detalles del mensaje en cuarentena**:
  - **Permisos** de eliminación habilitados: **el botón Quitar de cuarentena** está disponible.
  - **Eliminar** permiso deshabilitado: el **botón Quitar de cuarentena** no está disponible.

- **Notificaciones en cuarentena**: sin efecto.

#### <a name="preview-permission"></a>Permiso de vista previa

El **permiso Vista** previa (_PermissionToPreview_) controla la capacidad de los usuarios para obtener una vista previa de sus mensajes en cuarentena.

- **Detalles del mensaje en cuarentena**:
  - **Permiso** de vista previa habilitado: **el botón Vista previa del** mensaje está disponible.
  - **Permiso** de vista previa deshabilitado: **el botón Vista previa del** mensaje no está disponible.

- **Notificaciones en cuarentena**: sin efecto.

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a>Permitir que los destinatarios liberen un mensaje del permiso de cuarentena

Permitir **que los destinatarios** liberen un mensaje del permiso de cuarentena (_PermissionToRelease_) controla la capacidad de los usuarios para liberar sus mensajes en cuarentena directamente y sin la aprobación de un administrador.

- **Detalles del mensaje en cuarentena**:
  - Permiso habilitado: el **botón Liberar mensaje** está disponible.
  - Permiso deshabilitado: el **botón Liberar mensaje** no está disponible.

- **Notificaciones en cuarentena**:
  - Permiso habilitado: el **botón Liberar** está disponible.
  - Permiso deshabilitado: el **botón Liberar** no está disponible.

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a>Permitir que los destinatarios soliciten un mensaje que se liberará del permiso de cuarentena

Allow **recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages. El mensaje solo se libera después de que un administrador apruebe la solicitud.

- **Detalles del mensaje en cuarentena**:
  - Permiso habilitado: el **botón Solicitar versión** está disponible.
  - Permiso deshabilitado: el **botón Solicitar versión** no está disponible.

- **Notificaciones en cuarentena**:
  - Permiso habilitado: el **botón Solicitar versión** está disponible.
  - Permiso deshabilitado: el **botón Solicitar versión** no está disponible.
