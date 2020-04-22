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
# <a name="manage-recipients-in-eop"></a><span data-ttu-id="a2f4f-104">Administrar destinatarios en EOP</span><span class="sxs-lookup"><span data-stu-id="a2f4f-104">Manage recipients in EOP</span></span>

<span data-ttu-id="a2f4f-105">Microsoft Exchange Online Protection (EOP) ofrece varias maneras de administrar los destinatarios de correo.</span><span class="sxs-lookup"><span data-stu-id="a2f4f-105">Microsoft Exchange Online Protection (EOP) offers several ways to manage your mail recipients.</span></span> <span data-ttu-id="a2f4f-106">Como administrador, puede realizar ciertas tareas de administración dentro del centro de administración de Exchange (EAC) o mediante Windows PowerShell remoto y comprobar otras tareas de administración realizadas en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a2f4f-106">As an administrator, you can perform certain management tasks within the Exchange admin center (EAC) or using remote Windows PowerShell, and verify other management tasks performed in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="a2f4f-107">EOP admite los siguientes tipos de destinatarios:</span><span class="sxs-lookup"><span data-stu-id="a2f4f-107">EOP supports the following types of recipients:</span></span>

- <span data-ttu-id="a2f4f-108">**Usuarios de correo**: los usuarios de correo son destinatarios en los dominios administrados de EOP.</span><span class="sxs-lookup"><span data-stu-id="a2f4f-108">**Mail Users**: Mail users are recipients in your EOP managed domains.</span></span> <span data-ttu-id="a2f4f-109">Estos destinatarios tienen credenciales de inicio de sesión en la organización, pero tienen direcciones de correo electrónico externas, lo que significa que sus buzones de destinatarios se encuentran fuera de la organización en la nube.</span><span class="sxs-lookup"><span data-stu-id="a2f4f-109">These recipients have logon credentials in your organization, but they have external email addresses, meaning that their recipient mailboxes are located outside of your cloud organization.</span></span>

  <span data-ttu-id="a2f4f-110">Puede Agregar usuarios de correo para que puedan recibir correo y también puede crear reglas de flujo de correo (también conocidas como reglas de transporte) para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="a2f4f-110">You can add mail users so that they can receive mail and you can also create mail flow rules (also known as transport rules) for specific users.</span></span> <span data-ttu-id="a2f4f-111">Además puede asignar roles a los usuarios de correo de su organización; los usuarios con privilegios de grupo de funciones de administración pueden acceder al Centro de administración de Exchange (EAC) y realizar determinadas tareas de administración.</span><span class="sxs-lookup"><span data-stu-id="a2f4f-111">You can also assign roles to mail users in your organization; users with management role group privileges can access the Exchange admin center (EAC) and perform certain management tasks.</span></span> <span data-ttu-id="a2f4f-112">Para obtener más información sobre los roles de usuario y cómo asignar los roles de usuario en EOP, consulte [Manage admin role Group Permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="a2f4f-112">To learn more about user roles and how to assign user roles in EOP, see [Manage admin role group permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span></span>

  <span data-ttu-id="a2f4f-113">Para obtener más información sobre la administración de usuarios de correo en EOP, consulte [Administrar usuarios de correo en EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="a2f4f-113">For more information about managing mail users in EOP, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

- <span data-ttu-id="a2f4f-114">**Grupos**: los usuarios de correo se pueden agrupar en grupos de distribución o grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a2f4f-114">**Groups**: Mail users can be grouped together into distribution groups or security groups.</span></span>

<span data-ttu-id="a2f4f-115">Para obtener más información acerca de la administración de grupos en EOP, consulte [Administrar grupos en EOP](manage-groups-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="a2f4f-115">For more information about managing groups in EOP, see [Manage groups in EOP](manage-groups-in-eop.md).</span></span>
