---
title: Directivas de envíos de usuario
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden aprender a configurar un buzón para recopilar correo electrónico no deseado y suplantación de identidad que son notificados por los usuarios.
ms.openlocfilehash: c8dec927442cc83752f7c3497f295008fae85377
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446932"
---
# <a name="user-submissions-policies"></a>Directivas de envíos de usuario

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En Microsoft 365 organizaciones con buzones de correo de Exchange Online, puede especificar un buzón para recibir mensajes que los usuarios notifican como malintencionados o no malintencionados. Cuando los usuarios envían mensajes con las distintas opciones de informes, puede usar este buzón de correo para interceptar mensajes (enviar solo al buzón personalizado) o recibir copias de los mensajes (enviar al buzón de correo personalizado y Microsoft). Esta característica funciona con las siguientes opciones de informe de mensajes:

- [El complemento de mensajes de informe](enable-the-report-message-add-in.md)

- [Informes integrados en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (anteriormente conocido como Outlook Web App)

- [Informes integrados en Outlook para iOS y Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Si se ha [deshabilitado la generación de informes en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), la habilitación de los envíos de usuario aquí invalidará esa configuración y permitirá a los usuarios volver a notificar los mensajes en Outlook en la Web.

También puede configurar herramientas de informes de mensajes de terceros para reenviar mensajes al buzón de correo que especifique.

La entrega de mensajes de usuario que se han informado a un buzón de correo personalizado, en lugar de hacerlo directamente a Microsoft, permite a los administradores informar de forma selectiva y selectiva a Microsoft mediante el [envío de administración](admin-submission.md).

## <a name="custom-mailbox-prerequisites"></a>Requisitos previos de buzón personalizados

Use los siguientes artículos para configurar los requisitos previos necesarios para que los mensajes que el usuario haya notificado vayan a su buzón personalizado:

- Omitir el filtrado de correo no deseado en el buzón personalizado mediante la creación de una regla de flujo de correo de Exchange para establecer el nivel de confianza contra correo no deseado. Consulte [usar el EAC para crear una regla de flujo de correo que establezca el SCL de un mensaje](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) para establecer el SCL en **-1**.

- Desactive el examen de datos adjuntos para malware en el buzón personalizado. Use [configurar directivas de datos adjuntos seguros en Office 365 ATP](set-up-atp-safe-attachments-policies.md) para crear una directiva de datos adjuntos seguros con la opción **desactivada** para la **respuesta de malware desconocido de datos adjuntos seguros**.

- Desactive el análisis de URL en los mensajes del buzón personalizado. Use [configurar directivas de vínculos seguros en Office 365 ATP](set-up-atp-safe-links-policies.md) para crear una directiva de vínculos a prueba de errores con el valor **desactivar** para **Seleccione la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes**.

- Cree una directiva antimalware para desactivar la depuración automática de malware de cero horas. Consulte [usar el centro de seguridad & cumplimiento para crear directivas antimalware](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) para establecer la **depuración automática de cero horas de malware** en **desactivada**.

- Cree una directiva de filtro de correo no deseado para deshabilitar la depuración automática de cero horas (ZAP) para correo no deseado y suplantación de identidad en el buzón personalizado. Consulte [usar el centro de seguridad & cumplimiento para crear directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) y desactivar las **casillas de verificación** para el **correo no deseado** y **Zap de phish**.

- Deshabilite la regla de correo no deseado en el buzón personalizado. Use [configurar la configuración del correo electrónico no deseado en buzones de Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md) para deshabilitar la regla de correo no deseado. Una vez deshabilitado, EOP no puede mover mensajes a la carpeta de correo no deseado en función de la acción de veredicto " **mover mensaje a la carpeta correo no deseado** " o la colección de listas seguras del buzón.

Una vez que haya comprobado que el buzón cumple todos los requisitos previos aplicables, [use el centro de seguridad & cumplimiento para configurar el buzón de envíos de usuarios](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (en este artículo).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página **envíos de usuarios** , use <https://protection.office.com/userSubmissionsReportMessage> .

- Para modificar la configuración de los envíos de usuario, debe ser miembro de uno de los siguientes grupos de roles:

  - **Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).
  - **Administración** de la organización en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Usar el centro de seguridad & cumplimiento para configurar el buzón de envíos de usuarios

1. En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **envíos de usuarios**de la Directiva de administración de amenazas.

2. En la página **envíos de usuarios** que aparece, seleccione una de las siguientes opciones:

   a. **Habilitar la característica de mensaje de informe para Outlook (recomendado)**: Seleccione esta opción si usa el complemento de mensajes de informe o los informes integrados en Outlook en la web y, a continuación, configure las siguientes opciones:

      - **Personalizar el mensaje de confirmación del usuario final**: haga clic en este vínculo. En el control flotante **personalizar mensaje de confirmación** que aparece, configure las siguientes opciones:

      - **Antes de enviar**: en los cuadros de mensaje **título** y **confirmación** , escriba el texto descriptivo que verán los usuarios antes de que informen de un mensaje mediante el complemento de mensajes de informe. Puede usar la variable% Type% para incluir el tipo de envío (correo no deseado, correo deseado, phish, etc.).

        Como se indicó, si selecciona una opción que envía los mensajes notificados a Microsoft, también se agregará el siguiente texto a la notificación:

        > El correo electrónico se enviará tal cual a Microsoft para su análisis. Algunos mensajes de correo electrónico pueden contener información personal o confidencial.

      - **Después del envío**: haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) . En los cuadros de texto **título** y **confirmación** , escriba el texto descriptivo que los usuarios verán después de que informen de un mensaje mediante el complemento de mensajes de informe. Puede usar la variable% Type% para incluir el tipo de envío.

      Cuando haya terminado, haga clic en **Guardar**. Para borrar estos valores, haga clic en **restaurar** de nuevo en la página **envíos de usuarios** .

      - **Enviar los mensajes notificados a**: realice una de las siguientes selecciones:

        - **Microsoft (recomendado)**: no se usa el buzón de envíos de usuario (todos los mensajes que se han informado van a Microsoft).

        - **Microsoft y un buzón personalizado**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de Exchange Online existente. No se permiten los grupos de distribución. Los envíos de usuarios Irán a Microsoft para su análisis y al buzón de correo personalizado para que los analice el administrador o el equipo de operaciones de seguridad.

        - **Buzón personalizado**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de Exchange Online existente. No se permiten los grupos de distribución. Use esta opción si desea que el mensaje solo vaya a un administrador o al equipo de operaciones de seguridad para su análisis en primer lugar. Los mensajes no pasarán a Microsoft a menos que el administrador los reenvíe por sí mismos.

        > [!NOTE]
        > Las organizaciones gubernamentales de Estados Unidos (GCC, GCC-H y DoD) solo pueden configurar el **buzón personalizado**. Las otras dos opciones están deshabilitadas. 

      Cuando haya terminado, haga clic en **confirmar**.

      > [!CAUTION]
      > Si ha [deshabilitado la notificación de correo no deseado en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) con directivas de buzón de Outlook en la web, pero configura cualquiera de las opciones anteriores para notificar mensajes a Microsoft, los usuarios podrán informar de los mensajes a Microsoft en Outlook en la web mediante el complemento de mensajes de informe.

   - **Deshabilitar la característica de mensaje de informe para Outlook**: Seleccione esta opción si usa herramientas de informes de terceros en lugar del complemento de mensajes de informe o la creación de informes integrados en Outlook en la web y, a continuación, configure las siguientes opciones:

      Seleccione **usar este buzón personalizado para recibir envíos notificados por el usuario**. En el cuadro que aparece, escriba la dirección de correo electrónico de un buzón existente que ya esté en Office 365. Debe ser un buzón existente en Exchange online que pueda recibir correo electrónico.

      Cuando haya terminado, haga clic en **confirmar**.

## <a name="message-submission-format"></a>Formato de envío de mensajes

Los mensajes que se envían a los buzones personalizados deben seguir un formato de correo de envío específico. El asunto (título de sobre) del envío debe tener este formato:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

donde SafetyAPIAction es uno de los siguientes valores enteros:

- 1: correo no deseado
- 2: NotJunk
- 3: phish

En el siguiente ejemplo:

- El mensaje se está notificando como phish.
- El identificador de mensaje de red es 49871234-6dc6-43e8-ABCD-08d797f20abe.
- La IP del remitente es 167.220.232.101.
- La dirección de es test@contoso.com.
- La línea de asunto del mensaje es "test phish Submission"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

Los mensajes que no siguen este formato no se mostrarán correctamente en el portal de envíos.
