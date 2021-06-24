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
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender cómo ver, crear, modificar y eliminar directivas contra correo electrónico no deseado en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: afcb82789168999f5f061ca0f86ad3c07b54846d
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108240"
---
# <a name="configure-anti-spam-policies-in-eop"></a>Configuración de directivas contra correo no deseado en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En organizaciones de Microsoft 365 con buzones de correo de Exchange Online u organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP protege automáticamente los mensajes de correo electrónico entrantes contra el correo no deseado. EOP usa directivas de bloqueo de correo no deseado (también conocidas como directivas de filtro de correo no deseado o directivas de filtro de contenido) como parte de la defensa general de la organización contra el correo no deseado. Para obtener más información, consulte [Protección contra correo no deseado](anti-spam-protection.md).

Los administradores pueden ver, editar y configurar (pero no eliminar) la directiva contra correo no deseado predeterminada. Para disfrutar de una mayor granularidad, también puede crear directivas personalizadas de filtro de correo no deseado que se aplican a usuarios, grupos o dominios específicos de la organización. Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.

Puede configurar directivas contra correo no deseado en el portal de Microsoft 365 Defender o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; EOP PowerShell independiente para organizaciones sin buzones de Exchange Online).

Los elementos básicos de una directiva contra correo no deseado son:

- **La directiva de filtro de correo no deseado**: especifica las acciones para los veredictos de filtro de correo no deseado y las opciones de notificación.
- **La regla de filtro de correo no deseado**: especifica la prioridad y los filtros de destinatarios (a los que se aplica la directiva) de una directiva de filtro de correo no deseado.

La diferencia entre estos dos elementos no es obvia cuando administra directivas contra correo no deseado en el portal de Microsoft 365 Defender:

- Cuando crea una directiva contra correo no deseado, en realidad, está creando una regla de filtro de correo no deseado y, al mismo tiempo, la directiva de filtro de correo no deseado asociada a esta, con el mismo nombre para ambas.
- Al modificar una directiva contra correo no deseado, las opciones de configuración relacionadas con el nombre, la prioridad, el activado o desactivado y los filtros de destinatarios modifican la regla de filtro de correo no deseado. Todas las demás opciones modifican la directiva de filtro de correo no deseado asociada.
- Cuando se quita una directiva contra correo no deseado, se elimina la regla de filtro de correo no deseado y la directiva de filtro de correo no deseado asociada.

En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado. Para más información, consulte la sección [Uso de Exchange Online PowerShell o EOP PowerShell independiente para configurar directivas contra correo no deseado](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies), que se muestra más adelante en este mismo artículo.

Cada organización tiene una directiva contra correo no deseado integrada que se denomina Predeterminada, que tiene estas propiedades:

- La directiva se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla de filtro de correo no deseado (filtros de destinatarios) asociada a la directiva.
- La directiva tiene un valor de prioridad personalizado **Mínimo** que no se puede modificar (la directiva siempre se aplica en último lugar). Las directivas personalizadas que cree siempre tendrán una prioridad mayor.
- La directiva es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar esta directiva predeterminada.

Para aumentar la eficacia del filtrado de correo no deseado, puede crear directivas de bloqueo de correo no deseado personalizadas con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Directivas contra correo no deseado**, use <https://security.microsoft.com/antispam>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para agregar, modificar y eliminar directivas contra correo no deseado, debe ser miembro de los grupos de roles **Administración de la organización** o **Administrador de seguridad**.
  - Para obtener acceso de solo lectura a las directivas contra correo no deseado, tiene que ser miembro del grupo de roles **Lector de seguridad**.

  Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para saber la configuración recomendada para las directivas contra correo electrónico no deseado, consulte [Configuración de la directiva de correo no deseado de EOP](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-spam-policies"></a>Usar el portal de Microsoft 365 Defender para crear directivas contra correo no deseado

La creación de una directiva contra correo no deseado en el portal de Microsoft 365 Defender crea una regla de filtro de correo no deseado y la directiva de filtro de correo no deseado asociada al mismo tiempo con el mismo nombre para ambas.

1. En el portal de Microsoft 365 Defender, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **Directivas de amenazas** \> **Sección de directivas** \> **Anti-spam**.

2. En la página de directivas **antispam**, haga clic en el![icono para crea](../../media/m365-cc-sc-create-icon.png) **Crear directiva**, y luego, seleccione **Entrada** en la lista desplegable.

3. Se abrirá el asistente para directivas. En la **página Asigne un nombre a la directiva**, configure estas opciones:
   - **Nombre**: escriba un nombre único y descriptivo para la directiva.
   - **Descripción**: escriba una descripción opcional para la directiva.

   Cuando termine, haga clic en **Siguiente**.

4. En la página **Usuarios, grupos y dominios** que aparece, identifique los destinatarios internos a los que se aplica la directiva (condiciones de destinatario):
   - **Usuarios**: los buzones, usuarios de correo o contactos de correo especificados de su organización.
   - **Grupos**: los grupos de distribución, los grupos de seguridad habilitados para correo electrónico o los Grupos de Microsoft 365 especificados de la organización.
   - **Dominios**: todos los destinatarios de los [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados en la organización.

   Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados. Repita este proceso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono de quitar](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

   Para los usuarios o grupos, puede usar la mayoría de los identificadores (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de cuenta, etc.), pero el nombre para mostrar correspondiente se muestra en los resultados. Para los usuarios, escriba un asterisco (\*) para ver todos los valores disponibles.

   Varios valores en la misma condición usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Hay diferentes condiciones que usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

   - **Excluir estos usuarios, grupos y dominios**: para agregar excepciones a los destinatarios internos a los que se aplica la directiva (excepciones de destinatarios), seleccione esta opción y configure las excepciones. La configuración y el comportamiento se muestran exactamente igual que las condiciones.

   Cuando termine, haga clic en **Siguiente**.

5. En la página **Umbral de correo electrónico en masa y propiedades de correo no deseado** que aparece, configure las opciones siguientes:

   - **Umbral de correo electrónico en masa**: especifica el nivel de quejas masivas (BCL) de un mensaje que desencadena la acción especificada para el veredicto de filtrado de correo no deseado **en masa** que configurará en la siguiente página (mayor que el valor especificado, no superior al mismo o igual al mismo). Un valor superior indica que el mensaje es menos deseado (tiene más posibilidades de parecer correo no deseado). El valor predeterminado es 7. Para más información, consulte [Valores de nivel de quejas masivas (BCL) en EOP](bulk-complaint-level-values.md) y [¿Cuál es la diferencia entre el correo electrónico no deseado y el correo electrónico en masa?](what-s-the-difference-between-junk-email-and-bulk-email.md).

     De forma predeterminada, la configuración solo para PowerShell _MarkAsSpamBulkMail_ está `On` en directivas contra correo no deseado. Esta configuración afecta enormemente a los resultados de un veredicto de filtrado **en masa**:

     - **_MarkAsSpamBulkMail_ está Activado**: una BCL que es superior al umbral se convierte en un SCL 6 que corresponde a un veredicto de filtrado de **Correo no deseado**, y la acción del veredicto de filtrado **en masa** se lleva a cabo en el mensaje.
     - **_MarkAsSpamBulkMail_ está desactivada**: el mensaje está marcado con los BCL, pero no se realiza _ninguna acción_ para un veredicto de filtrado **en masa**. De hecho, el umbral de BCL y el veredicto de filtrado **en masa** no son relevantes.

   - **Aumentar la puntuación del correo no deseado**, **Marcar como correo no deseado**<sup>\*</sup> y **Modo de prueba**: contiene la configuración del Filtro avanzado de correo no deseado (ASF) desactivada de forma predeterminada. Las opciones ASF pronto estarán en desuso y su funcionalidad se incorporará a otras partes de la pila de filtrado. Se recomienda desactivar todas las opciones de ASF en las directivas contra el correo no deseado.

     Para más información sobre estas opciones, consulte [Opciones avanzadas de filtro de correo no deseado en EOP](advanced-spam-filtering-asf-options.md).

      <sup>\*</sup> **Contiene idiomas específicos** y **de estos países** no forman parte de la configuración de ASF.

   - **Contiene idiomas específicos**: Haga clic en la casilla y seleccione **Activado** o **Desactivado** en la lista desplegable. Si la activa, aparecerá un cuadro. Empiece a escribir el nombre de un idioma en el cuadro. Aparecerá una lista filtrada de idiomas admitidos. Cuando encuentre el idioma que está buscando, selecciónelo. Repita este paso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar en ![Quitar icono](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

   - **De estos países** _: Haga clic en la casilla y seleccione_ *Activar** o **Desactivar** en la lista desplegable. Si la activa, aparecerá un cuadro. Empiece a escribir el nombre de un país en el cuadro. Se mostrará una lista filtrada de países admitidos. Cuando encuentre el país que está buscando, selecciónelo. Repita este paso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar en ![Quitar icono](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

   Cuando termine, haga clic en **Siguiente**.

6. En la página **Acciones** que aparece, configure las opciones siguientes:

   - **Acciones de mensaje**: seleccione o revise la acción que se debe realizar en los mensajes en función de los siguientes veredictos de filtrado de correo no deseado:
     - **Correo no deseado**
     - **Correo no deseado de alta confianza**
     - **Suplantación de identidad (phishing)**
     - **Suplantación de identidad de alta confianza**
     - **Masivo**

     En la siguiente tabla se describen las acciones disponibles en los veredictos de filtrado de correo no deseado.

     - Una marca de verificación ( ![Marca de verificación](../../media/checkmark.png)) indica que la acción está disponible (no todas las acciones están disponibles para todos los veredictos).
     - Un asterisco (<sup>\*</sup>) después de la marca de verificación indica la acción predeterminada para el veredicto de filtrado de correo no deseado.

     <br>

     ****

     |Acción|Correo no deseado|Alto<br>confianza<br>correo no deseado|Suplantación de identidad (phishing)|Alto<br>confianza<br>suplantación de identidad (phishing)|Masivo|
     |---|:---:|:---:|:---:|:---:|:---:|
     |**Mover el mensaje a la carpeta Correo no deseado**: el mensaje se entrega al buzón y se mueve a la carpeta Correo no deseado.<sup>1</sup>|![Marca de verificación](../../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)<sup>\*</sup>|
     |**Agregar encabezado X**: agrega un encabezado X al encabezado del mensaje y entrega el mensaje al buzón. <p> Especifique el nombre de campo del encabezado X (no el valor) más adelante en el cuadro **Agregar este texto de encabezado X**. <p> Para los veredictos **Correo no deseado** y **Correo no deseado de alta confianza**, el mensaje se mueve a la carpeta Correo no deseado.<sup>1,2</sup>|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)||![Marca de verificación](../../media/checkmark.png)<sup>\*</sup>|
     |**Anteponer la línea de asunto al texto**: agrega texto al principio de la línea de asunto del mensaje. El mensaje se entrega al buzón y se mueve a la carpeta Correo no deseado.<sup>1,2</sup> <p> Especifique el texto más adelante en el cuadro **Prefijo de línea de asunto con este texto**.|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)||![Marca de verificación](../../media/checkmark.png)|
     |**Redirigir el mensaje a la dirección de correo electrónico**: envía el mensaje a otros destinatarios en vez de a los especificados. <p> Especifique los destinatarios más tarde en el cuadro **Redirigir a esta dirección de correo electrónico**.|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
     |**Eliminar mensaje**: elimina el mensaje completo, incluidos todos los datos adjuntos.|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)||![Marca de verificación](../../media/checkmark.png)|
     |**Colocar el mensaje en cuarentena**: envía el mensaje a la cuarentena en lugar de a los destinatarios. <p> Especifique cuánto tiempo se debe conservar el mensaje en cuarentena más adelante en el cuadro **Cuarentena**.|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)<sup>\*</sup>|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
     |**Ninguna acción**|||||![Marca de verificación](../../media/checkmark.png)|
     |

     > <sup>1</sup> En Exchange Online, el mensaje se mueve a la carpeta Correo no deseado si está habilitada la regla de correo no deseado en el buzón (está activada de forma predeterminada). Para más información, consulte [Configuración de las opciones del correo no deseado en buzones de Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).
     >
     > En entornos híbridos en los que EOP protege los buzones de Exchange locales, tiene que configurar las reglas de flujo de correo (también conocidas como reglas de transporte) en Exchange local para traducir el veredicto de filtro de correo no deseado de EOP para que la regla de correo no deseado pueda mover el mensaje a la carpeta de correo electrónico no deseado. Para obtener información, consulte [Configuración de un EOP para entregar el correo no deseado en la carpeta de correo no deseado en entornos híbridos](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).
     >
     > <sup>2</sup> Puede usar este valor como condición en las reglas de flujo de correo (también conocidas como reglas de transporte) para filtrar o redirigir el mensaje.

   - **Mantener correo no deseado en cuarentena durante este número de días**: especifica cuánto tiempo debe mantenerse el mensaje en cuarentena si ha seleccionado **Mensaje en cuarentena** como la acción para un veredicto de filtrado de correo no deseado. Cuando expire el período de tiempo, el mensaje se eliminará. El valor predeterminado es 30 días. Los valores válidos están comprendidos entre 1 y 30 días. Para obtener más información acerca de la cuarentena, consulte los siguientes temas:

     - [Mensajes en cuarentena en EOP](quarantine-email-messages.md)
     - [Administración de mensajes en cuarentena y archivos como administrador en EOP](manage-quarantined-messages-and-files.md)
     - [Búsqueda y liberación de mensajes en cuarentena como usuario en EOP](find-and-release-quarantined-messages-as-a-user.md)

   - **Agregar este texto de encabezado X**: este cuadro es obligatorio y solo está disponible si se ha seleccionado **Agregar encabezado X** como acción para un veredicto de filtrado de correo no deseado. El valor que especifique es el *nombre* del campo de encabezado que se agrega al encabezado del mensaje. El *valor* del campo de encabezado siempre es `This message appears to be spam`.

     La longitud máxima es de 255 caracteres y el valor no puede contener espacios o dos puntos (:).

     Por ejemplo, si escribe el valor `X-This-is-my-custom-header`, el encabezado X que se agrega al mensaje es `X-This-is-my-custom-header: This message appears to be spam.`

     Si escribe un valor que contiene espacios o dos puntos (:), el valor que escriba se ignora y se agrega el encabezado X predeterminado al mensaje (`X-This-Is-Spam: This message appears to be spam.`).

   - **Anteponer la línea de asunto con este texto**: este cuadro es obligatorio y solo está disponible si se ha seleccionado **Anteponer la línea de asunto con este texto** como acción para un veredicto de filtrado de correo no deseado. Escriba el texto que se agregará al principio de la línea de asunto del mensaje.

   - **Redirigir a esta dirección de correo electrónico**: este cuadro es obligatorio y solo está disponible si ha seleccionado la **Redirigir el mensaje a dirección de correo electrónico** como la acción para un veredicto de filtrado de correo no deseado. Escriba la dirección de correo electrónico a la que quiere enviar el mensaje. Puede especificar varios valores separados por punto y coma (;).

   - **Habilitar las Sugerencias de seguridad**: de forma predeterminada, las Sugerencias de seguridad están habilitadas, pero puede deshabilitarlas si desactiva la casilla de verificación. Para obtener más información sobre las Sugerencias de seguridad, consulte [Sugerencias de seguridad en mensajes de correo electrónico](safety-tips-in-office-365.md).

   - **Habilitar la Purga automática (ZAP)**: la Purga automática detecta y realiza acciones en mensajes que ya se han entregado a buzones de Exchange Online. Para más información sobre ZAP, consulte [Purga automática: protección contra correo no deseado y malware](zero-hour-auto-purge.md).

     ZAP está activada de manera predeterminada. Cuando ZAP está activada, están disponibles las opciones de configuración siguientes:

     - **Habilitar ZAP para los mensajes de suplantación de identidad**: de manera predeterminada, ZAP está habilitada para la detección de la suplantación de identidad, pero puede deshabilitarla si desactiva la casilla.
     - **Habilitar ZAP para los mensajes de correo no deseado**: de forma predeterminada, ZAP está habilitada para la detección de correo no deseado, pero puede deshabilitarla si desactiva la casilla.

   - **Habilitar notificaciones de correo no deseado para el usuario final**: Para más información, vea la sección [Configurar las notificaciones de correo no deseado para el usuario final](#configure-end-user-spam-notifications) más adelante en este tema.

   Cuando termine, haga clic en **Siguiente**.

7. En el control flotante **Lista de permitidos y bloqueados** que aparece, puede configurar los remitentes de mensajes por dirección de correo electrónico o por dominio de correo electrónico que pueden omitir el filtrado de correo no deseado.

   En la sección **Permitidos**, puede configurar los remitentes permitidos y los dominios permitidos. En la sección **Bloqueados**, puede agregar remitentes bloqueados y dominios bloqueados.

   > [!IMPORTANT]
   >
   > Piense detenidamente antes de agregar dominios a la lista de dominios permitidos. Para más información, consulte [Crear listas de remitentes seguros en EOP](create-safe-sender-lists-in-office-365.md)
   >
   > Nunca agregue sus propios [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) o dominios comunes (por ejemplo, microsoft.com o office.com) a la lista de dominios permitidos. Si estos dominios pueden omitir el filtrado de correo no deseado, los atacantes podrán enviar correo electrónico a su organización con facilidad.
   >
   > Agregar dominios a la lista de dominios bloqueados para bloquear manualmente los dominios no es peligroso, pero puede aumentar su carga de trabajo administrativa. Para más información, consulte [Crear listas de remitentes bloqueados en EOP](create-block-sender-lists-in-office-365.md).
   >
   > Habrá ocasiones en las que un mensaje evada nuestros filtros, no esté de acuerdo con el veredicto de filtrado o nuestros sistemas tarden un poco en ponerse al día. En estos casos, la lista de permitidos y la lista de bloqueados están disponibles para anular los veredictos de filtrado actuales. Sin embargo, debe usar estas listas con moderación y de manera temporal: las listas largas pueden dejar de ser manejables y nuestra pila de filtrado debería funcionar como se espera. Si va a mantener un dominio permitido durante un largo período de tiempo, debe decirle al remitente que compruebe que su dominio esté autenticado y establecido en rechazar DMARC.

   Los pasos para agregar entradas a cualquiera de las listas son los mismos:

   1. Haga clic en el vínculo de la lista que quiera configurar:
      - **Remitentes** \> **permitidos**: haga clic en **Administrar (nn) remitentes**.
      - **Dominios** \> **permitidos**: haga clic en **Permitir dominios**.
      - **Remitentes** \> **bloqueados**: haga clic en **Administrar (nn) remitentes (nn)**.
      - **Dominios** \> **bloqueados**: haga clic en **Bloquear dominios**.

   2. En el control flotante que aparece, siga los pasos siguientes:
      1. Haga clic en ![Crear icono](../../media/m365-cc-sc-create-icon.png) **Agregar remitentes** o **Agregar dominios**.
      2. En el control flotante **Agregar remitentes** o **Agregar dominios** que aparece, escriba la dirección de correo electrónico del remitente en el cuadro **Remitente** o el dominio en el cuadro **Dominio**. Mientras escribe, el valor aparece debajo del cuadro. Cuando haya terminado de escribir la dirección de correo electrónico o el dominio, seleccione el valor debajo del cuadro.
      3. Repita el paso anterior tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono de quitar](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

      Cuando haya terminado, haga clic en **Agregar remitentes** o **Agregar dominios**.

      De nuevo en el control flotante principal, los remitentes o dominios que agregó aparecerán en la página. Para quitar una entrada de esta página, siga los pasos siguientes:

      1. Seleccione una o más entradas de la lista. También puede usar el cuadro **Búsqueda** para buscar valores en la lista.
      2. Después de seleccionar al menos una entrada, el icono Eliminar ![Icono Eliminar](../../media/m365-cc-sc-delete-icon.png) aparece.
      3. Haga clic en el icono Eliminar ![Icono Eliminar](../../media/m365-cc-sc-delete-icon.png) para quitar las entradas seleccionadas.

      Cuando haya terminado, haga clic en **Listo**.

      De nuevo en la página **Lista de permitidos y bloqueados**, haga clic en **Siguiente** cuando esté listo para continuar.

8. En la página **Revisar** que aparece, revise la configuración. Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Crear**.

9. En la página de confirmación que aparece, haga clic en **Listo**.

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-spam-policies"></a>Usar el portal de Microsoft 365 Defender para ver directivas contra correo no deseado

1. En el portal de Microsoft 365 Defender, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **Directivas de amenazas** \> **Sección de directivas** \> **Anti-spam**.

2. En la página de directivas **antispam**, busque uno de los siguientes valores:
   - El valor **Tipo** es **Directiva contra el correo no deseado personalizada**
   - El valor **Nombre** es **Directiva de entrada contra el correo no deseado (predeterminado)**

   Las siguientes propiedades se muestran en la lista de directivas contra el correo no deseado:

   - **Nombre**
   - **Estado**
   - **Prioridad**
   - **Tipo**

3. Cuando selecciona una directiva contra correo no deseado al hacer clic en el nombre, la configuración de la directiva se muestra en un control flotante.

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-spam-policies"></a>Usar el portal de Microsoft 365 Defender para modificar directivas contra correo no deseado

1. En el portal de Microsoft 365 Defender, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **Directivas de amenazas** \> **Sección de directivas** \> **Anti-spam**.

2. En la página **Directivas contra el correo no deseado**, seleccione una directiva contra el correo no deseado en la lista. Para ello, haga clic en el nombre:
   - Una directiva personalizada que creó, cuyo valor de la columna **Tipo** es **Directiva contra correo no deseado personalizada**.
   - La directiva predeterminada denominada **Directiva de entrada contra correo no deseado (predeterminado)**.

3. En el control flotante de detalles de la directiva que aparece, seleccione **Editar** en cada sección para modificar la configuración dentro de la sección. Para más información sobre la configuración, vea la sección [Usar el portal de Microsoft 365 Defender para crear directivas contra el correo no deseado](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) en este artículo.

   Para la directiva contra correo no deseado predeterminada, la sección **Se aplica a** no está disponible (la directiva se aplica a todos los usuarios) y no se puede cambiar el nombre de la directiva.

Vea las secciones siguientes para habilitar o deshabilitar una directiva, establecer el orden de prioridad de la directiva o configurar las notificaciones en cuarentena para el usuario final.

### <a name="enable-or-disable-anti-spam-policies"></a>Habilitar o deshabilitar las directivas contra correo no deseado

No se puede deshabilitar la directiva contra correo no deseado predeterminada.

1. En el portal de Microsoft 365 Defender, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **Directivas de amenazas** \> **Sección de directivas** \> **Anti-spam**.

2. En la página **Directivas contra correo no deseado**, seleccione una directiva con el **Valor de tipo** de **Directiva personalizada contra el correo no deseado** de la lista. Para ello, haga clic en el nombre.

3. En la parte superior del control flotante de detalles de la directiva que aparece, verá uno de los siguientes valores:
   - **Directiva desactivada**: para activar la directiva, haga clic en el ![Icono Activar](../../media/m365-cc-sc-turn-on-off-icon.png) **Activar**.
   - **Directiva activada**: Para desactivar la directiva, haga clic en el ![Icono desactivar](../../media/m365-cc-sc-turn-on-off-icon.png) y **Desactivar**.

4. En el cuadro de diálogo de confirmación que aparece, haga clic **Activar** o **Desactivar**.

5. Haga clic en **Cerrar** en el control flotante de detalles de la directiva.

De nuevo en la página principal de la directiva, el valor **Estado** de la directiva estará **Activado** o **Desactivado**.

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>Establecer la prioridad de las directivas contra correo no deseado personalizadas

De manera predeterminada, a las directivas contra correo no deseado se les asigna una prioridad en función del orden en que se crearon (las directivas más recientes tienen una prioridad menor que las directivas anteriores). Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor). Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

Para cambiar la prioridad de una directiva, haga clic en **Aumentar la prioridad** o en **Reducir la prioridad** en las propiedades de la directiva (no se puede modificar directamente el número de **Prioridad** en el portal de Microsoft 365 Defender). Cambiar la prioridad de una directiva solo tiene sentido si tiene varias directivas.

 **Notas**:

- En el portal de Microsoft 365 Defender, solo puede cambiar la prioridad de la directiva contra el correo no deseado después de crearla. En PowerShell, puede invalidar la prioridad predeterminada al crear la regla de filtrado de correo no deseado (lo cual puede afectar a la prioridad de las reglas existentes).
- Las directivas contra correo no deseado se procesan en el orden en el que se muestran (la primera directiva tiene el valor de **Prioridad** 0). La directiva predeterminada contra correo no deseado tiene el valor de prioridad **Más bajo** y no puede cambiarlo.

1. En el portal de Microsoft 365 Defender, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **Directivas de amenazas** \> **Sección de directivas** \> **Anti-spam**.

2. En la página **Directivas contra correo no deseado**, seleccione una directiva con el **Valor de tipo** de **Directiva personalizada contra el correo no deseado** de la lista. Para ello, haga clic en el nombre.

3. En la parte superior del control flotante de detalles de la directiva que aparece, verá **Aumentar la prioridad** o **Disminuir la prioridad** en función del valor de prioridad actual y del número de directivas personalizadas:
   - La directiva contra el correo no deseado con el valor de **Prioridad** **0** solo tiene disponible la opción **Reducir la prioridad**.
   - La directiva contra correo no deseado con el valor de **Prioridad** inferior (por ejemplo, **3**) solo tiene disponible la opción **Aumentar la prioridad**.
   - Si tiene tres o más directivas contra correo no deseado, las directivas entre los valores de prioridad más alto y más bajo tienen disponibles tanto las opciones de **Aumentar la prioridad** como de **Disminuir la prioridad**.

   Haga clic en el ![Icono Aumentar la prioridad](../../media/m365-cc-sc-increase-icon.png) **Aumentar la prioridad** o en el ![Icono Disminuir la prioridad](../../media/m365-cc-sc-decrease-icon.png) **Reducir la prioridad** para cambiar el valor de **Prioridad**.

4. Cuando haya terminado, haga clic en **Cerrar** en el control flotante de detalles de la directiva.

### <a name="configure-end-user-spam-notifications"></a>Configurar notificaciones de correo no deseado para el usuario final

Cuando un veredicto de filtrado de correo no deseado pone en cuarentena un mensaje, puede configurar las notificaciones de correo no deseado para el usuario final para que los destinatarios sepan lo que ha sucedido con los mensajes que se les han enviado. Para obtener más información acerca de estas notificaciones, consulte [Notificaciones de correo no deseado para el usuario final en EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).

1. En el portal de Microsoft 365 Defender, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **Directivas de amenazas** \> **Sección de directivas** \> **Anti-spam**.

2. En la página **Directivas contra el correo no deseado**, seleccione una directiva contra el correo no deseado en la lista. Para ello, haga clic en el nombre:
   - Una directiva personalizada que creó, cuyo valor de la columna **Tipo** es **Directiva contra correo no deseado personalizada**.
   - La directiva predeterminada denominada **Directiva de entrada contra correo no deseado (predeterminado)**.

3. En el control flotante de detalles de la directiva que aparece, haga clic en **Editar** en la sección **Acciones**. En el control flotante de **Acciones** que aparece, configure las opciones siguientes:

   - **Habilitar las notificaciones de correo no deseado para el usuario final**: seleccione la casilla para habilitar las notificaciones o desactive la casilla para deshabilitar las notificaciones. Al seleccionar la casilla, se mostrarán las siguientes opciones de configuración adicionales:

     - **Enviar notificaciones de correo no deseado para el usuario final cada (días)**: seleccione la frecuencia con la que se envían las notificaciones. El valor predeterminado es 3 días. Puede escribir entre 1 y 15 días.

       Existen tres ciclos de notificaciones de correo no deseado del usuario final dentro de un período de 24 horas que comienzan en los siguientes horarios: 01:00 UTC, 08:00 UTC y 16:00 UTC.

       > [!NOTE]
       > Si alguna notificación se ausenta durante un ciclo anterior, el ciclo subsiguiente enviará la notificación. Esto puede hacer que parezca que hay varias notificaciones en un mismo día.

     - **Idioma**: haga clic en la lista desplegable y seleccione un idioma disponible de la lista. El valor por defecto es **Default** que corresponde al idioma inglés.

   Cuando haya terminado, haga clic en **Guardar**.

4. De nuevo en el control flotante de detalles de la directiva, haga clic en **Cerrar**.

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-spam-policies"></a>Usar el portal de Microsoft 365 Defender para quitar directivas contra correo no deseado personalizadas

Cuando se utiliza el portal de Microsoft 365 Defender para eliminar una directiva antispam personalizada, se eliminan tanto la regla del filtro antispam como la directiva del filtro antispam correspondiente. No se puede eliminar la directiva antispam predeterminada.

1. En el portal de Microsoft 365 Defender, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **Directivas de amenazas** \> **Sección de directivas** \> **Anti-spam**.

2. En la página **Directivas contra correo no deseado**, seleccione una directiva con el **Valor de tipo** de **Directiva personalizada contra el correo no deseado** de la lista. Para ello, haga clic en el nombre. En la parte superior del control flotante de detalles de la directiva que aparece, haga clic en el ![Icono Más acciones](../../media/m365-cc-sc-more-actions-icon.png) **Más acciones** \> ![Icono Eliminar directiva](../../media/m365-cc-sc-delete-icon.png) **Eliminar directiva**.

3. En el cuadro de diálogo de confirmación que aparece, haga clic en **Sí**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a>Uso de Exchange Online PowerShell o EOP PowerShell para configurar directivas contra correo no deseado

Como se describió anteriormente, una directiva contra correo no deseado consiste en una directiva de filtro de correo no deseado y una regla de filtro de correo no deseado.

La diferencia entre las directivas de filtro de correo no deseado y las reglas de filtro de correo no deseado en Exchange Online PowerShell o en EOP PowerShell es importante. Para administrar las directivas de filtro de correo no deseado usará los cmdlets de **\*-HostedContentFilterPolicy** y para administrar las reglas de filtro de correo no deseado, los cmdlets de **\*-HostedContentFilterRule**.

- En PowerShell, la directiva de filtro de correo no deseado se crea en primer lugar y, después, se crea la regla de filtro de correo no deseado que identifica la directiva a la que se aplica la regla.
- En PowerShell, las opciones de configuración de la directiva de filtro de correo no deseado y la regla de filtro de correo no deseado se modifican por separado.
- Al quitar una directiva de filtro de correo no deseado de PowerShell, la regla de filtro de correo no deseado correspondiente no se quita automáticamente, y viceversa.

Las siguientes opciones de configuración de directivas contra correo no deseado solo están disponibles en PowerShell:

- El parámetro _MarkAsSpamBulkMail_ que es `On` de forma predeterminada. Los efectos de esta opción se explicaron anteriormente en este artículo, en la sección [Uso del portal de Microsoft 365 Defender para crear directivas contra correo no deseado](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies).

- Las siguientes opciones de configuración del correo no deseado para el usuario final ponen las notificaciones en cuarentena:
  - El parámetro _DownloadLink_ que muestra u oculta el vínculo a la Herramienta de informes de correo no deseado para Outlook.
  - El parámetro _EndUserSpamNotificationCustomSubject_ que puede usar para personalizar la línea de asunto de la notificación.

### <a name="use-powershell-to-create-anti-spam-policies"></a>Uso de PowerShell para crear directivas contra correo no deseado

La creación de una directiva contra correo no deseado en PowerShell es un proceso de dos pasos:

1. Cree la directiva de filtro de correo no deseado.
2. Cree la regla de filtro de correo no deseado que especifica la directiva de filtro de correo no deseado a la que se aplica la regla.

 **Notas**:

- Puede crear una nueva regla de filtro de correo no deseado y asignar una directiva de filtro de correo no deseado existente sin asociar. Las reglas de filtro de correo no deseado no se pueden asociar con más de una directiva de filtro de correo no deseado.
- Puede configurar las siguientes opciones de nuevas directivas de filtro de correo no deseado en PowerShell, que no estarán disponibles en el portal de Microsoft 365 Defender hasta que cree la directiva:
  - Crear la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-HostedContentFilterRule**).
  - Establecer la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_) en el cmdlet **New-HostedContentFilterRule**).

- No se puede ver ninguna directiva de filtro de correo no deseado nueva que cree en PowerShell en el portal de Microsoft 365 Defender hasta que asigne la directiva a una regla de filtro de correo no deseado.

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>Paso 1: Uso de PowerShell para crear una directiva de filtro de correo no deseado

Para crear una directiva de filtro de correo no deseado, use esta sintaxis:

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

En este ejemplo se crea una directiva de filtro de correo no deseado llamada Contoso Executives con la siguiente configuración:

- Poner en cuarentena mensajes cuando el veredicto de filtrado de correo no deseado determine que es correo no deseado o correo no deseado de alta confianza.
- BCL 7, 8 o 9 activa la acción para un veredicto de filtrado de correo no deseado en masa.

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).

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

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule).

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

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).

### <a name="use-powershell-to-view-spam-filter-rules"></a>Uso de PowerShell para ver reglas de filtro de correo no deseado

Para ver reglas de filtro de correo no deseado existentes, use la siguiente sintaxis:

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

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule).

### <a name="use-powershell-to-modify-spam-filter-policies"></a>Uso de PowerShell para modificar directivas de filtro de correo no deseado

Además de los siguientes elementos, las mismas opciones están disponibles al modificar una directiva de filtro de correo no deseado en PowerShell como cuando crea la directiva, como se describe en la sección [Paso 1: Usar PowerShell para crear una directiva de filtro de correo no deseado](#step-1-use-powershell-to-create-a-spam-filter-policy) anteriormente en este artículo.

- El conmutador _MakeDefault_ que convierte la directiva especificada en la predeterminada (se aplica a todos los usuarios, siempre tiene la prioridad **Mínima** y no se puede eliminar) solo está disponible cuando se modifica una directiva de filtro de correo no deseado en PowerShell.
- No puede cambiar el nombre de una directiva de filtro de correo no deseado (el cmdlet **Set-HostedContentFilterPolicy** no tiene parámetro _Name_). Cuando se cambia el nombre de una directiva contra correo no deseado en el portal de Microsoft 365 Defender, solo cambia el nombre de la _regla_ de filtro de correo no deseado.

Para modificar una directiva de filtro de correo no deseado, use esta sintaxis:

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).

### <a name="use-powershell-to-modify-spam-filter-rules"></a>Uso de PowerShell para modificar reglas de filtro de correo no deseado

La única opción que no está disponible al modificar una regla de filtro de correo no deseado en PowerShell es el parámetro _Enabled_ que le permite crear una regla deshabilitada. Para habilitar o deshabilitar las reglas de filtro de correo no deseado existentes, vea la siguiente sección.

Por lo demás, no hay opciones de configuración adicionales disponibles al modificar una regla de filtro de correo no deseado en PowerShell. Están disponibles las mismas opciones de configuración cuando se crea una regla que las descritas en la sección [Paso 2: Usar PowerShell para crear una regla de filtro de correo no deseado](#step-2-use-powershell-to-create-a-spam-filter-rule) anteriormente en este tema.

Para modificar una regla de filtro de correo no deseado, use esta sintaxis:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

Este ejemplo cambia el nombre de la regla de filtrado de correo no deseado existente denominada `{Fabrikam Spam Filter}`.

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule).

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

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule) y [Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule).

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a>Uso de PowerShell para establecer la prioridad de las reglas de filtro de correo no deseado

El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.

A fin de establecer la prioridad de una regla para filtrar el correo no deseado en PowerShell, use la siguiente sintaxis:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

En el ejemplo siguiente, la prioridad de la regla denominada "Marketing Department" se establece en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).

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

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy).

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

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>Envíe un mensaje GTUBE para comprobar la configuración de la directiva de correo no deseado

> [!NOTE]
> Estos pasos solo funcionarán si la organización de correo electrónico desde la que envía el mensaje GTUBE no detecta correo no deseado saliente. Si lo hace, no podrá enviar el mensaje de prueba.

Prueba genérica de correo electrónico en masa no solicitado (GTUBE) es una cadena de texto que se incluye en un mensaje de prueba para comprobar la configuración del correo no deseado de la organización. Un mensaje GTUBE es similar al archivo de texto del European Institute of Computer virus Research (EICAR) para probar la configuración de malware.

Incluya el siguiente texto GTUBE en un mensaje de correo electrónico en una única línea, sin espacios ni saltos de línea:

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```
