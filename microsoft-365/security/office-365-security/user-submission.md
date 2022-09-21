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
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: e11b30d14a7aff37c6c33dd5e8ce36b0e922097b
ms.sourcegitcommit: 95ac076310ab9006ed92c69938f7ae771cd10826
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67851070"
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

Antes de empezar, debe configurar Exchange Online Protection y Defender para Office 365 para que los mensajes notificados por el usuario se entreguen al buzón de correo de envíos de usuario sin filtrarse como se describe en los pasos siguientes:

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

  - **Microsoft**: los informes de usuario van directamente a Microsoft para su análisis. Solo los metadatos como el remitente, el destinatario y los detalles del mensaje de los informes de usuario se proporcionan al administrador de inquilinos a través del portal de Microsoft 365 Defender.

  - **Buzón de Microsoft y mi organización**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de correo Exchange Online existente que se usará como buzón de correo de envíos del usuario. No se permiten grupos de distribución. Los envíos de usuarios van a Microsoft para su análisis y al buzón de correo de envíos de usuario para que un equipo de operaciones de seguridad o administrador los analice.

  - **Buzón de mi organización**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de correo Exchange Online existente. No se permiten grupos de distribución. Los envíos de usuarios solo van al buzón de correo de envíos de usuario para que un administrador o el equipo de operaciones de seguridad los analice. Los mensajes no van a Microsoft para su análisis a menos que un administrador envíe manualmente los mensajes.

  > [!IMPORTANT]
  > En las organizaciones gubernamentales de Ee. UU. (GCC, GCC High y DoD), la única selección disponible en la sección **Enviar los mensajes notificados a es el** **buzón de mi organización**. Las otras dos opciones están atenuadas.
  >
  > Si ha usado [Outlook en la Web directivas de buzón de correo](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/configure-outlook-web-app-mailbox-policy-properties) para deshabilitar los informes de correo no deseado en Outlook en la Web, pero selecciona **Microsoft** o **Microsoft y el buzón de mi organización**, los usuarios podrán notificar mensajes a Microsoft en Outlook en la Web mediante el complemento Mensaje de informe o el complemento Suplantación de identidad de informe.
  >
  > Si selecciona **el buzón de mi organización**, los mensajes notificados aparecerán en la pestaña **Mensajes notificados** por el usuario de la página **Envíos** de <https://security.microsoft.com/reportsubmission>. Pero el valor **Result** de estos mensajes siempre estará vacío, ya que los mensajes no se examinaron de nuevo.
  >
  > Si usa [Entrenamiento de simulación de ataque](attack-simulation-training-get-started.md) o un producto de terceros para realizar simulaciones de suplantación de identidad (phishing), debe configurar el buzón de correo de envíos de usuario como buzón de SecOps, tal como se describió anteriormente en la sección [Requisitos de configuración para el buzón de correo de envíos de usuario](#configuration-requirements-for-the-user-submissions-mailbox) anteriormente en este artículo. Si no lo hace, un usuario que informe de un mensaje podría desencadenar una asignación de entrenamiento en el producto de simulación de suplantación de identidad (phishing).

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
  
  - **Personalizar notificaciones**: haga clic en este vínculo para personalizar la notificación por correo electrónico que se envía después de que un administrador revise y marque un mensaje notificado.

    En el control flotante **Personalizar mensaje de confirmación** que aparece, configure los siguientes valores:

    - **Pestañas de phishing**, **correo no deseado** y **No se encontraron amenazas** : en el **texto del resultado de la revisión** en algunas, ninguna o todas las pestañas, escriba el texto personalizado que se va a usar.
    - **Pestaña Pie de página** : están disponibles las siguientes opciones:
      - **Texto del pie de página**: escriba el texto del pie de página del mensaje personalizado que se va a usar.
      - **Mostrar logotipo de la empresa**: antes de seleccionar esta opción, debe seguir las instrucciones de [Personalización del tema de Microsoft 365 para que su organización](../../admin/setup/customize-your-organization-theme.md) cargue el logotipo personalizado.

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
- El mensaje notificado debe contener los siguientes encabezados necesarios:
  - 1. X-Microsoft-Antispam-Message-Info
  - 2. Id. de mensaje
  - 3. X-Ms-Exchange-Organization-Network-Message-Id
  - 4. X-Ms-Exchange-Crosstenant-Id

> [!NOTE]
> TenantId en `X-Ms-Exchange-Crosstenant-Id` debe ser el mismo que el inquilino.
>
> `X-Microsoft-Antispam-Message-Info` debe ser un xmi válido.

- La línea asunto (título de sobre) de los mensajes enviados al buzón de envíos del usuario debe comenzar con uno de los siguientes valores de prefijo:
  - `1|` o `Junk:`.
  - `2|` o `Not junk:`.
  - `3|` o `Phishing:`.

  Por ejemplo:

  - `3|This text in the Subject line is ignored by the system`
  - `Not Junk:This text in the Subject line is also ignored by the system`

  Los mensajes que no siguen este formato no se mostrarán correctamente en la página **Envíos** de <https://security.microsoft.com/reportsubmission>.
