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
ms.openlocfilehash: bc7575b87b8c5e512116f60ae98b700071e2bbd0
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822387"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configurar directivas contra suplantación de identidad en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Las directivas contra suplantación de identidad en [Microsoft Defender](defender-for-office-365.md) para Office 365 pueden ayudar a proteger su organización de ataques de suplantación de identidad malintencionados y otros tipos de ataques de suplantación de identidad. Para obtener más información acerca de las diferencias entre las directivas contra suplantación de identidad en Exchange Online Protection (EOP) y las directivas contra suplantación de identidad en Microsoft Defender para Office 365, vea [Protección](anti-phishing-protection.md)contra la suplantación de identidad .

Los administradores pueden ver, editar y configurar (pero no eliminar) la directiva contra suplantación de identidad predeterminada. Para mayor granularidad, también puede crear directivas personalizadas contra la suplantación de identidad que se aplican a usuarios, grupos o dominios específicos de la organización. Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.

Puede configurar directivas contra la suplantación de identidad en Defender para Office 365 en el centro de seguridad de Microsoft 365 o en PowerShell Exchange Online.

Para obtener información sobre cómo configurar las directivas contra suplantación de identidad más limitadas que están disponibles en Exchange Online Protection (es decir, organizaciones sin Defender para Office 365), vea [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

Los elementos básicos de una directiva contra la suplantación de identidad son:

- **La directiva contra suplantación de** identidad : especifica las protecciones de suplantación de identidad (phishing) que se habilitarán o deshabilitarán y las acciones que se aplicarán a las opciones.
- **La regla contra suplantación de** identidad : especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva) para una directiva contra suplantación de identidad.

La diferencia entre estos dos elementos no es obvia al administrar directivas contra suplantación de identidad en el centro de seguridad:

- Al crear una directiva, está creando una regla contra suplantación de identidad (phish) y la directiva contra suplantación de identidad asociada al mismo tiempo con el mismo nombre para ambos.
- Al modificar una directiva, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada y los filtros de destinatarios modifican la regla contra suplantación de identidad. Todas las demás opciones modifican la directiva contra suplantación de identidad asociada.
- Al quitar una directiva, se quitan la regla contra phishing y la directiva contra suplantación de identidad asociada.

En Exchange Online PowerShell, administra la directiva y la regla por separado. Para obtener más información, vea la sección [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) más adelante en este artículo.

Cada organización de Defender para Office 365 tiene una directiva contra la suplantación de identidad integrada denominada Office365 AntiPhish Default que tiene estas propiedades:

- La directiva se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla contra la suplantación de identidad (filtros de destinatarios) asociada a la directiva.
- La directiva tiene un valor de prioridad personalizado **Mínimo** que no se puede modificar (la directiva siempre se aplica en último lugar). Las directivas personalizadas que cree siempre tendrán una prioridad mayor.
- La directiva es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar esta directiva predeterminada.

Para aumentar la eficacia de la protección contra suplantación de identidad en Defender para Office 365, puede crear directivas contra suplantación de identidad personalizadas con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Puede abrir el Centro de seguridad en <https://security.microsoft.com>. Para ir directamente a la **página Anti-phishing,** use <https://security.microsoft.com/antiphishing> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Debe tener permisos asignados en la **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para agregar, modificar y eliminar directivas contra suplantación de identidad, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.
  - Para obtener acceso de solo lectura a directivas contra suplantación de identidad, debe ser miembro de los grupos de roles Lector **global** o Lector **de** <sup>\*</sup> seguridad.

  Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para obtener información sobre la configuración recomendada para las directivas contra suplantación de identidad en Defender para Office 365, consulte [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).

- Permitir hasta 30 minutos para que se aplique una directiva nueva o actualizada.

- Para obtener información sobre dónde se aplican las directivas contra suplantación de identidad en la canalización de filtrado, vea [Order and precedence of email protection](how-policies-and-protections-are-combined.md).

## <a name="use-the-security-center-to-create-anti-phishing-policies"></a>Usar el centro de seguridad para crear directivas contra suplantación de identidad

La creación de una directiva contra suplantación de identidad personalizada en el centro de seguridad crea la regla contra suplantación de identidad (phishing) y la directiva contra suplantación de identidad asociada al mismo tiempo con el mismo nombre para ambos.

1. En el centro de seguridad, vaya a Correo electrónico **& directivas** de colaboración & De directivas de amenazas de reglas \>  \>  \>  sección \> **Anti-phishing**.

2. En la **página Anti-phishing,** haga clic ![ en Crear icono ](../../media/m365-cc-sc-create-icon.png) **Crear**.

3. Se abrirá el asistente para directivas. En la **página Nombre de directiva,** configure estas opciones:
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

5. En la **página de protección de & de** suplantación de identidad que aparece, configure las siguientes opciones:

   - **Umbral de correo electrónico de** suplantación de identidad : use el control deslizante para seleccionar uno de los siguientes valores:
     - **1- Estándar** (este es el valor predeterminado).
     - **2 : agresivo**
     - **3: más agresivo**
     - **4: más agresivo**

     Para obtener más información, consulte [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

   - **Suplantación:** esta configuración es una condición para la directiva que identifica remitentes específicos para buscar (individualmente o por dominio) en la dirección De de los mensajes entrantes. Para obtener más información, vea Configuración de suplantación en directivas contra suplantación de identidad en [Microsoft Defender para Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

     > [!NOTE]
     >
     > - En cada directiva contra phishing, puede especificar un máximo de 60 usuarios protegidos (direcciones de correo electrónico del remitente). No puede especificar el mismo usuario protegido en varias directivas.
     >
     > - La protección de suplantación de usuario no funciona si el remitente y el destinatario se han comunicado previamente por correo electrónico. Si el remitente y el destinatario nunca se han comunicado por correo electrónico, el mensaje se identificará como un intento de suplantación.

     - **Permitir a los usuarios proteger:** el valor predeterminado está desactivado (no seleccionado). Para activarla, active la casilla y, a continuación, haga clic en el vínculo Administrar **(nn) remitentes** que aparece.

       En el control desplegable Administrar **remitentes** para protección de suplantación que aparece, siga estos pasos:

       - **Remitentes internos:** haga clic ![ en Agregar icono interno Seleccione ](../../media/m365-cc-sc-add-internal-icon.png) **interno**. En el **control desplegable Agregar remitentes** internos que aparece, haga clic en el cuadro y seleccione un usuario interno de la lista. Puede filtrar la lista escribiendo el usuario y, a continuación, seleccionando el usuario en los resultados. Puede usar la mayoría de los identificadores (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de cuenta, etc.), pero el nombre para mostrar correspondiente se muestra en los resultados.

         Repita este paso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono de quitar](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

         Cuando haya terminado, haga clic en **Agregar**

       - **Remitentes externos:** haga clic ![ en Agregar icono externo Seleccione ](../../media/m365-cc-sc-create-icon.png) **externo**. En el control desplegable Agregar **remitentes externos** que  aparece, escriba un nombre para mostrar en el cuadro Agregar un nombre y una dirección de correo electrónico en el cuadro Agregar un correo electrónico vacío y, **a** continuación, haga clic en **Agregar**.

         Repita este paso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono de quitar](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

         Cuando haya terminado, haga clic en **Agregar**

       En el control desplegable Administrar **remitentes** para suplantación, puede quitar entradas seleccionando una o más entradas de la lista. Puede buscar entradas mediante el cuadro ![ Buscar en el icono ](../../media/m365-cc-sc-create-icon.png)  buscar.

       Después de seleccionar al menos una entrada, aparece el icono Quitar usuarios seleccionados Quitar usuarios seleccionados, que puede usar para ![ quitar las entradas ](../../media/m365-cc-sc-remove-selected-users-icon.png)  seleccionadas.

       Cuando haya terminado, haga clic en **Listo**.

     - **Habilitar dominios para proteger:** el valor predeterminado está desactivado (no seleccionado). Para activarla, active la casilla y, a continuación, configure una o ambas opciones de configuración que aparecen:
       - **Incluir los dominios que tengo:** para activar esta configuración, active la casilla. Para ver los dominios que posee, haga clic **en Ver mis dominios**.
       - **Incluir dominios personalizados:** para activar esta configuración, active la casilla y, a continuación, haga clic en el vínculo Administrar **(nn)** dominios personalizados que aparece. En el control desplegable Administrar dominios **personalizados** para protección de suplantación que aparece, haga clic ![ en Agregar dominios icono Agregar ](../../media/m365-cc-sc-create-icon.png) **dominios**.

         En **el** control desplegable Agregar dominios personalizados que aparece, haga clic en el cuadro Dominio, escriba un valor y, a continuación, presione Entrar o seleccione el valor que se muestra debajo del cuadro.  Repita este paso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar en ![Quitar icono](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

         Cuando haya terminado, haga clic en **Agregar dominios**

         > [!NOTE]
         > Puede tener un máximo de 50 dominios en todas las directivas contra suplantación de identidad.

       En el **control** desplegable Administrar dominios personalizados para suplantación, puede quitar entradas seleccionando una o más entradas de la lista. Puede buscar entradas mediante el cuadro ![ Buscar en el icono ](../../media/m365-cc-sc-create-icon.png)  buscar.

       Después de seleccionar al menos una entrada, aparece el icono Eliminar dominios Eliminar, que puede usar ![ para quitar las entradas ](../../media/m365-cc-sc-delete-icon.png)  seleccionadas.

   - **Agregar remitentes y** dominios de confianza: : especifique excepciones de protección de suplantación para la directiva haciendo clic en Administrar **(nn) remitentes** de confianza y dominios . En el control desplegable Administrar dominios **personalizados** para protección de suplantación que aparece, configure las siguientes opciones:
      - **Remitentes:** compruebe que la **pestaña** Remitente está seleccionada y haga clic ![ en Agregar remitentes icono ](../../media/m365-cc-sc-create-icon.png) . En el control desplegable Agregar **remitentes de** confianza que aparece, escriba una dirección de correo electrónico en el cuadro y, a continuación, haga clic en **Agregar**. Repita este paso tantas veces como sea necesario. Para quitar una entrada existente, haga clic ![ en Eliminar icono para la ](../../media/m365-cc-sc-close-icon.png) entrada.

        Cuando haya terminado, haga clic en **Agregar**.

      - **Dominios:** seleccione la **pestaña Dominio** y haga clic en Agregar dominios ![ icono ](../../media/m365-cc-sc-create-icon.png) .
  
        En **el** control desplegable Agregar dominios de  confianza que aparece, haga clic en el cuadro Dominio, escriba un valor y, a continuación, presione Entrar o seleccione el valor que se muestra debajo del cuadro. Repita este paso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar en ![Quitar icono](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

        Cuando haya terminado, haga clic en **Agregar**.

     En el  control desplegable Administrar dominios personalizados para suplantación,  puede quitar entradas de las pestañas Remitente y Dominio seleccionando una o más entradas de la lista.  Puede buscar entradas mediante el cuadro ![ Buscar en el icono ](../../media/m365-cc-sc-create-icon.png)  buscar.

     Después de seleccionar al menos  una entrada, aparece el icono Eliminar, que puede usar para quitar las entradas seleccionadas.

     Cuando haya terminado, haga clic en **Listo**.

   - **Habilitar inteligencia de** buzones: el valor predeterminado está en (seleccionado) y se recomienda dejarla activada. Para desactivarla, desactive la casilla.

     - **Habilitar la protección de suplantación** basada en inteligencia: esta configuración solo está disponible si **Habilitar** inteligencia de buzones está activada (seleccionada). Esta configuración permite que la inteligencia de buzones de correo tome medidas en los mensajes que se identifican como intentos de suplantación. Especifique la acción que debe realizar en la configuración Si la inteligencia **de buzones detecta** un usuario suplantado en la página siguiente.

       Se recomienda activar esta configuración activando la casilla. Para desactivar esta configuración, desactive la casilla.

   - **Suplantación:** en esta sección, use la casilla Habilitar la inteligencia suplantación para activar o desactivar la inteligencia suplantación.  El valor predeterminado está en (seleccionado) y se recomienda dejarlo en. Especifique la acción que se debe realizar en los mensajes de remitentes suplantados bloqueados en la configuración **If message is detected as spoof** en la página siguiente.

     Para desactivar la inteligencia de suplantación, desactive la casilla.

     > [!NOTE]
     > No es necesario desactivar la protección contra la suplantación si el registro MX no apunta a Microsoft 365; habilitar el filtrado mejorado para conectores en su lugar. Para obtener instrucciones, consulte [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   Cuando termine, haga clic en **Siguiente**.

6. En la página **Acciones** que aparece, configure las opciones siguientes:

   - **Acciones de mensaje:** configure las siguientes acciones en esta sección:
     - **Si el mensaje se detecta como** un usuario suplantado: esta configuración solo está disponible si seleccionó Habilitar usuarios **para** proteger en la página anterior. Seleccione una de las siguientes acciones en la lista desplegable para los mensajes donde el remitente es uno de los usuarios protegidos que especificó en la página anterior:
       - **No aplicar ninguna acción**
       - **Redirigir el mensaje a otras direcciones de correo electrónico**
       - **Mover el mensaje a las carpetas de correo no deseado de los destinatarios**
       - **Poner en cuarentena el mensaje**
       - **Entregar el mensaje y agregar otras direcciones a la línea CCO**
       - **Eliminar el mensaje antes de entregarlo**

     - **Si el mensaje se detecta como** un dominio suplantado: esta configuración solo está disponible si seleccionó Habilitar dominios para proteger **en** la página anterior. Seleccione una de las siguientes acciones en la lista desplegable para los mensajes en los que la dirección de correo electrónico del remitente se encuentra en uno de los dominios protegidos que especificó en la página anterior:
       - **No aplicar ninguna acción**
       - **Redirigir el mensaje a otras direcciones de correo electrónico**
       - **Mover el mensaje a las carpetas de correo no deseado de los destinatarios**
       - **Poner en cuarentena el mensaje**
       - **Entregar el mensaje y agregar otras direcciones a la línea CCO**
       - **Eliminar el mensaje antes de entregarlo**

     - **Si la inteligencia de buzones** detecta un usuario suplantado: esta configuración solo está disponible si seleccionó Habilitar inteligencia para la protección de suplantación **en** la página anterior. Seleccione una de las siguientes acciones en la lista desplegable para los mensajes que se identificaron como intentos de suplantación por inteligencia de buzones:
       - **No aplicar ninguna acción**
       - **Redirigir el mensaje a otras direcciones de correo electrónico**
       - **Mover el mensaje a las carpetas de correo no deseado de los destinatarios**
       - **Poner en cuarentena el mensaje**
       - **Entregar el mensaje y agregar otras direcciones a la línea CCO**
       - **Eliminar el mensaje antes de entregarlo**

     - **Si el mensaje se detecta como** suplantación: esta configuración solo está disponible si seleccionó Habilitar la inteligencia de suplantación en la página anterior.  Seleccione una de las siguientes acciones en la lista desplegable para los mensajes de remitentes suplantados bloqueados:
       - **Mover el mensaje a las carpetas de correo no deseado de los destinatarios**
       - **Poner en cuarentena el mensaje**

   - **Sugerencias de & indicadores** de seguridad: Configure las siguientes opciones:
     - **Mostrar la suplantación de consejo de seguridad:** esta configuración solo está disponible si seleccionó Habilitar usuarios **para** proteger en la página anterior.
     - **Mostrar la suplantación de dominio consejo de seguridad:** esta configuración solo está disponible si seleccionó Habilitar dominios **para** proteger en la página anterior.
     - **Mostrar caracteres inusuales de suplantación de usuario consejo de seguridad** Esta configuración solo está disponible si seleccionó **Habilitar** usuarios para proteger o Habilitar dominios **para** proteger en la página anterior.
     - **Mostrar (?)** para remitentes no autenticados para suplantación de identidad: esta configuración solo está disponible si seleccionó Habilitar la inteligencia de suplantación de identidad en la página anterior.  Agrega un signo de interrogación a la foto del remitente en el cuadro De de  Outlook si el mensaje no pasa las comprobaciones SPF o DKIM y el mensaje no pasa dmarc ni autenticación compuesta [.](email-validation-and-authentication.md#composite-authentication)
     - **Mostrar etiqueta "via":** esta configuración solo está disponible si seleccionó Habilitar la inteligencia **de** suplantación en la página anterior. Agrega una etiqueta via (chris@contoso.com a través de fabrikam.com) a la dirección De si es diferente del dominio en la firma DKIM o la **dirección MAIL FROM.** El valor predeterminado está en (seleccionado). Para desactivarla, desactive la casilla.

       > [!NOTE]
       > Actualmente, la configuración de la etiqueta **Mostrar "a través"** no está disponible en todas las organizaciones. Si no tiene la configuración de etiqueta **Mostrar "a** través", el signo de interrogación y la etiqueta via están controlados por show  **(?)** para remitentes no autenticados para la configuración de suplantación de identidad en su organización.

     Para activar una configuración, active la casilla. Para desactivarla, desactive la casilla.

   Cuando termine, haga clic en **Siguiente**.

7. En la página **Revisar** que aparece, revise la configuración. Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Enviar**.

8. En la página de confirmación que aparece, haga clic en **Listo**.

## <a name="use-the-security-center-to-view-anti-phishing-policies"></a>Usar el centro de seguridad para ver directivas contra suplantación de identidad

1. En el centro de seguridad, vaya a Correo electrónico **& directivas** de colaboración & De directivas de amenazas de reglas \>  \>  \>  sección \> **Anti-phishing**.

2. En la **página Anti-phishing,** las siguientes propiedades se muestran en la lista de directivas contra suplantación de identidad:

   - **Nombre**
   - **Estado**
   - **Prioridad**
   - **Última modificación**

3. Al seleccionar una directiva haciendo clic en el nombre, la configuración de la directiva se muestra en un menú desplegable.

## <a name="use-the-security-center-to-modify-anti-phishing-policies"></a>Usar el centro de seguridad para modificar directivas contra suplantación de identidad

1. En el centro de seguridad, vaya a Correo electrónico **& directivas** de colaboración & De directivas de amenazas de reglas \>  \>  \>  sección \> **Anti-phishing**.

2. En la **página Anti-phishing,** seleccione una directiva de la lista haciendo clic en el nombre.

3. En el control flotante de detalles de la directiva que aparece, seleccione **Editar** en cada sección para modificar la configuración dentro de la sección. Para obtener más información acerca de la configuración, vea la sección Usar el centro de seguridad para crear directivas [contra suplantación](#use-the-security-center-to-create-anti-phishing-policies) de identidad anteriores en este artículo.  

   Para la directiva contra suplantación de identidad predeterminada, la sección **Usuarios,** grupos y dominios no está disponible (la directiva se aplica a todos) y no puede cambiar el nombre de la directiva.

Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la directiva, consulte las secciones siguientes.

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Habilitar o deshabilitar directivas personalizadas contra suplantación de identidad

No puede deshabilitar la directiva contra suplantación de identidad predeterminada.

1. En el centro de seguridad, vaya a Correo electrónico **& directivas** de colaboración & De directivas de amenazas de reglas \>  \>  \>  sección \> **Anti-phishing**.

2. En la **página Anti-phishing,** seleccione una directiva personalizada de la lista haciendo clic en el nombre.

3. En la parte superior del control flotante de detalles de la directiva que aparece, verá uno de los siguientes valores:
   - **Directiva desactivada**: para activar la directiva, haga clic en el ![Icono Activar](../../media/m365-cc-sc-turn-on-off-icon.png) **Activar**.
   - **Directiva activada**: Para desactivar la directiva, haga clic en el ![Icono desactivar](../../media/m365-cc-sc-turn-on-off-icon.png) y **Desactivar**.

4. En el cuadro de diálogo de confirmación que aparece, haga clic **Activar** o **Desactivar**.

5. Haga clic en **Cerrar** en el control flotante de detalles de la directiva.

De nuevo en la página principal de la directiva, el valor **Estado** de la directiva estará **Activado** o **Desactivado**.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>Establecer la prioridad de las directivas contra suplantación de identidad personalizadas

De forma predeterminada, las directivas contra suplantación de identidad tienen una prioridad que se basa en el orden en que se crearon (las directivas más recientes son de menor prioridad que las directivas anteriores). Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor). Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

Para cambiar la prioridad de una directiva, haga clic en **Aumentar la prioridad** o en **Reducir la prioridad** en las propiedades de la directiva (no se puede modificar directamente el número de **Prioridad** en el Centro de seguridad). Cambiar la prioridad de una directiva solo tiene sentido si tiene varias directivas.

 **Notas**:

- En el centro de seguridad, solo puede cambiar la prioridad de la directiva contra suplantación de identidad después de crearla. En PowerShell, puede invalidar la prioridad predeterminada al crear la regla contra suplantación de identidad (lo que puede afectar a la prioridad de las reglas existentes).
- Las directivas contra suplantación de identidad se procesan en el orden en que se muestran (la primera directiva tiene el **valor de prioridad** 0). La directiva contra suplantación de identidad predeterminada tiene el valor de prioridad **Lowest** y no puede cambiarla.

1. En el centro de seguridad, vaya a Correo electrónico **& directivas** de colaboración & De directivas de amenazas de reglas \>  \>  \>  sección \> **Anti-phishing**.

2. En la **página Anti-phishing,** seleccione una directiva personalizada de la lista haciendo clic en el nombre.

3. En la parte superior del control flotante de detalles de la directiva que aparece, verá **Aumentar la prioridad** o **Disminuir la prioridad** en función del valor de prioridad actual y del número de directivas personalizadas:
   - La directiva contra suplantación de identidad con el valor **de** prioridad **0** solo tiene disponible **la opción Disminuir** prioridad.
   - La directiva contra suplantación de identidad con el valor **priority** más bajo (por ejemplo, **3**) solo tiene disponible **la opción Aumentar** prioridad.
   - Si tiene tres o más directivas contra la suplantación de identidad, las directivas entre los valores de prioridad más alta y más baja tienen disponibles las opciones **Aumentar** prioridad y **Disminuir** prioridad.

   Haga clic en el ![Icono Aumentar la prioridad](../../media/m365-cc-sc-increase-icon.png) **Aumentar la prioridad** o en el ![Icono Disminuir la prioridad](../../media/m365-cc-sc-decrease-icon.png) **Reducir la prioridad** para cambiar el valor de **Prioridad**.

4. Cuando haya terminado, haga clic en **Cerrar** en el control flotante de detalles de la directiva.

## <a name="use-the-security-center-to-remove-custom-anti-phishing-policies"></a>Usar el centro de seguridad para quitar directivas personalizadas contra suplantación de identidad

Cuando se usa el centro de seguridad para quitar una directiva de anti phishing personalizada, se eliminan tanto la regla contra suplantación de identidad como la directiva anti phishing correspondiente. No puede quitar la directiva contra suplantación de identidad predeterminada.

1. En el centro de seguridad, vaya a Correo electrónico **& directivas** de colaboración & De directivas de amenazas de reglas \>  \>  \>  sección \> **Anti-phishing**.

2. Seleccione una directiva personalizada de la lista haciendo clic en el nombre de la directiva. En la parte superior del control flotante de detalles de la directiva que aparece, haga clic en el ![Icono Más acciones](../../media/m365-cc-sc-more-actions-icon.png) **Más acciones** \> ![Icono Eliminar directiva](../../media/m365-cc-sc-delete-icon.png) **Eliminar directiva**.

3. En el cuadro de diálogo de confirmación que aparece, haga clic en **Sí**.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Usar Exchange Online PowerShell para configurar directivas contra suplantación de identidad

Como se describió anteriormente, una directiva contra correo no deseado consta de una directiva contra suplantación de identidad (phish) y una regla contra suplantación de identidad (phish).

En Exchange Online PowerShell, la diferencia entre las directivas contra suplantación de identidad y las reglas contra suplantación de identidad es aparente. Las directivas contra suplantación de identidad se administran mediante los cmdlets **\* -AntiPhishPolicy** y se administran reglas contra suplantación de identidad mediante los cmdlets **\* -AntiPhishRule.**

- En PowerShell, primero se crea la directiva contra suplantación de identidad y, a continuación, se crea la regla contra suplantación de identidad que identifica la directiva a la que se aplica la regla.
- En PowerShell, se modifica la configuración de la directiva contra suplantación de identidad y la regla contra suplantación de identidad por separado.
- Al quitar una directiva contra suplantación de identidad de PowerShell, la regla anti-phish correspondiente no se quita automáticamente y viceversa.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Usar PowerShell para crear directivas contra suplantación de identidad

Crear una directiva contra la suplantación de identidad en PowerShell es un proceso de dos pasos:

1. Cree la directiva contra suplantación de identidad.
2. Cree la regla contra suplantación de identidad que especifica la directiva contra suplantación de identidad a la que se aplica la regla.

 **Notas**:

- Puede crear una nueva regla contra suplantación de identidad (phish) y asignarle una directiva anti-phish existente y no asociada. Una regla contra la suplantación de identidad no se puede asociar a más de una directiva contra suplantación de identidad.
- Puede configurar las siguientes opciones en las nuevas directivas contra suplantación de identidad en PowerShell que no están disponibles en el centro de seguridad hasta después de crear la directiva:
  - Cree la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-AntiPhishRule).**
  - Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_ ) en el cmdlet **New-AntiPhishRule).**
- Una nueva directiva contra suplantación de identidad que cree en PowerShell no será visible en el centro de seguridad hasta que asigne la directiva a una regla contra suplantación de identidad.

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

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).

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

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).

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

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).

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

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Usar PowerShell para modificar directivas contra suplantación de identidad

Aparte de los siguientes elementos, la misma configuración está disponible al modificar una directiva contra suplantación de identidad en PowerShell que al crear la directiva, tal como se describe en el Paso 1: Usar PowerShell para crear una sección de directiva contra suplantación de identidad [(phish policy)](#step-1-use-powershell-to-create-an-anti-phish-policy) anterior en este artículo.

- El _modificador MakeDefault_ que convierte la directiva especificada en la directiva predeterminada (aplicada a todos, siempre **con** prioridad más baja y no puede eliminarla) solo está disponible cuando modifica una directiva contra suplantación de identidad en PowerShell.

- No puede cambiar el nombre de una directiva contra suplantación de identidad (el cmdlet **Set-AntiPhishPolicy** no tiene ningún _parámetro Name)._ Al cambiar el nombre de una directiva contra suplantación de identidad en el centro de seguridad, solo se cambia el nombre de la regla contra _suplantación de identidad_.

Para modificar una directiva contra phishing, use esta sintaxis:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Usar PowerShell para modificar reglas contra suplantación de identidad

La única configuración que no está disponible al modificar una regla contra suplantación de identidad en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada. Para habilitar o deshabilitar las reglas antiphishing existentes, consulte la siguiente sección.

De lo contrario, no hay ninguna configuración adicional disponible al modificar una regla contra suplantación de identidad en PowerShell. La misma configuración está disponible al crear una regla tal como se describe en el paso [2: Usar PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) para crear una regla contra suplantación de identidad anterior en este artículo.

Para modificar una regla contra phishing, use esta sintaxis:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).

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

Para obtener información detallada acerca de la sintaxis y los parámetros, vea [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) y [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Usar PowerShell para establecer la prioridad de las reglas contra suplantación de identidad

El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.

Para establecer la prioridad de una regla contra suplantación de identidad en PowerShell, use la siguiente sintaxis:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

En el ejemplo siguiente, la prioridad de la regla denominada "Marketing Department" se establece en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).

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

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).

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

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha configurado correctamente directivas contra suplantación de identidad en Defender para Office 365, siga estos pasos:

- En el centro de seguridad, vaya a Correo electrónico **& directivas** de colaboración & De directivas de amenazas de reglas \>  \>  \>  sección \> **Anti-phishing**. Compruebe la lista de directivas, sus **valores de** estado y sus **valores de** prioridad. Para ver más detalles, seleccione la directiva de la lista haciendo clic en el nombre y viendo los detalles en el menú desplegable que aparece.

- En Exchange Online PowerShell, reemplace por el nombre de la directiva o regla y ejecute el \<Name\> siguiente comando y compruebe la configuración:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
