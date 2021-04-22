---
title: Conector de Microsoft Defender para endpoint flow
ms.reviewer: ''
description: Use El conector de Microsoft Defender para endpoint flow para automatizar la seguridad y crear un flujo que se desencadenará cada vez que se produzca una nueva alerta en el espacio empresarial.
keywords: flow, api admitidas, api, flujo de Microsoft, consulta, automatización
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
ms.openlocfilehash: 33a7c7b1907ac761dfdde43a70bfb8f515235150
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929304"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a><span data-ttu-id="831e0-104">Microsoft Power Automate (anteriormente Microsoft Flow) y Azure Functions</span><span class="sxs-lookup"><span data-stu-id="831e0-104">Microsoft Power Automate (formerly Microsoft Flow), and Azure Functions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="831e0-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="831e0-105">**Applies to:**</span></span>
- [<span data-ttu-id="831e0-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="831e0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="831e0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="831e0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="831e0-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="831e0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="831e0-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="831e0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="831e0-110">Automatizar los procedimientos de seguridad es un requisito estándar para todos los centros de operaciones de seguridad modernos.</span><span class="sxs-lookup"><span data-stu-id="831e0-110">Automating security procedures is a standard requirement for every modern Security Operations Center.</span></span> <span data-ttu-id="831e0-111">La falta de ciberdelincuntes profesionales obliga a SOC a trabajar de la manera más eficiente y la automatización es una obligación.</span><span class="sxs-lookup"><span data-stu-id="831e0-111">The lack of professional cyber defenders forces SOC to work in the most efficient way and automation is a must.</span></span> <span data-ttu-id="831e0-112">Microsoft Power Automate admite diferentes conectores creados exactamente para ello.</span><span class="sxs-lookup"><span data-stu-id="831e0-112">Microsoft Power Automate supports different connectors that were built exactly for that.</span></span> <span data-ttu-id="831e0-113">Puede crear una automatización de procedimientos de extremo a extremo en unos minutos.</span><span class="sxs-lookup"><span data-stu-id="831e0-113">You can build an end-to-end procedure automation within a few minutes.</span></span>

<span data-ttu-id="831e0-114">La API de Microsoft Defender tiene un conector de flujo oficial con muchas capacidades.</span><span class="sxs-lookup"><span data-stu-id="831e0-114">Microsoft Defender API has an official Flow Connector with many capabilities.</span></span>

![Imagen de las credenciales de edición1](images/api-flow-0.png)

> [!NOTE]
> <span data-ttu-id="831e0-116">Para obtener más información acerca de los requisitos previos de licencias de conectores premium, vea [Licensing for premium connectors](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors).</span><span class="sxs-lookup"><span data-stu-id="831e0-116">For more details about premium connectors licensing prerequisites, see [Licensing for premium connectors](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors).</span></span>


## <a name="usage-example"></a><span data-ttu-id="831e0-117">Ejemplo de uso</span><span class="sxs-lookup"><span data-stu-id="831e0-117">Usage example</span></span>

<span data-ttu-id="831e0-118">En el ejemplo siguiente se muestra cómo crear un flujo que se desencadena cada vez que se produce una nueva alerta en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="831e0-118">The following example demonstrates how to create a Flow that is triggered any time a new Alert occurs on your tenant.</span></span>

1. <span data-ttu-id="831e0-119">Inicie sesión en [Microsoft Power Automate](https://flow.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="831e0-119">Log in to [Microsoft Power Automate](https://flow.microsoft.com).</span></span>

2. <span data-ttu-id="831e0-120">Vaya a **Mis flujos**  >  **Nuevo**  >  **automatizado desde en blanco**.</span><span class="sxs-lookup"><span data-stu-id="831e0-120">Go to **My flows** > **New** > **Automated-from blank**.</span></span>

    ![Imagen de las credenciales de edición2](images/api-flow-1.png)

3. <span data-ttu-id="831e0-122">Elija un nombre para el flujo, busque "Desencadenadores de ATP de Microsoft Defender" como desencadenador y, a continuación, seleccione el nuevo desencadenador de alertas.</span><span class="sxs-lookup"><span data-stu-id="831e0-122">Choose a name for your Flow, search for "Microsoft Defender ATP Triggers" as the trigger, and then select the new Alerts trigger.</span></span>

    ![Imagen de las credenciales de edición3](images/api-flow-2.png)

<span data-ttu-id="831e0-124">Ahora tienes un flujo que se desencadena cada vez que se produce una nueva alerta.</span><span class="sxs-lookup"><span data-stu-id="831e0-124">Now you have a Flow that is triggered every time a new Alert occurs.</span></span>

![Imagen de las credenciales de edición4](images/api-flow-3.png)

<span data-ttu-id="831e0-126">Todo lo que necesita hacer ahora es elegir los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="831e0-126">All you need to do now is choose your next steps.</span></span>
<span data-ttu-id="831e0-127">Por ejemplo, puedes aislar el dispositivo si la gravedad de la alerta es alta y enviar un correo electrónico al respecto.</span><span class="sxs-lookup"><span data-stu-id="831e0-127">For example, you can isolate the device if the Severity of the Alert is High and send an email about it.</span></span>
<span data-ttu-id="831e0-128">El desencadenador de alerta solo proporciona el identificador de alerta y el id. de máquina.</span><span class="sxs-lookup"><span data-stu-id="831e0-128">The Alert trigger provides only the Alert ID and the Machine ID.</span></span> <span data-ttu-id="831e0-129">Puede usar el conector para expandir estas entidades.</span><span class="sxs-lookup"><span data-stu-id="831e0-129">You can use the connector to expand these entities.</span></span>

### <a name="get-the-alert-entity-using-the-connector"></a><span data-ttu-id="831e0-130">Obtener la entidad Alert mediante el conector</span><span class="sxs-lookup"><span data-stu-id="831e0-130">Get the Alert entity using the connector</span></span>

1. <span data-ttu-id="831e0-131">Elija **ATP de Microsoft Defender** para el nuevo paso.</span><span class="sxs-lookup"><span data-stu-id="831e0-131">Choose **Microsoft Defender ATP** for the new step.</span></span>

2. <span data-ttu-id="831e0-132">Choose **Alerts - Get single alert API**.</span><span class="sxs-lookup"><span data-stu-id="831e0-132">Choose **Alerts - Get single alert API**.</span></span>

3. <span data-ttu-id="831e0-133">Establezca el **identificador de alerta** del último paso como **Input**.</span><span class="sxs-lookup"><span data-stu-id="831e0-133">Set the **Alert ID** from the last step as **Input**.</span></span>

    ![Imagen de las credenciales de edición5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a><span data-ttu-id="831e0-135">Aislar el dispositivo si la gravedad de la alerta es alta</span><span class="sxs-lookup"><span data-stu-id="831e0-135">Isolate the device if the Alert's severity is High</span></span>

1. <span data-ttu-id="831e0-136">Agregue **Condition** como un paso nuevo.</span><span class="sxs-lookup"><span data-stu-id="831e0-136">Add **Condition** as a new step.</span></span>

2. <span data-ttu-id="831e0-137">Compruebe si la gravedad de la alerta **es igual a** Alta.</span><span class="sxs-lookup"><span data-stu-id="831e0-137">Check if the Alert severity **is equal to** High.</span></span>

   <span data-ttu-id="831e0-138">Si es así, agrega la **acción Atp de Microsoft Defender:** aislar la acción del equipo con el id. de máquina y un comentario.</span><span class="sxs-lookup"><span data-stu-id="831e0-138">If yes, add the **Microsoft Defender ATP - Isolate machine** action with the Machine ID and a comment.</span></span>

    ![Imagen de las credenciales de edición6](images/api-flow-5.png)

3. <span data-ttu-id="831e0-140">Agregue un nuevo paso para enviar mensajes de correo electrónico sobre la alerta y el aislamiento.</span><span class="sxs-lookup"><span data-stu-id="831e0-140">Add a new step for emailing about the Alert and the Isolation.</span></span> <span data-ttu-id="831e0-141">Hay varios conectores de correo electrónico que son muy fáciles de usar, como Outlook o Gmail.</span><span class="sxs-lookup"><span data-stu-id="831e0-141">There are multiple email connectors that are very easy to use, such as Outlook or Gmail.</span></span>

4. <span data-ttu-id="831e0-142">Guarde el flujo.</span><span class="sxs-lookup"><span data-stu-id="831e0-142">Save your flow.</span></span>

<span data-ttu-id="831e0-143">También puedes crear un **flujo programado que** ejecute consultas de búsqueda avanzada y mucho más.</span><span class="sxs-lookup"><span data-stu-id="831e0-143">You can also create a **scheduled** flow that runs Advanced Hunting queries and much more!</span></span>

## <a name="related-topic"></a><span data-ttu-id="831e0-144">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="831e0-144">Related topic</span></span>
- [<span data-ttu-id="831e0-145">Microsoft Defender para api de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="831e0-145">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
