---
title: Acciones de corrección en investigación automatizada y funciones de respuesta de la protección contra amenazas de Microsoft
description: Obtenga información general sobre la investigación y respuesta automatizada en la Protección contra amenazas de Microsoft
keywords: automatizada, investigación, alerta, desencadenante, acción, corrección
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 73bb90a0537df8e6f23e4e0e50a748aebda3a487
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175967"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a><span data-ttu-id="bef25-104">Acciones de corrección en investigación automatizada y funciones de respuesta de la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bef25-104">Remediation actions in automated investigation and response capabilities in Microsoft Threat Protection</span></span>

<span data-ttu-id="bef25-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="bef25-105">**Applies to:**</span></span>
- <span data-ttu-id="bef25-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bef25-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="bef25-107">Las capacidades de investigación y respuesta automatizadas de Microsoft Threat Protection incluyen ciertas acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="bef25-107">Automated investigation and response capabilities in Microsoft Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="bef25-108">Algunos tipos de acciones de corrección se realizan en dispositivos, también conocidos como puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="bef25-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="bef25-109">Otras acciones de corrección se realizan en el contenido del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="bef25-109">Other remediation actions are taken on email content.</span></span>

<span data-ttu-id="bef25-110">En la tabla siguiente se resumen las acciones de corrección que son compatibles actualmente con la protección contra amenazas de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="bef25-110">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="bef25-111">Acciones de corrección de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="bef25-111">Endpoints remediation actions</span></span>  |<span data-ttu-id="bef25-112">Acciones de corrección de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="bef25-112">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="bef25-113">Poner archivo en cuarentena</span><span class="sxs-lookup"><span data-stu-id="bef25-113">Quarantine file</span></span><br/><span data-ttu-id="bef25-114">Eliminar clave del registro</span><span class="sxs-lookup"><span data-stu-id="bef25-114">Remove registry key</span></span><br/><span data-ttu-id="bef25-115">Terminar proceso</span><span class="sxs-lookup"><span data-stu-id="bef25-115">Kill process</span></span> <br/><span data-ttu-id="bef25-116">Detener el servicio</span><span class="sxs-lookup"><span data-stu-id="bef25-116">Stop service</span></span> <br/><span data-ttu-id="bef25-117">Eliminar clave del registro</span><span class="sxs-lookup"><span data-stu-id="bef25-117">Remove registry key</span></span> <br/><span data-ttu-id="bef25-118">Deshabilitar controlador</span><span class="sxs-lookup"><span data-stu-id="bef25-118">Disable driver</span></span> <br/><span data-ttu-id="bef25-119">Eliminar tarea programada.</span><span class="sxs-lookup"><span data-stu-id="bef25-119">Remove scheduled task</span></span>      |<span data-ttu-id="bef25-120">Eliminar temporalmente mensajes de correo electrónico o clústeres</span><span class="sxs-lookup"><span data-stu-id="bef25-120">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="bef25-121">Bloquear URL (tiempo de clic)</span><span class="sxs-lookup"><span data-stu-id="bef25-121">Block URL (time-of-click)</span></span><br/><span data-ttu-id="bef25-122">Desactivar el reenvío de correo externo</span><span class="sxs-lookup"><span data-stu-id="bef25-122">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="bef25-123">Las acciones de corrección, tanto si están pendientes de aprobación como si ya están completas, se pueden ver en el [centro de actividades](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="bef25-123">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="next-steps"></a><span data-ttu-id="bef25-124">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="bef25-124">Next steps</span></span>

- [<span data-ttu-id="bef25-125">Aprobar o rechazar acciones relacionadas con la investigación y la respuesta automatizadas</span><span class="sxs-lookup"><span data-stu-id="bef25-125">Approve or reject actions related to automated investigation and response</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="bef25-126">Más información sobre el Centro de actividades</span><span class="sxs-lookup"><span data-stu-id="bef25-126">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
