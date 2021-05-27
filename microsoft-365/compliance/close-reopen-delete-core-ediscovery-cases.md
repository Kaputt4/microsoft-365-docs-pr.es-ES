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
description: En este artículo se describe cómo administrar los casos principales de exhibición de documentos electrónicos. Esto incluye cerrar un caso, volver a abrir un caso cerrado y eliminar un caso.
ms.openlocfilehash: d729c91d4e81ad12d0b4b16574aa4edad8e239a3
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684104"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a>Cerrar, volver a abrir y eliminar un caso de exhibición de documentos electrónicos principal

En este artículo se describe cómo cerrar, volver a abrir y eliminar los casos principales de exhibición de documentos electrónicos en Microsoft 365.

## <a name="close-a-case"></a>Cerrar un caso

Cuando se complete el caso legal o la investigación admitida por un caso de exhibición de documentos electrónicos principales, puede cerrar el caso. Esto es lo que sucede al cerrar un caso:
  
- Si el caso contiene alguna retención de exhibición de documentos electrónicos, se desactivarán. Después de desactivar la retención, se aplica un período de gracia de 30 días (denominado retención de *retraso)* a las ubicaciones de contenido que estaban en espera. Esto ayuda a evitar que el contenido se elimine inmediatamente y proporciona a los administradores la oportunidad de buscar y restaurar contenido antes de que pueda eliminarse permanentemente después de que expire el período de retención de retraso. Para obtener más información, vea [Quitar ubicaciones de contenido de una retención de exhibición de documentos electrónicos](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).

- Cerrar un caso solo desactiva las retenciones que están asociadas a ese caso. Si otras retenciones se colocan en una ubicación de contenido (como una retención por juicio, una directiva de retención o una retención de un caso de exhibición de documentos electrónicos principal diferente) esas retenciones se mantendrán.

- El caso sigue en la lista en la página eDiscovery principal del centro de Microsoft 365 cumplimiento. Se conservan los detalles, las suspensiones, las búsquedas y los miembros de un caso cerrado.

- Puede editar un caso después de cerrarlo. Por ejemplo, puede agregar o quitar miembros, crear búsquedas y exportar resultados de búsqueda. La diferencia principal entre los casos activos y cerrados es que las retenciones de exhibición de documentos electrónicos se apagan cuando se cierra un caso.

Para cerrar un caso:
  
1. En el centro Microsoft 365 cumplimiento, haga clic en **eDiscovery** Core para mostrar la lista de casos principales de exhibición de documentos electrónicos  >   en su organización.

2. Haga clic en el nombre del caso que desea cerrar.

   ![Cerrar caso en la página principal del caso](../media/eDiscoveryCaseHomePage.png)

3. En la página principal, en **Estado**, haga clic **en Cerrar caso**.

    Se muestra una advertencia que dice que las retenciones asociadas con el caso se desactivarán.

4. Haga **clic en Sí** para cerrar el caso.

    El estado de la página principal del caso cambia **de Activo** a **Cierre**.

5. En la **página Exhibición de documentos electrónicos principal,** haga clic **en Actualizar** para actualizar el estado del caso cerrado. El proceso de cierre puede tardar hasta 60 minutos en completarse.

    Una vez completado el proceso, el estado del caso cambia a **Cerrado** en la **página eDiscovery** principal.

## <a name="reopen-a-closed-case"></a>Volver a abrir un caso cerrado

Al volver a abrir un caso, las retenciones de exhibición de documentos electrónicos que estaban en su lugar cuando se cerró el caso no se restablecerán automáticamente. Una vez que se vuelva a abrir el caso, tendrás que ir a la página **Retenciones** y activar las retenciones anteriores. Para activar una retención, selecciónela para mostrar la página flotante y luego configure el interruptor de **Estado** en **Activado**.
  
1. En el centro Microsoft 365 cumplimiento, haga clic en **eDiscovery** Core para mostrar la lista de casos principales de exhibición de documentos electrónicos  >   en su organización.

2. Haga clic en el nombre del caso que desea volver a abrir.

   ![Volver a abrir un caso cerrado](../media/eDiscoveryCaseHomePageReopen.png)

3. En la página principal, en **Estado,** haga clic **en Abrir caso**.

    Se muestra una advertencia que dice que las retenciones asociadas con el caso cuando se cerró no se activarán automáticamente.

4. Haga **clic en Sí** para volver a abrir el caso.

    El estado de la página principal del caso se cambia de **Cerrado** a **Activo.**

5. En la **página Exhibición de documentos electrónicos principal,** haga clic **en Actualizar** para actualizar el estado del caso reabrido. El proceso de reapertura puede tardar hasta 60 minutos en completarse. 

    Una vez completado el proceso, el estado del caso cambia a **Activo** en la **página eDiscovery** principal.

6. (Opcional) Para activar las retenciones asociadas con  el caso reabierto, vaya a la  pestaña Retenciones, seleccione una retención y, a continuación, active la casilla en Estado en la página de control desplegable de retención.
  
## <a name="delete-a-case"></a>Eliminar un caso

También puede eliminar los casos de exhibición de documentos electrónicos principales activos y cerrados. Al eliminar un caso, se eliminan todas las búsquedas y exportaciones del caso  y el caso se quita de la lista de casos de la página Exhibición de documentos electrónicos principal del centro de cumplimiento de Microsoft 365. No puede volver a abrir un caso eliminado.

Para poder eliminar un caso (ya sea activo o cerrado), primero debe eliminar todas las retenciones de *exhibición* de documentos electrónicos asociadas con el caso. Esto incluye la eliminación de retenciones con el estado **Off**. 

Para eliminar una retención de exhibición de documentos electrónicos:

1. Vaya a la **pestaña Retenciones** en el caso de que desee eliminar.

2. Seleccione la retención que desea eliminar.

3. En la página desplegable, haga clic en **Eliminar**.

      ![Eliminar una retención de exhibición de documentos electrónicos](../media/DeleteeDiscoveryHold.png)

Para eliminar un caso:

1. En el centro Microsoft 365 cumplimiento, haga clic en **eDiscovery** Core para mostrar la lista de casos principales de exhibición de documentos electrónicos  >   en su organización.

2. Haga clic en el nombre del caso que desea eliminar.

3. En la página principal del caso, en **Estado**, haga clic **en Eliminar caso**.

      ![Eliminar un caso](../media/eDiscoveryCaseHomePageDelete.png)

Si el caso que intenta eliminar aún contiene retenciones de exhibición de documentos electrónicos, recibirá un mensaje de error. Tendrás que eliminar todas las retenciones asociadas con el caso e intentar de nuevo eliminar el caso.
