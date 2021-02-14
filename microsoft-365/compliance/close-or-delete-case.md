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
description: Obtenga información sobre lo que sucede cuando se cierra o elimina una investigación o un caso legal compatible con un caso de eDiscovery avanzado.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ffdd93351325be0c4b5d6d8cdfb78e55b710c0be
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419066"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>Cerrar o eliminar un caso de eDiscovery avanzado

Cuando se complete el caso legal o la investigación compatible con un caso de eDiscovery avanzado, puede cerrar o eliminar un caso. También puede volver a abrir un caso cerrado.

## <a name="close-a-case"></a>Cerrar un caso

Esto es lo que sucede cuando cierra un caso de eDiscovery avanzado:

- Si el caso contiene alguna ubicación de contenido en espera, dichas retenciones se desactivarán. Después de desactivar la retención, se aplica un período de gracia de 30 días (denominado retención retrasada) a las ubicaciones de contenido que estaban en espera. Esto ayuda a evitar que el contenido se elimine inmediatamente y ofrece a los administradores la oportunidad de buscar o recuperar contenido que se eliminará permanentemente después de que expire el período de retención de retraso. Para obtener más información, vea [Quitar ubicaciones de contenido de una retención de exhibición de documentos electrónicos.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)

- Cerrar un caso solo desactiva las retenciones asociadas a ese caso. Si otras retenciones se encuentran en una ubicación de contenido (como una retención por juicio, una suspensión de eDiscovery principal o una retención de otro caso de eDiscovery avanzado), dichas retenciones se seguirán conservando.

- El caso aún aparece en la página de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365. Se conservan los detalles, las retenciones, las búsquedas y los miembros de un caso cerrado.

- Puede editar un caso después de cerrarlo. Por ejemplo, puede agregar o quitar miembros, crear búsquedas, exportar resultados de búsqueda y preparar los resultados de búsqueda para el análisis en eDiscovery avanzado. La principal diferencia entre los casos activos y cerrados es que las retenciones se apagan cuando se cierra un caso.

Para cerrar un caso:

1. En la **página eDiscovery avanzado,** seleccione el caso que desea cerrar.

2. En la **pestaña Configuración,** en Información **de casos**, haga clic **en Seleccionar**.

3. Haga clic **en Cerrar caso.**

   El proceso de cierre puede tardar hasta 60 minutos en completarse.

## <a name="reopen-a-closed-case"></a>Volver a abrir un caso cerrado

Al volver a abrir un caso de eDiscovery avanzado, las retenciones que estaban en su lugar cuando se cerró el caso no se restablecerán automáticamente. Una vez que se vuelva a abrir el caso, tendrá que ir a la pestaña **Retenciones** y activar las retenciones anteriores. Para activar una retención, selecciónelo para mostrar la página desplegable y, a continuación, establezca el botón de alternancia de **estado** en **Activar**.

Para volver a abrir un caso cerrado:

1. En la **página eDiscovery avanzado,** seleccione el caso que desea volver a abrir.

2. En la **pestaña Configuración,** en Información **de** casos , haga clic **en Seleccionar**.

3. Haga clic **en Volver a abrir caso.**

   El proceso de reabrimiento puede tardar hasta 60 minutos en completarse.

## <a name="delete-a-case"></a>Eliminar un caso

Puede eliminar los casos activos y cerrados de eDiscovery avanzado. Al eliminar un caso, se eliminan todos los componentes asociados con el caso, como la lista de administradores, las comunicaciones, las búsquedas, los conjuntos de revisión y el trabajo de exportación. El caso se quita de la lista de casos de la página **eDiscovery** avanzado en el Centro de cumplimiento de Microsoft 365. No puede recuperar ni volver a abrir un caso eliminado.

> [!NOTE]
> En escenarios de pérdida de datos, la única forma de quitar elementos de un conjunto de revisión es eliminar el caso de eDiscovery avanzado. Otros métodos de "búsqueda y depuración" no quitan elementos de un conjunto de revisión.

Para poder eliminar un caso (ya sea activo o  cerrado), primero debe eliminar todas las retenciones asociadas con el caso. Esto incluye la eliminación de retenciones con el estado **Desactivado**.

Para eliminar retenciones asociadas a un caso:

1. Vaya a **la pestaña Retenciones** en el caso de eDiscovery avanzado que desea eliminar.

2. Haga clic en la retención que desea eliminar.

3. En la página desplegable, haga clic **en Eliminar retención.**

Para eliminar un caso:

1. En la **página eDiscovery avanzado,** seleccione el caso que desea eliminar.

2. En la **pestaña Configuración,** en Información **de casos**, haga clic **en Seleccionar**.

3. Haga clic **en Eliminar caso.**
