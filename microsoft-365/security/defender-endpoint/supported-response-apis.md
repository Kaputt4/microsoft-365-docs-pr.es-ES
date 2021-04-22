---
title: Api de respuesta admitidas de Microsoft Defender para puntos de conexión
description: Obtenga información sobre las llamadas específicas de Microsoft Defender para api de extremo relacionadas con la respuesta.
keywords: apis de respuesta, api de gráfico, api admitidas, actor, alertas, dispositivo, usuario, dominio, ip, archivo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 36ed1f624fda7ae413ffbbf807925cf00e0a23ca
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933774"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a><span data-ttu-id="11c58-104">Api de consulta de extremo admitidas de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="11c58-104">Supported Microsoft Defender for Endpoint query APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="11c58-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="11c58-105">**Applies to:**</span></span>
- [<span data-ttu-id="11c58-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="11c58-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> <span data-ttu-id="11c58-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="11c58-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="11c58-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="11c58-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

<span data-ttu-id="11c58-109">Obtenga información sobre las llamadas API relacionadas con la respuesta admitidas que puede ejecutar y detalles como los encabezados de solicitud necesarios y la respuesta esperada de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="11c58-109">Learn about the supported response-related API calls you can run and details such as the required request headers, and expected response from the calls.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="11c58-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="11c58-110">In this section</span></span>
<span data-ttu-id="11c58-111">Tema</span><span class="sxs-lookup"><span data-stu-id="11c58-111">Topic</span></span> | <span data-ttu-id="11c58-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="11c58-112">Description</span></span>
:---|:---
<span data-ttu-id="11c58-113">Recopilar paquete de investigación</span><span class="sxs-lookup"><span data-stu-id="11c58-113">Collect investigation package</span></span> | <span data-ttu-id="11c58-114">Ejecute esta API para recopilar un paquete de investigación desde un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="11c58-114">Run this API to collect an investigation package from a device.</span></span>
<span data-ttu-id="11c58-115">Aislar dispositivo</span><span class="sxs-lookup"><span data-stu-id="11c58-115">Isolate device</span></span> | <span data-ttu-id="11c58-116">Ejecute esta API para aislar un dispositivo de la red.</span><span class="sxs-lookup"><span data-stu-id="11c58-116">Run this API to isolate a device from the network.</span></span>
<span data-ttu-id="11c58-117">Unisolate device</span><span class="sxs-lookup"><span data-stu-id="11c58-117">Unisolate device</span></span> | <span data-ttu-id="11c58-118">Quita un dispositivo del aislamiento.</span><span class="sxs-lookup"><span data-stu-id="11c58-118">Remove a device from isolation.</span></span> 
<span data-ttu-id="11c58-119">Restringir la ejecución de código</span><span class="sxs-lookup"><span data-stu-id="11c58-119">Restrict code execution</span></span> | <span data-ttu-id="11c58-120">Ejecute esta API para contener un ataque deteniendo procesos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="11c58-120">Run this API to contain an attack by stopping malicious processes.</span></span> <span data-ttu-id="11c58-121">También puedes bloquear un dispositivo e impedir que se ejecuten los intentos posteriores de programas potencialmente malintencionados.</span><span class="sxs-lookup"><span data-stu-id="11c58-121">You can also lock down a device and prevent subsequent attempts of potentially malicious programs from running.</span></span>
<span data-ttu-id="11c58-122">Ejecución de código sin restricto</span><span class="sxs-lookup"><span data-stu-id="11c58-122">Unrestrict code execution</span></span> | <span data-ttu-id="11c58-123">Ejecute esto para revertir la restricción de la directiva de aplicaciones después de comprobar que el dispositivo en peligro se ha corregido.</span><span class="sxs-lookup"><span data-stu-id="11c58-123">Run this to reverse the restriction of applications policy after you have verified that the compromised device has been remediated.</span></span>
<span data-ttu-id="11c58-124">Ejecutar examen antivirus</span><span class="sxs-lookup"><span data-stu-id="11c58-124">Run antivirus scan</span></span> | <span data-ttu-id="11c58-125">Inicie de forma remota un examen antivirus para ayudar a identificar y corregir malware que podría estar presente en un dispositivo en peligro.</span><span class="sxs-lookup"><span data-stu-id="11c58-125">Remotely initiate an antivirus scan to help identify and remediate malware that might be present on a compromised device.</span></span>
<span data-ttu-id="11c58-126">Detener y poner en cuarentena un archivo</span><span class="sxs-lookup"><span data-stu-id="11c58-126">Stop and quarantine file</span></span> |  <span data-ttu-id="11c58-127">Ejecute esta llamada para detener la ejecución de procesos, poner en cuarentena archivos y eliminar la persistencia, como las claves del Registro.</span><span class="sxs-lookup"><span data-stu-id="11c58-127">Run this call to stop running processes, quarantine  files, and delete persistency such as registry keys.</span></span>
<span data-ttu-id="11c58-128">Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="11c58-128">Request sample</span></span> | <span data-ttu-id="11c58-129">Ejecute esta llamada para solicitar una muestra de un archivo desde un dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="11c58-129">Run this call to request a sample of a file from a specific device.</span></span> <span data-ttu-id="11c58-130">El archivo se recopilará desde el dispositivo y se cargará en un almacenamiento seguro.</span><span class="sxs-lookup"><span data-stu-id="11c58-130">The file will be collected from the device and uploaded to a secure storage.</span></span>
<span data-ttu-id="11c58-131">Bloquear archivo</span><span class="sxs-lookup"><span data-stu-id="11c58-131">Block file</span></span> | <span data-ttu-id="11c58-132">Ejecute esta API para evitar la propagación posterior de un ataque en su organización mediante la prohibición de archivos potencialmente malintencionados o malware sospechoso.</span><span class="sxs-lookup"><span data-stu-id="11c58-132">Run this API to prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 
<span data-ttu-id="11c58-133">Desbloquear archivo</span><span class="sxs-lookup"><span data-stu-id="11c58-133">Unblock file</span></span> | <span data-ttu-id="11c58-134">Permitir que un archivo se ejecute en la organización con Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="11c58-134">Allow a file run in the organization using Microsoft Defender Antivirus.</span></span>
<span data-ttu-id="11c58-135">Obtener EL URI de SAS del paquete</span><span class="sxs-lookup"><span data-stu-id="11c58-135">Get package SAS URI</span></span> | <span data-ttu-id="11c58-136">Ejecute esta API para obtener un URI que permita descargar un paquete de investigación.</span><span class="sxs-lookup"><span data-stu-id="11c58-136">Run this API to get a URI that allows downloading an investigation package.</span></span>
<span data-ttu-id="11c58-137">Obtener objeto MachineAction</span><span class="sxs-lookup"><span data-stu-id="11c58-137">Get MachineAction object</span></span> | <span data-ttu-id="11c58-138">Ejecute esta API para obtener el objeto MachineAction.</span><span class="sxs-lookup"><span data-stu-id="11c58-138">Run this API to get MachineAction object.</span></span>
<span data-ttu-id="11c58-139">Obtener colección MachineActions</span><span class="sxs-lookup"><span data-stu-id="11c58-139">Get MachineActions collection</span></span> | <span data-ttu-id="11c58-140">Ejecute esto para obtener la colección MachineAction.</span><span class="sxs-lookup"><span data-stu-id="11c58-140">Run this to get MachineAction collection.</span></span>
<span data-ttu-id="11c58-141">Obtener colección FileActions</span><span class="sxs-lookup"><span data-stu-id="11c58-141">Get FileActions collection</span></span> | <span data-ttu-id="11c58-142">Ejecute esta API para obtener la colección FileActions.</span><span class="sxs-lookup"><span data-stu-id="11c58-142">Run this API to get FileActions collection.</span></span>
<span data-ttu-id="11c58-143">Obtener objeto FileMachineAction</span><span class="sxs-lookup"><span data-stu-id="11c58-143">Get FileMachineAction object</span></span> | <span data-ttu-id="11c58-144">Ejecute esta API para obtener el objeto FileMachineAction.</span><span class="sxs-lookup"><span data-stu-id="11c58-144">Run this API to get FileMachineAction object.</span></span>
<span data-ttu-id="11c58-145">Obtener colección FileMachineActions</span><span class="sxs-lookup"><span data-stu-id="11c58-145">Get FileMachineActions collection</span></span> | <span data-ttu-id="11c58-146">Ejecute esta API para obtener la colección FileMachineAction.</span><span class="sxs-lookup"><span data-stu-id="11c58-146">Run this API to get FileMachineAction collection.</span></span>
