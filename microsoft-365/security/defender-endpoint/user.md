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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 39b73772bcc626590aa784bb5b21357f66229816
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772142"
---
# <a name="user-resource-type"></a><span data-ttu-id="bf15b-104">Tipo de recurso de usuario</span><span class="sxs-lookup"><span data-stu-id="bf15b-104">User resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bf15b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="bf15b-105">**Applies to:**</span></span>
- [<span data-ttu-id="bf15b-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="bf15b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="bf15b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf15b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bf15b-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="bf15b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bf15b-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="bf15b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="bf15b-110">Método</span><span class="sxs-lookup"><span data-stu-id="bf15b-110">Method</span></span>|<span data-ttu-id="bf15b-111">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bf15b-111">Return Type</span></span> |<span data-ttu-id="bf15b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf15b-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="bf15b-113">Enumerar alertas relacionadas con el usuario</span><span class="sxs-lookup"><span data-stu-id="bf15b-113">List User related alerts</span></span>](get-user-related-alerts.md) | <span data-ttu-id="bf15b-114">Colección [alert](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="bf15b-114">[alert](alerts.md) collection</span></span> |  <span data-ttu-id="bf15b-115">Enumerar todas las alertas asociadas a un [usuario](user.md).</span><span class="sxs-lookup"><span data-stu-id="bf15b-115">List all the alerts that are associated with a [user](user.md).</span></span>
[<span data-ttu-id="bf15b-116">Enumerar dispositivos relacionados con el usuario</span><span class="sxs-lookup"><span data-stu-id="bf15b-116">List User related devices</span></span>](get-user-related-machines.md) | <span data-ttu-id="bf15b-117">[colección machine](machine.md)</span><span class="sxs-lookup"><span data-stu-id="bf15b-117">[machine](machine.md) collection</span></span> | <span data-ttu-id="bf15b-118">Enumerar todos los dispositivos que un usuario ha iniciado [sesión.](user.md)</span><span class="sxs-lookup"><span data-stu-id="bf15b-118">List all the devices that were logged on by a [user](user.md).</span></span>
