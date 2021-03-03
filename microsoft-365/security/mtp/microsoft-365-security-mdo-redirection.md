---
title: Redirigir cuentas de Microsoft Defender para Office 365 al nuevo centro de seguridad de Microsoft 365
description: Cómo redirigir desde Defender para Office 365 al Centro de seguridad de Microsoft 365.
keywords: Centro de seguridad de Microsoft 365, Introducción al centro de seguridad de Microsoft 365, redirección del centro de seguridad
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 30fa10e23fd6a0c92bd5a56c797d3b7ff5b4bfd6
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2021
ms.locfileid: "50416827"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a><span data-ttu-id="5deba-104">Redirigir cuentas de Microsoft Defender para Office 365 al Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5deba-104">Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5deba-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="5deba-105">**Applies to:**</span></span>

- <span data-ttu-id="5deba-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5deba-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="5deba-107">Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="5deba-107">Defender for Office 365</span></span>

<span data-ttu-id="5deba-108">En este artículo se explica cómo enrutar cuentas al Centro de seguridad de Microsoft 365 habilitando la redirección automática desde el antiguo Centro de seguridad y cumplimiento de Microsoft (protection.office.com o securitycenter.microsoft.com), al Centro de seguridad de Microsoft 365 (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="5deba-108">This article explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Security and Compliance Center (protection.office.com or securitycenter.microsoft.com), to the Microsoft 365 security center (security.microsoft.com).</span></span>

>[!NOTE]
> <span data-ttu-id="5deba-109">La funcionalidad de redirección del portal está disponible solo para clientes de Office 365 E5 y Microsoft Defender para office P2</span><span class="sxs-lookup"><span data-stu-id="5deba-109">Portal redirection capability is available for Office 365 E5 and Microsoft Defender for Office P2 customers only</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="5deba-110">Qué esperar</span><span class="sxs-lookup"><span data-stu-id="5deba-110">What to expect</span></span>
<span data-ttu-id="5deba-111">Una vez habilitada y activa la redirección automática, los usuarios que tengan acceso a las funciones relacionadas con la seguridad en Office 365 Seguridad y cumplimiento (protection.office.com), se enruta automáticamente al Centro de seguridad de Microsoft 365 ( https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="5deba-111">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to the Microsoft 365 security center (https://security.microsoft.com).</span></span>  

<span data-ttu-id="5deba-112">Obtenga más información sobre los cambios: [Microsoft Defender para Office 365 en el](microsoft-365-security-center-mdo.md)Centro de seguridad de Microsoft 365 .</span><span class="sxs-lookup"><span data-stu-id="5deba-112">Learn more about what’s changed: [Microsoft Defender for Office 365 in the Microsoft 365 security center](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="5deba-113">Con el redireccionamiento automático activado, los usuarios se enrutarán al Centro de seguridad de Microsoft 365 cuando usen funciones de seguridad en el Centro de seguridad y cumplimiento de Office 365.</span><span class="sxs-lookup"><span data-stu-id="5deba-113">With automatic redirection turned on, users will be routed to Microsoft 365 security center when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="5deba-114">Estas incluyen funcionalidades en la sección Administración de amenazas y en el panel e informes de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="5deba-114">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="5deba-115">Los elementos del Centro de seguridad y cumplimiento de Office 365 que no están relacionados con la seguridad no se redirigen al Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5deba-115">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to the Microsoft 365 security center.</span></span>

<span data-ttu-id="5deba-116">Los elementos relacionados con el cumplimiento se pueden encontrar en el Centro de cumplimiento de Microsoft 365 y los elementos relacionados con el flujo de correo se pueden encontrar en el Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="5deba-116">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="5deba-117">El resto de funcionalidades, ya sean relacionadas con el cumplimiento o las funcionalidades que sirven a ambos, no se ven afectadas por el redireccionamiento.</span><span class="sxs-lookup"><span data-stu-id="5deba-117">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="5deba-118">Las alertas de seguridad de Office 365 aparecen en el Centro de seguridad de Microsoft 365 y en el Centro de seguridad y cumplimiento de Office 365, sin redirección.</span><span class="sxs-lookup"><span data-stu-id="5deba-118">Office 365 security alerts appear in both the Microsoft 365 security center and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="5deba-119">Configurar la redirección del portal</span><span class="sxs-lookup"><span data-stu-id="5deba-119">Set up portal redirection</span></span>
<span data-ttu-id="5deba-120">Para iniciar el enrutamiento de cuentas al Centro de seguridad de Microsoft 365 en security.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="5deba-120">To start routing accounts to the Microsoft 365 security center at security.microsoft.com:</span></span>

1. <span data-ttu-id="5deba-121">Asegúrese de que es un administrador global o que tiene permisos de administrador de seguridad en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5deba-121">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="5deba-122">[Inicie sesión](https://security.microsoft.com/) en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5deba-122">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>
3. <span data-ttu-id="5deba-123">Vaya a **Configuración Correo**  >  **& redireccionamiento del** portal de  >  **colaboración.**</span><span class="sxs-lookup"><span data-stu-id="5deba-123">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="5deba-124">Alterna la configuración de redirección automática a **On**.</span><span class="sxs-lookup"><span data-stu-id="5deba-124">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="5deba-125">Haga **clic en** Habilitar para aplicar el redireccionamiento automático al portal del centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5deba-125">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

> [!NOTE]
> <span data-ttu-id="5deba-126">Una vez habilitada la redirección, las cuentas en sesiones activas mientras se aplica esta configuración no se expulsarán de su sesión y solo se enrutarán al centro de seguridad de Microsoft 365 después de finalizar la sesión actual y volver a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="5deba-126">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="5deba-127">¿Puedo volver a usar el portal anterior?</span><span class="sxs-lookup"><span data-stu-id="5deba-127">Can I go back to using the former portal?</span></span>
<span data-ttu-id="5deba-128">Si algo no funciona para usted o si hay algo que no se puede completar a través del portal del centro de seguridad de Microsoft 365, queremos escucharlo con la opción de comentarios del portal.</span><span class="sxs-lookup"><span data-stu-id="5deba-128">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="5deba-129">Si ha encontrado algún problema con el redireccionamiento, le recomendamos que se ponga en contacto con su compañero de pm directamente a través de la vista previa privada o háganoslo saber a través del formulario Enviar comentarios.</span><span class="sxs-lookup"><span data-stu-id="5deba-129">If you’ve encountered any issues with redirection, we encourage you to reach out to your PM buddy directly through private preview or let us know via the Give feedback submission form.</span></span>

<span data-ttu-id="5deba-130">Para volver al portal anterior:</span><span class="sxs-lookup"><span data-stu-id="5deba-130">To revert to the former portal:</span></span>

1. <span data-ttu-id="5deba-131">[Inicie sesión](https://security.microsoft.com/) en el Centro de seguridad de Microsoft 365 como administrador global o use y tenga una cuenta con permisos de administrador de seguridad en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5deba-131">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="5deba-132">Vaya a **Configuración**  >  **Desdireccionamiento del** Portal  >  **general**  >  **de extremos**.</span><span class="sxs-lookup"><span data-stu-id="5deba-132">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection**.</span></span>  

3. <span data-ttu-id="5deba-133">Alterna la opción Redirección automática a **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="5deba-133">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="5deba-134">Haga **clic en** Deshabilitar & compartir comentarios cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="5deba-134">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="5deba-135">Esta configuración se puede habilitar de nuevo en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="5deba-135">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="5deba-136">Una vez deshabilitadas, las cuentas ya no se enrutarán a security.microsoft.com y volverás a tener acceso al antiguo portal: securitycenter.windows.com o securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5deba-136">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="5deba-137">Información relacionada</span><span class="sxs-lookup"><span data-stu-id="5deba-137">Related information</span></span>
- [<span data-ttu-id="5deba-138">Vista general del Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5deba-138">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="5deba-139">Microsoft Defender para endpoint en el Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5deba-139">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="5deba-140">Microsoft ofrece SIEM y XDR unificados para modernizar las operaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="5deba-140">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="5deba-141">XDR frente a la infografía siem</span><span class="sxs-lookup"><span data-stu-id="5deba-141">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="5deba-142">El nuevo defensor</span><span class="sxs-lookup"><span data-stu-id="5deba-142">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="5deba-143">Acerca de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5deba-143">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="5deba-144">Portales de seguridad de Microsoft y centros de administración</span><span class="sxs-lookup"><span data-stu-id="5deba-144">Microsoft security portals and admin centers</span></span>](portals.md)