---
title: Cerrar, volver a abrir y eliminar casos principales de eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: En este artículo se describe cómo administrar casos básicos de eDiscovery. Esto incluye cerrar un caso, volver a abrir un caso cerrado y eliminar un caso.
ms.openlocfilehash: 45282486c2c3b1d00b99a1cda5968b3bb042f6c2
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208422"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a>Cerrar, volver a abrir y eliminar un caso de exhibición de documentos electrónicos principal

En este artículo se describe cómo cerrar, volver a abrir y eliminar los casos de eDiscovery principales en Microsoft 365.

## <a name="close-a-case"></a>Cerrar un caso

Cuando se completa el caso legal o la investigación admitidos por un caso de exhibición de documentos electrónicos principal, puede cerrar el caso. Esto es lo que sucede cuando se cierra un caso:
  
- Si el caso contiene alguna ubicación de contenido en la suspensión de exhibición de documentos electrónicos, dichas suspensiones se desactivarán. Esto puede dar lugar a que el usuario o un proceso automatizado eliminen o purguen permanentemente el contenido, como una directiva de eliminación.

- Si se cierra un caso, sólo se desactivan las suspensiones asociadas a ese caso. Si se colocan otras suspensiones en una ubicación de contenido (como una retención por juicio, una directiva de retención o una retención de un caso de exhibición de documentos electrónicos principal diferente), estas se conservarán.

- El caso todavía aparece en la Página principal de eDiscovery del centro de cumplimiento de Microsoft 365. Se conservan los detalles, las suspensiones, las búsquedas y los miembros de un caso cerrado.

- Puede editar un caso después de cerrarlo. Por ejemplo, puede Agregar o quitar miembros, crear búsquedas y exportar los resultados de la búsqueda. La principal diferencia entre los casos activos y cerrados es que las suspensiones de eDiscovery se desactivan cuando se cierra un caso.

Para cerrar un caso:
  
1. En el centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery**  >  **Core** para mostrar la lista de casos de eDiscovery principales en su organización.

2. Haga clic en el nombre del caso que desea cerrar.

    Se muestra la página flotante **administrar este caso** .

3. En **administrar estado de caso**, haga clic en **cerrar caso**.

    Se muestra una advertencia que indica que las suspensiones asociadas con el caso se desactivarán.

4. Haga clic en **sí** para cerrar el caso.

    El estado de la página desplegable **administrar este caso** se cambia de **activo** a **cierre**.

5. Cierre la página **administrar este caso** .

6. En la página **principal de eDiscovery** , haga clic en **Actualizar** para actualizar el estado del caso cerrado. El proceso de cierre puede tardar hasta 60 minutos en completarse.

    Una vez finalizado el proceso, el estado del caso cambia a **cerrado** en la página **principal de eDiscovery** . Vuelva a hacer clic en el nombre del caso para mostrar la página flotante **administrar este caso** , que contiene información sobre cuándo se cerró el caso y quién lo cerró.

## <a name="reopen-a-closed-case"></a>Volver a abrir un caso cerrado

Cuando vuelva a abrir un caso, las suspensiones de exhibición de documentos electrónicos que estuvieran en su ubicación cuando se cerró el caso no se restituyerán automáticamente. Después de volver a abrir el caso, tendrá que ir a la página **suspensiones** y activar las suspensiones anteriores. Para activar una retención, selecciónela para mostrar la página de flotante y, a continuación, establezca el **Estado** en activar como **activado**.
  
1. En el centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery**  >  **Core** para mostrar la lista de casos de eDiscovery principales en su organización.

2. Haga clic en el nombre del caso que desea volver a abrir.

    Se muestra la página flotante **administrar este caso** . 

3. En **administrar estado de caso**, haga clic en **volver a abrir el caso**.

    Se muestra una advertencia que indica que las suspensiones asociadas con el caso cuando se cerró no se activarán automáticamente.

4. Haga clic en **sí** para volver a abrir el caso.

    El estado de la página desplegable **administrar este caso** se ha cambiado de **cerrado** a **activo**.

5. Cierre la página **administrar este caso** . 

6. En la página **principal de eDiscovery** , haga clic en **Actualizar** para actualizar el estado del caso reabierto. El proceso de reapertura puede tardar hasta 60 minutos en completarse. 

    Una vez finalizado el proceso, el estado del caso cambia a **activo** en la página **principal de eDiscovery** . 
  
## <a name="delete-a-case"></a>Eliminar un caso

También puede eliminar casos de exhibición de documentos electrónicos principales activos y cerrados. Al eliminar un caso, se eliminan todas las búsquedas y exportaciones en el caso y se elimina el caso de la lista de casos de la página **principal de eDiscovery** en el centro de cumplimiento de Microsoft 365. No se puede volver a abrir un caso eliminado.

Antes de que pueda eliminar un caso (ya sea activo o cerrado), primero debe eliminar *todas* las suspensiones de eDiscovery asociadas con el caso. Esto incluye la eliminación de suspensiones con el estado **desactivado**. 

Para eliminar una suspensión de exhibición de documentos electrónicos:

1. Vaya a la pestaña **suspensiones** en el caso de que quiera eliminar.

2. Haga clic en la suspensión que desee eliminar.

3. En la página flotante, haga clic en **eliminar suspensión**.

Para eliminar un caso:

1. En el centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery**  >  **Core** para mostrar la lista de casos de eDiscovery principales en su organización.

2. Haga clic en el nombre del caso que desea eliminar.

3. En **administrar estado de caso** en la página flotante, haga clic en **eliminar caso**.

Si el caso que está intentando eliminar todavía contiene suspensiones de eDiscovery, recibirá un mensaje de error. Tendrá que eliminar todas las suspensiones asociadas con el caso y, a continuación, volver a intentar eliminar el caso.
