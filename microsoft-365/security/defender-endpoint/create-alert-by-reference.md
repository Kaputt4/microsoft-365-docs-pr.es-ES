---
title: Crear alerta desde la API de eventos
description: Obtén información sobre cómo usar la API crear alertas para crear una nueva alerta encima del evento en Microsoft Defender para endpoint.
keywords: apis, api de gráficos, api admitidas, get, alert, information, id
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
ms.openlocfilehash: 9066bcdae549f7a6b1372714d567674eb03c1e51
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167072"
---
# <a name="create-alert-api"></a><span data-ttu-id="55bc5-104">Crear API de alertas</span><span class="sxs-lookup"><span data-stu-id="55bc5-104">Create alert API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="55bc5-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="55bc5-105">**Applies to:**</span></span>
- [<span data-ttu-id="55bc5-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="55bc5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="55bc5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55bc5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="55bc5-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="55bc5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="55bc5-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="55bc5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="55bc5-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="55bc5-110">API description</span></span>
<span data-ttu-id="55bc5-111">Crea una [nueva alerta](alerts.md) en la parte superior del **evento**.</span><span class="sxs-lookup"><span data-stu-id="55bc5-111">Creates new [Alert](alerts.md) on top of **Event**.</span></span>
<br><span data-ttu-id="55bc5-112">**Se requiere Microsoft Defender para el evento endpoint** para la creación de alertas.</span><span class="sxs-lookup"><span data-stu-id="55bc5-112">**Microsoft Defender for Endpoint Event** is required for the alert creation.</span></span>
<br><span data-ttu-id="55bc5-113">Deberá proporcionar 3 parámetros del evento en la solicitud: **Hora del** evento , **Id. de** máquina e **Id. de informe.**</span><span class="sxs-lookup"><span data-stu-id="55bc5-113">You will need to supply 3 parameters from the Event in the request: **Event Time**, **Machine ID** and **Report ID**.</span></span> <span data-ttu-id="55bc5-114">Vea el ejemplo abajo.</span><span class="sxs-lookup"><span data-stu-id="55bc5-114">See example below.</span></span>
<br><span data-ttu-id="55bc5-115">Puedes usar un evento que se encuentra en la API de búsqueda avanzada o portal.</span><span class="sxs-lookup"><span data-stu-id="55bc5-115">You can use an event found in Advanced Hunting API or Portal.</span></span>
<br><span data-ttu-id="55bc5-116">Si existe una alerta abierta en el mismo dispositivo con el mismo título, la nueva alerta creada se combinará con ella.</span><span class="sxs-lookup"><span data-stu-id="55bc5-116">If there existing an open alert on the same Device with the same Title, the new created alert will be merged with it.</span></span>
<br><span data-ttu-id="55bc5-117">Una investigación automática se inicia automáticamente en alertas creadas a través de la API.</span><span class="sxs-lookup"><span data-stu-id="55bc5-117">An automatic investigation starts automatically on alerts created via the API.</span></span>


## <a name="limitations"></a><span data-ttu-id="55bc5-118">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="55bc5-118">Limitations</span></span>
1. <span data-ttu-id="55bc5-119">Las limitaciones de velocidad para esta API son 15 llamadas por minuto.</span><span class="sxs-lookup"><span data-stu-id="55bc5-119">Rate limitations for this API are 15 calls per minute.</span></span>


## <a name="permissions"></a><span data-ttu-id="55bc5-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="55bc5-120">Permissions</span></span>

<span data-ttu-id="55bc5-121">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="55bc5-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="55bc5-122">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="55bc5-122">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="55bc5-123">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="55bc5-123">Permission type</span></span> |   <span data-ttu-id="55bc5-124">Permiso</span><span class="sxs-lookup"><span data-stu-id="55bc5-124">Permission</span></span>  |   <span data-ttu-id="55bc5-125">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="55bc5-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="55bc5-126">Aplicación</span><span class="sxs-lookup"><span data-stu-id="55bc5-126">Application</span></span> |   <span data-ttu-id="55bc5-127">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="55bc5-127">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="55bc5-128">'Leer y escribir todas las alertas'</span><span class="sxs-lookup"><span data-stu-id="55bc5-128">'Read and write all alerts'</span></span>
<span data-ttu-id="55bc5-129">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="55bc5-129">Delegated (work or school account)</span></span> | <span data-ttu-id="55bc5-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="55bc5-130">Alert.ReadWrite</span></span> | <span data-ttu-id="55bc5-131">'Leer y escribir alertas'</span><span class="sxs-lookup"><span data-stu-id="55bc5-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="55bc5-132">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="55bc5-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="55bc5-133">El usuario debe tener al menos el siguiente permiso de función: "Investigación de alertas" (vea [Crear y](user-roles.md) administrar roles para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="55bc5-133">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="55bc5-134">El usuario debe tener acceso al dispositivo asociado a la alerta, según la configuración del grupo de dispositivos (consulta [Crear](machine-groups.md) y administrar grupos de dispositivos para obtener más información)</span><span class="sxs-lookup"><span data-stu-id="55bc5-134">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="55bc5-135">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="55bc5-135">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a><span data-ttu-id="55bc5-136">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="55bc5-136">Request headers</span></span>

<span data-ttu-id="55bc5-137">Nombre</span><span class="sxs-lookup"><span data-stu-id="55bc5-137">Name</span></span> | <span data-ttu-id="55bc5-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="55bc5-138">Type</span></span> | <span data-ttu-id="55bc5-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="55bc5-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="55bc5-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="55bc5-140">Authorization</span></span> | <span data-ttu-id="55bc5-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="55bc5-141">String</span></span> | <span data-ttu-id="55bc5-142">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="55bc5-142">Bearer {token}.</span></span> <span data-ttu-id="55bc5-143">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="55bc5-143">**Required**.</span></span>
<span data-ttu-id="55bc5-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="55bc5-144">Content-Type</span></span> | <span data-ttu-id="55bc5-145">Cadena</span><span class="sxs-lookup"><span data-stu-id="55bc5-145">String</span></span> | <span data-ttu-id="55bc5-146">application/json.</span><span class="sxs-lookup"><span data-stu-id="55bc5-146">application/json.</span></span> <span data-ttu-id="55bc5-147">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="55bc5-147">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="55bc5-148">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="55bc5-148">Request body</span></span>

<span data-ttu-id="55bc5-149">En el cuerpo de la solicitud, proporcione los siguientes valores (todos son necesarios):</span><span class="sxs-lookup"><span data-stu-id="55bc5-149">In the request body, supply the following values (all are required):</span></span>

<span data-ttu-id="55bc5-150">Propiedad</span><span class="sxs-lookup"><span data-stu-id="55bc5-150">Property</span></span> | <span data-ttu-id="55bc5-151">Tipo</span><span class="sxs-lookup"><span data-stu-id="55bc5-151">Type</span></span> | <span data-ttu-id="55bc5-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="55bc5-152">Description</span></span>
:---|:---|:---
<span data-ttu-id="55bc5-153">eventTime</span><span class="sxs-lookup"><span data-stu-id="55bc5-153">eventTime</span></span> | <span data-ttu-id="55bc5-154">DateTime(UTC)</span><span class="sxs-lookup"><span data-stu-id="55bc5-154">DateTime(UTC)</span></span> | <span data-ttu-id="55bc5-155">La hora precisa del evento como cadena, como se obtiene de la búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="55bc5-155">The precise time of the event as string, as obtained from advanced hunting.</span></span> <span data-ttu-id="55bc5-156">Por ejemplo, Obligatorio ```2018-08-03T16:45:21.7115183Z``` .</span><span class="sxs-lookup"><span data-stu-id="55bc5-156">e.g. ```2018-08-03T16:45:21.7115183Z``` **Required**.</span></span>
<span data-ttu-id="55bc5-157">reportId</span><span class="sxs-lookup"><span data-stu-id="55bc5-157">reportId</span></span> | <span data-ttu-id="55bc5-158">Cadena</span><span class="sxs-lookup"><span data-stu-id="55bc5-158">String</span></span> | <span data-ttu-id="55bc5-159">El reportId del evento, como se obtiene de la búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="55bc5-159">The reportId of the event, as obtained from advanced hunting.</span></span> <span data-ttu-id="55bc5-160">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="55bc5-160">**Required**.</span></span>
<span data-ttu-id="55bc5-161">machineId</span><span class="sxs-lookup"><span data-stu-id="55bc5-161">machineId</span></span> | <span data-ttu-id="55bc5-162">Cadena</span><span class="sxs-lookup"><span data-stu-id="55bc5-162">String</span></span> | <span data-ttu-id="55bc5-163">Id. del dispositivo en el que se identificó el evento.</span><span class="sxs-lookup"><span data-stu-id="55bc5-163">Id of the device on which the event was identified.</span></span> <span data-ttu-id="55bc5-164">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="55bc5-164">**Required**.</span></span>
<span data-ttu-id="55bc5-165">severity</span><span class="sxs-lookup"><span data-stu-id="55bc5-165">severity</span></span> | <span data-ttu-id="55bc5-166">Cadena</span><span class="sxs-lookup"><span data-stu-id="55bc5-166">String</span></span> | <span data-ttu-id="55bc5-167">Gravedad de la alerta.</span><span class="sxs-lookup"><span data-stu-id="55bc5-167">Severity of the alert.</span></span> <span data-ttu-id="55bc5-168">Los valores de propiedad son: 'Low', 'Medium' y 'High'.</span><span class="sxs-lookup"><span data-stu-id="55bc5-168">The property values are: 'Low', 'Medium' and 'High'.</span></span> <span data-ttu-id="55bc5-169">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="55bc5-169">**Required**.</span></span>
<span data-ttu-id="55bc5-170">title</span><span class="sxs-lookup"><span data-stu-id="55bc5-170">title</span></span> | <span data-ttu-id="55bc5-171">Cadena</span><span class="sxs-lookup"><span data-stu-id="55bc5-171">String</span></span> | <span data-ttu-id="55bc5-172">Título de la alerta.</span><span class="sxs-lookup"><span data-stu-id="55bc5-172">Title for the alert.</span></span> <span data-ttu-id="55bc5-173">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="55bc5-173">**Required**.</span></span>
<span data-ttu-id="55bc5-174">description</span><span class="sxs-lookup"><span data-stu-id="55bc5-174">description</span></span> | <span data-ttu-id="55bc5-175">Cadena</span><span class="sxs-lookup"><span data-stu-id="55bc5-175">String</span></span> | <span data-ttu-id="55bc5-176">Descripción de la alerta.</span><span class="sxs-lookup"><span data-stu-id="55bc5-176">Description of the alert.</span></span> <span data-ttu-id="55bc5-177">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="55bc5-177">**Required**.</span></span>
<span data-ttu-id="55bc5-178">recommendedAction</span><span class="sxs-lookup"><span data-stu-id="55bc5-178">recommendedAction</span></span>| <span data-ttu-id="55bc5-179">Cadena</span><span class="sxs-lookup"><span data-stu-id="55bc5-179">String</span></span> | <span data-ttu-id="55bc5-180">Acción recomendada por el responsable de seguridad al analizar la alerta.</span><span class="sxs-lookup"><span data-stu-id="55bc5-180">Action that is recommended to be taken by security officer when analyzing the alert.</span></span> <span data-ttu-id="55bc5-181">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="55bc5-181">**Required**.</span></span>
<span data-ttu-id="55bc5-182">categoría</span><span class="sxs-lookup"><span data-stu-id="55bc5-182">category</span></span>| <span data-ttu-id="55bc5-183">Cadena</span><span class="sxs-lookup"><span data-stu-id="55bc5-183">String</span></span> | <span data-ttu-id="55bc5-184">Categoría de la alerta.</span><span class="sxs-lookup"><span data-stu-id="55bc5-184">Category of the alert.</span></span> <span data-ttu-id="55bc5-185">Los valores de propiedad son: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span><span class="sxs-lookup"><span data-stu-id="55bc5-185">The property values are: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span></span>

## <a name="response"></a><span data-ttu-id="55bc5-186">Respuesta</span><span class="sxs-lookup"><span data-stu-id="55bc5-186">Response</span></span>

<span data-ttu-id="55bc5-187">Si se realiza correctamente, este método devuelve 200 Ok y un nuevo [objeto alert](alerts.md) en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="55bc5-187">If successful, this method returns 200 OK, and a new [alert](alerts.md) object in the response body.</span></span> <span data-ttu-id="55bc5-188">If event with the specified properties (_reportId_, _eventTime_ and _machineId_) was not found - 404 Not Found.</span><span class="sxs-lookup"><span data-stu-id="55bc5-188">If event with the specified properties (_reportId_, _eventTime_ and _machineId_) was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="55bc5-189">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="55bc5-189">Example</span></span>

<span data-ttu-id="55bc5-190">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="55bc5-190">**Request**</span></span>

<span data-ttu-id="55bc5-191">Aquí tiene un ejemplo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="55bc5-191">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
