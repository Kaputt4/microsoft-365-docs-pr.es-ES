---
title: Configurar el filtrado de spam de salida
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre cómo ver, crear, modificar y eliminar directivas de correo no deseado salientes en Exchange Online Protection (EOP).
ms.openlocfilehash: 22a809370787df1798f2f777c852d1004565d2a6
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "46798287"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>Configurar el filtrado de correo no deseado saliente en EOP

En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, los mensajes de correo electrónico salientes que se envían a través de EOP se comprueban automáticamente en busca de correo no deseado y actividad de envío inusual.

Normalmente, el correo no deseado saliente de un usuario de la organización indica una cuenta en peligro. Los mensajes sospechosos se marcan como correo no deseado (independientemente del nivel de confianza de correo no deseado o de SCL) y se enrutan a través del [grupo de entrega de alto riesgo](high-risk-delivery-pool-for-outbound-messages.md) para ayudar a proteger la reputación del servicio (es decir, mantenga los servidores de correo electrónico de origen de Microsoft 365 en las listas de direcciones IP bloqueadas). Los administradores reciben automáticamente una notificación de la actividad de correo electrónico saliente y de los usuarios bloqueados mediante [directivas de alerta](../../compliance/alert-policies.md).

EOP usa directivas de correo no deseado salientes como parte de la defensa general de la organización contra el correo no deseado. Para obtener más información, consulte [Protección contra correo no deseado](anti-spam-protection.md).

Los administradores pueden ver, editar y configurar (pero no eliminar) la Directiva de correo no deseado saliente predeterminada. Para una mayor granularidad, también puede crear directivas de correo no deseado saliente personalizadas que se aplican a usuarios, grupos o dominios específicos de la organización. Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.

Puede configurar directivas de correo no deseado salientes en el centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para Microsoft 365 organizaciones con buzones en Exchange Online; independiente de EOP para organizaciones sin buzones de correo de Exchange Online).

## <a name="outbound-spam-policies-in-the-security--compliance-center-vs-powershell"></a>Directivas de correo no deseado salientes en el centro de seguridad & cumplimiento vs PowerShell

Los elementos básicos de una directiva de correo no deseado saliente en EOP son los siguientes:

- **La Directiva de filtro de correo no deseado saliente**: especifica las acciones para los veredictos de filtrado de correo no deseado saliente y las opciones de notificación.

- **La regla de filtro de correo no deseado saliente**: especifica la prioridad y los filtros de destinatarios (a los que se aplica la Directiva) para una directiva de filtro de correo no deseado saliente.

La diferencia entre estos dos elementos no es obvia cuando se administran las directivas de correo no deseado saliente en el centro de seguridad & cumplimiento:

- Cuando se crea una directiva de correo no deseado saliente en el centro de seguridad & cumplimiento, en realidad se crea una regla de filtro de correo no deseado saliente y la Directiva de filtro de correo no deseado saliente asociada al mismo tiempo con el mismo nombre para ambas.

- Cuando se modifica una directiva de correo no deseado saliente en el centro de seguridad & cumplimiento, la configuración relacionada con los filtros nombre, prioridad, habilitado o deshabilitado y destinatarios modifica la regla de filtro de correo no deseado saliente. Todas las demás opciones modifican la Directiva de filtro de correo no deseado saliente asociada.

- Cuando quita una directiva de correo no deseado saliente del centro de seguridad & cumplimiento, se quita la regla de filtro de correo no deseado saliente y la Directiva de filtro de correo no deseado saliente asociada.

En Exchange Online PowerShell o en PowerShell independiente de EOP, la diferencia entre las directivas de filtro de correo no deseado saliente y las reglas de filtro de correo no deseado saliente es evidente. Puede administrar las directivas de filtro de correo no deseado saliente con los cmdlets ** \* -HostedOutboundSpamFilterPolicy** y administrar las reglas de filtro de correo no deseado saliente con los cmdlets ** \* -HostedOutboundSpamFilterRule** .

- En PowerShell, se crea la Directiva de filtro de correo no deseado saliente en primer lugar y, a continuación, se crea la regla de filtro de correo no deseado saliente que identifica la Directiva a la que se aplica la regla.

- En PowerShell, se modifica la configuración de la Directiva de filtro de correo no deseado saliente y de la regla de filtro de correo no deseado saliente por separado.

- Cuando quita una directiva de filtro de correo no deseado saliente de PowerShell, la regla de filtro de correo no deseado saliente correspondiente no se quita automáticamente y viceversa.

### <a name="default-outbound-spam-policy"></a>Directiva de correo no deseado saliente predeterminada

Cada organización tiene integrada una directiva de correo no deseado saliente denominada predeterminada que tiene estas propiedades:

- La Directiva de filtro de correo no deseado saliente denominada predeterminada se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla de filtro de correo no deseado saliente (filtros de destinatario) asociada a la Directiva.

- La directiva denominada Predeterminada tiene un valor de prioridad personalizado **Inferior** que no se puede modificar (la directiva siempre se aplica en último lugar). Las directivas personalizadas que cree siempre tendrán una prioridad mayor que la directiva denominada Predeterminada.

- La directiva denominada Predeterminada es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar la directiva predeterminada.

Para aumentar la eficacia del filtrado de correo no deseado saliente, puede crear directivas de correo no deseado saliente personalizadas con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página **Configuración contra correo no deseado**, use <https://protection.office.com/antispam>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Para poder realizar los procedimientos de este tema, deberá tener asignados los permisos necesarios:

  - Para agregar, modificar y eliminar directivas de correo no deseado saliente, debe pertenecer a uno de los siguientes grupos de roles:

    - **Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).
    - **Administración de la organización** o **Administración de higiene** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Para el acceso de solo lectura a las directivas de correo no deseado saliente, debe pertenecer a uno de los siguientes grupos de roles:

    - **Lector de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).
    - **Administración de la organización de solo visualización** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Para conocer la configuración recomendada para las directivas de correo no deseado saliente, consulte [EOP Outbound Spam Filter Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).

- Las [directivas de alerta](../../compliance/alert-policies.md) predeterminadas denominadas límite de envío de **correo electrónico superado**, los **patrones de envío de correo electrónico sospechoso detectados**y el **usuario restringido del envío de correo electrónico** ya envían notificaciones por correo electrónico a los miembros del grupo **TenantAdmins** (**global Admins**) sobre la actividad de correo electrónico saliente y los usuarios bloqueados debido a correo no deseado saliente. Para obtener más información, consulte [Verify The Alert Settings for Restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Se recomienda usar estas directivas de alerta en lugar de las opciones de notificación en las directivas de correo no deseado saliente.

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>Usar el centro de seguridad & cumplimiento para crear directivas de correo no deseado saliente

La creación de una directiva personalizada de correo no deseado saliente en el centro de seguridad & cumplimiento crea la regla de filtro de correo no deseado y la Directiva de filtro de correo no deseado asociada al mismo tiempo con el mismo nombre para ambas.

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la página **configuración contra correo no deseado** , haga clic en **crear una directiva de salida**.

3. En la **Directiva de filtro de correo no deseado saliente** , vaya hacia fuera que se abre, configure las siguientes opciones:

   - **Nombre**: escriba un nombre único y descriptivo para la directiva.

   - **Descripción**: escriba una descripción opcional para la directiva.

4. Opcional Expanda la sección **notificaciones** para configurar usuarios adicionales que deben recibir copias y notificaciones de mensajes de correo electrónico salientes sospechosos:

   - **Enviar una copia de los mensajes de correo electrónico saliente sospechosos a personas específicas**: esta opción agrega los usuarios especificados como destinatarios en copia oculta a los mensajes sospechosos de salida.

     > [!NOTE]
     > Esta configuración solo funciona en la directiva predeterminada de correo no deseado saliente. No funciona en las directivas de correo no deseado saliente personalizadas que cree.

     Para habilitar esta opción:

     1. Active la casilla para habilitar la configuración.

     1. Haga clic en **Agregar personas**. En el control flotante **Agregar o quitar destinatarios** que aparece:

     1. Escriba la dirección de correo electrónico del remitente. Puede especificar varias direcciones de correo electrónico separadas por punto y coma (;) o un destinatario por línea.

     1. Haga clic en ![Icono Agregar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) para agregar los destinatarios.

        Repita estos pasos tantas veces como sea necesario.

        Los destinatarios que ha agregado aparecen en la sección **lista de destinatarios** en el control flotante. Para eliminar un destinatario, haga clic en el ![ botón quitar ](../../media/scc-remove-icon.png) .

     1. Cuando haya terminado, haga clic en **Guardar**.

        Para deshabilitar esta opción, desactive la casilla de verificación.

   - **Notificar a personas específicas si un remitente está bloqueado debido al envío de correo no deseado saliente**:

     > [!IMPORTANT]
     >
     > - Esta configuración está en desuso de las directivas de correo no deseado saliente.
     >
     > - La [Directiva de alerta](../../compliance/alert-policies.md) predeterminada denominada **usuario restringido del envío de correo electrónico** ya envía notificaciones por correo electrónico a los miembros del grupo **TenantAdmins** (**administradores globales**) cuando los usuarios se bloquean debido a que superan los límites de la sección **límites de destinatarios** . Se **recomienda encarecidamente usar la Directiva de alertas en lugar de esta opción en la Directiva de correo no deseado saliente para notificar a los administradores y a otros usuarios**. Para obtener instrucciones, consulte [Verify The Alert Settings for Restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).

5. Opcional Expanda la sección **límites de destinatarios** para configurar los límites y las acciones de los mensajes de correo electrónico saliente sospechosos:

   > [!NOTE]
   > Esta configuración solo se aplica a los buzones basados en la nube.

   - **Número máximo de destinatarios por usuario**

     Un valor válido es de 0 a 10000. El valor predeterminado es 0, lo que significa que se usan los valores predeterminados del servicio. Para obtener más información, consulte [límites de envío](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

     - **Límite horario externo**: el número máximo de destinatarios externos por hora.

     - **Límite horario interno**: el número máximo de destinatarios internos por hora.

     - **Límite diario**: número máximo total de destinatarios por día.

   - **Acción cuando un usuario supera los límites anteriores**: configure la acción que se llevará a cabo cuando se supere alguno de los **límites de destinatarios** . Para todas las acciones, los destinatarios especificados en el **usuario restringió el envío de la Directiva de alerta de correo electrónico** (y en el ahora la Directiva de notificación de correo no deseado **se bloquea al enviar un remitente porque al enviar la configuración de correo no deseado saliente** en la Directiva de correo no deseado de salida recibe notificaciones de correo electrónico.

     - **Restringir al usuario el envío de correo hasta el siguiente día**: este es el valor predeterminado. Se envían notificaciones por correo electrónico y el usuario no podrá enviar más mensajes hasta el día siguiente, en función de la hora UTC. El administrador no tiene forma de reemplazar este bloque.

       - La alerta de actividad denominada **usuario restringido del envío de correo electrónico** notifica a los administradores (por correo electrónico y en la página **Ver alertas** ).

       - También se notifica a los destinatarios especificados en la directiva **notificar a personas específicas si un remitente está bloqueado debido al envío de correo no deseado saliente** en la Directiva.

       - El usuario no podrá enviar más mensajes hasta el día siguiente, en función de la hora UTC. El administrador no tiene forma de reemplazar este bloque.

     - **Restringir al usuario el envío de correo**: se envían notificaciones por correo electrónico, el usuario se agrega al portal **[Restricted users] <https://sip.protection.office.com/restrictedusers> ** en el centro de seguridad & cumplimiento y el usuario no puede enviar correo electrónico hasta que un administrador lo elimine del portal de **usuarios restringidos** . Una vez que un administrador quita al usuario de la lista, el usuario no volverá a estar restringido para ese día. Para obtener instrucciones, consulte [quitar un usuario del portal de usuarios restringidos después de enviar correo no deseado](removing-user-from-restricted-users-portal-after-spam.md).

     - **No se realiza ninguna acción, solo alerta**: se envían notificaciones por correo electrónico.
6. Opcional Expanda la sección **desvío automático** para configurar los controles sobre cómo se controla el reenvío automático por parte de los usuarios.

   > [!NOTE]
   > Esta configuración solo se aplica a los buzones basados en la nube.

   - **Reenvío automático**
  
      Seleccione una de las opciones para controlar cómo se controla el reenvío automático.

      - **Automático**: configuración predeterminada que permite al sistema controlar el reenvío automático con el reenvío automático deshabilitado de forma predeterminada.
      - **On**: el reenvío externo está habilitado en la Directiva sin restricción.
      - **Desactivado**: el reenvío externo está deshabilitado y se bloqueará

7. Necesarios Expanda la sección **aplicado a** para identificar los remitentes internos a los que se aplica la Directiva.

    Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<sender1\>_ o _\<sender2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<sender1\>_ y _\<member of group 1\>_).

    Es más fácil hacer clic en **Agregar una condición** tres veces para ver todas las condiciones disponibles. Puede hacer clic en el ![botón Quitar](../../media/scc-remove-icon.png) para quitar condiciones que no quiera configurar.

    - **El dominio del remitente es**: especifica los remitentes en uno o varios de los dominios aceptados configurados en la organización. Haga clic en el cuadro **Agregar una etiqueta** para ver y seleccionar un dominio. Haga clic de nuevo en el cuadro **Agregar una etiqueta** para seleccionar dominios adicionales si hay más de un dominio disponible.

    - **Sender es**: especifica uno o más usuarios en la organización. Haga clic en **Agregar una etiqueta** y comience a escribir para filtrar la lista. Vuelva a hacer clic en el cuadro **Agregar una etiqueta** para seleccionar remitentes adicionales.

    - **Sender es un miembro de**: especifica uno o más grupos de la organización. Haga clic en **Agregar una etiqueta** y comience a escribir para filtrar la lista. Vuelva a hacer clic en el cuadro **Agregar una etiqueta** para seleccionar remitentes adicionales.

    - **Excepto si**: para agregar excepciones para la regla, haga clic en **Agregar una condición** tres veces para ver todas las excepciones disponibles. La configuración y el comportamiento se muestran exactamente igual que las condiciones.

8. Cuando haya terminado, haga clic en **Guardar**.

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>Usar el centro de seguridad & cumplimiento para ver las directivas de correo no deseado saliente

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la página **configuración contra correo no deseado** , haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) para expandir una directiva de correo no deseado saliente:

   - La directiva predeterminada denominada **Directiva de filtro de correo no deseado saliente**.

   - Una directiva personalizada creada donde el valor de la columna **tipo** es Directiva de **correo no deseado saliente personalizada**.

3. La configuración de la Directiva se muestra en los detalles de la Directiva ampliada que aparecen, o bien puede hacer clic en **Editar Directiva**.

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>Usar el centro de seguridad & cumplimiento para modificar las directivas de correo no deseado saliente

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la página **configuración contra correo no deseado** , haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) para expandir una directiva de correo no deseado saliente:

   - La directiva predeterminada denominada **Directiva de filtro de correo no deseado saliente**.

   - Una directiva personalizada creada donde el valor de la columna **tipo** es Directiva de **correo no deseado saliente personalizada**.

3. Haga clic en **Editar directiva**.

Para directivas de correo no deseado personalizadas personalizadas, la configuración disponible en el control flotante que aparece es idéntica a la descrita en el [centro de seguridad & cumplimiento para crear directivas de correo no deseado saliente](#use-the-security--compliance-center-to-create-outbound-spam-policies) .

Para la Directiva de correo no deseado saliente predeterminada denominada **Directiva de filtro de correo no deseado saliente**, la sección **aplicado a** no está disponible (la Directiva se aplica a todos los usuarios) y no puede cambiar el nombre de la Directiva.

Vea las secciones siguientes para habilitar o deshabilitar una directiva, establecer el orden de prioridad de la directiva o configurar las notificaciones en cuarentena para el usuario final.

### <a name="enable-or-disable-outbound-spam-policies"></a>Habilitar o deshabilitar las directivas de correo no deseado saliente

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la página **configuración contra correo no deseado** , haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) para expandir una directiva personalizada que haya creado (el valor en la columna **tipo** es **Directiva de correo no deseado saliente personalizada**).

3. En los detalles de la directiva expandida que aparecen, observe el valor de la columna **Habilitada**.

   Mueva el botón de alternancia a la izquierda para deshabilitar la directiva: ![Deshabilitar](../../media/scc-toggle-off.png)

   Mueva el botón de alternancia a la derecha para habilitar la directiva: ![Habilitar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

No se puede deshabilitar la Directiva de correo no deseado saliente predeterminada.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>Establecer la prioridad de las directivas de correo no deseado saliente personalizadas

De forma predeterminada, las directivas de correo no deseado saliente tienen una prioridad que se basa en el orden en que se crearon (las nuevas directivas tienen una prioridad más baja que las directivas anteriores). Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor). Ninguna de las dos directivas puede tener la misma prioridad y el procesamiento de directivas se detiene después de aplicar la primera Directiva.

Las directivas de correo no deseado de salida personalizadas se muestran en el orden en que se procesan (la primera Directiva tiene el valor de **prioridad** 0). La Directiva de correo no deseado saliente predeterminada denominada **Directiva de filtro de correo no deseado saliente** tiene el valor de prioridad **más bajo**y no se puede cambiar.

Para cambiar la prioridad de una directiva, suba o baje la directiva en la lista (no puede modificar directamente el número de **Prioridad** en el Centro de seguridad y cumplimiento).

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la página **configuración contra correo no deseado** , busque las directivas en las que el valor de la columna **tipo** es **Directiva de correo no deseado saliente personalizada**. Observe los valores de la columna **Prioridad**:

   - La directiva personalizada de correo no deseado saliente con la prioridad más alta tiene el ![ icono de flecha abajo de valor ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.

   - La directiva personalizada de correo no deseado saliente con la prioridad más baja tiene el ![ icono de flecha arriba de valor ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (por ejemplo, ![ icono de flecha arriba ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).

   - Si tiene tres o más directivas de correo no deseado saliente personalizadas, las directivas entre la prioridad más alta y la más baja tienen ![ un ](../../media/ITPro-EAC-UpArrowIcon.png)![ icono de flecha abajo hacia arriba ](../../media/ITPro-EAC-DownArrowIcon.png) (por ejemplo, **icono flecha** arriba en el icono ![ de ](../../media/ITPro-EAC-UpArrowIcon.png)![ flecha arriba ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).

3. Haga clic en ![Icono flecha arriba](../../media/ITPro-EAC-UpArrowIcon.png) o ![Icono flecha abajo](../../media/ITPro-EAC-DownArrowIcon.png) para mover la Directiva de correo no deseado saliente personalizada hacia arriba o hacia abajo en la lista de prioridades.

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>Usar el centro de seguridad & cumplimiento para eliminar directivas de correo no deseado saliente

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la página **configuración contra correo no deseado** , haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) para expandir la directiva personalizada que desea eliminar (la columna **tipo** es **Directiva de correo no deseado saliente personalizada**).

3. En los detalles de la directiva expandida que aparecen, haga clic en **Eliminar directiva**.

4. Haga clic en **Sí** en el mensaje de advertencia que se muestra.

No puede quitar la directiva predeterminada.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Usar Exchange Online PowerShell o PowerShell independiente de EOP para configurar las directivas de correo no deseado saliente

### <a name="use-powershell-to-create-outbound-spam-policies"></a>Usar PowerShell para crear directivas de correo no deseado saliente

La creación de una directiva de correo no deseado saliente en PowerShell es un proceso de dos pasos:

1. Crear la Directiva de filtro de correo no deseado saliente.

2. Cree la regla de filtro de correo no deseado saliente que especifica la Directiva de filtro de correo no deseado saliente a la que se aplica la regla.

 **Notas**:

- Puede crear una nueva regla de filtro de correo no deseado saliente y asignar una directiva de filtro de correo no deseado saliente existente que no esté asociada. Una regla de filtro de correo no deseado saliente no se puede asociar con más de una directiva de filtro de correo no deseado saliente.

- Puede configurar las siguientes opciones en nuevas directivas de filtro de correo no deseado saliente en PowerShell que no están disponibles en el centro de seguridad & cumplimiento hasta que se crea la Directiva:

  - Cree la nueva directiva como deshabilitada (_habilitada_ `$false` en el cmdlet **New-HostedOutboundSpamFilterRule** ).

  - Establezca la prioridad de la Directiva durante la creación (_prioridad_ _\<Number\>_ ) en el cmdlet **New-HostedOutboundSpamFilterRule** ).

- Una nueva Directiva de filtro de correo no deseado saliente que se crea en PowerShell no es visible en el centro de seguridad & cumplimiento hasta que se asigna la Directiva a una regla de filtro de correo no deseado.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Paso 1: usar PowerShell para crear una directiva de filtro de correo no deseado saliente

Para crear una directiva de filtro de correo no deseado saliente, use esta sintaxis:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

En este ejemplo se crea una nueva Directiva de filtro de correo no deseado saliente denominada ejecutivos de Contoso con la siguiente configuración:

- Los límites de frecuencia de destinatarios están restringidos a valores más bajos que los valores predeterminados. Para obtener más información, consulte [límites de envío en las opciones de Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).

- Una vez que se alcanza uno de los límites, se impide el envío de mensajes al usuario.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Paso 2: usar PowerShell para crear una regla de filtro de correo no deseado saliente

Para crear una regla de filtro de correo no deseado saliente, use esta sintaxis:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

En este ejemplo se crea una nueva regla de filtro de correo no deseado saliente denominada ejecutivos de Contoso con esta configuración:

- La Directiva de filtro de correo no deseado saliente denominada ejecutivos de Contoso está asociada a la regla.

- La regla se aplica a los miembros del grupo denominado Contoso Executives Group.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>Usar PowerShell para ver las directivas de filtro de correo no deseado saliente

Para obtener una lista resumida de todas las directivas de filtro de correo no deseado salientes, ejecute este comando:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Para obtener información detallada sobre una directiva de filtro de correo no deseado específica, use esta sintaxis:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

En este ejemplo se devuelven todos los valores de propiedad de la Directiva de filtro de correo no deseado saliente denominada Executives.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>Usar PowerShell para ver las reglas de filtro de correo no deseado saliente

Para ver las reglas de filtro de correo no deseado saliente existentes, use la siguiente sintaxis:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

Para obtener una lista resumida de todas las reglas de filtro de correo no deseado salientes, ejecute este comando:

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

Para obtener información detallada sobre una regla de filtrado de correo no deseado específica, use esta sintaxis:

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

En este ejemplo se devuelven todos los valores de propiedad de la regla de filtro de correo no deseado saliente denominada ejecutivos de contoso.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>Usar PowerShell para modificar las directivas de filtro de correo no deseado saliente

La misma configuración está disponible cuando modifica una directiva de filtro de malware en PowerShell como cuando crea la Directiva tal como se describe en la sección [paso 1: usar PowerShell para crear una directiva de filtro de correo no deseado saliente](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) anteriormente en este tema.

> [!NOTE]
> No se puede cambiar el nombre de una directiva de filtro de correo no deseado saliente (el cmdlet **set-HostedOutboundSpamFilterPolicy** no tiene ningún parámetro _Name_ ). Al cambiar el nombre de una directiva de correo no deseado saliente en el centro de seguridad & cumplimiento, sólo cambia el nombre de la _regla_de filtro de correo no deseado saliente.

Para modificar una directiva de filtro de correo no deseado saliente, use esta sintaxis:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>Usar PowerShell para modificar las reglas de filtro de correo no deseado saliente

El único valor que no está disponible cuando se modifica una regla de filtro de correo no deseado saliente en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada. Para habilitar o deshabilitar las reglas de filtro de correo no deseado saliente existentes, consulte la siguiente sección.

De lo contrario, no hay opciones de configuración adicionales disponibles cuando se modifica una regla de filtro de correo no deseado saliente en PowerShell. La misma configuración está disponible cuando se crea una regla tal y como se describe en la sección [paso 2: usar PowerShell para crear una regla de filtro de correo no deseado saliente](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) anteriormente en este tema.

Para modificar una regla de filtro de correo no deseado saliente, use esta sintaxis:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>Usar PowerShell para habilitar o deshabilitar reglas de filtro de correo no deseado saliente

La habilitación o deshabilitación de una regla de filtro de correo no deseado saliente en PowerShell habilita o deshabilita toda la Directiva de correo no deseado saliente (la regla de filtro de correo no deseado saliente y la Directiva de filtro de correo no deseado saliente asignada). No se puede habilitar o deshabilitar la Directiva de correo no deseado saliente predeterminada (siempre se aplica siempre a todos los destinatarios).

Para habilitar o deshabilitar una regla de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

En este ejemplo se deshabilita la regla de filtro de correo no deseado saliente denominada Marketing Department.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Este ejemplo habilita la misma regla.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) y [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>Usar PowerShell para establecer la prioridad de las reglas de filtro de correo no deseado saliente

El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo que se puede establecer depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.

Para establecer la prioridad de una regla de filtro de correo no deseado saliente en PowerShell, use la siguiente sintaxis:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-HostedOutboundSpamFilterRule** en su lugar.
>
> - La Directiva de filtro de correo no deseado predeterminado saliente no tiene una regla de filtro de correo no deseado correspondiente y siempre tiene el valor de prioridad no modificable **más bajo**.

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>Usar PowerShell para quitar las directivas de filtro de correo no deseado saliente

Cuando se usa PowerShell para quitar una directiva de filtro de correo no deseado saliente, no se quita la regla de filtro de correo no deseado saliente correspondiente.

Para quitar una directiva de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

En este ejemplo se quita la Directiva de filtro de correo no deseado saliente denominada Marketing Department.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>Usar PowerShell para quitar reglas de filtro de correo no deseado saliente

Cuando se usa PowerShell para quitar una regla de filtro de correo no deseado saliente, no se elimina la Directiva de filtro de correo no deseado saliente correspondiente.

Para quitar una regla de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

En este ejemplo se quita la regla de filtro de correo no deseado saliente denominada Marketing Department.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).

## <a name="for-more-information"></a>Más información

[Quitar usuarios bloqueados del portal de Usuarios restringidos](removing-user-from-restricted-users-portal-after-spam.md)

[Grupo de entrega de alto riesgo para mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md)

[Preguntas más frecuentes sobre la protección contra correo electrónico no deseado](anti-spam-protection-faq.md)

[Informe de mensajes reenviados automáticamente](mfi-auto-forwarded-messages-report.md)
