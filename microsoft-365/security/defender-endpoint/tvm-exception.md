---
title: 'Crear y ver excepciones para recomendaciones de seguridad: Administración de amenazas y vulnerabilidades'
description: Cree y supervise excepciones para las recomendaciones de seguridad en Administración de amenazas y vulnerabilidades.
keywords: Microsoft Defender para la corrección de endpoint tvm, Microsoft Defender para Endpoint tvm, Administración de amenazas y vulnerabilidades, threat & administración de vulnerabilidades, threat & administración de vulnerabilidades remediation, tvm remediation intune, tvm remediation sccm
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1af8e5ec9d3aef560c739de5212e8118cf89cd7a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933750"
---
# <a name="create-and-view-exceptions-for-security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="53f60-104">Crear y ver excepciones para recomendaciones de seguridad: Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="53f60-104">Create and view exceptions for security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="53f60-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="53f60-105">**Applies to:**</span></span>

- [<span data-ttu-id="53f60-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="53f60-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="53f60-107">Amenaza y administración de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="53f60-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="53f60-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="53f60-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="53f60-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="53f60-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="53f60-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="53f60-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="53f60-111">Como alternativa a una solicitud de corrección cuando una recomendación no es relevante en este momento, puede crear excepciones para las recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="53f60-111">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> <span data-ttu-id="53f60-112">Si tu organización tiene grupos de dispositivos, podrás tener en cuenta la excepción para grupos de dispositivos específicos.</span><span class="sxs-lookup"><span data-stu-id="53f60-112">If your organization has device groups, you will be able to scope the exception to specific device groups.</span></span> <span data-ttu-id="53f60-113">Las excepciones se pueden crear para grupos de dispositivos seleccionados o para todos los grupos de dispositivos pasados y presentes.</span><span class="sxs-lookup"><span data-stu-id="53f60-113">Exceptions can either be created for selected device groups, or for all device groups past and present.</span></span>  

<span data-ttu-id="53f60-114">Cuando se crea una excepción para una recomendación, la recomendación no estará activa hasta el final de la duración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="53f60-114">When an exception is created for a recommendation, the recommendation will not be active until the end of the exception duration.</span></span> <span data-ttu-id="53f60-115">El estado de recomendación cambiará a **Excepción completa** o **Excepción parcial** (por grupo de dispositivos).</span><span class="sxs-lookup"><span data-stu-id="53f60-115">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

## <a name="permissions"></a><span data-ttu-id="53f60-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="53f60-116">Permissions</span></span>

<span data-ttu-id="53f60-117">Solo los usuarios con permisos de "control de excepciones" pueden administrar excepciones (incluida la creación o la cancelación).</span><span class="sxs-lookup"><span data-stu-id="53f60-117">Only users with “exceptions handling” permissions can manage exceptions (including creating or canceling).</span></span> <span data-ttu-id="53f60-118">[Obtenga más información sobre los roles RBAC](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="53f60-118">[Learn more about RBAC roles](user-roles.md).</span></span>

![Vista del permiso de control de excepciones.](images/tvm-exception-permissions.png)

## <a name="create-an-exception"></a><span data-ttu-id="53f60-120">Crear una excepción</span><span class="sxs-lookup"><span data-stu-id="53f60-120">Create an exception</span></span>

<span data-ttu-id="53f60-121">Seleccione una recomendación de seguridad para la que quiera crear una excepción y, a continuación, seleccione **Opciones de excepción** y rellene el formulario.</span><span class="sxs-lookup"><span data-stu-id="53f60-121">Select a security recommendation you would like create an exception for, and then select **Exception options** and fill out the form.</span></span>  

![Mostrar dónde se encuentra el botón de "opciones de excepción" en un control de control de recomendación de seguridad.](images/tvm-exception-options.png)

### <a name="exception-by-device-group"></a><span data-ttu-id="53f60-123">Excepción por grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="53f60-123">Exception by device group</span></span>

<span data-ttu-id="53f60-124">Aplica la excepción a todos los grupos de dispositivos actuales o elige grupos de dispositivos específicos.</span><span class="sxs-lookup"><span data-stu-id="53f60-124">Apply the exception to all current device groups or choose specific device groups.</span></span> <span data-ttu-id="53f60-125">Los grupos de dispositivos futuros no se incluirán en la excepción.</span><span class="sxs-lookup"><span data-stu-id="53f60-125">Future device groups won't be included in the exception.</span></span> <span data-ttu-id="53f60-126">Los grupos de dispositivos que ya tienen una excepción no se mostrarán en la lista.</span><span class="sxs-lookup"><span data-stu-id="53f60-126">Device groups that already have an exception will not be displayed in the list.</span></span> <span data-ttu-id="53f60-127">Si solo seleccionas determinados grupos de dispositivos, el estado de recomendación cambiará de "activo" a "excepción parcial".</span><span class="sxs-lookup"><span data-stu-id="53f60-127">If you only select certain device groups, the recommendation state will change from “active” to “partial exception.”</span></span> <span data-ttu-id="53f60-128">El estado cambiará a "excepción completa" si seleccionas todos los grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="53f60-128">The state will change to “full exception” if you select all the device groups.</span></span>

![Mostrar la lista desplegable de grupos de dispositivos.](images/tvm-exception-device-group-500.png)

#### <a name="filtered-views"></a><span data-ttu-id="53f60-130">Vistas filtradas</span><span class="sxs-lookup"><span data-stu-id="53f60-130">Filtered views</span></span>

<span data-ttu-id="53f60-131">Si has filtrado por grupo de dispositivos en cualquiera de las Administración de amenazas y vulnerabilidades, solo los grupos de dispositivos filtrados aparecerán como opciones.</span><span class="sxs-lookup"><span data-stu-id="53f60-131">If you have filtered by device group on any of the threat and vulnerability management pages, only your filtered device groups will appear as options.</span></span>

<span data-ttu-id="53f60-132">Este es el botón para filtrar por grupo de dispositivos en cualquiera de las Administración de amenazas y vulnerabilidades:</span><span class="sxs-lookup"><span data-stu-id="53f60-132">This is the button to filter by device group on any of the threat and vulnerability management pages:</span></span> 

![Mostrar el filtro de grupos de dispositivos seleccionados.](images/tvm-selected-device-groups.png)

<span data-ttu-id="53f60-134">Vista de excepción con grupos de dispositivos filtrados:</span><span class="sxs-lookup"><span data-stu-id="53f60-134">Exception view with filtered device groups:</span></span>

![Mostrar la lista desplegable de grupos de dispositivos filtrados.](images/tvm-exception-device-filter500.png)

#### <a name="large-number-of-device-groups"></a><span data-ttu-id="53f60-136">Gran número de grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="53f60-136">Large number of device groups</span></span>

<span data-ttu-id="53f60-137">Si tu organización tiene más de 20 grupos de dispositivos, selecciona **Editar** junto a la opción grupo de dispositivos filtrado.</span><span class="sxs-lookup"><span data-stu-id="53f60-137">If your organization has more than 20 device groups, select **Edit** next to the filtered device group option.</span></span>

![Muestra cómo editar un gran número de grupos.](images/tvm-exception-edit-groups.png)

<span data-ttu-id="53f60-139">Aparecerá un menú desplegable donde puedes buscar y elegir los grupos de dispositivos que quieras incluir.</span><span class="sxs-lookup"><span data-stu-id="53f60-139">A flyout will appear where you can search and choose device groups you want included.</span></span> <span data-ttu-id="53f60-140">Seleccione el icono de marca de verificación debajo de Buscar para activar o desactivar todo.</span><span class="sxs-lookup"><span data-stu-id="53f60-140">Select the check mark icon below Search to check/uncheck all.</span></span>

![Mostrar el menú desplegable de grupos de dispositivos grandes.](images/tvm-exception-device-group-flyout-400.png)

### <a name="global-exceptions"></a><span data-ttu-id="53f60-142">Excepciones globales</span><span class="sxs-lookup"><span data-stu-id="53f60-142">Global exceptions</span></span>

<span data-ttu-id="53f60-143">Si tiene permisos de administrador global, podrá crear y cancelar una excepción global.</span><span class="sxs-lookup"><span data-stu-id="53f60-143">If you have global administrator permissions, you will be able to create and cancel a global exception.</span></span> <span data-ttu-id="53f60-144">Afecta a todos **los** grupos de dispositivos actuales y futuros de la organización y solo un usuario con permisos similares podría cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="53f60-144">It affects **all** current and future device groups in your organization, and only a user with similar permission would be able to change it.</span></span> <span data-ttu-id="53f60-145">El estado de recomendación cambiará de "activo" a "excepción completa".</span><span class="sxs-lookup"><span data-stu-id="53f60-145">The recommendation state will change from “active” to “full exception.”</span></span>

![Mostrar la opción de excepción global.](images/tvm-exception-global.png)

<span data-ttu-id="53f60-147">Algunas cosas a tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="53f60-147">Some things to keep in mind:</span></span>

- <span data-ttu-id="53f60-148">Si una recomendación está en excepción global, las excepciones recién creadas para grupos de dispositivos se suspenderán hasta que la excepción global haya expirado o se haya cancelado.</span><span class="sxs-lookup"><span data-stu-id="53f60-148">If a recommendation is under global exception, then newly created exceptions for device groups will be suspended until the global exception has expired or been cancelled.</span></span> <span data-ttu-id="53f60-149">Después de ese punto, las nuevas excepciones de grupo de dispositivos se harán efectivas hasta que expiren.</span><span class="sxs-lookup"><span data-stu-id="53f60-149">After that point, the new device group exceptions will go into effect until they expire.</span></span>
- <span data-ttu-id="53f60-150">Si una recomendación ya tiene excepciones para grupos de dispositivos específicos y se crea una excepción global, la excepción de grupo de dispositivos se suspenderá hasta que expire o la excepción global se cancele antes de que expire.</span><span class="sxs-lookup"><span data-stu-id="53f60-150">If a recommendation already has exceptions for specific device groups and a global exception is created, then the device group exception will be suspended until it expires or the global exception is cancelled before it expires.</span></span>

### <a name="justification"></a><span data-ttu-id="53f60-151">Justificación</span><span class="sxs-lookup"><span data-stu-id="53f60-151">Justification</span></span>

<span data-ttu-id="53f60-152">Seleccione la justificación de la excepción que necesita presentar en lugar de corregir la recomendación de seguridad en cuestión.</span><span class="sxs-lookup"><span data-stu-id="53f60-152">Select your justification for the exception you need to file instead of remediating the security recommendation in question.</span></span> <span data-ttu-id="53f60-153">Rellene el contexto de justificación y, a continuación, establezca la duración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="53f60-153">Fill out the justification context, then set the exception duration.</span></span>

<span data-ttu-id="53f60-154">En la siguiente lista se detallan las justificaciones detrás de las opciones de excepción:</span><span class="sxs-lookup"><span data-stu-id="53f60-154">The following list details the justifications behind the exception options:</span></span>

- <span data-ttu-id="53f60-155">**Control de terceros:** un producto o software de terceros ya aborda esta recomendación: elegir este tipo de justificación reducirá la puntuación de exposición y aumentará la puntuación segura porque se reduce el riesgo</span><span class="sxs-lookup"><span data-stu-id="53f60-155">**Third party control** - A third party product or software already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="53f60-156">**Mitigación alternativa:** una herramienta interna ya aborda esta recomendación: elegir este tipo de justificación reducirá la puntuación de exposición y aumentará la puntuación segura porque el riesgo se reduce.</span><span class="sxs-lookup"><span data-stu-id="53f60-156">**Alternate mitigation** - An internal tool already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="53f60-157">**Riesgo aceptado:** el riesgo bajo o la implementación de la recomendación es demasiado caro</span><span class="sxs-lookup"><span data-stu-id="53f60-157">**Risk accepted** - Poses low risk and/or implementing the recommendation is too expensive</span></span>
- <span data-ttu-id="53f60-158">**Corrección planeada (gracia):** ya planeada, pero está a la espera de la ejecución o autorización</span><span class="sxs-lookup"><span data-stu-id="53f60-158">**Planned remediation (grace)** - Already planned but is awaiting execution or authorization</span></span>

## <a name="view-all-exceptions"></a><span data-ttu-id="53f60-159">Ver todas las excepciones</span><span class="sxs-lookup"><span data-stu-id="53f60-159">View all exceptions</span></span>

<span data-ttu-id="53f60-160">Vaya a la **pestaña Excepciones** de la **página Corrección.**</span><span class="sxs-lookup"><span data-stu-id="53f60-160">Navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="53f60-161">Puede filtrar por justificación, tipo y estado.</span><span class="sxs-lookup"><span data-stu-id="53f60-161">You can filter by justification, type, and status.</span></span>

 <span data-ttu-id="53f60-162">Seleccione una excepción para abrir un control desplegable con más detalles.</span><span class="sxs-lookup"><span data-stu-id="53f60-162">Select an exception to open a flyout with more details.</span></span> <span data-ttu-id="53f60-163">Las excepciones por grupo de dispositivos tendrán una lista de todos los grupos de dispositivos que cubre la excepción, que puedes exportar.</span><span class="sxs-lookup"><span data-stu-id="53f60-163">Exceptions per devices group will have a list of every device group the exception covers, which you can export.</span></span> <span data-ttu-id="53f60-164">También puede ver la recomendación relacionada o cancelar la excepción.</span><span class="sxs-lookup"><span data-stu-id="53f60-164">You can also view the related recommendation or cancel the exception.</span></span>

![Mostrar la pestaña "Excepciones" en la página Corrección.](images/tvm-exception-view.png)

## <a name="how-to-cancel-an-exception"></a><span data-ttu-id="53f60-166">Cómo cancelar una excepción</span><span class="sxs-lookup"><span data-stu-id="53f60-166">How to cancel an exception</span></span>

<span data-ttu-id="53f60-167">Para cancelar una excepción, vaya a la **pestaña Excepciones** de la **página** Corrección.</span><span class="sxs-lookup"><span data-stu-id="53f60-167">To cancel an exception, navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="53f60-168">Seleccione la excepción.</span><span class="sxs-lookup"><span data-stu-id="53f60-168">Select the exception.</span></span>

<span data-ttu-id="53f60-169">Para cancelar la excepción para todos los grupos de dispositivos o para una excepción global, selecciona el **botón Cancelar excepción para todos los** grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="53f60-169">To cancel the exception for all device groups or for a global exception, select the **Cancel exception for all device groups** button.</span></span> <span data-ttu-id="53f60-170">Solo podrás cancelar excepciones para grupos de dispositivos para los que tienes permisos.</span><span class="sxs-lookup"><span data-stu-id="53f60-170">You will only be able to cancel exceptions for device groups you have permissions for.</span></span>

![Botón Cancelar.](images/tvm-exception-cancel.png)

### <a name="cancel-the-exception-for-a-specific-device-group"></a><span data-ttu-id="53f60-172">Cancelar la excepción de un grupo de dispositivos específico</span><span class="sxs-lookup"><span data-stu-id="53f60-172">Cancel the exception for a specific device group</span></span>

<span data-ttu-id="53f60-173">Selecciona el grupo de dispositivos específico para cancelar la excepción.</span><span class="sxs-lookup"><span data-stu-id="53f60-173">Select the specific device group to cancel the exception for it.</span></span> <span data-ttu-id="53f60-174">Aparecerá un control desplegable para el grupo de dispositivos y puedes seleccionar **Cancelar excepción**.</span><span class="sxs-lookup"><span data-stu-id="53f60-174">A flyout will appear for the device group, and you can select **Cancel exception**.</span></span>

![Muestra cómo seleccionar un grupo de dispositivos específico.](images/tvm-exception-device-group-hover.png)

## <a name="view-impact-after-exceptions-are-applied"></a><span data-ttu-id="53f60-176">Ver impacto después de aplicar excepciones</span><span class="sxs-lookup"><span data-stu-id="53f60-176">View impact after exceptions are applied</span></span>

<span data-ttu-id="53f60-177">En la página Recomendaciones seguridad,  seleccione Personalizar columnas y active las **casillas dispositivos expuestos (después** de excepciones) e **Impacto (después de excepciones).**</span><span class="sxs-lookup"><span data-stu-id="53f60-177">In the Security Recommendations page, select **Customize columns** and check the boxes for **Exposed devices (after exceptions)** and **Impact (after exceptions)**.</span></span>

![Mostrar opciones de personalizar columnas.](images/tvm-after-exceptions.png)

<span data-ttu-id="53f60-179">La columna dispositivos expuestos (después de excepciones) muestra los dispositivos restantes que siguen expuestos a vulnerabilidades después de aplicar excepciones.</span><span class="sxs-lookup"><span data-stu-id="53f60-179">The exposed devices (after exceptions) column shows the remaining devices that are still exposed to vulnerabilities after exceptions are applied.</span></span> <span data-ttu-id="53f60-180">Las justificaciones de excepción que afectan a la exposición incluyen "control de terceros" y "mitigación alternativa".</span><span class="sxs-lookup"><span data-stu-id="53f60-180">Exception justifications that affect the exposure include ‘third party control’ and ‘alternate mitigation’.</span></span> <span data-ttu-id="53f60-181">Otras justificaciones no reducen la exposición de un dispositivo y aún se consideran expuestas.</span><span class="sxs-lookup"><span data-stu-id="53f60-181">Other justifications do not reduce the exposure of a device, and they are still considered exposed.</span></span>

<span data-ttu-id="53f60-182">El impacto (después de las excepciones) muestra el impacto restante en la puntuación de exposición o la puntuación segura después de aplicar las excepciones.</span><span class="sxs-lookup"><span data-stu-id="53f60-182">The impact (after exceptions) shows remaining impact to exposure score or secure score after exceptions are applied.</span></span> <span data-ttu-id="53f60-183">Las justificaciones de excepción que afectan a las puntuaciones incluyen "control de terceros" y "mitigación alternativa".</span><span class="sxs-lookup"><span data-stu-id="53f60-183">Exception justifications that affect the scores include ‘third party control’ and ‘alternate mitigation.’</span></span> <span data-ttu-id="53f60-184">Otras justificaciones no reducen la exposición de un dispositivo, por lo que la puntuación de exposición y la puntuación segura no cambian.</span><span class="sxs-lookup"><span data-stu-id="53f60-184">Other justifications do not reduce the exposure of a device, and so the exposure score and secure score do not change.</span></span>

![Mostrar las columnas de la tabla.](images/tvm-after-exceptions-table.png)

## <a name="related-topics"></a><span data-ttu-id="53f60-186">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="53f60-186">Related topics</span></span>

- [<span data-ttu-id="53f60-187">Información general sobre amenazas administración de vulnerabilidades amenazas</span><span class="sxs-lookup"><span data-stu-id="53f60-187">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="53f60-188">Corregir puntos vulnerables</span><span class="sxs-lookup"><span data-stu-id="53f60-188">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="53f60-189">Recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="53f60-189">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="53f60-190">Puntuación de exposición</span><span class="sxs-lookup"><span data-stu-id="53f60-190">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="53f60-191">Puntuación de seguridad de Microsoft para dispositivos</span><span class="sxs-lookup"><span data-stu-id="53f60-191">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
