---
title: Visite el Centro de acciones para ver acciones de corrección
description: Usar el centro de acción para ver detalles y resultados después de una investigación automatizada
keywords: acción, centro, autoir, automatizado, investigación, respuesta, corrección
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: e51cc1d613e6f9e7ab96653692362ed7fe239e3e
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274849"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a><span data-ttu-id="d6a72-104">Visite el Centro de acciones para ver acciones de corrección</span><span class="sxs-lookup"><span data-stu-id="d6a72-104">Visit the Action center to see remediation actions</span></span>

<span data-ttu-id="d6a72-105">Durante y después de una investigación automatizada, se identifican las acciones de corrección para las detecciones de amenazas.</span><span class="sxs-lookup"><span data-stu-id="d6a72-105">During and after an automated investigation, remediation actions for threat detections are identified.</span></span> <span data-ttu-id="d6a72-106">Según la amenaza en particular y la configuración de [Microsoft Defender para](https://docs.microsoft.com/windows/security/threat-protection) endpoint para su organización, algunas acciones de corrección se toman automáticamente y otras requieren aprobación.</span><span class="sxs-lookup"><span data-stu-id="d6a72-106">Depending on the particular threat and how [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) is configured for your organization, some remediation actions are taken automatically, and others require approval.</span></span> <span data-ttu-id="d6a72-107">Si forma parte del equipo de operaciones de seguridad de su organización, puede ver las acciones de corrección pendientes y completadas [en](manage-auto-investigation.md#remediation-actions) el Centro **de acciones**.</span><span class="sxs-lookup"><span data-stu-id="d6a72-107">If you're part of your organization's security operations team, you can view pending and completed [remediation actions](manage-auto-investigation.md#remediation-actions) in the **Action center**.</span></span> 


<span data-ttu-id="d6a72-108">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d6a72-108">**Applies to:**</span></span>
- [<span data-ttu-id="d6a72-109">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d6a72-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d6a72-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d6a72-110">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a><span data-ttu-id="d6a72-111">(¡NUEVO!) Un centro de acción unificado</span><span class="sxs-lookup"><span data-stu-id="d6a72-111">(NEW!) A unified Action center</span></span>


<span data-ttu-id="d6a72-112">Nos complace anunciar un nuevo centro de acción unificado ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) )!</span><span class="sxs-lookup"><span data-stu-id="d6a72-112">We are pleased to announce a new, unified Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center))!</span></span>

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Centro de acciones en el Centro de seguridad de Microsoft 365":::

<span data-ttu-id="d6a72-114">En la tabla siguiente se compara el nuevo centro de acciones unificado con el centro de acciones anterior.</span><span class="sxs-lookup"><span data-stu-id="d6a72-114">The following table compares the new, unified Action center to the previous Action center.</span></span>

|<span data-ttu-id="d6a72-115">El nuevo centro de acciones unificado</span><span class="sxs-lookup"><span data-stu-id="d6a72-115">The new, unified Action center</span></span>  |<span data-ttu-id="d6a72-116">El centro de acciones anterior</span><span class="sxs-lookup"><span data-stu-id="d6a72-116">The previous Action center</span></span>  |
|---------|---------|
|<span data-ttu-id="d6a72-117">Enumera las acciones pendientes y completadas para dispositivos y correo electrónico en una ubicación</span><span class="sxs-lookup"><span data-stu-id="d6a72-117">Lists pending and completed actions for devices and email in one location</span></span> <br/><span data-ttu-id="d6a72-118">([Microsoft Defender para Endpoint](microsoft-defender-endpoint.md) más Microsoft Defender para Office [365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp))</span><span class="sxs-lookup"><span data-stu-id="d6a72-118">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) plus [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp))</span></span>|<span data-ttu-id="d6a72-119">Enumera las acciones pendientes y completadas para dispositivos</span><span class="sxs-lookup"><span data-stu-id="d6a72-119">Lists pending and completed actions for devices</span></span> <br/> <span data-ttu-id="d6a72-120">([Solo Microsoft Defender para punto de](microsoft-defender-endpoint.md) conexión)</span><span class="sxs-lookup"><span data-stu-id="d6a72-120">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) only)</span></span>   |
|<span data-ttu-id="d6a72-121">Se encuentra en:</span><span class="sxs-lookup"><span data-stu-id="d6a72-121">Is located at:</span></span><br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |<span data-ttu-id="d6a72-122">Se encuentra en:</span><span class="sxs-lookup"><span data-stu-id="d6a72-122">Is located at:</span></span><br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| <span data-ttu-id="d6a72-123">En el Centro de seguridad de Microsoft 365, elija **Centro de acciones**.</span><span class="sxs-lookup"><span data-stu-id="d6a72-123">In the Microsoft 365 security center, choose **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Navegar al Centro de acciones en el Centro de seguridad de Microsoft 365"::: | <span data-ttu-id="d6a72-125">En el Centro de seguridad de Microsoft Defender, elija **Centro de acciones de investigaciones automatizadas.**  >  </span><span class="sxs-lookup"><span data-stu-id="d6a72-125">In the Microsoft Defender Security Center, choose **Automated investigations** > **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Navegar al Centro de acciones desde el Centro de seguridad de Microsoft Defender":::  |

<span data-ttu-id="d6a72-127">El Centro de acción unificado reúne acciones de corrección en Defender para Endpoint y Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="d6a72-127">The unified Action center brings together remediation actions across Defender for Endpoint and Defender for Office 365.</span></span> <span data-ttu-id="d6a72-128">Define un lenguaje común para todas las acciones de corrección y proporciona una experiencia de investigación unificada.</span><span class="sxs-lookup"><span data-stu-id="d6a72-128">It defines a common language for all remediation actions, and provides a unified investigation experience.</span></span> 

<span data-ttu-id="d6a72-129">Puede usar el Centro de acciones unificado si tiene los permisos adecuados y una o varias de las siguientes suscripciones:</span><span class="sxs-lookup"><span data-stu-id="d6a72-129">You can use the unified Action center if you have appropriate permissions and one or more of the following subscriptions:</span></span>
- [<span data-ttu-id="d6a72-130">Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d6a72-130">Defender for Endpoint</span></span>](microsoft-defender-endpoint.md)
- [<span data-ttu-id="d6a72-131">Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="d6a72-131">Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="d6a72-132">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d6a72-132">Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> <span data-ttu-id="d6a72-133">Para obtener más información, vea [Requisitos](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).</span><span class="sxs-lookup"><span data-stu-id="d6a72-133">To learn more, see [Requirements](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).</span></span>

## <a name="using-the-action-center"></a><span data-ttu-id="d6a72-134">Uso del Centro de acciones</span><span class="sxs-lookup"><span data-stu-id="d6a72-134">Using the Action center</span></span>

<span data-ttu-id="d6a72-135">Para llegar al Centro de acciones unificado en el centro de seguridad mejorado de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="d6a72-135">To get to the unified Action center in the improved Microsoft 365 security center:</span></span>
1. <span data-ttu-id="d6a72-136">Vaya al Centro de seguridad de Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="d6a72-136">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="d6a72-137">En el panel de navegación, seleccione **Centro de acciones**.</span><span class="sxs-lookup"><span data-stu-id="d6a72-137">In the navigation pane, select **Action center**.</span></span> 

<span data-ttu-id="d6a72-138">Al visitar el Centro de acciones, verá dos pestañas: **Acciones pendientes** e **Historial**.</span><span class="sxs-lookup"><span data-stu-id="d6a72-138">When you visit the Action center, you see two tabs: **Pending actions** and **History**.</span></span> <span data-ttu-id="d6a72-139">En la tabla siguiente se resume lo que verá en cada pestaña:</span><span class="sxs-lookup"><span data-stu-id="d6a72-139">The following table summarizes what you'll see on each tab:</span></span>

|<span data-ttu-id="d6a72-140">Pestaña</span><span class="sxs-lookup"><span data-stu-id="d6a72-140">Tab</span></span>  |<span data-ttu-id="d6a72-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6a72-141">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="d6a72-142">**Pending**</span><span class="sxs-lookup"><span data-stu-id="d6a72-142">**Pending**</span></span>     | <span data-ttu-id="d6a72-143">Muestra una lista de acciones que requieren atención.</span><span class="sxs-lookup"><span data-stu-id="d6a72-143">Displays a list of actions that require attention.</span></span> <span data-ttu-id="d6a72-144">Puede aprobar o rechazar acciones de una en una, o seleccionar varias acciones si tienen el mismo tipo de acción (como el **archivo en cuarentena).**</span><span class="sxs-lookup"><span data-stu-id="d6a72-144">You can approve or reject actions one at a time, or select multiple actions if they have the same type of action (such as **Quarantine file**).</span></span> <br/><span data-ttu-id="d6a72-145">**SUGERENCIA:** Asegúrese de revisar y aprobar [(o rechazar)](manage-auto-investigation.md) las acciones pendientes tan pronto como sea posible para que las investigaciones automatizadas puedan completarse de forma oportuna.</span><span class="sxs-lookup"><span data-stu-id="d6a72-145">**TIP**: Make sure to [review and approve (or reject) pending actions](manage-auto-investigation.md) as soon as possible so that your automated investigations can complete in a timely manner.</span></span> |
|<span data-ttu-id="d6a72-146">**Historial**</span><span class="sxs-lookup"><span data-stu-id="d6a72-146">**History**</span></span>     | <span data-ttu-id="d6a72-147">Sirve como registro de auditoría para las acciones que se han realizado, como:</span><span class="sxs-lookup"><span data-stu-id="d6a72-147">Serves as an audit log for actions that were taken, such as:</span></span> <br/><span data-ttu-id="d6a72-148">- Acciones de corrección que se realizaron como resultado de investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="d6a72-148">- Remediation actions that were taken as a result of automated investigations</span></span> <br><span data-ttu-id="d6a72-149">- Acciones de corrección aprobadas por el equipo de operaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="d6a72-149">- Remediation actions that were approved by your security operations team</span></span>  <br/><span data-ttu-id="d6a72-150">- Comandos que se ejecutaron y acciones de corrección que se aplicaron durante las sesiones de Live Response</span><span class="sxs-lookup"><span data-stu-id="d6a72-150">- Commands that were run and remediation actions that were applied during Live Response sessions</span></span>  <br/><span data-ttu-id="d6a72-151">- Acciones de corrección realizadas por las características de protección contra amenazas en Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d6a72-151">- Remediation actions that were taken by threat protection features in Microsoft Defender Antivirus</span></span>  <p><span data-ttu-id="d6a72-152">Proporciona una forma de deshacer determinadas acciones (vea [Deshacer acciones completadas](manage-auto-investigation.md#undo-completed-actions)).</span><span class="sxs-lookup"><span data-stu-id="d6a72-152">Provides a way to undo certain actions (see [Undo completed actions](manage-auto-investigation.md#undo-completed-actions)).</span></span>       |

<span data-ttu-id="d6a72-153">Puede personalizar, ordenar, filtrar y exportar datos en el Centro de acciones.</span><span class="sxs-lookup"><span data-stu-id="d6a72-153">You can customize, sort, filter, and export data in the Action center.</span></span>

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="Columnas y filtros en el Centro de acciones":::

- <span data-ttu-id="d6a72-155">Seleccione un encabezado de columna para ordenar los elementos en orden ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="d6a72-155">Select a column heading to sort items in ascending or descending order.</span></span>
- <span data-ttu-id="d6a72-156">Use el filtro de período de tiempo para ver los datos del último día, semana, 30 días o 6 meses.</span><span class="sxs-lookup"><span data-stu-id="d6a72-156">Use the time period filter to view data for the past day, week, 30 days, or 6 months.</span></span>
- <span data-ttu-id="d6a72-157">Elija las columnas que desea ver.</span><span class="sxs-lookup"><span data-stu-id="d6a72-157">Choose the columns that you want to view.</span></span>
- <span data-ttu-id="d6a72-158">Especifique cuántos elementos se deben incluir en cada página de datos.</span><span class="sxs-lookup"><span data-stu-id="d6a72-158">Specify how many items to include on each page of data.</span></span>
- <span data-ttu-id="d6a72-159">Use filtros para ver solo los elementos que desea ver.</span><span class="sxs-lookup"><span data-stu-id="d6a72-159">Use filters to view just the items you want to see.</span></span>
- <span data-ttu-id="d6a72-160">Seleccione **Exportar** para exportar resultados a un .csv archivo.</span><span class="sxs-lookup"><span data-stu-id="d6a72-160">Select **Export** to export results to a .csv file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="d6a72-161">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d6a72-161">Next steps</span></span>

- [<span data-ttu-id="d6a72-162">Ver y aprobar acciones de corrección</span><span class="sxs-lookup"><span data-stu-id="d6a72-162">View and approve remediation actions</span></span>](manage-auto-investigation.md)
- [<span data-ttu-id="d6a72-163">Consulta la guía interactiva: Investigar y corregir amenazas con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="d6a72-163">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a><span data-ttu-id="d6a72-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6a72-164">See also</span></span>

- [<span data-ttu-id="d6a72-165">Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d6a72-165">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
