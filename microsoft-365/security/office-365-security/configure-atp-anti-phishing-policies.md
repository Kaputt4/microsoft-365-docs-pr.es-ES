---
title: Configurar directivas contra phishing de ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo crear, modificar y eliminar las Directivas avanzadas de suplantación de identidad (phishing) que están disponibles en las organizaciones con Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: 7b1806b20ef5974b83cc4e5ab681c847d826d04b
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352050"
---
# <a name="configure-atp-anti-phishing-policies"></a>Configurar directivas contra phishing de ATP

Las directivas antiphishing de ATP forman parte de la [protección contra amenazas avanzada de Office 365](office-365-atp.md). Las directivas antiphishing de ATP pueden ayudar a proteger a su organización de ataques de suplantación de identidad (phishing) malintencionados y otros tipos de ataques de suplantación de identidad. Para obtener más información acerca de las diferencias entre las directivas antiphishing en Exchange Online Protection (EOP) y las directivas antiphishing de ATP, consulte [anti-phishing Protection](anti-phishing-protection.md).

Los administradores pueden ver, editar y configurar (pero no eliminar) la Directiva antiphishing predeterminada de ATP. Para una mayor granularidad, también puede crear directivas antiphishing de ATP personalizadas que se aplican a usuarios, grupos o dominios específicos de la organización. Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.

Puede configurar las directivas antiphishing de ATP en el centro de seguridad & cumplimiento o en Exchange Online PowerShell.

Para obtener información acerca de la configuración de las directivas antiphishing más limitadas que están disponibles en las organizaciones de Exchange Online Protection (es decir, las organizaciones de Microsoft 365 sin ATP de Office 365), vea [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a>Directivas antiphishing de ATP en el centro de seguridad & cumplimiento de vs PowerShell

Los elementos básicos de una directiva contra la suplantación de identidad ATP son los siguientes:

- **La Directiva ANTIPHISH**: especifica las protecciones de suplantación de identidad (phishing) que se deben habilitar o deshabilitar y las acciones para aplicar opciones.

- **La regla anti-phish**: especifica la prioridad y los filtros de destinatarios (a los que se aplica la Directiva) para una directiva antiphishing.

La diferencia entre estos dos elementos no es obvia cuando se administran las directivas antiphishing de ATP en el centro de seguridad & cumplimiento:

- Al crear una directiva contra la suplantación de identidad ATP en el centro de seguridad & cumplimiento, en realidad está creando una regla ANTIPHISH y la Directiva ANTIPHISH asociada al mismo tiempo con el mismo nombre para ambas.

- Cuando modifica una directiva de ATP antiphishing en el centro de seguridad & cumplimiento, la configuración relacionada con los filtros nombre, prioridad, habilitado o deshabilitado, y de destinatarios modifica la regla contra el phish. Todas las demás opciones modifican la Directiva ANTIPHISH asociada.

- Al quitar una directiva de ATP contra la suplantación de identidad del centro de seguridad & cumplimiento, se quita la regla antiphishing y la Directiva de ANTIPHISH asociada.

En Exchange Online PowerShell, la diferencia entre las directivas antiphishing y las reglas antiphishing es evidente. Las directivas antiphishing se administran mediante los cmdlets ** \* -AntiPhishPolicy** y se administran las reglas antiphishing mediante los cmdlets ** \* -AntiPhishRule** .

- En PowerShell, se crea la Directiva ANTIPHISH en primer lugar y, a continuación, se crea la regla ANTIPHISH que identifica la Directiva a la que se aplica la regla.

- En PowerShell, la configuración de la Directiva antiphishing y la regla antiphishing se modifican por separado.

- Cuando se quita una directiva ANTIPHISH de PowerShell, la regla antiphishing correspondiente no se elimina automáticamente y viceversa.

### <a name="default-atp-anti-phishing-policy"></a>Directiva antiphishing de ATP predeterminada

Cada organización ATP tiene una directiva antiphishing de ATP integrada llamada Office365 ANTIPHISH predeterminada con estas propiedades:

- La Directiva ANTIPHISH denominada Office365 ANTIPHISH predeterminada se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla antiphishing (filtros de destinatario) asociada a la Directiva.

- La Directiva denominada predeterminada de la ANTIPHISH de Office365 tiene el valor de prioridad personalizado **más bajo** que no se puede modificar (la Directiva se aplica siempre en último lugar). Cualquier directiva personalizada que cree siempre tendrá una prioridad mayor que la Directiva denominada Office365 ANTIPHISH predeterminada.

- La Directiva denominada Office365 ANTIPHISH predeterminada es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True` ) y no se puede eliminar la directiva predeterminada.

Para aumentar la eficacia de la protección contra suplantación de identidad (phishing), puede crear directivas antiphishing personalizadas de ATP con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página **contra la suplantación de identidad ATP** , use <https://protection.office.com/antiphishing> .

- Para conectarse a PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

- Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos. Para agregar, modificar y eliminar directivas antiphishing, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** . Para el acceso de solo lectura a las directivas antiphishing, debe ser miembro del grupo de roles **lector de seguridad** . Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

- Para obtener la configuración recomendada para las directivas antiphishing de ATP, consulte [configuración de la Directiva de antiphishing de Office ATP](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).

- Permitir que se aplique una directiva nueva o actualizada durante un máximo de 30 minutos.

- Para obtener información acerca de dónde se aplican las directivas contra la suplantación de identidad (phishing) en la canalización de filtros, consulte [Order and Precedence of email Protection](how-policies-and-protections-are-combined.md).

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a>Usar el centro de seguridad & cumplimiento para crear directivas contra la suplantación de identidad ATP

La creación de una directiva antiphishing de ATP personalizada en el centro de seguridad & cumplimiento crea la regla ANTIPHISH y la Directiva de ANTIPHISH asociada al mismo tiempo con el mismo nombre para ambas.

Al crear una directiva contra la suplantación de identidad ATP, solo puede especificar el nombre de la Directiva, la descripción y el filtro de destinatarios que identifica a quién se aplica la Directiva. Después de crear la Directiva, puede modificar la Directiva para cambiar o revisar la configuración predeterminada de la suplantación de identidad (phishing).

1. En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.

2. En la página **contra la suplantación de identidad** , haga clic en **crear**.

3. Se abrirá el Asistente para **crear una nueva Directiva antiphishing** . En la página **asigne un nombre a la Directiva** , configure las siguientes opciones:

   - **Nombre**: escriba un nombre único y descriptivo para la directiva.

   - **Descripción**: escriba una descripción opcional para la directiva.

   Cuando termine, haga clic en **Siguiente**.

4. En la página **aplicado a** que aparece, identifique los destinatarios internos a los que se aplica la Directiva.

   Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción. Varios valores de la misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ or _\<recipient2\>_). Diversas condiciones o excepciones usan la lógica AND (por ejemplo, _\<recipient1\>_ and _\<miembro del grupo 1\>_).

   Haga clic en **Agregar condición**. En la lista desplegable que aparece, seleccione una condición en **aplicado si**:

   - **El destinatario es**: especifica uno o más buzones de correo, usuarios de correo o contactos de correo de su organización.
   - **El destinatario es un miembro de**: especifica uno o más grupos de la organización.
   - **El dominio del destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en la organización.

   Después de seleccionar la condición, aparece la lista desplegable correspondiente con una **de estas** casillas.

   - Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.
   - Haga clic en el cuadro y comience a escribir para filtrar la lista y seleccionar un valor.
   - Para agregar más valores, haga clic en un área vacía del cuadro.
   - Para quitar entradas individuales, haga **Remove** clic en ![ el icono quitar quitar del ](../../media/scc-remove-icon.png) valor.
   - Para quitar toda la condición, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación en la condición.

   Para agregar una condición adicional, haga clic en **Agregar condición** y seleccione un valor restante en **aplicado si**.

   Para agregar excepciones, haga clic en **Agregar una condición** y seleccione una excepción en **excepto si**. La configuración y el comportamiento se muestran exactamente igual que las condiciones.

   Cuando termine, haga clic en **Siguiente**.

5. En la página **Revise la configuración** que aparece, revise la configuración. Puede hacer clic en **Editar** en cada configuración para modificarla.

   Cuando haya terminado, haga clic en **crear esta directiva**.

6. Haga clic en **Aceptar** en el cuadro de diálogo de confirmación que aparece.

Después de crear la Directiva contra la suplantación de identidad ATP con estas opciones de directiva generales, siga las instrucciones de la siguiente sección para configurar las opciones de protección de la Directiva.

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a>Usar el centro de seguridad & cumplimiento para modificar las directivas antiphishing de ATP

Use los siguientes procedimientos para modificar las directivas antiphishing de ATP: una nueva directiva que ha creado o las directivas existentes que ya ha personalizado.

1. Si aún no está ahí, abra el centro de seguridad & cumplimiento y vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP anti-phishing**.

2. Seleccione la Directiva antiphishing de ATP personalizada que quiera modificar. Si ya está seleccionada, anule la selección y vuelva a seleccionarla.

3. Aparece el control flotante **editar el \< nombre \> de la Directiva** . Al hacer clic en **Editar** en cualquier sección, obtendrá acceso a la configuración de esa sección.

   - Los pasos siguientes se presentan en el orden en que aparecen las secciones, pero no son secuenciales (puede seleccionar y modificar las secciones en cualquier orden).

   - Después de hacer clic en **Editar** en una sección, la configuración disponible se presenta en un formato de asistente, pero puede saltar dentro de las páginas en cualquier orden y puede hacer clic en **Guardar** en cualquier página (o en **Cancelar** o **cerrar** el ![ icono cerrar ](../../media/scc-remove-icon.png) para volver a la página **editar el \< nombre \> de la Directiva** (no es necesario visitar la última página del Asistente para guardarla o dejarla).

4. **Configuración de directiva**: haga clic en **Editar** para modificar la misma configuración que estaba disponible cuando [creó la Directiva](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) en la sección anterior:

   - **Nombre**
   - **Descripción**
   - **Aplicado a**
   - **Revisar la configuración**

   Cuando haya terminado, haga clic en **Guardar** en cualquier página.

5. **Suplantación**: haga clic en **Editar** para modificar los remitentes protegidos y los dominios protegidos en la Directiva. Esta configuración es una condición para la Directiva que identifica a los remitentes suplantados para que busquen (de forma individual o por dominio) en la dirección de de los mensajes entrantes. Para obtener más información, consulte [configuración de suplantación en las directivas de antiphishing de ATP](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).

   - **Agregar usuarios para proteger**: el valor predeterminado es **desactivado**. Para activarla, deslice el botón de alternancia a **activado**y, a continuación, haga clic en el botón **Agregar usuario** que aparece.

     En el control flotante **Agregar usuario** que aparece, configure los siguientes valores:

     - **Dirección de correo electrónico**:

        - Haga clic en el cuadro y desplácese por la lista de usuarios que desea seleccionar.
        - Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario.
        - Para quitar una entrada, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación en el usuario.

     - **Nombre**: este valor se rellena en función de la dirección de correo electrónico que haya seleccionado, pero puede cambiarlo.

     Cuando haya terminado, haga clic en **Guardar** en cualquier página.

    Para editar una entrada existente, seleccione el usuario protegido en la lista.

   - **Agregar dominios para proteger**: configure una o ambas de las siguientes opciones:

     - **Incluir automáticamente los dominios que tengo**: el valor predeterminado es **desactivado**. Para activarla, deslice el botón de alternancia a **activado**.
     - **Incluir dominios personalizados**: el valor predeterminado es **desactivado**. Para activarla, deslice el botón de alternancia a **activado**y, en el cuadro **Agregar dominios** , escriba el nombre de dominio (por ejemplo, contoso.com), presione entrar y repita lo mismo según sea necesario.

   - **Acciones**: haga clic en **Editar**

     - **Si un usuario suplantado envía un correo electrónico**: configure una de las siguientes acciones para los mensajes en los que el remitente falso sea uno de los usuarios protegidos que ha especificado en **Agregar usuarios para proteger**:

       - **No aplicar ninguna acción**
       - **Redirigir un mensaje a otras direcciones de correo electrónico**
       - **Mover mensaje a la carpeta Correo no deseado**
       - **Poner en cuarentena el mensaje**
       - **Entregar el mensaje y agregar otras direcciones a la línea CCO**
       - **Eliminar el mensaje antes de su entrega**

     - **Si un dominio suplantado envía un correo electrónico**: configure una de las siguientes acciones para los mensajes en los que el remitente falso esté en uno de los dominios protegidos que ha especificado en **Agregar dominios para proteger**:

     - **No aplicar ninguna acción**
     - **Redirigir un mensaje a otras direcciones de correo electrónico**
     - **Mover mensaje a la carpeta Correo no deseado**
     - **Poner en cuarentena el mensaje**
     - **Entregar el mensaje y agregar otras direcciones a la línea CCO**
     - **Eliminar el mensaje antes de su entrega**

   - Haga clic en **Activar sugerencias de seguridad de suplantación** y configure cualquiera de las siguientes opciones:

     - **Mostrar sugerencia para usuarios suplantados**: el valor predeterminado es **desactivado**. Para activarla, deslice el botón de alternancia a **activado**.
     - **Mostrar sugerencia para dominios suplantados**: el valor predeterminado es **desactivado**. Para activarla, deslice el botón de alternancia a **activado**.
     - **Mostrar sugerencia para caracteres inusuales**: el valor predeterminado es **desactivado**. Para activarla, deslice el botón de alternancia a **activado**.

     Cuando haya terminado, haga clic en **Guardar**.

   - **Inteligencia de buzones de correo**:

     - **¿Habilitar la inteligencia de buzones?**: el valor predeterminado es **activado**. Para desactivarla, deslice el botón de alternancia a **desactivado**.

     - **¿Habilitar la protección de suplantación basada en buzones de correo?**: esta opción solo está disponible si **Habilitar inteligencia de buzones de correo?** es **activado**.

       En **si un usuario suplantado envía un correo electrónico**, puede especificar una de las siguientes acciones para que se realicen en los mensajes que no superen la inteligencia del buzón (las mismas acciones que están disponibles para los usuarios protegidos y los dominios protegidos):

       - **No aplicar ninguna acción**
       - **Redirigir un mensaje a otras direcciones de correo electrónico**
       - **Mover mensaje a la carpeta Correo no deseado**
       - **Poner en cuarentena el mensaje**
       - **Entregar el mensaje y agregar otras direcciones a la línea CCO**
       - **Eliminar el mensaje antes de su entrega**

   - **Agregue los remitentes y dominios de confianza**: especifique las excepciones de la Directiva:

     - **Remitentes de confianza**:

       - Haga clic en el cuadro y desplácese por la lista de usuarios que desea seleccionar.
       - Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario.
       - Para quitar una entrada, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación en el usuario.

     - **Dominios de confianza**: escriba el nombre del dominio (por ejemplo, contoso.com), presione entrar y repita el procedimiento según sea necesario.

   - **Revise la configuración**: en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.

     - Puede hacer clic en **Editar** en cada sección para volver a la página correspondiente.
     - Puede activar o **desactivar** la siguiente configuración **directamente en esta** página:

       - **Usuarios protegidos**
       - **Dominios protegidos** \> **Incluir dominios de su propiedad**
       - **Dominios protegidos** \> **Dominios protegidos** (dominios personalizados)
       - **Inteligencia de buzones**

   Cuando haya terminado, haga clic en **Guardar** en cualquier página.

6. **Suplantación de identidad**: haga clic en **Editar** para activar o desactivar la inteligencia de suplantación, activar o desactivar la identificación del remitente sin autenticar en Outlook y configurar la acción para aplicar a los mensajes de los remitentes suplantados bloqueados. Para obtener más información, consulte [configuración de la suplantación de identidades en directivas antiphishing](set-up-anti-phishing-policies.md#spoof-settings).

   Tenga en cuenta que esta misma configuración también está disponible en las directivas antiphishing en EOP.

   - **Configuración del filtro de suplantación de identidad**: el valor predeterminado es **activado**y se recomienda que lo deje activado. Para desactivarla, deslice el botón de alternancia a **desactivado**. Para obtener más información, vea [Configure outsimulate Intelligence in EOP](learn-about-spoof-intelligence.md).

     > [!NOTE]
     > No es necesario deshabilitar la protección contra la suplantación de identidad si el registro MX no apunta a Microsoft 365; en su lugar, se habilita el filtrado mejorado para los conectores. Para obtener instrucciones, vea [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - **Habilitar la característica de remitente sin autenticar**: el valor predeterminado es **activado**. Para desactivarla, deslice el botón de alternancia a **desactivado**.

   - **Acciones**: especificar la acción que se realizará en los mensajes que no superen la inteligencia de identidad:

     **Si el correo electrónico lo envía alguien que no tiene permiso para suplantar su dominio**:

     - **Mover mensaje a las carpetas de correo no deseado de los destinatarios**
     - **Poner en cuarentena el mensaje**

   - **Revise la configuración**: en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.

     - Puede hacer clic en **Editar** en cada sección para volver a la página correspondiente.
     - Puede activar o **desactivar** la siguiente configuración **directamente en esta** página:

       - **Habilitar la protección contra la suplantación de identidad**
       - **Habilitar la característica de remitente sin autenticar**

   Cuando haya terminado, haga clic en **Guardar** en cualquier página.

7. **Configuración avanzada**: haga clic en **Editar** para configurar los umbrales de suplantación de identidad avanzada. Para obtener más información, consulte [umbrales de suplantación de identidad avanzada en las directivas de antiphishing de ATP](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).

   - **Umbrales de suplantación de identidad avanzada**: Seleccione uno de los siguientes valores:

   - **1-estándar** (este es el valor predeterminado).
   - **2-agresivo**
   - **3-más agresivo**
   - **4: más agresivo**

   - **Revise la configuración**: haga clic en **Editar** para volver a la página **umbrales de suplantación de identidad avanzada** .

   Cuando haya terminado, haga clic en **Guardar** en cualquiera de las páginas.

8. De nuevo en la página **Editar \< el \> nombre de la Directiva** , revise la configuración y, a continuación, haga clic en **cerrar**.

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a>Usar el centro de seguridad & cumplimiento para modificar la Directiva antiphishing de ATP predeterminada

La Directiva antiphishing de ATP predeterminada se denomina Office365 ANTIPHISH predeterminada y no aparece en la lista de directivas. Para modificar la Directiva antiphishing de ATP predeterminada, siga estos pasos:

1. En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.

2. En la página **contra la suplantación de identidad** , haga clic en **directiva predeterminada**.

3. Aparecerá la página **editar la Directiva de ANTIPHISH predeterminada de Office365** . Las siguientes secciones están disponibles, que contienen ajustes idénticos para cuando se [modifica una directiva personalizada](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):

   - **Suplantación**
   - **Suplantación**
   - **Configuración avanzada**

   Las siguientes opciones de configuración no están disponibles cuando se modifica la directiva predeterminada:

   - Puede ver la sección y los valores de configuración de la **Directiva** , pero no hay ningún vínculo **Editar** , por lo que no puede modificar la configuración (nombre de Directiva, Descripción y a quién se aplica la Directiva (se aplica a todos los destinatarios)).
   - No puede eliminar la directiva predeterminada.
   - No puede cambiar la prioridad de la directiva predeterminada (siempre se aplica en último lugar).

4. En la página **editar la Directiva de ANTIPHISH predeterminada de Office365** , revise la configuración y, a continuación, haga clic en **cerrar**.

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a>Habilitar o deshabilitar las directivas antiphishing de ATP personalizadas

1. En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.

2. Observe el valor de la columna **Estado** :

   - Deslice el botón de alternancia a **desactivado** para deshabilitar la Directiva.

   - Deslice el botón de alternancia a **activado** para habilitar la Directiva.

No se puede deshabilitar la Directiva antiphishing predeterminada.

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a>Establecer la prioridad de las directivas anti-phishing personalizadas de ATP

De forma predeterminada, las directivas antiphishing de ATP reciben una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen una prioridad más baja que las directivas anteriores). Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor). Dos directivas no pueden tener la misma prioridad.

Las directivas de antiphishing de ATP personalizadas se muestran en el orden en que se procesan (la primera Directiva tiene el valor de **prioridad** 0). La Directiva antiphishing predeterminada denominada Office365 ANTIPHISH predeterminada tiene el valor de prioridad personalizado **más bajo**y no se puede cambiar.

 **Nota**: en el centro de seguridad & cumplimiento, solo puede cambiar la prioridad de la Directiva contra la suplantación de identidad (phishing) de ATP después de crearla. En PowerShell, puede invalidar la prioridad predeterminada al crear la regla antiphishing (que puede afectar a la prioridad de las reglas existentes).

Para cambiar la prioridad de una directiva, haga clic en **aumentar prioridad** o **disminuir prioridad** en las propiedades de la Directiva (no puede modificar directamente el número de **prioridad** en el centro de seguridad & cumplimiento). Cambiar la prioridad de una directiva solo tiene sentido si tiene varias directivas.

1. En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.

2. Seleccione la Directiva que desea modificar. Si ya está seleccionada, anule la selección y vuelva a seleccionarla.

3. Aparece el control flotante **editar el \< nombre \> de la Directiva** .

   - La Directiva antiphishing de ATP personalizada con el valor de **prioridad** **0** solo tiene el botón **disminuir prioridad** disponible.

   - La Directiva antiphishing de ATP personalizada con el valor de **prioridad** más bajo (por ejemplo, **3**) solo tiene el botón **aumentar prioridad** disponible.

   - Si tiene tres o más directivas de suplantación de identidad personalizadas, las directivas entre los valores de prioridad mayor y menor tienen los botones **aumentar prioridad** y **disminuir prioridad** disponibles.

4. Haga clic en **aumentar prioridad** o **disminuir prioridad** para cambiar el valor de **prioridad** .

5. Cuando haya terminado, haga clic en **Cerrar**.

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a>Usar el centro de seguridad & cumplimiento para ver las directivas de ATP antiphishing

1. En el centro de seguridad & cumplimiento y vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP anti-phishing**.

2. Realice uno de los pasos siguientes:

   - Seleccione una directiva antiphishing de ATP personalizada que quiera ver. Si ya está seleccionada, anule la selección y vuelva a seleccionarla.

   - Haga clic en **directiva predeterminada** para ver la Directiva contra la suplantación de identidad predeterminada.

3. Aparece el control flotante **editar el \< nombre \> de la Directiva** , donde puede ver la configuración y los valores.

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a>Usar el centro de seguridad & cumplimiento para quitar las directivas antiphishing de ATP

1. En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.

2. Seleccione la Directiva que desea quitar. Si ya está seleccionada, anule la selección y vuelva a seleccionarla.

3. En el control flotante **Editar \< el \> nombre** de la Directiva que aparece, haga clic en **eliminar Directiva**y, a continuación, haga clic en **sí** en el cuadro de diálogo de advertencia que aparece.

No puede quitar la directiva predeterminada.

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a>Usar Exchange Online PowerShell para configurar las directivas antiphishing de ATP

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Usar PowerShell para crear directivas antiphishing

La creación de una directiva contra la suplantación de identidad (phishing) en PowerShell es un proceso de dos pasos:

1. Cree la Directiva contra phish.

2. Cree la regla ANTIPHISH que especifica la Directiva antiphishing a la que se aplica la regla.

 **Notas**:

- Puede crear una nueva regla antiphishing y asignarle una directiva ANTIPHISH existente no asociada. Una regla antiphishing no puede asociarse con más de una directiva antiphishing.

- Puede configurar las siguientes opciones en nuevas directivas antiphishing en PowerShell que no están disponibles en el centro de seguridad & cumplimiento hasta que se crea la Directiva:

  - Cree la nueva directiva como deshabilitada (_habilitada_ `$false` en el cmdlet **New-AntiPhishRule** ).

  - Establezca la prioridad de la Directiva durante la creación ( _ \< número \> _de_prioridad_ ) en el cmdlet **New-AntiPhishRule** ).

- Una nueva Directiva antiphishing que cree en PowerShell no es visible en el centro de seguridad & cumplimiento hasta que asigna la Directiva a una regla antiphishing.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Paso 1: usar PowerShell para crear una directiva ANTIPHISH

Para crear una directiva contra phish, use esta sintaxis:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

En este ejemplo se crea una directiva contra phish denominada Research Quarantine con la siguiente configuración:

- La Directiva está habilitada (no se usa el parámetro _Enabled_ y el valor predeterminado es `$true` ).
- La descripción es: Research Department Policy.
- Habilita la protección de dominios de organización para todos los dominios aceptados y la protección de dominios de destino para fabrikam.com.
- Especifica el Mai Fuji (mfujito@fabrikam.com) como el usuario que se va a proteger de la suplantación.
- Habilita la inteligencia de buzones.
- Habilita la protección de inteligencia de buzones de correo y especifica la acción de cuarentena.
- Habilita las sugerencias de seguridad.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Paso 2: usar PowerShell para crear una regla contra el phish

Para crear una regla contra el phish, use esta sintaxis:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

En este ejemplo se crea una regla ANTIPHISH denominada Research Department con las siguientes condiciones:

- La regla está asociada a la Directiva ANTIPHISH denominada Research Quarantine.
- La regla se aplica a los miembros del grupo denominado Research Department.
- Como no se usa el parámetro _Priority_ , se usa la prioridad predeterminada.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).

### <a name="use-powershell-to-view-anti-phish-policies"></a>Usar PowerShell para ver las directivas ANTIPHISH

Para ver las directivas ANTIPHISH existentes, use la siguiente sintaxis:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista resumida de todas las directivas contra phish junto con las propiedades especificadas.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

En este ejemplo se devuelven todos los valores de propiedad de la Directiva ANTIPHISH denominada Executives.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).

### <a name="use-powershell-to-view-anti-phish-rules"></a>Usar PowerShell para ver las reglas ANTIPHISH

Para ver las reglas ANTIPHISH existentes, use la siguiente sintaxis:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista resumida de todas las reglas antiphishing junto con las propiedades especificadas.

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

En este ejemplo se devuelven todos los valores de propiedad de la regla antiphishing denominada ejecutivos de contoso.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Usar PowerShell para modificar las directivas ANTIPHISH

Aparte de los siguientes elementos, la misma configuración está disponible cuando se modifica una directiva ANTIPHISH en PowerShell como cuando se crea la Directiva tal como se describe en la sección [paso 1: usar PowerShell para crear una directiva ANTIPHISH](#step-1-use-powershell-to-create-an-anti-phish-policy) anteriormente en este tema.

- El modificador _MakeDefault_ que convierte la Directiva especificada en la directiva predeterminada (aplicado a todos, siempre la prioridad **más baja** y no puede eliminarla) solo está disponible cuando se modifica una directiva ANTIPHISH en PowerShell.

- No se puede cambiar el nombre de una directiva antiphishing (el cmdlet **set-AntiPhishPolicy** no tiene un parámetro _Name_ ). Al cambiar el nombre de una directiva antiphishing en el centro de seguridad & cumplimiento, sólo cambia el nombre de la _regla_antiphishing.

Para modificar una directiva contra phish, use esta sintaxis:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Usar PowerShell para modificar reglas antiphishing

La única opción que no está disponible cuando se modifica una regla antiphishing en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada. Para habilitar o deshabilitar las reglas de ANTIPHISH existentes, consulte la siguiente sección.

De lo contrario, no hay opciones de configuración adicionales disponibles cuando se modifica una regla antiphishing en PowerShell. La misma configuración está disponible cuando se crea una regla tal y como se describe en la sección [paso 2: usar PowerShell para crear una regla ANTIPHISH](#step-2-use-powershell-to-create-an-anti-phish-rule) anteriormente en este tema.

Para modificar una regla antiphishing, use esta sintaxis:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Usar PowerShell para habilitar o deshabilitar reglas antiphishing

La habilitación o deshabilitación de una regla antiphishing en PowerShell habilita o deshabilita toda la Directiva antiphishing (la regla ANTIPHISH y la Directiva de ANTIPHISH asignada). No se puede habilitar o deshabilitar la Directiva de suplantación de identidad (phishing) predeterminada (siempre se aplica a todos los destinatarios).

Para habilitar o deshabilitar una regla antiphishing en PowerShell, use esta sintaxis:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

En este ejemplo se deshabilita la regla antiphishing denominada Marketing Department.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

Este ejemplo habilita la misma regla.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) y [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Usar PowerShell para establecer la prioridad de las reglas antiphishing

El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo que se puede establecer depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.

Para establecer la prioridad de una regla anti-phish en PowerShell, use la siguiente sintaxis:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Notas**:

- Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-AntiPhishRule** en su lugar.

- La Directiva ANTIPHISH predeterminada no tiene una regla ANTIPHISH correspondiente y siempre tiene el valor de prioridad no modificable **más bajo**.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Usar PowerShell para quitar directivas antiphishing

Cuando se usa PowerShell para quitar una directiva antiphishing, no se elimina la regla antiphishing correspondiente.

Para quitar una directiva ANTIPHISH en PowerShell, use esta sintaxis:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

En este ejemplo se quita la Directiva antiphishing denominada Marketing Department.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Usar PowerShell para eliminar reglas antiphishing

Cuando se usa PowerShell para quitar una regla antiphishing, no se elimina la Directiva antiphishing correspondiente.

Para quitar una regla contra el phish en PowerShell, use esta sintaxis:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

En este ejemplo se quita la regla antiphishing denominada Marketing Department.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha configurado correctamente las directivas antiphishing de ATP, siga uno de estos pasos:

- En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**. Compruebe la lista de directivas, sus valores de **Estado** y sus valores de **prioridad** . Para ver más detalles, realice uno de los pasos siguientes:

  - Seleccione la Directiva de la lista y vea los detalles en el control flotante.
  - Haga clic en **directiva predeterminada** y vea los detalles en el control flotante.

- En Exchange Online PowerShell, reemplace \< name \> por el nombre de la Directiva o regla y ejecute el siguiente comando y Compruebe la configuración:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
