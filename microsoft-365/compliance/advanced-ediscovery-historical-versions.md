---
title: Configuración de versiones históricas en eDiscovery (Premium)
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
ms.assetid: ''
description: Use versiones históricas de eDiscovery (Premium) para recopilar contenido de todas las versiones de documentos almacenados en SharePoint y OneDrive.
ms.openlocfilehash: a8f41cae51510ca26a63655101e304a455a47f0a
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67824849"
---
# <a name="set-up-historical-versions-in-ediscovery-premium-preview"></a>Configuración de versiones históricas en eDiscovery (Premium) (versión preliminar)

La característica de versiones históricas de eDiscovery (Premium) permite a los administradores de exhibición de documentos electrónicos de su organización buscar y recopilar contenido de todas las versiones de documentos almacenados en SharePoint Online y OneDrive para la Empresa. A continuación, puede agregar ese contenido a un conjunto de revisión para su análisis y revisión. Esto le ayuda a buscar y revisar el contenido de una versión específica de un documento que puede ser relevante para un caso o una investigación, incluso si la versión más reciente del mismo documento no contiene la información pertinente.

Para admitir la funcionalidad de versiones históricas en eDiscovery (Premium), los administradores de SharePoint deben habilitar el control de versiones para los sitios de su organización. A continuación, cuando los usuarios modifican documentos en SharePoint o OneDrive, se crean versiones regulares implícitas cuando se guarda el documento (o se guarda automáticamente). El control de versiones de SharePoint permite realizar un seguimiento de la actividad realizada en elementos de SharePoint (incluidos documentos, eventos y tareas). Esta funcionalidad de control de versiones deja un rastro de auditoría que puede proporcionar pruebas en las investigaciones legales. Estas versiones anteriores de un documento están disponibles para la organización, que pueden ser necesarias para compartir esas versiones que tienen contenido confidencial o relevante durante la detección judicial en un asunto legal.

Después de que un administrador de eDiscovery active las versiones históricas de la organización y, a continuación, la active para sitios específicos de SharePoint, el servicio de inserción de contenido de SharePoint rastrea todas las versiones principales y secundarias de los documentos en los sitios activados y, a continuación, envía esas versiones para la indexación. Una vez completado el proceso de rastreo e indexación, los documentos y sus versiones están disponibles para la búsqueda de eDiscovery. Siempre que se pueda acceder a una versión específica (por historial de versiones), esa versión se podrá detectar en una búsqueda de colección de eDiscovery (Premium).

## <a name="set-up-historical-versions"></a>Configurar versiones históricas

Para habilitar versiones históricas en eDiscovery (Premium), la organización tiene que activarla y activar sitios específicos para que todas las versiones de documentos almacenados en esos sitios se indexen para la búsqueda. Antes de configurar eDiscovery (Premium) para versiones históricas, debe habilitar la compatibilidad con el control de versiones en SharePoint.

### <a name="step-1-turn-on-versioning-in-sharepoint"></a>Paso 1: Activar el control de versiones en SharePoint

El primer paso es activar el control de versiones en SharePoint Online para que se conserven todas las versiones de un documento. Para obtener instrucciones, vea [Control de versiones en SharePoint](/microsoft-365/community/versioning-basics-best-practices).

### <a name="step-2-turn-on-historical-versions"></a>Paso 2: Activar versiones históricas

El siguiente paso es activar las versiones históricas en eDiscovery (Premium). Para activar las versiones históricas de su organización, una persona debe ser un administrador global o un administrador de exhibición de documentos electrónicos (miembro del subgrupo Administrador de exhibición de documentos electrónicos en el grupo de roles administrador de exhibición de documentos electrónicos). Una vez activadas las versiones históricas, se aplicará a toda la organización.

> [!IMPORTANT]
> Después de activar las versiones históricas, no podrá desactivarla durante la versión preliminar pública. Podrá desactivarla una vez publicadas las versiones históricas para disponibilidad general.

1. En el portal de cumplimiento Microsoft Purview, vaya a [eDiscovery (Premium)](https://go.microsoft.com/fwlink/p/?linkid=2173764) y, a continuación, haga clic en **configuración de eDiscovery (Premium).**

   ![Selección de la configuración de eDiscovery (Premium)](..\media\HistoricalVersions1.png)

2. En la página **Configuración** , seleccione la pestaña **Versiones históricas (versión preliminar)** y, a continuación, cambie el **control de inquilino Versiones históricas** a activado.

   ![Activar el botón de alternancia para habilitar las versiones históricas](..\media\HistoricalVersions2.png)

   Se muestra una advertencia que indica que no podrá desactivar las versiones históricas. Como se indicó anteriormente, no podrá desactivar las versiones históricas hasta que la característica se publique para la disponibilidad general.

3. Haga clic en **Sí** para activar las versiones históricas.

### <a name="step-3-activate-sharepoint-sites"></a>Paso 3: Activar sitios de SharePoint

Después de activar las versiones históricas de su organización, el último paso es activar sitios de SharePoint para admitir versiones históricas. Al activar un sitio (agregándolo a una lista de sitios en la pestaña **Versiones históricas** ), el sitio se vuelve a rastrear y todas las versiones de los documentos almacenados en ese sitio se indexan para la búsqueda.

> [!NOTE]
> Hay un límite de 100 activaciones de sitio por organización durante la versión preliminar pública de las versiones históricas. Una activación se cuenta con este límite cada vez que se habilita o deshabilita un sitio para las versiones históricas. Si habilita varios sitios, cada sitio se cuenta como una única activación. El número total de activaciones se muestra en la pestaña **Versiones históricas** .

1. En la pestaña **Versiones históricas** de la página **Configuración** de eDiscovery (Premium), haga clic en **Habilitar** para activar sitios para versiones históricas.

   ![Haga clic en Habilitar para activar sitios para versiones históricas](..\media\HistoricalVersions3.png)  

   Se muestra una página de control flotante que contiene una lista de todos los sitios de SharePoint de su organización.

2. Seleccione un sitio para activarlo y, a continuación, haga clic en **Habilitar** para activarlo en versiones históricas. Puede usar el cuadro de búsqueda para buscar un sitio específico.

   Se muestra una advertencia que indica que las versiones del documento en el sitio se indizarán y este proceso de indexación tardará algún tiempo antes de que las versiones estén listas para buscarse. La advertencia también indica que no podrá deshabilitar las versiones históricas del sitio seleccionado durante 30 días.

3. Haga clic en **Sí** para activar el sitio para las versiones históricas.

   ![Se muestran el sitio activado y el número de activaciones de sitio.](..\media\HistoricalVersions4.png)  

   El sitio se agrega a la lista de sitios activados. El contador que muestra el número de activaciones de sitio también se actualiza.

4. Repita los pasos anteriores para cada sitio que quiera activar para las versiones históricas.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**¿En qué se diferencian las versiones históricas que la opción de "recopilar todas las versiones" al confirmar una colección de borradores en un conjunto de revisión?**

Actualmente, solo se indexa la versión más reciente de los documentos para la búsqueda. Esto significa que cuando se ejecuta una colección de borradores, solo se buscan las versiones más recientes de los documentos. Si un documento coincide con la consulta de palabra clave de la colección, se devuelve en los resultados de la colección. Sin embargo, si la versión más reciente de un documento no coincide con una consulta de búsqueda, el documento no se devolverá si las versiones anteriores del documento contienen la palabra clave . Para ayudar a mitigar esta situación, eDiscovery (Premium) ofrece la capacidad de recopilar todas las versiones del documento al [confirmar una colección en un conjunto de revisión](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set). Esto significa que cualquier versión anterior que pueda contener la palabra clave se agregará al conjunto de revisión.

Las versiones históricas son diferentes y más eficaces que "recopilar todas las versiones", ya que al activar un sitio, todas las versiones de un documento (y no solo la última versión) se indizan para la búsqueda. El resultado es que si una versión anterior de un documento contiene una palabra clave que coincide con la consulta de búsqueda, la colección la devolverá.

**Cuando las versiones históricas están habilitadas para un sitio, ¿afecta al rendimiento del sitio?**

No. Una vez habilitadas las versiones históricas para un sitio, el rendimiento del sitio será el mismo que antes de que se habilitara el sitio. Los procesos de rastreo e indexación que se realizan en el sitio después de habilitarlo se producirán a una velocidad más lenta y se realizarán durante las horas fuera del pico. La habilitación de versiones históricas para un sitio iniciará un proceso de reposición, que busca todas las versiones de los documentos del sitio y, a continuación, envía esas versiones al índice. En función del número de versiones del documento para el sitio, este proceso de reposición podría afectar al estado del servicio. Hemos mitigado este posible impacto de las siguientes maneras:

- Hacemos el mejor esfuerzo para procesar estas versiones durante las horas de poca actividad.

- Procesamos las versiones de documentos en nuestras colas de prioridad más baja, lo que permite que la mayoría de los recursos de servicio se deleguen a los cambios del usuario.

**¿Cuánto tiempo tengo que esperar después de activar un sitio hasta que todas las versiones históricas de los documentos de ese sitio estén indexadas y disponibles para la búsqueda de exhibición de documentos electrónicos?**

En función del número de documentos de un sitio y del número medio de versiones por documento, intentamos calcular el número total de archivos por sitio. En función de esto, una estimación del tiempo que puede tardar en indexar es la siguiente:

`Number of versions / (Processing rate of 100,000 files per day ) + .5 days = Total number of days to process a site`

El medio día se agrega como búfer, ya que la indexación de versiones en el sitio está optimizada para ejecutarse durante las horas fuera del pico.

Por ejemplo, si el número total de documentos y todas las versiones de un sitio es de 150 000, el sitio tardará al menos dos días en procesar el sitio para las versiones históricas:

`150,000 files/100,000 files per day + .5 days = 2 days`

**¿Por qué no se recomienda activar o desactivar sitios con frecuencia para versiones históricas?**

Al desactivar un sitio activado anteriormente, se desencadena un proceso de limpieza. Este proceso tardará tiempo en completarse. Si ese mismo sitio se activa de nuevo, se debe volver a ejecutar el proceso de reindexación del sitio. Tanto los procesos de limpieza como de reposición consumen mucho tiempo y recursos. Por lo tanto, le recomendamos que tenga en cuenta y planee cuidadosamente qué sitios desea activar para la versión histórica, de modo que pueda evitar activar y desactivar repetidamente las versiones históricas de un sitio.
