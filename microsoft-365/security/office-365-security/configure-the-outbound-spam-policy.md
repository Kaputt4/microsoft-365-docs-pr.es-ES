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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a ver, crear, modificar y eliminar directivas de correo no deseado salientes en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: aec3149a4a91e011c6d6d206d9fc10f36a3d6588
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903909"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>Configurar el filtrado de correo no deseado saliente en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

En las organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, los mensajes de correo electrónico salientes que se envían a través de EOP se comprueban automáticamente en busca de correo no deseado y actividad de envío inusual.

El correo no deseado saliente de un usuario de la organización suele indicar una cuenta comprometida. Los mensajes salientes sospechosos se marcan como correo no deseado (independientemente del nivel de confianza de correo no deseado o SCL) y se enruta a través del grupo de entrega de alto riesgo para ayudar a proteger la reputación del servicio (es decir, mantener los servidores de correo electrónico de origen de Microsoft 365 fuera de listas de direcciones IP bloqueados). [](high-risk-delivery-pool-for-outbound-messages.md) A los administradores se les notifica automáticamente sobre la actividad de correo electrónico saliente sospechosa y se bloquean los usuarios mediante directivas [de alerta.](../../compliance/alert-policies.md)

EOP usa directivas de correo no deseado salientes como parte de la defensa general de su organización contra el correo no deseado. Para obtener más información, consulte [Protección contra correo no deseado](anti-spam-protection.md).

Los administradores pueden ver, editar y configurar (pero no eliminar) la directiva de correo no deseado saliente predeterminada. Para mayor granularidad, también puede crear directivas de correo no deseado saliente personalizadas que se aplican a usuarios, grupos o dominios específicos de la organización. Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.

Puede configurar directivas de correo no deseado salientes en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell EOP independiente para organizaciones sin buzones de Exchange Online).

Los elementos básicos de una directiva de correo no deseado saliente en EOP son:

- **La directiva de filtro de correo no** deseado saliente: especifica las acciones para los veredictos de filtrado de correo no deseado saliente y las opciones de notificación.
- **La regla de filtro de correo** no deseado saliente: especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva) para una directiva de filtro de correo no deseado saliente.

La diferencia entre estos dos elementos no es obvia cuando se administran directivas de correo no deseado salientes en el Centro de seguridad & cumplimiento:

- Al crear una directiva, está creando una regla de filtro de correo no deseado saliente y la directiva de filtro de correo no deseado saliente asociada al mismo tiempo con el mismo nombre para ambos.
- Al modificar una directiva, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada, y los filtros de destinatarios modifican la regla de filtro de correo no deseado saliente. Todas las demás opciones modifican la directiva de filtro de correo no deseado saliente asociada.
- Al quitar una directiva, se quitan la regla de filtro de correo no deseado saliente y la directiva de filtro de correo no deseado saliente asociada.

En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado. Para obtener más información, vea la sección [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) más adelante en este artículo.

Cada organización tiene una directiva de correo no deseado de salida integrada denominada Default que tiene estas propiedades:

- La directiva se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla de filtro de correo no deseado saliente (filtros de destinatarios) asociada a la directiva.
- La directiva tiene un valor de prioridad personalizado **Mínimo** que no se puede modificar (la directiva siempre se aplica en último lugar). Las directivas personalizadas que cree siempre tendrán una prioridad mayor que la directiva denominada Predeterminada.
- La directiva es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar esta directiva predeterminada.

Para aumentar la eficacia del filtrado de correo no deseado saliente, puede crear directivas de correo no deseado saliente personalizadas con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página **Configuración contra correo no deseado**, use <https://protection.office.com/antispam>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para agregar, modificar y eliminar directivas de correo no deseado salientes, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.
  - Para obtener acceso de solo lectura a las directivas de correo no deseado saliente, debe ser miembro de los grupos de roles **Lector global** o **Lector de** seguridad.

  Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para obtener la configuración recomendada para las directivas de correo no deseado saliente, vea [Configuración de la directiva de filtro de correo no deseado saliente de EOP](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).

- Se [](../../compliance/alert-policies.md) superaron las directivas de alerta predeterminadas denominadas  Límite de envío de correo **electrónico,** patrones de envío de correo electrónico sospechosos **detectados** y Usuarios restringidos para enviar correo electrónico ya enviar notificaciones por correo electrónico a los miembros del grupo **TenantAdmins** ( Administradores globales ) sobre la actividad de correo electrónico saliente inusual y los usuarios **bloqueados** debido al correo no deseado saliente. Para obtener más información, vea [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Se recomienda usar estas directivas de alerta en lugar de las opciones de notificación en las directivas de correo no deseado saliente.

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>Usar el Centro de seguridad & cumplimiento para crear directivas de correo no deseado saliente

La creación de una directiva de correo no deseado saliente personalizada en el Centro de seguridad y cumplimiento de & crea la regla de filtro de correo no deseado y la directiva de filtro de correo no deseado asociada al mismo tiempo con el mismo nombre para ambos.

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la **página Configuración contra correo** no deseado, haga clic en Crear una directiva de **salida.**

3. En la **directiva de filtro de correo no** deseado saliente que se abre, configure las siguientes opciones:

   - **Nombre**: escriba un nombre único y descriptivo para la directiva.

   - **Descripción**: escriba una descripción opcional para la directiva.

4. (Opcional) Expanda la **sección Notificaciones para** configurar usuarios adicionales que deben recibir copias y notificaciones de mensajes de correo electrónico saliente sospechosos:

   - **Enviar una copia de mensajes de** correo electrónico saliente sospechosos a personas específicas: esta configuración agrega los usuarios especificados como destinatarios CCO a los mensajes salientes sospechosos.

     > [!NOTE]
     > Esta configuración solo funciona en la directiva de correo no deseado saliente predeterminada. No funciona en las directivas de correo no deseado saliente personalizadas que cree.

     Para habilitar esta configuración:

     1. Active la casilla para habilitar la configuración.

     1. Haga clic **en Agregar personas**. En el **menú desplegable Agregar o quitar** destinatarios que aparece:

     1. Escriba la dirección de correo electrónico del remitente. Puede especificar varias direcciones de correo electrónico separadas por punto y coma (;) o un destinatario por línea.

     1. Haga clic en ![Icono Agregar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) para agregar los destinatarios.

        Repita estos pasos tantas veces como sea necesario.

        Los destinatarios que agregó aparecen en la sección **Lista de destinatarios** en el menú desplegable. Para eliminar un destinatario, haga clic ![ en El botón Quitar ](../../media/scc-remove-icon.png) .

     1. Cuando haya terminado, haga clic en **Guardar**.

        Para deshabilitar esta configuración, desactive la casilla.

   - **Notificar a personas específicas si un remitente está bloqueado debido al envío de correo no deseado saliente:**

     > [!IMPORTANT]
     >
     > - Esta configuración está en proceso de desuso de las directivas de correo no deseado saliente.
     >
     > - La [](../../compliance/alert-policies.md) directiva de  alerta predeterminada denominada Usuario restringido para enviar correo electrónico ya envía notificaciones por correo electrónico a los miembros del grupo **TenantAdmins** ( Administradores globales ) cuando los usuarios se bloquean debido a que superan los límites de la sección **Límites** de destinatarios.  **Se recomienda encarecidamente que use la** directiva de alertas en lugar de esta configuración en la directiva de correo no deseado saliente para notificar a los administradores y otros usuarios . Para obtener instrucciones, consulte [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).

5. (Opcional) Expanda la **sección Límites de** destinatarios para configurar los límites y acciones de los mensajes de correo electrónico saliente sospechosos:

   > [!NOTE]
   > Esta configuración solo se aplica a los buzones basados en la nube.

   - **Número máximo de destinatarios por usuario**

     Un valor válido es de 0 a 10000. El valor predeterminado es 0, lo que significa que se usan los valores predeterminados del servicio. Para obtener más información, vea [Límites de envío](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

     - **Límite por hora externo:** el número máximo de destinatarios externos por hora.

     - **Límite por hora interno:** el número máximo de destinatarios internos por hora.

     - **Límite diario:** el número total máximo de destinatarios por día.

   - **Acción cuando un usuario supera los límites** anteriores: Configure la acción que debe realizarse cuando se supere **alguno** de los límites de destinatarios. Para todas las acciones, los  destinatarios especificados en la directiva de alerta de correo electrónico restringido por el usuario (y en la ahora redundante Notificar a personas específicas si un remitente está bloqueado debido **al** envío de correo no deseado saliente en la directiva de correo no deseado saliente reciben notificaciones de correo electrónico.

     - **Restringir al usuario el envío de correo hasta el día siguiente:** este es el valor predeterminado. Se envían notificaciones por correo electrónico y el usuario no podrá enviar más mensajes hasta el día siguiente, en función de la hora UTC. No hay forma de que el administrador invalide este bloque.

       - La alerta de actividad denominada **Usuario restringido para enviar correo** electrónico notifica a los administradores (por correo electrónico y en la página Ver **alertas).**

       - También se notificará a los destinatarios especificados en la configuración Notificar a personas específicas si un remitente está bloqueado debido al envío de **correo** no deseado saliente en la directiva.

       - El usuario no podrá enviar más mensajes hasta el día siguiente, según la hora UTC. No hay forma de que el administrador invalide este bloque.

     - **Restringir** al usuario el envío de correo: se envían notificaciones de correo electrónico, el usuario se agrega al portal **[Usuarios restringidos] <https://sip.protection.office.com/restrictedusers>** en el Centro de seguridad & Cumplimiento y el usuario no puede enviar correo electrónico hasta que un administrador no las quite del **portal** de usuarios restringidos. Después de que un administrador quite el usuario de la lista, no se restringirá de nuevo para ese día. Para obtener instrucciones, consulte [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).

     - **Sin acción, solo alerta:** se envían notificaciones por correo electrónico.

6. (Opcional) Expanda **Sección Reenvío automático para** controlar el reenvío automático de correo electrónico por parte de los usuarios a remitentes externos. Para obtener más información, consulte [Controlar el reenvío automático de correo electrónico externo en Microsoft 365](external-email-forwarding.md).

   > [!NOTE]
   >
   > - Antes de septiembre de 2020, esta configuración está disponible pero no se aplica.
   >
   > - Esta configuración solo se aplica a los buzones basados en la nube.
   >
   > - Cuando se deshabilita el reenvío automático, el destinatario recibirá un informe de no entrega (también conocido como NDR o mensaje de desenviamiento) si los remitentes externos envían correo electrónico a un buzón que tiene el reenvío en su lugar. Si un remitente interno envía  el mensaje y el método de reenvío es el reenvío de buzones [(también](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) conocido como reenvío _SMTP),_ el remitente interno recibirá el NDR. El remitente interno no obtiene un NDR si el reenvío se produjo debido a una regla de bandeja de entrada.

   Los valores disponibles son los siguientes:

   - **Automático: controlado por el sistema:** permite el filtrado de correo no deseado saliente para controlar el reenvío automático de correo electrónico externo. Este es el valor predeterminado.
   - **On**: La directiva no deshabilita el reenvío automático de correo electrónico externo.
   - **Desactivado:** la directiva deshabilita todo el reenvío automático de correo electrónico externo.

7. (Obligatorio) Expanda la **sección Aplicado a** para identificar los remitentes internos a los que se aplica la directiva.

    Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<sender1\>_ o _\<sender2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<sender1\>_ y _\<member of group 1\>_).

    Es más fácil hacer clic en **Agregar una condición** tres veces para ver todas las condiciones disponibles. Puede hacer clic en el ![botón Quitar](../../media/scc-remove-icon.png) para quitar condiciones que no quiera configurar.

    - **El dominio del remitente es**: especifica remitentes en uno o varios de los dominios aceptados configurados en la organización. Haga clic en el cuadro **Agregar una etiqueta** para ver y seleccionar un dominio. Haga clic de nuevo en el cuadro **Agregar una etiqueta** para seleccionar dominios adicionales si hay más de un dominio disponible.

    - **Sender es**: especifica uno o varios usuarios de la organización. Haga clic en **Agregar una etiqueta** y comience a escribir para filtrar la lista. Haga clic de nuevo **en el cuadro Agregar una etiqueta** para seleccionar remitentes adicionales.

    - **El remitente es miembro de**: Especifica uno o más grupos de la organización. Haga clic en **Agregar una etiqueta** y comience a escribir para filtrar la lista. Haga clic de nuevo **en el cuadro Agregar una etiqueta** para seleccionar remitentes adicionales.

    - **Excepto si**: para agregar excepciones para la regla, haga clic en **Agregar una condición** tres veces para ver todas las excepciones disponibles. La configuración y el comportamiento se muestran exactamente igual que las condiciones.

8. Cuando haya terminado, haga clic en **Guardar**.

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>Usar el Centro de seguridad & cumplimiento para ver directivas de correo no deseado saliente

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la **página Configuración contra correo** no deseado, haga clic en Expandir icono para expandir una directiva de correo no deseado ![ ](../../media/scc-expand-icon.png) saliente:

   - La directiva predeterminada denominada **Directiva de filtro de correo no deseado saliente**.

   - Una directiva personalizada que creó donde el valor de la columna **Tipo** es **Directiva de correo no deseado de salida personalizada.**

3. La configuración de directiva se muestra en los detalles de directiva expandido que aparecen o puede hacer clic en **Editar directiva**.

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>Usar el Centro de seguridad & cumplimiento para modificar directivas de correo no deseado saliente

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la **página Configuración contra correo** no deseado, haga clic en Expandir icono para expandir una directiva de correo no deseado ![ ](../../media/scc-expand-icon.png) saliente:

   - La directiva predeterminada denominada **Directiva de filtro de correo no deseado saliente**.

   - Una directiva personalizada que creó donde el valor de la columna **Tipo** es **Directiva de correo no deseado de salida personalizada.**

3. Haga clic en **Editar directiva**.

Para las directivas de correo no deseado saliente personalizadas, la configuración disponible en el control desplegable que aparece es idéntica a la descrita en la sección Usar el Centro de seguridad [& cumplimiento](#use-the-security--compliance-center-to-create-outbound-spam-policies) para crear directivas de correo no deseado salientes.

Para la directiva de correo no deseado  saliente predeterminada denominada Directiva de filtro de **correo** no deseado saliente, la sección Aplicado a no está disponible (la directiva se aplica a todos) y no se puede cambiar el nombre de la directiva.

Vea las secciones siguientes para habilitar o deshabilitar una directiva, establecer el orden de prioridad de la directiva o configurar las notificaciones en cuarentena para el usuario final.

### <a name="enable-or-disable-outbound-spam-policies"></a>Habilitar o deshabilitar directivas de correo no deseado salientes

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la **página Configuración contra correo** no deseado, haga clic en Expandir icono para expandir una directiva personalizada que haya creado (el valor de la columna Tipo es Directiva de correo no deseado de salida ![ ](../../media/scc-expand-icon.png) **personalizada).** 

3. En los detalles de la directiva expandida que aparecen, observe el valor de la columna **Habilitada**.

   Mueva el botón de alternancia a la izquierda para deshabilitar la directiva: ![Deshabilitar](../../media/scc-toggle-off.png)

   Mueva el botón de alternancia a la derecha para habilitar la directiva: ![Habilitar](../../media/scc-toggle-on.png)

No puede deshabilitar la directiva de correo no deseado saliente predeterminada.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>Establecer la prioridad de las directivas de correo no deseado saliente personalizadas

De forma predeterminada, las directivas de correo no deseado saliente tienen una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen una prioridad menor que las directivas anteriores). Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor). Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

Las directivas de correo no deseado saliente personalizadas se muestran en el orden en que se procesan (la primera directiva tiene el **valor de** prioridad 0). La directiva de correo no deseado saliente predeterminada denominada Directiva de filtro de **correo** no deseado saliente tiene el valor de prioridad **Lowest** y no se puede cambiar.

Para cambiar la prioridad de una directiva, suba o baje la directiva en la lista (no puede modificar directamente el número de **Prioridad** en el Centro de seguridad y cumplimiento).

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la **página Configuración contra correo** no deseado,  busque las directivas donde el valor de la columna Tipo es Directiva de correo no deseado de **salida personalizada.** Observe los valores de la columna **Prioridad**:

   - La directiva de correo no deseado saliente personalizada con la prioridad más alta tiene el valor ![ Flecha abajo icono ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.

   - La directiva de correo no deseado saliente personalizada con la prioridad más baja tiene el valor Flecha arriba ![ icono ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (por ejemplo, ![ icono flecha arriba ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).

   - Si tiene tres o más directivas de correo no deseado saliente personalizadas, las directivas entre la prioridad más alta y la más baja tienen valores Icono flecha arriba icono flecha ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ abajo ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (por ejemplo, icono flecha arriba icono flecha abajo ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ icono ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).

3. Haga clic en ![Icono flecha arriba](../../media/ITPro-EAC-UpArrowIcon.png) o ![Icono flecha abajo](../../media/ITPro-EAC-DownArrowIcon.png) para mover la directiva de correo no deseado saliente personalizada hacia arriba o hacia abajo en la lista de prioridad.

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>Usar el Centro de seguridad & cumplimiento para quitar directivas de correo no deseado saliente

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Directiva** \> **Correo no deseado**.

2. En la **página Configuración contra correo** no deseado, haga clic en Expandir icono para expandir la directiva personalizada que desea eliminar (la columna Tipo es Directiva de correo no deseado de salida ![ ](../../media/scc-expand-icon.png) **personalizada).** 

3. En los detalles de la directiva expandida que aparecen, haga clic en **Eliminar directiva**.

4. Haga clic en **Sí** en el mensaje de advertencia que se muestra.

No puede quitar la directiva predeterminada.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Usar PowerShell de Exchange Online o PowerShell de EOP independiente para configurar directivas de correo no deseado saliente

Como se describió anteriormente, una directiva de correo no deseado saliente consta de una directiva de filtro de correo no deseado saliente y una regla de filtro de correo no deseado saliente.

En PowerShell de Exchange Online o en PowerShell de EOP independiente, la diferencia entre las directivas de filtro de correo no deseado saliente y las reglas de filtro de correo no deseado saliente es aparente. Las directivas de filtro de correo no deseado saliente se administran mediante los cmdlets **\* -HostedOutboundSpamFilterPolicy** y se administran las reglas de filtro de correo no deseado saliente mediante los cmdlets **\* -HostedOutboundSpamFilterRule.**

- En PowerShell, primero se crea la directiva de filtro de correo no deseado saliente y, a continuación, se crea la regla de filtro de correo no deseado saliente que identifica la directiva a la que se aplica la regla.
- En PowerShell, modifica la configuración de la directiva de filtro de correo no deseado saliente y la regla de filtro de correo no deseado saliente por separado.
- Al quitar una directiva de filtro de correo no deseado saliente de PowerShell, la regla de filtro de correo no deseado saliente correspondiente no se quita automáticamente y viceversa.

### <a name="use-powershell-to-create-outbound-spam-policies"></a>Usar PowerShell para crear directivas de correo no deseado saliente

Crear una directiva de correo no deseado saliente en PowerShell es un proceso de dos pasos:

1. Cree la directiva de filtro de correo no deseado saliente.
2. Cree la regla de filtro de correo no deseado saliente que especifique la directiva de filtro de correo no deseado saliente a la que se aplica la regla.

 **Notas**:

- Puede crear una nueva regla de filtro de correo no deseado saliente y asignarle una directiva de filtro de correo no deseado saliente existente y sin asociar. Una regla de filtro de correo no deseado saliente no se puede asociar a más de una directiva de filtro de correo no deseado saliente.

- Puede configurar las siguientes opciones en las nuevas directivas de filtro de correo no deseado saliente en PowerShell que no están disponibles en el Centro de seguridad y cumplimiento de & hasta después de crear la directiva:

  - Cree la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-HostedOutboundSpamFilterRule).**
  - Establezca la prioridad de la directiva durante la creación (_Prioridad_ ) en _\<Number\>_ el cmdlet **New-HostedOutboundSpamFilterRule).**

- Una nueva directiva de filtro de correo no deseado saliente que cree en PowerShell no está visible en el Centro de seguridad y cumplimiento de & hasta que asigne la directiva a una regla de filtro de correo no deseado.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Paso 1: Usar PowerShell para crear una directiva de filtro de correo no deseado saliente

Para crear una directiva de filtro de correo no deseado saliente, use esta sintaxis:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

En este ejemplo se crea una nueva directiva de filtro de correo no deseado saliente denominada Ejecutivos de Contoso con la siguiente configuración:

- Los límites de velocidad de destinatarios están restringidos a valores más pequeños que los valores predeterminados. Para obtener más información, vea [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).

- Una vez alcanzado uno de los límites, se impide que el usuario envíe mensajes.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Paso 2: Usar PowerShell para crear una regla de filtro de correo no deseado saliente

Para crear una regla de filtro de correo no deseado saliente, use esta sintaxis:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

En este ejemplo se crea una nueva regla de filtro de correo no deseado saliente denominada Ejecutivos de Contoso con esta configuración:

- La directiva de filtro de correo no deseado saliente denominada Ejecutivos de Contoso está asociada a la regla.
- La regla se aplica a los miembros del grupo denominado Contoso Executives Group.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>Usar PowerShell para ver directivas de filtro de correo no deseado saliente

Para devolver una lista resumida de todas las directivas de filtro de correo no deseado saliente, ejecute este comando:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Para devolver información detallada sobre una directiva de filtro de correo no deseado saliente específica, use la sintaxis siguiente:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

En este ejemplo se devuelven todos los valores de propiedad de la directiva de filtro de correo no deseado saliente denominada Ejecutivos.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>Usar PowerShell para ver reglas de filtro de correo no deseado saliente

Para ver las reglas de filtro de correo no deseado saliente existentes, use la siguiente sintaxis:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

Para devolver una lista resumida de todas las reglas de filtro de correo no deseado saliente, ejecute este comando:

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

En este ejemplo se devuelven todos los valores de propiedad de la regla de filtro de correo no deseado saliente denominada Ejecutivos de Contoso.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>Usar PowerShell para modificar directivas de filtro de correo no deseado saliente

La misma configuración está disponible cuando se modifica una directiva de filtro de malware en PowerShell que cuando se crea la directiva como se describe en el paso [1:](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) Usar PowerShell para crear una directiva de filtro de correo no deseado saliente anteriormente en este artículo.

> [!NOTE]
> No puede cambiar el nombre de una directiva de filtro de correo no deseado saliente (el cmdlet **Set-HostedOutboundSpamFilterPolicy** no tiene ningún _parámetro Name)._ Al cambiar el nombre de una directiva de correo no deseado saliente en el Centro de seguridad & cumplimiento, solo se cambia el nombre de la regla de filtro de correo no _deseado saliente._

Para modificar una directiva de filtro de correo no deseado saliente, use esta sintaxis:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>Usar PowerShell para modificar reglas de filtro de correo no deseado saliente

La única configuración que no está disponible al modificar una regla de filtro de correo no deseado saliente en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada. Para habilitar o deshabilitar las reglas de filtro de correo no deseado saliente existentes, consulte la siguiente sección.

De lo contrario, no hay ninguna configuración adicional disponible al modificar una regla de filtro de correo no deseado saliente en PowerShell. La misma configuración está disponible al crear una regla tal como se describe en el paso [2: Usar PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) para crear una regla de filtro de correo no deseado saliente anteriormente en este artículo.

Para modificar una regla de filtro de correo no deseado saliente, use esta sintaxis:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>Usar PowerShell para habilitar o deshabilitar reglas de filtro de correo no deseado saliente

Habilitar o deshabilitar una regla de filtro de correo no deseado saliente en PowerShell habilita o deshabilita toda la directiva de correo no deseado saliente (la regla de filtro de correo no deseado saliente y la directiva de filtro de correo no deseado saliente asignada). No puede habilitar ni deshabilitar la directiva de correo no deseado saliente predeterminada (siempre se aplica a todos los destinatarios).

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
> - La directiva de filtro de correo no deseado predeterminada saliente no tiene una regla de filtro de correo no deseado correspondiente y siempre tiene el valor de prioridad no modificable **Lowest**.

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>Usar PowerShell para quitar directivas de filtro de correo no deseado saliente

Cuando usa PowerShell para quitar una directiva de filtro de correo no deseado saliente, no se quita la regla de filtro de correo no deseado saliente correspondiente.

Para quitar una directiva de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

En este ejemplo se quita la directiva de filtro de correo no deseado saliente denominada Departamento de marketing.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>Usar PowerShell para quitar reglas de filtro de correo no deseado saliente

Cuando usa PowerShell para quitar una regla de filtro de correo no deseado saliente, no se quita la directiva de filtro de correo no deseado saliente correspondiente.

Para quitar una regla de filtro de correo no deseado saliente en PowerShell, use esta sintaxis:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

En este ejemplo se quita la regla de filtro de correo no deseado saliente denominada Departamento de marketing.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).

## <a name="for-more-information"></a>Más información

[Quitar usuarios bloqueados del portal de Usuarios restringidos](removing-user-from-restricted-users-portal-after-spam.md)

[Grupo de entrega de alto riesgo para mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md)

[Preguntas más frecuentes sobre la protección contra correo electrónico no deseado](anti-spam-protection-faq.md)

[Informe de mensajes reenviados automáticamente](mfi-auto-forwarded-messages-report.md)