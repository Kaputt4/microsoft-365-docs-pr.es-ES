---
title: Configurar versiones históricas en Advanced eDiscovery
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
description: Use versiones históricas en Advanced eDiscovery para recopilar contenido de todas las versiones de documentos almacenados en SharePoint y OneDrive.
ms.openlocfilehash: 5ecbb9c9216482223ce756aed5742e25a3b851a1
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61936659"
---
# <a name="set-up-historical-versions-in-advanced-ediscovery-preview"></a>Configurar versiones históricas en Advanced eDiscovery (versión preliminar)

La característica de versiones históricas de Advanced eDiscovery permite a los administradores de exhibición de documentos electrónicos de la organización buscar y recopilar contenido de todas las versiones de documentos almacenados en SharePoint Online y OneDrive para la Empresa. A continuación, puede agregar ese contenido a un conjunto de revisión para su análisis y revisión. Esto le ayuda a buscar y revisar contenido de una versión específica de un documento que puede ser relevante para un caso o investigación, incluso si la versión más reciente del mismo documento no contiene la información relevante.

Para admitir la funcionalidad de versiones históricas en Advanced eDiscovery, SharePoint administradores deben habilitar el control de versiones para los sitios de su organización. A continuación, cuando los usuarios modifican documentos SharePoint o OneDrive, las versiones regulares implícitas se crean cuando se guarda el documento (o se guarda automáticamente). SharePoint control de versiones permite realizar un seguimiento de la actividad realizada en SharePoint (incluidos documentos, eventos y tareas). Esta funcionalidad de control de versiones deja un rastro de auditoría que puede proporcionar pruebas en investigaciones legales. Estas versiones anteriores de un documento están disponibles para la organización, que puede estar obligada a compartir dichas versiones que tienen contenido confidencial o relevante durante la detección judicial en un asunto legal.

Después de que un administrador de exhibición de documentos electrónicos active las versiones históricas de la organización y la active para sitios de SharePoint específicos, el servicio de inserción de contenido de SharePoint rastrea todas las versiones principales y secundarias de los documentos en los sitios activados y, a continuación, envía esas versiones para la indización. Una vez completado el proceso de rastreo e indización, los documentos y sus versiones están disponibles para la búsqueda de exhibición de documentos electrónicos. Siempre que se pueda tener acceso a una versión específica (por historial de versiones), esa versión se podrá detectar en una búsqueda de Advanced eDiscovery colección.

## <a name="set-up-historical-versions"></a>Configurar versiones históricas

Para habilitar las versiones históricas en Advanced eDiscovery, la organización debe activarla y, a continuación, activar sitios específicos para que todas las versiones de documentos almacenadas en esos sitios se indexe para la búsqueda. Antes de configurar Advanced eDiscovery versiones históricas, debe habilitar la compatibilidad con el control de versiones en SharePoint.

### <a name="step-1-turn-on-versioning-in-sharepoint"></a>Paso 1: Activar el control de versiones en SharePoint

El primer paso es activar el control de versiones en SharePoint Online para que se conserven todas las versiones de un documento. Para obtener instrucciones, vea [Control de versiones en SharePoint](/microsoft-365/community/versioning-basics-best-practices).

### <a name="step-2-turn-on-historical-versions"></a>Paso 2: Activar versiones históricas

El siguiente paso es activar las versiones históricas en Advanced eDiscovery. Para activar las versiones históricas de la organización, una persona debe ser un administrador global o un administrador de exhibición de documentos electrónicos (miembro del subgrupo administrador de exhibición de documentos electrónicos en el grupo de roles administrador de exhibición de documentos electrónicos). Una vez activadas las versiones históricas, se aplicará a toda la organización.

> [!IMPORTANT]
> Después de activar las versiones históricas, no podrá desactivarla durante la vista previa pública. Podrás desactivarla después de que se publicaron versiones históricas para la disponibilidad general.

1. En el Centro de cumplimiento de Microsoft 365, vaya [a Advanced eDiscovery](https://go.microsoft.com/fwlink/p/?linkid=2173764)y, a continuación, haga clic **en Advanced eDiscovery configuración**.

   ![Seleccionar Advanced eDiscovery configuración](..\media\HistoricalVersions1.png)

2. En la **Configuración,** seleccione la pestaña Versiones históricas **(versión preliminar)** y, a continuación, cambie el control de inquilino Versiones históricas **a** activar.

   ![Activar la alternancia para habilitar versiones históricas](..\media\HistoricalVersions2.png)

   Se muestra una advertencia que indica que no podrá desactivar las versiones históricas. Como se ha indicado anteriormente, no podrá desactivar las versiones históricas hasta que la característica se haya publicado para la disponibilidad general.

3. Haga **clic en Sí** para activar las versiones históricas.

### <a name="step-3-activate-sharepoint-sites"></a>Paso 3: Activar SharePoint sitios

Después de activar las versiones históricas de la organización, el último paso es activar los sitios SharePoint para admitir versiones históricas. Al activar un sitio (agregándole a una  lista de sitios en la pestaña Versiones históricas), el sitio se vuelve a buscar y todas las versiones de documentos almacenados en ese sitio se indizan para su búsqueda.

> [!NOTE]
> Hay un límite de 100 activaciones de sitios por organización durante la versión preliminar pública de versiones históricas. Una activación se cuenta con este límite siempre que habilite o deshabilite un sitio para versiones históricas. Si habilita varios sitios, cada sitio se cuenta como una única activación. El número total de activaciones se muestra en la **pestaña Versiones históricas.**

1. En la **pestaña Versiones históricas** de la Advanced eDiscovery  **Configuración,** haga clic en Habilitar para activar sitios para versiones históricas.

   ![Haga clic en Habilitar para activar sitios para versiones históricas](..\media\HistoricalVersions3.png)  

   Se muestra una página desplegable que contiene una lista de todos los SharePoint de la organización.

2. Seleccione un sitio para activar y, a continuación, haga clic en **Habilitar** para activarlo para versiones históricas. Puede usar el cuadro de búsqueda para buscar un sitio específico.

   Se muestra una advertencia que indica que las versiones de documentos del sitio se indizarán y este proceso de indización llevará algún tiempo antes de que las versiones estén listas para buscarse. La advertencia también indica que no podrá deshabilitar las versiones históricas del sitio seleccionado durante 30 días.

3. Haga **clic en** Sí para activar el sitio para versiones históricas.

   ![Se muestran el sitio activado y el número de activaciones de sitio](..\media\HistoricalVersions4.png)  

   El sitio se agrega a la lista de sitios activados. También se actualiza el contador que muestra el número de activaciones de sitio.

4. Repita los pasos anteriores para cada sitio que desee activar para las versiones históricas.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes.

**¿En qué se diferencian las versiones históricas de la opción de "recopilar todas las versiones" cuando se confirma un borrador de colección en un conjunto de revisión?**

Actualmente, solo se indiza la versión más reciente de los documentos para la búsqueda. Esto significa que al ejecutar una colección borrador, solo se buscan las versiones más recientes de los documentos. Si un documento coincide con la consulta de palabras clave de la colección, se devuelve en los resultados de la colección. Sin embargo, si la versión más reciente de un documento no coincide con una consulta de búsqueda, no se devolverá el evento si las versiones anteriores del documento contienen la palabra clave. Para ayudar a mitigar esta situación, Advanced eDiscovery permite recopilar todas las versiones del documento al confirmar una colección [en un conjunto de revisión](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set). Esto significa que cualquier versión anterior que pueda contener la palabra clave se agregará al conjunto de revisión.

Las versiones históricas son diferentes y más eficientes que "recopilar todas las versiones" porque al activar un sitio, todas las versiones de un documento (y no solo la última versión) se indizan para la búsqueda. El resultado es que si una versión anterior de un documento contiene una palabra clave que coincide con la consulta de búsqueda, la colección la devolverá.

**Cuando las versiones históricas están habilitadas para un sitio, ¿afecta al rendimiento del sitio?**

No. Una vez habilitadas las versiones históricas para un sitio, el rendimiento del sitio será el mismo que antes de habilitar el sitio. Los procesos de rastreo e indización que se realizan en el sitio después de habilitarse se producirán a un ritmo más lento y se realizarán durante las horas de baja actividad. Al habilitar versiones históricas para un sitio, se inicia un proceso de relleno, que busca todas las versiones de documentos en el sitio y, a continuación, envía esas versiones al índice. Según el número de versiones de documento para el sitio, este proceso de relleno podría afectar al estado del servicio. Hemos mitigado este impacto potencial de las siguientes maneras:

- We make the best effort to process these versions during off-peak hours.

- Procesamos versiones de documentos en nuestras colas de prioridad más baja, lo que permite que la mayoría de los recursos de servicio se deleguen a los cambios del usuario.

**¿Cuánto tiempo tengo que esperar después de que se active un sitio hasta que todas las versiones históricas de documentos de ese sitio estén indizadas y disponibles para la búsqueda de exhibición de documentos electrónicos?**

Basándonos en el número de documentos de un sitio y el número promedio de versiones por documento, intentamos calcular el número total de archivos por sitio. Basándose en esto, una estimación del tiempo que puede tardar en indexar es la siguiente:

`Number of versions / (Processing rate of 100,000 files per day ) + .5 days = Total number of days to process a site`

El medio día se agrega como búfer, ya que la indización de versiones en el sitio está optimizada para ejecutarse durante las horas de mayor actividad.

Por ejemplo, si el número total de documentos y todas las versiones de un sitio es de 150 000, se tardarán al menos dos días en procesar el sitio para las versiones históricas:

`150,000 files/100,000 files per day + .5 days = 2 days`

**¿Por qué no se recomienda activar o desactivar sitios para versiones históricas con frecuencia?**

Al desactivar un sitio activado previamente, se desencadena un proceso de limpieza. Este proceso llevará tiempo completarse. Si se vuelve a activar ese mismo sitio, se debe volver a ejecutar el proceso de reindexación del sitio. Tanto los procesos de limpieza como los procesos de reposición consumen mucho tiempo y recursos. Por lo tanto, le recomendamos que considere cuidadosamente y planee los sitios que desea activar para la versión histórica para evitar la activación y desactivación repetidas de versiones históricas de un sitio.
