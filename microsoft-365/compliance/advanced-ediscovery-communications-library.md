---
title: Administrar plantillas de comunicaciones de custodia en la biblioteca de comunicaciones en Advanced eDiscovery
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
description: Puede agregar plantillas de comunicaciones de custodia (como una plantilla para notificación de retención) en Advanced eDiscovery para que se puedan usar en cualquier caso en su organización.
ms.openlocfilehash: 1b5be4a4a923050b43943e81ac64265e16749899
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63331212"
---
# <a name="manage-custodian-communications-templates-in-advanced-ediscovery"></a>Administrar plantillas de comunicaciones de custodia en Advanced eDiscovery

Cuando usted u otros usuarios crean una notificación de retención u otros tipos de comunicaciones de custodia, tenía que crear el documento de comunicación desde cero mediante el editor de comunicaciones de la pestaña Comunicaciones en un Advanced eDiscovery caso. Ahora, hemos lanzado una nueva característica que le permite crear plantillas de comunicaciones que se pueden usar para crear comunicaciones en cualquier caso en su organización. Una vez creadas las plantillas de comunicación, están disponibles para usarse en un caso. Esto significa que los asistentes legales u otros usuarios que crean comunicaciones de custodia no tienen que empezar desde cero para crear una notificación. En su lugar, pueden seleccionar una plantilla para crear la notificación que se envía a un custodio.

En este artículo se explica cómo crear plantillas de comunicaciones en toda la organización y seleccionarlas al crear una nueva notificación de custodia para un caso Advanced eDiscovery específico.

## <a name="before-you-create-templates-in-the-communications-library"></a>Antes de crear plantillas en la biblioteca de comunicaciones

- Debe ser administrador de exhibición de documentos electrónicos en su organización para agregar o quitar plantillas en la biblioteca de comunicaciones de Advanced eDiscovery. Para obtener más información, vea [Assign eDiscovery permissions in the Centro de cumplimiento de Microsoft 365](assign-ediscovery-permissions.md)  

- Su organización puede tener un máximo de 50 plantillas en la biblioteca de comunicaciones.

## <a name="create-a-communications-template"></a>Crear una plantilla de comunicaciones

1. En el Centro de cumplimiento de Microsoft 365, vaya [a Advanced eDiscovery](https://go.microsoft.com/fwlink/p/?linkid=2173764) y, a continuación, haga clic **en Advanced eDiscovery configuración**.

   ![Seleccione Advanced eDiscovery configuración](..\media\HistoricalVersions1.png)

2. En la **Configuración**, seleccione la **pestaña Biblioteca de** comunicaciones.

3. En la página **Biblioteca de** comunicaciones, haga clic en **Crear**.

4. Siga el procedimiento para crear una comunicación de custodia. Para obtener instrucciones paso a paso, consulta [Crear una notificación de retención legal](create-hold-notification.md).

   > [!NOTE]
   > Los pasos para crear una plantilla de comunicaciones son los mismos que el flujo de trabajo para crear una notificación en un caso. La única diferencia es que al crear una plantilla, no se especifica un oficial emisor y no se asignan custodios. La especificación de un oficial emisor y la asignación de custodios se realiza cuando se usa una plantilla de comunicaciones para crear una notificación de custodia para un caso.

5. Después de crear una plantilla, se muestra en la página **biblioteca de** comunicaciones.

   ![Plantillas mostradas en la biblioteca de comunicaciones](..\media\AeDCommunicationsLibrary1.png)

Usted u otros administradores de exhibición de documentos electrónicos pueden editar una plantilla de comunicaciones. Los cambios realizados en una plantilla no afectan ni modifican las notificaciones que se crearon anteriormente con esa plantilla. Estos cambios solo se aplicarán a las notificaciones nuevas creadas con la plantilla actualizada.

## <a name="use-a-communications-template-to-create-a-custodian-notification"></a>Usar una plantilla de comunicaciones para crear una notificación de custodia

Después de crear una o varias plantillas de comunicaciones en la biblioteca de comunicaciones, estas plantillas se pueden seleccionar para crear una notificación de custodia en un caso.

Para seleccionar una plantilla:

1. En el Centro de cumplimiento de Microsoft 365, vaya a **eDiscovery > Advanced** para mostrar la lista de casos de su organización.

2. Seleccione un caso, haga clic en la **pestaña** Comunicaciones y, a continuación, haga clic **en Nueva comunicación**.

3. En la **página Comunicación de** nombre, use  la lista desplegable Seleccionar plantilla de comunicación para seleccionar una plantilla de comunicaciones que se usará para crear la notificación de custodia.

   La lista de plantillas de la biblioteca de comunicaciones de la organización se muestra en la lista desplegable.

   ![Plantillas de la biblioteca de comunicaciones que se muestran en la lista desplegable.](..\media\AeDCommunicationsTemplates1.png)
