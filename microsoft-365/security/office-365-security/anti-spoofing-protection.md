---
title: Protección contra la suplantación de identidad
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- m365-security
- Strat_O365_IP
- m365initiative-defender-office365
- EngageScoreSep2022
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
ms.localizationpriority: high
description: Los administradores pueden obtener más información sobre las características contra la suplantación de identidad disponibles en Exchange Online Protection (EOP), que pueden ayudar a reducir los ataques de suplantación de identidad de los remitentes y dominios falsos.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 2ad4ab1bb3a3cdd4eb4cd05f4fefc0deedb326b1
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68069191"
---
# <a name="anti-spoofing-protection-in-eop"></a>Protección contra la suplantación de identidad en EOP

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones de correo de Exchange Online o las organizaciones independientes de Exchange Online Protection (EOP) que no tienen buzones de Exchange Online, EOP incluye características para ayudarle a proteger su organización frente a remitentes falsificados.

Cuando se trata de proteger a sus usuarios, Microsoft se toma muy en serio las amenazas de suplantación de identidad. La suplantación es una técnica común usada por atacantes. **Los mensajes falsificados parecen provenir de una persona o un lugar distinto a la fuente real**. Esta técnica se usa a menudo en campañas de suplantación de identidad (phishing), diseñadas para obtener credenciales de usuarios. La tecnología contra la suplantación de identidad en EOP examina específicamente la posible falsificación del encabezado De en el cuerpo del mensaje (que se usa para mostrar el remitente del mensaje en los clientes de correo electrónico). Cuando EOP confía mucho en que el encabezado De es falso, el mensaje se identifica como falso.

Las siguientes tecnologías contra la suplantación de identidad están disponibles en EOP:

- **Autenticación de correo electrónico**: una parte integral de cualquier esfuerzo contra la suplantación de identidad es el uso de la autenticación de correo electrónico (también conocida como validación de correo electrónico) por registros de DMARC, DKIM y DMARC en DNS. Puede configurar estos registros para sus dominios, de modo que los sistemas de correo electrónico de destino puedan comprobar la validez de los mensajes que requieran que se envíen a los remitentes de su dominio. Para los mensajes entrantes, Microsoft 365 requiere la autenticación de correo electrónico para los dominios de remitente. Para obtener más información, consulte [Autenticación de correo electrónico de Microsoft 365](email-validation-and-authentication.md).

  EOP analiza y bloquea los mensajes que no se pueden autenticar con la combinación de métodos de autenticación de correo electrónico estándar y técnicas de reputación del remitente.

  :::image type="content" source="../../media/eop-anti-spoofing-protection.png" alt-text="Comprobaciones contra la suplantación de identidad de EOP" lightbox="../../media/eop-anti-spoofing-protection.png":::

- **Spoof intelligence insight**: Review spoofed messages from senders in internal and external domains during the last 7 days, and allow or block those senders. For more information, see [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md).

- **Permitir o bloquear remitentes suplantados en la lista de permitidos o bloqueados** de inquilinos: al invalidar el veredicto en la información de inteligencia de suplantación de identidad, el remitente suplantado se convierte en una entrada manual de permitir o bloquear que solo aparece en la pestaña **Remitentes suplantados de la lista de permitidos o bloqueados de inquilinos** . También puede crear entradas de permitidos o bloqueados manualmente para remitentes de suplantación de identidad antes de que la inteligencia contra la suplantación de identidad los detecte. Para obtener más información, consulte [Administrar la lista de permitidos y bloqueados del espacio empresarial en EOP](manage-tenant-allow-block-list.md).

- **Directivas contra el phishing**: En EOP y Microsoft Defender para Office 365, las directivas contra el phishing contienen las siguientes opciones de configuración contra suplantación de identidad:
  - Activar o desactivar la inteligencia contra la suplantación de identidad.
  - Activar o desactivar los indicadores de remitente no autentificado en Outlook.
  - Especificar la acción para los remitentes bloqueados a los que se les ha suplantado la identidad.

  Para obtener más información, consulte [Configuración de suplantación de identidad en las directivas contra phishing](set-up-anti-phishing-policies.md#spoof-settings).

  **Nota**: Las directivas contra phishing en Microsoft Defender para Office 365 contienen protecciones de adición, lo que incluye protección frente a la **suplantación**. Para obtener más información, consulte [Configuración exclusiva en directivas contra phishing en Microsoft Defender para Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

- **Informe de detección de suplantación de identidad**: Para obtener más información, consulte el [Informe de detección de suplantación de identidad](view-email-security-reports.md#spoof-detections-report).

  **Note**: Defender for Office 365 organizations can also use Real-time detections (Plan 1) or Threat Explorer (Plan 2) to view information about phishing attempts. For more information, see [Microsoft 365 threat investigation and response](office-365-ti.md).

## <a name="how-spoofing-is-used-in-phishing-attacks"></a>Uso de la suplantación de identidad (spoofing) en ataques de phishing

Los mensajes de suplantación de identidad tienen estas implicaciones negativas para los usuarios:

- **Los mensajes falsificados engañan a los usuarios**: un mensaje falsificado puede engañar al destinatario para que haga clic en un vínculo y proporcione sus credenciales, descargue malware o responda a un mensaje con contenido confidencial (conocido como Business Email Compromise: compromiso de correo electrónico empresarial o BEC).

  Por ejemplo, el siguiente es un ejemplo de suplantación de identidad que usa el remitente falsificado msoutlook94@service.outlook.com:

  ![Mensaje de suplantación de identidad que suplanta service.outlook.com.](../../media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)

  Este mensaje no proviene de service.outlook.com, pero el atacante ha falsificado el campo de encabezado **De** para que parezca que es así. Este era un intento de engañar al destinatario para que hiciese clic en el vínculo **cambiar la contraseña** y proporcionase sus credenciales.

  El siguiente mensaje es un ejemplo de BEC que usa el dominio de correo electrónico falsificado contoso.com:

  ![Mensaje de suplantación de identidad: compromiso de correo electrónico empresarial.](../../media/da15adaa-708b-4e73-8165-482fc9182090.jpg)

  El mensaje parece legítimo, pero el remitente es falso.

- **Los usuarios confunden mensajes reales con falsos**: incluso los usuarios que sepan acerca de la suplantación de identidad podrían tener dificultades para ver las diferencias entre los mensajes reales y los mensajes falsificados.

  El siguiente mensaje es un ejemplo de un mensaje de restablecimiento de contraseña real desde la cuenta de Microsoft Security:

  ![Restablecimiento de contraseña legítimo de Microsoft.](../../media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)

  The message really did come from Microsoft, but users have been conditioned to be suspicious. Because it's difficult to the difference between a real password reset message and a fake one, users might ignore the message, report it as spam, or unnecessarily report the message to Microsoft as phishing.

## <a name="different-types-of-spoofing"></a>Distintos tipos de suplantación

Microsoft distingue entre dos tipos de mensajes falsificados:

- **Intra-org spoofing**: Also known as _self-to-self_ spoofing. For example:

  - El remitente y el destinatario están en el mismo dominio:
    > De: jose@contoso.com <br> Para: carla@contoso.com

  - El remitente y el destinatario están en subdominios del mismo dominio:
    > De: laura@marketing.fabrikam.com <br> Para: julia@engineering.fabrikam.com

  - El remitente y el destinatario están en dominios diferentes que pertenecen a la misma organización (es decir, los dos dominios están configurados como [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) en la misma organización):
    > De: remitente @ microsoft.com <br> Para: destinatario @ bing.com

    Los espacios se usan en las direcciones de correo electrónico para evitar la recolección de bots de correo no deseado.

  Los mensajes que producen un error de [autenticación compuesta](email-validation-and-authentication.md#composite-authentication) debido a la suplantación de identidad dentro de la organización contienen los siguientes valores en los encabezados:

  `Authentication-Results: ... compauth=fail reason=6xx`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.11`

  - `reason=6xx` indica suplantación de identidad dentro de la organización.

  - SFTY es el nivel de seguridad del mensaje. 9 indica suplantación de identidad (phishing), .11 indica suplantación dentro de la organización.

- **Suplantación entre dominios**: los dominios del remitente y el destinatario son distintos, y no tienen ninguna relación entre sí (también conocidos como dominios externos). Por ejemplo:
    > De: jose@contoso.com <br> Para: carla@tailspintoys.com

  Los mensajes que producen un error de [autenticación compuesta](email-validation-and-authentication.md#composite-authentication) debido a la suplantación de identidad entre dominios contienen los siguientes valores en los encabezados:

  `Authentication-Results: ... compauth=fail reason=000/001`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22`

  - `reason=000` indica que el mensaje falló en la autentificación explícita del correo electrónico. `reason=001` indica que el mensaje ha producido un error de autenticación de correo electrónico implícita.

  - `SFTY` es el nivel de seguridad del mensaje. 9 indica suplantación de identidad (phishing), .22 indica suplantación entre dominios.

> [!NOTE]
> If you've gotten a message like ***compauth=fail reason=###** _ and need to know about composite authentication (compauth), and the values related to spoofing, see [_Anti-spam message headers in Microsoft 365*](anti-spam-message-headers.md). Or go directly to the [*reason*](anti-spam-message-headers.md) codes.

Para obtener más información acerca de la configuración de DMARC, consulte [Usar DMARC para comprobar el correo electrónico en Microsoft 365](use-dmarc-to-validate-email.md).

## <a name="problems-with-anti-spoofing-protection"></a>Problemas con la protección contra la suplantación de identidad

Se sabe que las listas de correo (también conocidas como listas de discusión) tienen problemas con la protección contra la suplantación debido a la forma en que reenvían y modifican mensajes.

Por ejemplo, Gabriela Laureano (glaureano@contoso.com) está interesada en la observación de aves, se une a la lista de correo observadoresdeaves@fabrikam.com y envía el siguiente mensaje a la lista:.

> **De:** "Gabriela Laureano" \<glaureano@contoso.com\> <br> **Para:** Lista de discusión de observadores de aves \<birdwatchers@fabrikam.com\> <br> **Subject:** Great viewing of blue jays at the top of Mt. Rainier this week <p> ¿Alguien quiere echar un vistazo a la vista de esta semana desde el Monte Rainier?

El servidor de la lista de distribución de correo recibe el mensaje, modifica su contenido y lo reproduce para los miembros de la lista. El mensaje reproducido tiene la misma dirección De: (glaureano@contoso.com), pero se han agregado una etiqueta en la línea de asunto y un pie de página en la parte inferior del mensaje. Este tipo de modificación es común en las listas de distribución de correo y puede producir falsos positivos de suplantación de identidad.

> **De:** "Gabriela Laureano" \<glaureano@contoso.com\> <br> **Para:** Lista de discusión de observadores de aves \<birdwatchers@fabrikam.com\> <br> **Subject:** [BIRDWATCHERS] Great viewing of blue jays at the top of Mt. Rainier this week <p> ¿Alguien quiere echar un vistazo a la vista de esta semana desde el Monte Rainier? <p> Este mensaje se envió a la lista de discusión de observadores de aves. Puede cancelar la suscripción en cualquier momento.

Para ayudar a que los mensajes de la lista de distribución de correo pasen las comprobaciones contra la suplantación, siga los pasos siguientes en función de si controla la lista de distribución de correo:

- La organización es propietaria de la lista de distribución de correo:

  - Consulte las preguntas más frecuentes en DMARC.org: [Manejo una lista de distribución de correo y quiero interactúan con DMARC, ¿qué debo hacer?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)

  - Lea las instrucciones en esta entrada de blog: [Una sugerencia para los operadores de la lista de distribución de correo para interactuar con DMARC sin errores](/archive/blogs/tzink/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures).

  - Considere instalar las actualizaciones en el servidor de la lista de distribución de correo para admitir ARC, vea <http://arc-spec.org>.

- La organización no es propietaria de la lista de distribución de correo:

  - Pida al encargado de la lista de distribución de correo que configure la autenticación de correo electrónico para el dominio desde el que se reenvía la lista de distribución de correo.

    Cuando hay suficientes remitentes que responden a los propietarios de dominios pidiéndoles que configuren los registros de autenticación de correo electrónico, es más probable que tomen medidas. Aunque Microsoft también trabaja con los propietarios de dominios para publicar los registros necesarios, es aún más efectivo cuando los usuarios individuales lo solicitan.

  - Cree reglas de buzón en el cliente de correo para mover mensajes a la Bandeja de entrada. También puede pedir a sus administradores que configuren reemplazos tal y como se describe en [Información de la inteligencia contra la suplantación de identidad en EOP](learn-about-spoof-intelligence.md) y [Administrar la lista de permitidos o bloqueados del espacio empresarial](manage-tenant-allow-block-list.md).

  - Use la lista de Permitir/Bloquear inquilinos para invalidar que la lista de distribución de correo la trate como legítima. Para obtener más información, consulte [Creación de entradas permitidas para remitentes suplantados](allow-block-email-spoof.md#create-allow-entries-for-spoofed-senders).

Si todos los demás falla, puede notificar el mensaje como falso positivo a Microsoft. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="considerations-for-anti-spoofing-protection"></a>Consideraciones para la protección contra la suplantación de identidad

Si es un administrador que actualmente envía mensajes a Microsoft 365, debe asegurarse de que el correo electrónico se haya autenticado correctamente. En caso contrario, es posible que se marque como correo no deseado o phishing. Para obtener más información, consulte [Soluciones para remitentes legítimos que envían correo electrónico sin autenticar](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email).

Senders in an individual user's (or admin's) Safe Senders list will bypass parts of the filtering stack, including spoof protection. For more information, see [Outlook Safe Senders](create-safe-sender-lists-in-office-365.md#use-outlook-safe-senders).

Los administradores deben evitar (siempre que sea posible) el uso de listas de remitentes permitidos o de dominios permitidos. Estos remitentes omiten toda la protección contra correo no deseado, suplantación electrónica, protección contra phishing y autenticación de remitente (SPF, DKIM, DMARC). Para más información, consulte [Usar listas de remitentes permitidos o listas de dominios permitidos](create-safe-sender-lists-in-office-365.md#use-allowed-sender-lists-or-allowed-domain-lists).
