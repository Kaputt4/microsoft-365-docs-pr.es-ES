---
title: Introducción a los vínculos seguros completos para Microsoft Defender para Office 365
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
- m365-security
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
description: Obtenga información sobre la protección de vínculos seguros en Defender para Office 365 para proteger una organización contra suplantación de identidad (phishing) y otros ataques que usan direcciones URL malintencionadas. Descubra vínculos seguros de Teams y vea los gráficos de los mensajes de vínculos seguros.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 9365cc73239eb9086c565468aeb8f3104ad35b6f
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68626871"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Vínculos seguros en Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](defender-for-office-365.md). Si usa Outlook.com, Microsoft 365 Familia o Microsoft 365 Personal y busca información sobre Safelinks en Outlook, vea [Seguridad avanzada de Outlook.com](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Vínculos seguros es una característica de [Defender para Office 365](defender-for-office-365.md) que proporciona examen de direcciones URL y reescritura de mensajes de correo electrónico entrantes en el flujo de correo, así como la comprobación del tiempo de clic de direcciones URL y vínculos en mensajes de correo electrónico y otras ubicaciones. El análisis de vínculos seguros se produce además del [antispam](anti-spam-protection.md) y [el antimalware](anti-malware-protection.md) normales en los mensajes de correo electrónico entrantes en Exchange Online Protection (EOP). El examen de vínculos seguros puede ayudar a proteger a su organización de vínculos malintencionados que se usan en la suplantación de identidad (phishing) y otros ataques.

Vea este breve vídeo sobre cómo protegerse frente a vínculos malintencionados con vínculos seguros en Microsoft Defender para Office 365.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGzjb]

> [!NOTE]
> Aunque no hay ninguna directiva de vínculos seguros predeterminada, la directiva de seguridad preestablecida **de protección integrada** proporciona protección de vínculos seguros en mensajes de correo electrónico, Microsoft Teams y archivos en aplicaciones de Office compatibles a todos los destinatarios con licencia para Defender para Office 365 (usuarios que no están definidos en las directivas de seguridad preestablecidas estándar o estricta o en directivas de vínculos seguros personalizados). Para obtener más información, vea [Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md). También puede crear directivas de vínculos seguros que se apliquen a usuarios, grupos o dominios específicos. Para obtener instrucciones, consulte [Configuración de directivas de vínculos seguros en Microsoft Defender para Office 365](set-up-safe-links-policies.md).

La protección de vínculos seguros está disponible en las siguientes ubicaciones:

- **Email mensajes**: las directivas de vínculos seguros controlan las protecciones de vínculos seguros para los vínculos de los mensajes de correo electrónico.

  Para obtener más información sobre la protección de vínculos seguros para mensajes de correo electrónico, consulte la sección [Vínculos seguros para mensajes de correo electrónico](#safe-links-settings-for-email-messages) más adelante en este artículo.

  > [!NOTE]
  > Vínculos seguros no funciona en carpetas públicas habilitadas para correo.
  >
  > Vínculos seguros solo admite formatos HTTP(S) y FTP.

- **Microsoft Teams**: la protección de vínculos seguros para vínculos en conversaciones de Teams, chats de grupo o desde canales se controla mediante directivas de vínculos seguros.

  Para obtener más información sobre la protección de vínculos seguros en Teams, consulte la sección [Vínculos seguros para Microsoft Teams](#safe-links-settings-for-microsoft-teams) más adelante en este artículo.

  > [!NOTE]
  > Actualmente, la protección de vínculos seguros para Microsoft Teams no está disponible en Microsoft 365 GCC High o Microsoft 365 DoD.

- **Aplicaciones de Office**: la protección de vínculos seguros para aplicaciones web, móviles y de escritorio de Office admitidas se controla mediante directivas de vínculos seguros.

  Para obtener más información sobre la protección de vínculos seguros en aplicaciones de Office, vea la sección [Configuración de vínculos seguros para aplicaciones de Office](#safe-links-settings-for-office-apps) más adelante en este artículo.

En este artículo se incluyen descripciones detalladas de los siguientes tipos de configuración de vínculos seguros:

- **Configuración en directivas de vínculos seguros**: esta configuración solo se aplica a los usuarios que se incluyen en las directivas específicas, y la configuración puede ser diferente entre las directivas. Entre estas opciones se incluyen:

  - [Configuración de vínculos seguros para mensajes de correo electrónico](#safe-links-settings-for-email-messages)
  - [Configuración de vínculos seguros para Microsoft Teams](#safe-links-settings-for-microsoft-teams)
  - [Configuración de vínculos seguros para aplicaciones de Office](#safe-links-settings-for-office-apps)
  - [Listas de "No volver a escribir las siguientes direcciones URL" en las directivas de vínculos seguros](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **Configuración de vínculos seguros globales**: esta configuración se configura globalmente, no en las directivas de vínculos seguros. Entre estas opciones se incluyen:

  - [Lista "Bloquear las siguientes direcciones URL" para vínculos seguros](#block-the-following-urls-list-for-safe-links)

  > [!NOTE]
  > El menú **Configuración global** y la lista **Bloquear las siguientes direcciones URL** para vínculos seguros están en desuso. En su lugar, use entradas de bloque para las direcciones URL de la [lista de permitidos o bloqueados de inquilinos](allow-block-urls.md#use-the-microsoft-365-defender-portal-to-create-block-entries-for-urls-in-the-tenant-allowblock-list) .

En la tabla siguiente se describen los escenarios de vínculos seguros en Microsoft 365 y Office 365 organizaciones que incluyen Defender para Office 365 (tenga en cuenta que la falta de licencias nunca es un problema en los ejemplos).

|Escenario|Resultado|
|---|---|
|Jean es miembro del departamento de marketing. La protección de vínculos seguros para aplicaciones de Office está activada en una directiva de vínculos seguros que se aplica a los miembros del departamento de marketing. Jean abre una presentación de PowerPoint en un mensaje de correo electrónico y, a continuación, hace clic en una dirección URL en la presentación.|Jean está protegido por vínculos seguros. <p> Jean se incluye en una directiva de vínculos seguros en la que está activada la protección de vínculos seguros para aplicaciones de Office. <p> Para obtener más información sobre los requisitos de protección de vínculos seguros en aplicaciones de Office, consulte la sección [Configuración de vínculos seguros para aplicaciones de Office](#safe-links-settings-for-office-apps) más adelante en este artículo.|
|La organización Microsoft 365 E5 de Chris no tiene configuradas directivas de vínculos seguros. Chris recibe un correo electrónico de un remitente externo que contiene una dirección URL a un sitio web malintencionado en el que, en última instancia, hace clic.|Chris está protegido por vínculos seguros. <p> La directiva de seguridad preestablecida **de protección integrada** proporciona protección de vínculos seguros a todos los destinatarios (usuarios que no están definidos en las directivas de seguridad preestablecidas Estándar o Estricta o en directivas de vínculos seguros personalizadas). Para obtener más información, vea [Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md).|
|En la organización de Pat, los administradores han creado una directiva de vínculos seguros que aplica Pat, pero la protección de vínculos seguros para aplicaciones de Office está desactivada. Pat abre un documento de Word y hace clic en una dirección URL en el archivo.|Pat no está protegido por vínculos seguros. <p> Aunque Pat se incluye en una directiva de vínculos seguros activa, la protección de vínculos seguros para aplicaciones de Office está desactivada en esa directiva, por lo que no se puede aplicar la protección.|
|Jamie y Julia trabajan para contoso.com. Hace mucho tiempo, los administradores configuraron directivas de vínculos seguros que se aplican tanto a Jamie como a Julia. Jamie envía un correo electrónico a Julia, sin saber que el correo electrónico contiene una dirección URL malintencionada.|Julia está protegida por vínculos seguros **si** la directiva vínculos seguros que se aplica a ella está configurada para aplicarse a los mensajes entre destinatarios internos. Para obtener más información, consulte la sección [Configuración de vínculos seguros para mensajes de correo electrónico](#safe-links-settings-for-email-messages) más adelante en este artículo.|

## <a name="recipient-filters-in-safe-links-policies"></a>Filtros de destinatarios en directivas de vínculos seguros

Debe especificar las condiciones y excepciones del destinatario que determinan a quién se aplica la directiva. Puede usar estas propiedades para condiciones y excepciones:

- **Usuarios**
- **Grupos**
- **Dominios**

Solo puede usar una condición o excepción una vez, pero la condición o excepción puede contener varios valores. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

> [!IMPORTANT]
> Los diferentes tipos de condiciones o excepciones no son aditivos; son inclusivos. La directiva se aplica _solo_ a los destinatarios que coinciden con _todos_ los filtros de destinatarios especificados. Por ejemplo, se configura una condición de filtro de destinatario en la directiva con los siguientes valores:
>
> - Usuarios: romain@contoso.com
> - Grupos: Ejecutivos
>
> La directiva se aplica a romain@contoso.com _solo_ si también es miembro del grupo de Ejecutivos. Si no es miembro del grupo, la directiva no se le aplica.
>
> Asimismo, si utiliza el mismo filtro de destinatarios como excepción a la directiva, esta no se aplica a romain@contoso.com _solo_ si también es miembro del grupo de Ejecutivos. Si no es miembro del grupo, la directiva se le sigue aplicando.

## <a name="safe-links-settings-for-email-messages"></a>Configuración de vínculos seguros para mensajes de correo electrónico

Vínculos seguros examina el correo electrónico entrante en busca de hipervínculos malintencionados conocidos. Las direcciones URL examinadas se vuelven a escribir o _encapsulan_ con el prefijo de dirección URL estándar de Microsoft: `https://nam01.safelinks.protection.outlook.com`. Después de reescribir el vínculo, se analiza en busca de contenido potencialmente malintencionado.

Luego de que Vínculos seguros reescriba una dirección URL, la dirección URL permanece reescrita incluso si el mensaje se reenvía o responde _manualmente_ (tanto a destinatarios internos como externos). Los vínculos adicionales que se agregan al mensaje reenviado o respondido no se vuelven a escribir.

En el caso del reenvío _automático_ por reglas de bandeja de entrada o reenvío SMTP, la dirección URL no se volverá a escribir en el mensaje destinado al destinatario final _a menos_ que se cumpla una de las siguientes instrucciones:

- El destinatario también está protegido por vínculos seguros.
- La dirección URL ya se reescribió en una comunicación anterior.

Siempre que la protección de vínculos seguros esté activada, las direcciones URL se examinan antes de la entrega de mensajes, independientemente de si las direcciones URL se vuelven a escribir o no. En las versiones admitidas de Outlook (Outlook para escritorio, versión 16.0.12513 o posterior), las direcciones URL no codificadas se comprueban mediante una llamada API del lado cliente a Vínculos seguros en el momento de hacer clic.

La configuración de las directivas de vínculos seguros que se aplican a los mensajes de correo electrónico se describe en la lista siguiente:

- **Activado: Vínculos seguros comprueba una lista de vínculos malintencionados conocidos cuando los usuarios hacen clic en vínculos en el correo electrónico**: active o desactive el examen de vínculos seguros en los mensajes de correo electrónico. El valor recomendado está seleccionado (activado) y da como resultado las siguientes acciones:
  - El examen de vínculos seguros está activado en Outlook (C2R) en Windows.
  - Las direcciones URL se vuelven a escribir y los usuarios se enrutan a través de la protección de vínculos seguros al hacer clic en direcciones URL en los mensajes.
  - Cuando se hace clic en ellas, las direcciones URL se comprueban en una lista de direcciones URL malintencionadas conocidas y en la [lista "Bloquear las siguientes direcciones URL"](#block-the-following-urls-list-for-safe-links).
  - Las direcciones URL que no tienen una reputación válida se detonan de forma asincrónica en segundo plano.

  La siguiente configuración solo está disponible si está activado el examen de vínculos seguros en mensajes de correo electrónico:

  - **Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización**: active o desactive el examen de vínculos seguros en los mensajes enviados entre remitentes internos y destinatarios internos dentro de la misma organización Exchange Online. El valor recomendado está seleccionado (activado).

  - **Aplicar el examen de direcciones URL en tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos**: activa el examen en tiempo real de los vínculos, incluidos los vínculos de los mensajes de correo electrónico que apuntan al contenido descargable. El valor recomendado está seleccionado (activado).

    - **Esperar a que se complete el examen de direcciones URL antes de entregar el mensaje**:
      - Seleccionado (activado): los mensajes que contienen direcciones URL se mantienen hasta que finaliza el examen. Los mensajes se entregan solo después de confirmar que las direcciones URL son seguras. Este es el valor recomendado.
      - No seleccionado (desactivado): si el examen de direcciones URL no se puede completar, entregue el mensaje de todos modos.

  - **No vuelva a escribir direcciones URL, realice comprobaciones solo a través de safeLinks API**: si esta configuración está seleccionada (activada), no se produce ningún ajuste de dirección URL. En las versiones compatibles de Outlook (Outlook para escritorio, versión 16.0.12513 o posterior), vínculos seguros se llama exclusivamente a través de LAS API en el momento de hacer clic en la dirección URL.

  Para obtener más información sobre los valores recomendados para la configuración de directivas Estándar y Estricta para las directivas de vínculos seguros, consulte [Configuración de directivas de Vínculos seguros](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).

### <a name="how-safe-links-works-in-email-messages"></a>Funcionamiento de vínculos seguros en los mensajes de correo electrónico

En un nivel alto, aquí se muestra cómo funciona la protección de vínculos seguros en las direcciones URL de los mensajes de correo electrónico:

1. Todo el correo electrónico pasa por EOP, donde el protocolo de Internet (IP) y los filtros de sobre, protección contra malware basada en firmas, filtros contra correo no deseado y antimalware antes de que el mensaje se entregue al buzón del destinatario.

2. El usuario abre el mensaje en su buzón y hace clic en una dirección URL del mensaje.

3. Vínculos seguros comprueba inmediatamente la dirección URL antes de abrir el sitio web:

   - Si la dirección URL apunta a un sitio web que se ha determinado que es malintencionado, se abre una página de [advertencia de sitio web malintencionado](#malicious-website-warning) (o una página de advertencia diferente).

   - Si la dirección URL apunta a un archivo descargable y la opción Aplicar examen de **direcciones URL en tiempo real en busca de vínculos sospechosos que apuntan a archivos** está activada en la directiva que se aplica al usuario, se comprueba el archivo descargable.

   - Si se determina que la dirección URL es segura, se abre el sitio web.

## <a name="safe-links-settings-for-microsoft-teams"></a>Configuración de vínculos seguros para Microsoft Teams

Activa o desactiva la protección de vínculos seguros para Microsoft Teams en directivas de vínculos seguros. En concreto, usa **activado: Vínculos seguros comprueba una lista de vínculos malintencionados conocidos cuando los usuarios hacen clic en vínculos en** la configuración de Microsoft Teams. El valor recomendado está activado (seleccionado).

> [!NOTE]
> Al activar o desactivar la protección de vínculos seguros para Teams, el cambio puede tardar hasta 24 horas en surtir efecto.
>
> Actualmente, la protección de vínculos seguros para Microsoft Teams no está disponible en Microsoft 365 GCC High o Microsoft 365 DoD.

Después de activar la protección de vínculos seguros para Microsoft Teams, las direcciones URL de Teams se comprueban en una lista de vínculos malintencionados conocidos cuando el usuario protegido hace clic en el vínculo (protección al hacer clic). Las direcciones URL no se reescriben. Si se detecta que un vínculo es malintencionado, los usuarios tendrán las siguientes experiencias:

- Si se hizo clic en el vínculo en una conversación de Teams, chat en grupo o desde canales, la página de advertencia, como se muestra en la captura de pantalla siguiente, aparecerá en el explorador web predeterminado.
- Si se hizo clic en el vínculo desde una pestaña anclada, la página de advertencia aparecerá en la interfaz de Teams de la pestaña. La opción para abrir el vínculo en un explorador web está deshabilitada por motivos de seguridad.
- En función de cómo se configure **la opción Permitir a los usuarios hacer clic en la dirección URL original** de la directiva, el usuario podrá o no hacer clic en la dirección URL original (**continuar de todos modos (no recomendado)** en la captura de pantalla. Se recomienda no seleccionar la opción **Permitir a los usuarios hacer clic en la dirección URL original para** que los usuarios no puedan hacer clic en la dirección URL original.

Si el usuario que envió el vínculo no está protegido por una directiva de vínculos seguros en la que está activada la protección de Teams, el usuario puede hacer clic en la dirección URL original de su equipo o dispositivo.

:::image type="content" source="../../media/tp-safe-links-for-teams-malicious.png" alt-text="Una páginas de vínculos seguros para Teams que informa de un vínculo malintencionado" lightbox="../../media/tp-safe-links-for-teams-malicious.png":::

Al hacer clic en el botón **Volver** de la página de advertencia, el usuario volverá a su contexto o ubicación URL original. Sin embargo, al volver a hacer clic en el vínculo original, los vínculos seguros volverán a examinar la dirección URL, por lo que la página de advertencia volverá a aparecer.

### <a name="how-safe-links-works-in-teams"></a>Cómo funcionan los vínculos seguros en Teams

En un nivel alto, aquí se muestra cómo funciona la protección de vínculos seguros para direcciones URL en Microsoft Teams:

1. Un usuario inicia la aplicación Teams.

2. Microsoft 365 comprueba que la organización del usuario incluye Microsoft Defender para Office 365 y que el usuario está incluido en una directiva de vínculos seguros activa en la que está activada la protección de Microsoft Teams.

3. Las direcciones URL se validan al hacer clic para el usuario en chats, chats de grupo, canales y pestañas.

## <a name="safe-links-settings-for-office-apps"></a>Configuración de vínculos seguros para aplicaciones de Office

Protección de vínculos seguros para aplicaciones de Office comprueba vínculos en documentos de Office, no vínculos en mensajes de correo electrónico. Sin embargo, puede comprobar los vínculos de los documentos adjuntos de Office en los mensajes de correo electrónico después de abrir el documento.

Activa o desactiva la protección de vínculos seguros para aplicaciones de Office en directivas de vínculos seguros. En concreto, usa la **opción Activado: Vínculos seguros comprueba una lista de vínculos malintencionados conocidos cuando los usuarios hacen clic en vínculos en** la configuración de aplicaciones de Microsoft Office. El valor recomendado está activado (seleccionado).

La protección de vínculos seguros para aplicaciones de Office tiene los siguientes requisitos de cliente:

- Aplicaciones Microsoft 365 o Microsoft 365 Empresa Premium.
  - Versiones actuales de Word, Excel y PowerPoint en Windows, Mac o en un explorador web.
  - Aplicaciones de Office en dispositivos iOS o Android.
  - Visio en Windows.
  - OneNote en un explorador web.
  - Outlook para Windows al abrir archivos EML o MSG guardados.

- Las aplicaciones de Office están configuradas para usar la autenticación moderna. Para obtener más información, vea [Cómo funciona la autenticación moderna para aplicaciones cliente de Office 2013, Office 2016 y Office 2019](../../enterprise/modern-auth-for-office-2013-and-2016.md).

- Los usuarios han iniciado sesión con sus cuentas profesionales o educativas. Para obtener más información, consulte [Inicio de sesión en Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).

Para obtener más información sobre los valores recomendados para la configuración de directiva estándar y estricta, consulte [Configuración global para vínculos seguros](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links).

### <a name="how-safe-links-works-in-office-apps"></a>Funcionamiento de vínculos seguros en aplicaciones de Office

En un nivel alto, aquí se muestra cómo funciona la protección de vínculos seguros para las direcciones URL en las aplicaciones de Office. Las aplicaciones de Office admitidas se describen en la sección anterior.

1. Un usuario inicia sesión con su cuenta profesional o educativa en una organización que incluye Aplicaciones Microsoft 365 o Microsoft 365 Empresa Premium.

2. El usuario abre y hace clic en un vínculo a un documento de Office en una aplicación de Office compatible.

3. Vínculos seguros comprueba inmediatamente la dirección URL antes de abrir el sitio web de destino:

   - Si la dirección URL se incluye en la lista que omite el examen de vínculos seguros (la lista **Bloquear las siguientes direcciones URL** ), se abre una página de [advertencia de dirección URL bloqueada](#blocked-url-warning) .

   - Si la dirección URL apunta a un sitio web que se ha determinado que es malintencionado, se abre una página de [advertencia de sitio web malintencionado](#malicious-website-warning) (o una página de advertencia diferente).

   - Si la dirección URL apunta a un archivo descargable y la directiva vínculos seguros que se aplica al usuario está configurada para examinar los vínculos al contenido descargable (**aplicar el examen de direcciones URL en tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos**), se comprueba el archivo descargable.

   - Si la dirección URL se considera segura, el usuario se lleva al sitio web.

   - Si el análisis de vínculos seguros no se puede completar, la protección de vínculos seguros no se desencadena. En los clientes de escritorio de Office, se advertirá al usuario antes de continuar con el sitio web de destino.

> [!NOTE]
> Al principio de cada sesión puede tardar varios segundos en comprobar que los vínculos seguros para aplicaciones de Office están disponibles para el usuario.

## <a name="click-protection-settings-in-safe-links-policies"></a>Haga clic en Configuración de protección en Directivas de vínculos seguros

Esta configuración se aplica a vínculos seguros en el correo electrónico, Teams y aplicaciones de Office:

- **Seguimiento de los clics del usuario**: active o desactive el almacenamiento de datos de clic de vínculos seguros para las direcciones URL en las que se ha hecho clic. Se recomienda dejar esta opción seleccionada (activada).

  En Vínculos seguros para aplicaciones de Office, esta configuración se aplica a las versiones de escritorio de Word, Excel, PowerPoint y Visio.

  Si selecciona esta configuración, están disponibles las siguientes opciones:

  - **Permitir que los usuarios haga clic en la dirección URL original**: controla si los usuarios pueden hacer clic en la [página de advertencia](#warning-pages-from-safe-links) a la dirección URL original. El valor de recomendación no está seleccionado (desactivado).

    En Vínculos seguros para aplicaciones de Office, esta configuración se aplica a la dirección URL original en las versiones de escritorio de Word, Excel, PowerPoint y Visio.

  - **Mostrar la personalización de marca de la organización en las páginas de notificación y advertencia**: esta opción muestra la personalización de marca de la organización en las páginas de advertencia. La marca ayuda a los usuarios a identificar advertencias legítimas, ya que los atacantes suelen usar las páginas de advertencia predeterminadas de Microsoft. Para obtener más información sobre la personalización de la marca, consulte [Personalizar el tema de Microsoft 365 para la organización](../../admin/setup/customize-your-organization-theme.md).

## <a name="priority-of-safe-links-policies"></a>Prioridad de las directivas de vínculos seguros

Después de crear varias directivas, puede especificar el orden en que se aplican. Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva. La directiva **de protección integrada** siempre se aplica en último lugar. Las directivas de vínculos seguros asociadas **a** las directivas de seguridad estándar y **estricta** se aplican siempre antes que las directivas de vínculos seguros personalizadas.

Para obtener más información sobre el orden de precedencia y cómo se evalúan y aplican varias directivas, vea [Orden de precedencia para las directivas de seguridad preestablecidas y otras directivas](preset-security-policies.md#order-of-precedence-for-preset-security-policies-and-other-policies) y [Orden y prioridad de la protección por correo electrónico](how-policies-and-protections-are-combined.md).

## <a name="block-the-following-urls-list-for-safe-links"></a>Lista "Bloquear las siguientes direcciones URL" para vínculos seguros

> [!NOTE]
> La lista **Bloquear las siguientes direcciones URL** para vínculos seguros está en desuso. En su lugar, use entradas de bloque para las direcciones URL de la [lista de permitidos o bloqueados de inquilinos](allow-block-urls.md#use-the-microsoft-365-defender-portal-to-create-block-entries-for-urls-in-the-tenant-allowblock-list) . Los mensajes que contienen la dirección URL bloqueada se ponen en cuarentena.

La lista **Bloquear las siguientes direcciones URL** define los vínculos que siempre están bloqueados por el examen de vínculos seguros en las siguientes ubicaciones:

- Mensajes de correo electrónico
- Documentos en aplicaciones de Office en Windows y Mac.
- Documentos en Office para iOS y Android.

Cuando un usuario de una directiva de vínculos seguros activa hace clic en un vínculo bloqueado en una aplicación compatible, se le lleva a la página [de advertencia url bloqueada](#blocked-url-warning) .

La lista de direcciones URL se configura en la configuración global de Vínculos seguros. Para obtener instrucciones, consulte [Configurar la lista "Bloquear las siguientes direcciones URL"](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-microsoft-365-defender-portal).

**Notas**:

- Para obtener una lista verdaderamente universal de direcciones URL que están bloqueadas en todas partes, consulte [Administrar la lista de permitidos o bloqueados de inquilinos](manage-tenant-allow-block-list.md).
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

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>Listas de "No volver a escribir las siguientes direcciones URL" en las directivas de vínculos seguros

> [!NOTE]
> Las entradas de la lista "No volver a escribir las siguientes direcciones URL" no se examinan ni encapsulan mediante vínculos seguros durante el flujo de correo. Use [entradas de dirección URL permitidas en la lista de permitidos o bloqueados de inquilinos](allow-block-urls.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-urls-in-the-submissions-portal) para que las direcciones URL no se examinen ni ajusten mediante vínculos seguros durante el flujo de correo _y_ en el momento de hacer clic.

Cada directiva de vínculos seguros contiene una lista **No volver a escribir las siguientes direcciones URL** que puede usar para especificar direcciones URL que no se reescriban mediante el examen de vínculos seguros. En otras palabras, la lista permite a los usuarios incluidos en la directiva acceder a las direcciones URL especificadas que, de lo contrario, estarían bloqueadas por vínculos seguros. Puede configurar diferentes listas en diferentes directivas de vínculos seguros. El procesamiento de directivas se detiene después de que se aplique al usuario la primera directiva (probablemente, la prioridad más alta). Por lo tanto, solo se aplica una opción **No volver a escribir la lista de direcciones URL siguientes** a un usuario que se incluye en varias directivas de vínculos seguros activas.

Para agregar entradas a la lista en directivas de vínculos seguros nuevas o existentes, consulte [Crear directivas de vínculos seguros](set-up-safe-links-policies.md#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) o [Modificar directivas de vínculos seguros](set-up-safe-links-policies.md#use-the-microsoft-365-defender-portal-to-modify-safe-links-policies).

**Notas**:

- Los clientes siguientes no reconocen las listas **No volver a escribir las siguientes direcciones URL** en las directivas de vínculos seguros. Se puede impedir que los usuarios incluidos en las directivas accedan a las direcciones URL en función de los resultados del examen de vínculos seguros en estos clientes:
  - Microsoft Teams
  - Aplicaciones web de Office

  Para obtener una lista verdaderamente universal de direcciones URL que se permiten en todas partes, consulte [Administrar la lista de permitidos o bloqueados de inquilinos](manage-tenant-allow-block-list.md). Sin embargo, tenga en cuenta que las direcciones URL agregadas no se excluirán de la reescritura de vínculos seguros, como debe hacerse en una directiva de vínculos seguros.

- Considere la posibilidad de agregar direcciones URL internas de uso frecuente a la lista para mejorar la experiencia del usuario. Por ejemplo, si tiene servicios locales, como Skype Empresarial o SharePoint, puede agregar esas direcciones URL para excluirlas del examen.
- Si ya tiene **no volver a escribir las siguientes entradas de direcciones URL** en las directivas de vínculos seguros, asegúrese de revisar las listas y agregar caracteres comodín según sea necesario. Por ejemplo, la lista tiene una entrada como `https://contoso.com/a` y, más adelante, decide incluir subpaths como `https://contoso.com/a/b`. En lugar de agregar una nueva entrada, agregue un carácter comodín a la entrada existente para que se convierta en `https://contoso.com/a/*`.
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

## <a name="warning-pages-from-safe-links"></a>Páginas de advertencia de vínculos seguros

Esta sección contiene ejemplos de las distintas páginas de advertencia desencadenadas por la protección de vínculos seguros al hacer clic en una dirección URL.

Tenga en cuenta que se han actualizado varias páginas de advertencia. Si aún no ve las páginas actualizadas, pronto lo hará. Las páginas actualizadas incluyen una nueva combinación de colores, más detalles y la capacidad de continuar con un sitio a pesar de las advertencias y recomendaciones dadas.

### <a name="scan-in-progress-notification"></a>Notificación de examen en curso

Vínculos seguros examinan la dirección URL en la que se ha hecho clic. Es posible que tenga que esperar unos instantes antes de volver a intentar el vínculo.

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

Un administrador de la organización ha bloqueado manualmente la dirección URL en la que se ha hecho clic (la lista **Bloquear las siguientes direcciones URL** en la configuración global de Vínculos seguros). Los vínculos seguros no examinaron el vínculo porque se bloqueó manualmente.

Hay varias razones por las que un administrador bloquearía manualmente direcciones URL específicas. Si cree que el sitio no debe bloquearse, póngase en contacto con el administrador.

:::image type="content" source="../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png" alt-text="La advertencia que indica que el administrador bloqueó el sitio web" lightbox="../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png":::

La página de advertencia original tenía este aspecto:

:::image type="content" source="../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png" alt-text="La advertencia original que indica que el sitio web se ha bloqueado según la directiva de dirección URL de la organización" lightbox="../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png":::

### <a name="error-warning"></a>Advertencia de error

Se ha producido algún tipo de error y no se puede abrir la dirección URL.

:::image type="content" source="../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png" alt-text="No se puede cargar la advertencia que indica la página a la que está intentando acceder." lightbox="../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png":::

La página de advertencia original tenía este aspecto:

:::image type="content" source="../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png" alt-text="Advertencia que indica que no se pudo cargar la página web" lightbox="../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png":::
