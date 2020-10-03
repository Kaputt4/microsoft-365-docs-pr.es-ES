---
title: Configurar las Directivas de datos adjuntos seguros en la ATP de Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo definir directivas de datos adjuntos seguros para proteger a su organización de archivos malintencionados en el correo electrónico.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6794cf72afdb94e587e06319f87a406521ad2710
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350388"
---
# <a name="set-up-safe-attachments-policies-in-office-365-atp"></a>Configurar las Directivas de datos adjuntos seguros en la ATP de Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md). Si es un usuario doméstico que busca información sobre el análisis de datos adjuntos en Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Datos adjuntos seguros es una característica de la [protección contra amenazas avanzada (ATP) de Office 365](office-365-atp.md) que usa un entorno virtual para comprobar los datos adjuntos en los mensajes de correo electrónico entrantes después de que hayan sido examinados por [protección antimalware en Exchange Online Protection (EOP)](anti-malware-protection.md), pero antes de entregarlos a los destinatarios. Para obtener más información, consulte [datos adjuntos seguros en Office 365 ATP](atp-safe-attachments.md).

No hay una directiva de datos adjuntos seguros integrada o predeterminada. Para obtener datos adjuntos seguros del análisis de datos adjuntos de mensajes de correo electrónico, debe crear una o más directivas de datos adjuntos seguros, como se describe en este artículo.

Puede configurar directivas de datos adjuntos seguros en el centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para las organizaciones de Microsoft 365 con buzones en Exchange Online; independiente de EOP para las organizaciones sin buzones de Exchange Online, pero con Office 365 las suscripciones complementarias de ATP).

Los elementos básicos de una directiva de datos adjuntos seguros son los siguientes:

- **La Directiva de datos adjuntos seguros**: especifica las acciones para detecciones de malware desconocidas, si se deben enviar mensajes con datos adjuntos de malware a una dirección de correo electrónico especificada y si se deben entregar mensajes si no se puede completar el análisis de datos adjuntos seguros.
- **La regla de datos adjuntos seguros**: especifica la prioridad y los filtros de destinatarios (a los que se aplica la Directiva).

La diferencia entre estos dos elementos no es obvia cuando se administran directivas de datos adjuntos seguros en el centro de seguridad & cumplimiento:

- Al crear una directiva de datos adjuntos seguros, en realidad está creando una regla de datos adjuntos seguros y la Directiva de datos adjuntos seguros asociada al mismo tiempo con el mismo nombre para ambas.
- Cuando modifica una directiva de datos adjuntos seguros, la configuración relacionada con el nombre, la prioridad, habilitada o deshabilitada y los filtros de destinatarios modifican la regla de datos adjuntos seguros. Todas las demás opciones modifican la Directiva de datos adjuntos seguros asociada.
- Al quitar una directiva de datos adjuntos seguros, se quitan la regla de datos adjuntos seguros y la Directiva de datos adjuntos seguros asociada.

En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado. Para obtener más información, vea la sección [usar Exchange Online PowerShell o Standalone EOP PowerShell para configurar directivas de datos adjuntos seguros](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) , más adelante en este artículo.

> [!NOTE]
> En el área configuración global de datos adjuntos seguros, puede configurar características que no dependen de las directivas de datos adjuntos seguros. Para obtener instrucciones, consulte [Activar ATP para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) y [documentos seguros en Microsoft 365 E5](safe-docs.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página **datos adjuntos seguros de ATP** , use <https://protection.office.com/safeattachmentv2> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Para ver, crear, modificar y eliminar directivas de datos adjuntos seguros, debe pertenecer a uno de los siguientes grupos de roles:

  - **Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).
  - **Administración** de la organización en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Para conocer la configuración recomendada para las directivas de datos adjuntos seguros, consulte [configuración de datos adjuntos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).

- Permitir que se aplique una directiva nueva o actualizada durante un máximo de 30 minutos.

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>Usar el centro de seguridad & cumplimiento para crear directivas de datos adjuntos seguros

La creación de una directiva de datos adjuntos seguros personalizada en el centro de seguridad & cumplimiento crea la regla de datos adjuntos seguros y la Directiva de datos adjuntos seguros asociada al mismo tiempo con el mismo nombre para ambas.

1. En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **datos adjuntos seguros de ATP**de directiva de administración de amenazas.

2. En la página **datos adjuntos seguros** , haga clic en **crear**.

3. Se abre el Asistente para **nueva Directiva de datos adjuntos seguros** . En la página **asigne un nombre a la Directiva** , configure las siguientes opciones:

   - **Nombre**: escriba un nombre único y descriptivo para la directiva.

   - **Descripción**: escriba una descripción opcional para la directiva.

   Cuando termine, haga clic en **Siguiente**.

4. En la página de **configuración** que aparece, configure las siguientes opciones:

   - **Datos adjuntos seguros respuesta de malware desconocida**: Seleccione uno de los siguientes valores:

     - **Desactivado**: normalmente, no se recomienda este valor.
     - **Monitor**
     - **Block**: este es el valor predeterminado y el valor recomendado en las directivas de seguridad estándar y estrictas [preestablecidas](preset-security-policies.md).
     - **Replace**
     - **Entrega dinámica (característica de versión preliminar)**

     Estos valores se explican en la configuración de la [Directiva de datos adjuntos seguros](atp-safe-attachments.md#safe-attachments-policy-settings).

   - **Enviar los datos adjuntos a la siguiente dirección de correo electrónico**: para los valores de la acción **bloquear**, **supervisar**o **reemplazar**, puede seleccionar **Habilitar redireccionamiento** para enviar mensajes que contienen datos adjuntos de malware a la dirección de correo electrónico interna o externa especificada para el análisis y la investigación.

     La recomendación para la configuración de directivas estándar y estricta es habilitar la redirección. Para obtener más información, consulte [configuración de datos adjuntos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).

   - **Aplicar la selección anterior si el análisis de malware para archivos adjuntos se agota el tiempo de espera o error**: la acción especificada por la **respuesta de malware de datos adjuntos seguros** no se realiza en los mensajes, incluso cuando no se completa el análisis de datos adjuntos seguros. Seleccione siempre esta opción si selecciona **Habilitar redirección**. De lo contrario, los mensajes podrían perderse.

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
   - Para quitar entradas individuales, haga **Remove** clic en ![ el icono quitar quitar del ](../../media/scc-remove-icon.png) valor.
   - Para quitar toda la condición, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación en la condición.

   Para agregar una condición adicional, haga clic en **Agregar condición** y seleccione un valor restante en **aplicado si**.

   Para agregar excepciones, haga clic en **Agregar una condición** y seleccione una excepción en **excepto si**. La configuración y el comportamiento se muestran exactamente igual que las condiciones.

   Cuando termine, haga clic en **Siguiente**.

6. En la página **Revise la configuración** que aparece, revise la configuración. Puede hacer clic en **Editar** en cada configuración para modificarla.

   Cuando haya terminado, haga clic en **Finalizar**.

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>Usar el centro de seguridad & cumplimiento para ver directivas de datos adjuntos seguros

1. En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **datos adjuntos seguros de ATP**de directiva de administración de amenazas.

2. En la página **datos adjuntos seguros** , seleccione una directiva de la lista y haga clic en ella (no active la casilla de verificación).

   Los detalles de la Directiva aparecen en un vuelo hacia fuera

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>Usar el centro de seguridad & cumplimiento para modificar directivas de datos adjuntos seguros

1. En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **datos adjuntos seguros de ATP**de directiva de administración de amenazas.

2. En la página **datos adjuntos seguros** , seleccione una directiva de la lista y haga clic en ella (no active la casilla de verificación).

3. En los detalles de la Directiva hacia fuera que aparece, haga clic en **Editar Directiva**.

La configuración disponible en la volar hacia fuera que aparece es idéntica a la que se describe en la sección [usar el centro de seguridad & cumplimiento para crear directivas de datos adjuntos seguros](#use-the-security--compliance-center-to-create-safe-attachments-policies) .

Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la Directiva, consulte las siguientes secciones.

### <a name="enable-or-disable-safe-attachments-policies"></a>Habilitar o deshabilitar las directivas de datos adjuntos seguros

1. En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **datos adjuntos seguros de ATP**de directiva de administración de amenazas.

2. Observe el valor de la columna **Estado** :

   - Mover el botón de alternancia a la izquierda ![Desactivar Directiva](../../media/scc-toggle-off.png) para deshabilitar la Directiva.

   - Mover el botón de alternancia a la derecha ![Activar la Directiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) para habilitar la Directiva.

### <a name="set-the-priority-of-safe-attachments-policies"></a>Establecer la prioridad de las directivas de datos adjuntos seguros

De forma predeterminada, las directivas de datos adjuntos seguros reciben una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen prioridad más baja que las directivas anteriores). Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor). Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).

Las directivas de datos adjuntos seguros se muestran en el orden en que se procesan (la primera Directiva tiene el valor de **prioridad** 0).

**Nota**: en el centro de seguridad & cumplimiento, solo puede cambiar la prioridad de la Directiva de datos adjuntos seguros después de crearla. En PowerShell, puede invalidar la prioridad predeterminada al crear la regla de datos adjuntos seguros (lo que puede afectar a la prioridad de las reglas existentes).

Para cambiar la prioridad de una directiva, suba o baje la directiva en la lista (no puede modificar directamente el número de **Prioridad** en el Centro de seguridad y cumplimiento).

1. En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **datos adjuntos seguros de ATP**de directiva de administración de amenazas.

2. En la página **datos adjuntos seguros** , seleccione una directiva de la lista y haga clic en ella (no active la casilla de verificación).

3. En los detalles de la Directiva volar hacia fuera que aparece, haga clic en el botón prioridad disponible.

   - La Directiva de datos adjuntos seguros con el valor de **prioridad** **0** sólo tiene disponible el botón **disminuir prioridad** .

   - La Directiva de datos adjuntos seguros con el valor de **prioridad** más bajo (por ejemplo, **3**) solo tiene el botón **aumentar prioridad** disponible.

   - Si tiene tres o más directivas de datos adjuntos seguros, las directivas entre los valores de prioridad mayor y menor tienen los botones **aumentar prioridad** y **disminuir prioridad** disponibles.

4. Haga clic en **aumentar prioridad** o **disminuir prioridad** para cambiar el valor de **prioridad** .

5. Cuando haya terminado, haga clic en **Cerrar**.

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>Usar el centro de seguridad & cumplimiento para quitar directivas de datos adjuntos seguros

1. En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **datos adjuntos seguros de ATP**de directiva de administración de amenazas.

2. En la página **datos adjuntos seguros** , seleccione una directiva de la lista y haga clic en ella (no active la casilla de verificación).

3. En los detalles de la Directiva que aparecen, haga clic en **eliminar Directiva**y, a continuación, haga clic en **sí** en el cuadro de diálogo de advertencia que aparece.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Usar Exchange Online PowerShell o PowerShell independiente de EOP para configurar directivas de datos adjuntos seguros

Como se ha descrito anteriormente, una directiva de datos adjuntos seguros consta de una directiva de datos adjuntos seguros y una regla de datos adjuntos seguros.

En PowerShell, es evidente la diferencia entre las directivas de datos adjuntos seguros y las reglas de datos adjuntos seguros. Para administrar las directivas de datos adjuntos seguros, puede usar los cmdlets ** \* -SafeAttachmentPolicy** y administrar reglas de datos adjuntos seguras con los cmdlets ** \* -SafeAttachmentRule** .

- En PowerShell, se crea la Directiva de datos adjuntos seguros en primer lugar y, a continuación, se crea la regla de datos adjuntos seguros que identifica la Directiva a la que se aplica la regla.
- En PowerShell, la configuración de la Directiva de datos adjuntos seguros y la regla de datos adjuntos seguros se modifica por separado.
- Cuando se quita una directiva de datos adjuntos seguros de PowerShell, la regla de datos adjuntos seguros correspondiente no se quita automáticamente y viceversa.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>Usar PowerShell para crear directivas de datos adjuntos seguros

La creación de una directiva de datos adjuntos seguros en PowerShell es un proceso de dos pasos:

1. Cree la Directiva de datos adjuntos seguros.
2. Cree la regla de datos adjuntos seguros que especifica la Directiva de datos adjuntos seguros a la que se aplica la regla.

 **Notas**:

- Puede crear una nueva regla de datos adjuntos seguros y asignar una directiva de datos adjuntos seguros existente no asociada. No se puede asociar una regla de datos adjuntos seguros con más de una directiva de datos adjuntos seguros.

- Puede configurar las siguientes opciones en nuevas directivas de datos adjuntos seguros en PowerShell que no están disponibles en el centro de seguridad & cumplimiento hasta que se crea la Directiva:
  - Cree la nueva directiva como deshabilitada (_habilitada_ `$false` en el cmdlet **New-SafeAttachmentRule** ).
  - Establezca la prioridad de la Directiva durante la creación (_prioridad_ _\<Number\>_ ) en el cmdlet **New-SafeAttachmentRule** ).

- Una nueva Directiva de datos adjuntos seguros que se crea en PowerShell no es visible en el centro de seguridad & cumplimiento hasta que se asigna la Directiva a una regla de datos adjuntos seguros.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Paso 1: usar PowerShell para crear una directiva de datos adjuntos seguros

Para crear una directiva de datos adjuntos seguros, use esta sintaxis:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

En este ejemplo se crea una directiva de datos adjuntos seguros denominada contoso All con los valores siguientes:

- Bloquear mensajes que se encuentren para contener malware mediante documentos seguros análisis (no estamos usando el parámetro _Action_ y el valor predeterminado es `Block` ).
- La redirección está habilitada, y los mensajes que contienen malware se envían a sec-ops@contoso.com para el análisis y la investigación.
- Si el análisis de datos adjuntos seguros no está disponible o encuentra errores, no entrega el mensaje (no se usa el parámetro _ActionOnError_ y el valor predeterminado es `$true` ).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>Paso 2: usar PowerShell para crear una regla de datos adjuntos seguros

Para crear una regla de datos adjuntos seguros, use esta sintaxis:

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

En este ejemplo se crea una regla de datos adjuntos seguros denominada contoso All con las siguientes condiciones:

- La regla está asociada a la Directiva de datos adjuntos seguros llamada contoso ALL.
- La regla se aplica a todos los destinatarios del dominio contoso.com.
- Como no se usa el parámetro _Priority_ , se usa la prioridad predeterminada.
- La regla está habilitada (no se usa el parámetro _Enabled_ y el valor predeterminado es `$true` ).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).

### <a name="use-powershell-to-view-safe-attachment-policies"></a>Usar PowerShell para ver las directivas de datos adjuntos seguros

Para ver las directivas de datos adjuntos seguros existentes, use la siguiente sintaxis:

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista resumida de todas las directivas de datos adjuntos seguros.

```PowerShell
Get-SafeAttachmentPolicy
```

En este ejemplo se muestra información detallada sobre la Directiva de datos adjuntos seguros denominada ejecutivos de contoso.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).

### <a name="use-powershell-to-view-safe-attachment-rules"></a>Usar PowerShell para ver las reglas de datos adjuntos seguros

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

En este ejemplo se muestra información detallada sobre la regla de datos adjuntos seguros denominada ejecutivos de contoso.

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>Usar PowerShell para modificar directivas de datos adjuntos seguros

No puede cambiar el nombre de una directiva de datos adjuntos seguros en PowerShell (el cmdlet **set-SafeAttachmentPolicy** no tiene ningún parámetro _Name_ ). Al cambiar el nombre de una directiva de datos adjuntos seguros en el centro de seguridad & cumplimiento, sólo cambia el nombre de la _regla_de datos adjuntos seguros.

De lo contrario, la misma configuración está disponible cuando se crea una directiva de datos adjuntos seguros, tal como se describe en la sección [paso 1: usar PowerShell para crear una directiva de datos adjuntos seguros](#step-1-use-powershell-to-create-a-safe-attachment-policy) , anteriormente en este artículo.

Para modificar una directiva de datos adjuntos seguros, use esta sintaxis:

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>Usar PowerShell para modificar reglas de datos adjuntos seguros

La única opción que no está disponible cuando se modifica una regla de datos adjuntos seguros en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada. Para habilitar o deshabilitar las reglas de datos adjuntos seguros existentes, consulte la siguiente sección.

De lo contrario, la misma configuración está disponible cuando se crea una regla, tal y como se describe en la sección [paso 2: usar PowerShell para crear una regla de datos adjuntos seguros](#step-2-use-powershell-to-create-a-safe-attachment-rule) , anteriormente en este artículo.

Para modificar una regla de datos adjuntos seguros, use esta sintaxis:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>Usar PowerShell para habilitar o deshabilitar reglas de datos adjuntos seguras

Habilitar o deshabilitar una regla de datos adjuntos seguros en PowerShell habilita o deshabilita toda la Directiva de datos adjuntos seguros (la regla de datos adjuntos seguros y la Directiva de datos adjuntos seguros asignada).

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

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) y [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).

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

**Nota**: para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-SafeAttachmentRule** en su lugar.

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>Usar PowerShell para quitar directivas de datos adjuntos seguros

Cuando se usa PowerShell para quitar una directiva de datos adjuntos seguros, no se quita la regla de datos adjuntos seguros correspondiente.

Para quitar una directiva de datos adjuntos seguros en PowerShell, use esta sintaxis:

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

En este ejemplo se quita la Directiva de datos adjuntos seguros denominada Marketing Department.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>Usar PowerShell para quitar reglas de datos adjuntos seguros

Cuando se usa PowerShell para quitar una regla de datos adjuntos seguros, no se quita la Directiva de datos adjuntos seguros correspondiente.

Para quitar una regla de datos adjuntos seguros en PowerShell, use esta sintaxis:

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

En este ejemplo se quita la regla de datos adjuntos seguros denominada Marketing Department.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que las directivas de datos adjuntos seguras se crearon, modificaron o quitaron correctamente, siga uno de estos pasos:

- En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **datos adjuntos seguros de ATP**de directiva de administración de amenazas. Compruebe la lista de directivas, sus valores de **Estado** y sus valores de **prioridad** . Para ver más detalles, seleccione la Directiva de la lista y vea los detalles en la lista desplegable.

- En PowerShell de Exchange Online PowerShell o Exchange Online Protection, reemplace \<Name\> por el nombre de la Directiva o regla, ejecute el siguiente comando y Compruebe la configuración:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Para comprobar que los datos adjuntos seguros están examinando los mensajes, consulte los informes de protección contra amenazas avanzada disponibles. Para obtener más información, consulte [View Reports for Office 365 ATP](view-reports-for-atp.md) and [use Explorer en el centro de seguridad & cumplimiento](threat-explorer.md).
