---
title: Simular un ataque de suplantación de identidad con Microsoft defender para Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Los administradores pueden obtener información sobre cómo simular ataques de suplantación de identidad y entrenarles a sus usuarios en la prevención de suplantación de identidad mediante la simulación de ataques en Microsoft defender para Office 365.
ms.openlocfilehash: 3707041067fd76ee9535d0dccf5cdfcb9d74fbd7
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667580"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="7d070-103">Simular un ataque de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="7d070-103">Simulate a phishing attack</span></span>

<span data-ttu-id="7d070-104">El aprendizaje del simulador de ataques en Microsoft defender para Office 365 le permite ejecutar simulaciones benignas de ciberataque en su organización para probar las directivas y prácticas de seguridad, así como entrenar a sus empleados para aumentar su conocimiento y reducir la susceptibilidad a los ataques.</span><span class="sxs-lookup"><span data-stu-id="7d070-104">Attack simulator training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="7d070-105">En este artículo se explica cómo crear un ataque simulado de suplantación de identidad mediante el aprendizaje de simulación de ataques.</span><span class="sxs-lookup"><span data-stu-id="7d070-105">This article walks you through creating  a simulated phishing attack using attack simulator training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="7d070-106">Para iniciar un ataque simulado de suplantación de identidad (phishing), abra el [centro de seguridad de Microsoft 365](https://security.microsoft.com/), vaya a **correo electrónico &** \> el **simulador de ataque** de colaboración y cambie a la pestaña [**simulaciones**](https://security.microsoft.com/attacksimulator?viewid=simulations) .</span><span class="sxs-lookup"><span data-stu-id="7d070-106">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulator**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="7d070-107">En **simulaciones**, seleccione **+ iniciar una simulación**.</span><span class="sxs-lookup"><span data-stu-id="7d070-107">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Iniciar un botón de simulación en el centro de seguridad 365 de Microsoft](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="7d070-109">En cualquier momento durante la creación de la simulación, puede guardar y cerrar para seguir configurando la simulación en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="7d070-109">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="7d070-110">Selección de una técnica de ingeniería social</span><span class="sxs-lookup"><span data-stu-id="7d070-110">Selecting a social engineering technique</span></span>

<span data-ttu-id="7d070-111">Seleccione cuatro técnicas distintas, creados de la [Mitre de ATT&CK® Framework](https://attack.mitre.org/techniques/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="7d070-111">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="7d070-112">Hay diferentes cargas disponibles para distintas técnicas:</span><span class="sxs-lookup"><span data-stu-id="7d070-112">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="7d070-113">La **cosecha de credenciales** intenta recopilar las credenciales poniendo a los usuarios en un sitio web de aspecto conocido con cuadros de entrada para enviar un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="7d070-113">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="7d070-114">Los **datos adjuntos de malware** agregan datos adjuntos malintencionados a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="7d070-114">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="7d070-115">Cuando el usuario abre los datos adjuntos, se ejecuta código arbitrario que ayudará al atacante a poner en peligro el dispositivo del destino.</span><span class="sxs-lookup"><span data-stu-id="7d070-115">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="7d070-116">El **vínculo en datos adjuntos** es un tipo de una implementación híbrida de cosecha de credenciales.</span><span class="sxs-lookup"><span data-stu-id="7d070-116">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="7d070-117">Un atacante inserta una dirección URL en un archivo adjunto de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7d070-117">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="7d070-118">La dirección URL dentro de los datos adjuntos sigue la misma técnica que la cosecha de credenciales.</span><span class="sxs-lookup"><span data-stu-id="7d070-118">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="7d070-119">El **vínculo a malware** ejecutará código arbitrario de un archivo hospedado en un conocido servicio de uso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="7d070-119">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="7d070-120">El mensaje enviado al usuario contendrá un vínculo a este archivo malintencionado.</span><span class="sxs-lookup"><span data-stu-id="7d070-120">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="7d070-121">Abrir el archivo y ayudar al atacante a poner en peligro el dispositivo de destino.</span><span class="sxs-lookup"><span data-stu-id="7d070-121">Opening the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="7d070-122">Al hacer clic en **Ver detalles** en la descripción de cada técnica se mostrará más información y los pasos de simulación para la técnica.</span><span class="sxs-lookup"><span data-stu-id="7d070-122">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Pasos de simulación para la recopilación de credenciales en la simulación de ataques en el centro de seguridad de Microsoft 365](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="7d070-124">Una vez que haya seleccionado la técnica y haya hecho clic en **siguiente**, dé un nombre a su simulación y, opcionalmente, una descripción.</span><span class="sxs-lookup"><span data-stu-id="7d070-124">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="7d070-125">Selección de una carga</span><span class="sxs-lookup"><span data-stu-id="7d070-125">Selecting a payload</span></span>

<span data-ttu-id="7d070-126">A continuación, tendrá que seleccionar una carga del catálogo de carga existente.</span><span class="sxs-lookup"><span data-stu-id="7d070-126">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="7d070-127">Las cargas tienen varios puntos de datos para ayudarle a elegir:</span><span class="sxs-lookup"><span data-stu-id="7d070-127">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="7d070-128">Los **tipos de tasa de clics** tienen en cuenta cuántos usuarios hacen clic en esta carga.</span><span class="sxs-lookup"><span data-stu-id="7d070-128">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="7d070-129">La **tasa de compromiso pronosticada** pronostica el porcentaje de personas que se verán comprometidas con esta carga en función de los datos históricos de la carga en Microsoft defender para Office 365 clientes.</span><span class="sxs-lookup"><span data-stu-id="7d070-129">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="7d070-130">**Simulations lanzadas** cuenta el número de veces que se usó esta carga en otras simulaciones.</span><span class="sxs-lookup"><span data-stu-id="7d070-130">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="7d070-131">La **complejidad**, disponible a través de **filtros**, se calcula en función del número de indicadores dentro de la carga en los que se encuentra un ataque a los objetivos de una pista.</span><span class="sxs-lookup"><span data-stu-id="7d070-131">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="7d070-132">Más indicadores conducen a una complejidad más baja.</span><span class="sxs-lookup"><span data-stu-id="7d070-132">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="7d070-133">**Origen**, disponible a través de **filtros**, indica si la carga se creó en su inquilino o forma parte del catálogo de carga existente (global) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7d070-133">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Carga seleccionada en el centro de seguridad de la simulación de ataques en Microsoft 365 Security Center](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="7d070-135">Seleccione una carga de la lista para ver una vista previa de la carga con información adicional sobre ella.</span><span class="sxs-lookup"><span data-stu-id="7d070-135">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="7d070-136">Si quiere crear su propia carga de carga, lea [crear una carga para la formación de simulación de ataques](attack-simulation-training-payloads.md).</span><span class="sxs-lookup"><span data-stu-id="7d070-136">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="7d070-137">Identificación de audiencia</span><span class="sxs-lookup"><span data-stu-id="7d070-137">Audience targeting</span></span>

<span data-ttu-id="7d070-138">Ahora es el momento de seleccionar la audiencia de esta simulación.</span><span class="sxs-lookup"><span data-stu-id="7d070-138">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="7d070-139">Puede elegir incluir a **todos los usuarios de la organización** o **incluir sólo usuarios y grupos específicos**.</span><span class="sxs-lookup"><span data-stu-id="7d070-139">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="7d070-140">Cuando elige **incluir sólo usuarios y grupos específicos** , puede:</span><span class="sxs-lookup"><span data-stu-id="7d070-140">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="7d070-141">**Agregue usuarios**, lo que le permite aprovechar la búsqueda para su espacio empresarial, así como las capacidades avanzadas de búsqueda y filtrado, como dirigirse a los usuarios que no han sido dirigidos por una simulación en los últimos tres meses.</span><span class="sxs-lookup"><span data-stu-id="7d070-141">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="7d070-142">![Filtrado de usuarios en el centro de seguridad de la simulación de ataques en Microsoft 365 Security Center](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="7d070-142">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="7d070-143">**Importar desde CSV** permite importar un conjunto predefinido de usuarios para esta simulación.</span><span class="sxs-lookup"><span data-stu-id="7d070-143">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="7d070-144">Asignar formación</span><span class="sxs-lookup"><span data-stu-id="7d070-144">Assigning training</span></span>

<span data-ttu-id="7d070-145">Le recomendamos que asigne un entrenamiento para cada simulación, ya que los empleados que vayan a realizar cursos de formación serán menos susceptibles a ataques similares.</span><span class="sxs-lookup"><span data-stu-id="7d070-145">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="7d070-146">Puede elegir entre tener un entrenamiento asignado para usted o seleccionar los módulos y los cursos de formación usted mismo.</span><span class="sxs-lookup"><span data-stu-id="7d070-146">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="7d070-147">Seleccione la **fecha de vencimiento** de la formación para asegurarse de que los empleados finalicen la formación de manera oportuna.</span><span class="sxs-lookup"><span data-stu-id="7d070-147">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="7d070-148">Si decide seleccionar los cursos y los módulos usted mismo, podrá ver el contenido recomendado, así como todos los cursos y módulos disponibles.</span><span class="sxs-lookup"><span data-stu-id="7d070-148">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Adición de formación recomendada en el centro de seguridad de la simulación de ataques en Microsoft 365 Security Center](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="7d070-150">En los pasos siguientes, tendrá que **Agregar formación** si opta por seleccionarla usted mismo y personalizar su página de inicio de formación.</span><span class="sxs-lookup"><span data-stu-id="7d070-150">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="7d070-151">Podrá obtener una vista previa de la página de inicio del aprendizaje, así como cambiar el encabezado y el cuerpo de la misma.</span><span class="sxs-lookup"><span data-stu-id="7d070-151">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="7d070-152">Información de lanzamiento y revisión</span><span class="sxs-lookup"><span data-stu-id="7d070-152">Launch details and review</span></span>

<span data-ttu-id="7d070-153">Ahora que todo está configurado, puede iniciar esta simulación inmediatamente o programarla para una fecha posterior.</span><span class="sxs-lookup"><span data-stu-id="7d070-153">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="7d070-154">También tendrá que elegir cuándo finalizar esta simulación.</span><span class="sxs-lookup"><span data-stu-id="7d070-154">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="7d070-155">Dejaremos de capturar la interacción con esta simulación más allá del tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="7d070-155">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="7d070-156">**Habilite la entrega de zona horaria consciente** de la región para entregar mensajes de ataque simulados a los empleados durante el horario laboral en función de su región.</span><span class="sxs-lookup"><span data-stu-id="7d070-156">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="7d070-157">Una vez que haya terminado, haga clic en **siguiente** y revise los detalles de la simulación.</span><span class="sxs-lookup"><span data-stu-id="7d070-157">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="7d070-158">Haga clic en **Editar** en cualquiera de las partes para volver y cambiar los detalles que deben cambiar.</span><span class="sxs-lookup"><span data-stu-id="7d070-158">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="7d070-159">Una vez hecho, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="7d070-159">Once done, click **Submit**.</span></span>
