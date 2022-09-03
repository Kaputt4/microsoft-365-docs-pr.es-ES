---
title: Directivas de cuarentena
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Los administradores pueden aprender a usar directivas de cuarentena para controlar lo que los usuarios pueden hacer en los mensajes en cuarentena.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 1943a52b69c4e0bdb76769facdc1d93e7f53bd7b
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67595461"
---
# <a name="quarantine-policies"></a>Directivas de cuarentena

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a:**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Las directivas de cuarentena (anteriormente _conocidas como etiquetas de cuarentena_) en Exchange Online Protection (EOP) y Microsoft Defender para Office 365 permiten a los administradores controlar lo que los usuarios pueden hacer en los mensajes en cuarentena en función de por qué se puso en cuarentena el mensaje. Esta característica está disponible en todas las organizaciones de Microsoft 365 con buzones Exchange Online.

Tradicionalmente, se han permitido o denegado los niveles de interactividad de los mensajes de cuarentena en función de por qué se puso en cuarentena el mensaje. Por ejemplo, los usuarios pueden ver y liberar mensajes que se pusieron en cuarentena mediante el filtrado antispam como correo no deseado o de forma masiva, pero no pueden ver ni liberar mensajes que se pusieron en cuarentena como phishing o malware de alta confianza.

En [el caso de las características de protección admitidas, las directivas](#step-2-assign-a-quarantine-policy-to-supported-features) de cuarentena especifican qué usuarios pueden hacer con sus propios mensajes (mensajes donde son destinatarios) en cuarentena y en _notificaciones de cuarentena_. [Las notificaciones de cuarentena](use-spam-notifications-to-release-and-report-quarantined-messages.md) son el reemplazo de las notificaciones de correo no deseado del usuario final. Estas notificaciones ahora están controladas por directivas de cuarentena y contienen información sobre los mensajes en cuarentena para todas las características de protección admitidas (no solo los veredictos de directivas contra correo no deseado y de directiva anti phishing).

Las directivas de cuarentena predeterminadas que aplican las funcionalidades de usuario históricas se asignan automáticamente a las acciones de las características de protección admitidas que ponen en cuarentena los mensajes. O bien, puede crear directivas de cuarentena personalizadas y asignarlas a las características de protección admitidas para permitir o impedir que los usuarios realicen acciones específicas en esos tipos de mensajes en cuarentena.

Los permisos de directiva de cuarentena individuales se combinan en los siguientes grupos de permisos preestablecidos:

- Sin acceso
- Acceso limitado
- Acceso completo

En la tabla siguiente se describen los permisos de directiva de cuarentena individuales que se encuentran en los grupos de permisos preestablecidos:

|Permiso|Sin acceso|Acceso limitado|Acceso completo|
|---|:---:|:---:|:---:|
|**Remitente de bloques** (_PermissionToBlockSender_)||![Marca de verificación.](../../media/checkmark.png)|![Marca de verificación.](../../media/checkmark.png)|
|**Eliminar** (_PermissionToDelete_)||![Marca de verificación.](../../media/checkmark.png)|![Marca de verificación.](../../media/checkmark.png)|
|**Versión preliminar** (_PermissionToPreview_)||![Marca de verificación.](../../media/checkmark.png)|![Marca de verificación.](../../media/checkmark.png)|
|**Permitir a los destinatarios liberar un mensaje de la cuarentena** (_PermissionToRelease_)<sup>\*</sup>|||![Marca de verificación.](../../media/checkmark.png)|
|**Permitir que los destinatarios soliciten que se libere un mensaje de la cuarentena** (_PermissionToRequestRelease_)||![Marca de verificación](../../media/checkmark.png)||

<sup>\*</sup>El permiso **Permitir a los destinatarios liberar un mensaje de la cuarentena** no se respeta en las directivas antimalware ni en el veredicto de suplantación de identidad de alta confianza en las directivas contra correo no deseado. Los usuarios no pueden liberar su propio malware o mensajes de suplantación de identidad de alta confianza de la cuarentena. En el mejor de los casos, puede usar **el permiso Permitir a los destinatarios solicitar que se libere un mensaje del permiso de cuarentena** .

En la tabla siguiente se describen las directivas de cuarentena predeterminadas, sus grupos de permisos asociados y si las notificaciones de cuarentena están habilitadas:

|Directiva de cuarentena predeterminada|Grupo de permisos usado|¿Las notificaciones de cuarentena están habilitadas?|
|---|:---:|:---:|
|AdminOnlyAccessPolicy|Sin acceso|No|
|DefaultFullAccessPolicy|Acceso completo|No|
|NotificationEnabledPolicy<sup>\*</sup>|Acceso completo|Yes|

Si no le gustan los permisos predeterminados en los grupos de permisos preestablecidos o si desea habilitar las notificaciones de cuarentena, cree y use directivas de cuarentena personalizadas. Para obtener más información sobre lo que hace cada permiso, consulte la sección [Detalles del permiso de directiva de cuarentena](#quarantine-policy-permission-details) más adelante en este artículo.

Las directivas de cuarentena se crean y asignan en el portal de Microsoft 365 Defender o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones de Exchange Online; PowerShell EOP independiente en organizaciones EOP sin buzones de Exchange Online).

> [!NOTE]
> El tiempo que los mensajes en cuarentena se mantienen en cuarentena antes de que expiren se controla mediante la **opción Conservar correo no deseado en cuarentena durante estos muchos días** (_QuarantineRetentionPeriod_) en las directivas contra correo no deseado. Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).
>
> Si cambia la directiva de cuarentena asignada a una característica de protección compatible, el cambio afecta a los mensajes que se ponen en cuarentena _después_ de realizar el cambio. Los mensajes que esa característica de protección ha puesto en cuarentena anteriormente no se ven afectados por la configuración de la nueva asignación de directiva de cuarentena.

## <a name="full-access-permissions-and-quarantine-notifications"></a>Permisos de acceso completo y notificaciones de cuarentena

<sup>\*</sup> La directiva de cuarentena denominada NotificationEnabledPolicy no está presente en todos los entornos. Tendrá la directiva de cuarentena NotificationEnabledPolicy si su organización cumple los dos requisitos siguientes:

- La organización existía antes de que se activara la característica de directiva de cuarentena (finales de julio o principios de agosto de 2021).
- Tenía una o varias [directivas contra correo no deseado](configure-your-spam-filter-policies.md) (la directiva de correo no deseado predeterminada o directivas personalizadas contra correo no deseado) donde se activaba la opción **Habilitar notificaciones de correo no deseado del usuario final** .

Como se describió anteriormente, las notificaciones de cuarentena en las directivas de cuarentena reemplazan las notificaciones de correo no deseado del usuario final que usó para activar o desactivar en las directivas contra correo no deseado. La directiva de cuarentena integrada denominada DefaultFullAccessPolicy duplica los _permisos_ históricos de los mensajes en cuarentena, pero _las notificaciones de cuarentena no están activadas_ en la directiva de cuarentena. Además, como no puede modificar la directiva integrada, no puede activar las notificaciones de cuarentena en DefaultFullAccessPolicy.

Para proporcionar los permisos de DefaultFullAccessPolicy, pero con las notificaciones de cuarentena activadas, creamos la directiva denominada NotificationEnabledPolicy para usarla en lugar de DefaultFullAccessPolicy para aquellas organizaciones que lo necesitaban (organizaciones en las que se activaron las notificaciones de correo no deseado del usuario final).

Para las nuevas organizaciones o organizaciones anteriores que nunca tenían habilitadas las notificaciones de correo no deseado del usuario final en las directivas contra correo no deseado, no tendrá la directiva de cuarentena denominada NotificationEnabledPolicy. La manera de activar las notificaciones de cuarentena es crear y usar directivas de cuarentena personalizadas donde las notificaciones de cuarentena estén activadas.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Directivas de cuarentena** , use <https://security.microsoft.com/quarantinePolicies>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Para ver, crear, modificar o quitar directivas de cuarentena, debe ser miembro de los roles Administración de la **organización**, **Administrador de seguridad o Administrador** de **cuarentena** en el portal de Microsoft 365 Defender. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

## <a name="step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Paso 1: Crear directivas de cuarentena en el portal de Microsoft 365 Defender

1. En el [portal de Microsoft 365 Defender](https://security.microsoft.com), vaya a **directivas de colaboración Email &**  **directivas de** colaboración \> & directivas de **cuarentena** de reglas \> \> directivas de cuarentena en la sección **Reglas**. O bien, para ir directamente a la página **Directivas de cuarentena** , use <https://security.microsoft.com/quarantinePolicies>.

   :::image type="content" source="../../media/mdo-quarantine-policy-page.png" alt-text="Página Directiva de cuarentena en el portal de Microsoft 365 Defender." lightbox="../../media/mdo-quarantine-policy-page.png":::

2. En la página **Directivas de cuarentena** , haga clic en el ![icono Agregar directiva personalizada.](../../media/m365-cc-sc-create-icon.png) **Agregar directiva personalizada**.

3. Se abre el Asistente **para nueva directiva** . En la página **Nombre de** directiva, escriba un nombre breve pero único en el cuadro **Nombre de** directiva. Deberá identificar y seleccionar la directiva de cuarentena por nombre en los próximos pasos. Cuando termine, haga clic en **Siguiente**.

4. En la página **Acceso a mensajes de destinatario** , seleccione uno de los siguientes valores:
   - **Acceso limitado**: los permisos individuales que se incluyen en este grupo de permisos se describen anteriormente en este artículo.
   - **Establecer acceso específico (avanzado):** use este valor para especificar permisos personalizados. Configure los siguientes valores que aparecen:
     - **Seleccionar preferencia de acción de versión**: seleccione uno de los valores siguientes:
       - En blanco: este es el valor predeterminado.
       - **Permitir que los destinatarios liberen un mensaje de la cuarentena**
       - **Permitir que los destinatarios soliciten que un mensaje se libere de la cuarentena**
     - **Seleccione acciones adicionales que los destinatarios pueden realizar en los mensajes en cuarentena**: seleccione algunos, todos o ninguno de los valores siguientes:
       - **Eliminar**
       - **Vista previa**
       - **Bloquear remitente**

   Estos permisos y su efecto en los mensajes en cuarentena y en las notificaciones de cuarentena se describen en la sección [Detalles del permiso](#quarantine-policy-permission-details) de directiva de cuarentena más adelante en este artículo.

   Cuando termine, haga clic en **Siguiente**.

5. En la página **Notificación de correo no deseado del usuario final** , seleccione **Habilitar** para habilitar las notificaciones de cuarentena (anteriormente conocidas como notificaciones de correo no deseado del usuario final). Cuando termine, haga clic en **Siguiente**.

   > [!NOTE]
   > Como se explicó anteriormente, las directivas integradas (AdminOnlyAccessPolicy o DefaultFullAccessPolicy) no tienen activadas las notificaciones en cuarentena y no se pueden modificar las directivas.

6. En la página **Revisar directiva** , revise la configuración. Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Enviar**.

7. En la página de confirmación que aparece, haga clic en **Listo**.

Ahora está listo para asignar la directiva de cuarentena a una característica de cuarentena, como se describe en la sección [Paso 2](#step-2-assign-a-quarantine-policy-to-supported-features) .

### <a name="create-quarantine-policies-in-powershell"></a>Creación de directivas de cuarentena en PowerShell

Si prefiere usar PowerShell para crear directivas de cuarentena, conéctese a Exchange Online PowerShell o Exchange Online Protection PowerShell y use el cmdlet **New-QuarantinePolicy**.

> [!NOTE]
> Si no usa el parámetro _ESNEnabled_ y el valor `$true`, las notificaciones de cuarentena se desactivan.

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a>Uso del parámetro EndUserQuarantinePermissionsValue

Para crear una directiva de cuarentena mediante el parámetro _EndUserQuarantinePermissionsValue_ , use la sintaxis siguiente:

```powershell
New-QuarantinePolicy -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236> [-EsnEnabled $true]
```

El parámetro _EndUserQuarantinePermissionsValue_ usa un valor decimal que se convierte a partir de un valor binario. El valor binario corresponde a los permisos de cuarentena de usuario final disponibles en un orden específico. Para cada permiso, el valor 1 es igual a True y el valor 0 es False.

El orden y los valores necesarios para cada permiso individual se describen en la tabla siguiente:

|Permiso|Valor decimal|Valor binario|
|---|:---:|:---:|
|PermissionToViewHeader<sup>\*</sup>|128|10000000|
|PermissionToDownload<sup>\*\*</sup>|64|01000000|
|PermissionToAllowSender<sup>\*\*</sup>|32|00100000|
|PermissionToBlockSender|16 |00010000|
|PermissionToRequestRelease<sup>\*\*\*</sup>|8 |00001000|
|PermissionToRelease<sup>\*\*\*</sup>|4|00000100|
|PermissionToPreview|2|00000010|
|PermissionToDelete|1|00000001|

<sup>\*</sup> El valor 0 no oculta el botón **Ver encabezado del mensaje** en los detalles del mensaje en cuarentena (el botón siempre está disponible).

<sup>\*\*</sup> Esta configuración no se usa (el valor 0 o 1 no hace nada).

<sup>\*\*\*</sup> No establezca ambos valores en 1. Establezca uno en 1 y el otro en 0 o establezca ambos en 0.

Para los permisos de acceso limitado, los valores necesarios son:

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
|Valor decimal que se va a usar|27|

En este ejemplo se crea una nueva directiva de cuarentena denominada LimitedAccess con las notificaciones de cuarentena activadas que asigna los permisos de acceso limitado, como se describe en la tabla anterior.

```powershell
New-QuarantinePolicy -Name LimitedAccess -EndUserQuarantinePermissionsValue 27 -EsnEnabled $true
```

Para los permisos personalizados, use la tabla anterior para obtener el valor binario que corresponde a los permisos que desee. Convierta el valor binario en un valor decimal y use el valor decimal para el parámetro _EndUserQuarantinePermissionsValue_ . No use el valor binario para el valor del parámetro.

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [New-QuarantinePolicy](/powershell/module/exchange/new-quarantinepolicy).

## <a name="step-2-assign-a-quarantine-policy-to-supported-features"></a>Paso 2: Asignación de una directiva de cuarentena a las características admitidas

En las características _de protección admitidas_ que ponen en cuarentena los mensajes de correo electrónico, puede asignar una directiva de cuarentena a las acciones de cuarentena disponibles. En la tabla siguiente se describen las características que ponen en cuarentena los mensajes y la disponibilidad de las directivas de cuarentena:

|Característica|¿Se admiten directivas de cuarentena?|Directivas de cuarentena predeterminadas usadas|
|---|:---:|---|
|[Directivas contra correo no deseado](configure-your-spam-filter-policies.md): <ul><li>**Spam** (_SpamAction_)</li><li>**Spam de alta confianza** (_HighConfidenceSpamAction_)</li><li>**Phishing** (_PhishSpamAction_)</li><li>**Phishing de alta confianza** (_HighConfidencePhishAction_)</li><li>**Bulk** (_BulkSpamAction_)</li></ul>|Yes|<ul><li>DefaultFullAccessPolicy<sup>\*</sup> (acceso completo)</li><li>DefaultFullAccessPolicy<sup>\*</sup> (acceso completo)</li><li>DefaultFullAccessPolicy<sup>\*</sup> (acceso completo)</li><li>AdminOnlyAccessPolicy (sin acceso)</li><li>DefaultFullAccessPolicy<sup>\*</sup> (acceso completo)</li></ul>|
|Directivas de protección contra phishing: <ul><li>[Protección de inteligencia contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</li><li>[Protección contra suplantación en Defender para Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<ul><li>**Si el mensaje se detecta como un usuario suplantado** (_TargetedUserProtectionAction_)</li><li>**Si el mensaje se detecta como un dominio suplantado** (_TargetedDomainProtectionAction_)</li><li>**Si la inteligencia del buzón detecta y suplanta a un usuario** (_MailboxIntelligenceProtectionAction_)</li></ul></li></ul>|Yes|<ul><li>DefaultFullAccessPolicy<sup>\*</sup> (acceso completo)</li><li>Protección contra suplantación:<ul><li>DefaultFullAccessPolicy<sup>\*</sup> (acceso completo)</li><li>DefaultFullAccessPolicy<sup>\*</sup> (acceso completo)</li><li>DefaultFullAccessPolicy<sup>\*</sup> (acceso completo)</li></ul></li></ul>|
|[Directivas antimalware](configure-anti-malware-policies.md): todos los mensajes detectados siempre se ponen en cuarentena.|Yes|AdminOnlyAccessPolicy (sin acceso)|
|[Protección de datos adjuntos seguros](safe-attachments.md): <ul><li>Email mensajes con datos adjuntos que se ponen en cuarentena como malware mediante directivas de datos adjuntos seguros (_Habilitar_ y _acción_)</li><li>Archivos en cuarentena como malware por [datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li></ul>|<ul><li>Yes</li><li>No</li></ul>|<ul><li>AdminOnlyAccessPolicy (sin acceso)</li><li>No aplicable</li></ul>|
|[Reglas de flujo de correo](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (también conocidas como reglas de transporte) con la acción: **Entregar el mensaje a la cuarentena hospedada** (_cuarentena_).|No|No aplicable|

<sup>\*</sup> Como [se describió anteriormente en este artículo](#full-access-permissions-and-quarantine-notifications), su organización podría usar NotificationEnabledPolicy en lugar de DefaultFullAccessPolicy. La única diferencia entre estas dos directivas de cuarentena es que las notificaciones de cuarentena están activadas en NotificationEnabledPolicy y desactivadas en DefaultFullAccessPolicy.

Las directivas de cuarentena predeterminadas, los grupos de permisos preestablecidos y los permisos se describen al [principio de este artículo](#quarantine-policies) y [versiones posteriores de este artículo](#preset-permissions-groups).

> [!NOTE]
> Si está satisfecho con los permisos predeterminados del usuario final y las notificaciones de cuarentena proporcionadas (o no proporcionadas) por las directivas de cuarentena predeterminadas, no es necesario hacer nada. Si desea agregar o quitar funcionalidades de usuario final (los botones disponibles) para los mensajes en cuarentena del usuario, o habilitar las notificaciones de cuarentena y agregar o quitar las mismas funcionalidades en las notificaciones de cuarentena, puede asignar una directiva de cuarentena diferente a la acción de cuarentena.

## <a name="assign-quarantine-policies-in-supported-policies-in-the-microsoft-365-defender-portal"></a>Asignación de directivas de cuarentena en directivas admitidas en el portal de Microsoft 365 Defender

> [!NOTE]
> Los usuarios no pueden liberar sus propios mensajes que se pusieron en cuarentena como malware (directivas antimalware) o phishing de alta confianza (directivas contra correo no deseado), independientemente de cómo se configure la directiva de cuarentena. En el mejor de los casos, los administradores pueden configurar la directiva de cuarentena para que los usuarios puedan solicitar la liberación de su malware en cuarentena o mensajes de suplantación de identidad de alta confianza.

### <a name="anti-spam-policies"></a>Directivas contra correo electrónico no deseado

1. En el [portal de Microsoft 365 Defender](https://security.microsoft.com), vaya a **Directivas de colaboración Email &** **reglas de &** \> **Directivas** \> \> **de amenazas Antispam** en la sección **Directivas**.

   O bien, para ir directamente a la página **Directivas de correo no deseado de Ant** , use <https://security.microsoft.com/antispam>.

2. En la página **Directivas contra correo no deseado** , realice uno de los pasos siguientes:
   - Busque y seleccione una directiva **antispam entrante** existente.
   - Cree una nueva directiva de antispam **entrante** .

3. Realice uno de los pasos siguientes:
   - **Editar existente**: seleccione la directiva haciendo clic en el nombre de la directiva. En el control flotante de detalles de la directiva, vaya a la sección **Acciones** y, a continuación, haga clic en **Editar acciones**.
   - **Crear nuevo**: en el asistente para nueva directiva, acceda a la página **Acciones** .

4. En la página **Acciones** , cada veredicto que tenga la acción **Mensaje de cuarentena** también tendrá el cuadro **Seleccionar directiva de cuarentena** para que seleccione una directiva de cuarentena correspondiente.

   **Nota**: Al crear una nueva directiva, un valor **seleccionar directiva de cuarentena** en blanco indica que se usa la directiva de cuarentena predeterminada para ese veredicto. Cuando edita posteriormente la directiva, los valores en blanco se reemplazan por los nombres de directivas de cuarentena predeterminados reales, como se describe en la tabla anterior.

   :::image type="content" source="../../media/quarantine-tags-in-anti-spam-policies.png" alt-text="Selecciones de directivas de cuarentena en una directiva contra correo no deseado" lightbox="../../media/quarantine-tags-in-anti-spam-policies.png":::

Las instrucciones completas para crear y modificar directivas contra correo no deseado se describen en [Configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).

#### <a name="anti-spam-policies-in-powershell"></a>Directivas contra correo no deseado en PowerShell

Si prefiere usar PowerShell para asignar directivas de cuarentena en directivas contra correo no deseado, conéctese a Exchange Online PowerShell o Exchange Online Protection PowerShell y use la sintaxis siguiente:

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>"> [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

**Notas**:

- El valor predeterminado de los parámetros _PhishSpamAction_ y _HighConfidencePhishAction_ es Cuarentena, por lo que no es necesario usar esos parámetros al crear nuevas directivas de filtro de correo no deseado en PowerShell. Para los parámetros _SpamAction_, _HighConfidenceSpamAction_ y _BulkSpamAction_ en directivas antispam nuevas o existentes, la directiva de cuarentena solo es efectiva si el valor es Cuarentena.

  Para ver los valores de parámetros importantes en las directivas antispam existentes, ejecute el siguiente comando:

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*SpamAction,HighConfidencePhishAction,*QuarantineTag
  ```

  Para obtener información sobre los valores de acción predeterminados y los valores de acción recomendados para Estándar y Estricto, consulte [Configuración de la directiva contra correo no deseado de EOP](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).

- Al crear nuevas directivas contra correo no deseado, un veredicto de filtrado de correo no deseado sin un parámetro de directiva de cuarentena correspondiente significa que se usa la [directiva de cuarentena predeterminada](#step-2-assign-a-quarantine-policy-to-supported-features) para ese veredicto.

  Debe reemplazar una directiva de cuarentena predeterminada por una directiva de cuarentena personalizada solo si desea cambiar las funcionalidades predeterminadas del usuario final en los mensajes en cuarentena para ese veredicto de filtrado de correo no deseado determinado.

- Una nueva directiva contra correo no deseado en PowerShell requiere una directiva de filtro de correo no deseado (configuración) mediante el cmdlet **New-HostedContentFilterPolicy** y una regla de filtro de correo no deseado exclusivo (filtros de destinatarios) mediante el cmdlet **New-HostedContentFilterRule** . Para obtener instrucciones, consulte [Uso de PowerShell para crear directivas contra correo no deseado](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).

En este ejemplo se crea una nueva directiva de filtro de correo no deseado denominada Departamento de investigación con la siguiente configuración:

- La acción para todos los veredictos de filtrado de correo no deseado se establece en Cuarentena.
- La directiva de cuarentena personalizada denominada NoAccess que asigna permisos **Sin acceso** reemplaza a las directivas de cuarentena predeterminadas que no asignan permisos **De acceso** de forma predeterminada.

```powershell
New-HostedContentFilterPolicy -Name "Research Department" -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).

En este ejemplo se modifica la directiva de filtro de correo no deseado existente denominada Recursos humanos. La acción para el veredicto de cuarentena de correo no deseado se establece en Cuarentena y se asigna la directiva de cuarentena personalizada denominada NoAccess.

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).

### <a name="anti-phishing-policies"></a>Directivas de protección contra phishing

La inteligencia sobre suplantación de identidad está disponible en EOP y Defender para Office 365. La protección de suplantación de usuario, la protección de suplantación de dominio y la inteligencia de buzones solo están disponibles en Defender para Office 365. Para obtener más información, consulte [Directivas contra la suplantación de identidad en Microsoft 365 ](set-up-anti-phishing-policies.md).

1. En el [portal de Microsoft 365 Defender](https://security.microsoft.com), vaya a **Directivas de colaboración** \> **Email & & reglas Directivas** \> \> de **amenazas** **Anti-phishing** en la sección **Directivas**.

   O bien, para ir directamente a la página **Directivas de correo no deseado de Ant** , use <https://security.microsoft.com/antiphishing>.

2. En la página **Anti-phishing** , realice uno de los pasos siguientes:
   - Busque y seleccione una directiva anti phishing existente.
   - Cree una nueva directiva contra phishing.

3. Realice uno de los pasos siguientes:
   - **Editar existente**: seleccione la directiva haciendo clic en el nombre de la directiva. En el control flotante detalles de la directiva, vaya a la sección **Configuración de protección** y, a continuación, haga clic en **Editar configuración de protección**.
   - **Crear nuevo**: en el asistente para nueva directiva, acceda a la página **Acciones** .

4. En la página **Configuración de protección** , compruebe que la configuración siguiente está activada y configurada según sea necesario:
   - **Usuarios habilitados para proteger**: especifique los usuarios.
   - **Dominios habilitados para proteger**: seleccione **Incluir dominios que poseo** o **Incluir dominios personalizados** y especifique los dominios.
   - **Habilitar la inteligencia de buzones**
   - **Habilitación de la inteligencia para la protección contra suplantación**
   - **Habilitación de la inteligencia de suplantación de identidad**

5. Realice uno de los pasos siguientes:
   - **Editar existente**: en el control flotante detalles de la directiva, vaya a la sección **Acciones** y, a continuación, haga clic en **Editar acciones**.
   - **Crear nuevo**: en el asistente para nueva directiva, acceda a la página **Acciones** .

6. En la página **Acciones** , cada veredicto que tenga la acción **Poner en cuarentena el mensaje** también tendrá el cuadro Aplicar directiva de **cuarentena** para que seleccione una directiva de cuarentena correspondiente.

   **Nota**: Al crear una nueva directiva, un valor **en blanco Aplicar directiva de cuarentena** indica que se usa la directiva de cuarentena predeterminada para esa acción. Cuando edita posteriormente la directiva, los valores en blanco se reemplazan por los nombres de directivas de cuarentena predeterminados reales, como se describe en la tabla anterior.

   :::image type="content" source="../../media/quarantine-tags-in-anti-phishing-policies.png" alt-text="Selecciones de directivas de cuarentena en una directiva contra suplantación de identidad" lightbox="../../media/quarantine-tags-in-anti-phishing-policies.png":::

Las instrucciones completas para crear y modificar directivas contra phishing están disponibles en los temas siguientes:

- [Configuración de directivas contra phishing en EOP](configure-anti-phishing-policies-eop.md)
- [Configuración de directivas contra phishing en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md)

#### <a name="anti-phishing-policies-in-powershell"></a>Directivas contra suplantación de identidad en PowerShell

Si prefiere usar PowerShell para asignar directivas de cuarentena en directivas anti phishing, conéctese a Exchange Online PowerShell o Exchange Online Protection PowerShell y use la sintaxis siguiente:

```powershell
<New-AntiPhishPolicy -Name "<Unique name>" | Set-AntiPhishPolicy -Identity "<Policy name>"> [-EnableSpoofIntelligence $true] [-AuthenticationFailAction Quarantine] [-SpoofQuarantineTag <QuarantineTagName>] [-EnableMailboxIntelligence $true] [-EnableMailboxIntelligenceProtection $true] [-MailboxIntelligenceProtectionAction Quarantine] [-MailboxIntelligenceQuarantineTag <QuarantineTagName>] [-EnableOrganizationDomainsProtection $true] [-EnableTargetedDomainsProtection $true] [-TargetedDomainProtectionAction Quarantine] [-TargetedDomainQuarantineTag <QuarantineTagName>] [-EnableTargetedUserProtection $true] [-TargetedUserProtectionAction Quarantine] [-TargetedUserQuarantineTag <QuarantineTagName>] ...
```

**Notas**:

- Los parámetros _Enable\*_ son necesarios para activar las características de protección específicas. El valor predeterminado de los parámetros _EnableMailboxIntelligence_ y _EnableSpoofIntelligence_ es $true, por lo que no es necesario usar estos parámetros al crear nuevas directivas anti phish en PowerShell. Todos los demás parámetros _Enable\*_ deben tener el valor $true para que pueda establecer el valor Cuarentena en los parámetros _de acción correspondientes\*_ para asignar una directiva de cuarentena. Ninguno de los parámetros _*\Action_ tiene el valor predeterminado Cuarentena.

  Para ver los valores de parámetro importantes en las directivas anti phish existentes, ejecute el siguiente comando:

  ```powershell
  Get-AntiPhishPolicy | Format-List Name,Enable*Intelligence,Enable*Protection,*Action,*QuarantineTag
  ```

  Para obtener información sobre los valores de acción predeterminados y los valores de acción recomendados para Estándar y Estricto, consulte [Configuración de directivas de suplantación y configuración](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) de directivas de suplantación de EOP [en directivas contra suplantación de identidad en Microsoft Defender para Office 365](recommended-settings-for-eop-and-office365.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

- Al crear directivas de anti phishing, una acción contra suplantación de identidad (phishing) sin un parámetro de directiva de cuarentena correspondiente significa que se usa la [directiva de cuarentena predeterminada](#step-2-assign-a-quarantine-policy-to-supported-features) para ese veredicto.

  Solo debe reemplazar una directiva de cuarentena predeterminada por una directiva de cuarentena personalizada si desea cambiar las funcionalidades predeterminadas del usuario final en los mensajes en cuarentena para ese veredicto concreto.

- Una nueva directiva anti-phishing en PowerShell requiere una directiva antifish (configuración) mediante el cmdlet **New-AntiPhishPolicy** y una regla antifish exclusiva (filtros de destinatarios) mediante el cmdlet **New-AntiPhishRule** . Para obtener instrucciones, consulte los temas siguientes:
  - [Uso de PowerShell para configurar directivas contra suplantación de identidad en EOP](configure-anti-phishing-policies-eop.md#use-exchange-online-powershell-to-configure-anti-phishing-policies)
  - [Uso de Exchange Online PowerShell para configurar directivas anti phishing](configure-mdo-anti-phishing-policies.md#use-exchange-online-powershell-to-configure-anti-phishing-policies)

En este ejemplo se crea una nueva directiva anti phish denominada Departamento de investigación con la siguiente configuración:

- La acción para todos los veredictos de filtrado de correo no deseado se establece en Cuarentena.
- La directiva de cuarentena personalizada denominada NoAccess que asigna permisos **Sin acceso** reemplaza a las directivas de cuarentena predeterminadas que no asignan permisos **De acceso** de forma predeterminada.

```powershell
New-AntiPhishPolicy -Name "Research Department" -AuthenticationFailAction Quarantine -SpoofQuarantineTag NoAccess -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -MailboxIntelligenceQuarantineTag NoAccess -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainProtectionAction Quarantine -TargetedDomainQuarantineTag NoAccess -EnableTargetedUserProtection $true -TargetedUserProtectionAction Quarantine -TargetedUserQuarantineTag NoAccess
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [New-AntiPhishPolicy](/powershell/module/exchange/new-antiphishpolicy).

En este ejemplo se modifica la directiva anti phish existente denominada Recursos humanos. La acción para los mensajes detectados por la suplantación de usuario y la suplantación de dominio se establece en Cuarentena y se asigna la directiva de cuarentena personalizada denominada NoAccess.

```powershell
Set-AntiPhishPolicy -Identity "Human Resources" -EnableTargetedDomainsProtection $true -TargetedDomainProtectionAction Quarantine -TargetedDomainQuarantineTag NoAccess -EnableTargetedUserProtection $true -TargetedUserProtectionAction Quarantine -TargetedUserQuarantineTag NoAccess
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Set-AntiPhishPolicy](/powershell/module/exchange/set-antiphishpolicy).

### <a name="anti-malware-policies"></a>Directivas antimalware

1. En el [portal de Microsoft 365 Defender](https://security.microsoft.com), vaya a **Directivas de colaboración** \> **Email & & reglas** \> **Directivas** \> **de amenazas Antimalware** en la sección **Directivas**.

   O bien, para ir directamente a la página **Antimalware** , use <https://security.microsoft.com/antimalwarev2>.

2. En la página **Antimalware** , realice uno de los pasos siguientes:
   - Busque y seleccione una directiva antimalware existente.
   - Cree una nueva directiva antimalware.

3. Realice uno de los pasos siguientes:
   - **Editar existente**: seleccione la directiva haciendo clic en el nombre de la directiva. En el control flotante detalles de la directiva, vaya a la sección **Configuración de protección** y, a continuación, haga clic en **Editar configuración de protección**.
   - **Crear nuevo**: en el asistente para nueva directiva, acceda a la página **Acciones** .

4. En la página **Configuración de protección** , seleccione una directiva de cuarentena en el cuadro **Directiva de cuarentena** .

   **Nota**: Al crear una nueva directiva, un valor de **directiva de cuarentena** en blanco indica la directiva de cuarentena predeterminada para la que se usa. Cuando edita posteriormente la directiva, el valor en blanco se reemplaza por el nombre predeterminado real de la directiva de cuarentena, como se describe en la tabla anterior.

#### <a name="anti-malware-policies-in-powershell"></a>Directivas antimalware en PowerShell

Si prefiere usar PowerShell para asignar directivas de cuarentena en directivas antimalware, conéctese a Exchange Online PowerShell o Exchange Online Protection PowerShell y use la sintaxis siguiente:

```powershell
<New-AntiMalwarePolicy -Name "<Unique name>" | Set-AntiMalwarePolicy -Identity "<Policy name>"> [-QuarantineTag <QuarantineTagName>]
```

**Notas**:

- Al crear nuevas directivas antimalware sin usar el parámetro QuarantineTag al crear una nueva directiva antimalware, se usa la directiva de cuarentena predeterminada para las detecciones de malware (AdminOnlyAccessPolicy).

  Debe reemplazar la directiva de cuarentena predeterminada por una directiva de cuarentena personalizada solo si desea cambiar las funcionalidades predeterminadas del usuario final en los mensajes que se ponen en cuarentena como malware.

  Para ver los valores de parámetro importantes en las directivas anti phish existentes, ejecute el siguiente comando:

  ```powershell
  Get-MalwareFilterPolicy | Format-Table Name,QuarantineTag
  ```

- Una nueva directiva antimalware en PowerShell requiere una directiva de filtro de malware (configuración) mediante el cmdlet **New-MalwareFilterPolicy** y una regla de filtro de malware exclusiva (filtros de destinatarios) mediante el cmdlet **New-MalwareFilterRule** . Para obtener instrucciones, consulte [Uso Exchange Online PowerShell o PowerShell EOP independiente para configurar directivas antimalware](configure-anti-malware-policies.md#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-malware-policies).

En este ejemplo se crea una directiva de filtro de malware denominada Departamento de investigación que usa la directiva de cuarentena personalizada denominada NoAccess que asigna permisos **Sin acceso** a los mensajes en cuarentena.

```powershell
New-MalwareFilterPolicy -Name "Research Department" -QuarantineTag NoAccess
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [New-MalwareFilterPolicy](/powershell/module/exchange/new-malwarefilterpolicy).

En este ejemplo se modifica la directiva de filtro de malware existente denominada Recursos humanos mediante la asignación de la directiva de cuarentena personalizada denominada NoAccess que asigna permisos **Sin acceso** a los mensajes en cuarentena.

```powershell
New-MalwareFilterPolicy -Identity "Human Resources" -QuarantineTag NoAccess
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Set-MalwareFilterPolicy](/powershell/module/exchange/set-malwarefilterpolicy).

### <a name="safe-attachments-policies-in-defender-for-office-365"></a>Directivas de datos adjuntos seguros en Defender para Office 365

1. En el [portal de Microsoft 365 Defender](https://security.microsoft.com), vaya a **Directivas de colaboración** \> **Email & & reglas** \> **Directivas de amenazas** \> **Datos adjuntos seguros** en la sección **Directivas**.

   O bien, para ir directamente a la página **Datos adjuntos seguros** , use <https://security.microsoft.com/safeattachmentv2>.

2. En la página **Datos adjuntos seguros** , realice uno de los pasos siguientes:
   - Busque y seleccione una directiva de datos adjuntos seguros existente.
   - Cree una nueva directiva de datos adjuntos seguros.

3. Realice uno de los pasos siguientes:
   - **Editar existente**: seleccione la directiva haciendo clic en el nombre de la directiva. En el control flotante de detalles de la directiva, vaya a la sección **Configuración** y, a continuación, haga clic en **Editar configuración**.
   - **Crear nuevo**: en el asistente para nueva directiva, llegue a la página **Configuración** .

4. En la página **Configuración** , siga estos pasos:
   1. **Respuesta de malware desconocida de datos adjuntos seguros**: seleccione **Bloquear**, **Reemplazar** o **Entrega dinámica**.
   2. Seleccione una directiva de cuarentena en el cuadro **Directiva de cuarentena** .

   **Nota**: Al crear una nueva directiva, un valor de **directiva de cuarentena** en blanco indica que se usa la directiva de cuarentena predeterminada. Cuando edita posteriormente la directiva, el valor en blanco se reemplaza por el nombre predeterminado real de la directiva de cuarentena, como se describe en la tabla anterior.

Las instrucciones completas para crear y modificar directivas de datos adjuntos seguros se describen en [Configuración de directivas de datos adjuntos seguros en Microsoft Defender para Office 365](set-up-safe-attachments-policies.md).

#### <a name="safe-attachments-policies-in-powershell"></a>Directivas de datos adjuntos seguros en PowerShell

Si prefiere usar PowerShell para asignar directivas de cuarentena en directivas de datos adjuntos seguros, conéctese a Exchange Online PowerShell o Exchange Online Protection PowerShell y use la sintaxis siguiente:

```powershell
<New-SafeAttachmentPolicy -Name "<Unique name>" | Set-SafeAttachmentPolicy -Identity "<Policy name>"> -Enable $true -Action <Block | Replace | DynamicDelivery> [-QuarantineTag <QuarantineTagName>]
```

**Notas**:

- Los valores de parámetro _Action_ Block, Replace o DynamicDelivery pueden dar lugar a mensajes en cuarentena (el valor Permitir no pone en cuarentena los mensajes). Valor del parámetro _Action_ en significativo solo cuando el valor del parámetro _Enable_ es `$true`.

- Al crear nuevas directivas de datos adjuntos seguros sin usar el parámetro QuarantineTag, se usa la directiva de cuarentena predeterminada para las detecciones de datos adjuntos seguros en el correo electrónico (AdminOnlyAccessPolicy).

  Debe reemplazar la directiva de cuarentena predeterminada por una directiva de cuarentena personalizada solo si desea cambiar las funcionalidades predeterminadas del usuario final en los mensajes de correo electrónico que están en cuarentena mediante directivas de datos adjuntos seguros.

  Para ver los valores de parámetro importantes, ejecute el siguiente comando:

  ```powershell
  Get-SafeAttachmentPolicy | Format-List Name,Enable,Action,QuarantineTag
  ```

- Una nueva directiva de datos adjuntos seguros en PowerShell requiere una directiva de datos adjuntos seguros (configuración) mediante el cmdlet **New-SafeAttachmentPolicy** y una regla de datos adjuntos seguros exclusivos (filtros de destinatarios) mediante el cmdlet **New-SafeAttachmentRule** . Para obtener instrucciones, consulte [Uso Exchange Online PowerShell o PowerShell EOP independiente para configurar directivas de datos adjuntos seguros](set-up-safe-attachments-policies.md#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies).

En este ejemplo se crea una directiva de datos adjuntos segura denominada Departamento de investigación que bloquea los mensajes detectados y usa la directiva de cuarentena personalizada denominada NoAccess que asigna permisos **Sin acceso** a los mensajes en cuarentena.

```powershell
New-SafeAttachmentPolicy -Name "Research Department" -Enable $true -Action Block -QuarantineTag NoAccess
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [New-MalwareFilterPolicy](/powershell/module/exchange/new-malwarefilterpolicy).

En este ejemplo se modifica la directiva de datos adjuntos seguros existente denominada Recursos humanos mediante la asignación de la directiva de cuarentena personalizada denominada NoAccess que asigna permisos **Sin acceso** .

```powershell
Set-SafeAttachmentPolicy -Identity "Human Resources" -QuarantineTag NoAccess
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Set-MalwareFilterPolicy](/powershell/module/exchange/set-malwarefilterpolicy).

## <a name="configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal"></a>Configuración de la notificación de cuarentena global en el portal de Microsoft 365 Defender

La configuración global de las directivas de cuarentena le permite personalizar las notificaciones de cuarentena que se envían a los destinatarios de los mensajes en cuarentena si las notificaciones de cuarentena están activadas en la directiva de cuarentena. Para obtener más información sobre estas notificaciones, consulte [Cuarentena de notificaciones](use-spam-notifications-to-release-and-report-quarantined-messages.md).

1. En el portal de Microsoft 365 Defender, vaya a **directivas de colaboración** \> de Email & **& reglas** \>  \> Directivas de **cuarentena** de amenazas en la sección **Reglas**. O bien, para ir directamente a la página **Directivas de cuarentena** , use <https://security.microsoft.com/quarantinePolicies>.

2. En la página **Directivas de cuarentena** , seleccione **Configuración global**.

3. En el control flotante **Configuración de notificación de cuarentena** que se abre, configure los siguientes valores:

   - Personalice las notificaciones de cuarentena en función del idioma del destinatario:

     - **Nombre para mostrar** del remitente que se usa en las notificaciones de cuarentena, como se muestra en la captura de pantalla siguiente.

       :::image type="content" source="../../media/quarantine-tags-esn-customization-display-name.png" alt-text="Nombre para mostrar del remitente personalizado en una notificación de cuarentena." lightbox="../../media/quarantine-tags-esn-customization-display-name.png":::

     - Texto **de declinación de responsabilidades** que se agrega a la parte inferior de las notificaciones de cuarentena. El texto localizado, **una declinación de responsabilidades de su organización:** siempre se incluye primero, seguido del texto que especifique como se muestra en la captura de pantalla siguiente:

       :::image type="content" source="../../media/quarantine-tags-esn-customization-disclaimer.png" alt-text="Una declinación de responsabilidades personalizada en la parte inferior de una notificación de cuarentena." lightbox="../../media/quarantine-tags-esn-customization-disclaimer.png":::

     - Identificador de idioma para los valores **Nombre para mostrar** y **Declinación de responsabilidades** . Las notificaciones de cuarentena ya están localizadas en función de la configuración de idioma del destinatario. Los valores **Nombre para mostrar** y **Declinación de responsabilidades** se usan en las notificaciones de cuarentena que se aplican al idioma del destinatario.

       Seleccione el idioma en el cuadro **Elegir idioma** _antes de_ escribir valores en los cuadros **Nombre para mostrar** y **Declinación de responsabilidades** . Al cambiar el valor en el cuadro **Elegir idioma** , se vacían los valores de los cuadros **Nombre para mostrar** y **Declinación de responsabilidades** .

     Siga estos pasos para personalizar las notificaciones de cuarentena en función del idioma del destinatario:

     1. Seleccione el idioma en el cuadro **Elegir idioma** . El valor predeterminado es **Predeterminado**, lo que significa el idioma predeterminado para la organización de Microsoft 365. Para obtener más información, vea [Cómo establecer la configuración de idioma y región para Microsoft 365](/office365/troubleshoot/access-management/set-language-and-region).
     2. Escriba los valores de **Nombre para mostrar** y **Declinación de responsabilidades**. Los valores deben ser únicos para cada idioma. Si intenta reutilizar un **valor de Nombre para mostrar** o **Declinación de responsabilidades** para varios idiomas, recibirá un error al hacer clic en **Guardar**.
     3. Haga clic en el botón **Agregar**.
     4. Repita los pasos anteriores para crear un máximo de tres notificaciones de cuarentena personalizadas en función del idioma del destinatario. Un cuadro sin etiquetar muestra los idiomas que ha configurado:

        :::image type="content" source="../../media/quarantine-tags-esn-customization-selected-languages.png" alt-text="Los idiomas seleccionados en la configuración de notificación de cuarentena global de las directivas de cuarentena." lightbox="../../media/quarantine-tags-esn-customization-selected-languages.png":::

   - **Usar el logotipo de mi empresa**: seleccione esta opción para reemplazar el logotipo de Microsoft predeterminado que se usa en la parte superior de las notificaciones de cuarentena. Antes de realizar este paso, debe seguir las instrucciones de [Personalización del tema de Microsoft 365 para que su organización](../../admin/setup/customize-your-organization-theme.md) cargue el logotipo personalizado. Esta opción no se admite si su organización tiene un logotipo personalizado que apunta a una dirección URL en lugar de a un archivo de logotipo personalizado cargado. 

     En la captura de pantalla siguiente se muestra un logotipo personalizado en una notificación de cuarentena:

     :::image type="content" source="../../media/quarantine-tags-esn-customization-logo.png" alt-text="Logotipo personalizado en una notificación de cuarentena" lightbox="../../media/quarantine-tags-esn-customization-logo.png":::

   - **Enviar una notificación de correo no deseado del usuario final cada (días):** seleccione la frecuencia de las notificaciones de cuarentena. El valor predeterminado es de 3 días, pero puede seleccionar de 1 a 15 días.

4. Cuando haya terminado, haga clic en **Guardar**.

   :::image type="content" source="../../media/mdo-quarantine-policy-quarantine-notification-settings.png" alt-text="Control flotante de configuración de notificaciones de cuarentena en el portal de Microsoft 365 Defender." lightbox="../../media/mdo-quarantine-policy-quarantine-notification-settings.png":::

## <a name="view-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Ver directivas de cuarentena en el portal de Microsoft 365 Defender

1. En el portal de Microsoft 365 Defender, vaya a **directivas de colaboración** \> de Email & **& reglas** \>  \> Directivas de **cuarentena** de amenazas en la sección **Reglas**. O bien, para ir directamente a la página **Directivas de cuarentena** , use <https://security.microsoft.com/quarantinePolicies>.

2. La página **Directivas de cuarentena** muestra la lista de directivas por **nombre** y **fecha de última actualización** .

3. Para ver la configuración de las directivas de cuarentena integradas o personalizadas, seleccione la directiva de cuarentena de la lista haciendo clic en el nombre.

4. Para ver la configuración global, haga clic en **Configuración global.**

### <a name="view-quarantine-policies-in-powershell"></a>Visualización de directivas de cuarentena en PowerShell

Si prefiere usar PowerShell para ver las directivas de cuarentena, siga estos pasos:

- Para ver una lista de resumen de todas las directivas integradas o personalizadas, ejecute el siguiente comando:

  ```powershell
  Get-QuarantinePolicy | Format-Table Name
  ```

- Para ver la configuración de las directivas de cuarentena integradas o personalizadas, reemplace por \<QuarantinePolicyName\> el nombre de la directiva de cuarentena y ejecute el siguiente comando:

  ```powershell
  Get-QuarantinePolicy -Identity "<QuarantinePolicyName>"
  ```

- Para ver la configuración global de las notificaciones de cuarentena, ejecute el siguiente comando:

  ```powershell
  Get-QuarantinePolicy -QuarantinePolicyType GlobalQuarantinePolicy
  ```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).

## <a name="modify-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Modificación de directivas de cuarentena en el portal de Microsoft 365 Defender

No puede modificar las directivas de cuarentena integradas denominadas AdminOnlyAccessPolicy o DefaultFullAccessPolicy. Puede modificar la directiva integrada denominada NotificationEnabledPolicy ([si la tiene](#full-access-permissions-and-quarantine-notifications)) y las directivas de cuarentena personalizadas.

1. En el portal de Microsoft 365 Defender, vaya a **directivas de colaboración** \> de Email & **& reglas** \>  \> Directivas de **cuarentena** de amenazas en la sección **Reglas**. O bien, para ir directamente a la página **Directivas de cuarentena** , use <https://security.microsoft.com/quarantinePolicies>.

2. En la página **Directivas de cuarentena** , seleccione la directiva haciendo clic en el nombre.

3. Después de seleccionar la directiva, haga clic en el ![icono Editar directiva.](../../media/m365-cc-sc-edit-icon.png) **Icono de edición de directiva** que aparece.

4. El Asistente para **editar directivas** que se abre es prácticamente idéntico al Asistente para **nueva directiva**, tal como se describe en la sección [Crear directivas de cuarentena en el portal de Microsoft 365 Defender](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal) anteriormente en este artículo.

   La principal diferencia es que no se puede cambiar el nombre de una directiva existente.

5. Cuando haya terminado de modificar la directiva, vaya a la página **Resumen** y haga clic en **Enviar**.

### <a name="modify-quarantine-policies-in-powershell"></a>Modificación de directivas de cuarentena en PowerShell

Si prefiere usar PowerShell para modificar una directiva de cuarentena personalizada, reemplace por \<QuarantinePolicyName\> el nombre de la directiva de cuarentena y use la sintaxis siguiente:

```powershell
Set-QuarantinePolicy -Identity "<QuarantinePolicyName>" [Settings]
```

La configuración disponible es la misma que se describió para crear directivas de cuarentena anteriormente en este artículo.

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Set-QuarantinePolicy](/powershell/module/exchange/set-quarantinepolicy).

## <a name="remove-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Eliminación de directivas de cuarentena en el portal de Microsoft 365 Defender

**Notas**:

- No puede quitar las directivas de cuarentena integradas denominadas AdminOnlyAccessPolicy o DefaultFullAccessPolicy. Puede quitar la directiva integrada denominada NotificationEnabledPolicy ([si la tiene](#full-access-permissions-and-quarantine-notifications)) y las directivas de cuarentena personalizadas.
- Antes de quitar una directiva de cuarentena, compruebe que no se está usando. Por ejemplo, ejecute el siguiente comando en PowerShell:

  ```powershell
  Write-Output -InputObject "Anti-spam policies","----------------------";Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag; Write-Output -InputObject "Anti-phishing policies","----------------------";Get-AntiPhishPolicy | Format-List Name,*QuarantineTag; Write-Output -InputObject "Anti-malware policies","----------------------";Get-MalwareFilterPolicy | Format-List Name,QuarantineTag; Write-Output -InputObject "Safe Attachments policies","---------------------------";Get-SafeAttachmentPolicy | Format-List Name,QuarantineTag
  ```

  Si se usa la directiva de cuarentena, [reemplace la directiva de cuarentena asignada](#step-2-assign-a-quarantine-policy-to-supported-features) antes de quitarla.

1. En el portal de Microsoft 365 Defender, vaya a **directivas de colaboración** \> de Email & **& reglas** \>  \> Directivas de **cuarentena** de amenazas en la sección **Reglas**. O bien, para ir directamente a la página **Directivas de cuarentena** , use <https://security.microsoft.com/quarantinePolicies>.

2. En la página **Directivas de cuarentena** , seleccione la directiva de cuarentena personalizada que desea quitar haciendo clic en el nombre.

3. Después de seleccionar la directiva, haga clic en el ![icono Eliminar directiva.](../../media/m365-cc-sc-delete-icon.png) **Eliminar icono de directiva** que aparece.

4. Haga clic en **Quitar directiva** en el cuadro de diálogo de confirmación que aparece.

### <a name="remove-quarantine-policies-in-powershell"></a>Eliminación de directivas de cuarentena en PowerShell

Si prefiere usar PowerShell para quitar una directiva de cuarentena personalizada, reemplace por \<QuarantinePolicyName\> el nombre de la directiva de cuarentena y ejecute el siguiente comando:

```powershell
Remove-QuarantinePolicy -Identity "<QuarantinePolicyName>"
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Remove-QuarantinePolicy](/powershell/module/exchange/remove-quarantinepolicy).

## <a name="system-alerts-for-quarantine-release-requests"></a>Alertas del sistema para solicitudes de lanzamiento en cuarentena

De forma predeterminada, la directiva de alerta predeterminada denominada **User requested to release a quarantined message** automatically generates an informational alert and sends notification messages to members of the following role groups whenever a user requests the release of a quarantined message:

- Administrador de cuarentena
- Administrador de seguridad
- Administración de la organización (administrador global)

Los administradores pueden personalizar los destinatarios de notificaciones por correo electrónico o crear una directiva de alertas personalizada para obtener más opciones.

Para obtener más información sobre las directivas de alerta, consulte [Directivas de alerta en Microsoft 365](../../compliance/alert-policies.md).

## <a name="quarantine-policy-permission-details"></a>Detalles del permiso de directiva de cuarentena

En las secciones siguientes se describen los efectos de los grupos de permisos preestablecidos y los permisos individuales en los detalles de los mensajes en cuarentena y en las notificaciones de cuarentena.

### <a name="preset-permissions-groups"></a>Grupos de permisos preestablecidos

Los permisos individuales que se incluyen en los grupos de permisos preestablecidos se enumeran en la tabla al principio de este artículo.

#### <a name="no-access"></a>Sin acceso

Si la directiva de cuarentena asigna los permisos **Sin acceso** (solo acceso de administrador), los usuarios no podrán ver los mensajes que están en cuarentena:

- **Detalles del mensaje en cuarentena**: no se mostrará ningún mensaje en la vista del usuario final.
- **Notificaciones de cuarentena**: no se enviará ninguna notificación para esos mensajes.

#### <a name="limited-access"></a>Acceso limitado

Si la directiva de cuarentena asigna los permisos **de acceso limitado** , los usuarios obtienen las siguientes funcionalidades:

- **Detalles del mensaje en cuarentena**: están disponibles los siguientes botones:
  - **Solicitud de versión**
  - **Ver encabezados de mensaje**
  - **Vista previa de mensaje**
  - **Quitar de cuarentena**
  - **Bloquear remitente**

  :::image type="content" source="../../media/quarantine-tags-quarantined-message-details-limited-access.png" alt-text="Los botones disponibles en los detalles del mensaje en cuarentena si la directiva de cuarentena concede al usuario permisos de acceso limitados" lightbox="../../media/quarantine-tags-quarantined-message-details-limited-access.png":::

- **Notificaciones de cuarentena**: están disponibles los siguientes botones:
  - **Bloquear remitente**
  - **Solicitud de versión**
  - **Revisar**

  :::image type="content" source="../../media/quarantine-tags-esn-limited-access.png" alt-text="Los botones disponibles en la notificación de cuarentena si la directiva de cuarentena concede al usuario permisos de acceso limitados" lightbox="../../media/quarantine-tags-esn-limited-access.png":::

#### <a name="full-access"></a>Acceso completo

Si la directiva de cuarentena asigna los permisos **de acceso completo** (todos los permisos disponibles), los usuarios obtienen las siguientes funcionalidades:

- **Detalles del mensaje en cuarentena**: están disponibles los siguientes botones:
  - **Mensaje de versión**
  - **Ver encabezados de mensaje**
  - **Vista previa de mensaje**
  - **Quitar de cuarentena**
  - **Bloquear remitente**

  :::image type="content" source="../../media/quarantine-tags-quarantined-message-details-full-access.png" alt-text="Los botones disponibles en los detalles del mensaje en cuarentena si la directiva de cuarentena concede al usuario permisos de acceso completo" lightbox="../../media/quarantine-tags-quarantined-message-details-full-access.png":::

- **Notificaciones de cuarentena**: están disponibles los siguientes botones:
  - **Bloquear remitente**
  - **Release**
  - **Revisar**

  :::image type="content" source="../../media/quarantine-tags-esn-full-access.png" alt-text="Los botones disponibles en la notificación de cuarentena si la directiva de cuarentena concede al usuario permisos de acceso completo" lightbox="../../media/quarantine-tags-esn-full-access.png":::

> [!NOTE]
> Como se explicó anteriormente, las notificaciones de cuarentena se deshabilitan en la directiva de cuarentena predeterminada denominada DefaultFullAccessPolicy, aunque esa directiva de cuarentena tenga asignado el grupo de permisos **de acceso completo** . Las notificaciones de cuarentena solo están disponibles en las directivas de cuarentena personalizadas que cree o en la directiva de acceso de cuarentena predeterminada denominada NotificationEnabledPolicy ([si esa directiva está disponible en su organización](#full-access-permissions-and-quarantine-notifications)).

### <a name="individual-permissions"></a>Permisos individuales

#### <a name="block-sender-permission"></a>Bloquear permiso de remitente

El permiso **Bloquear remitente** (_PermissionToBlockSender_) controla el acceso al botón que permite a los usuarios agregar convenientemente el remitente del mensaje en cuarentena a su lista de remitentes bloqueados.

- **Detalles del mensaje en cuarentena**:
  - **Bloquear permiso de remitente** habilitado: el botón **Bloquear remitente** está disponible.
  - **Bloquear permiso de remitente** deshabilitado: el botón **Bloquear remitente** no está disponible.

- **Notificaciones de cuarentena**:
  - **Bloquear permiso de remitente** habilitado: el botón **Bloquear remitente** está disponible.
  - **Bloquear permiso de remitente** deshabilitado: el botón **Bloquear remitente** no está disponible.

Para obtener más información sobre la lista Remitentes bloqueados, vea [Bloquear mensajes de alguien](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) y [Usar Exchange Online PowerShell para configurar la colección de listas seguras en un buzón](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).

#### <a name="delete-permission"></a>Permiso de eliminación

El permiso **Eliminar** (_PermissionToDelete_) controla la capacidad de los usuarios para eliminar sus mensajes (mensajes en los que el usuario es un destinatario) de la cuarentena.

- **Detalles del mensaje en cuarentena**:
  - **Permiso de eliminación** habilitado: el botón **Quitar de la cuarentena** está disponible.
  - **Permiso de eliminación** deshabilitado: el botón **Quitar de la cuarentena** no está disponible.

- **Notificaciones de cuarentena**: sin efecto.

#### <a name="preview-permission"></a>Permiso de vista previa

El permiso **De vista previa** (_PermissionToPreview_) controla la capacidad de los usuarios para obtener una vista previa de sus mensajes en cuarentena.

- **Detalles del mensaje en cuarentena**:
  - **Permiso de vista previa** habilitado: el botón **De vista previa del mensaje** está disponible.
  - **Permiso de vista previa** deshabilitado: el botón **De vista previa del mensaje** no está disponible.

- **Notificaciones de cuarentena**: sin efecto.

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a>Permitir que los destinatarios liberen un mensaje del permiso de cuarentena

> [!NOTE]
> Este permiso no se respeta en las directivas antimalware ni en el veredicto de suplantación de identidad de alta confianza en las directivas contra correo no deseado. Los usuarios no pueden liberar su propio malware o mensajes de suplantación de identidad de alta confianza de la cuarentena. En el mejor de los casos, puede usar [permitir que los destinatarios soliciten que se libere un mensaje del permiso de cuarentena](#allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission) .

**El permiso Permitir a los destinatarios liberar un mensaje del** permiso de cuarentena (_PermissionToRelease_) controla la capacidad de los usuarios de liberar sus mensajes en cuarentena directamente y sin la aprobación de un administrador.

- **Detalles del mensaje en cuarentena**:
  - Permiso habilitado: el botón **Release message (Liberar mensaje** ) está disponible.
  - Permiso deshabilitado: el botón **Liberar mensaje** no está disponible.

- **Notificaciones de cuarentena**:
  - Permiso habilitado: el botón **Liberar** está disponible.
  - Permiso deshabilitado: el botón **Liberar** no está disponible.

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a>Permitir que los destinatarios soliciten que se libere un mensaje del permiso de cuarentena

**Permitir que los destinatarios soliciten que se libere un mensaje del permiso de cuarentena** (_PermissionToRequestRelease_) controla la capacidad de los usuarios de _solicitar_ la liberación de sus mensajes en cuarentena. El mensaje solo se publica después de que un administrador apruebe la solicitud.

- **Detalles del mensaje en cuarentena**:
  - Permiso habilitado: el botón **Solicitar versión** está disponible.
  - Permiso deshabilitado: el botón **Solicitar versión** no está disponible.

- **Notificaciones de cuarentena**:
  - Permiso habilitado: el botón **Solicitar versión** está disponible.
  - Permiso deshabilitado: el botón **Solicitar versión** no está disponible.
