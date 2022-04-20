---
title: Agregar o quitar miembros de un caso
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
description: Obtenga información sobre cómo agregar o quitar los miembros que pueden acceder a un caso al administrar un caso de exhibición de documentos electrónicos (Premium).
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9586fd0f606c3f95cda19ca9d6ae036bc23763dc
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64943203"
---
# <a name="add-or-remove-members-from-a-case"></a>Agregar o quitar miembros de un caso

Puede agregar o quitar miembros para administrar quién tiene acceso al caso. Sin embargo, antes de que un miembro pueda acceder a un caso de exhibición de documentos electrónicos (Premium) (y realizar tareas en el caso), debe agregar el usuario al grupo de roles del Administrador de exhibición de documentos electrónicos en la página **Permisos** del portal de cumplimiento de Microsoft Purview. Para más información, consulte [Asignar permisos de eDiscovery](./assign-ediscovery-permissions.md).

1. En la página **eDiscovery (Premium),** vaya al caso al que desea agregar un miembro.

2. Haga clic en la pestaña **Configuración** y luego haga clic en **Seleccionar** en el mosaico **Acceso y permisos**.

3. En **Administrar miembros a**, haga clic en **Agregar** para agregar miembros al caso. También puede elegir agregar un grupo de roles al caso haciendo clic en  **Agregar** en **Administrar grupos de roles**.

4. En la lista de personas o grupos de roles que se pueden agregar como miembros del caso, active la casilla situada junto a los nombres de las personas o grupos de roles que quiera agregar.

   > [!NOTE]
   > Al agregar un grupo de roles a un caso, solo puede agregar los grupos de roles de los que es miembro.

5. Después de seleccionar las personas o grupos de roles que se van a agregar como miembros del caso, haga clic en **Agregar**.

6. En la página desplegable **Administrar este caso**, haga clic en **Guardar** para guardar la nueva lista de miembros del caso.

> [!IMPORTANT]
> Si se agrega o quita un rol de un grupo de roles que ha agregado como miembro de un caso, el grupo de roles se quitará automáticamente como miembro del caso (o en cualquier caso, el grupo de roles es miembro de ). El motivo es proteger su organización frente a proporcionar permisos adicionales involuntariamente a los miembros de un caso. De forma similar, si se elimina un grupo de roles, se quitará de todos los casos de los que era miembro. Para más información, consulte [Asignar permisos de eDiscovery](assign-ediscovery-permissions.md#adding-role-groups-as-members-of-ediscovery-cases).

## <a name="removing-members-from-a-case"></a>Eliminación de miembros de un caso

Solo un [administrador de eDiscovery](assign-ediscovery-permissions.md) puede quitar miembros de un caso. Incluso si está asignado al grupo de roles del Administrador de exhibición de documentos electrónicos o ha creado inicialmente el caso, no podrá quitarse a usted mismo ni a otros miembros de un caso a menos que también sea administrador de eDiscovery. Para quitarse a usted mismo u otros miembros de un caso, póngase en contacto con un administrador de exhibición de documentos electrónicos de su organización.
