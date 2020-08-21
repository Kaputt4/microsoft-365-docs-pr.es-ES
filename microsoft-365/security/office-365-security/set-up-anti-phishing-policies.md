---
title: Directivas contra phishing
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
description: Los administradores pueden obtener información sobre las directivas antiphishing que están disponibles en Exchange Online Protection (EOP) y Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: f671588ff4232c6ca1c1342475f48802bf1a0076
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825106"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Directivas antiphishing en Microsoft 365

Las directivas para configurar las opciones de protección contra suplantación de identidad están disponibles en Microsoft 365 organizaciones con buzones de Exchange Online, organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online y organizaciones de la protección contra amenazas avanzada de Office 365 (ATP de Office 365).

Las directivas antiphishing de ATP solo están disponibles en organizaciones que tienen Office 365 ATP. Por ejemplo:

- Microsoft 365 Enterprise E5, Microsoft 365 Education A5, etc.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Empresa](https://www.microsoft.com/microsoft-365/business)
- [Office 365 ATP como un complemento](https://products.office.com/exchange/advance-threat-protection)

Todas las demás organizaciones tienen directivas antiphishing.

En la tabla siguiente se describen las diferencias de alto nivel entre las directivas contra la suplantación de identidad y las directivas de ATP contra el phishing:

****

|Característica|Directivas contra phishing|Directivas contra la suplantación de identidad ATP|
|---|:---:|:---:|
|Directiva predeterminada creada automáticamente|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Crear directivas personalizadas|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Configuración de Directiva<sup>\*</sup>|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Configuración de suplantación||![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Configuración de suplantación|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Umbrales de suplantación de identidad avanzada||![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<sup>\*</sup> En la directiva predeterminada, el nombre y la descripción de la Directiva son de solo lectura (la descripción está en blanco) y no se puede especificar a quién se aplica la Directiva (la directiva predeterminada se aplica a todos los destinatarios).

Para configurar las directivas contra la suplantación de identidad (phishing), vea los siguientes artículos:

- [Configurar directivas contra la suplantación de identidad (phishing) en EOP](configure-anti-phishing-policies-eop.md)

- [Configurar las directivas de protección contra suplantación de ATP en Microsoft 365](configure-atp-anti-phishing-policies.md)

En el resto de este artículo se describe la configuración disponible en las directivas antiphishing y en las directivas antiphishing de ATP.

## <a name="policy-settings"></a>Configuración de directivas

La siguiente configuración de directiva está disponible en las directivas antiphishing y en las directivas antiphishing de ATP:

- **Name**: no se puede cambiar el nombre de la Directiva de suplantación de identidad (phishing) predeterminada, pero puede nombrar y cambiar el nombre de las directivas personalizadas que cree.

- **Descripción** No puede Agregar una descripción a la Directiva de suplantación de identidad (phishing) predeterminada, pero puede Agregar y cambiar la descripción de las directivas personalizadas que cree.

- Se **aplica a**: identifica a los destinatarios internos a los que se aplica la Directiva contra la suplantación de identidad. Este valor es necesario en las directivas personalizadas y no está disponible en la directiva predeterminada (la directiva predeterminada se aplica a todos los destinatarios).

  Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

  - El **destinatario es**: uno o más buzones de correo, usuarios de correo o contactos de correo de su organización.
  - El **destinatario es un miembro de**: uno o más grupos de la organización.
  - **El dominio del destinatario es**: uno o más de los dominios aceptados configurados en Microsoft 365.

  - **Excepto cuando**: excepciones para la regla. La configuración y el comportamiento son exactamente iguales a las condiciones:

    - **El destinatario es**
    - **El destinatario es un miembro de**
    - **El dominio del destinatario es**

## <a name="spoof-settings"></a>Configuración de suplantación

La suplantación de identidad es cuando la dirección de origen en un mensaje de correo electrónico (la dirección del remitente que se muestra en los clientes de correo electrónico) no coincide con el dominio del origen del correo electrónico. Para obtener más información acerca de la suplantación, vea [protección contra la suplantación de identidad en Microsoft 365](anti-spoofing-protection.md).

La siguiente configuración de suplantación está disponible en las directivas antiphishing y en las directivas antiphishing de ATP:

- **Protección contra la suplantación de identidad**: habilita o deshabilita la protección contra la suplantación de identidad. Le recomendamos que lo deje habilitado. La Directiva de **inteligencia de suplantación** se usa para permitir o bloquear remitentes específicos suplantados y externos. Para obtener más información, consulte [Configuración de inteligencia contra la suplantación de identidad en Microsoft 365 ](learn-about-spoof-intelligence.md).

  > [!NOTE]
  > La configuración de suplantación de identidad está habilitada de forma predeterminada en la Directiva antiphishing predeterminada en EOP, la Directiva antiphishing de ATP predeterminada y en nuevas directivas antiphishing personalizadas o en las directivas antiphishing de ATP que cree. <br/><br/> No es necesario deshabilitar la protección contra la suplantación de identidad si el registro MX no apunta a Microsoft 365; en su lugar, se habilita el filtrado mejorado para los conectores. Para obtener instrucciones, vea [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

  Para los mensajes de los remitentes suplantados bloqueados, también puede especificar la acción que se llevará a cabo en los mensajes:

  - **Mover el mensaje a la carpeta de correo no deseado**: este es el valor predeterminado. El mensaje se entrega al buzón y se mueve a la carpeta de correo no deseado. En Exchange Online, el mensaje se mueve a la carpeta correo electrónico no deseado si la regla de correo no deseado está habilitada en el buzón (está habilitada de forma predeterminada). Para obtener más información, consulte [configurar la configuración del correo electrónico no deseado en buzones de Exchange online en Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Poner en cuarentena el mensaje**: envía el mensaje a la cuarentena en lugar de a los destinatarios deseados. Para obtener información acerca de la cuarentena, vea los siguientes artículos:

    - [Poner en cuarentena en Microsoft 365](quarantine-email-messages.md)
    - [Administrar archivos y mensajes en cuarentena como administrador en Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Buscar y liberar mensajes en cuarentena como un usuario en Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

- **Remitente sin autenticar**: vea la descripción en la siguiente sección.

### <a name="unauthenticated-sender"></a>Remitente sin autenticar

La identificación de remitente sin autenticar forma parte de la [configuración de suplantación](#spoof-settings) de identidad disponible en las directivas antiphishing y en las directivas antiphishing de ATP, tal como se describe en la sección anterior.

El valor de configuración de **remitente sin autenticar** habilita o deshabilita la identificación de remitente sin identificar en Outlook. En particular:

- Se agrega un signo de interrogación (?) a la foto del remitente si el mensaje no pasa las comprobaciones de SPF o DKIM **y** el mensaje no pasa la [autenticación compuesta](email-validation-and-authentication.md#composite-authentication)o de DMARC.

- La etiqueta Via (chris@contoso.com <u>mediante</u> Michelle@fabrikam.com) se agrega si el dominio de la dirección de remitente (el remitente del mensaje que se muestra en los clientes de correo electrónico) es distinto del dominio de la firma DKIM o de la dirección **remitente** . Para obtener más información acerca de estas direcciones, vea [información general sobre los estándares de mensajes de correo electrónico](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

Para evitar que estos identificadores se agreguen a los mensajes de remitentes específicos, tiene las siguientes opciones:

- Permitir que el remitente suplante la Directiva de inteligencia empresarial de suplantación de identidad. Para obtener instrucciones, consulte [configurar inteligencia simulada en Microsoft 365](learn-about-spoof-intelligence.md).

- [Configurar la autenticación de correo electrónico](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) para el dominio del remitente.
  
  - Para el signo de interrogación de la foto del remitente, SPF o DKIM son los más importantes.
  - Para la etiqueta Via, confirme el dominio en la firma DKIM o la coincidencia de la dirección **de correo de** (o es un subdominio de) el dominio en la dirección de from.

Para obtener más información, consulte [identificar mensajes sospechosos en Outlook.com y Outlook en la web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a>Configuración exclusiva en las directivas antiphishing de ATP

En esta sección se describen las opciones de configuración de directivas que solo están disponibles en las directivas antiphishing de ATP.

> [!NOTE]
> De forma predeterminada, la configuración exclusiva de ATP no está configurada ni activada, incluso en la directiva predeterminada. Para aprovechar estas características, debe habilitarlas y configurarlas en la Directiva de antiphishing de ATP predeterminada o crear y configurar directivas antiphishing de ATP personalizadas.

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Configuración de suplantación en las directivas antiphishing de ATP

La suplantación es cuando el dominio de correo electrónico del remitente o del remitente de un mensaje tiene un aspecto similar a un remitente o dominio real:

- Un ejemplo de suplantación del dominio contoso.com es ćóntoso.com.
- Un ejemplo de suplantación del usuario michelle@contoso.com es michele@contoso.com.

De lo contrario, un dominio suplantado podría considerarse legítimo (dominio registrado, registros de autenticación de correo electrónico configurados, etc.), pero su intención es engañar a los destinatarios.

La siguiente configuración de suplantación solo está disponible en las directivas contra la suplantación de identidad ATP:

- **Usuarios que se deben proteger**: impide que los usuarios internos o externos especificados se suplanten. Por ejemplo, Executives (Internal) y Board Members (external). Puede Agregar hasta 60 direcciones internas y externas. Esta lista de usuarios protegidos es diferente de la lista de destinatarios a los que se aplica la Directiva en la configuración de **aplicado a** .

  Por ejemplo, especifique Felipe Apodaca (felipea@contoso.com) como usuario protegido en una directiva que se aplica al grupo denominado ejecutivos. La Directiva actuará sobre los mensajes entrantes enviados a miembros del grupo ejecutivos donde se suplanta a Felipe Apodaca, (la acción que se configura para los usuarios suplantados).

- **Dominios para proteger**: impedir la suplantación de los dominios especificados. Por ejemplo, todos los dominios que son de su propiedad ([dominios aceptados](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) o dominios específicos (dominios que posee o dominios asociados). Esta lista de dominios protegidos es diferente de la lista de dominios a los que se aplica la Directiva en la configuración **aplicado a** .

  Por ejemplo, puede especificar tailspintoys.com como un dominio protegido en una directiva que se aplica a los miembros del grupo denominado ejecutivos. La Directiva actuará sobre los mensajes entrantes enviados a miembros del grupo ejecutivos donde se suplanta a tailspintoys.com (la acción que configuró para los dominios suplantados).

- **Acciones para usuarios o dominios protegidos**: elija la acción que se realizará en los mensajes entrantes que contengan intentos de suplantación con los usuarios protegidos y los dominios protegidos de la Directiva. Puede especificar distintas acciones para la suplantación de los usuarios protegidos frente a la suplantación de los dominios protegidos:

  - **No aplicar ninguna acción**

  - **Redirigir un mensaje a otras direcciones de correo electrónico**: envía el mensaje a los destinatarios especificados en lugar de a los destinatarios deseados.

  - **Mover el mensaje a la carpeta de correo no deseado**: el mensaje se entrega al buzón y se mueve a la carpeta de correo no deseado. En Exchange Online, el mensaje se mueve a la carpeta correo electrónico no deseado si la regla de correo no deseado está habilitada en el buzón (está habilitada de forma predeterminada). Para obtener más información, consulte [configurar la configuración del correo electrónico no deseado en buzones de Exchange online en Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

    - **Poner en cuarentena el mensaje**: envía el mensaje a la cuarentena en lugar de a los destinatarios deseados. Para obtener información acerca de la cuarentena, vea los siguientes artículos:

    - [Poner en cuarentena en Microsoft 365](quarantine-email-messages.md)
    - [Administrar archivos y mensajes en cuarentena como administrador en Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Buscar y liberar mensajes en cuarentena como un usuario en Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - **Entregar el mensaje y agregar otras direcciones a la línea CCO**: entregar el mensaje a los destinatarios previstos y entregar el mensaje en modo silencioso a los destinatarios especificados.

  - **Eliminar el mensaje antes de su entrega**: elimina silenciosamente el mensaje completo, incluidos todos los datos adjuntos.

- **Sugerencias de seguridad**: habilita o deshabilita las sugerencias de seguridad de suplantación siguientes, que aparecerán como mensajes que no cumplen las comprobaciones de suplantación:

  - **Usuarios suplantados**: la dirección de contiene un usuario protegido.
  - **Dominios suplantados**: la dirección de contiene un dominio protegido.
  - **Caracteres inusuales**: la dirección de contiene juegos de caracteres inusuales (por ejemplo, símbolos matemáticos y texto o una combinación de letras mayúsculas y minúsculas) en un dominio o remitente protegido.

- **Inteligencia de buzones**: habilita o deshabilita la inteligencia artificial (AI) que determina los patrones de correo electrónico del usuario con sus contactos frecuentes. Esta configuración ayuda a los AI a distinguir los correos electrónicos legítimos y falsos de los contactos. La inteligencia de buzones solo está disponible para buzones de Exchange Online.

- **Protección de suplantación basada en la inteligencia de buzones**: habilita o deshabilita los resultados de suplantación mejorados en función del mapa de remitentes individuales de cada usuario. Esta inteligencia permite a Microsoft 365 personalizar la detección de suplantación de usuario y administrar mejor los falsos positivos. Cuando se detecta la suplantación del usuario, puede definir una acción específica que se debe llevar a cabo en el mensaje:

  - **No aplicar ninguna acción**
  - **Redirigir un mensaje a otras direcciones de correo electrónico**
  - **Mover mensaje a la carpeta Correo no deseado**
  - **Poner en cuarentena el mensaje**
  - **Entregar el mensaje y agregar otras direcciones a la línea CCO**
  - **Eliminar el mensaje antes de su entrega**

- **Remitentes y dominios de confianza**: excepciones a la configuración de la protección de suplantación. Los mensajes de los dominios remitentes y remitentes especificados nunca se clasifican como ataques basados en suplantación por la Directiva. En otras palabras, la acción para los remitentes protegidos, los dominios protegidos o la protección de inteligencia de buzones no se aplican a estos remitentes o dominios de remitentes de confianza. El límite máximo de estas listas es de aproximadamente 1000 entradas.

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a>Umbrales de suplantación de identidad avanzada en las directivas antiphishing de ATP

Los siguientes umbrales de suplantación de identidad avanzada solo están disponibles en las directivas antiphishing de ATP para controlar la sensibilidad de la aplicación de modelos de aprendizaje automáticos a los mensajes para determinar un veredicto de suplantación de identidad:

- **1-estándar**: este es el valor predeterminado. La gravedad de la acción que se realiza en el mensaje depende del grado de confianza que el mensaje es "phishing" (baja, media, alta o muy alta confianza). Por ejemplo, los mensajes que se identifican como phishing con un grado muy alto de confianza tienen las acciones más graves aplicadas, mientras que los mensajes que se identifican como phishing con bajo grado de confianza tienen acciones menos graves aplicadas.

- **2-agresivo**: los mensajes que se identifican como suplantación de identidad (phishing) con un alto grado de confianza se tratan como si se hubieran identificado con un grado muy alto de confianza.

- **3-más agresivo**: los mensajes que se identifican como suplantación de identidad (phishing) con un grado de confianza medio o alto se tratan como si se hubieran identificado con un grado muy alto de confianza.

- **4: más agresivo**: los mensajes que se identifican como suplantación de identidad (phishing) con un nivel bajo, medio o alto de confianza se tratan como si se hubieran identificado con un grado muy alto de confianza.

La probabilidad de falsos positivos (mensajes buenos marcados como no válidos) aumenta a medida que se aumenta esta configuración. Para obtener información acerca de la configuración recomendada, consulte [configuración de la Directiva de suplantación de identidad ATP de Office](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).
