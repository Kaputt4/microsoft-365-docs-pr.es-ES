---
title: Administrar destinatarios en EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 2921f544-8257-4bae-8e3a-ce9250e9f162
description: Microsoft Exchange Online Protection (EOP) ofrece varias maneras de administrar los destinatarios de correo. Como administrador, puede realizar ciertas tareas de administración dentro del centro de administración de Exchange (EAC) o mediante Windows PowerShell remoto y comprobar otras tareas de administración realizadas en el centro de administración de Microsoft 365.
ms.openlocfilehash: b5d1efa0fb54b97f226f25375fb747e5373a36cd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635345"
---
# <a name="manage-recipients-in-eop"></a>Administrar destinatarios en EOP

Microsoft Exchange Online Protection (EOP) ofrece varias maneras de administrar los destinatarios de correo. Como administrador, puede realizar ciertas tareas de administración dentro del centro de administración de Exchange (EAC) o mediante Windows PowerShell remoto y comprobar otras tareas de administración realizadas en el centro de administración de Microsoft 365.

EOP admite los siguientes tipos de destinatarios:

- **Usuarios de correo**: los usuarios de correo son destinatarios en los dominios administrados de EOP. Estos destinatarios tienen credenciales de inicio de sesión en la organización, pero tienen direcciones de correo electrónico externas, lo que significa que sus buzones de destinatarios se encuentran fuera de la organización en la nube.

  Puede Agregar usuarios de correo para que puedan recibir correo y también puede crear reglas de flujo de correo (también conocidas como reglas de transporte) para usuarios específicos. Además puede asignar roles a los usuarios de correo de su organización; los usuarios con privilegios de grupo de funciones de administración pueden acceder al Centro de administración de Exchange (EAC) y realizar determinadas tareas de administración. Para obtener más información sobre los roles de usuario y cómo asignar los roles de usuario en EOP, consulte [Manage admin role Group Permissions in EOP](manage-admin-role-group-permissions-in-eop.md).

  Para obtener más información sobre la administración de usuarios de correo en EOP, consulte [Administrar usuarios de correo en EOP](manage-mail-users-in-eop.md).

- **Grupos**: los usuarios de correo se pueden agrupar en grupos de distribución o grupos de seguridad.

Para obtener más información acerca de la administración de grupos en EOP, consulte [Administrar grupos en EOP](manage-groups-in-eop.md).
