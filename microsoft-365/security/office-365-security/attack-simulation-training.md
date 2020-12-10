---
title: Simule un ataque de suplantación de identidad con Microsoft defender para
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Obtenga información sobre cómo simular ataques de suplantación de identidad y entrenar a los usuarios en la prevención de suplantación de identidad con la formación de simulación de ataques en Microsoft defender para Office 365.
ms.openlocfilehash: 8f5f457f60c81fe961282f33bb8c37f4d9e27aab
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616109"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="26082-103">Simular un ataque de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="26082-103">Simulate a phishing attack</span></span>

<span data-ttu-id="26082-104">El aprendizaje del simulador de ataque a través de Microsoft defender para Office 365 le permite realizar simulaciones de ataque cibernéticos benignas en su organización para probar las directivas y prácticas de seguridad, así como entrenar a los empleados de su organización para aumentar su conciencia y reducir la susceptibilidad a los ataques.</span><span class="sxs-lookup"><span data-stu-id="26082-104">Attack simulator training through Microsoft Defender for Office 365 lets you run benign cyber attack simulations on your organization to test your security policies and practices, as well as train the employees of your organization to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="26082-105">A continuación, se explica cómo simular un ataque de suplantación de identidad mediante el aprendizaje del simulador de ataques.</span><span class="sxs-lookup"><span data-stu-id="26082-105">The following walks you through simulating a phishing attack using attack simulator training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="26082-106">Para iniciar un ataque simulado de suplantación de identidad, navegue al [centro de seguridad de Microsoft 365](https://security.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="26082-106">To launch a simulated phishing attack, navigate to the [Microsoft 365 security center](https://security.microsoft.com/).</span></span> <span data-ttu-id="26082-107">En **correo electrónico & colaboración** , haga clic en **simulador de ataque** y cambie a la pestaña [**simulaciones**](https://security.microsoft.com/attacksimulator?viewid=simulations) .</span><span class="sxs-lookup"><span data-stu-id="26082-107">Under **Email & collaboration** click on **Attack simulator** and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="26082-108">En **simulaciones** , seleccione **+ iniciar una simulación**.</span><span class="sxs-lookup"><span data-stu-id="26082-108">Under **Simulations** select **+ Launch a simulation**.</span></span>

![Iniciar un botón de simulación en el centro de seguridad 365 de Microsoft](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="26082-110">En cualquier momento durante la creación de la simulación, puede guardar y cerrar para seguir configurando la simulación en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="26082-110">At any point during simulation creation you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="26082-111">Selección de una técnica de ingeniería social</span><span class="sxs-lookup"><span data-stu-id="26082-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="26082-112">Seleccione cuatro técnicas distintas, creados de la [Mitre de ATT&CK® Framework](https://attack.mitre.org/techniques/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="26082-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="26082-113">Hay diferentes cargas disponibles para distintas técnicas.</span><span class="sxs-lookup"><span data-stu-id="26082-113">Different payloads are available for different techniques.</span></span>

- <span data-ttu-id="26082-114">La **cosecha de credenciales** intenta recopilar las credenciales de los empleados al llevarlos a un sitio web de aspecto conocido con cuadros de entrada para enviar un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="26082-114">**Credential harvest** attempts to collect credentials from employees by taking them to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="26082-115">Los **datos adjuntos de malware** agregan datos adjuntos malintencionados a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="26082-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="26082-116">Cuando se abre, estos datos adjuntos ejecutarán código arbitrario que ayudará al atacante a poner en peligro el dispositivo de destino.</span><span class="sxs-lookup"><span data-stu-id="26082-116">When opened, this attachment will run some arbitrary code that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="26082-117">El **vínculo en datos adjuntos** es un tipo de una implementación híbrida de cosecha de credenciales.</span><span class="sxs-lookup"><span data-stu-id="26082-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="26082-118">Un atacante inserta una dirección URL en un archivo adjunto de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="26082-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="26082-119">La dirección URL dentro de los datos adjuntos sigue la misma técnica que la cosecha de credenciales.</span><span class="sxs-lookup"><span data-stu-id="26082-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="26082-120">**Vínculo a malware** ejecutará código arbitrario de un archivo hospedado en un sitio de uso compartido de archivos conocido.</span><span class="sxs-lookup"><span data-stu-id="26082-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file-sharing site.</span></span> <span data-ttu-id="26082-121">Se agrega un vínculo a este archivo malintencionado en el mensaje que se envía al destino y se hace clic en él para ejecutar el archivo y ayudar al atacante a poner en peligro el dispositivo del destino.</span><span class="sxs-lookup"><span data-stu-id="26082-121">A link to this malicious file is added to the message sent to the target and clicking it will run the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="26082-122">Al hacer clic en **Ver detalles** en la descripción de cada técnica se mostrará más información sobre la técnica, así como los pasos de simulación para dicha técnica.</span><span class="sxs-lookup"><span data-stu-id="26082-122">Clicking on **View details** within the description of each technique will display further information about the technique as well as the simulation steps for that technique.</span></span>
>
> ![Pasos de simulación para la recopilación de credenciales en la simulación de ataques en el centro de seguridad de Microsoft 365](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="26082-124">Una vez que haya seleccionado la técnica y haga clic en el **siguiente** , asigne un nombre a su simulación y, opcionalmente, una descripción.</span><span class="sxs-lookup"><span data-stu-id="26082-124">Once you've selected the technique and clicked on **Next** give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="26082-125">Selección de una carga</span><span class="sxs-lookup"><span data-stu-id="26082-125">Selecting a payload</span></span>

<span data-ttu-id="26082-126">A continuación, tendrá que seleccionar una carga del catálogo de carga existente.</span><span class="sxs-lookup"><span data-stu-id="26082-126">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="26082-127">Las cargas tienen varios puntos de datos para ayudarle a elegir:</span><span class="sxs-lookup"><span data-stu-id="26082-127">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="26082-128">Los **tipos de tasa de clics** tienen en cuenta cuántos usuarios hacen clic en esta carga.</span><span class="sxs-lookup"><span data-stu-id="26082-128">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="26082-129">La **tasa de compromiso pronosticada predice** el porcentaje de personas que se verán comprometidas con esta carga según los datos históricos de esta carga en Microsoft defender para Office 365 clientes.</span><span class="sxs-lookup"><span data-stu-id="26082-129">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historic data for this payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="26082-130">**Simulations lanzadas** cuenta el número de veces que se usó esta carga en otras simulaciones.</span><span class="sxs-lookup"><span data-stu-id="26082-130">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="26082-131">La **complejidad**, disponible a través de **filtros**, se calcula en función del número de indicadores dentro de la carga en los que se encuentra un ataque a los objetivos de una pista.</span><span class="sxs-lookup"><span data-stu-id="26082-131">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="26082-132">Más indicadores conducen a una complejidad más baja.</span><span class="sxs-lookup"><span data-stu-id="26082-132">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="26082-133">**Origen**, disponible a través de **filtros**, indica si la carga se creó en su inquilino o forma parte del catálogo de carga existente (global) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="26082-133">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Carga seleccionada en el centro de seguridad de la simulación de ataques en Microsoft 365 Security Center](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="26082-135">Seleccione una carga de la lista para ver una vista previa de la carga con información adicional sobre ella.</span><span class="sxs-lookup"><span data-stu-id="26082-135">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="26082-136">Si quiere crear su propia carga de carga, lea [crear una carga para la formación de simulación de ataques](attack-simulation-training-payloads.md).</span><span class="sxs-lookup"><span data-stu-id="26082-136">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="26082-137">Identificación de audiencia</span><span class="sxs-lookup"><span data-stu-id="26082-137">Audience targeting</span></span>

<span data-ttu-id="26082-138">Ahora es el momento de seleccionar la audiencia de esta simulación.</span><span class="sxs-lookup"><span data-stu-id="26082-138">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="26082-139">Puede elegir incluir a **todos los usuarios de la organización** o **incluir sólo usuarios y grupos específicos**.</span><span class="sxs-lookup"><span data-stu-id="26082-139">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="26082-140">Cuando elige **incluir sólo usuarios y grupos específicos** , puede:</span><span class="sxs-lookup"><span data-stu-id="26082-140">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="26082-141">**Agregue usuarios**, lo que le permite aprovechar la búsqueda para su espacio empresarial, así como las capacidades avanzadas de búsqueda y filtrado, como dirigirse a los usuarios que no han sido dirigidos por una simulación en los últimos tres meses.</span><span class="sxs-lookup"><span data-stu-id="26082-141">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="26082-142">![Filtrado de usuarios en el centro de seguridad de la simulación de ataques en Microsoft 365 Security Center](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="26082-142">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="26082-143">**Importar desde CSV** permite importar un conjunto predefinido de usuarios para esta simulación.</span><span class="sxs-lookup"><span data-stu-id="26082-143">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="26082-144">Asignar formación</span><span class="sxs-lookup"><span data-stu-id="26082-144">Assigning training</span></span>

<span data-ttu-id="26082-145">Le recomendamos que asigne un entrenamiento para cada simulación, ya que los empleados que vayan a realizar cursos de formación serán menos susceptibles a ataques similares.</span><span class="sxs-lookup"><span data-stu-id="26082-145">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="26082-146">Puede elegir entre tener un entrenamiento asignado para usted o seleccionar los módulos y los cursos de formación usted mismo.</span><span class="sxs-lookup"><span data-stu-id="26082-146">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="26082-147">Seleccione la **fecha de vencimiento** de la formación para asegurarse de que los empleados finalicen la formación de manera oportuna.</span><span class="sxs-lookup"><span data-stu-id="26082-147">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="26082-148">Si decide seleccionar los cursos y los módulos usted mismo, podrá ver el contenido recomendado, así como todos los cursos y módulos disponibles.</span><span class="sxs-lookup"><span data-stu-id="26082-148">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Adición de formación recomendada en el centro de seguridad de la simulación de ataques en Microsoft 365 Security Center](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="26082-150">En los pasos siguientes, tendrá que **Agregar formación** si opta por seleccionarla usted mismo y personalizar su página de inicio de formación.</span><span class="sxs-lookup"><span data-stu-id="26082-150">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="26082-151">Podrá obtener una vista previa de la página de inicio del aprendizaje, así como cambiar el encabezado y el cuerpo de la misma.</span><span class="sxs-lookup"><span data-stu-id="26082-151">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="26082-152">Información de lanzamiento y revisión</span><span class="sxs-lookup"><span data-stu-id="26082-152">Launch details and review</span></span>

<span data-ttu-id="26082-153">Ahora que todo está configurado, puede iniciar esta simulación inmediatamente o programarla para una fecha posterior.</span><span class="sxs-lookup"><span data-stu-id="26082-153">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="26082-154">También tendrá que elegir cuándo finalizar esta simulación.</span><span class="sxs-lookup"><span data-stu-id="26082-154">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="26082-155">Dejaremos de capturar la interacción con esta simulación más allá del tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="26082-155">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="26082-156">**Habilite la entrega de zona horaria consciente** de la región para entregar mensajes de ataque simulados a los empleados durante el horario laboral en función de su región.</span><span class="sxs-lookup"><span data-stu-id="26082-156">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="26082-157">Una vez que haya terminado, haga clic en **siguiente** y revise los detalles de la simulación.</span><span class="sxs-lookup"><span data-stu-id="26082-157">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="26082-158">Haga clic en **Editar** en cualquiera de las partes para volver y cambiar los detalles que deben cambiar.</span><span class="sxs-lookup"><span data-stu-id="26082-158">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="26082-159">Una vez hecho, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="26082-159">Once done, click **Submit**.</span></span>
