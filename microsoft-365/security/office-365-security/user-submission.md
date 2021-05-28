---
title: Directiva de envíos de usuarios
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden aprender a configurar un buzón para recopilar correo no deseado y correo electrónico de suplantación de identidad notificados por los usuarios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 719bd2b86cae1c6a951cb34408ecb9d2b8da699a
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2021
ms.locfileid: "52696591"
---
# <a name="user-submissions-policy"></a>Directiva de envíos de usuarios

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En Microsoft 365 con Exchange Online buzones de correo, puede especificar un buzón para recibir mensajes que los usuarios reportan como malintencionados o no malintencionados. Cuando los usuarios envían mensajes con las distintas opciones de informes, puede usar este buzón para interceptar mensajes (solo enviar al buzón personalizado) o recibir copias de mensajes (enviar al buzón personalizado y Microsoft). Esta característica funciona con las siguientes opciones de informes de mensajes:

- [El complemento Mensaje de informe](enable-the-report-message-add-in.md)

- [El complemento Detección de suplantación de identidad de informes](enable-the-report-phish-add-in.md)

- [Herramientas de informes de terceros](#third-party-reporting-tools)

La entrega de mensajes notificados por el usuario a un buzón personalizado en lugar de directamente a Microsoft permite a los administradores notificar mensajes de forma selectiva y manual a Microsoft mediante [el envío de administrador.](admin-submission.md)

  > [!NOTE]
  > Si los informes se han deshabilitado en Outlook en la [web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)al habilitar los envíos de usuario aquí se invalidará esa configuración y se permitirá a los usuarios notificar mensajes en Outlook en la web de nuevo.

## <a name="custom-mailbox-prerequisites"></a>Requisitos previos de buzón personalizado

Use los artículos siguientes para configurar los requisitos previos necesarios para que los mensajes notificados por el usuario vayan al buzón personalizado:

- Omitir el filtrado de correo no deseado en el buzón personalizado mediante la creación de una regla de flujo de correo de Exchange para establecer el nivel de confianza de correo no deseado. Vea [Usar el EAC para crear una](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) regla de flujo de correo que establezca el SCL de un mensaje para establecer el SCL en Omitir filtrado de correo no **deseado.**

- Desactiva el examen de datos adjuntos en busca de malware en el buzón personalizado. Use [Configurar directivas](set-up-safe-attachments-policies.md) Caja fuerte datos adjuntos en Defender para Office 365 para crear una directiva de datos adjuntos de Caja fuerte con la opción **Desactivado** para la respuesta de malware desconocido de Caja fuerte **datos adjuntos.**

- Desactivar el examen de direcciones URL en los mensajes del buzón personalizado. Use Configurar directivas Caja fuerte [vínculos](set-up-safe-links-policies.md) en Defender para Office 365 para crear una directiva de vínculos de Caja fuerte con la opción **Desactivado** para **Seleccionar** la acción para direcciones URL potencialmente malintencionadas desconocidas en mensajes .

- Crear una directiva antimalware para desactivar Malware Zero-hour Auto Purge. Consulte [Use the Security & Compliance Center to create anti-malware policies](configure-your-spam-filter-policies.md#use-the-security-center-to-create-anti-spam-policies) to set Malware **Zero-hour Auto Purge** to **Off**.

- Cree una directiva de filtro de correo no deseado para deshabilitar la purga automática de hora cero (ZAP) para correo no deseado y suplantación de identidad (phishing) en el buzón personalizado. Vea [Usar el Centro de seguridad & cumplimiento para](configure-your-spam-filter-policies.md#use-the-security-center-to-create-anti-spam-policies)  crear directivas contra correo no deseado y desactive las casillas Activar para **ZAP** de correo no deseado y ZAP **de suplantación de identidad**.

- Deshabilite la regla de correo no deseado en el buzón personalizado. Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule. Una vez deshabilitado, EOP no puede mover mensajes a la carpeta  correo no deseado en función de la acción de veredicto de filtrado de correo no deseado Mover el mensaje a la carpeta correo no deseado o la colección de listas seguras en el buzón.

Después de comprobar que el buzón cumple todos los requisitos previos aplicables, use el Centro de seguridad & cumplimiento para configurar el buzón de [envíos](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) de usuario (en este artículo).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la **página Envíos de usuario,** use <https://protection.office.com/userSubmissionsReportMessage> .

- Para modificar la configuración de envíos de usuarios, debe ser miembro de uno de los siguientes grupos de roles:

  - **Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).
  - **Administración de** la [organización en Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

- Necesita tener acceso a Exchange Online PowerShell. Si la cuenta que está intentando usar no tiene acceso Exchange Online PowerShell, recibirá un error similar al siguiente al especificar el buzón de envío:

  > Especificar una dirección de correo electrónico en el dominio

  Para obtener más información acerca de cómo habilitar o deshabilitar el acceso a Exchange Online PowerShell, consulte los siguientes temas:

  - [Habilitar o deshabilitar el acceso a Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Reglas de acceso de cliente en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Usar el Centro de seguridad & cumplimiento para configurar el buzón de envíos de usuario

1. En el Centro de & cumplimiento, vaya a **Administración** de amenazas \>  \> **Envíos de usuario de directiva**.

2. En la **página Envíos de** usuario que aparece, seleccione una de las siguientes opciones:

      1. Habilitar la característica Mensaje de informe para **Outlook (recomendado):** seleccione esta opción si usa el complemento Mensaje de informe, el complemento Report Phishing o los informes integrados de Outlook en la web y, a continuación, configure las siguientes opciones:

    - **Personalizar el mensaje de confirmación del usuario final:** haga clic en este vínculo. En el **menú desplegable Personalizar mensaje** de confirmación que aparece, configure las siguientes opciones:

        - **Antes del** envío:  en los cuadros Título y Mensaje de confirmación, escriba el texto descriptivo que los usuarios ven antes de informar de un mensaje mediante el complemento Report Message o el complemento Report Phishing.  Puede usar la variable %type% para incluir el tipo de envío (correo no deseado, no deseado, phish, etc.).

          Como se ha indicado, si selecciona una opción que envía los mensajes notificados a Microsoft, también se agregará el siguiente texto a la notificación:

          > El correo electrónico se enviará tal como está a Microsoft para su análisis. Algunos correos electrónicos pueden contener información personal o confidencial.

        - **Después del envío:** haga clic ![ en Expandir icono ](../../media/scc-expand-icon.png) . En los  **cuadros Título** y Mensaje de confirmación, escriba el texto descriptivo que los usuarios ven después de informar de un mensaje mediante el complemento Report Message o el complemento Report Phishing. Puede usar la variable %type% para incluir el tipo de envío.

      Cuando haya terminado, haga clic en **Guardar**. Para borrar estos valores, haga clic **en Restaurar** de nuevo en la **página Envíos de** usuario.
    
    - **Personalizar las opciones de informes del** usuario final: haga clic en este vínculo. En el **control desplegable Personalizar opciones** de informes del usuario final que aparece, escriba el texto descriptivo de las opciones de informes de correo no deseado. 
    
      En **Opciones para mostrar cuándo se notifican los mensajes,** seleccione al menos una de las siguientes opciones:
        - **Pregúnteme antes de enviar un informe**
        - **Enviar informes automáticamente**
        - **Nunca enviar informes**
       
      Cuando haya terminado, haga clic en **Guardar**.

        - **Enviar los mensajes notificados a**: Realice una de las siguientes selecciones:

        - **Microsoft (recomendado):** el buzón de envíos de usuario no se usa (todos los mensajes notificados van a Microsoft).

        - **Microsoft y un buzón personalizado:** en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de correo Exchange Online existente. Los grupos de distribución no están permitidos. Los envíos de usuario irán a Microsoft para su análisis y al buzón personalizado para que el administrador o el equipo de operaciones de seguridad analicen.

        - **Solo buzón personalizado:** en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de correo Exchange Online existente. Los grupos de distribución no están permitidos. Use esta opción si desea que el mensaje solo vaya a un administrador o al equipo de operaciones de seguridad para su análisis primero. Los mensajes no irán a Microsoft a menos que el administrador lo reenvía ellos mismos.

          > [!NOTE]
          > Las organizaciones gubernamentales de Estados Unidos (GCC, GCC-H y DoD) solo pueden configurar **el buzón personalizado**. Las otras dos opciones están deshabilitadas.

          > [!NOTE]
          > Si las organizaciones están configuradas para enviar solo al buzón personalizado, los mensajes notificados no se enviarán para volver a examinarse y los resultados en el portal de mensajes notificados por el usuario siempre estarán vacíos.

      Cuando haya terminado, haga clic en **Confirmar**.

      > [!CAUTION]
      > Si ha deshabilitado los informes de correo no deseado en Outlook en la [web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) mediante Outlook en las directivas de buzón de correo web, pero configura cualquiera de las opciones anteriores para notificar mensajes a Microsoft, los usuarios podrán notificar mensajes a Microsoft en Outlook en la web mediante el complemento Report Message o el complemento Report Phishing.


    2. Deshabilitar la característica Mensaje de informe para **Outlook:** Seleccione esta opción si usa herramientas de informes de terceros en lugar del complemento Report Message, el complemento Report Phishing o los informes integrados en Outlook en la web y, a continuación, configure las siguientes opciones:

       Seleccione **Usar este buzón personalizado para recibir envíos notificados por el usuario**. En el cuadro que aparece, escriba la dirección de correo electrónico de un buzón existente que ya está en Office 365. Debe ser un buzón de correo existente en Exchange Online que pueda recibir correo electrónico.

       Cuando haya terminado, haga clic en **Confirmar**.

## <a name="third-party-reporting-tools"></a>Herramientas de informes de terceros

Puede configurar herramientas de informes de mensajes de terceros para enviar mensajes notificados al buzón personalizado. El único requisito es que el mensaje original se incluya como datos adjuntos en el mensaje que se envía al buzón personalizado (no solo reenvía el mensaje original al buzón personalizado).

Los requisitos de formato de mensaje se describen en la sección siguiente. El formato es opcional, pero si no sigue el formato prescrito, los informes siempre se envían como suplantación de identidad.

## <a name="message-submission-format"></a>Formato de envío de mensajes

Para identificar correctamente los mensajes adjuntos originales, los mensajes que se envían al buzón personalizado requieren un formato específico. Si los mensajes no usan este formato, los mensajes adjuntos originales siempre se identifican como envíos de suplantación de identidad.

Para identificar correctamente los mensajes adjuntos originales, los mensajes que se envían al buzón personalizado deben usar la siguiente sintaxis para el asunto (título del sobre):

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

donde SafetyAPIAction es uno de los siguientes valores enteros:

- 1: Correo no deseado
- 2: No deseado
- 3: Phishing

En este ejemplo se usan los siguientes valores:

- El mensaje se notifica como suplantación de identidad.
- El identificador de mensaje de red es 49871234-6dc6-43e8-abcd-08d797f20abe.
- La DIRECCIÓN IP del remitente es 167.220.232.101.
- La dirección De es test@contoso.com.
- La línea de asunto del mensaje es "probar el envío de suplantación de identidad"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

Los mensajes que no siguen este formato no se mostrarán correctamente en el portal de envíos.
