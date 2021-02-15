---
title: Administrar administradores en un caso de eDiscovery avanzado
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
description: Obtenga información sobre cómo ver detalles, editar y editar en masa la lista de administradores en un caso de eDiscovery avanzado.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739873"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a>Administrar administradores en un caso de eDiscovery avanzado

La página Administradores  de la pestaña Orígenes en un caso de eDiscovery avanzado contiene una lista de todos los administradores que se han agregado al caso. Después de agregar administradores a un caso, los detalles sobre cada administrador se recopilan automáticamente desde Azure Active Directory y se pueden ver en eDiscovery avanzado.

![Administrar administradores](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a>Ver detalles del administrador

Para ver los detalles sobre un administrador, haga clic en el administrador de la lista en la **pestaña Administradores.** Se muestra una página desplegable que contiene la siguiente información sobre el administrador:

- Información de contacto

  - **Nombre para** mostrar: nombre que se muestra en la libreta de direcciones del administrador. Suele ser la combinación del nombre del administrador, la inicial del segundo nombre y los apellidos.
  
   - **Correo/SMTP:** la dirección SMTP principal del administrador, por ejemplo, brianj@contoso.onmicrosoft.com. También se muestra el nombre principal de usuario (UPN) del administrador.

  - **Título:** puesto del administrador.

  - **Departamento:** nombre del departamento en el que trabaja el administrador.

  - **Administrador:** administrador del administrador. El administrador designado recibirá cualquier comunicación de escalamiento para este administrador.
  
- Información de ubicación

  - **Ciudad:** la ciudad en la que se encuentra el administrador.

  - **Estado:** el estado o la provincia en la dirección del administrador.

  - **País o región:** país o región donde se encuentra el administrador.

  - **Office:** la ubicación de la oficina en el lugar de trabajo del administrador.

- Información de casos

  - **Estado de retención:** indica si el administrador se ha puesto en retención. 

  - **Estado de** comunicación: indica si se ha emitido un aviso de retención al administrador. Si se ha emitido un aviso al administrador, este valor de esta propiedad **se publica.** Si no se ha emitido un aviso al administrador, el estado es **No publicado.** 

  - **Estado:** el estado del administrador dentro del caso. Un estado **activo** indica que el administrador forma parte del caso. Si un administrador se libera de un caso, el estado cambia a **Liberado.** 

- Orígenes de datos e información de indización

    - **Orígenes de** datos: muestra el recuento y el tipo de orígenes de datos (buzones, sitios y Teams) que están asociados con el administrador y forman parte del caso.

    - **Hora de actualización del índice:** indica la hora y la fecha de la última vez que se desencadenó el trabajo de indización avanzado. Esta propiedad también indicará cuándo está en curso el proceso de indización avanzado.


## <a name="edit-a-custodian"></a>Editar un administrador

A medida que su caso avanza, puede descubrir que puede haber orígenes de datos adicionales relevantes para un administrador específico & su caso. En otros escenarios, es posible que desee quitar determinados orígenes de datos que se han revisado y que se consideran no relevantes.

Para actualizar los orígenes de datos asociados con un administrador:

1. Vaya a  **eDiscovery > eDiscovery avanzado** y abra el caso.
  
2. Haga clic en **la pestaña** Orígenes.
  
3. En la **página Administradores,** seleccione un administrador de la lista y haga clic **en Editar** en la página desplegable.

    ![Editar orígenes de datos](../media/EditCustodianDataSource.PNG)
  
4. Haga **clic en la pestaña Elegir** orígenes de datos para cambiar la configuración del buzón de Exchange del administrador y la cuenta de OneDrive, haga clic en Elegir orígenes de **datos.**
  
5. Haga clic **en la pestaña** Seleccionar orígenes de datos adicionales para agregar o quitar buzones de Teams, SharePoint o Exchange asociados con el administrador. 

    Para obtener más información acerca de los orígenes de datos asociados con un administrador, vea [Agregar administradores a un caso.](add-custodians-to-case.md) 
  
6. Haga **clic en Colocar retenciones de** administrador para habilitar o deshabilitar la retención del administrador.

## <a name="re-index-custodian-data"></a>Volver a indizar datos de administrador

En la mayoría de los flujos de trabajo de exhibición de documentos electrónicos para investigaciones legales, se busca en un subconjunto de los datos de un administrador después de que el administrador se agrega a un caso legal. Debido a tamaños de archivo muy grandes o a posibles daños en los datos, algunos elementos de los orígenes de datos asociados con un administrador se pueden indizar parcialmente. Con la [capacidad de indización](indexing-custodian-data.md) avanzada en la exhibición avanzada de documentos electrónicos, la mayoría de los elementos parcialmente indizados se pueden corregir automáticamente mediante la indización de estos elementos a petición.

Cuando se agrega un administrador a un caso, los datos ubicados en los orígenes de datos asociados con el administrador se indizan automáticamente (por el proceso de indización avanzado). Esto significa que puede dejar los datos en su lugar en lugar de tener que descargarlos y corregirlos y, a continuación, buscarlos sin conexión). Sin embargo, durante el ciclo de vida de un caso legal, los nuevos orígenes de datos podrían asociarse con un administrador. En este caso, puede volver a indizar los datos del administrador si vuelve a ejecutar el proceso de indización avanzado para corregir los elementos parcialmente indizados y actualizar el índice de los datos del administrador.

Para desencadenar el proceso de re indización para que se direccione a elementos parcialmente indizados:

1. Vaya a  **eDiscovery > eDiscovery avanzado** y abra el caso.

2. Haga clic en **la pestaña** Orígenes.

3. En la **página Administradores,** seleccione un administrador cuyos datos deben volver a indexarse.

4. En la página desplegable, haga clic **en Actualizar índice**.

   Se muestra un cuadro de diálogo que dice que se ha creado el trabajo de índice.

Volver a indizar los datos de administrador es un proceso de larga duración; el trabajo correspondiente que se crea se denomina **Volver a indizar datos de administrador.** Puede realizar un seguimiento  del progreso en la ficha Trabajos o en la ficha **Administradores** supervisando el estado en la columna Estado del trabajo **de indización.**

Para obtener más información, vea:

- [Trabajar con errores de proceso](processing-data-for-case.md)

- [Administrar trabajos](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a>Liberar a un administrador de un caso

Un administrador se libera en situaciones en las que un caso está cerrado, el administrador ya no tiene la obligación de conservar el contenido de un caso o cuando se considera que el administrador ya no es relevante para el caso. 

Si libera a un administrador después de publicar un aviso de retención, se enviará un aviso de lanzamiento al administrador. Además, se quitan las retenciones realizadas en orígenes de datos asociados con el administrador. Si el administrador se colocó en una retención *silenciosa,* donde no se emitieron notificaciones de retención legal, no se enviará un aviso de liberación, pero se quitarán las retenciones realizadas en los orígenes de datos asociados con ese administrador.

Para liberar a un administrador: 

1. Vaya a  **eDiscovery > eDiscovery avanzado** y abra el caso.

2. Haga clic en **la pestaña** Orígenes.

3. En la **página Administradores** y, a continuación, seleccione el administrador que se va a liberar del caso.

4. En la página desplegable, haga clic **en Liberar administrador.**

   Se muestra una página de advertencia en la que se explica que si se coloca una retención en un origen de datos asociado con el administrador, se quitará la retención y se aplicará cualquier otra retención asociada con un caso de eDiscovery avanzado diferente. Esto incluye otros tipos de características de conservación y retención (como una directiva de retención de Microsoft 365).

5. Haga **clic en** Sí para confirmar que desea liberar al administrador. 

    El estado de este usuario en la pestaña **Administradores** se establece en **Liberado** y el estado de retención en la página desplegable se cambia a **False**.  

> [!NOTE]
> Un administrador puede estar involucrado simultáneamente en varios casos legales. Cuando un administrador se libera de un caso, las retenciones y notificaciones en otros asuntos no se verán afectadas.

## <a name="bulk-edit-custodians"></a>Administradores de edición masiva

Puede usar el editor masivo para editar varios administradores al mismo tiempo. Para ello, simplemente seleccione dos o más  administradores en la pestaña Administradores para mostrar el editor en masa y, a continuación, haga clic en una de las tareas.

![Página desplegable para editar la configuración de varios administradores](../media/AeDBulkEditCustodians.png)
