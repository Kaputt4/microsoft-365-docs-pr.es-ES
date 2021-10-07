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
description: Obtenga información sobre cómo agregar o quitar los miembros que pueden tener acceso a un caso al administrar un Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 13a97af715a3f81b5570617f18b10cd8e35f9aec
ms.sourcegitcommit: afee35210f8d68a7f20676ff2a829464b0b0adb2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2021
ms.locfileid: "60217107"
---
# <a name="add-or-remove-members-from-a-case"></a>Agregar o quitar miembros de un caso

Puede agregar o quitar miembros para administrar quién tiene acceso al caso. Sin embargo, antes de que un miembro pueda tener acceso a un caso Advanced eDiscovery (y realizar tareas  en el caso), debe agregar el usuario al grupo de roles administrador de exhibición de documentos electrónicos en la página Permisos de la Centro de cumplimiento de Microsoft 365. Para más información, consulte [Asignar permisos de eDiscovery](./assign-ediscovery-permissions.md).

1. En la página de **eDiscovery avanzado**, vaya al caso al que desea agregar un miembro.

2. Haga clic en la pestaña **Configuración** y luego haga clic en **Seleccionar** en el mosaico **Acceso y permisos**.

3. Haga clic en **Actualizar**.

4. En **Administrar miembros a**, haga clic en **Agregar** para agregar miembros al caso. También puede elegir agregar un grupo de roles al caso haciendo clic en  **Agregar en** Administrar grupos **de roles**.

5. En la lista de personas o grupos de roles que se pueden agregar como miembros del caso, active la casilla situada junto a los nombres de las personas o grupos de roles que quiera agregar.

   > [!NOTE]
   > Al agregar un grupo de roles a un caso, solo puede agregar los grupos de roles de los que es miembro.

6. Después de seleccionar las personas o grupos de roles que se agregarán como miembros del caso, haga clic en **Agregar**.

7. En la página desplegable **Administrar este caso**, haga clic en **Guardar** para guardar la nueva lista de miembros del caso.

> [!IMPORTANT]
> Si se agrega o quita un rol de un grupo de roles que ha agregado como miembro de un caso, el grupo de roles se quitará automáticamente como miembro del caso (o en cualquier caso el grupo de roles es miembro de). El motivo es proteger la organización de proporcionar permisos adicionales a los miembros de un caso de forma involuntaria. Del mismo modo, si se elimina un grupo de roles, se quitará de todos los casos de los que era miembro. Para más información, consulte [Asignar permisos de eDiscovery](assign-ediscovery-permissions.md#adding-role-groups-as-members-of-ediscovery-cases).
