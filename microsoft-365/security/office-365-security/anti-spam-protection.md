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
ms.localizationpriority: medium
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
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: e5c2ed6ddc31c75baa87b62bbd642ca4fd9cc30f
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480501"
---
# <a name="anti-spam-protection-in-eop"></a>Protección contra correo no deseado en EOP

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)

> [!NOTE]
> Este tema está pensado para administradores. Para ver los temas de usuario final, consulte [Información general sobre el filtro de Email no deseado](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) y [Información sobre el correo electrónico no deseado y la suplantación de identidad (phishing](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31)).

En las organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin Exchange Online buzones, EOP protege automáticamente los mensajes de correo electrónico contra correo no deseado (correo no deseado).

El plan de seguridad para el correo electrónico de Microsoft incluye un enfoque sin igual que abarca diferentes productos. La tecnología antispam y anti-phishing de EOP se aplica en nuestras plataformas de correo electrónico para proporcionar a los usuarios las últimas herramientas e innovaciones contra el correo no deseado y contra suplantación de identidad en toda la red. El objetivo de EOP es ofrecer un servicio de correo electrónico completo y práctico que ayude a detectar el correo no deseado, las amenazas de correo electrónico fraudulento (phishing) y los virus, y que proteja a los usuarios de todo ello.

A medida que su uso aumenta, también lo hace el abuso. El correo electrónico no deseado y no supervisado puede colapsar las bandejas de entrada y las redes, afectar al grado de satisfacción del usuario y limitar la eficacia de las comunicaciones legítimas. Por eso Microsoft sigue invirtiendo en tecnologías contra el correo no deseado. Sencillamente se trata de contener y filtrar el correo electrónico no deseado.

> [!TIP]
> Las siguientes tecnologías contra correo no deseado son útiles cuando se desea permitir o bloquear mensajes en función del sobre del mensaje (por ejemplo, el dominio del remitente o la dirección IP de origen del mensaje). Para permitir o bloquear mensajes en función de la carga (por ejemplo, direcciones URL en los archivos adjuntos o de mensajes), debe usar el [portal de lista de inquilinos permitidos o bloqueados](manage-tenant-allow-block-list.md).

## <a name="anti-spam-technologies-in-eop"></a>Tecnologías antispam en EOP

Para ayudar a reducir el correo no deseado, EOP incluye protección contra correo no deseado que usa tecnologías propietarias de filtrado de correo no deseado para identificar y separar el correo electrónico no deseado del correo electrónico legítimo. El filtrado de correo no deseado de EOP aprende de amenazas conocidas de spam y phishing y comentarios de los usuarios de nuestra plataforma de consumidores, Outlook.com. Los comentarios continuos de los usuarios de EOP que participan en el programa de clasificación de correo electrónico no deseado garantizan que las tecnologías de EOP estén en un proceso continuo de aprendizaje y mejora.

La configuración de antispam en EOP se compone de las siguientes tecnologías:

- **Filtrado de conexiones**: identifica los servidores de origen de correo electrónico correctos y incorrectos al principio de la conexión de correo electrónico entrante a través de la lista de direcciones IP permitidas, la lista de bloqueos IP y la *lista segura* (una lista dinámica pero no editable de remitentes de confianza mantenida por Microsoft). Estas opciones se configuran en la directiva de filtro de conexión. Obtenga más información en [Configuración del filtrado de conexiones](configure-the-connection-filter-policy.md).

- **Filtrado de correo no deseado (filtrado de contenido):** EOP usa los veredictos de filtrado de correo no deseado **Spam**, **spam de alta confianza**, **correo electrónico masivo**, **correo electrónico de phishing** y **correo electrónico de suplantación de identidad de alta confianza** para clasificar los mensajes. Puede configurar las acciones que se deben realizar en función de estos veredictos y puede configurar qué usuarios pueden hacer en los mensajes en cuarentena y si el usuario recibe notificaciones de cuarentena mediante [directivas de cuarentena](quarantine-policies.md). Para obtener más información, consulte [Configuración de directivas contra correo no deseado en Microsoft 365](configure-your-spam-filter-policies.md).

  > [!NOTE]
  > De forma predeterminada, el filtrado de correo no deseado está configurado para enviar mensajes marcados como correo no deseado a la carpeta de Email no deseado del destinatario. Sin embargo, en entornos híbridos donde EOP protege los buzones de Exchange locales, debe configurar dos reglas de flujo de correo (también conocidas como reglas de transporte) en la organización local de Exchange para reconocer los encabezados de correo no deseado de EOP que se agregan a los mensajes. Para obtener información, consulte [Configuración de un EOP para entregar el correo no deseado en la carpeta de correo no deseado en entornos híbridos](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).

- **Filtrado de correo no deseado saliente**: EOP también comprueba si los usuarios no envían correo no deseado, ya sea en el contenido del mensaje saliente o superando los límites de mensajes salientes. Para obtener más información, consulte [Configuración del filtrado de correo no deseado saliente en Microsoft 365](configure-the-outbound-spam-policy.md).

- **Inteligencia de suplantación de** identidad: para obtener más información, vea [Protección contra la suplantación de identidad en EOP](anti-spoofing-protection.md).

## <a name="manage-errors-in-spam-filtering"></a>Administración de errores en el filtrado de correo no deseado

Es posible que los mensajes buenos se puedan identificar como spam (también conocidos como falsos positivos) o que el correo no deseado se pueda entregar a la Bandeja de entrada (también conocido como falsos negativos). Puede usar las sugerencias de las secciones siguientes para averiguar lo que ocurrió y ayudar a evitar que suceda en el futuro.

Estos son algunos procedimientos recomendados que se aplican a cualquiera de los escenarios:

- Informe siempre de mensajes clasificados erróneamente a Microsoft. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

- **Examine los encabezados de mensajes antispam**: estos valores le indicarán por qué se marcó un mensaje como correo no deseado o por qué omitió el filtrado de correo no deseado. Para obtener más información, vea [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md).

- **Apunte su registro MX a Microsoft 365**: Para que EOP proporcione la mejor protección, siempre se recomienda que primero se envíe correo electrónico a Microsoft 365. Para obtener instrucciones, consulte [Creación de registros DNS en cualquier proveedor de hospedaje de DNS para Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

  Si el registro MX apunta a otra ubicación (por ejemplo, una solución o dispositivo antispam de terceros), es difícil que EOP proporcione un filtrado de correo no deseado preciso. En este escenario, debe configurar el filtrado mejorado para conectores (también conocido como _omitir lista_). Para obtener instrucciones, consulte [Filtrado mejorado para conectores en Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **Usar autenticación por correo electrónico**: si es propietario de un dominio de correo electrónico, puede usar DNS para ayudar a asegurarse de que los mensajes de los remitentes de ese dominio son legítimos. Para ayudar a evitar el correo no deseado y la suplantación de identidad no deseada en EOP, use todos los métodos de autenticación de correo electrónico siguientes:

  - **SPF**: el marco de directivas del remitente comprueba la dirección IP de origen del mensaje con el propietario del dominio de envío. Para obtener una introducción rápida a SPF y configurarlo rápidamente, consulte [Configuración de SPF para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Para comprender en detalle cómo Microsoft 365 usa SPF, o para la solución de problemas o las implementaciones no estándar (por ejemplo, implementaciones híbridas), comience con [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md) (Cómo Microsoft 365 usa el marco de directivas permanente [SPF] para evitar la suplantación de identidad).

  - **DKIM**: DomainKeys Identified Mail agrega una firma digital al encabezado de mensaje de los mensajes enviados desde el dominio. Para obtener información, consulte [Uso de DKIM para validar el correo electrónico saliente enviado desde el dominio personalizado en Microsoft 365](use-dkim-to-validate-outbound-email.md).

  - **DMARC**: La autenticación de mensajes basada en dominio, la generación de informes y la conformidad ayuda a los sistemas de correo electrónico de destino a determinar qué hacer con los mensajes que producen errores en las comprobaciones SPF o DKIM y proporciona otro nivel de confianza para los asociados de correo electrónico. Para obtener más información, vea [Usar DMARC para validar el correo electrónico en Microsoft 365](use-dmarc-to-validate-email.md).

- **Comprobar la configuración de correo electrónico masivo**: el umbral de nivel de queja masiva (BCL) que configura en las directivas contra correo no deseado determina si el correo electrónico masivo (también conocido como _correo gris_) está marcado como correo no deseado. La configuración de Solo PowerShell _MarkAsSpamBulkMail_ que está activada de forma predeterminada también contribuye a los resultados. Para obtener más información, consulte [Configuración de directivas contra correo no deseado en Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Impedir la entrega de correo no deseado a la Bandeja de entrada

- **Comprobar la configuración de la organización**: tenga cuidado con la configuración que permite que los mensajes omitan el filtrado de correo no deseado (por ejemplo, si agrega su propio dominio a la lista de dominios permitidos en las directivas contra correo no deseado). Para ver nuestra configuración recomendada, consulte [Configuración recomendada para EOP y seguridad de Microsoft Defender para Office 365](recommended-settings-for-eop-and-office365.md) y [Creación de listas de remitentes seguros](create-safe-sender-lists-in-office-365.md).

- **Usar las listas de remitentes bloqueados disponibles**: para obtener información, consulte [Creación de listas de remitentes bloqueados](create-block-sender-lists-in-office-365.md).

- **Cancelación de la suscripción al correo electrónico masivo** Si el mensaje era algo que el usuario se registró (boletines, anuncios de productos, etc.) y contiene un vínculo de cancelación de suscripción de una fuente de confianza, considere la posibilidad de pedirle simplemente cancelar la suscripción.

- **EOP independiente: cree reglas de flujo de correo en exchange local para veredictos de filtrado de correo no deseado de EOP**: en entornos híbridos donde EOP protege buzones de Exchange locales, debe configurar reglas de flujo de correo (también conocidas como reglas de transporte) en Exchange local. Estas reglas de flujo de correo traducen el veredicto de filtrado de correo no deseado de EOP para que la regla de correo no deseado del buzón pueda mover el mensaje a la carpeta De correo no deseado Email. Para obtener información, consulte [Configuración de un EOP para entregar el correo no deseado en la carpeta de correo no deseado en entornos híbridos](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Impedir que se identifique un correo electrónico correcto como correo no deseado

Estos son algunos pasos que puede seguir para ayudar a evitar falsos positivos:

- **Compruebe la configuración del filtro de Email no deseado de Outlook del usuario**:

  - **Compruebe que el filtro de Email no deseado de Outlook está deshabilitado**: cuando el filtro de Email no deseado de Outlook está establecido en el valor predeterminado **Sin filtrado automático**, Outlook no intenta clasificar los mensajes como correo no deseado.  Cuando se establece en **Bajo** o **Alto**, el Filtro de Email basura de Outlook usa su propia tecnología de filtro SmartScreen para identificar y mover el correo no deseado a la carpeta de Email de correo no deseado, de modo que pueda obtener falsos positivos. Tenga en cuenta que Microsoft dejó de producir actualizaciones de definición de correo no deseado para los filtros SmartScreen en Exchange y Outlook en noviembre de 2016. Las definiciones de correo no deseado de SmartScreen existentes se dejaron en su lugar, pero su eficacia probablemente se degradará con el tiempo.

  - **Compruebe que la opción "Solo listas seguras" de Outlook está deshabilitada**: cuando esta opción está habilitada, solo se entregan a la Bandeja de entrada los mensajes de remitentes de la lista de remitentes seguros del usuario o de destinatarios seguros; el correo electrónico de todos los demás se mueve automáticamente a la carpeta de Email no deseado.

  Para obtener más información sobre esta configuración, consulte [Configuración de las opciones de correo no deseado en Exchange Online buzones de Correo en Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Usar las listas de remitentes seguros disponibles**: para obtener información, consulte [Creación de listas de remitentes seguros](create-safe-sender-lists-in-office-365.md).

- **Compruebe que los usuarios están dentro de los límites de envío y recepción**, como se describe en [Recepción y envío de límites](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) en la descripción del servicio Exchange Online.

- **EOP independiente: use la sincronización de directorios**: si usa EOP independiente para ayudar a proteger su organización de Exchange local, debe sincronizar la configuración de usuario con el servicio mediante la sincronización de directorios. De esta forma, se asegura de que EOP respeta las listas de remitentes seguros de los usuarios. Para obtener más información, consulte [utilizar la sincronización de directorios para administrar usuarios de correo](/exchange/standalone-eop/manage-mail-users-in-eop#synchronize-directories-with-azure-active-directory-connect-aad-connect).

## <a name="anti-spam-legislation"></a>Legislación contra el correo no deseado

En Microsoft, creemos que el desarrollo de nuevas tecnologías y autorregulación requiere el apoyo de marcos jurídicos y políticas gubernamentales eficaces. La proliferación mundial de correo no deseado ha impulsado a numerosos órganos legislativos a regular el correo electrónico comercial. Muchos países ahora tienen leyes de lucha contra correo no deseado en vigor. El Estados Unidos tiene leyes federales y estatales que rigen el correo no deseado, y este enfoque complementario está ayudando a reducir el spam al tiempo que permite que el comercio electrónico legítimo prospere. La Ley CAN-SPAM amplía las herramientas disponibles para poner freno a los mensajes de correo electrónico fraudulentos y engañosos.
