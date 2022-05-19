---
title: Introducción a los vínculos Caja fuerte completos para Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
ms.date: 09/08/2021
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: Obtenga información sobre la protección de vínculos de Caja fuerte en Defender para Office 365 para proteger una organización contra suplantación de identidad (phishing) y otros ataques que usan direcciones URL malintencionadas. Descubra Teams Caja fuerte Vínculos y vea los gráficos de los mensajes de vínculos de Caja fuerte.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0aef211b91ef406926720f8c50e4af457d07eaab
ms.sourcegitcommit: e624221597480295b799d56568c4f6f56d40b41d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2022
ms.locfileid: "65535116"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>vínculos de Caja fuerte en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](defender-for-office-365.md). Si usa Outlook.com, Microsoft 365 Familia o Microsoft 365 Personal y busca información sobre Safelinks en Outlook, consulte [Seguridad avanzada de Outlook.com](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Caja fuerte Vínculos es una característica de [Defender para Office 365](defender-for-office-365.md) que proporciona examen de direcciones URL y reescritura de mensajes de correo electrónico entrantes en el flujo de correo, y la comprobación del tiempo de clic de direcciones URL y vínculos en mensajes de correo electrónico y otras ubicaciones. Caja fuerte análisis de vínculos se produce además del [antispam](anti-spam-protection.md) y [antimalware](anti-malware-protection.md) normales en los mensajes de correo electrónico entrantes en Exchange Online Protection (EOP). El examen de vínculos seguros puede ayudar a proteger a su organización de vínculos malintencionados que se usan en la suplantación de identidad (phishing) y otros ataques.

La protección de vínculos seguros está disponible en las siguientes ubicaciones:

- **Mensajes de correo electrónico**: aunque no hay ninguna directiva de vínculos de Caja fuerte predeterminada, la directiva de seguridad preestablecida **de protección integrada** proporciona Caja fuerte Protección de vínculos a todos los destinatarios (usuarios que no están definidos en directivas personalizadas de vínculos de Caja fuerte). Para obtener más información, vea [Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md). También puede crear directivas de vínculos Caja fuerte que se apliquen a usuarios, grupos o dominios específicos. Para obtener instrucciones, consulte [Configurar directivas de vínculos de Caja fuerte en Microsoft Defender para Office 365](set-up-safe-links-policies.md).

  Para obtener más información sobre Caja fuerte Protección de vínculos para mensajes de correo electrónico, consulte la sección [configuración de vínculos de Caja fuerte para mensajes de correo electrónico](#safe-links-settings-for-email-messages) más adelante en este artículo.
  
  > [!NOTE]
  > Caja fuerte Vínculos no funciona en carpetas públicas habilitadas para correo.
  >
  > Caja fuerte Links solo admite formatos HTTP(S) y FTP.

- **Microsoft Teams**: la protección de vínculos seguros para vínculos en conversaciones de Teams, chats de grupo o desde canales también se controla mediante directivas de vínculos seguros.

  Para obtener más información sobre la protección de vínculos de Caja fuerte en Teams, consulte la sección [configuración de vínculos de Caja fuerte para Microsoft Teams](#safe-links-settings-for-microsoft-teams) más adelante en este artículo.

- **Aplicaciones de Office 365**: la protección de vínculos seguros para aplicaciones de Office 365 está disponible en aplicaciones de escritorio, móviles y web compatibles. La protección de vínculos de Caja fuerte se **configura** para las aplicaciones de Office 365 en la configuración global que están **fuera** de las directivas de vínculos de Caja fuerte. Para obtener instrucciones, consulte [Configuración global de los valores de vínculos de Caja fuerte en Microsoft Defender para Office 365](configure-global-settings-for-safe-links.md).

  Protección de vínculos seguros para las aplicaciones de Office 365 se aplica a todos los usuarios de la organización con licencia de Defender para Office 365, independientemente de si los usuarios están incluidos en las directivas activas de vínculos seguros o no.

  Para obtener más información sobre la protección de vínculos de Caja fuerte en aplicaciones Office 365, consulte la sección [Configuración de vínculos de Caja fuerte para aplicaciones Office 365](#safe-links-settings-for-office-365-apps) más adelante en este artículo.

En este artículo se incluyen descripciones detalladas de los siguientes tipos de configuración de vínculos de Caja fuerte:

- **Configuración en las directivas de vínculos de Caja fuerte**: esta configuración solo se aplica a los usuarios que se incluyen en las directivas específicas, y la configuración puede ser diferente entre las directivas. Entre estas opciones se incluyen:

  - [Caja fuerte Configuración de vínculos para mensajes de correo electrónico](#safe-links-settings-for-email-messages)
  - [Configuración de vínculos seguros para Microsoft Teams](#safe-links-settings-for-microsoft-teams)
  - [Listas de "No volver a escribir las siguientes direcciones URL" en las directivas de vínculos de Caja fuerte](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **Configuración global de vínculos de Caja fuerte**: esta configuración se configura globalmente, no en las directivas de vínculos de Caja fuerte. Entre estas opciones se incluyen:

  - [configuración de vínculos de Caja fuerte para aplicaciones de Office 365](#safe-links-settings-for-office-365-apps)
  - [Lista "Bloquear las siguientes direcciones URL" para vínculos de Caja fuerte](#block-the-following-urls-list-for-safe-links)

En la tabla siguiente se describen escenarios de vínculos de Caja fuerte en organizaciones Microsoft 365 y Office 365 que incluyen Defender para Office 365 (tenga en cuenta que la falta de licencias nunca es un problema en los ejemplos).

|Escenario|Resultado|
|---|---|
|Jean es miembro del departamento de marketing. Caja fuerte La protección de vínculos para aplicaciones Office 365 está activada en la configuración global de Caja fuerte Links y existe una directiva de vínculos de Caja fuerte que se aplica a los miembros del departamento de marketing. Jean abre una presentación PowerPoint en un mensaje de correo electrónico y, a continuación, hace clic en una dirección URL en la presentación.|Jean está protegido por Caja fuerte Links. <p> Jean está incluido en una directiva de vínculos de Caja fuerte y Caja fuerte la protección de vínculos para aplicaciones Office 365 está activada. <p> Para obtener más información sobre los requisitos para la protección de vínculos de Caja fuerte en aplicaciones Office 365, consulte la sección [Configuración de vínculos de Caja fuerte para aplicaciones Office 365](#safe-links-settings-for-office-365-apps) más adelante en este artículo.|
|La organización Microsoft 365 E5 de Chris no tiene configuradas directivas de vínculos de Caja fuerte. Chris recibe un correo electrónico de un remitente externo que contiene una dirección URL a un sitio web malintencionado en el que, en última instancia, hace clic.|Chris no está protegido por Caja fuerte Links. <p> Un administrador debe crear al menos una directiva de vínculos de Caja fuerte para que cualquier usuario obtenga Caja fuerte protección de vínculos en los mensajes de correo electrónico entrantes. Chris debe incluirse en las condiciones de la directiva para obtener Caja fuerte protección de vínculos.|
|En la organización de Pat, ningún administrador ha creado ninguna directiva de vínculos de Caja fuerte, pero Caja fuerte la protección de vínculos para aplicaciones Office 365 está activada. Pat abre un documento de Word y hace clic en una dirección URL en el archivo.|Pat no está protegido por Caja fuerte Vínculos. <p> Aunque la protección de vínculos de Caja fuerte para aplicaciones Office 365 está activada globalmente, Pat no se incluye en ninguna directiva activa de vínculos Caja fuerte, por lo que no se puede aplicar la protección.|
|En la organización de Lee, `https://tailspintoys.com` se configura en la lista **Bloquear las siguientes direcciones URL** en la configuración global de Caja fuerte Vínculos. Ya existe una directiva de vínculos de Caja fuerte que incluye Lee. Lee recibe un mensaje de correo electrónico que contiene la dirección URL `https://tailspintoys.com/aboutus/trythispage`. Lee hace clic en la dirección URL.|Es posible que la dirección URL se bloquee automáticamente para Lee; depende de la entrada de dirección URL de la lista y del cliente de correo electrónico que usó Lee. Para obtener más información, consulte la [lista "Bloquear las siguientes direcciones URL" para Caja fuerte sección Vínculos](#block-the-following-urls-list-for-safe-links) más adelante en este artículo.|
|Jamie y Julia trabajan para contoso.com. Hace mucho tiempo, los administradores configuraron Caja fuerte directivas de vínculos que se aplican tanto a Jamie como a Julia. Jamie envía un correo electrónico a Julia, sin saber que el correo electrónico contiene una dirección URL malintencionada.|Julia está protegida por Caja fuerte Links **si** la directiva de vínculos de Caja fuerte que se aplica a ella está configurada para aplicarse a los mensajes entre destinatarios internos. Para obtener más información, consulte la sección [configuración de vínculos de Caja fuerte para mensajes de correo electrónico](#safe-links-settings-for-email-messages) más adelante en este artículo.|

## <a name="safe-links-settings-for-email-messages"></a>Caja fuerte Configuración de vínculos para mensajes de correo electrónico

Vínculos seguros examina el correo electrónico entrante en busca de hipervínculos malintencionados conocidos. Las direcciones URL examinadas se vuelven a escribir con el prefijo de dirección URL estándar de Microsoft: `https://nam01.safelinks.protection.outlook.com`. Después de reescribir el vínculo, se analiza en busca de contenido potencialmente malintencionado.

Después de Caja fuerte Links reescriba una dirección URL, la dirección URL permanece reescrita incluso si el mensaje se reenvía o responde _manualmente_ a (tanto a destinatarios internos como externos). Los vínculos adicionales que se agregan al mensaje reenviado o respondido no se vuelven a escribir. Sin embargo, en el caso del reenvío _automático_ por reglas de bandeja de entrada o reenvío SMTP, la dirección URL no se volverá a escribir en el mensaje destinado al destinatario final _a menos_ que ese destinatario también esté protegido por Caja fuerte Vínculos o que la dirección URL ya se haya reescrito en una comunicación anterior. Siempre que Caja fuerte Vínculos esté habilitado, las direcciones URL se seguirán analizando antes de la entrega, independientemente de si se han reescrito o no. Las direcciones URL no coronadas también se comprobarán mediante una llamada API del lado cliente a Caja fuerte Vínculos en el momento de hacer clic en Outlook para desktop versión 16.0.12513 o posterior.

La configuración de las directivas de vínculos de Caja fuerte que se aplican a los mensajes de correo electrónico se describe en la lista siguiente:

- **Activado: Caja fuerte Vínculos comprueba una lista de vínculos malintencionados conocidos cuando los usuarios hacen clic en vínculos en el correo electrónico**: habilita o deshabilita el examen de vínculos Caja fuerte en los mensajes de correo electrónico. El valor recomendado está seleccionado (activado) y da como resultado las siguientes acciones:
  - el examen de vínculos de Caja fuerte está habilitado en Outlook (C2R) en Windows.
  - Las direcciones URL se vuelven a escribir y los usuarios se enrutan a través de Caja fuerte Protección de vínculos al hacer clic en direcciones URL en los mensajes.
  - Cuando se hace clic en ellas, las direcciones URL se comprueban en una lista de direcciones URL malintencionadas conocidas y en la [lista "Bloquear las siguientes direcciones URL"](#block-the-following-urls-list-for-safe-links).
  - Las direcciones URL que no tienen una reputación válida se detonan de forma asincrónica en segundo plano.

  La siguiente configuración solo está disponible si el examen de vínculos de Caja fuerte está activado en los mensajes de correo electrónico:

  - **Aplicar Caja fuerte Vínculos a los mensajes de correo electrónico enviados dentro de la organización**: habilita o deshabilita el examen de vínculos de Caja fuerte en los mensajes enviados entre remitentes internos y destinatarios internos dentro de la misma organización Exchange Online. El valor recomendado está seleccionado (activado).

  - **Aplicar el examen de direcciones URL en tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos**: habilita el examen en tiempo real de vínculos, incluidos los vínculos en mensajes de correo electrónico que apuntan a contenido descargable. El valor recomendado está seleccionado (activado).

  - **Espere a que se complete el examen de direcciones URL antes de entregar el mensaje**:
    - Seleccionado (activado): los mensajes que contienen direcciones URL se mantienen hasta que finaliza el examen. Los mensajes se entregan solo después de confirmar que las direcciones URL son seguras. Este es el valor recomendado.
    - No seleccionado (desactivado): si el examen de direcciones URL no se puede completar, entregue el mensaje de todos modos.

  - **No vuelva a escribir direcciones URL, realice comprobaciones solo a través de safeLinks API**: si esta configuración está habilitada, no se produce ningún ajuste de direcciones URL. Caja fuerte Vínculos se llama exclusivamente a través de las API en el momento de hacer clic en la dirección URL Outlook clientes que lo admiten. El valor de recomendación está deshabilitado.

- **Realizar un seguimiento de los clics del usuario**: habilita o deshabilita el almacenamiento de datos de clic de vínculos Caja fuerte para las direcciones URL en las que se ha hecho clic en los mensajes de correo electrónico. El valor recomendado es dejar esta configuración seleccionada (realizar un seguimiento de los clics del usuario).

  Actualmente no se admite el seguimiento de clics en direcciones URL para vínculos en mensajes de correo electrónico enviados entre remitentes internos y destinatarios internos.

- **Permitir que los usuarios haga clic en la dirección URL original**: permite o impide que los usuarios haga clic en la [página de advertencia](#warning-pages-from-safe-links) a la dirección URL original. El valor de recomendación está deshabilitado.

- **Mostrar la personalización de marca de la organización en las páginas de notificación y advertencia**: esta opción muestra la personalización de marca de la organización en las páginas de advertencia. La personalización de marca ayuda a los usuarios a identificar advertencias legítimas, ya que los atacantes suelen usar las páginas de advertencia predeterminadas de Microsoft. Para obtener más información sobre la personalización de marca personalizada, consulte [Personalización del tema de Microsoft 365 para su organización](../../admin/setup/customize-your-organization-theme.md).

  Para obtener más información sobre los valores recomendados para la configuración de directivas estándar y estricta para las directivas de vínculos de Caja fuerte, consulte [configuración de directivas de vínculos de Caja fuerte](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).

- **Filtros de destinatario**: debe especificar las condiciones y excepciones del destinatario que determinan a quién se aplica la directiva. Puede usar estas propiedades para condiciones y excepciones:
  - **El destinatario es**
  - **El dominio de destinatario es**
  - **El destinatario es un miembro de**

  Solo puede usar una condición o una excepción una vez, pero la condición o la excepción pueden contener varios valores. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

- **Prioridad**: si crea varias directivas, puede especificar el orden en que se aplican. Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

  Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).
  
### <a name="how-safe-links-works-in-email-messages"></a>Funcionamiento de los vínculos Caja fuerte en los mensajes de correo electrónico

En un nivel alto, aquí se muestra cómo funciona la protección de vínculos de Caja fuerte en las direcciones URL de los mensajes de correo electrónico:

1. Todo el correo electrónico pasa por EOP, donde el protocolo de Internet (IP) y los filtros de sobre, protección contra malware basada en firmas, filtros contra correo no deseado y antimalware antes de que el mensaje se entregue al buzón del destinatario.

2. El usuario abre el mensaje en su buzón y hace clic en una dirección URL del mensaje.

3. Caja fuerte Vínculos comprueba inmediatamente la dirección URL antes de abrir el sitio web:

   - Si la dirección URL se incluye en la lista **Bloquear las siguientes direcciones URL** , se abre una [advertencia de dirección URL bloqueada](#blocked-url-warning) .

   - Si la dirección URL apunta a un sitio web que se ha determinado que es malintencionado, se abre una página de [advertencia de sitio web malintencionado](#malicious-website-warning) (o una página de advertencia diferente).

   - Si la dirección URL apunta a un archivo descargable y la opción Aplicar examen de **direcciones URL en tiempo real en busca de vínculos sospechosos que apuntan a archivos** está habilitada en la directiva que se aplica al usuario, se comprueba el archivo descargable.

   - Si se determina que la dirección URL es segura, se abre el sitio web.

## <a name="safe-links-settings-for-microsoft-teams"></a>Configuración de vínculos seguros para Microsoft Teams

Puede habilitar o deshabilitar la protección de vínculos seguros para Microsoft Teams en las directivas de vínculos seguros. En concreto, se usa **la opción Seleccionar la acción para direcciones URL desconocidas o potencialmente malintencionadas dentro de Microsoft Teams** configuración. El valor recomendado es **On**.

> [!NOTE]
> Al activar o desactivar Caja fuerte protección de vínculos para Teams, el cambio puede tardar hasta 24 horas en surtir efecto.

La siguiente configuración de Caja fuerte Las directivas de vínculos que se aplican a los vínculos de mensajes de correo electrónico también se aplican a los vínculos de Teams:

- **Aplicar el examen de direcciones URL en tiempo real en busca de vínculos y vínculos sospechosos que apunten a archivos**
- **No hacer seguimiento de los clics de los usuarios**
- **No permitir que los usuarios hagan clic en la dirección URL original**

Esta configuración se explica anteriormente en [Caja fuerte Configuración de vínculos para mensajes de correo electrónico](#safe-links-settings-for-email-messages).

Después de activar la protección de vínculos seguros para Microsoft Teams, las direcciones URL de Teams se comprueban en una lista de vínculos malintencionados conocidos cuando el usuario protegido hace clic en el vínculo (protección al hacer clic). Las direcciones URL no se reescriben. Si se detecta que un vínculo es malintencionado, los usuarios tendrán las siguientes experiencias:

- Si se hizo clic en el vínculo en una conversación de Teams, chat en grupo o desde canales, la página de advertencia como se muestra en la captura de pantalla siguiente aparecerá en el explorador web predeterminado.
- Si se hizo clic en el vínculo desde una pestaña anclada, la página de advertencia aparecerá en la interfaz de Teams de la pestaña. La opción para abrir el vínculo en un explorador web está deshabilitada por motivos de seguridad.
- Dependiendo de cómo se establezca la configuración **No permitir que los usuarios hagan clic en la dirección URL original** de la directiva, el usuario podrá o no podrá hacer clic en la dirección URL original (**Continuar de todos modos (no recomendado)** en la captura de pantalla). Se recomienda habilitar la opción **No permitir que los usuarios hagan clic en la dirección URL original para** que los usuarios no puedan hacer clic en la dirección URL original.

Si el usuario que envió el vínculo no está incluido en una directiva de vínculos seguros donde está habilitada la protección de Teams, el usuario puede hacer clic en la dirección URL original en su equipo o dispositivo.

:::image type="content" source="../../media/tp-safe-links-for-teams-malicious.png" alt-text="Una páginas de vínculos seguros para Teams que informa de un vínculo malintencionado" lightbox="../../media/tp-safe-links-for-teams-malicious.png":::

Al hacer clic en el botón **Volver** de la página de advertencia, el usuario volverá a su contexto o ubicación URL original. Sin embargo, al volver a hacer clic en el vínculo original, los vínculos seguros volverán a examinar la dirección URL, por lo que la página de advertencia volverá a aparecer.

### <a name="how-safe-links-works-in-teams"></a>Cómo funcionan los vínculos seguros en Teams

En un nivel alto, aquí se muestra cómo funciona la protección de vínculos seguros para direcciones URL en Microsoft Teams:

1. Un usuario inicia la aplicación Teams.

2. Microsoft 365 comprueba que la organización del usuario incluye Microsoft Defender para Office 365 y que el usuario se incluye en una directiva de vínculos seguros activa en la que la protección de Microsoft Teams está habilitada.

3. Las direcciones URL se validan al hacer clic para el usuario en chats, chats de grupo, canales y pestañas.

## <a name="safe-links-settings-for-office-365-apps"></a>configuración de vínculos de Caja fuerte para aplicaciones de Office 365

Caja fuerte Protección de vínculos para aplicaciones de Office 365 comprueba los vínculos de Office documentos, no los vínculos en los mensajes de correo electrónico (pero puede comprobar los vínculos en los documentos adjuntos Office en los mensajes de correo electrónico después de abrir el documento).

Caja fuerte La protección de vínculos para aplicaciones de Office 365 tiene los siguientes requisitos de cliente:

- Aplicaciones Microsoft 365 o Microsoft 365 Empresa Premium.
  - Versiones actuales de Word, Excel y PowerPoint en Windows, Mac o en un explorador web.
  - Office aplicaciones en dispositivos iOS o Android.
  - Visio en Windows.
  - OneNote en un explorador web.
  - Outlook para Windows al abrir archivos EML o MSG guardados.

- Office 365 aplicaciones están configuradas para usar la autenticación moderna. Para obtener más información, consulte Funcionamiento de la [autenticación moderna para las aplicaciones cliente de Office 2013, Office 2016 y Office 2019](../../enterprise/modern-auth-for-office-2013-and-2016.md).

- Los usuarios han iniciado sesión con sus cuentas profesionales o educativas. Para obtener más información, consulte [Inicio de sesión en Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).

La protección de vínculos de Caja fuerte se configura para las aplicaciones de Office 365 en la configuración global de vínculos de Caja fuerte, no en las directivas de vínculos de Caja fuerte. La protección se aplica a todos los usuarios de la organización que tienen licencia para Defender para Office 365, independientemente de si los usuarios están incluidos en las directivas activas de vínculos de Caja fuerte o no.

La siguiente configuración de vínculos de Caja fuerte está disponible para las aplicaciones de Office 365:

- **Office 365 aplicaciones**: habilita o deshabilita el examen de vínculos de Caja fuerte en aplicaciones Office 365 compatibles. El valor predeterminado y recomendado es **Activado**.

- **No realizar un seguimiento cuando los usuarios hacen clic en vínculos de Caja fuerte**: habilita o deshabilita el almacenamiento de Caja fuerte los datos de clic de vínculos para las direcciones URL en las que se ha hecho clic en las versiones de escritorio de Word, Excel, PowerPoint y Visio. El valor recomendado es **Desactivado**, lo que significa que se realiza un seguimiento de los clics del usuario.

- **No permitir que los usuarios hagan clic a través de vínculos seguros a la dirección URL original**: permite o impide que los usuarios hagan clic en la [página de advertencia](#warning-pages-from-safe-links) a la dirección URL original en las versiones de escritorio de Word, Excel, PowerPoint y Visio. El valor predeterminado y recomendado es **Activado**.

Para configurar los valores de vínculos de Caja fuerte para aplicaciones de Office 365, consulte [Configuración de la protección de vínculos de Caja fuerte para aplicaciones de Office 365](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-microsoft-365-defender-portal).

Para obtener más información sobre los valores recomendados para la configuración de directiva estándar y estricta, consulte [Configuración global para vínculos de Caja fuerte](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links).

### <a name="how-safe-links-works-in-office-365-apps"></a>Funcionamiento de Caja fuerte Links en aplicaciones de Office 365

En un nivel alto, aquí se muestra cómo funciona la protección de vínculos de Caja fuerte para las direcciones URL de Office 365 aplicaciones. Las aplicaciones de Office 365 admitidas se describen en la sección anterior.

1. Un usuario inicia sesión con su cuenta profesional o educativa en una organización que incluye Aplicaciones Microsoft 365 o Microsoft 365 Empresa Premium.

2. El usuario abre y hace clic en un vínculo a un documento de Office en un Aplicación de Office compatible.

3. Caja fuerte Vínculos comprueba inmediatamente la dirección URL antes de abrir el sitio web de destino:

   - Si la dirección URL se incluye en la lista que omite Caja fuerte examen de vínculos (la lista **Bloquear las siguientes direcciones URL**), se abre una página de [advertencia de dirección URL bloqueada](#blocked-url-warning).

   - Si la dirección URL apunta a un sitio web que se ha determinado que es malintencionado, se abre una página de [advertencia de sitio web malintencionado](#malicious-website-warning) (o una página de advertencia diferente).

   - Si la dirección URL apunta a un archivo descargable y la directiva de vínculos de Caja fuerte que se aplica al usuario está configurada para examinar vínculos al contenido descargable (**Aplicar examen de direcciones URL en tiempo real para vínculos sospechosos y vínculos que apunten a archivos**), se comprueba el archivo descargable.

   - Si la dirección URL se considera segura, el usuario se lleva al sitio web.

   - Si Caja fuerte no se puede completar el examen de vínculos, no se desencadena la protección de vínculos de Caja fuerte. En Office clientes de escritorio, se advertirá al usuario antes de continuar con el sitio web de destino.

> [!NOTE]
> Al principio de cada sesión, el usuario puede tardar varios segundos en comprobar que el usuario tiene habilitados Caja fuerte Vínculos para Office.

## <a name="block-the-following-urls-list-for-safe-links"></a>Lista "Bloquear las siguientes direcciones URL" para vínculos de Caja fuerte

La lista **Bloquear las siguientes direcciones URL** define los vínculos que siempre están bloqueados por Caja fuerte Análisis de vínculos en las siguientes ubicaciones:

- Mensajes de correo electrónico
- Documentos en aplicaciones de Office 365 en Windows y Mac.
- Documentos en Office para iOS y Android.

Cuando un usuario de una directiva activa de vínculos de Caja fuerte hace clic en un vínculo bloqueado en una aplicación compatible, se le lleva a la página [de advertencia url bloqueada](#blocked-url-warning).

La lista de direcciones URL se configura en la configuración global de vínculos Caja fuerte. Para obtener instrucciones, consulte [Configurar la lista "Bloquear las siguientes direcciones URL"](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-microsoft-365-defender-portal).

**Notas**:

- Para obtener una lista verdaderamente universal de direcciones URL que están bloqueadas en todas partes, consulte [Administrar la lista de permitidos o bloqueados de inquilinos](tenant-allow-block-list.md).
- Límites de la lista **Bloquear las siguientes direcciones URL** :
  - El número máximo de entradas es 500.
  - La longitud máxima de una entrada es de 128 caracteres.
  - Todas las entradas no pueden superar los 10 000 caracteres.
- No incluya una barra diagonal (`/`) al final de la dirección URL. Por ejemplo, use `https://www.contoso.com`, no `https://www.contoso.com/`.
- Una dirección URL de solo dominio (por ejemplo `contoso.com` , o `tailspintoys.com`) bloqueará cualquier dirección URL que contenga el dominio.
- Puede bloquear un subdominio sin bloquear el dominio completo. Por ejemplo, `toys.contoso.com*` bloquea cualquier dirección URL que contenga el subdominio, pero no bloquea las direcciones URL que contienen el dominio `contoso.com`completo.
- Puede incluir hasta tres caracteres comodín (`*`) por entrada de dirección URL.

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>Sintaxis de entrada para la lista "Bloquear las siguientes direcciones URL"

En la tabla siguiente se describen ejemplos de los valores que puede especificar y sus resultados:

|Valor|Resultado|
|---|---|
|`contoso.com` <p> o <p> `*contoso.com*`|Bloquea el dominio, los subdominios y las rutas de acceso. Por ejemplo, `https://www.contoso.com`, `https://sub.contoso.com`y `https://contoso.com/abc` están bloqueados.|
|`https://contoso.com/a`|Bloquea `https://contoso.com/a` , pero no sube rutas secundarias adicionales como `https://contoso.com/a/b`.|
|`https://contoso.com/a*`|Bloques `https://contoso.com/a` y rutas secundarias adicionales como `https://contoso.com/a/b`.|
|`https://toys.contoso.com*`|Bloquea un subdominio (`toys` en este ejemplo), pero permite hacer clic en otras direcciones URL de dominio (como `https://contoso.com` o `https://home.contoso.com`).|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>Listas de "No volver a escribir las siguientes direcciones URL" en las directivas de vínculos de Caja fuerte

> [!NOTE]
> Si su organización usa directivas de vínculos de Caja fuerte, las listas **No volver a escribir las siguientes direcciones URL** son el único método admitido para las pruebas de suplantación de identidad de terceros.

Cada directiva de vínculos de Caja fuerte contiene una lista **No volver a escribir las siguientes direcciones URL** que puede usar para especificar direcciones URL que no se reescriban mediante el examen de vínculos de Caja fuerte. En otras palabras, la lista permite a los usuarios incluidos en la directiva acceder a las direcciones URL especificadas que, de lo contrario, Caja fuerte Links bloquearían. Puede configurar diferentes listas en diferentes directivas de vínculos de Caja fuerte. El procesamiento de directivas se detiene después de que se aplique al usuario la primera directiva (probablemente, la prioridad más alta). Por lo tanto, solo se aplica una opción **No volver a escribir la siguiente lista de direcciones URL** a un usuario que se incluye en varias directivas activas de vínculos de Caja fuerte.

Para agregar entradas a la lista en directivas de vínculos de Caja fuerte nuevas o existentes, consulte [Crear directivas de vínculos Caja fuerte](set-up-safe-links-policies.md#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) o [Modificar directivas de vínculos Caja fuerte](set-up-safe-links-policies.md#use-the-microsoft-365-defender-portal-to-modify-safe-links-policies).

**Notas**:

- Los clientes siguientes no reconocen las listas **No volver a escribir las siguientes direcciones URL** en las directivas de vínculos de Caja fuerte. Se puede impedir que los usuarios incluidos en las directivas accedan a las direcciones URL en función de los resultados del examen de vínculos de Caja fuerte en estos clientes:
  - Microsoft Teams
  - aplicaciones web de Office

  Para obtener una lista verdaderamente universal de direcciones URL que se permiten en todas partes, consulte [Administrar la lista de permitidos o bloqueados de inquilinos](tenant-allow-block-list.md). Sin embargo, tenga en cuenta que las direcciones URL agregadas no se excluirán de la reescritura de vínculos de Caja fuerte, como debe hacerse en una directiva de vínculos de Caja fuerte.

- Considere la posibilidad de agregar direcciones URL internas de uso frecuente a la lista para mejorar la experiencia del usuario. Por ejemplo, si tiene servicios locales, como Skype Empresarial o SharePoint, puede agregar esas direcciones URL para excluirlas del examen.
- Si ya tiene **no volver a escribir las siguientes entradas de direcciones URL** en las directivas de vínculos de Caja fuerte, asegúrese de revisar las listas y agregar caracteres comodín según sea necesario. Por ejemplo, la lista tiene una entrada como `https://contoso.com/a` y, más adelante, decide incluir subpaths como `https://contoso.com/a/b`. En lugar de agregar una nueva entrada, agregue un carácter comodín a la entrada existente para que se convierta en `https://contoso.com/a/*`.
- Puede incluir hasta tres caracteres comodín (`*`) por entrada de dirección URL. Los caracteres comodín incluyen explícitamente prefijos o subdominios. Por ejemplo, la entrada `contoso.com` no es la misma `*.contoso.com/*`que , porque `*.contoso.com/*` permite a los usuarios visitar subdominios y rutas de acceso en el dominio especificado.
- Si una dirección URL usa el redireccionamiento automático para HTTP a HTTPS (por ejemplo, redirección 302 para `http://www.contoso.com` `https://www.contoso.com`) e intenta escribir entradas HTTP y HTTPS para la misma dirección URL en la lista, es posible que observe que la segunda entrada url reemplaza a la primera entrada de dirección URL. Este comportamiento no se produce si las versiones HTTP y HTTPS de la dirección URL son completamente independientes.
- No especifique http:// ni https:// (es decir, contoso.com) para excluir las versiones HTTP y HTTPS.
- `*.contoso.com`**no** cubre contoso.com, por lo que tendría que excluir ambos para cubrir tanto el dominio especificado como los dominios secundarios.
- `contoso.com/*`**cubre solo** contoso.com, por lo que no es necesario excluir tanto `contoso.com` y `contoso.com/*`; bastaría`contoso.com/*`.
- Para excluir todas las iteraciones de un dominio, se necesitan dos entradas de exclusión; `contoso.com/*` y `*.contoso.com/*`. Se combinan para excluir HTTP y HTTPS, el dominio principal contoso.com y los dominios secundarios, así como cualquier parte final (por ejemplo, se cubren contoso.com y contoso.com/vdir1).

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>Sintaxis de entrada para la lista "No volver a escribir las siguientes direcciones URL"

En la tabla siguiente se describen ejemplos de los valores que puede especificar y sus resultados:

|Valor|Resultado|
|---|---|
|`contoso.com`|Permite el acceso a `https://contoso.com` subdominios o rutas de acceso, pero no a ellos.|
|`*.contoso.com/*`|Permite el acceso a un dominio, subdominios y rutas de acceso (por ejemplo, `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`o `https://www.contoso.com/a`). <p> Esta entrada es intrínsecamente mejor que `*contoso.com*`, porque no permite sitios potencialmente fraudulentos, como `https://www.falsecontoso.com` o `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Permite el acceso a `https://contoso.com/a`, pero no a rutas secundarias como `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Permite el acceso a `https://contoso.com/a` rutas secundarias y como `https://contoso.com/a/b`|

## <a name="warning-pages-from-safe-links"></a>Páginas de advertencia de vínculos de Caja fuerte

Esta sección contiene ejemplos de las distintas páginas de advertencia desencadenadas por Caja fuerte Protección de vínculos al hacer clic en una dirección URL.

Tenga en cuenta que se han actualizado varias páginas de advertencia. Si aún no ve las páginas actualizadas, pronto lo hará. Las páginas actualizadas incluyen una nueva combinación de colores, más detalles y la capacidad de continuar con un sitio a pesar de las advertencias y recomendaciones dadas.

### <a name="scan-in-progress-notification"></a>Notificación de examen en curso

Los vínculos Caja fuerte examinan la dirección URL en la que se ha hecho clic. Es posible que tenga que esperar unos instantes antes de volver a intentar el vínculo.

:::image type="content" source="../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png" alt-text="La notificación de que el vínculo se está analizando" lightbox="../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png":::

La página de notificación original tenía este aspecto:

:::image type="content" source="../../media/04368763-763f-43d6-94a4-a48291d36893.png" alt-text="Se está analizando la notificación del vínculo" lightbox="../../media/04368763-763f-43d6-94a4-a48291d36893.png":::

### <a name="suspicious-message-warning"></a>Advertencia de mensaje sospechoso

La dirección URL en la que se ha hecho clic estaba en un mensaje de correo electrónico similar a otros mensajes sospechosos. Se recomienda comprobar el mensaje de correo electrónico antes de continuar con el sitio.

:::image type="content" source="../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png" alt-text="Se ha hecho clic en un vínculo desde una advertencia de mensaje sospechoso." lightbox="../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png":::

### <a name="phishing-attempt-warning"></a>Advertencia de intento de suplantación de identidad

La dirección URL en la que se ha hecho clic estaba en un mensaje de correo electrónico que se ha identificado como un ataque de suplantación de identidad (phishing). Como resultado, se bloquean todas las direcciones URL del mensaje de correo electrónico. Se recomienda no continuar con el sitio.

:::image type="content" source="../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png" alt-text="La advertencia que indica que se ha hecho clic en un vínculo desde un mensaje de suplantación de identidad" lightbox="../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png":::

### <a name="malicious-website-warning"></a>Advertencia de sitios web malintencionados

La dirección URL en la que se ha hecho clic apunta a un sitio que se ha identificado como malintencionado. Se recomienda no continuar con el sitio.

:::image type="content" source="../../media/058883c8-23f0-4672-9c1c-66b084796177.png" alt-text="La advertencia que indica que el sitio web está clasificado como malintencionado" lightbox="../../media/058883c8-23f0-4672-9c1c-66b084796177.png":::

La página de advertencia original tenía este aspecto:

:::image type="content" source="../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png" alt-text="La advertencia original que indica que el sitio web está clasificado como malintencionado" lightbox="../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png":::

### <a name="blocked-url-warning"></a>Advertencia de dirección URL bloqueada

Un administrador de la organización ha bloqueado manualmente la dirección URL en la que se ha hecho clic (la lista **Bloquear las siguientes direcciones URL** en la configuración global de Caja fuerte Vínculos). Los vínculos de Caja fuerte no examinaron el vínculo porque se bloqueó manualmente.

Hay varias razones por las que un administrador bloquearía manualmente direcciones URL específicas. Si cree que el sitio no debe bloquearse, póngase en contacto con el administrador.

:::image type="content" source="../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png" alt-text="La advertencia que indica que el administrador bloqueó el sitio web" lightbox="../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png":::

La página de advertencia original tenía este aspecto:

:::image type="content" source="../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png" alt-text="La advertencia original que indica que el sitio web se ha bloqueado según la directiva de dirección URL de la organización" lightbox="../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png":::

### <a name="error-warning"></a>Advertencia de error

Se ha producido algún tipo de error y no se puede abrir la dirección URL.

:::image type="content" source="../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png" alt-text="No se puede cargar la advertencia que indica la página a la que está intentando acceder." lightbox="../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png":::

La página de advertencia original tenía este aspecto:

:::image type="content" source="../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png" alt-text="Advertencia que indica que no se pudo cargar la página web" lightbox="../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png":::
