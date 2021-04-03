---
title: Requisitos previos para cuentas de invitados
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
ms.openlocfilehash: bbf679a01716fc48d37b241d69740f50a985f048
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574612"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="0c40c-104">Requisitos previos para cuentas de invitados</span><span class="sxs-lookup"><span data-stu-id="0c40c-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="0c40c-105">Microsoft Managed Desktop requiere la siguiente configuración en la organización de Azure AD para el acceso a la cuenta de invitado.</span><span class="sxs-lookup"><span data-stu-id="0c40c-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="0c40c-106">Puede ajustar esta configuración en [Azure Portal](https://portal.azure.com) en **Identidades externas / Colaboración externa:**</span><span class="sxs-lookup"><span data-stu-id="0c40c-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration**:</span></span>

-   <span data-ttu-id="0c40c-107">**Los administradores y usuarios del rol invitado** invitado pueden invitar establecido en **Sí**</span><span class="sxs-lookup"><span data-stu-id="0c40c-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="0c40c-108">Para **restricciones de colaboración,** elija cualquiera de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="0c40c-108">For **Collaboration restrictions**, choose any of these options:</span></span>
    -   <span data-ttu-id="0c40c-109">Si selecciona Permitir **que las invitaciones se envíen a cualquier dominio (más inclusivo),** no se requiere ninguna otra configuración.</span><span class="sxs-lookup"><span data-stu-id="0c40c-109">If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration required.</span></span>
    -   <span data-ttu-id="0c40c-110">Si selecciona Denegar invitaciones a los dominios **especificados,** asegúrese de que Microsoft.com no aparece en los dominios de destino.</span><span class="sxs-lookup"><span data-stu-id="0c40c-110">If you select **Deny invitations to the specified domains**, make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="0c40c-111">Si selecciona Permitir invitaciones solo a los dominios **especificados (más**  restrictivos), asegúrese de que Microsoft.com en los dominios de destino.</span><span class="sxs-lookup"><span data-stu-id="0c40c-111">If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="0c40c-112">Si establece restricciones que interactúan con esta configuración, asegúrese de excluir las cuentas de servicio de Azure Active Directory **Modern Workplace**.</span><span class="sxs-lookup"><span data-stu-id="0c40c-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="0c40c-113">Por ejemplo, si tiene una directiva de acceso condicional que impide que las cuentas de invitado tengan acceso al portal de Intune, excluya el grupo **Cuentas** de servicio de lugares de trabajo modernos de esta directiva.</span><span class="sxs-lookup"><span data-stu-id="0c40c-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="0c40c-114">Pasos para prepararse</span><span class="sxs-lookup"><span data-stu-id="0c40c-114">Steps to get ready</span></span>

1. <span data-ttu-id="0c40c-115">Revisar [los requisitos previos de Microsoft Managed Desktop](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="0c40c-115">Review [prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="0c40c-116">Use [herramientas de evaluación de preparación](readiness-assessment-tool.md).</span><span class="sxs-lookup"><span data-stu-id="0c40c-116">Use [readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. <span data-ttu-id="0c40c-117">[Requisitos previos para cuentas invitadas](guest-accounts.md) (este artículo)</span><span class="sxs-lookup"><span data-stu-id="0c40c-117">[Prerequisites for guest accounts](guest-accounts.md) (This article)</span></span>
4. [<span data-ttu-id="0c40c-118">Configuración de red para el Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0c40c-118">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="0c40c-119">Preparar los certificados y los perfiles de red para el Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0c40c-119">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="0c40c-120">Preparar el acceso a los recursos locales para el Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0c40c-120">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="0c40c-121">Aplicaciones en Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0c40c-121">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="0c40c-122">Preparar unidades asignadas para el Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0c40c-122">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="0c40c-123">Preparar recursos de impresión para el Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0c40c-123">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)