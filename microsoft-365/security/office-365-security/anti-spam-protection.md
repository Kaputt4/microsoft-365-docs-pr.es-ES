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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre la configuración y los filtros contra correo no deseado que ayudarán a evitar el correo no deseado en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ae2c4f42d42c37f5b7a7df2b6c8306fd390b0af
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175864"
---
# <a name="anti-spam-protection-in-eop"></a>Protección contra correo no deseado en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!NOTE]
> Este tema está pensado para administradores. Para obtener temas sobre el usuario final, consulte Información general sobre el [filtro de](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) correo no deseado y obtenga información sobre correo electrónico no deseado [y suplantación de identidad](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31).

En organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP protege automáticamente los mensajes de correo electrónico contra correo no deseado (correo no deseado).

El plan de seguridad para el correo electrónico de Microsoft incluye un enfoque sin igual que abarca diferentes productos. EOP anti-spam and anti-phishing technology is applied across our email platforms to provide users with the latest anti-spam and anti-phishing tools and innovations throughout the network. El objetivo de EOP es ofrecer un servicio de correo electrónico completo y práctico que ayude a detectar el correo no deseado, las amenazas de correo electrónico fraudulento (phishing) y los virus, y que proteja a los usuarios de todo ello.

A medida que su uso aumenta, también lo hace el abuso. El correo electrónico no deseado y no supervisado puede colapsar las bandejas de entrada y las redes, afectar al grado de satisfacción del usuario y limitar la eficacia de las comunicaciones legítimas. Por eso Microsoft sigue invirtiendo en tecnologías contra el correo no deseado. Sencillamente se trata de contener y filtrar el correo electrónico no deseado.

> [!TIP]
> Las siguientes tecnologías contra correo no deseado son útiles cuando se desea permitir o bloquear mensajes basados en el sobre del mensaje (por ejemplo, el dominio del remitente o la dirección IP de origen del mensaje). Para permitir o bloquear mensajes en función de la carga (por ejemplo, direcciones URL en el mensaje o archivos adjuntos), debe usar el portal de listas de permitidos [o bloqueados del](tenant-allow-block-list.md)espacio empresarial.

## <a name="anti-spam-technologies-in-eop"></a>Tecnologías contra correo no deseado en EOP

Para ayudar a reducir el correo no deseado, EOP incluye protección contra correo no deseado que usa tecnologías de filtrado de correo no deseado propietarias para identificar y separar el correo no deseado del correo electrónico legítimo. EOP spam filtering learns from known spam and phishing threats and user feedback from our consumer platform, Outlook.com. Los comentarios continuos de los usuarios de EOP que participan en el programa de clasificación de correo electrónico no deseado garantizan que las tecnologías de EOP estén en un proceso continuo de aprendizaje y mejora.

La configuración contra correo no deseado en EOP está hecha de las siguientes tecnologías:

- Filtrado de conexiones: identifica servidores de origen de correo electrónico buenos y no modificables al principio de la conexión de correo electrónico entrante a través de la lista de direcciones IP permitidos, la lista de direcciones IP bloqueados y la lista segura *(una* lista dinámica pero no modificable de remitentes de confianza mantenida por Microsoft). Estas opciones se configuran en la directiva de filtro de conexión. Obtenga más información en [Configurar el filtrado de conexiones.](configure-the-connection-filter-policy.md)

  > [!NOTE]
  > La inteligencia de suplantación de identidad usa el filtrado de conexiones para crear listas de remitentes permitidos y bloqueados que suplanten su dominio de correo electrónico. Para obtener más información, vea Más información sobre la inteligencia de [suplantación de documentos en Microsoft 365.](learn-about-spoof-intelligence.md)

- Filtrado de correo no deseado (filtrado de  **contenido):** EOP usa los veredictos de filtrado de correo no deseado, correo no deseado de confianza alta, correo electrónico masivo, correo electrónico de suplantación de identidad y correo electrónico de **suplantación** de identidad de confianza alta para clasificar mensajes.    Puede configurar las acciones que se realizarán en función de estos veredictos y puede configurar las opciones de notificación del usuario final para los mensajes que se han puesto en cuarentena en lugar de entregarse. Para obtener más información, vea [Configurar directivas contra correo no deseado en Microsoft 365.](configure-your-spam-filter-policies.md)

  > [!NOTE]
  > De forma predeterminada, el filtrado de correo no deseado está configurado para enviar mensajes marcados como correo no deseado a la carpeta de correo no deseado del destinatario. Sin embargo, en entornos híbridos en los que EOP protege los buzones de Exchange locales, debe configurar dos reglas de flujo de correo (también conocidas como reglas de transporte) en la organización de Exchange local para reconocer los encabezados de correo no deseado de EOP que se agregan a los mensajes. Para obtener información, consulte [Configuración de un EOP independiente para entregar el correo no deseado en la carpeta de correo no deseado en entornos híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- **Filtrado de correo** no deseado saliente: EOP también comprueba que los usuarios no envíen correo no deseado, ya sea en el contenido de los mensajes salientes o superando los límites de mensajes salientes. Para obtener más información, vea [Configurar el filtrado de correo no deseado saliente en Microsoft 365.](configure-the-outbound-spam-policy.md)

- **Inteligencia de suplantación** de seguridad: para obtener más información, vea Más información sobre la inteligencia de suplantación de documentos [en Microsoft 365.](learn-about-spoof-intelligence.md)

## <a name="manage-errors-in-spam-filtering"></a>Administrar errores en el filtrado de correo no deseado

Es posible que los mensajes buenos se identifiquen como correo no deseado (también conocidos como falsos positivos) o que el correo no deseado se pueda entregar en la Bandeja de entrada. Puede usar las sugerencias de las secciones siguientes para averiguar qué ha ocurrido y ayudar a evitar que ocurra en el futuro.

Estos son algunos procedimientos recomendados que se aplican a cualquiera de los dos escenarios:

- Envíe siempre mensajes clasificados erróneamente a Microsoft. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

- **Examine los encabezados de los** mensajes contra correo no deseado: estos valores le mostrarán por qué un mensaje se marcó como correo no deseado o por qué omitió el filtrado de correo no deseado. Para obtener más información, vea [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md).

- Apunte su registro MX a **Microsoft 365:** para que EOP proporcione la mejor protección, siempre recomendamos que primero envíe el correo electrónico a Microsoft 365. Para obtener instrucciones, [consulte Crear registros DNS en cualquier proveedor de hospedaje DNS para Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

  Si el registro MX apunta a otra ubicación (por ejemplo, una solución o dispositivo contra correo no deseado de terceros), es difícil para EOP proporcionar un filtrado preciso de correo no deseado. En este escenario, debe configurar el filtrado mejorado para conectores (también conocido como omitir _lista)._ Para obtener instrucciones, consulte [Filtrado mejorado para conectores en Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **Usar la autenticación** de correo electrónico: si es propietario de un dominio de correo electrónico, puede usar DNS para ayudar a garantizar que los mensajes de los remitentes de ese dominio son legítimos. Para ayudar a evitar el correo no deseado y la suplantación de seguridad no deseada en EOP, use todos los siguientes métodos de autenticación de correo electrónico:

  - **SPF:** el marco de directivas de remitente comprueba la dirección IP de origen del mensaje con el propietario del dominio remitente. Para obtener una introducción rápida a SPF y configurarlo rápidamente, consulte Configurar SPF para ayudar a evitar [la suplantación de documentos.](set-up-spf-in-office-365-to-help-prevent-spoofing.md) Para comprender en detalle cómo Microsoft 365 usa SPF, o para la solución de problemas o las implementaciones no estándar (por ejemplo, implementaciones híbridas), comience con [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md) (Cómo Microsoft 365 usa el marco de directivas permanente [SPF] para evitar la suplantación de identidad).

  - **DKIM:** DomainKeys Identified Mail agrega una firma digital al encabezado del mensaje de los mensajes enviados desde su dominio. Para obtener información, vea Usar DKIM para validar el correo electrónico saliente [enviado desde su dominio personalizado en Microsoft 365](use-dkim-to-validate-outbound-email.md).

  - **DMARC:** la autenticación, los informes y la conformidad de mensajes basados en dominio ayuda a los sistemas de correo electrónico de destino a determinar qué hacer con los mensajes que no cumplen las comprobaciones SPF o DKIM y proporciona otro nivel de confianza para los socios de correo electrónico. Para obtener más información, [vea Usar DMARC para validar el correo electrónico en Microsoft 365.](use-dmarc-to-validate-email.md)

- **Compruebe** la configuración del correo electrónico masivo: el umbral de nivel de cumplimiento masivo (BCL) que configure en las directivas contra correo no deseado determina si el correo masivo (también conocido como correo _gris)_ está marcado como correo no deseado. La configuración de Solo PowerShell _MarkAsSpamBulkMail_ que está activa de forma predeterminada también contribuye a los resultados. Para obtener más información, vea [Configurar directivas contra correo no deseado en Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Impedir la entrega de correo no deseado a la Bandeja de entrada

- **Compruebe la configuración** de su organización: tenga cuidado con las opciones que permiten que los mensajes omitan el filtrado de correo no deseado (por ejemplo, si agrega su propio dominio a la lista de dominios permitidos en directivas contra correo no deseado). Para obtener la configuración recomendada, consulte Configuración recomendada para EOP y Microsoft Defender para la seguridad de [Office 365](recommended-settings-for-eop-and-office365-atp.md) y Crear [listas de remitentes seguros.](create-safe-sender-lists-in-office-365.md)

- **Compruebe** que la regla de correo no deseado está habilitada en el buzón del usuario: está habilitada de forma predeterminada, pero si está deshabilitada, los mensajes marcados como correo no deseado no se pueden mover a la carpeta de correo no deseado. Para obtener más información, vea [Configurar las opciones de correo no deseado en buzones de Exchange Online en Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Use las listas de remitentes bloqueados** disponibles: Para obtener información, vea [Crear listas de remitentes bloqueados.](create-block-sender-lists-in-office-365.md)

- **Cancelar la suscripción del correo electrónico masivo** Si el mensaje era algo para lo que el usuario se suscribió (boletines, anuncios de productos, etc.) y contiene un vínculo para cancelar la suscripción de un origen de confianza, considere la posibilidad de pedirles que simplemente cancelen la suscripción.

- **EOP independiente:** cree reglas de flujo de correo en Exchange local para veredictos de filtrado de correo no deseado de EOP: en entornos de EOP independientes donde EOP protege los buzones de Exchange locales, debe configurar reglas de flujo de correo (también conocidas como reglas de transporte) en Exchange local para traducir el veredicto de filtrado de correo no deseado de EOP para que la regla de correo no deseado pueda mover el mensaje a la carpeta correo no deseado. Para obtener información, consulte [Configuración de un EOP independiente para entregar el correo no deseado en la carpeta de correo no deseado en entornos híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Evitar que el correo electrónico bueno se identifique como correo no deseado

Estos son algunos pasos que puede seguir para ayudar a evitar falsos positivos:

- **Compruebe la configuración del filtro de correo** no deseado de Outlook del usuario:

  - **Compruebe** que el filtro de correo no deseado de Outlook está deshabilitado: cuando el filtro de correo no deseado de Outlook se establece en el valor predeterminado **No** hay filtrado automático, Outlook no intenta clasificar los idiomas como correo no deseado.  Cuando se establece  en Baja o **Alta,** el filtro de correo no deseado de Outlook usa su propia tecnología de filtro SmartScreen para identificar y mover correo no deseado a la carpeta correo no deseado, por lo que podría obtener falsos positivos. Tenga en cuenta que Microsoft dejó de producir actualizaciones de definiciones de correo no deseado para los filtros SmartScreen en Exchange y Outlook en noviembre de 2016. Las definiciones de correo no deseado de SmartScreen existentes se dejaron en su lugar, pero es probable que su eficacia se degrade con el tiempo.

  - Compruebe que la opción **"Solo** listas seguras" de Outlook está deshabilitada: cuando esta opción está habilitada, solo se entregan en la Bandeja de entrada los mensajes de remitentes de la lista de remitentes seguros o de la lista de destinatarios seguros del usuario; el correo electrónico de todos los demás se mueve automáticamente a la carpeta correo no deseado.

  Para obtener más información acerca de estas opciones, vea Configurar las opciones de correo no deseado en los buzones de [Exchange Online en Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Use las listas de remitentes seguros** disponibles: Para obtener información, vea [Crear listas de remitentes seguros.](create-safe-sender-lists-in-office-365.md)

- **Compruebe que los usuarios se encuentran dentro** de los límites de envío y recepción, tal como se describe en [los](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) límites de recepción y envío en la descripción del servicio de Exchange Online.

- **EOP independiente: use** la sincronización de directorios: si usa EOP independiente para ayudar a proteger su organización de Exchange local, debe sincronizar la configuración del usuario con el servicio mediante la sincronización de directorios. De esta forma, se asegura de que EOP respeta las listas de remitentes seguros de los usuarios. Para obtener más información, consulte [utilizar la sincronización de directorios para administrar usuarios de correo](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users).

## <a name="anti-spam-legislation"></a>Legislación contra correo no deseado

En Microsoft, creemos que el desarrollo de nuevas tecnologías y la autorregulación requiere el soporte de marcos legales y de directivas gubernamentales eficaces. La proliferación de correo no deseado en todo el mundo ha puesto en marcha numerosos organismos nacionales para regular el correo electrónico comercial. Muchos países tienen ahora vigentes leyes contra el correo no deseado. Los Estados Unidos tienen leyes federales y estatales que rigen el correo no deseado y este enfoque complementario ayuda a reducir el correo no deseado a la vez que permite que el comercio electrónico legítimo se desenlaza. La Ley CAN-SPAM amplía las herramientas disponibles para reducir los mensajes de correo electrónico fraudulentos y engañosos.
