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
description: Obtenga información sobre qué ocurre cuando se cierra o se elimina una investigación o un caso legal admitido por un caso avanzado de eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e64f5cc0483129396a28cbf657778001e5d372a7
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292416"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>Cerrar o eliminar un caso de exhibición avanzada de documentos electrónicos

Cuando se completa el caso legal o la investigación admitidos por un caso de exhibición avanzada de documentos electrónicos, puede cerrar o eliminar un caso. También puede volver a abrir un caso cerrado.

## <a name="close-a-case"></a>Cerrar un caso

Esto es lo que sucede cuando cierra un caso de exhibición avanzada de documentos electrónicos:

- Si el caso contiene ubicaciones de contenido en suspensión, dichas suspensiones se desactivarán. Esto puede dar lugar a que el usuario o un proceso automatizado eliminen o purguen permanentemente el contenido, como una directiva de eliminación.

- Si se cierra un caso, sólo se desactivan las suspensiones asociadas a ese caso. Si otras retenciones se colocan en una ubicación de contenido (como una retención por juicio, una suspensión de exhibición de documentos electrónicos principal o una retención de un caso de eDiscovery avanzado diferente), estas se conservarán.

- El caso sigue apareciendo en la página de exhibición de documentos electrónicos del centro de cumplimiento de Microsoft 365. Se conservan los detalles, las suspensiones, las búsquedas y los miembros de un caso cerrado.

- Puede editar un caso después de cerrarlo. Por ejemplo, puede Agregar o quitar miembros, crear búsquedas, exportar los resultados de la búsqueda y preparar los resultados de la búsqueda para analizarlos en la exhibición avanzada de documentos electrónicos. La principal diferencia entre los casos activos y cerrados es que las suspensiones se desactivan cuando se cierra un caso.

Para cerrar un caso:

1. En la página **exhibición avanzada** de documentos electrónicos, seleccione el caso que quiera cerrar.

2. En la pestaña **configuración** , en **información de casos**, haga clic en **seleccionar**.

3. Haga clic en **cerrar caso**.

   El proceso de cierre puede tardar hasta 60 minutos en completarse.

## <a name="reopen-a-closed-case"></a>Volver a abrir un caso cerrado

Cuando vuelve a abrir un caso de exhibición avanzada de documentos electrónicos, las suspensiones que estuvieran en su ubicación cuando se cerró el caso no se restituyerán automáticamente. Después de volver a abrir el caso, tendrá que ir a la pestaña **suspensiones** y activar las suspensiones anteriores. Para activar una retención, selecciónela para mostrar la página de flotante y, a continuación, establezca el **Estado** en activar como **activado**.

Para volver a abrir un caso cerrado:

1. En la página **exhibición avanzada** de documentos electrónicos, seleccione el caso que quiera eliminar.

2. En la pestaña **configuración** , en **información de casos**, haga clic en **seleccionar**.

3. Haga clic en **volver a abrir el caso**.

   El proceso de reapertura puede tardar hasta 60 minutos en completarse.

## <a name="delete-a-case"></a>Eliminar un caso

Puede eliminar tanto los casos de eDiscovery avanzado activos como los cerrados. Al eliminar un caso, se eliminan todos los componentes asociados con el caso, como la lista de custodios, las comunicaciones, las búsquedas, los conjuntos de revisión y el trabajo de exportación. El caso se elimina de la lista de casos de la página **exhibición avanzada** de documentos electrónicos en el centro de cumplimiento de Microsoft 365. No se puede recuperar ni volver a abrir un caso eliminado.

> [!NOTE]
> En los escenarios de derrames de datos, la única forma de quitar elementos de un conjunto de revisiones es eliminar el caso de eDiscovery avanzado. Otros métodos de "búsqueda y depuración" no quitan elementos de un conjunto de revisión.

Antes de que pueda eliminar un caso (ya sea activo o cerrado), primero debe eliminar *todas las* suspensiones asociadas con el caso. Esto incluye la eliminación de suspensiones con el estado **desactivado**.

Para eliminar suspensiones asociadas a un caso:

1. Vaya a la pestaña **suspensiones** en el caso de eDiscovery avanzado que desee eliminar.

2. Haga clic en la suspensión que desee eliminar.

3. En la página flotante, haga clic en **eliminar suspensión**.

Para eliminar un caso:

1. En la página **exhibición avanzada** de documentos electrónicos, seleccione el caso que quiera eliminar.

2. En la pestaña **configuración** , en **información de casos**, haga clic en **seleccionar**.

3. Haga clic en **eliminar caso**.
