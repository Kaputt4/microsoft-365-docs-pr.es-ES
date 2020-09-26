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
ms.openlocfilehash: 85a800c3e21c270f46de78bdef77d7b7a98e0eca
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285446"
---
# <a name="assign-permissions-for-data-investigations-preview"></a><span data-ttu-id="db93a-103">Asignar permisos para las investigaciones de datos (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="db93a-103">Assign permissions for Data Investigations (preview)</span></span>

<span data-ttu-id="db93a-104">Para tener acceso a una investigación de datos en el centro de cumplimiento de Office 365 o Microsoft 365, debe ser miembro del grupo de funciones de investigador de datos.</span><span class="sxs-lookup"><span data-stu-id="db93a-104">To access a data investigation in the Office 365 or Microsoft 365 compliance center, you need be a member of the Data Investigator role group.</span></span> <span data-ttu-id="db93a-105">Para agregar miembros a un grupo de roles, debe ser miembro del grupo de roles de administración de la organización o tener asignado el rol de administración de roles en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="db93a-105">To add members to a role group, you must be a member of the Organization Management role group or assigned the Role Management role in the Security & Compliance Center.</span></span> <span data-ttu-id="db93a-106">Una vez que un usuario se convierte en miembro del grupo de funciones del investigador de datos, puede crear, acceder y realizar investigaciones en las investigaciones de datos de las que es miembro.</span><span class="sxs-lookup"><span data-stu-id="db93a-106">After a user becomes a member of the Data Investigator role group, they can create, access, and conduct investigations in the data investigations that you are a member of.</span></span>

<span data-ttu-id="db93a-107">Para asignar permisos de investigación de datos:</span><span class="sxs-lookup"><span data-stu-id="db93a-107">To assign data investigations permissions:</span></span>

1. <span data-ttu-id="db93a-108">Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con las credenciales de una cuenta de administrador de su organización.</span><span class="sxs-lookup"><span data-stu-id="db93a-108">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="db93a-109">En el centro de seguridad & cumplimiento, haga clic en **permisos**.</span><span class="sxs-lookup"><span data-stu-id="db93a-109">In the Security & Compliance Center, click **Permissions**.</span></span>

3. <span data-ttu-id="db93a-110">Haga clic en el grupo de funciones del **investigador de datos** y, a continuación, junto a **miembros** en la página flotante, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="db93a-110">Click the **Data Investigator** role group, and then next to **Members** on the flyout page, click **Edit**.</span></span>

4. <span data-ttu-id="db93a-111">Haga clic en **elegir miembros** y, a continuación, en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="db93a-111">Click **Choose members** and then click **Add**.</span></span> <span data-ttu-id="db93a-112">Seleccione los usuarios que desea agregar como investigadores de datos y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="db93a-112">Select the users that you want to add as data investigators, and then click **Add**.</span></span>

5. <span data-ttu-id="db93a-113">Una vez que haya agregado todos los usuarios, haga clic en **listo** y, a continuación, haga clic en **Guardar** para guardar los cambios en el grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="db93a-113">After you've added all the users, click **Done** and then click **Save** to save the changes to the role group.</span></span>

> [!NOTE]
> <span data-ttu-id="db93a-114">El rol de administración de investigación de datos que se asigna al grupo de funciones de investigador de datos proporciona los permisos necesarios para acceder a la herramienta de investigaciones de datos en el centro de cumplimiento de Office 365 o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db93a-114">The Data Investigation Management role that is assigned to the Data Investigator role group provides the necessary permissions to access the Data Investigations tool in the Office 365 or Microsoft 365 compliance center.</span></span> <span data-ttu-id="db93a-115">De forma predeterminada, este rol no se asigna al grupo de roles de administración de la organización, lo que significa que los administradores globales de la organización no podrán obtener acceso a la herramienta de investigaciones de datos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="db93a-115">By default, this role is not assigned to the Organization Management role group, which means that global admins in your organization may not be able to access the Data Investigations tool by default.</span></span> <span data-ttu-id="db93a-116">Para solucionar esto, puede agregar administradores globales al grupo de funciones del investigador de datos o agregar el rol de administración de investigación de datos al grupo de roles de administración de la organización.</span><span class="sxs-lookup"><span data-stu-id="db93a-116">To fix this, you can add global admins to the Data Investigator role group or add the Data Investigation Management role to the Organization Management role group.</span></span> <span data-ttu-id="db93a-117">Una tercera opción sería crear un grupo de funciones personalizado y asignar el rol de administración de investigación de datos (y otras funciones) y, a continuación, agregar miembros apropiados.</span><span class="sxs-lookup"><span data-stu-id="db93a-117">A third option would be to create a custom role group and assign the Data Investigation Management role (and other roles) and then add appropriate members.</span></span> <span data-ttu-id="db93a-118">Para obtener más información acerca de los grupos de roles y los roles, consulte [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="db93a-118">For more information about role groups and roles, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>
