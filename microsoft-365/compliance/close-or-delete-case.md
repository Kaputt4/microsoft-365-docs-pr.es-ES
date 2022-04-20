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
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Obtenga información sobre lo que sucede cuando se cierra o elimina una investigación o caso legal compatible con un caso de exhibición de documentos electrónicos (Premium) de Microsoft Purview.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c3ea769fe6c1e01a14e6a552170da8421a03cf07
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64940431"
---
# <a name="close-or-delete-an-ediscovery-premium-case"></a>Cerrar o eliminar un caso de exhibición de documentos electrónicos (Premium)

Cuando se complete el caso legal o la investigación compatible con un caso de exhibición de documentos electrónicos (Premium) de Microsoft Purview, puede cerrar o eliminar un caso. También puede volver a abrir un caso cerrado.

## <a name="close-a-case"></a>Cerrar un caso

Esto es lo que sucede al cerrar un caso de eDiscovery (Premium):

- Si el caso contiene ubicaciones de contenido en espera, esas retenciones se desactivarán. Una vez desactivada la suspensión, se aplica un período de gracia de 30 días (denominado *suspensión de retraso*) a las ubicaciones de contenido que estaban en espera. Esto ayuda a evitar que el contenido se elimine inmediatamente y ofrece a los administradores la oportunidad de buscar o recuperar contenido que se eliminará permanentemente después de que expire el período de retención de retraso. Para obtener más información, vea [Eliminación de ubicaciones de contenido de una suspensión de eDiscovery](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).

- Cerrar un caso solo desactiva las retenciones que están asociadas a ese caso. Si hay otras retenciones en una ubicación de contenido (como una suspensión por juicio, una suspensión de Exhibición de documentos electrónicos de Microsoft Purview (estándar) o una suspensión de un caso de exhibición de documentos electrónicos (Premium) diferente), esas retenciones se mantendrán.

- El caso sigue aparecen en la página eDiscovery del portal de cumplimiento de Microsoft Purview. Se conservan los detalles, las retenciones, las búsquedas y los miembros de un caso cerrado.

- Puede editar un caso después de cerrarlo. Por ejemplo, puede agregar o quitar miembros, crear búsquedas, exportar resultados de búsqueda y preparar los resultados de búsqueda para su análisis en eDiscovery (Premium). La principal diferencia entre los casos activos y cerrados es que las retenciones se desactivarán cuando se cierra un caso.

Para cerrar un caso:

1. En la página **eDiscovery (Premium),** seleccione el caso que desea cerrar.

2. En la pestaña **Configuración**, en **Información del**, haga clic en **Seleccionar**.

   ![Acceda a la página de control flotante de información del caso en un caso de eDiscovery (Premium).](..\media\AeDSelectCaseInformation.png) 

3. En la parte inferior de la página desplegable **Información** del caso, haga clic en **Accionesy**, a continuación, haga clic en **Cerrar caso**.

   El proceso de cierre puede tardar hasta 60 minutos en completarse.

## <a name="reopen-a-closed-case"></a>Volver a abrir un caso cerrado

Al volver a abrir un caso de exhibición de documentos electrónicos (Premium), las retenciones que hubieran estado en su lugar cuando se cerró el caso no se restablecerán automáticamente. Una vez que se vuelva a abrir el caso, tendrá que ir a la pestaña **Retenciones** y activar las retenciones anteriores. Para activar una retención, selecciónela para mostrar la página flotante y luego configure el interruptor de **Estado** en **Activado**.

Para volver a abrir un caso cerrado:

1. En la página **eDiscovery (Premium),** seleccione el caso que desea volver a abrir.

2. En la pestaña **Configuración**, en **Información de caso**, haga clic en **Seleccionar**.

3. En la parte inferior de la página desplegable **Información** del caso, haga clic en **Accionesy**, a continuación, haga clic en **Volver a abrir caso**.

   El proceso de reapertura puede tardar hasta 60 minutos en completarse.

## <a name="delete-a-case"></a>Eliminar un caso

Puede eliminar casos de exhibición de documentos electrónicos activos y cerrados (Premium). Al eliminar un caso, se eliminan todos los componentes asociados al caso, como la lista de administradores, comunicaciones, búsquedas, conjuntos de revisión y trabajo de exportación. El caso se quita de la lista de casos de la página **eDiscovery (Premium)** del portal de cumplimiento de Microsoft Purview. No se puede recuperar ni volver a abrir un caso eliminado.

> [!NOTE]
> En escenarios de desbordamiento de datos, la única manera de quitar elementos de un conjunto de revisión es eliminar el caso de eDiscovery (Premium). Otros métodos de "búsqueda y purga" no quitan elementos de un conjunto de revisión.

Para poder eliminar un caso (ya sea activo o cerrado), primero debe eliminar *todas las* retenciones asociadas al caso. Esto incluye la eliminación de retenciones con el estado **Desactivado**.

Para eliminar las retenciones asociadas a un caso:

1. Vaya a la pestaña **Retenciones** en el caso de exhibición de documentos electrónicos (Premium) que desea eliminar.

2. Haga clic en la suspensión que desea eliminar.

3. En la página de control flotante, haga clic en **Eliminar suspensión**.

Para eliminar un caso:

1. En la página **eDiscovery (Premium),** seleccione el caso que desea eliminar.

2. En la pestaña **Configuración**, en **Información del**, haga clic en **Seleccionar**.

3. En la parte inferior de la página desplegable **Información** del caso, haga clic en **Accionesy**, a continuación, haga clic en **Eliminar caso**.

