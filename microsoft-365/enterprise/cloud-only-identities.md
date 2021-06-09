---
title: Microsoft 365 identidad de solo nube
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
description: Describe cómo crear usuarios y grupos cuando la suscripción Microsoft 365 está usando la identidad de solo nube.
ms.openlocfilehash: 111c42e644913a8f7f6e41d4e8bf65685263f757
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327932"
---
# <a name="microsoft-365-cloud-only-identity"></a><span data-ttu-id="d681b-103">Microsoft 365 identidad de solo nube</span><span class="sxs-lookup"><span data-stu-id="d681b-103">Microsoft 365 cloud-only identity</span></span>

<span data-ttu-id="d681b-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="d681b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d681b-105">Con la identidad de solo nube, todos los usuarios, grupos y contactos se almacenan en el inquilino de Azure Active Directory (Azure AD) de su Microsoft 365 suscripción.</span><span class="sxs-lookup"><span data-stu-id="d681b-105">With cloud-only identity, all your users, groups, and contacts are stored in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="d681b-106">Estos son los componentes básicos de la identidad de solo nube.</span><span class="sxs-lookup"><span data-stu-id="d681b-106">Here are the basic components of cloud-only identity.</span></span>
 
![Los componentes básicos de la identidad de solo nube](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="d681b-108">Los usuarios y sus cuentas de usuario en las organizaciones se pueden clasificar de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="d681b-108">Users and their user accounts in organizations can be categorized in a number of ways.</span></span> <span data-ttu-id="d681b-109">Por ejemplo, algunos son empleados y tienen un estado permanente.</span><span class="sxs-lookup"><span data-stu-id="d681b-109">For example, some are employees and have a permanent status.</span></span> <span data-ttu-id="d681b-110">Algunos son proveedores, contratistas o socios que tienen un estado temporal.</span><span class="sxs-lookup"><span data-stu-id="d681b-110">Some are vendors, contractors, or partners that have a temporary status.</span></span> <span data-ttu-id="d681b-111">Algunos son usuarios externos que no tienen cuentas de usuario, pero que aún deben tener acceso a servicios y recursos específicos para admitir la interacción y la colaboración.</span><span class="sxs-lookup"><span data-stu-id="d681b-111">Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration.</span></span> <span data-ttu-id="d681b-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d681b-112">For example:</span></span>

- <span data-ttu-id="d681b-113">Cuentas de espacio empresarial que representan a usuarios de su organización a los que asigna una licencia para servicios en la nube</span><span class="sxs-lookup"><span data-stu-id="d681b-113">Tenant accounts represent users within your organization that you license for cloud services</span></span>

- <span data-ttu-id="d681b-114">Cuentas entre empresas (B2B) que representan a usuarios externos a la organización a los que invita a participar en colaboración</span><span class="sxs-lookup"><span data-stu-id="d681b-114">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="d681b-115">Hacer un balance de los tipos de usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="d681b-115">Take stock of the types of users in your organization.</span></span> <span data-ttu-id="d681b-116">¿Cuáles son las agrupaciones?</span><span class="sxs-lookup"><span data-stu-id="d681b-116">What are the groupings?</span></span> <span data-ttu-id="d681b-117">Por ejemplo, puede agrupar usuarios por función o propósito de alto nivel para su organización.</span><span class="sxs-lookup"><span data-stu-id="d681b-117">For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="d681b-p104">Además, algunos servicios en la nube se pueden compartir con usuarios externos a la organización sin cuentas de usuario. También necesitará identificar estos grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="d681b-p104">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

<span data-ttu-id="d681b-120">Puede usar grupos en Azure AD para varios fines que simplifican la administración del entorno en la nube.</span><span class="sxs-lookup"><span data-stu-id="d681b-120">You can use groups in Azure AD for several purposes that simplify management of your cloud environment.</span></span> <span data-ttu-id="d681b-121">Por ejemplo, con los grupos de Azure AD, puede:</span><span class="sxs-lookup"><span data-stu-id="d681b-121">For example, with Azure AD groups, you can:</span></span>

- <span data-ttu-id="d681b-122">Use licencias basadas en grupos para asignar licencias de Microsoft 365 a sus cuentas de usuario automáticamente en cuanto se agregan como miembros.</span><span class="sxs-lookup"><span data-stu-id="d681b-122">Use group-based licensing to assign licenses for Microsoft 365 to your user accounts automatically as soon as they are added as members.</span></span>
- <span data-ttu-id="d681b-123">Agregue cuentas de usuario a grupos específicos dinámicamente en función de los atributos de cuenta de usuario, como el nombre del departamento.</span><span class="sxs-lookup"><span data-stu-id="d681b-123">Add user accounts to specific groups dynamically based on user account attributes, such as department name.</span></span>
- <span data-ttu-id="d681b-124">Aprovisionar automáticamente a los usuarios para aplicaciones de Software como Servicio (SaaS) y proteger el acceso a esas aplicaciones con autenticación multifactor (MFA) y otras directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="d681b-124">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication (MFA) and other Conditional Access policies.</span></span>
- <span data-ttu-id="d681b-125">Aprovisione permisos y niveles de acceso para SharePoint de grupo en línea.</span><span class="sxs-lookup"><span data-stu-id="d681b-125">Provision permissions and levels of access for SharePoint Online team sites.</span></span>

## <a name="next-steps-for-cloud-only-identity"></a><span data-ttu-id="d681b-126">Pasos siguientes para la identidad de solo nube</span><span class="sxs-lookup"><span data-stu-id="d681b-126">Next steps for cloud-only identity</span></span>

- [<span data-ttu-id="d681b-127">Administrar cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="d681b-127">Manage user accounts</span></span>](manage-microsoft-365-accounts.md)
- [<span data-ttu-id="d681b-128">Asignar licencias a cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="d681b-128">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)
- [<span data-ttu-id="d681b-129">Administrar grupos y pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="d681b-129">Manage groups and group membership</span></span>](manage-microsoft-365-groups.md)
- [<span data-ttu-id="d681b-130">Administrar contraseñas de cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="d681b-130">Manage user account passwords</span></span>](manage-microsoft-365-passwords.md)
