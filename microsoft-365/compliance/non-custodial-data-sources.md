---
title: Agregar orígenes de datos que no son de custodia a un caso de eDiscovery avanzado
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
description: Puede agregar orígenes de datos que no son de custodia a un caso de eDiscovery avanzado y colocar una retención en el origen de datos. Los orígenes de datos que no son de custodia se reindexa, por lo que cualquier contenido que se marcó como parcialmente indizado se vuelve a procesar para que se pueda buscar de forma completa y rápida.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740357"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a>Agregar orígenes de datos que no son de custodia a un caso de eDiscovery avanzado

En los casos de eDiscovery avanzado, no siempre satisface sus necesidades asociar un origen de datos de Microsoft 365 con un administrador en el caso. Pero es posible que aún deba asociar los datos con un caso para poder buscarlos, agregarlos a un conjunto de revisión y analizarlos y revisarlos. La característica de eDiscovery avanzado se denomina orígenes de datos no *administradores* y le permite agregar datos a un caso sin tener que asociarlo a un administrador. También aplica la misma funcionalidad de eDiscovery avanzado a los datos que no son de custodia y que están disponibles para los datos asociados con el administrador. Dos de las cosas más útiles que puede aplicar a los datos que no son de custodia es ponerlos en retención y procesarlos mediante [la indización avanzada.](indexing-custodian-data.md)

## <a name="add-a-non-custodial-data-source"></a>Agregar un origen de datos que no es de custodia

Siga estos pasos para agregar y administrar orígenes de datos que no son de custodia en un caso de eDiscovery avanzado.

1. En la **página principal de eDiscovery** avanzado, haga clic en el caso al que desea agregar los datos.

2. Haga clic en la **pestaña Orígenes de** datos y, a continuación, haga clic en Agregar ubicaciones de datos **de** origen de  >  **datos.**

3. En la **página desplegable Nuevas** ubicaciones de datos no confidenciales, elija los orígenes de datos que desea agregar al caso. Puede agregar varios buzones y sitios expandiendo las secciones de **SharePoint** o **Exchange** y, a continuación, haciendo clic en **Editar**.

   ![Agregar sitios de SharePoint y buzones de Exchange como orígenes de datos no administradores](../media/NonCustodialDataSources1.png)

   - **SharePoint:** haga **clic en Editar** para agregar sitios. Seleccione un sitio en la lista o puede buscar un sitio escribiendo la dirección URL del sitio en la barra de búsqueda. Seleccione los sitios que desea agregar como orígenes de datos no administradores y haga clic en **Agregar**.

   - **Exchange:** haga **clic en Editar** para agregar buzones. Escriba un nombre o alias (un mínimo de tres caracteres) en el cuadro de búsqueda para buzones o grupos de distribución. Seleccione los buzones que desea agregar como orígenes de datos no administradores y haga clic en **Agregar**.

   > [!NOTE]
   > Puede usar las secciones **de SharePoint** y **Exchange** para agregar sitios y buzones asociados con un grupo de Team o Yammer como orígenes de datos no administradores. Debe agregar por separado el buzón y el sitio asociados a un grupo de Team o Yammer.

4. Después de agregar orígenes de datos que no son de custodia, tiene la opción de poner esas ubicaciones en retención o no. Active o anule la selección **de la casilla** De retención situada junto al origen de datos para ponerla en espera.

5. Haga **clic en** Agregar en la parte inferior de la página desplegable Nuevas ubicaciones de datos no **confidenciales** para agregar los orígenes de datos al caso.

   Cada origen de datos no administrador que agregó aparece en la página **Orígenes de** datos. Los orígenes de datos que no son de custodia se identifican mediante el valor **de ubicación de** datos en la columna Tipo **de** origen.

   ![Orígenes de datos que no son de custodia en la pestaña Orígenes de datos](../media/NonCustodialDataSources2.png)

Después de agregar orígenes de datos que no son de custodia al caso, se crea un trabajo denominado *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case. Una vez creado el trabajo, se inicia el proceso de indización avanzada y se vuelve a indexar los orígenes de datos.

## <a name="manage-the-hold-for-non-custodial-data-sources"></a>Administrar la retención de orígenes de datos que no son de custodia

Después de colocar una retención en un origen de datos que no es de custodia, se crea automáticamente una directiva de retención que contiene los orígenes de datos que no son administradores del caso. Cuando coloca otros orígenes de datos no administradores en retención, se agregan a esta directiva de retención.

1. Abra el caso de eDiscovery avanzado y seleccione la **pestaña** Retención.

2. Haga **clic en \<GUID\> NCDSHold-**, donde el valor GUID es único para el caso.

   La página desplegable muestra información y estadísticas sobre los orígenes de datos no administradores en espera.

   ![La página desplegable para la retención de orígenes de datos no administradores muestra estadísticas](../media/NonCustodialDataSourcesHoldFlyout.png)

3. Haga **clic en Editar retención** para ver los orígenes de datos que no son de custodia puestos en retención y realizar las siguientes tareas de administración:

   - En la **página** Ubicaciones, puede liberar un origen de datos que no sea de custodia si lo quita de la retención. Liberar un origen de datos no quita del caso el origen de datos que no es de custodia. Solo quita la retención que se colocó en el origen de datos.

   - En la **página** Consulta, puede editar la retención para crear una retención basada en consultas que se aplique a todos los orígenes de datos que no son de custodia en el caso.
