---
title: Creación y administración de casos de eDiscovery (Premium) en Microsoft 365
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: 04/08/2022
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: En este artículo se describe cómo crear y administrar casos de Microsoft Purview eDiscovery (Premium). El primer paso es crear un caso y empezar a usar características y funcionalidad de eDiscovery (Premium).
ms.openlocfilehash: b8577a8d44cb6860cd595d3f2f13c731c290ba12
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66630375"
---
# <a name="create-and-manage-an-ediscovery-premium-case"></a>Creación y administración de un caso de eDiscovery (Premium)

Después de configurar Microsoft Purview eDiscovery (Premium) y [asignar permisos a los administradores de exhibición de documentos electrónicos](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions) de la organización que administrarán los casos, el siguiente paso es crear y administrar un caso.

En este artículo también se proporciona información general de alto nivel sobre el uso de casos para administrar el flujo de trabajo de eDiscovery (Premium) para un caso legal u otros tipos de investigaciones.

## <a name="create-a-case"></a>Crear un caso

Complete los pasos siguientes para crear un caso y agregar miembros. El usuario que crea el caso se agrega automáticamente como miembro. Los miembros del caso pueden acceder al caso en el portal de cumplimiento Microsoft Purview y realizar tareas de exhibición de documentos electrónicos (Premium).

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento</a> e inicie sesión con las credenciales de la cuenta de usuario a la que se han asignado permisos de exhibición de documentos electrónicos. Los miembros del grupo de roles Administración de la organización también pueden crear casos de exhibición de documentos electrónicos (Premium).

2. En el panel de navegación izquierdo del portal de cumplimiento, haga clic en **Mostrar todo** y, a continuación, seleccione **eDiscovery** > **Advanced** y, a continuación, seleccione la <a href="https://go.microsoft.com/fwlink/p/?linkid=2173764" target="_blank">pestaña **Casos**</a>.

3. Seleccione **Crear un caso**.

4. En la página flotante **Nuevo caso de exhibición de** documentos electrónicos, asigne un nombre (obligatorio) al caso y, a continuación, escriba un número de caso opcional y una descripción. El nombre del caso debe ser único en su organización.

5. Haga clic en **Guardar** para crear el caso.

   Se crea el nuevo caso y se muestra la pestaña **Configuración** del nuevo caso.

6. En el icono **Permisos de acceso &** de la pestaña **Configuración** , haga clic en **Seleccionar**.

7. En la página desplegable **Administrar este caso** , en **Administrar miembros**, haga clic en **Agregar** para agregar miembros al caso.

8. En la lista de personas, active la casilla situada junto a los nombres de las personas que desea agregar al caso. Como se explicó anteriormente, asegúrese de que a las personas que agregue al caso se les hayan asignado los permisos de exhibición de documentos electrónicos adecuados.

9. Después de seleccionar las personas que se van a agregar como miembros del caso, haga clic en **Agregar**.

10. En la página desplegable **Administrar este caso**, haga clic en **Guardar** para guardar la nueva lista de miembros del caso.

11. Haga clic en la pestaña **Inicio** para ir a la página principal del caso.

## <a name="manage-the-workflow"></a>Administrar el flujo de trabajo

Para empezar a usar eDiscovery (Premium), este es un flujo de trabajo básico que se alinea con [las prácticas comunes de eDiscovery](advanced-ediscovery-edrm.md). En cada uno de estos pasos, también resaltaremos algunas funciones extendidas de eDiscovery (Premium) que puede explorar.

![Flujo de trabajo de eDiscovery (Premium).](../media/AeDWorkflow.png)

1. **[Agregue custodios](add-custodians-to-case.md) y [orígenes de datos que no sean de custodia](non-custodial-data-sources.md) al caso**. El primer paso después de crear un caso es agregar custodios. Un *custodio* es una persona que tiene control administrativo de un documento o archivo electrónico que puede ser relevante para el caso. Además, puede agregar orígenes de datos que no están asociados a un usuario específico, pero que pueden ser relevantes para el caso.

   Estas son algunas cosas que suceden (o que puede hacer) al agregar custodios a un caso:

   - Los datos del buzón de Exchange del custodio, la cuenta de OneDrive y cualquier grupo de Microsoft Teams o Yammer del que sea miembro el custodio se pueden "marcar" como datos de custodia en el caso.
  
   - Los datos del custodio se vuelven a indexar (mediante un proceso denominado *Indexación avanzada*). Esto ayuda a optimizar la búsqueda en el paso siguiente.
  
   - Puede retener los datos del custodio. Esto conserva los datos que pueden ser relevantes para el caso durante la investigación.
  
   - Puede asociar otros orígenes de datos a un custodio (por ejemplo, puede asociar un sitio de SharePoint o un grupo de Microsoft 365 a un custodio) para que estos datos se puedan volver a indexar, colocar en espera y buscar, al igual que los datos del buzón del custodio o la cuenta de OneDrive.

   - Puede usar el [flujo de trabajo de comunicaciones](managing-custodian-communications.md) en eDiscovery (Premium) para enviar una notificación de suspensión legal a los custodios.

2. **[Recopilar contenido relevante de orígenes de datos](create-draft-collection.md)**. Después de agregar custodios y orígenes de datos que no son de custodia a un caso, use la herramienta de colecciones integradas para buscar en estos orígenes de datos contenido que pueda ser relevante para el caso. Las palabras clave, las propiedades y las condiciones se usan para [crear consultas de búsqueda](building-search-queries.md) que devuelven resultados de búsqueda con los datos que probablemente sean relevantes para el caso. También puede:

   - Vea [las estadísticas de recopilación](collection-statistics-reports.md) que pueden ayudarle a refinar una colección para restringir los resultados.

   - Obtenga una vista previa de un ejemplo de la colección para comprobar rápidamente si se encuentran los datos pertinentes.

   - Revise una consulta y vuelva a ejecutar la colección.

3. **[Confirme la colección en un conjunto de revisión](commit-draft-collection.md)**. Una vez que haya configurado y comprobado que una búsqueda devuelve los datos deseados, el siguiente paso es agregar los resultados de la búsqueda a un conjunto de revisión. Al agregar datos a un conjunto de revisión, los elementos se copian de su ubicación original en una ubicación segura de Azure Storage. Los datos se vuelven a indexar para optimizarlos para realizar búsquedas exhaustivas y rápidas al revisar y analizar elementos del conjunto de revisión. Además, también puede [agregar datos que no sean Office 365 a un conjunto de revisión](load-non-office-365-data-into-a-review-set.md).

   También hay un tipo especial de conjunto de revisión al que puede agregar datos, denominado *conjunto de revisión de conversaciones*. Estos tipos de conjuntos de revisiones proporcionan funcionalidades de reconstrucción de conversaciones para reconstruir, revisar y exportar conversaciones en subprocesos como las de Microsoft Teams. Para obtener más información, vea [Revisar conversaciones en eDiscovery (Premium).](conversation-review-sets.md)

4. **Revise y analice los datos de un conjunto de revisión**. Ahora que los datos están en un conjunto de revisión, puede usar una amplia variedad de herramientas y funcionalidades para ver y analizar los datos del caso con el objetivo de reducir el conjunto de datos a lo más relevante para el caso que está investigando. Esta es una lista de algunas herramientas y funcionalidades que puede usar durante este proceso.

   - [Ver documentos](view-documents-in-review-set.md). Esto incluye la visualización de los metadatos de cada documento en un conjunto de revisión y la visualización del documento en su versión nativa o en su versión de texto.

   - [Cree consultas y filtros](review-set-search.md). Las consultas de búsqueda se crean mediante diversos criterios de búsqueda (incluida la capacidad de buscar en todas las [propiedades de metadatos de archivo](document-metadata-fields-in-advanced-ediscovery.md) para refinar y seleccionar aún más los datos del caso en lo que es más relevante para el caso. También puede usar filtros de conjunto de revisión para aplicar rápidamente otras condiciones a los resultados de una consulta de búsqueda para refinar aún más esos resultados. 

   - [Cree y use etiquetas](tagging-documents.md). Puede aplicar etiquetas a los documentos de un conjunto de revisión para identificar cuáles responden (o no responden al caso) y, a continuación, usar esas etiquetas al crear consultas de búsqueda para incluir o excluir los documentos etiquetados. También puede etiquetar para determinar qué documentos exportar.

   - [Anotación y redacción de documentos](view-documents-in-review-set.md#annotate-view). Puede usar la herramienta de anotación en una revisión para anotar documentos y redactar contenido en documentos como producto de trabajo. Generamos una versión EN PDF de un documento anotado o redactado durante la revisión para reducir el riesgo de exportar la versión nativa no promulgada del documento.

   - [Analizar datos de casos](analyzing-data-in-review-set.md). La funcionalidad de análisis de eDiscovery (Premium) es eficaz. Después de ejecutar análisis en los datos del conjunto de revisión, se realizan análisis como la detección casi duplicada, el subproceso de correo electrónico y los temas que pueden ayudar a reducir el volumen de documentos que tiene que revisar. También generamos informes de Analytics que resumen el resultado de la ejecución de análisis. Como se explicó anteriormente, la ejecución de análisis también ejecuta [el modelo de detección de privilegios abogado-cliente](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model).

5. **Exportación y descarga de datos de casos**. Un último paso después de recopilar, revisar y analizar datos de casos es exportarlos fuera de eDiscovery (Premium) para su revisión externa o para su revisión por personas ajenas al equipo de investigación. La exportación de datos es un proceso de dos pasos. El primer paso consiste en [exportar](export-documents-from-review-set.md) los datos del conjunto de revisión y copiarlos en otra ubicación de Azure Storage (una proporcionada por Microsoft o otra administrada por su organización). A continuación, use Explorador de Azure Storage para [descargar](download-export-jobs.md) los datos en un equipo local. Además de los archivos de datos exportados, el contenido del paquete de exportación también contiene un informe de exportación, un informe de resumen y un informe de errores.

## <a name="ediscovery-premium-architecture"></a>Arquitectura de eDiscovery (Premium)

Este es un diagrama de arquitectura que muestra el flujo de trabajo de un extremo a otro de eDiscovery (Premium) en un entorno geográfico único y en un entorno multigeográfico, y el flujo de datos de un extremo a otro que está alineado con el [modelo de referencia de detección electrónica](overview-ediscovery-20.md#ediscovery-premium-alignment-with-the-electronic-discovery-reference-model).

[![Póster del modelo: Arquitectura de eDiscovery (Premium) en Microsoft 365.](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Visualización como imagen](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Descargar como un archivo PDF](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Descarga como archivo de Visio](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)
