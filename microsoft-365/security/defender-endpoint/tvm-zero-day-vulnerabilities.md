---
title: 'Mitigar vulnerabilidades de día cero: Administración de amenazas y vulnerabilidades'
description: Obtenga información sobre cómo buscar y mitigar vulnerabilidades de día cero en su entorno a través de Administración de amenazas y vulnerabilidades.
keywords: Vulnerabilidades de día cero de Microsoft Defender para Endpoint tvm, tvm, threat & administración de vulnerabilidades, zero day, 0-day, mitigate 0 day vulnerabilities, vulnerable CVE
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
ms.openlocfilehash: 2c746a74899a34827e089f4c9c2f6ecc396bb69c
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538776"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a><span data-ttu-id="f0f73-104">Mitigar vulnerabilidades de día cero: Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="f0f73-104">Mitigate zero-day vulnerabilities - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f0f73-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f0f73-105">**Applies to:**</span></span>

- [<span data-ttu-id="f0f73-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f0f73-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="f0f73-107">Amenaza y administración de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="f0f73-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="f0f73-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f0f73-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f0f73-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="f0f73-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f0f73-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="f0f73-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="f0f73-111">Una vulnerabilidad de día cero es una vulnerabilidad divulgada públicamente para la que no se han publicado revisiones oficiales ni actualizaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f0f73-111">A zero-day vulnerability is a publicly disclosed vulnerability for which no official patches or security updates have been released.</span></span> <span data-ttu-id="f0f73-112">Las vulnerabilidades de día cero suelen tener niveles de gravedad altos y se aprovechan activamente.</span><span class="sxs-lookup"><span data-stu-id="f0f73-112">Zero-day vulnerabilities often have high severity levels and are actively exploited.</span></span>

<span data-ttu-id="f0f73-113">Las amenazas administración de vulnerabilidades solo mostrarán vulnerabilidades de día cero de las que tenga información.</span><span class="sxs-lookup"><span data-stu-id="f0f73-113">Threat and vulnerability management will only display zero-day vulnerabilities it has information about.</span></span>

## <a name="find-information-about-zero-day-vulnerabilities"></a><span data-ttu-id="f0f73-114">Buscar información sobre vulnerabilidades de día cero</span><span class="sxs-lookup"><span data-stu-id="f0f73-114">Find information about zero-day vulnerabilities</span></span>

<span data-ttu-id="f0f73-115">Una vez que se haya encontrado una vulnerabilidad de día cero, la información sobre ella se transmitirá a través de las siguientes experiencias en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="f0f73-115">Once a zero-day vulnerability has been found, information about it will be conveyed through the following experiences in the Microsoft Defender Security Center.</span></span>

>[!NOTE]
> <span data-ttu-id="f0f73-116">La funcionalidad de 0 días no está disponible actualmente para productos que no Windows (Mac, Linux); sin embargo, se agregará en el futuro.</span><span class="sxs-lookup"><span data-stu-id="f0f73-116">0-day capability is not currently available for non-Windows products (Mac, Linux); it will, however, be added in the future.</span></span>

### <a name="threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="f0f73-117">Panel de administración de vulnerabilidades amenazas</span><span class="sxs-lookup"><span data-stu-id="f0f73-117">Threat and vulnerability management dashboard</span></span>

<span data-ttu-id="f0f73-118">Busque recomendaciones con una etiqueta de día cero en la tarjeta "Recomendaciones de seguridad principales".</span><span class="sxs-lookup"><span data-stu-id="f0f73-118">Look for recommendations with a zero-day tag in the “Top security recommendations” card.</span></span>

![Recomendaciones principales con una etiqueta de día cero.](images/tvm-zero-day-top-security-recommendations.png)

<span data-ttu-id="f0f73-120">Busca el software superior con la etiqueta de día cero en la tarjeta "Software vulnerable superior".</span><span class="sxs-lookup"><span data-stu-id="f0f73-120">Find top software with the zero-day tag in the "Top vulnerable software" card.</span></span>

![Software vulnerable superior con una etiqueta de día cero.](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a><span data-ttu-id="f0f73-122">Página Puntos débiles</span><span class="sxs-lookup"><span data-stu-id="f0f73-122">Weaknesses page</span></span>

<span data-ttu-id="f0f73-123">Busque la vulnerabilidad de día cero con nombre junto con una descripción y detalles.</span><span class="sxs-lookup"><span data-stu-id="f0f73-123">Look for the named zero-day vulnerability along with a description and details.</span></span>

- <span data-ttu-id="f0f73-124">Si esta vulnerabilidad tiene asignado un identificador CVE, verás la etiqueta de día cero junto al nombre CVE.</span><span class="sxs-lookup"><span data-stu-id="f0f73-124">If this vulnerability has a CVE-ID assigned, you’ll see the zero-day label next to the CVE name.</span></span>

- <span data-ttu-id="f0f73-125">Si esta vulnerabilidad no tiene ningún identificador CVE asignado, lo encontrarás con un nombre interno y temporal que tenga el aspecto de "TVM-XXXX-XXXX".</span><span class="sxs-lookup"><span data-stu-id="f0f73-125">If this vulnerability has no CVE-ID assigned, you'll find it under an internal, temporary name that looks like “TVM-XXXX-XXXX”.</span></span> <span data-ttu-id="f0f73-126">El nombre se actualizará una vez que se haya asignado un identificador CVE oficial, pero el nombre interno anterior aún se podrá buscar y se encontrará en el panel lateral.</span><span class="sxs-lookup"><span data-stu-id="f0f73-126">The name will be updated once an official CVE-ID has been assigned, but the previous internal name will still be searchable and found in the side-panel.</span></span>

![Ejemplo de día cero para CVE-2020-17087 en la página de puntos débiles.](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a><span data-ttu-id="f0f73-128">Página de inventario de software</span><span class="sxs-lookup"><span data-stu-id="f0f73-128">Software inventory page</span></span>

<span data-ttu-id="f0f73-129">Busque software con la etiqueta de día cero.</span><span class="sxs-lookup"><span data-stu-id="f0f73-129">Look for software with the zero-day tag.</span></span> <span data-ttu-id="f0f73-130">Filtra por la etiqueta "día cero" para ver solo el software con vulnerabilidades de día cero.</span><span class="sxs-lookup"><span data-stu-id="f0f73-130">Filter by the "zero day" tag to only see software with zero-day vulnerabilities.</span></span>

![Ejemplo de día cero Windows Server 2016 en la página de inventario de software.](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a><span data-ttu-id="f0f73-132">Página de software</span><span class="sxs-lookup"><span data-stu-id="f0f73-132">Software page</span></span>

<span data-ttu-id="f0f73-133">Busque una etiqueta de día cero para cada software afectado por la vulnerabilidad de día cero.</span><span class="sxs-lookup"><span data-stu-id="f0f73-133">Look for a zero-day tag for each software that has been affected by the zero–day vulnerability.</span></span>

![Ejemplo de día cero para Windows Server 2016 de software.](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a><span data-ttu-id="f0f73-135">Página recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="f0f73-135">Security recommendations page</span></span>

<span data-ttu-id="f0f73-136">Vea sugerencias claras sobre las opciones de corrección y mitigación, incluidas las soluciones alternativas si existen.</span><span class="sxs-lookup"><span data-stu-id="f0f73-136">View clear suggestions about remediation and mitigation options, including workarounds if they exist.</span></span> <span data-ttu-id="f0f73-137">Filtre por la etiqueta "día cero" para ver solo las recomendaciones de seguridad que abordan las vulnerabilidades de día cero.</span><span class="sxs-lookup"><span data-stu-id="f0f73-137">Filter by the "zero day" tag to only see security recommendations addressing zero-day vulnerabilities.</span></span>

<span data-ttu-id="f0f73-138">Si hay software con una vulnerabilidad de día cero y vulnerabilidades adicionales que solucionar, tendrás una recomendación sobre todas las vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="f0f73-138">If there's software with a zero-day vulnerability and additional vulnerabilities to address, you'll get one recommendation about all vulnerabilities.</span></span>

![Ejemplo de día cero Windows Server 2016 en la página de recomendaciones de seguridad.](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a><span data-ttu-id="f0f73-140">Abordar vulnerabilidades de día cero</span><span class="sxs-lookup"><span data-stu-id="f0f73-140">Addressing zero-day vulnerabilities</span></span>

<span data-ttu-id="f0f73-141">Vaya a la página recomendación de seguridad y seleccione una recomendación con un día cero.</span><span class="sxs-lookup"><span data-stu-id="f0f73-141">Go to the security recommendation page and select a recommendation with a zero-day.</span></span> <span data-ttu-id="f0f73-142">Se abrirá un flyout con información sobre el día cero y otras vulnerabilidades de ese software.</span><span class="sxs-lookup"><span data-stu-id="f0f73-142">A flyout will open with information about the zero-day and other vulnerabilities for that software.</span></span>

<span data-ttu-id="f0f73-143">Habrá un vínculo a las opciones de mitigación y soluciones alternativas si están disponibles.</span><span class="sxs-lookup"><span data-stu-id="f0f73-143">There will be a link to mitigation options and workarounds if they are available.</span></span> <span data-ttu-id="f0f73-144">Las soluciones alternativas pueden ayudar a reducir el riesgo que representa esta vulnerabilidad de día cero hasta que se pueda implementar una revisión o actualización de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f0f73-144">Workarounds may help reduce the risk posed by this zero-day vulnerability until a patch or security update can be deployed.</span></span>

<span data-ttu-id="f0f73-145">Abra las opciones de corrección y elija el tipo de atención.</span><span class="sxs-lookup"><span data-stu-id="f0f73-145">Open remediation options and choose the attention type.</span></span> <span data-ttu-id="f0f73-146">Se recomienda una opción de corrección "necesaria para la atención" para las vulnerabilidades de día cero, ya que aún no se ha publicado una actualización.</span><span class="sxs-lookup"><span data-stu-id="f0f73-146">An "attention required" remediation option is recommended for the zero-day vulnerabilities, since an update hasn't been released yet.</span></span> <span data-ttu-id="f0f73-147">No podrá seleccionar una fecha de vencimiento, ya que no hay ninguna acción específica que realizar.</span><span class="sxs-lookup"><span data-stu-id="f0f73-147">You won't be able to select a due date, since there's no specific action to perform.</span></span> <span data-ttu-id="f0f73-148">Si hay vulnerabilidades más antiguas para este software que desea corregir, puede invalidar la opción de corrección "atención requerida" y elegir "actualizar".</span><span class="sxs-lookup"><span data-stu-id="f0f73-148">If there are older vulnerabilities for this software you wish to remediation, you can override the "attention required" remediation option and choose “update.”</span></span>

![Ejemplo de flyout de día cero Windows Server 2016 en la página de recomendaciones de seguridad.](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a><span data-ttu-id="f0f73-150">Realizar un seguimiento de las actividades de corrección de día cero</span><span class="sxs-lookup"><span data-stu-id="f0f73-150">Track zero-day remediation activities</span></span>

<span data-ttu-id="f0f73-151">Vaya a la página Administración de amenazas y vulnerabilidades [corrección para](tvm-remediation.md) ver el elemento de actividad de corrección.</span><span class="sxs-lookup"><span data-stu-id="f0f73-151">Go to the threat and vulnerability management [Remediation](tvm-remediation.md) page to view the remediation activity item.</span></span> <span data-ttu-id="f0f73-152">Si elige la opción de corrección "atención requerida", no habrá ninguna barra de progreso, estado de vale o fecha de vencimiento, ya que no hay ninguna acción real que podamos supervisar.</span><span class="sxs-lookup"><span data-stu-id="f0f73-152">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there's no actual action we can monitor.</span></span> <span data-ttu-id="f0f73-153">Puede filtrar por tipo de corrección, como "actualización de software" o "atención necesaria", para ver todos los elementos de actividad de la misma categoría.</span><span class="sxs-lookup"><span data-stu-id="f0f73-153">You can filter by remediation type, such as "software update" or "attention required," to see all activity items in the same category.</span></span>

## <a name="patching-zero-day-vulnerabilities"></a><span data-ttu-id="f0f73-154">Revisión de vulnerabilidades de día cero</span><span class="sxs-lookup"><span data-stu-id="f0f73-154">Patching zero-day vulnerabilities</span></span>

<span data-ttu-id="f0f73-155">Cuando se libera una revisión para el día cero, la recomendación se cambiará a "Actualizar" y una etiqueta azul junto a ella que diga "Nueva actualización de seguridad para el día cero".</span><span class="sxs-lookup"><span data-stu-id="f0f73-155">When a patch is released for the zero-day, the recommendation will be changed to “Update” and a blue label next to it that says “New security update for zero day.”</span></span> <span data-ttu-id="f0f73-156">Ya no se considerará como un día cero, la etiqueta de día cero se quitará de todas las páginas.</span><span class="sxs-lookup"><span data-stu-id="f0f73-156">It will no longer consider as a zero-day, the zero-day tag will be removed from all pages.</span></span>

![Recomendación para "Actualizar Microsoft Windows 10" con la nueva etiqueta de revisión.](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a><span data-ttu-id="f0f73-158">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="f0f73-158">Related articles</span></span>

- [<span data-ttu-id="f0f73-159">Información general sobre amenazas administración de vulnerabilidades amenazas</span><span class="sxs-lookup"><span data-stu-id="f0f73-159">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="f0f73-160">Panel</span><span class="sxs-lookup"><span data-stu-id="f0f73-160">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="f0f73-161">Recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="f0f73-161">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="f0f73-162">Inventario de software</span><span class="sxs-lookup"><span data-stu-id="f0f73-162">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="f0f73-163">Vulnerabilidades de mi organización</span><span class="sxs-lookup"><span data-stu-id="f0f73-163">Vulnerabilities in my organization</span></span>](tvm-weaknesses.md)
