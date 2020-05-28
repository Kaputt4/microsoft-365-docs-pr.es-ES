---
title: Configurar directivas de acceso condicional para campañas de 365 de Microsoft
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo configurar directivas de acceso condicional para las campañas de Microsoft 365 para agregar una seguridad adicional importante.
ms.openlocfilehash: d7c9cfee2ef00e4ebe231a28ccca185c10f53c6b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403026"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="58c65-103">Configurar directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="58c65-103">Set up conditional access policies</span></span>

<span data-ttu-id="58c65-104">Las directivas de [acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) agregan una seguridad adicional importante.</span><span class="sxs-lookup"><span data-stu-id="58c65-104">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substantial additional security.</span></span> <span data-ttu-id="58c65-105">Microsoft proporciona un conjunto de directivas de acceso condicional de línea base que se recomiendan para todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="58c65-105">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="58c65-106">Las directivas de línea base son un conjunto de directivas predefinidas que ayudan a proteger a las organizaciones frente a muchos ataques comunes.</span><span class="sxs-lookup"><span data-stu-id="58c65-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="58c65-107">Estos ataques comunes pueden incluir aerosol, reproducción y suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="58c65-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="58c65-108">Estas directivas requieren que los administradores y los usuarios escriban una segunda forma de autenticación (denominada autenticación multifactor o MFA) cuando se cumplan ciertas condiciones.</span><span class="sxs-lookup"><span data-stu-id="58c65-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="58c65-109">Por ejemplo, si un usuario inicia sesión desde un país diferente, el inicio de sesión puede considerarse arriesgado y el usuario debe proporcionar una forma de autenticación adicional.</span><span class="sxs-lookup"><span data-stu-id="58c65-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="58c65-110">Actualmente, las directivas de línea base son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="58c65-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="58c65-111">**Requerir MFA para los administradores** &ndash; Requiere multi-factor Authentication para los roles de administrador con mayor privilegios, incluido el administrador global.</span><span class="sxs-lookup"><span data-stu-id="58c65-111">**Require MFA for admins** &ndash; Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="58c65-112">Protección del usuario **final** &ndash; Requiere la autenticación multifactor para los usuarios solo cuando un inicio de sesión es arriesgado.</span><span class="sxs-lookup"><span data-stu-id="58c65-112">**End user protection** &ndash; Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="58c65-113">**Bloquear la autenticación** &ndash; heredada Las aplicaciones cliente más antiguas y algunas aplicaciones nuevas no usan protocolos de autenticación más recientes, más seguros.</span><span class="sxs-lookup"><span data-stu-id="58c65-113">**Block legacy authentication** &ndash; Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="58c65-114">Estas aplicaciones antiguas pueden omitir las directivas de acceso condicional y obtener acceso no autorizado a su entorno.</span><span class="sxs-lookup"><span data-stu-id="58c65-114">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="58c65-115">Esta directiva bloquea el acceso de los clientes que no admiten el acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="58c65-115">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="58c65-116">**Requerir MFA para la administración** &ndash; de servicios Requiere multi-factor Authentication para el acceso a las herramientas de administración, incluido Azure portal (donde se configuran las directivas de línea base).</span><span class="sxs-lookup"><span data-stu-id="58c65-116">**Require MFA for Service Management** &ndash; Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="58c65-117">Microsoft recomienda habilitar todas estas directivas de línea base.</span><span class="sxs-lookup"><span data-stu-id="58c65-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="58c65-118">Una vez habilitadas estas directivas, se pedirá a los administradores y a los usuarios que se registren para la autenticación de varios factores de Azure.</span><span class="sxs-lookup"><span data-stu-id="58c65-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="58c65-119">Para obtener más información acerca de estas directivas, vea [¿Qué son las directivas de línea base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span><span class="sxs-lookup"><span data-stu-id="58c65-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="58c65-120">Configurar directivas de línea base</span><span class="sxs-lookup"><span data-stu-id="58c65-120">Set up baseline policies</span></span>

1. <span data-ttu-id="58c65-121">Vaya a [Azure portal](https://portal.azure.com)y navegue a **Azure Active Directory** \> **Conditional Access**.</span><span class="sxs-lookup"><span data-stu-id="58c65-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="58c65-122">Las directivas de línea base se enumeran en la página.</span><span class="sxs-lookup"><span data-stu-id="58c65-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="58c65-123">![Página donde se enumeran las directivas de línea base para el acceso condicional.](../media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="58c65-123">![Page that lists baseline policies for conditional access.](../media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="58c65-124">Consulte las siguientes instrucciones específicas para cada directiva:</span><span class="sxs-lookup"><span data-stu-id="58c65-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="58c65-125">Requerir MFA para los administradores</span><span class="sxs-lookup"><span data-stu-id="58c65-125">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="58c65-126">Requerir MFA para los usuarios</span><span class="sxs-lookup"><span data-stu-id="58c65-126">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="58c65-127">Bloquear la autenticación heredada</span><span class="sxs-lookup"><span data-stu-id="58c65-127">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="58c65-128">Requerir MFA para la administración de servicios</span><span class="sxs-lookup"><span data-stu-id="58c65-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="58c65-129">Puede configurar muchas directivas adicionales, como requerir aplicaciones cliente aprobadas.</span><span class="sxs-lookup"><span data-stu-id="58c65-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="58c65-130">Para obtener más información, consulte la [documentación de acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="58c65-130">For more information, see the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
