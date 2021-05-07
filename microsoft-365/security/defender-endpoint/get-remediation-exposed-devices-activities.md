---
title: Lista de dispositivos expuestos de una actividad de corrección
description: Devuelve información sobre los dispositivos expuestos para la tarea de corrección especificada.
keywords: apis, remediation, remediation api, get, remediation tasks, remediation exposed devices
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 92b5a93e86a20f36469d2b5cb606a8ddc2e97077
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241717"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a><span data-ttu-id="bedfb-104">Lista de dispositivos expuestos de una actividad de corrección</span><span class="sxs-lookup"><span data-stu-id="bedfb-104">List exposed devices of one remediation activity</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bedfb-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="bedfb-105">**Applies to:**</span></span>

- [<span data-ttu-id="bedfb-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="bedfb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bedfb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bedfb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bedfb-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="bedfb-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bedfb-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="bedfb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="bedfb-110">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="bedfb-110">API Description</span></span>

<span data-ttu-id="bedfb-111">Devuelve información sobre los dispositivos expuestos para la tarea de corrección especificada.</span><span class="sxs-lookup"><span data-stu-id="bedfb-111">Returns information about exposed devices for the specified remediation task.</span></span>

<span data-ttu-id="bedfb-112">[Obtenga más información sobre las actividades de corrección](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="bedfb-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a><span data-ttu-id="bedfb-113">Enumerar los dispositivos expuestos asociados con una tarea de corrección (id)</span><span class="sxs-lookup"><span data-stu-id="bedfb-113">List exposed devices associated with a remediation task (id)</span></span>

<span data-ttu-id="bedfb-114">**DIRECCIÓN URL:** GET: /api/remediationTasks/ \{ id \} /machineReferences</span><span class="sxs-lookup"><span data-stu-id="bedfb-114">**URL:** GET: /api/remediationTasks/\{id\}/machineReferences</span></span>

## <a name="permissions"></a><span data-ttu-id="bedfb-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="bedfb-115">Permissions</span></span>

<span data-ttu-id="bedfb-116">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="bedfb-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bedfb-117">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="bedfb-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="bedfb-118">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="bedfb-118">Permission type</span></span> | <span data-ttu-id="bedfb-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="bedfb-119">Permission</span></span> | <span data-ttu-id="bedfb-120">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="bedfb-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="bedfb-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="bedfb-121">Application</span></span> | <span data-ttu-id="bedfb-122">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="bedfb-122">RemediationTask.Read.All</span></span> | <span data-ttu-id="bedfb-123">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="bedfb-123">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="bedfb-124">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="bedfb-124">Delegated (work or school account)</span></span> | <span data-ttu-id="bedfb-125">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="bedfb-125">RemediationTask.Read.Read</span></span> | <span data-ttu-id="bedfb-126">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="bedfb-126">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties-details"></a><span data-ttu-id="bedfb-127">Detalles de propiedades</span><span class="sxs-lookup"><span data-stu-id="bedfb-127">Properties details</span></span>

<span data-ttu-id="bedfb-128">Propiedad (id)</span><span class="sxs-lookup"><span data-stu-id="bedfb-128">Property (id)</span></span> | <span data-ttu-id="bedfb-129">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="bedfb-129">Data type</span></span> | <span data-ttu-id="bedfb-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="bedfb-130">Description</span></span> | <span data-ttu-id="bedfb-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bedfb-131">Example</span></span>
:---|:---|:---|:---
<span data-ttu-id="bedfb-132">id</span><span class="sxs-lookup"><span data-stu-id="bedfb-132">id</span></span> | <span data-ttu-id="bedfb-133">Cadena</span><span class="sxs-lookup"><span data-stu-id="bedfb-133">String</span></span> | <span data-ttu-id="bedfb-134">Id. de dispositivo</span><span class="sxs-lookup"><span data-stu-id="bedfb-134">Device ID</span></span> | <span data-ttu-id="bedfb-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span><span class="sxs-lookup"><span data-stu-id="bedfb-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span></span>
<span data-ttu-id="bedfb-136">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="bedfb-136">computerDnsName</span></span> | <span data-ttu-id="bedfb-137">Cadena</span><span class="sxs-lookup"><span data-stu-id="bedfb-137">String</span></span> | <span data-ttu-id="bedfb-138">Nombre del dispositivo</span><span class="sxs-lookup"><span data-stu-id="bedfb-138">Device name</span></span> | <span data-ttu-id="bedfb-139">PC-SRV2012R2Foo.UserNameVldNet.local</span><span class="sxs-lookup"><span data-stu-id="bedfb-139">PC-SRV2012R2Foo.UserNameVldNet.local</span></span>
<span data-ttu-id="bedfb-140">osPlatform</span><span class="sxs-lookup"><span data-stu-id="bedfb-140">osPlatform</span></span> | <span data-ttu-id="bedfb-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="bedfb-141">String</span></span> | <span data-ttu-id="bedfb-142">Sistema operativo del dispositivo</span><span class="sxs-lookup"><span data-stu-id="bedfb-142">Device operating system</span></span> | <span data-ttu-id="bedfb-143">WindowsServer2012R2</span><span class="sxs-lookup"><span data-stu-id="bedfb-143">WindowsServer2012R2</span></span>
<span data-ttu-id="bedfb-144">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="bedfb-144">rbacGroupName</span></span> | <span data-ttu-id="bedfb-145">Cadena</span><span class="sxs-lookup"><span data-stu-id="bedfb-145">String</span></span> | <span data-ttu-id="bedfb-146">Nombre del grupo de dispositivos al que está asociado este dispositivo</span><span class="sxs-lookup"><span data-stu-id="bedfb-146">Name of the device group this device is associated with</span></span> | <span data-ttu-id="bedfb-147">Servidores</span><span class="sxs-lookup"><span data-stu-id="bedfb-147">Servers</span></span>

## <a name="example"></a><span data-ttu-id="bedfb-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bedfb-148">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="bedfb-149">Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="bedfb-149">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

### <a name="response-example"></a><span data-ttu-id="bedfb-150">Ejemplo de respuesta</span><span class="sxs-lookup"><span data-stu-id="bedfb-150">Response example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "3cb5df6bb3640a2d37ad09fcd357b182d684fafc",
            "computerDnsName": "ComputerPII_2ea21b2d97c9df23c143ad9e3e454cb674232529.DomainPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3d9b1ca53e8f077199c7dcbfc9dbfa78f9bf1918",
            "computerDnsName": "ComputerPII_001d606fc149567c192747f48fae304b43c0ddba.DomainxPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3db8b27e6172951d7ea2e2d75945abec56feaf82",
            "computerDnsName": "ComputerPII_ce60cfbjj4b82a091deb5eae560332bba99a9bd7.DomainPII_0bc1aee0fa396d175e514bd61a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3bad326dcda5b53fab47408cd4a7080f3f3cc8ab",
            "computerDnsName": "ComputerPII_b6b35960dd6539d1d1cef5ada02e235e7b357408.DomainPII_21eed80b089e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        }
]
}
```

## <a name="see-also"></a><span data-ttu-id="bedfb-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="bedfb-151">See also</span></span>

- [<span data-ttu-id="bedfb-152">Propiedades y métodos de corrección</span><span class="sxs-lookup"><span data-stu-id="bedfb-152">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="bedfb-153">Obtener una actividad de corrección por id.</span><span class="sxs-lookup"><span data-stu-id="bedfb-153">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="bedfb-154">Enumerar todas las actividades de corrección</span><span class="sxs-lookup"><span data-stu-id="bedfb-154">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="bedfb-155">Amenazas basadas en riesgos & administración de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="bedfb-155">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="bedfb-156">Vulnerabilidades de la organización</span><span class="sxs-lookup"><span data-stu-id="bedfb-156">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
