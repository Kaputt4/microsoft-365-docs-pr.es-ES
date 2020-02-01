---
title: Buscar y liberar mensajes en cuarentena como un administrador
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ab95bf17-bb09-4dd1-9990-ddd02ddecf05
ms.collection:
- M365-security-compliance
description: En este tema se describe cómo los administradores de Exchange Online y Exchange Online Protection (EOP) pueden buscar, liberar e informar sobre los mensajes en cuarentena en el centro de administración de Exchange (EAC).
ms.openlocfilehash: d7ea57f1dc78b21dae713ca1b9861abafacfc53a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599397"
---
# <a name="find-and-release-quarantined-messages-as-an-administrator"></a>Buscar y liberar mensajes en cuarentena como un administrador

En este tema se describe cómo los administradores de Exchange Online y Exchange Online Protection (EOP) pueden buscar, liberar e informar sobre los mensajes en cuarentena en el centro de administración de Exchange (EAC). Office 365 dirige los mensajes a la cuarentena ya sea porque se identificaron como correo no deseado o coincidieron con una regla de flujo de correo (también denominada regla de transporte).

Puede usar el centro de seguridad & cumplimiento en lugar del EAC para completar estas tareas también; el portal de cuarentena del centro de administración de Exchange (EAC) se establece en decommisioned. Para obtener más información, vea [cuarentena de mensajes de correo electrónico en Office 365](quarantine-email-messages.md).

Los mensajes en cuarentena figuran en la página **cuarentena** de EAC. De forma predeterminada, aparecen ordenados del más reciente al más antiguo en el campo **RECIBIDOS**. También se muestran los valores de **REMITENTE**, **ASUNTO** y **EXPIRA** de cada mensaje. Puede ordenar por cualquiera de estos campos haciendo clic en sus encabezados. Si hace clic en un encabezado de columna por segunda vez, se invertirá el orden. La página **cuarentena** puede mostrar como máximo 500 mensajes.

Puede ver una lista de todos los mensajes en cuarentena o puede buscar mensajes concretos especificando criterios de filtros (el filtrado también puede ayudar a reducir el conjunto de resultados si tiene más de 500 mensajes). Después de buscar y localizar un mensaje en cuarentena concreto, puede consultar detalles sobre dicho mensaje. También puede hacer lo siguiente:

- Puede liberar el mensaje para un destinatario (o para varios) y, opcionalmente, puede identificar el mensaje como falso positivo (es decir, que no se trata de correo no deseado) al equipo de análisis de correo no deseado de Microsoft, quienes lo evaluarán y analizarán. Según los resultados del análisis, se podrían ajustar las reglas de filtro de contenido de correo no deseado de todo el sistema a fin de permitir que pase el mensaje.

- Puede liberar el mensaje y permitir todos los mensajes que el remitente envíe en el futuro.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Deberá tener permisos asignados para poder llevar a cabo estos procedimientos. Para ver qué permisos necesita, consulte el entrada "cuarentena" en el tema [permisos de características de Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) .

- Puede liberar o informar sobre varios mensajes a la vez en la página **cuarentena**. De forma alternativa, puede crear un script de Windows PowerShell remoto para realizar esta tarea. Use el cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) para buscar los mensajes y el cmdlet [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) para liberarlos.

- Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> ¿Problemas? Solicite ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-advanced-search-to-filter-and-locate-quarantined-messages"></a>Usar búsqueda avanzada para filtrar y buscar mensajes en cuarentena

En el centro de administración de Exchange (EAC), puede filtrar elementos en cuarentena con base en distintas condiciones mediante la búsqueda avanzada. Puede utilizar estas condiciones por separado o combinadas. La búsqueda proporcionará una lista de los mensajes que cumplen los criterios del filtro.

1. En EAC, vaya a **Protección** \> **cuarentena** y, a continuación, haga clic en **Búsqueda avanzada**.

2. En la ventana **Búsqueda avanzada**, seleccione cualquier combinación de las condiciones siguientes. Seleccione la casilla de verificación asociada para habilitar cada condición. No se admiten caracteres comodín.

   1. **Identificador del mensaje**: puede usar este parámetro para realizar una búsqueda dirigida de un mensaje específico. Por ejemplo, si un usuario de la organización envió o recibió un mensaje específico, pero el mensaje nunca llegó al destino, puede buscarlo mediante la característica de seguimiento de mensajes. Para más información, consulte [Run a Message Trace and View Results](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/run-a-message-trace-and-view-results). Si descubre que el mensaje se envió a cuarentena, quizás porque coincidía con una regla o se identificó como correo no deseado, lo encontrará fácilmente en la cuarentena especificando este identificador de mensaje. Asegúrese de incluir la cadena de Id. de mensaje completa. Esto puede incluir corchetes angulares\<\>().

   2. **Dirección de correo electrónico del remitente**: especifique la dirección de correo electrónico de la persona que envió el mensaje.

   3. **Dirección de correo electrónico del destinatario**: especifique la dirección de correo electrónico del destinatario del mensaje.

   4. **Asunto**: especifique el texto de la línea de asunto del mensaje.

   5. **Recibido**: puede seleccionar que el mensaje se ha recibido en cuarentena en las últimas 24 horas ( **hoy**), en las últimas 48 horas ( **últimos 2 días**), en la semana pasada ( **últimos 7 días**), o puede seleccionar un intervalo de tiempo personalizado durante el cual la cuarentena recibió el mensaje.

   6. **Expires**: puede seleccionar que el mensaje se eliminará de la cuarentena en las próximas 24 horas ( **hoy**), en las próximas 48 horas ( **próximos 2 días**), en la próxima semana ( **próximos 7 días**), o puede seleccionar un intervalo de tiempo personalizado durante el cual se eliminará el mensaje de la cuarentena.

      > [!IMPORTANT]
      > De forma predeterminada, los mensajes en cuarentena de correo no deseado se mantienen en cuarentena durante 30 días, mientras que los mensajes en cuarentena que coinciden con una regla de flujo de correo se mantienen en cuarentena durante un máximo de 30 días en función del período de retención establecido en la Directiva de filtro de contenido predeterminada. Finalizado este tiempo, Office 365 elimina estos mensajes y ya no se pueden recuperar. No se puede configurar el período de retención de los mensajes en cuarentena que coinciden con una regla de flujo de correo. Sin embargo, es posible reducir el período de retención de los mensajes de correo no deseado en cuarentena mediante la configuración **Mantener el correo no deseado durante (días)** en las directivas de filtro de contenido. Para obtener más información, vea [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).

   7. **Tipo** Puede especificar si desea buscar mensajes en cuarentena que se hayan identificado como **correo no deseado**o si desea buscar los mensajes que coinciden con una regla de flujo de correo (**regla de transporte**).

3. Haga clic en **Aceptar** para iniciar la ejecución de la búsqueda avanzada.

   > [!NOTE]
   > Para borrar el criterio de búsqueda y ver todos los mensajes de la cuarentena, desactive todas las casillas de la ventana **Búsqueda avanzada** y, a continuación, haga clic en **Aceptar**.

Después de buscar los mensajes, los resultados que coinciden con los criterios especificados se muestran en la interfaz de usuario. El EAC puede mostrar como máximo 500 mensajes.

## <a name="view-details-about-a-specific-quarantined-message"></a>Ver detalles acerca de un mensaje en cuarentena específico

Una vez encontrado un mensaje en cuarentena específico en la página **cuarentena**, puede ver detalles acerca de él.

1. En la página **cuarentena**, seleccione un mensaje específico y, en el panel de detalles de la derecha de la pantalla, aparecerá un resumen de las propiedades de ese mensaje.

   Los valores de **estado del mensaje** son:

   - **Tipo**: indica si el mensaje se ha identificado como **correo no deseado** o si coincide con una regla de flujo de correo (**regla de transporte**).

   - **Expires**: la fecha en la que se eliminará el mensaje de la cuarentena.

   Los valores de **detalles del mensaje** son:

   - **Sender**: dirección de correo electrónico de la persona que envió el mensaje.

   - **Subject**: el texto de la línea de asunto del mensaje.

   - **Received**: la fecha en la que la cuarentena recibió el mensaje.

   - **Size**: el tamaño del mensaje, en kilobytes (KB), o bien, si el tamaño del mensaje es superior a 999 KB, en megabytes (MB).

   - **Ver encabezado del mensaje**: haga clic en este vínculo para abrir el cuadro de diálogo **encabezado del mensaje** , que permite ver el texto del encabezado del mensaje. También puede copiar el texto del encabezado del mensaje en el Portapapeles y pegarlo en el [Analizador de encabezados de mensaje](https://testconnectivity.microsoft.com/?tabid=mha). Cuando esté en la herramienta Analizador de encabezados de mensaje, haga clic en **Analizar encabezados** para recuperar la información sobre el encabezado.

    > [!TIP]
    > Para obtener información acerca de los campos de encabezado de mensaje contra correo no deseado específicos que inserta el servicio, consulte [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md).

   - **Vista previa del mensaje de correo electrónico** Haga clic en este vínculo para revisar el texto del mensaje.

2. Si hace doble clic sobre un mensaje en cuarentena, se abre la ventana **Mensaje en cuarentena** y se muestra la información siguiente:

   - **Lanzado a**: una lista de todas las direcciones de correo electrónico a las que se ha lanzado el mensaje, si corresponde.

   - **Todavía no se ha lanzado a**: una lista de todas las direcciones de correo electrónico a las que no se ha lanzado el mensaje, si corresponde. Puede hacer clic en el vínculo **Publicar para** a fin de publicar el mensaje; para obtener más información sobre cómo liberar un mensaje, consulte la sección siguiente.

   - **Identificador del mensaje**: el identificador del mensaje de Internet (también conocido como el identificador de cliente) que se encuentra en el encabezado del mensaje.

   Haga clic en **Cerrar** para volver al panel de cuarentena principal.

## <a name="release-messages-from-quarantine"></a>Liberar mensajes en cuarentena

Si desea liberar los mensajes dirigidos para sus destinatarios, tiene las opciones siguientes:

- [Liberar un mensaje en cuarentena y permitir los mensajes que el remitente envíe en el futuro](#release-a-quarantined-message-and-allow-future-messages-from-the-sender)

- [Liberar un mensaje en cuarentena para sus destinatarios sin identificarlo como falso positivo](#release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive)

- [Liberar un mensajes en cuarentena (o más) para todos los destinatarios](#release-one-or-more-quarantined-messages-to-all-recipients)

- [Liberar un mensaje en cuarentena (o más) para todos los destinatarios e identificarlo como falso positivo](#release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives)

### <a name="release-a-quarantined-message-and-allow-future-messages-from-the-sender"></a>Liberar un mensaje en cuarentena y permitir los mensajes que el remitente envíe en el futuro

1. En EAC, vaya a **Protección** \> **cuarentena**.

2. Haga clic en un mensaje para seleccionarlo y, a continuación, haga clic en el icono **Liberar mensaje** que se muestra en la siguiente pantalla.

   ![Muestra la página de cuarentena con el icono de liberar mensaje resaltado y con las opciones de liberación.](../media/36ee081f-3e30-40c9-8ce3-240cee1970cc.png)

   Haga clic en **Liberar el mensaje seleccionado y permitir el remitente** en la lista desplegable.

3. Se abrirá el cuadro de diálogo **liberar mensaje y permitir remitente**. Si lo desea, puede informar del mensaje a Microsoft; a continuación, haga clic en **liberar y permitir**. El mensaje se liberará para todos los destinatarios y se permitirán todos los mensajes que este remitente envíe en el futuro. Sin embargo, si este mensaje se ha puesto en cuarentena debido a una regla de flujo de correo o a un remitente bloqueado, el remitente seguirá bloqueado para futuros mensajes.

### <a name="release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive"></a>Liberar un mensaje en cuarentena para sus destinatarios sin identificarlo como falso positivo

1. En EAC, vaya a **Protección** \> **cuarentena**.

2. Seleccione un mensaje, haga clic en el icono **Liberar mensaje** y, luego, haga clic en **Liberar mensaje para unos destinatarios específicos** de la lista desplegable.

3. En el cuadro de diálogo **Liberar mensaje**, seleccione una de las siguientes opciones:

   - **Liberar mensaje para todos los destinatarios** Cuando seleccione esta opción, tenga en cuenta que no se puede liberar un mensaje más de una vez para el mismo destinatario. Si un destinatario ya recibió el mensaje, no se lo puede volver a liberar para ese destinatario.

   - **Liberar mensaje para los destinatarios especificados** Seleccione los destinatarios para los que se liberará el mensaje. Dado que el mensaje solamente se puede publicar una vez para cada destinatario, solamente los destinatarios a quienes puede ser publicado aparecen en la lista. Se admite la selección múltiple. Después de seleccionar los destinatarios, haga clic en **agregar**.

4. Haga clic en **publicar**.

Si hace clic en **Actualizar** ![icono](../media/ITPro-EAC-RefreshIcon.gif) de actualización para actualizar los datos y, a continuación, hace doble clic en el mensaje, verá que se ha lanzado a los destinatarios deseados.

### <a name="release-one-or-more-quarantined-messages-to-all-recipients"></a>Liberar un mensajes en cuarentena (o más) para todos los destinatarios

1. En EAC, vaya a **Protección** \> **cuarentena**.

2. Haga clic en un mensaje para seleccionarlo o utilice la tecla MAYÚS para seleccionar varios mensajes. A continuación, haga clic en el icono **Liberar mensaje**.

3. Haga clic en **Liberar los mensajes seleccionados para TODOS los destinatarios** en la lista desplegable.

4. Aparecerá el cuadro de diálogo de advertencia. Lea la advertencia y seleccione **Sí** si desea continuar. Cuando seleccione esta opción, tenga en cuenta que no se puede liberar un mensaje más de una vez para el mismo destinatario. Si un destinatario ya recibió el mensaje, no se puede volver a liberar para ese destinatario.

### <a name="release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives"></a>Liberar un mensaje en cuarentena (o más) para todos los destinatarios e identificarlo como falso positivo

1. En EAC, vaya a **Protección** \> **cuarentena**.

2. Haga clic en un mensaje para seleccionarlo o utilice la tecla MAYÚS para seleccionar varios mensajes. A continuación, haga clic en el icono **Liberar mensaje**.

3. Haga clic en **Liberar los mensajes seleccionados e informar de ellos como falso positivo** en la lista desplegable.

4. Aparecerá el cuadro de diálogo de advertencia. Lea la advertencia y seleccione **Sí** si desea continuar. Cuando seleccione esta opción, tenga en cuenta que no se puede liberar un mensaje más de una vez para el mismo destinatario. Si un destinatario ya recibió el mensaje, no se puede volver a liberar para ese destinatario.

   Cuando se elige esta opción, el mensaje se libera para todos los destinatarios que todavía no lo hayan recibido. Si es un mensaje en cuarentena por correo no deseado, se notificará también al equipo de análisis de correo no deseado de Microsoft, que lo evaluará y analizará. Según los resultados del análisis, se podrían ajustar las reglas de filtro de contenido de correo no deseado de todo el sistema a fin de permitir que pase el mensaje.

> [!TIP]
> Para ayudar a garantizar que un mensaje no se marque como correo no deseado, siga los pasos en [Cómo ayudar a garantizar que un mensaje no se marque como correo no deseado](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md).

Si hace clic en el icono **Actualizar**![Icono Actualizar](../media/ITPro-EAC-RefreshIcon.gif) para actualizar los datos y, a continuación, hace doble clic en el mensaje, verá que se ha liberado para los destinatarios previstos.

## <a name="for-more-information"></a>Más información

[Preguntas más frecuentes sobre la cuarentena](quarantine-faq.md)
