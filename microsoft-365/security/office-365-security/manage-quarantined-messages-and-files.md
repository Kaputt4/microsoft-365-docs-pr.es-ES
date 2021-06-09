---
title: Administrar mensajes en cuarentena y archivos como administrador
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a ver y administrar mensajes en cuarentena para todos los usuarios de Exchange Online Protection (EOP). Los administradores de organizaciones con Microsoft Defender para Office 365 también pueden administrar archivos en cuarentena en SharePoint Online, OneDrive para la Empresa y Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7b484cc3a8462115b5151b34ba93ba0c041e16b4
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822303"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>Administración de mensajes en cuarentena y archivos como administrador en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online, la cuarentena retiene los mensajes que pueden ser peligrosos o no deseados. Para obtener más información, vea [Quarantined email messages in EOP](quarantine-email-messages.md).

Los administradores pueden ver, liberar y eliminar todos los tipos de mensajes en cuarentena para todos los usuarios. Solo los administradores pueden administrar mensajes que se han puesto en cuarentena como malware, phishing de elevada confianza o como resultado de reglas de flujo de correo (también conocidas como reglas de transporte). Los administradores también pueden notificar falsos positivos a Microsoft.

Los administradores de organizaciones con Microsoft Defender para Office 365 también pueden ver, descargar y eliminar archivos en cuarentena en SharePoint Online, OneDrive para la Empresa y Microsoft Teams.

Puede ver y administrar mensajes en cuarentena en el centro de seguridad de Microsoft 365 o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Para abrir el centro de seguridad, vaya a <https://security.microsoft.com> . Para abrir directamente la página de Cuarentena, vaya a <https://security.microsoft.com/quarantine>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para realizar acciones en los mensajes en cuarentena para todos los usuarios, debe ser miembro de los grupos de roles Administración de la **organización,** Administrador de seguridad **o** Administrador <sup>\*</sup> de cuarentena.
  - Para obtener acceso de solo lectura a mensajes en cuarentena para todos los usuarios, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.

  Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Notas**:

  - Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.
  - <sup>\*</sup>Los miembros **del** grupo de roles Administrador de cuarentena también deben ser miembros del grupo de roles **Administración** de higiene en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) para realizar procedimientos de cuarentena en Exchange Online PowerShell.

- Los mensajes en cuarentena se conservan durante un período de tiempo predeterminado antes de que se eliminen automáticamente:
  - 30 días para los mensajes en cuarentena por directivas contra correo no deseado (correo no deseado, suplantación de identidad y correo electrónico masivo). Este es el valor predeterminado y máximo. Para configurar (inferior) este valor, vea [Configure anti-spam policies](configure-your-spam-filter-policies.md).
  - 15 días para los mensajes que contienen malware.
  - 15 días para los archivos en cuarentena por Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams en Defender para Office 365.

  Cuando un mensaje expira de la cuarentena, no se puede recuperar.

## <a name="use-the-security-center-to-manage-quarantined-email-messages"></a>Usar el centro de seguridad para administrar mensajes de correo electrónico en cuarentena

### <a name="view-quarantined-email"></a>Ver correo electrónico en cuarentena

1. En el centro de seguridad, vaya a **Correo & de colaboración** \> **Revisar** \> **cuarentena**.

2. En la **página Cuarentena,** compruebe que **View quarantined** está establecido en el valor **predeterminado** email .

3. Para ordenar los resultados, haga clic en un encabezado de columna disponible. Haga clic en **Modificar columnas** para mostrar un máximo de siete columnas. Los valores predeterminados están marcados con un asterisco (<sup>\*</sup>):

   - **Recibido**<sup>\*</sup>
   - **Remitente**<sup>\*</sup>
   - **Asunto**<sup>\*</sup>
   - **Motivo de la cuarentena**<sup>\*</sup>
   - **¿Liberado?**<sup>\*</sup>
   - **Tipo de directiva**<sup>\*</sup>
   - **Expira**<sup>\*</sup>
   - **Destinatario**
   - **Id. de mensaje**
   - **Nombre de la directiva**
   - **Tamaño**
   - **Dirección**

   Cuando haya terminado, haga clic en **Guardar** o en **Establecer como predeterminado**.

4. Para filtrar los resultados, haga clic en **Filtrar**. Los filtros disponibles son:
   - **Hora de expiración**: Filtrar los mensajes según cuando expiran de la cuarentena:
     - **Hoy**
     - **Próximos 2 días**
     - **Próximos 7 días**
     - **Personalizado**: Introduzca **Fecha de inicio** y **Fecha de finalización**.
   - **Hora de recepción**: Introduzca **Fecha de inicio** y **Fecha de finalización**.
   - **Motivo de la cuarentena**:
     - **Directiva:** el mensaje coincide con las condiciones de una regla de flujo de correo (también conocida como regla de transporte).
     - **Masivo**
     - **Phish:** el veredicto de filtro de correo no deseado era **correo** electrónico de suplantación de identidad o protección contra suplantación de identidad en cuarentena el mensaje [(](set-up-anti-phishing-policies.md#spoof-settings) configuración de suplantación o protección [de suplantación](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).
     - **Malware**
     - **Correo no deseado**
     - **Phish de elevada confianza**
   - **Tipo de directiva**: Filtrar mensajes por tipo de directiva:
     - **Directiva antimalware**
     - **Caja fuerte Directiva de datos adjuntos**
     - **Política Antiphishing**
     - **Directiva de filtro de contenido alojado** (directiva anti-spam)
     - **Regla de transporte**
   - **Destinatario de correo** electrónico: todos los usuarios o solo los mensajes que se le envíen. Los usuarios finales solo pueden administrar los mensajes en cuarentena que se les envíen.

   Para borrar el filtro, haga clic en **Borrar**. Para ocultar el control flotante del filtro, haga clic de nuevo en **Filtrar**.

5. Use **Ordenar resultados por**(de forma predeterminada, el botón **Id. de mensaje**) y el valor correspondiente para encontrar mensajes específicos. No se admiten los caracteres comodín. Puede buscar según los siguientes valores:
   - **Id. de mensaje**: El identificador único global del mensaje.

     Por ejemplo, usó [el](message-trace-scc.md) seguimiento de mensajes para buscar un mensaje que se envió a un usuario de la organización y se determina que el mensaje se ha puesto en cuarentena en lugar de entregarse. Asegúrese de incluir el valor de identificador de mensaje completo, que puede incluir corchetes angulares ( \<\> ). Por ejemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.

   - **Dirección de correo electrónico del remitente**: Una única dirección de correo electrónico de remitente.
   - **Nombre de directiva**: Use el nombre de la Directiva completa del mensaje. La búsqueda no distingue entre mayúsculas y minúsculas.
   - **Dirección de correo electrónico del destinatario**: Una única dirección de correo electrónico de destinatario.
   - **Asunto**: Use el asunto completo del mensaje. La búsqueda no distingue entre mayúsculas y minúsculas.
   - **Nombre de** la directiva: el nombre de la directiva responsable de la anulación del mensaje.

   Cuando haya introducido los criterios de búsqueda, haga clic en ![Botón actualizar](../../media/scc-quarantine-refresh.png) **Actualizar** para filtrar los resultados.

Cuando encuentre un mensaje en cuarentena específico, seleccione el mensaje para ver los detalles del mismo y para realizar una acción (por ejemplo, ver, liberar, descargar o eliminar el mensaje).

#### <a name="view-quarantined-message-details"></a>Ver detalles de mensajes en cuarentena

Al seleccionar un mensaje de correo electrónico en la lista, los siguientes detalles del mensaje están disponibles en el menú desplegable de detalles que aparece:

- **Id. de mensaje**: El identificador único global para el mensaje.
- **Dirección del remitente**
- **Recibido**: La fecha/hora en que se ha recibido el mensaje.
- **Asunto**
- **Motivo de cuarentena:** muestra si un mensaje se ha identificado como **Correo** no deseado **,** Masivo , **Phish**, coincide con una regla de flujo de correo (**regla** de transporte ), o si se identificó como que contiene **malware**.
- **Recuento de destinatarios**
- **Destinatarios**: Si el mensaje contiene varios destinatarios, deberá hacer clic en **Vista previa del mensaje** o **Ver encabezado del mensaje** para ver la lista completa de destinatarios.
- **Expira**: La fecha/hora en que el mensaje se eliminará automática y permanentemente de la cuarentena.
- **Liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje se ha liberado.
- **Todavía no se ha liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje no se ha liberado aún.

### <a name="take-action-on-quarantined-email"></a>Llevar a cabo una acción en un correo electrónico en cuarentena

Después de seleccionar un mensaje, tiene varias opciones para qué hacer con los mensajes en el menú desplegable de detalles:

- **Mensaje de versión:** en el menú desplegable que aparece, elija las siguientes opciones:
  - **Notificar mensajes a Microsoft para su** análisis: está seleccionado de forma predeterminada e informa el mensaje erróneamente en cuarentena a Microsoft como falso positivo. Si el mensaje se ha puesto en cuarentena como correo no deseado, masivo, suplantación de identidad (phishing) o que contiene malware, el mensaje también se notifica al equipo de análisis de correo no deseado de Microsoft. Según su análisis, las reglas de filtro de correo no deseado de todo el servicio podrían ajustarse para permitir la entrada del mensaje.
  - Elija una de las siguientes opciones:
    - **Liberar mensajes a todos los destinatarios**
    - **Liberar mensajes a destinatarios específicos**
    - **Liberar mensajes a otras personas:** tenga en cuenta que no se admite liberar mensajes de malware a personas que no son destinatarios originales.

  Cuando haya terminado, haga clic en **Liberar mensajes**.

  Notas sobre cómo liberar mensajes:

  - No puede liberar un mensaje al mismo destinatario más de una vez.
  - Solo los destinatarios que no hayan recibido el mensaje aparecerán en la lista de posibles destinatarios.

- **Ver encabezado del mensaje**: Seleccione este vínculo para ver el texto del encabezado del mensaje. Copie el texto del encabezado del mensaje en el portapapeles para analizar los campos y valores del encabezado en profundidad y luego elija **Analizador de encabezados de mensaje de Microsoft** para desplazarse hasta el Analizador de conectividad remota (haga clic con el botón derecho y elija **Abrir en una nueva pestaña** si no desea que Microsoft 365 complete esta tarea). Pegue el encabezado del mensaje en la página en la sección del Analizador de encabezados de mensaje y seleccione **Analizar encabezados**:
- **Mensaje de vista** previa: en el menú desplegable que aparece, elija una de las siguientes opciones:
  - **Vista de código fuente**: Muestra la versión HTML del cuerpo del mensaje con todos los vínculos desactivados.
  - **Vista de texto**: Muestra el cuerpo del mensaje como texto sin formato.
- **Quitar de la cuarentena:** después de hacer clic en **Sí** en la advertencia que aparece, el mensaje se elimina inmediatamente sin enviarse a los destinatarios originales.
- **Descargar mensaje:** en el control desplegable que aparece, **seleccione** Comprender los riesgos de descargar este mensaje para guardar una copia local del mensaje en formato .eml.
- **Bloquear remitente**: Agregue el remitente a la lista Remitentes bloqueados del buzón. Para más información, consulte [Bloquear un remitente de correo](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).
- **Enviar mensaje:** en el menú desplegable que aparece, elija las siguientes opciones:
  - **Tipo de objeto**: **Correo electrónico** (predeterminado), **DIRECCIÓN URL** o **Datos adjuntos**.
  - **Formato de envío:** **Id.** de mensaje de red (predeterminado, con el valor correspondiente en el cuadro **Id.** de mensaje de red) o **Archivo** (vaya a un archivo .eml o .msg local). Tenga en cuenta que si selecciona **Archivo** y, a continuación, selecciona **Id. de mensaje** de red, el valor inicial se ha ido.
  - **Destinatarios:** escriba en concesión un destinatario original del mensaje o haga clic en **Seleccionar** todo para identificar todos los destinatarios. También puede hacer clic en **Seleccionar todo y,** a continuación, quitar selectivamente los destinatarios individuales.
  - **Motivo del envío:** **no debería haber sido bloqueado** (predeterminado) o debería haber sido **bloqueado**.

  Cuando haya terminado, haga clic en **Enviar**.

Si no libera o elimina el mensaje, se eliminará cuando expire el período de retención en cuarentena predeterminado.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Realice una acción en varios mensajes de correo electrónico en cuarentena

Cuando selecciona varios mensajes en cuarentena en la lista (hasta 100), aparece el **control** desplegable Acciones masivas donde puede realizar las siguientes acciones:

- **Liberar mensajes**: Las opciones son las mismas que cuando libera un único mensaje, salvo que no puede seleccionar **Liberar mensajes para destinatarios específicos**; solo puede seleccionar **Liberar mensaje para todos los destinatarios** o **Liberar mensajes para otras personas**.

  > [!NOTE]
  > Tenga en cuenta el siguiente escenario: john@gmail.com envía un mensaje a faith@contoso.com y john@subsidiary.contoso.com. Gmail bifurca este mensaje en dos copias que se enrutan a la cuarentena como phishing en Microsoft. Un administrador libera ambos mensajes para admin@contoso.com. Se entrega el primer mensaje publicado que llega al buzón de administración. El segundo mensaje liberado se identifica como entrega duplicada y se omite. Los mensajes se identifican como duplicados si tienen el mismo identificador de mensaje y el mismo tiempo recibido.

- **Eliminar mensajes:** después de hacer clic en **Sí** en la advertencia que aparece, los mensajes se eliminan inmediatamente sin que se envíen a los destinatarios originales.

Cuando haya terminado, haga clic en **Cerrar**.

## <a name="use-the-security-center-to-manage-quarantined-files-in-defender-for-office-365"></a>Use el Centro de seguridad para administrar archivos en cuarentena en Defender para Office 365

> [!NOTE]
> Los procedimientos para los archivos en cuarentena de esta sección solo están disponibles para Microsoft Defender Office 365 los suscriptores del Plan 1 y plan 2.

En organizaciones con Defender para Office 365, los administradores pueden administrar archivos en cuarentena en SharePoint Online, OneDrive para la Empresa y Microsoft Teams. Para habilitar la protección de estos archivos, vea Activar Caja fuerte datos adjuntos para [SharePoint, OneDrive y Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).

### <a name="view-quarantined-files"></a>Ver archivos en cuarentena

1. En el centro de seguridad, vaya a **Correo & de colaboración** \> **Revisar** \> **cuarentena**.

2. En la **página Cuarentena,** cambie **Ver en cuarentena** a los archivos de **valor**. Puede ordenar un campo haciendo clic en un encabezado de columna disponible.

3. Para ordenar los resultados, haga clic en un encabezado de columna disponible. Haga clic en **Modificar columnas** para mostrar un máximo de siete columnas. Las columnas predeterminadas se marcan con un asterisco ( <sup>\*</sup> ):
   - **Usuario**<sup>\*</sup>
   - **Ubicación**<sup>\*</sup>
   - **Nombre de archivo**<sup>\*</sup>
   - **DIRECCIÓN URL de archivo**<sup>\*</sup>
   - **Tamaño de archivo**<sup>\*</sup>
   - **Expira**<sup>\*</sup>
   - **¿Liberado?**<sup>\*</sup>
   - **Detectado por**
   - **Modificado por hora**

4. Para filtrar los resultados, haga clic en **Filtrar**. Los filtros disponibles son:
   - **Hora de expiración**: Filtrar los mensajes según cuando expiran de la cuarentena:
     - **Hoy**
     - **Próximos 2 días**
     - **Próximos 7 días**
     - Un intervalo de fecha y hora personalizado.
   - **Tiempo recibido**
   - **Motivo de cuarentena:** el único valor disponible es **Malware**.
   - **Tipo de directiva**

Después de encontrar un archivo en cuarentena específico, seleccione el archivo para ver detalles sobre él y para realizar acciones sobre él (por ejemplo, ver, liberar, descargar o eliminar el mensaje).

#### <a name="view-quarantined-file-details"></a>Ver detalles del archivo en cuarentena

Al seleccionar un archivo en la lista, los siguientes detalles del archivo están disponibles en el menú desplegable de detalles que se abre:

- **Nombre de archivo**
- **Dirección URL de** archivo: dirección URL que define la ubicación del archivo (por ejemplo, en SharePoint online).
- **Contenido malintencionado detectado en** La fecha y hora en que el archivo se ha puesto en cuarentena.
- **Expira:** la fecha en la que el archivo se eliminará de la cuarentena.
- **Detectado por**: Defender para Office 365 o el motor antimalware de Microsoft.
- **¿Liberado?**
- **Nombre de malware**
- **Id. de** documento: identificador único del documento.
- **Tamaño de archivo:** en kilobytes (KB).
- **Organización** Id. único de la organización.
- **Última modificación**
- **Modified By:** el usuario que modificó por última vez el archivo.
- Valor de algoritmo hash seguro de **256 bits (SHA-256):** puede usar este valor hash para identificar el archivo en otros almacenes de reputación o en otras ubicaciones del entorno.

### <a name="take-action-on-quarantined-files"></a>Realizar acciones en archivos en cuarentena

Al seleccionar un archivo en la lista, puede realizar las siguientes acciones en el archivo en el menú desplegable de detalles:

- **Liberar archivos:** seleccione (predeterminado) o anule la selección de Archivos de informe en **Microsoft** para su análisis y, a continuación, haga clic **en Liberar archivos**.
- **Descargar archivo**
- **Quitar archivo de cuarentena**

Si no libera o quita los archivos, se eliminarán después de que expire el período de retención de cuarentena predeterminado.

#### <a name="actions-on-multiple-quarantined-files"></a>Acciones en varios archivos en cuarentena

Al seleccionar varios archivos en cuarentena en la lista (hasta 100), aparece el **control** desplegable Acciones masivas donde puede realizar las siguientes acciones:

- **Liberar archivos**
- **Eliminar archivos:** después de hacer clic en **Sí** en la advertencia que aparece, los archivos se eliminan inmediatamente.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Usar Exchange Online PowerShell o PowerShell de EOP independiente para ver y administrar mensajes y archivos en cuarentena

Los cmdlets que usa para ver y administrar mensajes y archivos en cuarentena son:

- [Delete-QuarantineMessage](/powershell/module/exchange/delete-quarantinemessage)

- [Export-QuarantineMessage](/powershell/module/exchange/export-quarantinemessage)

- [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)

- [Preview-QuarantineMessage:](/powershell/module/exchange/preview-quarantinemessage)tenga en cuenta que este cmdlet solo es para mensajes, no archivos en cuarentena de datos adjuntos de Caja fuerte para SharePoint, OneDrive y Microsoft Teams.

- [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)
