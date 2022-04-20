---
title: Exportación y descarga de contenido desde un caso de exhibición de documentos electrónicos (estándar)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.custom: admindeeplinkCOMPLIANCE
description: Describe cómo exportar y descargar contenido de un caso de exhibición de documentos electrónicos (estándar) en Microsoft 365.
ms.openlocfilehash: 2a63d22c8b4cb20e2c0f1317a8496e1cf517b2da
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64995456"
---
# <a name="export-content-from-a-ediscovery-standard-case"></a>Exportación de contenido desde un caso de exhibición de documentos electrónicos (estándar)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Una vez que una búsqueda asociada a un caso de exhibición de documentos electrónicos (estándar) de Microsoft Purview se ejecuta correctamente, puede exportar los resultados de la búsqueda. Al exportar los resultados de búsqueda, los elementos de buzón se descargan en archivos PST o como mensajes individuales. Al exportar contenido de sitios SharePoint y OneDrive para la Empresa, se exportan copias de documentos nativos Office y otros documentos. También se exporta un archivo Results.csv que contiene información sobre cada elemento exportado y un archivo de manifiesto (en formato XML) que contiene información sobre cada resultado de búsqueda.
  
## <a name="export-search-results"></a>Exportar resultados de búsqueda

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento de Microsoft Purview</a> e inicie sesión con las credenciales de la cuenta de usuario a la que se han asignado los permisos de eDiscovery adecuados.

2. En el panel de navegación izquierdo del portal de cumplimiento, seleccione **Mostrar todo** y, a continuación, seleccione **eDiscoveryCore** > .<a href="https://go.microsoft.com/fwlink/p/?linkid=2174007" target="_blank"></a>

3. En la página **eDiscovery (Estándar),** haga clic en el nombre del caso en el que desea crear la suspensión.

4. En la página **Inicio** del caso, haga clic en la pestaña **Búsquedas** .

5. En el menú **Acciones** de la parte inferior de la página desplegable, haga clic en **Exportar resultados**.

   ![Opción Exportar resultados en el menú Acciones.](../media/ActionMenuExportResults.png)

   El flujo de trabajo para exportar los resultados de una búsqueda asociada a un caso de exhibición de documentos electrónicos (estándar) es el mismo que exportar los resultados de búsqueda para una búsqueda en la página **Búsqueda de contenido** . Para obtener instrucciones paso a paso, consulte [Exportación de resultados de búsqueda de contenido](export-search-results.md).

   > [!NOTE]
   > Al exportar los resultados de búsqueda, tiene la opción de habilitar la desduplicación para que solo se exporte una copia de un mensaje de correo electrónico, aunque se hayan encontrado varias instancias del mismo mensaje en los buzones de correo en los que se ha buscado. Para obtener más información sobre la desduplicación y cómo se identifican los elementos duplicados, vea [Desduplicación en los resultados de búsqueda de eDiscovery](de-duplication-in-ediscovery-search-results.md).

   Después de iniciar la exportación, los resultados de la búsqueda se preparan para su descarga, lo que significa que se transfieren a una ubicación de Azure Storage proporcionada por Microsoft en la nube de Microsoft.
  
6. Haga clic en la pestaña **Exportaciones** en el caso para mostrar la lista de trabajos de exportación.
  
   ![Exporte trabajos en la pestaña Exportar en el caso de exhibición de documentos electrónicos (estándar).](../media/CoreeDiscoveryExport.png)

   Es posible que tenga que hacer clic en **Actualizar** para actualizar la lista de trabajos de exportación para que muestre el trabajo de exportación que ha creado. Los trabajos de exportación tienen el mismo nombre que la búsqueda correspondiente con **_Export** anexado al nombre de búsqueda.

7. Haga clic en el trabajo de exportación que creó para mostrar información de estado en la página de control flotante. Esta información incluye el porcentaje de elementos que se han transferido a la ubicación de almacenamiento de Azure.

8. Una vez transferidos todos los elementos, haga clic en **Descargar resultados** para descargar los resultados de búsqueda en el equipo local. Para obtener más información sobre cómo descargar los resultados de la búsqueda, consulte el paso 2 en [Exportación de resultados de búsqueda de contenido](export-search-results.md#step-2-download-the-search-results).

> [!NOTE]
> Los resultados de búsqueda exportados se deben descargar en un plazo de 14 días después de crear el trabajo de exportación.

### <a name="more-information-about-exporting-searches-from-a-case"></a>Más información sobre la exportación de búsquedas desde un caso

- Para obtener más información sobre los archivos de exportación que se incluyen al exportar los resultados de búsqueda, vea [Exportar un informe de búsqueda de contenido](export-a-content-search-report.md#whats-included-in-the-report).

- Si reinicia la exportación, los cambios realizados en las consultas de las búsquedas que componen el trabajo de exportación no afectarán a los resultados de la búsqueda que se recuperan. Al reiniciar una exportación, se volverá a ejecutar el mismo trabajo de consulta de búsqueda combinada que se ejecutó cuando se creó el trabajo de exportación.

- Además, si reinicia una exportación, los resultados de búsqueda que se copian en la ubicación Azure Storage sobrescriben los resultados anteriores. Los resultados anteriores que se copiaron no estarán disponibles para su descarga.
