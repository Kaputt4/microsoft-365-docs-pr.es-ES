---
title: Protección contra correo no deseado
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre la configuración y los filtros de correo no deseado que le ayudarán a evitar el correo no deseado en Exchange Online Protection (EOP).
ms.openlocfilehash: 4e5c41ebf92de320651a90813220abfcfa50c30e
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199140"
---
# <a name="anti-spam-protection-in-eop"></a>Protección contra correo no deseado en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Este tema está destinado a los administradores. Para los temas de los usuarios finales, vea [información general sobre el filtro de correo no deseado](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) y [obtenga información sobre el correo no deseado y el phishing](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31).

En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP protege automáticamente contra correo no deseado (correo no deseado).

El plan de seguridad para el correo electrónico de Microsoft incluye un enfoque sin igual que abarca diferentes productos. La tecnología de protección contra correo no deseado y antiphishing de EOP se aplica en nuestras plataformas de correo electrónico para proporcionar a los usuarios las herramientas e innovaciones más recientes contra el correo no deseado y antiphishing a través de la red. El objetivo de EOP es ofrecer un servicio de correo electrónico completo y práctico que ayude a detectar el correo no deseado, las amenazas de correo electrónico fraudulento (phishing) y los virus, y que proteja a los usuarios de todo ello.

A medida que su uso aumenta, también lo hace el abuso. El correo electrónico no deseado y no supervisado puede colapsar las bandejas de entrada y las redes, afectar al grado de satisfacción del usuario y limitar la eficacia de las comunicaciones legítimas. Por eso Microsoft sigue invirtiendo en tecnologías contra el correo no deseado. Sencillamente se trata de contener y filtrar el correo electrónico no deseado.

> [!TIP]
> Las siguientes tecnologías contra el correo electrónico no deseado son útiles cuando se desea permitir o bloquear mensajes en función del sobre del mensaje (por ejemplo, el dominio del remitente o la dirección IP de origen del mensaje). Para permitir o bloquear mensajes en función de la carga (por ejemplo, las direcciones URL del mensaje o los archivos adjuntos), debe usar el portal de la [lista de permitidos/bloqueados del inquilino](tenant-allow-block-list.md).

## <a name="anti-spam-technologies-in-eop"></a>Tecnologías contra correo electrónico no deseado en EOP

Para ayudar a reducir el correo no deseado, EOP incluye protección contra correo no deseado que usa tecnologías de filtrado de correo no deseado de propietario para identificar y separar el correo electrónico no deseado de correo electrónico legítimo. El filtrado de correo no deseado de EOP aprende de las amenazas de correo no deseado y suplantación de identidad y los comentarios del usuario de nuestra plataforma de consumidores, Outlook.com. Los comentarios continuos de los usuarios de EOP que participan en el programa de clasificación de correo electrónico no deseado garantizan que las tecnologías de EOP estén en un proceso continuo de aprendizaje y mejora.

La configuración contra correo no deseado en EOP se realiza de las siguientes tecnologías:

- **Filtrado de conexiones**: identifica los servidores de origen de correo electrónico buenos y defectuosos al principio de la conexión de correo electrónico entrante a través de la lista de direcciones IP permitidas, la lista de direcciones IP bloqueadas y la *lista segura* (una lista de remitentes de confianza dinámicos pero no editables que mantiene Microsoft). Estas opciones se configuran en la Directiva de filtro de conexión. Para obtener más información, vea [configurar el filtrado de conexiones](configure-the-connection-filter-policy.md).

  > [!NOTE]
  > La inteligencia de identidad utiliza el filtrado de conexiones para crear listas de permitidos y bloqueados de remitentes que suplantan el dominio de correo electrónico. Para obtener más información, vea más información [acerca de la inteligencia de suplantación de identidad en Microsoft 365](learn-about-spoof-intelligence.md).

- **Filtrado de correo no deseado (filtrado de contenido)**: EOP usa el correo no deseado los veredictos **spam,** correo **no deseado de alta confianza**, **correo masivo**, **correo de phishing** y **correo de suplantación de identidad de alta confianza** para clasificar mensajes. Puede configurar las acciones que se realizarán en función de estos veredictos y puede configurar las opciones de notificación para el usuario final para los mensajes que se pusieron en cuarentena en lugar de entregarse. Para obtener más información, vea [configurar directivas contra correo no deseado en Microsoft 365](configure-your-spam-filter-policies.md).

  > [!NOTE]
  > De forma predeterminada, el filtrado de correo no deseado está configurado para enviar mensajes que se marcaron como correo no deseado a la carpeta de correo no deseado del destinatario. Sin embargo, en entornos híbridos donde EOP protege los buzones de Exchange locales, debe configurar dos reglas de flujo de correo (también conocidas como reglas de transporte) en la organización de Exchange local para reconocer los encabezados de correo no deseado de EOP que se agregan a los mensajes. Para obtener información, consulte [Configuración de un EOP independiente para entregar el correo no deseado en la carpeta de correo no deseado en entornos híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- **Filtrado de correo no deseado saliente**: EOP también se asegura de que los usuarios no envíen correo no deseado, ya sea en el contenido del mensaje saliente o superándose los límites de los mensajes salientes. Para obtener más información, consulte [configurar el filtrado de correo no deseado saliente en Microsoft 365](configure-the-outbound-spam-policy.md).

- **Inteligencia de suplantación de identidad**: para obtener más información, vea más información acerca de la [inteligencia de suplantación en Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="manage-errors-in-spam-filtering"></a>Administrar errores en el filtrado de correo no deseado

Es posible que los mensajes buenos puedan identificarse como correo no deseado (también conocidos como falsos positivos) o que el correo no deseado se entregue a la bandeja de entrada. Puede usar las sugerencias de las siguientes secciones para averiguar qué ha sucedido y ayudar a evitar que se produzca en el futuro.

Estos son algunos procedimientos recomendados que se aplican a cualquiera de los escenarios:

- Envíe siempre mensajes no clasificados a Microsoft. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

- **Examine los encabezados de mensajes contra correo no deseado**: estos valores le indicarán por qué un mensaje se marcó como correo no deseado o por qué omitió el filtrado de correo no deseado. Para obtener más información, vea [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md).

- **Apunte su registro MX a Microsoft 365**: para que EOP proporcione la mejor protección, siempre recomendamos que se entregue el correo electrónico a Microsoft 365 primero. Para obtener instrucciones, vea [crear registros DNS en cualquier proveedor de host DNS para Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

  Si el registro MX apunta a alguna otra ubicación (por ejemplo, una solución contra correo no deseado o un dispositivo de terceros), es difícil para EOP proporcionar un filtrado de correo no deseado preciso. En este escenario, debe configurar el filtrado mejorado para los conectores (también conocido como _omitir la lista_). Para obtener instrucciones, vea [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **Usar autenticación de correo electrónico**: Si posee un dominio de correo electrónico, puede usar DNS para ayudar a garantizar que los mensajes de los remitentes de ese dominio sean legítimos. Para ayudar a evitar el correo no deseado y la suplantación de identidad en EOP, use todos los métodos de autenticación de correo electrónico siguientes:

  - **SPF**: el marco de directivas de remitente comprueba la dirección IP de origen del mensaje con el propietario del dominio remitente. Para obtener una introducción rápida a SPF y configurarlo rápidamente, consulte [configurar SPF para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Para comprender en detalle cómo Microsoft 365 usa SPF, o para la solución de problemas o las implementaciones no estándar (por ejemplo, implementaciones híbridas), comience con [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md) (Cómo Microsoft 365 usa el marco de directivas permanente [SPF] para evitar la suplantación de identidad).

  - **DKIM**: el correo identificado por domainkeyss agrega una firma digital al encabezado del mensaje de los mensajes enviados desde su dominio. Para obtener más información, vea [usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Microsoft 365](use-dkim-to-validate-outbound-email.md).

  - **DMARC**: la autenticación de mensajes basada en el dominio, la creación de informes y el cumplimiento ayudan a los sistemas de correo electrónico de destino a determinar qué hacer con los mensajes que no superen las comprobaciones de SPF o DKIM y proporcionan otro nivel de confianza para los asociados de correo electrónico. Para obtener más información, vea [usar DMARC para validar el correo electrónico en Microsoft 365](use-dmarc-to-validate-email.md).

- **Compruebe la configuración del correo electrónico masivo**: el umbral de nivel compatible con todo el ámbito (BCL) que se configura en las directivas contra correo no deseado determina si el correo electrónico masivo (también conocido como _correo gris_) se marca como correo no deseado. La configuración solo de PowerShell _MarkAsSpamBulkMail_ que está activada de forma predeterminada también contribuye a los resultados. Para obtener más información, vea [configurar directivas contra correo no deseado en Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Impedir la entrega de correo no deseado en la bandeja de entrada

- **Compruebe la configuración de la organización**: vea la configuración que permite a los mensajes omitir el filtrado de correo no deseado (por ejemplo, si agrega su propio dominio a la lista de dominios permitidos en directivas contra correo no deseado). Para obtener la configuración recomendada, consulte [configuración recomendada para EOP y Office 365 ATP Security](recommended-settings-for-eop-and-office365-atp.md) y [Create Safe Sender lists](create-safe-sender-lists-in-office-365.md).

- **Compruebe que la regla de correo no deseado está habilitada en el buzón del usuario**: está habilitada de forma predeterminada, pero si está deshabilitada, los mensajes marcados como correo no deseado no se pueden mover a la carpeta correo electrónico no deseado. Para obtener más información, consulte [configurar la configuración del correo electrónico no deseado en buzones de Exchange online en Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Use las listas de remitentes bloqueados disponibles**: para obtener más información, vea [crear listas de remitentes bloqueados](create-block-sender-lists-in-office-365.md).

- **Cancelar la suscripción del correo electrónico masivo** Si el mensaje fue algo que el usuario registró (boletines, anuncios de productos, etc.) y contiene un vínculo de cancelación de suscripción de un origen de prestigio, considere la posibilidad de solicitarles que simplemente cancelen la suscripción.

- **EOP independiente: crear reglas de flujo de correo en Exchange local para los veredictos de filtrado de correo no deseado de EOP**: en entornos de EOP independientes donde EOP protege los buzones de correo de Exchange local, debe configurar las reglas de flujo de correo (también conocidas como reglas de transporte) en Exchange local para traducir el veredicto de filtrado de correo no deseado de EOP de modo Para obtener información, consulte [Configuración de un EOP independiente para entregar el correo no deseado en la carpeta de correo no deseado en entornos híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Evitar que se identifique un correo no deseado

Estos son algunos de los pasos que puede seguir para ayudar a evitar falsos positivos:

- **Compruebe la configuración del filtro de correo no deseado de Outlook del usuario**:

  - **Compruebe que el filtro de correo electrónico no deseado de Outlook está deshabilitado**: cuando el filtro de correo electrónico no deseado de Outlook está establecido en el valor predeterminado **sin filtrado automático**, Outlook no intenta clasificar los masaje como correo no deseado.  Cuando se establece en **Low** o **High**, el filtro de correo electrónico no deseado de Outlook usa su propia tecnología de Filtro SmartScreen para identificar y mover el correo no deseado a la carpeta de correo no deseado, por lo que podría obtener falsos positivos. Tenga en cuenta que Microsoft dejó de generar actualizaciones de definición de correo no deseado para los filtros SmartScreen en Exchange y Outlook en noviembre de 2016. Las definiciones de correo no deseado de SmartScreen existentes se dejaron en su lugar, pero su eficacia probablemente se degradará con el tiempo.

  - **Compruebe que la opción "solo listas de confianzas" de Outlook está deshabilitada**: cuando esta configuración está habilitada, solo los mensajes de los remitentes de la lista de remitentes seguros del usuario o de la lista de destinatarios seguros se entregan en la bandeja de entrada; el correo electrónico de todos los demás se mueve automáticamente a la carpeta de correo no deseado.

  Para obtener más información acerca de estas opciones, consulte [configurar la configuración del correo electrónico no deseado en buzones de Exchange online en Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Use las listas de remitentes seguros disponibles**: para obtener más información, vea [Create Safe Sender lists](create-safe-sender-lists-in-office-365.md).

- **Compruebe que los usuarios se encuentran dentro de los límites de envío y recepción** , tal y como se describe en [límites de recepción y envío](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) en la descripción del servicio de Exchange Online.

- **EOP independiente: usar la sincronización de directorios**: Si usa EOP independiente para ayudar a proteger su organización de Exchange local, debe sincronizar la configuración de usuario con el servicio mediante la sincronización de directorios. De esta forma, se asegura de que EOP respeta las listas de remitentes seguros de los usuarios. Para obtener más información, consulte [utilizar la sincronización de directorios para administrar usuarios de correo](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users).

## <a name="anti-spam-legislation"></a>Legislación contra correo no deseado

En Microsoft, creemos que el desarrollo de nuevas tecnologías y el propio reglamento requiere el apoyo de la Directiva del gobierno y los marcos de personalidad legales eficaces. La proliferación mundial de correo no deseado ha spurreddo numerosos organismos legislativos para regular el correo electrónico comercial. Actualmente, muchos países tienen leyes de lucha contra el correo no deseado en su ubicación. Estados Unidos tiene tanto leyes federales como estatales que rigen el correo no deseado, y este enfoque complementario está ayudando a contraer el correo no deseado y a prosperar el comercio electrónico legítimo. La ley CAN-SPAM amplía las herramientas disponibles para moderar los mensajes de correo electrónico fraudulentos y engañosos.
