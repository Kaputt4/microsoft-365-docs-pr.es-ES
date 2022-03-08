---
title: Administrar los agentes emisores en Advanced eDiscovery
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
description: Puede agregar agentes emisores de toda la organización en Advanced eDiscovery para que se puedan agregar a cualquier comunicación de custodia en cualquier caso en su organización.
ms.openlocfilehash: 21c5a3db9cb0cfefb26bc75537f298c7e8a5c09a
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319336"
---
# <a name="manage-issuing-officers-in-advanced-ediscovery"></a>Administrar los agentes emisores en Advanced eDiscovery

Cuando usted u otros usuarios crean una notificación de retención u otro tipo de comunicación que se envía a un usuario que es un custodio en caso de que sea, debe especificar un oficial emisor. La notificación se envía al custodio en nombre del oficial emisor especificado. Por ejemplo, un asistente legal de la organización puede ser responsable de crear y enviar notificaciones de retención a los custodios en un caso. En este escenario, el asistente puede especificar un abogado de la organización como el oficial emisor. Quién puede especificarse como oficial emisor? Hay dos tipos de usuarios que se pueden seleccionar como responsables de emisión de una comunicación de custodia:

- Cualquier miembro del caso específico del que se envía la comunicación en nombre de.

- Cualquier usuario que se agrega a una lista de oficiales emisores de toda la organización. Los usuarios de esta lista pueden agregar un oficial emisor a cualquier caso de su organización.

En este artículo se explica cómo agregar y quitar usuarios a la lista de agentes emisores de toda la organización.

## <a name="before-you-add-an-issuing-officer"></a>Antes de agregar un oficial emisor

- Debe ser administrador de exhibición de documentos electrónicos en su organización para agregar o quitar agentes emisores. Para obtener más información, vea [Assign eDiscovery permissions in the Centro de cumplimiento de Microsoft 365](assign-ediscovery-permissions.md)  

- El usuario que se agrega como oficial emisor debe tener un buzón activo en su Microsoft 365 organización.

- Su organización puede tener un máximo de 15 agentes emisores. Los miembros de un caso que se puede especificar como oficial emisor no se cuentan para este límite. Este límite solo se aplica al número de usuarios que se pueden agregar a la página De  oficiales emisores en Advanced eDiscovery.

## <a name="add-an-issuing-officer"></a>Agregar un oficial emisor

1. En el Centro de cumplimiento de Microsoft 365, vaya [a Advanced eDiscovery](https://go.microsoft.com/fwlink/p/?linkid=2173764) y, a continuación, haga clic **en Advanced eDiscovery configuración**.

   ![Seleccione Advanced eDiscovery configuración](..\media\HistoricalVersions1.png)

2. En la **Configuración**, **seleccione la pestaña** Agentes emisores para mostrar la **página Administrar agentes emisores**.

   ![Página de configuración de los agentes emisores.](..\media\AeDIssuingOfficers1.png)

3. Haga **clic en** Agregar y, a continuación, busque y agregue uno o varios usuarios a la lista de agentes emisores.

Después de agregar usuarios como responsables de emisión, usted u otros usuarios podrán especificar estos usuarios como responsable de emisión de comunicaciones de custodia para cualquier caso de su organización. Para obtener más información acerca de la creación de comunicaciones de custodia, vea [Crear un aviso de retención legal](create-hold-notification.md).

## <a name="remove-an-issuing-officer"></a>Quitar un oficial emisor

1. En el Centro de cumplimiento de Microsoft 365, vaya [a Advanced eDiscovery](https://go.microsoft.com/fwlink/p/?linkid=2173764) y, a continuación, haga clic **en Advanced eDiscovery configuración**.

2. En la **Configuración**, seleccione la pestaña Agentes **emisores**.

3. Seleccione uno o varios usuarios en la lista de agentes emisores y, a continuación, haga clic en **Eliminar**.

Después de eliminar usuarios de la lista de agentes emisores, estos usuarios ya no se pueden especificar como responsables de emisión en las nuevas comunicaciones de custodia, a menos que el usuario sea miembro del caso específico desde el que se emite la comunicación. Además, la eliminación de un oficial emisor no afectará a las comunicaciones que se enviaron antes de que el usuario se quitara como oficial emisor.
