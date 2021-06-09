---
title: Requisitos previos para las cuentas de invitado
description: Directrices de configuración para cuentas de invitado y cómo ajustarlas
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: d29b9d6bdc30d981b273d95925ba740bc92304c4
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694250"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="daab3-104">Requisitos previos para las cuentas de invitado</span><span class="sxs-lookup"><span data-stu-id="daab3-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="daab3-105">Escritorio administrado de Microsoft requiere la siguiente configuración en la organización de Azure AD para el acceso a la cuenta de invitado.</span><span class="sxs-lookup"><span data-stu-id="daab3-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="daab3-106">Puede ajustar esta configuración en [Azure Portal](https://portal.azure.com) en **Identidades externas / Configuración de colaboración externa:**</span><span class="sxs-lookup"><span data-stu-id="daab3-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration settings**:</span></span>

-   <span data-ttu-id="daab3-107">Para **las restricciones de invitación de invitado establecidas** en Usuarios miembros y usuarios asignados a roles de administrador específicos pueden invitar a usuarios **invitados,** incluidos los invitados con permisos de miembro</span><span class="sxs-lookup"><span data-stu-id="daab3-107">For **Guest invite restrictions** set to **Member users and users assigned to specific admin roles can invite guest users including guests with member permissions**</span></span>
-   <span data-ttu-id="daab3-108">Para **restricciones de colaboración,** elija cualquiera de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="daab3-108">For **Collaboration restrictions**, choose any of these options:</span></span>
    -   <span data-ttu-id="daab3-109">Si selecciona Permitir **que las invitaciones se envíen a cualquier dominio (más inclusivo),** no se requiere ninguna otra configuración.</span><span class="sxs-lookup"><span data-stu-id="daab3-109">If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration required.</span></span>
    -   <span data-ttu-id="daab3-110">Si selecciona Denegar invitaciones a los dominios **especificados,** asegúrese de que Microsoft.com no aparece en los dominios de destino.</span><span class="sxs-lookup"><span data-stu-id="daab3-110">If you select **Deny invitations to the specified domains**, make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="daab3-111">Si selecciona Permitir invitaciones solo a los dominios **especificados (más**  restrictivos), asegúrese de que Microsoft.com en los dominios de destino.</span><span class="sxs-lookup"><span data-stu-id="daab3-111">If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="daab3-112">Si establece restricciones que interactúan con estas opciones de configuración, asegúrese de excluir las Azure Active Directory **modern Workplace Service Accounts**.</span><span class="sxs-lookup"><span data-stu-id="daab3-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="daab3-113">Por ejemplo, si tiene una directiva de acceso condicional que impide que las cuentas de invitado tengan acceso al portal de Intune, excluya el grupo **Cuentas** de servicio de lugares de trabajo modernos de esta directiva.</span><span class="sxs-lookup"><span data-stu-id="daab3-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="daab3-114">Pasos para prepararse</span><span class="sxs-lookup"><span data-stu-id="daab3-114">Steps to get ready</span></span>

1. <span data-ttu-id="daab3-115">Revisar los [requisitos previos del Escritorio administrado de Microsoft](prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="daab3-115">Review [prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="daab3-116">Usar las [herramientas para evaluar la preparación](readiness-assessment-tool.md)</span><span class="sxs-lookup"><span data-stu-id="daab3-116">Use [readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. <span data-ttu-id="daab3-117">[Requisitos previos para cuentas invitadas](guest-accounts.md) (este artículo)</span><span class="sxs-lookup"><span data-stu-id="daab3-117">[Prerequisites for guest accounts](guest-accounts.md) (This article)</span></span>
4. [<span data-ttu-id="daab3-118">Configuración de red para el Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="daab3-118">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="daab3-119">Preparar los certificados y los perfiles de red para el Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="daab3-119">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="daab3-120">Preparar el acceso a los recursos locales para el Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="daab3-120">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="daab3-121">Aplicaciones en el Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="daab3-121">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="daab3-122">Preparar unidades asignadas para el Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="daab3-122">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="daab3-123">Preparar recursos de impresión para el Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="daab3-123">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
