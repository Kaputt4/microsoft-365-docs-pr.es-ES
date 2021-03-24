---
title: Usar reglas de flujo de correo para filtrar correo masivo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a usar reglas de flujo de correo (reglas de transporte) para identificar y filtrar el correo masivo (correo gris) en Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c86f229d6c7371854878a67937cc38374ed00961
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069888"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>Usar reglas de flujo de correo para filtrar correo electrónico masivo en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP usa directivas contra correo no deseado (también conocidas como directivas de filtro de correo no deseado o directivas de filtro de contenido) para examinar mensajes entrantes en busca de correo no deseado y correo masivo (también conocido como correo gris). Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).

Si desea más opciones para filtrar el correo masivo, puede crear reglas de flujo de correo (también conocidas como reglas de transporte) para buscar patrones de texto o frases que se encuentran con frecuencia en el correo masivo y marcar esos mensajes como correo no deseado. Para obtener más información acerca del correo masivo, vea ¿Cuál es la diferencia entre el correo no deseado y el correo [masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md) y Nivel de queja masiva [(BCL) en EOP](bulk-complaint-level-values.md).

En este tema se explica cómo crear estas reglas de flujo de correo en el Centro de administración de Exchange (EAC) y PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Debe tener asignados permisos en Exchange Online o Exchange Online Protection antes de poder realizar los procedimientos descritos en este artículo. En concreto, necesita el rol **Reglas** de transporte, que se asigna a los grupos de roles **Administración** de la **organización,** Administración de cumplimiento (administradores globales) y Administración **de** registros de forma predeterminada.

  Para obtener más información, consulte los siguientes temas:

  - [Permisos de Exchange Online](/exchange/permissions-exo/permissions-exo)
  - [Permisos en EOP independiente](feature-permissions-in-eop.md)
  - [Usar el EAC modificar la lista de miembros en grupos de roles](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Para abrir el EAC en Exchange Online, vea [Centro de administración de Exchange en Exchange Online](/Exchange/exchange-admin-center). Para abrir el EAC en EOP independiente, vea Centro de [administración de Exchange en EOP independiente.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Para obtener más información acerca de las reglas de flujo de correo en Exchange Online y EOP independiente, consulte los temas siguientes:

  - [Reglas de flujo de correo (reglas de transporte) en Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Condiciones y excepciones de reglas de flujo de correo (predicados) en Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Acciones de regla de flujo de correo en Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- La lista de palabras y patrones de texto que se usan para identificar el correo masivo en los ejemplos no son exhaustivas; puede agregar y quitar entradas según sea necesario. Sin embargo, son un buen punto de partida.

- La búsqueda de palabras o patrones de texto en el asunto u otros campos del encabezado del mensaje ocurre *después* de que el mensaje se haya decodificado desde el método de codificación de transferencia de contenido MIME que se usó para transmitir el mensaje binario entre los servidores SMTP en texto ASCII. No puede usar condiciones ni excepciones para buscar los valores codificados sin formato (normalmente, Base64) del asunto o de otros campos del encabezado del mensaje.

- Los siguientes procedimientos marcan un mensaje masivo como correo no deseado para toda la organización. Sin embargo, puede agregar otra condición para aplicar estas reglas solo a destinatarios específicos, por lo que puede usar el filtrado agresivo en unos pocos usuarios altamente dirigidos, mientras que el resto de los usuarios (que en su mayoría reciben el correo electrónico masivo con el que se han registrado) no se ve afectado.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Usar el EAC para crear reglas de flujo de correo que filtran correo masivo

1. En el EAC, vaya a **Flujo de correo** \> **Reglas**.

2. Haga **clic en** Agregar icono Agregar ![ ](../../media/ITPro-EAC-AddIcon.png) **y, a continuación, seleccione Crear una nueva regla.**

3. En la ventana **Nueva regla** que se abre, configure las siguientes opciones:

   - **Nombre:** escriba un nombre descriptivo único para la regla.

   - Haga clic en **Más opciones**.

   - **Aplique esta regla si:** configure una de las siguientes opciones para buscar contenido en mensajes con expresiones regulares (RegEx) o palabras o frases:

     - **El asunto o el cuerpo** \> **asunto o cuerpo** coincide con estos  patrones de texto: en el cuadro de diálogo Especificar palabras o frases que aparece, escriba uno de los siguientes valores, haga clic en **Agregar** icono y repita hasta que haya escrito todos los ![ ](../../media/ITPro-EAC-AddIcon.png) valores.

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      Para editar una entrada, selecciónelo y haga clic **en Editar** icono ![ Editar ](../../media/ITPro-EAC-EditIcon.png) . Para quitar una entrada, selecciónelo y haga clic **en Quitar** icono ![ Quitar ](../../media/ITPro-EAC-DeleteIcon.png) .

       Cuando haya terminado, haga clic en **Aceptar**.

     - **El asunto o el cuerpo** \> **asunto o cuerpo** incluye cualquiera de  estas palabras: en el cuadro de diálogo Especificar  palabras o frases que aparece, escriba uno de los siguientes valores, haga clic en Agregar icono y repita hasta que haya escrito todos los ![ ](../../media/ITPro-EAC-AddIcon.png) valores.

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

      Para editar una entrada, selecciónelo y haga clic **en Editar** icono ![ Editar ](../../media/ITPro-EAC-EditIcon.png) . Para quitar una entrada, selecciónelo y haga clic **en Quitar** icono ![ Quitar ](../../media/ITPro-EAC-DeleteIcon.png) .

       Cuando haya terminado, haga clic en **Aceptar**.

   - **Haga lo siguiente:** Seleccione **Modificar las propiedades del mensaje** para establecer el nivel de confianza de correo no deseado \> **(SCL).** En el cuadro de diálogo Especificar **SCL** que aparece, configure una de las siguientes opciones:

     - Para marcar los mensajes **como correo no** deseado, seleccione **6**. La acción que ha  configurado para los veredictos de filtrado de correo no deseado en las directivas contra correo no deseado se aplica a los mensajes (el valor predeterminado es Mover mensaje a la carpeta **correo no deseado**).

     - Para marcar los mensajes como **correo no deseado de confianza alta,** seleccione **9**. La acción que ha configurado para los veredictos de filtrado de **correo** no deseado de elevada confianza en las directivas contra correo no deseado se aplica a los mensajes (el valor predeterminado es Mover mensaje a la carpeta correo **no deseado**).

    Para obtener más información acerca de los valores de SCL, vea Nivel de confianza de [correo no deseado (SCL) en EOP](spam-confidence-levels.md).

   Cuando haya terminado, haga clic en **Guardar**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>Usar PowerShell para crear reglas de flujo de correo que filtran el correo electrónico masivo

Use la sintaxis siguiente para crear una o ambas reglas de flujo de correo (expresiones regulares frente a palabras):

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

En este ejemplo se crea una nueva regla denominada "Filtrado masivo de correo electrónico - RegEx" que usa la misma lista de expresiones regulares de anteriormente en el tema para establecer mensajes como **Correo no deseado**.

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

En este ejemplo se crea una nueva regla denominada "Filtrado masivo de correo electrónico: palabras" que usa la misma lista de palabras de anteriormente en el tema para establecer mensajes como correo no deseado **de elevada confianza.**

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Para obtener información detallada acerca de la sintaxis y los parámetros, vea [New-TransportRule](/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Para comprobar que ha configurado reglas de flujo de correo para filtrar correo masivo, siga estos pasos:

- En el EAC, vaya a **Flujo** de correo Reglas seleccione la regla haga clic en \>  \> \> **Editar** icono Editar y compruebe ![ la ](../../media/ITPro-EAC-EditIcon.png) configuración.

- En PowerShell, reemplace por el nombre de la regla y \<Rule Name\> ejecute el siguiente comando para comprobar la configuración:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Desde una cuenta externa, envíe un mensaje de prueba a un destinatario afectado que contenga una de las frases o patrones de texto y compruebe los resultados.