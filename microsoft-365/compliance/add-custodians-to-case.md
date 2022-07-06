---
title: Adición de custodios a un caso de exhibición de documentos electrónicos (Premium)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
description: Aprenda a usar la herramienta de administración de custodios integrada en Microsoft Purview eDiscovery (Premium) para coordinar los flujos de trabajo e identificar los orígenes de datos pertinentes en un caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4e7734e886651cb0169d5823a23790761791eb4e
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66640994"
---
# <a name="add-custodians-to-an-ediscovery-premium-case"></a>Adición de custodios a un caso de exhibición de documentos electrónicos (Premium)

Use la herramienta de administración de custodios integrada en Microsoft Purview eDiscovery (Premium) para coordinar los flujos de trabajo en torno a la administración de custodios y la identificación de orígenes de datos pertinentes y custodiales asociados a un caso. Al agregar un custodio, el sistema puede identificar y colocar automáticamente una suspensión en su buzón de Exchange y OneDrive para la Empresa cuenta. Durante el proceso de detección de la investigación, también puede identificar otros orígenes de datos (como buzones, sitios o Teams) a los que un custodio accedió o contribuyó. En esta situación, puede usar la herramienta de administración de custodios para asociar esos orígenes de datos a un custodio específico. Después de agregar custodios a un caso y asociar otro origen de datos con ellos, puede conservar rápidamente los datos y buscar en los datos de custodia.

Puede agregar y administrar custodios en casos de eDiscovery (Premium) en cuatro pasos:

1. Identifique a los custodios.

2. Elija ubicaciones de datos de custodio.

3. Configure los valores de suspensión.

4. Revise los custodios y complete el proceso.

## <a name="make-sure-you-have-the-necessary-permissions"></a>Asegúrese de que tiene los permisos necesarios.

Para agregar custodios a un caso, debe ser miembro del grupo de roles administrador de exhibición de documentos electrónicos. Esto le proporciona los permisos necesarios para agregar custodios a un caso y colocar una suspensión en los orígenes de datos de custodia. Para más información, consulte [Asignar permisos de eDiscovery](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).

## <a name="step-1-identify-custodians"></a>Paso 1: Identificación de custodios

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) e inicie sesión con una cuenta de usuario a la que se hayan asignado los permisos de exhibición de documentos electrónicos adecuados.

2. En el panel de navegación izquierdo de la portal de cumplimiento Microsoft Purview, seleccione [](https://go.microsoft.com/fwlink/p/?linkid=2173764) **eDiscovery eDiscovery** > **(Premium)** y seleccione la pestaña Casos.

3. Seleccione el caso al que desea agregar custodios.

4. Seleccione la pestaña **Orígenes de datos** y, a continuación, seleccione **Agregar origen de** >  datos **Agregar nuevos custodios**.

5. Agregue uno o varios usuarios de la organización como custodios al caso escribiendo la primera parte del nombre o alias de una persona. Se buscan usuarios activos e inactivos. Después de encontrar la persona correcta, seleccione su nombre para agregarlo a la lista. 

## <a name="step-2-choose-custodian-data-locations"></a>Paso 2: Elegir ubicaciones de datos de custodio

Después de seleccionar custodios, el sistema intenta identificar y comprobar automáticamente estos usuarios y sus orígenes de datos. Después de agregar custodios a la lista, la herramienta incluye automáticamente el buzón principal y la cuenta de OneDrive para cada usuario activo que se ha agregado como custodio. Si el usuario está inactivo, la herramienta solo identificará el buzón principal. Puede optar por no incluir estos orígenes de datos al agregar custodios al caso.

Además del buzón de un custodio y la cuenta de OneDrive, también puede asociar otras ubicaciones de datos a un custodio, como un sitio de SharePoint o un equipo de Microsoft al que pertenece el custodio. Esto le permite conservar, recopilar, analizar y revisar contenido en otros orígenes de datos asociados a los custodios del caso.

Para anular la selección del buzón principal y la cuenta de OneDrive para un custodio:

1. Expanda el custodio para ver las ubicaciones de datos principales que se han asociado automáticamente a cada custodio.

2. Seleccione **Borrar** junto a **Buzón** o **OneDrive** para quitar el buzón de un custodio o la cuenta de OneDrive de estar asociado como ubicación de datos para este custodio.

   ![Configure las ubicaciones para asociar a un custodio.](../media/ConfigureCustodianLocations.png)

Para asociar otros buzones de correo, sitios, teams o grupos de Yammer a un custodio específico:

1. Expanda un custodio para mostrar los siguientes servicios para asociar ubicaciones de datos con el custodio. Haga clic en **Editar** junto a un servicio para agregar una ubicación de datos.

   - **Exchange**: se usa para asociar otros buzones al custodio. Escriba en el cuadro de búsqueda el nombre o alias (un mínimo de tres caracteres) de los buzones de usuario o grupos de distribución. Seleccione los buzones que se van a asignar al custodio y, a continuación, haga clic en **Agregar**.

   - **SharePoint**: se usa para asociar sitios de SharePoint al custodio. Seleccione un sitio en la lista o busque un sitio escribiendo una dirección URL en el cuadro de búsqueda. Seleccione los sitios que se van a asignar al custodio y, a continuación, haga clic en **Agregar**. Si un usuario está inactivo, su sitio de OneDrive tendrá que agregarse como una ubicación adicional de SharePoint aquí. 

   - **Teams**: se usa para asignar a Microsoft Teams del que es miembro actualmente el custodio. Seleccione los equipos que se van a asignar al custodio y, a continuación, haga clic en **Agregar**. Después de agregar un equipo, el sistema identifica y localiza automáticamente el sitio de SharePoint y el buzón de grupo asociados a ese equipo y los asigna al custodio.

   - **Yammer**: se usa para asignar los grupos de Yammer de los que el custodio es miembro actualmente. Seleccione los grupos que se van a asignar al custodio y, a continuación, haga clic en **Agregar**. Después de agregar un equipo, el sistema identifica y localiza automáticamente el sitio y el buzón de grupo de SharePoint asociados a ese grupo y los asigna al custodio.

   > [!NOTE]
   > Puede usar los selectores de ubicación de **Exchange** y **SharePoint** para asociar cualquier buzón o sitio de su organización a un custodio. , esto incluye la asociación del buzón de correo y el sitio para un grupo de Microsoft Team o Yammer del que un custodio no es miembro. Para ello, debe agregar tanto el buzón como el sitio asociados a cada equipo o grupo de Yammer.

2. Puede ver el número total de buzones, sitios, equipos y grupos de Yammer asignados a cada custodio expandiendo cada custodio en la tabla. Cuando haya finalizado las ubicaciones de datos asignadas para cada custodio, estas asociaciones se mantendrán y usarán durante las fases de recopilación, procesamiento y revisión del flujo de trabajo de eDiscovery (Premium).

3. Después de agregar custodios y configurar sus ubicaciones de datos, haga clic en **Siguiente** para ir a la página **Configuración de suspensión** .  

## <a name="step-3-configure-hold-settings"></a>Paso 3: Configurar las opciones de suspensión

 Después de finalizar los custodios y sus ubicaciones de datos, puede poner a algunos o todos los custodios en espera. Cuando coloca un custodio en espera, todo el contenido de todas las ubicaciones de contenido asociadas al custodio se conserva hasta que quita la suspensión o libera al custodio de la retención. En algunos casos, es posible que desee agregar custodios a un caso sin ponerlos en espera.

Para poner en espera a los custodios y orígenes de datos:

1. En la página **Configuración de suspensión** , puede aplicar una retención a los custodios individuales seleccionando la casilla en la columna **Suspensión** .

   Como alternativa, puede colocar todos los custodios en espera si activa la casilla **Detención** en la parte superior de la columna.

2. Compruebe que el custodio mantiene las selecciones y, a continuación, haga clic en **Siguiente**.

   > [!NOTE]
   > Si no coloca una suspensión en un custodio, el custodio y sus orígenes de datos asociados se agregarán al caso, pero el contenido de esos orígenes de datos no se conservará mediante la retención asociada al caso.

## <a name="step-4-review-the-custodians-and-complete-the-process"></a>Paso 4: Revisar los custodios y completar el proceso

Antes de agregar realmente los custodios al caso, puede revisar la lista de custodios, las ubicaciones de datos asignadas a ellos y la configuración de suspensión.

1. Compruebe y revise todo el recuento de orígenes de datos y la configuración de suspensión asociada a cada custodio de la tabla. Si es necesario, vuelva a las páginas **Identificación del custodio** o **Configuración de suspensión** para realizar los cambios.

2. Haga clic en **Enviar** para agregar custodios y sus ubicaciones de datos al caso y aplicar toda la configuración de suspensión de custodia.

   Los nuevos custodios se agregan al caso y se muestran en la pestaña **Orígenes de datos** .

   [![Custodios que aparecen en la pestaña Orígenes de datos.](../media/DataSourcesTab.png) ](../media/DataSourcesTab.png#lightbox)
