---
title: Configurar directivas de vínculos seguros en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Los administradores pueden aprender a ver, crear, modificar y eliminar directivas de vínculos seguros y la configuración global de vínculos seguros en Microsoft Defender para Office 365.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: ac2c6a2fb5ca151ba50176ae9faf06ec7b8cd0ab
ms.sourcegitcommit: 651610ca73bfd1d008d97311b59782790df664fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2022
ms.locfileid: "67611331"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Configurar directivas de vínculos seguros en Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](defender-for-office-365.md). Si es un usuario principal que busca información sobre Safelinks en Outlook, consulte [Seguridad avanzada de Outlook.com](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Vínculos seguros en [Microsoft Defender para Office 365](defender-for-office-365.md) proporciona el examen de direcciones URL de los mensajes de correo electrónico entrantes en el flujo de correo y la comprobación de la hora del clic de las direcciones URL y los vínculos en los mensajes de correo electrónico y en otras ubicaciones. Para obtener más información, vea [Vínculos seguros en Microsoft Defender para Office 365](safe-links.md).

Aunque no hay ninguna directiva de vínculos seguros predeterminada, la directiva de seguridad preestablecida **de protección integrada** proporciona protección de vínculos seguros a todos los destinatarios (usuarios que no están definidos en las directivas de seguridad preestablecidas estándar o estricta o en directivas de vínculos seguros personalizadas). Para obtener más información, vea [Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md).

También puede usar los procedimientos de este artículo para crear directivas de vínculos seguros que se apliquen a usuarios, grupos o dominios específicos.

> [!NOTE]
>
> Configure la lista "Bloquear las siguientes direcciones URL" en la configuración global para la protección de vínculos seguros **fuera** de las directivas de vínculos seguros. Para obtener instrucciones, consulte [Configuración global de vínculos seguros en Microsoft Defender para Office 365](configure-global-settings-for-safe-links.md).
>
> Los administradores deben tener en cuenta las distintas opciones de configuración de Vínculos seguros. Una de las opciones disponibles es incluir información de identificación del usuario en Vínculos seguros. Esta característica permite a los equipos de operaciones de seguridad (SecOps) investigar posibles riesgos de usuario, tomar medidas correctivas y limitar infracciones costosas.

Puede configurar directivas de vínculos seguros contra correo no deseado en el portal de Microsoft 365 Defender o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; EOP PowerShell independiente para organizaciones sin buzones de Exchange Online, pero con suscripciones a completos de Microsoft Defender for Office 365).

Los elementos básicos de una directiva de Vínculos seguros son:

- **La directiva de vínculos seguros**: active la protección de vínculos seguros, active el examen de direcciones URL en tiempo real, especifique si se debe esperar a que se complete el examen en tiempo real antes de entregar el mensaje, activar el examen de mensajes internos, especificar si se debe realizar un seguimiento de los clics del usuario en las direcciones URL y especificar si se permite a los usuarios hacer clic en la dirección URL original.
- **Regla de vínculos seguros**: especifica la prioridad y los filtros de destinatario (a quién se aplica la directiva).

La diferencia entre estos dos elementos no es obvia al administrar directivas de vínculos seguros en el portal de Microsoft 365 Defender:

- Cuando crea una directiva de Vínculos seguros, en realidad, está creando una regla de Vínculos seguros y, al mismo tiempo, la directiva de Vínculos seguros asociada a esta, con el mismo nombre para ambas.
- Al modificar una directiva de Vínculos Seguros, las opciones de configuración relacionadas con el nombre, la prioridad, la activación o desactivación y los filtros de destinatarios modifican la regla de filtro de Vínculos seguros. Todas las demás opciones modifican la directiva de Vínculos Seguros asociada.
- Al quitar una directiva de Vínculos seguros, se quitan la regla de Vínculos seguros y la directiva de Vínculos seguros asociada.

En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado. Para obtener más información, consulte la sección [Uso Exchange Online PowerShell o EOP independiente de PowerShell para configurar directivas de vínculos seguros](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) más adelante en este artículo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Vínculos seguros** , use <https://security.microsoft.com/safelinksv2>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener asignados permisos para poder realizar los procedimientos de este artículo:
  - Para crear, modificar y eliminar directivas de vínculos seguros, debe ser miembro de los grupos de roles Administración de la **organización** o **Administrador de seguridad** en el portal de Microsoft 365 Defender **y** miembro del grupo de roles Administración de la **organización** en Exchange Online.
  - Para el acceso de solo lectura a las directivas de vínculos seguros, debe ser miembro de los grupos de roles **Lector global** o **Lector de seguridad** .

  Para obtener más información, vea [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md) y [Permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el portal de Microsoft 365 Defender _y_ permisos para otras características de Microsoft 365. Para más información, consulte[Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  . - El grupo **de roles View-Only Organization Management** de [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para ver nuestra configuración recomendada para las directivas de vínculos seguros, consulte [Configuración de directivas de vínculos seguros](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).

- Espere hasta 6 horas para que se aplique una directiva nueva o actualizada.

- [Las nuevas características se agregan continuamente a Microsoft Defender para Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365). A medida que se agregan nuevas características, es posible que tenga que realizar ajustes en las directivas de vínculos seguros existentes.

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a>Uso del portal de Microsoft 365 Defender para crear directivas de vínculos seguros

La creación de una directiva de vínculos seguros personalizada en el portal de Microsoft 365 Defender crea la regla de vínculos seguros y la directiva de vínculos seguros asociada al mismo tiempo con el mismo nombre para ambos.

1. En el portal de Microsoft 365 Defender de <https://security.microsoft.com>, vaya a Email & Directivas de **colaboración** \> **& Reglas** \> **Vínculos seguros** de **directivas** \> de amenazas en la sección **Directivas**. Para ir directamente a la página **Vínculos seguros** , use <https://security.microsoft.com/safelinksv2>.

2. En la página **Vínculos seguros** , haga clic en el ![icono Crear.](../../media/m365-cc-sc-create-icon.png) **Create**.

3. Se abre el Asistente para **Nueva directiva de Vínculos seguros**. En la página **Nombre de la directiva** , configure los siguientes valores:

   - **Nombre**: escriba un nombre único y descriptivo para la directiva.
   - **Descripción**: escriba una descripción opcional para la directiva.

   Cuando termine, haga clic en **Siguiente**.

4. En la página **Usuarios y dominios** que aparece, identifique los destinatarios internos a los que se aplica la directiva (condiciones de destinatario):
   - **Usuarios**: los buzones de correo, los usuarios de correo o los contactos de correo especificados.
   - **Grupos**:
     - Miembros de los grupos de distribución o grupos de seguridad habilitados para correo especificados.
     - Los Grupos de Microsoft 365 especificados.
   - **Dominios**: todos los destinatarios de los [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados en la organización.

   Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados. Repita este proceso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

   Para los usuarios o grupos, puede utilizar la mayoría de los identificadores (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de la cuenta, etc.), pero el nombre para mostrar correspondiente se muestra en los resultados. Para los usuarios, introduzca un asterisco (\*) por sí mismo para ver todos los valores disponibles.

   Varios valores en la misma condición usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Hay diferentes condiciones que usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

   - **Excluir estos usuarios, grupos y dominios**: para agregar excepciones para los destinatarios internos a los que se aplica la directiva (excepciones de destinatarios), seleccione esta opción y configure las excepciones. La configuración y el comportamiento son exactamente iguales a las condiciones.

   > [!IMPORTANT]
   > Los diferentes tipos de condiciones o excepciones no son aditivos; son inclusivos. La directiva se aplica _solo_ a los destinatarios que coinciden con _todos_ los filtros de destinatarios especificados. Por ejemplo, se configura una condición de filtro de destinatario en la directiva con los siguientes valores:
   >
   > - Usuarios: romain@contoso.com
   > - Grupos: Ejecutivos
   >
   > La directiva se aplica a romain@contoso.com _solo_ si también es miembro del grupo de Ejecutivos. Si no es miembro del grupo, la directiva no se le aplica.
   >
   > Asimismo, si utiliza el mismo filtro de destinatarios como excepción a la directiva, esta no se aplica a romain@contoso.com _solo_ si también es miembro del grupo de Ejecutivos. Si no es miembro del grupo, la directiva se le sigue aplicando.

   Cuando termine, haga clic en **Siguiente**.

5. En la **dirección URL & haga clic en la página configuración de protección** que aparece, configure las siguientes opciones:

   - **Acción en direcciones URL potencialmente malintencionadas en la sección Correos electrónicos** :
     - **Activado: Vínculos seguros comprueba una lista de vínculos malintencionados conocidos cuando los usuarios hacen clic en vínculos en el correo electrónico**: seleccione esta opción para activar la protección de vínculos seguros para los vínculos en los mensajes de correo electrónico. Si selecciona esta opción, están disponibles las opciones siguientes:
       - **Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización**: seleccione esta opción para aplicar la directiva Vínculos seguros a los mensajes entre remitentes internos y destinatarios internos.
       - **Aplicar el examen de direcciones URL en tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos**: seleccione esta opción para activar el examen en tiempo real de los vínculos en los mensajes de correo electrónico. Si selecciona esta opción, está disponible la siguiente configuración:
         - **Espere a que se complete el examen de direcciones URL antes de entregar el mensaje**: seleccione esta opción para esperar a que se complete el examen de direcciones URL en tiempo real antes de entregar el mensaje.
       - **No vuelva a escribir direcciones URL, realice comprobaciones solo a través de safeLinks API**: seleccione esta opción para evitar el ajuste de direcciones URL. Vínculos seguros se llama exclusivamente a través de las API en el momento de hacer clic en la dirección URL por parte de los clientes de Outlook que lo admiten.

       - **No vuelva a escribir las siguientes direcciones URL en la sección de correo electrónico** : haga clic en **Administrar (nn) direcciones URL** para permitir el acceso a direcciones URL específicas que, de lo contrario, estarían bloqueadas por vínculos seguros.

         > [!NOTE]
         > Las entradas de la lista "No volver a escribir las siguientes direcciones URL" no se examinan ni encapsulan mediante vínculos seguros durante el flujo de correo. Use [las entradas de permiso de dirección URL en la lista de permitidos o bloqueados de inquilinos](allow-block-urls.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-urls-in-the-submissions-portal) para que las direcciones URL no se examinen ni ajusten mediante vínculos seguros durante el flujo de correo _y_ en el momento de hacer clic.

     1. En el control flotante **Administrar direcciones URL para no volver a escribir** que aparece, haga clic en ![el icono Agregar direcciones URL.](../../media/m365-cc-sc-create-icon.png) **Agregar direcciones URL**.
     2. En el control flotante **Agregar direcciones URL** que aparece, escriba la dirección URL o el valor que desee, seleccione la entrada que aparece debajo del cuadro y, a continuación, haga clic en **Guardar**. Repita este paso tantas veces como sea necesario.

        Para obtener la sintaxis de entrada, consulte [Sintaxis de entrada para la lista "No volver a escribir las siguientes direcciones URL"](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).

        Para quitar una entrada, haga clic en ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto a la entrada.

        Cuando haya terminado, haga clic en **Guardar**.

     3. De nuevo en el control flotante **Administrar direcciones URL para no volver a escribir** , haga clic en **Listo** o realice el mantenimiento en la lista de entradas:

        Para quitar entradas de la lista, puede usar el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro de búsqueda** para buscar la entrada.

        Para seleccionar una sola entrada, haga clic en el valor de la columna **Direcciones URL** .

        Para seleccionar varias entradas de una en una, haga clic en el área en blanco situada a la izquierda del valor.

        Para seleccionar todas las entradas en una, haga clic en el área en blanco situada a la izquierda del encabezado de columna **de direcciones URL** .

        Con una o varias entradas seleccionadas, haga clic en ![Icono Agregar direcciones URL.](../../media/m365-cc-sc-create-icon.png) o ![Icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) iconos que aparecen.

        Cuando haya terminado, haga clic en **Listo**.

   - **Acciones para direcciones URL potencialmente malintencionadas en la sección Microsoft Teams** :
     - **Activado: Vínculos seguros comprueba una lista de vínculos malintencionados conocidos cuando los usuarios hacen clic en vínculos en Microsoft Teams**: seleccione esta opción para habilitar la protección de vínculos seguros para vínculos en Teams. Tenga en cuenta que esta configuración puede tardar hasta 24 horas en surtir efecto.

     > [!NOTE]
     > Actualmente, la protección de vínculos seguros para Microsoft Teams no está disponible en Microsoft 365 GCC High o Microsoft 365 DoD.

   - **Acciones para direcciones URL potencialmente malintencionadas en la sección aplicaciones de Microsoft Office** :
     - **Activado: Vínculos seguros comprueba una lista de vínculos malintencionados conocidos cuando los usuarios hacen clic en vínculos en aplicaciones de Microsoft Office**: seleccione esta opción para habilitar la protección de vínculos seguros para vínculos en archivos en aplicaciones web, móviles y de escritorio de Office compatibles.

   - **Haga clic en la sección configuración de protección** :
     - **Realizar un seguimiento de los clics del usuario**: deje esta opción seleccionada para habilitar los clics del usuario de seguimiento en las direcciones URL. Si selecciona esta opción, están disponibles las siguientes opciones:
       - **Permitir que los usuarios haga clic en la dirección URL original**: desactive esta opción para impedir que los usuarios haga clic en la dirección URL original en [las páginas de advertencia](safe-links.md#warning-pages-from-safe-links).
       - **Mostrar la personalización de marca de la organización en las páginas de notificación y advertencia**: para obtener más información sobre la personalización de marca personalizada, vea [Personalizar el tema de Microsoft 365 para su organización](../../admin/setup/customize-your-organization-theme.md).

   Para obtener información detallada sobre esta configuración, consulte:

   - [Configuración de vínculos seguros para mensajes de correo electrónico](safe-links.md#safe-links-settings-for-email-messages).
   - [Configuración de vínculos seguros para Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).
   - [Configuración de vínculos seguros para aplicaciones de Office](safe-links.md#safe-links-settings-for-office-apps).
   - [Haga clic en Configuración de protección en Directivas de vínculos seguros](safe-links.md#click-protection-settings-in-safe-links-policies)

   Para obtener más información sobre los valores recomendados para la configuración de directivas estándar y estricta, consulte [Configuración de directivas de vínculos seguros](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).

   Cuando termine, haga clic en **Siguiente**.

6. En la página **Notificación** que aparezca, seleccione uno de los siguientes valores para **¿Cómo desea notificar a los usuarios?**:
   - **Use el texto de notificación predeterminado**
   - **Usar texto de notificación personalizado**: si selecciona este valor, aparecerá la siguiente configuración:
     - **Utilizar el traductor de Microsoft para la localización automática**
     - **Texto de notificación personalizado**: escriba el texto de notificación personalizado en este cuadro (la longitud no puede superar los 200 caracteres).

   Cuando termine, haga clic en **Siguiente**.

7. En la página **Revisar** que aparece, revise la configuración. Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Enviar**.

8. En la página de confirmación que aparece, haga clic en **Listo**.

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a>Uso del portal de Microsoft 365 Defender para ver las directivas de vínculos seguros

1. En el portal de Microsoft 365 Defender de <https://security.microsoft.com>, vaya a Email & Directivas de **colaboración** \> **& Reglas** \> **Vínculos seguros** de **directivas** \> de amenazas en la sección **Directivas**. Para ir directamente a la página **Vínculos seguros** , use <https://security.microsoft.com/safelinksv2>.

2. En la página **Vínculos seguros** , se muestran las siguientes propiedades en la lista de directivas de vínculos seguros:
   - **Nombre**
   - **Estado**
   - **Prioridad**

3. Al seleccionar una directiva haciendo clic en el nombre, la configuración de la directiva se muestra en un control flotante.

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a>Uso del portal de Microsoft 365 Defender para modificar directivas de vínculos seguros

1. En el portal de Microsoft 365 Defender, vaya a **Directivas & reglas** \> **Directivas** \> de amenazas Sección \> **Directivas** de amenazas **Vínculos seguros**.

2. En la página **Vínculos seguros** , seleccione una directiva de la lista haciendo clic en el nombre.

3. En el control flotante de detalles de la directiva que aparece, seleccione **Editar** en cada sección para modificar la configuración dentro de la sección. Para obtener más información sobre la configuración, consulte la sección [Anterior Uso del portal de Microsoft 365 Defender para crear directivas de vínculos seguros](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) en este artículo.

Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la directiva, consulte las secciones siguientes.

### <a name="enable-or-disable-safe-links-policies"></a>Habilitación o deshabilitación de directivas de vínculos seguros

1. En el portal de Microsoft 365 Defender de <https://security.microsoft.com>, vaya a Email & Directivas de **colaboración** \> **& Reglas** \> **Vínculos seguros** de **directivas** \> de amenazas en la sección **Directivas**. Para ir directamente a la página **Vínculos seguros** , use <https://security.microsoft.com/safelinksv2>.

2. En la página **Vínculos seguros** , seleccione una directiva de la lista haciendo clic en el nombre.

3. En la parte superior del control flotante de detalles de la directiva que aparece, verá uno de los siguientes valores:
   - **Directiva desactivada**: para activar la directiva, haga clic en ![icono Activar.](../../media/m365-cc-sc-turn-on-off-icon.png) **Activar** .
   - **Directiva activada**: para desactivar la directiva, haga clic en el ![Icono Desactivar](../../media/m365-cc-sc-turn-on-off-icon.png) **Desactivar**.

4. En el cuadro de diálogo de confirmación que aparece, haga clic **Activar** o **Desactivar**.

5. Haga clic en **Cerrar** en el control flotante de detalles de la directiva.

De nuevo en la página principal de la directiva, el valor **Estado** de la directiva estará **Activado** o **Desactivado**.

### <a name="set-the-priority-of-safe-links-policies"></a>Establecer la prioridad de las directivas de vínculos seguros

De forma predeterminada, los vínculos seguros tienen una prioridad que se basa en el orden en el que se crearon (las directivas más recientes son menos prioritarias que las directivas anteriores). Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor). Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

Para cambiar la prioridad de una directiva, haga clic en **Aumentar prioridad** o **Reducir prioridad** en las propiedades de la directiva (no puede modificar directamente el número de **Prioridad** en el portal de Microsoft 365 Defender). Cambiar la prioridad de una directiva sólo tiene sentido si tiene varias directivas.

**Nota**:

- En el portal de Microsoft 365 Defender, solo puede cambiar la prioridad de la directiva Vínculos seguros después de crearla. En PowerShell, puede invalidar la prioridad predeterminada al crear la regla de vínculos seguros (que puede afectar a la prioridad de las reglas existentes).
- Las directivas de vínculos seguros se procesan en el orden en que se muestran (la primera directiva tiene el valor **de prioridad** 0). Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).

1. En el portal de Microsoft 365 Defender de <https://security.microsoft.com>, vaya a Email & Directivas de **colaboración** \> **& Reglas** \> **Vínculos seguros** de **directivas** \> de amenazas en la sección **Directivas**. Para ir directamente a la página **Vínculos seguros** , use <https://security.microsoft.com/safelinksv2>.

2. En la página **Vínculos seguros** , seleccione una directiva de la lista haciendo clic en el nombre.

3. En la parte superior del control flotante de detalles de la directiva que aparece, verá **Aumentar la prioridad** o **Disminuir la prioridad** en función del valor de prioridad actual y del número de directivas personalizadas:
   - La directiva con el valor **De prioridad** **0** solo tiene la opción **Reducir prioridad** disponible.
   - La directiva con el valor **de prioridad** más bajo (por ejemplo, **3**) solo tiene la opción **Aumentar prioridad** disponible.
   - Si tiene tres o más directivas, las directivas entre los valores de prioridad más altos y más bajos tienen disponibles las opciones **Aumentar prioridad** y **Reducir prioridad** .

   Haga clic en el ![Icono Aumentar la prioridad.](../../media/m365-cc-sc-increase-icon.png) **Aumentar la prioridad** o en el ![Icono Disminuir la prioridad](../../media/m365-cc-sc-decrease-icon.png) **Reducir la prioridad** para cambiar el valor de **Prioridad**.

4. Cuando haya terminado, haga clic en **Cerrar** en el control flotante de detalles de la directiva.

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a>Uso del portal de Microsoft 365 Defender para quitar directivas de vínculos seguros

1. En el portal de Microsoft 365 Defender, vaya a Email & Directivas de **colaboración** \> **& Reglas** \> **Vínculos seguros** de **directivas** \> de amenazas en la sección **Directivas**.

2. En la página **Vínculos seguros** , seleccione una directiva de la lista haciendo clic en el nombre. En la parte superior del control flotante de detalles de la directiva que aparece, haga clic en ![icono Más acciones.](../../media/m365-cc-sc-more-actions-icon.png) **Más acciones** \> ![Icono Eliminar directiva](../../media/m365-cc-sc-delete-icon.png)**Eliminar directiva**.

3. En el cuadro de diálogo de confirmación que aparece, haga clic en **Sí**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Usar Exchange Online PowerShell o PowerShell EOP independiente para configurar directivas de vínculos seguros

Como se describió anteriormente, una directiva de vínculos seguros consta de una directiva de vínculos seguros y una regla de vínculos seguros.

En PowerShell, la diferencia entre las directivas de vínculos seguros y las reglas de vínculos seguros es evidente. Las directivas de vínculos seguros se administran mediante los cmdlets **\*-SafeLinksPolicy**, y puede administrar reglas de vínculos seguros mediante los cmdlets **\*-SafeLinksRule**.

- En PowerShell, primero se crea la directiva de vínculos seguros y, a continuación, se crea la regla de vínculos seguros que identifica la directiva a la que se aplica la regla.
- En PowerShell, puede modificar la configuración de la directiva de vínculos seguros y la regla de vínculos seguros por separado.
- Cuando se quita una directiva de vínculos seguros de PowerShell, la regla de vínculos seguros correspondiente no se quita automáticamente y viceversa.

### <a name="use-powershell-to-create-safe-links-policies"></a>Uso de PowerShell para crear directivas de vínculos seguros

La creación de una directiva de vínculos seguros en PowerShell es un proceso de dos pasos:

1. Cree la directiva de vínculos seguros.
2. Cree la regla de vínculos seguros que especifique la directiva de vínculos seguros a la que se aplica la regla.

> [!NOTE]
>
> - Puede crear una nueva regla de vínculos seguros y asignarle una directiva de vínculos seguros existente sin asociar. Una regla de vínculos seguros no se puede asociar a más de una directiva de vínculos seguros.
>
> - Puede configurar las siguientes opciones en las nuevas directivas de vínculos seguros de PowerShell que no estén disponibles en el portal de Microsoft 365 Defender hasta después de crear la directiva:
>   - Cree la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-SafeLinksRule** ).
>   - Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_) en el cmdlet **New-SafeLinksRule** .
>
> - Una nueva directiva de vínculos seguros que cree en PowerShell no será visible en el portal de Microsoft 365 Defender hasta que asigne la directiva a una regla de vínculos seguros.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Paso 1: Uso de PowerShell para crear una directiva de vínculos seguros

Para crear una directiva de vínculos seguros, use esta sintaxis:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSafeLinksForEmail <$true | $false>] [-EnableSafeLinksForOffice <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-AllowClickThrough <$true | $false>] [-TrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - Para obtener más información sobre la sintaxis de entrada que se va a usar para el parámetro _DoNotRewriteUrls_ , vea [Sintaxis de entrada para la lista "No volver a escribir las siguientes direcciones URL"](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).
>
> - Para obtener una sintaxis adicional que puede usar para el parámetro _DoNotRewriteUrls al modificar las directivas de vínculos_ seguros existentes mediante el cmdlet **Set-SafeLinksPolicy** , consulte la sección [Uso de PowerShell para modificar directivas de vínculos seguros](#use-powershell-to-modify-safe-links-policies) más adelante en este artículo.

En este ejemplo se crea una directiva de vínculos seguros denominada Contoso All con los valores siguientes:

- Active el examen de direcciones URL y la reescritura de direcciones URL en los mensajes de correo electrónico.
  - Active el examen y reescritura de direcciones URL para los mensajes internos.
  - Active el examen en tiempo real de las direcciones URL en las que se ha hecho clic, incluidos los vínculos en los que se ha hecho clic que apuntan a los archivos.
    - Espere a que el análisis de URL se complete antes de entregar el mensaje.
- Active el examen de direcciones URL en Teams.
- Active el examen de direcciones URL en aplicaciones de Office compatibles.
- Realizar un seguimiento de los clics de usuario relacionados con la protección de vínculos seguros (no se usa el parámetro _TrackUserClicks_ y el valor predeterminado es $true).
- No permita que los usuarios hagan clic en la dirección URL original.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -EnableSafeLinksForEmail $true -EnableSafeLinksForOffice $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -AllowClickThrough $false
```

Para obtener información detallada sobre la sintaxis y los [parámetros, consulte New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Paso 2: Uso de PowerShell para crear una regla de vínculos seguros

Para crear una regla de vínculos seguros, use esta sintaxis:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

En este ejemplo se crea una regla de vínculos seguros denominada Contoso All con las condiciones siguientes:

- La regla está asociada a la directiva de vínculos seguros denominada Contoso All.
- La regla se aplica a todos los destinatarios del dominio contoso.com.
- Dado que no se usa el parámetro _Priority_ , se usa la prioridad predeterminada.
- La regla está habilitada (no se usa el parámetro _Enabled_ y el valor predeterminado es `$true`).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

En este ejemplo se crea una regla de vínculos seguros similar al ejemplo anterior, pero en este ejemplo, la regla se aplica a los destinatarios de todos los dominios aceptados de la organización.

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs (Get-AcceptedDomain).Name
```

En este ejemplo se crea una regla de vínculos seguros similar a los ejemplos anteriores, pero en este ejemplo, la regla se aplica a los destinatarios de los dominios especificados en un archivo .csv.

```powershell
$Data = Import-Csv -Path "C:\Data\SafeLinksDomains.csv"
$SLDomains = $Data.Domains
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs $SLDomains
```

Para obtener información detallada sobre la sintaxis y los [parámetros, consulte New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).

### <a name="use-powershell-to-view-safe-links-policies"></a>Uso de PowerShell para ver directivas de vínculos seguros

Para ver las directivas de vínculos seguros existentes, use la sintaxis siguiente:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista de resumen de todas las directivas de vínculos seguros.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

En este ejemplo se devuelve información detallada de la directiva de vínculos seguros denominada Contoso Executives.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Para obtener información detallada sobre la sintaxis y los [parámetros, consulte Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).

### <a name="use-powershell-to-view-safe-links-rules"></a>Uso de PowerShell para ver reglas de vínculos seguros

Para ver las reglas de vínculos seguros existentes, use la sintaxis siguiente:

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista de resumen de todas las reglas de vínculos seguros.

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

En este ejemplo se devuelve información detallada de la regla de vínculos seguros denominada Contoso Executives.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Para obtener información detallada sobre la sintaxis y los [parámetros, consulte Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).

### <a name="use-powershell-to-modify-safe-links-policies"></a>Uso de PowerShell para modificar directivas de vínculos seguros

No se puede cambiar el nombre de una directiva de vínculos seguros en PowerShell (el cmdlet **Set-SafeLinksPolicy** no tiene ningún parámetro _Name_ ). Al cambiar el nombre de una directiva de vínculos seguros en el portal de Microsoft 365 Defender, solo cambia el nombre de la _regla_ de vínculos seguros.

La única consideración adicional para modificar directivas de vínculos seguros en PowerShell es la sintaxis disponible para el parámetro _DoNotRewriteUrls_ (la [lista "No volver a escribir las direcciones URL siguientes"](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):

- Para agregar valores que reemplazarán las entradas existentes, use la sintaxis siguiente: `"Entry1","Entry2,..."EntryN"`.
- Para agregar o quitar valores sin afectar a otras entradas existentes, use la sintaxis siguiente: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

De lo contrario, la misma configuración está disponible al crear una directiva de vínculos seguros, como se describe en la sección [Paso 1: Usar PowerShell para crear una directiva de vínculos seguros](#step-1-use-powershell-to-create-a-safe-links-policy) anteriormente en este artículo.

Para modificar una directiva de vínculos seguros, use esta sintaxis:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Para obtener información detallada sobre la sintaxis y los [parámetros, consulte Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).

### <a name="use-powershell-to-modify-safe-links-rules"></a>Uso de PowerShell para modificar reglas de vínculos seguros

La única configuración que no está disponible al modificar una regla de vínculos seguros en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada. Para habilitar o deshabilitar las reglas de vínculos seguros existentes, consulte la sección siguiente.

De lo contrario, la misma configuración está disponible al crear una regla como se describe en la sección [Paso 2: Uso de PowerShell para crear una regla de vínculos seguros](#step-2-use-powershell-to-create-a-safe-links-rule) anteriormente en este artículo.

Para modificar una regla de vínculos seguros, use esta sintaxis:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

En este ejemplo se agregan todos los dominios aceptados de la organización como condición a la regla de vínculos seguros denominada Contoso All.

```powershell
Set-SafeLinksRule -Identity "Contoso All" -RecipientDomainIs (Get-AcceptedDomain).Name
```

En este ejemplo se agregan los dominios de la .csv especificada como condición a la regla de vínculos seguros denominada Contoso All.

```powershell
$Data = Import-Csv -Path "C:\Data\SafeLinksDomains.csv"
$SLDomains = $Data.Domains
Set-SafeLinksRule -Identity "Contoso All" -RecipientDomainIs $SLDomains
```

Para obtener información detallada sobre la sintaxis y los [parámetros, consulte Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>Uso de PowerShell para habilitar o deshabilitar reglas de vínculos seguros

La habilitación o deshabilitación de una regla de vínculos seguros en PowerShell habilita o deshabilita toda la directiva de vínculos seguros (la regla de vínculos seguros y la directiva de vínculos seguros asignados).

Para habilitar o deshabilitar una regla de vínculos seguros en PowerShell, use esta sintaxis:

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

En este ejemplo se deshabilita la regla de vínculos seguros denominada Departamento de marketing.

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

Este ejemplo habilita la misma regla.

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) y [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>Uso de PowerShell para establecer la prioridad de las reglas de vínculos seguros

El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.

Para establecer la prioridad de una regla de vínculos seguros en PowerShell, use la sintaxis siguiente:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

En el ejemplo siguiente, la prioridad de la regla denominada "Marketing Department" se establece en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-SafeLinksRule** en su lugar.

Para obtener información detallada sobre la sintaxis y los [parámetros, consulte Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-remove-safe-links-policies"></a>Uso de PowerShell para quitar directivas de vínculos seguros

Cuando se usa PowerShell para quitar una directiva de vínculos seguros, no se quita la regla de vínculos seguros correspondiente.

Para quitar una directiva de vínculos seguros en PowerShell, use esta sintaxis:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

En este ejemplo se quita la directiva de vínculos seguros denominada Departamento de marketing.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).

### <a name="use-powershell-to-remove-safe-links-rules"></a>Uso de PowerShell para quitar reglas de vínculos seguros

Cuando se usa PowerShell para quitar una regla de vínculos seguros, no se quita la directiva de vínculos seguros correspondiente.

Para quitar una regla de vínculos seguros en PowerShell, use esta sintaxis:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

En este ejemplo se quita la regla de vínculos seguros denominada Departamento de marketing.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los [parámetros, consulte Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).

Para comprobar que Vínculos seguros está examinando los mensajes, compruebe los informes de Microsoft Defender para Office 365 disponibles. Para obtener más información, vea [Ver informes para Defender para Office 365](view-reports-for-mdo.md) y [Usar explorador en el portal de Microsoft 365 Defender](threat-explorer.md).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha creado, modificado o quitado correctamente directivas de vínculos seguros, siga estos pasos:

- En la página **Vínculos seguros** del portal de Microsoft 365 Defender en <https://security.microsoft.com/safelinksv2>, compruebe la lista de directivas, sus valores **de estado** y sus valores **de prioridad**. Para ver más detalles, seleccione la directiva de la lista y vea los detalles del control flotante.

- En Exchange Online PowerShell o Exchange Online Protection PowerShell, reemplace por \<Name\> el nombre de la directiva o regla, ejecute el siguiente comando y compruebe la configuración:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
