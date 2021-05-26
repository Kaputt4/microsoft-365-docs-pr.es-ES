---
title: Cerrar o eliminar un caso
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
description: Obtenga información sobre qué sucede cuando se cierra o elimina una investigación o un caso legal admitido por un Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7b11faa2ccdb44fca916b2f602d5120adadf1739
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657656"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>Cerrar o eliminar un Advanced eDiscovery caso

Cuando se complete el caso legal o la investigación admitida por un Advanced eDiscovery caso, puede cerrar o eliminar un caso. También puede volver a abrir un caso cerrado.

## <a name="close-a-case"></a>Cerrar un caso

Esto es lo que sucede al cerrar un Advanced eDiscovery caso:

- Si el caso contiene ubicaciones de contenido en espera, esas retenciones se desactivarán. Después de desactivar la retención, se aplica un período de gracia de 30 días (denominado retención de *retraso)* a las ubicaciones de contenido que estaban en espera. Esto ayuda a evitar que el contenido se elimine inmediatamente y ofrece a los administradores la oportunidad de buscar o recuperar contenido que se eliminará permanentemente después de que expire el período de retención de retraso. Para obtener más información, vea [Quitar ubicaciones de contenido de una retención de exhibición de documentos electrónicos](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).

- Cerrar un caso solo desactiva las retenciones que están asociadas a ese caso. Si otras retenciones se encuentran en una ubicación de contenido (como una retención por juicio, una retención de exhibición de documentos electrónicos principal o una retención de un caso Advanced eDiscovery diferente) esas retenciones se mantendrán.

- El caso aún se muestra en la página exhibición de documentos electrónicos en el centro de Microsoft 365 cumplimiento. Se conservan los detalles, las suspensiones, las búsquedas y los miembros de un caso cerrado.

- Puede editar un caso después de cerrarlo. Por ejemplo, puede agregar o quitar miembros, crear búsquedas, exportar resultados de búsqueda y preparar resultados de búsqueda para el análisis en Advanced eDiscovery. La principal diferencia entre los casos activos y cerrados es que las retenciones se desactivarán cuando se cierra un caso.

Para cerrar un caso:

1. En la página de **eDiscovery avanzado**, seleccione el caso que desea cerrar.

2. En la pestaña **Configuración**, en **Información del**, haga clic en **Seleccionar**.

3. En la parte inferior de la **página desplegable Información** de casos, haga clic en (**...**) **Más opciones** y, a continuación, haga clic **en Cerrar caso**.

   ![Opción en el menú Más opciones para cerrar un Advanced eDiscovery caso](..\Media\CloseAdvancedeDiscoveryCase.png)

   El proceso de cierre puede tardar hasta 60 minutos en completarse.

## <a name="reopen-a-closed-case"></a>Volver a abrir un caso cerrado

Al volver a abrir un Advanced eDiscovery, las retenciones que estaban en su lugar cuando se cerró el caso no se restablecerán automáticamente. Una vez que se vuelva a abrir el caso, tendrás que ir a la pestaña **Retenciones** y activar las retenciones anteriores. Para activar una retención, selecciónela para mostrar la página flotante y luego configure el interruptor de **Estado** en **Activado**.

Para volver a abrir un caso cerrado:

1. En la página de **eDiscovery avanzado**, seleccione el caso que quiere volver a abrir.

2. En la pestaña **Configuración**, en **Información del**, haga clic en **Seleccionar**.

3. En la parte inferior de la **página desplegable Información** de casos, haga clic en (**...**) **Más opciones y,** a continuación, haga clic **en Abrir caso**.

   ![Opción en el menú Más opciones para volver a abrir un Advanced eDiscovery caso](..\Media\ReopenAdvancedeDiscoveryCase.png)

   El proceso de reapertura puede tardar hasta 60 minutos en completarse.

## <a name="delete-a-case"></a>Eliminar un caso

Puede eliminar los casos activos y Advanced eDiscovery cerrados. Al eliminar un caso, se eliminan todos los componentes asociados al caso, como la lista de administradores, comunicaciones, búsquedas, conjuntos de revisión y trabajo de exportación. El caso se quita de la lista de casos de la **Advanced eDiscovery** en el centro de Microsoft 365 cumplimiento. No puede recuperar ni volver a abrir un caso eliminado.

> [!NOTE]
> En escenarios de derrame de datos, la única forma de quitar elementos de un conjunto de revisión es eliminar el Advanced eDiscovery caso. Otros métodos de "búsqueda y purga" no quitan elementos de un conjunto de revisión.

Para poder eliminar un caso (ya sea activo o  cerrado), primero debe eliminar todas las retenciones asociadas con el caso. Esto incluye la eliminación de retenciones con el estado **Off**.

Para eliminar las retenciones asociadas a un caso:

1. Vaya a **la pestaña Retenciones** en el Advanced eDiscovery caso que desee eliminar.

2. Haga clic en la retención que desea eliminar.

3. En la página desplegable, haga clic **en Eliminar retención**.

Para eliminar un caso:

1. En la página de **eDiscovery avanzado**, seleccione el caso que desea eliminar.

2. En la pestaña **Configuración**, en **Información del**, haga clic en **Seleccionar**.

3. En la parte inferior de la **página desplegable Información** de casos, haga clic en (**...**) **Más opciones y,** a continuación, haga clic **en Eliminar caso**.

   ![Opción en el menú Más opciones para eliminar un Advanced eDiscovery caso](..\Media\DeleteAdvancedeDiscoveryCase.png)
