---
title: Administrar las notificaciones de retención
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use el flujo de trabajo de comunicaciones en eDiscovery (Premium) para realizar un seguimiento del estado de las notificaciones de suspensión legal y, si es necesario, actualizarlas y reenviarlas.
ms.openlocfilehash: 161628061d27c17e9e606cb7f88fbbe52d22be8f
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66632253"
---
# <a name="manage-hold-notifications"></a>Administrar las notificaciones de retención

Después de iniciar el flujo de trabajo de notificación de suspensión legal, puede usar el flujo de trabajo de comunicaciones en Microsoft Purview eDiscovery (Premium) para realizar un seguimiento del estado de las comunicaciones. La pestaña Comunicaciones contiene una lista de todas las notificaciones dentro del caso de eDiscovery (Premium). Puede ver detalles como el número de custodios que se han asignado o que han confirmado el aviso.

## <a name="monitor-acknowledgments"></a>Supervisión de confirmaciones

Después de seleccionar una comunicación en la pestaña **Comunicaciones** , puede ver una lista de custodios que han confirmado un aviso de suspensión. 

1. En el centro de cumplimiento, vaya a **eDiscovery > eDiscovery (Premium).**

2. Seleccione un caso y, a continuación, haga clic en la pestaña **Comunicaciones** .

3. Seleccione una comunicación para mostrar la página desplegable **Comunicación del custodio** .

En la página de control flotante de comunicación se muestra una lista de custodios asociados a la comunicación seleccionada. En esta página también se muestran las conclusiones y el número de confirmaciones recibidas y cuántas pendientes. En la página también se muestra qué custodios han enviado una confirmación de que han recibido la notificación de suspensión.

## <a name="re-send-a-hold-notice"></a>Volver a enviar un aviso de suspensión

En ocasiones, los custodios pierden el seguimiento de los mensajes de correo electrónico en su trabajo diario. O bien, para un caso de litigio de larga duración, un custodio puede ponerse en contacto con usted u otros usuarios y solicitar que vuelva a enviar un aviso. A medida que administra el flujo de trabajo de comunicaciones para los avisos de suspensión legal, es posible que tenga que volver a enviar un aviso para devolverlo a la "parte superior del buzón de un usuario".

Para volver a enviar un aviso de suspensión a un custodio:

1. En eDiscovery (Premium), seleccione un caso y, a continuación, haga clic en la pestaña **Comunicaciones** .

2. Seleccione una comunicación para mostrar la página desplegable **Comunicación del custodio** .

3. Haga clic en **Más > Volver a enviar el aviso de retención**.

4. En la página flotante **Volver a enviar el aviso de suspensión** , seleccione los custodios a los que desea volver a enviar el aviso y escriba un motivo opcional.

5. Haga clic en **Volver a enviar** para enviar el aviso a los custodios seleccionados.

Si un custodio no ha confirmado la notificación de suspensión, se reinicia el flujo de trabajo de recordatorio y escalación. Si un custodio ha reconocido el aviso de suspensión, el custodio recibirá una copia del aviso de suspensión original.

> [!NOTE]
> Solo puede reenviar una notificación de suspensión legal a los custodios asignados a la comunicación. 

## <a name="update-preservation-requirements"></a>Actualizar los requisitos de conservación
  
A medida que avanza el caso, es posible que los custodios deban conservar datos adicionales o menos de los indicados anteriormente. En términos de eDiscovery, debe volver a emitir el aviso de suspensión con contenido actualizado.

Para actualizar el contenido del aviso de suspensión inicial:

1. En eDiscovery (Premium), seleccione un caso y, a continuación, haga clic en la pestaña **Comunicaciones** .

2. Seleccione el aviso de suspensión que desea actualizar y haga clic en **Editar** en la página desplegable **Comunicación del custodio** .

3. En el Asistente para **editar comunicaciones** , haga clic en **Definir contenido del portal** en el panel izquierdo del asistente y actualice el contenido del aviso.

4. Haga clic en **Guardar**.

El aviso de re-emisión se enviará a todos los custodios asignados a la notificación de suspensión legal. Además, si el aviso de recordatorio o escalación está habilitado, se reiniciarán los flujos de trabajo de esos tipos de avisos.

## <a name="update-legal-hold-notifications-and-settings"></a>Actualización de las notificaciones y la configuración de suspensión legal

Al actualizar el contenido o la configuración del aviso de emisión, versión, reedición, recordatorio o escalación, estos cambios se aplicarán a todas las comunicaciones futuras generadas por el flujo de trabajo.

## <a name="more-information"></a>Más información

- [Agregar administradores a un caso](add-custodians-to-case.md)

- [Creación de un aviso de suspensión legal](create-hold-notification.md)

- [Confirmar una notificación de retención](acknowledge-hold-notification.md)
