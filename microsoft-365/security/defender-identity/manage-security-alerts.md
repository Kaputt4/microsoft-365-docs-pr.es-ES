---
title: Alertas de seguridad de Microsoft Defender para identidad en Microsoft 365 Defender
description: Obtenga información sobre cómo administrar y revisar las alertas de seguridad emitidas por Microsoft Defender for Identity en Microsoft 365 Defender
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: c81f14b92b285359bda7e291bd8d3a8b636ae54d
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228968"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a><span data-ttu-id="0ec52-103">Alertas de seguridad de Defender for Identity en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ec52-103">Defender for Identity security alerts in Microsoft 365 Defender</span></span>

<span data-ttu-id="0ec52-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0ec52-104">**Applies to:**</span></span>

- <span data-ttu-id="0ec52-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ec52-105">Microsoft 365 Defender</span></span>
- <span data-ttu-id="0ec52-106">Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="0ec52-106">Defender for Identity</span></span>

<span data-ttu-id="0ec52-107">En este artículo se explican los conceptos básicos sobre cómo trabajar con [alertas](/defender-for-identity) de seguridad de Microsoft Defender para identidades en el [centro Microsoft 365 seguridad.](/microsoft-365/security/defender/overview-security-center)</span><span class="sxs-lookup"><span data-stu-id="0ec52-107">This article explains the basics of how to work with [Microsoft Defender for Identity](/defender-for-identity) security alerts in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center).</span></span>

<span data-ttu-id="0ec52-108">Las alertas de Defender for Identity se integran de forma nativa en el [Microsoft 365 de seguridad](https://security.microsoft.com) con un formato de página de alerta de identidad dedicado.</span><span class="sxs-lookup"><span data-stu-id="0ec52-108">Defender for Identity alerts are natively integrated into the [Microsoft 365 security center](https://security.microsoft.com) with a dedicated Identity alert page format.</span></span> <span data-ttu-id="0ec52-109">Esto marca el primer paso en el viaje para introducir la experiencia completa de [Microsoft Defender for Identity en Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="0ec52-109">This marks the first step in the journey to [introduce the full Microsoft Defender for Identity experience into Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).</span></span>

<span data-ttu-id="0ec52-110">La nueva página alerta de identidad proporciona a los clientes de Microsoft Defender para identidad mejores enriquecimiento de señales entre dominios y nuevas capacidades automatizadas de respuesta de identidad.</span><span class="sxs-lookup"><span data-stu-id="0ec52-110">The new Identity alert page gives Microsoft Defender for Identity customers better cross-domain signal enrichment and new automated identity response capabilities.</span></span> <span data-ttu-id="0ec52-111">Garantiza la seguridad y ayuda a mejorar la eficacia de las operaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0ec52-111">It ensures that you stay secure and helps improve the efficiency of your security operations.</span></span>

<span data-ttu-id="0ec52-112">Una de las ventajas de investigar alertas a través de [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) es que las alertas de Identidad de Microsoft Defender se correlacionan aún más con la información obtenida de cada uno de los otros productos del conjunto de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0ec52-112">One of the benefits of investigating alerts through [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) is that Microsoft Defender for Identity alerts are further correlated with information obtained from each of the other products in the suite.</span></span> <span data-ttu-id="0ec52-113">Estas alertas mejoradas son coherentes con los otros formatos de alerta Microsoft 365 Defender de [Microsoft Defender](/microsoft-365/security/office-365-security) para Office 365 y Microsoft Defender [para endpoint](/microsoft-365/security/defender-endpoint).</span><span class="sxs-lookup"><span data-stu-id="0ec52-113">These enhanced alerts are consistent with the other Microsoft 365 Defender alert formats originating from [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security) and [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span> <span data-ttu-id="0ec52-114">La nueva página elimina eficazmente la necesidad de navegar a otro portal de productos para investigar alertas asociadas con la identidad.</span><span class="sxs-lookup"><span data-stu-id="0ec52-114">The new page effectively eliminates the need to navigate to another product portal to investigate alerts associated with identity.</span></span>

<span data-ttu-id="0ec52-115">Las alertas que se originan en Defender for Identity ahora pueden desencadenar las capacidades de investigación y respuesta automatizadas [(AIR)](/microsoft-365/security/defender/m365d-autoir) de Microsoft 365 Defender, incluida la corrección automática de alertas y la mitigación de herramientas y procesos que pueden contribuir a la actividad sospechosa.</span><span class="sxs-lookup"><span data-stu-id="0ec52-115">Alerts originating from Defender for Identity can now trigger the [Microsoft 365 Defender automated investigation and response (AIR)](/microsoft-365/security/defender/m365d-autoir) capabilities, including automatically remediating alerts and the mitigation of tools and processes that can contribute to the suspicious activity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ec52-116">Como parte de la convergencia con Microsoft 365 Defender, algunas opciones y detalles han cambiado desde su ubicación en el portal de Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="0ec52-116">As part of the convergence with Microsoft 365 Defender, some options and details have changed from their location in the Defender for Identity portal.</span></span> <span data-ttu-id="0ec52-117">Lea los detalles siguientes para descubrir dónde encontrar las características conocidas y las nuevas.</span><span class="sxs-lookup"><span data-stu-id="0ec52-117">Please read the details below to discover where to find both the familiar and new features.</span></span>

## <a name="review-security-alerts"></a><span data-ttu-id="0ec52-118">Revisar alertas de seguridad</span><span class="sxs-lookup"><span data-stu-id="0ec52-118">Review security alerts</span></span>

<span data-ttu-id="0ec52-119">Se puede acceder a las alertas desde varias ubicaciones, incluida la página **Alertas,** la página Incidentes, las páginas de dispositivos **individuales** y desde la **página Búsqueda** avanzada. </span><span class="sxs-lookup"><span data-stu-id="0ec52-119">Alerts can be accessed from multiple locations, including the **Alerts** page, the **Incidents** page, the pages of individual **Devices**, and from the **Advanced hunting** page.</span></span> <span data-ttu-id="0ec52-120">En este ejemplo, revisaremos la página **Alertas**.</span><span class="sxs-lookup"><span data-stu-id="0ec52-120">In this example, we'll review the **Alerts page**.</span></span>

<span data-ttu-id="0ec52-121">En el [Microsoft 365 de seguridad,](https://security.microsoft.com/)vaya a **Incidentes & y,** a continuación, a **Alertas**.</span><span class="sxs-lookup"><span data-stu-id="0ec52-121">In the [Microsoft 365 security center](https://security.microsoft.com/), go to **Incidents & alerts** and then to **Alerts**.</span></span>

![Vaya a Incidentes y alertas y, a continuación, Alertas](../../media/defender-identity/incidents-alerts.png)

<span data-ttu-id="0ec52-123">Para ver alertas de Defender for Identity, en la  parte superior derecha, seleccione **Filtrar** y, a continuación, en Orígenes de servicio, seleccione **Microsoft Defender para Identidad** y **seleccione Aplicar**:</span><span class="sxs-lookup"><span data-stu-id="0ec52-123">To see alerts from Defender for Identity, on the top-right select **Filter**, and then under **Service sources** select **Microsoft Defender for Identity**, and select **Apply**:</span></span>

![Filtrar para eventos de Defender for Identity](../../media/defender-identity/filter-defender-for-identity.png)

<span data-ttu-id="0ec52-125">Las alertas se muestran con información en las siguientes columnas: **Nombre** de alerta **,** **Etiquetas**, Gravedad **,** Estado de investigación , **Estado**, **Categoría** **,** Origen de detección **,** Activos afectados **,** Primera actividad y Última **actividad**.</span><span class="sxs-lookup"><span data-stu-id="0ec52-125">The alerts are displayed with information in the following columns: **Alert name**, **Tags**, **Severity**, **Investigation state**, **Status**, **Category**, **Detection source**, **Impacted assets**, **First activity**, and **Last activity**.</span></span>

![Eventos de Defender for Identity](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a><span data-ttu-id="0ec52-127">Administrar alertas</span><span class="sxs-lookup"><span data-stu-id="0ec52-127">Manage alerts</span></span>

<span data-ttu-id="0ec52-128">Si hace clic en **el nombre de alerta** de una de las alertas, irá a la página con detalles sobre la alerta.</span><span class="sxs-lookup"><span data-stu-id="0ec52-128">If you click the **Alert name** for one of the alerts, you'll go to the page with details about the alert.</span></span> <span data-ttu-id="0ec52-129">En el panel izquierdo, verá un resumen de Lo que **ocurrió**:</span><span class="sxs-lookup"><span data-stu-id="0ec52-129">In the left pane, you'll see a summary of **What happened**:</span></span>

![Lo que ocurrió en alerta](../../media/defender-identity/what-happened.png)

<span data-ttu-id="0ec52-131">Encima del **cuadro Qué sucedió** hay botones para **cuentas,** **host de destino** y host de origen **de** la alerta.</span><span class="sxs-lookup"><span data-stu-id="0ec52-131">Above the **What happened** box are buttons for the **Accounts**, **Destination Host** and **Source Host** of the alert.</span></span> <span data-ttu-id="0ec52-132">Para otras alertas, es posible que vea los botones para obtener información sobre hosts, cuentas, direcciones IP, dominios y grupos de seguridad adicionales.</span><span class="sxs-lookup"><span data-stu-id="0ec52-132">For other alerts, you might see buttons for details about additional hosts, accounts, IP addresses, domains, and security groups.</span></span> <span data-ttu-id="0ec52-133">Seleccione cualquiera de ellos para obtener más detalles sobre las entidades implicadas.</span><span class="sxs-lookup"><span data-stu-id="0ec52-133">Select any of them to get more details about the entities involved.</span></span>

<span data-ttu-id="0ec52-134">En el panel derecho, verá los detalles **de la alerta**.</span><span class="sxs-lookup"><span data-stu-id="0ec52-134">On the right pane, you'll see the **Alert details**.</span></span> <span data-ttu-id="0ec52-135">Aquí puede ver más detalles y realizar varias tareas:</span><span class="sxs-lookup"><span data-stu-id="0ec52-135">Here you can see more details and perform several tasks:</span></span>

- <span data-ttu-id="0ec52-136">**Clasificar esta alerta:** aquí puede designar esta alerta como **alerta True** o **False alert**</span><span class="sxs-lookup"><span data-stu-id="0ec52-136">**Classify this alert** - Here you can designate this alert as a **True alert** or **False alert**</span></span>

    ![Clasificar alerta](../../media/defender-identity/classify-alert.png)

- <span data-ttu-id="0ec52-138">**Estado de alerta:** en **Establecer clasificación,** puede clasificar la alerta como **True** o **False**.</span><span class="sxs-lookup"><span data-stu-id="0ec52-138">**Alert state** - In **Set Classification**, you can classify the alert as **True** or **False**.</span></span> <span data-ttu-id="0ec52-139">En **Asignado a**, puede asignar la alerta a usted mismo o desasignación.</span><span class="sxs-lookup"><span data-stu-id="0ec52-139">In **Assigned to**, you can assign the alert to yourself or unassign it.</span></span>

    ![Estado de alerta](../../media/defender-identity/alert-state.png)

- <span data-ttu-id="0ec52-141">Detalles de **alerta:** en Detalles de **alerta,** puede encontrar más información sobre la alerta específica, seguir un vínculo a la documentación sobre el tipo de alerta, ver a qué incidente está asociada la alerta, revisar las investigaciones automatizadas vinculadas a este tipo de alerta y ver los dispositivos y usuarios afectados.</span><span class="sxs-lookup"><span data-stu-id="0ec52-141">**Alert details** - Under **Alert details**, you can find more information about the specific alert, follow a link to documentation about the type of alert, see which incident the alert is associated with, review any automated investigations linked to this alert type, and see the impacted devices and users.</span></span>

    ![Detalles de la alerta](../../media/defender-identity/alert-details.png)

- <span data-ttu-id="0ec52-143">**Comentarios & historial:** aquí puede agregar sus comentarios a la alerta y ver el historial de todas las acciones asociadas con la alerta.</span><span class="sxs-lookup"><span data-stu-id="0ec52-143">**Comments & history** - Here you can add your comments to the alert, and see the history of all actions associated with the alert.</span></span>

    ![Comentarios e historial](../../media/defender-identity/comments-history.png)

- <span data-ttu-id="0ec52-145">**Administrar alerta:** si selecciona **Administrar alerta,** irá a un panel que le permitirá editar:</span><span class="sxs-lookup"><span data-stu-id="0ec52-145">**Manage alert** - If you select **Manage alert**, you'll go to a pane that will allow you to edit the:</span></span>
  - <span data-ttu-id="0ec52-146">**Estado:** puede elegir **Nuevo**, **Resuelto** o **En curso**.</span><span class="sxs-lookup"><span data-stu-id="0ec52-146">**Status** - You can choose **New**, **Resolved** or **In progress**.</span></span>
  - <span data-ttu-id="0ec52-147">**Clasificación:** puede elegir **Alerta verdadera o** Alerta **falsa.**</span><span class="sxs-lookup"><span data-stu-id="0ec52-147">**Classification** - You can choose **True alert** or **False alert**.</span></span>
  - <span data-ttu-id="0ec52-148">**Comentario:** puede agregar un comentario sobre la alerta.</span><span class="sxs-lookup"><span data-stu-id="0ec52-148">**Comment** - You can add a comment about the alert.</span></span>

    <span data-ttu-id="0ec52-149">Si selecciona los tres puntos junto a Administrar alerta **,** puede consultar a un experto en **amenazas,** Exportar la alerta **a** un archivo Excel o Vincular a **otro incidente**.</span><span class="sxs-lookup"><span data-stu-id="0ec52-149">If you select the three dots next to **Manage alert**, you can **Consult a threat expert**, **Export** the alert to an Excel file, or **Link to another incident**.</span></span>

    ![Administrar alerta](../../media/defender-identity/manage-alert.png)

    > [!NOTE]
    > <span data-ttu-id="0ec52-151">En el Excel, ahora tiene dos vínculos disponibles: Ver en **Microsoft Defender** para identidad y ver **en Microsoft 365 Defender**.</span><span class="sxs-lookup"><span data-stu-id="0ec52-151">In the Excel file, you now have two links available: **View in Microsoft Defender for Identity** and **View in Microsoft 365 Defender**.</span></span> <span data-ttu-id="0ec52-152">Cada vínculo le llevará al portal correspondiente y le proporcionará información sobre la alerta allí.</span><span class="sxs-lookup"><span data-stu-id="0ec52-152">Each link will bring you to the relevant portal, and provide information about the alert there.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ec52-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ec52-153">See also</span></span>

- [<span data-ttu-id="0ec52-154">Investigar alertas en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ec52-154">Investigate alerts in Microsoft 365 Defender</span></span>](../defender/investigate-alerts.md)
