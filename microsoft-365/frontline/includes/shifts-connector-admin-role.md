---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: microsoft-365-frontline
ms.openlocfilehash: 6531024304774ce8d4316156dd7c83f42b1e0c65
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68222658"
---
Para completar los pasos de este artículo, debe ser administrador global de Microsoft 365 o administrador del conector de Turnos.

 El rol de administrador del conector de Turnos es un rol personalizado que se crea en Azure AD y se asigna a un usuario. El nombre del rol debe ser "Administrador de conector de Turnos". No es necesario que el rol tenga permisos específicos, aunque se debe establecer al menos un permiso al crearlo. El servicio se basa en la presencia del rol en el usuario y no en sus permisos.  Para más información, vea [Crear y asignar un rol personalizado en Azure AD](/azure/active-directory/roles/custom-create) y [Asignar roles de Azure AD a los usuarios](/azure/active-directory/roles/manage-roles-portal). Tenga en cuenta que el rol puede tardar hasta 24 horas en crearse y aplicarse a un usuario.