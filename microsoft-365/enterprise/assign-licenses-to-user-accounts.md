---
title: Asignar licencias de Microsoft 365 a cuentas de usuario
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Describe cómo asignar licencias de Microsoft 365 a cuentas de usuario, ya sea individualmente o en función de la pertenencia a grupos.
ms.openlocfilehash: a2eed7b3597dcc2531834456a9b05f5aa1b07a23
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326512"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="725ee-103">Asignar licencias de Microsoft 365 a cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="725ee-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="725ee-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="725ee-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="725ee-105">Para el modelo de identidad solo de nube, puede asignar licencias de Microsoft 365 a las cuentas de usuario a medida que se crean, en función de cómo las cree.</span><span class="sxs-lookup"><span data-stu-id="725ee-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="725ee-106">Para el modelo de identidad híbrida, cuando las cuentas de usuario de Servicios de dominio de Active Directory (AD DS) se sincronizan por primera vez, no se les asigna automáticamente una ubicación o una licencia de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="725ee-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a location or a Microsoft 365 license.</span></span> <span data-ttu-id="725ee-107">**Debe configurar cada cuenta de usuario con una ubicación de usuario antes o junto con la asignación de una licencia.**</span><span class="sxs-lookup"><span data-stu-id="725ee-107">**You must configure each user account with a user location prior to or along with assigning a license.**</span></span>

<span data-ttu-id="725ee-108">En cualquier caso, debe asignar una licencia a las cuentas de usuario para que los usuarios puedan acceder a los servicios de Microsoft 365, como el correo electrónico y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="725ee-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="725ee-109">Puede asignar licencias a cuentas de usuario de forma individual o automática a través de la pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="725ee-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="725ee-110">Para asignar licencias de Microsoft 365 a cuentas de usuario individuales, puede usar:</span><span class="sxs-lookup"><span data-stu-id="725ee-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="725ee-111">Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="725ee-111">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [<span data-ttu-id="725ee-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="725ee-112">PowerShell</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- <span data-ttu-id="725ee-113">Centro de administración de Azure AD</span><span class="sxs-lookup"><span data-stu-id="725ee-113">The Azure AD admin center</span></span>

## <a name="group-based-licensing"></a><span data-ttu-id="725ee-114">Licencias basadas en grupos</span><span class="sxs-lookup"><span data-stu-id="725ee-114">Group-based licensing</span></span>

<span data-ttu-id="725ee-115">Puedes configurar grupos de seguridad en Azure AD para asignar automáticamente licencias de un conjunto de suscripciones a todos los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="725ee-115">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="725ee-116">Esto se conoce como *licencias basadas en grupos*.</span><span class="sxs-lookup"><span data-stu-id="725ee-116">This is known as *group-based licensing*.</span></span> <span data-ttu-id="725ee-117">Si una cuenta de usuario se añade o se elimina del grupo, se asignará o quitará la asignación de las licencias de suscripciones del grupo automáticamente desde la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="725ee-117">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="725ee-118">Asegúrese de que tiene suficientes licencias para todos los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="725ee-118">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="725ee-119">Si se queda sin licencias, no se asignarán licencias a nuevos usuarios hasta que estén disponibles otras nuevas.</span><span class="sxs-lookup"><span data-stu-id="725ee-119">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="725ee-120">No configure las licencias basadas en grupos para los grupos que contengan cuentas entre empresas (B2B) de Azure.</span><span class="sxs-lookup"><span data-stu-id="725ee-120">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="725ee-121">Para obtener más información, consulta [licencias basadas en grupos en Azure AD.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="725ee-121">For more informaion, see [group-based licensing in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="725ee-122">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="725ee-122">Next steps</span></span>

<span data-ttu-id="725ee-123">Con el conjunto adecuado de cuentas de usuario a las que se han asignado licencias, ya está listo para:</span><span class="sxs-lookup"><span data-stu-id="725ee-123">With the appropriate set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="725ee-124">Implementar la seguridad</span><span class="sxs-lookup"><span data-stu-id="725ee-124">Implement security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [<span data-ttu-id="725ee-125">Implementar software cliente, como Aplicaciones de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="725ee-125">Deploy client software, such as Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="725ee-126">Configurar la administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="725ee-126">Set up device management</span></span>](device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="725ee-127">Configurar servicios y aplicaciones</span><span class="sxs-lookup"><span data-stu-id="725ee-127">Configure services and applications</span></span>](configure-services-and-applications.md)
