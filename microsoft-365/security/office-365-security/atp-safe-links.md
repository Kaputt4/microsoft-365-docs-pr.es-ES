---
title: Vínculos seguros
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.article: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
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
description: En este artículo, los administradores pueden obtener información sobre la protección de vínculos seguros en defender para Office 365 para proteger su organización del phishing y otros ataques que usan direcciones URL malintencionadas.
ms.openlocfilehash: f2a747b0776a16ac981158ab866f28699583a06b
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616325"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Vínculos seguros en Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Microsoft defender para Office 365](office-365-atp.md). Si está usando Outlook.com, Microsoft 365 Family o Microsoft 365 personal, y está buscando información sobre Safelinks en Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Vínculos seguros es una característica de [defender para Office 365](office-365-atp.md) que proporciona el análisis y la reescritura de direcciones URL de los mensajes de correo electrónico entrantes en el flujo de correo y la comprobación del tiempo de clic de direcciones URL y vínculos en mensajes de correo electrónico y otras ubicaciones. El análisis de vínculos seguros se produce además de la protección normal contra el [correo no deseado y antimalware](anti-spam-and-anti-malware-protection.md) en los mensajes de correo electrónico entrantes en Exchange Online Protection (EOP). El análisis de vínculos seguros puede ayudarle a proteger su organización de vínculos malintencionados que se usan en suplantación de identidad (phishing) y otros ataques.

La protección de vínculos seguros está disponible en las siguientes ubicaciones:

- **Mensajes de correo electrónico**: la protección de vínculos seguros para vínculos en mensajes de correo electrónico se controla mediante directivas de vínculos seguros. No hay ninguna directiva de vínculos a prueba de errores predeterminada, **por lo que para obtener la protección de vínculos seguros en los mensajes de correo electrónico, debe crear una o varias directivas de vínculos a prueba** de errores. Para obtener instrucciones, consulte [configurar directivas de vínculos seguros en Microsoft defender para Office 365](set-up-atp-safe-links-policies.md).

  Para obtener más información acerca de la protección de vínculos seguros para los mensajes de correo electrónico, consulte la sección [configuración de vínculos seguros para los mensajes de correo electrónico](#safe-links-settings-for-email-messages) más adelante en este artículo.

- **Microsoft Teams** (actualmente en vista previa): la protección de vínculos seguros para vínculos en conversaciones de Microsoft Teams, chats de grupos o desde canales también está controlada por las directivas de vínculos a prueba de errores. No hay ninguna directiva de vínculos a prueba de errores predeterminada, **por lo que para obtener la protección de vínculos seguros en Microsoft Teams, debe crear una o varias directivas de vínculos a prueba** de errores.

  Para obtener más información acerca de la protección de vínculos seguros en Teams, consulte la sección [configuración de vínculos seguros para Microsoft Teams](#safe-links-settings-for-microsoft-teams) más adelante en este tema.

- **Office 365 apps**: la protección de vínculos seguros para aplicaciones de Office 365 está disponible en los AP de escritorio, móviles y Web admitidos. Puede **configurar** la protección de vínculos seguros para las aplicaciones de Office 365 en la configuración global que se encuentran **fuera** de las directivas de vínculos seguros. Para obtener instrucciones, consulte [configurar las opciones globales de configuración de vínculos seguros en Microsoft defender para Office 365](configure-global-settings-for-safe-links.md).

  Pero, la protección de vínculos seguros para las aplicaciones de Office 365 solo se **aplica** a los usuarios que se incluyen en las directivas de vínculos seguros activos. Si un usuario no está incluido en una directiva de vínculos seguros activa, el usuario no obtiene protección de vínculos seguros en las aplicaciones de Office 365 compatibles.

  Para obtener más información sobre la protección de vínculos seguros en aplicaciones de Office 365, vea la sección [configuración de vínculos seguros para office 365 apps](#safe-links-settings-for-office-365-apps) más adelante en este artículo.

En este artículo se incluyen descripciones detalladas de los siguientes tipos de configuración de vínculos a prueba de errores:

- **Configuración en directivas de vínculos seguros**: esta configuración solo se aplica a los usuarios que están incluidos en las directivas específicas y la configuración puede ser diferente en las directivas. Estas opciones de configuración incluyen:

  - [Configuración de vínculos seguros para los mensajes de correo electrónico](#safe-links-settings-for-email-messages)
  - [Configuración de vínculos seguros para Microsoft Teams](#safe-links-settings-for-microsoft-teams)
  - [Listas "no volver a escribir las siguientes direcciones URL" en directivas de vínculos a prueba de errores](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **Configuración de vínculos seguros globales**: estas opciones se configuran globalmente, no en las directivas de vínculos a prueba de errores. Pero la configuración se aplica únicamente a los usuarios que se incluyen en las directivas de vínculos seguros activos. Estas opciones de configuración incluyen:

  - [Configuración de vínculos seguros para aplicaciones de Office 365](#safe-links-settings-for-office-365-apps)
  - [Lista "bloquear las siguientes direcciones URL" para vínculos seguros](#block-the-following-urls-list-for-safe-links)

En la tabla siguiente se describen los escenarios de vínculos a prueba de errores en organizaciones de Microsoft 365 y Office 365 que incluyen defender para Office 365 (es decir, la falta de licencias nunca es un problema en los ejemplos).

****

|Escenario|Resultado|
|---|---|
|Jean es miembro del Departamento de marketing. La protección de vínculos seguros para las aplicaciones de Office 365 está activada en la configuración global de vínculos seguros y existe una directiva de vínculos seguros que se aplica a los miembros del Departamento de marketing. Jean abre una presentación de PowerPoint en un mensaje de correo electrónico y, a continuación, hace clic en una dirección URL de la presentación.|Jean está protegido por vínculos seguros. <p> Jean se incluye en una directiva de vínculos seguros y la protección de vínculos seguros para las aplicaciones de Office 365 está activada. <p> Para obtener más información acerca de los requisitos para la protección de vínculos seguros en las aplicaciones de Office 365, vea la sección [configuración de vínculos seguros para office 365 apps](#safe-links-settings-for-office-365-apps) más adelante en este artículo.|
|La organización Microsoft 365 E5 de Carlos no tiene configurada ninguna directiva de vínculos seguros. Chris recibe un correo electrónico de un remitente externo que contiene una dirección URL a un sitio Web malintencionado en el que se hace clic en último término.|Carlos no está protegido por vínculos seguros. <p> Un administrador debe crear al menos una directiva de vínculos seguros para que cualquiera obtenga protección de vínculos seguros en los mensajes de correo electrónico entrantes. Chris debe incluirse en las condiciones de la Directiva para obtener protección de vínculos seguros.|
|En la organización de Pat, ningún administrador ha creado ninguna directiva de vínculos a prueba de errores, pero la protección de vínculos seguros para las aplicaciones de Office 365 está activada. Pat abre un documento de Word y hace clic en una dirección URL en el archivo.|Pat no está protegido por vínculos seguros. <p> Aunque la protección de vínculos seguros para las aplicaciones de Office 365 está activada globalmente, Pat no se incluye en ninguna directiva de vínculos a prueba de errores, por lo que no se puede aplicar la protección.|
|En la organización de Lee, `https://tailspintoys.com` se configura en la lista **bloquear las siguientes direcciones URL** en la configuración global para vínculos seguros. Ya existe una directiva de vínculos a prueba de errores que incluye Lee. Lee recibe un mensaje de correo electrónico que contiene la dirección URL `https://tailspintoys.com/aboutus/trythispage` . Lee hace clic en la dirección URL.|Es posible que la dirección URL se bloquee automáticamente para Lucas; depende de la entrada de la dirección URL de la lista y del cliente de correo electrónico Lee que se usa. Para obtener más información, vea la [lista "bloquear las siguientes direcciones URL"](#block-the-following-urls-list-for-safe-links) en la sección vínculos seguros más adelante en este tema.|
|Jamie y Julia trabajan para contoso.com. Hace mucho tiempo, los administradores configuraron directivas de vínculos a prueba de errores que se aplican a Pablo y Julia. Pablo envía un correo electrónico a Julia, pero no sabe que el correo electrónico contiene una dirección URL malintencionada.|Julia protege los vínculos a prueba de errores **si** la Directiva de vínculos seguros que se aplica a ella está configurada para aplicarse a los mensajes entre los destinatarios internos. Para obtener más información, vea la sección [configuración de vínculos seguros para los mensajes de correo electrónico](#safe-links-settings-for-email-messages) más adelante en este tema.|

## <a name="safe-links-settings-for-email-messages"></a>Configuración de vínculos seguros para los mensajes de correo electrónico

Vínculos seguros busca los hipervínculos malintencionados conocidos en el correo electrónico entrante. Las direcciones URL examinadas se reescriben con el prefijo de dirección URL estándar de Microsoft: `https://nam01.safelinks.protection.outlook.com` . Una vez reescrito el vínculo, se analiza en busca de contenido potencialmente malintencionado.

Después de que los vínculos seguros reescriben una dirección URL, la dirección URL permanece reescrita, incluso si el mensaje se reenvía o se responde. No se rescribirán los vínculos adicionales que se agreguen al mensaje reenviado o respondido.

Las opciones de configuración de las directivas de vínculos a prueba de errores que se aplican a los mensajes de correo electrónico se describen en la siguiente lista:

- **Seleccione la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes**: habilita o deshabilita el análisis de vínculos seguros en los mensajes de correo electrónico. El valor recomendado es **on**. Al activar esta configuración, se producen las siguientes acciones.

  - La exploración de vínculos seguros está habilitada en Outlook (C2R) en Windows.
  - Las direcciones URL se reescriben y los usuarios se redirigen a través de la protección de vínculos seguros cuando hacen clic en direcciones URL en los mensajes.
  - Cuando se hace clic en ellas, las direcciones URL se comprueban con una lista de direcciones URL malintencionadas conocidas y la [lista "bloquear las siguientes direcciones URL"](#block-the-following-urls-list-for-safe-links).
  - Las direcciones URL que no tienen una reputación válida se superponen de forma asíncrona en segundo plano.

- **Aplique un análisis de URL en tiempo real de vínculos y vínculos sospechosos que apunten a archivos**: permite el análisis en tiempo real de vínculos, incluidos los vínculos de los mensajes de correo electrónico que apuntan a contenido descargable. El valor recomendado está habilitado.

  - **Espere a que se complete el análisis de URL antes de entregar el mensaje**:

    - Habilitado: los mensajes que contienen direcciones URL se conservan hasta que finaliza el examen. Los mensajes solo se entregan después de que las direcciones URL se confirmen como seguras. Este es el valor recomendado.
    - Deshabilitado: Si no se puede completar el análisis de direcciones URL, entregar el mensaje de todos modos.

- **Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización**: habilita o deshabilita el análisis de vínculos seguros en los mensajes enviados entre remitentes internos y destinatarios internos dentro de la misma organización de Exchange Online. El valor recomendado está habilitado.

- **No hacer un seguimiento de los clics del usuario**: habilita o deshabilita el almacenamiento de vínculos seguros haga clic en datos de direcciones URL en mensajes de correo electrónico. El valor recomendado es dejar esta configuración desactivada (para hacer un seguimiento de los clics del usuario).

  Dirección URL haga clic en seguimiento para los vínculos de los mensajes de correo electrónico enviados entre los remitentes internos y los destinatarios internos no se admite actualmente.

- **No permita que los usuarios hagan clic a través de la dirección URL original**: permite o bloquea que los usuarios hagan clic en la [Página de advertencia](#warning-pages-from-safe-links) a la dirección URL original. El valor recomendado está habilitado.

- **No reescriba las siguientes direcciones** URL: deja las direcciones URL tal y como están. Mantiene una lista personalizada de direcciones URL seguras que no necesitan análisis. La lista es única para cada directiva de vínculos seguros. Para obtener más información acerca de la lista no **reescribir las siguientes direcciones URL** , vea las [listas "no reescribir las siguientes direcciones URL" en la sección directivas de vínculos seguros](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) , más adelante en este artículo.

Para obtener más información acerca de los valores recomendados para la configuración estándar y estricta de las directivas de vínculos a prueba de errores, vea [configuración de directivas de vínculos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).

- **Filtros de destinatarios**: debe especificar las condiciones y excepciones de destinatarios que determinan a quién se aplica la Directiva. Puede usar estas propiedades para las condiciones y excepciones:

  - **El destinatario es**
  - **El dominio del destinatario es**
  - **El destinatario es un miembro de**

  Solo se puede usar una condición o excepción una vez, pero la condición o excepción puede contener varios valores. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

- **Prioridad**: Si crea varias directivas, puede especificar el orden en que se aplican. Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

  Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).

### <a name="how-safe-links-works-in-email-messages"></a>Cómo funcionan los vínculos seguros en los mensajes de correo electrónico

En un nivel alto, a continuación se muestra cómo funciona la protección de vínculos seguros en direcciones URL en mensajes de correo electrónico:

1. Todo el correo electrónico pasa a través de EOP, donde los filtros de protocolo de Internet (IP) y sobre, la protección contra malware basada en firmas, los filtros contra correo no deseado y antimalware antes de entregar el mensaje al buzón de correo del destinatario.

2. El usuario abre el mensaje en su buzón y hace clic en una dirección URL en el mensaje.

3. Vínculos seguros comprueba inmediatamente la dirección URL antes de abrir el sitio web:

   - Si la dirección URL se incluye en la lista **bloquear las siguientes direcciones** URL, se abrirá una [Advertencia de dirección URL bloqueada](#blocked-url-warning) .

   - Si la dirección URL apunta a un sitio web que se ha determinado que es malintencionado, se abre una página de [Advertencia de sitio Web malintencionado](#malicious-website-warning) (o una página de advertencia diferente).

   - Si la dirección URL apunta a un archivo descargable y la configuración **aplicar análisis de URL en tiempo real para vínculos sospechosos y vínculos que apuntan a archivos** está habilitada en la Directiva que se aplica al usuario, se comprueba el archivo descargable.

   - Si se determina que la dirección URL es segura, se abrirá el sitio Web.

## <a name="safe-links-settings-for-microsoft-teams"></a>Configuración de vínculos seguros para Microsoft Teams

> [!IMPORTANT]
> A partir del 2020 de marzo, esta característica se encuentra en versión preliminar y solo está disponible para los miembros del programa de adopción de tecnología de Microsoft Teams (TAP). Para obtener información sobre la programación de versiones, consulte el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams).

Puede habilitar o deshabilitar la protección de vínculos seguros para Microsoft Teams en directivas de vínculos a prueba de errores. En concreto, use la opción **seleccionar la acción para direcciones URL potencialmente malintencionadas o desconocidas en Microsoft Teams** . El valor recomendado es **on**.

Las siguientes opciones de configuración en las directivas de vínculos seguros que se aplican a los vínculos de los mensajes de correo electrónico también se aplican a los vínculos de Teams:

- **Aplicar un análisis de URL en tiempo real de vínculos y vínculos sospechosos que señalan a archivos**
- **No hacer un seguimiento de los clics del usuario**
- **No permitir que los usuarios hagan clic a través de la dirección URL original**

Esta configuración se explica en la sección [configuración de vínculos seguros anterior para los mensajes de correo electrónico](#safe-links-settings-for-email-messages) .

Después de activar la protección de vínculos seguros para Microsoft Teams, las direcciones URL en Teams se comprueban con una lista de vínculos malintencionados conocidos cuando el usuario protegido hace clic en el vínculo (protección de tiempo de clic). Las direcciones URL no se reescriben. Si se encuentra que un vínculo es malintencionado, los usuarios tendrán las siguientes experiencias:

- Si se hizo clic en el vínculo en una conversación de Microsoft Teams, un chat de grupo o desde los canales, la página de advertencia, tal como se muestra en la captura de pantalla siguiente, aparecerá en el explorador Web predeterminado.
- Si se hizo clic en el vínculo desde una pestaña anclada, la página de advertencia aparecerá en la interfaz de Microsoft Teams dentro de esa pestaña. La opción para abrir el vínculo en un explorador web está deshabilitada por motivos de seguridad.
- Dependiendo de cómo esté configurada la opción no **permitir que los usuarios hagan clic en la dirección URL original** de la Directiva, el usuario podrá hacer clic en la dirección URL original (continuar de **todos modos (no recomendado)** en la captura de pantalla). Le recomendamos que habilite la configuración no **permitir que los usuarios hagan clic con la dirección URL original** , de modo que los usuarios no puedan hacer clic a través de la dirección URL original.

Si el usuario que envió el vínculo no está incluido en una directiva de vínculos seguros en la que la protección de Teams está habilitada, el usuario podrá hacer clic en ella para obtener la dirección URL original en su equipo o dispositivo.

![Una página vínculos seguros para Microsoft teams que informa de un vínculo malintencionado.](../../media/tp-safe-links-for-teams-malicious.png)

Si se hace clic en el botón volver **atrás** de la página de advertencia, el usuario se devolverá a su contexto original o a la ubicación de la dirección URL. Sin embargo, si vuelve a hacer clic en el vínculo original, los vínculos a prueba de errores volverán a examinar la dirección URL, por lo que volverá a aparecer la página de advertencia.

### <a name="how-safe-links-works-in-teams"></a>Cómo funcionan los vínculos seguros en Microsoft Teams

En un nivel alto, a continuación se muestra cómo funciona la protección de vínculos seguros para las direcciones URL en Microsoft Teams:

1. Un usuario inicia la aplicación Microsoft Teams.

2. Microsoft 365 comprueba que la organización del usuario incluye Microsoft defender para Office 365 y que el usuario se incluye en una directiva de vínculos seguros activa donde la protección para Microsoft Teams está habilitada.

3. Las direcciones URL se validan en el momento de hacer clic para el usuario en chats, chats de grupo, canales y pestañas.

## <a name="safe-links-settings-for-office-365-apps"></a>Configuración de vínculos seguros para aplicaciones de Office 365

Safe links Protection for Office 365 apps comprueba vínculos en documentos de Office, no vínculos en mensajes de correo electrónico (pero puede comprobar vínculos en documentos de Office adjuntos en mensajes de correo electrónico después de abrir el documento).

La protección de vínculos seguros para las aplicaciones de Office 365 tiene los siguientes requisitos de cliente:

- Microsoft 365 Apps o Microsoft 365 empresa Premium.
  - Versiones actuales de Word, Excel y PowerPoint en Windows, Mac o en un explorador Web.
  - Aplicaciones de Office en dispositivos iOS o Android.
  - Visio en Windows.
  - OneNote en un explorador Web.

- Las aplicaciones de Office 365 están configuradas para usar la autenticación moderna. Para obtener más información, vea [Cómo funciona la autenticación moderna para las aplicaciones cliente de office 2013, office 2016 y office 2019](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).

- Los usuarios inician sesión con su cuenta profesional o educativa. Para obtener más información, vea [iniciar sesión en Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).

Puede configurar la protección de vínculos seguros para las aplicaciones de Office 365 en la configuración global de vínculos seguros, no en las directivas de vínculos a prueba de errores. Sin embargo, para que se aplique la protección de vínculos seguros para las aplicaciones de Office 365, el usuario que abra el documento de Office y haga clic en el vínculo debe incluirse en una directiva de vínculos seguros activa.

Están disponibles las siguientes opciones de configuración de vínculos seguros para las aplicaciones de Office 365:

- **Aplicaciones de office 365**: habilita o deshabilita el análisis de vínculos seguros en aplicaciones de Office 365 compatibles. El valor predeterminado y el valor recomendado es **on**.

- **No realizar seguimiento cuando los usuarios hacen clic en vínculos seguros**: habilita o deshabilita el almacenamiento de vínculos seguros haga clic en datos de direcciones URL en las versiones de escritorio Word, Excel, PowerPoint y Visio. El valor recomendado es **OFF**, lo que significa que se realiza un seguimiento de los clics del usuario.

- **No permita que los usuarios hagan clic en los vínculos seguros a la dirección URL original**: permite o bloquea que los usuarios hagan clic en la [Página de advertencia](#warning-pages-from-safe-links) en la dirección URL original en las versiones de escritorio Word, Excel, PowerPoint y Visio. El valor predeterminado y el valor recomendado es **on**.

Para configurar las opciones de vínculos seguros para las aplicaciones de Office 365, consulte [Configure Safe links Protection for office 365 apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center).

Para obtener más información acerca de los valores recomendados para la configuración de directivas estándar y estricta, consulte [configuración global para vínculos seguros](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links).

### <a name="how-safe-links-works-in-office-365-apps"></a>Cómo funcionan los vínculos seguros en las aplicaciones de Office 365

En un nivel alto, aquí se muestra cómo funciona la protección de vínculos seguros para las direcciones URL en las aplicaciones de Office 365. Las aplicaciones de Office 365 admitidas se describen en la sección anterior.

1. Un usuario inicia sesión con su cuenta profesional o educativa en una organización que incluye Microsoft 365 Apps o Microsoft 365 empresa Premium.

2. El usuario abre y hace clic en un vínculo de un documento de Office en una aplicación de Office compatible.

3. Vínculos seguros comprueba inmediatamente la dirección URL antes de abrir el sitio web de destino:

   - Si la dirección URL se incluye en la lista que omite el análisis de vínculos seguros (la lista **bloquear la siguiente URL** ), se abrirá una [Advertencia de dirección URL bloqueada](#blocked-url-warning) .

   - Si la dirección URL apunta a un sitio web que se ha determinado que es malintencionado, se abre una página de [Advertencia de sitio Web malintencionado](#malicious-website-warning) (o una página de advertencia diferente).

   - Si la dirección URL apunta a un archivo descargable y la Directiva de vínculos seguros que se aplica al usuario está configurada para analizar los vínculos a contenido descargable (**aplicar un análisis de URL en tiempo real para vínculos sospechosos y vínculos que señalan a archivos**), se comprueba el archivo descargable.

   - Si la dirección URL se considera segura, el usuario se dirigirá al sitio Web.

   - Si no se puede completar el análisis de vínculos seguros, la protección de vínculos seguros no se activará. En los clientes de escritorio de Office, el usuario recibirá una advertencia antes de pasar al sitio web de destino.

> [!NOTE]
> Puede tardar varios segundos al principio de cada sesión para comprobar que el usuario tiene vínculos seguros para Office habilitado.

## <a name="block-the-following-urls-list-for-safe-links"></a>Lista "bloquear las siguientes direcciones URL" para vínculos seguros

La lista **bloquear las siguientes direcciones URL** define los vínculos que el análisis de vínculos seguros siempre bloquea en las siguientes ubicaciones:

- Mensajes de correo electrónico
- Documentos en aplicaciones de Office 365 en Windows y Mac.
- Documentos en Office para iOS y Android.

Cuando un usuario de una directiva de vínculos seguros activa hace clic en un vínculo bloqueado en una aplicación admitida, se le lleva a la página de [Advertencia de dirección URL bloqueada](#blocked-url-warning) .

Configure la lista de direcciones URL en la configuración global para vínculos seguros. Para obtener instrucciones, consulte [configurar la lista "bloquear las siguientes direcciones URL"](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center).

**Notas**:

- Para obtener una lista verdaderamente universal de las direcciones URL que están bloqueadas en todas partes, consulte [administrar direcciones URL en la lista de permitidos/bloqueados del inquilino](tenant-allow-block-list.md).

- Impuestos
  - El número máximo de entradas es 500.
  - La longitud máxima de una entrada es de 128 caracteres.
  - Todas las entradas no pueden superar los 10.000 caracteres.

- No incluya una barra diagonal ( `/` ) al final de la dirección URL. Por ejemplo, use `https://www.contoso.com` , no `https://www.contoso.com/` .

- Una dirección URL de dominio solamente (por ejemplo, `contoso.com` o `tailspintoys.com` ) bloqueará cualquier dirección URL que contenga el dominio.

- Puede bloquear un subdominio sin bloquear el dominio completo. Por ejemplo, `toys.contoso.com*` bloquea cualquier dirección URL que contenga el subdominio, pero no bloquea las direcciones URL que contienen el dominio completo `contoso.com` .

- Puede incluir hasta tres caracteres comodín ( `*` ) por entrada de dirección URL.

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>Sintaxis de la entrada de la lista "bloquear las siguientes direcciones URL"

En la tabla siguiente, se describen ejemplos de los valores que puede escribir y sus resultados:

****

|Valor|Resultado|
|---|---|
|`contoso.com` <p> o <p> `*contoso.com*`|Bloquea el dominio, los subdominios y las rutas de los. Por ejemplo, `https://www.contoso.com` , `https://sub.contoso.com` y `https://contoso.com/abc` se bloquean.|
|`https://contoso.com/a`|Bloques, `https://contoso.com/a` pero no subtrazados adicionales como `https://contoso.com/a/b` .|
|`https://contoso.com/a*`|Bloques `https://contoso.com/a` y subrutas adicionales como `https://contoso.com/a/b` .|
|`https://toys.contoso.com*`|Bloquea un subdominio ( `toys` en este ejemplo) pero permite hacer clic en otras direcciones URL de dominio (como `https://contoso.com` o `https://home.contoso.com` ).|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>Listas "no volver a escribir las siguientes direcciones URL" en directivas de vínculos a prueba de errores

> [!NOTE]
> Si su organización usa directivas de vínculos a prueba de errores, las siguientes listas de **direcciones URL no reescribirán** el único método admitido para las pruebas de suplantación de identidad de terceros.

Cada directiva de vínculos seguros contiene una lista no **reescribir las siguientes direcciones URL** que puede usar para especificar direcciones URL que no se reescriben mediante el análisis de vínculos seguros. Es decir, la lista permite que los usuarios incluidos en la Directiva tengan acceso a las direcciones URL especificadas que, de lo contrario, se bloquearían mediante vínculos seguros. Puede configurar distintas listas en las directivas de vínculos a prueba de errores diferentes. El procesamiento de directivas se detiene después de aplicar la primera Directiva (probablemente, la prioridad más alta) al usuario. Por lo tanto, solo una de ellas **no reescribe la siguiente lista de direcciones URL** se aplica a un usuario que se incluye en varias directivas de vínculos seguros activos.

Para agregar entradas a la lista en las directivas de vínculos seguros nuevos o existentes, consulte [crear directivas de vínculos seguros](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) o [modificar directivas de vínculos seguros](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies).

**Notas**:

- Los siguientes clientes no reconocen la lista no **reescribir las siguientes direcciones URL** en las directivas de vínculos a prueba de errores. Se puede bloquear el acceso de los usuarios incluidos en las directivas a las direcciones URL en función de los resultados del análisis de vínculos seguros en estos clientes:

  - Microsoft Teams
  - Office Web Apps

  Para obtener una lista verdaderamente universal de las direcciones URL que se permiten en cualquier lugar, consulte [administrar direcciones URL en la lista de permitidos/bloqueados del inquilino](tenant-allow-block-list.md).

- Considere la posibilidad de agregar direcciones URL internas de uso frecuente a la lista para mejorar la experiencia del usuario. Por ejemplo, si tiene servicios locales, como Skype empresarial o SharePoint, puede agregar esas direcciones URL para excluirlas del análisis.

- Si ya tiene las **siguientes entradas de URL no rescribirlas** en las directivas de vínculos a prueba de errores, asegúrese de revisar las listas y agregar caracteres comodín según sea necesario. Por ejemplo, la lista tiene una entrada como `https://contoso.com/a` y, más tarde, decide incluir subrutas como `https://contoso.com/a/b` . En lugar de agregar una nueva entrada, agregue un comodín a la entrada existente para que quede `https://contoso.com/a/*` .

- Puede incluir hasta tres caracteres comodín ( `*` ) por entrada de dirección URL. Los caracteres comodín incluyen explícitamente prefijos o subdominios. Por ejemplo, la entrada `contoso.com` no es la misma que `*.contoso.com/*` , ya que `*.contoso.com/*` permite a los usuarios visitar subdominios y rutas de acceso en el dominio especificado.

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>Sintaxis de la entrada "no volver a escribir las siguientes direcciones URL"

En la tabla siguiente, se describen ejemplos de los valores que puede escribir y sus resultados:

****

|Valor|Resultado|
|---|---|
|`contoso.com`|Permite el acceso, `https://contoso.com` pero no los subdominios o las rutas de acceso.|
|`*.contoso.com/*`|Permite el acceso a un dominio, subdominios y rutas de acceso (por ejemplo,,, `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` o `https://www.contoso.com/a` ). <p> Esta entrada es intrínsecamente mejor que `*contoso.com*` , porque no permite sitios potencialmente fraudulentos, como `https://www.falsecontoso.com` o `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Permite el acceso `https://contoso.com/a` , pero no los subtrazados como `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Permite el acceso `https://contoso.com/a` y las subrutas como `https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>Páginas de advertencia de vínculos seguros

Esta sección contiene ejemplos de las distintas páginas de advertencia que se activan mediante la protección de vínculos seguros al hacer clic en una dirección URL.

Tenga en cuenta que se han actualizado varias páginas de advertencia. Si aún no está viendo las páginas actualizadas, pronto lo hará. Las páginas actualizadas incluyen una nueva combinación de colores, más detalles y la posibilidad de continuar a un sitio a pesar de las advertencias y las recomendaciones especificadas.

### <a name="scan-in-progress-notification"></a>Notificación de análisis en curso

Los vínculos seguros están examinando la dirección URL en la que se hizo clic. Es posible que tenga que esperar unos minutos antes de volver a intentar el vínculo.

![Notificación "se está analizando el vínculo"](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

La página de notificaciones original tenía el siguiente aspecto:

![Notificación "el vínculo se está examinando" original](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a>ADVERTENCIA de mensaje sospechoso

La dirección URL en la que se hizo clic estaba en un mensaje de correo electrónico similar a otros mensajes sospechosos. Le recomendamos que vuelva a comprobar el mensaje de correo electrónico antes de continuar con el sitio.

![ADVERTENCIA "se hizo clic en un vínculo de un mensaje sospechoso"](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a>ADVERTENCIA de intento de phishing

La dirección URL en la que se hizo clic estaba en un mensaje de correo electrónico que se identificó como un ataque de suplantación de identidad. Como resultado, se bloquean todas las direcciones URL en el mensaje de correo electrónico. Le recomendamos que no continúe con el sitio.

![ADVERTENCIA "se hizo clic en el vínculo desde el mensaje de suplantación de identidad"](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a>ADVERTENCIA de sitio Web malintencionado

La dirección URL en la que se hace clic apunta a un sitio que se ha identificado como malintencionado. Le recomendamos que no continúe con el sitio.

![ADVERTENCIA "este sitio web está clasificado como malintencionado"](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

La página de advertencia original tenía el siguiente aspecto:

![ADVERTENCIA "este sitio web se ha clasificado como malintencionado" original](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a>ADVERTENCIA de dirección URL bloqueada

El administrador de la organización ha bloqueado manualmente la dirección URL en la que se ha pulsado (la lista **bloquear las siguientes direcciones URL** en la configuración global de vínculos seguros). Vínculos seguros no examinó el vínculo porque se bloqueó manualmente.

Hay varias razones por las que un administrador bloquearía manualmente direcciones URL específicas. Si cree que el sitio no debe bloquearse, póngase en contacto con el administrador.

![ADVERTENCIA "este sitio web fue bloqueado por su administrador"](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

La página de advertencia original tenía el siguiente aspecto:

![ADVERTENCIA del original "este sitio web se bloqueó según la Directiva de dirección URL de su organización"](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>ADVERTENCIA de error

Se ha producido algún tipo de error y no se puede abrir la dirección URL.

![ADVERTENCIA "la página a la que intenta obtener acceso no se puede cargar"](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

La página de advertencia original tenía el siguiente aspecto:

![ADVERTENCIA "esta página web no pudo cargarse" original](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
