---
title: Agregar administradores a un caso de eDiscovery avanzado
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
description: Obtenga información sobre cómo usar la herramienta de administración de administradores integrada en eDiscovery avanzado para coordinar los flujos de trabajo e identificar orígenes de datos relevantes en un caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740347"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>Agregar administradores a un caso de eDiscovery avanzado

Use la herramienta de administración de administradores integrada en eDiscovery avanzado para coordinar los flujos de trabajo en torno a la administración de administradores e identificación de orígenes de datos relevantes y de custodia asociados a un caso. Cuando agrega un administrador, el sistema puede identificar y colocar automáticamente una retención en su buzón de Exchange y en su cuenta de OneDrive para la Empresa. Durante el proceso de detección de la investigación, es posible que también identifique otros orígenes de datos (como buzones, sitios o Teams) a los que un administrador ha accedido o al que ha colaborado. En esta situación, puede usar la herramienta de administración de administradores para asociar esos orígenes de datos a un administrador específico. Después de agregar administradores a un caso y asociar otros orígenes de datos con ellos, puede conservar rápidamente los datos y buscar en los datos de custodia.

Puede agregar y administrar administradores en casos de eDiscovery avanzado en cuatro pasos:

1. Identifique a los administradores.

2. Elija ubicaciones de datos de administrador.

3. Configure las opciones de retención.

4. Revise los administradores y complete el proceso.

   [![Pestaña Orígenes en caso de eDiscovery avanzado ](../media/AeD-Sources-Tab.png)](../media/AeD-Sources-Tab.png#lightbox)

## <a name="make-sure-you-have-the-necessary-permissions"></a>Asegúrese de que tiene los permisos necesarios

Para agregar administradores a un caso, debe ser miembro del grupo de roles administrador de exhibición de documentos electrónicos. Esto le proporciona los permisos necesarios para agregar administradores a un caso y retener los orígenes de datos de administrador. Para obtener más información, consulte [Asignar permisos de exhibición de documentos electrónicos](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).

## <a name="step-1-identify-custodians"></a>Paso 1: Identificar administradores

1. Vaya e inicie sesión con una cuenta de usuario a la que se hayan asignado los permisos de exhibición de documentos [https://compliance.microsoft.com](https://compliance.microsoft.com) electrónicos adecuados.

2. En el panel de navegación izquierdo del Centro de cumplimiento de Microsoft 365, haga clic en Mostrar todo y, a continuación, haga clic en **eDiscovery > avanzado.**

3. En la **página eDiscovery**  avanzado, haga clic en la pestaña Casos y, a continuación, seleccione el caso al que desea agregar administradores.

4. Haga clic en **la pestaña Orígenes de** datos y, a continuación, haga clic en Agregar origen **de** datos Agregar  >  **nuevos administradores.**

5. Agregue uno o más usuarios de su organización como administradores al caso escribiendo la primera parte del nombre o alias de una persona. Después de encontrar a la persona correcta, seleccione su nombre para agregarlo a la lista.

## <a name="step-2-choose-custodian-data-locations"></a>Paso 2: Elegir ubicaciones de datos de administrador

Después de seleccionar administradores, el sistema intenta identificar y comprobar automáticamente estos usuarios y sus orígenes de datos. Después de agregar administradores a la lista, la herramienta incluye automáticamente el buzón principal y la cuenta de OneDrive para cada administrador. Puede optar por no incluir estos orígenes de datos al agregar administradores al caso.

Además del buzón de un administrador y una cuenta de OneDrive, también puede asociar otras ubicaciones de datos a un administrador, como un sitio de SharePoint o un equipo de Microsoft del que el administrador es miembro. Esto le permite conservar, recopilar, analizar y revisar el contenido de otros orígenes de datos asociados con los administradores del caso.

Para anular la selección del buzón principal y la cuenta de OneDrive para un administrador:

1. Expanda el administrador para ver las ubicaciones de datos principales que se han asociado automáticamente a cada administrador.

2. Seleccione **Borrar** junto a **Buzón** de correo o **OneDrive** para quitar el buzón de un administrador o cuenta de OneDrive para que no se asocie como ubicación de datos para este administrador.

   ![Configurar ubicaciones para asociar a un administrador](../media/ConfigureCustodianLocations.png)

Para asociar otros buzones, sitios, Teams o grupos de Yammer a un administrador específico:

1. Expanda un administrador para mostrar los siguientes servicios para asociar ubicaciones de datos con el administrador. Haga **clic en** Editar junto a un servicio para agregar una ubicación de datos.

   - **Exchange:** se usa para asociar otros buzones al administrador. Escriba en el cuadro de búsqueda el nombre o el alias (un mínimo de tres caracteres) de los buzones de usuario o grupos de distribución. Seleccione los buzones que desea asignar al administrador y, a continuación, haga clic **en Agregar**.

   - **SharePoint:** se usa para asociar sitios de SharePoint al administrador. Seleccione un sitio en la lista o busque un sitio escribiendo una dirección URL en el cuadro de búsqueda. Seleccione los sitios que desea asignar al administrador y, a continuación, haga clic en **Agregar**.

   - **Teams:** se usa para asignar a Microsoft Teams el administrador del que es miembro actualmente. Seleccione los equipos que desea asignar al administrador y, a continuación, haga clic **en Agregar**. Después de agregar un equipo, el sistema identifica y localiza automáticamente el sitio de SharePoint y el buzón de grupo asociados a ese equipo y los asigna al administrador.

   - **Yammer:** se usa para asignar los grupos de Yammer de los que el administrador es miembro actualmente. Seleccione los grupos que desea asignar al administrador y, a continuación, haga clic en **Agregar**. Después de agregar un equipo, el sistema identifica y localiza automáticamente el sitio de SharePoint y el buzón de grupo asociados a ese grupo y los asigna al administrador.

   > [!NOTE]
   > Puede usar los selectores de ubicación de **Exchange** y **SharePoint** para asociar otros equipos o grupos de Yammer (de los que un administrador no es miembro) a un administrador. Para ello, debe agregar el buzón y el sitio asociados con cada equipo o grupo de Yammer.

2. Puede ver el número total de buzones, sitios, equipos y grupos de Yammer asignados a cada administrador expandiendo cada uno de los administradores en la tabla. Cuando haya finalizado las ubicaciones de datos asignadas para cada administrador, estas asociaciones se mantendrán y usarán durante las fases de recopilación, procesamiento y revisión en el flujo de trabajo de eDiscovery avanzado.

3. Después de agregar administradores y configurar sus ubicaciones de datos, haga clic en Siguiente **para** ir a la página Configuración **de retención.**  

## <a name="step-3-configure-hold-settings"></a>Paso 3: Configurar la retención

 Una vez que haya finalizado los administradores y sus ubicaciones de datos, puede poner algunos o todos los administradores en retención. Cuando se coloca a un administrador en retención, todo el contenido de todas las ubicaciones de contenido asociadas con el administrador se conserva hasta que se quita la retención o se libera al administrador de la retención. En algunos casos, es posible que desee agregar administradores a un caso sin ponerlos en retención.

Para poner los administradores y los orígenes de datos en retención:

1. En la **página Configuración de** retención, puede aplicar una retención a los administradores individuales activando la casilla de la columna **Retención.**

   Como alternativa, puede poner a todos los administradores en retención activando la casilla Detención en la parte superior de la columna. 

2. Compruebe las selecciones de retención de administrador y, a continuación, haga clic en **Siguiente**.

   > [!NOTE]
   > Si no coloca una retención en un administrador, el administrador y sus orígenes de datos asociados se agregarán al caso, pero el contenido de esos orígenes de datos no se conservará por la retención asociada al caso.

## <a name="step-4-review-the-custodians-and-complete-the-process"></a>Paso 4: Revisar los administradores y completar el proceso

Antes de agregar realmente los administradores al caso, puede revisar la lista de administradores, las ubicaciones de datos asignadas a ellos y la configuración de retención.

1. Compruebe y revise todos los recuentos de orígenes de datos y la configuración de retención asociada con cada administrador de la tabla. Si es necesario, vuelva a  las páginas de configuración de identificación **de** administrador o retención para realizar cambios.

2. Haga **clic en** Enviar para agregar administradores y sus ubicaciones de datos al caso y aplicar toda la configuración de retención de administradores.

   Los nuevos administradores se agregan al caso y se muestran en la **pestaña Orígenes de** datos.

   [![Administradores enumerados en la pestaña Orígenes de datos ](../media/DataSourcesTab.png)](../media/DataSourcesTab.png#lightbox)
