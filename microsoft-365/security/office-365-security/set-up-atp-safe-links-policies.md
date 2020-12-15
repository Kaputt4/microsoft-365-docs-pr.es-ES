---
title: Configurar directivas de vínculos a prueba de errores en Microsoft defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo ver, crear, modificar y eliminar directivas de vínculos seguros y la configuración de vínculos seguros globales en Microsoft defender para Office 365.
ms.openlocfilehash: 8a6d8a7ad567b658f04cb0b28800d4edbc33ec67
ms.sourcegitcommit: f81ca61f74f11a7436a6172538c3bda81b484d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "49675246"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Configurar directivas de vínculos a prueba de errores en Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](office-365-atp.md). Si es un usuario doméstico que busca información sobre Safelinks en Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Vínculos seguros es una característica de [Microsoft defender para Office 365](office-365-atp.md) que proporciona análisis de URL de los mensajes de correo electrónico entrantes en el flujo de correo y la hora de la comprobación de direcciones URL y vínculos en mensajes de correo electrónico y en otras ubicaciones. Para obtener más información, vea [vínculos a prueba de errores en Microsoft defender para Office 365](atp-safe-links.md).

No hay ninguna directiva de vínculos a prueba de errores integrada o predeterminada. Para obtener vínculos a prueba de errores de las direcciones URL, debe crear una o más directivas de vínculos seguros, como se describe en este artículo.

> [!NOTE]
> La configuración global de la protección de vínculos seguros se establece **fuera** de las directivas de vínculos seguros. Para obtener instrucciones, vea [Configure global Settings for Safe links in Microsoft defender for Office 365](configure-global-settings-for-safe-links.md).

Puede configurar directivas de vínculos seguros en el centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para las organizaciones de Microsoft 365 con buzones de correo en Exchange Online; PowerShell de EOP independiente para las organizaciones sin buzones de Exchange Online, pero con Microsoft defender para Office 365 para las suscripciones complementarias).

Los elementos básicos de una directiva de vínculos seguros son los siguientes:

- **La Directiva de vínculos seguros**: activar la protección de vínculos seguros, activar el análisis de URL en tiempo real, especificar si se debe esperar a que se complete la detección en tiempo real antes de entregar el mensaje, activar el examen de mensajes internos, especificar si se realiza un seguimiento de los clics del usuario en las direcciones URL y especificar si se permite a los usuarios hacer clic en el valle.
- **La regla de vínculos seguros**: especifica la prioridad y los filtros de destinatarios (a los que se aplica la Directiva).

La diferencia entre estos dos elementos no es obvia cuando se administran directivas de vínculos seguros en el centro de seguridad & cumplimiento:

- Al crear una directiva de vínculos seguros, en realidad está creando una regla de vínculos seguros y la Directiva de vínculos seguros asociada al mismo tiempo con el mismo nombre para ambas.
- Cuando se modifica una directiva de vínculos seguros, la configuración relacionada con los filtros nombre, prioridad, habilitado o deshabilitado y de destinatarios modifica la regla de vínculos a prueba de errores. Todas las demás opciones modifican la Directiva de vínculos seguros asociada.
- Cuando se quita una directiva de vínculos seguros, se quitan la regla de vínculos seguros y la Directiva de vínculos seguros asociada.

En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado. Para obtener más información, vea la sección [usar Exchange Online PowerShell o Standalone EOP PowerShell para configurar directivas de vínculos seguros](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) , más adelante en este artículo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página de **vínculos seguros** , use <https://protection.office.com/safelinksv2> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento de Office 365 antes de que pueda usar este cmdlet.
  - Para crear, modificar y eliminar directivas de vínculos a prueba de errores, debe ser miembro de los grupos de funciones administración de la **organización** o **Administrador de seguridad** .
  - Para el acceso de solo lectura a las directivas de vínculos a prueba de errores, debe ser miembro de los grupos de roles **lector global** o **lector de seguridad** .

  Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

  **Notas**:

  - Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para conocer la configuración recomendada para las directivas de vínculos seguros, consulte [configuración de directivas de vínculos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).

- Permitir que se aplique una directiva nueva o actualizada durante un máximo de 30 minutos.

- [Las nuevas características se agregan continuamente a Microsoft defender para Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365). A medida que se agreguen nuevas características, es posible que deba realizar ajustes en las directivas de vínculos a prueba de errores existentes.

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>Usar el centro de seguridad & cumplimiento para crear directivas de vínculos a prueba de errores

La creación de una directiva de vínculos seguros personalizada en el centro de seguridad & cumplimiento crea la regla de vínculos seguros y la Directiva de vínculos seguros asociada al mismo tiempo con el mismo nombre para ambas.

1. En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \>  \> **ATP Safe links**.

2. En la página **vínculos seguros** , haga clic en **crear**.

3. Se abre el Asistente para **nueva Directiva de vínculos seguros** . En la página **asigne un nombre a la Directiva** , configure las siguientes opciones:

   - **Nombre**: escriba un nombre único y descriptivo para la directiva.

   - **Descripción**: escriba una descripción opcional para la directiva.

   Cuando termine, haga clic en **Siguiente**.

4. En la página de **configuración** que aparece, configure las siguientes opciones:

   - **Seleccione la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes**: seleccione **activado** para habilitar la protección de vínculos seguros para vínculos en mensajes de correo electrónico.

   - **Seleccione la acción para direcciones URL potencialmente malintencionadas o desconocidas en Microsoft Teams**: seleccione **activado** para habilitar la protección de vínculos seguros para vínculos en Microsoft Teams.

   - **Aplique un análisis de URL en tiempo real en busca de vínculos y vínculos sospechosos que apunten a archivos**: Seleccione esta opción para habilitar el análisis en tiempo real de vínculos en mensajes de correo electrónico.

   - **Espere a que se complete el análisis de URL antes de entregar el mensaje**: Seleccione esta opción para esperar a que se complete el análisis de URL en tiempo real antes de entregar el mensaje.

   - **Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización**: Seleccione esta opción para aplicar la Directiva de vínculos seguros a los mensajes entre los remitentes internos y los destinatarios internos.

   - **No hacer un seguimiento de los clics del usuario**: deje esta opción sin seleccionar para permitir que el seguimiento del usuario haga clic en direcciones URL en mensajes de correo electrónico.

   - **No permita que los usuarios hagan clic a través de la dirección URL original**: Seleccione esta opción para impedir que los usuarios hagan clic a través de la dirección URL original en [las páginas de advertencia](atp-safe-links.md#warning-pages-from-safe-links).

   - **No vuelva a escribir las siguientes direcciones URL**: permite el acceso a las direcciones URL especificadas que, de lo contrario, bloquearían mediante vínculos seguros.

     En el cuadro, escriba la dirección URL o el valor que desee y, a continuación, haga clic en ![Icono Agregar botón](../../media/ITPro-EAC-AddIcon.png).

     Para quitar una entrada existente, selecciónela y, a continuación, haga clic en ![Icono Eliminar botón](../../media/ITPro-EAC-DeleteIcon.png).

     Para obtener la sintaxis de la entrada, consulte [la sintaxis de la entrada "no reescribir las siguientes direcciones URL"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).

   Para obtener información detallada acerca de estas opciones, vea configuración de [vínculos seguros para los mensajes de correo electrónico](atp-safe-links.md#safe-links-settings-for-email-messages) y la [configuración de vínculos seguros para Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).

   Para obtener más información sobre los valores recomendados para la configuración de directivas estándar y estricta, consulte [configuración de directivas de vínculos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).

   Cuando termine, haga clic en **Siguiente**.

5. En la página **aplicado a** que aparece, identifique los destinatarios internos a los que se aplica la Directiva.

   Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

   Haga clic en **Agregar condición**. En la lista desplegable que aparece, seleccione una condición en **aplicado si**:

   - **El destinatario es**: especifica uno o más buzones de correo, usuarios de correo o contactos de correo de su organización.
   - **El destinatario es un miembro de**: especifica uno o más grupos de la organización.
   - **El dominio del destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en su organización.

   Después de seleccionar la condición, aparece la lista desplegable correspondiente con una **de estas** casillas.

   - Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.
   - Haga clic en el cuadro y comience a escribir para filtrar la lista y seleccionar un valor.
   - Para agregar más valores, haga clic en un área vacía del cuadro.
   - Para quitar entradas individuales, haga  clic en ![ el icono quitar quitar del ](../../media/scc-remove-icon.png) valor.
   - Para quitar toda la condición, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación en la condición.

   Para agregar una condición adicional, haga clic en **Agregar condición** y seleccione un valor restante en **aplicado si**.

   Para agregar excepciones, haga clic en **Agregar una condición** y seleccione una excepción en **excepto si**. La configuración y el comportamiento se muestran exactamente igual que las condiciones.

   Cuando termine, haga clic en **Siguiente**.

6. En la página **Revise la configuración** que aparece, revise la configuración. Puede hacer clic en **Editar** en cada configuración para modificarla.

   Cuando haya terminado, haga clic en **Finalizar**.

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>Usar el centro de seguridad & cumplimiento para ver las directivas de vínculos a prueba de errores

1. En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \>  \> **ATP Safe links**.

2. En la página **vínculos seguros** , seleccione una directiva de la lista y haga clic en ella (no active la casilla de verificación).

   Los detalles de la Directiva aparecen en un vuelo hacia fuera

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>Usar el centro de seguridad & cumplimiento para modificar las directivas de vínculos a prueba de errores

1. En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \>  \> **ATP Safe links**.

2. En la página **vínculos seguros** , seleccione una directiva de la lista y haga clic en ella (no active la casilla de verificación).

3. En los detalles de la Directiva hacia fuera que aparece, haga clic en **Editar Directiva**.

La configuración disponible en la volar hacia fuera que aparece es idéntica a la que se describe en la sección [usar el centro de seguridad & cumplimiento para crear directivas de vínculos seguros](#use-the-security--compliance-center-to-create-safe-links-policies) .

Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la Directiva, consulte las siguientes secciones.

### <a name="enable-or-disable-safe-links-policies"></a>Habilitar o deshabilitar las directivas de vínculos a prueba de errores

1. En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \>  \> **ATP Safe links**.

2. Observe el valor de la columna **Estado** :

   - Mueva el botón de alternancia a la izquierda para deshabilitar la directiva: ![Desactivar Directiva](../../media/scc-toggle-off.png).

   - Mueva el botón de alternancia a la derecha para habilitar la directiva: ![Activar la Directiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

### <a name="set-the-priority-of-safe-links-policies"></a>Establecer la prioridad de las directivas de vínculos a prueba de errores

De forma predeterminada, las directivas de vínculos a prueba de errores reciben una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen prioridad más baja que las directivas anteriores). Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor). Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).

Las directivas de vínculos seguros se muestran en el orden en que se procesan (la primera Directiva tiene el valor de **prioridad** 0).

**Nota**: en el centro de seguridad & cumplimiento, solo puede cambiar la prioridad de la Directiva de vínculos seguros después de crearla. En PowerShell, puede invalidar la prioridad predeterminada al crear la regla de vínculos seguros (que puede afectar a la prioridad de las reglas existentes).

Para cambiar la prioridad de una directiva, suba o baje la directiva en la lista (no puede modificar directamente el número de **Prioridad** en el Centro de seguridad y cumplimiento).

1. En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \>  \> **ATP Safe links**.

2. En la página **vínculos seguros** , seleccione una directiva de la lista y haga clic en ella (no active la casilla de verificación).

3. En los detalles de la Directiva volar hacia fuera que aparece, haga clic en el botón prioridad disponible:

   - La Directiva de vínculos seguros con el valor de **prioridad** **0** sólo tiene disponible el botón **disminuir prioridad** .

   - La Directiva de vínculos seguros con el valor de **prioridad** más bajo (por ejemplo, **3**) solo tiene el botón **aumentar prioridad** disponible.

   - Si tiene tres o más directivas de vínculos seguros, las directivas entre los valores de prioridad mayor y menor tienen los botones **aumentar prioridad** y **disminuir prioridad** disponibles.

4. Haga clic en **aumentar prioridad** o **disminuir prioridad** para cambiar el valor de **prioridad** .

5. Cuando haya terminado, haga clic en **Cerrar**.

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>Usar el centro de seguridad & cumplimiento para quitar directivas de vínculos a prueba de errores

1. En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \>  \> **ATP Safe links**.

2. En la página **vínculos seguros** , seleccione una directiva de la lista y haga clic en ella (no active la casilla de verificación).

3. En los detalles de la Directiva que aparecen, haga clic en **eliminar Directiva** y, a continuación, haga clic en **sí** en el cuadro de diálogo de advertencia que aparece.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Usar Exchange Online PowerShell o PowerShell independiente de EOP para configurar directivas de vínculos seguros

Como se ha descrito anteriormente, una directiva de vínculos seguros consta de una directiva de vínculos seguros y una regla de vínculos seguros.

En PowerShell, la diferencia entre las directivas de vínculos a prueba de errores y las reglas de vínculos seguros es evidente. Las directivas de vínculos a prueba de errores se administran mediante los cmdlets **\* -SafeLinksPolicy** y se administran las reglas de vínculos a prueba de errores mediante los cmdlets **\* -SafeLinksRule** .

- En PowerShell, se crea la Directiva de vínculos seguros en primer lugar y, a continuación, se crea la regla de vínculos seguros que identifica la Directiva a la que se aplica la regla.
- En PowerShell, la configuración de la Directiva de vínculos seguros y la regla de vínculos seguros se modifica por separado.
- Cuando se quita una directiva de vínculos seguros de PowerShell, la regla de vínculos seguros correspondiente no se quita automáticamente y viceversa.

### <a name="use-powershell-to-create-safe-links-policies"></a>Usar PowerShell para crear directivas de vínculos a prueba de errores

La creación de una directiva de vínculos seguros en PowerShell es un proceso de dos pasos:

1. Cree la Directiva de vínculos seguros.
2. Cree la regla de vínculos seguros que especifica la Directiva de vínculos a prueba de errores a la que se aplica la regla.

 **Notas**:

- Puede crear una nueva regla de vínculos seguros y asignarle una directiva de vínculos seguros existente no asociada. No se puede asociar una regla de vínculos seguros con más de una directiva de vínculos seguros.

- Puede configurar las siguientes opciones en nuevas directivas de vínculos a prueba de errores en PowerShell que no están disponibles en el centro de seguridad & cumplimiento hasta que se crea la Directiva:

  - Cree la nueva directiva como deshabilitada (_habilitada_ `$false` en el cmdlet **New-SafeLinksRule** ).
  - Establezca la prioridad de la Directiva durante la creación (_prioridad_ _\<Number\>_ ) en el cmdlet **New-SafeLinksRule** ).

- Una nueva Directiva de vínculos seguros que se crea en PowerShell no es visible en el centro de seguridad & cumplimiento hasta que se asigna la Directiva a una regla de vínculos seguros.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Paso 1: usar PowerShell para crear una directiva de vínculos seguros

Para crear una directiva de vínculos seguros, use esta sintaxis:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

**Notas**:

- Para obtener información detallada sobre la sintaxis de entrada que se debe usar para el parámetro _DoNotRewriteUrls_ , vea [la sintaxis de entrada de la lista "no reescribir las siguientes direcciones URL"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).

- Para obtener más sintaxis que puede usar para el parámetro _DoNotRewriteUrls_ al modificar las directivas de vínculos a prueba de errores existentes mediante el cmdlet **set-SafeLinksPolicy** , consulte la sección [usar PowerShell para modificar las directivas de vínculos seguros](#use-powershell-to-modify-safe-links-policies) , más adelante en este artículo.

En este ejemplo se crea una directiva de vínculos seguros llamada contoso All con los valores siguientes:

- Activar el análisis y la reescritura de URL en mensajes de correo electrónico.
- Active el análisis de URL en Teams (pulse solo vista previa).
- Active el análisis en tiempo real de las direcciones URL en las que hizo clic, incluidos los vínculos a los que se hizo clic que señalan a archivos.
- Espere a que se complete el análisis de URL antes de entregar el mensaje.
- Activar el análisis y la reescritura de URL para los mensajes internos.
- Realizar un seguimiento de los clics de usuario relacionados con la protección de vínculos seguros (no se usa el parámetro _DoNotTrackUserClicks_ y el valor predeterminado es $false, lo que significa que se realiza un seguimiento de los clics del usuario).
- No permita que los usuarios hagan clic en la dirección URL original.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Paso 2: usar PowerShell para crear una regla de vínculos seguros

Para crear una regla de vínculos seguros, use esta sintaxis:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

En este ejemplo se crea una regla de vínculos a prueba de errores denominada contoso All con las siguientes condiciones:

- La regla está asociada a la Directiva de vínculos a prueba de errores denominada contoso ALL.
- La regla se aplica a todos los destinatarios del dominio contoso.com.
- Como no se usa el parámetro _Priority_ , se usa la prioridad predeterminada.
- La regla está habilitada (no se usa el parámetro _Enabled_ y el valor predeterminado es `$true` ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).

### <a name="use-powershell-to-view-safe-links-policies"></a>Usar PowerShell para ver las directivas de vínculos a prueba de errores

Para ver las directivas de vínculos a prueba de errores existentes, use la siguiente sintaxis:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista resumida de todas las directivas de vínculos a prueba de errores.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

En este ejemplo se muestra información detallada de la Directiva de vínculos a prueba de errores denominada ejecutivos de contoso.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).

### <a name="use-powershell-to-view-safe-links-rules"></a>Usar PowerShell para ver las reglas de vínculos a prueba de errores

Para ver las reglas de vínculos a prueba de errores existentes, use la siguiente sintaxis:

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista resumida de todas las reglas de vínculos a prueba de errores.

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

En este ejemplo se muestra información detallada de la regla de vínculos a prueba de errores denominada ejecutivos de contoso.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).

### <a name="use-powershell-to-modify-safe-links-policies"></a>Usar PowerShell para modificar directivas de vínculos a prueba de errores

No puede cambiar el nombre de una directiva de vínculos seguros en PowerShell (el cmdlet **set-SafeLinksPolicy** no tiene ningún parámetro _Name_ ). Al cambiar el nombre de una directiva de vínculos seguros en el centro de seguridad & cumplimiento, sólo cambia el nombre de la _regla_ de vínculos seguros.

La única consideración adicional para modificar las directivas de vínculos a prueba de errores en PowerShell es la sintaxis disponible para el parámetro _DoNotRewriteUrls_ (la [lista "no reescribir las siguientes direcciones URL"](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):

- Para agregar valores que van a reemplazar las entradas existentes, use la siguiente sintaxis: `"Entry1","Entry2,..."EntryN"` .
- Para agregar o quitar valores sin que ello afecte a las entradas existentes, use la sintaxis siguiente: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

De lo contrario, la misma configuración está disponible cuando se crea una directiva de vínculos seguros, tal como se describe en la sección [paso 1: usar PowerShell para crear una directiva de vínculos seguros](#step-1-use-powershell-to-create-a-safe-links-policy) anteriormente en este artículo.

Para modificar una directiva de vínculos seguros, use esta sintaxis:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).

### <a name="use-powershell-to-modify-safe-links-rules"></a>Usar PowerShell para modificar las reglas de vínculos a prueba de errores

La única opción que no está disponible cuando se modifica una regla de vínculos seguros en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada. Para habilitar o deshabilitar reglas de vínculos a prueba de errores, consulte la siguiente sección.

De lo contrario, la misma configuración está disponible cuando se crea una regla tal y como se describe en la sección [paso 2: usar PowerShell para crear una regla de vínculos seguros](#step-2-use-powershell-to-create-a-safe-links-rule) anteriormente en este artículo.

Para modificar una regla de vínculos a prueba de errores, use esta sintaxis:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>Usar PowerShell para habilitar o deshabilitar reglas de vínculos a prueba de errores

Al habilitar o deshabilitar una regla de vínculos a prueba de errores en PowerShell, se habilita o deshabilita toda la Directiva de vínculos seguros (la regla de vínculos seguros y la Directiva de vínculos seguros asignada).

Para habilitar o deshabilitar una regla de vínculos a prueba de errores en PowerShell, use esta sintaxis:

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

En este ejemplo se deshabilita la regla de vínculos a prueba de errores denominada Marketing Department.

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

Este ejemplo habilita la misma regla.

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) y [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>Usar PowerShell para establecer la prioridad de las reglas de vínculos a prueba de errores

El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo que se puede establecer depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.

Para establecer la prioridad de una regla de vínculos seguros en PowerShell, use la sintaxis siguiente:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

**Nota**: para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-SafeLinksRule** en su lugar.

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-remove-safe-links-policies"></a>Usar PowerShell para quitar directivas de vínculos a prueba de errores

Cuando se usa PowerShell para quitar una directiva de vínculos seguros, no se quita la regla de vínculos seguros correspondiente.

Para quitar una directiva de vínculos seguros en PowerShell, use esta sintaxis:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

En este ejemplo se quita la Directiva de vínculos a prueba de errores denominada Marketing Department.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).

### <a name="use-powershell-to-remove-safe-links-rules"></a>Usar PowerShell para quitar reglas de vínculos a prueba de errores

Cuando se usa PowerShell para quitar una regla de vínculos seguros, no se quita la Directiva de vínculos seguros correspondiente.

Para quitar una regla de vínculos a prueba de errores en PowerShell, use esta sintaxis:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

En este ejemplo se quita la regla de vínculos a prueba de errores denominada Marketing Department.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).

Para comprobar que vínculos seguros está examinando los mensajes, consulte los informes de Microsoft defender para Office 365. Para obtener más información, vea [ver informes de defender para Office 365](view-reports-for-atp.md) y [usar el explorador en el centro de seguridad & cumplimiento](threat-explorer.md).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que las directivas de vínculos seguros se crearon, modificaron o quitaron correctamente, siga uno de estos pasos:

- En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \>  \> **ATP Safe links**. Compruebe la lista de directivas, sus valores de **Estado** y sus valores de **prioridad** . Para ver más detalles, seleccione la Directiva de la lista y vea los detalles en la lista desplegable.

- En PowerShell de Exchange Online PowerShell o Exchange Online Protection, reemplace \<Name\> por el nombre de la Directiva o regla, ejecute el siguiente comando y Compruebe la configuración:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
