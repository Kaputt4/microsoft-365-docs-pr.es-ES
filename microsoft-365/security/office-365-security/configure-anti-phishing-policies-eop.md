---
title: Configuración de directivas contra phishing en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Los administradores pueden aprender a crear, modificar y eliminar las directivas contra suplantación de identidad que están disponibles en las organizaciones de Exchange Online Protection (EOP) con o sin buzones de Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f199cb3dbaddc47416c24a82b3066a2631641706
ms.sourcegitcommit: a7e1d155939e862337271fbe38bf26f62bd49bdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2022
ms.locfileid: "64847407"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>Configuración de directivas contra phishing en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)

En Microsoft 365 organizaciones con buzones de correo en organizaciones Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, hay una directiva predeterminada contra suplantación de identidad (phishing) que contiene un número limitado de características contra la suplantación de identidad que están habilitadas. de forma predeterminada. Para obtener más información, consulte [Configuración de suplantación de identidad en las directivas contra phishing](set-up-anti-phishing-policies.md#spoof-settings).

Los administradores pueden ver, editar y configurar (pero no eliminar) la directiva predeterminada contra phishing. Para una mayor granularidad, también puede crear directivas personalizadas contra suplantación de identidad (phishing) que se apliquen a usuarios, grupos o dominios específicos de la organización. Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.

Las organizaciones con buzones de Exchange Online pueden configurar directivas contra phishing en el portal de Microsoft 365 Defender o en Exchange Online PowerShell. Las organizaciones EOP independientes solo pueden usar el portal de Microsoft 365 Defender.

Para obtener información sobre cómo crear y modificar las directivas anti-phishing más avanzadas que están disponibles en Microsoft Defender para Office 365, consulte [Configuración de directivas anti-phishing en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md).

Los elementos básicos de una directiva contra suplantación de identidad son:

- **La directiva antifish**: especifica las protecciones de suplantación de identidad para habilitar o deshabilitar, y las acciones para aplicar opciones.
- **La regla anti phish**: especifica la prioridad y los filtros de destinatario (a los que se aplica la directiva) para una directiva anti-phish.

La diferencia entre estos dos elementos no es obvia al administrar directivas contra suplantación de identidad en el portal de Microsoft 365 Defender:

- Al crear una directiva anti-phishing, realmente está creando una regla anti-phish y la directiva anti-phish asociada al mismo tiempo con el mismo nombre para ambos.
- Al modificar una directiva de anti phishing, la configuración relacionada con el nombre, la prioridad, habilitado o deshabilitado y los filtros de destinatarios modifican la regla antifish. Todas las demás configuraciones modifican la directiva anti-phish asociada.
- Al quitar una directiva contra suplantación de identidad (phishing), se quitan la regla antiphish y la directiva anti-phish asociada.

En Exchange Online PowerShell, la directiva y la regla se administran por separado. Para obtener más información, consulte la sección [Uso de Exchange Online PowerShell para configurar directivas anti phishing](#use-exchange-online-powershell-to-configure-anti-phishing-policies) más adelante en este artículo.

Cada organización tiene una directiva anti phishing integrada denominada Office365 AntiPhish Default que tiene estas propiedades:

- La directiva se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla anti phish (filtros de destinatarios) asociada a la directiva.
- La directiva tiene un valor de prioridad personalizado **Mínimo** que no se puede modificar (la directiva siempre se aplica en último lugar). Las directivas personalizadas que cree siempre tendrán una prioridad mayor.
- La directiva es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar esta directiva predeterminada.

Para aumentar la eficacia de la protección contra suplantación de identidad (phishing), puede crear directivas personalizadas contra suplantación de identidad (phishing) con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Anti-phishing** , use <https://security.microsoft.com/antiphishing>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

  No se pueden administrar directivas de anti phishing en PowerShell de EOP independiente.

- Debe tener permisos asignados en la **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para agregar, modificar y eliminar directivas contra phishing, debe ser miembro de los grupos de roles Administración de la **organización** o **Administrador de seguridad** .
  - Para el acceso de solo lectura a las directivas contra phishing, debe ser miembro de los grupos de roles **Lector global** o **Lector de seguridad** .

  Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - La adición de usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365. Para obtener más información, consulte [Acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo **de roles View-Only Organization Management** de [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica <sup>\*</sup>.

- Para ver nuestra configuración recomendada para las directivas contra suplantación de identidad (phishing), consulte [Configuración de directivas contra suplantación de identidad (EOP](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)).

- Espere hasta 30 minutos para que se aplique la directiva actualizada.

- Para obtener información sobre dónde se aplican las directivas contra phishing en la canalización de filtrado, consulte [Orden y prioridad de la protección por correo electrónico](how-policies-and-protections-are-combined.md).

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a>Uso del portal de Microsoft 365 Defender para crear directivas contra suplantación de identidad

La creación de una directiva de anti-phishing personalizada en el portal de Microsoft 365 Defender crea la regla antiphish y la directiva anti-phish asociada al mismo tiempo con el mismo nombre para ambos.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas de colaboración** \> & correo electrónico **& Directivas** de **amenazas** \> de reglas \> **Anti-phishing** en la sección **Directivas**. Para ir directamente a la página **Anti-phishing** , use <https://security.microsoft.com/antiphishing>.

2. En la página **Anti-phishing** , haga clic en ![el icono Crear.](../../media/m365-cc-sc-create-icon.png) **Create**.

3. Se abrirá el asistente para directivas. En la página **Nombre de directiva** , configure estas opciones:
   - **Nombre**: escriba un nombre único y descriptivo para la directiva.
   - **Descripción**: escriba una descripción opcional para la directiva.

   Cuando termine, haga clic en **Siguiente**.

4. En la página **Usuarios, grupos y dominios** que aparece, identifique los destinatarios internos a los que se aplica la directiva (condiciones de destinatario):
   - **Usuarios**: buzones, usuarios de correo o contactos de correo especificados.
   - **Grupos**:
     - Miembros de los grupos de distribución especificados o grupos de seguridad habilitados para correo.
     - El Grupos de Microsoft 365 especificado.
   - **Dominios**: todos los destinatarios de los [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados en la organización.

   Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados. Repita este proceso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

   Para los usuarios o grupos, puede utilizar la mayoría de los identificadores (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de la cuenta, etc.), pero el nombre para mostrar correspondiente se muestra en los resultados. Para los usuarios, introduzca un asterisco (\*) por sí mismo para ver todos los valores disponibles.

   Varios valores en la misma condición usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Hay diferentes condiciones que usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

   - **Excluir estos usuarios, grupos y dominios**: para agregar excepciones para los destinatarios internos a los que se aplica la directiva (excepciones de destinatarios), seleccione esta opción y configure las excepciones. La configuración y el comportamiento son exactamente iguales a las condiciones.

   Cuando termine, haga clic en **Siguiente**.

5. En la página **Umbral de suplantación de identidad & protección** que aparece, use la casilla **Habilitar inteligencia de suplantación** de identidad para activar o desactivar la inteligencia suplantada. El valor predeterminado está activado (seleccionado) y se recomienda dejarlo activado. Configure la acción para realizar los mensajes falsificados bloqueados en la página siguiente.

   Para desactivar la inteligencia de suplantación de identidad, desactive la casilla.

   > [!NOTE]
   > No es necesario desactivar la protección contra la suplantación de identidad si el registro MX no apunta a Microsoft 365; en su lugar, habilita filtrado mejorado para conectores. Para obtener instrucciones, consulte [Filtrado mejorado para conectores en Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   Cuando termine, haga clic en **Siguiente**.

6. En la página **Acciones** que aparece, configure las opciones siguientes:
   - **Si el mensaje se detecta como suplantación de identidad**: esta configuración solo está disponible si seleccionó **Habilitar inteligencia de suplantación de identidad** en la página anterior. Seleccione una de las siguientes acciones en la lista desplegable para los mensajes de remitentes falsificados bloqueados:
     - **Mover el mensaje a las carpetas de correo no deseado de los destinatarios**
     - **Poner en cuarentena el mensaje**: si selecciona esta acción, aparece un cuadro **Aplicar directiva de cuarentena** donde se selecciona la directiva de cuarentena que se aplica a los mensajes que están en cuarentena mediante la protección de inteligencia de suplantación de identidad. Las directivas de cuarentena definen qué pueden hacer los usuarios en los mensajes en cuarentena y si los usuarios reciben notificaciones de cuarentena. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).

       Un valor en blanco **Aplicar directiva de cuarentena** significa que se usa la directiva de cuarentena predeterminada (DefaultFullAccessPolicy para las detecciones de inteligencia de suplantación de identidad). Cuando más adelante edite la directiva contra suplantación de identidad (phishing) o vea la configuración, se muestra el nombre predeterminado de la directiva de cuarentena. Para obtener más información sobre las directivas de cuarentena predeterminadas que se usan para veredictos de filtrado de protección admitidos, consulte [esta tabla](quarantine-policies.md#step-2-assign-a-quarantine-policy-to-supported-features).

   - **Consejos de seguridad & indicadores**:
     - **Mostrar la primera consejo de seguridad de contactos**: para obtener más información, consulte [Primera consejo de seguridad de contactos](set-up-anti-phishing-policies.md#first-contact-safety-tip).
     - **Mostrar (?) para remitentes no autenticados para suplantación de identidad**<sup>\*</sup>: agrega un signo de interrogación (?) a la foto del remitente en el cuadro De en Outlook si el mensaje no pasa comprobaciones SPF o DKIM **y** el mensaje no pasa dmARC o [autenticación compuesta](email-validation-and-authentication.md#composite-authentication).
     - **Mostrar etiqueta**<sup>\*</sup> "via": agrega una etiqueta via (chris@contoso.com a través de fabrikam.com) a la dirección From si es diferente del dominio de la firma DKIM o de la dirección **MAIL FROM** .

     Para activar una configuración, active la casilla . Para desactivarlo, desactive la casilla.

     <sup>\*</sup> Esta configuración solo está disponible si seleccionó **Habilitar inteligencia de suplantación de identidad** en la página anterior. Para obtener más información, vea [Remitente no autenticado](set-up-anti-phishing-policies.md#unauthenticated-sender).

   Cuando termine, haga clic en **Siguiente**.

7. En la página **Revisar** que aparece, revise la configuración. Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Enviar**.

8. En la página de confirmación que aparece, haga clic en **Listo**.

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a>Uso del portal de Microsoft 365 Defender para ver las directivas contra suplantación de identidad

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas de colaboración** \> & correo electrónico **& Directivas** de **amenazas** \> de reglas \> **Anti-phishing** en la sección **Directivas**. Para ir directamente a la página **Anti-phishing** , use <https://security.microsoft.com/antiphishing>.

2. En la página **Anti-phishing** , se muestran las siguientes propiedades en la lista de directivas:

   - **Nombre**
   - **Estado**
   - **Prioridad**
   - **Última modificación**

3. Al seleccionar una directiva haciendo clic en el nombre, la configuración de la directiva se muestra en un control flotante.

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a>Uso del portal de Microsoft 365 Defender para modificar las directivas contra suplantación de identidad

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas de colaboración** \> & correo electrónico **& Directivas** de **amenazas** \> de reglas \> **Anti-phishing** en la sección **Directivas**. Para ir directamente a la página **Anti-phishing** , use <https://security.microsoft.com/antiphishing>.

2. En la página **Anti-phishing** , seleccione una directiva de la lista haciendo clic en el nombre.

3. En el control flotante de detalles de la directiva que aparece, seleccione **Editar** en cada sección para modificar la configuración dentro de la sección. Para obtener más información sobre la configuración, consulte [la sección Uso del portal de Microsoft 365 Defender para crear directivas contra phishing](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) anteriormente en este artículo.

   Para la directiva de anti phishing predeterminada, la sección **Usuarios, grupos y dominios** no está disponible (la directiva se aplica a todos) y no se puede cambiar el nombre de la directiva.

Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la directiva, consulte las secciones siguientes.

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Habilitación o deshabilitación de directivas personalizadas contra suplantación de identidad

No se puede deshabilitar la directiva de anti phishing predeterminada.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas de colaboración** \> & correo electrónico **& Directivas** de **amenazas** \> de reglas \> **Anti-phishing** en la sección **Directivas**. Para ir directamente a la página **Anti-phishing** , use <https://security.microsoft.com/antiphishing>.

2. En la página **Anti-phishing** , seleccione una directiva personalizada en la lista haciendo clic en el nombre.

3. En la parte superior del control flotante de detalles de la directiva que aparece, verá uno de los siguientes valores:
   - **Directiva desactivada**: para activar la directiva, haga clic en ![icono Activar.](../../media/m365-cc-sc-turn-on-off-icon.png) **Activar** .
   - **Directiva activada**: para desactivar la directiva, haga clic en el ![Icono Desactivar](../../media/m365-cc-sc-turn-on-off-icon.png) **Desactivar**.

4. En el cuadro de diálogo de confirmación que aparece, haga clic **Activar** o **Desactivar**.

5. Haga clic en **Cerrar** en el control flotante de detalles de la directiva.

De nuevo en la página principal de la directiva, el valor **Estado** de la directiva estará **Activado** o **Desactivado**.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>Establecer la prioridad de las directivas de anti-phishing personalizadas

De forma predeterminada, las directivas contra phishing tienen una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen una prioridad menor que las directivas anteriores). Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor). Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

Para cambiar la prioridad de una directiva, haga clic en **Aumentar prioridad** o **Reducir prioridad** en las propiedades de la directiva (no puede modificar directamente el número de **Prioridad** en el portal de Microsoft 365 Defender). Cambiar la prioridad de una directiva sólo tiene sentido si tiene varias directivas.

 **Notas**:

- En el portal de Microsoft 365 Defender, solo puede cambiar la prioridad de la directiva contra suplantación de identidad después de crearla. En PowerShell, puede invalidar la prioridad predeterminada al crear la regla anti phish (que puede afectar a la prioridad de las reglas existentes).
- Las directivas contra phishing se procesan en el orden en que se muestran (la primera directiva tiene el valor **de prioridad** 0). La directiva de anti phishing predeterminada tiene el valor de prioridad **Más bajo** y no se puede cambiar.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas de colaboración** \> & correo electrónico **& Directivas** de **amenazas** \> de reglas \> **Anti-phishing** en la sección **Directivas**. Para ir directamente a la página **Anti-phishing** , use <https://security.microsoft.com/antiphishing>.

2. En la página **Anti-phishing** , seleccione una directiva personalizada en la lista haciendo clic en el nombre.

3. En la parte superior del control flotante de detalles de la directiva que aparece, verá **Aumentar la prioridad** o **Disminuir la prioridad** en función del valor de prioridad actual y del número de directivas personalizadas:
   - La directiva con el valor **De prioridad** **0** solo tiene la opción **Reducir prioridad** disponible.
   - La directiva con el valor **de prioridad** más bajo (por ejemplo, **3**) solo tiene la opción **Aumentar prioridad** disponible.
   - Si tiene tres o más directivas, las directivas entre los valores de prioridad más altos y más bajos tienen disponibles las opciones **Aumentar prioridad** y **Reducir prioridad** .

   Haga clic en el ![Icono Aumentar la prioridad.](../../media/m365-cc-sc-increase-icon.png) **Aumentar la prioridad** o en el ![Icono Disminuir la prioridad](../../media/m365-cc-sc-decrease-icon.png) **Reducir la prioridad** para cambiar el valor de **Prioridad**.

4. Cuando haya terminado, haga clic en **Cerrar** en el control flotante de detalles de la directiva.

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a>Uso del portal de Microsoft 365 Defender para quitar directivas de anti phishing personalizadas

Cuando se usa el portal de Microsoft 365 Defender para quitar una directiva antiphish personalizada, se eliminan la regla antiphish y la directiva anti-phish correspondiente. No puede quitar la directiva de anti-phishing predeterminada.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas de colaboración** \> & correo electrónico **& Directivas** de **amenazas** \> de reglas \> **Anti-phishing** en la sección **Directivas**. Para ir directamente a la página **Anti-phishing** , use <https://security.microsoft.com/antiphishing>.

2. En la página **Anti-phishing** , seleccione una directiva personalizada en la lista haciendo clic en el nombre.

3. En la parte superior del control flotante de detalles de la directiva que aparece, haga clic en ![icono Más acciones.](../../media/m365-cc-sc-more-actions-icon.png) **Más acciones** \> ![Icono Eliminar directiva](../../media/m365-cc-sc-delete-icon.png)**Eliminar directiva**.

4. En el cuadro de diálogo de confirmación que aparece, haga clic en **Sí**.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Uso de Exchange Online PowerShell para configurar directivas anti phishing

Como se describió anteriormente, una directiva anti-phishing consta de una directiva anti-phish y una regla anti-phish.

En Exchange Online PowerShell, la diferencia entre las directivas anti phish y las reglas anti-phish es evidente. Las directivas antifish se administran mediante los **\*cmdlets -AntiPhishPolicy** y se administran las reglas antifish mediante los **\*cmdlets -AntiPhishRule** .

- En PowerShell, primero se crea la directiva anti phish y, a continuación, se crea la regla anti phish que identifica la directiva a la que se aplica la regla.
- En PowerShell, se modifica la configuración de la directiva anti phish y la regla anti phish por separado.
- Al quitar una directiva anti phish de PowerShell, la regla anti phish correspondiente no se quita automáticamente y viceversa.

> [!NOTE]
> Los siguientes procedimientos de PowerShell no están disponibles en organizaciones EOP independientes que usan Exchange Online Protection PowerShell.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Uso de PowerShell para crear directivas contra suplantación de identidad

La creación de una directiva contra phishing en PowerShell es un proceso de dos pasos:

1. Cree la directiva anti-phish.
2. Cree la regla anti phish que especifica la directiva anti phish a la que se aplica la regla.

 **Notas**:

- Puede crear una nueva regla anti phish y asignarle una directiva anti-phish existente y no asociada. Una regla anti phish no se puede asociar a más de una directiva anti-phish.

- Puede configurar las siguientes opciones en nuevas directivas anti phish en PowerShell que no estén disponibles en el portal de Microsoft 365 Defender hasta que haya creado la directiva:

  - Cree la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-AntiPhishRule** ).
  - Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_) en el cmdlet **New-AntiPhishRule** ).

- Una nueva directiva anti phish que cree en PowerShell no será visible en el portal de Microsoft 365 Defender hasta que asigne la directiva a una regla anti phish.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Paso 1: Uso de PowerShell para crear una directiva antiphish

Para crear una directiva anti phish, use esta sintaxis:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>] [-SpoofQuarantineTag <QuarantineTagName>]
```

En este ejemplo se crea una directiva anti phish denominada Cuarentena de investigación con la siguiente configuración:

- La descripción es: Directiva del departamento de investigación.
- Cambia la acción predeterminada para las detecciones de suplantación a Cuarentena y usa la [directiva de cuarentena](quarantine-policies.md) predeterminada para los mensajes en cuarentena (no se usa el parámetro _SpoofQuarantineTag_ ).

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).

> [!NOTE]
> Para obtener instrucciones detalladas para especificar las [directivas de cuarentena](quarantine-policies.md) que se usarán en una directiva antiphish, consulte [Uso de PowerShell para especificar la directiva de cuarentena en las directivas contra suplantación de identidad (phishing).](quarantine-policies.md#anti-phishing-policies)

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Paso 2: Uso de PowerShell para crear una regla antiphish

Para crear una regla anti phish, use esta sintaxis:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

En este ejemplo se crea una regla anti phish denominada Departamento de investigación con las condiciones siguientes:

- La regla está asociada a la directiva anti-phish denominada Cuarentena de investigación.
- La regla se aplica a los miembros del grupo denominado Research Department.
- Dado que no se usa el parámetro _Priority_ , se usa la prioridad predeterminada.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).

### <a name="use-powershell-to-view-anti-phish-policies"></a>Uso de PowerShell para ver directivas antiphish

Para ver las directivas anti phish existentes, use la sintaxis siguiente:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista de resumen de todas las directivas antifish junto con las propiedades especificadas.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

En este ejemplo se devuelven todos los valores de propiedad de la directiva anti phish denominada Executives.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).

### <a name="use-powershell-to-view-anti-phish-rules"></a>Uso de PowerShell para ver las reglas antiphish

Para ver las reglas anti phish existentes, use la sintaxis siguiente:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista de resumen de todas las reglas antifish junto con las propiedades especificadas.

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

En este ejemplo se devuelven todos los valores de propiedad de la regla anti phish denominada Contoso Executives.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Uso de PowerShell para modificar directivas antiphish

Aparte de los siguientes elementos, la misma configuración está disponible cuando se modifica una directiva anti phish en PowerShell como cuando se crea una directiva como se describe en [Paso 1: Uso de PowerShell para crear una directiva anti phish](#step-1-use-powershell-to-create-an-anti-phish-policy) anteriormente en este artículo.

- El modificador _MakeDefault_ que convierte la directiva especificada en la directiva predeterminada (aplicada a todos, siempre prioridad **más baja** y no se puede eliminar) solo está disponible cuando se modifica una directiva anti phish en PowerShell.
- No se puede cambiar el nombre de una directiva antifish (el cmdlet **Set-AntiPhishPolicy** no tiene ningún parámetro _Name_ ). Al cambiar el nombre de una directiva anti-phishing en el portal de Microsoft 365 Defender, solo se cambia el nombre de la _regla_ antiphish.

Para modificar una directiva anti phish, use esta sintaxis:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).

> [!NOTE]
> Para obtener instrucciones detalladas para especificar la [directiva de cuarentena](quarantine-policies.md) que se usará en una directiva antiphish, consulte [Uso de PowerShell para especificar la directiva de cuarentena en las directivas contra suplantación de identidad (phishing).](quarantine-policies.md#anti-phishing-policies)

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Uso de PowerShell para modificar reglas antiphish

La única configuración que no está disponible al modificar una regla antiphish en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada. Para habilitar o deshabilitar las reglas antifish existentes, consulte la sección siguiente.

De lo contrario, la misma configuración está disponible al crear una regla como se describe en la sección [Paso 2: Uso de PowerShell para crear una regla antiphish](#step-2-use-powershell-to-create-an-anti-phish-rule) anteriormente en este artículo.

Para modificar una regla antiphish, use esta sintaxis:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Uso de PowerShell para habilitar o deshabilitar reglas antifish

La habilitación o deshabilitación de una regla antifish en PowerShell habilita o deshabilita toda la directiva contra suplantación de identidad (la regla antifish y la directiva antifish asignada). No se puede habilitar ni deshabilitar la directiva de anti phishing predeterminada (siempre se aplica a todos los destinatarios).

Para habilitar o deshabilitar una regla antifish en PowerShell, use esta sintaxis:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

En este ejemplo se deshabilita la regla anti-phish denominada Departamento de marketing.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

Este ejemplo habilita la misma regla.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) y [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Uso de PowerShell para establecer la prioridad de las reglas antiphish

El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.

Para establecer la prioridad de una regla anti phish en PowerShell, use la sintaxis siguiente:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

En el ejemplo siguiente, la prioridad de la regla denominada "Marketing Department" se establece en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Notas**:

- Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-AntiPhishRule** en su lugar.
- La directiva antifish predeterminada no tiene una regla antifish correspondiente y siempre tiene el valor de prioridad no modificable **Más bajo**.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Uso de PowerShell para quitar directivas antiphish

Cuando se usa PowerShell para quitar una directiva antiphish, no se quita la regla anti phish correspondiente.

Para quitar una directiva anti phish en PowerShell, use esta sintaxis:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

En este ejemplo se quita la directiva anti-phish denominada Departamento de marketing.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Uso de PowerShell para quitar reglas antiphish

Cuando se usa PowerShell para quitar una regla anti phish, no se quita la directiva anti phish correspondiente.

Para quitar una regla anti phish en PowerShell, use esta sintaxis:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

En este ejemplo se quita la regla anti-phish denominada Departamento de marketing.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha configurado correctamente las directivas de anti phishing en EOP, realice cualquiera de los pasos siguientes:

- En la página **Anti-phishing** del portal de Microsoft 365 Defender en <https://security.microsoft.com/antiphishing>, compruebe la lista de directivas, sus valores **de estado** y sus valores **de prioridad**. Para ver más detalles, seleccione la directiva de la lista haciendo clic en el nombre y viendo los detalles en el control flotante que aparece.

- En Exchange Online PowerShell, reemplace por \<Name\> el nombre de la directiva o regla, ejecute el siguiente comando y compruebe la configuración:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
