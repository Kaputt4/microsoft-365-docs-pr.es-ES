---
title: Configuración de las directivas de filtro de correo no deseado
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender cómo ver, crear, modificar y eliminar directivas contra correo electrónico no deseado en Exchange Online Protection (EOP).
ms.openlocfilehash: 2bb6bff5fae661d755ea19dbb5af8ca62fbacbd8
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130868"
---
# <a name="configure-anti-spam-policies-in-eop"></a>Configuración de directivas contra correo no deseado en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En organizaciones de Microsoft 365 con buzones de correo de Exchange Online u organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP protege automáticamente los mensajes de correo electrónico entrantes contra el correo no deseado. EOP usa directivas de bloqueo de correo no deseado (también conocidas como directivas de filtro de correo no deseado o directivas de filtro de contenido) como parte de la defensa general de la organización contra el correo no deseado. Para obtener más información, consulte [Protección contra correo no deseado](anti-spam-protection.md).

Los administradores pueden ver, editar y configurar (pero no eliminar) la directiva contra correo no deseado predeterminada. Para disfrutar de una mayor granularidad, también puede crear directivas personalizadas de filtro de correo no deseado que se aplican a usuarios, grupos o dominios específicos de la organización. Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.

Puede configurar directivas contra correo no deseado en el Centro de seguridad y cumplimiento o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; EOP PowerShell independiente para organizaciones sin buzones de Exchange Online).

Los elementos básicos de una directiva contra correo no deseado son:

- **La directiva de filtro de correo no deseado**: especifica las acciones para los veredictos de filtro de correo no deseado y las opciones de notificación.
- **La regla de filtro de correo no deseado**: especifica la prioridad y los filtros de destinatarios (a los que se aplica la directiva) de una directiva de filtro de correo no deseado.

La diferencia entre estos dos elementos no es obvia cuando administra directivas contra correo no deseado en el Centro de seguridad y cumplimiento:

- Cuando crea una directiva contra correo no deseado, en realidad, está creando una regla de filtro de correo no deseado y, al mismo tiempo, la directiva de filtro de correo no deseado asociada a esta, con el mismo nombre para ambas.
- Al modificar una directiva contra correo no deseado, las opciones de configuración relacionadas con el nombre, la prioridad, el activado o desactivado y los filtros de destinatarios modifican la regla de filtro de correo no deseado. Todas las demás opciones modifican la directiva de filtro de correo no deseado asociada.
- Cuando se quita una directiva contra correo no deseado, se elimina la regla de filtro de correo no deseado y la directiva de filtro de correo no deseado asociada.

En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado. Para más información, consulte la sección [Uso de Exchange Online PowerShell o EOP PowerShell independiente para configurar directivas contra correo no deseado](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies), que se muestra más adelante en este mismo tema.

Cada organización tiene una directiva contra correo no deseado integrada que se denomina Predeterminada, que tiene estas propiedades:

- La directiva se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla de filtro de correo no deseado (filtros de destinatarios) asociada a la directiva.
- La directiva tiene un valor de prioridad personalizado **Mínimo** que no se puede modificar (la directiva siempre se aplica en último lugar). Las directivas personalizadas que cree siempre tendrán una prioridad mayor.
- La directiva es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar esta directiva predeterminada.

Para aumentar la eficacia del filtrado de correo no deseado, puede crear directivas de bloqueo de correo no deseado personalizadas con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página **Configuración contra correo no deseado**, use <https://protection.office.com/antispam>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Para poder realizar los procedimientos de este tema, deberá tener asignados los permisos necesarios:

  - Para agregar, modificar y eliminar directivas de correo no deseado, deberá ser miembro de uno de los siguientes grupos de roles:

    - **Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).
    - **Administración de la organización** o **Administración de higiene** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Para obtener acceso de solo lectura a las directivas de correo no deseado, deberá ser miembro de uno de los siguientes grupos de roles:

    - **Lector de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).
    - **Administración de la organización de solo visualización** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Para saber la configuración recomendada para las directivas contra correo electrónico no deseado, consulte [Configuración de la directiva de correo no deseado de EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a>Uso del Centro de seguridad y cumplimiento para crear directivas contra correo no deseado

La creación de una directiva contra correo no deseado en el Centro de seguridad y cumplimiento crea una regla de filtro de correo no deseado y la directiva de filtro de correo no deseado asociada al mismo tiempo con el mismo nombre para ambas.

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la página **Configuración contra correo no deseado**, haga clic en **Crear una directiva**.

3. En la ventana **Nuevo directiva de filtro contra correo no deseado** que se abre, configure las siguientes opciones:

   - **Nombre**: escriba un nombre único y descriptivo para la directiva. No use los siguientes caracteres: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.

      Si previamente creó directivas contra correo no deseado en el Centro de admin. de Exchange (EAC) que contiene estos caracteres, debe cambiar el nombre de la directiva contra correo no deseado en PowerShell. Para obtener instrucciones, consulte la sección [Uso de PowerShell para modificar las reglas de filtro de correo no deseado](#use-powershell-to-modify-spam-filter-rules) más adelante en este tema.

   - **Descripción**: escriba una descripción opcional para la directiva.

4. (Opcional) Amplíe la sección **Acciones de correo electrónico en masa y correo no deseado** y compruebe o configure las siguientes opciones:

   - **Seleccionar la acción que se llevará a cabo en caso de correo no deseado entrante y correo electrónico en masa**: seleccione o revise la acción que se llevará a cabo en los mensajes en función de los siguientes veredictos de filtrado de correo no deseado:

     - **Correo no deseado**
     - **Correo no deseado de alta confianza**
     - **Correo de suplantación de identidad**
     - **Correo de suplantación de identidad de alta confianza**
     - **Correo electrónico en masa**

     En la siguiente tabla se describen las acciones disponibles en los veredictos de filtrado de correo no deseado.

     - Una marca de verificación ( ![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)) indica que la acción está disponible (no todas las acciones están disponibles para todos los veredictos de filtrado de correo no deseado).
     - Un asterisco (<sup>\*</sup>) después de la marca de verificación indica la acción predeterminada para el veredicto de filtrado de correo no deseado.

     ****

     |<span>|Correo no deseado|Alto<br/>confianza<br/>correo no deseado|Suplantación de identidad (phishing)<br/>correo electrónico|Alto<br/>confianza<br/>suplantación de identidad (phishing)<br/>correo electrónico|Masivo<br/>correo electrónico|
     |---|:---:|:---:|:---:|:---:|:---:|
     |**Mover el mensaje a la carpeta Correo no deseado**: el mensaje se entrega al buzón y se mueve a la carpeta Correo no deseado.<sup>1</sup>|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
     |**Agregar encabezado X**: agrega un encabezado X al encabezado del mensaje y entrega el mensaje al buzón. <p> Especifique el nombre de campo del encabezado X (no el valor) más adelante en el cuadro **Agregar este texto de encabezado X**. <p> Para los veredictos **Correo no deseado** y **Correo no deseado de alta confianza**, el mensaje se mueve a la carpeta Correo no deseado.<sup>1,2</sup>|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
     |**Anteponer la línea de asunto al texto**: agrega texto al principio de la línea de asunto del mensaje. El mensaje se entrega al buzón y se mueve a la carpeta Correo no deseado.<sup>1,2</sup> <p> Especifique el texto más adelante en el cuadro **Prefijo de línea de asunto con este texto**.|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**Redirigir el mensaje a la dirección de correo electrónico**: envía el mensaje a otros destinatarios en vez de a los especificados. <p> Especifique los destinatarios más tarde en el cuadro **Redirigir a esta dirección de correo electrónico**.|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**Eliminar mensaje**: elimina el mensaje completo, incluidos todos los datos adjuntos.|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**Colocar el mensaje en cuarentena**: envía el mensaje a la cuarentena en lugar de a los destinatarios. <p> Especifique cuánto tiempo se debe conservar el mensaje en cuarentena más adelante en el cuadro **Cuarentena**.|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**Ninguna acción**|||||![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |

     <sup>1</sup> En Exchange Online, el mensaje se mueve a la carpeta Correo no deseado si está habilitada la regla de correo no deseado en el buzón (está activada de forma predeterminada). Para más información, consulte [Configuración de las opciones del correo no deseado en buzones de Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).

     En entornos de EOP independientes en los que EOP protege los buzones de Exchange locales, tiene que configurar las reglas de flujo de correo (también conocidas como reglas de transporte) en Exchange local para traducir el veredicto de filtro de correo no deseado de EOP para que la regla de correo no deseado pueda mover el mensaje a la carpeta de correo electrónico no deseado. Para obtener información, consulte [Configuración de un EOP independiente para entregar el correo no deseado en la carpeta de correo no deseado en entornos híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

     <sup>2</sup> Puede usar este valor como condición en las reglas de flujo de correo (también conocidas como reglas de transporte) para filtrar o redirigir el mensaje.

   - **Seleccionar el umbral**: especifica el nivel de quejas masivas (BCL) de un mensaje que desencadena la acción especificada para el veredicto de filtro de correo no deseado **Correo electrónico en masa** (mayor que el valor especificado, no mayor o igual a él). Un valor superior indica que el mensaje es menos deseado (tiene más posibilidades de parecer correo no deseado). El valor predeterminado es 7. Para más información, consulte [Valores de nivel de quejas masivas (BCL) en EOP](bulk-complaint-level-values.md) y [¿Cuál es la diferencia entre el correo electrónico no deseado y el correo electrónico en masa?](what-s-the-difference-between-junk-email-and-bulk-email.md).

     De forma predeterminada, la configuración solo para PowerShell _MarkAsSpamBulkMail_ está `On` en directivas contra correo no deseado. Esta configuración afecta mucho a los resultados de un veredicto de filtro de **correo electrónico en masa**:

     - **_MarkAsSpamBulkMail_ está Activado**: una BCL que es superior al umbral se convierte en un SCL 6 que corresponde a un veredicto de filtro de **Correo no deseado**, y la acción del veredicto de filtro de **Correo electrónico en masa** se lleva a cabo en el mensaje.

     - **_MarkAsSpamBulkMail_ está desactivada**: el mensaje está marcado con los BCL, pero no se realiza _ninguna acción_ para un veredicto de filtro de **Correo electrónico en masa**. De hecho, el umbral de BCL y el veredicto de filtrado de **Correo electrónico en masa** no es relevante.

   - **Cuarentena**: especifica cuánto tiempo debe mantenerse el mensaje en cuarentena si ha seleccionado **Mensaje en cuarentena** como la acción para un veredicto de filtrado de correo no deseado. Cuando expire el período de tiempo, el mensaje se eliminará. El valor predeterminado es 30 días. Los valores válidos están comprendidos entre 1 y 30 días. Para obtener más información acerca de la cuarentena, consulte los siguientes temas:

     - [Mensajes en cuarentena en EOP](quarantine-email-messages.md)
     - [Administración de mensajes en cuarentena y archivos como administrador en EOP](manage-quarantined-messages-and-files.md)
     - [Búsqueda y liberación de mensajes en cuarentena como usuario en EOP](find-and-release-quarantined-messages-as-a-user.md)

   - **Agregar este texto de encabezado X**: este cuadro es obligatorio y solo está disponible si se ha seleccionado **Agregar encabezado X** como acción para un veredicto de filtrado de correo no deseado. El valor que especifique es el *nombre* del campo de encabezado que se agrega al encabezado del mensaje. El *valor* del campo de encabezado siempre es `This message appears to be spam`.

     La longitud máxima es de 255 caracteres y el valor no puede contener espacios o dos puntos (:).

     Por ejemplo, si escribe el valor `X-This-is-my-custom-header`, el encabezado X que se agrega al mensaje es `X-This-is-my-custom-header: This message appears to be spam.`

     Si escribe un valor que contiene espacios o dos puntos (:), el valor que escriba se ignora y se agrega el encabezado X predeterminado al mensaje (`X-This-Is-Spam: This message appears to be spam.`).

   - **Anteponer la línea de asunto con este texto**: este cuadro es obligatorio y solo está disponible si se ha seleccionado **Anteponer la línea de asunto con este texto** como acción para un veredicto de filtrado de correo no deseado. Escriba el texto que se agregará al principio de la línea de asunto del mensaje.

   - **Redirigir a esta dirección de correo electrónico**: este cuadro es obligatorio y solo está disponible si ha seleccionado la **Redirigir el mensaje a dirección de correo electrónico** como la acción para un veredicto de filtrado de correo no deseado. Escriba la dirección de correo electrónico a la que quiere enviar el mensaje. Puede especificar varios valores separados por punto y coma (;).

   - **Sugerencias de seguridad**: de forma predeterminada, las Sugerencias de seguridad están habilitadas, pero puede deshabilitarlas si desactiva la casilla de verificación **Activada**. Para obtener más información sobre las Sugerencias de seguridad, consulte [Sugerencias de seguridad en mensajes de correo electrónico](safety-tips-in-office-365.md).

   Configuración **Purga automática**: la Purga automática detecta y realiza acciones en mensajes que ya se han entregado a buzones de Exchange Online. Para obtener más información sobre la Purga automática, consulte [Purga automática: protección contra correo no deseado y malware](zero-hour-auto-purge.md).

   - **Purga automática de correo no deseado**: de forma predeterminada, la Purga automática está habilitada para las detecciones de correo no deseado, pero puede deshabilitarla si desactiva la casilla de verificación **Activada**.

   - **Purga automática de correo de suplantación de identidad**: de forma predeterminada, la Purga automática está habilitada para las detecciones de correo de suplantación de identidad, pero puede deshabilitarla si desactiva la casilla de verificación **Activada**.

5. (Opcional) Expanda la sección **Listas de permitidos** para configurar los remitentes de mensajes según la dirección de correo electrónico o el dominio de correo electrónico que pueden omitir el filtrado de correo no deseado:

   > [!CAUTION]
   >
   > - Piense muy atentamente antes de agregar dominios aquí. Para más información, consulte [Crear listas de remitentes seguros en EOP](create-safe-sender-lists-in-office-365.md)
   >
   > - Nunca agregue dominios aceptados (dominios de su propiedad) o dominios comunes (por ejemplo, microsoft.com o office.com) a la lista de dominios permitidos. Esto permitiría que los atacantes envíen correo electrónico que omita el filtrado de correo no deseado en la organización.

   - **Permitir remitente**: haga clic en **Editar**. En la ventana **Lista de remitentes permitidos** que aparece:

      a. Escriba la dirección de correo electrónico del remitente. Puede especificar varias direcciones de correo electrónico separadas por punto y coma (;).

      b. Haga clic en ![Icono Agregar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) para agregar los remitentes.

      Repita estos pasos tantas veces como sea necesario.

      Los remitentes que agregue aparecerán en la sección **Remitentes permitidos** en la ventana. Para eliminar un remitente, haga clic en el ![icono Quitar](../../media/scc-remove-icon.png).

      Cuando haya terminado, haga clic en **Guardar**.

   - **Permitir dominio**: haga clic en **Editar**. En la ventana **Lista de dominios permitidos** que aparece, siga estos pasos:

      a. Escriba el dominio. Puede especificar varios dominios separados por punto y coma (;).

      b. Haga clic en ![Icono Agregar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) para agregar los dominios.

      Repita estos pasos tantas veces como sea necesario.

      Los dominios que agregue aparecerán en la sección **Dominios permitidos** en la ventana. Para eliminar un dominio, haga clic en el ![icono Quitar](../../media/scc-remove-icon.png).

      Cuando haya terminado, haga clic en **Guardar**.

6. (Opcional) Expanda la sección **Listas de bloqueados** para configurar los remitentes de mensajes según la dirección de correo electrónico o el dominio de correo electrónico que siempre se marcarán como correo no deseado de alta confianza:

   > [!NOTE]
   > Bloquear manualmente los dominios no es peligroso, pero puede incrementar la carga de trabajo administrativa. Para más información, consulte [Crear listas de remitentes bloqueados en EOP](create-block-sender-lists-in-office-365.md)

   - **Bloquear remitente**: haga clic en **Editar**. En la ventana **Lista de remitentes bloqueados** que aparece, siga estos pasos:

      a. Escriba la dirección de correo electrónico del remitente. Puede especificar varias direcciones de correo electrónico separadas por punto y coma (;). No se admiten los caracteres comodín (*).

      b. Haga clic en ![Icono Agregar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) para agregar los remitentes.

      Repita estos pasos tantas veces como sea necesario.

      Los remitentes que agregue aparecerán en la sección **Remitentes bloqueados** en la ventana. Para eliminar un remitente, haga clic en el ![botón Quitar](../../media/scc-remove-icon.png).

      Cuando haya terminado, haga clic en **Guardar**.

   - **Bloquear dominio**: haga clic en **Editar**. En la **lista Dominios bloqueados** que aparece:

      a. Escriba el dominio. Puede especificar varios dominios separados por punto y coma (;). No se admiten los caracteres comodín (*).

      b. Haga clic en ![Icono Agregar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) para agregar los dominios.

      Repita estos pasos tantas veces como sea necesario.

      Los dominios que agregue aparecerán en la lista **Dominios bloqueados** en la ventana. Para eliminar un dominio, haga clic en el ![botón Quitar](../../media/scc-remove-icon.png).

      Cuando haya terminado, haga clic en **Guardar**.

7. (Opcional) Expanda la sección **Correo no deseado internacional** para configurar los idiomas de correo electrónico o países de origen bloqueados por el filtrado de correo no deseado:

   - **Filtrar mensajes de correo electrónico escritos en los siguientes idiomas**: esta opción está deshabilitada de forma predeterminada (**Estado: Desactivada**). Haga clic en **Editar**. En la **Configuración de correo no deseado internacional** que aparece, configure las siguientes opciones:

     - **Filtrar mensajes de correo electrónico en los siguientes idioma**: seleccione la casilla para habilitar esta configuración. Desactive la casilla para deshabilitar esta configuración.

     - Haga clic en el cuadro y empiece a escribir el *nombre* del idioma. Se mostrará una lista filtrada de idiomas compatibles, junto con el código de lenguaje ISO 639-2. Cuando encuentre el idioma que está buscando, selecciónelo. Repita este paso tantas veces como sea necesario.

       La lista de idiomas que ha seleccionado aparece en el control flotante. Para eliminar un idioma, haga clic en ![el botón Quitar](../../media/scc-remove-icon.png).

     Cuando haya terminado, haga clic en **Guardar**.

   - **Filtrar mensajes de correo electrónico enviados de los siguientes países o regiones**: esta opción está deshabilitada de forma predeterminada (estado **: desactivada**). Para habilitarla, haga clic en **Editar**. En la **Configuración de correo no deseado internacional** que aparece, configure las siguientes opciones:

     - Seleccione la casilla **Filtrar mensajes de correo electrónico de los siguientes países o regiones** para habilitar esta configuración. Desactive la casilla para deshabilitar esta configuración.

     - Haga clic en el cuadro y empiece a escribir el *nombre* del país o región. Se mostrará una lista filtrada de países compatibles, junto con el código de país de dos letras ISO 3166-1. Cuando encuentre el idioma o región que está buscando, selecciónelo. Repita este paso tantas veces como sea necesario.

       La lista de países que ha seleccionado aparece en el control flotante. Para eliminar un país o una región, haga clic en ![el botón Quitar](../../media/scc-remove-icon.png).

     Cuando haya terminado, haga clic en **Guardar**.

8. La sección opcional **Propiedades del correo no deseado** contiene las opciones avanzadas de filtro de correo no deseado (ASF) que están desactivadas de forma predeterminada. Las opciones ASF pronto estarán en desuso y su funcionalidad se incorporará a otras partes de la pila de filtrado. Se recomienda desactivar todas las opciones de ASF en las directivas contra el correo no deseado.

   Para más información sobre estas opciones, consulte [Opciones avanzadas de filtro de correo no deseado en EOP](advanced-spam-filtering-asf-options.md).

9. (Obligatorio) Expanda la sección **Se aplica a** para identificar los destinatarios internos a los que se aplica la directiva.

    Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

    Es más fácil hacer clic en **Agregar una condición** tres veces para ver todas las condiciones disponibles. Puede hacer clic en el ![botón Quitar](../../media/scc-remove-icon.png) para quitar condiciones que no quiera configurar.

    - **El dominio del destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en su organización. Haga clic en el cuadro **Agregar una etiqueta** para ver y seleccionar un dominio. Haga clic de nuevo en el cuadro **Agregar una etiqueta** para seleccionar dominios adicionales si hay más de un dominio disponible.

    - **El destinatario es**: especifica uno o varios buzones, usuarios de correo o contactos de correo de su organización. Haga clic en **Agregar una etiqueta** y comience a escribir para filtrar la lista. Haga clic de nuevo en el cuadro **Agregar una etiqueta** para seleccionar otros destinatarios.

    - **El destinatario es un miembro de**: especifica uno o más grupos de su organización. Haga clic en **Agregar una etiqueta** y comience a escribir para filtrar la lista. Haga clic de nuevo en el cuadro **Agregar una etiqueta** para seleccionar otros destinatarios.

    - **Excepto si**: para agregar excepciones para la regla, haga clic en **Agregar una condición** tres veces para ver todas las excepciones disponibles. La configuración y el comportamiento se muestran exactamente igual que las condiciones.

10. Cuando haya terminado, haga clic en **Guardar**.

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a>Uso del Centro de seguridad y cumplimiento para ver directivas contra correo no deseado

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la página **Configuración contra el correo no deseado**, haga clic en el ![icono expandir](../../media/scc-expand-icon.png) para expandir una directiva contra correo no deseado:

   - La directiva predeterminada denominada **Directiva de filtro de correo no deseado predeterminada**.

   - Una directiva personalizada que creó, cuyo valor de la columna **Tipo** es **Directiva contra correo no deseado personalizada**.

3. Las opciones de directiva importantes se muestran en los detalles de la directiva expandidos que aparecen. Para ver más detalles, haga clic en **Editar directiva**.

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a>Uso del Centro de seguridad y cumplimiento para modificar directivas contra correo no deseado

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la página **Configuración contra el correo no deseado**, haga clic en el ![icono expandir](../../media/scc-expand-icon.png) para expandir una directiva contra correo no deseado:

   - La directiva predeterminada denominada **Directiva de filtro de correo no deseado predeterminada**.

   - Una directiva personalizada que creó, cuyo valor de la columna **Tipo** es **Directiva contra correo no deseado personalizada**.

3. Haga clic en **Editar directiva**.

Para las directivas de correo no deseado personalizadas, las opciones de configuración disponibles en el control flotante que aparecen son las mismas que las descritas en la sección [Uso del Centro de seguridad y cumplimiento para crear directivas contra correo no deseado](#use-the-security--compliance-center-to-create-anti-spam-policies).

Para la directiva contra correo no deseado predeterminada denominada **Directiva de filtro de correo no deseado predeterminada**, la sección **Se aplica a** no está disponible (la directiva se aplica a todos los usuarios) y no se puede cambiar el nombre de la directiva.

Vea las secciones siguientes para habilitar o deshabilitar una directiva, establecer el orden de prioridad de la directiva o configurar las notificaciones en cuarentena para el usuario final.

### <a name="enable-or-disable-anti-spam-policies"></a>Habilitar o deshabilitar las directivas contra correo no deseado

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la página **Configuración contra el correo no deseado**, haga clic en el ![icono expandir](../../media/scc-expand-icon.png) para expandir una directiva personalizada que creó (el valor de la columna **Tipo** es **Directiva contra el correo no deseado personalizada**).

3. En los detalles de la directiva expandida que aparecen, observe el valor de la columna **Habilitada**.

   Mueva el botón de alternancia a la izquierda para deshabilitar la directiva: ![Deshabilitar](../../media/scc-toggle-off.png)

   Mueva el botón de alternancia a la derecha para habilitar la directiva: ![Habilitar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

No se puede deshabilitar la directiva contra correo no deseado predeterminada.

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>Establecer la prioridad de las directivas contra correo no deseado personalizadas

De manera predeterminada, a las directivas contra correo no deseado se les asigna una prioridad en función del orden en que se crearon (las directivas más recientes tienen una prioridad menor que las directivas anteriores). Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor). Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).

Las directivas contra correo no deseado personalizadas se muestran en el orden en que se procesan (la primera directiva tiene el valor de **Prioridad** 0). La directiva contra correo no deseado predeterminada denominada **Directiva de filtro de correo no deseado predeterminada** tiene el valor de prioridad **Mínimo**, y no puede cambiarlo.

 **Tenga en cuenta**: en el Centro de seguridad y cumplimiento, solo puede cambiar la prioridad de la directiva contra correo no deseado después de crearla. En PowerShell, puede reemplazar la prioridad predeterminada al crear la regla de filtro de correo no deseado (que puede afectar a la prioridad de las reglas existentes).

Para cambiar la prioridad de una directiva, suba o baje la directiva en la lista (no puede modificar directamente el número de **Prioridad** en el Centro de seguridad y cumplimiento).

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la página **Configuración contra correo no deseado**, busque las directivas en las que el valor de la columna **Tipo** es **Directiva contra correo no deseado personalizada**. Observe los valores de la columna **Prioridad**:

   - La directiva contra correo no deseado personalizada que tiene la prioridad máxima tiene el valor de ![icono de flecha abajo](../../media/ITPro-EAC-DownArrowIcon.png) **0**.

   - La directiva contra correo no deseado personalizada que tiene la prioridad mínima tiene el valor ![icono de flecha arriba](../../media/ITPro-EAC-UpArrowIcon.png) **n** (por ejemplo, ![icono de flecha arriba](../../media/ITPro-EAC-UpArrowIcon.png) **3**).

   - Si tiene tres o más directivas contra correo no deseado personalizadas, las directivas entre la prioridad máxima y la mínima tienen valores ![icono de flecha arriba](../../media/ITPro-EAC-UpArrowIcon.png)![icono de flecha abajo](../../media/ITPro-EAC-DownArrowIcon.png) **n** (por ejemplo, ![icono de flecha arriba](../../media/ITPro-EAC-UpArrowIcon.png)![icono de flecha abajo](../../media/ITPro-EAC-DownArrowIcon.png) **2**).

3. Haga clic en ![Icono flecha arriba](../../media/ITPro-EAC-UpArrowIcon.png) o ![Icono flecha abajo](../../media/ITPro-EAC-DownArrowIcon.png) para mover la directiva contra correo no deseado personalizada hacia arriba o hacia abajo en la lista de prioridades.

### <a name="configure-end-user-spam-notifications"></a>Configurar notificaciones de correo no deseado para el usuario final

Cuando un veredicto de filtrado de correo no deseado pone en cuarentena un mensaje, puede configurar las notificaciones de correo no deseado para el usuario final para que los destinatarios sepan lo que ha sucedido con los mensajes que se les han enviado. Para obtener más información acerca de estas notificaciones, consulte [Notificaciones de correo no deseado para el usuario final en EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la página **Configuración contra el correo no deseado**, haga clic en el ![icono expandir](../../media/scc-expand-icon.png) para expandir una directiva contra correo no deseado:

   - La directiva predeterminada denominada **Directiva de filtro de correo no deseado predeterminada**.

   - Una directiva personalizada que creó, cuyo valor de la columna **Tipo** es **Directiva contra correo no deseado personalizada**.

3. En los detalles de la directiva expandida que aparecen, haga clic en **Configurar las notificaciones de correo no deseado para el usuario final**.

4. En el cuadro de diálogo **\<Policy Name\>** que se abre, configure las siguientes opciones:

   - **Habilitar las notificaciones de correo no deseado para el usuario final**: seleccione la casilla para habilitar las notificaciones. Desactive la casilla para deshabilitar las notificaciones.

   - **Enviar notificaciones de correo no deseado para el usuario final cada (días)**: seleccione la frecuencia con la que se envían las notificaciones. El valor predeterminado es 3 días. Puede escribir entre 1 y 15 días.

     Existen tres ciclos de notificaciones de correo no deseado del usuario final dentro de un período de 24 horas que comienzan en los siguientes horarios: 01:00 UTC, 08:00 UTC y 16:00 UTC.

     > [!NOTE]
     > Si alguna notificación se ausenta durante un ciclo anterior, el ciclo subsiguiente enviará la notificación. Esto puede hacer que parezca que hay varias notificaciones en un mismo día.

   - **Idioma de notificación**: haga clic en la lista desplegable y seleccione un idioma disponible de la lista. El valor por defecto es **Default** que corresponde al idioma inglés.

   Cuando haya terminado, haga clic en **Guardar**.

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a>Uso del Centro de seguridad y cumplimiento para quitar directivas contra correo no deseado

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la página **Configuración contra el correo no deseado**, haga clic en el ![icono expandir](../../media/scc-expand-icon.png) para expandir la directiva personalizada que quiera eliminar (la columna **Tipo** es la **Directiva contra el correo no deseado personalizada**).

3. En los detalles de la directiva expandida que aparecen, haga clic en **Eliminar directiva**.

4. Haga clic en **Sí** en el mensaje de advertencia que se muestra.

No puede quitar la directiva predeterminada.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a>Uso de Exchange Online PowerShell o EOP PowerShell para configurar directivas contra correo no deseado

Como se describió anteriormente, una directiva contra correo no deseado consiste en una directiva de filtro de correo no deseado y una regla de filtro de correo no deseado.

La diferencia entre las directivas de filtro de correo no deseado y las reglas de filtro de correo no deseado en Exchange Online PowerShell o en EOP PowerShell es importante. Para administrar las directivas de filtro de correo no deseado usará los cmdlets de **\*-HostedContentFilterPolicy** y para administrar las reglas de filtro de correo no deseado, los cmdlets de **\*-HostedContentFilterRule**.

- En PowerShell, la directiva de filtro de correo no deseado se crea en primer lugar y, después, se crea la regla de filtro de correo no deseado que identifica la directiva a la que se aplica la regla.
- En PowerShell, las opciones de configuración de la directiva de filtro de correo no deseado y la regla de filtro de correo no deseado se modifican por separado.
- Al quitar una directiva de filtro de correo no deseado de PowerShell, la regla de filtro de correo no deseado correspondiente no se quita automáticamente, y viceversa.

Las siguientes opciones de configuración de directivas contra correo no deseado solo están disponibles en PowerShell:

- El parámetro _MarkAsSpamBulkMail_ que es `On` de forma predeterminada. Los efectos de esta opción se explicaron anteriormente en este tema, en la sección [Uso del Centro de seguridad y cumplimiento para crear directivas contra correo no deseado](#use-the-security--compliance-center-to-create-anti-spam-policies).

- Las siguientes opciones de configuración del correo no deseado para el usuario final ponen las notificaciones en cuarentena:

  - El parámetro _DownloadLink_ que muestra u oculta el vínculo a la Herramienta de informes de correo no deseado para Outlook.

  - El parámetro _EndUserSpamNotificationCustomSubject_ que puede usar para personalizar la línea de asunto de la notificación.

### <a name="use-powershell-to-create-anti-spam-policies"></a>Uso de PowerShell para crear directivas contra correo no deseado

La creación de una directiva contra correo no deseado en PowerShell es un proceso de dos pasos:

1. Cree la directiva de filtro de correo no deseado.
2. Cree la regla de filtro de correo no deseado que especifica la directiva de filtro de correo no deseado a la que se aplica la regla.

 **Notas**:

- Puede crear una nueva regla de filtro de correo no deseado y asignar una directiva de filtro de correo no deseado existente sin asociar. Las reglas de filtro de correo no deseado no se pueden asociar con más de una directiva de filtro de correo no deseado.

- Puede configurar las siguientes opciones de nuevas directivas de filtro de correo no deseado en PowerShell, que no estarán disponibles en el Centro de seguridad y cumplimiento hasta que cree la directiva:

  - Crear la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-HostedContentFilterRule**).
  - Establecer la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_) en el cmdlet **New-HostedContentFilterRule**).

- No se puede ver ninguna directiva de filtro de correo no deseado nueva que cree en PowerShell en el Centro de seguridad y cumplimiento hasta que asigne la directiva a una regla de filtro de correo no deseado.

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>Paso 1: Uso de PowerShell para crear una directiva de filtro de correo no deseado

Para crear una directiva de filtro de correo no deseado, use esta sintaxis:

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

En este ejemplo se crea una directiva de filtro de correo no deseado llamada Contoso Executives con la siguiente configuración:

- Poner en cuarentena mensajes cuando el veredicto de filtrado de correo no deseado determine que es correo no deseado o correo no deseado de alta confianza.

- BCL 6 activa la acción para un veredicto de filtrado de correo no deseado en masa.

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> **New-HostedContentFilterPolicy** y **Set-HostedContentFilterPolicy** contienen un parámetro _ZapEnabled_ más antiguo, además de los parámetros _PhishZapEnabled_ y _SpamZapEnabled_ más recientes. El parámetro _ZapEnabled_ quedó obsoleto en febrero de 2020. Los parámetros _PhishZapEnabled_ y _SpamZapEnabled_ solían heredar sus valores del parámetro _ZapEnabled_. Pero si usa los parámetros _PhishZapEnabled_ y _SpamZapEnabled_ en un comando, o bien usa la configuración **Purga automática de correo no deseado** o **Purga automática de correo de suplantación de identidad** en la directiva de correo no deseado en el Centro de seguridad y cumplimiento, el valor del parámetro _ZapEnabled_ se ignora. Es decir, no use el parámetro _ZapEnabled_. En su lugar use los parámetros _PhishZapEnabled_ y _SpamZapEnabled_.

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a>Paso 2: Uso de PowerShell para crear una regla de filtro de correo no deseado

Para crear una regla de filtro de correo no deseado, use esta sintaxis:

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

En este ejemplo se crea una nueva regla de filtro de correo no deseado llamada Contoso Executives con esta configuración:

- La directiva de filtro de correo no deseado denominada Contoso Executives está asociada a la regla.

- La regla se aplica a los miembros del grupo denominado Contoso Executives Group.

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule).

### <a name="use-powershell-to-view-spam-filter-policies"></a>Uso de PowerShell para ver directivas de filtro de correo no deseado

Para obtener una lista de resumen de todas las directivas de filtro de correo no deseado, ejecute este comando:

```PowerShell
Get-HostedContentFilterPolicy
```

Para obtener información detallada sobre una directiva de filtro de correo no deseado determinada, use esta sintaxis:

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

Este ejemplo devuelve todos los valores de propiedad para la directiva de filtro de correo no deseado denominada Executives.

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).

### <a name="use-powershell-to-view-spam-filter-rules"></a>Uso de PowerShell para ver reglas de filtro de correo no deseado

Para ver reglas de filtro de correo no deseado existentes, use la siguiente sintaxis:

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

Para obtener una lista de resumen de todas las reglas de filtro de correo no deseado, ejecute este comando:

```PowerShell
Get-HostedContentFilterRule
```

Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

Para obtener información detallada sobre una regla de filtro de correo no deseado determinada, use esta sintaxis:

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

Este ejemplo devuelve todos los valores de propiedad para la regla de filtro de correo no deseado denominada Contoso Executives.

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule).

### <a name="use-powershell-to-modify-spam-filter-policies"></a>Uso de PowerShell para modificar directivas de filtro de correo no deseado

Además de los siguientes elementos, las mismas opciones están disponibles al modificar una directiva de filtro de correo no deseado en PowerShell como cuando rea la directiva, como se describe en la sección [Paso 1: Usar PowerShell para crear una directiva de filtro de correo no deseado](#step-1-use-powershell-to-create-a-spam-filter-policy) anteriormente en este tema.

- El conmutador _MakeDefault_ que convierte la directiva especificada en la predeterminada (se aplica a todos los usuarios, siempre tiene la prioridad **Mínima** y no se puede eliminar) solo está disponible cuando se modifica una directiva de filtro de correo no deseado en PowerShell.

- No puede cambiar el nombre de una directiva de filtro de correo no deseado (el cmdlet **Set-HostedContentFilterPolicy** no tiene parámetro _Name_). Cuando se cambia el nombre de una directiva contra correo no deseado en el Centro de seguridad y cumplimiento, solo cambia el nombre de la _regla_ de filtro de correo no deseado.

Para modificar una directiva de filtro de correo no deseado, use esta sintaxis:

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).

### <a name="use-powershell-to-modify-spam-filter-rules"></a>Uso de PowerShell para modificar reglas de filtro de correo no deseado

La única opción que no está disponible al modificar una regla de filtro de correo no deseado en PowerShell es el parámetro _Enabled_ que le permite crear una regla deshabilitada. Para habilitar o deshabilitar las reglas de filtro de correo no deseado existentes, vea la siguiente sección.

Por lo demás, no hay opciones de configuración adicionales disponibles al modificar una regla de filtro de correo no deseado en PowerShell. Están disponibles las mismas opciones de configuración cuando se crea una regla que las descritas en la sección [Paso 2: Usar PowerShell para crear una regla de filtro de correo no deseado](#step-2-use-powershell-to-create-a-spam-filter-rule) anteriormente en este tema.

Para modificar una regla de filtro de correo no deseado, use esta sintaxis:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

Este ejemplo cambia el nombre de la regla de filtro de correo no deseado existente llamada `{Fabrikam Spam Filter}` que podría causar problemas en el Centro de seguridad y cumplimiento.

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule).

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a>Uso de PowerShell para habilitar o deshabilitar las reglas de filtro de correo no deseado

Habilitar o deshabilitar una regla de filtro de correo no deseado en PowerShell habilita o deshabilita toda la directiva de correo no deseado (la regla de filtro de correo no deseado y la directiva de filtro de correo no deseado asignada). No puede habilitar o deshabilitar la directiva de correo no deseado predeterminada (siempre se aplica a todos los destinatarios).

Use esta sintaxis para habilitar o deshabilitar una regla de filtro de correo no deseado en PowerShell:

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

Este ejemplo deshabilita la regla de filtro de correo no deseado denominada Marketing Department.

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

Este ejemplo habilita la misma regla.

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule) y [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule).

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a>Uso de PowerShell para establecer la prioridad de las reglas de filtro de correo no deseado

El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo que se puede establecer depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.

Para establecer la prioridad de una regla de correo no deseado en PowerShell, use la siguiente sintaxis:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

**Notas**:

- Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-HostedContentFilterRule** en su lugar.

- La directiva de filtro de correo no deseado predeterminada no tiene una regla de filtro de correo no deseado correspondiente y siempre tiene el valor de prioridad no modificable **Mínima**.

### <a name="use-powershell-to-remove-spam-filter-policies"></a>Uso de PowerShell para quitar directivas de filtro de correo no deseado

Cuando use PowerShell para quitar una directiva de filtro de correo no deseado, la regla de filtro de correo no deseado correspondiente no se elimina.

Para quitar una directiva de filtro de correo no deseado en PowerShell, use esta sintaxis:

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

Este ejemplo quita la directiva de filtro de correo no deseado denominada Marketing Department.

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy).

### <a name="use-powershell-to-remove-spam-filter-rules"></a>Uso de PowerShell para quitar reglas de filtro de correo no deseado

Cuando use PowerShell para quitar una regla de filtro de correo no deseado, la directiva de filtro de correo no deseado correspondiente no se elimina.

Para quitar una regla de filtro de correo no deseado en PowerShell, use esta sintaxis:

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

Este ejemplo quita la regla de filtro de correo no deseado denominada Marketing Department.

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>Envíe un mensaje GTUBE para comprobar la configuración de la directiva de correo no deseado

> [!NOTE]
> Estos pasos solo funcionarán si la organización de correo electrónico desde la que está enviando el mensaje GTUBE no detecta correo no deseado saliente. Si lo hace, no se puede enviar el mensaje de prueba.

Prueba genérica de correo electrónico en masa no solicitado (GTUBE) es una cadena de texto que se incluye en un mensaje de prueba para comprobar la configuración del correo no deseado de la organización. Un mensaje GTUBE es similar al archivo de texto del European Institute of Computer virus Research (EICAR) para probar la configuración de malware.

Incluya el siguiente texto GTUBE en un mensaje de correo electrónico en una única línea, sin espacios ni saltos de línea:

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a>Lista de bloqueados y lista de permitidos

En algunas ocasiones, nuestros filtros pueden cometer un error o los sistemas pueden necesitar tiempo para ponerse al día. En estos casos, la directiva contra correo no deseado le permite crear listas de permitidos y bloqueados para invalidar la clasificación realizada por el filtro. Esta opción se debe usar con moderación, ya que las listas pueden alcanzar tamaños excesivos, y de forma provisional, ya que nuestro sistema de filtrado debería funcionar correctamente.

> [!TIP]
> Puede ocurrir que la organización no esté de acuerdo con la clasificación hecha por el servicio. En este caso, usted puede plantearse mantener la lista de permitidos o bloqueados de forma permanente. Sin embargo, si va a colocar un dominio en la lista de permitidos durante largos períodos de tiempo, debe solicitar al remitente que se asegure de que su dominio está autenticado y, si no lo está, establecer DMARC para rechazarlo.
