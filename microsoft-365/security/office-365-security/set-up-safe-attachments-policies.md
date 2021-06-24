---
title: Configurar directivas Caja fuerte datos adjuntos en Microsoft Defender para Office 365
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
description: Obtenga información sobre cómo definir directivas Caja fuerte datos adjuntos para proteger su organización de archivos malintencionados en el correo electrónico.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e516a16ff28c762e154fd908312df65ea48699bc
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108228"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Configurar directivas Caja fuerte datos adjuntos en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](whats-new-in-defender-for-office-365.md). Si es un usuario principal que busca información sobre el examen de datos adjuntos en Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Caja fuerte Los datos adjuntos son una característica de [Microsoft Defender](whats-new-in-defender-for-office-365.md) para Office 365 que usa un entorno virtual para comprobar los datos adjuntos de los mensajes de correo electrónico entrantes después de haber sido examinados por la protección antimalware en [Exchange Online Protection (EOP),](anti-malware-protection.md)pero antes de la entrega a los destinatarios. Para obtener más información, [vea Caja fuerte datos adjuntos de Microsoft Defender para Office 365](safe-attachments.md).

No hay ninguna directiva de datos adjuntos integrada o predeterminada Caja fuerte datos adjuntos. Para obtener Caja fuerte análisis de datos adjuntos de mensajes de correo electrónico, debe crear una o más directivas de datos adjuntos Caja fuerte como se describe en este artículo.

Puede configurar directivas de datos adjuntos de Caja fuerte en el portal de Microsoft 365 Defender o en PowerShell (PowerShell de Exchange Online para organizaciones de Microsoft 365 elegibles con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de Exchange Online, pero con Defender para suscripciones de complemento de Office 365).

Los elementos básicos de una directiva Caja fuerte datos adjuntos son:

- La **directiva** de datos adjuntos seguros: especifica las acciones para detecciones de malware desconocidas, si se envían mensajes con datos adjuntos de malware a una dirección de correo electrónico especificada y si se entregan mensajes si no se puede completar el examen de datos adjuntos Caja fuerte.
- **La regla de datos adjuntos seguros:** especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva).

La diferencia entre estos dos elementos no es obvia al administrar las directivas Caja fuerte datos adjuntos en el portal Microsoft 365 Defender datos adjuntos:

- Al crear una directiva Caja fuerte datos adjuntos, en realidad está creando una regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asociada al mismo tiempo con el mismo nombre para ambos.
- Al modificar una directiva Caja fuerte datos adjuntos, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada y los filtros de destinatarios modifican la regla de datos adjuntos seguros. Todas las demás opciones modifican la directiva de datos adjuntos seguros asociada.
- Al quitar una directiva Caja fuerte datos adjuntos, se quitan la regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asociada.

En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado. Para obtener más información, vea la sección [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Caja fuerte Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) más adelante en este artículo.

> [!NOTE]
> En el área de configuración global de Caja fuerte datos adjuntos, se configuran características que no dependen de Caja fuerte de datos adjuntos. Para obtener instrucciones, vea [Turn on Caja fuerte Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and Caja fuerte Documents in [Microsoft 365 E5](safe-docs.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la **página Caja fuerte datos adjuntos,** use <https://security.microsoft.com/safeattachmentv2> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Necesita permisos para poder realizar los procedimientos descritos en este artículo:
  - Para crear, modificar y eliminar directivas de datos adjuntos de  Caja fuerte,  debe ser miembro de los grupos de roles  Administración de la organización o Administrador de seguridad en el **portal** de Microsoft 365 Defender y miembro del grupo de roles Administración de la organización en Exchange Online.
  - Para obtener acceso de solo lectura a Caja fuerte de datos adjuntos,  debe ser miembro de los grupos de roles Lector **global** o Lector de seguridad en el portal de Microsoft 365 Defender datos.

  Para obtener más información, vea [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - Agregar usuarios al rol Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el _portal_ de Microsoft 365 Defender y permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para obtener la configuración recomendada para las Caja fuerte de datos adjuntos, [vea Caja fuerte de datos adjuntos](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

- Permitir hasta 30 minutos para que se aplique una directiva nueva o actualizada.

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a>Usar el portal Microsoft 365 Defender para crear directivas Caja fuerte datos adjuntos

La creación de una directiva Caja fuerte datos adjuntos personalizada en el portal de Microsoft 365 Defender crea la regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asociada al mismo tiempo con el mismo nombre para ambos.

1. En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  Caja fuerte \>  \> **datos adjuntos**.

2. En la **página Caja fuerte datos adjuntos,** haga clic en Crear ![ icono ](../../media/m365-cc-sc-create-icon.png) **Crear**.

3. Se abrirá el asistente para directivas. En la **página Nombre de la directiva,** configure las siguientes opciones:
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

   - **Excluir estos usuarios, grupos y dominios**: para agregar excepciones a los destinatarios internos a los que se aplica la directiva (excepciones de destinatarios), seleccione esta opción y configure las excepciones. La configuración y el comportamiento se muestran exactamente igual que las condiciones.

   Cuando termine, haga clic en **Siguiente**.

5. En la **Configuración,** configure las siguientes opciones:

   - **Caja fuerte datos adjuntos respuesta de malware desconocido:** seleccione uno de los siguientes valores:
     - **Off**: Normalmente, no recomendamos este valor.
     - **Supervisar**
     - **Block:** este es el valor predeterminado y el valor recomendado en Directivas de seguridad predeterminadas estándar y [estrictas.](preset-security-policies.md)
     - **Replace**
     - **Entrega dinámica (característica de vista previa)**

     Estos valores se explican en Caja fuerte [de directiva de datos adjuntos](safe-attachments.md#safe-attachments-policy-settings).

   - Redirigir mensajes con datos adjuntos detectados: si selecciona Habilitar redireccionamiento, puede especificar una dirección de correo electrónico en el cuadro Enviar mensajes que contengan datos adjuntos **bloqueados,** supervisados o reemplazados en el cuadro dirección de correo electrónico especificada para enviar mensajes que contengan datos adjuntos de malware para su análisis e investigación.

     La recomendación para la configuración de directivas estándar y estricta es habilitar la redirección. Para obtener más información, [vea Caja fuerte configuración de datos adjuntos](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

   - Aplicar la respuesta de detección de datos adjuntos de Caja fuerte si el examen no se puede completar (tiempo de espera o **errores):** la acción especificada por **Caja fuerte Attachments unknown malware response** se toma en mensajes incluso cuando no se puede completar el examen de datos adjuntos Caja fuerte. Si seleccionó esta opción, seleccione siempre Habilitar redireccionamiento y especifique una dirección de correo electrónico para enviar mensajes que contengan datos adjuntos de malware.  De lo contrario, los mensajes podrían perderse.

   Cuando termine, haga clic en **Siguiente**.

6. En la página **Revisar** que aparece, revise la configuración. Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Enviar**.

7. En la página de confirmación que aparece, haga clic en **Listo**.

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a>Usar el portal Microsoft 365 Defender para ver las directivas Caja fuerte datos adjuntos

1. En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  Caja fuerte \>  \> **datos adjuntos**.

2. En la **Caja fuerte datos adjuntos,** las siguientes propiedades se muestran en la lista de directivas:
   - **Nombre**
   - **Estado**
   - **Prioridad**

3. Al seleccionar una directiva haciendo clic en el nombre, la configuración de la directiva se muestra en un menú desplegable.

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a>Usar el portal Microsoft 365 Defender para modificar las directivas Caja fuerte datos adjuntos

1. En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  Caja fuerte \>  \> **datos adjuntos**.

2. En la **Caja fuerte datos adjuntos,** seleccione una directiva de la lista haciendo clic en el nombre.

3. En el control flotante de detalles de la directiva que aparece, seleccione **Editar** en cada sección para modificar la configuración dentro de la sección. Para obtener más información acerca de la configuración, vea la sección Use [the Microsoft 365 Defender portal to create Caja fuerte Attachments policies](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) anterior en este artículo.  

Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la directiva, consulte las secciones siguientes.

### <a name="enable-or-disable-safe-attachments-policies"></a>Habilitar o deshabilitar directivas Caja fuerte datos adjuntos

1. En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  Caja fuerte \>  \> **datos adjuntos**.

2. En la **Caja fuerte datos adjuntos,** seleccione una directiva de la lista haciendo clic en el nombre.

3. En la parte superior del control flotante de detalles de la directiva que aparece, verá uno de los siguientes valores:
   - **Directiva desactivada**: para activar la directiva, haga clic en el ![Icono Activar](../../media/m365-cc-sc-turn-on-off-icon.png) **Activar**.
   - **Directiva activada**: Para desactivar la directiva, haga clic en el ![Icono desactivar](../../media/m365-cc-sc-turn-on-off-icon.png) y **Desactivar**.

4. En el cuadro de diálogo de confirmación que aparece, haga clic **Activar** o **Desactivar**.

5. Haga clic en **Cerrar** en el control flotante de detalles de la directiva.

De nuevo en la página principal de la directiva, el valor **Estado** de la directiva estará **Activado** o **Desactivado**.

### <a name="set-the-priority-of-safe-attachments-policies"></a>Establecer la prioridad de las directivas Caja fuerte datos adjuntos

De forma predeterminada, Caja fuerte de datos adjuntos tienen una prioridad que se basa en el orden en que se crearon (las directivas más recientes son de menor prioridad que las directivas anteriores). Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor). Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).

Caja fuerte Las directivas de datos adjuntos se muestran en el orden en que se procesan (la primera directiva tiene el **valor de** prioridad 0).

**Nota:** En el portal Microsoft 365 Defender, solo puede cambiar la prioridad de la directiva de datos adjuntos Caja fuerte después de crearla. En PowerShell, puede invalidar la prioridad predeterminada al crear la regla de datos adjuntos seguros (lo que puede afectar a la prioridad de las reglas existentes).

Para cambiar la prioridad de una directiva, haga clic en **Aumentar la prioridad** o en **Reducir la prioridad** en las propiedades de la directiva (no se puede modificar directamente el número de **Prioridad** en el portal de Microsoft 365 Defender). Cambiar la prioridad de una directiva solo tiene sentido si tiene varias directivas.

1. En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  Caja fuerte \>  \> **datos adjuntos**.

2. En la **Caja fuerte datos adjuntos,** seleccione una directiva de la lista haciendo clic en el nombre.

3. En la parte superior del menú desplegable de  detalles de  la directiva que aparece, verá Aumentar prioridad o Disminuir prioridad en función del valor de prioridad actual y el número de directivas:
   - La directiva con el **valor de prioridad** **0** solo tiene disponible la **opción Disminuir** prioridad.
   - La directiva con el valor **de prioridad** más bajo (por ejemplo, **3**) solo tiene disponible **la opción Aumentar** prioridad.
   - Si tiene tres o más directivas, las directivas entre los valores de prioridad más alta y más baja tienen disponibles las opciones **Aumentar** prioridad y **Disminuir** prioridad.

   Haga clic en el ![Icono Aumentar la prioridad](../../media/m365-cc-sc-increase-icon.png) **Aumentar la prioridad** o en el ![Icono Disminuir la prioridad](../../media/m365-cc-sc-decrease-icon.png) **Reducir la prioridad** para cambiar el valor de **Prioridad**.

4. Cuando haya terminado, haga clic en **Cerrar** en el control flotante de detalles de la directiva.

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a>Usar el portal Microsoft 365 Defender para quitar directivas Caja fuerte datos adjuntos

1. En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  Caja fuerte \>  \> **datos adjuntos**.

2. En la **Caja fuerte datos adjuntos,** seleccione una directiva personalizada de la lista haciendo clic en el nombre de la directiva.

3. En la parte superior del control flotante de detalles de la directiva que aparece, haga clic en el ![Icono Más acciones](../../media/m365-cc-sc-more-actions-icon.png) **Más acciones** \> ![Icono Eliminar directiva](../../media/m365-cc-sc-delete-icon.png) **Eliminar directiva**.

4. En el cuadro de diálogo de confirmación que aparece, haga clic en **Sí**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Usar Exchange Online PowerShell o PowerShell de EOP independiente para configurar directivas de datos adjuntos Caja fuerte independientes

Como se describió anteriormente, una directiva Caja fuerte datos adjuntos consiste en una directiva de datos adjuntos seguros y una regla de datos adjuntos seguros.

En PowerShell, la diferencia entre las directivas de datos adjuntos seguros y las reglas de datos adjuntos seguros es aparente. Las directivas de datos adjuntos seguros se administran mediante los cmdlets **\* -SafeAttachmentPolicy** y se administran reglas de datos adjuntos seguros mediante los cmdlets **\* -SafeAttachmentRule.**

- En PowerShell, primero se crea la directiva de datos adjuntos seguros y, a continuación, se crea la regla de datos adjuntos seguros que identifica la directiva a la que se aplica la regla.
- En PowerShell, modifica la configuración de la directiva de datos adjuntos seguros y la regla de datos adjuntos seguros por separado.
- Al quitar una directiva de datos adjuntos seguros de PowerShell, la regla de datos adjuntos seguros correspondiente no se quita automáticamente y viceversa.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>Usar PowerShell para crear directivas Caja fuerte datos adjuntos

Crear una directiva Caja fuerte datos adjuntos en PowerShell es un proceso de dos pasos:

1. Cree la directiva de datos adjuntos seguros.
2. Cree la regla de datos adjuntos seguros que especifique la directiva de datos adjuntos seguros a la que se aplica la regla.

 **Notas**:

- Puede crear una nueva regla de datos adjuntos seguros y asignarle una directiva de datos adjuntos seguros existente y no asociada. Una regla de datos adjuntos seguros no se puede asociar a más de una directiva de datos adjuntos seguros.

- Puede configurar las siguientes opciones en las nuevas directivas de datos adjuntos seguros en PowerShell que no están disponibles en el portal de Microsoft 365 Defender hasta después de crear la directiva:
  - Cree la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-SafeAttachmentRule).**
  - Establezca la prioridad de la directiva durante la creación (_Prioridad_ ) en _\<Number\>_ el cmdlet **New-SafeAttachmentRule).**

- Una nueva directiva de datos adjuntos seguros que cree en PowerShell no será visible en el portal de Microsoft 365 Defender hasta que asigne la directiva a una regla de datos adjuntos seguros.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Paso 1: Usar PowerShell para crear una directiva de datos adjuntos seguros

Para crear una directiva de datos adjuntos seguros, use esta sintaxis:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

En este ejemplo se crea una directiva de datos adjuntos segura denominada Contoso All con los siguientes valores:

- Bloquear los mensajes que se encuentran que contienen malware mediante el examen de documentos Caja fuerte (no estamos usando el parámetro _Action_ y el valor predeterminado es `Block` ).
- El redireccionamiento está habilitado y los mensajes que se encuentran que contienen malware se envían a sec-ops@contoso.com para su análisis e investigación.
- Si Caja fuerte análisis de datos adjuntos no está disponible o encuentra errores, no entregue el mensaje (no estamos usando el parámetro _ActionOnError_ y el valor predeterminado es `$true` ).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>Paso 2: Usar PowerShell para crear una regla de datos adjuntos seguros

Para crear una regla de datos adjuntos seguros, use esta sintaxis:

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

En este ejemplo se crea una regla de datos adjuntos segura denominada Contoso All con las condiciones siguientes:

- La regla está asociada con la directiva de datos adjuntos seguros denominada Contoso All.
- La regla se aplica a todos los destinatarios del contoso.com dominio.
- Dado que no estamos usando el parámetro _Priority,_ se usa la prioridad predeterminada.
- La regla está habilitada (no estamos usando el parámetro _Enabled_ y el valor predeterminado es `$true` ).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).

### <a name="use-powershell-to-view-safe-attachment-policies"></a>Usar PowerShell para ver directivas de datos adjuntos seguros

Para ver las directivas de datos adjuntos seguros existentes, use la siguiente sintaxis:

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista resumida de todas las directivas de datos adjuntos seguros.

```PowerShell
Get-SafeAttachmentPolicy
```

En este ejemplo se devuelve información detallada sobre la directiva de datos adjuntos seguros denominada Ejecutivos de Contoso.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).

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

En este ejemplo se devuelve información detallada sobre la regla de datos adjuntos seguros denominada Ejecutivos de Contoso.

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>Usar PowerShell para modificar directivas de datos adjuntos seguros

No puede cambiar el nombre de una directiva de datos adjuntos seguros en PowerShell (el cmdlet **Set-SafeAttachmentPolicy** no tiene ningún _parámetro Name)._ Al cambiar el nombre de una directiva Caja fuerte datos adjuntos en el portal de Microsoft 365 Defender, solo se cambia el nombre de la regla de datos _adjuntos seguros._

De lo contrario, la misma configuración está disponible al crear una directiva de datos adjuntos seguros, tal como se describe en step [1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.

Para modificar una directiva de datos adjuntos seguros, use esta sintaxis:

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>Usar PowerShell para modificar reglas de datos adjuntos seguros

La única configuración que no está disponible al modificar una regla de datos adjuntos seguros en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada. Para habilitar o deshabilitar las reglas de datos adjuntos seguros existentes, consulte la siguiente sección.

De lo contrario, la misma configuración está disponible al crear una regla tal como se describe en el paso [2: Usar PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) para crear una regla de datos adjuntos segura anteriormente en este artículo.

Para modificar una regla de datos adjuntos seguros, use esta sintaxis:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>Usar PowerShell para habilitar o deshabilitar reglas de datos adjuntos seguros

Habilitar o deshabilitar una regla de datos adjuntos seguros en PowerShell habilita o deshabilita toda la directiva de datos adjuntos de Caja fuerte (la regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asignada).

Para habilitar o deshabilitar una regla de datos adjuntos seguros en PowerShell, use esta sintaxis:

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

En este ejemplo se deshabilita la regla de datos adjuntos seguros denominada Departamento de marketing.

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

Este ejemplo habilita la misma regla.

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) y [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>Usar PowerShell para establecer la prioridad de las reglas de datos adjuntos seguros

El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.

Para establecer la prioridad de una regla de datos adjuntos seguros en PowerShell, use la siguiente sintaxis:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

En el ejemplo siguiente, la prioridad de la regla denominada "Marketing Department" se establece en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**Nota:** Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-SafeAttachmentRule** en su lugar.

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>Usar PowerShell para quitar directivas de datos adjuntos seguros

Cuando usa PowerShell para quitar una directiva de datos adjuntos seguros, no se quita la regla de datos adjuntos seguros correspondiente.

Para quitar una directiva de datos adjuntos seguros en PowerShell, use esta sintaxis:

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

En este ejemplo se quita la directiva de datos adjuntos seguros denominada Departamento de marketing.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>Usar PowerShell para quitar reglas de datos adjuntos seguros

Al usar PowerShell para quitar una regla de datos adjuntos seguros, no se quita la directiva de datos adjuntos seguros correspondiente.

Para quitar una regla de datos adjuntos seguros en PowerShell, use esta sintaxis:

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

En este ejemplo se quita la regla de datos adjuntos seguros denominada Departamento de marketing.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha creado, modificado o quitado correctamente las directivas de datos adjuntos de Caja fuerte, siga estos pasos:

- En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  Caja fuerte \>  \> **datos adjuntos**. Compruebe la lista de directivas, sus **valores de** estado y sus **valores de** prioridad. Para ver más detalles, seleccione la directiva de la lista haciendo clic en el nombre y vea los detalles en el menú desplegable.

- En Exchange Online PowerShell o Exchange Online Protection PowerShell, reemplace por el nombre de la directiva o regla, ejecute el siguiente comando y compruebe \<Name\> la configuración:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Para comprobar que Caja fuerte datos adjuntos está analizando mensajes, compruebe el Defender disponible para Office 365 informes. Para obtener más información, vea [View reports for Defender for Office 365](view-reports-for-mdo.md) and Use Explorer in the Microsoft 365 Defender [portal](threat-explorer.md).
