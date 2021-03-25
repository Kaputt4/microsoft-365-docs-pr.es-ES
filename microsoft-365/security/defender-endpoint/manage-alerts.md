---
title: Administrar alertas de Microsoft Defender para puntos de conexión
description: Cambie el estado de las alertas, cree reglas de supresión para ocultar alertas, enviar comentarios y revisar el historial de cambios de alertas individuales con el menú Administrar alerta.
keywords: administrar alertas, administrar, alertas, estado, nuevo, en curso, resuelto, resolver alertas, suprimir, supresión, reglas, contexto, historial, comentarios, cambios
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: f03c2209b369e6fb9e001452c53073daeb5fe1c6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187006"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a><span data-ttu-id="790ca-104">Administrar alertas de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="790ca-104">Manage Microsoft Defender for Endpoint alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="790ca-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="790ca-105">**Applies to:**</span></span>
- [<span data-ttu-id="790ca-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="790ca-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="790ca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="790ca-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="790ca-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="790ca-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="790ca-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="790ca-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="790ca-110">Defender for Endpoint le notifica posibles eventos malintencionados, atributos e información contextual a través de alertas.</span><span class="sxs-lookup"><span data-stu-id="790ca-110">Defender for Endpoint notifies you of possible malicious events, attributes, and contextual information through alerts.</span></span> <span data-ttu-id="790ca-111">En el panel de operaciones de seguridad se muestra un resumen de las alertas nuevas y se puede obtener acceso a todas las alertas de la cola **De alertas.**</span><span class="sxs-lookup"><span data-stu-id="790ca-111">A summary of new alerts is displayed in the **Security operations dashboard**, and you can access all alerts in the **Alerts queue**.</span></span>

<span data-ttu-id="790ca-112">Puedes administrar alertas seleccionando una alerta en  la cola de alertas **o** en la pestaña Alertas de la página Dispositivo de un dispositivo individual.</span><span class="sxs-lookup"><span data-stu-id="790ca-112">You can manage alerts by selecting an alert in the **Alerts queue**, or the **Alerts** tab of the Device page for an individual device.</span></span>

<span data-ttu-id="790ca-113">Al seleccionar una alerta en cualquiera de esos lugares, se muestra el panel **de administración de alertas**.</span><span class="sxs-lookup"><span data-stu-id="790ca-113">Selecting an alert in either of those places brings up the **Alert management pane**.</span></span>

![Imagen del panel de administración de alertas y la cola de alertas](images/atp-alerts-selected.png)

## <a name="link-to-another-incident"></a><span data-ttu-id="790ca-115">Vincular a otro incidente</span><span class="sxs-lookup"><span data-stu-id="790ca-115">Link to another incident</span></span>
<span data-ttu-id="790ca-116">Puede crear un nuevo incidente a partir de la alerta o vínculo a un incidente existente.</span><span class="sxs-lookup"><span data-stu-id="790ca-116">You can create a new incident from the alert or link to an existing incident.</span></span> 

## <a name="assign-alerts"></a><span data-ttu-id="790ca-117">Asignar alertas</span><span class="sxs-lookup"><span data-stu-id="790ca-117">Assign alerts</span></span>
<span data-ttu-id="790ca-118">Si aún no se ha asignado una alerta, puedes seleccionar **Asignarme** para asignarte la alerta.</span><span class="sxs-lookup"><span data-stu-id="790ca-118">If an alert is not yet assigned, you can select **Assign to me** to assign the alert to yourself.</span></span>


## <a name="suppress-alerts"></a><span data-ttu-id="790ca-119">Suprimir alertas</span><span class="sxs-lookup"><span data-stu-id="790ca-119">Suppress alerts</span></span>
<span data-ttu-id="790ca-120">Es posible que haya escenarios en los que necesite suprimir las alertas para que no aparezcan en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="790ca-120">There might be scenarios where you need to suppress alerts from appearing in Microsoft Defender Security Center.</span></span> <span data-ttu-id="790ca-121">Defender for Endpoint te permite crear reglas de supresión para alertas específicas que se sabe que son inocuas, como herramientas o procesos conocidos de la organización.</span><span class="sxs-lookup"><span data-stu-id="790ca-121">Defender for Endpoint lets you create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span>

<span data-ttu-id="790ca-122">Las reglas de supresión se pueden crear a partir de una alerta existente.</span><span class="sxs-lookup"><span data-stu-id="790ca-122">Suppression rules can be created from an existing alert.</span></span> <span data-ttu-id="790ca-123">Se pueden deshabilitar y volver a habilitar si es necesario.</span><span class="sxs-lookup"><span data-stu-id="790ca-123">They can be disabled and reenabled if needed.</span></span>

<span data-ttu-id="790ca-124">Cuando se crea una regla de supresión, tendrá efecto desde el punto en que se crea la regla.</span><span class="sxs-lookup"><span data-stu-id="790ca-124">When a suppression rule is created, it will take effect from the point when the rule is created.</span></span> <span data-ttu-id="790ca-125">La regla no afectará a las alertas existentes ya en la cola, antes de la creación de la regla.</span><span class="sxs-lookup"><span data-stu-id="790ca-125">The rule will not affect existing alerts already in the queue, prior to the rule creation.</span></span> <span data-ttu-id="790ca-126">La regla solo se aplicará en alertas que cumplan las condiciones establecidas después de crear la regla.</span><span class="sxs-lookup"><span data-stu-id="790ca-126">The rule will only be applied on alerts that satisfy the conditions set after the rule is created.</span></span>

<span data-ttu-id="790ca-127">Hay dos contextos para una regla de supresión entre las que puede elegir:</span><span class="sxs-lookup"><span data-stu-id="790ca-127">There are two contexts for a suppression rule that you can choose from:</span></span>

- <span data-ttu-id="790ca-128">**Suprimir alerta en este dispositivo**</span><span class="sxs-lookup"><span data-stu-id="790ca-128">**Suppress alert on this device**</span></span>
- <span data-ttu-id="790ca-129">**Suprimir alerta en mi organización**</span><span class="sxs-lookup"><span data-stu-id="790ca-129">**Suppress alert in my organization**</span></span>

<span data-ttu-id="790ca-130">El contexto de la regla te permite adaptar lo que se ve en el portal y asegurarte de que solo se desencien alertas de seguridad reales en el portal.</span><span class="sxs-lookup"><span data-stu-id="790ca-130">The context of the rule lets you tailor what gets surfaced into the portal and ensure that only real security alerts are surfaced into the portal.</span></span>

<span data-ttu-id="790ca-131">Puede usar los ejemplos de la tabla siguiente para ayudarle a elegir el contexto de una regla de supresión:</span><span class="sxs-lookup"><span data-stu-id="790ca-131">You can use the examples in the following table to help you choose the context for a suppression rule:</span></span>

| <span data-ttu-id="790ca-132">**Context**</span><span class="sxs-lookup"><span data-stu-id="790ca-132">**Context**</span></span>                           | <span data-ttu-id="790ca-133">**Definición**</span><span class="sxs-lookup"><span data-stu-id="790ca-133">**Definition**</span></span>                                                                                                                                              | <span data-ttu-id="790ca-134">**Escenarios de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="790ca-134">**Example scenarios**</span></span>                                                                                                                                                                                                  |
|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="790ca-135">**Suprimir alerta en este dispositivo**</span><span class="sxs-lookup"><span data-stu-id="790ca-135">**Suppress alert on this device**</span></span>    | <span data-ttu-id="790ca-136">Las alertas con el mismo título de alerta y en ese dispositivo específico solo se suprimirán.</span><span class="sxs-lookup"><span data-stu-id="790ca-136">Alerts with the same alert title and on that specific device only will be suppressed.</span></span> <br /><br /><span data-ttu-id="790ca-137">El resto de alertas de ese dispositivo no se suprimirán.</span><span class="sxs-lookup"><span data-stu-id="790ca-137">All other alerts on that device will not be suppressed.</span></span> | <ul><li><span data-ttu-id="790ca-138">Un investigador de seguridad está investigando un script malintencionado que se ha usado para atacar otros dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="790ca-138">A security researcher is investigating a malicious script that has been used to attack other devices in your organization.</span></span></li><li><span data-ttu-id="790ca-139">Un desarrollador crea regularmente scripts de PowerShell para su equipo.</span><span class="sxs-lookup"><span data-stu-id="790ca-139">A developer regularly creates PowerShell scripts for their team.</span></span></li></ul> |
| <span data-ttu-id="790ca-140">**Suprimir alerta en mi organización**</span><span class="sxs-lookup"><span data-stu-id="790ca-140">**Suppress alert in my organization**</span></span> | <span data-ttu-id="790ca-141">Las alertas con el mismo título de alerta en cualquier dispositivo se suprimirán.</span><span class="sxs-lookup"><span data-stu-id="790ca-141">Alerts with the same alert title on any device will be suppressed.</span></span>                                                                                         | <ul><li><span data-ttu-id="790ca-142">Todos los usuarios de la organización usan una herramienta administrativa benigna.</span><span class="sxs-lookup"><span data-stu-id="790ca-142">A benign administrative tool is used by everyone in your organization.</span></span></li></ul>                                                                                                                               |

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a><span data-ttu-id="790ca-143">Suprimir una alerta y crear una nueva regla de supresión:</span><span class="sxs-lookup"><span data-stu-id="790ca-143">Suppress an alert and create a new suppression rule:</span></span>
<span data-ttu-id="790ca-144">Cree reglas personalizadas para controlar cuándo se suprimen o resuelven las alertas.</span><span class="sxs-lookup"><span data-stu-id="790ca-144">Create custom rules to control when alerts are suppressed, or resolved.</span></span> <span data-ttu-id="790ca-145">Puede controlar el contexto para cuando se suprime una alerta especificando el título de la alerta, el indicador de compromiso y las condiciones.</span><span class="sxs-lookup"><span data-stu-id="790ca-145">You can control the context for when an alert is suppressed by specifying the alert title, Indicator of compromise, and the conditions.</span></span> <span data-ttu-id="790ca-146">Después de especificar el contexto, podrá configurar la acción y el ámbito en la alerta.</span><span class="sxs-lookup"><span data-stu-id="790ca-146">After specifying the context, you’ll be able to configure the action and scope on the alert.</span></span> 

1. <span data-ttu-id="790ca-147">Seleccione la alerta que desea suprimir.</span><span class="sxs-lookup"><span data-stu-id="790ca-147">Select the alert you'd like to suppress.</span></span> <span data-ttu-id="790ca-148">Esto muestra el panel **administración de alertas.**</span><span class="sxs-lookup"><span data-stu-id="790ca-148">This brings up the **Alert management** pane.</span></span>

2.  <span data-ttu-id="790ca-149">Seleccione **Crear una regla de supresión**.</span><span class="sxs-lookup"><span data-stu-id="790ca-149">Select **Create a suppression rule**.</span></span>

    <span data-ttu-id="790ca-150">Puede crear una condición de supresión con estos atributos.</span><span class="sxs-lookup"><span data-stu-id="790ca-150">You can create a suppression condition using these attributes.</span></span> <span data-ttu-id="790ca-151">Se aplica un operador AND entre cada condición, por lo que la supresión se produce solo si se cumplen todas las condiciones.</span><span class="sxs-lookup"><span data-stu-id="790ca-151">An AND operator is applied between each condition, so suppression occurs only if all conditions are met.</span></span>
    
    * <span data-ttu-id="790ca-152">Archivo SHA1</span><span class="sxs-lookup"><span data-stu-id="790ca-152">File SHA1</span></span>
    * <span data-ttu-id="790ca-153">Nombre de archivo: comodín admitido</span><span class="sxs-lookup"><span data-stu-id="790ca-153">File name - wildcard supported</span></span>
    * <span data-ttu-id="790ca-154">Ruta de acceso de carpeta: comodín compatible</span><span class="sxs-lookup"><span data-stu-id="790ca-154">Folder path - wildcard supported</span></span>
    * <span data-ttu-id="790ca-155">Dirección IP</span><span class="sxs-lookup"><span data-stu-id="790ca-155">IP address</span></span>
    * <span data-ttu-id="790ca-156">DIRECCIÓN URL: comodín compatible</span><span class="sxs-lookup"><span data-stu-id="790ca-156">URL - wildcard supported</span></span>
    * <span data-ttu-id="790ca-157">Línea de comandos: comodín compatible</span><span class="sxs-lookup"><span data-stu-id="790ca-157">Command line - wildcard supported</span></span>

3. <span data-ttu-id="790ca-158">Seleccione el **IOC desencadenante**.</span><span class="sxs-lookup"><span data-stu-id="790ca-158">Select the **Triggering IOC**.</span></span>
    
4. <span data-ttu-id="790ca-159">Especifique la acción y el ámbito en la alerta.</span><span class="sxs-lookup"><span data-stu-id="790ca-159">Specify the action and scope on the alert.</span></span> <br>
   <span data-ttu-id="790ca-160">Puede resolver automáticamente una alerta u ocultarla del portal.</span><span class="sxs-lookup"><span data-stu-id="790ca-160">You can automatically resolve an alert or hide it from the portal.</span></span> <span data-ttu-id="790ca-161">Las alertas que se resuelven automáticamente aparecerán en la sección resuelta de la cola de alertas, la página de alertas y la escala de tiempo del dispositivo y aparecerán como resueltas en Defender para las API de extremo.</span><span class="sxs-lookup"><span data-stu-id="790ca-161">Alerts that are automatically resolved will appear in the resolved section of the alerts queue, alert page, and device timeline and will appear as resolved across Defender for Endpoint APIs.</span></span> <br><br> <span data-ttu-id="790ca-162">Las alertas marcadas como ocultas se suprimirán de todo el sistema, tanto en las alertas asociadas del dispositivo como desde el panel y no se transmitirán a través de las API de Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="790ca-162">Alerts that are marked as hidden will be suppressed from the entire system, both on the device's associated alerts and from the dashboard and will not be streamed across Defender for Endpoint APIs.</span></span>


5. <span data-ttu-id="790ca-163">Escriba un nombre de regla y un comentario.</span><span class="sxs-lookup"><span data-stu-id="790ca-163">Enter a rule name and a comment.</span></span>

6. <span data-ttu-id="790ca-164">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="790ca-164">Click **Save**.</span></span>

#### <a name="view-the-list-of-suppression-rules"></a><span data-ttu-id="790ca-165">Ver la lista de reglas de supresión</span><span class="sxs-lookup"><span data-stu-id="790ca-165">View the list of suppression rules</span></span>

1. <span data-ttu-id="790ca-166">En el panel de navegación, seleccione **Configuración**  >  **supresión de alertas**.</span><span class="sxs-lookup"><span data-stu-id="790ca-166">In the navigation pane, select **Settings** > **Alert suppression**.</span></span>

2. <span data-ttu-id="790ca-167">La lista de reglas de supresión muestra todas las reglas que los usuarios de la organización han creado.</span><span class="sxs-lookup"><span data-stu-id="790ca-167">The list of suppression rules shows all the rules that users in your organization have created.</span></span>

<span data-ttu-id="790ca-168">Para obtener más información sobre la administración de reglas de supresión, vea [Administrar reglas de supresión](manage-suppression-rules.md)</span><span class="sxs-lookup"><span data-stu-id="790ca-168">For more information on managing suppression rules, see [Manage suppression rules](manage-suppression-rules.md)</span></span>

## <a name="change-the-status-of-an-alert"></a><span data-ttu-id="790ca-169">Cambiar el estado de una alerta</span><span class="sxs-lookup"><span data-stu-id="790ca-169">Change the status of an alert</span></span>

<span data-ttu-id="790ca-170">Puede clasificar las alertas (como **Nuevo**, **En curso** o **Resuelto)** cambiando su estado a medida que avanza la investigación.</span><span class="sxs-lookup"><span data-stu-id="790ca-170">You can categorize alerts (as **New**, **In Progress**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="790ca-171">Esto te ayuda a organizar y administrar cómo tu equipo puede responder a las alertas.</span><span class="sxs-lookup"><span data-stu-id="790ca-171">This helps you organize and manage how your team can respond to alerts.</span></span>

<span data-ttu-id="790ca-172">Por ejemplo, un jefe de equipo puede revisar todas las **alertas** Nuevas y decidir asignarlas a la cola **En** curso para un análisis posterior.</span><span class="sxs-lookup"><span data-stu-id="790ca-172">For example, a team leader can review all **New** alerts, and decide to assign them to the **In Progress** queue for further analysis.</span></span>

<span data-ttu-id="790ca-173">Como alternativa, el jefe de equipo  puede asignar la alerta a la cola Resuelto si sabe que la alerta es benigna, procedente de un dispositivo que es irrelevante (por ejemplo, uno que pertenece a un administrador de seguridad) o que se trata a través de una alerta anterior.</span><span class="sxs-lookup"><span data-stu-id="790ca-173">Alternatively, the team leader might assign the alert to the **Resolved** queue if they know the alert is benign, coming from a device that is irrelevant (such as one belonging to a security administrator), or is being dealt with through an earlier alert.</span></span>



## <a name="alert-classification"></a><span data-ttu-id="790ca-174">Clasificación de alertas</span><span class="sxs-lookup"><span data-stu-id="790ca-174">Alert classification</span></span>
<span data-ttu-id="790ca-175">Puede elegir no establecer una clasificación o especificar si una alerta es una alerta verdadera o una alerta falsa.</span><span class="sxs-lookup"><span data-stu-id="790ca-175">You can choose not to set a classification, or specify whether an alert is a true alert or a false alert.</span></span> <span data-ttu-id="790ca-176">Es importante proporcionar la clasificación de verdadero positivo/falso positivo.</span><span class="sxs-lookup"><span data-stu-id="790ca-176">It's important to provide the classification of true positive/false positive.</span></span> <span data-ttu-id="790ca-177">Esta clasificación se usa para supervisar la calidad de las alertas y hacer que las alertas sea más precisa.</span><span class="sxs-lookup"><span data-stu-id="790ca-177">This classification is used to monitor alert quality, and make alerts more accurate.</span></span> <span data-ttu-id="790ca-178">El campo "determinación" define fidelidad adicional para una clasificación "verdadero positivo".</span><span class="sxs-lookup"><span data-stu-id="790ca-178">The "determination" field defines additional fidelity for a "true positive" classification.</span></span> 

## <a name="add-comments-and-view-the-history-of-an-alert"></a><span data-ttu-id="790ca-179">Agregar comentarios y ver el historial de una alerta</span><span class="sxs-lookup"><span data-stu-id="790ca-179">Add comments and view the history of an alert</span></span>
<span data-ttu-id="790ca-180">Puede agregar comentarios y ver eventos históricos sobre una alerta para ver los cambios anteriores realizados en la alerta.</span><span class="sxs-lookup"><span data-stu-id="790ca-180">You can add comments and view historical events about an alert to see previous changes made to the alert.</span></span>

<span data-ttu-id="790ca-181">Cada vez que se realiza un cambio o comentario en una alerta, se registra en la **sección Comentarios e** historial.</span><span class="sxs-lookup"><span data-stu-id="790ca-181">Whenever a change or comment is made to an alert, it is recorded in the **Comments and history** section.</span></span>

<span data-ttu-id="790ca-182">Los comentarios agregados aparecen al instante en el panel.</span><span class="sxs-lookup"><span data-stu-id="790ca-182">Added comments instantly appear on the pane.</span></span>


## <a name="related-topics"></a><span data-ttu-id="790ca-183">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="790ca-183">Related topics</span></span>
- [<span data-ttu-id="790ca-184">Administrar reglas de supresión</span><span class="sxs-lookup"><span data-stu-id="790ca-184">Manage suppression rules</span></span>](manage-suppression-rules.md)
- [<span data-ttu-id="790ca-185">Ver y organizar la cola de Alertas de punto de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="790ca-185">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="790ca-186">Investigar alertas de punto de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="790ca-186">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="790ca-187">Investigar un archivo asociado a una alerta de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="790ca-187">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="790ca-188">Investigar dispositivos en la lista Microsoft Defender para dispositivos de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="790ca-188">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="790ca-189">Investigar una dirección IP asociada a una alerta de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="790ca-189">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="790ca-190">Investigar un dominio asociado a una alerta de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="790ca-190">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="790ca-191">Investigar una cuenta de usuario en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="790ca-191">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
