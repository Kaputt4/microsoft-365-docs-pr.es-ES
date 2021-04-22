---
title: Buscar dispositivos expuestos
description: Obtenga información sobre cómo se puede usar la administración de amenazas y vulnerabilidades para ayudar a los administradores de seguridad, los administradores de TI y SecOps a colaborar.
keywords: Escenarios de Microsoft Defender para Endpoint-tvm, Microsoft Defender para endpoint, tvm, escenarios de tvm, reducir la exposición & vulnerabilidad & amenazas, reducir la amenaza y vulnerabilidad, mejorar la configuración de seguridad, aumentar la puntuación segura de Microsoft para dispositivos, aumentar la vulnerabilidad & Microsoft Secure Score para dispositivos, Puntuación segura de Microsoft para dispositivos, puntuación de exposición, controles de seguridad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a9a8ebcc89c3009cd93fbb42f2a74bbb9ffcc31b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934098"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a><span data-ttu-id="75a30-104">Búsqueda de dispositivos expuestos: administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="75a30-104">Hunt for exposed devices - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="75a30-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="75a30-105">**Applies to:**</span></span>

- [<span data-ttu-id="75a30-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="75a30-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="75a30-107">Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="75a30-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="75a30-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75a30-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="75a30-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="75a30-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="75a30-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="75a30-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a><span data-ttu-id="75a30-111">Usar la búsqueda avanzada para buscar dispositivos con vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="75a30-111">Use advanced hunting to find devices with vulnerabilities</span></span>

<span data-ttu-id="75a30-112">La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consulta que le permite explorar hasta 30 días de datos sin procesar.</span><span class="sxs-lookup"><span data-stu-id="75a30-112">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="75a30-113">Puede inspeccionar de forma proactiva los eventos de la red para localizar indicadores y entidades de amenazas.</span><span class="sxs-lookup"><span data-stu-id="75a30-113">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="75a30-114">El acceso flexible a los datos permite la búsqueda sin restricciones para amenazas conocidas y potenciales.</span><span class="sxs-lookup"><span data-stu-id="75a30-114">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span> [<span data-ttu-id="75a30-115">Más información sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="75a30-115">Learn more about advanced hunting</span></span>](advanced-hunting-overview.md)

### <a name="schema-tables"></a><span data-ttu-id="75a30-116">Tablas del esquema</span><span class="sxs-lookup"><span data-stu-id="75a30-116">Schema tables</span></span>

- <span data-ttu-id="75a30-117">[DeviceTvmSoftwareInventory:](advanced-hunting-devicetvmsoftwareinventory-table.md) inventario de software instalado en dispositivos, incluida la información de su versión y el estado de finalización del soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="75a30-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - Inventory of software installed on devices, including their version information and end-of-support status.</span></span>

- <span data-ttu-id="75a30-118">[DeviceTvmSoftwareVulnerabilities:](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) vulnerabilidades de software encontradas en dispositivos y la lista de actualizaciones de seguridad disponibles que abordan cada vulnerabilidad.</span><span class="sxs-lookup"><span data-stu-id="75a30-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Software vulnerabilities found on devices and the list of available security updates that address each vulnerability.</span></span>

- <span data-ttu-id="75a30-119">[DeviceTvmSoftwareVulnerabilitiesKB:](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) base de conocimiento de las vulnerabilidades divulgadas públicamente, incluido si el código de vulnerabilidad está disponible públicamente.</span><span class="sxs-lookup"><span data-stu-id="75a30-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available.</span></span>

- <span data-ttu-id="75a30-120">[DeviceTvmSecureConfigurationAssessment:](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) eventos de evaluación de la administración de amenazas y vulnerabilidades, que indican el estado de varias configuraciones de seguridad en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="75a30-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - Threat and vulnerability management assessment events, indicating the status of various security configurations on devices.</span></span>

- <span data-ttu-id="75a30-121">[DeviceTvmSecureConfigurationAssessmentKB:](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) base de conocimientos de varias configuraciones de seguridad usadas por threat & Vulnerability Management para evaluar los dispositivos; incluye asignaciones a diversos estándares y puntos de referencia</span><span class="sxs-lookup"><span data-stu-id="75a30-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span>

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a><span data-ttu-id="75a30-122">Comprobar qué dispositivos están implicados en alertas de alta gravedad</span><span class="sxs-lookup"><span data-stu-id="75a30-122">Check which devices are involved in high severity alerts</span></span>

1. <span data-ttu-id="75a30-123">Ve a **Búsqueda avanzada desde** el panel de navegación izquierdo del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="75a30-123">Go to **Advanced hunting** from the left-hand navigation pane of the Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="75a30-124">Desplácese hacia abajo hasta los esquemas de búsqueda avanzados de TVM para familiarizarse con los nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="75a30-124">Scroll down to the TVM advanced hunting schemas to familiarize yourself with the column names.</span></span>

3. <span data-ttu-id="75a30-125">Escriba las siguientes consultas:</span><span class="sxs-lookup"><span data-stu-id="75a30-125">Enter the following queries:</span></span>

```kusto
// Search for devices with High active alerts or Critical CVE public exploit
DeviceTvmSoftwareVulnerabilities
| join kind=inner(DeviceTvmSoftwareVulnerabilitiesKB) on CveId
| where IsExploitAvailable == 1 and CvssScore >= 7
| summarize NumOfVulnerabilities=dcount(CveId),
DeviceName=any(DeviceName) by DeviceId
| join kind =inner(DeviceAlertEvents) on DeviceId  
| summarize NumOfVulnerabilities=any(NumOfVulnerabilities),
DeviceName=any(DeviceName) by DeviceId, AlertId
| project DeviceName, NumOfVulnerabilities, AlertId  
| order by NumOfVulnerabilities desc
```

## <a name="related-topics"></a><span data-ttu-id="75a30-126">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="75a30-126">Related topics</span></span>

- [<span data-ttu-id="75a30-127">Introducción a la administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="75a30-127">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="75a30-128">Recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="75a30-128">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="75a30-129">API</span><span class="sxs-lookup"><span data-stu-id="75a30-129">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)
- [<span data-ttu-id="75a30-130">Configurar el acceso a datos para roles de administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="75a30-130">Configure data access for threat and vulnerability management roles</span></span>](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [<span data-ttu-id="75a30-131">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="75a30-131">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [<span data-ttu-id="75a30-132">Todas las tablas de búsqueda avanzadas</span><span class="sxs-lookup"><span data-stu-id="75a30-132">All advanced hunting tables</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
