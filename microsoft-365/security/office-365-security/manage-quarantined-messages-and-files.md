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
description: Los administradores pueden aprender a ver y administrar mensajes en cuarentena para todos los usuarios en Exchange Online Protection (EOP). Los administradores de organizaciones con Microsoft Defender para Office 365 también pueden administrar archivos en cuarentena en SharePoint Online, OneDrive para la Empresa y Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 22bcf0cefb746e92ccadf8254f4076b47ee475c4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287790"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>Administración de mensajes en cuarentena y archivos como administrador en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

En las organizaciones de Microsoft 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online, la cuarentena retiene los mensajes que pueden ser peligrosos o no deseados. Para obtener más información, vea [Mensajes de correo electrónico en cuarentena en EOP.](quarantine-email-messages.md)

Los administradores pueden ver, liberar y eliminar todos los tipos de mensajes en cuarentena para todos los usuarios. Solo los administradores pueden administrar mensajes que se han puesto en cuarentena como malware, suplantación de identidad de confianza alta o como resultado de reglas de flujo de correo (también conocidas como reglas de transporte). Los administradores también pueden notificar falsos positivos a Microsoft.

Los administradores de organizaciones con Microsoft Defender para Office 365 también pueden ver, descargar y eliminar archivos en cuarentena en SharePoint Online, OneDrive para la Empresa y Microsoft Teams.

Puede ver y administrar los mensajes en cuarentena en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; EOP PowerShell independiente para organizaciones sin buzones de Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Para abrir el Centro de seguridad y cumplimiento, vaya a <https://protection.office.com>. Para abrir directamente la página de Cuarentena, vaya a <https://protection.office.com/quarantine>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:
  - Para realizar acciones en los mensajes en cuarentena para todos los usuarios, debe  ser miembro de los grupos de roles Administración de la **organización,** Administrador de seguridad o Administrador <sup>\*</sup> de cuarentena.
  - Para obtener acceso de solo lectura a los mensajes en cuarentena para todos los usuarios, debe ser miembro de los grupos de roles Lector **global** o **Lector de** seguridad.

  Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

  **Notas**:

  - Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.
  - <sup>\*</sup> Los miembros del grupo **de** roles Administrador de cuarentena también deben ser miembros del grupo de roles **Administración** de higiene en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) para poder realizar procedimientos de cuarentena en Exchange Online PowerShell.

- Los mensajes en cuarentena se conservan durante un período de tiempo predeterminado antes de que se eliminen automáticamente:
  - 30 días para los mensajes en cuarentena por directivas contra correo no deseado (correo no deseado, suplantación de identidad y correo electrónico masivo). Este es el valor predeterminado y máximo. Para configurar (inferior) este valor, consulte [Configurar directivas contra correo no deseado.](configure-your-spam-filter-policies.md)
  - 15 días para los mensajes que contienen malware.
  - 15 días para los archivos en cuarentena por datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams en Defender para Office 365.

  Cuando un mensaje expira de la cuarentena, no se puede recuperar.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>Usar el Centro de seguridad & cumplimiento para administrar mensajes de correo electrónico en cuarentena

### <a name="view-quarantined-email"></a>Ver el correo electrónico en cuarentena

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Revisar** \> **Cuarentena**.

2. Compruebe que **La vista en cuarentena** está establecida en el valor predeterminado correo **electrónico.**

3. Para ordenar los resultados, haga clic en un encabezado de columna disponible. Haga clic en **Modificar columnas** para mostrar un máximo de siete columnas. Los valores predeterminados están marcados con un asterisco (<sup>\*</sup>):

   - **Recibido**<sup>\*</sup>
   - **Remitente**<sup>\*</sup>
   - **Asunto**<sup>\*</sup>
   - **Motivo de la cuarentena**<sup>\*</sup>
   - **¿Liberado?**<sup>\*</sup>
   - **Tipo de directiva**<sup>\*</sup>
   - **Expires**
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
     - **Directiva:** el mensaje coincidía con las condiciones de una regla de flujo de correo (también conocida como regla de transporte).
     - **Correo masivo**
     - **Suplantación** de identidad : el veredicto del filtro de correo no deseado era correo electrónico de suplantación de identidad o protección contra suplantación de identidad **(phishing)** pone en cuarentena el mensaje [(configuración](set-up-anti-phishing-policies.md#spoof-settings) de suplantación de identidad o protección [contra suplantación).](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
     - **Malware**
     - **Correo no deseado**
     - **Suplantación de identidad de confianza alta**

   - **Tipo de directiva**: Filtrar mensajes por tipo de directiva:
     - **Directiva antimalware**
     - **Directiva de datos adjuntos seguros**
     - **Política Antiphishing**
     - **Directiva de filtro de contenido alojado** (directiva anti-spam)
     - **Regla de transporte**

   - **Destinatario de correo** electrónico: todos los usuarios o solo los mensajes que se le envíen. Los usuarios finales solo pueden administrar los mensajes en cuarentena que se les envían.

   Para borrar el filtro, haga clic en **Borrar**. Para ocultar el control flotante del filtro, haga clic de nuevo en **Filtrar**.

5. Use **Ordenar resultados por**(de forma predeterminada, el botón **Id. de mensaje**) y el valor correspondiente para encontrar mensajes específicos. No se admiten los caracteres comodín. Puede buscar según los siguientes valores:

   - **Id. de mensaje**: El identificador único global del mensaje.

     Por ejemplo, [](message-trace-scc.md) usó el seguimiento de mensajes para buscar un mensaje que se envió a un usuario de su organización y determinar que el mensaje se ha puesto en cuarentena en lugar de entregarse. Asegúrese de incluir el valor completo del identificador de mensaje, que puede incluir corchetes angulares ( \<\> ). Por ejemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.

   - **Dirección de correo electrónico del remitente**: Una única dirección de correo electrónico de remitente.

   - **Nombre de directiva**: Use el nombre de la Directiva completa del mensaje. La búsqueda no distingue entre mayúsculas y minúsculas.

   - **Dirección de correo electrónico del destinatario**: Una única dirección de correo electrónico de destinatario.

   - **Asunto**: Use el asunto completo del mensaje. La búsqueda no distingue entre mayúsculas y minúsculas.

   - **Nombre de** la directiva: el nombre de la directiva responsable de la anulación del mensaje.

   Cuando haya introducido los criterios de búsqueda, haga clic en ![Botón actualizar](../../media/scc-quarantine-refresh.png) **Actualizar** para filtrar los resultados.

Cuando encuentre un mensaje en cuarentena específico, seleccione el mensaje para ver los detalles del mismo y para realizar una acción (por ejemplo, ver, liberar, descargar o eliminar el mensaje).

#### <a name="view-quarantined-message-details"></a>Ver detalles de mensajes en cuarentena

Cuando selecciona un mensaje de correo electrónico de la lista, aparecen los detalles de mensaje siguientes en el panel flotante **Detalles**:

- **Id. de mensaje**: El identificador único global para el mensaje.

- **Dirección del remitente**

- **Recibido**: La fecha/hora en que se ha recibido el mensaje.

- **Asunto**

- **Motivo de la** cuarentena: muestra si un mensaje se ha identificado como correo no deseado **,** masivo **,** suplantación de identidad **,** coincide con una regla de flujo de correo **(** regla de transporte ) o se identificó como que contiene **malware**.

- **Número de destinatarios**

- **Destinatarios**: Si el mensaje contiene varios destinatarios, deberá hacer clic en **Vista previa del mensaje** o **Ver encabezado del mensaje** para ver la lista completa de destinatarios.

- **Expira**: La fecha/hora en que el mensaje se eliminará automática y permanentemente de la cuarentena.

- **Liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje se ha liberado.

- **Todavía no se ha liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje no se ha liberado aún.

### <a name="take-action-on-quarantined-email"></a>Llevar a cabo una acción en un correo electrónico en cuarentena

Después de seleccionar un mensaje, tiene varias opciones para  saber qué hacer con los mensajes en el panel desplegable Detalles:

- **Mensaje de** versión: en el panel desplegable que aparece, elija las siguientes opciones:

  - **Notificar mensajes a Microsoft para su** análisis: esta opción está seleccionada de forma predeterminada e informa de que el mensaje en cuarentena erróneamente a Microsoft es un falso positivo. Si el mensaje se ha puesto en cuarentena como correo no deseado, masivo, suplantación de identidad (phishing) o que contiene malware, el mensaje también se notifica al equipo de análisis de correo no deseado de Microsoft. Según su análisis, las reglas de filtro de correo no deseado de todo el servicio podrían ajustarse para permitir que pase el mensaje.

  - Elija una de las siguientes opciones:
    - **Liberar mensajes para todos los destinatarios**
    - **Liberar mensajes a destinatarios específicos**
    - **Liberar mensajes a otras personas:** tenga en cuenta que no se admite liberar mensajes de malware para personas que no son destinatarios originales.

  Cuando haya terminado, haga clic en **Liberar mensajes**.

  Notas sobre la publicación de mensajes:

  - No puede liberar un mensaje para el mismo destinatario más de una vez.
  - Solo los destinatarios que no hayan recibido el mensaje aparecerán en la lista de posibles destinatarios.

- **Ver encabezado del mensaje**: Seleccione este vínculo para ver el texto del encabezado del mensaje. Copie el texto del encabezado del mensaje en el portapapeles para analizar los campos y valores del encabezado en profundidad y luego elija **Analizador de encabezados de mensaje de Microsoft** para desplazarse hasta el Analizador de conectividad remota (haga clic con el botón derecho y elija **Abrir en una nueva pestaña** si no desea que Microsoft 365 complete esta tarea). Pegue el encabezado del mensaje en la página en la sección del Analizador de encabezados de mensaje y seleccione **Analizar encabezados**:

- **Vista previa del mensaje**: En el panel flotante que aparece, elija una de las siguientes opciones:

  - **Vista de código fuente**: Muestra la versión HTML del cuerpo del mensaje con todos los vínculos desactivados.
  - **Vista de texto**: Muestra el cuerpo del mensaje como texto sin formato.

- **Quitar de cuarentena:** después de hacer clic **en** Sí en la advertencia que aparece, el mensaje se elimina inmediatamente sin enviarse a los destinatarios originales.

- **Descargar mensaje**: En el panel de flotante que aparece, seleccione **Entiendo los riesgos de descargar este mensaje** para guardar una copia local del mensaje en formato .eml.

- **Enviar mensaje:** en el panel desplegable que aparece, elija las siguientes opciones:

  - **Tipo de objeto**: **Correo** electrónico (predeterminado), **dirección URL** o **datos adjuntos.**

  - **Formato de** envío: **Id.** de mensaje de  red (predeterminado, con el valor correspondiente en el cuadro Id. de mensaje de red) o **Archivo** (vaya a un archivo .eml o .msg local). Tenga en cuenta que si selecciona **Archivo** y, a continuación, selecciona **Id.** de mensaje de red, el valor inicial se ha perdido.

  - **Destinatarios:** escriba al concesión un destinatario original del mensaje o haga clic en Seleccionar todo **para** identificar a todos los destinatarios. También puede hacer clic **en Seleccionar todo** y, a continuación, quitar destinatarios individuales de forma selectiva.

  - **Motivo del envío:** **no debería haber sido bloqueado** (predeterminado) o debería haber sido **bloqueado.**

  Cuando haya terminado, haga clic en **Enviar.**

Si no libera o elimina el mensaje, se eliminará cuando expire el período de retención en cuarentena predeterminado.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Realice una acción en varios mensajes de correo electrónico en cuarentena

Al seleccionar varios mensajes en cuarentena de la lista (hasta 100), se mostrará el panel de control flotante **Acciones en masa**, donde puede realizar las acciones siguientes:

- **Liberar mensajes**: Las opciones son las mismas que cuando libera un único mensaje, salvo que no puede seleccionar **Liberar mensajes para destinatarios específicos**; solo puede seleccionar **Liberar mensaje para todos los destinatarios** o **Liberar mensajes para otras personas**.

  > [!NOTE]
  > Tenga en cuenta el siguiente escenario: john@gmail.com envía un mensaje a faith@contoso.com y john@subsidiary.contoso.com. Gmail bifurca este mensaje en dos copias que se enruta a cuarentena como suplantación de identidad en Microsoft. Un administrador libera estos dos mensajes para admin@contoso.com. Se entrega el primer mensaje publicado que llega al buzón de administrador. El segundo mensaje publicado se identifica como entrega duplicada y se omite. Los mensajes se identifican como duplicados si tienen el mismo identificador de mensaje y la misma hora de recibido.

- **Eliminar mensajes:** después de hacer clic en **Sí** en la advertencia que aparece, los mensajes se eliminan inmediatamente sin que se envíen a los destinatarios originales.

Cuando haya terminado, haga clic en **Cerrar**.

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Solo Microsoft Defender para Office 365: Usar el Centro de seguridad & cumplimiento para administrar archivos en cuarentena

> [!NOTE]
> Los procedimientos para archivos en cuarentena de esta sección solo están disponibles para suscriptores de Microsoft Defender para Office 365 Plan 1 y Plan 2.

En organizaciones con Defender para Office 365, los administradores pueden administrar archivos en cuarentena en SharePoint Online, OneDrive para la Empresa y Microsoft Teams. Para habilitar la protección de estos archivos, vea Activar datos adjuntos seguros [para SharePoint, OneDrive y Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)

### <a name="view-quarantined-files"></a>Ver archivos en cuarentena

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Revisar** \> **Cuarentena**.

2. Cambiar **vista en cuarentena a** los archivos de **valor.** Puede ordenar un campo haciendo clic en un encabezado de columna disponible.

3. Para ordenar los resultados, haga clic en un encabezado de columna disponible. Haga clic en **Modificar columnas** para mostrar un máximo de siete columnas. Las columnas predeterminadas se marcan con un asterisco ( <sup>\*</sup> ):

   - **Usuario**<sup>\*</sup>
   - **Ubicación**<sup>\*</sup>
   - **Nombre de archivo**<sup>\*</sup>
   - **Dirección URL del archivo**<sup>\*</sup>
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
   - **Tiempo de recibido**
   - **Motivo de la** cuarentena: el único valor disponible es **Malware**.
   - **Tipo de directiva**

Después de encontrar un archivo en cuarentena específico, seleccione el archivo para ver los detalles sobre él y para realizar acciones en él (por ejemplo, ver, liberar, descargar o eliminar el mensaje).

#### <a name="view-quarantined-file-details"></a>Ver detalles del archivo en cuarentena

Al seleccionar un archivo en la lista, los siguientes detalles del archivo aparecen en el **panel** desplegable Detalles:

- **Nombre de archivo**
- **Dirección URL del** archivo: dirección URL que define la ubicación del archivo (por ejemplo, en SharePoint Online).
- **Contenido malintencionado detectado en** La fecha y hora en que el archivo se ha puesto en cuarentena.
- **Expira:** la fecha en la que el archivo se eliminará de la cuarentena.
- **Detectado por**: Defender para Office 365 o el motor antimalware de Microsoft.
- **¿Liberado?**
- **Nombre de malware**
- **Identificador de** documento: identificador único del documento.
- **Tamaño de archivo:** en kilobytes (KB).
- **Organización** Identificador único de su organización.
- **Última modificación**
- **Modificado por:** el usuario que modificó por última vez el archivo.
- Valor de algoritmo hash seguro de **256 bits (SHA-256):** puede usar este valor hash para identificar el archivo en otros almacenes de reputación o en otras ubicaciones de su entorno.

### <a name="take-action-on-quarantined-files"></a>Realizar acciones en archivos en cuarentena

Al seleccionar un archivo en la lista, puede realizar las siguientes acciones en el archivo en el **panel** desplegable Detalles:

- **Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click Release **files**.
- **Descargar archivo**
- **Quitar archivo de cuarentena**

Si no libera o quita los archivos, se eliminarán después de que expire el período de retención de cuarentena predeterminado.

#### <a name="actions-on-multiple-quarantined-files"></a>Acciones en varios archivos en cuarentena

Cuando selecciona varios archivos en cuarentena en la lista (hasta 100), aparece el panel desplegable Acciones masivas, donde puede realizar las siguientes acciones: 

- **Liberar archivos**
- **Eliminar archivos:** después de hacer clic en **Sí** en la advertencia que aparece, los archivos se eliminan inmediatamente.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Usar Exchange Online PowerShell o EOP PowerShell independiente para ver y administrar mensajes y archivos en cuarentena

Los cmdlets que usa para ver y administrar mensajes y archivos en cuarentena son:

- [Delete-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [Export-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- [Preview-QuarantineMessage:](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)tenga en cuenta que este cmdlet solo es para mensajes, no archivos de malware de datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams.

- [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
