---
title: Configuración de mensajes notificados por el usuario
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
ms.openlocfilehash: 4b86341434c05f18e1dd264b6fdabef8e36f2d29
ms.sourcegitcommit: 5c9137f98e688ab23c144e75687399e390bb2601
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2022
ms.locfileid: "64705371"
---
# <a name="user-reported-message-settings"></a>Configuración de mensajes notificados por el usuario

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En Microsoft 365 organizaciones con buzones de Exchange online, puede especificar un buzón para recibir mensajes que los usuarios informen como malintencionados o no malintencionados. Cuando los usuarios notifican mensajes con las distintas opciones de informes, puede usar este buzón para interceptar mensajes (enviar solo al buzón personalizado) o recibir copias de mensajes (enviar al buzón personalizado y a Microsoft). Esta característica funciona con las siguientes opciones de informes de mensajes:

- [Complemento Mensaje de informe](enable-the-report-message-add-in.md)
- [Complemento de suplantación de identidad de informe](enable-the-report-phish-add-in.md)
- [Herramientas de informes de terceros](#third-party-reporting-tools)

La entrega de mensajes notificados por el usuario a un buzón personalizado en lugar de directamente a Microsoft permite a los administradores notificar mensajes de forma selectiva y manual a Microsoft mediante [el envío de administrador](admin-submission.md). Esta configuración se conocía anteriormente como directiva de envíos de usuarios.

  > [!NOTE]
  > Si los informes se han [deshabilitado en Outlook en la Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), la habilitación de los mensajes notificados por el usuario aquí invalidará esa configuración y permitirá a los usuarios informar de los mensajes en Outlook en la Web de nuevo.

## <a name="custom-mailbox-prerequisites"></a>Requisitos previos del buzón personalizado

Use los artículos siguientes para configurar los requisitos previos necesarios para que los mensajes notificados por el usuario vayan al buzón personalizado:

- Omita el filtrado de correo no deseado en el buzón personalizado mediante la creación de una regla de flujo de correo de intercambio para establecer el nivel de confianza de correo no deseado. Consulte [Uso del EAC para crear una regla de flujo de correo que establezca la SCL de un mensaje](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) para establecer la SCL en **Omitir el filtrado de correo no deseado**.

- [Cree una directiva antimalware](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) que incluya el buzón personalizado donde la purga automática de cero horas (ZAP) para malware está desactivada (la sección \>**Configuración de protección** **Habilitar purga automática de cero horas para malware** no está seleccionada).

- [Cree una directiva contra correo no deseado](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) que incluya el buzón personalizado donde zap para correo no deseado y ZAP para phishing están desactivados (no está seleccionada la sección \>**Purga automática** de **cero horas habilitada (ZAP).**

Si tiene Microsoft Defender para Office 365, también debe configurar los siguientes valores para que nuestro filtrado avanzado no afecte a los usuarios que informan de los mensajes:

- [Cree una directiva de vínculos seguros](set-up-safe-links-policies.md) que incluya el buzón personalizado donde está desactivado el examen de vínculos seguros (**seleccione la acción para direcciones URL potencialmente malintencionadas desconocidas en** la sección \> **De mensajes Desactivada**).

- [Cree una directiva de datos adjuntos seguros](set-up-safe-attachments-policies.md) que incluya el buzón personalizado donde está desactivado el examen de datos adjuntos seguros (sección \>**Respuesta de malware desconocida de datos adjuntos seguros** **desactivada**).

Después de comprobar que el buzón cumple todos los requisitos previos aplicables, puede usar los procedimientos de este artículo para configurar el buzón de correo de envíos de usuario.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Envíos de usuarios** , use <https://security.microsoft.com/userSubmissionsReportMessage>.

- Para modificar la configuración de los envíos de usuarios, debe ser miembro de uno de los siguientes grupos de roles:

  - **Administración de la organización** o **administrador de seguridad** en los [permisos del portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

- Necesita acceso a Exchange PowerShell en línea. Si la cuenta que intenta usar no tiene acceso a Exchange PowerShell en línea, recibirá un error similar al siguiente al especificar el buzón de correo de envíos:

  > Especificar una dirección de correo electrónico en el dominio

  Para obtener más información sobre cómo habilitar o deshabilitar el acceso a Exchange PowerShell en línea, consulte los temas siguientes:

  - [Habilitar o deshabilitar el acceso al PowerShell de Exchange Online](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [Reglas de acceso de cliente en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a>Uso del portal de Microsoft 365 Defender para configurar el buzón de correo de envíos de usuario

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas** \> **Directivas** \> de amenazas **Configuración de mensajes notificados por el usuario** en la sección **Otros**. Para ir directamente a la página **Envíos de usuarios** , use <https://security.microsoft.com/userSubmissionsReportMessage>.

2. En la página **Envíos** de usuarios, lo que ve viene determinado por si la configuración del **botón Mensaje de informe de Microsoft Outlook** es **Desactivado** o **Activado**:

   - Botón \> Mensaje de informe **de Microsoft Outlook** **Activar** ![alternancia.](../../media/scc-toggle-on.png) Seleccione esta opción si usa el complemento Mensaje de informe, el complemento De suplantación de identidad de informe o los informes integrados en Outlook en la Web y, a continuación, configure las siguientes opciones:
     - **Enviar los mensajes notificados a**: Seleccione una de las siguientes opciones:
       - **Microsoft**: No se usa el buzón de correo de envíos de usuario (todos los mensajes notificados van a Microsoft).
       - **Buzón de Microsoft y mi organización**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de correo Exchange en línea existente. No se permiten grupos de distribución. Los envíos de usuarios se dirigirán a Microsoft para su análisis y al buzón personalizado para que el equipo de operaciones de administración o seguridad lo analice.
       - **Buzón de mi organización**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón Exchange en línea existente. No se permiten grupos de distribución. Use esta opción si desea que el mensaje solo vaya a un administrador o al equipo de operaciones de seguridad para su análisis en primer lugar. Los mensajes no irán a Microsoft a menos que el administrador lo reenvíe por sí mismo.

          > [!IMPORTANT]
          > Las organizaciones gubernamentales de Ee. UU. (GCC, GCC High y DoD) solo pueden configurar el **buzón de mi organización**. Las otras dos opciones están deshabilitadas.
          >
          > Si las organizaciones están configuradas para enviar solo al buzón personalizado, los mensajes notificados no se enviarán para volver a examinarse y los resultados en el portal mensajes notificados por el usuario siempre estarán vacíos.

       Independientemente del valor que haya seleccionado para **Enviar los mensajes notificados a**, están disponibles los siguientes valores:

       - **Permitir que los usuarios elijan si quieren informar de su mensaje a Microsoft**
       - **Seleccione las opciones de informes que están disponibles para los usuarios** en la sección: Seleccione al menos una de las siguientes opciones:
         - **Pregúnteme antes de enviar el mensaje**
         - **Informar siempre del mensaje**
         - **Nunca informe del mensaje**

          > [!CAUTION]
          > Si ha [deshabilitado los informes de correo no deseado en Outlook en la Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) mediante Outlook en la Web directivas de buzón de correo, pero ha configurado cualquiera de las opciones anteriores para informar de mensajes a Microsoft, los usuarios podrán notificar mensajes a Microsoft en Outlook en la Web mediante el complemento Mensaje de informe o el complemento Suplantación de identidad de informe.

     Deje el botón Mensaje de **informe de Microsoft Outlook** activado ![**Activar**](../../media/scc-toggle-on.png) para permitir que los usuarios finales notifiquen mensajes falsos positivos desde el portal de cuarentena.

     - **Sección experiencia de informes de usuario**
       - **Antes de la pestaña Informes** : en los cuadros **Título** y **Cuerpo del mensaje** , escriba el texto descriptivo que los usuarios ven antes de que informen de un mensaje mediante el complemento Mensaje de informe o el complemento Suplantación de identidad de informe. Puede usar la variable %type% para incluir el tipo de envío (correo no deseado, no basura, phish, etc.).
       - **Pestaña Después de informar** : en los cuadros **de mensaje Título** y **Confirmación** , escriba el texto descriptivo que los usuarios ven después de que informen de un mensaje mediante el complemento Mensaje de informe o el complemento De suplantación de identidad de informe. Puede usar la variable %type% para incluir el tipo de envío.
       - **Solo se muestra cuando el usuario informa de suplantación de identidad (phishing**): active esta opción si desea mostrar el mensaje solo cuando se notifica un correo electrónico como phish. Si no es así, se mostrarán los mensajes comprobados para cualquier tipo de informe.

       Como se muestra en la página, si selecciona una opción que envía los mensajes notificados a Microsoft, también se agrega el texto siguiente a la notificación:

          > Su correo electrónico se enviará tal y como está a Microsoft para su análisis. Algunos correos electrónicos pueden contener información personal o confidencial.

   - Botón Desactivar desactivar mensaje de informe de **Microsoft Outlook** \>  ![](../../media/scc-toggle-off.png): seleccione esta opción si usa herramientas de informes de terceros en lugar del complemento Mensaje de informe, el complemento De suplantación de identidad de informe o los informes integrados en Outlook en la Web y, a continuación, configure las siguientes opciones:
     - Seleccione **Usar este buzón personalizado para recibir envíos notificados por el usuario**. En el cuadro que aparece, escriba la dirección de correo electrónico de un buzón Exchange en línea existente que puede recibir correo electrónico.

   - **Botón De mensaje de informe de cuarentena**: habilite esta característica si desea permitir que los usuarios finales informen de los mensajes de la cuarentena.

   Cuando haya terminado, haga clic en **Confirmar**. Para borrar estos valores, haga clic en **Restaurar.**

## <a name="third-party-reporting-tools"></a>Herramientas de informes de terceros

Puede configurar herramientas de informes de mensajes de terceros para enviar mensajes notificados al buzón personalizado. Para ello, establezca el **botón Mensaje de informe de Microsoft Outlook** en **Desactivado** y establezca el **buzón de Mi organización** en un buzón Office 365 de su elección.

El único requisito es que el mensaje original se incluya como . EML o . Datos adjuntos MSG (no comprimidos) en el mensaje que se envía al buzón personalizado (no reenvíe el mensaje original al buzón personalizado).

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

- Ambos mensajes se notifican como No basura en función del asunto.
- El resto se omite.


Los mensajes que no siguen este formato no se mostrarán correctamente en el portal Envíos.
