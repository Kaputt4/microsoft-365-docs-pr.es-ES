---
title: Configuración de directivas de datos adjuntos de Caja fuerte en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo definir directivas de datos adjuntos de Caja fuerte para proteger su organización de archivos malintencionados en el correo electrónico.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 46b69c1bea0f967fe22c031397a8887f3399c99b
ms.sourcegitcommit: 18bc521a88b7b521bccb0e69d02deac764218087
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2022
ms.locfileid: "66115573"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Configuración de directivas de datos adjuntos de Caja fuerte en Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](whats-new-in-defender-for-office-365.md). Si es un usuario doméstico que busca información sobre el examen de datos adjuntos en Outlook, consulte [Seguridad avanzada de Outlook.com](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Caja fuerte Datos adjuntos es una característica de [Microsoft Defender para Office 365](whats-new-in-defender-for-office-365.md) que usa un entorno virtual para comprobar los datos adjuntos en los mensajes de correo electrónico entrantes después de haber sido examinados por [la protección contra malware en Exchange Online Protection (EOP),](anti-malware-protection.md) pero antes de entregarlos a los destinatarios. Para obtener más información, consulte [Caja fuerte Datos adjuntos en Microsoft Defender para Office 365](safe-attachments.md).

Aunque no hay ninguna directiva de datos adjuntos de Caja fuerte predeterminada, la directiva de seguridad preestablecida **de protección integrada** proporciona Caja fuerte protección de datos adjuntos a todos los destinatarios (usuarios que no están definidos en directivas personalizadas de datos adjuntos de Caja fuerte). Para obtener más información, vea [Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md). También puede usar los procedimientos de este artículo para crear directivas de datos adjuntos de Caja fuerte que se aplican a usuarios, grupos o dominios específicos.

Puede configurar directivas de datos adjuntos de Caja fuerte en el portal de Microsoft 365 Defender o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 aptas con buzones en Exchange Online; PowerShell EOP independiente para organizaciones sin Exchange Online buzones, pero con Defender para Office 365 suscripciones de complementos).

Los elementos básicos de una directiva de datos adjuntos de Caja fuerte son:

- **La directiva de datos adjuntos seguros**: especifica las acciones para las detecciones de malware desconocidas, si enviar mensajes con datos adjuntos de malware a una dirección de correo electrónico especificada y si entregar mensajes si Caja fuerte análisis de datos adjuntos no se puede completar.
- **La regla de datos adjuntos seguros**: especifica la prioridad y los filtros de destinatario (a quién se aplica la directiva).

La diferencia entre estos dos elementos no es obvia al administrar directivas de datos adjuntos de Caja fuerte en el portal de Microsoft 365 Defender:

- Al crear una directiva de datos adjuntos de Caja fuerte, realmente está creando una regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asociada al mismo tiempo con el mismo nombre para ambos.
- Al modificar una directiva de datos adjuntos de Caja fuerte, la configuración relacionada con el nombre, la prioridad, habilitado o deshabilitado y los filtros de destinatarios modifican la regla de datos adjuntos seguros. Todas las demás configuraciones modifican la directiva de datos adjuntos seguros asociada.
- Al quitar una directiva de datos adjuntos de Caja fuerte, se quitan la regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asociada.

En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado. Para obtener más información, consulte la sección [Uso Exchange Online PowerShell o EOP independiente de PowerShell para configurar directivas de datos adjuntos de Caja fuerte](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) más adelante en este artículo.

> [!NOTE]
> En el área de configuración global de Caja fuerte Configuración de datos adjuntos, se configuran características que no dependen de las directivas de datos adjuntos de Caja fuerte. Para obtener instrucciones[, consulte Activar datos adjuntos de Caja fuerte para SharePoint, OneDrive y Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) y [Caja fuerte Documentos en Microsoft 365 E5](safe-docs.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **datos adjuntos de Caja fuerte**, use <https://security.microsoft.com/safeattachmentv2>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Necesita permisos para poder realizar los procedimientos de este artículo:
  - Para crear, modificar y eliminar directivas de datos adjuntos de Caja fuerte, debe ser miembro de los grupos de roles Administración de la **organización** o **Administrador de seguridad** en el portal de Microsoft 365 Defender **y** miembro del grupo de roles Administración de la **organización** en Exchange Online.
  - Para obtener acceso de solo lectura a Caja fuerte directivas de datos adjuntos, debe ser miembro de los grupos de roles **Lector global** o **Lector de seguridad** en el portal de Microsoft 365 Defender.

  Para obtener más información, vea [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md) y [Permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el portal de Microsoft 365 Defender _y_ permisos para otras características en Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Para ver nuestra configuración recomendada para las directivas de datos adjuntos de Caja fuerte, consulte [configuración de datos adjuntos de Caja fuerte](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

- Espere hasta 30 minutos para que se aplique una directiva nueva o actualizada.

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a>Uso del portal de Microsoft 365 Defender para crear directivas de datos adjuntos de Caja fuerte

Al crear una directiva de datos adjuntos de Caja fuerte personalizada en el portal de Microsoft 365 Defender se crea la regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asociada al mismo tiempo con el mismo nombre para ambos.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas de colaboración** \> & correo electrónico **& directivas** de **amenazas** \> de reglas \> **Caja fuerte datos adjuntos** en la sección **Directivas**. Para ir directamente a la página **datos adjuntos de Caja fuerte**, use <https://security.microsoft.com/safeattachmentv2>.

2. En la página **Datos adjuntos de Caja fuerte**, haga clic en ![el icono Crear.](../../media/m365-cc-sc-create-icon.png) **Create**.

3. Se abrirá el asistente para directivas. En la página **Nombre de la directiva** , configure los siguientes valores:
   - **Nombre**: escriba un nombre único y descriptivo para la directiva.
   - **Descripción**: escriba una descripción opcional para la directiva.

   Cuando termine, haga clic en **Siguiente**.

4. En la página **Usuarios y dominios** que aparece, identifique los destinatarios internos a los que se aplica la directiva (condiciones de destinatario):
   - **Usuarios**: los buzones de correo, los usuarios de correo o los contactos de correo especificados.
   - **Grupos**:
     - Miembros de los grupos de distribución o grupos de seguridad habilitados para correo especificados.
     - Los Grupos de Microsoft 365 especificados.
   - **Dominios**: todos los destinatarios de los [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados en la organización.

   Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados. Repita este proceso tantas veces como sea necesario. Para quitar un valor existente, haga clic en Quitar ![Icono Quitar.](../../media/m365-cc-sc-remove-selection-icon.png) junto al valor.

   Para los usuarios o grupos, puede utilizar la mayoría de los identificadores (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de la cuenta, etc.), pero el nombre para mostrar correspondiente se muestra en los resultados. Para los usuarios, introduzca un asterisco (\*) por sí mismo para ver todos los valores disponibles.

   Varios valores en la misma condición usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_). Hay diferentes condiciones que usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).

   - **Excluir estos usuarios, grupos y dominios**: para agregar excepciones para los destinatarios internos a los que se aplica la directiva (excepciones de destinatarios), seleccione esta opción y configure las excepciones. La configuración y el comportamiento son exactamente iguales a las condiciones.

   > [!IMPORTANT]
   > Varias condiciones o excepciones diferentes no son aditivas; son inclusivos. La directiva _solo_ se aplica a los destinatarios que coinciden _con todos los_ filtros de destinatarios especificados. Por ejemplo, configure una condición de filtro de destinatario en la directiva con los siguientes valores:
   >
   > - El destinatario es: romain@contoso.com
   > - El destinatario es miembro de: Ejecutivos
   >
   > La política se aplica a romain@contoso.com _solo_ si también es miembro de los grupos ejecutivos. Si no es miembro del grupo, la directiva no se aplica a él.
   >
   > Del mismo modo, si usa el mismo filtro de destinatario como excepción a la directiva, la directiva no se aplica a romain@contoso.com _solo_ si también es miembro de los grupos ejecutivos. Si no es miembro del grupo, la política se aplica a él.

   Cuando termine, haga clic en **Siguiente**.

5. En la página **Configuración**, configure los siguientes valores:

   - **Caja fuerte Respuesta de malware desconocida de datos adjuntos**: seleccione uno de los valores siguientes:
     - **Desactivado**: normalmente, no se recomienda este valor.
     - **Supervisar**
     - **Bloquear**: este es el valor predeterminado y el valor recomendado en Directivas de [seguridad preestablecidas](preset-security-policies.md) estándar y estricta.
     - **Replace**
     - **Entrega dinámica (característica de versión preliminar)**

     Estos valores se explican en [Caja fuerte configuración de directiva de datos adjuntos](safe-attachments.md#safe-attachments-policy-settings).

   - **Directiva de cuarentena**: seleccione la directiva de cuarentena que se aplica a los mensajes que están en cuarentena por Caja fuerte Datos adjuntos (**Bloquear**, **Reemplazar** o **Entrega dinámica**). Las directivas de cuarentena definen qué pueden hacer los usuarios en los mensajes en cuarentena y si los usuarios reciben notificaciones de cuarentena. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).

     Un valor en blanco significa que se usa la directiva de cuarentena predeterminada (AdminOnlyAccessPolicy para las detecciones de correo electrónico por Caja fuerte Attachments). Cuando más adelante edite la directiva de datos adjuntos de Caja fuerte o vea la configuración, se muestra el nombre predeterminado de la directiva de cuarentena.

   - **Redirigir mensajes con datos adjuntos detectados**: si selecciona **Habilitar redirección**, puede especificar una dirección de correo electrónico en el cuadro **Enviar mensajes que contengan datos adjuntos bloqueados, supervisados o reemplazados a la dirección de correo electrónico especificada** para enviar mensajes que contengan datos adjuntos de malware para su análisis e investigación.

     La recomendación para la configuración de directivas estándar y estricta es habilitar el redireccionamiento. Para obtener más información, consulte [Caja fuerte Configuración de datos adjuntos](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

   - **Aplique la respuesta de detección de datos adjuntos Caja fuerte si el examen no puede completarse (tiempo de espera o errores):** la acción especificada por **Caja fuerte Respuesta de malware desconocida de los datos adjuntos** se realiza en los mensajes incluso cuando no se puede completar el examen de datos adjuntos de Caja fuerte. Si seleccionó esta opción, seleccione siempre **Habilitar redirección** y especifique una dirección de correo electrónico para enviar mensajes que contengan datos adjuntos de malware. De lo contrario, es posible que se pierdan los mensajes.

   Cuando termine, haga clic en **Siguiente**.

6. En la página **Revisar** que aparece, revise la configuración. Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Enviar**.

7. En la página de confirmación que aparece, haga clic en **Listo**.

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a>Uso del portal de Microsoft 365 Defender para ver las directivas de datos adjuntos de Caja fuerte

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas de colaboración** \> & correo electrónico **& directivas** de **amenazas** \> de reglas \> **Caja fuerte datos adjuntos** en la sección **Directivas**. Para ir directamente a la página **datos adjuntos de Caja fuerte**, use <https://security.microsoft.com/safeattachmentv2>.

2. En la página **datos adjuntos de Caja fuerte**, se muestran las siguientes propiedades en la lista de directivas:
   - **Nombre**
   - **Estado**
   - **Prioridad**

3. Al seleccionar una directiva haciendo clic en el nombre, la configuración de la directiva se muestra en un control flotante.

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a>Uso del portal de Microsoft 365 Defender para modificar las directivas de datos adjuntos de Caja fuerte

1. IIn the Microsoft 365 Defender portal at <https://security.microsoft.com>, go **to Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Caja fuerte Attachments** in the **Policies** section. Para ir directamente a la página **datos adjuntos de Caja fuerte**, use <https://security.microsoft.com/safeattachmentv2>.

2. En la página **Caja fuerte Datos adjuntos**, haga clic en el nombre para seleccionar una directiva de la lista.

3. En el control flotante de detalles de la directiva que aparece, seleccione **Editar** en cada sección para modificar la configuración dentro de la sección. Para obtener más información sobre la configuración, consulte [la sección Uso del portal de Microsoft 365 Defender para crear directivas de datos adjuntos de Caja fuerte](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) anteriormente en este artículo.

Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la directiva, consulte las secciones siguientes.

### <a name="enable-or-disable-safe-attachments-policies"></a>Habilitar o deshabilitar directivas de datos adjuntos de Caja fuerte

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas de colaboración** \> & correo electrónico **& directivas** de **amenazas** \> de reglas \> **Caja fuerte datos adjuntos** en la sección **Directivas**. Para ir directamente a la página **datos adjuntos de Caja fuerte**, use <https://security.microsoft.com/safeattachmentv2>.

2. En la página **Caja fuerte Datos adjuntos**, haga clic en el nombre para seleccionar una directiva de la lista.

3. En la parte superior del control flotante de detalles de la directiva que aparece, verá uno de los siguientes valores:
   - **Directiva desactivada**: para activar la directiva, haga clic en ![icono Activar.](../../media/m365-cc-sc-turn-on-off-icon.png) **Activar** .
   - **Directiva activada**: para desactivar la directiva, haga clic en el ![Icono Desactivar](../../media/m365-cc-sc-turn-on-off-icon.png) **Desactivar**.

4. En el cuadro de diálogo de confirmación que aparece, haga clic **Activar** o **Desactivar**.

5. Haga clic en **Cerrar** en el control flotante de detalles de la directiva.

De nuevo en la página principal de la directiva, el valor **Estado** de la directiva estará **Activado** o **Desactivado**.

### <a name="set-the-priority-of-safe-attachments-policies"></a>Establecer la prioridad de las directivas de datos adjuntos de Caja fuerte

De forma predeterminada, Caja fuerte las directivas de datos adjuntos tienen una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen una prioridad menor que las directivas anteriores). Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor). Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.

Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).

Caja fuerte las directivas de datos adjuntos se muestran en el orden en que se procesan (la primera directiva tiene el valor **de prioridad** 0).

**Nota**: En el portal de Microsoft 365 Defender, solo puede cambiar la prioridad de la directiva de datos adjuntos de Caja fuerte después de crearla. En PowerShell, puede invalidar la prioridad predeterminada al crear la regla de datos adjuntos seguros (que puede afectar a la prioridad de las reglas existentes).

Para cambiar la prioridad de una directiva, haga clic en **Aumentar prioridad** o **Reducir prioridad** en las propiedades de la directiva (no puede modificar directamente el número de **Prioridad** en el portal de Microsoft 365 Defender). Cambiar la prioridad de una directiva sólo tiene sentido si tiene varias directivas.

1. En el portal de Microsoft 365 Defender, vaya a **Directivas de colaboración** \> & correo electrónico **& Directivas** de **amenazas** \> de reglas \> **Caja fuerte datos adjuntos** en la sección **Directivas**.

2. En la página **Caja fuerte Datos adjuntos**, haga clic en el nombre para seleccionar una directiva de la lista.

3. En la parte superior del control flotante de detalles de la directiva que aparece, verá **Aumentar prioridad** o **Reducir prioridad** según el valor de prioridad actual y el número de directivas:
   - La directiva con el valor **De prioridad** **0** solo tiene la opción **Reducir prioridad** disponible.
   - La directiva con el valor **de prioridad** más bajo (por ejemplo, **3**) solo tiene la opción **Aumentar prioridad** disponible.
   - Si tiene tres o más directivas, las directivas entre los valores de prioridad más altos y más bajos tienen disponibles las opciones **Aumentar prioridad** y **Reducir prioridad** .

   Haga clic en el ![Icono Aumentar la prioridad.](../../media/m365-cc-sc-increase-icon.png) **Aumentar la prioridad** o en el ![Icono Disminuir la prioridad](../../media/m365-cc-sc-decrease-icon.png) **Reducir la prioridad** para cambiar el valor de **Prioridad**.

4. Cuando haya terminado, haga clic en **Cerrar** en el control flotante de detalles de la directiva.

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a>Uso del portal de Microsoft 365 Defender para quitar directivas de datos adjuntos de Caja fuerte

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas de colaboración** \> & correo electrónico **& directivas** de **amenazas** \> de reglas \> **Caja fuerte datos adjuntos** en la sección **Directivas**. Para ir directamente a la página **datos adjuntos de Caja fuerte**, use <https://security.microsoft.com/safeattachmentv2>.

2. En la página **datos adjuntos de Caja fuerte**, seleccione una directiva personalizada en la lista haciendo clic en el nombre de la directiva.

3. En la parte superior del control flotante de detalles de la directiva que aparece, haga clic en ![icono Más acciones.](../../media/m365-cc-sc-more-actions-icon.png) **Más acciones** \> ![Icono Eliminar directiva](../../media/m365-cc-sc-delete-icon.png)**Eliminar directiva**.

4. En el cuadro de diálogo de confirmación que aparece, haga clic en **Sí**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Use Exchange Online PowerShell o PowerShell EOP independiente para configurar directivas de datos adjuntos de Caja fuerte

Como se describió anteriormente, una directiva de datos adjuntos de Caja fuerte consta de una directiva de datos adjuntos seguros y una regla de datos adjuntos seguros.

En PowerShell, la diferencia entre las directivas de datos adjuntos seguros y las reglas de datos adjuntos seguros es evidente. Las directivas de datos adjuntos seguros se administran mediante los **\*cmdlets -SafeAttachmentPolicy** y se administran las reglas de datos adjuntos seguros mediante los **\*cmdlets -SafeAttachmentRule** .

- En PowerShell, primero se crea la directiva de datos adjuntos seguros y, a continuación, se crea la regla de datos adjuntos seguros que identifica la directiva a la que se aplica la regla.
- En PowerShell, modifica la configuración de la directiva de datos adjuntos seguros y la regla de datos adjuntos seguros por separado.
- Al quitar una directiva de datos adjuntos seguros de PowerShell, la regla de datos adjuntos seguros correspondiente no se quita automáticamente y viceversa.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>Uso de PowerShell para crear directivas de datos adjuntos de Caja fuerte

La creación de una directiva de datos adjuntos de Caja fuerte en PowerShell es un proceso de dos pasos:

1. Cree la directiva de datos adjuntos seguros.
2. Cree la regla de datos adjuntos seguros que especifica la directiva de datos adjuntos seguros a la que se aplica la regla.

 **Notas**:

- Puede crear una nueva regla de datos adjuntos seguros y asignarle una directiva de datos adjuntos seguros no asociada existente. Una regla de datos adjuntos seguros no se puede asociar a más de una directiva de datos adjuntos seguros.

- Puede configurar las siguientes opciones en las nuevas directivas de datos adjuntos seguros en PowerShell que no están disponibles en el portal de Microsoft 365 Defender hasta después de crear la directiva:
  - Cree la nueva directiva como deshabilitada (_habilitada_ `$false` en el cmdlet **New-SafeAttachmentRule** ).
  - Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_) en el cmdlet **New-SafeAttachmentRule** ).

- Una nueva directiva de datos adjuntos seguros que cree en PowerShell no será visible en el portal de Microsoft 365 Defender hasta que asigne la directiva a una regla de datos adjuntos seguros.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Paso 1: Uso de PowerShell para crear una directiva de datos adjuntos seguros

Para crear una directiva de datos adjuntos seguros, use esta sintaxis:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" -Enable $true [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>] [-QuarantineTag <QuarantinePolicyName>]
```

En este ejemplo se crea una directiva de datos adjuntos seguros denominada Contoso All con los valores siguientes:

- Bloquee los mensajes que se encuentran para contener malware Caja fuerte examen de documentos (no se usa el parámetro _Action_ y el valor predeterminado es `Block`).
- Se usa la [directiva de cuarentena](quarantine-policies.md) predeterminada (AdminOnlyAccessPolicy), porque no se usa el parámetro _QuarantineTag_ .
- El redireccionamiento está habilitado y los mensajes que contienen malware se envían a sec-ops@contoso.com para su análisis e investigación.
- Si Caja fuerte análisis de datos adjuntos no está disponible o encuentra errores, no entregue el mensaje (no se usa el parámetro _ActionOnError_ y el valor predeterminado es `$true`).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Enable $true -Redirect $true -RedirectAddress sec-ops@contoso.com
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).

> [!NOTE]
> Para obtener instrucciones detalladas para especificar la [directiva de cuarentena](quarantine-policies.md) que se usará en una directiva de datos adjuntos seguros, consulte [Uso de PowerShell para especificar la directiva de cuarentena en Caja fuerte directivas de datos adjuntos](quarantine-policies.md#safe-attachments-policies-in-powershell).

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>Paso 2: Uso de PowerShell para crear una regla de datos adjuntos seguros

Para crear una regla de datos adjuntos seguros, use esta sintaxis:

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

En este ejemplo se crea una regla de datos adjuntos seguros denominada Contoso All con las condiciones siguientes:

- La regla está asociada a la directiva de datos adjuntos seguros denominada Contoso All.
- La regla se aplica a todos los destinatarios del dominio contoso.com.
- Dado que no se usa el parámetro _Priority_ , se usa la prioridad predeterminada.
- La regla está habilitada (no se usa el parámetro _Enabled_ y el valor predeterminado es `$true`).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).

### <a name="use-powershell-to-view-safe-attachment-policies"></a>Uso de PowerShell para ver directivas de datos adjuntos seguros

Para ver las directivas de datos adjuntos seguros existentes, use la sintaxis siguiente:

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista de resumen de todas las directivas de datos adjuntos seguros.

```PowerShell
Get-SafeAttachmentPolicy
```

En este ejemplo se devuelve información detallada de la directiva de datos adjuntos seguros denominada Contoso Executives.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).

### <a name="use-powershell-to-view-safe-attachment-rules"></a>Uso de PowerShell para ver reglas de datos adjuntos seguros

Para ver las reglas de datos adjuntos seguros existentes, use la sintaxis siguiente:

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

En este ejemplo se devuelve una lista de resumen de todas las reglas de datos adjuntos seguros.

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

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>Uso de PowerShell para modificar directivas de datos adjuntos seguros

No se puede cambiar el nombre de una directiva de datos adjuntos seguros en PowerShell (el cmdlet **Set-SafeAttachmentPolicy** no tiene ningún parámetro _Name_ ). Al cambiar el nombre de una directiva de datos adjuntos de Caja fuerte en el portal de Microsoft 365 Defender, solo cambia el nombre de la _regla_ de datos adjuntos seguros.

De lo contrario, la misma configuración está disponible al crear una directiva de datos adjuntos seguros, como se describe en la sección [Paso 1: Uso de PowerShell para crear una directiva de datos adjuntos seguros](#step-1-use-powershell-to-create-a-safe-attachment-policy) anteriormente en este artículo.

Para modificar una directiva de datos adjuntos seguros, use esta sintaxis:

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).

> [!NOTE]
> Para obtener instrucciones detalladas para especificar la [directiva de cuarentena](quarantine-policies.md) que se usará en una directiva de datos adjuntos seguros, consulte [Uso de PowerShell para especificar la directiva de cuarentena en Caja fuerte directivas de datos adjuntos](quarantine-policies.md#safe-attachments-policies-in-powershell).

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>Uso de PowerShell para modificar reglas de datos adjuntos seguros

La única configuración que no está disponible al modificar una regla de datos adjuntos seguros en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada. Para habilitar o deshabilitar las reglas de datos adjuntos seguros existentes, consulte la sección siguiente.

De lo contrario, la misma configuración está disponible al crear una regla como se describe en la sección [Paso 2: Uso de PowerShell para crear una regla de datos adjuntos segura](#step-2-use-powershell-to-create-a-safe-attachment-rule) anteriormente en este artículo.

Para modificar una regla de datos adjuntos seguros, use esta sintaxis:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>Uso de PowerShell para habilitar o deshabilitar reglas de datos adjuntos seguros

La habilitación o deshabilitación de una regla de datos adjuntos seguros en PowerShell habilita o deshabilita toda la directiva de datos adjuntos de Caja fuerte (la regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asignada).

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

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>Uso de PowerShell para establecer la prioridad de las reglas de datos adjuntos seguros

El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.

Para establecer la prioridad de una regla de datos adjuntos seguros en PowerShell, use la sintaxis siguiente:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

En el ejemplo siguiente, la prioridad de la regla denominada "Marketing Department" se establece en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**Nota**: Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-SafeAttachmentRule** en su lugar.

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>Uso de PowerShell para quitar directivas de datos adjuntos seguros

Cuando se usa PowerShell para quitar una directiva de datos adjuntos seguros, no se quita la regla de datos adjuntos seguros correspondiente.

Para quitar una directiva de datos adjuntos seguros en PowerShell, use esta sintaxis:

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

En este ejemplo se quita la directiva de datos adjuntos seguros denominada Departamento de marketing.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>Uso de PowerShell para quitar reglas de datos adjuntos seguros

Cuando se usa PowerShell para quitar una regla de datos adjuntos seguros, no se quita la directiva de datos adjuntos seguros correspondiente.

Para quitar una regla de datos adjuntos seguros en PowerShell, use esta sintaxis:

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

En este ejemplo se quita la regla de datos adjuntos seguros denominada Departamento de marketing.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).

## <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

Para comprobar que ha creado, modificado o quitado correctamente Caja fuerte directivas de datos adjuntos, siga estos pasos:

- En la página **datos adjuntos de Caja fuerte** del portal de Microsoft 365 Defender en <https://security.microsoft.com/safeattachmentv2>, compruebe la lista de directivas, sus valores **de estado** y sus valores **de prioridad**. Para ver más detalles, seleccione la directiva de la lista haciendo clic en el nombre y vea los detalles del control flotante.

- En Exchange Online PowerShell o Exchange Online Protection PowerShell, reemplace por \<Name\> el nombre de la directiva o regla, ejecute el siguiente comando y compruebe la configuración:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Para comprobar que Caja fuerte Attachments está examinando los mensajes, compruebe los informes de Defender para Office 365 disponibles. Para obtener más información, vea [Ver informes para Defender para Office 365](view-reports-for-mdo.md) y [Usar explorador en el portal de Microsoft 365 Defender](threat-explorer.md).
