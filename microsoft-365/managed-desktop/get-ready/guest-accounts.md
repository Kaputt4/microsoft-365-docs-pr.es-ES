---
title: Requisitos previos para las cuentas de invitado
description: Instrucciones de configuración para cuentas de invitado y cómo ajustarlas
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8953e9f451daa02671a1e1544f2dfe6649ab1b3
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073247"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="cd010-104">Requisitos previos para las cuentas de invitado</span><span class="sxs-lookup"><span data-stu-id="cd010-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="cd010-105">Microsoft Managed Desktop requiere la siguiente configuración en su organización de Azure AD para el acceso a la cuenta de invitado.</span><span class="sxs-lookup"><span data-stu-id="cd010-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="cd010-106">Puede ajustar esta configuración en el [portal de Azure](https://portal.azure.com) en **identidades externas/colaboración externa** :</span><span class="sxs-lookup"><span data-stu-id="cd010-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration** :</span></span>

-   <span data-ttu-id="cd010-107">**Los administradores y los usuarios de la función invitador invitado pueden invitar** a que se establezcan en **yes**</span><span class="sxs-lookup"><span data-stu-id="cd010-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="cd010-108">Para las **restricciones de colaboración** , elija una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="cd010-108">For **Collaboration restrictions** , choose any of these options:</span></span>
    -   <span data-ttu-id="cd010-109">Si selecciona **permitir que se envíen invitaciones a cualquier dominio (en la mayoría de los casos)** , no se requiere ninguna otra configuración.</span><span class="sxs-lookup"><span data-stu-id="cd010-109">If you select **Allow invitations to be sent to any domain (most inclusive)** , no other configuration required.</span></span>
    -   <span data-ttu-id="cd010-110">Si selecciona **denegar invitaciones a los dominios especificados** , asegúrese de que Microsoft.com no aparezca en los dominios de destino.</span><span class="sxs-lookup"><span data-stu-id="cd010-110">If you select **Deny invitations to the specified domains** , make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="cd010-111">Si selecciona **permitir invitaciones solo para los dominios especificados (más restrictivos)** , asegúrese de *que Microsoft.com aparezca* en los dominios de destino.</span><span class="sxs-lookup"><span data-stu-id="cd010-111">If you select **Allow invitations only to the specified domains (most restrictive)** , make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="cd010-112">Si establece restricciones que interactúan con esta configuración, asegúrese de excluir las cuentas de **servicio del área de trabajo moderna** de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cd010-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="cd010-113">Por ejemplo, si tiene una directiva de acceso condicional que impide que las cuentas de invitado obtengan acceso al portal de Intune, excluya el grupo de **cuentas de servicio del lugar de trabajo moderno** de esta Directiva.</span><span class="sxs-lookup"><span data-stu-id="cd010-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

