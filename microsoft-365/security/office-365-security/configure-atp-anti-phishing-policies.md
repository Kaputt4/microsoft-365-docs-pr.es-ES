---
title: Configurar directivas contra suplantación de identidad en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a crear, modificar y eliminar las directivas avanzadas contra la suplantación de identidad que están disponibles en organizaciones con Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d75455df972e9db0ef1cf4bbeba9f3b78b11002b
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406203"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configurar directivas contra suplantación de identidad en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Las directivas contra suplantación de identidad en [Microsoft Defender para Office 365](office-365-atp.md) pueden ayudar a proteger su organización de ataques de suplantación de identidad malintencionados y otros tipos de ataques de suplantación de identidad. Para obtener más información acerca de las diferencias entre las directivas contra suplantación de identidad (phishing) en Exchange Online Protection (EOP) y las directivas contra suplantación de identidad en Microsoft Defender para Office 365, vea [Anti-phishing protection](anti-phishing-protection.md).

Los administradores pueden ver, editar y configurar (pero no eliminar) la directiva contra suplantación de identidad predeterminada. Para mayor granularidad, también puede crear directivas personalizadas contra la suplantación de identidad que se aplican a usuarios, grupos o dominios específicos de la organización. Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.

Puede configurar directivas contra la suplantación de identidad en el Centro de seguridad & cumplimiento o en PowerShell de Exchange Online.

Para obtener información sobre cómo configurar las directivas contra suplantación de identidad más limitadas que están disponibles en las organizaciones de Exchange Online Protection (es decir, organizaciones sin Microsoft Defender para Office 365), vea [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

Los elementos básicos de una directiva contra la suplantación de identidad son:

- **La directiva contra suplantación de** identidad : especifica las protecciones de suplantación de identidad (phishing) que se habilitarán o deshabilitarán y las acciones que se aplicarán a las opciones.
- **La regla contra suplantación de** identidad : especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva) para una directiva contra suplantación de identidad.

La diferencia entre estos dos elementos no es obvia cuando se administran directivas contra suplantación de identidad en el Centro de seguridad & cumplimiento:

- Al crear una directiva, está creando una regla contra suplantación de identidad (phish) y la directiva contra suplantación de identidad asociada al mismo tiempo con el mismo nombre para ambos.
- Al modificar una directiva, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada y los filtros de destinatarios modifican la regla contra suplantación de identidad. Todas las demás opciones modifican la directiva contra suplantación de identidad asociada.
- Al quitar una directiva, se quitan la regla contra phishing y la directiva contra suplantación de identidad asociada.

En Exchange Online PowerShell, administra la directiva y la regla por separado. Para obtener más información, vea la sección [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) más adelante en este artículo.

Cada organización de Microsoft Defender para Office 365 tiene una directiva contra suplantación de identidad integrada denominada Office365 AntiPhish Default que tiene estas propiedades:

- La directiva se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla contra la suplantación de identidad (filtros de destinatarios) asociada a la directiva.
- La directiva tiene un valor de prioridad personalizado **Mínimo** que no se puede modificar (la directiva siempre se aplica en último lugar). Las directivas personalizadas que cree siempre tendrán una prioridad mayor.
- La directiva es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar esta directiva predeterminada.

Para aumentar la eficacia de la protección contra suplantación de identidad (phishing) en Microsoft Defender para Office 365, puede crear directivas anti phishing personalizadas con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la **página contra suplantación** de identidad atp, use <https://protection.office.com/antiphishing> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Debe tener asignados permisos en **Exchange Online** para poder realizar los procedimientos descritos en este artículo:
  - Para agregar, modificar y eliminar directivas contra suplantación de identidad, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.
  - Para obtener acceso de solo lectura a directivas contra suplantación de identidad, debe ser miembro de los grupos de roles Lector **global** o Lector **de** <sup>\*</sup> seguridad.

  Para obtener más información, consulte los [permisos en Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos y permisos necesarios para _otras_ características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El **grupo de roles Administración** de la organización de solo vista en Exchange [Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica <sup>\*</sup> .
  - <sup>\*</sup> En el Centro de & seguridad, el acceso de solo lectura permite a los usuarios ver la configuración de las directivas personalizadas contra la suplantación de identidad. Los usuarios de solo lectura no pueden ver la configuración en la directiva contra suplantación de identidad predeterminada.

- Para obtener información sobre la configuración recomendada para las directivas contra suplantación de identidad en Microsoft Defender para Office 365, vea [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).

- Permitir hasta 30 minutos para que se aplique una directiva nueva o actualizada.

- Para obtener información sobre dónde se aplican las directivas contra suplantación de identidad en la canalización de filtrado, vea [Order and precedence of email protection](how-policies-and-protections-are-combined.md).

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Usar el Centro de seguridad & cumplimiento para crear directivas contra suplantación de identidad en Microsoft Defender para Office 365

La creación de una directiva contra suplantación de identidad personalizada en el Centro de seguridad & Cumplimiento crea la regla contra suplantación de identidad (phishing) y la directiva contra suplantación de identidad asociada al mismo tiempo con el mismo nombre para ambos.

Al crear una directiva anti phishing, solo puede especificar el nombre de la directiva, la descripción y el filtro de destinatarios que identifica a quién se aplica la directiva. Después de crear la directiva, puede modificar la directiva para cambiar o revisar la configuración predeterminada contra suplantación de identidad.

1. En el Centro de & cumplimiento, vaya a **Directiva de administración** de amenazas contra la \>  \> **suplantación de identidad atp**.

2. En la **página Anti-phishing,** haga clic **en Crear**.

3. Se abrirá el Asistente para crear una nueva directiva **contra suplantación de** identidad. En la **página Nombre de la directiva,** configure las siguientes opciones:

   - **Nombre**: escriba un nombre único y descriptivo para la directiva.

   - **Descripción**: escriba una descripción opcional para la directiva.

   Cuando termine, haga clic en **Siguiente**.

4. En la **página Aplicada a** que aparece, identifique los destinatarios internos a los que se aplica la directiva.

   Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

   Haga **clic en Agregar una condición**. En el desplegable que aparece, seleccione una condición en **Aplicada si**:

   - **El destinatario es**: especifica uno o varios buzones, usuarios de correo o contactos de correo de la organización.
   - **El destinatario es miembro de**: Especifica uno o más grupos de la organización.
   - **El dominio de destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en la organización.

   Después de seleccionar la condición, aparece un desplegable correspondiente con **un cuadro Cualquiera de estos.**

   - Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.
   - Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un valor.
   - Para agregar valores adicionales, haga clic en un área vacía del cuadro.
   - Para quitar entradas individuales, haga clic **en Quitar** ![ icono Quitar del ](../../media/scc-remove-icon.png) valor.
   - Para quitar toda la condición, haga clic **en Quitar** icono Quitar en ![ la ](../../media/scc-remove-icon.png) condición.

   Para agregar una condición adicional, haga clic **en Agregar una condición** y seleccione un valor restante en Aplicado **si**.

   Para agregar excepciones, haga clic **en Agregar una condición** y seleccione una excepción en Excepto **si**. La configuración y el comportamiento se muestran exactamente igual que las condiciones.

   Cuando termine, haga clic en **Siguiente**.

5. En la **página Revisar la configuración** que aparece, revisa la configuración. Puede hacer clic **en Editar** en cada configuración para modificarla.

   Cuando haya terminado, haga clic **en Crear esta directiva.**

6. Haga **clic en Aceptar** en el cuadro de diálogo de confirmación que aparece.

Después de crear la directiva contra suplantación de identidad con esta configuración general, use las instrucciones de la sección siguiente para configurar las opciones de protección en la directiva.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Usar el Centro de & seguridad para modificar directivas contra suplantación de identidad en Microsoft Defender para Office 365

Use los siguientes procedimientos para modificar las directivas contra suplantación de identidad: una nueva directiva que creó o directivas existentes que ya ha personalizado.

1. Si aún no está allí, abra el Centro de seguridad & cumplimiento y vaya a **Directiva** de administración de amenazas \>  \> **contra la suplantación** de identidad atp .

2. Seleccione la directiva contra suplantación de identidad personalizada que desea modificar. Si ya está seleccionado, anule la selección y selecciónelo de nuevo.

3. Aparece el control **desplegable \<name\>** Editar la directiva. Si **hace clic** en Editar en cualquier sección, podrá acceder a la configuración de esa sección.

   - Los pasos siguientes se presentan en el orden en que aparecen las secciones, pero no son secuenciales (puede seleccionar y modificar las secciones en cualquier orden).

   - Después de  hacer clic en Editar en una sección, la configuración disponible se presenta en un formato de asistente,  pero  puede saltar dentro de las páginas en cualquier orden y puede hacer clic en Guardar en cualquier página (o  ![ ](../../media/scc-remove-icon.png) **\<name\>** cancelar o cerrar cerrar icono para volver a la página Editar la directiva (no es necesario visitar la última página del asistente para guardar o salir).

4. **Configuración de directiva:** haga clic **en Editar** para modificar la misma configuración que estaba disponible al [crear la directiva](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) en la sección anterior:

   - **Nombre**
   - **Descripción**
   - **Aplicado a**
   - **Revisar la configuración**

   Cuando haya terminado, haga clic en **Guardar** en cualquier página.

5. **Suplantación:** haga clic **en Editar** para modificar los remitentes protegidos y los dominios protegidos de la directiva. Esta configuración es una condición para la directiva que identifica remitentes suplantados para buscar (individualmente o por dominio) en la dirección De de los mensajes entrantes. Para obtener más información, vea Configuración de suplantación en directivas contra suplantación de identidad en [Microsoft Defender para Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

   - **Agregar usuarios para proteger**: El valor predeterminado es **Off**. Para activarlo, deslice el botón de alternancia a **On** y, a continuación, haga clic en **el botón Agregar usuario** que aparece.

     En el **control desplegable Agregar** usuario que aparece, configure los siguientes valores:

     - **Dirección de correo** electrónico :

       - Haga clic en el cuadro y desplácese por la lista de usuarios que desea seleccionar.
       - Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario.
       - Para quitar una entrada, haga clic **en Quitar** icono Quitar ![ del ](../../media/scc-remove-icon.png) usuario.

     - **Nombre:** este valor se rellena en función de la dirección de correo electrónico seleccionada, pero puede cambiarlo.

     Cuando haya terminado, haga clic en **Guardar** en cualquier página.

     Para editar una entrada existente, seleccione el usuario protegido en la lista.

     > [!NOTE]
     >
     > - En cada directiva contra phishing, puede especificar un máximo de 60 usuarios protegidos (direcciones de correo electrónico del remitente). No puede especificar el mismo usuario protegido en varias directivas.
     >
     > - La protección de suplantación de usuario no funciona si el remitente y el destinatario se han comunicado previamente por correo electrónico. Si el remitente y el destinatario nunca se han comunicado por correo electrónico, el mensaje se identificará como un intento de suplantación.

   - **Agregar dominios para proteger:** Configure una o ambas opciones de configuración:

     - **Incluya automáticamente los dominios que tengo:** El valor predeterminado es **Off**. Para activarlo, deslice el botón de alternancia a **On**.
     - **Incluir dominios personalizados:** el valor predeterminado es **Off**. Para activarlo, deslice el botón de  alternancia en **On** y, en el cuadro Agregar dominios, escriba el nombre de dominio (por ejemplo, contoso.com), presione ENTRAR y repita según sea necesario.

     > [!NOTE]
     > Puede tener un máximo de 50 dominios en todas las directivas contra suplantación de identidad.

   - **Acciones:** haga clic en **Editar**

     - **Si** un usuario suplantado envía correo electrónico: configure una de las siguientes acciones para los mensajes en los que el remitente suplantado sea uno de los usuarios protegidos que especificó en Agregar usuarios para **proteger**:

       - **No aplicar ninguna acción**
       - **Redirigir el mensaje a otras direcciones de correo electrónico**
       - **Mover mensaje a la carpeta Correo no deseado**
       - **Poner en cuarentena el mensaje**
       - **Entregar el mensaje y agregar otras direcciones a la línea CCO**
       - **Eliminar el mensaje antes de entregarlo**

     - **Si** un dominio suplantado envía correo electrónico: configure una de las siguientes acciones para los mensajes en los que el remitente suplantado se encuentra en uno de los dominios protegidos que especificó en Agregar dominios para **proteger**:

       - **No aplicar ninguna acción**
       - **Redirigir el mensaje a otras direcciones de correo electrónico**
       - **Mover mensaje a la carpeta Correo no deseado**
       - **Poner en cuarentena el mensaje**
       - **Entregar el mensaje y agregar otras direcciones a la línea CCO**
       - **Eliminar el mensaje antes de entregarlo**

   - Haga clic en Activar sugerencias de seguridad **de suplantación** y configure cualquiera de las siguientes opciones:

     - **Sugerencia para usuarios suplantados:** el valor predeterminado es **Off**. Para activarlo, deslice el botón de alternancia a **On**.
     - **Sugerencia para dominios suplantados:** el valor predeterminado es **Off**. Para activarlo, deslice el botón de alternancia a **On**.
     - **Sugerencia para mostrar caracteres inusuales:** el valor predeterminado es **Off**. Para activarlo, deslice el botón de alternancia a **On**.

     Cuando haya terminado, haga clic en **Guardar**.

   - **Inteligencia de buzones**:

     - **Habilitar la inteligencia de buzones de correo:** el valor predeterminado es **On**. Para desactivarlo, deslice el botón de alternancia a **Desactivado**.

     - **Habilitar la protección de suplantación basada** en inteligencia de buzones de correo: esta configuración solo está disponible si Habilitar inteligencia **de buzones de correo es** **On**.

       En **If email is sent by an suersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):

       - **No aplicar ninguna acción**
       - **Redirigir el mensaje a otras direcciones de correo electrónico**
       - **Mover mensaje a la carpeta Correo no deseado**
       - **Poner en cuarentena el mensaje**
       - **Entregar el mensaje y agregar otras direcciones a la línea CCO**
       - **Eliminar el mensaje antes de entregarlo**

   - **Agregar remitentes y dominios de confianza:** especifique excepciones para la directiva:

     - **Remitentes de confianza:**

       - Haga clic en el cuadro y desplácese por la lista de usuarios que desea seleccionar.
       - Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario.
       - Para quitar una entrada, haga clic **en Quitar** icono Quitar ![ del ](../../media/scc-remove-icon.png) usuario.

     - **Dominios de** confianza: escriba el nombre de dominio (por ejemplo, contoso.com), presione ENTRAR y repita según sea necesario.

   - **Revise la configuración:** en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.

     - Puede hacer clic **en Editar** en cada sección para volver a la página correspondiente.
     - Puedes activar o desactivar la **siguiente** configuración **directamente** en esta página:

       - **Usuarios protegidos**
       - **Dominios protegidos** \> **Incluir dominios de mi propiedad**
       - **Dominios protegidos** \> **Dominios protegidos** (dominios personalizados)
       - **Inteligencia de buzones**

   Cuando haya terminado, haga clic en **Guardar** en cualquier página.

6. **Suplantación:**  haga clic en Editar para activar o desactivar la inteligencia de suplantación de identidad, activar o desactivar la identificación de remitentes no autenticados en Outlook y configurar la acción para que se aplique a los mensajes de remitentes suplantados bloqueados. Para obtener más información, vea [Configuración de suplantación de identidad en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings).

   Tenga en cuenta que esta misma configuración también está disponible en las directivas contra suplantación de identidad en EOP.

   - **Configuración del filtro de suplantación:** el valor predeterminado es **On** y le recomendamos que lo deje en. Para desactivarlo, deslice el botón de alternancia a **Desactivado**. Para obtener más información, vea [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).

     > [!NOTE]
     > No es necesario deshabilitar la protección contra la suplantación si el registro MX no apunta a Microsoft 365; habilitar el filtrado mejorado para conectores en su lugar. Para obtener instrucciones, consulte [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - **Habilitar la característica Remitente no autenticado:** el valor predeterminado es **On**. Para desactivarlo, deslice el botón de alternancia a **Desactivado**.

   - **Acciones:** especifique la acción que se debe realizar en los mensajes que no puedan suplantar la inteligencia:

     Si alguien que no tiene permiso para **suplantación** de dominio envía correo electrónico:

     - **Mover el mensaje a las carpetas de correo no deseado de los destinatarios**
     - **Poner en cuarentena el mensaje**

   - **Revise la configuración:** en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.

     - Puede hacer clic **en Editar** en cada sección para volver a la página correspondiente.
     - Puedes activar o desactivar la **siguiente** configuración **directamente** en esta página:
       - **Habilitar la protección contra la suplantación**
       - **Habilitar la característica Remitente no autenticado**

   Cuando haya terminado, haga clic en **Guardar** en cualquier página.

7. **Configuración avanzada:** haga clic **en Editar** para configurar los umbrales de suplantación de identidad avanzados. Para obtener más información, vea [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

   - **Umbrales de suplantación de identidad avanzados:** seleccione uno de los siguientes valores:

   - **1- Estándar** (este es el valor predeterminado).
   - **2 : agresivo**
   - **3: más agresivo**
   - **4: más agresivo**

   - **Revisa la configuración:** haz clic **en Editar** para volver a la **página Umbrales de suplantación de** identidad avanzada.

   Cuando haya terminado, haga clic en **Guardar** en cualquier página.

8. Vuelva a la **página Editar la \<Name\> directiva,** revise la configuración y, a continuación, haga clic en **Cerrar**.

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a>Usar el Centro de & seguridad para modificar la directiva contra suplantación de identidad predeterminada en Microsoft Defender para Office 365

La directiva contra suplantación de identidad predeterminada en Microsoft Defender para Office 365 se denomina Office365 AntiPhish Default y no aparece en la lista de directivas. Para modificar la directiva contra suplantación de identidad predeterminada, siga estos pasos:

1. En el Centro de & cumplimiento, vaya a **Directiva de administración** de amenazas contra la \>  \> **suplantación de identidad atp**.

2. En la **página Anti-phishing,** haga clic en **Directiva predeterminada**.

3. Aparece **la página Editar la directiva Office365 AntiPhish Default.** Las siguientes secciones están disponibles, que contienen una configuración idéntica para cuando [se modifica una directiva personalizada:](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)

   - **Suplantación**
   - **Suplantación**
   - **Configuración avanzada**

   La siguiente configuración no está disponible al modificar la directiva predeterminada:

   - Puede ver  la sección Configuración de directiva y los valores, pero no hay ningún vínculo **Editar,** por lo que no puede modificar la configuración (nombre de directiva, descripción y a quién se aplica la directiva (se aplica a todos los destinatarios)).
   - No puede eliminar la directiva predeterminada.
   - No puede cambiar la prioridad de la directiva predeterminada (siempre se aplica en último lugar).

4. En la página Editar la directiva predeterminada de **Office365 AntiPhish,** revise la configuración y, a continuación, haga clic **en Cerrar**.

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Habilitar o deshabilitar directivas anti phishing personalizadas en Microsoft Defender para Office 365

1. En el Centro de & cumplimiento, vaya a **Directiva de administración** de amenazas contra la \>  \> **suplantación de identidad atp**.

2. Observe el valor de la **columna Estado:**

   - Deslice el botón de **alternancia a Desactivado** para deshabilitar la directiva.

   - Deslice el botón de **alternancia a Activar** para habilitar la directiva.

No puede deshabilitar la directiva contra suplantación de identidad predeterminada.

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Establecer la prioridad de las directivas anti phishing personalizadas en Microsoft Defender para Office 365

De forma predeterminada, las directivas contra suplantación de identidad tienen una prioridad que se basa en el orden en que se crearon (las directivas más recientes son de menor prioridad que las directivas anteriores). Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor). Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).

Las directivas contra suplantación de identidad personalizadas se muestran en el orden en que se procesan (la primera directiva tiene el **valor de prioridad** 0). La directiva contra suplantación de identidad predeterminada denominada Office365 AntiPhish Default tiene el valor de prioridad personalizado **Lowest** y no se puede cambiar.

 **Nota:** En el Centro de seguridad & cumplimiento, solo puede cambiar la prioridad de la directiva contra suplantación de identidad después de crearla. En PowerShell, puede invalidar la prioridad predeterminada al crear la regla contra suplantación de identidad (lo que puede afectar a la prioridad de las reglas existentes).

Para cambiar la prioridad de  una directiva, haga clic en Aumentar prioridad o Disminuir  prioridad en las propiedades de la directiva (no puede modificar directamente el número de prioridad en el Centro de seguridad & cumplimiento).  Cambiar la prioridad de una directiva solo tiene sentido si tiene varias directivas.

1. En el Centro de & cumplimiento, vaya a **Directiva de administración** de amenazas contra la \>  \> **suplantación de identidad atp**.

2. Seleccione la directiva que desea modificar. Si ya está seleccionado, anule la selección y selecciónelo de nuevo.

3. Aparece el control **desplegable \<name\>** Editar la directiva.

   - La directiva contra suplantación de identidad personalizada con el valor **de prioridad** **0** solo tiene disponible el **botón Disminuir** prioridad.

   - La directiva contra suplantación de identidad personalizada con el valor **priority** más bajo (por ejemplo, **3**) solo tiene disponible **el botón Aumentar** prioridad.

   - Si tiene tres o más directivas contra suplantación de identidad personalizadas, las  directivas entre los valores de prioridad más alta y más baja tienen disponibles los botones Aumentar prioridad y Disminuir prioridad. 

4. Haga **clic en Aumentar prioridad** o Disminuir **prioridad** para cambiar el valor **De** prioridad.

5. Cuando haya terminado, haga clic en **Cerrar**.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Usar el Centro de seguridad & cumplimiento para ver directivas contra suplantación de identidad en Microsoft Defender para Office 365

1. En el Centro de seguridad & cumplimiento y vaya a **Directiva de administración** de amenazas ATP contra \>  \> **suplantación** de identidad .

2. Realice uno de los pasos siguientes:

   - Seleccione una directiva contra suplantación de identidad personalizada que desee ver. Si ya está seleccionado, anule la selección y selecciónelo de nuevo.

   - Haga **clic en Directiva predeterminada** para ver la directiva contra suplantación de identidad predeterminada.

3. Aparece **el \<name\> control desplegable** Editar la directiva, donde puede ver la configuración y los valores.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Usar el Centro de & seguridad para quitar directivas contra suplantación de identidad en Microsoft Defender para Office 365

1. En el Centro de & cumplimiento, vaya a **Directiva de administración** de amenazas contra la \>  \> **suplantación de identidad atp**.

2. Seleccione la directiva que desea quitar. Si ya está seleccionado, anule la selección y selecciónelo de nuevo.

3. En el **control \<name\>** desplegable Editar la directiva que aparece, haga clic en **Eliminar** directiva y, a continuación, haga clic en **Sí** en el cuadro de diálogo de advertencia que aparece.

No puede quitar la directiva predeterminada.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Usar Exchange Online PowerShell para configurar directivas contra suplantación de identidad en Microsoft Defender para Office 365

Como se describió anteriormente, una directiva contra correo no deseado consta de una directiva contra suplantación de identidad (phish) y una regla contra suplantación de identidad (phish).

En Exchange Online PowerShell, la diferencia entre las directivas contra suplantación de identidad (phish) y las reglas contra suplantación de identidad (phishing) es aparente. Las directivas contra suplantación de identidad se administran mediante los cmdlets **\* -AntiPhishPolicy** y se administran reglas contra suplantación de identidad mediante los cmdlets **\* -AntiPhishRule.**

- En PowerShell, primero se crea la directiva contra suplantación de identidad y, a continuación, se crea la regla contra suplantación de identidad que identifica la directiva a la que se aplica la regla.
- En PowerShell, se modifica la configuración de la directiva contra suplantación de identidad y la regla contra suplantación de identidad por separado.
- Al quitar una directiva contra suplantación de identidad de PowerShell, la regla anti-phish correspondiente no se quita automáticamente y viceversa.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Usar PowerShell para crear directivas contra suplantación de identidad

Crear una directiva contra la suplantación de identidad en PowerShell es un proceso de dos pasos:

1. Cree la directiva contra suplantación de identidad.
2. Cree la regla contra suplantación de identidad que especifica la directiva contra suplantación de identidad a la que se aplica la regla.

 **Notas**:

- Puede crear una nueva regla contra suplantación de identidad (phish) y asignarle una directiva anti-phish existente y no asociada. Una regla contra la suplantación de identidad no se puede asociar a más de una directiva contra suplantación de identidad.

- Puede configurar las siguientes opciones en las nuevas directivas contra suplantación de identidad en PowerShell que no están disponibles en el Centro de seguridad y cumplimiento de & hasta después de crear la directiva:

  - Cree la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-AntiPhishRule).**
  - Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_ ) en el cmdlet **New-AntiPhishRule).**

- Una nueva directiva contra suplantación de identidad que cree en PowerShell no está visible en el Centro de seguridad y cumplimiento de & hasta que asigne la directiva a una regla contra suplantación de identidad.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Paso 1: Usar PowerShell para crear una directiva contra suplantación de identidad

Para crear una directiva contra phishing, use esta sintaxis:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

En este ejemplo se crea una directiva contra phishing denominada Cuarentena de investigación con la siguiente configuración:

- La directiva está habilitada (no estamos usando el parámetro _Enabled_ y el valor predeterminado es `$true` ).
- La descripción es: Directiva del departamento de investigación.
- Habilita la protección de dominios de la organización para todos los dominios aceptados y la protección de dominios de destino para fabrikam.com.
- Especifica Mai Fujito (mfujito@fabrikam.com) como el usuario que se debe proteger de la suplantación.
- Habilita la inteligencia de buzones.
- Habilita la protección de inteligencia de buzones de correo y especifica la acción de cuarentena.
- Habilita las sugerencias de seguridad.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Paso 2: Usar PowerShell para crear una regla contra suplantación de identidad

Para crear una regla contra phishing, use esta sintaxis:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

En este ejemplo se crea una regla contra suplantación de identidad (phish) denominada Departamento de investigación con las siguientes condiciones:

- La regla está asociada con la directiva contra phishing denominada Cuarentena de investigación.
- La regla se aplica a los miembros del grupo denominado Research Department.
- Dado que no estamos usando el parámetro _Priority,_ se usa la prioridad predeterminada.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).

### <a name="use-powershell-to-view-anti-phish-policies"></a>Usar PowerShell para ver directivas contra suplantación de identidad

Para ver las directivas anti phish existentes, use la siguiente sintaxis:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista resumida de todas las directivas contra phishing junto con las propiedades especificadas.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

En este ejemplo se devuelven todos los valores de propiedad de la directiva contra suplantación de identidad denominada Executives.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).

### <a name="use-powershell-to-view-anti-phish-rules"></a>Usar PowerShell para ver reglas contra suplantación de identidad

Para ver las reglas anti phish existentes, use la siguiente sintaxis:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista resumida de todas las reglas contra phishing junto con las propiedades especificadas.

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

En este ejemplo se devuelven todos los valores de propiedad de la regla contra suplantación de identidad denominada Ejecutivos de Contoso.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Usar PowerShell para modificar directivas contra suplantación de identidad

Aparte de los siguientes elementos, la misma configuración está disponible al modificar una directiva contra suplantación de identidad en PowerShell que al crear la directiva, tal como se describe en el Paso 1: Usar PowerShell para crear una sección de directiva contra suplantación de identidad [(phish policy)](#step-1-use-powershell-to-create-an-anti-phish-policy) anterior en este artículo.

- El _modificador MakeDefault_ que convierte la directiva especificada en la directiva predeterminada (aplicada a todos, siempre **con** prioridad más baja y no puede eliminarla) solo está disponible cuando modifica una directiva contra suplantación de identidad en PowerShell.

- No puede cambiar el nombre de una directiva contra suplantación de identidad (el cmdlet **Set-AntiPhishPolicy** no tiene ningún _parámetro Name)._ Al cambiar el nombre de una directiva contra suplantación de identidad en el Centro de seguridad & cumplimiento, solo se cambia el nombre de la regla contra _suplantación de identidad_.

Para modificar una directiva contra phishing, use esta sintaxis:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Usar PowerShell para modificar reglas contra suplantación de identidad

La única configuración que no está disponible al modificar una regla contra suplantación de identidad en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada. Para habilitar o deshabilitar las reglas antiphishing existentes, consulte la siguiente sección.

De lo contrario, no hay ninguna configuración adicional disponible al modificar una regla contra suplantación de identidad en PowerShell. La misma configuración está disponible al crear una regla tal como se describe en el paso [2: Usar PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) para crear una regla contra suplantación de identidad anterior en este artículo.

Para modificar una regla contra phishing, use esta sintaxis:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Usar PowerShell para habilitar o deshabilitar reglas contra suplantación de identidad

Habilitar o deshabilitar una regla contra suplantación de identidad en PowerShell habilita o deshabilita toda la directiva contra suplantación de identidad (la regla anti phishing y la directiva contra suplantación de identidad asignada). No puede habilitar ni deshabilitar la directiva contra suplantación de identidad predeterminada (siempre se aplica a todos los destinatarios).

Para habilitar o deshabilitar una regla contra phishing en PowerShell, use esta sintaxis:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

En este ejemplo se deshabilita la regla contra suplantación de identidad (phish) denominada Departamento de marketing.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

Este ejemplo habilita la misma regla.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, vea [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) y [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Usar PowerShell para establecer la prioridad de las reglas contra suplantación de identidad

El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo que se puede establecer depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.

Para establecer la prioridad de una regla contra suplantación de identidad en PowerShell, use la siguiente sintaxis:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Notas**:

- Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-AntiPhishRule** en su lugar.

- La directiva contra suplantación de identidad predeterminada no tiene una regla anti phish correspondiente y siempre tiene el valor de prioridad no modificable **Lowest**.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Usar PowerShell para quitar directivas contra suplantación de identidad

Cuando se usa PowerShell para quitar una directiva contra suplantación de identidad, no se quita la regla contra suplantación de identidad correspondiente.

Para quitar una directiva contra suplantación de identidad en PowerShell, use esta sintaxis:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

En este ejemplo se quita la directiva contra suplantación de identidad denominada Departamento de marketing.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Usar PowerShell para quitar reglas contra suplantación de identidad

Cuando usa PowerShell para quitar una regla contra phishing, no se quita la directiva anti phish correspondiente.

Para quitar una regla contra suplantación de identidad en PowerShell, use esta sintaxis:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

En este ejemplo se quita la regla contra suplantación de identidad (phish) denominada Departamento de marketing.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha configurado correctamente directivas contra suplantación de identidad (phishing) en Microsoft Defender para Office 365, siga estos pasos:

- En el Centro de & cumplimiento, vaya a **Directiva de administración** de amenazas contra la \>  \> **suplantación de identidad atp**. Compruebe la lista de directivas, sus **valores de** estado y sus **valores de** prioridad. Para ver más detalles, siga estos pasos:

  - Seleccione la directiva de la lista y vea los detalles en el menú desplegable.
  - Haga **clic en Directiva predeterminada** y vea los detalles en el menú desplegable.

- En Exchange Online PowerShell, reemplace por el nombre de la directiva o \<Name\> regla y ejecute el siguiente comando y compruebe la configuración:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
