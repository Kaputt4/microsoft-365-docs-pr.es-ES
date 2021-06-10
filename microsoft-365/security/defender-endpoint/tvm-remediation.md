---
title: Corregir vulnerabilidades con Administración de amenazas y vulnerabilidades
description: Corrija las debilidades de seguridad detectadas mediante recomendaciones de seguridad y cree excepciones si es necesario, en Administración de amenazas y vulnerabilidades.
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
ms.openlocfilehash: 602a38d8ad27505e81628db265681ac89218e593
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840916"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a><span data-ttu-id="ad7da-104">Corregir vulnerabilidades con Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="ad7da-104">Remediate vulnerabilities with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ad7da-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ad7da-105">**Applies to:**</span></span>
- [<span data-ttu-id="ad7da-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="ad7da-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="ad7da-107">Amenaza y administración de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="ad7da-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="ad7da-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad7da-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ad7da-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="ad7da-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ad7da-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="ad7da-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a><span data-ttu-id="ad7da-111">Corrección de solicitudes</span><span class="sxs-lookup"><span data-stu-id="ad7da-111">Request remediation</span></span>

<span data-ttu-id="ad7da-112">La Administración de amenazas y vulnerabilidades de Microsoft Defender para endpoints se abate entre los administradores de seguridad y TI a través del flujo de trabajo de solicitud de corrección.</span><span class="sxs-lookup"><span data-stu-id="ad7da-112">The threat and vulnerability management capability in Microsoft Defender for Endpoint bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="ad7da-113">Los administradores de seguridad como usted pueden solicitar al administrador de TI que corrija una vulnerabilidad de las **páginas** de recomendaciones de seguridad a Intune.</span><span class="sxs-lookup"><span data-stu-id="ad7da-113">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** pages to Intune.</span></span>

### <a name="enable-microsoft-intune-connection"></a><span data-ttu-id="ad7da-114">Habilitar Microsoft Intune conexión</span><span class="sxs-lookup"><span data-stu-id="ad7da-114">Enable Microsoft Intune connection</span></span>

<span data-ttu-id="ad7da-115">Para usar esta funcionalidad, habilite las Microsoft Intune conexión.</span><span class="sxs-lookup"><span data-stu-id="ad7da-115">To use this capability, enable your Microsoft Intune connections.</span></span> <span data-ttu-id="ad7da-116">En el Centro de seguridad de Microsoft Defender, vaya **a** Configuración  >  **características**  >  **avanzadas generales**.</span><span class="sxs-lookup"><span data-stu-id="ad7da-116">In the Microsoft Defender Security Center, navigate to **Settings** > **General** > **Advanced features**.</span></span> <span data-ttu-id="ad7da-117">Desplácese hacia abajo y busque **Microsoft Intune conexión**.</span><span class="sxs-lookup"><span data-stu-id="ad7da-117">Scroll down and look for **Microsoft Intune connection**.</span></span> <span data-ttu-id="ad7da-118">De forma predeterminada, la alternancia está desactivada.</span><span class="sxs-lookup"><span data-stu-id="ad7da-118">By default, the toggle is turned off.</span></span> <span data-ttu-id="ad7da-119">Activar la **Microsoft Intune de** **conexión** activa .</span><span class="sxs-lookup"><span data-stu-id="ad7da-119">Turn your **Microsoft Intune connection** toggle **On**.</span></span>

<span data-ttu-id="ad7da-120">**Nota:** Si tienes habilitada la conexión de Intune, obtienes una opción para crear una tarea de seguridad de Intune al crear una solicitud de corrección.</span><span class="sxs-lookup"><span data-stu-id="ad7da-120">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="ad7da-121">Esta opción no aparece si la conexión no está establecida.</span><span class="sxs-lookup"><span data-stu-id="ad7da-121">This option does not appear if the connection is not set.</span></span>

<span data-ttu-id="ad7da-122">Consulta [Usar Intune para corregir las vulnerabilidades identificadas por Microsoft Defender para obtener más](/intune/atp-manage-vulnerabilities) información.</span><span class="sxs-lookup"><span data-stu-id="ad7da-122">See [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](/intune/atp-manage-vulnerabilities) for details.</span></span>

### <a name="remediation-request-steps"></a><span data-ttu-id="ad7da-123">Pasos de solicitud de corrección</span><span class="sxs-lookup"><span data-stu-id="ad7da-123">Remediation request steps</span></span>

1. <span data-ttu-id="ad7da-124">Vaya al menú Administración de amenazas y vulnerabilidades navegación de la Centro de seguridad de Microsoft Defender y seleccione [**Recomendaciones de seguridad**](tvm-security-recommendation.md).</span><span class="sxs-lookup"><span data-stu-id="ad7da-124">Go to the threat and vulnerability management navigation menu in the Microsoft Defender Security Center, and select [**Security recommendations**](tvm-security-recommendation.md).</span></span>

2. <span data-ttu-id="ad7da-125">Seleccione una recomendación de seguridad para la que desea solicitar corrección y, a continuación, seleccione **Opciones de corrección**.</span><span class="sxs-lookup"><span data-stu-id="ad7da-125">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span>

3. <span data-ttu-id="ad7da-126">Rellene el formulario, incluidos los grupos de dispositivos aplicables, la prioridad, la fecha de vencimiento y las notas opcionales.</span><span class="sxs-lookup"><span data-stu-id="ad7da-126">Fill out the form, including what you are requesting remediation for, applicable device groups, priority, due date, and optional notes.</span></span>
    1. <span data-ttu-id="ad7da-127">Si elige la opción de corrección "atención requerida", la selección de una fecha de vencimiento no estará disponible ya que no hay ninguna acción específica.</span><span class="sxs-lookup"><span data-stu-id="ad7da-127">If you choose the "attention required" remediation option, selecting a due date will not be available since there is no specific action.</span></span>

4. <span data-ttu-id="ad7da-128">Seleccione **Enviar solicitud**.</span><span class="sxs-lookup"><span data-stu-id="ad7da-128">Select **Submit request**.</span></span> <span data-ttu-id="ad7da-129">Enviar una solicitud de corrección crea un elemento de actividad de corrección dentro de Administración de amenazas y vulnerabilidades, que se puede usar para supervisar el progreso de corrección de esta recomendación.</span><span class="sxs-lookup"><span data-stu-id="ad7da-129">Submitting a remediation request creates a remediation activity item within threat and vulnerability management, which can be used for monitoring the remediation progress for this recommendation.</span></span> <span data-ttu-id="ad7da-130">Esto no desencadenará una corrección ni aplicará ningún cambio en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ad7da-130">This will not trigger a remediation or apply any changes to devices.</span></span>

5. <span data-ttu-id="ad7da-131">Notifique al administrador de TI acerca de la nueva solicitud y haga que inicie sesión en Intune para aprobar o rechazar la solicitud e iniciar una implementación de paquete.</span><span class="sxs-lookup"><span data-stu-id="ad7da-131">Notify your IT Administrator about the new request and have them log into Intune to approve or reject the request and start a package deployment.</span></span>

6. <span data-ttu-id="ad7da-132">Vaya a la [**página Corrección**](tvm-remediation.md) para ver el estado de la solicitud de corrección.</span><span class="sxs-lookup"><span data-stu-id="ad7da-132">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span>

<span data-ttu-id="ad7da-133">Si quieres comprobar cómo se muestra el vale en Intune, consulta Usar Intune para corregir las vulnerabilidades identificadas por [Microsoft Defender](/intune/atp-manage-vulnerabilities) para endpoint para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ad7da-133">If you want to check how the ticket shows up in Intune, see [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](/intune/atp-manage-vulnerabilities) for details.</span></span>

>[!NOTE]
><span data-ttu-id="ad7da-134">Si la solicitud implica la corrección de más de 10 000 dispositivos, solo podemos enviar 10 000 dispositivos para su corrección a Intune.</span><span class="sxs-lookup"><span data-stu-id="ad7da-134">If your request involves remediating more than 10,000 devices, we can only send 10,000 devices for remediation to Intune.</span></span>

<span data-ttu-id="ad7da-135">Después de identificar y asignar las debilidades de seguridad cibernética de su organización a recomendaciones de seguridad que se pueden [realizar,](tvm-security-recommendation.md)comience a crear tareas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ad7da-135">After your organization's cybersecurity weaknesses are identified and mapped to actionable [security recommendations](tvm-security-recommendation.md), start creating security tasks.</span></span> <span data-ttu-id="ad7da-136">Puede crear tareas a través de la integración con Microsoft Intune donde se crean vales de corrección.</span><span class="sxs-lookup"><span data-stu-id="ad7da-136">You can create tasks through the integration with Microsoft Intune where remediation tickets are created.</span></span>

<span data-ttu-id="ad7da-137">Reduzca la exposición de su organización a las vulnerabilidades y aumente la configuración de seguridad mediante la corrección de las recomendaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ad7da-137">Lower your organization's exposure from vulnerabilities and increase your security configuration by remediating the security recommendations.</span></span>

## <a name="view-your-remediation-activities"></a><span data-ttu-id="ad7da-138">Ver las actividades de corrección</span><span class="sxs-lookup"><span data-stu-id="ad7da-138">View your remediation activities</span></span>

<span data-ttu-id="ad7da-139">Cuando envía una solicitud de corrección desde la página Recomendaciones de seguridad, inicia una actividad de corrección.</span><span class="sxs-lookup"><span data-stu-id="ad7da-139">When you submit a remediation request from the Security recommendations page, it kicks-off a remediation activity.</span></span> <span data-ttu-id="ad7da-140">Se crea una tarea de seguridad que se puede realizar un seguimiento en la página Administración de amenazas y vulnerabilidades **corrección** y se crea un vale de corrección en Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="ad7da-140">A security task is created that can be tracked in the threat and vulnerability management **Remediation** page, and a remediation ticket is created in Microsoft Intune.</span></span>

<span data-ttu-id="ad7da-141">Si elige la opción de corrección "atención requerida", no habrá ninguna barra de progreso, estado de vale o fecha de vencimiento, ya que no hay ninguna acción real que podamos supervisar.</span><span class="sxs-lookup"><span data-stu-id="ad7da-141">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there is no actual action we can monitor.</span></span>

<span data-ttu-id="ad7da-142">Una vez que se encuentra en la página Corrección, seleccione la actividad de corrección que desea ver.</span><span class="sxs-lookup"><span data-stu-id="ad7da-142">Once you are in the Remediation page, select the remediation activity that you want to view.</span></span> <span data-ttu-id="ad7da-143">Puede seguir los pasos de corrección, realizar un seguimiento del progreso, ver la recomendación relacionada, exportar a CSV o marcar como completada.</span><span class="sxs-lookup"><span data-stu-id="ad7da-143">You can follow the remediation steps, track progress, view the related recommendation, export to CSV, or mark as complete.</span></span>
<span data-ttu-id="ad7da-144">![Ejemplo de la página Corrección, con una actividad de corrección seleccionada, y el control desplegable de esa actividad enumera la descripción, las herramientas de administración de dispositivos y servicio de IT y el progreso de corrección de dispositivos.](images/remediation_flyouteolsw.png)</span><span class="sxs-lookup"><span data-stu-id="ad7da-144">![Example of the Remediation page, with a selected remediation activity, and that activity's flyout listing the description, IT service and device management tools, and device remediation progress.](images/remediation_flyouteolsw.png)</span></span>

>[!NOTE]
> <span data-ttu-id="ad7da-145">Hay un período de retención de 180 días para las actividades de corrección completadas.</span><span class="sxs-lookup"><span data-stu-id="ad7da-145">There is a 180 day retention period for completed remediation activities.</span></span> <span data-ttu-id="ad7da-146">Para mantener el rendimiento óptimo de la página Corrección, la actividad de corrección se quitará 6 meses después de su finalización.</span><span class="sxs-lookup"><span data-stu-id="ad7da-146">To keep the Remediation page performing optimally, the remediation activity will be removed 6 months after its completion.</span></span>

### <a name="completed-by-column"></a><span data-ttu-id="ad7da-147">Completado por columna</span><span class="sxs-lookup"><span data-stu-id="ad7da-147">Completed by column</span></span>

<span data-ttu-id="ad7da-148">Realice un seguimiento de quién cerró la actividad de corrección con la columna "Completado por" en la página Corrección.</span><span class="sxs-lookup"><span data-stu-id="ad7da-148">Track who closed the remediation activity with the "Completed by" column on the Remediation page.</span></span>

- <span data-ttu-id="ad7da-149">**Dirección de correo** electrónico: el correo electrónico de la persona que completó manualmente la tarea</span><span class="sxs-lookup"><span data-stu-id="ad7da-149">**Email address**: The email of the person who manually completed the task</span></span>
- <span data-ttu-id="ad7da-150">**Confirmación del** sistema: la tarea se completó automáticamente (se han corregido todos los dispositivos)</span><span class="sxs-lookup"><span data-stu-id="ad7da-150">**System confirmation**: The task was automatically completed (all devices remediated)</span></span>
- <span data-ttu-id="ad7da-151">**N/A:** la información no está disponible porque no sabemos cómo se completó esta tarea anterior</span><span class="sxs-lookup"><span data-stu-id="ad7da-151">**N/A**: Information is not available because we don't know how this older task was completed</span></span>

![Creado por y completado por columnas con dos filas.](images/tvm-completed-by.png)

### <a name="top-remediation-activities-in-the-dashboard"></a><span data-ttu-id="ad7da-154">Principales actividades de corrección en el panel</span><span class="sxs-lookup"><span data-stu-id="ad7da-154">Top remediation activities in the dashboard</span></span>

<span data-ttu-id="ad7da-155">Ver **las principales actividades de** corrección en el Administración de amenazas y vulnerabilidades [panel](tvm-dashboard-insights.md).</span><span class="sxs-lookup"><span data-stu-id="ad7da-155">View **Top remediation activities** in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span> <span data-ttu-id="ad7da-156">Seleccione cualquiera de las entradas para ir a la **página Corrección.**</span><span class="sxs-lookup"><span data-stu-id="ad7da-156">Select any of the entries to go to the **Remediation** page.</span></span> <span data-ttu-id="ad7da-157">Puede marcar la actividad de corrección como completada después de que el equipo de administración de TI corrija la tarea.</span><span class="sxs-lookup"><span data-stu-id="ad7da-157">You can mark the remediation activity as completed after the IT admin team remediates the task.</span></span>

![Ejemplo de tarjeta de actividades de corrección superior con una tabla que enumera las actividades principales que se generaron a partir de recomendaciones de seguridad.](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a><span data-ttu-id="ad7da-159">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="ad7da-159">Related articles</span></span>

- [<span data-ttu-id="ad7da-160">Información general sobre amenazas administración de vulnerabilidades amenazas</span><span class="sxs-lookup"><span data-stu-id="ad7da-160">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="ad7da-161">Panel</span><span class="sxs-lookup"><span data-stu-id="ad7da-161">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="ad7da-162">Recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="ad7da-162">Security recommendations</span></span>](tvm-security-recommendation.md)