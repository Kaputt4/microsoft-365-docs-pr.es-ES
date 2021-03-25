---
title: Cola de alertas en el Centro de seguridad de Microsoft Defender
ms.reviewer: ''
description: Ver y administrar las alertas que se han presentado en el Centro de seguridad de Microsoft Defender
keywords: ''
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.date: 09/03/2018
ms.technology: mde
ms.openlocfilehash: d40fc887f26dfe62e05f7ee6ac7bbbb8ac45a402
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075440"
---
# <a name="alerts-queue-in-microsoft-defender-security-center"></a><span data-ttu-id="53646-103">Cola de alertas en el Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="53646-103">Alerts queue in Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="53646-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="53646-104">**Applies to:**</span></span>
- [<span data-ttu-id="53646-105">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="53646-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="53646-106">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="53646-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="53646-107">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="53646-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="53646-108">Obtenga información sobre cómo puede ver y administrar la cola para que pueda investigar eficazmente las amenazas que se ven en entidades como dispositivos, archivos o cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="53646-108">Learn how you can view and manage the queue so that you can effectively investigate threats seen on entities such as devices, files, or user accounts.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="53646-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="53646-109">In this section</span></span>
<span data-ttu-id="53646-110">Tema</span><span class="sxs-lookup"><span data-stu-id="53646-110">Topic</span></span> | <span data-ttu-id="53646-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="53646-111">Description</span></span> 
:---|:---
[<span data-ttu-id="53646-112">Ver y organizar la cola de alertas</span><span class="sxs-lookup"><span data-stu-id="53646-112">View and organize the Alerts queue</span></span>](alerts-queue.md) | <span data-ttu-id="53646-113">Muestra una lista de alertas marcadas en la red.</span><span class="sxs-lookup"><span data-stu-id="53646-113">Shows a list of alerts that were flagged in your network.</span></span>
[<span data-ttu-id="53646-114">Administrar alertas</span><span class="sxs-lookup"><span data-stu-id="53646-114">Manage alerts</span></span>](manage-alerts.md) | <span data-ttu-id="53646-115">Obtenga información sobre cómo administrar alertas como cambiar su estado, asignarla a un miembro de operaciones de seguridad y ver el historial de una alerta.</span><span class="sxs-lookup"><span data-stu-id="53646-115">Learn about how you can manage alerts such as change its status, assign it to a security operations member, and see the history of an alert.</span></span>
[<span data-ttu-id="53646-116">Investigar alertas</span><span class="sxs-lookup"><span data-stu-id="53646-116">Investigate alerts</span></span>](investigate-alerts.md)| <span data-ttu-id="53646-117">Investigue las alertas que afectan a la red, comprenda lo que significan y cómo resolverlas.</span><span class="sxs-lookup"><span data-stu-id="53646-117">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>
[<span data-ttu-id="53646-118">Investigar archivos</span><span class="sxs-lookup"><span data-stu-id="53646-118">Investigate files</span></span>](investigate-files.md)| <span data-ttu-id="53646-119">Investigue los detalles de un archivo asociado a una alerta, comportamiento o evento específicos.</span><span class="sxs-lookup"><span data-stu-id="53646-119">Investigate the details of a file associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="53646-120">Investigar dispositivos</span><span class="sxs-lookup"><span data-stu-id="53646-120">Investigate devices</span></span>](investigate-machines.md)| <span data-ttu-id="53646-121">Investigar los detalles de un dispositivo asociado a una alerta, comportamiento o evento específicos.</span><span class="sxs-lookup"><span data-stu-id="53646-121">Investigate the details of a device associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="53646-122">Investigar una dirección IP</span><span class="sxs-lookup"><span data-stu-id="53646-122">Investigate an IP address</span></span>](investigate-ip.md) | <span data-ttu-id="53646-123">Examine las posibles comunicaciones entre dispositivos de la red y las direcciones IP (protocolos de Internet externos).</span><span class="sxs-lookup"><span data-stu-id="53646-123">Examine possible communication between devices in your network and external internet protocol (IP) addresses.</span></span>
[<span data-ttu-id="53646-124">Investigar un dominio</span><span class="sxs-lookup"><span data-stu-id="53646-124">Investigate a domain</span></span>](investigate-domain.md) | <span data-ttu-id="53646-125">Investigue un dominio para ver si los dispositivos y servidores de la red se han estado comunicando con un dominio malintencionado conocido.</span><span class="sxs-lookup"><span data-stu-id="53646-125">Investigate a domain to see if devices and servers in your network have been communicating with a known malicious domain.</span></span> 
[<span data-ttu-id="53646-126">Investigar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="53646-126">Investigate a user account</span></span>](investigate-user.md) | <span data-ttu-id="53646-127">Identifique las cuentas de usuario con las alertas más activas e investigue los casos de posibles credenciales comprometidas.</span><span class="sxs-lookup"><span data-stu-id="53646-127">Identify user accounts with the most active alerts and investigate cases of potential compromised credentials.</span></span>  


