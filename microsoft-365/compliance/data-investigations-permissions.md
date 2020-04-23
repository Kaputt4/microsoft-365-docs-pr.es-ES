---
title: Asignar permisos para las investigaciones de datos (versión preliminar)
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
description: En este artículo se describe cómo configurar los permisos necesarios para usar la herramienta de investigaciones de datos en Microsoft 365.
ms.openlocfilehash: 47a7923d38cfa0ea3bad6c4c266f580f8104c429
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637762"
---
# <a name="assign-permissions-for-data-investigations-preview"></a>Asignar permisos para las investigaciones de datos (versión preliminar)

Para tener acceso a una investigación de datos en el centro de cumplimiento de Office 365 o Microsoft 365, debe ser miembro del grupo de funciones de investigador de datos. Para agregar miembros a un grupo de roles, debe ser miembro del grupo de roles de administración de la organización o tener asignado el rol de administración de roles en el centro de seguridad & cumplimiento. Una vez que un usuario se convierte en miembro del grupo de funciones del investigador de datos, puede crear, acceder y realizar investigaciones en las investigaciones de datos de las que es miembro.

Para asignar permisos de investigación de datos:

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con las credenciales de una cuenta de administrador de su organización.

2. En el centro de seguridad & cumplimiento, haga clic en **permisos**.

3. Haga clic en el grupo de funciones del **investigador de datos** y, a continuación, junto a **miembros** en la página flotante, haga clic en **Editar**.

4. Haga clic en **elegir miembros** y, a continuación, en **Agregar**. Seleccione los usuarios que desea agregar como investigadores de datos y, a continuación, haga clic en **Agregar**.

5. Una vez que haya agregado todos los usuarios, haga clic en **listo** y, a continuación, haga clic en **Guardar** para guardar los cambios en el grupo de roles.

> [!NOTE]
> El rol de administración de investigación de datos que se asigna al grupo de funciones de investigador de datos proporciona los permisos necesarios para acceder a la herramienta de investigaciones de datos en el centro de cumplimiento de Office 365 o Microsoft 365. De forma predeterminada, este rol no se asigna al grupo de roles de administración de la organización, lo que significa que los administradores globales de la organización no podrán obtener acceso a la herramienta de investigaciones de datos de forma predeterminada. Para solucionar esto, puede agregar administradores globales al grupo de funciones del investigador de datos o agregar el rol de administración de investigación de datos al grupo de roles de administración de la organización. Una tercera opción sería crear un grupo de funciones personalizado y asignar el rol de administración de investigación de datos (y otras funciones) y, a continuación, agregar miembros apropiados. Para obtener más información acerca de los grupos de roles y los roles, consulte [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).
