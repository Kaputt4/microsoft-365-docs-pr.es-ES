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
description: Los administradores pueden aprender a ver, crear, modificar y eliminar directivas de vínculos de Caja fuerte y la configuración global de vínculos de Caja fuerte en Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 867d055c44ba0d0ae0b7b763bc556a06f16e5cd8
ms.sourcegitcommit: a7e1d155939e862337271fbe38bf26f62bd49bdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2022
ms.locfileid: "64847110"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Configurar directivas de vínculos seguros en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](defender-for-office-365.md). Si es un usuario doméstico que busca información sobre Safelinks en Outlook, consulte [Seguridad avanzada de Outlook.com](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Caja fuerte Vínculos en [Microsoft Defender para Office 365](defender-for-office-365.md) proporciona el examen de direcciones URL de los mensajes de correo electrónico entrantes en el flujo de correo y la hora de verificación de clic de direcciones URL y vínculos en mensajes de correo electrónico y en otras ubicaciones. Para obtener más información, consulte [vínculos de Caja fuerte en Microsoft Defender para Office 365](safe-links.md).

Aunque no hay ninguna directiva de vínculos de Caja fuerte predeterminada, la directiva de seguridad preestablecida de **protección integrada** proporciona protección de vínculos Caja fuerte a todos los destinatarios (usuarios que no están definidos en directivas personalizadas de vínculos de Caja fuerte). Para obtener más información, vea [Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md).

También puede usar los procedimientos de este artículo para crear directivas de vínculos de Caja fuerte que se aplican a usuarios, grupos o dominios específicos.

> [!NOTE]
>
> Los valores globales se configuran para la protección de vínculos de Caja fuerte **fuera** de las directivas de vínculos de Caja fuerte. Para obtener instrucciones, consulte [Configuración global de vínculos de Caja fuerte en Microsoft Defender para Office 365](configure-global-settings-for-safe-links.md).
>
> Los administradores deben tener en cuenta las distintas opciones de configuración de Caja fuerte Links. Una de las opciones disponibles es incluir información de identificación del usuario en Caja fuerte Vínculos. Esta característica permite a los equipos de operaciones de seguridad (SecOps) investigar posibles riesgos de usuario, tomar medidas correctivas y limitar infracciones costosas.

Puede configurar directivas de vínculos seguros contra correo no deseado en el portal de Microsoft 365 Defender o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; EOP PowerShell independiente para organizaciones sin buzones de Exchange Online, pero con suscripciones a completos de Microsoft Defender for Office 365).

Los elementos básicos de una directiva de vínculos de Caja fuerte son:

- **La directiva de vínculos seguros**: active Caja fuerte Protección de vínculos, active el examen de direcciones URL en tiempo real, especifique si debe esperar a que se complete el examen en tiempo real antes de entregar el mensaje, active el examen de mensajes internos, especifique si se debe realizar un seguimiento de los clics del usuario en las direcciones URL y si se permite a los usuarios hacer clic en la dirección URL original.
- **Regla de vínculos seguros**: especifica la prioridad y los filtros de destinatario (a quién se aplica la directiva).

La diferencia entre estos dos elementos no es obvia al administrar directivas de vínculos de Caja fuerte en el portal de Microsoft 365 Defender:

- Al crear una directiva de vínculos de Caja fuerte, realmente está creando una regla de vínculos seguros y la directiva de vínculos seguros asociada al mismo tiempo que usa el mismo nombre para ambos.
- Al modificar una directiva de vínculos de Caja fuerte, la configuración relacionada con el nombre, la prioridad, habilitado o deshabilitado y los filtros de destinatarios modifican la regla de vínculos seguros. Todas las demás configuraciones modifican la directiva de vínculos seguros asociados.
- Al quitar una directiva de vínculos de Caja fuerte, se quitan la regla de vínculos seguros y la directiva de vínculos seguros asociada.

En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado. Para obtener más información, consulte la sección [Uso de PowerShell Exchange Online o EOP independiente para configurar directivas de vínculos de Caja fuerte](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) más adelante en este artículo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **vínculos de Caja fuerte**, use <https://security.microsoft.com/safelinksv2>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener asignados permisos para poder realizar los procedimientos de este artículo:
  - Para crear, modificar y eliminar directivas de vínculos Caja fuerte, debe ser miembro de los grupos de roles Administración de la **organización** o **Administrador de seguridad** en el portal de Microsoft 365 Defender **y** miembro del grupo de roles **Administración** de la organización en Exchange Online.
  - Para obtener acceso de solo lectura a Caja fuerte directivas de vínculos, debe ser miembro de los grupos de roles **Lector global** o **Lector de seguridad**.

  Para obtener más información, vea [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md) y [Permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el portal de Microsoft 365 Defender _y_ permisos para otras características en Microsoft 365. Para más información, consulte[Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  . - El grupo **de roles View-Only Organization Management** de [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para ver nuestra configuración recomendada para las directivas de vínculos de Caja fuerte, consulte [configuración de directivas de vínculos de Caja fuerte](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).

- Espere hasta 6 horas para que se aplique una directiva nueva o actualizada.

- [Las nuevas características se agregan continuamente a Microsoft Defender para Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365). A medida que se agregan nuevas características, es posible que tenga que realizar ajustes en las directivas de vínculos de Caja fuerte existentes.

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a>Uso del portal de Microsoft 365 Defender para crear directivas de vínculos de Caja fuerte

La creación de una directiva personalizada de vínculos de Caja fuerte en el portal de Microsoft 365 Defender crea la regla de vínculos seguros y la directiva de vínculos seguros asociada al mismo tiempo con el mismo nombre para ambos.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas de colaboración** \> & correo electrónico **& directivas** de **amenazas** \> de reglas \> **Caja fuerte vínculos** en la sección **Directivas**. Para ir directamente a la página **vínculos de Caja fuerte**, use <https://security.microsoft.com/safelinksv2>.

2. En la página **Vínculos Caja fuerte**, haga clic en ![el icono Crear.](../../media/m365-cc-sc-create-icon.png) **Create**.

3. Se abre el Asistente para **directivas de vínculos Caja fuerte** nuevos. En la página **Nombre de la directiva** , configure los siguientes valores:

   - **Nombre**: escriba un nombre único y descriptivo para la directiva.
   - **Descripción**: escriba una descripción opcional para la directiva.

   Cuando termine, haga clic en **Siguiente**.

4. En la página **Usuarios y dominios** que aparece, identifique los destinatarios internos a los que se aplica la directiva (condiciones de destinatario):
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

5. En la página **Configuración de protección** que aparece, configure los siguientes valores:
   - **Seleccione la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes**: seleccione **Activado** para habilitar Caja fuerte Protección de vínculos para vínculos en mensajes de correo electrónico. Si activa esta configuración, están disponibles las siguientes opciones:
     - **Aplicar el examen de direcciones URL en tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos**: seleccione esta opción para habilitar el examen en tiempo real de los vínculos en los mensajes de correo electrónico. Si activa esta configuración, está disponible la siguiente configuración:
       - **Espere a que se complete el examen de direcciones URL antes de entregar el mensaje**: seleccione esta opción para esperar a que se complete el examen de direcciones URL en tiempo real antes de entregar el mensaje.
     - **Aplicar Caja fuerte Vínculos a mensajes de correo electrónico enviados dentro de la organización**: seleccione esta opción para aplicar la directiva de vínculos de Caja fuerte a los mensajes entre remitentes internos y destinatarios internos.
   - **Seleccione la acción para direcciones URL desconocidas o potencialmente malintencionadas dentro de Microsoft Teams**: seleccione **Activado** para habilitar la protección de vínculos de Caja fuerte para los vínculos de Teams. Tenga en cuenta que esta configuración puede tardar hasta 24 horas en surtir efecto.
   - **Realizar un seguimiento de los clics del usuario**: deje esta opción seleccionada para habilitar que el usuario de seguimiento haga clic en las direcciones URL de los mensajes de correo electrónico.
   - **Permitir que los usuarios haga clic en la dirección URL original**: desactive esta opción para impedir que los usuarios haga clic en la dirección URL original en [las páginas de advertencia](safe-links.md#warning-pages-from-safe-links).
   - **No vuelva a escribir las siguientes direcciones URL**: permite acceder a las direcciones URL especificadas que, de lo contrario, Caja fuerte Links bloquearían.

     En el cuadro, escriba la dirección URL o el valor que desee y, a continuación, haga clic en **Agregar**. Repita este paso tantas veces como sea necesario.

     Para quitar una entrada existente, haga clic en ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto a la entrada.

     Para obtener la sintaxis de entrada, consulte [Sintaxis de entrada para la lista "No volver a escribir las siguientes direcciones URL"](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).

   Para obtener información detallada sobre esta configuración, consulte [configuración de vínculos de Caja fuerte para mensajes de correo electrónico](safe-links.md#safe-links-settings-for-email-messages) y [configuración de vínculos de Caja fuerte para Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).

   Para obtener más información sobre los valores recomendados para la configuración de directivas estándar y estricta, consulte [configuración de directivas de vínculos de Caja fuerte](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).

   Cuando termine, haga clic en **Siguiente**.

6. En la página **Notificación** que aparece, seleccione uno de los siguientes valores para **¿Cómo desea notificar a los usuarios?**:
   - **Uso del texto de notificación predeterminado**
   - **Usar texto de notificación personalizado**: si selecciona este valor (la longitud no puede superar los 200 caracteres), aparecerá la siguiente configuración:
     - **Uso de Traductor de Microsoft para la localización automática**
     - **Texto de notificación personalizado**: escriba el texto de notificación personalizado en este cuadro.

   Cuando termine, haga clic en **Siguiente**.

7. En la página **Revisar** que aparece, revise la configuración. Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Enviar**.

8. En la página de confirmación que aparece, haga clic en **Listo**.

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a>Uso del portal de Microsoft 365 Defender para ver las directivas de vínculos de Caja fuerte

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas de colaboración** \> & correo electrónico **& directivas** de **amenazas** \> de reglas \> **Caja fuerte vínculos** en la sección **Directivas**. Para ir directamente a la página **vínculos de Caja fuerte**, use <https://security.microsoft.com/safelinksv2>.

2. En la página **Vínculos Caja fuerte**, se muestran las siguientes propiedades en la lista de directivas de vínculos de Caja fuerte:
   - **Nombre**
   - **Estado**
   - **Prioridad**

3. Al seleccionar una directiva haciendo clic en el nombre, la configuración de la directiva se muestra en un control flotante.

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a>Uso del portal de Microsoft 365 Defender para modificar las directivas de vínculos de Caja fuerte

1. En el portal de Microsoft 365 Defender, vaya a la sección \> **Directivas & reglas** \> **Directivas** \> de **amenazas** **Caja fuerte Vínculos**.

2. En la página **Vínculos Caja fuerte**, seleccione una directiva de la lista haciendo clic en el nombre.

3. En el control flotante de detalles de la directiva que aparece, seleccione **Editar** en cada sección para modificar la configuración dentro de la sección. Para obtener más información sobre la configuración, consulte la sección Anterior [Uso del portal de Microsoft 365 Defender para crear directivas de vínculos Caja fuerte](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) en este artículo.

Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la directiva, consulte las secciones siguientes.

### <a name="enable-or-disable-safe-links-policies"></a>Habilitar o deshabilitar directivas de vínculos de Caja fuerte

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas de colaboración** \> & correo electrónico **& directivas** de **amenazas** \> de reglas \> **Caja fuerte vínculos** en la sección **Directivas**. Para ir directamente a la página **vínculos de Caja fuerte**, use <https://security.microsoft.com/safelinksv2>.

2. En la página **Vínculos Caja fuerte**, seleccione una directiva de la lista haciendo clic en el nombre.

3. En la parte superior del control flotante de detalles de la directiva que aparece, verá uno de los siguientes valores:
   - **Directiva desactivada**: para activar la directiva, haga clic en ![icono Activar.](../../media/m365-cc-sc-turn-on-off-icon.png) **Activar** .
   - **Directiva activada**: para desactivar la directiva, haga clic en el ![Icono Desactivar](../../media/m365-cc-sc-turn-on-off-icon.png) **Desactivar**.

4. En el cuadro de diálogo de confirmación que aparece, haga clic **Activar** o **Desactivar**.

5. Haga clic en **Cerrar** en el control flotante de detalles de la directiva.

De nuevo en la página principal de la directiva, el valor **Estado** de la directiva estará **Activado** o **Desactivado**.

### <a name="set-the-priority-of-safe-links-policies"></a>Establecer la prioridad de las directivas de vínculos de Caja fuerte

De forma predeterminada, a los vínculos de Caja fuerte se les asigna una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen una prioridad menor que las directivas anteriores). Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor). Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

Para cambiar la prioridad de una directiva, haga clic en **Aumentar prioridad** o **Reducir prioridad** en las propiedades de la directiva (no puede modificar directamente el número de **Prioridad** en el portal de Microsoft 365 Defender). Cambiar la prioridad de una directiva sólo tiene sentido si tiene varias directivas.

**Nota**:

- En el portal de Microsoft 365 Defender, solo puede cambiar la prioridad de la directiva de vínculos de Caja fuerte después de crearla. En PowerShell, puede invalidar la prioridad predeterminada al crear la regla de vínculos seguros (que puede afectar a la prioridad de las reglas existentes).
- Caja fuerte las directivas de vínculos se procesan en el orden en que se muestran (la primera directiva tiene el valor **de prioridad** 0). Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas de colaboración** \> & correo electrónico **& directivas** de **amenazas** \> de reglas \> **Caja fuerte vínculos** en la sección **Directivas**. Para ir directamente a la página **vínculos de Caja fuerte**, use <https://security.microsoft.com/safelinksv2>.

2. En la página **Vínculos Caja fuerte**, seleccione una directiva de la lista haciendo clic en el nombre.

3. En la parte superior del control flotante de detalles de la directiva que aparece, verá **Aumentar la prioridad** o **Disminuir la prioridad** en función del valor de prioridad actual y del número de directivas personalizadas:
   - La directiva con el valor **De prioridad** **0** solo tiene la opción **Reducir prioridad** disponible.
   - La directiva con el valor **de prioridad** más bajo (por ejemplo, **3**) solo tiene la opción **Aumentar prioridad** disponible.
   - Si tiene tres o más directivas, las directivas entre los valores de prioridad más altos y más bajos tienen disponibles las opciones **Aumentar prioridad** y **Reducir prioridad** .

   Haga clic en el ![Icono Aumentar la prioridad.](../../media/m365-cc-sc-increase-icon.png) **Aumentar la prioridad** o en el ![Icono Disminuir la prioridad](../../media/m365-cc-sc-decrease-icon.png) **Reducir la prioridad** para cambiar el valor de **Prioridad**.

4. Cuando haya terminado, haga clic en **Cerrar** en el control flotante de detalles de la directiva.

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a>Uso del portal de Microsoft 365 Defender para quitar directivas de vínculos de Caja fuerte

1. En el portal de Microsoft 365 Defender, vaya a **Correo electrónico &** Directivas de colaboración \> **& Directivas** de **amenazas** \> de reglas \> **Caja fuerte Vínculos** en la sección **Directivas**.

2. En la página **Vínculos Caja fuerte**, seleccione una directiva de la lista haciendo clic en el nombre. En la parte superior del control flotante de detalles de la directiva que aparece, haga clic en ![icono Más acciones.](../../media/m365-cc-sc-more-actions-icon.png) **Más acciones** \> ![Icono Eliminar directiva](../../media/m365-cc-sc-delete-icon.png)**Eliminar directiva**.

3. En el cuadro de diálogo de confirmación que aparece, haga clic en **Sí**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Use Exchange Online PowerShell o PowerShell EOP independiente para configurar directivas de vínculos de Caja fuerte

Como se describió anteriormente, una directiva de vínculos de Caja fuerte consta de una directiva de vínculos seguros y una regla de vínculos seguros.

En PowerShell, la diferencia entre las directivas de vínculos seguros y las reglas de vínculos seguros es evidente. Las directivas de vínculos seguros se administran mediante los **\*cmdlets -SafeLinksPolicy** y se administran las reglas de vínculos seguros mediante los **\*cmdlets -SafeLinksRule** .

- En PowerShell, primero se crea la directiva de vínculos seguros y, a continuación, se crea la regla de vínculos seguros que identifica la directiva a la que se aplica la regla.
- En PowerShell, se modifica la configuración de la directiva de vínculos seguros y la regla de vínculos seguros por separado.
- Al quitar una directiva de vínculos seguros de PowerShell, la regla de vínculos seguros correspondiente no se quita automáticamente y viceversa.

### <a name="use-powershell-to-create-safe-links-policies"></a>Uso de PowerShell para crear directivas de vínculos Caja fuerte

La creación de una directiva de vínculos de Caja fuerte en PowerShell es un proceso de dos pasos:

1. Cree la directiva de vínculos seguros.
2. Cree la regla de vínculos seguros que especifique la directiva de vínculos seguros a la que se aplica la regla.

> [!NOTE]
>
> - Puede crear una nueva regla de vínculos seguros y asignarle una directiva de vínculos seguros no asociados existente. Una regla de vínculos seguros no se puede asociar a más de una directiva de vínculos seguros.
>
> - Puede configurar las siguientes opciones en nuevas directivas de vínculos seguros en PowerShell que no estén disponibles en el portal de Microsoft 365 Defender hasta que haya creado la directiva:
>   - Cree la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-SafeLinksRule** ).
>   - Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_) en el cmdlet **New-SafeLinksRule** .
>
> - Una nueva directiva de vínculos seguros que cree en PowerShell no será visible en el portal de Microsoft 365 Defender hasta que asigne la directiva a una regla de vínculos seguros.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Paso 1: Uso de PowerShell para crear una directiva de vínculos seguros

Para crear una directiva de vínculos seguros, use esta sintaxis:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSafeLinksForEmail <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-AllowClickThrough <$true | $false>] [-TrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - Para obtener más información sobre la sintaxis de entrada que se va a usar para el parámetro _DoNotRewriteUrls_ , vea [Sintaxis de entrada para la lista "No volver a escribir las siguientes direcciones URL"](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).
>
> - Para obtener una sintaxis adicional que puede usar para el parámetro _DoNotRewriteUrls al modificar las directivas de vínculos_ seguros existentes mediante el cmdlet **Set-SafeLinksPolicy** , consulte la sección [Uso de PowerShell para modificar directivas de vínculos seguros](#use-powershell-to-modify-safe-links-policies) más adelante en este artículo.

En este ejemplo se crea una directiva de vínculos seguros denominada Contoso All con los valores siguientes:

- Active el examen y la reescritura de direcciones URL en los mensajes de correo electrónico.
- Active el examen de direcciones URL en Teams.
- Active el examen en tiempo real de las direcciones URL en las que se ha hecho clic, incluidos los vínculos en los que se ha hecho clic que apuntan a los archivos.
- Espere a que se complete el examen de direcciones URL antes de entregar el mensaje.
- Active el examen y la reescritura de direcciones URL para los mensajes internos.
- Realizar un seguimiento de los clics de usuario relacionados con la protección de vínculos de Caja fuerte (no se usa el parámetro _TrackUserClicks_ y el valor predeterminado es $true).
- No permita que los usuarios hagan clic en la dirección URL original.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -EnableSafeLinksForEmail $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -AllowClickThrough $false
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

No se puede cambiar el nombre de una directiva de vínculos seguros en PowerShell (el cmdlet **Set-SafeLinksPolicy** no tiene ningún parámetro _Name_ ). Al cambiar el nombre de una directiva de vínculos de Caja fuerte en el portal de Microsoft 365 Defender, solo cambia el nombre de la _regla_ de vínculos seguros.

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

Para obtener información detallada sobre la sintaxis y los [parámetros, consulte Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>Uso de PowerShell para habilitar o deshabilitar reglas de vínculos seguros

La habilitación o deshabilitación de una regla de vínculos seguros en PowerShell habilita o deshabilita toda la directiva de vínculos Caja fuerte (la regla de vínculos seguros y la directiva de vínculos seguros asignados).

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

Para comprobar que Caja fuerte Vínculos está examinando mensajes, compruebe los informes de Microsoft Defender para Office 365 disponibles. Para obtener más información, vea [Ver informes para Defender para Office 365](view-reports-for-mdo.md) y [Usar explorador en el portal de Microsoft 365 Defender](threat-explorer.md).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha creado, modificado o quitado correctamente Caja fuerte directivas de vínculos, siga estos pasos:

- En la página **vínculos Caja fuerte** del portal de Microsoft 365 Defender en <https://security.microsoft.com/safelinksv2>, compruebe la lista de directivas, sus valores **de estado** y sus valores **de prioridad**. Para ver más detalles, seleccione la directiva de la lista y vea los detalles del control flotante.

- En Exchange Online PowerShell o Exchange Online Protection PowerShell, reemplace por \<Name\> el nombre de la directiva o regla, ejecute el siguiente comando y compruebe la configuración:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
