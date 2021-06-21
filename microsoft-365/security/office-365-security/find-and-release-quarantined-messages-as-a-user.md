---
title: Buscar y liberar mensajes en cuarentena como usuario
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los usuarios pueden obtener información sobre cómo ver y administrar los mensajes en cuarentena en Exchange Online Protection (EOP) que deberían haberles entregado.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c0f95561977c453d7040d84ba0c779c3d33e07f0
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029830"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a>Búsqueda y liberación de mensajes en cuarentena como usuario en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 que tienen buzones de Exchange Online o en las organizaciones con Exchange Online Protection (EOP) independientes sin buzones de Exchange Online, la cuarentena retiene los mensajes que pueden ser peligrosos o no deseados. Para más información, consulte [Cuarentena en EOP](quarantine-email-messages.md).

En tanto que destinatario de un mensaje en cuarentena, lo que puede hacer con el mensaje como usuario no administrador se describe en la tabla siguiente:

<br>

****

|Motivo de la cuarentena:|Ver|Liberar|Eliminar|
|---|:---:|:---:|:---:|
|Masivo|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|Correo no deseado|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|Suplantación de identidad (suplantación de identidad no de alta confianza)|![Marca de verificación](../../media/checkmark.png)||![Marca de verificación](../../media/checkmark.png)|
|

Puede ver y administrar los mensajes en cuarentena en el portal de Microsoft 365 Defender o, si un administrador lo ha configurado, en [notificaciones de correo no deseado para el usuario](use-spam-notifications-to-release-and-report-quarantined-messages.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Para abrir el portal de Microsoft 365 Defender, vaya a <https://security.microsoft.com>. Para abrir directamente la página de cuarentena, vaya a <https://security.microsoft.com/quarantine>.

- Los administradores pueden configurar cuánto tiempo se conservan los mensajes en cuarentena antes de que se eliminen de forma permanente (directivas contra correo electrónico no deseado). Los mensajes que han expirado de la cuarentena no se pueden recuperar. Para más información, consulte [Configurar directivas contra correo electrónico no deseado en EOP](configure-your-spam-filter-policies.md).

- Los administradores también pueden [configurar notificaciones de correo no deseado para el usuario final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) en directivas contra correo no deseado. Los usuarios pueden eliminar mensajes de correo no deseado en cuarentena directamente desde estas notificaciones. Los usuarios pueden revisar mensajes de suplantación de identidad (phishing) en cuarentena (no se trata de mensajes fraudulentos de alta confianza) directamente desde estas notificaciones. Para obtener más información, consulte [Notificaciones de correo no deseado para el usuario final en EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).

- Los mensajes puestos en cuarentena por suplantación de identidad de alta confianza, malware o por reglas de flujo de correo (también conocidas como reglas de transporte) solo están disponibles para los administradores y no son visibles para los usuarios. Para más información, consulte [Administrar mensajes en cuarentena y archivos como administrador en EOP](manage-quarantined-messages-and-files.md).

- Únicamente puede liberar un mensaje e identificarlo como un falso positivo (deseado) una vez.

## <a name="view-your-quarantined-messages"></a>Ver los mensajes en cuarentena

1. En el portal de Microsoft 365 Defender, vaya a **Colaboración y correos electrónicos** \> **Revisar** \> **Cuarentena**.

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
     - **Suplantación de identidad**

   - **Tipo de directiva**: Filtrar mensajes por tipo de directiva:
     - **directiva antimalware**
     - **Directiva de datos adjuntos seguros** (Defender para Office 365)
     - **Política Antiphishing**
     - **Directiva de filtro de contenido alojado** (directiva anti-spam)
     - **Regla de transporte**

     <sup>\*</sup>

   Para borrar el filtro, haga clic en **Borrar**. Para ocultar el control flotante del filtro, haga clic de nuevo en **Filtrar**.

4. Use **Ordenar resultados por**(de forma predeterminada, el botón **Id. de mensaje**) y el valor correspondiente para encontrar mensajes específicos. No se admiten los caracteres comodín. Puede buscar según los siguientes valores:

   - **Id. de mensaje**: El identificador único global del mensaje. Si selecciona un mensaje de la lista, el valor **Id. de mensaje** aparece en el panel flotante **Detalles** que aparece. Los administradores pueden usar [seguimiento de mensajes](message-trace-scc.md) para buscar mensajes y los valores de Id. de mensaje correspondientes.
   - **Dirección de correo electrónico del remitente**: Una única dirección de correo electrónico de remitente.
   - **Nombre de directiva**: Use el nombre de la Directiva completa del mensaje. La búsqueda no distingue entre mayúsculas y minúsculas.
   - **Dirección de correo electrónico del destinatario**: Una única dirección de correo electrónico de destinatario.
   - **Asunto**: Use el asunto completo del mensaje. La búsqueda no distingue entre mayúsculas y minúsculas.

   Cuando haya introducido los criterios de búsqueda, haga clic en ![Botón actualizar](../../media/scc-quarantine-refresh.png) **Actualizar** para filtrar los resultados.

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
- **Motivo de la cuarentena**: Muestra si un mensaje se ha identificado como **Correo no deseado**, **Masivo** o **Suplantación de identidad**.
- **Destinatarios**: Si el mensaje contiene varios destinatarios, deberá hacer clic en **Vista previa del mensaje** o **Ver encabezado del mensaje** para ver la lista completa de destinatarios.
- **Expira**: La fecha/hora en que el mensaje se eliminará automática y permanentemente de la cuarentena.
- **Liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje se ha liberado.
- **Todavía no se ha liberado para**: Todas las direcciones de correo electrónico (si corresponde) para las que el mensaje no se ha liberado aún.

### <a name="take-action-on-quarantined-email"></a>Llevar a cabo una acción en un correo electrónico en cuarentena

Después de seleccionar un mensaje, dispone opciones con respecto a qué hacer con los mensajes en el panel flotante **Detalles**:

- **Liberar mensaje**: En el panel flotante que aparece, elija si desea **Informar de los mensajes a Microsoft para su análisis**. Esta opción está seleccionada de forma predeterminada y comunica a Microsoft el mensaje puesto en cuarentena por error como falso positivo.

  Cuando haya terminado, haga clic en **Liberar mensajes**.

- **Ver encabezado del mensaje**: Seleccione este vínculo para ver el texto del encabezado del mensaje. Copie el texto del encabezado del mensaje en el portapapeles para analizar los campos y valores del encabezado en profundidad y luego elija **Analizador de encabezados de mensaje de Microsoft** para desplazarse hasta el Analizador de conectividad remota (haga clic con el botón derecho y elija **Abrir en una nueva pestaña** si no desea que Microsoft 365 complete esta tarea). Pegue el encabezado del mensaje en la página en la sección del Analizador de encabezados de mensaje y seleccione **Analizar encabezados**:

- **Vista previa del mensaje**: En el panel flotante que aparece, elija una de las siguientes opciones:
  - **Vista de código fuente**: Muestra la versión HTML del cuerpo del mensaje con todos los vínculos desactivados.
  - **Vista de texto**: Muestra el cuerpo del mensaje como texto sin formato.

- **Eliminar de cuarentena**: Después de hacer clic en **Sí** en la advertencia que aparece, el mensaje se elimina inmediatamente.

- **Bloquear remitente**: Agregue el remitente a la lista Remitentes bloqueados del buzón. Para más información, consulte [Bloquear un remitente de correo](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).

Agregue el remitente a la lista de remitentes bloqueados del buzón. Para más información, consulte [Bloquear un remitente de correo](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).

Cuando haya terminado, haga clic en **Cerrar**.

Si no libera o elimina el mensaje, se eliminará cuando expire el período de retención en cuarentena predeterminado.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Realice una acción en varios mensajes de correo electrónico en cuarentena

Al seleccionar varios mensajes en cuarentena de la lista (hasta 100), se mostrará el panel de control flotante **Acciones en masa**, donde puede realizar las acciones siguientes:

- **Liberar mensajes**: Las opciones son las mismas que cuando libera un único mensaje, salvo que no puede seleccionar **Liberar mensajes para destinatarios específicos**; solo puede seleccionar **Liberar mensaje para todos los destinatarios** o **Liberar mensajes para otras personas**.
- **Eliminar mensajes**: Después de hacer clic en **Sí** en la advertencia que aparece, el mensaje se elimina inmediatamente sin enviarse a los destinatarios originales.

Cuando haya terminado, haga clic en **Cerrar**.
