---
title: Administrar archivos y mensajes en cuarentena como un administrador en Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: Los administradores pueden ver, liberar y eliminar todos los tipos de mensajes en cuarentena para todos los usuarios. Solo los administradores pueden administrar los mensajes que se pusieron en cuarentena como malware, la suplantación de identidad de confianza alta o como resultado de las reglas de flujo de correo (reglas de transporte).
ms.openlocfilehash: fdab820d2ccedaf8e4f51ba71b15d2c807d06dd1
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857083"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a>Administrar archivos y mensajes en cuarentena como un administrador en Office 365

Quarantine contiene mensajes potencialmente peligrosos o no deseados en las organizaciones de Office 365 con buzones en Exchange online o organizaciones independientes de Exchange Online (EOP) sin buzones de Exchange Online. Para obtener más información, consulte [Quarantine in Office 365](quarantine-email-messages.md).

Los administradores pueden ver, liberar y eliminar todos los tipos de mensajes en cuarentena para todos los usuarios. Solo los administradores pueden administrar los mensajes que se pusieron en cuarentena como malware, la suplantación de identidad de confianza alta o como resultado de las reglas de flujo de correo (también conocidas como reglas de transporte). Los administradores también pueden informar de falsos positivos a Microsoft.

Los administradores de organizaciones con la protección contra amenazas avanzada (ATP) de Office 365 también pueden ver, descargar y eliminar archivos en cuarentena en SharePoint Online, OneDrive para la empresa y Microsoft Teams.

Puede ver y administrar los mensajes en cuarentena en el centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para Office 365 clientes; Exchange Online Protection PowerShell para clientes independientes de EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Para abrir el centro de cumplimiento de & de seguridad de Office <https://protection.office.com>365, vaya a. Para abrir la página de cuarentena directamente, vaya <https://protection.office.com/quarantine>a.

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse al PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Para conectarse a PowerShell de Exchange Online Protection, vea [conectarse a PowerShell de Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Debe tener permisos asignados para poder administrar la cuarentena como administrador. Los permisos se controlan mediante el rol **cuarentena** en el centro de seguridad & cumplimiento. De forma predeterminada, este rol se asigna a los grupos de roles administración de la **organización** (administradores globales), **Administrador de cuarentena**y administrador de **seguridad** en el centro de seguridad & cumplimiento. Para obtener más información, consulte [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Los mensajes en cuarentena se conservan durante un período de tiempo predeterminado antes de que se eliminen automáticamente:

  - Mensajes puestos en cuarentena por directivas contra correo no deseado (correo no deseado, phishing y correo electrónico masivo): 30 días. Este es el valor predeterminado y máximo. Para configurar este valor, consulte [configurar directivas contra correo no deseado en Office 365](configure-your-spam-filter-policies.md).

  - Mensajes puestos en cuarentena por las reglas de flujo de correo (la acción de regla es **entregar el mensaje a la cuarentena hospedada**): 30 días. No puede cambiar este valor.

  - Mensajes que contienen malware: 15 días.

  Cuando un mensaje expira de la cuarentena, no puede recuperarlo.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>Usar el centro de seguridad & cumplimiento para administrar los mensajes de correo electrónico en cuarentena

### <a name="view-quarantined-email"></a>Ver el correo electrónico en cuarentena

1. En el centro de seguridad y cumplimiento, vaya a **Threat Management** \> **Review** \> **Quarantine**.

2. Compruebe que **vista en cuarentena** se haya establecido en el **correo**de valor predeterminado.

3. Puede ordenar los resultados haciendo clic en un encabezado de columna disponible. Haga clic en **modificar columnas** para mostrar un máximo de siete columnas. Los valores predeterminados están marcados con<sup>\*</sup>un asterisco ():

   - **Obtenido**<sup>\*</sup>

   - **Remitente**<sup>\*</sup>

   - **Asunto**<sup>\*</sup>

   - **Motivo de cuarentena**<sup>\*</sup>

   - **Exento?**<sup>\*</sup>

   - **Tipo de Directiva**<sup>\*</sup>

   - **Expira**<sup>\*</sup>

   - **Recipient**

   - **Id. del mensaje**

   - **Nombre de la directiva**

   - **Size**

   - **Direction**

   Cuando haya terminado, haga clic en **Guardar**o haga clic en **establecer como predeterminado**.

4. Para filtrar los resultados, haga clic en **filtro**. Los filtros disponibles son los siguientes:

   - **Expira el tiempo**: filtrar los mensajes cuando expiren de la cuarentena:

     - **Toda**

     - **Próximos 2 días**

     - **Próximos 7 días**

     - **Personalizado**: especifique una **fecha de inicio** y una **fecha de finalización**.

   - **Hora de recepción**: especifique una **fecha de inicio** y una fecha de **finalización**.

   - **Motivo de cuarentena**:

     - **Directiva**: el mensaje coincide con las condiciones de una regla de flujo de correo (también denominada regla de transporte).

     - **Masivo**

     - **Conseguir**

     - **Malware**

     - **Correo no deseado**

     - **Phish de confianza alta**

   - **Destinatario de correo electrónico**: todos los usuarios o solo los mensajes que se le envíen. Los usuarios finales solo pueden administrar los mensajes en cuarentena que se les envían.

   Para borrar el filtro, haga clic en **Borrar**. Para ocultar el control flotante de filtro, haga clic de nuevo en **filtro** .

5. Use **ordenar resultados por** (el botón **identificador del mensaje** de forma predeterminada) y un valor correspondiente para buscar mensajes específicos. No se admiten caracteres comodín. Puede buscar por los siguientes valores:

   - **Identificador del mensaje**: el identificador único global del mensaje.

        Por ejemplo, usó el [seguimiento de mensajes](message-trace-scc.md) para buscar un mensaje que se envió a un usuario de su organización y usted determina que el mensaje se puso en cuarentena en lugar de entregarse. Asegúrese de incluir el valor completo del identificador de mensaje, que puede incluir corchetes\<\>angulares (). Por ejemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.

   - **Dirección de correo electrónico del remitente**: una sola dirección de correo electrónico del remitente.

   - **Dirección de correo electrónico del destinatario**: dirección de correo electrónico de un único destinatario.

   - **Asunto**: usar el asunto completo del mensaje. La búsqueda no distingue mayúsculas de minúsculas.

   Una vez que haya introducido los criterios de búsqueda ![, haga](../media/scc-quarantine-refresh.png) clic en actualizar botón **Actualizar** para filtrar los resultados.

Una vez que haya encontrado un mensaje en cuarentena específico, seleccione el mensaje para ver los detalles del mismo y para realizar acciones en él (por ejemplo, ver, liberar, descargar o eliminar el mensaje).

#### <a name="export-message-results"></a>Exportar resultados de mensajes

1. Seleccione los mensajes que le interesan y haga clic en **exportar resultados**.

2. Haga clic en **sí** en el mensaje de confirmación que le advierte de que debe mantener abierta la ventana del explorador.

3. Una vez que la exportación esté lista, puede asignar un nombre y elegir la ubicación de descarga del archivo. csv.

#### <a name="view-quarantined-message-details"></a>Ver los detalles de los mensajes en cuarentena

Al seleccionar un mensaje de correo electrónico en la lista, aparecen los siguientes detalles del mensaje en el panel flotante **detalles** :

- **Identificador del mensaje**: el identificador único global para el mensaje.

- **Dirección del remitente**

- **Received**: fecha y hora en que se recibió el mensaje.

- **Subject**

- **Motivo de cuarentena**: muestra si un mensaje se ha identificado **como correo no deseado**, en **masa**, **phish**, coincide con una regla de flujo de correo (**regla de transporte**) o se identificó como **malware**que lo contiene.

- **Destinatarios**: Si el mensaje contiene varios destinatarios, debe hacer clic en **vista previa del mensaje** o **Ver encabezado de mensaje** para ver la lista completa de destinatarios.

- **Expires**: fecha y hora en que se eliminará el mensaje de forma automática y permanente de la cuarentena.

- **Fecha de liberación para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje se ha liberado.

- **Todavía no se ha lanzado a**: todas las direcciones de correo electrónico (si las hay) en las que el mensaje no se ha lanzado todavía.

### <a name="take-action-on-quarantined-email"></a>Realizar acciones en correo electrónico en cuarentena

Después de seleccionar un mensaje, tiene varias opciones para qué hacer con los mensajes en el panel flotante **detalles** :

- **Mensaje de liberación**: en el panel flotante que aparece, elija las siguientes opciones:

  - **Notificar mensajes a Microsoft para su análisis**: esta opción está seleccionada de forma predeterminada y notifica a Microsoft el mensaje con una cuarentena incorrecta como falso positivo. Si el mensaje se puso en cuarentena como correo no deseado, en masa o con suplantación de identidad o con malware, el mensaje también se notifica al equipo de análisis de correo no deseado de Microsoft. Según el análisis, las reglas de filtro de correo no deseado de todo el servicio pueden ajustarse para permitir el paso del mensaje.

  - Elija una de las siguientes opciones:

    - **Liberar mensajes para todos los destinatarios**

    - **Liberar mensajes a destinatarios específicos**

    - **Liberar mensajes para otros usuarios**

  Cuando haya terminado, haga clic en **liberar mensajes**.

  Notas sobre la liberación de mensajes:

  - No puede publicar un mensaje en el mismo destinatario más de una vez.

  - Solo los destinatarios que no recibieron el mensaje aparecerán en la lista de posibles destinatarios.

- **Ver encabezado de mensaje**: haga clic en este vínculo para ver el texto del encabezado del mensaje. Para analizar los campos y valores de encabezado en profundidad, copie el texto del encabezado del mensaje en el portapapeles y, a continuación, elija **analizador de encabezados de mensajes de Microsoft** para ir al analizador de conectividad remota (haga clic con el botón secundario y elija **abrir en una nueva pestaña** si no desea salir de Office 365 para completar esta tarea). Pegue el encabezado del mensaje en la página en la sección analizador de encabezados de mensaje y elija **analizar encabezados**:

- **Vista previa del mensaje**: en el panel flotante que aparece, elija una de las siguientes opciones:

  - **Vista de código fuente**: muestra la versión HTML del cuerpo del mensaje con todos los vínculos deshabilitados.
  
  - **Vista de texto**: muestra el cuerpo del mensaje en texto sin formato.

- **Quitar de cuarentena**: después de hacer clic en **sí** en la advertencia que aparece, el mensaje se elimina inmediatamente sin enviarse a los destinatarios originales.

- **Mensaje de descarga**: en el panel flotante que aparece, seleccione entiendo **los riesgos de descargar este mensaje** para guardar una copia local del mensaje en formato. eml.

- **Enviar mensaje**: en el panel flotante que aparece, elija las siguientes opciones:

  - **Tipo de objeto**: **email** (predeterminado), **URL**o **Attachment**.

  - **Formato de envío**: **identificador de mensaje de red** (predeterminado, con el valor correspondiente en el cuadro identificador de mensaje de **red** ) o **archivo** (busque un archivo. eml o. msg local). Tenga en cuenta que si selecciona **archivo** y, a continuación, selecciona **identificador de mensaje de red**, el valor inicial desaparece.

  - **Destinatarios**: escriba la concesión un destinatario original del mensaje o haga clic en **seleccionar todo** para identificar todos los destinatarios. También puede hacer clic en **seleccionar todo** y quitar selectivamente destinatarios individuales.

  - **Motivo del envío**: **no se debe haber bloqueado** (predeterminado) o **debe haberse bloqueado**.

  Cuando haya terminado, haga clic en **Enviar**.

Si no publica ni quita el mensaje, se eliminará cuando expire el período de retención de cuarentena predeterminado.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Realizar acciones en varios mensajes de correo electrónico en cuarentena

Al seleccionar varios mensajes en cuarentena en la lista (hasta 100), aparece el panel flotante **acciones en masa** donde puede realizar las siguientes acciones:

- **Mensajes de liberación**: las opciones son las mismas que cuando se libera un solo mensaje, excepto que no se pueden seleccionar **mensajes de liberación a destinatarios específicos**; solo puede seleccionar **liberar mensaje para todos los destinatarios** o **mensajes de liberación a otros usuarios**.

- **Eliminar mensajes**: después de hacer clic en **sí** en la advertencia que aparece, el mensaje se elimina inmediatamente sin enviarse a los destinatarios originales.

Cuando haya terminado, haga clic en **cerrar**.

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Solo ATP: usar el centro de seguridad & cumplimiento para administrar los archivos en cuarentena

> [!NOTE]
> Los procedimientos para los archivos en cuarentena de esta sección solo están disponibles para los suscriptores de ATP plan 1 y plan 2.

En las organizaciones con ATP, los administradores pueden administrar los archivos en cuarentena en SharePoint Online, OneDrive para la empresa y Microsoft Teams.

### <a name="view-quarantined-files"></a>Ver archivos en cuarentena

1. En el centro de seguridad y cumplimiento, vaya a **Threat Management** \> **Review** \> **Quarantine**.

2. Cambiar **vista en cuarentena** en los **archivos**de valores predeterminados. Puede ordenar por un campo haciendo clic en un encabezado de columna disponible.

3. Puede ordenar los resultados haciendo clic en un encabezado de columna disponible. Haga clic en **modificar columnas** para mostrar un máximo de siete columnas. Las columnas predeterminadas se marcan con<sup>\*</sup>un asterisco ():

   - **Usuario**<sup>\*</sup>

   - **Ubicaciones**<sup>\*</sup>

   - **Nombre de archivo**<sup>\*</sup>

   - **Dirección URL de archivo**<sup>\*</sup>

   - **Tamaño de archivo**<sup>\*</sup>

   - **Expira**<sup>\*</sup>

   - **Exento?**<sup>\*</sup>

   - **Detectado por**

   - **Modificado por hora**

4. Para filtrar los resultados, haga clic en **filtro**. Los filtros disponibles son los siguientes:

   - **Expira el tiempo**: filtrar los mensajes cuando expiren de la cuarentena:

     - **Toda**

     - **Próximos 2 días**

     - **Próximos 7 días**

     - Un intervalo de fecha y hora personalizado.

   - **Hora de recepción**

   - **Motivo de cuarentena**: el único valor disponible es **malware**.

Una vez que haya encontrado un archivo en cuarentena específico, seleccione el archivo para ver los detalles del mismo y para realizar acciones en él (por ejemplo, ver, liberar, descargar o eliminar el mensaje).

#### <a name="export-file-results"></a>Resultados de la exportación de archivos

1. Seleccione los archivos que le interesan y haga clic en **exportar resultados**.

2. Haga clic en **sí** en el mensaje de confirmación que le advierte de que debe mantener abierta la ventana del explorador.

3. Una vez que la exportación esté lista, puede asignar un nombre y elegir la ubicación de descarga del archivo. csv.

#### <a name="view-quarantined-file-details"></a>Ver detalles de archivo en cuarentena

Al seleccionar un archivo de la lista, aparecen los siguientes detalles de archivo en el panel flotante de **detalles** :

- **Nombre de archivo**

- **Dirección URL del archivo**: dirección URL que define la ubicación del archivo (por ejemplo, en SharePoint Online).

- **Contenido malintencionado detectado en** La fecha y la hora en que se puso en cuarentena el archivo.

- **Expires**: la fecha en la que se eliminará el archivo de la cuarentena.

- **Detectado por**: ATP (protección contra amenazas avanzada) o motor antimalware de Microsoft.

- **Exento?**

- **Nombre del malware**

- **Identificador de documento**: un identificador único para el documento.

- **Tamaño de archivo**: en kilobytes (KB).

- **Organización** El identificador único de su organización.

- **Última modificación**

- **Modificado por**: el usuario que modificó el archivo por última vez.

- **Algoritmo hash seguro 256-bit (SHA-256) valor**: puede usar este valor de hash para identificar el archivo en otros almacenes de reputación o en otras ubicaciones del entorno.

### <a name="take-action-on-quarantined-files"></a>Realizar acciones en archivos en cuarentena

Al seleccionar un archivo de la lista, puede realizar las siguientes acciones en el archivo del panel flotante de **detalles** :

- **Liberar archivos**: seleccione (predeterminado) o anule la selección **de archivos de informe a Microsoft para su análisis**y, a continuación, haga clic en **liberar archivos**.

- **Descargar archivo**

- **Quitar archivo de la cuarentena**

Si no libera ni quita los archivos, se eliminarán después de que expire el período de retención de cuarentena predeterminado.

#### <a name="actions-on-multiple-quarantined-files"></a>Acciones en varios archivos en cuarentena

Al seleccionar varios archivos en cuarentena en la lista (hasta 100), aparece el panel flotante **acciones en masa** donde puede realizar las siguientes acciones:

- **Liberar archivos**

- **Eliminar archivos**: después de hacer clic en **sí** en la advertencia que aparece, los archivos se eliminan inmediatamente.

Cuando haya terminado, haga clic en **cerrar**.

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Usar Exchange Online PowerShell o PowerShell independiente de Exchange Online Protection para ver y administrar los mensajes y archivos en cuarentena

Los cmdlets que se usan para ver y administrar mensajes y archivos en cuarentena son los siguientes:

- [Delete-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [Export-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- [Vista previa de QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): tenga en cuenta que este cmdlet solo es para los mensajes, no para los archivos de malware de ATP para SharePoint Online, OneDrive para la empresa o Teams.

- [Versión-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
