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
description: En este artículo, los administradores pueden obtener información sobre la protección de vínculos seguros en Defender para Office 365 para proteger su organización contra la suplantación de identidad (phishing) y otros ataques que usan direcciones URL malintencionadas.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 251b3e71be30f90ac828abc8bf34877d65615336
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175780"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Vínculos seguros en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](office-365-atp.md). Si usa Outlook.com, Microsoft 365 Family o Microsoft 365 Personal, y está buscando información sobre safelinks en Outlook, consulte Advanced [Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Vínculos seguros es una característica de Defender para [Office 365](office-365-atp.md) que proporciona análisis y reescritura de direcciones URL de mensajes de correo electrónico entrantes en el flujo de correo, y comprobación con el tiempo de clic de direcciones URL y vínculos en mensajes de correo electrónico y otras ubicaciones. El examen de vínculos seguros se produce además de la protección contra correo electrónico no deseado y [antimalware](anti-spam-and-anti-malware-protection.md) normal en los mensajes de correo electrónico entrantes en Exchange Online Protection (EOP). El análisis de vínculos seguros puede ayudar a proteger su organización de vínculos malintencionados que se usan en ataques de suplantación de identidad (phishing) y otros ataques.

La protección de vínculos seguros está disponible en las siguientes ubicaciones:

- **Mensajes de correo** electrónico: la protección de vínculos seguros para vínculos en mensajes de correo electrónico se controla mediante directivas de vínculos seguros. No hay ninguna directiva de vínculos seguros predeterminada, por lo que para obtener la protección de vínculos seguros en mensajes de correo electrónico, debe crear una o más directivas **de vínculos seguros.** Para obtener instrucciones, [vea Configurar directivas de vínculos seguros en Microsoft Defender para Office 365.](set-up-atp-safe-links-policies.md)

  Para obtener más información acerca de la protección de vínculos seguros para mensajes de correo electrónico, vea la [sección](#safe-links-settings-for-email-messages) de configuración de vínculos seguros para mensajes de correo electrónico más adelante en este artículo.

- **Microsoft Teams** (actualmente en vista previa de TAP): la protección de vínculos seguros para vínculos en conversaciones de Teams, chats de grupo o canales también se controla mediante directivas de vínculos seguros. No hay ninguna directiva de vínculos seguros predeterminada, por lo que para obtener la protección de vínculos seguros en Teams, debe crear una o más directivas **de vínculos seguros.**

  Para obtener más información acerca de la protección de vínculos seguros en Teams, vea la sección de configuración de vínculos seguros [para Microsoft Teams](#safe-links-settings-for-microsoft-teams) más adelante en este artículo.

- **Aplicaciones de Office 365:** la protección de vínculos seguros para aplicaciones de Office 365 está disponible en aps de escritorio, móviles y web compatibles. Puede **configurar la** protección de vínculos seguros para las aplicaciones de Office 365 en la configuración global que están **fuera** de las directivas de vínculos seguros. Para obtener instrucciones, consulte Configuración global de la configuración [de vínculos seguros en Microsoft Defender para Office 365.](configure-global-settings-for-safe-links.md)

  Sin embargo, la protección de vínculos  seguros para aplicaciones de Office 365 solo se aplica a los usuarios que se incluyen en directivas de vínculos seguros activas. Si un usuario no está incluido en una directiva de vínculos seguros activa, el usuario no obtiene protección de vínculos seguros en las aplicaciones compatibles de Office 365.

  Para obtener más información acerca de la protección de vínculos seguros en aplicaciones de Office 365, vea la sección de configuración de vínculos seguros para aplicaciones de [Office 365](#safe-links-settings-for-office-365-apps) más adelante en este artículo.

En este artículo se incluyen descripciones detalladas de los siguientes tipos de configuración de vínculos seguros:

- **Configuración de las directivas de vínculos** seguros: esta configuración solo se aplica a los usuarios que se incluyen en las directivas específicas y la configuración puede ser diferente entre las directivas. Estas opciones incluyen:

  - [Configuración de vínculos seguros para mensajes de correo electrónico](#safe-links-settings-for-email-messages)
  - [Configuración de vínculos seguros para Microsoft Teams](#safe-links-settings-for-microsoft-teams)
  - ["No reescribir las siguientes direcciones URL" en las directivas de vínculos seguros](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **Configuración de vínculos seguros globales:** estas opciones se configuran globalmente, no en las directivas de vínculos seguros. Sin embargo, la configuración solo se aplica a los usuarios incluidos en las directivas de vínculos seguros activas. Estas opciones de configuración incluyen:

  - [Configuración de vínculos seguros para aplicaciones de Office 365](#safe-links-settings-for-office-365-apps)
  - [Lista "Bloquear las siguientes direcciones URL" para vínculos seguros](#block-the-following-urls-list-for-safe-links)

En la siguiente tabla se describen escenarios para vínculos seguros en organizaciones de Microsoft 365 y Office 365 que incluyen Defender para Office 365 (es decir, la falta de licencias nunca es un problema en los ejemplos).

****

|Escenario|Resultado|
|---|---|
|Juan es miembro del departamento de marketing. La protección de vínculos seguros para aplicaciones de Office 365 está activada en la configuración global de Vínculos seguros y existe una directiva de vínculos seguros que se aplica a los miembros del departamento de marketing. Juan abre una presentación de PowerPoint en un mensaje de correo electrónico y, a continuación, hace clic en una dirección URL de la presentación.|Juan está protegido por vínculos seguros. <p> Juan se incluye en una directiva de vínculos seguros y la protección de vínculos seguros para aplicaciones de Office 365 está activada. <p> Para obtener más información acerca de los requisitos para la protección de vínculos seguros en las aplicaciones de Office 365, vea la sección de configuración de vínculos seguros para aplicaciones de [Office 365](#safe-links-settings-for-office-365-apps) más adelante en este artículo.|
|La organización de Microsoft 365 E5 de Chris no tiene configuradas directivas de vínculos seguros. Chris recibe un correo electrónico de un remitente externo que contiene una dirección URL a un sitio web malintencionado en el que finalmente hace clic.|Chris no está protegido por vínculos seguros. <p> Un administrador debe crear al menos una directiva de vínculos seguros para que cualquier persona pueda obtener protección de vínculos seguros en mensajes de correo electrónico entrantes. Chris debe incluirse en las condiciones de la directiva para obtener la protección de vínculos seguros.|
|En la organización de Pat, ningún administrador ha creado directivas de vínculos seguros, pero la protección de vínculos seguros para aplicaciones de Office 365 está activada. Pat abre un documento de Word y hace clic en una dirección URL del archivo.|Pat no está protegido por vínculos seguros. <p> Aunque la protección de vínculos seguros para aplicaciones de Office 365 está activada globalmente, Pat no se incluye en ninguna de las directivas de vínculos seguros activas, por lo que no se puede aplicar la protección.|
|En la organización de Lee, se configura en la lista Bloquear las siguientes direcciones URL en la configuración `https://tailspintoys.com` global de Vínculos seguros.  Ya existe una directiva de vínculos seguros que incluya Lee. Lee recibe un mensaje de correo electrónico que contiene la dirección `https://tailspintoys.com/aboutus/trythispage` URL. Lee hace clic en la dirección URL.|Es posible que la dirección URL se bloquee automáticamente para Lee; depende de la entrada de la dirección URL en la lista y del cliente de correo electrónico que usó Lee. Para obtener más información, vea la [lista "Bloquear las siguientes](#block-the-following-urls-list-for-safe-links) direcciones URL" para vínculos seguros más adelante en este artículo.|
|Julia y Julia trabajan para contoso.com. Hace mucho tiempo, los administradores configuraron directivas de vínculos seguros que se aplican tanto a Julia como a Julia. Ara envía un correo electrónico a Julia, sin saber que el correo electrónico contiene una dirección URL malintencionada.|Julia está protegida  por vínculos seguros si la directiva de vínculos seguros que se aplica a ella está configurada para aplicarse a los mensajes entre destinatarios internos. Para obtener más información, vea la sección [Vínculos seguros para mensajes de](#safe-links-settings-for-email-messages) correo electrónico más adelante en este artículo.|

## <a name="safe-links-settings-for-email-messages"></a>Configuración de vínculos seguros para mensajes de correo electrónico

Vínculos seguros examina el correo electrónico entrante en busca de hipervínculos malintencionados conocidos. Las direcciones URL examinadas se reescriben con el prefijo de dirección URL estándar de Microsoft: `https://nam01.safelinks.protection.outlook.com` . Después de reescribir el vínculo, se analiza en busca de contenido potencialmente malintencionado.

Después de que Vínculos seguros reescriba una dirección URL, la dirección URL permanece reescrita, incluso si el mensaje se reenvía o responde. Los vínculos adicionales que se agregan al mensaje reenviado o respondido no se reescriben.

La configuración de las directivas de vínculos seguros que se aplican a los mensajes de correo electrónico se describe en la siguiente lista:

- **Seleccione la acción para direcciones URL potencialmente** malintencionadas desconocidas en los mensajes: habilita o deshabilita el examen de vínculos seguros en los mensajes de correo electrónico. El valor recomendado es **On**. Activar esta configuración da como resultado las siguientes acciones.

  - El examen de vínculos seguros está habilitado en Outlook (C2R) en Windows.
  - Las direcciones URL se reescriben y los usuarios se enrutan a través de la protección de vínculos seguros cuando hacen clic en las direcciones URL de los mensajes.
  - Cuando se hace clic, las direcciones URL se comprueban con una lista de direcciones URL malintencionadas conocidas y la lista ["Bloquear las siguientes direcciones URL".](#block-the-following-urls-list-for-safe-links)
  - Las direcciones URL que no tienen una reputación válida se detonan asincrónicamente en segundo plano.

- **Aplicar el examen de direcciones URL** en tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos: habilita el análisis en tiempo real de vínculos, incluidos los vínculos de los mensajes de correo electrónico que apuntan a contenido descargable. El valor recomendado está habilitado.

  - **Espere a que se complete el examen de direcciones URL antes de entregar el mensaje:**

    - Habilitado: los mensajes que contienen direcciones URL se mantienen hasta que finaliza el examen. Los mensajes se entregan solo después de confirmar que las direcciones URL son seguras. Este es el valor recomendado.
    - Deshabilitado: si el examen de direcciones URL no se puede completar, entrega el mensaje de todos modos.

- **Aplicar vínculos** seguros a los mensajes de correo electrónico enviados dentro de la organización: habilita o deshabilita el examen de vínculos seguros en los mensajes enviados entre remitentes internos y destinatarios internos dentro de la misma organización de Exchange Online. El valor recomendado está habilitado.

- **No realizar un seguimiento de los clics del usuario:** habilita o deshabilita el almacenamiento de datos de clic de vínculos seguros para las direcciones URL en las que se hace clic en los mensajes de correo electrónico. El valor recomendado es dejar esta configuración sin elegir (para realizar un seguimiento de los clics del usuario).

  Actualmente no se admite el seguimiento de clics de url para vínculos en mensajes de correo electrónico enviados entre remitentes internos y destinatarios internos.

- **No permitir que los usuarios hagan clic** en la dirección URL original: permite o impide que los usuarios hagan clic en la página de [advertencia](#warning-pages-from-safe-links) a la dirección URL original. El valor recomendado está habilitado.

- **No reescriba las siguientes direcciones URL:** deja las direcciones URL tal como están. Mantiene una lista personalizada de direcciones URL seguras que no necesitan análisis. La lista es única para cada directiva de vínculos seguros. Para obtener más información acerca de la sección No **reescribir** la siguiente lista de direcciones URL, vea las listas ["No reescribir](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) las siguientes direcciones URL" en la sección Directivas de vínculos seguros más adelante en este artículo.

Para obtener más información acerca de los valores recomendados para la configuración de directivas estándar y estricta para las directivas de vínculos seguros, vea la configuración de la directiva [de vínculos seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)

- **Filtros de** destinatarios: debe especificar las condiciones de destinatario y excepciones que determinan a quién se aplica la directiva. Puede usar estas propiedades para condiciones y excepciones:

  - **El destinatario es**
  - **El dominio del destinatario es**
  - **El destinatario es un miembro de**

  Solo puede usar una condición o excepción una vez, pero la condición o excepción puede contener varios valores. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

- **Prioridad:** si crea varias directivas, puede especificar el orden en que se aplican. Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

  Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).

### <a name="how-safe-links-works-in-email-messages"></a>Funcionamiento de vínculos seguros en mensajes de correo electrónico

En un nivel alto, aquí se muestra cómo funciona la protección de vínculos seguros en las direcciones URL de los mensajes de correo electrónico:

1. Todo el correo electrónico pasa por EOP, donde el protocolo de Internet (IP) y los filtros de sobre, la protección contra malware basada en firmas, el correo no deseado y los filtros antimalware antes de entregar el mensaje al buzón del destinatario.

2. El usuario abre el mensaje en su buzón y hace clic en una dirección URL del mensaje.

3. Vínculos seguros comprueba inmediatamente la dirección URL antes de abrir el sitio web:

   - Si la dirección URL se incluye en la lista Bloquear las siguientes direcciones **URL,** se abre una [advertencia de dirección URL](#blocked-url-warning) bloqueada.

   - Si la dirección URL apunta a un sitio [](#malicious-website-warning) web que se ha determinado como malintencionado, se abre una página de advertencia de un sitio web malintencionado (o una página de advertencia diferente).

   - Si la dirección URL apunta a un archivo descargable y la opción Aplicar análisis de url en tiempo **real** en busca de vínculos sospechosos y vínculos que apunten a la configuración de archivos está habilitada en la directiva que se aplica al usuario, se comprueba el archivo descargable.

   - Si se determina que la dirección URL es segura, se abre el sitio web.

## <a name="safe-links-settings-for-microsoft-teams"></a>Configuración de vínculos seguros para Microsoft Teams

> [!IMPORTANT]
> A partir de marzo de 2020, esta característica está en versión preliminar y solo está disponible para los miembros de microsoft Teams Programa de adopción de tecnología (TAP) (TAP). Para obtener información acerca de la programación de lanzamiento, consulte la guía [básica de Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)

Puede habilitar o deshabilitar la protección de vínculos seguros para Microsoft Teams en las directivas de vínculos seguros. Específicamente, use la opción Seleccionar la acción para direcciones URL desconocidas o potencialmente malintencionadas **dentro de la configuración de Microsoft Teams.** El valor recomendado es **On**.

Las siguientes opciones de configuración de las directivas de vínculos seguros que se aplican a los vínculos de los mensajes de correo electrónico también se aplican a los vínculos de Teams:

- **Aplicar análisis de url en tiempo real para vínculos sospechosos y vínculos que apunten a archivos**
- **No realizar un seguimiento de los clics del usuario**
- **No permitir que los usuarios hagan clic en la dirección URL original**

Esta configuración se explica en la sección anterior de [vínculos seguros para mensajes de correo](#safe-links-settings-for-email-messages) electrónico.

Después de activar la protección de vínculos seguros para Microsoft Teams, las direcciones URL de Teams se comprueban con una lista de vínculos malintencionados conocidos cuando el usuario protegido hace clic en el vínculo (protección con tiempo de clic). Las direcciones URL no se reescriben. Si se encuentra que un vínculo es malintencionado, los usuarios tendrán las siguientes experiencias:

- Si se hizo clic en el vínculo en una conversación de Teams, chat en grupo o desde canales, la página de advertencia, como se muestra en la captura de pantalla siguiente, aparecerá en el explorador web predeterminado.
- Si se hizo clic en el vínculo desde una pestaña anclada, la página de advertencia aparecerá en la interfaz de Teams dentro de esa pestaña. La opción para abrir el vínculo en un explorador web está deshabilitada por motivos de seguridad.
- Dependiendo de cómo se configure la opción No permitir a los usuarios hacer clic en la dirección **URL original** de la directiva, el usuario podrá o no hacer clic en la dirección URL original (continuar de todos modos **(no recomendado)** en la captura de pantalla). Se recomienda habilitar la opción No permitir a los usuarios hacer clic en la configuración de dirección **URL original** para que los usuarios no puedan hacer clic en la dirección URL original.

Si el usuario que envió el vínculo no está incluido en una directiva de vínculos seguros donde la protección de Teams está habilitada, el usuario puede hacer clic en la dirección URL original de su equipo o dispositivo.

![Una página Vínculos seguros para Teams que informa de un vínculo malintencionado.](../../media/tp-safe-links-for-teams-malicious.png)

Al hacer **clic en el botón** Volver atrás de la página de advertencia, el usuario volverá a su contexto o ubicación URL original. Sin embargo, si vuelve a hacer clic en el vínculo original, vínculos seguros volverá a examinar la dirección URL, por lo que la página de advertencia volverá a aparecer.

### <a name="how-safe-links-works-in-teams"></a>Funcionamiento de vínculos seguros en Teams

En un nivel alto, aquí se muestra cómo funciona la protección de vínculos seguros para las direcciones URL en Microsoft Teams:

1. Un usuario inicia la aplicación Teams.

2. Microsoft 365 comprueba que la organización del usuario incluye Microsoft Defender para Office 365 y que el usuario está incluido en una directiva de vínculos seguros activa donde la protección de Microsoft Teams está habilitada.

3. Las direcciones URL se validan en el momento de hacer clic para el usuario en chats, chats de grupo, canales y pestañas.

## <a name="safe-links-settings-for-office-365-apps"></a>Configuración de vínculos seguros para aplicaciones de Office 365

La protección de vínculos seguros para aplicaciones de Office 365 comprueba los vínculos de los documentos de Office, no los vínculos de los mensajes de correo electrónico (pero puede comprobar los vínculos de los documentos adjuntos de Office en los mensajes de correo electrónico después de abrir el documento).

La protección de vínculos seguros para aplicaciones de Office 365 tiene los siguientes requisitos de cliente:

- Aplicaciones de Microsoft 365 o Microsoft 365 Empresa Premium.
  - Versiones actuales de Word, Excel y PowerPoint en Windows, Mac o en un explorador web.
  - Aplicaciones de Office en dispositivos iOS o Android.
  - Visio en Windows.
  - OneNote en un explorador web.

- Las aplicaciones de Office 365 están configuradas para usar la autenticación moderna. Para obtener más información, vea Cómo funciona la autenticación moderna para aplicaciones cliente de [Office 2013, Office 2016 y Office 2019.](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)

- Los usuarios han iniciado sesión con sus cuentas de trabajo o escuela. Para obtener más información, vea [Iniciar sesión en Office.](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)

Puede configurar la protección de vínculos seguros para las aplicaciones de Office 365 en la configuración global de vínculos seguros, no en las directivas de vínculos seguros. Pero, para que se aplique la protección de vínculos seguros para aplicaciones de Office 365, el usuario que abre el documento de Office y hace clic en el vínculo debe incluirse en una directiva de vínculos seguros activa.

La siguiente configuración de vínculos seguros está disponible para las aplicaciones de Office 365:

- **Aplicaciones de Office 365:** habilita o deshabilita el examen de vínculos seguros en aplicaciones compatibles de Office 365. El valor predeterminado y recomendado es **On**.

- **No realice un seguimiento** de cuándo los usuarios hacen clic en Vínculos seguros: habilita o deshabilita el almacenamiento de datos de clic de vínculos seguros para las direcciones URL en las versiones de escritorio de Word, Excel, PowerPoint y Visio. El valor recomendado es **Desactivado,** lo que significa que se realiza un seguimiento de los clics del usuario.

- No permitir que los usuarios hagan clic a través de [](#warning-pages-from-safe-links) vínculos seguros a la dirección **URL original:** permite o impide que los usuarios hagan clic en la página de advertencia a la dirección URL original en las versiones de escritorio de Word, Excel, PowerPoint y Visio. El valor predeterminado y recomendado es **On**.

Para configurar las opciones de vínculos seguros para aplicaciones de Office 365, vea Configurar la protección de vínculos seguros para aplicaciones [de Office 365.](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)

Para obtener más información acerca de los valores recomendados para la configuración de directivas estándar y estricta, vea [Configuración global de vínculos seguros.](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links)

### <a name="how-safe-links-works-in-office-365-apps"></a>Funcionamiento de Vínculos seguros en aplicaciones de Office 365

En un nivel alto, aquí se muestra cómo funciona la protección de vínculos seguros para direcciones URL en aplicaciones de Office 365. Las aplicaciones compatibles de Office 365 se describen en la sección anterior.

1. Un usuario inicia sesión con su cuenta de trabajo o escuela en una organización que incluya Aplicaciones de Microsoft 365 o Microsoft 365 Empresa Premium.

2. El usuario abre y hace clic en un vínculo de un documento de Office en una aplicación compatible de Office.

3. Vínculos seguros comprueba inmediatamente la dirección URL antes de abrir el sitio web de destino:

   - Si la dirección URL se incluye en la  lista que omite el examen de vínculos seguros (la lista Bloquear las siguientes direcciones URL), se abre una página de advertencia [de dirección URL](#blocked-url-warning) bloqueada.

   - Si la dirección URL apunta a un sitio [](#malicious-website-warning) web que se ha determinado como malintencionado, se abre una página de advertencia de un sitio web malintencionado (o una página de advertencia diferente).

   - Si la dirección URL apunta a un archivo descargable y la directiva de vínculos seguros que se aplica al usuario está configurada para examinar vínculos a contenido descargable (aplicar análisis de url en tiempo **real** en busca de vínculos sospechosos y vínculos que apunten a archivos), se comprueba el archivo descargable.

   - Si la dirección URL se considera segura, el usuario se le redirige al sitio web.

   - Si no se puede completar el examen de vínculos seguros, la protección de vínculos seguros no se activa. En los clientes de escritorio de Office, se advertirá al usuario antes de continuar con el sitio web de destino.

> [!NOTE]
> Puede tardar varios segundos al principio de cada sesión comprobar que el usuario tiene habilitado Vínculos seguros para Office.

## <a name="block-the-following-urls-list-for-safe-links"></a>Lista "Bloquear las siguientes direcciones URL" para vínculos seguros

La **lista Bloquear las siguientes direcciones URL** define los vínculos que siempre están bloqueados por el examen de vínculos seguros en las siguientes ubicaciones:

- Mensajes de correo electrónico
- Documentos en aplicaciones de Office 365 en Windows y Mac.
- Documentos en Office para iOS y Android.

Cuando un usuario de una directiva de vínculos seguros activa hace clic en un vínculo bloqueado en una aplicación compatible, se le muestra la página de advertencia de [la dirección URL](#blocked-url-warning) bloqueada.

La lista de direcciones URL se configura en la configuración global de vínculos seguros. Para obtener instrucciones, [vea Configurar la lista "Bloquear las siguientes direcciones URL".](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)

**Notas**:

- Para obtener una lista realmente universal de direcciones URL bloqueadas en todas partes, vea Administrar la lista de permitidos [o bloqueados de inquilinos.](tenant-allow-block-list.md)

- Límites:
  - El número máximo de entradas es 500.
  - La longitud máxima de una entrada es de 128 caracteres.
  - Todas las entradas no pueden superar los 10.000 caracteres.

- No incluya una barra diagonal ( `/` ) al final de la dirección URL. Por ejemplo, use `https://www.contoso.com` , no `https://www.contoso.com/` .

- Una dirección URL de solo dominio (por ejemplo, o ) bloqueará `contoso.com` cualquier dirección URL que contenga el `tailspintoys.com` dominio.

- Puede bloquear un subdominio sin bloquear el dominio completo. Por ejemplo, bloquea cualquier dirección URL que contenga el subdominio, pero no bloquea las direcciones URL que `toys.contoso.com*` contienen el dominio `contoso.com` completo.

- Puede incluir hasta tres caracteres comodín ( `*` ) por entrada de dirección URL.

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>Sintaxis de entrada para la lista "Bloquear las siguientes direcciones URL"

En la tabla siguiente se describen ejemplos de los valores que puede especificar y sus resultados:

****

|Valor|Resultado|
|---|---|
|`contoso.com` <p> o <p> `*contoso.com*`|Bloquea el dominio, los subdominios y las rutas de acceso. Por ejemplo, `https://www.contoso.com` y `https://sub.contoso.com` están `https://contoso.com/abc` bloqueados.|
|`https://contoso.com/a`|`https://contoso.com/a`Bloques, pero no subpaths adicionales como `https://contoso.com/a/b` .|
|`https://contoso.com/a*`|Bloques `https://contoso.com/a` y subpaths adicionales como `https://contoso.com/a/b` .|
|`https://toys.contoso.com*`|Bloquea un subdominio (en este ejemplo) pero permite hacer clic en otras direcciones URL de `toys` dominio (como `https://contoso.com` o `https://home.contoso.com` ).|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>"No reescribir las siguientes direcciones URL" en las directivas de vínculos seguros

> [!NOTE]
> Si su organización usa directivas de vínculos seguros, no **reescribir** las siguientes listas de direcciones URL es el único método admitido para las pruebas de suplantación de identidad de terceros.

Cada directiva de vínculos seguros contiene una lista No **reescribir** la siguiente lista de direcciones URL que puede usar para especificar direcciones URL que no se reescriban mediante el examen de vínculos seguros. En otras palabras, la lista permite a los usuarios incluidos en la directiva obtener acceso a las direcciones URL especificadas que, de lo contrario, se bloquearían mediante vínculos seguros. Puede configurar diferentes listas en diferentes directivas de vínculos seguros. El procesamiento de directivas se detiene después de que se aplique la primera (probablemente, la prioridad más alta) al usuario. Por lo tanto, solo se aplica una no **reescritura** de la siguiente lista de direcciones URL a un usuario que está incluido en varias directivas de vínculos seguros activas.

Para agregar entradas a la lista en directivas de vínculos seguros nuevas o existentes, vea [Crear](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) directivas de vínculos seguros o [Modificar directivas de vínculos seguros.](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)

**Notas**:

- Los siguientes clientes no reconocen la opción **No reescribir** las siguientes listas de direcciones URL en las directivas de vínculos seguros. Se puede bloquear el acceso a las direcciones URL de los usuarios incluidos en las políticas en función de los resultados del examen de vínculos seguros en estos clientes:

  - Microsoft Teams
  - Aplicaciones web de Office

  Para obtener una lista realmente universal de direcciones URL que se permiten en todas partes, vea Administrar la lista de permitidos [o bloqueados del espacio empresarial.](tenant-allow-block-list.md)

- Considere la posibilidad de agregar direcciones URL internas usadas habitualmente a la lista para mejorar la experiencia del usuario. Por ejemplo, si tiene servicios locales, como Skype Empresarial o SharePoint, puede agregar esas direcciones URL para excluirlas del análisis.

- Si aún no ha **reescritura** las siguientes entradas de direcciones URL en las directivas de vínculos seguros, asegúrese de revisar las listas y agregar caracteres comodín según sea necesario. Por ejemplo, la lista tiene una entrada como y más adelante decide incluir `https://contoso.com/a` subpaths como `https://contoso.com/a/b` . En lugar de agregar una nueva entrada, agregue un carácter comodín a la entrada existente para que se convierta en `https://contoso.com/a/*` .

- Puede incluir hasta tres caracteres comodín ( `*` ) por entrada de dirección URL. Los caracteres comodín incluyen explícitamente prefijos o subdominios. Por ejemplo, la entrada no es la misma que , porque permite a los usuarios visitar subdominios y rutas de acceso `contoso.com` `*.contoso.com/*` en el dominio `*.contoso.com/*` especificado.

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>Sintaxis de entrada para la lista "No reescribir las siguientes direcciones URL"

En la tabla siguiente se describen ejemplos de los valores que puede especificar y sus resultados:

****

|Valor|Resultado|
|---|---|
|`contoso.com`|Permite el acceso a `https://contoso.com` subdominios o rutas de acceso, pero no a subdominios.|
|`*.contoso.com/*`|Permite el acceso a un dominio, subdominios y rutas de acceso (por ejemplo, `https://www.contoso.com` `https://www.contoso.com` , , o `https://maps.contoso.com` `https://www.contoso.com/a` ). <p> Esta entrada es inherentemente mejor que , porque no permite sitios `*contoso.com*` potencialmente fraudulentos, como `https://www.falsecontoso.com` o `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Permite el acceso `https://contoso.com/a` a , pero no a subpaths como `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Permite el acceso `https://contoso.com/a` y las subpaths como `https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>Páginas de advertencia de vínculos seguros

Esta sección contiene ejemplos de las distintas páginas de advertencia que desencadena la protección de vínculos seguros al hacer clic en una dirección URL.

Tenga en cuenta que se han actualizado varias páginas de advertencia. Si aún no ve las páginas actualizadas, lo verá pronto. Las páginas actualizadas incluyen una nueva combinación de colores, más detalles y la capacidad de continuar con un sitio a pesar de las advertencias y recomendaciones dadas.

### <a name="scan-in-progress-notification"></a>Notificación de examen en curso

Vínculos seguros examina la dirección URL en la que se hizo clic. Es posible que deba esperar unos minutos antes de volver a intentar el vínculo.

![Notificación "Se está analizando el vínculo"](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

La página de notificación original tenía este aspecto:

![Notificación original "Se está analizando el vínculo"](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a>Advertencia de mensaje sospechoso

La dirección URL en la que se hizo clic estaba en un mensaje de correo electrónico similar a otros mensajes sospechosos. Le recomendamos que compruebe de nuevo el mensaje de correo electrónico antes de continuar con el sitio.

![Advertencia "Se hizo clic en un vínculo desde un mensaje sospechoso"](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a>Advertencia de intento de suplantación de identidad

La dirección URL en la que se hizo clic estaba en un mensaje de correo electrónico que se ha identificado como un ataque de suplantación de identidad. Como resultado, se bloquean todas las direcciones URL del mensaje de correo electrónico. Se recomienda no continuar con el sitio.

![Advertencia "Se hizo clic en el vínculo desde un mensaje de suplantación de identidad"](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a>Advertencia de sitio web malintencionado

La dirección URL en la que se hizo clic apunta a un sitio identificado como malintencionado. Se recomienda no continuar con el sitio.

![Advertencia "Este sitio web se clasifica como malintencionado"](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

La página de advertencia original tenía este aspecto:

![Advertencia original "Este sitio web se ha clasificado como malintencionado"](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a>Advertencia de dirección URL bloqueada

Un administrador de la organización bloqueó manualmente la dirección URL en la que se hizo clic (la lista Bloquear las siguientes direcciones **URL** en la configuración global de Vínculos seguros). Vínculos seguros no ha analizado el vínculo porque se bloqueó manualmente.

Hay varias razones por las que un administrador bloquearía manualmente direcciones URL específicas. Si cree que el sitio no debe bloquearse, póngase en contacto con su administrador.

![Advertencia "El administrador bloqueó este sitio web"](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

La página de advertencia original tenía este aspecto:

![Advertencia original "Este sitio web se ha bloqueado según la directiva de dirección URL de la organización"](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>Advertencia de error

Se ha producido algún tipo de error y no se puede abrir la dirección URL.

![Advertencia de "No se puede cargar la página a la que está intentando acceder"](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

La página de advertencia original tenía este aspecto:

![Advertencia original de "No se pudo cargar esta página web"](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
