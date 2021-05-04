---
title: Obtener información sobre la directiva de prevención de pérdida de datos predeterminada en Microsoft Teams (versión preliminar)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Obtenga información sobre la directiva de prevención de pérdida de datos predeterminada en Microsoft Teams
ms.openlocfilehash: 0663c370373708009346d4f858729e17436f0f62
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114148"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a><span data-ttu-id="68d95-103">Obtener información sobre la directiva de prevención de pérdida de datos predeterminada en Microsoft Teams (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="68d95-103">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>

<span data-ttu-id="68d95-104">[Las capacidades de prevención](dlp-learn-about-dlp.md) de pérdida de datos se han ampliado para incluir Microsoft Teams chat y mensajes de canal, incluidos los mensajes de canal privado.</span><span class="sxs-lookup"><span data-stu-id="68d95-104">[Data loss prevention](dlp-learn-about-dlp.md) capabilities have been extended to include Microsoft Teams chat and channel messages, including private channel messages.</span></span> <span data-ttu-id="68d95-105">Como parte de esta versión, creamos una directiva DLP predeterminada para los clientes por primera vez en el Centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="68d95-105">As a part of this release, we created a default DLP policy for first-time customers to Compliance center.</span></span>

## <a name="applies-to"></a><span data-ttu-id="68d95-106">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="68d95-106">Applies to</span></span>

<span data-ttu-id="68d95-107">Cualquier inquilino con licencia con una o varias de las siguientes licencias y que tenga usuarios Teams activo</span><span class="sxs-lookup"><span data-stu-id="68d95-107">Any tenant who is licensed with one or more of the below licenses and have active Teams users</span></span>
 
- <span data-ttu-id="68d95-108">ME5,</span><span class="sxs-lookup"><span data-stu-id="68d95-108">ME5,</span></span> 
- <span data-ttu-id="68d95-109">MA5,</span><span class="sxs-lookup"><span data-stu-id="68d95-109">MA5,</span></span> 
- <span data-ttu-id="68d95-110">Cumplimiento de E5/A5,</span><span class="sxs-lookup"><span data-stu-id="68d95-110">E5/A5 Compliance,</span></span> 
- <span data-ttu-id="68d95-111">IP+G,</span><span class="sxs-lookup"><span data-stu-id="68d95-111">IP+G,</span></span> 
- <span data-ttu-id="68d95-112">OE5,</span><span class="sxs-lookup"><span data-stu-id="68d95-112">OE5,</span></span> 
- <span data-ttu-id="68d95-113">Cumplimiento avanzado de O365</span><span class="sxs-lookup"><span data-stu-id="68d95-113">O365 Advanced Compliance</span></span> 
- <span data-ttu-id="68d95-114">EMS E5</span><span class="sxs-lookup"><span data-stu-id="68d95-114">EMS E5</span></span>


## <a name="what-does-the-default-policy-do"></a><span data-ttu-id="68d95-115">¿Qué hace la directiva predeterminada?</span><span class="sxs-lookup"><span data-stu-id="68d95-115">What does the default policy do?</span></span>

<span data-ttu-id="68d95-116">La directiva DLP predeterminada realiza un seguimiento de todos los números de tarjeta de crédito compartidos interna y externamente en la organización.</span><span class="sxs-lookup"><span data-stu-id="68d95-116">The default DLP policy tracks all the credit card numbers shared internally and externally to the organization.</span></span> <span data-ttu-id="68d95-117">Esta directiva está predeterminada para todos los usuarios del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="68d95-117">This policy is on by default for all users of the tenant.</span></span> <span data-ttu-id="68d95-118">No genera ninguna sugerencia de directiva para los usuarios finales, pero genera un evento Alert y también desencadena un correo electrónico de baja gravedad para el administrador (agregado en la directiva).</span><span class="sxs-lookup"><span data-stu-id="68d95-118">It does not generate any policy tips for end users but does generate an Alert event and also triggers a low severity email to the admin (added in the policy).</span></span> <span data-ttu-id="68d95-119">El administrador puede ver las actividades y editar los detalles de las directivas iniciando sesión en el Centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="68d95-119">Administrator can view the activities and edit the policies details by logging into the Compliance center.</span></span>

<span data-ttu-id="68d95-120">Los administradores pueden ver esta directiva en la página Directivas de [prevención](https://compliance.microsoft.com/compliancesettings) > centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="68d95-120">Admins can view this policy in the [Compliance center](https://compliance.microsoft.com/compliancesettings) > Data Loss prevention policies page.</span></span>


> [!div class="mx-imgBorder"]
> <span data-ttu-id="68d95-121">![directiva Teams DLP predeterminada](../media/default-teams-dlp-policy.png)</span><span class="sxs-lookup"><span data-stu-id="68d95-121">![default Teams DLP policy](../media/default-teams-dlp-policy.png)</span></span>

## <a name="edit-or-delete-the-default-policy"></a><span data-ttu-id="68d95-122">Editar o eliminar la directiva predeterminada</span><span class="sxs-lookup"><span data-stu-id="68d95-122">Edit or delete the default policy</span></span>

<span data-ttu-id="68d95-123">Para [editar la directiva predeterminada para un mejor rendimiento o eliminarla,](create-test-tune-dlp-policy.md#tune-a-dlp-policy)solo tiene que usar una cuenta con permisos de administración de cumplimiento **DLP.**</span><span class="sxs-lookup"><span data-stu-id="68d95-123">To [edit the default policy for better performance or to delete it](create-test-tune-dlp-policy.md#tune-a-dlp-policy), just use an account with **DLP Compliance Management** permissions.</span></span> <span data-ttu-id="68d95-124">Para obtener más información, vea [Permissions](create-test-tune-dlp-policy.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="68d95-124">For more information, see, [Permissions](create-test-tune-dlp-policy.md#permissions).</span></span>

