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
ms.openlocfilehash: 4d3f2640752f2dae152ef4be8b9ac2d2996c802a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071075"
---
# <a name="user-submissions-policy"></a>Directiva de envíos de usuarios

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones de Exchange Online, puede especificar un buzón para recibir mensajes que los usuarios reportan como malintencionados o no malintencionados. Cuando los usuarios envían mensajes con las distintas opciones de informes, puede usar este buzón para interceptar mensajes (solo enviar al buzón personalizado) o recibir copias de mensajes (enviar al buzón personalizado y Microsoft). Esta característica funciona con las siguientes opciones de informes de mensajes:

- [El complemento Mensaje de informe](enable-the-report-message-add-in.md)

- [El complemento Detección de suplantación de identidad de informes](enable-the-report-phish-add-in.md)

- [Informes integrados en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (anteriormente conocido como Outlook Web App)

- [Informes integrados en Outlook para iOS y Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Si los informes se han deshabilitado en Outlook en la [web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)habilitar los envíos de usuario aquí invalidará esa configuración y permitirá a los usuarios notificar mensajes en Outlook en la web de nuevo.

También puede configurar herramientas de informes de mensajes de terceros para reenviar mensajes al buzón que especifique.

La entrega de mensajes notificados por el usuario a un buzón personalizado en lugar de directamente a Microsoft permite a los administradores notificar mensajes de forma selectiva y manual a Microsoft mediante [el envío de administrador.](admin-submission.md)

## <a name="custom-mailbox-prerequisites"></a>Requisitos previos de buzón personalizado

Use los artículos siguientes para configurar los requisitos previos necesarios para que los mensajes notificados por el usuario vayan al buzón personalizado:

- Omitir el filtrado de correo no deseado en el buzón personalizado mediante la creación de una regla de flujo de correo de Exchange para establecer el nivel de confianza de correo no deseado. Vea [Usar el EAC para crear una](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) regla de flujo de correo que establezca el SCL de un mensaje para establecer el SCL en **-1**.

- Desactiva el examen de datos adjuntos en busca de malware en el buzón personalizado. Use Configurar directivas de datos adjuntos seguros en [Defender para Office 365](set-up-safe-attachments-policies.md) para crear una directiva de datos adjuntos seguros con la opción **Desactivado** para datos adjuntos seguros respuesta de **malware desconocido**.

- Desactivar el examen de direcciones URL en los mensajes del buzón personalizado. Use Configurar directivas de vínculos seguros en [Defender para Office 365](set-up-safe-links-policies.md) para crear una directiva de vínculos seguros con la opción **Desactivado** para Seleccionar la acción para direcciones URL potencialmente malintencionadas desconocidas en **los mensajes.**

- Crear una directiva antimalware para desactivar Malware Zero-hour Auto Purge. Consulte [Use the Security & Compliance Center to create anti-malware policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) to set Malware **Zero-hour Auto Purge** to **Off**.

- Cree una directiva de filtro de correo no deseado para deshabilitar la purga automática de hora cero (ZAP) para correo no deseado y suplantación de identidad (phishing) en el buzón personalizado. Vea [Usar el Centro de seguridad & cumplimiento para](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)  crear directivas contra correo no deseado y desactive las casillas Activar para **ZAP** de correo no deseado y ZAP **de suplantación de identidad**.

- Deshabilite la regla de correo no deseado en el buzón personalizado. Use [Configurar la configuración de correo no deseado en los buzones de Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md) para deshabilitar la regla de correo no deseado. Una vez deshabilitado, EOP no puede mover mensajes a la carpeta  correo no deseado en función de la acción de veredicto de filtrado de correo no deseado Mover el mensaje a la carpeta correo no deseado o la colección de listas seguras en el buzón.

Después de comprobar que el buzón cumple todos los requisitos previos aplicables, use el Centro de seguridad & cumplimiento para configurar el buzón de [envíos](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) de usuario (en este artículo).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la **página Envíos de usuario,** use <https://protection.office.com/userSubmissionsReportMessage> .

- Para modificar la configuración de envíos de usuarios, debe ser miembro de uno de los siguientes grupos de roles:

  - **Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).
  - **Administración de la** organización [en Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

- Necesita acceso a Exchange Online PowerShell. Si la cuenta que está intentando usar no tiene acceso a Exchange Online PowerShell, recibirá un error similar al especificar el buzón de envíos:

  > Especificar una dirección de correo electrónico en el dominio

  Para obtener más información sobre cómo habilitar o deshabilitar el acceso a Exchange Online PowerShell, consulte los siguientes temas:

  - [Habilitar o deshabilitar el acceso a Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Reglas de acceso de cliente en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Usar el Centro de seguridad & cumplimiento para configurar el buzón de envíos de usuario

1. En el Centro de & cumplimiento, vaya a **Administración** de amenazas \>  \> **Envíos de usuario de directiva**.

2. En la **página Envíos de** usuario que aparece, seleccione una de las siguientes opciones:

      1. Habilitar la característica Mensaje de informe para **Outlook (recomendado):** seleccione esta opción si usa el complemento Mensaje de informe, el complemento de suplantación de identidad de informes o los informes integrados en Outlook en la web y, a continuación, configure las siguientes opciones:

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
        -  **Nunca enviar informes** \
   Cuando haya terminado, haga clic en **Guardar**.
              - **Enviar los mensajes notificados a**: Realice una de las siguientes selecciones:
              - **Microsoft (recomendado):** el buzón de envíos de usuario no se usa (todos los mensajes notificados van a Microsoft).
              - **Microsoft y un buzón personalizado:** en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de Exchange Online existente. Los grupos de distribución no están permitidos. Los envíos de usuario irán a Microsoft para su análisis y al buzón personalizado para que el administrador o el equipo de operaciones de seguridad analicen.
              - **Solo buzón personalizado:** en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de Exchange Online existente. Los grupos de distribución no están permitidos. Use esta opción si desea que el mensaje solo vaya a un administrador o al equipo de operaciones de seguridad para su análisis primero. Los mensajes no irán a Microsoft a menos que el administrador lo reenvía ellos mismos.

        > [!NOTE]
        > Las organizaciones gubernamentales de Estados Unidos (GCC, GCC-H y DoD) solo pueden configurar el **buzón personalizado**. Las otras dos opciones están deshabilitadas.

      Cuando haya terminado, haga clic en **Confirmar**.

      > [!CAUTION]
      > Si ha deshabilitado los informes de correo no deseado en Outlook en la [web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) con las directivas de buzón de correo de Outlook en la web, pero configura cualquiera de las opciones anteriores para notificar mensajes a Microsoft, los usuarios podrán notificar mensajes a Microsoft en Outlook en la web mediante el complemento Mensaje de informe o el complemento Report Phishing.


    1. Deshabilitar la característica Mensaje de informe para **Outlook:** seleccione esta opción si usa herramientas de informes de terceros en lugar del complemento Mensaje de informe, el complemento Report Phishing o los informes integrados en Outlook en la web y, a continuación, configure las siguientes opciones:

          Seleccione **Usar este buzón personalizado para recibir envíos notificados por el usuario**. En el cuadro que aparece, escriba la dirección de correo electrónico de un buzón existente que ya está en Office 365. Debe ser un buzón existente en Exchange Online que pueda recibir correo electrónico.

          Cuando haya terminado, haga clic en **Confirmar**.

## <a name="message-submission-format"></a>Formato de envío de mensajes

Los mensajes enviados a buzones personalizados deben seguir un formato de correo de envío específico. El asunto (título del sobre) del envío debe tener este formato:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

donde SafetyAPIAction es uno de los siguientes valores enteros:

- 1: Correo no deseado
- 2: No deseado
- 3: Phishing

En el siguiente ejemplo:

- El mensaje se notifica como suplantación de identidad.
- El identificador de mensaje de red es 49871234-6dc6-43e8-abcd-08d797f20abe.
- La DIRECCIÓN IP del remitente es 167.220.232.101.
- La dirección De es test@contoso.com.
- La línea de asunto del mensaje es "probar el envío de suplantación de identidad"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

Los mensajes que no siguen este formato no se mostrarán correctamente en el portal de envíos.