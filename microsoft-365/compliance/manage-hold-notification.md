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
description: Use el flujo de trabajo de comunicaciones Advanced eDiscovery para realizar un seguimiento del estado de las notificaciones de retención legal y, si es necesario, actualizarlas y reenviarlas.
ms.openlocfilehash: 8852bfd1651e1855d276b60ba6fac35c378d4631
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280118"
---
# <a name="manage-hold-notifications"></a>Administrar las notificaciones de retención

Después de iniciar el flujo de trabajo de notificación de retención legal, puede usar el flujo de trabajo de comunicaciones Advanced eDiscovery realizar un seguimiento del estado de las comunicaciones. La pestaña Comunicaciones contiene una lista de todas las notificaciones dentro de su Advanced eDiscovery caso. Puede ver detalles como el número de custodios que se han asignado o han reconocido el aviso.

## <a name="monitor-acknowledgments"></a>Supervisar confirmaciones

Después de seleccionar una comunicación en **la** pestaña Comunicaciones, puede ver una lista de custodios que han reconocido un aviso de retención. 

1. En el centro de cumplimiento, vaya **a eDiscovery > Advanced eDiscovery**.

2. Seleccione un caso y, a continuación, haga clic en la **pestaña** Comunicaciones.

3. Seleccione una comunicación para mostrar la **página desplegable comunicación** custodiada.

En la página desplegable de comunicación se muestra una lista de custodios asociados con la comunicación seleccionada. Esta página también muestra información sobre cuántas confirmaciones se recibieron y cuántas están pendientes. La página también muestra qué custodios han enviado un acuse de recibo de que recibieron la notificación de retención.

## <a name="re-send-a-hold-notice"></a>Volver a enviar un aviso de retención

En ocasiones, los custodios pierden el seguimiento de los mensajes de correo electrónico en su trabajo diario. O para un caso de litigio de larga duración, un custodio puede ponerse en contacto con usted u otros usuarios y solicitar que vuelva a enviar un aviso. A medida que administra el flujo de trabajo de comunicaciones para avisos de retención legal, es posible que deba volver a enviar un aviso para que vuelva a la "parte superior del buzón de un usuario".

Para volver a enviar un aviso de retención a un custodio:

1. En Advanced eDiscovery, seleccione un caso y, a continuación, haga clic en la **pestaña** Comunicaciones.

2. Seleccione una comunicación para mostrar la **página desplegable comunicación** custodiada.

3. Haga **clic en Más > volver a enviar el aviso de retención**.

4. En la **página Re-send hold notice** flyout, seleccione los custodios que desea volver a enviar el aviso y escriba un motivo opcional.

5. Haga **clic en Volver a enviar** para enviar el aviso a los custodios seleccionados.

Si un custodio no ha reconocido la notificación de retención, se reiniciará el flujo de trabajo de aviso y escalación. Si un custodio ha reconocido el aviso de retención, el custodio recibirá una copia del aviso de retención original.

> [!NOTE]
> Solo puede reenviar una notificación de retención legal a los custodios asignados a la comunicación. 

## <a name="update-preservation-requirements"></a>Actualizar requisitos de conservación
  
A medida que avanza el caso, es posible que los custodios deban conservar datos adicionales o inferiores a los que se instruyeron anteriormente. En términos de exhibición de documentos electrónicos, debe volver a emitir el aviso de retención con contenido actualizado.

Para actualizar el contenido del aviso de retención inicial:

1. En Advanced eDiscovery, seleccione un caso y, a continuación, haga clic en la **pestaña** Comunicaciones.

2. Seleccione el aviso de retención que desea actualizar y haga clic **en Editar** en la **página desplegable** Comunicación de custodia.

3. En el **Asistente para editar** comunicación, haga clic en Definir contenido del **portal** en el panel izquierdo del asistente y actualice el contenido del aviso.

4. Haga clic en **Guardar**.

El aviso de re-emisión se enviará a todos los custodios asignados a la notificación de retención legal. Además, si el aviso de aviso o escalación está habilitado, se reiniciarán los flujos de trabajo para esos tipos de avisos.

## <a name="update-legal-hold-notifications-and-settings"></a>Actualizar las notificaciones y la configuración de retención legal

Al actualizar el contenido o la configuración del aviso emisión, versión, reedición, aviso o escalación, estos cambios se aplicarán a todas las comunicaciones futuras generadas por el flujo de trabajo.

## <a name="more-information"></a>Más información

- [Agregar administradores a un caso](add-custodians-to-case.md)

- [Crear un aviso de retención legal](create-hold-notification.md)

- [Confirmar una notificación de retención](acknowledge-hold-notification.md)
