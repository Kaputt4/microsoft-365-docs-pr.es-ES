---
title: Especificar un buzón para envíos de usuarios de mensajes de correo no deseado y suplantación de identidad
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a configurar un buzón para recopilar correo electrónico no deseado y suplantación de identidad que son notificados por los usuarios.
ms.openlocfilehash: 6aa343b337139c4d81f35f78a227634d3b6a8781
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262528"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>Especificar un buzón para envíos de usuarios de correo no deseado y mensajes de suplantación de identidad en Exchange Online

En Microsoft 365 organizaciones con buzones de correo de Exchange Online, puede especificar un buzón para recibir mensajes que los usuarios notifican como malintencionados o no malintencionados. Cuando los usuarios envían mensajes con las distintas opciones de informes, puede usar este buzón de correo para interceptar mensajes (enviar solo al buzón personalizado) o recibir copias de los mensajes (enviar al buzón de correo personalizado y Microsoft). Esta característica funciona con las siguientes opciones de informe de mensajes:

- [El complemento de mensajes de informe](enable-the-report-message-add-in.md)

- [Informes integrados en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (anteriormente conocido como Outlook Web App)

  > [!NOTE]
  > Si se ha [deshabilitado la generación de informes en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), la habilitación de los envíos de usuario aquí invalidará esa configuración y permitirá a los usuarios volver a notificar los mensajes en Outlook en la Web.

También puede configurar herramientas de informes de mensajes de terceros para reenviar mensajes al buzón de correo que especifique.

La entrega de mensajes de usuario que se han informado a un buzón de correo personalizado, en lugar de hacerlo directamente a Microsoft, permite a los administradores informar de forma selectiva y selectiva a Microsoft mediante el [envío de administración](admin-submission.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página **envíos de usuarios** , use <https://protection.office.com/userSubmissionsReportMessage> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos. Para configurar el buzón de correo para envíos de usuarios, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** . Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

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

        - **Buzón personalizado**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de Exchange Online existente. No se permiten los grupos de distribución. Use esta opción si desea que el mensaje solo vaya al administrador o al equipo de operaciones de seguridad para su análisis en primer lugar. Los mensajes no pasarán a Microsoft a menos que el administrador lo reenvíe.

        Cuando haya terminado, haga clic en **confirmar**.

        ![Enviar mensajes notificados a Microsoft y a un buzón personalizado](../../media/user-submission-enable-outlook-report-message.png)

     > [!CAUTION]
     > Si ha [deshabilitado la notificación de correo no deseado en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) con directivas de buzón de Outlook en la web, pero configura cualquiera de las opciones anteriores para notificar mensajes a Microsoft, los usuarios podrán informar de los mensajes a Microsoft en Outlook en la web mediante el complemento de mensajes de informe.

   - **Deshabilitar la característica de mensaje de informe para Outlook**: Seleccione esta opción si usa herramientas de informes de terceros en lugar del complemento de mensajes de informe o la creación de informes integrados en Outlook en la web y, a continuación, configure las siguientes opciones:

      Seleccione **usar este buzón personalizado para recibir envíos notificados por el usuario**. En el cuadro que aparece, escriba la dirección de correo electrónico de un buzón existente que ya esté en Office 365. Debe ser un buzón existente en Exchange online que pueda recibir correo electrónico.

      Cuando haya terminado, haga clic en **confirmar**.

      ![Enviar mensajes de informes a un buzón personalizado con herramientas de terceros](../../media/user-submission-disable-outlook-report-message.png)
     
## <a name="message-submission-format"></a>Formato de envío de mensajes

Los mensajes que se envían a los buzones personalizados deben seguir un formato de correo de envío específico. El asunto (título de sobre) del envío debe tener este formato:

`{(int)safetyApiAction}|{networkId}|{senderIp}|{fromAddress}|({subject.Substring(0, Math.Min(subjectLen, subject.Length))})`

fueron SafetyApiAction es:

- Correo no deseado = 1
- NotJunk = 2
- Phish = 3

En el siguiente ejemplo:

- El mensaje se está notificando como phish.
- El identificador de mensaje de red es 49871234-6dc6-43e8-ABCD-08d797f20abe.
- La IP del remitente es 167.220.232.101.
- La dirección de es test@contoso.com.
- El asunto del correo electrónico del mensaje es "probar el envío de phish"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

Los mensajes que no siguen este formato no se mostrarán correctamente en el portal de envíos.
