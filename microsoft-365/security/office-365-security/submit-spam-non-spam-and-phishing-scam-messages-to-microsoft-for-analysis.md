---
title: Enviar mensajes a Microsoft de forma manual para su análisis
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'Usted y sus usuarios pueden enviar mensajes de correo no deseado falsos negativos y falsos positivos a Microsoft para su análisis. '
ms.openlocfilehash: 13b2e42f749b54e0c2b71fe095c077992560ea8c
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032809"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Enviar mensajes a Microsoft de forma manual para su análisis

> [!NOTE]
> Si es administrador de una organización de Office 365 con buzones de correo de Exchange Online, le recomendamos que use el portal de envíos del centro de seguridad & cumplimiento de Office 365. Para obtener más información, vea [usar el envío de administración para enviar un correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft](admin-submission.md).

Puede resultar frustrante cuando los usuarios de la organización reciben mensajes de correo no deseado o mensajes de suplantación de identidad (phishing) en su bandeja de entrada, o si no reciben un mensaje de correo electrónico legítimo porque está marcado como correo no deseado. Estamos ajustando constantemente los filtros de correo no deseado para que sean más precisos.

Usted y sus usuarios pueden ayudar a este proceso mediante el envío de falsos positivos (correo electrónico bueno marcado como no válido), los falsos negativos (correo erróneo permitido) y los mensajes de suplantación de identidad a Microsoft para su análisis.

> [!NOTE]
> Debido al elevado volumen de envíos que recibimos, es posible que no podamos contestar todas las solicitudes de análisis.

## <a name="submit-false-negatives-to-microsoft"></a>Enviar falsos negativos a Microsoft

> [!TIP]
> En lugar de usar los siguientes procedimientos para informar sobre falsos negativos, los usuarios de Outlook y Outlook en la web (anteriormente conocido como Outlook Web App) pueden usar el complemento de mensajes de informe para Microsoft Outlook. Para obtener información sobre cómo instalar y usar esta herramienta, consulte [Habilitar el complemento de mensajes de informe](enable-the-report-message-add-in.md).

Si recibe un mensaje que pasa a través del filtrado de correo no deseado que debería haberse identificado como correo no deseado o suplantación de identidad, puede enviar el mensaje a Microsoft spam Analysis y Microsoft phishing Analysis Teams según corresponda. Los analistas revisarán el mensaje y lo agregarán a los filtros de todo el servicio si cumple con los criterios de clasificación.

1. Cree un mensaje de correo electrónico nuevo en blanco con uno de los siguientes destinatarios:

   - **Correo no deseado**:`junk@office365.microsoft.com`

   - **Suplantación de identidad**:`phish@office365.microsoft.com`

2. Arrastre y coloque el mensaje no deseado o de suplantación de identidad en el nuevo mensaje. Se guardará el mensaje no deseado o de suplantación de identidad (phishing) como datos adjuntos en el nuevo mensaje. No copie y pegue el contenido del mensaje o lo reenvíe (necesitamos el mensaje original para que podamos inspeccionar los encabezados del mensaje).

   > [!NOTE]
   > <ul><li>Puede adjuntar varios mensajes en el nuevo mensaje. Asegúrese de que todos los mensajes sean del mismo tipo: mensajes de suplantación de identidad (phishing) o mensajes de correo electrónico no deseado.</li><li>Deje el cuerpo del nuevo mensaje en blanco.<li></li>Use cualquiera de los formatos. msg (formato predeterminado de Outlook) o. eml (formato predeterminado de Outlook en la web) para los mensajes adjuntos.</li></ul>

3. Cuando haya terminado, haga clic en **Enviar**.

> [!TIP]
> Los administradores tienen varias formas diferentes de bloquear mensajes específicos que se identifican como correo no deseado. Para obtener más información, vea [crear listas de remitentes bloqueados en Office 365](create-block-sender-lists-in-office-365.md).

## <a name="submit-false-positives-to-microsoft"></a>Enviar falsos positivos a Microsoft

> [!TIP]
> En lugar de usar los siguientes procedimientos para notificar falsos positivos, los usuarios de Outlook y Outlook en la web pueden usar el complemento de mensajes de informe para Microsoft Outlook. Para obtener información sobre cómo instalar y usar esta herramienta, consulte [Habilitar el complemento de mensajes de informe](enable-the-report-message-add-in.md).

Si un mensaje se identificó incorrectamente como correo no deseado, puede enviar el mensaje al equipo de análisis de correo no deseado de Microsoft. Los analistas evaluarán el mensaje y (según los resultados del análisis) se pueden ajustar los filtros de todo el servicio para permitir el paso del mensaje.

1. Cree un nuevo mensaje de correo electrónico en `not_junk@office365.microsoft.com` blanco con como destinatario:

2. Arrastre y coloque el mensaje con identificación indebido en el nuevo mensaje. De este modo, se guardará el mensaje identificado indebido como datos adjuntos en el nuevo mensaje. No copie y pegue el contenido del mensaje o lo reenvíe (necesitamos el mensaje original para que podamos inspeccionar los encabezados del mensaje).

   > [!NOTE]
   > <ul><li>Puede adjuntar varios mensajes en el nuevo mensaje. Asegúrese de que todos los mensajes sean del mismo tipo: mensajes de suplantación de identidad (phishing) o mensajes de correo electrónico no deseado.</li><li>Deje el cuerpo del nuevo mensaje en blanco.<li></li>Use cualquiera de los formatos. msg (formato predeterminado de Outlook) o. eml (formato predeterminado de Outlook en la web) para los mensajes adjuntos.</li></ul>

3. Cuando haya terminado, haga clic en **Enviar**.

> [!TIP]
> Los administradores tienen varias formas diferentes de permitir que mensajes específicos omitan el filtrado de correo no deseado. Para obtener más información, consulte [crear listas de remitentes seguros en Office 365](create-safe-sender-lists-in-office-365.md).

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Crear una regla de flujo de correo para recibir copias de mensajes que se notifican a Microsoft

Puede crear una regla de flujo de correo (también denominada regla de transporte) que busca mensajes de correo electrónico que se notifican a Microsoft mediante los métodos descritos en este tema y puede configurar destinatarios en copia oculta para recibir copias de estos mensajes notificados.

Puede crear la regla de flujo de correo en el centro de administración de Exchange (EAC) y PowerShell (Exchange Online PowerShell para Office 365 clientes; Exchange Online Protection PowerShell para clientes independientes de EOP).

### <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Debe tener asignados permisos en Exchange Online para poder realizar estos procedimientos. En concreto, debe tener asignado el rol **reglas de transporte** , que se asigna a las **funciones administración**de la organización, **Administración del cumplimiento**y administración de **registros** de forma predeterminada. Para obtener más información, consulte[Administrar grupos de roles en Exchange en línea](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Para abrir el EAC en Exchange Online, consulte [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Para conectarse a Exchange Online Protection PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Para obtener más información acerca de las reglas de flujo de correo en Exchange Online y EOP independiente, consulte los siguientes temas:

  - [Reglas de flujo de correo (reglas de transporte) en Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Excepciones (predicados) y condiciones de reglas de flujo de correo en Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Acciones de las reglas de flujo de correo en Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Usar el EAC para crear una regla de flujo de correo para recibir copias de mensajes notificados

1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.

2. Haga **Add** ![clic en agregar](../../media/ITPro-EAC-AddIcon.png) icono Agregar y, a continuación, seleccione **crear una nueva regla**.

3. En la ventana **Nueva regla** que se abre, configure las siguientes opciones:

   - **Name**: escriba un nombre único y descriptivo para la regla. Por ejemplo, los mensajes CCO que se notifican a Microsoft.

   - Haga clic en **Más opciones**.

   - **Aplicar esta regla si**: seleccione **la dirección del destinatario** \> **incluye cualquiera de estas palabras**: en el cuadro de diálogo **especificar palabras o frases** que aparece, escriba uno de los siguientes valores, haga](../../media/ITPro-EAC-AddIcon.png)clic en **Agregar** ![icono Agregar y repita el procedimiento hasta que haya introducido todos los valores.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     Para editar una entrada, selecciónela y haga clic en **Editar** ![icono](../../media/ITPro-EAC-EditIcon.png)de edición. Para quitar una entrada, selecciónela y haga clic en **quitar** ![icono](../../media/ITPro-EAC-DeleteIcon.png)quitar.

     Cuando haya terminado, haga clic en **Aceptar**.

   - **Haga lo siguiente**: seleccione **agregar destinatarios** \> **en el cuadro CCO**. En el cuadro de diálogo que aparece, busque y seleccione los destinatarios que desea agregar. Cuando haya terminado, haga clic en **Aceptar**.

4. Puede realizar selecciones adicionales para auditar la regla, probarla, activar la regla durante un período de tiempo específico y otras opciones de configuración. Se recomienda probar la regla antes de aplicarla.

5. Cuando haya terminado, haga clic en **Guardar**.

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Usar PowerShell para crear una regla de flujo de correo para recibir copias de mensajes notificados

En este ejemplo se crea una nueva regla de flujo de correo denominada BCC mensajes enviados a Microsoft que busca mensajes de correo electrónico que se notifican a Microsoft mediante los métodos descritos en este tema y agrega los usuarios laura@contoso.com y julia@contoso.com como destinatarios CCO.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Para comprobar que ha configurado una regla de flujo de correo para recibir copias de mensajes enviados, siga uno de estos pasos:

- En el EAC, vaya a **Mail flow** \> **reglas** \> de flujo de correo Seleccione \> la regla haga clic](../../media/ITPro-EAC-EditIcon.png)en **Editar** ![icono de edición y Compruebe la configuración.

- En PowerShell, ejecute el siguiente comando para comprobar la configuración:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Envíe mensajes de prueba a una de las direcciones de correo electrónico de informes y compruebe los resultados.
