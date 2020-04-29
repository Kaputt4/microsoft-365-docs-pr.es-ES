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
ms.openlocfilehash: a3a175c3815c6750086526ec92d097fb7cbcefa3
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2020
ms.locfileid: "43922668"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-office-365"></a>Especificar un buzón para envíos de usuarios de correo no deseado y mensajes de suplantación de identidad en Office 365

En Office 365 organizaciones con buzones de correo de Exchange Online, puede especificar un buzón para recibir mensajes que los usuarios notifican como malintencionados o no malintencionados. Cuando los usuarios envían mensajes con las distintas opciones de informes, puede usar este buzón de correo para interceptar mensajes (enviar solo al buzón personalizado) o recibir copias de los mensajes (enviar al buzón de correo personalizado y Microsoft). Esta característica funciona con las siguientes opciones de informe de mensajes:

- [El complemento de mensajes de informe](enable-the-report-message-add-in.md)

- [Informes integrados en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (anteriormente conocido como Outlook Web App)

También puede configurar herramientas de informes de mensajes de terceros para reenviar mensajes al buzón de correo que especifique.

La entrega de mensajes de usuario que se han informado a un buzón de correo personalizado, en lugar de hacerlo directamente a Microsoft, permite a los administradores informar de forma selectiva y selectiva a Microsoft mediante el [envío de administración](admin-submission.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página **envíos de usuarios** , use <https://protection.office.com/userSubmissionsReportMessage>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Para conectarse a Exchange Online Protection PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos. Para configurar el buzón de correo para envíos de usuarios, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** . Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md).

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Usar el centro de seguridad & cumplimiento para configurar el buzón de envíos de usuarios

1. En el centro de seguridad & cumplimiento, vaya a **envíos de usuarios**de la **Directiva** \> de **Administración** \> de amenazas.

2. En la página **envíos de usuarios** que aparece, seleccione una de las siguientes opciones:

   - **Habilitar la característica de mensaje de informe para Outlook (recomendado)**: Seleccione esta opción si usa el complemento de mensajes de informe o los informes integrados en Outlook en la web y, a continuación, configure las siguientes opciones:

     - **Personalizar el mensaje de confirmación del usuario final**: haga clic en este vínculo. En el control flotante **personalizar mensaje de confirmación** que aparece, configure las siguientes opciones:

       - **Antes de enviar**: en los cuadros de mensaje **título** y **confirmación** , escriba el texto descriptivo que verán los usuarios antes de que informen de un mensaje mediante el complemento de mensajes de informe. Puede usar la variable% Type% para incluir el tipo de envío (correo no deseado, correo deseado, phish, etc.).

         Como se indicó, el texto siguiente también se agrega a la notificación:

         > El correo electrónico se enviará tal cual a Microsoft para su análisis. Algunos mensajes de correo electrónico pueden contener información personal o confidencial.

       - **Después del envío**: ![haga clic](../../media/scc-expand-icon.png)en expandir icono. En los cuadros de texto **título** y **confirmación** , escriba el texto descriptivo que los usuarios verán después de que informen de un mensaje mediante el complemento de mensajes de informe. Puede usar la variable% Type% para incluir el tipo de envío.

      Cuando haya terminado, haga clic en **Guardar**. Para borrar estos valores, haga clic en **restaurar** de nuevo en la página **envíos de usuarios** .

   - **Enviar los mensajes notificados a**: realice una de las siguientes selecciones:

     - **Microsoft (recomendado)**: no se usa el buzón de envíos de usuario (todos los mensajes que se han informado van a Microsoft).

     - **Microsoft y un buzón personalizado**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de Exchange Online existente.

     - **Buzón personalizado**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de Exchange Online existente.

     Cuando haya terminado, haga clic en **confirmar**.

     ![Enviar mensajes notificados a Microsoft y a un buzón personalizado](../../media/user-submission-enable-outlook-report-message.png)

   - **Deshabilitar la característica de mensaje de informe para Outlook**: Seleccione esta opción si usa herramientas de informes de terceros en lugar del complemento de mensajes de informe o la creación de informes integrados en Outlook en la web y, a continuación, configure las siguientes opciones:

     Seleccione **usar este buzón personalizado para recibir envíos notificados por el usuario**. En el cuadro que aparece, escriba la dirección de correo electrónico de un buzón existente o la dirección de correo electrónico del buzón que desea crear.

     Cuando haya terminado, haga clic en **confirmar**.

     ![Enviar mensajes de informes a un buzón personalizado con herramientas de terceros](../../media/user-submission-disable-outlook-report-message.png)
