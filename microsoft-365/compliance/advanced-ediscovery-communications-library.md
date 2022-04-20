---
title: Administrar plantillas de comunicaciones de custodio en la biblioteca de comunicaciones en eDiscovery (Premium)
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
description: Puede agregar plantillas de comunicaciones de custodio (como una plantilla para la notificación de suspensión) en eDiscovery (Premium) para que se puedan usar en cualquier caso en su organización.
ms.openlocfilehash: be8311a9687eb4edb9cc44e15264808a2a05a69a
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64945161"
---
# <a name="manage-custodian-communications-templates-in-ediscovery-premium"></a>Administrar plantillas de comunicaciones de custodio en eDiscovery (Premium)

Cuando usted u otros usuarios crean una notificación de suspensión u otros tipos de comunicaciones de custodio, tuvo que crear el documento de comunicación desde cero mediante el editor de comunicaciones de la pestaña **Comunicaciones** en un caso de exhibición de documentos electrónicos (Premium). Ahora, hemos publicado una nueva característica que le permite crear plantillas de comunicaciones que se pueden usar para crear comunicaciones en cualquier caso en su organización. Una vez creadas las plantillas de comunicación, están disponibles para usarse en un caso. Esto significa que los asistentes u otros usuarios que crean comunicaciones de custodio no tienen que empezar desde cero para crear una notificación. En su lugar, pueden seleccionar una plantilla para compilar la notificación que se envía a un custodio.

En este artículo se explica cómo crear plantillas de comunicaciones para toda la organización y seleccionarlas al crear una nueva notificación de custodio para un caso específico de exhibición de documentos electrónicos (Premium).

## <a name="before-you-create-templates-in-the-communications-library"></a>Antes de crear plantillas en la biblioteca de comunicaciones

- Debe ser administrador de eDiscovery en su organización para agregar o quitar plantillas en la biblioteca de comunicaciones de eDiscovery (Premium). Para obtener más información, consulte [Asignación de permisos de exhibición de documentos electrónicos en el portal de cumplimiento de Microsoft Purview](assign-ediscovery-permissions.md).  

- Su organización puede tener un máximo de 50 plantillas en la biblioteca de comunicaciones.

## <a name="create-a-communications-template"></a>Creación de una plantilla de comunicaciones

1. En el portal de cumplimiento, vaya a [eDiscovery (Premium)](https://go.microsoft.com/fwlink/p/?linkid=2173764) y, a continuación, haga clic en **configuración de eDiscovery (Premium).**

   ![Seleccionar la configuración de eDiscovery (Premium)](..\media\HistoricalVersions1.png)

2. En la página **Configuración**, seleccione la pestaña **Biblioteca de comunicaciones**.

3. En la página **Biblioteca de comunicaciones** , haga clic en **Crear**.

4. Siga el procedimiento para crear una comunicación de custodio. Para obtener instrucciones paso a paso, consulte [Creación de una notificación de suspensión legal](create-hold-notification.md).

   > [!NOTE]
   > Los pasos para crear una plantilla de comunicaciones son los mismos que el flujo de trabajo para crear una notificación dentro de un caso. La única diferencia es que al crear una plantilla, no se especifica un oficial emisor y no se asignan custodios. La especificación de un oficial emisor y la asignación de custodios se realiza cuando se usa una plantilla de comunicaciones para crear una notificación de custodio para un caso.

5. Después de crear una plantilla, se muestra en la página **Biblioteca de comunicaciones** .

   ![Plantillas que se muestran en la biblioteca de comunicaciones](..\media\AeDCommunicationsLibrary1.png)

Usted u otros administradores de eDiscovery pueden editar una plantilla de comunicaciones. Los cambios realizados en una plantilla no afectan ni modifican las notificaciones que se crearon anteriormente con esa plantilla. Estos cambios solo se aplicarán a las nuevas notificaciones creadas mediante la plantilla actualizada.

## <a name="use-a-communications-template-to-create-a-custodian-notification"></a>Uso de una plantilla de comunicaciones para crear una notificación de custodio

Después de crear una o varias plantillas de comunicaciones en la biblioteca de comunicaciones, estas plantillas se pueden seleccionar para crear una notificación de custodio en un caso.

Para seleccionar una plantilla:

1. En el portal de cumplimiento, vaya a **eDiscovery > Avanzadas** para mostrar la lista de casos de su organización.

2. Seleccione un caso, haga clic en la pestaña **Comunicaciones** y, a continuación, haga clic en **Nueva comunicación**.

3. En la página **Comunicación de nombre** , use la lista desplegable **Seleccionar plantilla de comunicación** para seleccionar una plantilla de comunicaciones que se usará para crear la notificación de custodio.

   La lista de plantillas de la biblioteca de comunicaciones de la organización se muestra en la lista desplegable.

   ![Las plantillas de la biblioteca de comunicaciones se muestran en la lista desplegable.](..\media\AeDCommunicationsTemplates1.png)
