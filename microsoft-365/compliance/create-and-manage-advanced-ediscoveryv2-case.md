---
title: Crear y administrar casos de eDiscovery avanzado en Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: En este artículo se describe cómo crear y administrar casos de eDiscovery avanzado. El primer paso es crear un caso y empezar a usar características y funcionalidades de eDiscovery avanzado.
ms.openlocfilehash: c95994b3706880b40ff6306c02a4bdb5dba7748b
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841651"
---
# <a name="create-and-manage-an-advanced-ediscovery-case"></a>Crear y administrar un caso de eDiscovery avanzado

Después de configurar eDiscovery avanzado y asignar permisos a los administradores de exhibición de documentos electrónicos de su organización que administrarán [casos,](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions) el siguiente paso es crear y administrar un caso.

En este artículo también se proporciona información general de alto nivel sobre el uso de casos para administrar el flujo de trabajo de eDiscovery avanzado para una investigación legal.

## <a name="create-a-case"></a>Crear un caso

Complete los pasos siguientes para crear un caso y agregar miembros. El usuario que crea el caso se agrega automáticamente como miembro.

1. Vaya e inicie sesión con las credenciales de la cuenta de usuario a la que se han asignado [https://compliance.microsoft.com](https://compliance.microsoft.com) permisos de exhibición de documentos electrónicos. Los miembros del grupo de roles Administración de la organización también pueden crear casos de eDiscovery avanzado.

2. En el panel de navegación izquierdo del Centro de cumplimiento de Microsoft 365, haga clic en Mostrar todo y, a continuación, haga clic en **eDiscovery > avanzado.**

3. En la **página eDiscovery avanzado,** haga clic en la pestaña **Casos** y, a continuación, haga **clic en Crear un caso.**

4. En la **página desplegable Nuevo** caso de exhibición de documentos electrónicos, asigne un nombre (obligatorio) al caso y, a continuación, escriba un número de caso y una descripción opcionales. El nombre del caso debe ser único en la organización.

5. Haga **clic en** Guardar para crear el caso.

   Se crea el nuevo caso y se muestra **la** pestaña Configuración en el nuevo caso.

6. En el **icono & permisos de**  acceso en la pestaña Configuración, haga clic en **Seleccionar** y, a continuación, haga clic en **Actualizar**.

7. Haga clic en **Actualizar**.

8. En la **página desplegable Administrar este caso,** en Administrar **miembros,** haga clic en Agregar para agregar miembros al caso. 

9. En la lista de personas, active la casilla junto a los nombres de las personas que desea agregar al caso. Como se ha explicado anteriormente, asegúrese de que a las personas que agregue al caso se les hayan asignado los permisos de exhibición de documentos electrónicos adecuados.

10. Después de seleccionar las personas para agregar como miembros del caso, haga clic en **Agregar**.

11. En la **página desplegable Administrar este caso,** haga clic en Guardar para guardar la nueva lista de miembros del caso. 

12. Haga clic en **la** pestaña Inicio para ir a la página principal del caso.

## <a name="manage-the-workflow"></a>Administrar el flujo de trabajo

Para empezar a usar eDiscovery avanzado, este es un flujo de trabajo básico que se alinea con las prácticas comunes de [exhibición de documentos electrónicos.](advanced-ediscovery-edrm.md) En cada uno de estos pasos, también resaltaremos algunas funciones extendidas de eDiscovery avanzado que puede explorar.

![Flujo de trabajo avanzado de exhibición de documentos electrónicos](../media/AeDWorkflow.png)

1. **[Agregue administradores y](add-custodians-to-case.md) orígenes de datos que no son [administradores](non-custodial-data-sources.md) al caso.** El primer paso después de crear un caso es agregar administradores. Un *administrador es* una persona que tiene el control administrativo de un documento o archivo electrónico que puede ser relevante para el caso. Además, puede agregar orígenes de datos que no están asociados a un usuario específico, pero que pueden ser relevantes para el caso.

   Estas son algunas cosas que suceden (o que puede hacer) cuando agrega administradores a un caso:

   - Los datos del buzón de Exchange del administrador, la cuenta de OneDrive y cualquier grupo de Microsoft Teams o Yammer del que el administrador sea miembro se pueden "marcar" como datos de custodia en el caso.
  
   - Los datos de administrador se reindexa (mediante un proceso denominado *indización avanzada).* Esto ayuda a optimizar la búsqueda en el paso siguiente.
  
   - Puede poner en retención los datos de administrador. Esto conserva los datos que pueden ser relevantes para el caso durante la investigación.
  
   - Puede asociar otros orígenes de datos con un administrador (por ejemplo, puede asociar un sitio de SharePoint o un grupo de Microsoft 365 con un administrador) para que estos datos se puedan volver a indexar, colocar en retención y buscar, al igual que los datos del buzón del administrador o la cuenta de OneDrive.

   - Puede usar el flujo de [trabajo de comunicaciones](managing-custodian-communications.md) en eDiscovery avanzado para enviar una notificación de retención legal a los administradores.

2. **[Buscar en orígenes de datos datos relevantes para el caso.](collecting-data-for-ediscovery.md)** Después de agregar administradores y orígenes de datos no administradores a un caso, use la herramienta de búsqueda integrada para buscar en estos orígenes de datos datos que puedan ser relevantes para el caso. Las palabras clave, las propiedades [](building-search-queries.md) y las condiciones se usan para crear consultas de búsqueda que devuelvan resultados de búsqueda con los datos que probablemente sean más relevantes para el caso. También puede:

   - Ver [estadísticas de búsqueda que](search-statistics-in-advanced-ediscovery.md) pueden ayudarle a refinar una consulta de búsqueda para restringir los resultados.

   - Obtenga una vista previa de los resultados de la búsqueda para comprobar rápidamente si se encuentran los datos relevantes.

   - Revise una consulta y vuelva a ejecutar la búsqueda.

3. **[Agregar datos a un conjunto de revisión.](add-data-to-review-set.md)** Una vez que haya configurado y comprobado que una búsqueda devuelve los datos deseados, el siguiente paso es agregar los resultados de la búsqueda a un conjunto de revisión. Cuando agrega datos a un conjunto de revisión, los elementos se copian de su ubicación original a una ubicación segura de Azure Storage. Los datos se vuelve a indexar para optimizarlos para realizar búsquedas exhaustivas y rápidas al revisar y analizar elementos del conjunto de revisión. Además, también puede agregar datos que no son de [Office 365 a un conjunto de revisión.](load-non-office-365-data-into-a-review-set.md)

   También hay un tipo especial de conjunto de revisión al que puede agregar datos, denominado conjunto *de revisión de conversación.* Estos tipos de conjuntos de revisiones proporcionan capacidades de reconstrucción de conversaciones para reconstruir, revisar y exportar conversaciones en subproceso, como las de Microsoft Teams. Para obtener más información, vea [Revisar conversaciones en eDiscovery avanzado.](conversation-review-sets.md)

4. **Revisar y analizar datos en un conjunto de revisión.** Ahora que los datos están en un conjunto de revisión, puede usar una amplia variedad de herramientas y capacidades para ver y analizar los datos de casos con el objetivo de reducir el conjunto de datos a lo más relevante para el caso que está investigando. Esta es una lista de algunas herramientas y funcionalidades que puede usar durante este proceso.

   - [Ver documentos](view-documents-in-review-set.md). Esto incluye ver los metadatos de cada documento en un conjunto de revisión y ver el documento en su versión nativa o versión de texto.

   - [Cree consultas y filtros.](review-set-search.md) Las consultas de búsqueda se crean con varios criterios de búsqueda (incluida la capacidad de buscar en todas las propiedades de metadatos de [archivo)](document-metadata-fields-in-advanced-ediscovery.md)para refinar y limitar aún más los datos de caso a lo que es más relevante para el caso. También puede usar filtros de conjunto de revisión para aplicar rápidamente otras condiciones a los resultados de una consulta de búsqueda para refinar aún más esos resultados. 

   - [Crear y usar etiquetas](tagging-documents.md). Puede aplicar etiquetas a los documentos de un conjunto de revisión para identificar cuáles son dinámicos (o no responden al caso) y, a continuación, usar esas etiquetas al crear consultas de búsqueda para incluir o excluir los documentos etiquetados. También puede etiquetar para determinar qué documentos exportar.

   - [Anota y redacta documentos](view-documents-in-review-set.md#annotate-view). Puede usar la herramienta de anotación en una revisión para anotar documentos y censurar contenido en documentos como producto de trabajo. Generamos una versión EN PDF de un documento anotado o redactado durante la revisión para reducir el riesgo de exportar la versión nativa no modificada del documento.

   - [Analizar datos de casos.](analyzing-data-in-review-set.md) La funcionalidad de análisis de eDiscovery avanzado es eficaz. Después de ejecutar análisis en los datos del conjunto de revisión, se realizan análisis como la detección de duplicados cercanos, los subprocesos de correo electrónico y los temas que pueden ayudar a reducir el volumen de documentos que debe revisar. También generamos informes de Análisis que resumen el resultado de la ejecución de análisis. Como se ha explicado anteriormente, la ejecución de análisis también ejecuta el modelo de detección de privilegios [abogado-cliente.](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)

5. **Exportar y descargar datos de casos.** Un paso final después de recopilar, revisar y analizar datos de casos es exportarlos desde eDiscovery avanzado para revisión externa o para que los revisen personas fuera del equipo de investigación. La exportación de datos es un proceso de dos pasos. El primer paso [](export-documents-from-review-set.md) es exportar datos fuera del conjunto de revisión y copiarlos en una ubicación diferente de Azure Storage (una proporcionada por Microsoft o una administrada por su organización). A continuación, usa el Explorador de Azure Storage [para descargar](download-export-jobs.md) los datos en un equipo local. Además de los archivos de datos exportados, el contenido del paquete de exportación también contiene un informe de exportación, un informe de resumen y un informe de errores.
