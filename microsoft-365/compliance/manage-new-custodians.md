---
title: Administrar custodios en un Advanced eDiscovery caso
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
description: Obtenga información sobre cómo ver detalles, editar y editar en masa la lista de custodios en un Advanced eDiscovery caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 794677c8675f044bafb1c9a441e6c2bbee3e1c86
ms.sourcegitcommit: b19e54b3888a0b07d08dbd23172daec303c7c95b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2021
ms.locfileid: "61152423"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a>Administrar custodios en un Advanced eDiscovery caso

La **página Custodios** de la pestaña Orígenes de datos de un caso Advanced eDiscovery contiene una lista de todos los custodios que se han agregado al caso.  Después de agregar custodios a un caso, los detalles sobre cada custodio se recopilan automáticamente desde Azure Active Directory y se pueden ver en Advanced eDiscovery.

## <a name="view-custodian-details"></a>Ver detalles del custodio

Para ver los detalles sobre un custodio, haga clic en el custodio de la lista de la pestaña **Custodios.** Se muestra una página desplegable que contiene la siguiente información sobre el custodio.

![Detalles del custodio.](../media/CustodianDetails.PNG)

- Información de contacto

  - **Título**. El cargo del custodio.
  
  - **Nombre principal de usuario**. El nombre principal de usuario(UPN) del custodio, por ejemplo, AdeleV@contoso.onmicrosoft.com.
  
  - **Location**. Ubicación de la oficina en el lugar de negocios del custodio.
  
  - **Administrador**. El administrador del custodio. El administrador designado recibirá cualquier comunicación de escalamiento para este custodio.
  
  - **Departamento**. Nombre del departamento en el que trabaja el custodio.

- Información del caso

  - **Estado**. El estado del custodio dentro del caso. Un estado **de Active** indica que el custodio forma parte del caso. Si un custodio se libera de un caso, el estado cambia a **Liberado**.
  
  - **Mantenga en espera**. Indica si el custodio se ha puesto en espera.

- Ubicaciones de datos y retención de información

  ![Ubicaciones de datos de custodia y retención de información.](../media/CustodianHoldDetails.PNG)

  - **Ubicaciones de custodia**. Muestra el recuento y el tipo de orígenes de datos (buzones, sitios y Teams) que están asociados con el custodio y forman parte del caso.

    - Cada ubicación de datos muestra su estado de retención. Valores posibles para el estado de retención: **En espera**, No **en espera** y En **curso**.

    - Si no ve un estado de retención para un origen de datos, compruebe el  estado de la retención de custodia que aparece en la pestaña Retención del caso. La retención de custodia identifica los orígenes de datos específicos en espera.

## <a name="edit-a-custodian"></a>Editar un custodio

A medida que avanza el caso, puede descubrir que puede haber orígenes de datos adicionales relevantes para un custodio específico y el caso. En otros escenarios, es posible que desee quitar determinados orígenes de datos que se han revisado y que se consideran no relevantes.

Para actualizar los orígenes de datos asociados con un custodio:

1. Vaya a **eDiscovery > Advanced eDiscovery** y abra el caso.
  
2. Haga clic en **la pestaña Orígenes de** datos.
  
3. Seleccione un custodio de la lista y, a continuación, haga clic **en Editar** en la página desplegable.

    ![Editar orígenes de datos.](../media/EditCustodianDataSource.PNG)
  
4. Para agregar o quitar el buzón principal y OneDrive cuenta para el custodio:

    - Expanda el custodio para ver las ubicaciones de datos principales que se han asociado previamente con el custodio.

    - Haga **clic en** Editar junto a **Buzón** o **OneDrive** para agregar el buzón o la ubicación OneDrive custodia.

    - Seleccione **Borrar** junto  a **Buzón** o OneDrive para quitar el buzón o la cuenta OneDrive del custodio para que no se asocie como ubicación de datos para este custodio.

5. Para agregar o quitar otros buzones, sitios, Teams o grupos Yammer a un custodio específico, haga clic en **Editar** junto al servicio para agregar una ubicación de datos.

   - **Exchange:** se usa para asociar otros buzones al custodio. Escriba en el cuadro de búsqueda el nombre o el alias (un mínimo de tres caracteres) de los buzones de usuario o grupos de distribución. Seleccione los buzones que desea asignar al custodio y, a continuación, haga clic **en Agregar**.

   - **SharePoint:** se usa para asociar SharePoint sitios al custodio. Seleccione un sitio en la lista o busque un sitio escribiendo una dirección URL en el cuadro de búsqueda. Seleccione los sitios que desea asignar al custodio y, a continuación, haga clic **en Agregar**.

   - **Teams:** se usa para asignar el Microsoft Teams del que el custodio es miembro actualmente. Seleccione los equipos que desea asignar al custodio y, a continuación, haga clic **en Agregar**. Después de agregar un equipo, el sistema identifica y localiza automáticamente el buzón SharePoint sitio y grupo asociados a ese equipo y los asigna al administrador.

   - **Yammer:** se usa para asignar los grupos Yammer de los que el custodio es miembro actualmente. Seleccione los grupos que desea asignar al custodio y, a continuación, haga clic **en Agregar**. Después de agregar un equipo, el sistema identifica y localiza automáticamente el sitio SharePoint y el buzón de grupo asociados a ese grupo y los asigna al custodio.

   > [!NOTE]
   > Puede usar  los selectores de ubicación Exchange y **SharePoint** para asociar cualquier buzón o sitio de su organización, incluidos los equipos o grupos de Yammer de los que un custodio no es miembro, a un administrador. Para ello, debe agregar el buzón y el sitio asociados con cada grupo o Yammer grupo.

6. Después de editar las ubicaciones de datos del custodio, haga clic en **Siguiente** para ir a la **página Configuración de retención.**  

7. En la **página Configuración de retención,** actualice la configuración de retención del custodio.

## <a name="reindex-custodian-data"></a>Reindexar datos de custodia

En la mayoría de los flujos de trabajo de exhibición de documentos electrónicos para investigaciones legales, se busca un subconjunto de datos de un custodio después de agregarlo a un caso legal. Debido a tamaños de archivo muy grandes o posibles daños en los datos, es posible que algunos elementos de los orígenes de datos asociados con un custodio se indexe parcialmente. Con la [funcionalidad de indización](indexing-custodian-data.md) avanzada en el Advanced eDiscovery, la mayoría de los elementos parcialmente indizados se pueden corregir automáticamente reindexando estos elementos a petición.

Cuando se agrega un custodio a un caso, los datos ubicados en los orígenes de datos asociados con el custodio se reindexa automáticamente (mediante el proceso de indización avanzado). Esto significa que puede dejar los datos en su lugar en lugar de tener que descargarlos y corregirlos y, a continuación, buscarlos sin conexión). Sin embargo, durante el ciclo de vida de un caso legal, los nuevos orígenes de datos podrían asociarse con un custodio. En este caso, puede volver a indizar los datos del custodio al volver a ejecutar el proceso de indización avanzada para corregir los elementos parcialmente indizados y actualizar el índice de los datos del custodio.

Para desencadenar el proceso de reindexación para abordar elementos parcialmente indizados:

1. Vaya a **eDiscovery > Advanced eDiscovery** y abra el caso.

2. Haga clic en **la pestaña** Orígenes.

3. En la **página Custodios,** seleccione un custodio cuyos datos deben volver a indizarse.

4. En la página desplegable, haga clic **en Actualizar índice**.

   Se muestra un cuadro de diálogo que dice que se ha creado el trabajo de índice.

La reindexación de datos de custodia es un proceso de larga ejecución; el trabajo correspondiente que se crea se denomina **Re-indexing custodian data**. Puede realizar un seguimiento del progreso en **la** pestaña Trabajos o en la pestaña **Custodios** supervisando el estado en la columna Estado del trabajo **de indización.**

Para más información, vea:

- [Trabajar con errores de proceso](processing-data-for-case.md)

- [Administrar trabajos](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a>Liberar a un custodio de un caso

Un custodio se libera en situaciones en las que se cierra un caso, el custodio ya no tiene la obligación de conservar el contenido de un caso o cuando se considera que el custodio ya no es relevante para el caso. 

Si libera a un custodio después de publicar un aviso de retención, se enviará un aviso de liberación al custodio. Además, se quitan las retenciones realizadas en orígenes de datos asociados con el custodio. Si el custodio se colocó en una retención silenciosa *,* donde no se emitieron notificaciones de retención legal, no se enviará un aviso de liberación, pero se quitarán las retenciones de los orígenes de datos asociados con ese custodio.

Para liberar a un custodio:

1. Vaya a **eDiscovery > Advanced eDiscovery** y abra el caso.

2. Haga clic en **la pestaña** Orígenes.

3. En la **página Custodios** y, a continuación, seleccione el custodio que está siendo liberado del caso.

4. En la página desplegable, haga clic **en Liberar custodio**.

   Se muestra una página de advertencia que explica que si se coloca una retención en un origen de datos asociado con el custodio, se eliminará la retención y se aplicará cualquier otra retención asociada con un caso Advanced eDiscovery diferente. Esto incluye otros tipos de características de conservación y retención (como una Microsoft 365 de retención).

5. Haga **clic en** Sí para confirmar que desea liberar al custodio. 

    El estado de este usuario en la pestaña **Custodios** se establece en **Liberado** y el estado de retención en la página desplegable se cambia a **False**. 

> [!NOTE]
> Un custodio puede estar implicado simultáneamente en varios casos legales. Cuando un custodio se libera de un caso específico, las retenciones y notificaciones en otros casos no se verán afectadas.
