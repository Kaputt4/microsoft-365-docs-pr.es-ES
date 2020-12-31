---
title: Agregar orígenes de datos que no sean de Private a un caso de exhibición avanzada de documentos electrónicos
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
description: Puede Agregar orígenes de datos que no sean de Private a un caso de exhibición avanzada de documentos electrónicos y poner una retención en el origen de datos. Los orígenes de datos que no son de Private se reindizan, por lo que cualquier contenido marcado como parcialmente indizado se reprocesa para que se pueda buscar de forma completa y rápida.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740357"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a>Agregar orígenes de datos que no sean de Private a un caso de exhibición avanzada de documentos electrónicos

En los casos de eDiscovery avanzado, no siempre satisface sus necesidades de asociar un origen de datos de Microsoft 365 con un custodio en el caso. Pero es posible que tenga que asociar esos datos con un caso para que pueda buscarlos, agregarlos a un conjunto de revisión y analizarlos y revisarlos. La característica de eDiscovery avanzado se denomina *orígenes de datos que no son de Private* y le permite agregar datos a un caso sin tener que asociarlo a un custodio. También aplica la misma funcionalidad avanzada de exhibición de documentos electrónicos a los datos que no son de Private y que están disponibles para los datos asociados con custodio. Dos de las cosas más útiles que puede aplicar a los datos que no son de Private son ponerla en suspensión y procesarla con una [indización avanzada](indexing-custodian-data.md).

## <a name="add-a-non-custodial-data-source"></a>Agregar un origen de datos que no sea de privación

Siga estos pasos para agregar y administrar orígenes de datos que no sean de Private en un caso de exhibición avanzada de documentos electrónicos.

1. En la Página principal de **EDiscovery avanzado** , haga clic en el caso al que desea agregar los datos.

2. Haga clic en la ficha **orígenes** de datos y, a continuación, en **Agregar origen de datos**  >  **Agregar ubicaciones de datos**.

3. En la página desplegable de **ubicaciones de datos no coprivate** , elija los orígenes de datos que desee agregar al caso. Para agregar varios buzones y sitios, expanda las secciones **SharePoint** o **Exchange** y, a continuación, haga clic en **Editar**.

   ![Agregar sitios de SharePoint y buzones de Exchange como orígenes de datos que no son de privación](../media/NonCustodialDataSources1.png)

   - **SharePoint** : haga clic en **Editar** para agregar sitios. Seleccione un sitio de la lista o puede escribir la dirección URL del sitio en la barra de búsqueda para buscar un sitio. Seleccione los sitios que desea agregar como orígenes de datos no custodios y haga clic en **Agregar**.

   - **Exchange** : haga clic en **Editar** para agregar buzones. Escriba un nombre o alias (tres caracteres como mínimo) en el cuadro de búsqueda para buzones de correo o grupos de distribución. Seleccione los buzones que desea agregar como orígenes de datos no custodios y haga clic en **Agregar**.

   > [!NOTE]
   > Puede usar las secciones **SharePoint** y **Exchange** para agregar sitios y buzones asociados con un equipo o un grupo de Yammer como orígenes de datos que no son de privación. Debe agregar por separado el buzón de correo y el sitio asociados a un equipo o grupo de Yammer.

4. Después de agregar orígenes de datos que no sean de Private, tiene la opción de poner las ubicaciones en espera o no. Seleccione o anule la selección de la casilla **suspender** situada junto al origen de datos para ponerla en espera.

5. Haga clic en **Agregar** en la parte inferior de la página flotante de **ubicaciones de datos no coprivate** para agregar los orígenes de datos al caso.

   Cada origen de datos no de Private que agregó aparece en la lista de la página de **orígenes de datos** . Los orígenes de datos que no son de Private se identifican mediante el valor ubicación de los **datos** en la columna **tipo de origen** .

   ![Orígenes de datos que no son de apoyo en la ficha orígenes de datos](../media/NonCustodialDataSources2.png)

Después de agregar al caso orígenes de datos que no sean de Private, se crea un trabajo llamado *reindizar datos que no son de Private* y se muestra en la ficha **trabajos** del caso. Una vez creado el trabajo, el proceso de indización avanzado en iniciado y los orígenes de datos se reindizan.

## <a name="manage-the-hold-for-non-custodial-data-sources"></a>Administrar la retención de los orígenes de datos que no son de Private

Después de poner una retención en un origen de datos que no sea de Private, se creará automáticamente una directiva de retención que contiene los orígenes de datos que no son de Private para el caso. Cuando se retienen otros orígenes de datos no coprivate, se agregan a esta directiva de retención.

1. Abra el caso de exhibición avanzada de documentos electrónicos y seleccione la pestaña **retención** .

2. Haga clic en **NCDSHold- \<GUID\>**, donde el valor de GUID es único en el caso.

   La página de control flotante muestra información y estadísticas sobre los orígenes de datos que no son de custodia en suspensión.

   ![La página de control flotante para la retención de orígenes de datos que no son de Private muestra estadísticas](../media/NonCustodialDataSourcesHoldFlyout.png)

3. Haga clic en **Editar suspensión** para ver los orígenes de datos que no son de Private en suspensión y realizar las siguientes tareas de administración:

   - En la página **ubicaciones** , puede liberar un origen de datos que no sea de privación y quitarlo de la suspensión. Al liberar un origen de datos, no se quita del caso el origen de datos que no es de tipo Private. Solo quita la retención que se colocó en el origen de datos.

   - En la página **consulta** , puede editar la retención para crear una suspensión basada en consulta que se aplique a todos los orígenes de datos que no sean de custodia en el caso.
