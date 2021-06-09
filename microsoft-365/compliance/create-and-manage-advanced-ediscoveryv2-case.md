---
title: Crear y administrar Advanced eDiscovery casos en Microsoft 365
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
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: En este artículo se describe cómo crear y administrar Advanced eDiscovery casos. El primer paso es crear un caso y empezar a usar Advanced eDiscovery características y funcionalidades.
ms.openlocfilehash: 95e88bb071476de1ed66b3ffaa8942f0a9df89c2
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311645"
---
# <a name="create-and-manage-an-advanced-ediscovery-case"></a>Crear y administrar un Advanced eDiscovery caso

Después de configurar Advanced eDiscovery y asignar permisos a los administradores de exhibición de documentos electrónicos de la organización que administrarán los [casos,](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions) el siguiente paso es crear y administrar un caso.

En este artículo también se proporciona información general de alto nivel sobre el uso de casos para administrar el flujo de trabajo Advanced eDiscovery para un caso legal u otros tipos de investigaciones.

## <a name="create-a-case"></a>Crear un caso

Complete los pasos siguientes para crear un caso y agregar miembros. El usuario que crea el caso se agrega automáticamente como miembro. Los miembros del caso pueden tener acceso al caso en el centro de Microsoft 365 cumplimiento y realizar Advanced eDiscovery tareas.

1. Vaya a e inicie sesión con las credenciales de la cuenta de usuario a la que se han asignado permisos de <https://compliance.microsoft.com> exhibición de documentos electrónicos. Los miembros del grupo de roles Administración de la organización también pueden crear Advanced eDiscovery casos.

2. En el panel de navegación izquierdo del Centro de cumplimiento de Microsoft 365, haga clic en **Mostrar todo** y, luego, seleccione **eDiscovery > Avanzado**.

3. En la **Advanced eDiscovery,** haga clic en la **pestaña Casos** y, a continuación, haga **clic en Crear un caso**.

4. En la **página desplegable** Nuevo caso de exhibición de documentos electrónicos, asigne al caso un nombre (obligatorio) y, a continuación, escriba un número de caso y una descripción opcionales. El nombre del caso debe ser único en la organización.

5. Haga **clic en** Guardar para crear el caso.

   Se crea el nuevo caso y **se muestra Configuración** pestaña del nuevo caso.

6. En el **icono & permisos de** acceso de la **Configuración,** haga clic en **Seleccionar**.

7. En la página desplegable Administrar **este caso,** en **Administrar miembros,** haga clic en **Agregar** para agregar miembros al caso.

8. En la lista de personas, active la casilla junto a los nombres de las personas que desea agregar al caso. Como se ha explicado anteriormente, asegúrese de que las personas que agregue al caso tengan asignados los permisos de exhibición de documentos electrónicos adecuados.

9. Después de seleccionar las personas que se agregarán como miembros del caso, haga clic en **Agregar**.

10. En la página desplegable **Administrar este caso**, haga clic en **Guardar** para guardar la nueva lista de miembros del caso.

11. Haga clic en **la pestaña** Inicio para ir a la página principal del caso.

## <a name="manage-the-workflow"></a>Administrar el flujo de trabajo

Para empezar a usar Advanced eDiscovery, este es un flujo de trabajo básico que se alinea con los procedimientos comunes [de exhibición de documentos electrónicos](advanced-ediscovery-edrm.md). En cada uno de estos pasos, también destacaremos algunas funciones de Advanced eDiscovery que puede explorar.

![Advanced eDiscovery de trabajo](../media/AeDWorkflow.png)

1. **[Agregue custodios](add-custodians-to-case.md) y orígenes de datos [no custodiados](non-custodial-data-sources.md) al caso**. El primer paso después de crear un caso es agregar custodios. Un *custodio* es una persona que tiene el control administrativo de un documento o archivo electrónico que puede ser relevante para el caso. Además, puede agregar orígenes de datos que no están asociados con un usuario específico, pero que pueden ser relevantes para el caso.

   Estas son algunas cosas que ocurren (o que puede hacer) al agregar custodios a un caso:

   - Los datos del buzón de Exchange del custodio, la cuenta de OneDrive y los grupos de Microsoft Teams o Yammer de los que el custodio es miembro se pueden "marcar" como datos de custodia en el caso.
  
   - Los datos de custodia se reindexa (mediante un proceso denominado *Indexación avanzada).* Esto ayuda a optimizar la búsqueda en el siguiente paso.
  
   - Puede colocar una retención en los datos de custodia. Esto conserva los datos que pueden ser relevantes para el caso durante la investigación.
  
   - Puede asociar otros orígenes de datos con un custodio (por ejemplo, puede asociar un sitio de SharePoint o un grupo de Microsoft 365 con un custodio) para que estos datos se puedan volver a indizar, colocar en espera y buscar, al igual que los datos del buzón del custodio o de la cuenta OneDrive.

   - Puede usar el flujo de trabajo [de](managing-custodian-communications.md) comunicaciones en Advanced eDiscovery para enviar una notificación de retención legal a los custodios.

2. **[Recopilar contenido relevante de orígenes de datos](create-draft-collection.md)**. Después de agregar custodios y orígenes de datos no custodiados a un caso, use la herramienta de colecciones integradas para buscar en estos orígenes de datos contenido que pueda ser relevante para el caso. Se usan palabras clave, propiedades [](building-search-queries.md) y condiciones para crear consultas de búsqueda que devuelvan resultados de búsqueda con los datos que probablemente sean relevantes para el caso. También puede:

   - Ver [estadísticas de colección que](collection-statistics-reports.md) pueden ayudarle a refinar una colección para restringir los resultados.

   - Obtenga una vista previa de una muestra de la colección para comprobar rápidamente si se encuentran los datos relevantes.

   - Revise una consulta y vuelva a ejecutar la colección.

3. **[Confirmar colección a un conjunto de revisión](commit-draft-collection.md)**. Una vez que haya configurado y comprobado que una búsqueda devuelve los datos deseados, el siguiente paso es agregar los resultados de búsqueda a un conjunto de revisión. Al agregar datos a un conjunto de revisión, los elementos se copian desde su ubicación original a una ubicación Azure Storage seguridad. Los datos se reindexa de nuevo para optimizarlos para búsquedas exhaustivas y rápidas al revisar y analizar elementos del conjunto de revisión. Además, también puede agregar [datos no Office 365 a un conjunto de revisión](load-non-office-365-data-into-a-review-set.md).

   También hay un tipo especial de conjunto de revisión al que puede agregar datos, denominado conjunto *de revisión de conversación*. Estos tipos de conjuntos de revisiones proporcionan capacidades de reconstrucción de conversaciones para reconstruir, revisar y exportar conversaciones en subprocesos como las de Microsoft Teams. Para obtener más información, vea [Revisar conversaciones en Advanced eDiscovery](conversation-review-sets.md).

4. **Revisar y analizar los datos de un conjunto de revisión**. Ahora que los datos están en un conjunto de revisión, puede usar una amplia variedad de herramientas y capacidades para ver y analizar los datos de caso con el objetivo de reducir el conjunto de datos a lo que es más relevante para el caso que está investigando. Esta es una lista de algunas herramientas y funcionalidades que puede usar durante este proceso.

   - [Ver documentos](view-documents-in-review-set.md). Esto incluye ver los metadatos de cada documento en un conjunto de revisión y ver el documento en su versión nativa o versión de texto.

   - [Crear consultas y filtros](review-set-search.md). Puede crear consultas de búsqueda con varios criterios de búsqueda (incluida la capacidad de buscar todas las propiedades de metadatos de [archivo)](document-metadata-fields-in-advanced-ediscovery.md)para refinar y limitar aún más los datos de caso a lo que es más relevante para el caso. También puede usar filtros de conjunto de revisión para aplicar rápidamente otras condiciones a los resultados de una consulta de búsqueda para refinar aún más esos resultados. 

   - [Crear y usar etiquetas](tagging-documents.md). Puede aplicar etiquetas a documentos de un conjunto de revisión para identificar cuáles responden (o no responden al caso) y, a continuación, usar esas etiquetas al crear consultas de búsqueda para incluir o excluir los documentos etiquetados. También puede etiquetar para determinar qué documentos exportar.

   - [Anota y redacta documentos](view-documents-in-review-set.md#annotate-view). Puede usar la herramienta de anotación en una revisión para anotar documentos y redactar contenido en documentos como producto de trabajo. Generamos una versión PDF de un documento anotado o redactado durante la revisión para reducir el riesgo de exportar la versión nativa no modificada del documento.

   - [Analizar datos de casos](analyzing-data-in-review-set.md). La funcionalidad de análisis en Advanced eDiscovery es eficaz. Después de ejecutar el análisis en los datos del conjunto de revisión, llevamos a cabo análisis como detección de duplicados cercanos, subprocesos de correo electrónico y temas que pueden ayudar a reducir el volumen de documentos que debe revisar. También generamos informes de Analytics que resumen el resultado de la ejecución de análisis. Como se explicó anteriormente, la ejecución de análisis también ejecuta el modelo de detección de privilegios [abogado-cliente](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model).

5. **Exportar y descargar datos de casos**. Un último paso después de recopilar, revisar y analizar datos de casos es exportarlos fuera de Advanced eDiscovery para revisión externa o para revisión por personas fuera del equipo de investigación. La exportación de datos es un proceso de dos pasos. El primer paso [](export-documents-from-review-set.md) es exportar datos fuera del conjunto de revisión y copiarlos en una ubicación de Azure Storage diferente (una proporcionada por Microsoft o una administrada por su organización). A continuación, Explorador de Azure Storage [para descargar](download-export-jobs.md) los datos en un equipo local. Además de los archivos de datos exportados, el contenido del paquete de exportación también contiene un informe de exportación, un informe de resumen y un informe de errores.

## <a name="advanced-ediscovery-architecture"></a>Advanced eDiscovery arquitectura

Este es un diagrama de arquitectura que muestra el flujo de trabajo completo de Advanced eDiscovery en un entorno de una sola ubicación geográfica y en un entorno multige geográfico, y el flujo de datos de un extremo a otro alineado con el modelo de referencia de detección electrónica [.](overview-ediscovery-20.md#advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model)

[![Póster del modelo: Advanced eDiscovery arquitectura en Microsoft 365](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Ver como una imagen](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Descargar como archivo PDF](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Descargar como archivo Visio archivo](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)
