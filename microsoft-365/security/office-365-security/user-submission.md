---
title: Configuración del mensaje notificado por el usuario
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
ms.openlocfilehash: f59548a1f36e067d8b649f7fe22149362d6fe9c6
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083541"
---
# <a name="user-reported-message-settings"></a>Configuración del mensaje notificado por el usuario

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En Microsoft 365 con Exchange Online buzones de correo, puede especificar un buzón para recibir mensajes que los usuarios reportan como malintencionados o no malintencionados. Cuando los usuarios informan de mensajes con las distintas opciones de informes, puede usar este buzón para interceptar mensajes (solo enviar al buzón personalizado) o recibir copias de mensajes (enviar al buzón personalizado y Microsoft). Esta característica funciona con las siguientes opciones de informes de mensajes:

- [El complemento Mensaje de informe](enable-the-report-message-add-in.md)
- [El complemento Detección de suplantación de identidad de informes](enable-the-report-phish-add-in.md)
- [Herramientas de informes de terceros](#third-party-reporting-tools)

La entrega de mensajes notificados por el usuario a un buzón personalizado en lugar de directamente a Microsoft permite a los administradores notificar mensajes de forma selectiva y manual a Microsoft mediante [el envío de administrador.](admin-submission.md) Esta configuración se conocía anteriormente como directiva de envíos de usuario.

  > [!NOTE]
  > Si los informes se han deshabilitado en [Outlook en la Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), habilitar los mensajes notificados por el usuario aquí invalidará esa configuración y permitirá a los usuarios notificar mensajes en Outlook en la Web de nuevo.

## <a name="custom-mailbox-prerequisites"></a>Requisitos previos de buzón personalizado

Use los artículos siguientes para configurar los requisitos previos necesarios para que los mensajes notificados por el usuario vayan al buzón personalizado:

- Omitir el filtrado de correo no deseado en el buzón personalizado mediante la creación de una regla de flujo de correo de Exchange para establecer el nivel de confianza de correo no deseado. Vea [Usar el EAC para crear una](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) regla de flujo de correo que establezca el SCL de un mensaje para establecer el SCL en Omitir filtrado de correo no **deseado.**

- [Cree una directiva Caja fuerte datos](set-up-safe-attachments-policies.md) adjuntos que incluya el buzón personalizado donde se desactivará el examen de datos adjuntos de Caja fuerte ( Caja fuerte Sección De respuesta de **malware** desconocido de datos \> **adjuntos desactivado**).

- [Crear una directiva de vínculos](set-up-safe-links-policies.md) de Caja fuerte que incluya el buzón personalizado donde está desactivado el examen de vínculos de Caja fuerte (**Seleccione** la acción para direcciones URL potencialmente malintencionadas desconocidas en la sección mensajes \> **Desactivado**).

- Cree una directiva [antimalware](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) que incluya el buzón personalizado en el que la purga automática de cero horas (ZAP) para malware está desactivada **(** La sección Configuración de protección Habilitar la purga automática de horas cero para malware no está \>  seleccionada).

- [Cree](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) una directiva contra correo no deseado que incluya el buzón personalizado donde ZAP para correo no deseado y ZAP para phishing están desactivados **(** No está seleccionada la sección Purga automática de hora cero habilitada \> **(ZAP).**

- Deshabilite la regla de correo no deseado en el buzón personalizado. Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule. Después de deshabilitarlo, EOP no puede mover mensajes a la carpeta correo  no deseado en función de la acción de veredicto de filtrado de correo no deseado Mover el mensaje a la carpeta correo no deseado o a la colección de listas seguras del buzón.

Después de comprobar que el buzón cumple todos los requisitos previos aplicables, puede usar los procedimientos de este artículo para configurar el buzón de envíos de usuario.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com/>. Para ir directamente a la **página Envíos,** use <https://security.microsoft.com/reportsubmission> .

- Para modificar la configuración de envíos de usuarios, debe ser miembro de uno de los siguientes grupos de roles:

  - **Administración de** la organización **o Administrador** de seguridad en permisos en el portal de [Microsoft 365 Defender .](permissions-microsoft-365-security-center.md)
  - **Administración de** la [organización en Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

- Necesita tener acceso a Exchange Online PowerShell. Si la cuenta que está intentando usar no tiene acceso Exchange Online PowerShell, recibirá un error similar al siguiente al especificar el buzón de envío:

  > Especificar una dirección de correo electrónico en el dominio

  Para obtener más información acerca de cómo habilitar o deshabilitar el acceso a Exchange Online PowerShell, consulte los siguientes temas:

  - [Habilitar o deshabilitar el acceso a Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Reglas de acceso de cliente en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a>Usar el portal Microsoft 365 Defender para configurar el buzón de envíos de usuario

1. En el portal Microsoft 365 Defender, vaya a **Directivas &** reglas de amenazas Sección Otras secciones Configuración de mensajes \>  \>  \>  \> **notificados por el usuario Envíos de usuario**.

2. En la **página Envíos de** usuario, lo que ve está determinado por si la configuración del botón Mensaje de informe de **Microsoft Outlook** es **Off** o **On**:

   - **Botón Outlook mensaje de informe de Microsoft** \> **On** ![ Activar: seleccione esta opción si usa el complemento Mensaje de informe, el complemento Report Phishing o los informes integrados en Outlook en la Web y, a continuación, configure las siguientes ](../../media/scc-toggle-on.png) opciones:
     - **Enviar los mensajes notificados a**: Seleccione una de las siguientes opciones:
       - **Microsoft:** el buzón de envíos de usuario no se usa (todos los mensajes notificados van a Microsoft).
       - **Buzón de Microsoft** y mi organización: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de correo Exchange Online existente. Los grupos de distribución no están permitidos. Los envíos de usuario irán a Microsoft para su análisis y al buzón personalizado para que el administrador o el equipo de operaciones de seguridad analicen.
       - **Buzón de mi** organización: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de correo Exchange Online existente. Los grupos de distribución no están permitidos. Use esta opción si desea que el mensaje solo vaya a un administrador o al equipo de operaciones de seguridad para su análisis primero. Los mensajes no irán a Microsoft a menos que el administrador lo reenvía ellos mismos.

          > [!IMPORTANT]
          >
          > Las organizaciones gubernamentales de Estados Unidos (GCC, GCC High y DoD) solo pueden configurar el **buzón de Mi organización.** Las otras dos opciones están deshabilitadas.
          >
          > Si las organizaciones están configuradas para enviar solo al buzón personalizado, los mensajes notificados no se enviarán para volver a examinarse y los resultados en el portal de mensajes notificados por el usuario siempre estarán vacíos.

       Independientemente del valor seleccionado para **Enviar los mensajes notificados a**, la siguiente configuración está disponible:

       - **Permitir que los usuarios elijan si quieren informar de su mensaje a Microsoft**
       - **Sección Seleccionar opciones de informes que están** disponibles para los usuarios: Seleccione al menos una de las siguientes opciones:
         - **Pregúnteme antes de enviar el mensaje**
         - **Informar siempre del mensaje**
         - **No informar nunca del mensaje**

          > [!CAUTION]
          > Si ha deshabilitado los informes de correo no deseado en [Outlook en la Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) mediante directivas de buzón de correo de Outlook en la Web, pero ha configurado cualquiera de las opciones anteriores para notificar mensajes a Microsoft, los usuarios podrán notificar mensajes a Microsoft en Outlook en la Web mediante el complemento Mensaje de informe o el complemento Report Phishing.

     - **Sección Experiencia de informes de usuarios**
       - **Antes de informar:**  en  los cuadros de cuerpo Título y Mensaje, escriba el texto descriptivo que los usuarios ven antes de informar de un mensaje mediante el complemento Report Message o el complemento Report Phishing. Puede usar la variable %type% para incluir el tipo de envío (correo no deseado, no deseado, phish, etc.).
       - **Después de la** pestaña  Informes: en los cuadros Título y Mensaje de confirmación, escriba el texto descriptivo que los usuarios ven después de informar de un mensaje mediante el complemento Report Message o el complemento Report Phishing.  Puede usar la variable %type% para incluir el tipo de envío.

       Como se muestra en la página, si selecciona una opción que envía los mensajes notificados a Microsoft, también se agrega el siguiente texto a la notificación:

          > El correo electrónico se enviará tal como está a Microsoft para su análisis. Algunos correos electrónicos pueden contener información personal o confidencial.

   - **Botón Outlook mensaje de informe de Microsoft** \> **Desactivado** ![ Desactivar: seleccione esta opción si usa herramientas de informes de terceros en lugar del complemento Mensaje de informe, el complemento Report Phishing o los informes integrados en ](../../media/scc-toggle-off.png) Outlook en la Web y, a continuación, configure las siguientes opciones:
     - Seleccione **Usar este buzón personalizado para recibir envíos notificados por el usuario**. En el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de correo Exchange Online que pueda recibir correo electrónico.

   Cuando haya terminado, haga clic en **Confirmar**. Para borrar estos valores, haga clic en **Restaurar**

## <a name="third-party-reporting-tools"></a>Herramientas de informes de terceros

Puede configurar herramientas de informes de mensajes de terceros para enviar mensajes notificados al buzón personalizado. Para ello, establecerá la configuración del botón Mensaje de informe de **Microsoft Outlook** en **Desactivado** y establecerá el buzón de **Mi** organización en un buzón de correo Office 365 de su elección.

El único requisito es que el mensaje original se incluya como . EML o . Datos adjuntos MSG (no comprimidos) en el mensaje que se envía al buzón personalizado (no solo reenvía el mensaje original al buzón personalizado).

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
