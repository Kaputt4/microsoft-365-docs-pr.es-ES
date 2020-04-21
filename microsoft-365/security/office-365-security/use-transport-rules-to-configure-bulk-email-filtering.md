---
title: Usar reglas de flujo de correo para filtrar el correo electrónico masivo en Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a usar reglas de flujo de correo en Exchange Online Protection para el filtrado masivo de correo electrónico.
ms.openlocfilehash: 229a66658e041be737efbc4cbb7c36ba667d3aed
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631078"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-office-365"></a>Usar reglas de flujo de correo para filtrar el correo electrónico masivo en Office 365

Si es un cliente de Microsoft 365 con buzones en Exchange online o un cliente independiente de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP usa directivas contra correo no deseado (también conocidas como directivas de filtro de correo no deseado o directivas de filtro de contenido) para analizar los mensajes entrantes en busca de correo no deseado y correo masivo (también conocido como correo gris). Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado en Office 365 ](configure-your-spam-filter-policies.md).

Si desea más opciones para filtrar el correo masivo, puede crear reglas de flujo de correo (también conocidas como reglas de transporte) para buscar patrones de texto o frases que se encuentren con frecuencia en el correo masivo y marcar dichos mensajes como correo no deseado. Para obtener más información sobre el correo masivo, vea [¿cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo? y el](what-s-the-difference-between-junk-email-and-bulk-email.md) [nivel de quejas masivas (BCL) en Office 365](bulk-complaint-level-values.md).

En este tema se explica cómo crear estas reglas de flujo de correo en el centro de administración de Exchange (EAC) y PowerShell (Exchange Online PowerShell para los clientes de Microsoft 365; Exchange Online Protection PowerShell para clientes independientes de EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Debe tener asignados permisos en Exchange Online para poder realizar estos procedimientos. En concreto, debe tener asignado el rol **reglas de transporte** , que se asigna a las **funciones administración**de la organización, **Administración del cumplimiento**y administración de **registros** de forma predeterminada. Para obtener más información, consulte[Administrar grupos de roles en Exchange en línea](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Para abrir el EAC en Exchange Online, consulte [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Para conectarse a Exchange Online Protection PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Para obtener más información acerca de las reglas de flujo de correo en Exchange Online y EOP independiente, consulte los siguientes temas:

  - [Reglas de flujo de correo (reglas de transporte) en Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Excepciones (predicados) y condiciones de reglas de flujo de correo en Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Acciones de las reglas de flujo de correo en Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- La lista de palabras y patrones de texto que se usan para identificar el correo masivo en los ejemplos no es exhaustivo; puede Agregar y quitar las entradas que considere necesario. Sin embargo, son un buen punto de partida.

- La búsqueda de palabras o patrones de texto en el asunto u otros campos del encabezado del mensaje ocurre *después* de que el mensaje se haya decodificado desde el método de codificación de transferencia de contenido MIME que se usó para transmitir el mensaje binario entre los servidores SMTP en texto ASCII. No puede usar condiciones ni excepciones para buscar los valores codificados sin formato (normalmente, Base64) del asunto o de otros campos del encabezado del mensaje.

- Los siguientes procedimientos marcan un mensaje masivo como correo no deseado para toda la organización. Sin embargo, puede agregar otra condición para aplicar estas reglas solo a destinatarios específicos, de modo que pueda usar un filtrado agresivo en algunos usuarios muy dirigidos, mientras que el resto de los usuarios (que obtienen el correo electrónico en masa en el que se suscribiron) no se ven afectados.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Usar el EAC para crear reglas de flujo de correo que filtren el correo electrónico masivo

1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.

2. Haga **Add** ![clic en agregar](../../media/ITPro-EAC-AddIcon.png) icono Agregar y, a continuación, seleccione **crear una nueva regla**.

3. En la ventana **Nueva regla** que se abre, configure las siguientes opciones:

   - **Name**: escriba un nombre único y descriptivo para la regla.

   - Haga clic en **Más opciones**.

   - **Aplicar esta regla si**: configure una de las siguientes opciones para buscar contenido en los mensajes mediante expresiones regulares (regex) o palabras o frases:

     - **El asunto o el** \> **cuerpo o el asunto del cuerpo coinciden con estos patrones de texto**: en el cuadro de diálogo **especificar palabras o frases** que aparece, escriba uno de](../../media/ITPro-EAC-AddIcon.png)los siguientes valores, haga clic en **Agregar** ![icono y repita el procedimiento hasta que haya introducido todos los valores.

       - `If you are unable to view the content of this email\, please`

       - `\>(safe )?unsubscribe( here)?\</a\>`

       - `If you do not wish to receive further communications like this\, please`

       - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`

       - `To stop receiving these+emails\:http\://`

       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`

       - `no longer (wish )?(to )?(be sent|receive) w+ email`

       - `If you are unable to view the content of this email\, please click here`

       - `To ensure you receive (your daily deals|our e-?mails)\, add`

       - `If you no longer wish to receive these emails`

       - `to change your (subscription preferences|preferences or unsubscribe)`

       - `click (here to|the) unsubscribe`

      Para editar una entrada, selecciónela y haga clic en **Editar** ![icono](../../media/ITPro-EAC-EditIcon.png)de edición. Para quitar una entrada, selecciónela y haga clic en **quitar** ![icono](../../media/ITPro-EAC-DeleteIcon.png)quitar.

       Cuando haya terminado, haga clic en **Aceptar**.

     - **El asunto o** \> el asunto o el cuerpo del mensaje **incluye alguna de estas palabras**: en el cuadro de diálogo **especificar palabras o frases** que aparece, escriba uno de los siguientes valores](../../media/ITPro-EAC-AddIcon.png), haga clic en **Agregar** ![icono y repita el procedimiento hasta que haya introducido todos los valores.

       - `to change your preferences or unsubscribe`

       - `Modify email preferences or unsubscribe`

       - `This is a promotional email`

       - `You are receiving this email because you requested a subscription`

       - `click here to unsubscribe`

       - `You have received this email because you are subscribed`

       - `If you no longer wish to receive our email newsletter`

       - `to unsubscribe from this newsletter`

       - `If you have trouble viewing this email`

       - `This is an advertisement`

       - `you would like to unsubscribe or change your`

       - `view this email as a webpage`

       - `You are receiving this email because you are subscribed`

      Para editar una entrada, selecciónela y haga clic en **Editar** ![icono](../../media/ITPro-EAC-EditIcon.png)de edición. Para quitar una entrada, selecciónela y haga clic en **quitar** ![icono](../../media/ITPro-EAC-DeleteIcon.png)quitar.

       Cuando haya terminado, haga clic en **Aceptar**.

   - **Haga lo siguiente**: seleccione **modificar las propiedades** \> del mensaje **establecer el nivel de confianza contra correo no deseado (SCL)**. En el cuadro de diálogo **especificar SCL** que aparece, configure una de las siguientes opciones:

     - Para marcar los mensajes como **correo no deseado**, selecciona **6**. La acción que ha configurado para los veredictos de filtrado de **correo no deseado** en las directivas contra correo no deseado se aplica a los mensajes (el valor predeterminado es **mover mensaje a la carpeta de correo electrónico no deseado**).

     - Para marcar mensajes como **correo no deseado de alta confianza** , seleccione **9**. La acción que ha configurado para los veredictos de filtrado de **correo no deseado de confianza alta** en las directivas contra correo no deseado se aplica a los mensajes (el valor predeterminado es **mover mensaje a la carpeta correo electrónico no deseado**).

    Para obtener más información acerca de los valores de SCL, vea [nivel de confianza contra correo no deseado (SCL) en Office 365](spam-confidence-levels.md).

   Cuando haya terminado, haga clic en **Guardar** .

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>Usar PowerShell para crear reglas de flujo de correo que filtren el correo electrónico masivo

Use la siguiente sintaxis para crear una o ambas reglas de flujo de correo (expresiones regulares frente a palabras):

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

En este ejemplo se crea una nueva regla denominada "Bulk Email Filtering-RegEx" que usa la misma lista de expresiones regulares de la sección anterior en el tema para establecer mensajes como **correo no deseado**.

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

En este ejemplo se crea una nueva regla denominada "Bulk Email Filtering-Words" que usa la misma lista de palabras descritas anteriormente en el tema para establecer los mensajes como **correo no deseado de confianza alta**.

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Para comprobar que ha configurado reglas de flujo de correo para filtrar el correo masivo, siga estos pasos:

- En el EAC, vaya a **Mail flow** \> **reglas** \> de flujo de correo Seleccione \> la regla haga clic](../../media/ITPro-EAC-EditIcon.png)en **Editar** ![icono de edición y Compruebe la configuración.

- En PowerShell, reemplace \<el nombre\> de la regla por el nombre de la regla y ejecute el siguiente comando para comprobar la configuración:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Desde una cuenta externa, envíe mensajes de prueba a un destinatario afectado que contenga una de las frases o patrones de texto y compruebe los resultados.
