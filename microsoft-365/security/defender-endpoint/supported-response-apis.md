---
title: API de respuesta de Protección contra amenazas avanzada admitidas de Microsoft Defender
description: Obtenga información sobre las llamadas de la API de protección contra amenazas avanzada de Microsoft Defender relacionadas con la respuesta específica.
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
ms.openlocfilehash: a290c431f6d81b23896ddf77e7c7a47de378de22
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185556"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a><span data-ttu-id="f25e8-104">Api de consulta de extremo admitidas de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f25e8-104">Supported Microsoft Defender for Endpoint query APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f25e8-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f25e8-105">**Applies to:**</span></span>
- [<span data-ttu-id="f25e8-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f25e8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> <span data-ttu-id="f25e8-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="f25e8-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f25e8-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="f25e8-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

<span data-ttu-id="f25e8-109">Obtenga información sobre las llamadas API relacionadas con la respuesta admitidas que puede ejecutar y detalles como los encabezados de solicitud necesarios y la respuesta esperada de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="f25e8-109">Learn about the supported response-related API calls you can run and details such as the required request headers, and expected response from the calls.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f25e8-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f25e8-110">In this section</span></span>
<span data-ttu-id="f25e8-111">Tema</span><span class="sxs-lookup"><span data-stu-id="f25e8-111">Topic</span></span> | <span data-ttu-id="f25e8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f25e8-112">Description</span></span>
:---|:---
<span data-ttu-id="f25e8-113">Recopilar paquete de investigación</span><span class="sxs-lookup"><span data-stu-id="f25e8-113">Collect investigation package</span></span> | <span data-ttu-id="f25e8-114">Ejecute esta API para recopilar un paquete de investigación desde un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f25e8-114">Run this API to collect an investigation package from a device.</span></span>
<span data-ttu-id="f25e8-115">Aislar dispositivo</span><span class="sxs-lookup"><span data-stu-id="f25e8-115">Isolate device</span></span> | <span data-ttu-id="f25e8-116">Ejecute esta API para aislar un dispositivo de la red.</span><span class="sxs-lookup"><span data-stu-id="f25e8-116">Run this API to isolate a device from the network.</span></span>
<span data-ttu-id="f25e8-117">Unisolate device</span><span class="sxs-lookup"><span data-stu-id="f25e8-117">Unisolate device</span></span> | <span data-ttu-id="f25e8-118">Quita un dispositivo del aislamiento.</span><span class="sxs-lookup"><span data-stu-id="f25e8-118">Remove a device from isolation.</span></span> 
<span data-ttu-id="f25e8-119">Restringir la ejecución de código</span><span class="sxs-lookup"><span data-stu-id="f25e8-119">Restrict code execution</span></span> | <span data-ttu-id="f25e8-120">Ejecute esta API para contener un ataque deteniendo procesos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="f25e8-120">Run this API to contain an attack by stopping malicious processes.</span></span> <span data-ttu-id="f25e8-121">También puedes bloquear un dispositivo e impedir que se ejecuten los intentos posteriores de programas potencialmente malintencionados.</span><span class="sxs-lookup"><span data-stu-id="f25e8-121">You can also lock down a device and prevent subsequent attempts of potentially malicious programs from running.</span></span>
<span data-ttu-id="f25e8-122">Ejecución de código sin restricto</span><span class="sxs-lookup"><span data-stu-id="f25e8-122">Unrestrict code execution</span></span> | <span data-ttu-id="f25e8-123">Ejecute esto para revertir la restricción de la directiva de aplicaciones después de comprobar que el dispositivo en peligro se ha corregido.</span><span class="sxs-lookup"><span data-stu-id="f25e8-123">Run this to reverse the restriction of applications policy after you have verified that the compromised device has been remediated.</span></span>
<span data-ttu-id="f25e8-124">Ejecutar examen antivirus</span><span class="sxs-lookup"><span data-stu-id="f25e8-124">Run antivirus scan</span></span> | <span data-ttu-id="f25e8-125">Inicie de forma remota un examen antivirus para ayudar a identificar y corregir malware que podría estar presente en un dispositivo en peligro.</span><span class="sxs-lookup"><span data-stu-id="f25e8-125">Remotely initiate an antivirus scan to help identify and remediate malware that might be present on a compromised device.</span></span>
<span data-ttu-id="f25e8-126">Detener y poner en cuarentena el archivo</span><span class="sxs-lookup"><span data-stu-id="f25e8-126">Stop and quarantine file</span></span> |  <span data-ttu-id="f25e8-127">Ejecute esta llamada para detener la ejecución de procesos, poner en cuarentena archivos y eliminar la persistencia, como las claves del Registro.</span><span class="sxs-lookup"><span data-stu-id="f25e8-127">Run this call to stop running processes, quarantine  files, and delete persistency such as registry keys.</span></span>
<span data-ttu-id="f25e8-128">Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="f25e8-128">Request sample</span></span> | <span data-ttu-id="f25e8-129">Ejecute esta llamada para solicitar una muestra de un archivo desde un dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="f25e8-129">Run this call to request a sample of a file from a specific device.</span></span> <span data-ttu-id="f25e8-130">El archivo se recopilará desde el dispositivo y se cargará en un almacenamiento seguro.</span><span class="sxs-lookup"><span data-stu-id="f25e8-130">The file will be collected from the device and uploaded to a secure storage.</span></span>
<span data-ttu-id="f25e8-131">Bloquear archivo</span><span class="sxs-lookup"><span data-stu-id="f25e8-131">Block file</span></span> | <span data-ttu-id="f25e8-132">Ejecute esta API para evitar la propagación posterior de un ataque en su organización mediante la prohibición de archivos potencialmente malintencionados o malware sospechoso.</span><span class="sxs-lookup"><span data-stu-id="f25e8-132">Run this API to prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 
<span data-ttu-id="f25e8-133">Desbloquear archivo</span><span class="sxs-lookup"><span data-stu-id="f25e8-133">Unblock file</span></span> | <span data-ttu-id="f25e8-134">Permitir que un archivo se ejecute en la organización con Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="f25e8-134">Allow a file run in the organization using Microsoft Defender Antivirus.</span></span>
<span data-ttu-id="f25e8-135">Obtener EL URI de SAS del paquete</span><span class="sxs-lookup"><span data-stu-id="f25e8-135">Get package SAS URI</span></span> | <span data-ttu-id="f25e8-136">Ejecute esta API para obtener un URI que permita descargar un paquete de investigación.</span><span class="sxs-lookup"><span data-stu-id="f25e8-136">Run this API to get a URI that allows downloading an investigation package.</span></span>
<span data-ttu-id="f25e8-137">Obtener objeto MachineAction</span><span class="sxs-lookup"><span data-stu-id="f25e8-137">Get MachineAction object</span></span> | <span data-ttu-id="f25e8-138">Ejecute esta API para obtener el objeto MachineAction.</span><span class="sxs-lookup"><span data-stu-id="f25e8-138">Run this API to get MachineAction object.</span></span>
<span data-ttu-id="f25e8-139">Obtener colección MachineActions</span><span class="sxs-lookup"><span data-stu-id="f25e8-139">Get MachineActions collection</span></span> | <span data-ttu-id="f25e8-140">Ejecute esto para obtener la colección MachineAction.</span><span class="sxs-lookup"><span data-stu-id="f25e8-140">Run this to get MachineAction collection.</span></span>
<span data-ttu-id="f25e8-141">Obtener colección FileActions</span><span class="sxs-lookup"><span data-stu-id="f25e8-141">Get FileActions collection</span></span> | <span data-ttu-id="f25e8-142">Ejecute esta API para obtener la colección FileActions.</span><span class="sxs-lookup"><span data-stu-id="f25e8-142">Run this API to get FileActions collection.</span></span>
<span data-ttu-id="f25e8-143">Obtener objeto FileMachineAction</span><span class="sxs-lookup"><span data-stu-id="f25e8-143">Get FileMachineAction object</span></span> | <span data-ttu-id="f25e8-144">Ejecute esta API para obtener el objeto FileMachineAction.</span><span class="sxs-lookup"><span data-stu-id="f25e8-144">Run this API to get FileMachineAction object.</span></span>
<span data-ttu-id="f25e8-145">Obtener colección FileMachineActions</span><span class="sxs-lookup"><span data-stu-id="f25e8-145">Get FileMachineActions collection</span></span> | <span data-ttu-id="f25e8-146">Ejecute esta API para obtener la colección FileMachineAction.</span><span class="sxs-lookup"><span data-stu-id="f25e8-146">Run this API to get FileMachineAction collection.</span></span>
