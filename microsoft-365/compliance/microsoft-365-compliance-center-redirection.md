---
title: Redirigir usuarios desde el Office 365 seguridad y cumplimiento al Centro de cumplimiento de Microsoft 365
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Obtenga información sobre cómo redirigir automáticamente Office 365 usuarios del Centro de seguridad y cumplimiento al Centro de cumplimiento de Microsoft 365..
ms.collection: M365-security-compliance
ms.openlocfilehash: 62fc302f9f065ac7bb0475a6e72dc240a56a1fe1
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339411"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="51d4f-103">Redirigir usuarios desde el Office 365 seguridad y cumplimiento al Centro de cumplimiento de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="51d4f-103">Redirect users from the Office 365 Security and Compliance center to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="51d4f-104">En este artículo se explica cómo funciona la redirección automática para los usuarios que tienen acceso a soluciones de cumplimiento desde el Centro de seguridad y cumplimiento de Office 365 (protection.office.com) hasta el Centro de cumplimiento de Microsoft 365 (compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="51d4f-104">This article explains how automatic redirection works for users accessing compliance solutions from the Office 365 Security and Compliance Center (protection.office.com) to the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="51d4f-105">Qué esperar</span><span class="sxs-lookup"><span data-stu-id="51d4f-105">What to expect</span></span>

<span data-ttu-id="51d4f-106">El redireccionamiento automático está habilitado de forma predeterminada para todos los usuarios que tengan acceso a las siguientes soluciones relacionadas con el cumplimiento en Office 365 seguridad y cumplimiento (protection.office.com):</span><span class="sxs-lookup"><span data-stu-id="51d4f-106">Automatic redirection is enabled by default for all users accessing the following compliance-related solutions in Office 365 Security and Compliance (protection.office.com):</span></span>

- <span data-ttu-id="51d4f-107">Prevención de pérdida de datos (DLP)</span><span class="sxs-lookup"><span data-stu-id="51d4f-107">Data loss prevention (DLP)</span></span>
- <span data-ttu-id="51d4f-108">Clasificación</span><span class="sxs-lookup"><span data-stu-id="51d4f-108">Classification</span></span>
- <span data-ttu-id="51d4f-109">Información de gobierno</span><span class="sxs-lookup"><span data-stu-id="51d4f-109">Information governance</span></span>
- <span data-ttu-id="51d4f-110">Administración de registros</span><span class="sxs-lookup"><span data-stu-id="51d4f-110">Records management</span></span>
- <span data-ttu-id="51d4f-111">Cumplimiento de comunicaciones (anteriormente "Supervisión")</span><span class="sxs-lookup"><span data-stu-id="51d4f-111">Communication compliance (formerly 'Supervision')</span></span>

<span data-ttu-id="51d4f-112">Los usuarios se enruta automáticamente a las mismas soluciones de cumplimiento en el Centro de cumplimiento de Microsoft 365 (compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="51d4f-112">Users are automatically routed to the same compliance solutions in the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="51d4f-113">Para otras soluciones de cumplimiento incluidas en el Centro de seguridad y cumplimiento de Office 365, los usuarios seguirán administrando estas soluciones en el Centro de cumplimiento de Microsoft 365 o en el Centro de seguridad y cumplimiento de Office 365.</span><span class="sxs-lookup"><span data-stu-id="51d4f-113">For other compliance solutions included in the Office 365 Security and Compliance Center, users will continue to manage these solutions in either the Microsoft 365 compliance center or the Office 365 Security and Compliance Center.</span></span> <span data-ttu-id="51d4f-114">La redirección automática de estas soluciones de cumplimiento estará disponible próximamente.</span><span class="sxs-lookup"><span data-stu-id="51d4f-114">The automatic redirection for these compliance solutions will be available soon.</span></span>

<span data-ttu-id="51d4f-115">Esta característica y los controles asociados no habilitan la redirección automática de características de seguridad para Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="51d4f-115">This feature and associated controls does not enable the automatic redirection of Security features for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="51d4f-116">Para habilitar el redireccionamiento de características de seguridad, vea [Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="51d4f-116">To enable the redirection for security features, see [Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) for details.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="51d4f-117">¿Puedo volver a usar el portal anterior?</span><span class="sxs-lookup"><span data-stu-id="51d4f-117">Can I go back to using the former portal?</span></span>

<span data-ttu-id="51d4f-118">Si algo no funciona para usted o si hay algo que no puede completar a través del portal de Centro de cumplimiento de Microsoft 365, puede deshabilitar temporalmente el redireccionamiento automático para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="51d4f-118">If something isn't working for you or if there's anything you're unable to complete through the Microsoft 365 compliance center portal, you can temporarily disable the automatic redirection for all users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51d4f-119">El Centro de cumplimiento de Microsoft 365 es el portal de administración de reemplazo para soluciones de cumplimiento actualmente administradas en el centro de seguridad y cumplimiento Office 365 de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="51d4f-119">The Microsoft 365 compliance center is the replacement management portal for compliance solutions currently managed in the Office 365 Security and Compliance center.</span></span> <span data-ttu-id="51d4f-120">Todas Microsoft 365 de cumplimiento normativo se administrarán únicamente en el Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51d4f-120">All Microsoft 365 compliance solutions will be managed solely in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="51d4f-121">Deshabilitar la redirección a la Centro de cumplimiento de Microsoft 365 debe ser una solución a corto plazo.</span><span class="sxs-lookup"><span data-stu-id="51d4f-121">Disabling redirection to the Microsoft 365 compliance center should be a short-term solution.</span></span>

<span data-ttu-id="51d4f-122">Para volver al Centro Office 365 seguridad y cumplimiento (protection.microsoft.com) para todos los usuarios, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="51d4f-122">To switch back to the Office 365 Security and Compliance center (protection.microsoft.com) for all users, complete the following steps:</span></span>

1. <span data-ttu-id="51d4f-123">Inicie sesión en el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com) como administrador global o mediante cualquier cuenta con permisos de administrador de cumplimiento en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="51d4f-123">Sign in to the [Microsoft 365 compliance center](https://compliance.microsoft.com) as a global administrator or using any account with compliance administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="51d4f-124">Vaya **a** Configuración  >  **redirección del centro de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="51d4f-124">Navigate to **Settings** > **Compliance center redirection**.</span></span>
3. <span data-ttu-id="51d4f-125">Alterna la opción Redirección automática a **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="51d4f-125">Toggle the Automatic redirection setting to **Off**.</span></span>
4. <span data-ttu-id="51d4f-126">Seleccione **Desactivar y** compartir comentarios cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="51d4f-126">Select **Turn off** and share feedback when prompted.</span></span>

<span data-ttu-id="51d4f-127">Una vez deshabilitado, los usuarios ya no se enrutarán a compliance.microsoft.com y se dirigirán al Centro de seguridad y cumplimiento de Office 365 (protection.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="51d4f-127">Once disabled, users will no longer be routed to compliance.microsoft.com and they will be directed to the Office 365 Security and Compliance center (protection.microsoft.com).</span></span> <span data-ttu-id="51d4f-128">Los administradores globales o de cumplimiento pueden habilitar esta configuración de nuevo en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="51d4f-128">This setting can be enabled again at any time by Global or Compliance admins.</span></span>

## <a name="related-information"></a><span data-ttu-id="51d4f-129">Información relacionada</span><span class="sxs-lookup"><span data-stu-id="51d4f-129">Related information</span></span>

- [<span data-ttu-id="51d4f-130">Centro de cumplimiento de Microsoft 365 información general</span><span class="sxs-lookup"><span data-stu-id="51d4f-130">Microsoft 365 compliance center overview</span></span>](/microsoft-365/compliance/microsoft-365-compliance-center)
