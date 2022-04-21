---
title: Administrar custodios en un caso de exhibición de documentos electrónicos (Premium)
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
description: Obtenga información sobre cómo ver los detalles, editar y editar en bloque la lista de custodios en un caso de exhibición de documentos electrónicos (Premium).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2ab30e1343acd4718f80f816abc6ef850acf7215
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64996842"
---
# <a name="manage-custodians-in-an-ediscovery-premium-case"></a>Administrar custodios en un caso de exhibición de documentos electrónicos (Premium)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

La página **Custodios** de la pestaña **Orígenes de datos** de un caso de exhibición de documentos electrónicos (Premium) de Microsoft Purview contiene una lista de todos los custodios que se han agregado al caso. Después de agregar custodios a un caso, los detalles sobre cada custodio se recopilan automáticamente de Azure Active Directory y se pueden ver en eDiscovery (Premium).

## <a name="view-custodian-details"></a>Ver detalles del custodio

Para ver los detalles sobre un custodio, haga clic en el custodio de la lista de la pestaña **Custodios** . Se muestra una página de control flotante que contiene la siguiente información sobre el custodio.

![Detalles del custodio.](../media/CustodianDetails.PNG)

- Información de contacto

  - **Título**. El puesto del custodio.
  
  - **Nombre principal de usuario**. El nombre principal de usuario (UPN) del custodio, por ejemplo, AdeleV@contoso.onmicrosoft.com.
  
  - **Location**. La ubicación de la oficina en el lugar de negocios del custodio.
  
  - **Administrador**. El administrador del custodio. El administrador designado recibirá cualquier comunicación de escalación para este custodio.
  
  - **Departamento**. Nombre del departamento en el que trabaja el custodio.

- Información del caso

  - **Estado**. Estado del custodio dentro del caso. Un estado **activo** indica que el custodio forma parte del caso. Si un custodio se libera de un caso, el estado cambia a **Liberado**.
  
  - **Espera**. Indica si el custodio se ha colocado en espera.

- Ubicaciones de datos y almacenamiento de información

  ![Ubicaciones de datos de custodios y contienen información.](../media/CustodianHoldDetails.PNG)

  - **Ubicaciones de custodia**. Muestra el recuento y el tipo de orígenes de datos (buzones, sitios y Teams) que están asociados al custodio y forman parte del caso.

    - Cada ubicación de datos muestra su estado de suspensión. Valores posibles para el estado de suspensión: **En espera**, **No en espera** y **En curso**.

    - Si no ve un estado de suspensión para un origen de datos, compruebe el estado de la suspensión del custodio que aparece en la pestaña **Suspensión** para el caso. La suspensión del custodio identifica los orígenes de datos específicos que están en espera.

## <a name="edit-a-custodian"></a>Edición de un custodio

A medida que avanza el caso, es posible que descubra que puede haber orígenes de datos adicionales relevantes para un custodio específico y el caso. En otros escenarios, es posible que desee quitar determinados orígenes de datos que se han revisado y que se consideran no pertinentes.

Para actualizar los orígenes de datos asociados a un custodio:

1. Vaya a **eDiscovery > eDiscovery (Premium)** y abra el caso.
  
2. Haga clic en la pestaña **Orígenes de datos** .
  
3. Seleccione un custodio de la lista y, a continuación, haga clic en **Editar** en la página de control flotante.

    ![Editar orígenes de datos.](../media/EditCustodianDataSource.PNG)
  
4. Para agregar o quitar el buzón principal y OneDrive cuenta para el custodio:

    - Expanda el custodio para ver las ubicaciones de datos principales que se han asociado anteriormente con el custodio.

    - Haga clic en **Editar** junto a **Buzón** o **OneDrive** para agregar el buzón del custodio o OneDrive ubicación.

    - Seleccione **Borrar** junto a **Buzón de correo** o **OneDrive** para quitar el buzón de correo del custodio o OneDrive cuenta de estar asociado como una ubicación de datos para este custodio.

5. Para agregar o quitar otros buzones de correo, sitios, Teams o grupos de Yammer a un custodio específico, haga clic en **Editar** junto al servicio para agregar una ubicación de datos.

   - **Exchange**: use para asociar otros buzones al custodio. Escriba en el cuadro de búsqueda el nombre o alias (un mínimo de tres caracteres) de los buzones de usuario o grupos de distribución. Seleccione los buzones que se van a asignar al custodio y, a continuación, haga clic en **Agregar**.

   - **SharePoint**: use para asociar SharePoint sitios al custodio. Seleccione un sitio en la lista o busque un sitio escribiendo una dirección URL en el cuadro de búsqueda. Seleccione los sitios que se van a asignar al custodio y, a continuación, haga clic en **Agregar**.

   - **Teams**: use para asignar el Microsoft Teams del que el custodio es miembro actualmente. Seleccione los equipos que se van a asignar al custodio y, a continuación, haga clic en **Agregar**. Después de agregar un equipo, el sistema identifica y localiza automáticamente el sitio de SharePoint y el buzón de grupo asociados a ese equipo y los asigna al custodio.

   - **Yammer**: use para asignar los grupos de Yammer de los que el custodio es miembro actualmente. Seleccione los grupos que se van a asignar al custodio y, a continuación, haga clic en **Agregar**. Después de agregar un equipo, el sistema identifica y localiza automáticamente el buzón de correo SharePoint sitio y grupo asociado a ese grupo y los asigna al custodio.

   > [!NOTE]
   > Puede usar los selectores de ubicación **Exchange** y **SharePoint** para asociar a un custodio cualquier buzón o sitio de la organización, incluidos equipos o grupos de Yammer de los que un custodio no sea miembro. Para ello, debe agregar tanto el buzón como el sitio asociados a cada equipo o grupo de Yammer.

6. Después de editar las ubicaciones de datos del custodio, haga clic en **Siguiente** para ir a la página **Configuración de suspensión** .  

7. En la página **Configuración de suspensión** , actualice la configuración de suspensión del custodio.

## <a name="reindex-custodian-data"></a>Volver a indexar datos de custodios

En la mayoría de los flujos de trabajo de eDiscovery para investigaciones legales, se busca un subconjunto de datos de un custodio después de que el custodio se agregue a un caso legal. Debido a tamaños de archivo muy grandes o posibles daños en los datos, algunos elementos de los orígenes de datos asociados a un custodio pueden indizarse parcialmente. Con la funcionalidad [de indexación avanzada](indexing-custodian-data.md) en eDiscovery (Premium), la mayoría de los elementos indizados parcialmente se pueden corregir automáticamente mediante la reindexación de estos elementos a petición.

Cuando se agrega un custodio a un caso, los datos ubicados en los orígenes de datos asociados al custodio se vuelven a indexar automáticamente (mediante el proceso de indexación avanzada). Esto significa que puede dejar los datos en contexto en lugar de tener que descargarlos y corregirlos y, a continuación, buscarlos sin conexión). Sin embargo, durante el ciclo de vida de un caso legal, los nuevos orígenes de datos pueden asociarse a un custodio. En este caso, puede volver a indexar los datos del custodio si vuelve a ejecutar el proceso de indexación avanzada para corregir los elementos parcialmente indexados y actualizar el índice de los datos del custodio.

Para desencadenar el proceso de reindexación para abordar elementos parcialmente indexados:

1. Vaya a **eDiscovery > eDiscovery (Premium)** y abra el caso.

2. Haga clic en la pestaña **Orígenes** .

3. En la página **Custodios** , seleccione un custodio cuyos datos se deben volver a indexar.

4. En la página de control flotante, haga clic en **Actualizar índice**.

   Se muestra un cuadro de diálogo que indica que se ha creado el trabajo de índice.

La reindexación de datos de custodios es un proceso de ejecución prolongada; El trabajo correspondiente que se crea se denomina **Volver a indexar datos de custodios**. Puede realizar un seguimiento del progreso en la pestaña **Trabajos** o en la pestaña **Custodios** supervisando el estado en la columna **Estado del trabajo de indexación** .

Para más información, consulte lo siguiente:

- [Trabajar con errores de proceso](processing-data-for-case.md)

- [Administrar trabajos](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a>Liberación de un custodio de un caso

Un custodio se libera en situaciones en las que se cierra un caso, el custodio ya no está obligado a conservar el contenido de un caso, o cuando se considera que el custodio ya no es relevante para el caso. 

Si libera a un custodio después de publicar un aviso de suspensión, se enviará un aviso de liberación al custodio. Además, se quitan las retenciones colocadas en orígenes de datos asociados al custodio. Si el custodio se colocó en una *suspensión silenciosa*, donde no se emitieron notificaciones de suspensión legal, no se enviará un aviso de liberación, pero se quitarán las retenciones colocadas en los orígenes de datos asociados a ese custodio.

Para liberar un custodio:

1. Vaya a **eDiscovery > eDiscovery (Premium)** y abra el caso.

2. Haga clic en la pestaña **Orígenes** .

3. En la página **Custodios** y, a continuación, seleccione el custodio que se va a liberar del caso.

4. En la página de control flotante, haga clic en **Liberar custodio**.

   Se muestra una página de advertencia que explica que si se coloca una retención en un origen de datos asociado al custodio, se quitará la suspensión y que se seguirá aplicando cualquier otra retención asociada a otro caso de exhibición de documentos electrónicos (Premium). Esto incluye otros tipos de características de conservación y retención (como una directiva de retención de Microsoft 365).

5. Haga clic en **Sí** para confirmar que desea liberar al custodio. 

    El estado de este usuario en la pestaña **Custodios** se establece en **Liberado** y el **estado de suspensión** de la página de control flotante se cambia a **False**.

> [!NOTE]
> Un custodio puede estar involucrado simultáneamente en varios casos legales. Cuando se libera un custodio de un caso específico, las retenciones y notificaciones en otros casos no se verán afectadas.
