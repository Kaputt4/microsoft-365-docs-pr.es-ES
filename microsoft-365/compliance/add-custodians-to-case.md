---
title: Agregar custodios a un caso de eDiscovery avanzado
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
description: Obtenga información sobre cómo usar la herramienta de administración de custodios integrada en eDiscovery avanzado para coordinar sus flujos de trabajo e identificar los orígenes de datos relevantes en un caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740347"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>Agregar custodios a un caso de eDiscovery avanzado

Use la herramienta de administración de custodios integrada en eDiscovery avanzado para coordinar sus flujos de trabajo en la administración de custodios y para identificar los orígenes de datos relevantes y relevantes asociados a un caso. Cuando se agrega un custodio, el sistema puede identificar y retener automáticamente el buzón de Exchange y la cuenta de OneDrive para la empresa. Durante el proceso de detección de la investigación, también puede identificar otros orígenes de datos (como buzones, sitios o equipos) a los que un custodio ha tenido acceso o ha contribuido. En esta situación, puede usar la herramienta de administración de custodios para asociar esos orígenes de datos a un custodio específico. Después de agregar custodios a un caso y asociar otro origen de datos con ellos, puede conservar rápidamente los datos y buscar en los datos de las privaciones.

Puede Agregar y administrar custodios en casos de eDiscovery avanzados en cuatro pasos:

1. Identificar a los custodios.

2. Elija ubicaciones de datos de custodios.

3. Configurar opciones de retención.

4. Revise los custodios y complete el proceso.

   [![Ficha orígenes en caso ](../media/AeD-Sources-Tab.png) de exhibición avanzada de documentos electrónicos](../media/AeD-Sources-Tab.png#lightbox)

## <a name="make-sure-you-have-the-necessary-permissions"></a>Asegúrese de que tiene los permisos necesarios

Para agregar custodios a un caso, debe ser miembro del grupo de roles eDiscovery Manager. Esto le proporcionará los permisos necesarios para agregar custodios a un caso y realizar una retención en los orígenes de datos de Private. Para obtener más información, consulte [Asignar permisos de exhibición de documentos electrónicos](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).

## <a name="step-1-identify-custodians"></a>Paso 1: identificar los custodios

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) e inicie sesión con una cuenta de usuario a la que se le hayan asignado los permisos de eDiscovery apropiados.

2. En el panel de navegación izquierdo del centro de cumplimiento de Microsoft 365, haga clic en **Mostrar todo** y, a continuación, en **eDiscovery > avanzadas**.

3. En la página **exhibición avanzada** de documentos electrónicos, haga clic en la pestaña **casos** y, a continuación, seleccione el caso al que desea agregar custodios.

4. Haga clic en la pestaña **orígenes** de datos y, a continuación, haga clic en **Agregar origen de datos**  >  **agregar nuevos custodios**.

5. Agregue uno o más usuarios de la organización como custodios al caso; para ello, escriba la primera parte del alias o el nombre de una persona. Una vez que haya encontrado la persona correcta, seleccione su nombre para agregarla a la lista.

## <a name="step-2-choose-custodian-data-locations"></a>Paso 2: elegir ubicaciones de datos de custodios

Después de seleccionar custodios, el sistema intenta identificar y verificar estos usuarios y sus orígenes de datos de forma automática. Después de agregar custodios a la lista, la herramienta incluye automáticamente el buzón principal y la cuenta de OneDrive para cada custodio. Puede elegir no incluir estos orígenes de datos al agregar custodios al caso.

Además del buzón de un custodio y de la cuenta de OneDrive, también puede asociar otras ubicaciones de datos a un custodio, como un sitio de SharePoint o un equipo de Microsoft en el que el custodio es miembro. Esto le permite preservar, recopilar, analizar y revisar el contenido de otros orígenes de datos asociados con los custodios del caso.

Para anular la selección del buzón de correo principal y la cuenta de OneDrive para un custodio:

1. Expanda el custodio para ver las ubicaciones de datos principales que se han asociado automáticamente a cada custodio.

2. Seleccione **Borrar** junto a **buzón** o **onedrive** para quitar que el buzón o la cuenta de onedrive de un custodio se asocie como una ubicación de datos para este custodio.

   ![Configurar ubicaciones para asociar a un custodio](../media/ConfigureCustodianLocations.png)

Para asociar otros buzones de correo, sitios, equipos o grupos de Yammer a un custodio específico:

1. Expanda un custodio para mostrar los siguientes servicios para asociar las ubicaciones de datos con el custodio. Haga clic en **Editar** junto a un servicio para agregar una ubicación de datos.

   - **Exchange**: se usa para asociar otros buzones al custodio. Escriba en el cuadro de búsqueda el nombre o el alias (un mínimo de tres caracteres) de los buzones de usuario o los grupos de distribución. Seleccione los buzones que desea asignar al custodio y, a continuación, haga clic en **Agregar**.

   - **SharePoint**: Use para asociar sitios de SharePoint con el custodio. Seleccione un sitio de la lista o busque un sitio escribiendo una dirección URL en el cuadro de búsqueda. Seleccione los sitios que desea asignar al custodio y, a continuación, haga clic en **Agregar**.

   - **Teams**: usar para asignar a Microsoft Teams el custodio es actualmente miembro de. Seleccione los equipos que desee asignar a custodio y, a continuación, haga clic en **Agregar**. Después de agregar un equipo, el sistema identifica y localiza automáticamente el sitio de SharePoint y el buzón de grupo asociados a dicho equipo y los asigna al custodio.

   - **Yammer**: Use para asignar los grupos de Yammer en los que el custodio es actualmente miembro. Seleccione los grupos que desee asignar a custodio y, a continuación, haga clic en **Agregar**. Después de agregar un equipo, el sistema identifica y localiza automáticamente el sitio de SharePoint y el buzón de grupo asociados a ese grupo y los asigna al custodio.

   > [!NOTE]
   > Puede usar los selectores de ubicación de **Exchange** y **SharePoint** para asociar otros equipos o grupos de Yammer (que un custodio no es miembro de) a un custodio. Para ello, tiene que agregar el buzón de correo y el sitio asociados con cada grupo de equipo o de Yammer.

2. Puede ver el número total de buzones de correo, sitios, equipos y grupos de Yammer asignados a cada custodio expandiendo cada custodio en la tabla. Una vez finalizadas las ubicaciones de datos asignadas para cada custodio, estas asociaciones se mantendrán y se usarán durante las fases de recopilación, procesamiento y revisión del flujo de trabajo avanzado de eDiscovery.

3. Después de agregar custodios y configurar sus ubicaciones de datos, haga clic en **siguiente** para ir a la página **configuración de retención** .  

## <a name="step-3-configure-hold-settings"></a>Paso 3: configurar opciones de retención

 Una vez que haya finalizado los custodios y sus ubicaciones de datos, puede poner algunos o todos los custodios en retención. Cuando se pone un custodio en espera, todo el contenido de todas las ubicaciones de contenido que están asociados con el custodio se conserva hasta que se quita la retención o se libera el custodio de la retención. En algunos casos, es posible que quiera agregar custodios a un caso sin ponerlos en retención.

Para poner los custodios y los orígenes de datos en espera:

1. En la página **configuración de suspensión** , puede aplicar una retención a los custodios individuales activando la casilla en la columna **retención** .

   Como alternativa, puede retener todos los custodios seleccionando la casilla " **suspender** " en la parte superior de la columna.

2. Compruebe las selecciones de retención de custodios y haga clic en **siguiente**.

   > [!NOTE]
   > Si no pone una retención en un custodio, el custodio y sus orígenes de datos asociados se agregarán al caso, pero el contenido de dichos orígenes de datos no se mantendrá en la retención asociada con el caso.

## <a name="step-4-review-the-custodians-and-complete-the-process"></a>Paso 4: revisar los custodios y completar el proceso

Antes de agregar realmente los custodios al caso, puede revisar la lista de custodios, las ubicaciones de datos que tienen asignadas y la configuración de retención.

1. Compruebe y Revise todos los recuentos de los orígenes de datos y la configuración de retención asociada a cada custodio de la tabla. Si es necesario, vuelva a la página identificar la **configuración** de **custodios** o de suspensión para realizar cambios.

2. Haga clic en **Enviar** para agregar custodios y sus ubicaciones de datos al caso y aplicar toda la configuración de retención.

   Los nuevos custodios se agregan al caso y se muestran en la pestaña **orígenes de datos** .

   [![Custodios que aparecen en la pestaña ](../media/DataSourcesTab.png) orígenes de datos](../media/DataSourcesTab.png#lightbox)
