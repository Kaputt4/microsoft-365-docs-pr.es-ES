---
title: Configurar directivas de datos adjuntos seguros en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo definir directivas de datos adjuntos seguros para proteger su organización de archivos malintencionados en el correo electrónico.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 012c591d620fdf5abe5aad697404bea8cea95d1a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290554"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Configurar directivas de datos adjuntos seguros en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](office-365-atp.md). Si es un usuario principal que busca información sobre el examen de datos adjuntos en Outlook, vea Advanced [Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Datos adjuntos seguros es una característica de Microsoft Defender para [Office 365](office-365-atp.md) que usa un entorno virtual para comprobar los datos adjuntos de los mensajes de correo electrónico entrantes después de que la protección antimalware los haya analizado en [Exchange Online Protection (EOP),](anti-malware-protection.md)pero antes de la entrega a los destinatarios. Para obtener más información, vea [Datos adjuntos seguros en Microsoft Defender para Office 365.](atp-safe-attachments.md)

No hay ninguna directiva integrada o predeterminada de datos adjuntos seguros. Para obtener el examen de datos adjuntos seguros de datos adjuntos de mensajes de correo electrónico, debe crear una o más directivas de datos adjuntos seguros, tal como se describe en este artículo.

Puede configurar directivas de datos adjuntos seguros en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones elegibles de Microsoft 365 con buzones en Exchange Online; EOP PowerShell independiente para organizaciones sin buzones de Exchange Online, pero con suscripciones de complemento de Defender para Office 365).

Los elementos básicos de una directiva de datos adjuntos seguros son:

- La directiva de datos adjuntos **seguros:** especifica las acciones para detecciones de malware desconocidas, si se envían mensajes con datos adjuntos de malware a una dirección de correo electrónico especificada y si se entregan mensajes si no se puede completar el examen de datos adjuntos seguros.
- **La regla de datos adjuntos seguros:** especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva).

La diferencia entre estos dos elementos no es obvia cuando se administran directivas de datos adjuntos seguros en el Centro de & cumplimiento:

- Al crear una directiva de datos adjuntos seguros, realmente está creando una regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asociada al mismo tiempo con el mismo nombre para ambos.
- Al modificar una directiva de datos adjuntos seguros, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada, y los filtros de destinatarios modifican la regla de datos adjuntos seguros. Todas las demás opciones modifican la directiva de datos adjuntos seguros asociada.
- Al quitar una directiva de datos adjuntos seguros, se quitan la regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asociada.

En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado. Para obtener más información, vea la sección Usar Exchange Online PowerShell o [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) independiente para configurar directivas de datos adjuntos seguros más adelante en este artículo.

> [!NOTE]
> En el área de configuración global de la configuración de datos adjuntos seguros, se configuran características que no dependen de las directivas de datos adjuntos seguros. Para obtener instrucciones, vea Activar datos adjuntos seguros para [SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) y documentos seguros [en Microsoft 365 E5.](safe-docs.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página **Datos adjuntos** seguros, use <https://protection.office.com/safeattachmentv2> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Deberá tener asignados permisos antes de poder realizar los procedimientos descritos en este artículo:
  - Para crear, modificar y eliminar directivas de datos adjuntos  seguros, debe ser miembro de los grupos de roles  Administración de la organización o Administrador de seguridad en el Centro de seguridad & Cumplimiento y miembro del grupo de roles Administración de la organización en Exchange Online.  
  - Para obtener acceso de solo lectura a las directivas de datos  adjuntos seguros, debe ser miembro de los grupos de roles Lector **global** o Lector de seguridad en el Centro de seguridad & cumplimiento.

  Para obtener más información, vea [Permisos en el Centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md) y permisos en Exchange [Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para obtener la configuración recomendada para las directivas de datos adjuntos seguros, consulte [Configuración de datos adjuntos seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)

- Espere hasta 30 minutos para que se aplique una directiva nueva o actualizada.

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>Usar el Centro de seguridad & cumplimiento para crear directivas de datos adjuntos seguros

La creación de una directiva de datos adjuntos seguros personalizada en el Centro de seguridad y cumplimiento de & crea la regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asociada al mismo tiempo con el mismo nombre para ambos.

1. En el Centro de & cumplimiento, vaya a Directiva **de administración de** amenazas Datos \> **adjuntos** seguros \> **de ATP.**

2. En la página **Datos adjuntos** seguros, haga clic **en Crear**.

3. Se **abrirá el Asistente para nueva directiva de datos adjuntos** seguros. En la **página Nombre de la directiva,** configure las siguientes opciones:

   - **Nombre**: escriba un nombre único y descriptivo para la directiva.

   - **Descripción**: escriba una descripción opcional para la directiva.

   Cuando termine, haga clic en **Siguiente**.

4. En la **página Configuración** que aparece, configure las siguientes opciones:

   - Respuesta de malware desconocido de datos **adjuntos seguros:** seleccione uno de los siguientes valores:

     - **Desactivado:** normalmente, no recomendamos este valor.
     - **Monitor**
     - **Bloque:** este es el valor predeterminado y el valor recomendado en las directivas de seguridad preestablecidas Estándar y [Estricto.](preset-security-policies.md)
     - **Replace**
     - **Entrega dinámica (característica de vista previa)**

     Estos valores se explican en la configuración [de directiva de datos adjuntos seguros.](atp-safe-attachments.md#safe-attachments-policy-settings)

   - Envíe los datos adjuntos a la siguiente dirección de correo electrónico:  para los valores de acción **Bloquear,** **Supervisar** o **Reemplazar**, puede seleccionar Habilitar redireccionamiento para enviar mensajes que contienen datos adjuntos de malware a la dirección de correo electrónico interna o externa especificada para su análisis e investigación. 

     La recomendación para la configuración de directivas estándar y estricta es habilitar el redireccionamiento. Para obtener más información, vea [Configuración de datos adjuntos seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)

   - Aplique la selección anterior si se ha completado el análisis de malware para datos adjuntos o si se produce un error: la acción especificada por la respuesta de **malware** desconocido de datos adjuntos seguros se toma en los mensajes incluso cuando no se puede completar el examen de datos **adjuntos** seguros. Si seleccionó esta opción, seleccione siempre Redirección **habilitada.** De lo contrario, es posible que se pierdan mensajes.

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

   Para agregar excepciones, haga clic **en Agregar una condición** y seleccione una excepción en Excepto **si**. La configuración y el comportamiento se muestran exactamente igual que las condiciones.

   Cuando termine, haga clic en **Siguiente**.

6. En la **página Revisar la configuración** que aparece, revisa la configuración. Puedes hacer clic **en Editar** en cada opción para modificarla.

   Cuando haya terminado, haga clic **en Finalizar.**

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>Usar el Centro de seguridad & cumplimiento para ver directivas de datos adjuntos seguros

1. En el Centro de & cumplimiento, vaya a Directiva **de administración de** amenazas Datos \> **adjuntos** seguros \> **de ATP.**

2. En la **página Datos adjuntos** seguros, seleccione una directiva de la lista y haga clic en ella (no active la casilla).

   Los detalles de la directiva aparecen en un menú desplegable

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>Usar el Centro de seguridad & cumplimiento para modificar directivas de datos adjuntos seguros

1. En el Centro de & cumplimiento, vaya a Directiva **de administración de** amenazas Datos \> **adjuntos** seguros \> **de ATP.**

2. En la **página Datos adjuntos** seguros, seleccione una directiva de la lista y haga clic en ella (no active la casilla).

3. En el control emergente de detalles de la directiva que aparece, haga clic **en Editar directiva.**

La configuración disponible en el control emergente que aparece es idéntica a la que se describe en la sección Usar el Centro de seguridad [& cumplimiento](#use-the-security--compliance-center-to-create-safe-attachments-policies) para crear directivas de datos adjuntos seguros.

Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la directiva, consulte las secciones siguientes.

### <a name="enable-or-disable-safe-attachments-policies"></a>Habilitar o deshabilitar directivas de datos adjuntos seguros

1. En el Centro de & cumplimiento, vaya a Directiva **de administración de** amenazas Datos \> **adjuntos** seguros \> **de ATP.**

2. Observe el valor de la columna **Estado:**

   - Mover el botón de alternancia a la izquierda ![Desactivar la directiva](../../media/scc-toggle-off.png) para deshabilitar la directiva.

   - Mover el botón de alternancia a la derecha ![Activar la directiva](../../media/scc-toggle-on.png) para habilitar la directiva.

### <a name="set-the-priority-of-safe-attachments-policies"></a>Establecer la prioridad de las directivas de datos adjuntos seguros

De forma predeterminada, a las directivas de datos adjuntos seguros se les da una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen una prioridad menor que las directivas anteriores). Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor). Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).

Las directivas de datos adjuntos seguros se muestran en el orden en que se procesan (la primera directiva tiene el **valor de** prioridad 0).

**Nota:** En el Centro de & cumplimiento, solo puede cambiar la prioridad de la directiva de datos adjuntos seguros después de crearla. En PowerShell, puede invalidar la prioridad predeterminada al crear la regla de datos adjuntos seguros (que puede afectar a la prioridad de las reglas existentes).

Para cambiar la prioridad de una directiva, suba o baje la directiva en la lista (no puede modificar directamente el número de **Prioridad** en el Centro de seguridad y cumplimiento).

1. En el Centro de & cumplimiento, vaya a Directiva **de administración de** amenazas Datos \> **adjuntos** seguros \> **de ATP.**

2. En la **página Datos adjuntos** seguros, seleccione una directiva de la lista y haga clic en ella (no active la casilla).

3. En el control emergente de detalles de la directiva que aparece, haga clic en el botón de prioridad disponible.

   - La directiva de datos adjuntos seguros con **el** valor **de prioridad 0** solo tiene disponible el **botón** Disminuir prioridad.

   - La directiva de datos adjuntos seguros con el valor **de prioridad** más bajo (por ejemplo, **3)** solo tiene disponible **el** botón Aumentar prioridad.

   - Si tiene tres o más directivas de datos adjuntos seguros,  las directivas entre los valores de mayor y menor prioridad tienen disponibles los botones Aumentar prioridad **y** Disminuir prioridad.

4. Haga **clic en Aumentar prioridad** o **Disminuir** prioridad para cambiar el valor **de Prioridad.**

5. Cuando haya terminado, haga clic en **Cerrar**.

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>Usar el Centro de seguridad & cumplimiento para quitar directivas de datos adjuntos seguros

1. En el Centro de & cumplimiento, vaya a Directiva **de administración de** amenazas Datos \> **adjuntos** seguros \> **de ATP.**

2. En la **página Datos adjuntos** seguros, seleccione una directiva de la lista y haga clic en ella (no active la casilla).

3. En el menú desplegable de detalles de la directiva que aparece, haga clic en Eliminar directiva y, a continuación, haga clic en **Sí** en el cuadro de diálogo de advertencia que aparece.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Usar Exchange Online PowerShell o EOP PowerShell independiente para configurar directivas de datos adjuntos seguros

Como se describió anteriormente, una directiva de datos adjuntos seguros consta de una directiva de datos adjuntos seguros y una regla de datos adjuntos seguros.

En PowerShell, la diferencia entre las directivas de datos adjuntos seguros y las reglas de datos adjuntos seguros es aparente. Las directivas de datos adjuntos seguros se administran mediante los cmdlets **\* -SafeAttachmentPolicy** y se administran mediante los cmdlets **\* -SafeAttachmentRule.**

- En PowerShell, primero se crea la directiva de datos adjuntos seguros y, a continuación, se crea la regla de datos adjuntos seguros que identifica la directiva a la que se aplica la regla.
- En PowerShell, puede modificar la configuración de la directiva de datos adjuntos seguros y la regla de datos adjuntos seguros por separado.
- Al quitar una directiva de datos adjuntos seguros de PowerShell, la regla de datos adjuntos seguros correspondiente no se quita automáticamente y viceversa.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>Usar PowerShell para crear directivas de datos adjuntos seguros

Crear una directiva de datos adjuntos seguros en PowerShell es un proceso de dos pasos:

1. Cree la directiva de datos adjuntos seguros.
2. Cree la regla de datos adjuntos seguros que especifique la directiva de datos adjuntos seguros a la que se aplica la regla.

 **Notas**:

- Puede crear una nueva regla de datos adjuntos seguros y asignarle una directiva de datos adjuntos seguros existente y sin asociar. Una regla de datos adjuntos seguros no se puede asociar a más de una directiva de datos adjuntos seguros.

- Puede configurar las siguientes opciones en las nuevas directivas de datos adjuntos seguros en PowerShell que no estén disponibles en el Centro de seguridad & Cumplimiento hasta después de crear la directiva:
  - Cree la nueva directiva como deshabilitada _(habilitada en_ `$false` el cmdlet **New-SafeAttachmentRule).**
  - Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_ ) en el cmdlet **New-SafeAttachmentRule).**

- Una nueva directiva de datos adjuntos seguros que cree en PowerShell no será visible en el Centro de seguridad & Cumplimiento hasta que asigne la directiva a una regla de datos adjuntos seguros.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Paso 1: Usar PowerShell para crear una directiva de datos adjuntos seguros

Para crear una directiva de datos adjuntos seguros, use esta sintaxis:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

En este ejemplo se crea una directiva de datos adjuntos segura denominada Contoso All con los siguientes valores:

- Bloquear los mensajes que se encuentran que contienen malware mediante el examen de documentos seguros (no estamos usando el parámetro _Action_ y el valor predeterminado es `Block` ).
- El redireccionamiento está habilitado y los mensajes que se encuentran que contienen malware se envían a sec-ops@contoso.com para su análisis e investigación.
- Si el análisis de datos adjuntos seguros no está disponible o encuentra errores, no entregue el mensaje (no estamos usando el parámetro _ActionOnError_ y el valor predeterminado es `$true` ).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>Paso 2: Usar PowerShell para crear una regla de datos adjuntos segura

Para crear una regla de datos adjuntos segura, use esta sintaxis:

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

En este ejemplo se crea una regla de datos adjuntos segura denominada Contoso All con las siguientes condiciones:

- La regla está asociada a la directiva de datos adjuntos seguros denominada Contoso All.
- La regla se aplica a todos los destinatarios del contoso.com dominio.
- Como no estamos usando el parámetro _Priority,_ se usa la prioridad predeterminada.
- La regla está habilitada (no estamos usando el parámetro _Enabled_ y el valor predeterminado es `$true` ).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).

### <a name="use-powershell-to-view-safe-attachment-policies"></a>Usar PowerShell para ver directivas de datos adjuntos seguros

Para ver las directivas de datos adjuntos seguros existentes, use la siguiente sintaxis:

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista resumida de todas las directivas de datos adjuntos seguros.

```PowerShell
Get-SafeAttachmentPolicy
```

En este ejemplo se devuelve información detallada de la directiva de datos adjuntos seguros denominada Contoso Executives.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).

### <a name="use-powershell-to-view-safe-attachment-rules"></a>Usar PowerShell para ver reglas de datos adjuntos seguros

Para ver las reglas de datos adjuntos seguros existentes, use la siguiente sintaxis:

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista resumida de todas las reglas de datos adjuntos seguros.

```PowerShell
Get-SafeAttachmentRule
```

Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

En este ejemplo se devuelve información detallada de la regla de datos adjuntos seguros denominada Contoso Executives.

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>Usar PowerShell para modificar directivas de datos adjuntos seguros

No puede cambiar el nombre de una directiva de datos adjuntos seguros en PowerShell (el cmdlet **Set-SafeAttachmentPolicy** no tiene ningún _parámetro Name)._ Cuando cambia el nombre de una directiva de datos adjuntos seguros en el Centro de seguridad & cumplimiento, solo cambia el nombre de la regla de datos _adjuntos seguros._

De lo contrario, la misma configuración está disponible cuando se crea una directiva de datos adjuntos seguros como se describe en el paso [1: Usar PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) para crear una sección de directiva de datos adjuntos seguros anteriormente en este artículo.

Para modificar una directiva de datos adjuntos seguros, use esta sintaxis:

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>Usar PowerShell para modificar reglas de datos adjuntos seguros

La única configuración que no está disponible al modificar una regla de datos adjuntos seguros en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada. Para habilitar o deshabilitar las reglas de datos adjuntos seguros existentes, consulte la sección siguiente.

De lo contrario, la misma configuración está disponible al crear una regla como se describe en el paso [2: Usar PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) para crear una sección de regla de datos adjuntos seguros anteriormente en este artículo.

Para modificar una regla de datos adjuntos seguros, use esta sintaxis:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>Usar PowerShell para habilitar o deshabilitar reglas de datos adjuntos seguros

Habilitar o deshabilitar una regla de datos adjuntos seguros en PowerShell habilita o deshabilita toda la directiva de datos adjuntos seguros (la regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asignada).

Para habilitar o deshabilitar una regla de datos adjuntos seguros en PowerShell, use esta sintaxis:

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

En este ejemplo se deshabilita la regla de datos adjuntos seguros denominada Marketing Department.

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

Este ejemplo habilita la misma regla.

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) y [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>Usar PowerShell para establecer la prioridad de las reglas de datos adjuntos seguros

El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo que se puede establecer depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.

Para establecer la prioridad de una regla de datos adjuntos seguros en PowerShell, use la siguiente sintaxis:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**Nota:** Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-SafeAttachmentRule.**

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>Usar PowerShell para quitar directivas de datos adjuntos seguros

Al usar PowerShell para quitar una directiva de datos adjuntos seguros, no se quita la regla de datos adjuntos seguros correspondiente.

Para quitar una directiva de datos adjuntos seguros en PowerShell, use esta sintaxis:

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

En este ejemplo se quita la directiva de datos adjuntos seguros denominada Marketing Department.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>Usar PowerShell para quitar reglas de datos adjuntos seguros

Al usar PowerShell para quitar una regla de datos adjuntos seguros, no se quita la directiva de datos adjuntos seguros correspondiente.

Para quitar una regla de datos adjuntos seguros en PowerShell, use esta sintaxis:

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

En este ejemplo se quita la regla de datos adjuntos seguros denominada Marketing Department.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha creado, modificado o quitado correctamente directivas de datos adjuntos seguros, siga uno de estos pasos:

- En el Centro de & cumplimiento, vaya a Directiva **de administración de** amenazas Datos \> **adjuntos** seguros \> **de ATP.** Compruebe la lista de directivas, sus **valores de** estado y sus **valores de** prioridad. Para ver más detalles, seleccione la directiva de la lista y vea los detalles en el menú desplegable.

- En Exchange Online PowerShell o Exchange Online Protection PowerShell, reemplace por el nombre de la directiva o regla, ejecute el siguiente comando y \<Name\> compruebe la configuración:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Para comprobar que Datos adjuntos seguros está analizando mensajes, compruebe los informes disponibles de Defender para Office 365. Para obtener más información, vea Ver informes de Defender para [Office 365](view-reports-for-atp.md) y Usar el Explorador en el Centro de [& cumplimiento.](threat-explorer.md)
