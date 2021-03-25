---
title: Tipo de recurso de usuario
description: Recupera alertas recientes de Microsoft Defender para puntos de conexión relacionadas con los usuarios.
keywords: apis, api de gráficos, api admitidas, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e3b2a567a953883d1d0ecd062159bfee4135dc85
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51197962"
---
# <a name="user-resource-type"></a><span data-ttu-id="f16be-104">Tipo de recurso de usuario</span><span class="sxs-lookup"><span data-stu-id="f16be-104">User resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f16be-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f16be-105">**Applies to:**</span></span>
- [<span data-ttu-id="f16be-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f16be-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="f16be-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f16be-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f16be-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="f16be-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f16be-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="f16be-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="f16be-110">Método</span><span class="sxs-lookup"><span data-stu-id="f16be-110">Method</span></span>|<span data-ttu-id="f16be-111">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f16be-111">Return Type</span></span> |<span data-ttu-id="f16be-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f16be-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="f16be-113">Enumerar alertas relacionadas con el usuario</span><span class="sxs-lookup"><span data-stu-id="f16be-113">List User related alerts</span></span>](get-user-related-alerts.md) | <span data-ttu-id="f16be-114">Colección [alert](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="f16be-114">[alert](alerts.md) collection</span></span> |  <span data-ttu-id="f16be-115">Enumerar todas las alertas asociadas a un [usuario](user.md).</span><span class="sxs-lookup"><span data-stu-id="f16be-115">List all the alerts that are associated with a [user](user.md).</span></span>
[<span data-ttu-id="f16be-116">Enumerar dispositivos relacionados con el usuario</span><span class="sxs-lookup"><span data-stu-id="f16be-116">List User related devices</span></span>](get-user-related-machines.md) | <span data-ttu-id="f16be-117">[colección machine](machine.md)</span><span class="sxs-lookup"><span data-stu-id="f16be-117">[machine](machine.md) collection</span></span> | <span data-ttu-id="f16be-118">Enumerar todos los dispositivos que un usuario ha iniciado [sesión.](user.md)</span><span class="sxs-lookup"><span data-stu-id="f16be-118">List all the devices that were logged on by a [user](user.md).</span></span>
