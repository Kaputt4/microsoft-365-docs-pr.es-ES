---
title: Administración de agentes emisores en eDiscovery (Premium)
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
description: Puede agregar oficiales emisores de toda la organización en eDiscovery (Premium) para que se puedan agregar a cualquier comunicación de custodia en cualquier caso en su organización.
ms.openlocfilehash: 076e6ea8b8dbef18c6c34221937a039fc43fad75
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64943005"
---
# <a name="manage-issuing-officers-in-ediscovery-premium"></a>Administración de agentes emisores en eDiscovery (Premium)

Cuando usted u otros usuarios crean una notificación de suspensión u otro tipo de comunicación que se envía a un usuario que es un custodio en caso de que, en caso, tiene que especificar un oficial emisor. La notificación se envía al custodio en nombre del oficial emisor especificado. Por ejemplo, un asistente legal de su organización podría ser responsable de crear y enviar notificaciones de suspensión a los custodios en un caso. En este escenario, el asistente legal puede especificar un abogado de la organización como oficial emisor. Quién se puede especificar como oficial emisor? Hay dos tipos de usuarios que se pueden seleccionar como emisores para una comunicación de custodio:

- Cualquier miembro del caso específico del que se envía la comunicación en nombre de .

- Cualquier usuario que se agregue a una lista de oficiales emisores de toda la organización. A los usuarios de esta lista se puede agregar un oficial emisor a cualquier caso de la organización.

En este artículo se explica cómo agregar y quitar usuarios a la lista de oficiales emisores de toda la organización.

## <a name="before-you-add-an-issuing-officer"></a>Antes de agregar un oficial emisor

- Debe ser administrador de eDiscovery en su organización para agregar o quitar agentes emisores. Para obtener más información, consulte [Asignación de permisos de exhibición de documentos electrónicos en el portal de cumplimiento de Microsoft Purview](assign-ediscovery-permissions.md).  

- El usuario que se agrega como emisor debe tener un buzón activo en la organización Microsoft 365.

- Su organización puede tener un máximo de 15 oficiales emisores. Los miembros de un caso que se puede especificar como oficial emisor no se cuentan para este límite. Este límite solo se aplica al número de usuarios que se pueden agregar a la página **Agentes emisores** en eDiscovery (Premium).

## <a name="add-an-issuing-officer"></a>Incorporación de un emisor

1. En el portal de cumplimiento, vaya a [eDiscovery (Premium)](https://go.microsoft.com/fwlink/p/?linkid=2173764) y, a continuación, haga clic en **configuración de eDiscovery (Premium).**

   ![Seleccionar la configuración de eDiscovery (Premium)](..\media\HistoricalVersions1.png)

2. En la página **Configuración**, seleccione la pestaña **Oficiales emisores** para mostrar la página **Administrar oficiales emisores**.

   ![Página de configuración de los oficiales emisores.](..\media\AeDIssuingOfficers1.png)

3. Haga clic en **Agregar** y, a continuación, busque y agregue uno o varios usuarios a la lista de oficiales emisores.

Después de agregar usuarios como oficiales emisores, usted u otros usuarios podrán especificar estos usuarios como emisores de comunicaciones de custodio para cualquier caso en su organización. Para obtener más información sobre cómo crear comunicaciones de custodio, vea [Crear un aviso de suspensión legal](create-hold-notification.md).

## <a name="remove-an-issuing-officer"></a>Eliminación de un oficial emisor

1. En el portal de cumplimiento, vaya a [eDiscovery (Premium)](https://go.microsoft.com/fwlink/p/?linkid=2173764) y, a continuación, haga clic en **configuración de eDiscovery (Premium).**

2. En la página **Configuración**, seleccione la pestaña **Agentes emisores**.

3. Seleccione uno o varios usuarios en la lista de oficiales emisores y, a continuación, haga clic en **Eliminar**.

Después de eliminar usuarios de la lista de oficiales emisores, esos usuarios ya no se pueden especificar como emisores en nuevas comunicaciones de custodio, a menos que el usuario sea miembro del caso específico desde el que se emite la comunicación. Además, la eliminación de un oficial emisor no afectará a las comunicaciones que se enviaron antes de que el usuario se quitara como emisor.
