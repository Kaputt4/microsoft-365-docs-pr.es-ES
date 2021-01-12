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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las directivas contra la suplantación de identidad que están disponibles en Exchange Online Protection (EOP) y Microsoft Defender para Office 365.
ms.openlocfilehash: dadb41e1f0ff9e18681b13ad3d265f3f436c2052
ms.sourcegitcommit: f40378013757d560d5566a11ad4e6f527c018cc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49796199"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Directivas contra la suplantación de identidad en Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Las directivas para configurar la protección contra suplantación de identidad están disponibles en organizaciones de Microsoft 365 con buzones de Exchange Online, organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online y Microsoft Defender para organizaciones de Office 365.

Las directivas contra suplantación de identidad en Microsoft Defender para Office 365 solo están disponibles en las organizaciones que tienen Defender para Office 365. Por ejemplo:

- Microsoft 365 Enterprise E5, Microsoft 365 Educación A5, etc.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Empresa](https://www.microsoft.com/microsoft-365/business)
- [Microsoft Defender para Office 365 como complemento](https://products.office.com/exchange/advance-threat-protection)

Las diferencias de alto nivel entre las directivas contra suplantación de identidad en EOP y las directivas contra suplantación de identidad en Microsoft Defender para Office 365 se describen en la tabla siguiente:

****

|Característica|Directivas contra la suplantación de identidad en EOP|Directivas contra la suplantación de identidad en Microsoft Defender para Office 365|
|---|:---:|:---:|
|Directiva predeterminada creada automáticamente|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|Crear directivas personalizadas|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|Configuración de directiva<sup>\*</sup>|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|Configuración de suplantación||![Marca de verificación](../../media/checkmark.png)|
|Configuración de suplantación de seguridad|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|Umbrales avanzados de suplantación de identidad||![Marca de verificación](../../media/checkmark.png)|
|

<sup>\*</sup> En la directiva predeterminada, el nombre y la descripción de la directiva son de solo lectura (la descripción está en blanco) y no se puede especificar a quién se aplica la directiva (la directiva predeterminada se aplica a todos los destinatarios).

Para configurar directivas contra la suplantación de identidad, consulte los artículos siguientes:

- [Configuración de directivas contra phishing en EOP](configure-anti-phishing-policies-eop.md)

- [Configurar directivas contra la suplantación de identidad en Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md)

El resto de este artículo describe la configuración que está disponible en las directivas contra suplantación de identidad en EOP y Defender para Office 365.

## <a name="policy-settings"></a>Configuración de directivas

La siguiente configuración de directiva está disponible en las directivas contra suplantación de identidad en EOP y Microsoft Defender para Office 365:

- **Nombre:** no puede cambiar el nombre de la directiva contra suplantación de identidad predeterminada, pero puede nombrar y cambiar el nombre de las directivas personalizadas que cree.

- **Descripción** No puede agregar una descripción a la directiva contra suplantación de identidad predeterminada, pero puede agregar y cambiar la descripción de las directivas personalizadas que cree.

- **Se aplica** a: identifica los destinatarios internos a los que se aplica la directiva contra suplantación de identidad. Este valor es necesario en las directivas personalizadas y no está disponible en la directiva predeterminada (la directiva predeterminada se aplica a todos los destinatarios).

  Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

  - **El destinatario es:** uno o más buzones de correo, usuarios de correo o contactos de correo de su organización.
  - **El destinatario es miembro de**: Uno o más grupos de la organización.
  - **El dominio del destinatario es:** uno o varios de los dominios aceptados configurados en Microsoft 365.

  - **Excepto cuando**: Excepciones para la regla. La configuración y el comportamiento son exactamente iguales a las condiciones:

    - **El destinatario es**
    - **El destinatario es un miembro de**
    - **El dominio del destinatario es**

  > [!NOTE]
  > La **configuración Aplicada a** es necesaria en las directivas contra suplantación de identidad **personalizadas** para identificar los destinatarios de mensajes a los que <u>se aplica la directiva.</u> Las directivas contra suplantación de identidad en [](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Microsoft Defender para Office 365 también <u></u> tienen una configuración de suplantación en la que puede especificar direcciones de correo electrónico de remitente individuales o dominios de remitente que recibirán protección contra suplantación, tal como se describe más adelante en este artículo.

## <a name="spoof-settings"></a>Configuración de suplantación de seguridad

La suplantación de identidad se da cuando la dirección De de un mensaje de correo electrónico (la dirección del remitente que se muestra en los clientes de correo electrónico) no coincide con el dominio del origen de correo electrónico. Para obtener más información acerca de la suplantación de documentos, vea Protección contra la suplantación de documentos [en Microsoft 365.](anti-spoofing-protection.md)

La siguiente configuración de suplantación de identidad está disponible en las directivas contra suplantación de identidad en EOP y Microsoft Defender para Office 365:

- **Protección contra la suplantación:** habilita o deshabilita la protección contra la suplantación. Le recomendamos que lo deje habilitado. La directiva **de inteligencia de suplantación** de identidad se usa para permitir o bloquear remitentes internos y externos suplantados específicos. Para obtener más información, consulte [Configuración de inteligencia contra la suplantación de identidad en Microsoft 365 ](learn-about-spoof-intelligence.md).

  > [!NOTE]
  >
  > - La protección contra la suplantación de identidad está habilitada de forma predeterminada en la directiva contra suplantación de identidad predeterminada y en cualquier nueva directiva contra suplantación de identidad personalizada que cree.
  >
  > - No es necesario deshabilitar la protección contra la suplantación si el registro MX no apunta a Microsoft 365; En su lugar, habilite el filtrado mejorado para conectores. Para obtener instrucciones, consulte [Filtrado mejorado para conectores en Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).
  >
  > - Deshabilitar la protección contra la suplantación solo deshabilita la protección de suplantación implícita de las comprobaciones de [autenticación](email-validation-and-authentication.md#composite-authentication) compuesta. Si el remitente no supera las comprobaciones [de DMARC](use-dmarc-to-validate-email.md) explícitas en las que la directiva está establecida en cuarentena o rechazada, el mensaje se sigue cuarentenando o rechazando.

  Para los mensajes de remitentes suplantados bloqueados, también puede especificar la acción que se debe realizar en los mensajes:

  - **Mover el mensaje a la carpeta correo no deseado:** este es el valor predeterminado. El mensaje se entrega en el buzón y se mueve a la carpeta correo no deseado. En Exchange Online, el mensaje se mueve a la carpeta correo no deseado si la regla de correo no deseado está habilitada en el buzón (está habilitada de forma predeterminada). Para obtener más información, vea [Configurar las opciones de correo no deseado en buzones de Exchange Online en Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

  - **Poner en cuarentena el mensaje:** envía el mensaje a cuarentena en lugar de los destinatarios previstos. Para obtener información acerca de la cuarentena, vea los artículos siguientes:

    - [Cuarentena en Microsoft 365](quarantine-email-messages.md)
    - [Administrar mensajes y archivos en cuarentena como administrador en Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Buscar y liberar mensajes en cuarentena como un usuario en Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

- **Remitente no autenticado:** vea la información en la sección siguiente.

### <a name="unauthenticated-sender"></a>Remitente no autenticado

La identificación de remitentes no [](#spoof-settings) autenticados forma parte de la configuración de suplantación de identidad que está disponible en las directivas contra suplantación de identidad en EOP y Microsoft Defender para Office 365, como se describe en la sección anterior.

La **configuración Remitente no autenticado** habilita o deshabilita la identificación de remitentes no autenticados en Outlook. En particular:

- Se agrega un signo de interrogación (?) a la foto del remitente  si el mensaje no supera las comprobaciones SPF o DKIM y el mensaje no pasa la autenticación compuesta o DMARC. [](email-validation-and-authentication.md#composite-authentication) Si se deshabilita la identificación de remitentes no autenticados, se impide que el signo de interrogación se agrega a la foto del remitente.

- La etiqueta via (chris@contoso.com <u>a</u> través de fabrikam.com) se agrega si el dominio de la dirección De (el remitente del mensaje que se muestra en los clientes de correo electrónico) es diferente del dominio de la firma DKIM o la dirección **MAIL FROM.** Para obtener más información acerca de estas direcciones, consulte [Información general sobre los estándares de mensajes de correo electrónico.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

  Deshabilitar la identificación del remitente no autenticado no impide que se agregó la etiqueta via si el dominio de la dirección De es diferente del dominio de la firma DKIM o la dirección MAIL FROM.

Para evitar que el signo de interrogación o la etiqueta se agregó a mensajes de remitentes específicos, tiene las siguientes opciones:

- Permitir que el remitente suplante la identidad en la directiva de inteligencia de suplantación de identidad. Esta acción impedirá que la etiqueta via aparezca en los mensajes del remitente cuando la identificación del remitente no autenticado esté deshabilitada. Para obtener instrucciones, [consulte Configurar la inteligencia de suplantación de seguridad en Microsoft 365.](learn-about-spoof-intelligence.md)

- [Configure la autenticación de](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) correo electrónico para el dominio del remitente.
  - Para el signo de interrogación de la foto del remitente, SPF o DKIM son los más importantes.
  - Para la etiqueta via, confirme que el dominio de la firma DKIM o la dirección **MAIL FROM** coincida (o es un subdominio) del dominio en la dirección De.

Para obtener más información, vea [Identificar mensajes sospechosos en Outlook.com y Outlook en la Web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración exclusiva en directivas contra suplantación de identidad en Microsoft Defender para Office 365

En esta sección se describe la configuración de directiva que solo está disponible en las directivas contra suplantación de identidad en Microsoft Defender para Office 365.

> [!NOTE]
> La directiva contra suplantación de identidad predeterminada en [](set-up-anti-phishing-policies.md#spoof-settings) Microsoft Defender para Office 365 proporciona protección contra la suplantación de identidad e inteligencia de buzones para todos los destinatarios. Sin embargo, las otras características de [protección](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) de suplantación disponibles y la configuración avanzada [no](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) están configuradas ni habilitadas en la directiva predeterminada. Para habilitar todas las características de protección, modifique la directiva contra suplantación de identidad predeterminada o cree directivas adicionales contra la suplantación de identidad.

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración de suplantación en directivas contra suplantación de identidad en Microsoft Defender para Office 365

La suplantación es donde el remitente o el dominio de correo electrónico del remitente en un mensaje es similar a un remitente o dominio real:

- Un ejemplo de suplantación del dominio contoso.com es ćóntoso.com.
- Un ejemplo de suplantación del usuario michelle@contoso.com es michele@contoso.com.

Un dominio suplantado podría considerarse legítimo (dominio registrado, registros de autenticación de correo electrónico configurados, etc.), salvo que su intención sea engañar a los destinatarios.

La siguiente configuración de suplantación solo está disponible en las directivas contra suplantación de identidad en Microsoft Defender para Office 365:

- **Usuarios para proteger:** impide que las direcciones de correo electrónico internas o externas especificadas se suplante **como remitentes de mensajes.** Por ejemplo, recibe un mensaje de correo electrónico del vicepresidente de su empresa en el que se le pide que le envíe información interna de la compañía. ¿Lo haría? Muchas personas enviarían la respuesta sin pensarlo.

  Puede usar usuarios protegidos para agregar direcciones de correo electrónico de remitentes internos y externos para protegerse de la suplantación. Esta lista de **remitentes** que están protegidos contra la suplantación de usuario es diferente de la lista de destinatarios a  los que se [](#policy-settings) aplica la directiva (todos los destinatarios de la directiva predeterminada; destinatarios específicos configurados en la opción Aplicado a en la sección Configuración de directiva). 

  > [!NOTE]
  >
  > - En cada directiva contra la suplantación de identidad, puede especificar un máximo de 60 usuarios protegidos (direcciones de correo electrónico del remitente). No puede especificar el mismo usuario protegido en varias directivas.
  >
  > - La protección de suplantación de usuario no funciona si el remitente y el destinatario se han comunicado previamente por correo electrónico. Si el remitente y el destinatario nunca se han comunicado por correo electrónico, el mensaje se identificará como un intento de suplantación.

  De forma predeterminada, no hay direcciones de correo electrónico del remitente configuradas para la protección de suplantación en **usuarios para proteger**. Por lo tanto, de forma predeterminada, ninguna dirección de correo electrónico del remitente está cubierta por la protección de suplantación, ya sea en la directiva predeterminada o en las directivas personalizadas.

  Al agregar direcciones de correo  electrónico internas o externas a los usuarios para proteger la lista, los mensajes de esos **remitentes** están sujetos a comprobaciones de protección de suplantación. Se comprueba la suplantación del mensaje si se envía **a** un destinatario al que se aplica la directiva (todos los destinatarios de la directiva predeterminada;  **Se aplica a** los destinatarios en directivas personalizadas). Si se detecta la suplantación en la dirección de correo electrónico del remitente, las acciones de protección de suplantación para los usuarios se aplican al mensaje (qué hacer con el mensaje, si mostrar sugerencias de seguridad de usuarios suplantados, etc.).

- **Dominios para proteger:** impide que los dominios especificados se suplante en el dominio **del remitente del mensaje.** Por ejemplo, todos los dominios que posee[(dominios](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)aceptados) o dominios específicos (dominios que posee o dominios asociados). Esta lista  de dominios de remitente que están protegidos contra la suplantación es diferente de la lista de destinatarios a los que se [](#policy-settings) aplica la directiva (todos los destinatarios de la directiva predeterminada; destinatarios específicos configurados en la opción Aplicada a en la sección Configuración de directiva).  

  > [!NOTE]
  > El número máximo de dominios protegidos que puede definir en todas las directivas contra la suplantación de identidad es 50.

  De forma predeterminada, no hay dominios de remitente configurados para la protección de suplantación en **Dominios para proteger**. Por lo tanto, de forma predeterminada, no hay dominios de remitente cubiertos por la protección de suplantación, ya sea en la directiva predeterminada o en directivas personalizadas.

  Al agregar dominios a la lista **Dominios** para protegerlos, los mensajes de los **remitentes** de esos dominios están sujetos a comprobaciones de protección de suplantación. Se comprueba la suplantación del mensaje si se envía **a** un destinatario al que se aplica la directiva (todos los destinatarios de la directiva predeterminada;  **Se aplica a** los destinatarios en directivas personalizadas). Si se detecta la suplantación en el dominio del remitente, las acciones de protección de suplantación para dominios se aplican al mensaje (qué hacer con el mensaje, si mostrar sugerencias de seguridad de usuarios suplantados, etc.).

- **Acciones para usuarios o** dominios protegidos: elija la acción que se llevará a cabo en los mensajes entrantes que contengan intentos de suplantación contra los usuarios protegidos y los dominios protegidos de la directiva. Puede especificar diferentes acciones para la suplantación de usuarios protegidos frente a la suplantación de dominios protegidos:

  - **No aplicar ninguna acción**

  - **Redirigir el mensaje a otras direcciones de correo** electrónico: envía el mensaje a los destinatarios especificados en lugar de a los destinatarios previstos.

  - **Mover el mensaje a la carpeta correo no** deseado: el mensaje se entrega en el buzón y se mueve a la carpeta correo no deseado. En Exchange Online, el mensaje se mueve a la carpeta correo no deseado si la regla de correo no deseado está habilitada en el buzón (está habilitada de forma predeterminada). Para obtener más información, vea [Configurar las opciones de correo no deseado en buzones de Exchange Online en Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

    - **Poner en cuarentena el mensaje:** envía el mensaje a cuarentena en lugar de los destinatarios previstos. Para obtener información acerca de la cuarentena, vea los artículos siguientes:

    - [Cuarentena en Microsoft 365](quarantine-email-messages.md)
    - [Administrar mensajes y archivos en cuarentena como administrador en Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Buscar y liberar mensajes en cuarentena como un usuario en Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - Entregar el mensaje y agregar otras direcciones a la línea **CCO:** entregar el mensaje a los destinatarios previstos y entregar el mensaje de forma silenciosa a los destinatarios especificados.

  - **Elimine el mensaje antes de entregarlo:** elimina silenciosamente todo el mensaje, incluidos todos los datos adjuntos.

- **Sugerencias de** seguridad: habilita o deshabilita las siguientes sugerencias de seguridad de suplantación que aparecerán en mensajes que no cumplen las comprobaciones de suplantación:

  - **Usuarios suplantados:** la dirección De contiene un usuario protegido.
  - **Dominios suplantados:** la dirección De contiene un dominio protegido.
  - **Caracteres inusuales:** la dirección De contiene juegos de caracteres inusuales (por ejemplo, símbolos matemáticos y texto o una combinación de letras mayúsculas y minúsculas) en un remitente o dominio protegido.

  > [!IMPORTANT]
  >
  > Incluso cuando las sugerencias de seguridad de suplantación están desactivadas, se recomienda usar una regla de flujo de correo (también conocida como  regla de transporte) para agregar un encabezado de mensaje denominado **X-MS-Exchange-EnableFirstContactSafetyTip** con valor habilitado para los mensajes.  Una sugerencia de seguridad notificará a los destinatarios la primera vez que reciban un mensaje del remitente o si no suelen recibir mensajes del remitente.
  > :::image type="content" source="../../media/safety-tip-first-contact-multiple-recipients.png" alt-text="Texto de la sugerencia de seguridad para la protección de suplantación con varios destinatarios.":::

- **Inteligencia de buzones:** habilita o deshabilita la inteligencia artificial (IA) que determina los patrones de correo electrónico del usuario con sus contactos frecuentes. Esta configuración ayuda a la IA a distinguir entre el correo electrónico legítimo y el correo electrónico suplantado de esos contactos. La inteligencia de buzones solo está disponible para los buzones de Exchange Online.

- **Protección de suplantación** basada en inteligencia de buzones: habilita o deshabilita los resultados de suplantación mejorados en función del mapa de remitentes individual de cada usuario. Esta inteligencia permite a Microsoft 365 personalizar la detección de suplantación de usuario y controlar mejor los falsos positivos. Cuando se detecta la suplantación de usuario, puede definir una acción específica para realizar en el mensaje:

  - **No aplicar ninguna acción**
  - **Redirigir el mensaje a otras direcciones de correo electrónico**
  - **Mover mensaje a la carpeta Correo no deseado**
  - **Poner en cuarentena el mensaje**
  - **Entregar el mensaje y agregar otras direcciones a la línea CCO**
  - **Eliminar el mensaje antes de entregarlo**

- **Remitentes y dominios de** confianza: excepciones a la configuración de protección de suplantación. La directiva nunca clasifica los mensajes de los remitentes y dominios de remitente especificados como ataques basados en suplantación. En otras palabras, la acción para remitentes protegidos, dominios protegidos o protección de inteligencia de buzones de correo no se aplica a estos remitentes de confianza o dominios de remitente. El límite máximo para estas listas es de aproximadamente 1000 entradas.

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Umbrales avanzados de suplantación de identidad en directivas contra suplantación de identidad en Microsoft Defender para Office 365

Los siguientes umbrales avanzados de suplantación de identidad solo están disponibles en las directivas contra suplantación de identidad en Microsoft Defender para Office 365. Estos umbrales controlan la sensibilidad para aplicar modelos de aprendizaje automático a los mensajes para determinar un veredicto de suplantación de identidad:

- **1 - Estándar:** este es el valor predeterminado. La gravedad de la acción que se toma en el mensaje depende del grado de confianza que el mensaje es suplantación de identidad (confianza baja, media, alta o muy alta). Por ejemplo, los mensajes identificados como suplantación de identidad con un grado de confianza muy alto tienen aplicadas las acciones más graves, mientras que los mensajes identificados como suplantación de identidad con un bajo grado de confianza tienen acciones menos graves aplicadas.

- **2 - Agresivo:** los mensajes identificados como suplantación de identidad con un alto grado de confianza se tratan como si se identificaron con un grado de confianza muy alto.

- **3 - Más** agresivo: los mensajes identificados como suplantación de identidad con un grado de confianza medio o alto se tratan como si se identificaron con un grado de confianza muy alto.

- **4 -** Más agresivo: los mensajes identificados como suplantación de identidad con un grado de confianza bajo, medio o alto se tratan como si se identificaron con un grado de confianza muy alto.

La posibilidad de falsos positivos (mensajes buenos marcados como falsos) aumenta a medida que aumenta esta configuración. Para obtener información sobre la configuración recomendada, vea la directiva contra suplantación de identidad en Microsoft Defender para la configuración [de Office 365.](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)
