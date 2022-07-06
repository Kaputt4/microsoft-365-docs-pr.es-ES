---
title: Configuración del mensaje notificado por el usuario
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: Los administradores pueden aprender a configurar un buzón para recopilar correo no deseado y correo electrónico de suplantación de identidad (phishing) que notifican los usuarios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c4faa6ce80a885ecea864cc2fa51be29553c4a3d
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66636433"
---
# <a name="user-reported-message-settings"></a>Configuración del mensaje notificado por el usuario

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones de Exchange Online, puede especificar un buzón para recibir mensajes que los usuarios notifican como malintencionados o no malintencionados. Cuando los usuarios notifican mensajes con las distintas opciones de informes, puede usar este buzón para interceptar mensajes (enviar solo al buzón personalizado) o recibir copias de mensajes (enviar al buzón personalizado y a Microsoft). Esta característica funciona con las siguientes opciones de informes de mensajes:

- [Complemento Mensaje de informe](enable-the-report-message-add-in.md)
- [Complemento de suplantación de identidad de informe](enable-the-report-phish-add-in.md)
- [Herramientas de informes de terceros](#third-party-reporting-tools)

La entrega de mensajes notificados por el usuario a un buzón personalizado en lugar de directamente a Microsoft permite a los administradores notificar mensajes de forma selectiva y manual a Microsoft mediante [Administración envío](admin-submission.md). Esta configuración se conocía anteriormente como directiva de envíos de usuarios.

  > [!NOTE]
  > Si los informes se han [deshabilitado en Outlook en la Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), la habilitación de los mensajes notificados por el usuario aquí invalidará esa configuración y permitirá a los usuarios informar de los mensajes en Outlook en la Web de nuevo.

## <a name="custom-mailbox-prerequisites"></a>Requisitos previos del buzón personalizado

Use los artículos siguientes para configurar los requisitos previos necesarios para que los mensajes notificados por el usuario vayan al buzón personalizado:

- [Identifique el buzón personalizado como un buzón de SecOps](configure-advanced-delivery.md#use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy).

- [Cree una directiva antimalware](configure-anti-malware-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-malware-policies) para el buzón personalizado con la siguiente configuración:
  - La purga automática de cero horas (ZAP) para malware está desactivada (la sección \>**Configuración de protección** **Habilitar purga automática de cero horas para malware** no está seleccionada).
  - La opción de filtro de datos adjuntos comunes está desactivada (no está seleccionada la sección \>**Configuración de protección** **Habilitar el filtro de datos adjuntos comunes**).

Si tiene Microsoft Defender para Office 365, también debe configurar los siguientes valores para que nuestro filtrado avanzado no afecte a los mensajes notificados:

- Asegúrese de que el buzón personalizado no forma parte de ninguna directiva de [seguridad preestablecida](preset-security-policies.md#use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-standard-and-strict-preset-security-policies).

- [Cree una directiva de vínculos seguros](set-up-safe-links-policies.md) para el buzón personalizado donde está desactivado el examen de vínculos seguros (**seleccione la acción para direcciones URL potencialmente malintencionadas desconocidas en la sección de mensajes** > **Desactivado**).

- [Cree una directiva de datos adjuntos seguros](set-up-safe-attachments-policies.md) para el buzón personalizado en el que el examen de datos adjuntos seguros, incluida la entrega dinámica, esté desactivado (sección **De respuesta de malware desconocido de Datos adjuntos seguros** > **Desactivado**).

Después de comprobar que el buzón cumple todos los requisitos previos aplicables, puede usar los procedimientos de este artículo para configurar el buzón de correo de envíos de usuario.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Envíos de usuarios** , use <https://security.microsoft.com/userSubmissionsReportMessage>.

- Para modificar la configuración de los envíos de usuarios, debe ser miembro de uno de los siguientes grupos de roles:

  - **Administración de la organización** o **administrador de seguridad** en los [permisos del portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

- Necesita acceso a Exchange Online PowerShell. Si la cuenta que intenta usar no tiene acceso a Exchange Online PowerShell, recibirá un error similar al siguiente al especificar el buzón de correo de envíos:

  > Especificar una dirección de correo electrónico en el dominio

  Para obtener más información sobre cómo habilitar o deshabilitar el acceso a Exchange Online PowerShell, consulte los temas siguientes:

  - [Habilitar o deshabilitar el acceso al PowerShell de Exchange Online](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [Reglas de acceso de cliente en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a>Uso del portal de Microsoft 365 Defender para configurar el buzón de correo de envíos de usuario

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas** > **Directivas** >  de amenazas **Configuración de mensajes notificadas por el usuario** en la sección **Otros**. Para ir directamente a la página **Envíos de usuarios** , use <https://security.microsoft.com/userSubmissionsReportMessage>.

2. En la página **Envíos** de usuarios, lo que ve viene determinado por si la configuración del **botón Mensaje de informe de Microsoft Outlook** está **Desactivada** o **Activada**:

   - Botón  >  **Mensaje de informe de Microsoft Outlook** **En** ![ Alternar.](../../media/scc-toggle-on.png): seleccione esta opción si usa el complemento Mensaje de informe, el complemento De suplantación de identidad de informe o los informes integrados en Outlook en la Web y, a continuación, configure los siguientes valores:
     - **Enviar los mensajes notificados a**: Seleccione una de las siguientes opciones:
       - **Microsoft**: No se usa el buzón de correo de envíos de usuario (todos los mensajes notificados van a Microsoft).
       - **Buzón de Microsoft y mi organización**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de correo Exchange Online existente. No se permiten grupos de distribución. Los envíos de usuarios se dirigirán a Microsoft para su análisis y al buzón personalizado para que el equipo de operaciones de administración o seguridad lo analice.
       - **Buzón de mi organización**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de correo Exchange Online existente. No se permiten grupos de distribución. Use esta opción si desea que el mensaje solo vaya a un administrador o al equipo de operaciones de seguridad para su análisis en primer lugar. Los mensajes no irán a Microsoft a menos que el administrador lo reenvíe por sí mismo.

          > [!IMPORTANT]
          > Las organizaciones gubernamentales de Ee. UU. (GCC, GCC High y DoD) solo pueden configurar el **buzón de mi organización**. Las otras dos opciones están deshabilitadas.
          >
          > Si las organizaciones están configuradas para enviar mensajes notificados por el usuario solo al buzón personalizado, los mensajes notificados aparecerán en **Mensajes notificados** por el usuario, pero sus resultados siempre estarán vacíos (ya que no se habrían vuelto a examinar).
          >
          > Si realiza simulaciones de suplantación de identidad mediante [el entrenamiento de simulación de ataque](attack-simulation-training-get-started.md) o un producto de terceros, debe [configurar este buzón como buzón de SecOps](configure-advanced-delivery.md). Si no lo hace, los mensajes de informes pueden desencadenar asignaciones de entrenamiento en el producto de simulación de suplantación de identidad (phishing).

       Independientemente del valor que haya seleccionado para **Enviar los mensajes notificados a**, están disponibles los siguientes valores:

       - **Permitir que los usuarios elijan si quieren informar de su mensaje a Microsoft**
       - **Seleccione las opciones de informes que están disponibles para los usuarios** en la sección: Seleccione al menos una de las siguientes opciones:
         - **Pregúnteme antes de enviar el mensaje**
         - **Informar siempre del mensaje**
         - **Nunca informe del mensaje**

          > [!CAUTION]
          > Si ha [deshabilitado los informes de correo no deseado en Outlook en la Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) mediante Outlook en la Web directivas de buzón de correo, pero ha configurado cualquiera de las opciones anteriores para informar de mensajes a Microsoft, los usuarios podrán notificar mensajes a Microsoft en Outlook en la Web mediante el complemento Mensaje de informe o el complemento Suplantación de identidad de informe.

     Deje el botón ![**Mensaje de informe de Microsoft Outlook** activado Activar](../../media/scc-toggle-on.png) **para permitir** que los usuarios finales notifiquen mensajes falsos positivos desde el portal de cuarentena.

     - **Sección experiencia de informes de usuario**
       - **Antes de la pestaña Informes** : en los cuadros **Título** y **Cuerpo del mensaje** , escriba el texto descriptivo que los usuarios ven antes de que informen de un mensaje mediante el complemento Mensaje de informe o el complemento Suplantación de identidad de informe. Puede usar la variable %type% para incluir el tipo de envío (correo no deseado, no basura, phish, etc.).
       - **Pestaña Después de informar** : en los cuadros **de mensaje Título** y **Confirmación** , escriba el texto descriptivo que los usuarios ven después de que informen de un mensaje mediante el complemento Mensaje de informe o el complemento De suplantación de identidad de informe. Puede usar la variable %type% para incluir el tipo de envío.
       - **Solo se muestra cuando el usuario informa de suplantación de identidad (phishing**): active esta opción si desea mostrar el mensaje solo cuando se notifica un correo electrónico como phish. Si no es así, se mostrarán los mensajes comprobados para cualquier tipo de informe.

       Como se muestra en la página, si selecciona una opción que envía los mensajes notificados a Microsoft, también se agrega el texto siguiente a la notificación:

          > Su correo electrónico se enviará tal y como está a Microsoft para su análisis. Algunos correos electrónicos pueden contener información personal o confidencial.

   - Botón  >  **Mensaje de informe de Microsoft Outlook** **Desactivado** ![ Alternar desactivado:](../../media/scc-toggle-off.png) seleccione esta opción si usa herramientas de informes de terceros en lugar del complemento Mensaje de informe, el complemento De suplantación de identidad de informe o los informes integrados en Outlook en la Web y, a continuación, configure las siguientes opciones:
     - Seleccione **Usar este buzón personalizado para recibir envíos notificados por el usuario**. En el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de correo Exchange Online existente que puede recibir correo electrónico.

   - **Botón De mensaje de informe de cuarentena**: habilite esta característica si desea permitir que los usuarios finales informen de los mensajes de la cuarentena.

3. Cuando haya terminado, haga clic en **Confirmar**. Para borrar estos valores, haga clic en **Restaurar**.

## <a name="third-party-reporting-tools"></a>Herramientas de informes de terceros

Puede configurar herramientas de informes de mensajes de terceros para enviar mensajes notificados al buzón personalizado. Para ello, establezca el **botón Mensaje de informe de Microsoft Outlook** en **Desactivado** y establezca el **buzón de Mi organización** en un buzón Office 365 de su elección.

El único requisito es que el mensaje original se incluya como . EML o . Datos adjuntos MSG (no comprimidos) en el mensaje que se envía al buzón personalizado (no reenvíe el mensaje original al buzón personalizado).

 > [!NOTE]
 > Si hay varios datos adjuntos de correo electrónico presentes en el correo electrónico, se descartará el envío. Solo se admiten correos electrónicos con datos adjuntos de un correo electrónico.

Los requisitos de formato de mensaje se describen en la sección siguiente. El formato es opcional, pero si no sigue el formato prescrito, los informes siempre se enviarán como phish.

## <a name="message-submission-format"></a>Formato de envío de mensajes

Para identificar correctamente los mensajes adjuntos originales, los mensajes que se envían al buzón personalizado requieren formato específico. Si los mensajes no usan este formato, los mensajes adjuntos originales siempre se identifican como envíos de phishing.

Si desea especificar el motivo notificado para los mensajes adjuntos originales, los mensajes que se envían al buzón personalizado (no modifican los datos adjuntos) deben empezar con uno de los siguientes prefijos en el asunto (título del sobre):

- 1| o correo no deseado:
- 2| o no basura:
- 3| o phishing:

Por ejemplo:

`3|This part is ignored by the system` <br>
`Not Junk:This part of the subject is ignored as well`

Los mensajes que no siguen este formato no se mostrarán correctamente en el portal Envíos.
