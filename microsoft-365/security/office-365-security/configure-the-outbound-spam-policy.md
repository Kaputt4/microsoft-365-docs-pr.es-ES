---
title: Configurar el filtrado de spam de salida
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a ver, crear, modificar y eliminar directivas de correo no deseado saliente en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3c3c6fd32d03e5df84d35d399d963c28c3d745a6
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2022
ms.locfileid: "66772092"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>Configuración del filtrado de correo no deseado saliente en EOP

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, los mensajes de correo electrónico salientes que se envían a través de EOP se comprueban automáticamente si hay spam y actividad de envío inusual.

El correo no deseado saliente de un usuario de la organización suele indicar una cuenta en peligro. Los mensajes salientes sospechosos se marcan como correo no deseado (independientemente del nivel de confianza de correo no deseado o SCL) y se enrutan a través del [grupo de entrega de alto riesgo](high-risk-delivery-pool-for-outbound-messages.md) para ayudar a proteger la reputación del servicio (es decir, mantener los servidores de correo electrónico de origen de Microsoft 365 fuera de las listas de bloqueos IP). A los administradores se les notifica automáticamente la actividad de correo electrónico saliente sospechosa y los usuarios bloqueados a través de [directivas de alerta](../../compliance/alert-policies.md).

EOP usa directivas de correo no deseado saliente como parte de la defensa general de su organización contra el correo no deseado. Para obtener más información, consulte [Protección contra correo no deseado](anti-spam-protection.md).

Los administradores pueden ver, editar y configurar (pero no eliminar) la directiva de correo no deseado saliente predeterminada. Para una mayor granularidad, también puede crear directivas de correo no deseado de salida personalizadas que se apliquen a usuarios, grupos o dominios específicos de la organización. Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.

Puede configurar directivas de correo no deseado saliente en el portal de Microsoft 365 Defender de Microsoft 365 o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell EOP independiente para organizaciones sin Exchange Online buzones).

Los elementos básicos de una directiva de correo no deseado saliente en EOP son:

- **La directiva de filtro de correo no deseado saliente**: especifica las acciones para veredictos de filtrado de correo no deseado saliente y las opciones de notificación.
- **Regla de filtro de correo no deseado saliente**: especifica la prioridad y los filtros de remitente (a los que se aplica la directiva) para una directiva de filtro de correo no deseado saliente.

La diferencia entre estos dos elementos no es obvia al administrar las directivas de correo no deseado saliente en el portal de Microsoft 365 Defender:

- Al crear una directiva, realmente va a crear una regla de filtro de correo no deseado de salida y la directiva de filtro de correo no deseado de salida asociada al mismo tiempo con el mismo nombre para ambos.
- Al modificar una directiva, la configuración relacionada con el nombre, la prioridad, habilitado o deshabilitado, y los filtros de remitente modifican la regla de filtro de correo no deseado saliente. Todas las demás configuraciones modifican la directiva de filtro de correo no deseado saliente asociada.
- Al quitar una directiva, se quitan la regla de filtro de correo no deseado saliente y la directiva de filtro de correo no deseado de salida asociada.

En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado. Para obtener más información, consulte la sección [Uso de PowerShell Exchange Online o EOP independiente para configurar directivas de correo no deseado saliente](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) más adelante en este artículo.

Cada organización tiene una directiva de correo no deseado de salida integrada denominada Default que tiene estas propiedades:

- La directiva se aplica a todos los remitentes de la organización, aunque no haya ninguna regla de filtro de correo no deseado de salida (filtros de remitente) asociada a la directiva.
- La directiva tiene un valor de prioridad personalizado **Mínimo** que no se puede modificar (la directiva siempre se aplica en último lugar). Las directivas personalizadas que cree siempre tendrán una prioridad mayor que la directiva denominada Predeterminada.
- La directiva es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar esta directiva predeterminada.

Para aumentar la eficacia del filtrado de correo no deseado saliente, puede crear directivas de correo no deseado de salida personalizadas con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Configuración contra correo no deseado**, use <https://security.microsoft.com/antispam>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para agregar, modificar y eliminar directivas de correo no deseado salientes, debe ser miembro de los grupos de roles Administración de la **organización** o **Administrador de seguridad** .
  - Para el acceso de solo lectura a las directivas de correo no deseado saliente, debe ser miembro de los grupos de roles **Lector global** o **Lector de seguridad** .

  Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - La adición de usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365. Para obtener más información, consulte [Acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para ver nuestra configuración recomendada para las directivas de correo no deseado saliente, consulte [Configuración de la directiva de filtro de correo no deseado saliente de EOP](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).

- Se han superado [las directivas de alerta](../../compliance/alert-policies.md) predeterminadas **denominadas Límite de envío** de **correo electrónico, se han detectado patrones de envío de correo electrónico sospechoso** y **el usuario ha restringido el envío de correo electrónico** a los miembros del grupo **TenantAdmins** (**administradores globales**) sobre la actividad de correo electrónico saliente inusual y los usuarios bloqueados debido al correo no deseado saliente. Para obtener más información, consulte [Comprobación de la configuración de alertas para usuarios restringidos](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Se recomienda usar estas directivas de alerta en lugar de las opciones de notificación en las directivas de correo no deseado saliente.

## <a name="use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies"></a>Uso del portal de Microsoft 365 Defender para crear directivas de correo no deseado saliente

La creación de una directiva de correo no deseado de salida personalizada en el portal de Microsoft 365 Defender crea la regla de filtro de correo no deseado y la directiva de filtro de correo no deseado asociada al mismo tiempo con el mismo nombre para ambos.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **Directivas de amenazas** \> **Correo electrónico no deseado** en la sección **Directivas**. Para ir directamente a la página **Configuración contra correo no deseado**, use <https://security.microsoft.com/antispam>.

2. En la página **Directivas contra correo no deseado** , haga clic en ![el icono Crear.](../../media/m365-cc-sc-create-icon.png) **Cree una directiva** y, a continuación, seleccione **Saliente** en la lista desplegable.

3. Se abre el asistente de directivas. En la página **Nombre de la directiva**, configure estas opciones:
   - **Nombre**: escriba un nombre único y descriptivo para la directiva.
   - **Descripción**: escriba una descripción opcional para la directiva.

   Cuando termine, haga clic en **Siguiente**.

4. En la página **Usuarios, grupos y dominios** que aparece, identifique los remitentes internos a los que se aplica la directiva (condiciones de destinatario):
   - **Usuarios**: los buzones de correo, los usuarios de correo o los contactos de correo especificados.
   - **Grupos**:
     - Miembros de los grupos de distribución o grupos de seguridad habilitados para correo especificados.
     - Los Grupos de Microsoft 365 especificados.
   - **Dominios**: todos los remitentes de los [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados en su organización.

   Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados. Repita este proceso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

   Para los usuarios o grupos, puede utilizar la mayoría de los identificadores (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de la cuenta, etc.), pero el nombre para mostrar correspondiente se muestra en los resultados. Para los usuarios, introduzca un asterisco (\*) por sí mismo para ver todos los valores disponibles.

   Varios valores en la misma condición usan la lógica OR (por ejemplo, _\<sender1\>_ o _\<sender2\>_). Hay diferentes condiciones que usan la lógica AND (por ejemplo, _\<sender1\>_ y _\<member of group 1\>_).

   - **Excluir estos usuarios, grupos y dominios**: para agregar excepciones para los remitentes internos a los que se aplica la directiva (excepciones de destinatario), seleccione esta opción y configure las excepciones. La configuración y el comportamiento se muestran exactamente igual que las condiciones.

   > [!IMPORTANT]
   > Las diferentes condiciones o excepciones no son aditivas; son inclusivas. La directiva se aplica _solo_ a los destinatarios que coinciden con _todos_ los filtros de destinatarios especificados. Por ejemplo, se configura una condición de filtro de destinatario en la directiva con los siguientes valores:
   >
   > - El destinatario es: romain@contoso.com
   > - El destinatario es miembro de: Ejecutivos
   >
   > La política se aplica a romain@contoso.com _solo_ si también es miembro del grupo Ejecutivos. Si no es miembro del grupo, la directiva no se le aplica.
   >
   > Del mismo modo, si usa el mismo filtro de destinatario como excepción a la directiva, la directiva no se aplica a romain@contoso.com _solo_ si también es miembro del grupo Ejecutivos. Si no es miembro del grupo, la directiva se le sigue aplicando.

   Cuando termine, haga clic en **Siguiente**.

5. En la página **Configuración de protección** que se abre, configure los siguientes valores:
   - **Límites de mensajes**: la configuración de esta sección configura los límites para los mensajes de correo electrónico salientes de **Exchange Online** buzones:
     - **Establecer un límite de mensajes externos**: el número máximo de destinatarios externos por hora.
     - **Establecer un límite de mensajes interno**: el número máximo de destinatarios internos por hora.
     - **Establecer un límite de mensajes diario**: el número total máximo de destinatarios por día.

     Un valor válido es de 0 a 10000. El valor predeterminado es 0, lo que significa que se usan los valores predeterminados del servicio. Para obtener más información, consulte [Límites de envío](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

    Escriba un valor en el cuadro o use las flechas de aumento o disminución del cuadro.

   - **Restricción impuesta a los usuarios que alcanzan el límite de mensajes**: seleccione una acción de la lista desplegable cuando se supere cualquiera de los límites de la sección **Configuración** de protección.

     Para todas las acciones, los remitentes especificados en la directiva **Usuario restringido de envío de** alertas de correo electrónico (y en el ahora redundante **Notificar a estos usuarios y grupos si un remitente está bloqueado debido a la configuración de envío de correo no deseado saliente** más adelante en esta página) reciben notificaciones por correo electrónico.

     - **Restrinja al usuario el envío de correo hasta el día siguiente**: este es el valor predeterminado. Se envían notificaciones por correo electrónico y el usuario no podrá enviar más mensajes hasta el día siguiente, según la hora UTC. No hay ninguna manera de que el administrador invalide este bloque.
       - La directiva de alertas denominada **User restricted from sending email** notifica a los administradores (por correo electrónico y en la página **De visualización de alertas** \> de incidentes &).
       - También se notifica a todos los destinatarios especificados en la configuración **Notificar a personas específicas si un remitente está bloqueado debido al envío de correo no deseado** en la directiva.
       - El usuario no podrá enviar más mensajes hasta el día siguiente, según la hora UTC. No hay ninguna manera de que el administrador invalide este bloque.
     - **Impedir que el usuario envíe correo:** se envían notificaciones por correo electrónico, el usuario se agrega a **usuarios** <https://security.microsoft.com/restrictedusers> restringidos en el portal de Microsoft 365 Defender y el usuario no puede enviar correo electrónico hasta que un administrador los quite de **los usuarios restringidos**. Después de que un administrador quite al usuario de la lista, el usuario no se restringirá de nuevo para ese día. Para obtener instrucciones, consulte [Eliminación de un usuario del portal Usuarios restringidos después de enviar correo electrónico no deseado](removing-user-from-restricted-users-portal-after-spam.md).
     - **Sin acción, solo alerta**: se envían notificaciones por correo electrónico.

   - **Reglas de reenvío**: use la configuración de esta sección para controlar el reenvío automático de correo electrónico Exchange Online **buzones** a remitentes externos. Para obtener más información, consulte [Controlar el reenvío automático de correo electrónico externo en Microsoft 365](external-email-forwarding.md).

     > [!NOTE]
     > Cuando el reenvío automático está deshabilitado, el destinatario recibirá un informe de no entrega (también conocido como NDR o mensaje de devolución) si los remitentes externos envían correo electrónico a un buzón que tiene el reenvío en su lugar. Si el mensaje lo envía un remitente interno **y** el método de reenvío es el [reenvío de buzones](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (también conocido como _reenvío SMTP_), el remitente interno obtendrá el NDR. El remitente interno no obtiene un NDR si el reenvío se produjo debido a una regla de bandeja de entrada.

     Seleccione una de las siguientes acciones en la lista desplegable **Reglas de reenvío automático** :

     - **Automático: controlado por el sistema**: permite el filtrado de correo no deseado saliente para controlar el reenvío automático de correo electrónico externo. Este es el valor predeterminado.
     - **Activado**: la directiva no deshabilita el reenvío automático de correo electrónico externo.
     - **Desactivado**: la directiva deshabilita todo el reenvío automático de correo electrónico externo.

   - **Notificaciones**: use la configuración de la sección para configurar destinatarios adicionales que deben recibir copias y notificaciones de mensajes de correo electrónico salientes sospechosos:

     - **Enviar una copia de salida sospechosa que supere estos límites a estos usuarios y grupos**: esta configuración agrega los destinatarios especificados al campo CCO de mensajes salientes sospechosos.

       > [!NOTE]
       > Esta configuración solo funciona en la directiva de correo no deseado saliente predeterminada. No funciona en las directivas de correo no deseado saliente personalizadas que cree.

       Para habilitar esta configuración, active la casilla . En el cuadro que aparece, haga clic en el cuadro, escriba una dirección de correo electrónico válida y, a continuación, presione Entrar o seleccione el valor completo que se muestra debajo del cuadro.

       Repita este paso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

   - **Notificar a estos usuarios y grupos si un remitente está bloqueado debido al envío de correo no deseado saliente**

     > [!IMPORTANT]
     >
     > - Esta configuración está en desuso de las directivas de correo no deseado saliente.
     >
     > - La [directiva de alerta](../../compliance/alert-policies.md) predeterminada denominada **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section. **Se recomienda encarecidamente usar la directiva de alertas en lugar de esta configuración en la directiva de correo no deseado saliente para notificar a los administradores y a otros usuarios**. Para obtener instrucciones, consulte [Comprobación de la configuración de alertas para usuarios restringidos](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).

   Cuando termine, haga clic en **Siguiente**.

6. En la página **Revisar** que aparece, revise la configuración. Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Crear**.

7. En la página de confirmación que aparece, haga clic en **Listo**.

## <a name="use-the-microsoft-365-defender-portal-to-view-outbound-spam-policies"></a>Uso del portal de Microsoft 365 Defender para ver las directivas de correo no deseado saliente

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **Directivas de amenazas** \> **Correo electrónico no deseado** en la sección **Directivas**. Para ir directamente a la página **Configuración contra correo no deseado**, use <https://security.microsoft.com/antispam>.

2. En la página de directivas **antispam**, busque uno de los siguientes valores:
   - El valor **De tipo** es **Directiva de correo no deseado de salida personalizada**
   - El valor **Nombre** es **Directiva de salida contra correo no deseado (valor predeterminado)**

   Las siguientes propiedades se muestran en la lista de directivas contra el correo no deseado:

   - **Nombre**
   - **Estado**
   - **Prioridad**
   - **Tipo**

3. Al seleccionar una directiva de correo no deseado saliente haciendo clic en el nombre, la configuración de la directiva se muestra en un control flotante.

## <a name="use-the-microsoft-365-defender-portal-to-modify-outbound-spam-policies"></a>Uso del portal de Microsoft 365 Defender para modificar las directivas de correo no deseado saliente

1. En el portal de Microsoft 365 Defender, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **Directivas de amenazas** \> **Correo electrónico no deseado** en la sección **Directivas**.

2. En la página **Directivas contra correo no deseado** , seleccione una directiva de correo no deseado saliente en la lista haciendo clic en el nombre:
   - Una directiva personalizada que creó donde el valor de la columna **Tipo** es **Directiva de correo no deseado de salida personalizada**.
   - Directiva predeterminada denominada **Directiva de salida contra correo no deseado (valor predeterminado).**

3. En el control flotante de detalles de la directiva que aparece, seleccione **Editar** en cada sección para modificar la configuración dentro de la sección. Para obtener más información sobre la configuración, consulte la sección [Anterior Uso del portal de Microsoft 365 Defender para crear directivas de correo no deseado salientes](#use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies) de este artículo.

   Para la directiva de correo no deseado saliente predeterminada, la sección **Aplicado a** no está disponible (la directiva se aplica a todos) y no se puede cambiar el nombre de la directiva.

Para habilitar o deshabilitar una directiva, establecer el orden de prioridad de la directiva o configurar las notificaciones del usuario final, consulte las secciones siguientes.

### <a name="enable-or-disable-custom-outbound-spam-policies"></a>Habilitación o deshabilitación de directivas de correo no deseado saliente personalizadas

No puede deshabilitar la directiva de correo no deseado saliente predeterminada.

1. En el portal de Microsoft 365 Defender, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **Directivas de amenazas** \> **Correo electrónico no deseado** en la sección **Directivas**.

2. En la página **Directivas contra correo no deseado** , seleccione una directiva con el **valor Tipo** de Directiva de **correo no deseado de salida personalizada** de la lista haciendo clic en el nombre.

3. En la parte superior del control flotante de detalles de la directiva que aparece, verá uno de los siguientes valores:
   - **Directiva desactivada**: para activar la directiva, haga clic en ![icono Activar.](../../media/m365-cc-sc-turn-on-off-icon.png) **Activar** .
   - **Directiva activada**: para desactivar la directiva, haga clic en el ![Icono Desactivar](../../media/m365-cc-sc-turn-on-off-icon.png) **Desactivar**.

4. En el cuadro de diálogo de confirmación que aparece, haga clic **Activar** o **Desactivar**.

5. Haga clic en **Cerrar** en el control flotante de detalles de la directiva.

De nuevo en la página principal de la directiva, el valor **Estado** de la directiva estará **Activado** o **Desactivado**.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>Establecer la prioridad de las directivas de correo no deseado saliente personalizadas

De forma predeterminada, las directivas de correo no deseado saliente tienen una prioridad que se basa en el orden en el que se crearon (las directivas más recientes son menos prioritarias que las directivas anteriores). Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor). Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

Para cambiar la prioridad de una directiva, haga clic en **Aumentar prioridad** o **Reducir prioridad** en las propiedades de la directiva (no puede modificar directamente el número de **Prioridad** en el portal de Microsoft 365 Defender). Cambiar la prioridad de una directiva sólo tiene sentido si tiene varias directivas.

 **Notas**:

- En el portal de Microsoft 365 Defender, solo puede cambiar la prioridad de la directiva de correo no deseado saliente después de crearla. En PowerShell, puede reemplazar la prioridad predeterminada al crear la regla de filtro de correo no deseado (que puede afectar a la prioridad de las reglas existentes).
- Las directivas de correo no deseado saliente se procesan en el orden en que se muestran (la primera directiva tiene el valor **de prioridad** 0). La directiva de correo no deseado saliente predeterminada tiene el valor de prioridad **Más bajo** y no se puede cambiar.

1. En el portal de Microsoft 365 Defender, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **Directivas de amenazas** \> **Correo electrónico no deseado** en la sección **Directivas**.

2. En la página **Directivas de correo no deseado** , seleccione una directiva con el **valor Tipo** de Directiva de **correo no deseado saliente personalizada** de la lista haciendo clic en el nombre.

3. En la parte superior del control flotante de detalles de la directiva que aparece, verá **Aumentar la prioridad** o **Disminuir la prioridad** en función del valor de prioridad actual y del número de directivas personalizadas:
   - La directiva de correo no deseado saliente con el valor **De prioridad** **0** solo tiene la opción **Reducir prioridad** disponible.
   - La directiva de correo no deseado saliente con el valor **de prioridad** más bajo (por ejemplo, **3**) solo tiene la opción **Aumentar prioridad** disponible.
   - Si tiene tres o más directivas de correo no deseado saliente, las directivas entre los valores de prioridad más alta y más baja tienen disponibles las opciones **Aumentar prioridad** y **Reducir prioridad** .

   Haga clic en el ![Icono Aumentar la prioridad.](../../media/m365-cc-sc-increase-icon.png) **Aumentar la prioridad** o en el ![Icono Disminuir la prioridad](../../media/m365-cc-sc-decrease-icon.png) **Reducir la prioridad** para cambiar el valor de **Prioridad**.

4. Cuando haya terminado, haga clic en **Cerrar** en el control flotante de detalles de la directiva.

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-outbound-spam-policies"></a>Uso del portal de Microsoft 365 Defender para quitar directivas de correo no deseado saliente personalizadas

Cuando se usa el portal de Microsoft 365 Defender para quitar una directiva de correo no deseado saliente personalizada, se eliminan la regla de filtro de correo no deseado y la directiva de filtro de correo no deseado correspondiente. No puede quitar la directiva de correo no deseado saliente predeterminada.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **Directivas de amenazas** \> **Correo electrónico no deseado** en la sección **Directivas**. Para ir directamente a la página **Configuración contra correo no deseado**, use <https://security.microsoft.com/antispam>.

2. En la página **Directivas contra correo no deseado** , seleccione una directiva con el **valor Tipo** de Directiva de **correo no deseado de salida personalizada** de la lista haciendo clic en el nombre. En la parte superior del control flotante de detalles de la directiva que aparece, haga clic en ![icono Más acciones.](../../media/m365-cc-sc-more-actions-icon.png) **Más acciones** \> ![Icono Eliminar directiva](../../media/m365-cc-sc-delete-icon.png)**Eliminar directiva**.

3. En el cuadro de diálogo de confirmación que aparece, haga clic en **Sí**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Usar Exchange Online PowerShell o PowerShell EOP independiente para configurar directivas de correo no deseado salientes

Como se describió anteriormente, una directiva de correo no deseado saliente consta de una directiva de filtro de correo no deseado saliente y una regla de filtro de correo no deseado saliente.

En Exchange Online PowerShell o PowerShell EOP independiente, la diferencia entre las directivas de filtro de correo no deseado saliente y las reglas de filtro de correo no deseado saliente es evidente. Las directivas de filtro de correo no deseado saliente se administran mediante los **\*cmdlets -HostedOutboundSpamFilterPolicy** y se administran las reglas de filtro de correo no deseado saliente mediante los **\*cmdlets -HostedOutboundSpamFilterRule** .

- En PowerShell, primero se crea la directiva de filtro de correo no deseado saliente y, a continuación, se crea la regla de filtro de correo no deseado saliente que identifica la directiva a la que se aplica la regla.
- En PowerShell, modificará la configuración de la directiva de filtro de correo no deseado saliente y la regla de filtro de correo no deseado saliente por separado.
- Al quitar una directiva de filtro de correo no deseado saliente de PowerShell, la regla de filtro de correo no deseado saliente correspondiente no se quita automáticamente y viceversa.

### <a name="use-powershell-to-create-outbound-spam-policies"></a>Uso de PowerShell para crear directivas de correo no deseado saliente

La creación de una directiva de correo no deseado saliente en PowerShell es un proceso de dos pasos:

1. Cree la directiva de filtro de correo no deseado saliente.
2. Cree la regla de filtro de correo no deseado saliente que especifique la directiva de filtro de correo no deseado saliente a la que se aplica la regla.

   **Notas**:

   - Puede crear una nueva regla de filtro de correo no deseado saliente y asignarle una directiva de filtro de correo no deseado saliente existente y no asociada. Una regla de filtro de correo no deseado saliente no se puede asociar a más de una directiva de filtro de correo no deseado saliente.
   - Puede configurar las siguientes opciones en las nuevas directivas de filtro de correo no deseado saliente en PowerShell que no estén disponibles en el portal de Microsoft 365 Defender hasta después de crear la directiva:
     - Cree la nueva directiva como deshabilitada (_habilitada_ `$false` en el cmdlet **New-HostedOutboundSpamFilterRule** ).
     - Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_) en el cmdlet **New-HostedOutboundSpamFilterRule** .
   - Una nueva directiva de filtro de correo no deseado saliente que cree en PowerShell no será visible en el portal de Microsoft 365 Defender hasta que asigne la directiva a una regla de filtro de correo no deseado saliente.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Paso 1: Uso de PowerShell para crear una directiva de filtro de correo no deseado saliente

Para crear una directiva de filtro de correo no deseado saliente, use esta sintaxis:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

En este ejemplo se crea una nueva directiva de filtro de correo no deseado saliente denominada Contoso Executives con la siguiente configuración:

- Los límites de velocidad de destinatarios están restringidos a valores más pequeños que los valores predeterminados. Para obtener más información, consulte [Envío de límites en las opciones de Microsoft 365](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).

- Una vez alcanzado uno de los límites, se impide que el usuario envíe mensajes.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Paso 2: Uso de PowerShell para crear una regla de filtro de correo no deseado saliente

Para crear una regla de filtro de correo no deseado saliente, use esta sintaxis:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Sender filters> [<Sender filter exceptions>] [-Comments "<OptionalComments>"]
```

En este ejemplo se crea una nueva regla de filtro de correo no deseado saliente denominada Contoso Executives con esta configuración:

- La directiva de filtro de correo no deseado saliente denominada Contoso Executives está asociada a la regla.
- La regla se aplica a los miembros del grupo denominado Contoso Executives Group.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>Uso de PowerShell para ver las directivas de filtro de correo no deseado saliente

Para devolver una lista de resumen de todas las directivas de filtro de correo no deseado saliente, ejecute este comando:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Para devolver información detallada sobre una directiva de filtro de correo no deseado de salida específica, use esta sintaxis:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

En este ejemplo se devuelven todos los valores de propiedad de la directiva de filtro de correo no deseado saliente denominada Ejecutivos.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>Uso de PowerShell para ver las reglas de filtro de correo no deseado saliente

Para ver las reglas de filtro de correo no deseado saliente existentes, use la sintaxis siguiente:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

Para devolver una lista de resumen de todas las reglas de filtro de correo no deseado saliente, ejecute este comando:

```PowerShell
Get-HostedOutboundSpamFilterRule
```

Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

Para devolver información detallada sobre una regla de filtro de correo no deseado saliente específica, use esta sintaxis:

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

En este ejemplo se devuelven todos los valores de propiedad de la regla de filtro de correo no deseado saliente denominada Contoso Executives.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>Uso de PowerShell para modificar directivas de filtro de correo no deseado saliente

La misma configuración está disponible al modificar una directiva de filtro de malware en PowerShell que al crear la directiva, como se describe en la sección [Paso 1: Uso de PowerShell para crear una directiva de filtro de correo no deseado saliente](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) anteriormente en este artículo.

> [!NOTE]
> No se puede cambiar el nombre de una directiva de filtro de correo no deseado saliente (el cmdlet **Set-HostedOutboundSpamFilterPolicy** no tiene ningún parámetro _Name_ ). Al cambiar el nombre de una directiva de correo no deseado saliente en el portal de Microsoft 365 Defender, solo se cambia el nombre de la _regla_ de filtro de correo no deseado saliente.

Para modificar una directiva de filtro de correo no deseado saliente, use esta sintaxis:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>Uso de PowerShell para modificar las reglas de filtro de correo no deseado saliente

La única configuración que no está disponible al modificar una regla de filtro de correo no deseado saliente en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada. Para habilitar o deshabilitar las reglas de filtro de correo no deseado saliente existentes, consulte la sección siguiente.

De lo contrario, no hay ninguna configuración adicional disponible al modificar una regla de filtro de correo no deseado saliente en PowerShell. La misma configuración está disponible al crear una regla como se describe en la sección [Paso 2: Uso de PowerShell para crear una regla de filtro de correo no deseado saliente](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) anteriormente en este artículo.

Para modificar una regla de filtro de correo no deseado saliente, use esta sintaxis:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>Uso de PowerShell para habilitar o deshabilitar reglas de filtro de correo no deseado saliente

Habilitar o deshabilitar una regla de filtro de correo no deseado saliente en PowerShell habilita o deshabilita toda la directiva de correo no deseado saliente (la regla de filtro de correo no deseado saliente y la directiva de filtro de correo no deseado saliente asignada). No se puede habilitar ni deshabilitar la directiva de correo no deseado saliente predeterminada (siempre se aplica a todos los remitentes).

Para habilitar o deshabilitar una regla de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

En este ejemplo se deshabilita la regla de filtro de correo no deseado saliente denominada Departamento de marketing.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Este ejemplo habilita la misma regla.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) y [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>Uso de PowerShell para establecer la prioridad de las reglas de filtro de correo no deseado saliente

El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.

Para establecer la prioridad de una regla de filtro de correo no deseado saliente en PowerShell, use la sintaxis siguiente:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

En el ejemplo siguiente, la prioridad de la regla denominada "Marketing Department" se establece en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

**Notas**:

- Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-HostedOutboundSpamFilterRule** en su lugar.
- La directiva de filtro de correo no deseado predeterminada saliente no tiene una regla de filtro de correo no deseado correspondiente y siempre tiene el valor de prioridad no modificable **Más bajo**.

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>Uso de PowerShell para quitar directivas de filtro de correo no deseado saliente

Cuando se usa PowerShell para quitar una directiva de filtro de correo no deseado saliente, no se quita la regla de filtro de correo no deseado saliente correspondiente.

Para quitar una directiva de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

En este ejemplo se quita la directiva de filtro de correo no deseado saliente denominada Departamento de marketing.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>Uso de PowerShell para quitar reglas de filtro de correo no deseado saliente

Cuando se usa PowerShell para quitar una regla de filtro de correo no deseado saliente, no se quita la directiva de filtro de correo no deseado saliente correspondiente.

Para quitar una regla de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

En este ejemplo se quita la regla de filtro de correo no deseado saliente denominada Departamento de marketing.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).

## <a name="for-more-information"></a>Más información

[Eliminación de usuarios bloqueados del portal usuarios restringidos](removing-user-from-restricted-users-portal-after-spam.md)

[Grupo de entrega de alto riesgo para mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md)

[Preguntas más frecuentes sobre la protección contra correo electrónico no deseado](anti-spam-protection-faq.yml)

[Informe de mensajes reenviados automáticamente](mfi-auto-forwarded-messages-report.md)
