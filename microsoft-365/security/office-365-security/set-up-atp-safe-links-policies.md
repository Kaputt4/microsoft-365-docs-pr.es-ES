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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a ver, crear, modificar y eliminar directivas de vínculos seguros y la configuración global de vínculos seguros en Microsoft Defender para Office 365.
ms.openlocfilehash: ef83d0dba1de03aa2b36384474791783e926059f
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780537"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Configurar directivas de vínculos seguros en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](office-365-atp.md). Si es un usuario principal que busca información sobre safelinks en Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Vínculos seguros es una característica de Microsoft Defender para [Office 365](office-365-atp.md) que proporciona el análisis de direcciones URL de los mensajes de correo electrónico entrantes en el flujo de correo y el tiempo de comprobación de clics de direcciones URL y vínculos en mensajes de correo electrónico y en otras ubicaciones. Para obtener más información, vea [Vínculos seguros en Microsoft Defender para Office 365.](atp-safe-links.md)

No hay ninguna directiva de vínculos seguros integrada o predeterminada. Para obtener el análisis de vínculos seguros de direcciones URL, debe crear una o más directivas de vínculos seguros, tal como se describe en este artículo.

> [!NOTE]
> Las opciones globales de protección de vínculos seguros se configuran **fuera de** las directivas de vínculos seguros. Para obtener instrucciones, [consulte Configuración global de vínculos seguros en Microsoft Defender para Office 365.](configure-global-settings-for-safe-links.md)

Puede configurar directivas de vínculos seguros en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones elegibles de Microsoft 365 con buzones en Exchange Online; EOP PowerShell independiente para organizaciones sin buzones de Exchange Online, pero con suscripciones de complemento de Microsoft Defender para Office 365).

Los elementos básicos de una directiva de vínculos seguros son:

- La directiva de vínculos **seguros:** activar la protección de vínculos seguros, activar el examen de direcciones URL en tiempo real, especificar si se debe esperar a que se complete el análisis en tiempo real antes de entregar el mensaje, activar el examen de mensajes internos, especificar si se va a realizar un seguimiento de los clics del usuario en las direcciones URL y especificar si se permite a los usuarios hacer clic en la dirección URL original.
- **La regla de vínculos seguros:** especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva).

La diferencia entre estos dos elementos no es obvia cuando administra directivas de vínculos seguros en el Centro de & cumplimiento:

- Al crear una directiva de vínculos seguros, realmente está creando una regla de vínculos seguros y la directiva de vínculos seguros asociada al mismo tiempo con el mismo nombre para ambos.
- Al modificar una directiva de vínculos seguros, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada, y los filtros de destinatarios modifican la regla de vínculos seguros. Todas las demás opciones modifican la directiva de vínculos seguros asociada.
- Al quitar una directiva de vínculos seguros, se quitan la regla de vínculos seguros y la directiva de vínculos seguros asociada.

En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado. Para obtener más información, vea la sección Usar Exchange Online PowerShell o [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) independiente para configurar directivas de vínculos seguros más adelante en este artículo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la **página Vínculos seguros,** use <https://protection.office.com/safelinksv2> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Deberá tener asignados permisos antes de poder realizar los procedimientos descritos en este artículo:
  - Para crear, modificar y eliminar directivas de vínculos seguros, debe ser miembro de los grupos de  roles Administración de  la organización o Administrador de seguridad en el Centro de cumplimiento de & de seguridad y miembro del grupo de roles Administración de la organización en Exchange Online.  
  - Para obtener acceso de solo lectura a las directivas de vínculos seguros, debe ser miembro de los grupos de roles Lector **global** o **Lector de** seguridad.

  Para obtener más información, vea [Permisos en el Centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md) y permisos en Exchange [Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para obtener la configuración recomendada para las directivas de vínculos seguros, vea [la configuración de la directiva de vínculos seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)

- Espere hasta 30 minutos para que se aplique una directiva nueva o actualizada.

- [Las nuevas características se agregan continuamente a Microsoft Defender para Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365) A medida que se agregan nuevas características, es posible que deba realizar ajustes en las directivas de vínculos seguros existentes.

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>Usar el Centro de seguridad & cumplimiento para crear directivas de vínculos seguros

La creación de una directiva de vínculos seguros personalizada en el Centro de seguridad y cumplimiento de & crea la regla de vínculos seguros y la directiva de vínculos seguros asociada al mismo tiempo con el mismo nombre para ambos.

1. En el Centro de & cumplimiento, vaya **a** Vínculos seguros de ATP de la directiva de administración \>  \> **de amenazas.**

2. En la **página Vínculos seguros,** haga clic **en Crear**.

3. Se **abrirá el Asistente para nueva directiva de vínculos** seguros. En la **página Nombre de la directiva,** configure las siguientes opciones:

   - **Nombre**: escriba un nombre único y descriptivo para la directiva.

   - **Descripción**: escriba una descripción opcional para la directiva.

   Cuando termine, haga clic en **Siguiente**.

4. En la **página Configuración** que aparece, configure las siguientes opciones:

   - **Seleccione la acción para direcciones URL potencialmente** malintencionadas desconocidas en los mensajes: seleccione Activar para habilitar la protección de vínculos seguros para vínculos en mensajes de correo electrónico. 

   - **Seleccione la acción para direcciones** URL desconocidas o  potencialmente malintencionadas en Microsoft Teams: seleccione Activar para habilitar la protección de vínculos seguros para vínculos en Teams.

   - **Aplicar el examen de direcciones URL** en tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos: seleccione esta opción para habilitar el examen en tiempo real de los vínculos de los mensajes de correo electrónico.

   - **Espere a que se complete el** examen de direcciones URL antes de entregar el mensaje: seleccione esta opción para esperar a que se complete el examen de url en tiempo real antes de entregar el mensaje.

   - **Aplicar vínculos seguros a los** mensajes de correo electrónico enviados dentro de la organización: seleccione esta opción para aplicar la directiva de vínculos seguros a los mensajes entre remitentes internos y destinatarios internos.

   - **No realizar un seguimiento de los clics del** usuario: deje esta opción sin activar para habilitar los clics del usuario de seguimiento en las direcciones URL de los mensajes de correo electrónico.

   - **No permitir que los usuarios hagan clic** en la dirección URL original: seleccione esta opción para impedir que los usuarios hagan clic en la dirección URL original en las páginas de [advertencia.](atp-safe-links.md#warning-pages-from-safe-links)

   - **No reescriba las siguientes** direcciones URL: permite el acceso a las direcciones URL especificadas que, de lo contrario, estarían bloqueadas por vínculos seguros.

     En el cuadro, escriba la dirección URL o el valor que desee y, a continuación, haga clic en ![Icono de botón Agregar](../../media/ITPro-EAC-AddIcon.png).

     Para quitar una entrada existente, selecciónelo y, a continuación, haga clic en ![Icono de botón Eliminar](../../media/ITPro-EAC-DeleteIcon.png).

     Para obtener la sintaxis de entrada, vea la sintaxis entry para la lista ["No reescribir las siguientes direcciones URL".](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)

   Para obtener información detallada acerca de esta configuración, vea La configuración de vínculos [seguros](atp-safe-links.md#safe-links-settings-for-email-messages) para los mensajes de correo electrónico y la configuración de [vínculos seguros para Microsoft Teams.](atp-safe-links.md#safe-links-settings-for-microsoft-teams)

   Para obtener más información sobre los valores recomendados para la configuración de directivas estándar y estricta, consulte [Configuración de directiva de vínculos seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)

   Cuando termine, haga clic en **Siguiente**.

5. En la **página Aplicada a** que aparece, identifique los destinatarios internos a los que se aplica la directiva.

   Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción. Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

   Haga **clic en Agregar una condición.** En la lista desplegable que aparece, seleccione una condición en **Aplicada si:**

   - **El destinatario es**: especifica uno o varios buzones, usuarios de correo o contactos de correo de su organización.
   - **El destinatario es miembro de**: Especifica uno o más grupos de la organización.
   - **El dominio del destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en su organización.

   Después de seleccionar la condición, aparece un desplegable correspondiente con **uno de estos** cuadros.

   - Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.
   - Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un valor.
   - Para agregar valores adicionales, haga clic en un área vacía del cuadro.
   - Para quitar entradas individuales, haga clic **en el** ![ icono Quitar del ](../../media/scc-remove-icon.png) valor.
   - Para quitar toda la condición, haga clic **en el** icono Quitar de ![ la ](../../media/scc-remove-icon.png) condición.

   Para agregar una condición adicional, haga clic **en Agregar una condición** y seleccione un valor restante en Aplicado **si**.

   Para agregar excepciones, haga **clic en Agregar una condición** y seleccione una excepción en Excepto **si**. La configuración y el comportamiento se muestran exactamente igual que las condiciones.

   Cuando termine, haga clic en **Siguiente**.

6. En la **página Revisar la configuración** que aparece, revisa la configuración. Puedes hacer clic **en Editar** en cada opción para modificarla.

   Cuando haya terminado, haga clic **en Finalizar.**

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>Usar el Centro de & cumplimiento para ver directivas de vínculos seguros

1. En el Centro de & cumplimiento, vaya **a** Vínculos seguros de ATP de la directiva de administración \>  \> **de amenazas.**

2. En la **página Vínculos** seguros, seleccione una directiva de la lista y haga clic en ella (no active la casilla).

   Los detalles de la directiva aparecen en un menú desplegable

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>Usar el Centro de seguridad & cumplimiento para modificar directivas de vínculos seguros

1. En el Centro de & cumplimiento, vaya **a** Vínculos seguros de ATP de la directiva de administración \>  \> **de amenazas.**

2. En la **página Vínculos** seguros, seleccione una directiva de la lista y haga clic en ella (no active la casilla).

3. En el control emergente de detalles de la directiva que aparece, haga clic **en Editar directiva.**

La configuración disponible en el control emergente que aparece es idéntica a la que se describe en la sección Usar el Centro de seguridad & cumplimiento para crear directivas [de vínculos seguros.](#use-the-security--compliance-center-to-create-safe-links-policies)

Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la directiva, consulte las secciones siguientes.

### <a name="enable-or-disable-safe-links-policies"></a>Habilitar o deshabilitar directivas de vínculos seguros

1. En el Centro de & cumplimiento, vaya **a** Vínculos seguros de ATP de la directiva de administración \>  \> **de amenazas.**

2. Observe el valor de la columna **Estado:**

   - Mueva el botón de alternancia a la izquierda para deshabilitar la directiva: ![Desactivar la directiva](../../media/scc-toggle-off.png).

   - Mueva el botón de alternancia a la derecha para habilitar la directiva: ![Activar la directiva](../../media/scc-toggle-on.png).

### <a name="set-the-priority-of-safe-links-policies"></a>Establecer la prioridad de las directivas de vínculos seguros

De forma predeterminada, a las directivas de vínculos seguros se les da una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen una prioridad menor que las directivas anteriores). Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor). Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).

Las directivas de vínculos seguros se muestran en el orden en que se procesan (la primera directiva tiene el **valor de** prioridad 0).

**Nota:** En el Centro de & cumplimiento, solo puede cambiar la prioridad de la directiva de vínculos seguros después de crearla. En PowerShell, puede invalidar la prioridad predeterminada al crear la regla de vínculos seguros (que puede afectar a la prioridad de las reglas existentes).

Para cambiar la prioridad de una directiva, suba o baje la directiva en la lista (no puede modificar directamente el número de **Prioridad** en el Centro de seguridad y cumplimiento).

1. En el Centro de & cumplimiento, vaya **a** Vínculos seguros de ATP de la directiva de administración \>  \> **de amenazas.**

2. En la **página Vínculos** seguros, seleccione una directiva de la lista y haga clic en ella (no active la casilla).

3. En el control emergente de detalles de la directiva que aparece, haga clic en el botón de prioridad disponible:

   - La directiva de vínculos seguros con **el valor de** **prioridad 0** solo tiene disponible el **botón** Disminuir prioridad.

   - La directiva de vínculos seguros con el valor **de prioridad** más bajo (por ejemplo, **3)** solo tiene el **botón Aumentar** prioridad disponible.

   - Si tiene tres o más directivas de vínculos seguros, las  directivas entre los valores de prioridad más alta y menor tienen disponibles los botones Aumentar prioridad **y** Disminuir prioridad.

4. Haga **clic en Aumentar prioridad** o **Disminuir** prioridad para cambiar el valor **de Prioridad.**

5. Cuando haya terminado, haga clic en **Cerrar**.

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>Usar el Centro de seguridad & cumplimiento para quitar directivas de vínculos seguros

1. En el Centro de & cumplimiento, vaya **a** Vínculos seguros de ATP de la directiva de administración \>  \> **de amenazas.**

2. En la **página Vínculos** seguros, seleccione una directiva de la lista y haga clic en ella (no active la casilla).

3. En el menú desplegable de detalles de la directiva que aparece, haga clic en Eliminar directiva y, a continuación, haga clic en **Sí** en el cuadro de diálogo de advertencia que aparece.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Usar Exchange Online PowerShell o EOP PowerShell independiente para configurar directivas de vínculos seguros

Como se describió anteriormente, una directiva de vínculos seguros consta de una directiva de vínculos seguros y una regla de vínculos seguros.

En PowerShell, la diferencia entre las directivas de vínculos seguros y las reglas de vínculos seguros es aparente. Las directivas de vínculos seguros se administran mediante los cmdlets **\* -SafeLinksPolicy** y se administran mediante los cmdlets **\* -SafeLinksRule.**

- En PowerShell, primero se crea la directiva de vínculos seguros y, a continuación, se crea la regla de vínculos seguros que identifica la directiva a la que se aplica la regla.
- En PowerShell, puede modificar la configuración de la directiva de vínculos seguros y la regla de vínculos seguros por separado.
- Al quitar una directiva de vínculos seguros de PowerShell, la regla de vínculos seguros correspondiente no se quita automáticamente y viceversa.

### <a name="use-powershell-to-create-safe-links-policies"></a>Usar PowerShell para crear directivas de vínculos seguros

Crear una directiva de vínculos seguros en PowerShell es un proceso de dos pasos:

1. Cree la directiva de vínculos seguros.
2. Cree la regla de vínculos seguros que especifique la directiva de vínculos seguros a la que se aplica la regla.

 **Notas**:

- Puede crear una nueva regla de vínculos seguros y asignarle una directiva de vínculos seguros existente y sin asociar. Una regla de vínculos seguros no se puede asociar a más de una directiva de vínculos seguros.

- Puede configurar las siguientes opciones en las nuevas directivas de vínculos seguros en PowerShell que no estén disponibles en el Centro de seguridad & Cumplimiento hasta después de crear la directiva:

  - Cree la nueva directiva como deshabilitada _(habilitada en_ `$false` el cmdlet **New-SafeLinksRule).**
  - Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_ ) en el cmdlet **New-SafeLinksRule).**

- Una nueva directiva de vínculos seguros que cree en PowerShell no será visible en el Centro de seguridad & Cumplimiento hasta que asigne la directiva a una regla de vínculos seguros.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Paso 1: Usar PowerShell para crear una directiva de vínculos seguros

Para crear una directiva de vínculos seguros, use esta sintaxis:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

**Notas**:

- Para obtener más información acerca de la sintaxis de entrada que se va a usar para el parámetro _DoNotRewriteUrls,_ vea la sintaxis entry para la lista ["No reescribir](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)las siguientes direcciones URL".

- Para obtener sintaxis adicional que puede usar para el parámetro _DoNotRewriteUrls_ al modificar directivas de vínculos seguros existentes mediante el cmdlet **Set-SafeLinksPolicy,** vea la sección Usar [PowerShell](#use-powershell-to-modify-safe-links-policies) para modificar directivas de vínculos seguros más adelante en este artículo.

En este ejemplo se crea una directiva de vínculos seguros denominada Contoso All con los siguientes valores:

- Active el análisis y la reescritura de direcciones URL en los mensajes de correo electrónico.
- Activar el examen de direcciones URL en Teams (solo vista previa de TAP).
- Activa el examen en tiempo real de las direcciones URL en las que se ha hecho clic, incluidos los vínculos en los que se hace clic y que apuntan a archivos.
- Espere a que se complete el examen de direcciones URL antes de entregar el mensaje.
- Active la reescritura y el examen de direcciones URL para los mensajes internos.
- Realizar un seguimiento de los clics de usuario relacionados con la protección de vínculos seguros (no estamos usando el parámetro _DoNotTrackUserClicks_ y el valor predeterminado es $false, lo que significa que se realiza un seguimiento de los clics del usuario).
- No permita a los usuarios hacer clic en la dirección URL original.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Paso 2: Usar PowerShell para crear una regla de vínculos seguros

Para crear una regla de vínculos seguros, use esta sintaxis:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

En este ejemplo se crea una regla de vínculos seguros denominada Contoso All con las siguientes condiciones:

- La regla está asociada a la directiva de vínculos seguros denominada Contoso All.
- La regla se aplica a todos los destinatarios del contoso.com dominio.
- Como no estamos usando el parámetro _Priority,_ se usa la prioridad predeterminada.
- La regla está habilitada (no estamos usando el parámetro _Enabled_ y el valor predeterminado es `$true` ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).

### <a name="use-powershell-to-view-safe-links-policies"></a>Usar PowerShell para ver directivas de vínculos seguros

Para ver las directivas de vínculos seguros existentes, use la siguiente sintaxis:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista resumida de todas las directivas de vínculos seguros.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

En este ejemplo se devuelve información detallada de la directiva de vínculos seguros denominada Contoso Executives.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).

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

En este ejemplo se devuelve información detallada de la regla de vínculos seguros denominada Contoso Executives.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).

### <a name="use-powershell-to-modify-safe-links-policies"></a>Usar PowerShell para modificar directivas de vínculos seguros

No puede cambiar el nombre de una directiva de vínculos seguros en PowerShell (el cmdlet **Set-SafeLinksPolicy** no tiene ningún _parámetro Name)._ Cuando cambia el nombre de una directiva de vínculos seguros en el Centro de seguridad & cumplimiento, solo cambia el nombre de la regla de vínculos _seguros._

La única consideración adicional para modificar directivas de vínculos seguros en PowerShell es la sintaxis disponible para el parámetro _DoNotRewriteUrls_ (la lista ["No reescribir](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)las siguientes direcciones URL" ):

- Para agregar valores que reemplacen las entradas existentes, use la sintaxis siguiente: `"Entry1","Entry2,..."EntryN"` .
- Para agregar o quitar valores sin que ello afecte a otras entradas existentes, use la siguiente sintaxis: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

De lo contrario, la misma configuración está disponible al crear una directiva de vínculos seguros, como se describe en el paso [1: Usar PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) para crear una sección de directiva de vínculos seguros anteriormente en este artículo.

Para modificar una directiva de vínculos seguros, use esta sintaxis:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).

### <a name="use-powershell-to-modify-safe-links-rules"></a>Usar PowerShell para modificar reglas de vínculos seguros

La única configuración que no está disponible al modificar una regla de vínculos seguros en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada. Para habilitar o deshabilitar reglas de vínculos seguros existentes, consulte la sección siguiente.

De lo contrario, la misma configuración está disponible al crear una regla como se describe en el paso [2: Usar PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) para crear una sección de regla de vínculos seguros anteriormente en este artículo.

Para modificar una regla de vínculos seguros, use esta sintaxis:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>Usar PowerShell para habilitar o deshabilitar reglas de vínculos seguros

Habilitar o deshabilitar una regla de vínculos seguros en PowerShell habilita o deshabilita toda la directiva de vínculos seguros (la regla de vínculos seguros y la directiva de vínculos seguros asignada).

Para habilitar o deshabilitar una regla de vínculos seguros en PowerShell, use esta sintaxis:

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

En este ejemplo se deshabilita la regla de vínculos seguros denominada Marketing Department.

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

Este ejemplo habilita la misma regla.

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) y [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>Usar PowerShell para establecer la prioridad de las reglas de vínculos seguros

El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo que se puede establecer depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.

Para establecer la prioridad de una regla de vínculos seguros en PowerShell, use la siguiente sintaxis:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

**Nota:** Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-SafeLinksRule.**

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-remove-safe-links-policies"></a>Usar PowerShell para quitar directivas de vínculos seguros

Al usar PowerShell para quitar una directiva de vínculos seguros, no se quita la regla de vínculos seguros correspondiente.

Para quitar una directiva de vínculos seguros en PowerShell, use esta sintaxis:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

En este ejemplo se quita la directiva de vínculos seguros denominada Marketing Department.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).

### <a name="use-powershell-to-remove-safe-links-rules"></a>Usar PowerShell para quitar reglas de vínculos seguros

Al usar PowerShell para quitar una regla de vínculos seguros, no se quita la directiva de vínculos seguros correspondiente.

Para quitar una regla de vínculos seguros en PowerShell, use esta sintaxis:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

En este ejemplo se quita la regla de vínculos seguros denominada Marketing Department.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).

Para comprobar que Vínculos seguros está analizando mensajes, compruebe los informes disponibles de Microsoft Defender para Office 365. Para obtener más información, vea Ver informes de Defender para [Office 365](view-reports-for-atp.md) y Usar el Explorador en el Centro de [& cumplimiento.](threat-explorer.md)

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha creado, modificado o quitado correctamente directivas de vínculos a prueba de problemas, siga uno de estos pasos:

- En el Centro de & cumplimiento, vaya **a** Vínculos seguros de ATP de la directiva de administración \>  \> **de amenazas.** Compruebe la lista de directivas, sus **valores de** estado y sus **valores de** prioridad. Para ver más detalles, seleccione la directiva de la lista y vea los detalles en el menú desplegable.

- En Exchange Online PowerShell o Exchange Online Protection PowerShell, reemplace por el nombre de la directiva o regla, ejecute el siguiente comando y \<Name\> compruebe la configuración:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
