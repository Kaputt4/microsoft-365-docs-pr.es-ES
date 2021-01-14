---
title: Directiva de envíos de usuario
f1.keywords:
- NOCSH
ms.author: siosulli
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
description: Los administradores pueden aprender a configurar un buzón para recopilar correo no deseado y correo electrónico de suplantación de identidad que notifican los usuarios.
ms.openlocfilehash: 8f9da620643d46bf21a18eccc2047ad4361832cc
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865072"
---
# <a name="user-submissions-policy"></a>Directiva de envíos de usuario

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En las organizaciones de Microsoft 365 con buzones de Exchange Online, puede especificar un buzón para recibir mensajes que los usuarios informan como malintencionados o no malintencionados. Cuando los usuarios envían mensajes mediante las distintas opciones de informes, puede usar este buzón para interceptar mensajes (enviar solo al buzón personalizado) o recibir copias de mensajes (enviar al buzón personalizado y Microsoft). Esta característica funciona con las siguientes opciones de informes de mensajes:

- [El complemento Mensaje de informe](enable-the-report-message-add-in.md)

- [El complemento de suplantación de identidad de informes](enable-the-report-phish-add-in.md)

- [Informes integrados en Outlook en la Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (anteriormente conocido como Outlook Web App)

- [Informes integrados en Outlook para iOS y Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Si los informes se han deshabilitado en Outlook en la [Web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)habilitar los envíos de usuario aquí invalidará esa configuración y permitirá a los usuarios notificar mensajes en Outlook en la Web de nuevo.

También puede configurar herramientas de informes de mensajes de terceros para reenviar mensajes al buzón que especifique.

Entregar mensajes notificados por el usuario a un buzón personalizado en lugar de directamente a Microsoft permite a los administradores notificar mensajes de forma selectiva y manual a Microsoft mediante [el envío de administrador.](admin-submission.md)

## <a name="custom-mailbox-prerequisites"></a>Requisitos previos de buzón personalizado

Use los siguientes artículos para configurar los requisitos previos necesarios para que los mensajes notificados por el usuario vayan a su buzón personalizado:

- Omita el filtrado de correo no deseado en el buzón personalizado mediante la creación de una regla de flujo de correo de Exchange para establecer el nivel de confianza contra correo no deseado. Vea [Usar el EAC para crear una](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) regla de flujo de correo que establezca el SCL de un mensaje para establecer el SCL en **-1**.

- Desactivar el examen de datos adjuntos en busca de malware en el buzón personalizado. Use Configurar directivas de datos adjuntos seguros en Defender para Office  [365](set-up-atp-safe-attachments-policies.md) para crear una directiva de datos adjuntos seguros con la configuración desactivada para la respuesta de malware desconocido de datos **adjuntos seguros.**

- Desactive el examen de direcciones URL en los mensajes del buzón personalizado. Use Configurar directivas de vínculos seguros en Defender para [Office 365](set-up-atp-safe-links-policies.md) para crear una directiva de vínculos seguros con la configuración desactivada para Seleccionar la acción para direcciones URL potencialmente malintencionadas desconocidas en los **mensajes.** 

- Crear una directiva antimalware para desactivar la purga automática de malware de hora cero. Vea Usar el Centro de seguridad & cumplimiento para crear directivas [antimalware](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) para establecer malware purga automática **de** hora cero en **desactivado.**

- Cree una directiva de filtro de correo no deseado para deshabilitar la purga automática (ZAP) de cero horas para correo no deseado y suplantación de identidad en el buzón personalizado. Consulte [Usar el Centro de seguridad & cumplimiento para](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)  crear directivas contra correo no deseado y desactive las casillas Activar para **ZAP** de correo no deseado y **ZAP de suplantación de identidad**.

- Deshabilitar la regla de correo no deseado en el buzón personalizado. Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule. Una vez deshabilitado, EOP no puede mover mensajes a la carpeta  de correo no deseado en función de la acción de veredicto de filtrado de correo no deseado Mover mensaje a la carpeta De correo no deseado o la colección de listas seguras del buzón.

Después de comprobar que el buzón cumple todos los requisitos previos aplicables, use el Centro de seguridad [& y](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) cumplimiento para configurar el buzón de envío de usuario (en este artículo).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la **página Envíos de** usuario, use <https://protection.office.com/userSubmissionsReportMessage> .

- Para modificar la configuración de envíos de usuarios, debes ser miembro de uno de los siguientes grupos de roles:

  - **Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).
  - **Administración de la** organización [en Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Usar el Centro de & cumplimiento para configurar el buzón de envío de usuario

1. En el Centro de & cumplimiento, vaya a Envíos **de** usuario de \> **directiva** de \> **administración de amenazas.**

2. En la **página Envíos de** usuario que aparece, selecciona una de las siguientes opciones:

   1. Habilitar la característica de mensaje de informe para **Outlook (recomendado):** seleccione esta opción si usa el complemento Mensaje de informe, el complemento de suplantación de identidad de informes o los informes integrados en Outlook en la Web y, a continuación, configure las siguientes opciones:

      - **Personalice el mensaje de confirmación del usuario final:** haga clic en este vínculo. En el **menú desplegable Personalizar mensaje** de confirmación que aparece, configure las siguientes opciones:

      - **Antes del** envío:  en los cuadros de mensaje Título y Confirmación, escriba el texto descriptivo que verán los usuarios antes de informar de un mensaje mediante el complemento Mensaje de informe o el complemento Informar de suplantación de identidad.  Puedes usar la variable %type% para incluir el tipo de envío (correo no deseado, correo no deseado, phishing, etc.).

        Como se ha indicado, si selecciona una opción que envía los mensajes notificados a Microsoft, también se agrega el siguiente texto a la notificación:

        > El correo electrónico se enviará tal como está a Microsoft para su análisis. Algunos correos electrónicos pueden contener información personal o confidencial.

      - **Después del envío:** haga clic ![ en el icono Expandir ](../../media/scc-expand-icon.png) . En **los**  cuadros de mensaje Título y Confirmación, escriba el texto descriptivo que verán los usuarios después de informar de un mensaje mediante el complemento Mensaje de informe o el complemento Informar de suplantación de identidad. Puedes usar la variable %type% para incluir el tipo de envío.

      Cuando haya terminado, haga clic en **Guardar**. Para borrar estos valores, haz clic **en Restaurar** de nuevo en la **página Envíos de** usuario.

      - **Envíe los mensajes notificados a:** Realice una de las siguientes selecciones:

        - **Microsoft (recomendado): el** buzón de envío del usuario no se usa (todos los mensajes notificados van a Microsoft).

        - **Microsoft y un buzón personalizado:** en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de Exchange Online existente. No se permiten los grupos de distribución. Los envíos de usuarios irán a Microsoft para su análisis y al buzón personalizado para que el administrador o el equipo de operaciones de seguridad lo analicen.

        - **Buzón personalizado:** en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón existente de Exchange Online. No se permiten los grupos de distribución. Use esta opción si desea que el mensaje solo vaya primero a un administrador o al equipo de operaciones de seguridad para su análisis. Los mensajes no irán a Microsoft a menos que el administrador lo reenvía ellos mismos.

        > [!NOTE]
        > Las organizaciones gubernamentales de Estados Unidos (GCC, GCC-H y DoD) solo pueden configurar el **buzón personalizado.** Las otras dos opciones están deshabilitadas.

      Cuando haya terminado, haga clic en **Confirmar**.

      > [!CAUTION]
      > Si ha deshabilitado los informes de correo no deseado en Outlook en la [web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) mediante directivas de buzón de Outlook en la web, pero configura cualquiera de las opciones anteriores para notificar mensajes a Microsoft, los usuarios podrán informar de los mensajes a Microsoft en Outlook en la Web mediante el complemento Mensaje de informe o el complemento Detección de suplantación de identidad de informes.

   - Deshabilitar la característica Mensaje de informe para **Outlook:** seleccione esta opción si usa herramientas de informes de terceros en lugar del complemento Mensaje de informe, el complemento de suplantación de identidad de informes o los informes integrados en Outlook en la Web y, a continuación, configure las siguientes opciones:

      Seleccione **Usar este buzón personalizado para recibir envíos notificados por el usuario.** En el cuadro que aparece, escriba la dirección de correo electrónico de un buzón existente que ya está en Office 365. Debe ser un buzón existente en Exchange Online que pueda recibir correo electrónico.

      Cuando haya terminado, haga clic en **Confirmar**.

## <a name="message-submission-format"></a>Formato de envío de mensajes

Los mensajes enviados a buzones personalizados deben seguir un formato de correo de envío específico. El asunto (título del sobre) del envío debe tener este formato:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

donde SafetyAPIAction es uno de los siguientes valores enteros:

- 1: Correo no deseado
- 2: Correo no deseado
- 3: Suplantación de identidad (phishing)

En el siguiente ejemplo:

- El mensaje se está notificando como suplantación de identidad.
- El id. de mensaje de red es 49871234-6dc6-43e8-abcd-08d797f20abe.
- La dirección IP del remitente es 167.220.232.101.
- La dirección De es test@contoso.com.
- La línea de asunto del mensaje es "probar el envío de suplantación de identidad"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

Los mensajes que no sigan este formato no se mostrarán correctamente en el portal de envíos.
