---
title: Configuración de correo electrónico notificada por el usuario para correo no deseado, phish, como correo malintencionado
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 07/19/2022
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: Los administradores pueden aprender a identificar un buzón personalizado (también conocido como buzón de envíos de usuario) para recopilar mensajes de spam y phishing que notifican los usuarios. Otras configuraciones completan la experiencia de generación de informes para los usuarios cuando notifican mensajes.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c32d4ff27d44600ebe182f0764cb47c638a354c7
ms.sourcegitcommit: e8dd5cd434d17af7096d28d467a2b3b021cbb233
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "67051676"
---
# <a name="user-reported-message-settings"></a>Configuración del mensaje notificado por el usuario

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones de Exchange Online, puede dirigir el correo a un buzón personalizado (también conocido como _buzón de envíos de usuario_) cuando los usuarios informen de mensajes malintencionados o no malintencionados. Cuando los usuarios notifican mensajes de correo electrónico mediante las opciones de informes admitidas, los administradores pueden configurar la configuración de mensajes notificados por el usuario en su organización para enviar mensajes notificados al buzón de correo de envíos de usuarios. Puede configurar el buzón de correo de envíos de usuario para interceptar los mensajes notificados por el usuario (solo enviar al buzón de correo de envíos de usuario) o recibir copias de los mensajes notificados por el usuario a medida que los usuarios informan de los mensajes a Microsoft. Esta configuración se conocía anteriormente como directiva _de envíos de usuarios_.

La configuración de mensajes notificada por el usuario y el buzón de correo de envíos de usuario funcionan con las siguientes opciones de informes de mensajes:

- [Complemento Mensaje de informe](enable-the-report-message-add-in.md)
- [Complemento de suplantación de identidad de informe](enable-the-report-phish-add-in.md)
- [Herramientas de informes de terceros](#third-party-reporting-tools-options)

Entregar mensajes notificados por el usuario a un buzón de correo de envíos de usuario en lugar de directamente a Microsoft permite a los administradores informar de forma selectiva y manual de los mensajes a Microsoft en la página **Envíos** de <https://security.microsoft.com/reportsubmission>. Para obtener más información, consulte [Administración envío](admin-submission.md).

  > [!NOTE]
  > Si los informes se han [deshabilitado en Outlook en la Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), la habilitación de los mensajes notificados por el usuario aquí invalidará esa configuración y permitirá a los usuarios informar de los mensajes en Outlook en la Web de nuevo.

## <a name="configuration-requirements-for-the-user-submissions-mailbox"></a>Requisitos de configuración para el buzón de correo de envíos de usuario

Antes de empezar, yu debe configurar Exchange Online Protection y Defender para Office 365 para que los mensajes notificados por el usuario se entreguen al buzón de envíos del usuario sin filtrarse como se describe en los pasos siguientes:

- Identifique el buzón de correo de envíos de usuario como buzón de SecOps. Para obtener instrucciones, consulte [Uso del portal de Microsoft 365 Defender para configurar buzones de SecOps en la directiva de entrega avanzada](configure-advanced-delivery.md#use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy).

- Cree una directiva de antimalware personalizada para el buzón de correo de envíos de usuario con la siguiente configuración:

  - Desactive Purga automática de cero horas (ZAP) para malware (la sección \>**Configuración de protección** **Habilitar purga automática de cero horas para malware** no está seleccionada o `-ZapEnabled $false` en PowerShell).

  - Desactivar el filtrado de datos adjuntos comunes (sección \>**Configuración de protección** **Habilitar el filtro de datos adjuntos comunes** no está seleccionado o `EnableFileFilter $false` en PowerShell).
  
  Para obtener instrucciones, consulte [Creación de una directiva antimalware](configure-anti-malware-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-malware-policies).

- Compruebe que el buzón de correo de envíos de usuario no está incluido en las directivas de seguridad preestablecidas **Estándar** o **Estricta** . Para obtener instrucciones, consulte [Directivas de seguridad preestablecidas](preset-security-policies.md).

- **Defender para Office 365**: Configure los siguientes valores adicionales:

  - Excluya el buzón de correo de envíos de usuario de la directiva de seguridad preestablecida **de protección integrada** . Para obtener instrucciones, consulte [Directivas de seguridad preestablecidas](preset-security-policies.md).

  - Cree una directiva de datos adjuntos seguros para el buzón de correo de envíos del usuario en el que el examen de datos adjuntos seguros, incluida la entrega dinámica, esté desactivado (**sección** \> Configuración \> **datos adjuntos seguros respuesta de malware desconocido** **Desactivado** o `-Enable $false` en PowerShell). Para obtener instrucciones, consulte [Configurar directivas de datos adjuntos seguros en Microsoft Defender para Office 365](set-up-safe-attachments-policies.md).

  - Cree una directiva de vínculos seguros para el buzón de correo de envíos de usuarios donde el examen de vínculos seguros en el correo electrónico está desactivado (**url & configuración de** \> protección de **clics Activada: Vínculos seguros comprueba una lista de vínculos malintencionados conocidos cuando los usuarios hacen clic en vínculos en el correo electrónico** no está seleccionado o `EnableSafeLinksForEmail $false` en PowerShell). Para obtener instrucciones, consulte [Configuración de directivas de vínculos seguros en Microsoft Defender para Office 365](set-up-safe-links-policies.md).

Después de comprobar que el buzón cumple estos requisitos, use el resto de las instrucciones de este artículo para identificar el buzón de correo de envíos de usuario y otras configuraciones de mensajes notificadas por el usuario.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Envíos de usuarios** , use <https://security.microsoft.com/userSubmissionsReportMessage>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Para modificar la configuración de los envíos de usuarios, debe ser miembro de uno de los siguientes grupos de roles:

  - **Administración de la organización** o **administrador de seguridad** en los [permisos del portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

- Necesita acceso a Exchange Online PowerShell. Si la cuenta que intenta usar no tiene acceso a Exchange Online PowerShell, recibirá un error similar al siguiente al especificar el buzón de correo de envíos:

  > Especificar una dirección de correo electrónico en el dominio

  Para obtener más información sobre cómo habilitar o deshabilitar el acceso a Exchange Online PowerShell, consulte los temas siguientes:

  - [Habilitar o deshabilitar el acceso al PowerShell de Exchange Online](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [Reglas de acceso de cliente en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox-for-email"></a>Use el portal de Microsoft 365 Defender para configurar el buzón de correo electrónico de envíos de usuario

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas** \> **Directivas** \> de amenazas **Configuración de mensajes notificados por el usuario** en la sección **Otros**. Para ir directamente a la página **Envíos de usuarios** , use <https://security.microsoft.com/userSubmissionsReportMessage>.

2. En la página **Envíos** de usuarios, lo que ve viene determinado en gran medida por el botón de alternancia **del mensaje de informe de Microsoft Outlook** :

   - **En** ![ Activar.](../../media/scc-toggle-on.png): usa la experiencia de informes integrada de Microsoft, que incluye el complemento Mensaje de informe, el complemento De suplantación de identidad de informe o los informes integrados en Outlook en la Web.

     Esta configuración también permite a los usuarios notificar mensajes falsos positivos desde el portal de cuarentena.

   - **Desactivado** ![ ](../../media/scc-toggle-off.png)Desactivar: se usan herramientas de informes de mensajes de terceros en lugar de la experiencia de informes integrada de Microsoft.

Las opciones de configuración relacionadas se describen en las secciones siguientes.

### <a name="microsoft-integrated-reporting-experience-options"></a>Opciones de la experiencia de informes integrada de Microsoft

Cuando el **botón Mensaje de informe de Microsoft Outlook** está **Activado** ![para alternar,](../../media/scc-toggle-on.png) la siguiente configuración está disponible en la página **Envíos de usuarios** :

- **Enviar los mensajes notificados a la** sección: Seleccione una de las siguientes opciones:

  - **Microsoft**: no se usa el buzón de correo de envíos de usuario (todos los mensajes notificados van a Microsoft para su análisis).

  - **Buzón de Microsoft y mi organización**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de correo Exchange Online existente que se usará como buzón de correo de envíos del usuario. No se permiten grupos de distribución. Los envíos de usuarios van a Microsoft para su análisis y al buzón de correo de envíos de usuario para que un equipo de operaciones de seguridad o administrador los analice.

  - **Buzón de mi organización**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de correo Exchange Online existente. No se permiten grupos de distribución. Los envíos de usuarios solo van al buzón de correo de envíos de usuario para que un administrador o el equipo de operaciones de seguridad los analice. Los mensajes no van a Microsoft para su análisis a menos que un administrador envíe manualmente los mensajes.

  > [!IMPORTANT]
  > En las organizaciones gubernamentales de Ee. UU. (GCC, GCC High y DoD), la única selección disponible en la sección **Enviar los mensajes notificados a es el** **buzón de mi organización**. Las otras dos opciones están atenuadas.
  >
  > Si ha usado [Outlook en la Web directivas de buzón de correo](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/configure-outlook-web-app-mailbox-policy-properties) para deshabilitar los informes de correo no deseado en Outlook en la Web, pero selecciona **Microsoft** o **Microsoft y el buzón de mi organización**, los usuarios podrán notificar mensajes a Microsoft en Outlook en la Web mediante el complemento Mensaje de informe o el complemento Suplantación de identidad de informe.
  >
  > Si selecciona **el buzón de mi organización**, los mensajes notificados aparecerán en la pestaña **Mensajes notificados** por el usuario de la página **Envíos** de <https://security.microsoft.com/reportsubmission>. Pero el valor **Result** de estos mensajes siempre estará vacío, ya que los mensajes no se examinaron de nuevo.
  >
  > Si usa [el entrenamiento de simulación de ataques](attack-simulation-training-get-started.md) o un producto de terceros para realizar simulaciones de suplantación de identidad (phishing), debe configurar el buzón de correo de envíos de usuario como buzón de SecOps, tal como se describió anteriormente en la sección [Requisitos de configuración para el buzón de envíos de usuario](#configuration-requirements-for-the-user-submissions-mailbox) anteriormente en este artículo. Si no lo hace, un usuario que informe de un mensaje podría desencadenar una asignación de entrenamiento en el producto de simulación de suplantación de identidad (phishing).

  Independientemente de la selección, la siguiente configuración también está disponible en la sección **Enviar los mensajes notificados a** :

  - **Permitir a los usuarios elegir si quieren informar**: esta configuración controla las opciones que están disponibles en la sección **Seleccionar opciones de informes que están disponibles para los usuarios** :

    - **Permitir que los usuarios elijan si quieren informar** seleccionados: puede seleccionar algunas opciones, todas o ninguna de ellas en la sección **Seleccionar opciones de informes que están disponibles para los usuarios** .
    - **Permitir que los usuarios elijan si quieren informar** de que no están seleccionados: solo puede seleccionar una opción en la sección **Seleccionar opciones de informes que están disponibles para los usuarios** .

    - **Seleccione las opciones de informes que están disponibles para los usuarios** :
      - **Pregúnteme antes de enviar el mensaje**
      - **Informar siempre del mensaje**
      - **Nunca informe del mensaje**

- **Sección experiencia de informes de usuario** : están disponibles las siguientes opciones:

  Como se muestra en la página, si selecciona una opción que envía los mensajes notificados a Microsoft, también se agrega el texto siguiente a la notificación:

  > Su correo electrónico se enviará tal y como está a Microsoft para su análisis. Algunos correos electrónicos pueden contener información personal o confidencial.

  - **Antes de la pestaña Informes** : en los cuadros **Título** y **Cuerpo del mensaje** , escriba el texto descriptivo que los usuarios ven antes de que informen de un mensaje mediante el complemento Mensaje de informe o el complemento Suplantación de identidad de informe. Puede usar la variable `%type%` para incluir el tipo de envío (correo no deseado, no correo no deseado, phishing, etc.).
  - **Pestaña Después de informar** : en los cuadros **de mensaje Título** y **Confirmación** , escriba el texto descriptivo que los usuarios ven después de que informen de un mensaje mediante el complemento Mensaje de informe o el complemento De suplantación de identidad de informe. Puede usar la variable `%type%` para incluir el tipo de envío.

  - **Solo se muestra cuando el usuario notifica suplantación de identidad (phishing**): seleccione esta opción para mostrar las notificaciones **Antes de informar** y **Después de informar** solo cuando los usuarios notifiquen mensajes como suplantación de identidad (phishing). De lo contrario, se muestran las notificaciones para todos los mensajes notificados.

- **Email sección de notificaciones para los resultados de la revisión del administrador**: Están disponibles las siguientes opciones:

  - **Especifique Office 365 dirección de correo electrónico que se usará como remitente**: seleccione esta configuración y escriba la dirección de correo electrónico en el cuadro que aparece.
  
  - **Personalizar notificaciones**: haga clic en este vínculo para personalizar la notificación por correo electrónico que se envía después de que un administrador revise y marque los mensajes notificados.

    En el control flotante **Personalizar mensaje de confirmación** que aparece, configure los siguientes valores:

    - **Pestañas de phishing**, **correo no deseado** y **No se encontraron amenazas** : en el **texto del resultado de la revisión** en algunas, ninguna o todas las pestañas, escriba el texto personalizado que se va a usar.
    - **Pestaña Pie de página** : están disponibles las siguientes opciones:
      - **Texto del pie de página**: escriba el texto del pie de página del mensaje personalizado que se va a usar.
      - **Mostrar logotipo de empresa**: antes de seleccionar esta opción, debe seguir las instrucciones de [Personalización del tema de Microsoft 365 para que su organización](../../admin/setup/customize-your-organization-theme.md) cargue el logotipo personalizado.

  Cuando haya terminado en el control flotante **Personalizar mensaje de confirmación** , haga clic en **Confirmar**.

- **Personalice la experiencia de su organización al notificar posibles amenazas en la sección de cuarentena** :

  **Botón de mensaje de informe de cuarentena**: compruebe que esta opción está **activada**![.](../../media/scc-toggle-on.png) para permitir que los usuarios informen de mensajes de cuarentena. De lo contrario, desactive esta opción **desactivar**![.](../../media/scc-toggle-off.png)

Cuando haya terminado en la página **Envíos de usuarios** , haga clic en **Guardar**. Para restaurar la configuración a sus valores inmediatamente anteriores, haga clic en **Restaurar**.

### <a name="third-party-reporting-tools-options"></a>Opciones de herramientas de informes de terceros

Puede desactivar la experiencia de informes integrada de Microsoft para usar herramientas de informes de mensajes de terceros para enviar mensajes notificados al buzón de correo de envíos de usuarios.

El único requisito es que los mensajes originales se incluyan como sin comprimir. EML o . Datos adjuntos MSG en los mensajes que se envían al buzón de correo de envíos de usuario. En otras palabras, no reenvíe los mensajes originales al buzón de correo de envíos del usuario.

> [!NOTE]
> Si existen varios datos adjuntos de correo electrónico en el mensaje, se descartará el envío. Solo se admite el mensaje con un archivo adjunto de correo electrónico.

Los requisitos de formato de mensaje se describen en la sección siguiente. El formato es opcional, pero los mensajes notificados no siguen el formato prescrito; los mensajes notificados siempre se identifican como phishing.

Cuando el **botón Mensaje de informe de Microsoft Outlook** está **desactivado**![, desactive la opción Desactivar.](../../media/scc-toggle-off.png) La siguiente configuración está disponible en la página **Envíos de usuarios** :

- **Buzón de Microsoft y mi organización**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de correo Exchange Online existente que se usará como buzón de correo de envíos del usuario. No se permiten grupos de distribución.

- **Personalice la experiencia de su organización al notificar posibles amenazas en la sección de cuarentena** :

  **Botón de mensaje de informe de cuarentena**: compruebe que esta opción está **activada**![.](../../media/scc-toggle-on.png) para permitir que los usuarios informen de mensajes de cuarentena. De lo contrario, desactive esta opción **desactivar**![.](../../media/scc-toggle-off.png)

Cuando haya terminado en la página **Envíos de usuarios** , haga clic en **Guardar**. Para restaurar la configuración a sus valores inmediatamente anteriores, haga clic en **Restaurar**.

#### <a name="message-submission-format"></a>Formato de envío de mensajes

Para identificar correctamente los mensajes adjuntos originales, los mensajes enviados al buzón personalizado requieren un formato específico. Si los mensajes no usan este formato, los mensajes adjuntos originales siempre se identifican como phishing.

Para especificar el motivo por el que se notificaron los mensajes adjuntos originales, los mensajes enviados al buzón de correo de envíos del usuario deben cumplir los criterios siguientes:

- Los datos adjuntos del mensaje original no están modificados.
- La línea asunto (título de sobre) de los mensajes enviados al buzón de envíos del usuario debe comenzar con uno de los siguientes valores de prefijo:
  - `1|` o `Junk:`.
  - `2|` o `Not junk:`.
  - `3|` o `Phishing:`.

  Por ejemplo:

  - `3|This text in the Subject line is ignored by the system`
  - `Not Junk:This text in the Subject line is also ignored by the system`

  Los mensajes que no siguen este formato no se mostrarán correctamente en la página **Envíos** de <https://security.microsoft.com/reportsubmission>.

## <a name="use-exchange-online-powershell-to-configure-the-user-submissions-mailbox-for-email"></a>Usar Exchange Online PowerShell para configurar el buzón de correo electrónico de envíos de usuario

Después de [conectarse a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell), use los **\*cmdlets -ReportSubmissionPolicy** y **\*-ReportSubmissionRule** para administrar y configurar el buzón de correo de envíos del usuario y la configuración relacionada.

En Exchange Online PowerShell, los elementos básicos de la configuración del buzón de correo de envíos de usuario son:

- **La directiva de envío de informes**: activa o desactiva la experiencia de informes integrada de Microsoft, activa o desactiva el envío de mensajes notificados a Microsoft, activa o desactiva el envío de mensajes notificados al buzón de correo de envíos de usuarios y la mayoría de las demás configuraciones.
- **La regla de envío de informes**: especifica la dirección de correo electrónico del buzón de correo de envíos de usuario o un valor en blanco cuando no se usa el buzón de envíos del usuario (solo notifica mensajes a Microsoft).

La diferencia entre estos dos elementos no es obvia al administrar la configuración del buzón de correo de envíos de usuarios en el portal de Microsoft 365 Defender:

- Solo hay una directiva de envío de informes denominada DefaultReportSubmissionPolicy y una regla de envío de informes denominada DefaultReportSubmissionRule de forma predeterminada.

  Si nunca ha ido a <https://security.microsoft.com/userSubmissionsReportMessage>, no hay ninguna directiva de envío de informes o regla de envío de informes (los cmdlets Get-ReportSubmissionPolicy y Get-ReportSubmissionRule no devuelven nada).

  Tan pronto como visite <https://security.microsoft.com/userSubmissionsReportMessage> e incluso antes de configurar cualquier configuración, la directiva de envío de informes se crea con los valores predeterminados y es visible en PowerShell.

  Como después de configurar y guardar la configuración en <https://security.microsoft.com/userSubmissionsReportMessage> para especificar un buzón de correo de envíos de usuario (experiencia de informes integrada de Microsoft o herramientas de terceros), la regla de envío de informes denominada DefaultReportSubmissionRule se crea automáticamente. Tenga en cuenta que la regla tarda varios segundos en verse en PowerShell.

- Puede eliminar la regla de envío de informes y volver a crearla con un nombre diferente, pero la regla siempre está asociada a la directiva de envío de informes cuyo nombre no se puede cambiar. Por lo tanto, se recomienda asignar un nombre a la regla DefaultReportSubmissionRule cada vez que cree o vuelva a crear la regla.

- Al especificar la dirección de correo electrónico del buzón de correo de envíos de usuario en el portal de Microsoft 365 Defender, ese valor se establece principalmente en la regla de envío de informes, pero el valor también se copia en las propiedades relacionadas de la directiva de envío de informes. En PowerShell, al establecer la dirección de correo electrónico en la regla, el valor no se copia en las propiedades relacionadas de la directiva. Para coherencia con el portal de Microsoft 365 Defender y para mayor claridad, se recomienda agregar o actualizar la dirección de correo electrónico en la directiva y la regla.

### <a name="use-powershell-to-view-the-report-submission-policy-and-the-report-submission-rule"></a>Uso de PowerShell para ver la directiva de envío de informes y la regla de envío de informes

Para ver la directiva de envío de informes, ejecute el siguiente comando en Exchange Online PowerShell:

```powershell
Get-ReportSubmissionPolicy
```

Para ver la regla de envío de informes, ejecute el siguiente comando:

```powershell
Get-ReportSubmissionRule
```

Para ver la directiva y la regla al mismo tiempo, ejecute los siguientes comandos:

```powershell
Write-Output -InputObject `r`n,"Report Submission Policy","-------------------------------------------------------------------------------------"; Get-ReportSubmissionPolicy; Write-Output -InputObject `r`n,"Report Submission Rule","-------------------------------------------------------------------------------------"; Get-ReportSubmissionRule
```

Recuerde que, si nunca ha ido a <https://security.microsoft.com/userSubmissionsReportMessage> o ha creado manualmente la directiva de envío de informes o la regla de envío de informes en PowerShell, no hay ninguna directiva de envío de informes o regla de envío de informes, por lo que los cmdlets **Get-ReportSubmissionPolicy** y **Get-ReportSubmissionRule** no devuelven nada.

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Get-ReportSubmissionPolicy](/powershell/module/exchange/get-reportsubmissionpolicy) y [Get-ReportSubmissionRule](/powershell/module/exchange/get-reportsubmissionrule).

### <a name="use-powershell-to-create-the-report-submission-policy-and-the-report-submission-rule"></a>Uso de PowerShell para crear la directiva de envío de informes y la regla de envío de informes

Si los cmdlets **Get-ReportSubmissionPolicy** y **Get-ReportSubmissionRule** no devuelven ninguna salida, puede crear la directiva de envío de informes y la regla de envío de informes. Si intenta crearlos cuando ya existen, recibirá un error.

Cree siempre primero la directiva de envío de informes, ya que especifique la directiva de envío de informes en la regla de envío de informes.

Para obtener información detallada sobre la sintaxis y los parámetros, vea [New-ReportSubmissionPolicy](/powershell/module/exchange/new-reportsubmissionpolicy) y [New-ReportSubmissionRule](/powershell/module/exchange/new-reportsubmissionrule).

#### <a name="use-powershell-to-enable-the-microsoft-integrated-reporting-experience-with-report-to-microsoft-only"></a>Uso de PowerShell para habilitar la experiencia de informes integrada de Microsoft solo con informes para Microsoft

En este ejemplo se crea la directiva de envío de informes con la configuración predeterminada (la misma configuración que la primera vez que visita <https://security.microsoft.com/userSubmissionsReportMessage>, pero antes de configurar o guardar cualquier configuración):

- La experiencia de creación de informes integrada de Microsoft está activada: **botón de mensaje de informe de Microsoft Outlook** alternar: **Activado** ![activar.](../../media/scc-toggle-on.png)

- Enviar solo mensajes notificados a Microsoft: **envíe los mensajes notificados a** \> **Microsoft**.

- No se necesita ni se especifica ningún buzón de correo de envío de usuario, por lo que no se crea la regla de envío de informes.

```powershell
New-ReportSubmissionPolicy
```

#### <a name="use-powershell-for-the-microsoft-integrated-reporting-experience-with-report-to-microsoft-and-the-user-submissions-mailbox"></a>Uso de PowerShell para la experiencia de informes integrada de Microsoft con informes a Microsoft y el buzón de correo de envíos de usuarios

En este ejemplo se crea la directiva de envío de informes y la regla de envío de informes con la siguiente configuración:

- La experiencia de creación de informes integrada de Microsoft está activada: **botón de mensaje de informe de Microsoft Outlook** alternar: **Activado** ![activar.](../../media/scc-toggle-on.png) En el cmdlet **New-ReportSubmissionPolicy** , el valor predeterminado del parámetro _EnableReportToMicrosoft_ es `$true` y el valor predeterminado del parámetro _EnableThirdPartyAddress_ es `$false`, por lo que no es necesario usarlos.

- Enviar mensajes notificados a Microsoft y al buzón de correo de envíos de usuarios: **Envíe los mensajes notificados a** Microsoft y al \> **buzón de mi organización**:

  - **New-ReportSubmissionPolicy**: `-ReportJunkToCustomizedAddress $true -ReportJunkAddresses <emailaddress> -ReportNotJunkToCustomizedAddress $true -ReportNotJunkAddresses <emailaddress> -ReportPhishToCustomizedAddress $true -ReportPhishAddresses <emailaddress>`.
  - **Set-ReportSubmissionRule**: `SentTo <emailaddress>`.

  En este ejemplo, la dirección de correo electrónico del buzón de correo de envíos de usuario se reportedmessages@contoso.com en Exchange Online (no se puede especificar una dirección de correo electrónico externa).

  > [!NOTE]
  > Debe usar el mismo valor de dirección de correo electrónico en todos los parámetros que identifican el buzón de correo de envíos de usuario.

Los parámetros restantes son necesarios para crear la directiva de envío de informes. En este ejemplo, se usan los valores predeterminados. Si no especifica los valores predeterminados como se describe en este ejemplo, es posible que se requieran parámetros y configuraciones adicionales:

- **Deje que los usuarios elijan si quieren informar** de las opciones seleccionadas (`-DisableUserSubmissionOptions $false`) y no se selecciona **Seleccionar las opciones de informes que están disponibles para los usuarios** (se usa el valor `0` predeterminado del parámetro _UserSubmissionOptions_).
- **Sección experiencia de informes de usuario** :
  - No se especifica nada en los cuadros **Título** y **Cuerpo del mensaje** de las pestañas **Antes de informar** o **Después de informar** ().`-EnableCustomizedMsg $false`
  - **Solo se muestra cuando el usuario notifica la suplantación de identidad (phishing** ) seleccionada (`-OnlyShowPhishingDisclaimer $true`).
- **Email sección de notificaciones para los resultados de la revisión del administrador**:
  - **Especifique Office 365 dirección de correo electrónico que se usará como remitente** no seleccionado (`-EnableCustomNotificationSender $false`).
  - **Personalizar el** vínculo \> notificaciones Personalización de la pestaña **de pie de página** \> de **confirmación**: **Mostrar el logotipo de la empresa** no seleccionado (`-EnableOrganizationBranding $false`).
- **Personalice la experiencia de su organización al notificar posibles amenazas en la sección de cuarentena** :

  **Botón de activación del mensaje de informe de cuarentena**: **activado**![.](../../media/scc-toggle-on.png) (`-DisableQuarantineReportingOption $false`).

```powershell
$usersub = "reportedmessages@contoso.com"

New-ReportSubmissionPolicy -ReportJunkToCustomizedAddress $true -ReportJunkAddresses $usersub -ReportNotJunkToCustomizedAddress $true -ReportNotJunkAddresses $usersub -ReportPhishToCustomizedAddress $true -ReportPhishAddresses $usersub -DisableUserSubmissionOptions $false -EnableCustomizedMsg $false -OnlyShowPhishingDisclaimer $true -EnableCustomNotificationSender $false -EnableOrganizationBranding $false -DisableQuarantineReportingOption $false

New-ReportSubmissionRule -Name DefaultReportSubmissionRule -ReportSubmissionPolicy DefaultReportSubmissionPolicy -SentTo $usersub
```

#### <a name="use-powershell-for-the-microsoft-integrated-reporting-experience-with-report-to-the-user-submissions-mailbox-only"></a>Uso de PowerShell para la experiencia de informes integrada de Microsoft con informes solo para el buzón de correo de envíos de usuarios

En este ejemplo se crea la directiva de envío de informes y la regla de envío de informes con la siguiente configuración:

- La experiencia de creación de informes integrada de Microsoft está activada: **botón de mensaje de informe de Microsoft Outlook** alternar: **Activado** ![activar.](../../media/scc-toggle-on.png) En el cmdlet **New-ReportSubmissionPolicy** : `-EnableReportToMicrosoft $false`. El valor predeterminado del parámetro _EnableThirdPartyAddress_ es `$false`, por lo que no es necesario usarlo.

- Enviar mensajes notificados solo al buzón de correo de envíos de usuario: **Envíe los mensajes notificados al** \> **buzón Mis organizaciones**:

  - **New-ReportSubmissionPolicy**: `-ReportJunkToCustomizedAddress $true -ReportJunkAddresses <emailaddress> -ReportNotJunkToCustomizedAddress $true -ReportNotJunkAddresses <emailaddress> -ReportPhishToCustomizedAddress $true -ReportPhishAddresses <emailaddress>`.
  - **Set-ReportSubmissionRule**: `SentTo <emailaddress>`.

  En este ejemplo, la dirección de correo electrónico del buzón de correo de envíos de usuario se userreportedmessages@fabrikam.com en Exchange Online (no se puede especificar una dirección de correo electrónico externa).

  > [!NOTE]
  > Debe usar el mismo valor de dirección de correo electrónico en todos los parámetros que identifican el buzón de correo de envíos de usuario.

Como en el ejemplo anterior, se requieren los mismos parámetros restantes para crear la directiva de envío de informes. Como en el ejemplo anterior, también se usan los valores predeterminados de esos parámetros:

```powershell
$usersub = "userreportedmessages@fabrikam.com"

New-ReportSubmissionPolicy -EnableReportToMicrosoft $false -ReportJunkToCustomizedAddress $true -ReportJunkAddresses $usersub -ReportNotJunkToCustomizedAddress $true -ReportNotJunkAddresses $usersub -ReportPhishToCustomizedAddress $true -ReportPhishAddresses $usersub -DisableUserSubmissionOptions $false -EnableCustomizedMsg $false -OnlyShowPhishingDisclaimer $true -EnableCustomNotificationSender $false -EnableOrganizationBranding $false -DisableQuarantineReportingOption $false

New-ReportSubmissionRule -Name DefaultReportSubmissionRule -ReportSubmissionPolicy DefaultReportSubmissionPolicy -SentTo $usersub
```

#### <a name="use-powershell-for-third-party-reporting-tools"></a>Uso de PowerShell para herramientas de informes de terceros

En este ejemplo se crea la directiva de envío de informes y la regla de envío de informes con la siguiente configuración:

- La experiencia de informes integrada de Microsoft está desactivada: **botón mensaje de informe de Microsoft Outlook** alternar: **Desactivar** ![desactivar.](../../media/scc-toggle-off.png) En el cmdlet **New-ReportSubmissionPolicy** : `-EnableReportToMicrosoft $false -EnableThirdPartyAddress $true`.

- Use los parámetros siguientes para especificar la dirección de correo electrónico del buzón de correo de envíos de usuario:

  - **New-ReportSubmissionPolicy**: `-ThirdPartyReportAddresses <emailaddress>`
  - **Set-ReportSubmissionRule**: `SentTo <emailaddress>`.

  En este ejemplo, la dirección de correo electrónico del buzón de correo de envíos de usuario se thirdpartyreporting@wingtiptoys.com en Exchange Online (no se puede especificar una dirección de correo electrónico externa).

  > [!NOTE]
  > Debe usar el mismo valor de dirección de correo electrónico en todos los parámetros que identifican el buzón de correo de envíos de usuario.

Los parámetros restantes son necesarios para crear la directiva de envío de informes correctamente. En este ejemplo, se usan los valores predeterminados. No hay otras opciones disponibles en la directiva de envío de informes al desactivar la experiencia de informes integrada de Microsoft:

- **Personalice la experiencia de su organización al notificar posibles amenazas en la sección de cuarentena** :

  **Botón de activación del mensaje de informe de cuarentena**: **activado**![.](../../media/scc-toggle-on.png) (`-DisableQuarantineReportingOption $false`).

```powershell
$usersub = "thirdpartyreporting@wingtiptoys.com"

New-ReportSubmissionPolicy -EnableReportToMicrosoft $false -EnableThirdPartyAddress $true -ThirdPartyReportAddresses $usersub -DisableQuarantineReportingOption $false

New-ReportSubmissionRule -Name DefaultReportSubmissionRule -ReportSubmissionPolicy DefaultReportSubmissionPolicy -SentTo $usersub
```

### <a name="use-powershell-to-modify-the-report-submission-policy-and-the-report-submission-rule"></a>Uso de PowerShell para modificar la directiva de envío de informes y la regla de envío de informes

La misma configuración está disponible al modificar la directiva de envío de informes en PowerShell que cuando creó la directiva como se describe en [la sección anterior](#use-powershell-to-create-the-report-submission-policy-and-the-report-submission-rule). La principal diferencia es que los parámetros adicionales necesarios para crear la directiva (por ejemplo, _DisableQuarantineReportingOption_) no son necesarios durante mucho tiempo. Sin embargo, es posible que tenga que deshacer o anular algunas opciones importantes que configuró anteriormente o que no configuró. Además, es posible que tenga que crear o eliminar la regla de envío de informes para permitir o impedir la generación de informes a un buzón de correo de envíos de usuario.

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-ReportSubmissionPolicy](/powershell/module/exchange/set-reportsubmissionpolicy).

En los ejemplos siguientes se muestra cómo cambiar la experiencia de informes de usuario sin preocuparse por la configuración o los valores existentes:

- Cambie al **informe de la experiencia \> de informes integrada de Microsoft solo a Microsoft**:

  ```powershell
   Set-ReportSubmissionPolicy -Identity DefaultReportSubmissionPolicy -EnableReportToMicrosoft $true -EnableThirdPartyAddress $false -ThirdPartyReportAddresses $null -ReportJunkToCustomizedAddress $false -ReportJunkAddresses $null -ReportNotJunkToCustomizedAddress $false -ReportNotJunkAddresses $null -ReportPhishToCustomizedAddress $false -ReportPhishAddresses $null

  Get-ReportSubmissionRule | Remove-ReportSubmissionRule
  ```

- Cambie al **informe de experiencia \> de informes integrado de Microsoft a Microsoft y al buzón de correo de envíos de usuarios** (por ejemplo, reportedmessages@contoso.com):

  ```powershell
  $usersub = "reportedmessages@contoso.com"

  Set-ReportSubmissionPolicy -Identity DefaultReportSubmissionPolicy -EnableReportToMicrosoft $true -EnableThirdPartyAddress $false -ThirdPartyReportAddresses $null -ReportJunkToCustomizedAddress $true -ReportJunkAddresses $usersub -ReportNotJunkToCustomizedAddress $true -ReportNotJunkAddresses $usersub -ReportPhishToCustomizedAddress $true -ReportPhishAddresses $usersub
  ```

  El siguiente comando solo es necesario si aún no tiene la regla de envío de informes:

  ```powershell
  New-ReportSubmissionRule -Name DefaultReportSubmissionRule -ReportSubmissionPolicy DefaultReportSubmissionPolicy -SentTo $usersub
  ```

- Cambie al **informe de experiencia \> de informes integrado de Microsoft al buzón de correo de envíos de usuarios solo** (por ejemplo, userreportedmessages@fabrikam.com):

  ```powershell
  $usersub = "userreportedmessages@fabrikam.com"

  Set-ReportSubmissionPolicy -Identity DefaultReportSubmissionPolicy -EnableReportToMicrosoft $false -EnableThirdPartyAddress $false -ThirdPartyReportAddresses $null -ReportJunkToCustomizedAddress $true -ReportJunkAddresses $usersub -ReportNotJunkToCustomizedAddress $true -ReportNotJunkAddresses $usersub -ReportPhishToCustomizedAddress $true -ReportPhishAddresses $usersub
  ```

  El siguiente comando solo es necesario si aún no tiene la regla de envío de informes:

  ```powershell
  New-ReportSubmissionRule -Name DefaultReportSubmissionRule -ReportSubmissionPolicy DefaultReportSubmissionPolicy -SentTo $usersub
  ```

- Cambie a **Herramientas de informes de terceros** (por ejemplo, thirdpartyreporting@wingtiptoys.com):

  ```powershell
  $usersub = "thirdpartyreporting@wingtiptoys.com"

  Set-ReportSubmissionPolicy -Identity DefaultReportSubmissionPolicy -EnableReportToMicrosoft $false -EnableThirdPartyAddress $true -ThirdPartyReportAddresses $usersub -ReportJunkToCustomizedAddress $false -ReportJunkAddresses $null -ReportNotJunkToCustomizedAddress $false -ReportNotJunkAddresses $null -ReportPhishToCustomizedAddress $false -ReportPhishAddresses $null
  ```

  El siguiente comando solo es necesario si aún no tiene la regla de envío de informes:

  ```powershell
  New-ReportSubmissionRule -Name DefaultReportSubmissionRule -ReportSubmissionPolicy DefaultReportSubmissionPolicy -SentTo $usersub
  ```

La única configuración significativa que puede modificar en la regla de envío de informes es la dirección de correo electrónico del buzón de correo de envíos de usuario (el valor del parámetro _SentTo_ ). Por ejemplo:

```powershell
Get-ReportSubmissionRule | Set-ReportSubmissionRule -SentTo newemailaddress@contoso.com
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-ReportSubmissionRule](/powershell/module/exchange/set-reportsubmissionrule).

Para deshabilitar temporalmente el envío de mensajes de correo electrónico al buzón de correo de envíos de usuarios (experiencia de informes integrada de Microsoft o herramientas de terceros) sin anular la regla de envío de informes, use [Disable-ReportSubmissionRule](/powershell/module/exchange/disable-reportsubmissionrule). Por ejemplo:

```powershell
Get-ReportSubmissionRule | Disable-ReportSubmissionRule -Confirm:$false
```

Para volver a habilitar la regla de envío de informes, use [Enable-ReportSubmissionRule](/powershell/module/exchange/enable-reportsubmissionrule). Por ejemplo:

```powershell
Get-ReportSubmissionRule | Disable-ReportSubmissionRule -Confirm:$false
```

### <a name="use-powershell-to-remove-the-report-submission-policy-and-the-report-submission-rule"></a>Uso de PowerShell para quitar la directiva de envío de informes y la regla de envío de informes

Para empezar de nuevo con la configuración predeterminada de la directiva de envío de informes, puede eliminarla y volver a crearla. La eliminación de la directiva de envío de informes no elimina la regla de envío de informes y viceversa.

Para quitar la directiva de envío de informes, ejecute el siguiente comando en Exchange Online PowerShell:

```powershell
Remove-ReportSubmissionPolicy -Identity DefaultReportSubmissionPolicy
```

Para quitar la regla de envío de informes, ejecute el siguiente comando:

```powershell
Get-ReportSubmissionRule | Remove-ReportSubmissionRule
```

Para quitar la directiva de envío de informes y la regla de envío de informes en el mismo comando sin avisos, ejecute el siguiente comando:

```powershell
Remove-ReportSubmissionPolicy -Identity DefaultReportSubmissionPolicy; Get-ReportSubmissionRule | Remove-ReportSubmissionRule -Confirm:$false
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Remove-ReportSubmissionPolicy](/powershell/module/exchange/remove-reportsubmissionpolicy) y [Remove-ReportSubmissionRule](/powershell/module/exchange/remove-reportsubmissionrule).
