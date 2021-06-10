---
title: Redirigir cuentas desde el Centro Office 365 seguridad y cumplimiento al nuevo Microsoft 365 Defender
description: Cómo redirigir desde defender para Office 365 a Microsoft 365 Defender.
keywords: Microsoft 365 Defender, Introducción a Microsoft 365 Defender, redirección del centro de seguridad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842530"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a><span data-ttu-id="6d297-104">Redirigir cuentas desde el Centro Office 365 seguridad y cumplimiento a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d297-104">Redirecting accounts from Office 365 Security and Compliance Center to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6d297-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6d297-105">**Applies to:**</span></span>

- <span data-ttu-id="6d297-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d297-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="6d297-107">Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="6d297-107">Defender for Office 365</span></span>

<span data-ttu-id="6d297-108">En este artículo se explica cómo enrutar cuentas a Microsoft 365 Defender habilitando la redirección automática desde el antiguo Centro de seguridad y cumplimiento de Office 365 (protection.office.com), a Microsoft 365 Defender (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="6d297-108">This article explains how to route accounts to Microsoft 365 Defender by enabling automatic redirection from the former Office 365 Security and Compliance Center (protection.office.com), to Microsoft 365 Defender (security.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="6d297-109">Qué esperar</span><span class="sxs-lookup"><span data-stu-id="6d297-109">What to expect</span></span>
<span data-ttu-id="6d297-110">Una vez habilitada y activa la redirección automática, los usuarios que tengan acceso a las funciones relacionadas con la seguridad en Office 365 Seguridad y cumplimiento (protection.office.com), se enruta automáticamente a Microsoft 365 Defender ( https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="6d297-110">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to Microsoft 365 Defender (https://security.microsoft.com).</span></span>  

<span data-ttu-id="6d297-111">Obtenga más información sobre lo que ha cambiado: [Microsoft Defender para Office 365 en Microsoft 365 Defender](microsoft-365-security-center-mdo.md).</span><span class="sxs-lookup"><span data-stu-id="6d297-111">Learn more about what’s changed: [Microsoft Defender for Office 365 in Microsoft 365 Defender](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="6d297-112">Con el redireccionamiento automático activado, los usuarios se enrutarán a Microsoft 365 Defender cuando usen funciones de seguridad en el Centro de seguridad y cumplimiento Office 365 seguridad.</span><span class="sxs-lookup"><span data-stu-id="6d297-112">With automatic redirection turned on, users will be routed to Microsoft 365 Defender when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="6d297-113">Estas incluyen funcionalidades en la sección Administración de amenazas y en el panel e informes de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="6d297-113">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="6d297-114">Los elementos del Office 365 seguridad y cumplimiento que no están relacionados con la seguridad no se redirigen a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6d297-114">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to Microsoft 365 Defender.</span></span>

<span data-ttu-id="6d297-115">Los elementos relacionados con el cumplimiento se pueden encontrar en el centro de cumplimiento Microsoft 365 y los elementos relacionados con el flujo de correo se pueden encontrar en el centro de administración Exchange correo.</span><span class="sxs-lookup"><span data-stu-id="6d297-115">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="6d297-116">El resto de funcionalidades, ya sean relacionadas con el cumplimiento o las funcionalidades que sirven a ambos, no se ven afectadas por el redireccionamiento.</span><span class="sxs-lookup"><span data-stu-id="6d297-116">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="6d297-117">Office 365 alertas de seguridad aparecen tanto en Microsoft 365 Defender como en el Centro de seguridad y cumplimiento de Office 365, sin redirección.</span><span class="sxs-lookup"><span data-stu-id="6d297-117">Office 365 security alerts appear in both Microsoft 365 Defender and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="6d297-118">Configurar la redirección del portal</span><span class="sxs-lookup"><span data-stu-id="6d297-118">Set up portal redirection</span></span>
<span data-ttu-id="6d297-119">Para empezar a enrutar cuentas a Microsoft 365 Defender en security.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="6d297-119">To start routing accounts to Microsoft 365 Defender at security.microsoft.com:</span></span>

1. <span data-ttu-id="6d297-120">Asegúrese de que es un administrador global o que tiene permisos de administrador de seguridad en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6d297-120">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="6d297-121">[Inicie sesión](https://security.microsoft.com/) en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6d297-121">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender.</span></span>
3. <span data-ttu-id="6d297-122">Desplácese hasta **Configuración**  >  **correo & redireccionamiento del** portal de  >  **colaboración.**</span><span class="sxs-lookup"><span data-stu-id="6d297-122">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="6d297-123">Alterna la configuración de redirección automática a **On**.</span><span class="sxs-lookup"><span data-stu-id="6d297-123">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="6d297-124">Haga **clic en** Habilitar para aplicar la redirección automática a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6d297-124">Click **Enable** to apply automatic redirection to Microsoft 365 Defender.</span></span>

> [!NOTE]
> <span data-ttu-id="6d297-125">Una vez habilitada la redirección, las cuentas en sesiones activas mientras se aplica esta configuración no se expulsarán de su sesión y solo se enrutarán a Microsoft 365 Defender después de finalizar la sesión actual y volver a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="6d297-125">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="6d297-126">¿Puedo volver a usar el portal anterior?</span><span class="sxs-lookup"><span data-stu-id="6d297-126">Can I go back to using the former portal?</span></span>
<span data-ttu-id="6d297-127">Si algo no funciona para ti o si hay algo que no puedes completar a través de Microsoft 365 Defender, queremos escucharlo con la opción de comentarios del portal.</span><span class="sxs-lookup"><span data-stu-id="6d297-127">If something isn’t working for you or if there’s anything you’re unable to complete through Microsoft 365 Defender, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="6d297-128">Si ha encontrado algún problema con el redireccionamiento, háganoslo saber.</span><span class="sxs-lookup"><span data-stu-id="6d297-128">If you’ve encountered any issues with redirection, please let us know.</span></span>

<span data-ttu-id="6d297-129">Para volver al portal anterior:</span><span class="sxs-lookup"><span data-stu-id="6d297-129">To revert to the former portal:</span></span>

1. <span data-ttu-id="6d297-130">[Inicie sesión](https://security.microsoft.com/) en Microsoft 365 Defender como administrador global o usar y cuenta con permisos de administrador de seguridad en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6d297-130">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="6d297-131">Desplácese hasta **Configuración**  >  **correo & redireccionamiento del** portal de  >  **colaboración.**</span><span class="sxs-lookup"><span data-stu-id="6d297-131">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>   

3. <span data-ttu-id="6d297-132">Alterna la opción Redirección automática a **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="6d297-132">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="6d297-133">Haga **clic en** Deshabilitar & compartir comentarios cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="6d297-133">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="6d297-134">Esta configuración se puede habilitar de nuevo en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="6d297-134">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="6d297-135">Una vez deshabilitadas, las cuentas ya no se enrutarán a security.microsoft.com y volverás a tener acceso al portal anterior securitycenter.windows.com o securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="6d297-135">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal—securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="6d297-136">Información relacionada</span><span class="sxs-lookup"><span data-stu-id="6d297-136">Related information</span></span>
- [<span data-ttu-id="6d297-137">Microsoft 365 Introducción al defensor</span><span class="sxs-lookup"><span data-stu-id="6d297-137">Microsoft 365 Defender overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="6d297-138">Microsoft Defender para endpoint en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d297-138">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="6d297-139">Microsoft ofrece SIEM y XDR unificados para modernizar las operaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="6d297-139">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="6d297-140">XDR frente a la infografía siem</span><span class="sxs-lookup"><span data-stu-id="6d297-140">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="6d297-141">El nuevo defensor</span><span class="sxs-lookup"><span data-stu-id="6d297-141">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="6d297-142">Acerca de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d297-142">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="6d297-143">Portales de seguridad de Microsoft y centros de administración</span><span class="sxs-lookup"><span data-stu-id="6d297-143">Microsoft security portals and admin centers</span></span>](portals.md)
