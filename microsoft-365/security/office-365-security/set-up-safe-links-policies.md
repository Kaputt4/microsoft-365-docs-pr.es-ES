---
title: Configurar directivas Caja fuerte vínculos en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a ver, crear, modificar y eliminar directivas de vínculos de Caja fuerte y configuración global de vínculos de Caja fuerte en Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8d42051d2ca4f26758cbe7334d427f3f93178f97
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108216"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Configurar directivas Caja fuerte vínculos en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](defender-for-office-365.md). Si es un usuario principal que busca información sobre safelinks en Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Caja fuerte Los vínculos de [Microsoft Defender para Office 365](defender-for-office-365.md) proporcionan el examen de direcciones URL de los mensajes de correo electrónico entrantes en el flujo de correo y el momento de la comprobación de clics de direcciones URL y vínculos en mensajes de correo electrónico y en otras ubicaciones. Para obtener más información, [vea Caja fuerte Links in Microsoft Defender for Office 365](safe-links.md).

No hay ninguna directiva de vínculos integrada o Caja fuerte predeterminada. Para obtener Caja fuerte de vínculos de búsqueda de direcciones URL, debe crear una o más directivas de vínculos de Caja fuerte como se describe en este artículo.

> [!NOTE]
>
> Puede configurar la configuración global para la protección de Caja fuerte de vínculos **fuera** de Caja fuerte directivas de vínculos. Para obtener instrucciones, vea [Configure global settings for Caja fuerte Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).
>
> Los administradores deben tener en cuenta las diferentes opciones de configuración para Caja fuerte vínculos. Una de las opciones disponibles es incluir información de identificación del usuario en Caja fuerte vínculos. Esta característica permite a los *equipos de Operaciones* de seguridad investigar posibles riesgos de usuario, tomar medidas correctivas y limitar infracciones costosas.

Puede configurar directivas de vínculos de Caja fuerte en el portal de Microsoft 365 Defender o en PowerShell (powershell de Exchange Online para organizaciones de Microsoft 365 elegibles con buzones en Exchange Online; PowerShell EOP independiente para organizaciones sin buzones de Exchange Online, pero con Microsoft Defender para suscripciones de complemento Office 365).

Los elementos básicos de una directiva Caja fuerte links son:

- La directiva de vínculos **seguros:** active la protección de vínculos de Caja fuerte, active la detección de direcciones URL en tiempo real, especifique si debe esperar a que se complete el examen en tiempo real antes de entregar el mensaje, activar el examen de mensajes internos, especificar si se debe realizar un seguimiento de los clics de usuario en las direcciones URL y especificar si se permite a los usuarios hacer clic en la url original.
- **La regla de vínculos seguros:** especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva).

La diferencia entre estos dos elementos no es obvia cuando se administran directivas de vínculos Caja fuerte en el portal de Microsoft 365 Defender web:

- Al crear una directiva Caja fuerte vínculos, en realidad está creando una regla de vínculos seguros y la directiva de vínculos seguros asociada al mismo tiempo con el mismo nombre para ambos.
- Al modificar una directiva Caja fuerte vínculos, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada y los filtros de destinatarios modifican la regla de vínculos seguros. Todas las demás opciones modifican la directiva de vínculos seguros asociada.
- Al quitar una directiva de vínculos Caja fuerte, se quitan la regla de vínculos seguros y la directiva de vínculos seguros asociada.

En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado. Para obtener más información, vea la sección [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Caja fuerte Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) más adelante en este artículo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com/>. Para ir directamente a la **página Caja fuerte vínculos,** use <https://security.microsoft.com/safelinksv2> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener asignados permisos antes de poder realizar los procedimientos descritos en este artículo:
  - Para crear, modificar y eliminar directivas de vínculos de Caja fuerte, debe  ser miembro de los grupos de roles Administración  de la organización o Administrador de seguridad en el **portal** de Microsoft 365 Defender y miembro del grupo de roles Administración de la organización en Exchange Online. 
  - Para obtener acceso de solo lectura a Caja fuerte de vínculos, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.

  Para obtener más información, vea [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Agregar usuarios al rol Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el _portal_ de Microsoft 365 Defender y permisos para otras características de Microsoft 365. Para obtener más información, vea [Asignar roles de administrador](../../admin/add-users/about-admin-roles.md).
  . - El **grupo de roles Administración** de la organización de solo vista [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para obtener información sobre la configuración recomendada para Caja fuerte de vínculos, [consulte Caja fuerte configuración de directiva de vínculos.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)

- Permitir hasta 30 minutos para que se aplique una directiva nueva o actualizada.

- [Las nuevas características se agregan continuamente a Microsoft Defender para Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365). A medida que se agregan nuevas características, es posible que deba realizar ajustes en las directivas de vínculos de Caja fuerte existentes.

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a>Usar el portal Microsoft 365 Defender para crear directivas Caja fuerte vínculos

La creación de una directiva Caja fuerte links personalizada en el portal de Microsoft 365 Defender crea la regla de vínculos seguros y la directiva de vínculos seguros asociada al mismo tiempo con el mismo nombre para ambos.

1. En el portal Microsoft 365 Defender, vaya **a Directivas &** de directivas de amenazas sección Directivas \>  \> **de** amenazas \> **Caja fuerte Vínculos**.

2. En la **página Caja fuerte,** haga clic ![ en Crear icono ](../../media/m365-cc-sc-create-icon.png) **Crear**.

3. Se **abrirá el Asistente para Caja fuerte de directivas de nuevos** vínculos. En la **página Nombre de la directiva,** configure las siguientes opciones:

   - **Nombre**: escriba un nombre único y descriptivo para la directiva.
   - **Descripción**: escriba una descripción opcional para la directiva.

   Cuando termine, haga clic en **Siguiente**.

4. En la **página Usuarios y dominios** que aparece, identifique los destinatarios internos a los que se aplica la directiva (condiciones de destinatario):
   - **Usuarios**: los buzones, usuarios de correo o contactos de correo especificados de su organización.
   - **Grupos**: los grupos de distribución, los grupos de seguridad habilitados para correo electrónico o los Grupos de Microsoft 365 especificados de la organización.
   - **Dominios**: todos los destinatarios de los [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados en la organización.

   Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados. Repita este proceso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono de quitar](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

   Para los usuarios o grupos, puede usar la mayoría de los identificadores (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de cuenta, etc.), pero el nombre para mostrar correspondiente se muestra en los resultados. Para los usuarios, escriba un asterisco (\*) para ver todos los valores disponibles.

   Varios valores en la misma condición usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Hay diferentes condiciones que usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

   - **Excluir estos usuarios,** grupos y dominios: para agregar excepciones para los destinatarios internos a los que se aplica la directiva (excepciones de destinatarios), seleccione esta opción y configure las excepciones. La configuración y el comportamiento se muestran exactamente igual que las condiciones.

   Cuando termine, haga clic en **Siguiente**.

5. En la **página Configuración de** protección que aparece, configure las siguientes opciones:
   - **Seleccione la acción para direcciones** URL potencialmente  malintencionadas desconocidas en mensajes: seleccione Activar para habilitar la protección de vínculos de Caja fuerte para vínculos en mensajes de correo electrónico. Si activa esta configuración, estará disponible la siguiente configuración:
     - **Aplicar análisis de direcciones URL** en tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos: seleccione esta opción para habilitar el examen en tiempo real de vínculos en mensajes de correo electrónico. Si activa esta opción en la siguiente configuración, estará disponible:
       - **Espere a que se** complete el examen de direcciones URL antes de entregar el mensaje: seleccione esta opción para esperar a que se complete el examen de direcciones URL en tiempo real antes de entregar el mensaje.
     - **Aplicar Caja fuerte vínculos** a mensajes de correo electrónico enviados dentro de la organización: seleccione esta opción para aplicar la directiva de vínculos de Caja fuerte a los mensajes entre remitentes internos y destinatarios internos.
   - **Seleccione la acción para direcciones** URL desconocidas o  potencialmente malintencionadas dentro de Microsoft Teams : Seleccione Activar para habilitar la protección de vínculos de Caja fuerte para vínculos de Teams.
   - **No realizar un seguimiento de los clics del** usuario: deje esta configuración sin elegir para habilitar los clics de usuario de seguimiento en las direcciones URL de los mensajes de correo electrónico.
   - **No permitir que los usuarios hagan clic en** la dirección URL original: seleccione esta opción para impedir que los usuarios hagan clic en la dirección URL original en las páginas de [advertencia.](safe-links.md#warning-pages-from-safe-links)
   - **No vuelva a escribir las** siguientes direcciones URL: permite obtener acceso a las direcciones URL especificadas que, de lo contrario, se bloquearían mediante Caja fuerte vínculos.

     En el cuadro, escriba la dirección URL o el valor que desee y, a continuación, haga clic en **Agregar**. Repita este paso tantas veces como sea necesario.

     Para quitar una entrada existente, haga clic en ![Icono de quitar](../../media/m365-cc-sc-remove-selection-icon.png) junto a la entrada.

     Para obtener sintaxis de entrada, vea Sintaxis de entrada para la lista "No volver a [escribir las siguientes direcciones URL".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)

   Para obtener información detallada acerca de esta configuración, consulte [Caja fuerte links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and Caja fuerte Links settings for [Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).

   Para obtener más información sobre los valores recomendados para la configuración de directivas estándar y estricta, consulte [Caja fuerte configuración de directiva de vínculos](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).

   Cuando termine, haga clic en **Siguiente**.

6. En la **página Notificación** que aparece, seleccione uno de los siguientes valores para ¿Cómo desea notificar a **los usuarios?**:
   - **Usar el texto de notificación predeterminado**
   - **Usar texto de notificación** personalizado: si selecciona este valor (la longitud no puede superar los 200 caracteres), aparecerá la siguiente configuración:
     - **Usar Traductor de Microsoft para la localización automática**
     - **Texto de notificación personalizado:** escriba el texto de notificación personalizado en este cuadro.

   Cuando termine, haga clic en **Siguiente**.

7. En la página **Revisar** que aparece, revise la configuración. Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Enviar**.

8. En la página de confirmación que aparece, haga clic en **Listo**.

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a>Usar el portal de Microsoft 365 Defender para ver directivas Caja fuerte vínculos

1. En el portal Microsoft 365 Defender, vaya **a Directivas &** de directivas de amenazas sección Directivas \>  \> **de** amenazas \> **Caja fuerte Vínculos**.

2. En la **página Caja fuerte vínculos,** se muestran las siguientes propiedades en la lista de directivas Caja fuerte vínculos:
   - **Nombre**
   - **Estado**
   - **Prioridad**

3. Al seleccionar una directiva haciendo clic en el nombre, la configuración de la directiva se muestra en un menú desplegable.

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a>Usar el portal Microsoft 365 Defender para modificar las directivas Caja fuerte vínculos

1. En el portal Microsoft 365 Defender, vaya **a Directivas &** de directivas de amenazas sección Directivas \>  \> **de** amenazas \> **Caja fuerte Vínculos**.

2. En la **Caja fuerte vínculos,** seleccione una directiva de la lista haciendo clic en el nombre.

3. En el control flotante de detalles de la directiva que aparece, seleccione **Editar** en cada sección para modificar la configuración dentro de la sección. Para obtener más información acerca de la configuración, vea la sección anterior Use [the Microsoft 365 Defender portal to create Caja fuerte Links policies](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) en este artículo.  

Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la directiva, consulte las secciones siguientes.

### <a name="enable-or-disable-safe-links-policies"></a>Habilitar o deshabilitar directivas Caja fuerte vínculos

1. En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  \>  \> **Caja fuerte vínculos**.

2. En la **Caja fuerte vínculos,** seleccione una directiva de la lista haciendo clic en el nombre.

3. En la parte superior del control flotante de detalles de la directiva que aparece, verá uno de los siguientes valores:
   - **Directiva desactivada**: para activar la directiva, haga clic en el ![Icono Activar](../../media/m365-cc-sc-turn-on-off-icon.png) **Activar**.
   - **Directiva activada**: Para desactivar la directiva, haga clic en el ![Icono desactivar](../../media/m365-cc-sc-turn-on-off-icon.png) y **Desactivar**.

4. En el cuadro de diálogo de confirmación que aparece, haga clic **Activar** o **Desactivar**.

5. Haga clic en **Cerrar** en el control flotante de detalles de la directiva.

De nuevo en la página principal de la directiva, el valor **Estado** de la directiva estará **Activado** o **Desactivado**.

### <a name="set-the-priority-of-safe-links-policies"></a>Establecer la prioridad de las directivas Caja fuerte vínculos

De forma predeterminada, Caja fuerte a los vínculos se les da una prioridad que se basa en el orden en que se crearon (las directivas más recientes son de menor prioridad que las directivas anteriores). Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor). Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

Para cambiar la prioridad de una directiva, haga clic en **Aumentar la prioridad** o en **Reducir la prioridad** en las propiedades de la directiva (no se puede modificar directamente el número de **Prioridad** en el portal de Microsoft 365 Defender). Cambiar la prioridad de una directiva solo tiene sentido si tiene varias directivas.

**Nota**:

- En el portal Microsoft 365 Defender, solo puede cambiar la prioridad de la directiva de vínculos de Caja fuerte después de crearla. En PowerShell, puede invalidar la prioridad predeterminada al crear la regla de vínculos seguros (lo que puede afectar a la prioridad de las reglas existentes).
- Caja fuerte Las directivas de vínculos se procesan en el orden en que se muestran (la primera directiva tiene el **valor de** prioridad 0). Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).

1. En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  \>  \> **Caja fuerte vínculos**.

2. En la **Caja fuerte vínculos,** seleccione una directiva de la lista haciendo clic en el nombre.

3. En la parte superior del control flotante de detalles de la directiva que aparece, verá **Aumentar la prioridad** o **Disminuir la prioridad** en función del valor de prioridad actual y del número de directivas personalizadas:
   - La directiva con el **valor de prioridad** **0** solo tiene disponible la **opción Disminuir** prioridad.
   - La directiva con el valor **de prioridad** más bajo (por ejemplo, **3**) solo tiene disponible **la opción Aumentar** prioridad.
   - Si tiene tres o más directivas, las directivas entre los valores de prioridad más alta y más baja tienen disponibles las opciones **Aumentar** prioridad y **Disminuir** prioridad.

   Haga clic en el ![Icono Aumentar la prioridad](../../media/m365-cc-sc-increase-icon.png) **Aumentar la prioridad** o en el ![Icono Disminuir la prioridad](../../media/m365-cc-sc-decrease-icon.png) **Reducir la prioridad** para cambiar el valor de **Prioridad**.

4. Cuando haya terminado, haga clic en **Cerrar** en el control flotante de detalles de la directiva.

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a>Usar el portal Microsoft 365 Defender para quitar directivas Caja fuerte vínculos

1. En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  \>  \> **Caja fuerte vínculos**.

2. En la **Caja fuerte vínculos,** seleccione una directiva de la lista haciendo clic en el nombre. En la parte superior del control flotante de detalles de la directiva que aparece, haga clic en el ![Icono Más acciones](../../media/m365-cc-sc-more-actions-icon.png) **Más acciones** \> ![Icono Eliminar directiva](../../media/m365-cc-sc-delete-icon.png) **Eliminar directiva**.

3. En el cuadro de diálogo de confirmación que aparece, haga clic en **Sí**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Usar Exchange Online PowerShell o PowerShell independiente de EOP para configurar directivas Caja fuerte vínculos

Como se describió anteriormente, una directiva Caja fuerte links consiste en una directiva de vínculos seguros y una regla de vínculos seguros.

En PowerShell, la diferencia entre las directivas de vínculos seguros y las reglas de vínculos seguros es aparente. Las directivas de vínculos seguros se administran mediante los cmdlets **\* -SafeLinksPolicy** y se administran reglas de vínculos seguros mediante los cmdlets **\* -SafeLinksRule.**

- En PowerShell, primero se crea la directiva de vínculos seguros y, a continuación, se crea la regla de vínculos seguros que identifica la directiva a la que se aplica la regla.
- En PowerShell, se modifica la configuración de la directiva de vínculos seguros y la regla de vínculos seguros por separado.
- Al quitar una directiva de vínculos seguros de PowerShell, la regla de vínculos seguros correspondiente no se quita automáticamente y viceversa.

### <a name="use-powershell-to-create-safe-links-policies"></a>Usar PowerShell para crear directivas Caja fuerte vínculos

Crear una directiva Caja fuerte vínculos en PowerShell es un proceso de dos pasos:

1. Cree la directiva de vínculos seguros.
2. Cree la regla de vínculos seguros que especifica la directiva de vínculos seguros a la que se aplica la regla.

> [!NOTE]
>
> - Puede crear una nueva regla de vínculos seguros y asignarle una directiva de vínculos seguros existente y sin asociar. Una regla de vínculos seguros no se puede asociar a más de una directiva de vínculos seguros.
>
> - Puede configurar las siguientes opciones en nuevas directivas de vínculos seguros en PowerShell que no estén disponibles en el portal de Microsoft 365 Defender hasta después de crear la directiva:
>   - Cree la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-SafeLinksRule).**
>   - Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_ ) en el cmdlet **New-SafeLinksRule).**
>
> - Una nueva directiva de vínculos seguros que cree en PowerShell no será visible en el portal de Microsoft 365 Defender hasta que asigne la directiva a una regla de vínculos seguros.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Paso 1: Usar PowerShell para crear una directiva de vínculos seguros

Para crear una directiva de vínculos seguros, use esta sintaxis:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - Para obtener más información acerca de la sintaxis de entrada que se va a usar para el parámetro _DoNotRewriteUrls,_ vea [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).
>
> - Para obtener una sintaxis adicional que puede usar para el parámetro _DoNotRewriteUrls_ al modificar las directivas de vínculos seguros existentes mediante el cmdlet **Set-SafeLinksPolicy,** vea la sección Usar [PowerShell](#use-powershell-to-modify-safe-links-policies) para modificar directivas de vínculos seguros más adelante en este artículo.

En este ejemplo se crea una directiva de vínculos seguros denominada Contoso All con los siguientes valores:

- Activa la detección y reescritura de direcciones URL en los mensajes de correo electrónico.
- Activa el examen de direcciones URL en Teams (solo vista previa de TAP).
- Activa el examen en tiempo real de las direcciones URL en las que se hace clic, incluidos los vínculos en los que se hace clic que apuntan a archivos.
- Espere a que se complete el examen de direcciones URL antes de entregar el mensaje.
- Activa la detección y reescritura de direcciones URL para los mensajes internos.
- Realizar un seguimiento de los clics de usuario relacionados con la protección de vínculos de Caja fuerte (no estamos usando el parámetro _DoNotTrackUserClicks_ y el valor predeterminado es $false, lo que significa que se realiza un seguimiento de los clics del usuario).
- No permitir que los usuarios hagan clic en la dirección URL original.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Paso 2: Usar PowerShell para crear una regla de vínculos seguros

Para crear una regla de vínculos seguros, use esta sintaxis:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

En este ejemplo se crea una regla de vínculos seguros denominada Contoso All con las siguientes condiciones:

- La regla está asociada con la directiva de vínculos seguros denominada Contoso All.
- La regla se aplica a todos los destinatarios del contoso.com dominio.
- Dado que no estamos usando el parámetro _Priority,_ se usa la prioridad predeterminada.
- La regla está habilitada (no estamos usando el parámetro _Enabled_ y el valor predeterminado es `$true` ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).

### <a name="use-powershell-to-view-safe-links-policies"></a>Usar PowerShell para ver directivas de vínculos seguros

Para ver las directivas de vínculos seguros existentes, use la siguiente sintaxis:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista resumida de todas las directivas de vínculos seguros.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

En este ejemplo se devuelve información detallada sobre la directiva de vínculos seguros denominada Ejecutivos de Contoso.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).

### <a name="use-powershell-to-view-safe-links-rules"></a>Usar PowerShell para ver reglas de vínculos seguros

Para ver las reglas de vínculos seguros existentes, use la siguiente sintaxis:

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista resumida de todas las reglas de vínculos seguros.

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

En este ejemplo se devuelve información detallada para la regla de vínculos seguros denominada Ejecutivos de Contoso.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).

### <a name="use-powershell-to-modify-safe-links-policies"></a>Usar PowerShell para modificar directivas de vínculos seguros

No puede cambiar el nombre de una directiva de vínculos seguros en PowerShell (el cmdlet **Set-SafeLinksPolicy** no tiene ningún _parámetro Name)._ Al cambiar el nombre de una directiva Caja fuerte vínculos en el portal de Microsoft 365 Defender, solo se cambia el nombre de la regla de vínculos _seguros_.

La única consideración adicional para modificar directivas de vínculos seguros en PowerShell es la sintaxis disponible para el parámetro _DoNotRewriteUrls_ (la lista ["No volver](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)a escribir las siguientes direcciones URL" ):

- Para agregar valores que reemplacen las entradas existentes, use la sintaxis siguiente: `"Entry1","Entry2,..."EntryN"` .
- Para agregar o quitar valores sin afectar a otras entradas existentes, use la sintaxis siguiente: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

De lo contrario, la misma configuración está disponible al crear una directiva de vínculos seguros como se describe en el paso [1: Usar PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) para crear una directiva de vínculos seguros anteriormente en este artículo.

Para modificar una directiva de vínculos seguros, use esta sintaxis:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).

### <a name="use-powershell-to-modify-safe-links-rules"></a>Usar PowerShell para modificar reglas de vínculos seguros

La única configuración que no está disponible al modificar una regla de vínculos seguros en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada. Para habilitar o deshabilitar las reglas de vínculos seguros existentes, consulte la siguiente sección.

De lo contrario, la misma configuración está disponible al crear una regla tal como se describe en el paso [2: Usar PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) para crear una regla de vínculos seguros anteriormente en este artículo.

Para modificar una regla de vínculos seguros, use esta sintaxis:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>Usar PowerShell para habilitar o deshabilitar reglas de vínculos seguros

Habilitar o deshabilitar una regla de vínculos seguros en PowerShell habilita o deshabilita toda la directiva de vínculos de Caja fuerte (la regla de vínculos seguros y la directiva de vínculos seguros asignada).

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

Para obtener información detallada acerca de la sintaxis y los parámetros, vea [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) y [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>Usar PowerShell para establecer la prioridad de las reglas de vínculos seguros

El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.

Para establecer la prioridad de una regla de vínculos seguros en PowerShell, use la siguiente sintaxis:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

En el ejemplo siguiente, la prioridad de la regla denominada "Marketing Department" se establece en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-SafeLinksRule** en su lugar.

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-remove-safe-links-policies"></a>Usar PowerShell para quitar directivas de vínculos seguros

Cuando usa PowerShell para quitar una directiva de vínculos seguros, no se quita la regla de vínculos seguros correspondiente.

Para quitar una directiva de vínculos seguros en PowerShell, use esta sintaxis:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

En este ejemplo se quita la directiva de vínculos seguros denominada Departamento de marketing.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).

### <a name="use-powershell-to-remove-safe-links-rules"></a>Usar PowerShell para quitar reglas de vínculos seguros

Cuando usa PowerShell para quitar una regla de vínculos seguros, no se quita la directiva de vínculos seguros correspondiente.

Para quitar una regla de vínculos seguros en PowerShell, use esta sintaxis:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

En este ejemplo se quita la regla de vínculos seguros denominada Departamento de marketing.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).

Para comprobar que los Caja fuerte están analizando mensajes, compruebe los informes de Microsoft Defender disponibles Office 365 datos. Para obtener más información, vea [View reports for Defender for Office 365](view-reports-for-mdo.md) and Use Explorer in the Microsoft 365 Defender [portal](threat-explorer.md).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha creado, modificado o quitado correctamente las directivas de vínculos Caja fuerte, siga estos pasos:

- En el portal Microsoft 365 Defender, vaya **a Directivas & reglas** de amenazas \> **Caja fuerte** \> **vínculos**. Compruebe la lista de directivas, sus **valores de** estado y sus **valores de** prioridad. Para ver más detalles, seleccione la directiva de la lista y vea los detalles en el menú desplegable.

- En Exchange Online PowerShell o Exchange Online Protection PowerShell, reemplace por el nombre de la directiva o regla, ejecute el siguiente comando y compruebe \<Name\> la configuración:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
