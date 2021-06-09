---
title: Agregar custodios a un Advanced eDiscovery caso
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
ms.assetid: ''
description: Obtenga información sobre cómo usar la herramienta de administración de custodia integrada en Advanced eDiscovery coordinar los flujos de trabajo e identificar orígenes de datos relevantes en un caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740347"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>Agregar custodios a un Advanced eDiscovery caso

Use la herramienta de administración de custodia integrada en Advanced eDiscovery para coordinar los flujos de trabajo en torno a la administración de custodios e identificación de orígenes de datos relevantes y custodiales asociados con un caso. Al agregar un custodio, el sistema puede identificar y colocar automáticamente una retención en su Exchange buzón y OneDrive para la Empresa cuenta. Durante el proceso de detección de la investigación, también puede identificar otros orígenes de datos (como buzones, sitios o Teams) a los que un custodio ha accedido o contribuido. En esta situación, puede usar la herramienta de administración de custodia para asociar esos orígenes de datos a un custodio específico. Después de agregar custodios a un caso y asociar otro origen de datos con ellos, puede conservar rápidamente los datos y buscar en los datos de custodia.

Puede agregar y administrar custodios en Advanced eDiscovery casos en cuatro pasos:

1. Identifique a los custodios.

2. Elija ubicaciones de datos de custodia.

3. Configure las opciones de retención.

4. Revise a los custodios y complete el proceso.

   [![Ficha Orígenes en Advanced eDiscovery caso ](../media/AeD-Sources-Tab.png)](../media/AeD-Sources-Tab.png#lightbox)

## <a name="make-sure-you-have-the-necessary-permissions"></a>Asegúrese de que tiene los permisos necesarios

Para agregar custodios a un caso, debe ser miembro del grupo de roles administrador de exhibición de documentos electrónicos. Esto le proporciona los permisos necesarios para agregar custodios a un caso y colocar una retención en los orígenes de datos de custodia. Para más información, consulte [Asignar permisos de eDiscovery](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).

## <a name="step-1-identify-custodians"></a>Paso 1: Identificar custodios

1. Vaya a e inicie sesión con una cuenta de usuario a la que se han [https://compliance.microsoft.com](https://compliance.microsoft.com) asignado los permisos de exhibición de documentos electrónicos adecuados.

2. En el panel de navegación izquierdo del Centro de cumplimiento de Microsoft 365, haga clic en **Mostrar todo** y, luego, seleccione **eDiscovery > Avanzado**.

3. En la **Advanced eDiscovery,** haga clic en la pestaña **Casos** y, a continuación, seleccione el caso al que desea agregar custodios.

4. Haga clic en **la pestaña Orígenes de** datos y, a continuación, haga clic en **Agregar** origen de datos Agregar  >  **nuevos custodios.**

5. Agregue uno o varios usuarios de la organización como custodios al caso escribiendo la primera parte del nombre o alias de una persona. Después de encontrar a la persona correcta, seleccione su nombre para agregarlo a la lista.

## <a name="step-2-choose-custodian-data-locations"></a>Paso 2: Elegir ubicaciones de datos de custodia

Después de seleccionar custodios, el sistema intenta identificar y comprobar automáticamente estos usuarios y sus orígenes de datos. Después de agregar custodios a la lista, la herramienta incluye automáticamente el buzón principal y OneDrive cuenta para cada custodio. Puede elegir no incluir estos orígenes de datos al agregar custodios al caso.

Además del buzón de un custodio y una cuenta de OneDrive, también puede asociar otras ubicaciones de datos a un administrador, como un sitio SharePoint o un equipo de Microsoft del que el custodio es miembro. Esto le permite conservar, recopilar, analizar y revisar contenido en otros orígenes de datos asociados con los custodios del caso.

Para anular la selección del buzón principal y OneDrive cuenta para un custodio:

1. Expanda el custodio para ver las ubicaciones de datos principales que se han asociado automáticamente a cada uno de los custodios.

2. Seleccione **Borrar** junto  a **Buzón** o OneDrive para quitar el buzón o la cuenta de OneDrive de un custodio para que no se asocie como ubicación de datos para este custodio.

   ![Configurar ubicaciones para asociar a un custodio](../media/ConfigureCustodianLocations.png)

Para asociar otros buzones, sitios, Teams o grupos Yammer a un administrador específico:

1. Expanda un custodio para mostrar los siguientes servicios para asociar ubicaciones de datos con el custodio. Haga **clic en** Editar junto a un servicio para agregar una ubicación de datos.

   - **Exchange:** se usa para asociar otros buzones al custodio. Escriba en el cuadro de búsqueda el nombre o el alias (un mínimo de tres caracteres) de los buzones de usuario o grupos de distribución. Seleccione los buzones que desea asignar al custodio y, a continuación, haga clic **en Agregar**.

   - **SharePoint:** se usa para asociar SharePoint sitios al custodio. Seleccione un sitio en la lista o busque un sitio escribiendo una dirección URL en el cuadro de búsqueda. Seleccione los sitios que desea asignar al custodio y, a continuación, haga clic **en Agregar**.

   - **Teams:** se usa para asignar el Microsoft Teams del que el custodio es miembro actualmente. Seleccione los equipos que desea asignar al custodio y, a continuación, haga clic **en Agregar**. Después de agregar un equipo, el sistema identifica y localiza automáticamente el buzón SharePoint sitio y grupo asociados a ese equipo y los asigna al administrador.

   - **Yammer:** se usa para asignar los grupos Yammer de los que el custodio es miembro actualmente. Seleccione los grupos que desea asignar al custodio y, a continuación, haga clic **en Agregar**. Después de agregar un equipo, el sistema identifica y localiza automáticamente el sitio SharePoint y el buzón de grupo asociados a ese grupo y los asigna al custodio.

   > [!NOTE]
   > Puede usar  los selectores de Exchange y **SharePoint** para asociar otros equipos o grupos de Yammer (de los que un custodio no es miembro) a un custodio. Para ello, debe agregar el buzón y el sitio asociados con cada grupo o Yammer grupo.

2. Puede ver el número total de buzones, sitios, Teams y grupos de Yammer asignados a cada custodio expandiendo cada uno de los custodios de la tabla. Cuando haya finalizado las ubicaciones de datos asignadas para cada custodio, estas asociaciones se mantendrán y usarán durante las fases de recopilación, procesamiento y revisión del flujo de trabajo Advanced eDiscovery usuario.

3. Después de agregar custodios y configurar sus ubicaciones de datos, haga clic en **Siguiente** para ir a la **página Configuración de retención.**  

## <a name="step-3-configure-hold-settings"></a>Paso 3: Configurar las opciones de retención

 Después de finalizar los custodios y sus ubicaciones de datos, puede poner algunos o todos los custodios en espera. Al poner a un custodio en espera, todo el contenido de todas las ubicaciones de contenido asociadas con el custodio se conserva hasta que quite la retención o libere al custodio de la retención. En algunos casos, es posible que desee agregar custodios a un caso sin ponerlos en espera.

Para poner en espera a los custodios y orígenes de datos:

1. En la **página Configuración de** retención, puede aplicar una retención a los custodios individuales seleccionando la casilla debajo de la **columna** Retención.

   Como alternativa, puede poner en espera a todos  los custodios activando la casilla Detención en la parte superior de la columna.

2. Compruebe las selecciones de retención de custodia y, a continuación, haga clic **en Siguiente**.

   > [!NOTE]
   > Si no coloca una retención en un custodio, el custodio y sus orígenes de datos asociados se agregarán al caso, pero el contenido de esos orígenes de datos no se conservará mediante la retención asociada al caso.

## <a name="step-4-review-the-custodians-and-complete-the-process"></a>Paso 4: Revisar los custodios y completar el proceso

Antes de agregar realmente los custodios al caso, puede revisar la lista de custodios, las ubicaciones de datos asignadas a ellos y la configuración de retención.

1. Compruebe y revise todos los orígenes de datos y la configuración de retención asociada a cada uno de los custodios de la tabla. Si es necesario, vuelve a las páginas **Identificar custodia o** Configuración de **retención** para realizar cualquier cambio.

2. Haga **clic en** Enviar para agregar custodios y sus ubicaciones de datos al caso y aplicar toda la configuración de retención de custodia.

   Los nuevos custodios se agregan al caso y se muestran en la **pestaña Orígenes de** datos.

   [![Custodios enumerados en la pestaña Orígenes de datos ](../media/DataSourcesTab.png)](../media/DataSourcesTab.png#lightbox)
