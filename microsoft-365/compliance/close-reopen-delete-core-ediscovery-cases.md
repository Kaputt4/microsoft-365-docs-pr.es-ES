---
title: Cerrar, volver a abrir y eliminar casos principales de exhibición de documentos electrónicos
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
description: En este artículo se describe cómo administrar los casos principales de eDiscovery. Esto incluye cerrar un caso, volver a abrir un caso cerrado y eliminar un caso.
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412799"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a>Cerrar, volver a abrir y eliminar un caso de eDiscovery principal

En este artículo se describe cómo cerrar, volver a abrir y eliminar los casos principales de eDiscovery en Microsoft 365.

## <a name="close-a-case"></a>Cerrar un caso

Cuando se complete el caso legal o la investigación compatible con un caso de exhibición de documentos electrónicos principal, puede cerrar el caso. Esto es lo que sucede al cerrar un caso:
  
- Si el caso contiene ubicaciones de contenido en retención de exhibición de documentos electrónicos, dichas retenciones se desactivarán. Después de desactivar la retención, se aplica un período de gracia de 30 días (denominado retención retrasada) a las ubicaciones de contenido que estaban en espera. Esto ayuda a evitar que el contenido se elimine inmediatamente y proporciona a los administradores la oportunidad de buscar y restaurar contenido antes de que se elimine de forma permanente después de que expire el período de retención de retraso. Para obtener más información, vea [Quitar ubicaciones de contenido de una retención de exhibición de documentos electrónicos.](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)

- Cerrar un caso solo desactiva las retenciones asociadas a ese caso. Si se colocan otras retenciones en una ubicación de contenido (como una retención por juicio, una directiva de retención o una suspensión de otro caso de exhibición de documentos electrónicos principal), dichas retenciones se seguirán conservando.

- El caso aún aparece en la página de exhibición de documentos electrónicos principal en el Centro de cumplimiento de Microsoft 365. Se conservan los detalles, las retenciones, las búsquedas y los miembros de un caso cerrado.

- Puede editar un caso después de cerrarlo. Por ejemplo, puede agregar o quitar miembros, crear búsquedas y exportar resultados de búsqueda. La principal diferencia entre los casos activos y cerrados es que las retenciones de exhibición de documentos electrónicos se apagan cuando se cierra un caso.

Para cerrar un caso:
  
1. En el Centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery** Core para mostrar la lista de casos principales de  >   eDiscovery en su organización.

2. Haga clic en el nombre del caso que desea cerrar.

    Se **muestra la página desplegable** Administrar este caso.

3. En **Administrar estado de caso,** haga clic en Cerrar **caso.**

    Se muestra una advertencia que dice que se desactivarán las retenciones asociadas con el caso.

4. Haga **clic en Sí** para cerrar el caso.

    El estado de la **página de** control desplegable Administrar este caso cambia **de Activo** a **Cierre.**

5. Cierre la **página Administrar este caso.**

6. En la **página eDiscovery principal,** haga clic **en Actualizar** para actualizar el estado del caso cerrado. El proceso de cierre puede tardar hasta 60 minutos en completarse.

    Una vez completado el proceso, el estado del caso cambia a **Cerrado** en la **página de eDiscovery** principal. Vuelva a hacer clic en  el nombre del caso para mostrar la página desplegable Administrar este caso, que contiene información sobre cuándo se cerró el caso y quién lo cerró.

## <a name="reopen-a-closed-case"></a>Volver a abrir un caso cerrado

Al volver a abrir un caso, las retenciones de exhibición de documentos electrónicos que estaban en su lugar cuando se cerró el caso no se restablecerán automáticamente. Una vez que se vuelva a abrir el caso, tendrá que ir a la página **Retenciones** y activar las retenciones anteriores. Para activar una retención, selecciónelo para mostrar la página desplegable y, a continuación, establezca el botón de **alternancia** estado en **Activar**.
  
1. En el Centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery** Core para mostrar la lista de casos principales de  >   eDiscovery en su organización.

2. Haga clic en el nombre del caso que desea volver a abrir.

    Se **muestra la página desplegable** Administrar este caso. 

3. En **Administrar estado de caso,** haga clic en Volver a abrir **caso.**

    Se muestra una advertencia que dice que las retenciones asociadas con el caso cuando se cerró no se activarán automáticamente.

4. Haga **clic en Sí** para volver a abrir el caso.

    El estado de la **página de** control desplegable Administrar este caso se cambia **de Cerrado** a **Activo.**

5. Cierre la **página Administrar este caso.** 

6. En la **página eDiscovery principal,** haga clic **en Actualizar** para actualizar el estado del caso reabrido. El proceso de reabrimiento puede tardar hasta 60 minutos en completarse. 

    Una vez completado el proceso, el estado del caso cambia a **Activo** en la **página de exhibición** de documentos electrónicos principal. 
  
## <a name="delete-a-case"></a>Eliminar un caso

También puede eliminar los casos de eDiscovery principales activos y cerrados. Al eliminar un caso, se eliminan todas las búsquedas y exportaciones del caso y el caso se quita de la lista de casos en la página **eDiscovery** principal del Centro de cumplimiento de Microsoft 365. No puede volver a abrir un caso eliminado.

Para poder eliminar un caso (ya sea activo o cerrado), primero debe eliminar todas las retenciones de *exhibición* de documentos electrónicos asociadas con el caso. Esto incluye la eliminación de retenciones con el estado **Desactivado**. 

Para eliminar una retención de exhibición de documentos electrónicos:

1. Vaya a **la pestaña Retenciones** en caso de que desee eliminar.

2. Haga clic en la retención que desea eliminar.

3. En la página desplegable, haga clic **en Eliminar retención.**

Para eliminar un caso:

1. En el Centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery** Core para mostrar la lista de casos principales de  >   eDiscovery en su organización.

2. Haga clic en el nombre del caso que desea eliminar.

3. En **Administrar estado de caso** en la página desplegable, haga clic en Eliminar **caso.**

Si el caso que intenta eliminar aún contiene retenciones de exhibición de documentos electrónicos, recibirá un mensaje de error. Tendrá que eliminar todas las retenciones asociadas al caso y, a continuación, volver a intentar eliminar el caso.
