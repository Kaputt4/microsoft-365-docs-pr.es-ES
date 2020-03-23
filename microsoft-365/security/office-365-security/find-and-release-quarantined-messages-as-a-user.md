---
title: Buscar y liberar mensajes en cuarentena como usuario de Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: Como usuario de Office 365, puede ver, liberar y eliminar los mensajes puestos en cuarentena (mensajes de los que es destinatario y que el filtrado de correo no deseado puso en cuarentena como correo no deseado o correo electrónico masivo). Puede ver y administrar los mensajes en cuarentena en el Centro de seguridad y cumplimiento.
ms.openlocfilehash: 04f04cfddb123bf176f3c71568789c77d225a601
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893675"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a>Buscar y liberar mensajes en cuarentena como usuario de Office 365

La cuarentena retiene los mensajes que pueden ser peligrosos o no deseados en las organizaciones de Office 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online. Para obtener más información, consulte [Cuarentena en Office 365](quarantine-email-messages.md).

Como usuario, puede ver, liberar y eliminar mensajes puestos en cuarentena de los que es destinatario y que fueron puestos en cuarentena como correo no deseado, correo electrónico masivo o (a partir de abril de 2020) de suplantación de identidad. También puede notificar falsos positivos a Microsoft.

Puede ver y administrar los mensajes en cuarentena en el Centro de seguridad y cumplimiento.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Para abrir el Centro de seguridad y cumplimiento de Office 365, vaya a <https://protection.office.com> Para abrir directamente la página de Cuarentena, vaya a <https://protection.office.com/quarantine>.

- Los administradores pueden configurar cuánto tiempo se conservan los mensajes en cuarentena antes de que se eliminen de forma permanente (directivas contra correo electrónico no deseado). Los mensajes que han expirado de la cuarentena no se pueden recuperar. Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado en Office 365 ](configure-your-spam-filter-policies.md).

- Los administradores también pueden [configurar notificaciones de correo no deseado para el usuario final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) en directivas contra correo no deseado. A partir de octubre de 2019, ya no podrá liberar mensajes en cuarentena directamente desde estas notificaciones. Puede hacer clic en **Revisar** en la notificación, que le redireccionará a Cuarentena en el Centro de seguridad y cumplimiento. Para obtener más información sobre las notificaciones, consulte [Notificaciones de correo no deseado para el usuario final en Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).

- Los mensajes puestos en cuarentena por suplantación de identidad de alta confianza, malware o por reglas de flujo de correo (también conocidas como reglas de transporte) solo están disponibles para los administradores. Para más información, consulte [Administrar mensajes en cuarentena y archivos como administrador en Office 365](manage-quarantined-messages-and-files.md).

- Únicamente puede liberar un mensaje e identificarlo como un falso positivo (deseado) una vez.

## <a name="view-your-quarantined-messages"></a>Ver los mensajes en cuarentena

1. En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Revisar** \> **Cuarentena**.

2. Para ordenar los resultados, haga clic en un encabezado de columna disponible. Haga clic en **Modificar columnas** para mostrar un máximo de siete columnas. Los valores predeterminados están marcados con un asterisco (<sup>\*</sup>):

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

3. Para filtrar los resultados, haga clic en **Filtrar**. Los filtros disponibles son:

   - **Hora de expiración**: Filtrar los mensajes según cuando expiran de la cuarentena:

     - **Hoy**

     - **Próximos 2 días**

     - **Próximos 7 días**

     - **Personalizado**: Introduzca **Fecha de inicio** y **Fecha de finalización**.

   - **Hora de recepción**: Introduzca **Fecha de inicio** y **Fecha de finalización**.

   - **Motivo de la cuarentena**:

     - **Masivo**

     - **Correo no deseado**

     - **Suplantación de identidad** (a partir de abril de 2020)

   Para borrar el filtro, haga clic en **Borrar**. Para ocultar el control flotante del filtro, haga clic de nuevo en **Filtrar**.

4. Use **Ordenar resultados por**(de forma predeterminada, el botón **Id. de mensaje**) y el valor correspondiente para encontrar mensajes específicos. No se admiten los caracteres comodín. Puede buscar según los siguientes valores:

   - **Id. de mensaje**: El identificador único global del mensaje. Si selecciona un mensaje de la lista, el valor **Id. de mensaje** aparece en el panel flotante **Detalles** que aparece. Los administradores pueden usar [seguimiento de mensajes](message-trace-scc.md) para buscar mensajes y los valores de Id. de mensaje correspondientes.

   - **Dirección de correo electrónico del remitente**: Una única dirección de correo electrónico de remitente.

   - **Dirección de correo electrónico del destinatario**: Una única dirección de correo electrónico de destinatario.

   - **Asunto**: Use el asunto completo del mensaje. La búsqueda no distingue entre mayúsculas y minúsculas.

   Cuando haya introducido los criterios de búsqueda, haga clic en ![Botón actualizar](../media/scc-quarantine-refresh.png) **Actualizar** para filtrar los resultados.

Cuando encuentre un mensaje en cuarentena específico, seleccione el mensaje para ver los detalles del mismo y para realizar una acción (por ejemplo, ver, liberar, descargar o eliminar el mensaje).

### <a name="export-message-results"></a>Exportar los resultados de los mensajes

1. Seleccione los mensajes que le interesan y haga clic en **Exportar resultados**.

2. Haga clic en **Sí** en el mensaje de confirmación que le advierte de que debe mantener abierta la ventana del explorador.

3. Cuando la exportación esté lista, puede elegir el nombre y la ubicación de descarga del archivo .csv.

### <a name="view-quarantined-message-details"></a>Ver detalles de mensajes en cuarentena

Cuando selecciona un mensaje de correo electrónico de la lista, aparecen los detalles de mensaje siguientes en el panel flotante **Detalles**:

- **Id. de mensaje**: El identificador único global para el mensaje.

- **Dirección del remitente**

- **Recibido**: La fecha/hora en que se ha recibido el mensaje.

- **Asunto**

- **Motivo de la cuarentena**: Muestra si un mensaje se ha identificado como **Correo no deseado**, **Masivo** o (a partir de abril de 2020) **Suplantación de identidad**.

- **Destinatarios**: Si el mensaje contiene varios destinatarios, deberá hacer clic en **Vista previa del mensaje** o **Ver encabezado del mensaje** para ver la lista completa de destinatarios.

- **Expira**: La fecha/hora en que el mensaje se eliminará automática y permanentemente de la cuarentena.

- **Liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje se ha liberado.

- **Todavía no se ha liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje no se ha liberado aún.

### <a name="take-action-on-quarantined-email"></a>Llevar a cabo una acción en un correo electrónico en cuarentena

Después de seleccionar un mensaje, dispone opciones con respecto a qué hacer con los mensajes en el panel flotante **Detalles**:

- **Liberar mensaje**: En el panel flotante que aparece, elija si desea **Informar de los mensajes a Microsoft para su análisis**. Esta opción está seleccionada de forma predeterminada y comunica a Microsoft el mensaje puesto en cuarentena por error como falso positivo.

  Cuando haya terminado, haga clic en **Liberar mensajes**.

- **Ver encabezado del mensaje**: Seleccione este vínculo para ver el texto del encabezado del mensaje. Copie el texto del encabezado del mensaje en el portapapeles para analizar los campos y valores del encabezado en profundidad y luego elija **Analizador de encabezados de mensaje de Microsoft** para desplazarse hasta el Analizador de conectividad remota (haga clic con el botón derecho y elija **Abrir en una nueva pestaña** si no desea que Office 365 complete esta tarea). Pegue el encabezado del mensaje en la página en la sección del Analizador de encabezados de mensaje y seleccione **Analizar encabezados**:

- **Vista previa del mensaje**: En el panel flotante que aparece, elija una de las siguientes opciones:

  - **Vista de código fuente**: Muestra la versión HTML del cuerpo del mensaje con todos los vínculos desactivados.
  
  - **Vista de texto**: Muestra el cuerpo del mensaje como texto sin formato.

- **Descargar mensaje**: En el panel de flotante que aparece, seleccione **Entiendo los riesgos de descargar este mensaje** para guardar una copia local del mensaje en formato .eml.

- **Eliminar de cuarentena**: Después de hacer clic en **Sí** en la advertencia que aparece, el mensaje se elimina inmediatamente.

Cuando haya terminado, haga clic en **Cerrar**.

Si no libera o elimina el mensaje, se eliminará cuando expire el período de retención en cuarentena predeterminado.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Realice una acción en varios mensajes de correo electrónico en cuarentena

Al seleccionar varios mensajes en cuarentena de la lista (hasta 100), se mostrará el panel de control flotante**Acciones en masa**, donde puede realizar las acciones siguientes:

- **Liberar mensajes**: Las opciones son las mismas que cuando libera un único mensaje, salvo que no puede seleccionar **Liberar mensajes para destinatarios específicos**; solo puede seleccionar**Liberar mensaje para todos los destinatarios** o **Liberar mensajes para otras personas**.

- **Eliminar mensajes**: Después de hacer clic en **Sí** en la advertencia que aparece, el mensaje se elimina inmediatamente sin enviarse a los destinatarios originales.

Cuando haya terminado, haga clic en **Cerrar**.
