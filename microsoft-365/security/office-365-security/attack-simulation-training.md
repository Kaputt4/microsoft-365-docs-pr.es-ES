---
title: Simular un ataque de suplantación de identidad con Microsoft Defender para Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden aprender a simular ataques de suplantación de identidad (phishing) y entrenar a sus usuarios en la prevención de suplantación de identidad mediante el aprendizaje de simulación de ataques en Microsoft Defender para Office 365.
ms.technology: mdo
ms.openlocfilehash: 27279f927a15ea94ae84112ffdc23d88ea42d2ff
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207254"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="f7379-103">Simular un ataque de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="f7379-103">Simulate a phishing attack</span></span>

<span data-ttu-id="f7379-104">La formación en simulación de ataques en Microsoft Defender para Office 365 le permite ejecutar simulaciones de ciberataques benignas en su organización para probar sus directivas y prácticas de seguridad, así como entrenar a sus empleados para aumentar su concienciación y disminuir su susceptibilidad a los ataques.</span><span class="sxs-lookup"><span data-stu-id="f7379-104">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="f7379-105">Este artículo le guiará a través de la creación de un ataque de suplantación de identidad simulado mediante el entrenamiento de simulación de ataques.</span><span class="sxs-lookup"><span data-stu-id="f7379-105">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

<span data-ttu-id="f7379-106">Para obtener información de introducción sobre el aprendizaje de simulación de ataques, consulta [Introducción al aprendizaje de simulación de ataques.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="f7379-106">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="f7379-107">Para iniciar un ataque de suplantación de identidad simulada, abra el Centro de seguridad de [Microsoft 365,](https://security.microsoft.com/) **vaya a** Aprendizaje de simulación de ataques de colaboración de correo electrónico & y cambie a la pestaña \>  [**Simulaciones.**](https://security.microsoft.com/attacksimulator?viewid=simulations)</span><span class="sxs-lookup"><span data-stu-id="f7379-107">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulation training**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="f7379-108">En **Simulaciones,** seleccione **+ Iniciar una simulación**.</span><span class="sxs-lookup"><span data-stu-id="f7379-108">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Iniciar un botón de simulación en el Centro de seguridad de Microsoft 365](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="f7379-110">En cualquier momento durante la creación de la simulación, puede guardar y cerrar para continuar configurando la simulación más adelante.</span><span class="sxs-lookup"><span data-stu-id="f7379-110">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="f7379-111">Selección de una técnica de ingeniería social</span><span class="sxs-lookup"><span data-stu-id="f7379-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="f7379-112">Seleccione entre 4 técnicas diferentes, seleccionadas en el marco de trabajo&[MITRE ATT ® CK](https://attack.mitre.org/techniques/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="f7379-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="f7379-113">Hay diferentes cargas disponibles para diferentes técnicas:</span><span class="sxs-lookup"><span data-stu-id="f7379-113">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="f7379-114">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span><span class="sxs-lookup"><span data-stu-id="f7379-114">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="f7379-115">**Los datos adjuntos** de malware agregan datos adjuntos malintencionados a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="f7379-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="f7379-116">Cuando el usuario abre los datos adjuntos, se ejecuta código arbitrario que ayudará al atacante a poner en peligro el dispositivo del destino.</span><span class="sxs-lookup"><span data-stu-id="f7379-116">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="f7379-117">**Vínculo en datos adjuntos** es un tipo de híbrido de recolección de credenciales.</span><span class="sxs-lookup"><span data-stu-id="f7379-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="f7379-118">Un atacante inserta una dirección URL en un archivo adjunto de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f7379-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="f7379-119">La dirección URL dentro de los datos adjuntos sigue la misma técnica que la recolección de credenciales.</span><span class="sxs-lookup"><span data-stu-id="f7379-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="f7379-120">**El vínculo al malware** ejecutará código arbitrario desde un archivo hospedado en un servicio de uso compartido de archivos conocido.</span><span class="sxs-lookup"><span data-stu-id="f7379-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="f7379-121">El mensaje enviado al usuario contendrá un vínculo a este archivo malintencionado.</span><span class="sxs-lookup"><span data-stu-id="f7379-121">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="f7379-122">Abrir el archivo y ayudar al atacante a poner en peligro el dispositivo del destino.</span><span class="sxs-lookup"><span data-stu-id="f7379-122">Opening the file and help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="f7379-123">**La dirección URL de** unidad por es donde la dirección URL malintencionada del mensaje lleva al usuario a un sitio web de aspecto familiar que ejecuta o instala código de forma silenciosa en el dispositivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="f7379-123">**Drive-by URL** is where the malicious URL in the message takes the user to a familiar-looking website that silently runs and/or installs code code on the user's device.</span></span>

> [!TIP]
> <span data-ttu-id="f7379-124">Al hacer clic **en Ver detalles** dentro de la descripción de cada técnica, se mostrará más información y los pasos de simulación de la técnica.</span><span class="sxs-lookup"><span data-stu-id="f7379-124">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Pasos de simulación para la recolección de credenciales dentro de la formación de simulación de ataques en el Centro de seguridad de Microsoft 365](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="f7379-126">Después de seleccionar la técnica y hacer clic en **Siguiente,** asigne a la simulación un nombre y, opcionalmente, una descripción.</span><span class="sxs-lookup"><span data-stu-id="f7379-126">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="f7379-127">Selección de una carga</span><span class="sxs-lookup"><span data-stu-id="f7379-127">Selecting a payload</span></span>

<span data-ttu-id="f7379-128">A continuación, deberá seleccionar una carga del catálogo de carga existente.</span><span class="sxs-lookup"><span data-stu-id="f7379-128">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="f7379-129">Las cargas tienen varios puntos de datos que le ayudarán a elegir:</span><span class="sxs-lookup"><span data-stu-id="f7379-129">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="f7379-130">**La tasa de clics** cuenta cuántas personas han hecho clic en esta carga.</span><span class="sxs-lookup"><span data-stu-id="f7379-130">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="f7379-131">**La tasa de compromiso** predicho predice el porcentaje de personas que se verán comprometidas por esta carga en función de los datos históricos de la carga en Microsoft Defender para clientes de Office 365.</span><span class="sxs-lookup"><span data-stu-id="f7379-131">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="f7379-132">**Las simulaciones iniciadas** cuentan el número de veces que se usó esta carga en otras simulaciones.</span><span class="sxs-lookup"><span data-stu-id="f7379-132">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="f7379-133">**La** complejidad , **disponible** a través de filtros, se calcula en función del número de indicadores dentro de la carga que apunta a que se trata de un ataque.</span><span class="sxs-lookup"><span data-stu-id="f7379-133">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="f7379-134">Más indicadores llevan a una complejidad menor.</span><span class="sxs-lookup"><span data-stu-id="f7379-134">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="f7379-135">**Source**, disponible **a** través de filtros , indica si la carga se creó en el espacio empresarial o forma parte del catálogo de carga preexistnte (global) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f7379-135">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Carga útil seleccionada dentro del aprendizaje de simulación de ataques en el Centro de seguridad de Microsoft 365](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="f7379-137">Seleccione una carga de la lista para ver una vista previa de la carga con información adicional sobre ella.</span><span class="sxs-lookup"><span data-stu-id="f7379-137">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="f7379-138">Si quieres crear tu propia carga, lee crear una [carga para el entrenamiento de simulación de ataque.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="f7379-138">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="f7379-139">Identificación de audiencia</span><span class="sxs-lookup"><span data-stu-id="f7379-139">Audience targeting</span></span>

<span data-ttu-id="f7379-140">Ahora es el momento de seleccionar la audiencia de esta simulación.</span><span class="sxs-lookup"><span data-stu-id="f7379-140">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="f7379-141">Puede elegir incluir todos **los usuarios de la organización** o incluir solo usuarios y grupos **específicos.**</span><span class="sxs-lookup"><span data-stu-id="f7379-141">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="f7379-142">Cuando elige incluir **solo usuarios y** grupos específicos, puede:</span><span class="sxs-lookup"><span data-stu-id="f7379-142">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="f7379-143">**Agregue usuarios**, lo que le permite aprovechar la búsqueda de su espacio empresarial, así como las capacidades avanzadas de búsqueda y filtrado, como dirigirse a usuarios que no han sido dirigidos por una simulación en los últimos 3 meses.</span><span class="sxs-lookup"><span data-stu-id="f7379-143">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="f7379-144">![Filtrado de usuarios en el aprendizaje de simulación de ataques en el Centro de seguridad de Microsoft 365](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="f7379-144">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="f7379-145">**Importar desde CSV** permite importar un conjunto predefinido de usuarios para esta simulación.</span><span class="sxs-lookup"><span data-stu-id="f7379-145">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="f7379-146">Asignar formación</span><span class="sxs-lookup"><span data-stu-id="f7379-146">Assigning training</span></span>

<span data-ttu-id="f7379-147">Se recomienda asignar formación para cada simulación, ya que los empleados que pasan por el aprendizaje son menos propensos a ataques similares.</span><span class="sxs-lookup"><span data-stu-id="f7379-147">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="f7379-148">Puede elegir que se le asigne formación o seleccionar cursos de formación y módulos usted mismo.</span><span class="sxs-lookup"><span data-stu-id="f7379-148">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="f7379-149">Seleccione la **fecha de vencimiento del entrenamiento** para asegurarse de que los empleados finalicen su formación de forma oportuna.</span><span class="sxs-lookup"><span data-stu-id="f7379-149">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="f7379-150">Si elige seleccionar cursos y módulos usted mismo, podrá ver el contenido recomendado, así como todos los cursos y módulos disponibles.</span><span class="sxs-lookup"><span data-stu-id="f7379-150">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Agregar formación recomendada dentro del aprendizaje de simulación de ataques en el Centro de seguridad de Microsoft 365](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="f7379-152">En los pasos siguientes,  tendrás que agregar cursos si optas por seleccionarlo tú mismo y personalizar la página de aterrizaje del entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="f7379-152">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="f7379-153">Podrás obtener una vista previa de la página de aterrizaje del entrenamiento, así como cambiar el encabezado y el cuerpo de la página.</span><span class="sxs-lookup"><span data-stu-id="f7379-153">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="f7379-154">Detalles de inicio y revisión</span><span class="sxs-lookup"><span data-stu-id="f7379-154">Launch details and review</span></span>

<span data-ttu-id="f7379-155">Ahora que todo está configurado, puede iniciar esta simulación inmediatamente o programarla para una fecha posterior.</span><span class="sxs-lookup"><span data-stu-id="f7379-155">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="f7379-156">También tendrá que elegir cuándo finalizar esta simulación.</span><span class="sxs-lookup"><span data-stu-id="f7379-156">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="f7379-157">Dejaremos de capturar la interacción con esta simulación más allá de la hora seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f7379-157">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="f7379-158">**Habilite la entrega de zona horaria consciente de** la región para entregar mensajes de ataque simulados a sus empleados durante sus horas de trabajo en función de su región.</span><span class="sxs-lookup"><span data-stu-id="f7379-158">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="f7379-159">Una vez que haya terminado, haga clic en **Siguiente** y revise los detalles de la simulación.</span><span class="sxs-lookup"><span data-stu-id="f7379-159">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="f7379-160">Haga clic **en Editar** en cualquiera de las partes para volver atrás y cambiar los detalles que necesiten cambiar.</span><span class="sxs-lookup"><span data-stu-id="f7379-160">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="f7379-161">Una vez hecho esto, haga clic **en Enviar**.</span><span class="sxs-lookup"><span data-stu-id="f7379-161">Once done, click **Submit**.</span></span>
