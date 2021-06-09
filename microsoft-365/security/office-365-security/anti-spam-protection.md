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
ms.openlocfilehash: 52e891a86e75309dadd445736738a3f25584823e
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624866"
---
# <a name="anti-spam-protection-in-eop"></a>Protección contra correo no deseado en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)

> [!NOTE]
> Este tema está dirigido a los administradores. Para obtener temas de usuario final, vea [Overview of the Junk Email Filter](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) y Learn about junk email and [phishing](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31).

En Microsoft 365 organizaciones con buzones en organizaciones de Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, EOP protege automáticamente los mensajes de correo electrónico contra correo no deseado (correo no deseado).

El plan de seguridad para el correo electrónico de Microsoft incluye un enfoque sin igual que abarca diferentes productos. La tecnología contra correo no deseado y anti phishing de EOP se aplica en nuestras plataformas de correo electrónico para proporcionar a los usuarios las últimas herramientas e innovaciones contra correo no deseado y contra suplantación de identidad en toda la red. El objetivo de EOP es ofrecer un servicio de correo electrónico completo y práctico que ayude a detectar el correo no deseado, las amenazas de correo electrónico fraudulento (phishing) y los virus, y que proteja a los usuarios de todo ello.

A medida que su uso aumenta, también lo hace el abuso. El correo electrónico no deseado y no supervisado puede colapsar las bandejas de entrada y las redes, afectar al grado de satisfacción del usuario y limitar la eficacia de las comunicaciones legítimas. Por eso Microsoft sigue invirtiendo en tecnologías contra el correo no deseado. Sencillamente se trata de contener y filtrar el correo electrónico no deseado.

> [!TIP]
> Las siguientes tecnologías contra correo no deseado son útiles cuando se desea permitir o bloquear mensajes en función del sobre del mensaje (por ejemplo, el dominio del remitente o la dirección IP de origen del mensaje). Para permitir o bloquear mensajes en función de la carga (por ejemplo, direcciones URL en el mensaje o archivos adjuntos), debe usar el portal de lista de inquilinos [permitidos o bloqueados](tenant-allow-block-list.md).

## <a name="anti-spam-technologies-in-eop"></a>Tecnologías contra correo no deseado en EOP

Para ayudar a reducir el correo no deseado, EOP incluye protección contra correo no deseado que usa tecnologías de filtrado de correo no deseado propietarias para identificar y separar el correo no deseado del correo electrónico legítimo. EOP spam filtering learns from known spam and phishing threats and user feedback from our consumer platform, Outlook.com. Los comentarios continuos de los usuarios de EOP que participan en el programa de clasificación de correo electrónico no deseado garantizan que las tecnologías de EOP estén en un proceso continuo de aprendizaje y mejora.

La configuración contra correo no deseado en EOP está hecha de las siguientes tecnologías:

- **Filtrado de** conexiones: identifica los servidores de origen de correo electrónico buenos y malos al principio de la conexión de correo electrónico entrante a través de la lista de direcciones IP permitidos, la lista de direcciones IP bloqueados y la lista segura *(una* lista dinámica pero no editable de remitentes de confianza mantenidos por Microsoft). Estas opciones se configuran en la directiva de filtro de conexión. Obtenga más información en [Configurar el filtrado de conexiones](configure-the-connection-filter-policy.md).

- Filtrado de correo no deseado (filtrado de **contenido):** EOP usa los veredictos de filtrado de correo no deseado **Correo** no deseado **,** Correo no deseado de alta **confianza,** Correo electrónico masivo, **Correo** electrónico de suplantación de identidad y Correo electrónico de **suplantación** de identidad de elevada confianza para clasificar los mensajes. Puede configurar las acciones que deben realizarse en función de estos veredictos y puede configurar las opciones de notificación del usuario final para los mensajes que se han puesto en cuarentena en lugar de entregarse. Para obtener más información, vea [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).

  > [!NOTE]
  > De forma predeterminada, el filtrado de correo no deseado está configurado para enviar mensajes marcados como correo no deseado a la carpeta de correo no deseado del destinatario. Sin embargo, en entornos híbridos donde EOP protege los buzones de correo de Exchange locales, debe configurar dos reglas de flujo de correo (también conocidas como reglas de transporte) en la organización de Exchange local para reconocer los encabezados de correo no deseado de EOP que se agregan a los mensajes. Para obtener información, consulte [Configuración de un EOP para entregar el correo no deseado en la carpeta de correo no deseado en entornos híbridos](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).

- **Filtrado de correo** no deseado saliente: EOP también comprueba que los usuarios no envíen correo no deseado, ya sea en el contenido de mensajes salientes o superando los límites de mensajes salientes. Para obtener más información, vea [Configure outbound spam filtering in Microsoft 365](configure-the-outbound-spam-policy.md).

- **Inteligencia de suplantación:** para obtener más información, vea Protección contra la suplantación [en EOP](anti-spoofing-protection.md).

## <a name="manage-errors-in-spam-filtering"></a>Administrar errores en el filtrado de correo no deseado

Es posible que los mensajes buenos se puedan identificar como correo no deseado (también conocidos como falsos positivos) o que el correo no deseado se pueda entregar en la Bandeja de entrada. Puede usar las sugerencias de las secciones siguientes para averiguar qué ocurrió y ayudar a evitar que suceda en el futuro.

Estos son algunos procedimientos recomendados que se aplican a cualquiera de los dos escenarios:

- Envíe siempre mensajes mal clasificados a Microsoft. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

- **Examine los encabezados de mensajes** contra correo no deseado: estos valores le dirán por qué se marcó un mensaje como correo no deseado o por qué omitió el filtrado de correo no deseado. Para obtener más información, vea [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md).

- **Apunte el registro MX** a Microsoft 365: para que EOP proporcione la mejor protección, siempre recomendamos que envíe correo electrónico a Microsoft 365 primero. Para obtener instrucciones, vea [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

  Si el registro MX apunta a otra ubicación (por ejemplo, una solución o dispositivo contra correo no deseado de terceros), es difícil que EOP proporcione un filtrado de correo no deseado preciso. En este escenario, debe configurar el filtrado mejorado para conectores (también conocido como _listado de omitir_). Para obtener instrucciones, consulte [Enhanced Filtering for Connectors in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **Usar la autenticación** de correo electrónico: si es propietario de un dominio de correo electrónico, puede usar DNS para asegurar que los mensajes de los remitentes de ese dominio sean legítimos. Para ayudar a evitar correo no deseado y suplantación de correo no deseado en EOP, use todos los siguientes métodos de autenticación de correo electrónico:

  - **SPF:** el marco de directivas de remitente comprueba la dirección IP de origen del mensaje con el propietario del dominio de envío. Para obtener una introducción rápida a SPF y configurarla rápidamente, consulte Configurar SPF para ayudar a evitar la [suplantación](set-up-spf-in-office-365-to-help-prevent-spoofing.md)de documentos . Para comprender en detalle cómo Microsoft 365 usa SPF, o para la solución de problemas o las implementaciones no estándar (por ejemplo, implementaciones híbridas), comience con [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md) (Cómo Microsoft 365 usa el marco de directivas permanente [SPF] para evitar la suplantación de identidad).

  - **DKIM:** DomainKeys Identified Mail agrega una firma digital al encabezado del mensaje de los mensajes enviados desde su dominio. Para obtener información, vea [Use DKIM to validate outbound email sent from your custom domain in Microsoft 365](use-dkim-to-validate-outbound-email.md).

  - **DMARC:** Autenticación de mensajes basada en dominio, informes y conformidad ayuda a los sistemas de correo electrónico de destino a determinar qué hacer con los mensajes que no cumplen con las comprobaciones de SPF o DKIM y proporciona otro nivel de confianza para los partners de correo electrónico. Para obtener más información, vea [Use DMARC to validate email in Microsoft 365](use-dmarc-to-validate-email.md).

- **Compruebe** la configuración de correo electrónico masivo: el umbral de nivel de queja masiva (BCL) que configure en directivas contra correo no deseado determina si el correo masivo (también conocido como correo _gris)_ está marcado como correo no deseado. La configuración de solo PowerShell _MarkAsSpamBulkMail_ que está activa de forma predeterminada también contribuye a los resultados. Para obtener más información, vea [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Impedir la entrega de correo no deseado a la Bandeja de entrada

- **Compruebe la configuración de** la organización: tenga cuidado con las opciones que permiten a los mensajes omitir el filtrado de correo no deseado (por ejemplo, si agrega su propio dominio a la lista de dominios permitidos en directivas contra correo no deseado). Para obtener nuestra configuración recomendada, vea Configuración recomendada para [EOP](recommended-settings-for-eop-and-office365.md) y Microsoft Defender para Office 365 seguridad y [Crear listas de remitentes seguros.](create-safe-sender-lists-in-office-365.md)

- **Compruebe que** la regla de correo no deseado está habilitada en el buzón del usuario: está habilitada de forma predeterminada, pero si está deshabilitada, los mensajes marcados como correo no deseado no se pueden mover a la carpeta correo no deseado. Para obtener más información, vea [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Use las listas de remitentes bloqueados** disponibles: Para obtener información, vea [Crear listas de remitentes bloqueados.](create-block-sender-lists-in-office-365.md)

- **Cancelar la suscripción al correo electrónico masivo** Si el mensaje era algo para lo que el usuario se suscribió (boletines, anuncios de productos, etc.) y contiene un vínculo para cancelar la suscripción de una fuente de confianza, considere la posibilidad de pedirles que simplemente cancelen la suscripción.

- EOP independiente: cree reglas de flujo de correo en Exchange local para veredictos de filtrado de correo no deseado de **EOP:** en entornos EOP donde EOP protege buzones de correo Exchange locales, debe configurar reglas de flujo de correo (también conocidas como reglas de transporte) en Exchange local para traducir el veredicto de filtrado de correo no deseado de EOP para que la regla de correo no deseado pueda mover el mensaje a la carpeta correo no deseado. Para obtener información, consulte [Configuración de un EOP para entregar el correo no deseado en la carpeta de correo no deseado en entornos híbridos](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Impedir que el correo electrónico bueno se identifique como correo no deseado

Estos son algunos pasos que puede seguir para ayudar a evitar falsos positivos:

- **Compruebe la configuración del filtro de correo Outlook correo no deseado del usuario:**

  - **Compruebe** que el filtro de correo no deseado de Outlook está deshabilitado: cuando el filtro de correo no deseado de Outlook se establece en el valor predeterminado **No** hay filtrado automático , Outlook no intenta clasificar los masajes como correo no deseado.  Cuando se establece  en Bajo o **Alto,** el filtro de correo no deseado de Outlook usa su propia tecnología de filtro SmartScreen para identificar y mover correo no deseado a la carpeta correo no deseado, por lo que podría obtener falsos positivos. Tenga en cuenta que Microsoft dejó de producir actualizaciones de definición de correo no deseado para los filtros SmartScreen en Exchange y Outlook noviembre de 2016. Las definiciones de correo no deseado de SmartScreen existentes se dejaron en su lugar, pero es probable que su eficacia se degrade con el tiempo.

  - Compruebe que la configuración Outlook "solo listas de **Caja fuerte"** está deshabilitada: cuando esta configuración está habilitada, solo los mensajes de remitentes de la lista de remitentes de Caja fuerte o de la lista de destinatarios Caja fuerte del usuario se entregan a la Bandeja de entrada; el correo electrónico de todos los demás se mueve automáticamente a la carpeta Correo no deseado.

  Para obtener más información acerca de estas opciones, vea [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Use las listas de remitentes seguros** disponibles: Para obtener información, vea [Crear listas de remitentes seguros.](create-safe-sender-lists-in-office-365.md)

- **Compruebe que los usuarios se encuentran dentro** de los límites de envío y recepción, tal como se describe en [Límites](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) de recepción y envío en la Exchange Online descripción del servicio.

- **EOP independiente:** use la sincronización de directorios: si usa EOP independiente para ayudar a proteger su organización Exchange local, debe sincronizar la configuración del usuario con el servicio mediante la sincronización de directorios. De esta forma, se asegura de que EOP respeta las listas de remitentes seguros de los usuarios. Para obtener más información, consulte [utilizar la sincronización de directorios para administrar usuarios de correo](/exchange/standalone-eop/manage-mail-users-in-eop#synchronize-directories-with-azure-active-directory-connect-aad-connect).

## <a name="anti-spam-legislation"></a>Legislación contra correo no deseado

En Microsoft, creemos que el desarrollo de nuevas tecnologías y la autorregulación requiere el apoyo de marcos legales y de directivas gubernamentales eficaces. La proliferación mundial de correo no deseado ha impulsado a numerosos organismos legislativos a regular el correo electrónico comercial. Muchos países ahora tienen leyes contra correo no deseado en su lugar. Los Estados Unidos tienen leyes federales y estatales que rigen el correo no deseado, y este enfoque complementario ayuda a reducir el correo no deseado a la vez que permite que el comercio electrónico legítimo prospere. La Ley CAN-SPAM amplía las herramientas disponibles para limitar los mensajes de correo electrónico fraudulentos y engañosos.