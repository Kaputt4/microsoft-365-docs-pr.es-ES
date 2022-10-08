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
ms.localizationpriority: medium
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- m365-security
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las directivas contra phishing que están disponibles en Exchange Online Protection (EOP) y Microsoft Defender para Office 365.
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: 1c49e13e6942de8947b69e2bcb236cbe5ba6b493
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68072357"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Directivas contra suplantación de identidad en Microsoft 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Las directivas para configurar la protección contra suplantación de identidad (phishing) están disponibles en organizaciones de Microsoft 365 con buzones de Exchange Online, organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online y Microsoft Defender para Office 365 organizaciones.

Algunos ejemplos de organizaciones Microsoft Defender para Office 365 son:

- Microsoft 365 Enterprise E5, Microsoft 365 Educación A5, etc.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Empresa](https://www.microsoft.com/microsoft-365/business)
- [Microsoft Defender para Office 365 como complemento](https://products.office.com/exchange/advance-threat-protection)

En la tabla siguiente se describen las diferencias de alto nivel entre las directivas contra suplantación de identidad en EOP y las directivas contra suplantación de identidad en Defender para Office 365:

|Característica|Directivas contra suplantación de identidad en EOP|Directivas contra suplantación de identidad en Defender para Office 365|
|---|:---:|:---:|
|Directiva predeterminada creada automáticamente|![Marca de verificación.](../../media/checkmark.png)|![Marca de verificación.](../../media/checkmark.png)|
|Crear directivas personalizadas|![Marca de verificación.](../../media/checkmark.png)|![Marca de verificación.](../../media/checkmark.png)|
|Configuración de directiva común<sup>\*</sup>|![Marca de verificación.](../../media/checkmark.png)|![Marca de verificación.](../../media/checkmark.png)|
|Configuración de suplantación de identidad|![Marca de verificación.](../../media/checkmark.png)|![Marca de verificación.](../../media/checkmark.png)|
|Primer consejo de seguridad de contacto|![Marca de verificación.](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|Configuración de suplantación||![Marca de verificación](../../media/checkmark.png)|
|Umbrales avanzados de phishing||![Marca de verificación](../../media/checkmark.png)|

<sup>\*</sup> En la directiva predeterminada, el nombre de la directiva y la descripción son de solo lectura (la descripción está en blanco) y no se puede especificar a quién se aplica la directiva (la directiva predeterminada se aplica a todos los destinatarios).

Para configurar directivas contra phishing, consulte los artículos siguientes:

- [Configuración de directivas contra phishing en EOP](configure-anti-phishing-policies-eop.md)
- [Configuración de directivas contra phishing en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md)

En el resto de este artículo se describen los valores que están disponibles en las directivas contra la suplantación de identidad en EOP y Defender para Office 365.

## <a name="common-policy-settings"></a>Configuración de directiva común

La siguiente configuración de directiva está disponible en las directivas contra suplantación de identidad en EOP y Defender para Office 365:

- **Nombre**: no se puede cambiar el nombre de la directiva de anti phishing predeterminada. Después de crear una directiva de anti phishing personalizada, no puede cambiar el nombre de la directiva en el portal de Microsoft 365 Defender.

- **Descripción** No puede agregar una descripción a la directiva de anti phishing predeterminada, pero puede agregar y cambiar la descripción de las directivas personalizadas que cree.

- **Usuarios, grupos y dominios**: identifica los destinatarios internos a los que se aplica la directiva anti phishing. Este valor es necesario en las directivas personalizadas y no está disponible en la directiva predeterminada (la directiva predeterminada se aplica a todos los destinatarios).

  Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

  - **Usuarios**: uno o varios buzones de correo, usuarios de correo o contactos de correo de su organización.
  - **Grupos**: uno o varios grupos de la organización.
  - **Dominios**: uno o varios de los [dominios aceptados configurados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) en Microsoft 365.

  - **Excluir estos usuarios, grupos y dominios**: excepciones para la directiva. La configuración y el comportamiento son exactamente similares a las condiciones:
    - **Usuarios**
    - **Grupos**
    - **Dominios**

  > [!NOTE]
  > Se requiere al menos una selección en la configuración **usuarios, grupos y dominios** en las directivas de anti-phishing personalizadas para identificar los destinatarios del mensaje a **los** <u>que se aplica la directiva</u>. Las directivas contra suplantación de identidad en Defender para Office 365 también tienen [una configuración de suplantación](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) en la que puede especificar direcciones de correo electrónico de remitente individuales o dominios de remitente <u>que recibirán protección de suplantación</u>, como se describe más adelante en este artículo.
  >
  > Los diferentes tipos de condiciones o excepciones no son aditivos; son inclusivos. La directiva se aplica _solo_ a los destinatarios que coinciden con _todos_ los filtros de destinatarios especificados. Por ejemplo, se configura una condición de filtro de destinatario en la directiva con los siguientes valores:
  >
  > - Usuarios: romain@contoso.com
  > - Grupos: Ejecutivos
  >
  > La directiva se aplica a romain@contoso.com _solo_ si también es miembro del grupo de Ejecutivos. Si no es miembro del grupo, la directiva no se le aplica.
  >
  > Asimismo, si utiliza el mismo filtro de destinatarios como excepción a la directiva, esta no se aplica a romain@contoso.com _solo_ si también es miembro del grupo de Ejecutivos. Si no es miembro del grupo, la directiva se le sigue aplicando.

## <a name="spoof-settings"></a>Configuración de suplantación de identidad

La suplantación es cuando la dirección De en un mensaje de correo electrónico (la dirección del remitente que se muestra en los clientes de correo electrónico) no coincide con el dominio del origen de correo electrónico. Para obtener más información sobre la suplantación de identidad, consulte [Protección contra la suplantación de identidad en Microsoft 365](anti-spoofing-protection.md).

La siguiente configuración de suplantación de identidad está disponible en las directivas contra suplantación de identidad en EOP y Defender para Office 365:

- **Habilitar inteligencia suplantada**: activa o desactiva la inteligencia de suplantación de identidad. Se recomienda que lo deje activado.

  Cuando se habilita la inteligencia de suplantación de identidad, la **información de inteligencia sobre** suplantación de identidad muestra remitentes suplantados que se detectaron y permitieron o bloquearon automáticamente mediante inteligencia suplantada. Puede invalidar manualmente el veredicto de inteligencia de suplantación para permitir o bloquear a los remitentes suplantados detectados desde dentro de la información. Pero cuando lo hace, el remitente suplantado desaparece de la información de inteligencia de suplantación de identidad y ahora solo está visible en la pestaña **Remitentes suplantados de la Lista de permitidos o bloqueados de inquilinos** . También puede crear manualmente entradas de permitir o bloquear para remitentes suplantados en la lista de permitidos o bloqueados de inquilinos. Para más información, consulte los siguientes artículos:

  - [Información de inteligencia sobre suplantación de identidad en EOP](learn-about-spoof-intelligence.md)
  - [Administrar la lista de inquilinos permitidos o bloqueados en EOP](manage-tenant-allow-block-list.md)

  > [!NOTE]
  >
  > - La protección contra la suplantación de identidad está habilitada de forma predeterminada en la directiva predeterminada contra suplantación de identidad (phishing) y en las nuevas directivas personalizadas contra suplantación de identidad (phishing) que cree.
  > - No es necesario deshabilitar la protección contra la suplantación de identidad si el registro MX no apunta a Microsoft 365; en su lugar, habilita el filtrado mejorado para conectores. Para obtener instrucciones, consulte [Filtrado mejorado para conectores en Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).
  > - Al deshabilitar la protección contra la suplantación de identidad solo se deshabilita la protección de suplantación _implícita_ de las comprobaciones de [autenticación compuesta](email-validation-and-authentication.md#composite-authentication) . Si el remitente produce un error en las comprobaciones [de DMARC](use-dmarc-to-validate-email.md) _explícitas_ en las que la directiva está establecida en cuarentena o rechazo, el mensaje sigue en cuarentena o se rechaza.

- **Indicadores de remitente no autenticados**: disponible en la sección **Consejos de seguridad & indicadores** solo cuando la inteligencia de suplantación de identidad está activada. Consulte los detalles de la sección siguiente.
- **Acciones**: para los mensajes de remitentes falsificados bloqueados (bloqueados automáticamente por inteligencia de suplantación de identidad o bloqueados manualmente en la lista Permitir o bloquear inquilinos), también puede especificar la acción que debe realizar en los mensajes:
  - **Mover mensajes a las carpetas de Email no deseado de los destinatarios**: este es el valor predeterminado. El mensaje se entrega al buzón y se mueve a la carpeta de Email no deseado. Para obtener más información, consulte [Configuración del correo electrónico no deseado en Exchange Online buzones de Correo en Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).
  - **Poner en cuarentena el mensaje**: envía el mensaje a la cuarentena en lugar de a los destinatarios previstos. Para más información acerca de la cuarentena, consulte los siguientes artículos:
    - [Cuarentena en Microsoft 365](quarantine-email-messages.md)
    - [Administración de mensajes y archivos en cuarentena como administrador en Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Búsqueda y liberación de mensajes en cuarentena como usuario en Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

    Si selecciona **Poner en cuarentena el mensaje**, también puede seleccionar la directiva de cuarentena que se aplica a los mensajes que se pusieron en cuarentena mediante la protección de inteligencia de suplantación de identidad. Las directivas de cuarentena definen qué pueden hacer los usuarios en los mensajes en cuarentena y si los usuarios reciben notificaciones de cuarentena. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).

### <a name="unauthenticated-sender-indicators"></a>Indicadores de remitente no autenticados

Los indicadores de remitente no autenticados forman parte de la [configuración de suplantación](#spoof-settings) de identidad que están disponibles en la sección **Consejos de seguridad & indicadores de las directivas** contra la suplantación de identidad en EOP y Defender para Office 365. La siguiente configuración solo está disponible cuando la inteligencia de suplantación de identidad está activada:

- **Mostrar (?) para remitentes no autenticados para suplantación de identidad**: agrega un signo de interrogación a la foto del remitente en el cuadro De si el mensaje no pasa comprobaciones SPF o DKIM **y** el mensaje no pasa DMARC o [autenticación compuesta](email-validation-and-authentication.md#composite-authentication). Cuando esta configuración está desactivada, el signo de interrogación no se agrega a la foto del remitente.

- **Mostrar etiqueta "via"**: agrega la etiqueta via (chris@contoso.com <u>a través</u> de fabrikam.com) en el cuadro Desde si el dominio de la dirección De (el remitente del mensaje que se muestra en los clientes de correo electrónico) es diferente del dominio de la firma DKIM o de la dirección **MAIL FROM** . Para obtener más información sobre estas direcciones, consulte [Introducción a los estándares de mensajes de correo electrónico](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).

Para evitar que el signo de interrogación o la etiqueta se agreguen a mensajes de remitentes específicos, tiene las siguientes opciones:

- Permitir al remitente suplantado en la [información de inteligencia de suplantación](learn-about-spoof-intelligence.md) o manualmente en la [lista de permitidos o bloqueados](manage-tenant-allow-block-list.md) de inquilinos. Permitir que el remitente suplantado impida que la etiqueta via aparezca en los mensajes del remitente, incluso si la opción **Mostrar etiqueta "a través"** está activada en la directiva.
- [Configure la autenticación por correo electrónico](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) para el dominio remitente.
  - Para el signo de interrogación en la foto del remitente, SPF o DKIM son los más importantes.
  - En el caso de la etiqueta via, confirme que el dominio de la firma DKIM o la dirección **MAIL FROM** coinciden (o es un subdominio de) con el dominio en la dirección From.

Para obtener más información, consulte [Identificación de mensajes sospechosos en Outlook.com y Outlook en la Web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="first-contact-safety-tip"></a>Primer consejo de seguridad de contacto

La configuración **mostrar la primera sugerencia de seguridad de contacto** está disponible en EOP y Defender para Office 365 organizaciones, y no depende de la configuración de inteligencia de suplantación o protección contra suplantación. La sugerencia de seguridad se muestra a los destinatarios en los siguientes escenarios:

- La primera vez que recibe un mensaje de un remitente
- A menudo no reciben mensajes del remitente.

:::image type="content" source="../../media/safety-tip-first-contact-one-recipient.png" alt-text="La primera sugerencia de seguridad de contactos para los mensajes con un destinatario" lightbox="../../media/safety-tip-first-contact-one-recipient.png":::

:::image type="content" source="../../media/safety-tip-first-contact-multiple-recipients.png" alt-text="La primera sugerencia de seguridad de contactos para mensajes con varios destinatarios" lightbox="../../media/safety-tip-first-contact-multiple-recipients.png":::

Esta funcionalidad agrega una capa adicional de protección de seguridad contra posibles ataques de suplantación, por lo que se recomienda activarla.

La primera sugerencia de seguridad de contactos también reemplaza la necesidad de crear reglas de flujo de correo (también conocidas como reglas de transporte) que agreguen el encabezado denominado **X-MS-Exchange-EnableFirstContactSafetyTip** con el valor **Habilitar** a los mensajes (aunque esta funcionalidad sigue estando disponible).

> [!NOTE]
> Si el mensaje tiene varios destinatarios, si se muestra la sugerencia y a quién se basa en un modelo mayoritario. Si la mayoría de los destinatarios nunca reciben o no suelen recibir mensajes del remitente, los destinatarios afectados recibirán la sugerencia **Algunas personas que recibieron este mensaje...** Si le preocupa que este comportamiento exponga los hábitos de comunicación de un destinatario a otro, no debe habilitar la primera sugerencia de seguridad de contactos y seguir usando reglas de flujo de correo en su lugar.

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración exclusiva en las directivas contra suplantación de identidad en Microsoft Defender para Office 365

En esta sección se describe la configuración de directivas que solo están disponibles en las directivas contra suplantación de identidad en Defender para Office 365.

> [!NOTE]
> La directiva predeterminada contra suplantación de identidad (phishing) en Defender para Office 365 proporciona [protección contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings) e inteligencia de buzones para todos los destinatarios. Sin embargo, las otras características de [protección de suplantación](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) disponibles y [la configuración avanzada](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) no están configuradas ni habilitadas en la directiva predeterminada. Para habilitar todas las características de protección, modifique la directiva predeterminada contra suplantación de identidad (phishing) o cree directivas adicionales contra phishing.

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configuración de suplantación en directivas contra suplantación de identidad en Microsoft Defender para Office 365

La suplantación es donde el remitente o el dominio de correo electrónico del remitente en un mensaje es similar a un remitente o dominio real:

- Un ejemplo de suplantación del dominio contoso.com es ćóntoso.com.
- La suplantación de identidad de un usuario es la combinación del nombre para mostrar y la dirección de correo electrónico del usuario. Por ejemplo, Valeria Barrios (vbarrios@contoso.com) podría suplantarse como Valeria Barrios, pero con una dirección de correo electrónico completamente diferente.

> [!NOTE]
> La protección contra suplantación busca dominios similares. Por ejemplo, si el dominio está contoso.com, se comprueban distintos dominios de nivel superior (.com, .biz, etc.) como intentos de suplantación, pero también dominios que son incluso algo similares. Por ejemplo, contosososo.com o contoabcdef.com podrían verse como intentos de suplantación de contoso.com.

Un dominio suplantado podría considerarse legítimo (dominio registrado, registros de autenticación de correo electrónico configurados, etc.), salvo que su intención sea engañar a los destinatarios.

La siguiente configuración de suplantación solo está disponible en las directivas contra suplantación de identidad en Defender para Office 365:

- **Permitir que los usuarios protejan**: impide que las direcciones de correo electrónico internas o externas especificadas se suplante **como remitentes de mensajes**. Por ejemplo, recibe un mensaje de correo electrónico del Vicepresidente de su empresa en el que le pide que le envíe información interna de la empresa. ¿Lo harías? Muchas personas enviarían la respuesta sin pensar.

  Puede usar usuarios protegidos para agregar direcciones de correo electrónico de remitente internas y externas para protegerse de la suplantación. Esta lista de **remitentes protegidos** contra la suplantación de usuario es diferente de la lista de **destinatarios a los** que se aplica la directiva (todos los destinatarios de la directiva predeterminada; destinatarios específicos tal y como se configura en la configuración **Usuarios, grupos y dominios** de la sección [Configuración de directiva común](#common-policy-settings) ).

  > [!NOTE]
  >
  > - En cada directiva contra phishing, puede especificar un máximo de 350 usuarios protegidos (direcciones de correo electrónico del remitente). No se puede especificar el mismo usuario protegido en varias directivas. Por lo tanto, independientemente del número de directivas que se aplican a un destinatario, el número máximo de usuarios protegidos (direcciones de correo electrónico del remitente) para cada destinatario individual es 350. Para obtener más información sobre la prioridad de la directiva y cómo se detiene el procesamiento de directivas después de aplicar la primera directiva, vea [Orden y prioridad de la protección por correo electrónico](how-policies-and-protections-are-combined.md).
  > - La protección de suplantación de usuario no funciona si el remitente y el destinatario se han comunicado previamente por correo electrónico. Si el remitente y el destinatario nunca se han comunicado por correo electrónico, el mensaje se identificará como un intento de suplantación.

  De forma predeterminada, no hay ninguna dirección de correo electrónico del remitente configurada para la protección de suplantación en **Usuarios que se va a proteger**. Por lo tanto, de forma predeterminada, ninguna dirección de correo electrónico del remitente está cubierta por la protección de suplantación, ya sea en la directiva predeterminada o en las directivas personalizadas.

  Al agregar direcciones de correo electrónico internas o externas a la lista **Usuarios para proteger** , los mensajes de esos **remitentes están sujetos a comprobaciones** de protección de suplantación. Se comprueba la suplantación del mensaje **si** el mensaje se envía a un **destinatario** al que se aplica la directiva (todos los destinatarios de la directiva predeterminada; **Usuarios, grupos y destinatarios de dominios** en directivas personalizadas). Si se detecta la suplantación en la dirección de correo electrónico del remitente, las acciones de protección de suplantación para los usuarios se aplican al mensaje (qué hacer con el mensaje, si mostrar sugerencias de seguridad de usuarios suplantados, etc.).

- **Habilitar dominios para proteger**: impide que los dominios especificados se suplantan **en el dominio del remitente del mensaje**. Por ejemplo, todos los dominios que posee ([dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) o dominios personalizados específicos (dominios que posee o dominios asociados). Esta lista de **dominios de remitente** que están protegidos contra la suplantación es diferente de la lista de **destinatarios a los** que se aplica la directiva (todos los destinatarios de la directiva predeterminada; destinatarios específicos configurados en la configuración **Usuarios, grupos y dominios** de la sección [Configuración de directiva común](#common-policy-settings) ).

  > [!NOTE]
  > Puede especificar un máximo de 50 dominios personalizados en cada directiva anti-phishing.

  De forma predeterminada, no hay dominios de remitente configurados para la protección de suplantación en **Habilitar dominios para proteger**. Por lo tanto, de forma predeterminada, no hay dominios de remitente cubiertos por la protección de suplantación, ya sea en la directiva predeterminada o en directivas personalizadas.

  Al agregar dominios a la lista **Habilitar dominios para proteger** , los mensajes de **los remitentes de esos dominios están sujetos** a comprobaciones de protección de suplantación. Se comprueba la suplantación del mensaje **si** el mensaje se envía a un **destinatario** al que se aplica la directiva (todos los destinatarios de la directiva predeterminada; **Usuarios, grupos y destinatarios de dominios** en directivas personalizadas). Si se detecta la suplantación en el dominio del remitente, las acciones de protección de suplantación de dominios se aplican al mensaje (qué hacer con el mensaje, si se muestran sugerencias de seguridad para los usuarios suplantados, etc.).

- **Acciones**: elija la acción que se va a realizar en los mensajes entrantes que contienen intentos de suplantación contra los usuarios protegidos y los dominios protegidos de la directiva. Puede especificar diferentes acciones para la suplantación de usuarios protegidos frente a la suplantación de dominios protegidos:
  - **No aplicar ninguna acción**
  - **Redirigir el mensaje a otras direcciones de correo electrónico**: envía el mensaje a los destinatarios especificados en lugar de a los destinatarios previstos.
  - **Mover mensajes a las carpetas de Email no deseado de los destinatarios**: el mensaje se entrega al buzón y se mueve a la carpeta de Email no deseado. Para obtener más información, consulte [Configuración del correo electrónico no deseado en Exchange Online buzones de Correo en Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).
  - **Poner en cuarentena el mensaje**: envía el mensaje a la cuarentena en lugar de a los destinatarios previstos. Para más información acerca de la cuarentena, consulte los siguientes artículos:
    - [Cuarentena en Microsoft 365](quarantine-email-messages.md)
    - [Administración de mensajes y archivos en cuarentena como administrador en Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Búsqueda y liberación de mensajes en cuarentena como usuario en Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

    Si selecciona **Poner en cuarentena el mensaje**, también puede seleccionar la directiva de cuarentena que se aplica a los mensajes que están en cuarentena por suplantación de usuario o protección de suplantación de dominio. Las directivas de cuarentena definen lo que los usuarios pueden hacer en los mensajes en cuarentena. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).

  - **Entregue el mensaje y agregue otras direcciones a la línea CCO**: entregue el mensaje a los destinatarios previstos y entregue el mensaje de forma silenciosa a los destinatarios especificados.
  - **Elimine el mensaje antes de entregarlo**: elimina de forma silenciosa todo el mensaje, incluidos todos los datos adjuntos.

- **Sugerencias de seguridad de suplantación**: active o desactive las siguientes sugerencias de seguridad de suplantación que aparecerán mensajes que no cumplan las comprobaciones de suplantación:
  - **Mostrar sugerencia para los usuarios suplantados**: la dirección De contiene una **opción Habilitar a los usuarios para proteger al** usuario. Solo está disponible si **Habilitar a los usuarios para proteger** está activado y configurado.
  - **Mostrar sugerencia para dominios suplantados**: la dirección From contiene un **elemento Enable domains to protect domain (Habilitar dominios para proteger el** dominio). Solo está disponible si **Habilitar dominios para proteger** está activado y configurado.
  - **Mostrar sugerencia para caracteres inusuales**: la dirección From contiene conjuntos de caracteres inusuales (por ejemplo, símbolos matemáticos y texto o una combinación de letras mayúsculas y minúsculas) en **un elemento Enable users to protect sender (Permitir a los usuarios proteger al** remitente) o **en Enable domains to protect sender domain (Habilitar dominios para proteger el** dominio del remitente).  Solo está disponible si **Habilitar a los usuarios para proteger** _o_ **Habilitar dominios para proteger** está activado y configurado.

- **Habilitar inteligencia de buzón de correo**: habilita o deshabilita la inteligencia artificial (IA) que determina los patrones de correo electrónico del usuario con sus contactos frecuentes. Esta configuración ayuda a la inteligencia artificial a distinguir entre mensajes de remitentes legítimos y suplantados.

  Por ejemplo, Gabriela Laureano (glaureano@contoso.com) es la directora general de su empresa, por lo que la agrega como remitente protegido en **Habilitar a los usuarios para proteger** la configuración de la directiva. Sin embargo, algunos de los destinatarios a los que se aplica la directiva se comunican regularmente con un proveedor que también se llama Gabriela Laureano (glaureano@fabrikam.com). Dado que esos destinatarios tienen un historial de comunicación con glaureano@fabrikam.com, la inteligencia del buzón de correo no identificará los mensajes de glaureano@fabrikam.com como un intento de suplantación de glaureano@contoso.com para esos destinatarios.

  Para usar contactos frecuentes aprendidos por la inteligencia del buzón de correo (y su falta) para ayudar a proteger a los usuarios frente a ataques de suplantación, puede activar **Habilitar la protección de suplantación de inteligencia** después de activar **Habilitar inteligencia de buzón de correo**.

- **Habilitar la protección de suplantación de inteligencia**: active esta configuración para especificar la acción que se va a realizar en los mensajes para las detecciones de suplantación de los resultados de inteligencia del buzón:
  - **No aplique ninguna acción**: tenga en cuenta que este valor tiene el mismo resultado que activar la **inteligencia del buzón de correo** , pero desactivar **habilitar la protección de suplantación de inteligencia**.
  - **Redirigir el mensaje a otras direcciones de correo electrónico**
  - **Mover el mensaje a las carpetas de Email no deseado de los destinatarios**
  - **Poner en cuarentena el mensaje**: si selecciona esta acción, también puede seleccionar la directiva de cuarentena que se aplica a los mensajes que están en cuarentena mediante la protección de inteligencia del buzón de correo. Las directivas de cuarentena definen qué pueden hacer los usuarios en los mensajes en cuarentena y si los usuarios reciben notificaciones de cuarentena. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).
  - **Entregar el mensaje y agregar otras direcciones a la línea CCO**
  - **Eliminar el mensaje antes de entregarlo**

- **Agregar remitentes y dominios de confianza**: excepciones a la configuración de protección de suplantación. La directiva nunca clasifica los mensajes de los remitentes y dominios de remitente especificados como ataques basados en suplantación. En otras palabras, la acción para remitentes protegidos, dominios protegidos o protección de inteligencia de buzones no se aplica a estos remitentes o dominios de remitente de confianza. El límite máximo para estas listas es de 1024 entradas.

  > [!NOTE]
  >
  > - Si los mensajes del sistema de Microsoft 365 de los siguientes remitentes se identifican como intentos de suplantación, puede agregar los remitentes a la lista de remitentes de confianza:
  >   - `⁠noreply@email.teams.microsoft.com`
  >   - `noreply@emeaemail.teams.microsoft.com`
  >   - `no-reply@sharepointonline.com`
  >
  > - Las entradas de dominio de confianza no incluyen subdominios del dominio especificado. Debe agregar una entrada para cada subdominio.

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Umbrales avanzados de suplantación de identidad (phishing) en las directivas contra suplantación de identidad (phishing) en Microsoft Defender para Office 365

Los siguientes umbrales avanzados de suplantación de identidad solo están disponibles en las directivas contra suplantación de identidad en Defender para Office 365. Estos umbrales controlan la confidencialidad para aplicar modelos de aprendizaje automático a los mensajes para determinar un veredicto de phishing:

- **1 - Estándar**: este es el valor predeterminado. La gravedad de la acción que se realiza en el mensaje depende del grado de confianza de que el mensaje es phishing (confianza baja, media, alta o muy alta). Por ejemplo, los mensajes que se identifican como phishing con un grado de confianza muy alto tienen las acciones más severas aplicadas, mientras que los mensajes que se identifican como phishing con un bajo grado de confianza tienen acciones menos severas aplicadas.
- **2 - Agresivo**: Los mensajes que se identifican como phishing con un alto grado de confianza se tratan como si fueran identificados con un alto grado de confianza.
- **3 - Más agresivo**: los mensajes que se identifican como phishing con un grado medio o alto de confianza se tratan como si fueran identificados con un grado de confianza muy alto.
- **4 - Más agresivo**: los mensajes que se identifican como phishing con un bajo, medio o alto grado de confianza se tratan como si se identificaran con un grado muy alto de confianza.

La posibilidad de falsos positivos (mensajes buenos marcados como incorrectos) aumenta a medida que aumenta esta configuración. Para obtener información sobre la configuración recomendada, consulte la [directiva contra suplantación de identidad en la configuración de Microsoft Defender para Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).
