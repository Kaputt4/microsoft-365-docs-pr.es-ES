---
title: Simular un ataque de suplantación de identidad con Microsoft Defender para Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden aprender a simular ataques de suplantación de identidad (phishing) y entrenar a sus usuarios sobre la prevención de suplantación de identidad mediante la formación de simulación de ataques en Microsoft Defender para Office 365.
ms.openlocfilehash: 56ee8b7c11187ee6883bffc9b41961d2783e1ff4
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877157"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="38166-103">Simular un ataque de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="38166-103">Simulate a phishing attack</span></span>

<span data-ttu-id="38166-104">La formación de simulación de ataques en Microsoft Defender para Office 365 le permite ejecutar simulaciones de ciberataques benignos en su organización para probar las directivas y prácticas de seguridad, así como entrenar a sus empleados para aumentar su concienciación y reducir su susceptibilidad a los ataques.</span><span class="sxs-lookup"><span data-stu-id="38166-104">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="38166-105">Este artículo le guiará a través de la creación de un ataque de suplantación de identidad simulado mediante el entrenamiento de simulación de ataques.</span><span class="sxs-lookup"><span data-stu-id="38166-105">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

<span data-ttu-id="38166-106">Para obtener información de introducción sobre el aprendizaje de simulación de ataques, consulta Introducción [al entrenamiento de simulación de ataques.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="38166-106">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="38166-107">Para iniciar un ataque de suplantación de identidad simulado, abra el Centro de seguridad de [Microsoft 365,](https://security.microsoft.com/)vaya a Formación de simulación de ataques de colaboración de correo electrónico & y cambie **a** la pestaña \>  [**Simulaciones.**](https://security.microsoft.com/attacksimulator?viewid=simulations)</span><span class="sxs-lookup"><span data-stu-id="38166-107">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulation training**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="38166-108">En **Simulaciones,** seleccione **+ Iniciar una simulación.**</span><span class="sxs-lookup"><span data-stu-id="38166-108">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Iniciar un botón de simulación en el Centro de seguridad de Microsoft 365](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="38166-110">En cualquier momento durante la creación de la simulación, puede guardar y cerrar para continuar configurando la simulación más adelante.</span><span class="sxs-lookup"><span data-stu-id="38166-110">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="38166-111">Selección de una técnica de ingeniería social</span><span class="sxs-lookup"><span data-stu-id="38166-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="38166-112">Seleccione entre 4 técnicas diferentes, conservadas en el marco de trabajo&[CK ® MITRE ATT.](https://attack.mitre.org/techniques/enterprise/)</span><span class="sxs-lookup"><span data-stu-id="38166-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="38166-113">Hay diferentes cargas disponibles para diferentes técnicas:</span><span class="sxs-lookup"><span data-stu-id="38166-113">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="38166-114">**La recolección de** credenciales intenta recopilar credenciales llevando a los usuarios a un sitio web de aspecto conocido con cuadros de entrada para enviar un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="38166-114">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="38166-115">**Los datos adjuntos** de malware agregan datos adjuntos malintencionados a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="38166-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="38166-116">Cuando el usuario abre los datos adjuntos, se ejecuta código arbitrario que ayudará al atacante a poner en peligro el dispositivo del destino.</span><span class="sxs-lookup"><span data-stu-id="38166-116">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="38166-117">**El vínculo en los datos** adjuntos es un tipo de recolección de credenciales híbrida.</span><span class="sxs-lookup"><span data-stu-id="38166-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="38166-118">Un atacante inserta una dirección URL en un archivo adjunto de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="38166-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="38166-119">La dirección URL dentro de los datos adjuntos sigue la misma técnica que la recolección de credenciales.</span><span class="sxs-lookup"><span data-stu-id="38166-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="38166-120">**El vínculo al malware** ejecutará código arbitrario desde un archivo hospedado en un servicio de uso compartido de archivos conocido.</span><span class="sxs-lookup"><span data-stu-id="38166-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="38166-121">El mensaje enviado al usuario contendrá un vínculo a este archivo malintencionado.</span><span class="sxs-lookup"><span data-stu-id="38166-121">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="38166-122">Abrir el archivo y ayudar al atacante a poner en peligro el dispositivo del destino.</span><span class="sxs-lookup"><span data-stu-id="38166-122">Opening the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="38166-123">Al hacer **clic en Ver detalles** de la descripción de cada técnica, se mostrará más información y los pasos de simulación de la técnica.</span><span class="sxs-lookup"><span data-stu-id="38166-123">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Pasos de simulación para la recolección de credenciales dentro de la formación de simulación de ataques en el Centro de seguridad de Microsoft 365](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="38166-125">Después de seleccionar la técnica y hacer clic **en** Siguiente, asigne a la simulación un nombre y, opcionalmente, una descripción.</span><span class="sxs-lookup"><span data-stu-id="38166-125">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="38166-126">Selección de una carga</span><span class="sxs-lookup"><span data-stu-id="38166-126">Selecting a payload</span></span>

<span data-ttu-id="38166-127">A continuación, tendrás que seleccionar una carga del catálogo de carga ya existente.</span><span class="sxs-lookup"><span data-stu-id="38166-127">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="38166-128">Las cargas de trabajo tienen una serie de puntos de datos que le ayudarán a elegir:</span><span class="sxs-lookup"><span data-stu-id="38166-128">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="38166-129">**La tasa de clics** cuenta cuántas personas han hecho clic en esta carga.</span><span class="sxs-lookup"><span data-stu-id="38166-129">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="38166-130">**La tasa de compromiso** previsto predice el porcentaje de personas que se verán comprometidas por esta carga en función de los datos históricos de la carga en Microsoft Defender para los clientes de Office 365.</span><span class="sxs-lookup"><span data-stu-id="38166-130">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="38166-131">**Las simulaciones iniciadas** cuentan el número de veces que esta carga se usó en otras simulaciones.</span><span class="sxs-lookup"><span data-stu-id="38166-131">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="38166-132">**La** complejidad, disponible **a través de** filtros, se calcula en función del número de indicadores dentro de la carga en la que se dirige la pista en que se trata de un ataque.</span><span class="sxs-lookup"><span data-stu-id="38166-132">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="38166-133">Si hay más indicadores, la complejidad es menor.</span><span class="sxs-lookup"><span data-stu-id="38166-133">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="38166-134">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span><span class="sxs-lookup"><span data-stu-id="38166-134">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Carga seleccionada dentro de la formación de simulación de ataques en el Centro de seguridad de Microsoft 365](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="38166-136">Selecciona una carga de la lista para ver una vista previa de la carga con información adicional sobre ella.</span><span class="sxs-lookup"><span data-stu-id="38166-136">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="38166-137">Si quieres crear tu propia carga, lee crear una carga [para el entrenamiento de simulación de ataques.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="38166-137">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="38166-138">Identificación de audiencia</span><span class="sxs-lookup"><span data-stu-id="38166-138">Audience targeting</span></span>

<span data-ttu-id="38166-139">Ahora es el momento de seleccionar la audiencia de esta simulación.</span><span class="sxs-lookup"><span data-stu-id="38166-139">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="38166-140">Puede elegir incluir todos **los usuarios de su** organización o incluir solo usuarios y grupos **específicos.**</span><span class="sxs-lookup"><span data-stu-id="38166-140">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="38166-141">Si elige incluir **solo usuarios y** grupos específicos, puede:</span><span class="sxs-lookup"><span data-stu-id="38166-141">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="38166-142">**Agregue** usuarios, lo que le permite aprovechar la búsqueda de su espacio empresarial, así como las capacidades avanzadas de búsqueda y filtrado, como dirigirse a usuarios que no han sido objetivo de una simulación en los últimos 3 meses.</span><span class="sxs-lookup"><span data-stu-id="38166-142">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="38166-143">![Filtrado de usuarios en la formación de simulación de ataques en el Centro de seguridad de Microsoft 365](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="38166-143">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="38166-144">**La importación desde CSV** permite importar un conjunto predefinido de usuarios para esta simulación.</span><span class="sxs-lookup"><span data-stu-id="38166-144">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="38166-145">Asignación de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="38166-145">Assigning training</span></span>

<span data-ttu-id="38166-146">Te recomendamos que asignes formación para cada simulación, ya que los empleados que pasan por el entrenamiento son menos susceptibles a ataques similares.</span><span class="sxs-lookup"><span data-stu-id="38166-146">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="38166-147">Puede elegir que se le asigne formación o seleccionar cursos de aprendizaje y módulos usted mismo.</span><span class="sxs-lookup"><span data-stu-id="38166-147">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="38166-148">Seleccione la **fecha de vencimiento del aprendizaje** para asegurarse de que los empleados finalicen su aprendizaje de forma oportuna.</span><span class="sxs-lookup"><span data-stu-id="38166-148">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="38166-149">Si decide seleccionar cursos y módulos usted mismo, podrá ver el contenido recomendado, así como todos los cursos y módulos disponibles.</span><span class="sxs-lookup"><span data-stu-id="38166-149">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Adición de formación recomendada dentro de la formación de simulación de ataques en el Centro de seguridad de Microsoft 365](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="38166-151">En los pasos siguientes,  tendrá que agregar cursos de aprendizaje si optó por seleccionarlo usted mismo y personalizar la página de aterrizaje de la formación.</span><span class="sxs-lookup"><span data-stu-id="38166-151">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="38166-152">Podrás obtener una vista previa de la página de aterrizaje del entrenamiento, así como cambiar el encabezado y el cuerpo de la página.</span><span class="sxs-lookup"><span data-stu-id="38166-152">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="38166-153">Detalles de inicio y revisión</span><span class="sxs-lookup"><span data-stu-id="38166-153">Launch details and review</span></span>

<span data-ttu-id="38166-154">Ahora que todo está configurado, puede iniciar esta simulación inmediatamente o programarla para una fecha posterior.</span><span class="sxs-lookup"><span data-stu-id="38166-154">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="38166-155">También tendrá que elegir cuándo finalizar esta simulación.</span><span class="sxs-lookup"><span data-stu-id="38166-155">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="38166-156">Dejaremos de capturar la interacción con esta simulación más allá de la hora seleccionada.</span><span class="sxs-lookup"><span data-stu-id="38166-156">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="38166-157">**Habilitar la entrega de zona horaria consciente de** la región para entregar mensajes de ataque simulado a los empleados durante sus horas de trabajo en función de su región.</span><span class="sxs-lookup"><span data-stu-id="38166-157">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="38166-158">Una vez que haya terminado, haga clic en **Siguiente** y revise los detalles de la simulación.</span><span class="sxs-lookup"><span data-stu-id="38166-158">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="38166-159">Haga clic **en Editar** en cualquiera de los elementos para volver atrás y cambiar los detalles que necesiten cambiar.</span><span class="sxs-lookup"><span data-stu-id="38166-159">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="38166-160">Una vez hecho esto, haga clic **en Enviar**.</span><span class="sxs-lookup"><span data-stu-id="38166-160">Once done, click **Submit**.</span></span>
