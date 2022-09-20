---
title: Adición de orígenes de datos que no son de custodia a un caso de exhibición de documentos electrónicos (Premium)
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
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
description: Puede agregar orígenes de datos que no sean de custodia a un caso de exhibición de documentos electrónicos (Premium) y colocar una suspensión en el origen de datos. Los orígenes de datos sin custodia se vuelven a indexar, por lo que cualquier contenido marcado como parcialmente indexado se vuelve a procesar para que se pueda buscar de forma completa y rápida.
ms.openlocfilehash: 80ab3cf2640481a1fa0e8d3cc49a9324aed31b82
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67824055"
---
# <a name="add-non-custodial-data-sources-to-an-ediscovery-premium-case"></a>Adición de orígenes de datos que no son de custodia a un caso de exhibición de documentos electrónicos (Premium)

En los casos de Microsoft Purview eDiscovery (Premium), no siempre satisface sus necesidades para asociar un origen de datos de Microsoft 365 a un custodio en el caso. Pero es posible que todavía necesite asociar esos datos a un caso para poder buscarlos, agregarlos a un conjunto de revisión y analizarlos y revisarlos. La característica de eDiscovery (Premium) se denomina *orígenes de datos sin custodia* y permite agregar datos a un caso sin tener que asociarlos a un custodio. También aplica la misma funcionalidad de exhibición de documentos electrónicos (Premium) a los datos no custodiales que están disponibles para los datos asociados con el custodio. Dos de las cosas más útiles que puede aplicar a los datos que no son de custodia es colocarlos en espera y procesarlos mediante [la indexación avanzada](indexing-custodian-data.md).

## <a name="add-a-non-custodial-data-source"></a>Adición de un origen de datos que no es de custodia

Siga estos pasos para agregar y administrar orígenes de datos que no son de custodia en un caso de exhibición de documentos electrónicos (Premium).

1. En la página principal **de eDiscovery (Premium),** haga clic en el caso al que desea agregar los datos.

2. Haga clic en la pestaña **Orígenes de** datos y, a continuación, haga clic en **Agregar origen de** > **datos Agregar ubicaciones de datos**.

3. En la página flotante **Nuevas ubicaciones de datos sin custodia** , elija los orígenes de datos que desea agregar al caso. Puede agregar varios buzones de correo y sitios expandiendo las secciones **de SharePoint** o **Exchange** y, a continuación, haciendo clic en **Editar**.

   ![Agregue sitios de SharePoint y buzones de Exchange como orígenes de datos que no sean de custodia.](../media/NonCustodialDataSources1.png)

   - **SharePoint** : haga clic en **Editar** para agregar sitios. Seleccione un sitio en la lista o puede buscar un sitio escribiendo la dirección URL del sitio en la barra de búsqueda. Seleccione los sitios que desea agregar como orígenes de datos sin custodia y haga clic en **Agregar**.

   - **Exchange** : haga clic en **Editar** para agregar buzones. Escriba un nombre o alias (un mínimo de tres caracteres) en el cuadro de búsqueda de buzones o grupos de distribución. Seleccione los buzones que desea agregar como orígenes de datos que no son de custodia y haga clic en **Agregar**.

   > [!NOTE]
   > Puede usar las secciones **De SharePoint** y **Exchange** para agregar sitios y buzones asociados a un grupo de Team o Yammer como orígenes de datos que no son de custodia. Tiene que agregar por separado el buzón de correo y el sitio asociados a un grupo de Team o Yammer.<br/><br/> Además, no se admite la adición de una dirección URL del sitio raíz (como `https://contoso-my.sharepoint.com/personal/` o  `https://contoso-my.sharepoint.com/`) como origen de datos de SharePoint. Tiene que agregar sitios específicos.

4. Después de agregar orígenes de datos que no son de custodia, tiene la opción de colocar esas ubicaciones en espera o no. Active o anule la selección de la casilla **Detención** situada junto al origen de datos para colocarla en espera.

5. Haga clic en **Agregar** en la parte inferior de la página desplegable **Nuevas ubicaciones de datos sin custodia** para agregar los orígenes de datos al caso.

   Cada origen de datos sin custodia que agregó se muestra en la página **Orígenes de datos** . Los orígenes de datos sin custodia se identifican mediante el valor **Ubicación de** datos en la columna **Tipo de origen** .

   ![Orígenes de datos sin custodia en la pestaña Orígenes de datos.](../media/NonCustodialDataSources2.png)

Después de agregar orígenes de datos que no son de custodia al caso, se crea un trabajo denominado *Reindexación de datos que no son de custodia* y se muestra en la pestaña **Trabajos** del caso. Una vez creado el trabajo, se vuelve a indexar el proceso de indexación avanzada en iniciado y los orígenes de datos.

## <a name="manage-the-hold-for-non-custodial-data-sources"></a>Administración de la suspensión para orígenes de datos que no son de custodia

Después de colocar una suspensión en un origen de datos que no es de custodia, se crea automáticamente una directiva de suspensión que contiene los orígenes de datos que no son de custodia para el caso. Cuando coloca otros orígenes de datos que no son de custodia en espera, se agregan a esta directiva de suspensión.

1. Abra el caso de exhibición de documentos electrónicos (Premium) y seleccione la pestaña **Suspensión** .

2. Haga clic en **NCDSHold-\<GUID\>**, donde el valor GUID es único para el caso.

   La página de control flotante muestra información y estadísticas sobre los orígenes de datos que no son de custodia en espera.

   ![La página de control flotante de los orígenes de datos que no son de custodia muestra estadísticas.](../media/NonCustodialDataSourcesHoldFlyout.png)

3. Haga clic en **Editar suspensión** para ver los orígenes de datos que no son de custodia colocados en espera y realizar las siguientes tareas de administración:

   - En la página **Ubicaciones** , puede liberar un origen de datos que no sea de custodia quitándolo de la suspensión. La liberación de un origen de datos no quita el origen de datos que no es de custodia del caso. Solo quita la suspensión que se colocó en el origen de datos.

   - En la página **Consulta** , puede editar la suspensión para crear una suspensión basada en consultas que se aplique a todos los orígenes de datos que no son de custodia en el caso.
