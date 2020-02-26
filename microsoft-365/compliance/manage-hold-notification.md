---
title: Administrar las notificaciones de retención
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use el flujo de trabajo de comunicaciones en la exhibición avanzada de documentos electrónicos para realizar un seguimiento del estado de las notificaciones de retención legal y, si es necesario, actualizarlos y volver a enviarlos.
ms.openlocfilehash: 8852bfd1651e1855d276b60ba6fac35c378d4631
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280118"
---
# <a name="manage-hold-notifications"></a>Administrar las notificaciones de retención

Una vez que haya iniciado el flujo de trabajo de la notificación de retención legal, puede usar el flujo de trabajo de comunicaciones en eDiscovery avanzado para realizar un seguimiento del estado de las comunicaciones. La pestaña comunicaciones contiene una lista de todas las notificaciones en el caso de eDiscovery avanzado. Puede ver detalles como el número de custodios que se han asignado o que han confirmado el aviso.

## <a name="monitor-acknowledgments"></a>Comprobar confirmaciones

Después de seleccionar una comunicación en la pestaña **comunicaciones** , puede ver una lista de custodios que han confirmado una notificación de retención. 

1. En el centro de cumplimiento, vaya a **ediscovery > Advanced eDiscovery**.

2. Seleccione un caso y, a continuación, haga clic en la pestaña **comunicaciones** .

3. Seleccione una comunicación para mostrar la página flotante de **comunicación de custodios** .

En la página flotante de comunicación se muestra una lista de custodios asociados a la comunicación seleccionada. Esta página también muestra información y el número de reconocimientos que se han recibido y cuántos están pendientes. La página también muestra qué administradores han enviado una confirmación de que recibieron la notificación de retención.

## <a name="re-send-a-hold-notice"></a>Volver a enviar un aviso de suspensión

En ocasiones, los custodios pierden el seguimiento de los mensajes de correo electrónico en su trabajo cotidiano. Para un caso de litigio de ejecución prolongada, un custodio puede ponerse en contacto con usted o con otros usuarios y solicitarle que vuelva a enviar un aviso. Mientras administra el flujo de trabajo de comunicaciones para avisos de suspensión legal, es posible que deba volver a enviar un aviso para volver a la "parte superior del buzón de un usuario".

Para volver a enviar un aviso de suspensión a un custodio:

1. En eDiscovery avanzado, seleccione un caso y, a continuación, haga clic en la pestaña **comunicaciones** .

2. Seleccione una comunicación para mostrar la página flotante de **comunicación de custodios** .

3. Haga clic en **más > aviso de reenvío de retención**.

4. En la página desplegable **reenviar notificación de reenvío** , seleccione los custodios que desea que vuelva a enviar el aviso y escriba una razón opcional.

5. Haga clic en **volver a enviar** para enviar el aviso a los custodios seleccionados.

Si un custodio no ha reconocido la notificación de retención, se reiniciará el flujo de trabajo de Reminder y remisión. Si un custodio ha reconocido la notificación de retención, el custodio recibirá una copia del aviso de suspensión original.

> [!NOTE]
> Solo puede reenviar una notificación de suspensión legal a los custodios asignados a la comunicación. 

## <a name="update-preservation-requirements"></a>Requisitos de conservación de la actualización
  
A medida que avanza el caso, es posible que se necesiten custodios para conservar más o menos datos de los que se indicó anteriormente. En términos de exhibición de documentos electrónicos, debe volver a emitir el aviso de suspensión con contenido actualizado.

Para actualizar el contenido del aviso de suspensión inicial:

1. En eDiscovery avanzado, seleccione un caso y, a continuación, haga clic en la pestaña **comunicaciones** .

2. Seleccione el aviso de retención que quiera actualizar y haga clic en **Editar** en la página flotante de **comunicación de custodios** .

3. En el asistente **Editar comunicación** , haga clic en **definir contenido del portal** en el panel izquierdo del asistente y actualice el contenido del aviso.

4. Haga clic en **Guardar **.

El aviso de reemisión se enviará a todos los custodios asignados a la notificación de retención legal. Además, si el aviso de remisión o remisión está habilitado, se reiniciarán los flujos de trabajo de esos tipos de notificación.

## <a name="update-legal-hold-notifications-and-settings"></a>Actualizar la configuración y las notificaciones de retención legal

Cuando se actualiza el contenido o la configuración del aviso de emisión, publicación, reemisión, aviso o escalado, estos cambios se aplican a todas las comunicaciones futuras generadas por el flujo de trabajo.

## <a name="more-information"></a>Más información

- [Agregar administradores a un caso](add-custodians-to-case.md)

- [Crear un aviso de suspensión legal](create-hold-notification.md)

- [Confirmar una notificación de retención](acknowledge-hold-notification.md)
