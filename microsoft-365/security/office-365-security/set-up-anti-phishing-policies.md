---
title: Directivas de protección contra phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las directivas contra la suplantación de identidad que están disponibles en Exchange Online Protection (EOP) y Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9abed7f9601872eeb14ceb294c54a1cb54f63c2f
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229112"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Directivas contra la suplantación de identidad en Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Las directivas para configurar las opciones de protección contra suplantación de identidad están disponibles en organizaciones de Microsoft 365 con buzones de Exchange Online, organizaciones independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online y Microsoft Defender para Office 365 organizaciones.

Algunos ejemplos de Microsoft Defender para Office 365 organizaciones incluyen:

- Microsoft 365 Enterprise E5, Microsoft 365 Educación A5, etc.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Empresa](https://www.microsoft.com/microsoft-365/business)
- [Microsoft Defender para Office 365 como complemento](https://products.office.com/exchange/advance-threat-protection)

Las diferencias de alto nivel entre las directivas contra suplantación de identidad (phishing) en EOP y las directivas contra suplantación de identidad en Defender para Office 365 se describen en la tabla siguiente:

<br>

****

|Característica|Directivas contra suplantación de identidad en EOP|Directivas contra la suplantación de identidad en Defender para Office 365|
|---|:---:|:---:|
|Directiva predeterminada creada automáticamente|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|Crear directivas personalizadas|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|Configuración de directiva común<sup>\*</sup>|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|Configuración de suplantación|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|Primer contacto consejo de seguridad|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|Configuración de suplantación||![Marca de verificación](../../media/checkmark.png)|
|Umbrales de suplantación de identidad avanzada||![Marca de verificación](../../media/checkmark.png)|
|

<sup>\*</sup> En la directiva predeterminada, el nombre de la directiva y la descripción son de solo lectura (la descripción está en blanco) y no puede especificar a quién se aplica la directiva (la directiva predeterminada se aplica a todos los destinatarios).

Para configurar directivas contra suplantación de identidad, consulte los artículos siguientes:

- [Configuración de directivas contra phishing en EOP](configure-anti-phishing-policies-eop.md)
- [Configurar directivas contra suplantación de identidad en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md)

El resto de este artículo describe la configuración disponible en las directivas contra suplantación de identidad en EOP y Defender para Office 365.

## <a name="common-policy-settings"></a>Configuración de directiva común

La siguiente configuración de directiva está disponible en las directivas contra suplantación de identidad en EOP y Defender para Office 365:

- **Nombre:** no puede cambiar el nombre de la directiva contra suplantación de identidad predeterminada. Después de crear una directiva contra suplantación de identidad personalizada, no puede cambiar el nombre de la directiva en el portal de Microsoft 365 Defender suplantación de identidad.

- **Descripción** No puede agregar una descripción a la directiva contra suplantación de identidad predeterminada, pero puede agregar y cambiar la descripción de las directivas personalizadas que cree.

- **Usuarios, grupos y dominios:** identifica los destinatarios internos a los que se aplica la directiva contra suplantación de identidad. Este valor es necesario en las directivas personalizadas y no está disponible en la directiva predeterminada (la directiva predeterminada se aplica a todos los destinatarios).

  Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

  - **Usuarios:** uno o más buzones, usuarios de correo o contactos de correo de la organización.
  - **Grupos:** uno o más grupos de la organización.
  - **Dominios:** uno o varios de los dominios [aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) configurados en Microsoft 365.

  - **Excluir estos usuarios, grupos y dominios:** excepciones para la directiva. La configuración y el comportamiento son exactamente iguales a las condiciones:
    - **Usuarios**
    - **Grupos**
    - **Dominios**

  > [!NOTE]
  > Al menos una selección en la configuración **usuarios,** grupos y dominios es necesaria en las directivas **personalizadas** contra la suplantación de identidad para identificar los destinatarios de mensajes a los que se aplica <u>la directiva</u>. Las directivas contra suplantación de identidad [](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) en Defender para Office 365 también tienen una configuración <u></u> de suplantación en la que puede especificar direcciones de correo electrónico de remitente individuales o dominios de remitente que recibirán protección contra suplantación, tal como se describe más adelante en este artículo.

## <a name="spoof-settings"></a>Configuración de suplantación

La suplantación de identidad es cuando la dirección De de un mensaje de correo electrónico (la dirección del remitente que se muestra en los clientes de correo electrónico) no coincide con el dominio del origen de correo electrónico. Para obtener más información acerca de la suplantación, vea Protección contra la suplantación [en Microsoft 365](anti-spoofing-protection.md).

La siguiente configuración de suplantación de identidad está disponible en las directivas contra suplantación de identidad en EOP y Defender para Office 365:

- **Habilitar la inteligencia de suplantación:** activa o desactiva la inteligencia de suplantación. Le recomendamos que lo deje activado.

  Cuando la inteligencia de suplantación de identidad está habilitada, la información de inteligencia suplantada muestra remitentes suplantados que se detectaron y permitieron o bloquearon automáticamente mediante la inteligencia de suplantación de identidad.  Puede invalidar manualmente el veredicto de suplantación de identidad para permitir o bloquear los remitentes suplantados detectados desde dentro de la información. Pero, cuando lo hace, el remitente suplantado desaparece de la información de  inteligencia suplantada y ahora solo está visible en la pestaña Suplantación de identidad de la lista de permitidos o bloqueados del espacio empresarial. También puede crear manualmente entradas de permitir o bloquear para remitentes suplantados en la lista de inquilinos permitidos o bloqueados. Para más información, consulte los siguientes artículos:

  - [Suplantación de información de inteligencia en EOP](learn-about-spoof-intelligence.md)
  - [Administrar la lista de inquilinos permitidos o bloqueados en EOP](tenant-allow-block-list.md)

  > [!NOTE]
  >
  > - La protección contra la suplantación de identidad está habilitada de forma predeterminada en la directiva contra suplantación de identidad predeterminada y en cualquier nueva directiva contra suplantación de identidad personalizada que cree.
  > - No es necesario deshabilitar la protección contra la suplantación si el registro MX no apunta a Microsoft 365; habilitar el filtrado mejorado para conectores en su lugar. Para obtener instrucciones, consulte [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).
  > - Deshabilitar la protección contra la suplantación solo deshabilita la protección de suplantación implícita de las comprobaciones de [autenticación](email-validation-and-authentication.md#composite-authentication) compuesta.  Si el remitente produce un error _en las_ comprobaciones [de DMARC](use-dmarc-to-validate-email.md) explícitas en las que la directiva está establecida en cuarentena o rechazada, el mensaje sigue en cuarentena o rechazado.

- **Notificaciones de remitente no autenticadas:** estas notificaciones solo están disponibles cuando la inteligencia de suplantación de identidad está activada. Vea la información en la sección siguiente.
- **Acciones:** para los mensajes de remitentes suplantados bloqueados (bloqueados automáticamente por la inteligencia de suplantación de identidad o bloqueados manualmente en la lista Permitir/Bloquear inquilino), también puede especificar la acción que debe realizar en los mensajes:
  - **Mover mensajes a las carpetas de correo no** deseado de los destinatarios: este es el valor predeterminado. El mensaje se entrega en el buzón y se mueve a la carpeta Correo no deseado. En Exchange Online, el mensaje se mueve a la carpeta Correo no deseado si la regla de correo no deseado está habilitada en el buzón (está habilitada de forma predeterminada). Para obtener más información, vea [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).
  - **Poner en cuarentena el mensaje:** envía el mensaje a la cuarentena en lugar de los destinatarios previstos. Para obtener información acerca de la cuarentena, vea los artículos siguientes:
    - [Cuarentena en Microsoft 365](quarantine-email-messages.md)
    - [Administrar mensajes y archivos en cuarentena como administrador en Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Buscar y liberar mensajes en cuarentena como usuario en Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

### <a name="unauthenticated-sender"></a>Remitente no autenticado

Las notificaciones de remitente no autenticados [](#spoof-settings) forman parte de la configuración de suplantación de identidad que están disponibles en las directivas contra suplantación de identidad en EOP y Defender para Office 365 como se describe en la sección anterior. La siguiente configuración solo está disponible cuando la inteligencia de suplantación está activada:

- **Mostrar (?)** para remitentes no autenticados para suplantación de identidad: Esta notificación agrega un signo de interrogación se agrega a  la foto del remitente en el cuadro De si el mensaje no pasa comprobaciones SPF o DKIM y el mensaje no pasa dmarc o autenticación compuesta [.](email-validation-and-authentication.md#composite-authentication) Cuando esta configuración está desactivada, el signo de interrogación no se agrega a la foto del remitente.

- **Mostrar etiqueta "via":** esta notificación agrega la etiqueta via (chris@contoso.com a través de <u>fabrikam.com)</u> en el cuadro De si el dominio de la dirección De (el remitente del mensaje que se muestra en los clientes de correo electrónico) es diferente del dominio de la firma DKIM o la dirección **MAIL FROM.** Para obtener más información acerca de estas direcciones, vea [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).

Para evitar que el signo de interrogación o la etiqueta a través de la etiqueta se agregó a los mensajes de remitentes específicos, tiene las siguientes opciones:

- Permitir al remitente suplantado [](learn-about-spoof-intelligence.md) en la información de inteligencia suplantada o manualmente en la lista de [inquilinos permitidos o bloqueados.](tenant-allow-block-list.md) Permitir que el remitente suplantado impida que la etiqueta via aparezca en los mensajes del remitente cuando la identificación del remitente no autenticada esté deshabilitada.
- [Configurar la autenticación de](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) correo electrónico para el dominio del remitente.
  - Para el signo de interrogación de la foto del remitente, SPF o DKIM son los más importantes.
  - Para la etiqueta via, confirme que el dominio de la firma DKIM o la dirección **MAIL FROM** coincide (o es un subdominio de) el dominio en la dirección De.

Para obtener más información, vea [Identificar mensajes sospechosos en Outlook.com y Outlook en la Web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="first-contact-safety-tip"></a>Primer contacto consejo de seguridad

La configuración mostrar el primer contacto **consejo de seguridad** está disponible en EOP y Defender para organizaciones Office 365 y no depende de la configuración de la inteligencia de suplantación o la protección de suplantación. La consejo de seguridad se muestra a los destinatarios en los siguientes escenarios:

- La primera vez que obtienen un mensaje de un remitente
- A menudo no obtienen mensajes del remitente.

![Primer contacto consejo de seguridad para los mensajes con un destinatario.](../../media/safety-tip-first-contact-one-recipient.png)

![Primer contacto consejo de seguridad para los mensajes con varios destinatarios.](../../media/safety-tip-first-contact-multiple-recipients.png)

Esta funcionalidad agrega una capa adicional de protección de seguridad contra posibles ataques de suplantación, por lo que se recomienda activarla.

El primer consejo de seguridad de contacto también reemplaza la necesidad de crear reglas de flujo de correo (también conocidas como reglas de transporte) que agreguen el encabezado denominado **X-MS-Exchange-EnableFirstContactSafetyTip** con el valor **Enable** to messages (aunque esta funcionalidad aún está disponible).

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración exclusiva en directivas contra suplantación de identidad en Microsoft Defender para Office 365

En esta sección se describe la configuración de directiva que solo está disponible en las directivas contra suplantación de identidad en Defender para Office 365.

> [!NOTE]
> La directiva contra suplantación de identidad predeterminada [](set-up-anti-phishing-policies.md#spoof-settings) en Defender for Office 365 proporciona protección contra suplantación de identidad e inteligencia de buzones para todos los destinatarios. Sin embargo, las otras [características](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) de protección de suplantación disponibles y la configuración avanzada [no](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) están configuradas ni habilitadas en la directiva predeterminada. Para habilitar todas las características de protección, modifique la directiva contra suplantación de identidad predeterminada o cree directivas adicionales contra la suplantación de identidad.

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración de suplantación en directivas contra suplantación de identidad en Microsoft Defender para Office 365

La suplantación es donde el remitente o el dominio de correo electrónico del remitente en un mensaje tiene un aspecto similar al de un remitente o dominio real:

- Un ejemplo de suplantación del dominio contoso.com es ćóntoso.com.
- Un ejemplo de suplantación del usuario michelle@contoso.com es michele@contoso.com.

Un dominio suplantado podría considerarse legítimo (dominio registrado, registros de autenticación de correo electrónico configurados, etc.), salvo que su intención sea engañar a los destinatarios.

La siguiente configuración de suplantación solo está disponible en las directivas contra suplantación de identidad en Defender para Office 365:

- **Permitir a los usuarios proteger:** evita que las direcciones de correo electrónico internas o externas especificadas se suplanten **como remitentes de mensajes**. Por ejemplo, recibe un mensaje de correo electrónico del vicepresidente de su empresa pidiéndole que le envíe información interna de la compañía. ¿Lo haría? Muchas personas enviarían la respuesta sin pensarlo.

  Puede usar usuarios protegidos para agregar direcciones de correo electrónico de remitente internos y externos para protegerse de la suplantación. Esta lista de **remitentes** protegidos contra la suplantación  de usuario es diferente de la lista de destinatarios a los que se aplica la directiva (todos los destinatarios de la directiva predeterminada; destinatarios específicos configurados en la configuración **Usuarios,** grupos y dominios de la sección Configuración de directiva común). [](#common-policy-settings)

  > [!NOTE]
  >
  > - En cada directiva contra phishing, puede especificar un máximo de 350 usuarios protegidos (direcciones de correo electrónico del remitente). No puede especificar el mismo usuario protegido en varias directivas. Por lo tanto, independientemente de cuántas directivas se aplican a un destinatario, el número máximo de usuarios protegidos (direcciones de correo electrónico del remitente) para cada destinatario individual es 350. Para obtener más información sobre la prioridad de la directiva y cómo se detiene el procesamiento de directivas después de aplicar la primera directiva, vea [Order and precedence of email protection](how-policies-and-protections-are-combined.md).
  > - La protección de suplantación de usuario no funciona si el remitente y el destinatario se han comunicado previamente por correo electrónico. Si el remitente y el destinatario nunca se han comunicado por correo electrónico, el mensaje se identificará como un intento de suplantación.

  De forma predeterminada, no hay direcciones de correo electrónico del remitente configuradas para la protección de suplantación **en Usuarios para proteger**. Por lo tanto, de forma predeterminada, ninguna dirección de correo electrónico del remitente está cubierta por la protección de suplantación, ya sea en la directiva predeterminada o en directivas personalizadas.

  Al agregar direcciones de correo electrónico internas o externas a la **lista Usuarios** para proteger, los mensajes de esos **remitentes** están sujetos a comprobaciones de protección de suplantación. El mensaje se comprueba para suplantación si **el** mensaje se envía **a** un destinatario al que se aplica la directiva (todos los destinatarios de la directiva predeterminada; **Usuarios, grupos y destinatarios de dominios** en directivas personalizadas). Si se detecta suplantación en la dirección de correo electrónico del remitente, las acciones de protección de suplantación para los usuarios se aplican al mensaje (qué hacer con el mensaje, si se muestran sugerencias de seguridad de usuarios suplantados, etc.).

- **Habilitar dominios para proteger:** evita que los dominios especificados se suplanten en el dominio **del remitente del mensaje**. Por ejemplo, todos los dominios que posee ([dominios](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)aceptados ) o dominios personalizados específicos (dominios que posee o dominios asociados). Esta lista de dominios de remitente que están protegidos  contra la suplantación es diferente de la lista de destinatarios a los que se aplica la [](#common-policy-settings) directiva (todos los destinatarios de la directiva predeterminada; destinatarios específicos configurados en la configuración **Usuarios,** grupos y dominios de la sección Configuración de directiva común). 

  > [!NOTE]
  > El número máximo de dominios protegidos que puede definir en todas las directivas contra suplantación de identidad es 50.

  De forma predeterminada, no hay dominios de remitente configurados para la protección de suplantación en **Habilitar dominios para proteger**. Por lo tanto, de forma predeterminada, ningún dominio de remitente está cubierto por la protección de suplantación, ya sea en la directiva predeterminada o en directivas personalizadas.

  Al agregar dominios a la lista Habilitar dominios **para** proteger, los mensajes de **los remitentes** de esos dominios están sujetos a comprobaciones de protección de suplantación. El mensaje se comprueba para suplantación si **el** mensaje se envía **a** un destinatario al que se aplica la directiva (todos los destinatarios de la directiva predeterminada; **Usuarios, grupos y destinatarios de dominios** en directivas personalizadas). Si se detecta suplantación en el dominio del remitente, las acciones de protección de suplantación de dominios se aplican al mensaje (qué hacer con el mensaje, si se muestran sugerencias de seguridad de usuarios suplantados, etc.).

- **Acciones:** elija la acción que se debe realizar en los mensajes entrantes que contienen intentos de suplantación contra los usuarios protegidos y los dominios protegidos de la directiva. Puede especificar diferentes acciones para la suplantación de usuarios protegidos frente a la suplantación de dominios protegidos:
  - **No aplicar ninguna acción**
  - **Redirigir el mensaje a otras direcciones de correo** electrónico: envía el mensaje a los destinatarios especificados en lugar de a los destinatarios previstos.
  - **Mover mensajes a las carpetas** de correo no deseado de los destinatarios: el mensaje se entrega en el buzón y se mueve a la carpeta correo no deseado. En Exchange Online, el mensaje se mueve a la carpeta Correo no deseado si la regla de correo no deseado está habilitada en el buzón (está habilitada de forma predeterminada). Para obtener más información, vea [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).
  - **Poner en cuarentena el mensaje:** envía el mensaje a la cuarentena en lugar de los destinatarios previstos. Para obtener información acerca de la cuarentena, vea los artículos siguientes:
    - [Cuarentena en Microsoft 365](quarantine-email-messages.md)
    - [Administrar mensajes y archivos en cuarentena como administrador en Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Buscar y liberar mensajes en cuarentena como usuario en Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)
  - Entregue el mensaje y agregue otras direcciones a la línea **CCO:** entregue el mensaje a los destinatarios previstos y entregue el mensaje de forma silenciosa a los destinatarios especificados.
  - **Elimine el mensaje antes de entregarlo:** elimina silenciosamente todo el mensaje, incluidos todos los datos adjuntos.

- **Sugerencias de seguridad de** suplantación: Active o desactive las siguientes sugerencias de seguridad de suplantación que aparecerán en los mensajes que no puedan comprobar la suplantación:
  - **Mostrar sugerencia para usuarios suplantados:** la dirección De contiene **un permiso para que los usuarios protejan al** usuario. Solo está disponible si **Habilitar usuarios para proteger** está activado y configurado.
  - **Mostrar sugerencia para dominios suplantados:** la dirección De contiene **un habilitar dominios para proteger el** dominio. Solo está disponible si **Habilitar dominios para proteger** está activado y configurado.
  - **Mostrar sugerencia** para caracteres inusuales: la dirección De contiene conjuntos de caracteres inusuales (por ejemplo,  símbolos matemáticos y  texto o una combinación de letras mayúsculas y minúsculas) en un permitir a los usuarios proteger al remitente o habilitar dominios para proteger el dominio del remitente.  Solo está disponible si **Habilitar a los usuarios para proteger** _o_ **Habilitar dominios** para proteger está activado y configurado.

- **Habilitar la inteligencia de** buzones: habilita o deshabilita la inteligencia artificial (IA) que determina los patrones de correo electrónico del usuario con sus contactos frecuentes. Esta configuración ayuda a la IA a distinguir entre mensajes de remitentes legítimos y suplantados.

  Por ejemplo, Gabriela Laureano (glaureano@contoso.com) es la ceo de su empresa, por lo que la agrega como remitente protegida en **permitir** que los usuarios protejan la configuración de la directiva. Sin embargo, algunos de los destinatarios que la directiva aplica para comunicarse regularmente con un proveedor que también se llama Gabriela Laureano (glaureano@fabrikam.com). Dado que esos destinatarios tienen un historial de comunicación con glaureano@fabrikam.com, la inteligencia de buzones de correo no identificará los mensajes de glaureano@fabrikam.com como un intento de suplantación de glaureano@contoso.com para esos destinatarios.

  Para usar contactos frecuentes aprendidos por la inteligencia de buzones (y su falta) para ayudar a proteger a los usuarios de ataques de suplantación, puede activar **Habilitar** la protección de suplantación de inteligencia después de activar Habilitar inteligencia de buzones. 

- **Habilitar la protección de suplantación** de inteligencia: active esta configuración para especificar la acción que se debe realizar en los mensajes para las detecciones de suplantación de los resultados de inteligencia de buzones:
  - **No aplicar ninguna acción:** tenga en cuenta que este  valor tiene el mismo resultado que activar la inteligencia de buzones pero desactivar Habilitar protección de **suplantación de inteligencia**.
  - **Redirigir el mensaje a otras direcciones de correo electrónico**
  - **Mover el mensaje a las carpetas de correo no deseado de los destinatarios**
  - **Poner en cuarentena el mensaje**
  - **Entregar el mensaje y agregar otras direcciones a la línea CCO**
  - **Eliminar el mensaje antes de entregarlo**

- **Agregar remitentes y dominios de confianza:** excepciones a la configuración de protección de suplantación. Los mensajes de los remitentes y dominios de remitente especificados nunca se clasifican como ataques basados en suplantación por la directiva. En otras palabras, la acción para remitentes protegidos, dominios protegidos o protección de inteligencia de buzones de correo no se aplica a estos remitentes o dominios de remitente de confianza. El límite máximo de estas listas es de aproximadamente 1000 entradas.

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Umbrales de suplantación de identidad avanzados en directivas contra suplantación de identidad en Microsoft Defender para Office 365

Los siguientes umbrales avanzados de suplantación de identidad solo están disponibles en las directivas contra suplantación de identidad en Defender para Office 365. Estos umbrales controlan la confidencialidad para aplicar modelos de aprendizaje automático a los mensajes para determinar un veredicto de phishing:

- **1 - Estándar:** este es el valor predeterminado. La gravedad de la acción que se toma en el mensaje depende del grado de confianza que el mensaje es la suplantación de identidad (confianza baja, mediana, alta o muy alta). Por ejemplo, los mensajes identificados como phishing con un grado de confianza muy alto tienen las acciones más graves aplicadas, mientras que los mensajes que se identifican como phishing con un bajo grado de confianza tienen acciones menos graves aplicadas.
- **2 - Agresivo:** los mensajes que se identifican como suplantación de identidad con un alto grado de confianza se tratan como si se identificaron con un grado de confianza muy alto.
- **3 - Más** agresivo: los mensajes que se identifican como suplantación de identidad con un grado de confianza medio o alto se tratan como si se identificaron con un grado de confianza muy alto.
- **4 - Más** agresivo: los mensajes que se identifican como suplantación de identidad con un grado de confianza bajo, medio o alto se tratan como si se identificaron con un grado de confianza muy alto.

La probabilidad de falsos positivos (mensajes buenos marcados como negativos) aumenta a medida que aumenta esta configuración. Para obtener información sobre la configuración recomendada, vea la directiva [contra la suplantación](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)de identidad en Microsoft Defender para obtener Office 365 configuración.
