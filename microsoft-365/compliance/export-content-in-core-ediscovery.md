---
title: Exportar y descargar contenido de un caso de exhibición de documentos electrónicos principal
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
description: Describe cómo exportar y descargar contenido de un caso de exhibición de documentos electrónicos principal en Microsoft 365.
ms.openlocfilehash: 8eb54e23369ef682e8aa1ebf7e681eb34444f1cd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310861"
---
# <a name="export-content-from-a-core-ediscovery-case"></a>Exportar contenido desde un caso básico de eDiscovery

Después de ejecutar correctamente una búsqueda asociada a un caso de exhibición de documentos electrónicos principal, puede exportar los resultados de la búsqueda. Al exportar los resultados de la búsqueda, los elementos del buzón se descargan en archivos PST o como mensajes individuales. Al exportar contenido de sitios SharePoint y OneDrive para la Empresa, se exportan copias de documentos Office documentos nativos y otros documentos. Un Results.csv que contiene información sobre cada elemento que se exporta y también se exporta un archivo de manifiesto (en formato XML) que contiene información sobre cada resultado de búsqueda.
  
## <a name="export-search-results"></a>Exportar resultados de búsqueda

1. Vaya a e inicie sesión con las credenciales de la cuenta de usuario a la que se han asignado los [https://compliance.microsoft.com](https://compliance.microsoft.com) permisos de exhibición de documentos electrónicos adecuados.

2. En el panel de navegación izquierdo del centro de Microsoft 365 cumplimiento, haga clic en Mostrar todo **y,** a continuación, haga clic en **eDiscovery > Core**.

3. En la **página Exhibición de documentos electrónicos** principal, haga clic en el nombre del caso en el que desea crear la retención.

4. En la **página principal** del caso, haga clic en la **pestaña** Búsquedas.

5. En el **menú** Acciones de la parte inferior de la página desplegable, haga clic **en Exportar resultados**.

   ![Opción Exportar resultados en el menú Acciones](../media/ActionMenuExportResults.png)

   El flujo de trabajo para exportar los resultados de una búsqueda asociada a un caso de exhibición de documentos electrónicos principal es el mismo que exportar los resultados de búsqueda de una búsqueda en la página **Búsqueda de** contenido. Para obtener instrucciones paso a paso, vea [Exportar resultados de búsqueda de contenido](export-search-results.md).

   > [!NOTE]
   > Al exportar los resultados de búsqueda, tiene la opción de habilitar la desduplicación para que solo se exporte una copia de un mensaje de correo electrónico aunque se hayan encontrado varias instancias del mismo mensaje en los buzones de correo que se buscaron. Para obtener más información sobre la desduplicación y cómo se identifican los elementos duplicados, vea [Desduplicación en](de-duplication-in-ediscovery-search-results.md)los resultados de búsqueda de exhibición de documentos electrónicos .

   Después de iniciar la exportación, los resultados de la búsqueda están preparados para su descarga, lo que significa que se transfieren a una ubicación Azure Storage proporcionada por Microsoft en la nube de Microsoft.
  
6. Haga clic **en la pestaña** Exportaciones en el caso para mostrar la lista de trabajos de exportación.
  
   ![Exportar trabajos en la pestaña Exportar en el caso de exhibición de documentos electrónicos principales](../media/CoreeDiscoveryExport.png)

   Es posible que tenga que hacer clic **en Actualizar** para actualizar la lista de trabajos de exportación para que muestre el trabajo de exportación que creó. Los trabajos de exportación tienen el mismo nombre que la búsqueda correspondiente **_Export** anexado al nombre de búsqueda.

7. Haga clic en el trabajo de exportación que creó para mostrar información de estado en la página desplegable. Esta información incluye el porcentaje de elementos que se han transferido a la Azure Storage ubicación.

8. Después de transferir todos los elementos, haga clic en **Descargar resultados** para descargar los resultados de búsqueda en el equipo local. Para obtener más información sobre la descarga de resultados de búsqueda, vea el paso 2 en [Exportar resultados de búsqueda de contenido](export-search-results.md#step-2-download-the-search-results)

### <a name="more-information-about-exporting-searches-from-a-case"></a>Más información sobre cómo exportar búsquedas desde un caso

- Para obtener más información acerca de los archivos de exportación que se incluyen al exportar resultados de búsqueda, vea [Export a Content search report](export-a-content-search-report.md#whats-included-in-the-report).

- Si reinicia la exportación, los cambios en las consultas de las búsquedas que conste el trabajo de exportación no afectarán a los resultados de búsqueda que se recuperan. Al reiniciar una exportación, se volverá a ejecutar el mismo trabajo de consulta de búsqueda combinado que se ejecutaba cuando se creó el trabajo de exportación.

- Además, si reinicia una exportación, los resultados de búsqueda que se copian en la ubicación Azure Storage sobrescribe los resultados anteriores. Los resultados anteriores que se copiaron no estarán disponibles para su descarga.
