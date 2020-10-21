---
title: Crear un aviso de suspensión legal
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use la herramienta de comunicaciones en un caso avanzado de eDiscovery para enviar, recopilar y realizar un seguimiento de las notificaciones de retención legal.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 730b60c4d57f8fecb0e66f460942e9e890732c2c
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626183"
---
# <a name="create-a-legal-hold-notice"></a><span data-ttu-id="7f304-103">Crear un aviso de suspensión legal</span><span class="sxs-lookup"><span data-stu-id="7f304-103">Create a legal hold notice</span></span>

<span data-ttu-id="7f304-104">Mediante el uso de comunicaciones de custodios avanzadas de eDiscovery, las organizaciones pueden administrar su flujo de trabajo para comunicarse con los custodios.</span><span class="sxs-lookup"><span data-stu-id="7f304-104">Using Advanced eDiscovery custodian communications, organizations can manage their workflow around communicating with custodians.</span></span> <span data-ttu-id="7f304-105">Mediante la herramienta de comunicaciones, los equipos legales pueden enviar, recopilar y realizar un seguimiento sistemático de las notificaciones de retención legal.</span><span class="sxs-lookup"><span data-stu-id="7f304-105">Through the Communications tool, legal teams can systematically send, collect, and track legal hold notifications.</span></span> <span data-ttu-id="7f304-106">El proceso de creación flexible también permite a Microsoft Teams personalizar el flujo de trabajo de notificaciones de retención y el contenido de los avisos que se envían a los custodios.</span><span class="sxs-lookup"><span data-stu-id="7f304-106">The flexible creation process also allows teams to customize the hold notification workflow and the content in the notices sent to custodians.</span></span> 

![Página de comunicaciones](../media/CommunicationPage.PNG)

<span data-ttu-id="7f304-108">En el artículo se describen los pasos del flujo de trabajo de la notificación de retención.</span><span class="sxs-lookup"><span data-stu-id="7f304-108">The article outlines the steps in the hold notification workflow.</span></span>

## <a name="step-1-specify-communication-details"></a><span data-ttu-id="7f304-109">Paso 1: especificar detalles de comunicación</span><span class="sxs-lookup"><span data-stu-id="7f304-109">Step 1: Specify communication details</span></span>

<span data-ttu-id="7f304-110">El primer paso es especificar los detalles adecuados para los avisos de suspensión legal u otras comunicaciones de custodios.</span><span class="sxs-lookup"><span data-stu-id="7f304-110">The first step is to specify the appropriate details for legal hold notices or other custodian communications.</span></span>

![Página de comunicación de nombres](../media/NameCommunication.PNG)

1. <span data-ttu-id="7f304-112">En el centro de seguridad & cumplimiento, vaya a **ediscovery > Advanced eDiscovery** para mostrar la lista de casos de su organización.</span><span class="sxs-lookup"><span data-stu-id="7f304-112">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery** to display the list of cases in your organization.</span></span>

2. <span data-ttu-id="7f304-113">Seleccione un caso, haga clic en la pestaña **comunicaciones** y, a continuación, haga clic en **nueva comunicación**.</span><span class="sxs-lookup"><span data-stu-id="7f304-113">Select a case, click the **Communications** tab, and then click **New communication**.</span></span>

3. <span data-ttu-id="7f304-114">En la página **comunicación de nombre** , especifique los siguientes detalles de comunicación (obligatorios).</span><span class="sxs-lookup"><span data-stu-id="7f304-114">On the **Name communication** page, specify the following (required) communication details.</span></span>

    - <span data-ttu-id="7f304-115">**Name**: nombre de la comunicación.</span><span class="sxs-lookup"><span data-stu-id="7f304-115">**Name**: This is the name for the communication.</span></span>

    - <span data-ttu-id="7f304-116">**Responsable**de la emisión: la lista desplegable muestra una lista de miembros de casos.</span><span class="sxs-lookup"><span data-stu-id="7f304-116">**Issuing officer**: The dropdown list displays a list of case members.</span></span> <span data-ttu-id="7f304-117">Para obtener más información sobre cómo agregar nuevos miembros a un caso, vea [crear un caso de exhibición avanzada](get-started-with-advanced-ediscovery.md#step-4-create-an-advanced-ediscovery-case)de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="7f304-117">For more information on how to add new members to a case, see [Create an Advanced eDiscovery case](get-started-with-advanced-ediscovery.md#step-4-create-an-advanced-ediscovery-case).</span></span> <span data-ttu-id="7f304-118">Cada aviso que se envíe a los custodios se enviará en nombre del responsable de la expedición especificado.</span><span class="sxs-lookup"><span data-stu-id="7f304-118">Each notice sent to custodians will be sent on behalf of the specified issuing officer.</span></span>

> [!NOTE]
> <span data-ttu-id="7f304-119">El responsable de la emisión debe tener un **buzón activo** para que aparezca en la lista desplegable de la entidad emisora</span><span class="sxs-lookup"><span data-stu-id="7f304-119">The issuing officer must have an **active mailbox** to show up in the Issuing Officer dropdown</span></span>


4. <span data-ttu-id="7f304-120">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f304-120">Click **Next**.</span></span>

## <a name="step-2-define-the-portal-content"></a><span data-ttu-id="7f304-121">Paso 2: definir el contenido del portal</span><span class="sxs-lookup"><span data-stu-id="7f304-121">Step 2: Define the portal content</span></span>

<span data-ttu-id="7f304-122">A continuación, puede crear y agregar el contenido del aviso de suspensión.</span><span class="sxs-lookup"><span data-stu-id="7f304-122">Next, you can create and add the content of the hold notice.</span></span> <span data-ttu-id="7f304-123">En la página **definir contenido del portal** del Asistente para **crear una comunicación** , especifique el contenido del aviso de retención.</span><span class="sxs-lookup"><span data-stu-id="7f304-123">On the **Define portal content** page in the **Create communication** wizard, specify the contents of the hold notice.</span></span> <span data-ttu-id="7f304-124">Este contenido se anexará automáticamente a los avisos de emisión, reemisión, aviso y reasignación de responsabilidades.</span><span class="sxs-lookup"><span data-stu-id="7f304-124">This content will be automatically appended to the Issuance, Re-Issue, Reminder, and Escalation notices.</span></span> <span data-ttu-id="7f304-125">Además, este contenido aparecerá en el portal de cumplimiento de la custodio.</span><span class="sxs-lookup"><span data-stu-id="7f304-125">Additionally, this content will appear in the custodian's Compliance Portal.</span></span> 

![Página de contenido del portal](../media/PortalContent.PNG)

<span data-ttu-id="7f304-127">Para crear el contenido del portal:</span><span class="sxs-lookup"><span data-stu-id="7f304-127">To create the portal content:</span></span>

1. <span data-ttu-id="7f304-128">Escriba (o corte y pegue desde otro documento) el aviso de suspensión en el cuadro de texto para el contenido del portal.</span><span class="sxs-lookup"><span data-stu-id="7f304-128">Type (or cut and paste from another document) your hold notice in the textbox for the portal content.</span></span> 

2. <span data-ttu-id="7f304-129">Inserte las variables de combinación en el aviso para personalizar el aviso y compartir el portal de cumplimiento de custodios.</span><span class="sxs-lookup"><span data-stu-id="7f304-129">Insert merge variables into your notice to customize the notice and share the Custodian Compliance Portal.</span></span>

3. <span data-ttu-id="7f304-130">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f304-130">Click **Next**.</span></span>

  >[!Tip]
  ><span data-ttu-id="7f304-131">Para obtener más información acerca de cómo puede personalizar el contenido y el formato del contenido del portal, consulte [use el editor de comunicaciones](using-communications-editor.md).</span><span class="sxs-lookup"><span data-stu-id="7f304-131">To learn more about how to can customize the content and format of the portal content, see [Use the Communications Editor](using-communications-editor.md).</span></span>

## <a name="step-3-set-the-required-notifications"></a><span data-ttu-id="7f304-132">Paso 3: establecer las notificaciones necesarias</span><span class="sxs-lookup"><span data-stu-id="7f304-132">Step 3: Set the required notifications</span></span>

<span data-ttu-id="7f304-133">Una vez que haya definido el contenido del aviso de retención, puede configurar los flujos de trabajo para enviar y administrar el proceso de notificación.</span><span class="sxs-lookup"><span data-stu-id="7f304-133">After you've defined the contents of the hold notice, you can set up the workflows around sending and managing the notification process.</span></span> <span data-ttu-id="7f304-134">Las notificaciones son mensajes de correo electrónico que se envían a notificar y realizar un seguimiento con custodios.</span><span class="sxs-lookup"><span data-stu-id="7f304-134">Notifications are email messages that are sent to notify and follow up with custodians.</span></span> <span data-ttu-id="7f304-135">Todos los custodios que se agreguen a la comunicación recibirán la misma notificación.</span><span class="sxs-lookup"><span data-stu-id="7f304-135">Every custodian added to the communication will receive the same notification.</span></span> 

<span data-ttu-id="7f304-136">Para configurar y enviar un aviso de retención, debe incluir notificaciones de emisión, reemisión y publicación.</span><span class="sxs-lookup"><span data-stu-id="7f304-136">To set up and send a hold notice, you must include Issuance, Re-Issuance, and Release notifications.</span></span>

### <a name="issuance-notification"></a><span data-ttu-id="7f304-137">Notificación de emisión</span><span class="sxs-lookup"><span data-stu-id="7f304-137">Issuance notification</span></span> 

<span data-ttu-id="7f304-138">Una vez creada la comunicación, la **notificación de emisión** la inicia el responsable de la emisión especificado.</span><span class="sxs-lookup"><span data-stu-id="7f304-138">After the communication is created, the **Issuance Notification** is initiated by the specified Issuing Officer.</span></span> <span data-ttu-id="7f304-139">La notificación de emisión es la primera comunicación que se envía al custodio para informarles sobre sus obligaciones de conservación.</span><span class="sxs-lookup"><span data-stu-id="7f304-139">The Issuance notification is the first communication sent to the custodian to inform them about their preservation obligations.</span></span> 

<span data-ttu-id="7f304-140">Para crear una notificación de emisión:</span><span class="sxs-lookup"><span data-stu-id="7f304-140">To create an issuance notification:</span></span>

1. <span data-ttu-id="7f304-141">En el icono **emisión** , haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7f304-141">In the **Issuance** tile, click **Edit**.</span></span>

2. <span data-ttu-id="7f304-142">Si es necesario, agregue miembros del caso o personal adicional a los campos **CC** y **CCO** .</span><span class="sxs-lookup"><span data-stu-id="7f304-142">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="7f304-143">Para agregar varios usuarios a estos campos, separe las direcciones de correo electrónico con un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="7f304-143">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="7f304-144">Especifique el **asunto** del aviso (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7f304-144">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="7f304-145">Especifique el contenido o las instrucciones adicionales que desearía proporcionar al custodio (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7f304-145">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="7f304-146">El contenido del portal que definió en el paso 2 se agrega al final del aviso de emisión.</span><span class="sxs-lookup"><span data-stu-id="7f304-146">The portal content you defined in Step 2 is added to the end of the issuance notice.</span></span> 

5. <span data-ttu-id="7f304-147">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7f304-147">Click **Save**.</span></span>

### <a name="re-issuance-notification"></a><span data-ttu-id="7f304-148">Notificación de Re-Issuance</span><span class="sxs-lookup"><span data-stu-id="7f304-148">Re-Issuance notification</span></span>

<span data-ttu-id="7f304-149">A medida que avanza el caso, es posible que se necesiten custodios para conservar más o menos datos de los que se indicó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7f304-149">As the case progresses, custodians may be required to preserve additional or less data than was previously instructed.</span></span> <span data-ttu-id="7f304-150">Después de actualizar el contenido del portal, se envía la notificación de reemisión y se avisa a los custodios acerca de los cambios en sus obligaciones de conservación.</span><span class="sxs-lookup"><span data-stu-id="7f304-150">After you update the portal content, the re-issuance notification is sent and alerts custodians about any changes to their preservation obligations.</span></span>

<span data-ttu-id="7f304-151">Para crear una notificación de nueva emisión:</span><span class="sxs-lookup"><span data-stu-id="7f304-151">To create a re-issuance notification:</span></span>

1. <span data-ttu-id="7f304-152">En el icono de **reemisión** , haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7f304-152">In the **Reissue** tile, click **Edit**.</span></span>

2. <span data-ttu-id="7f304-153">Si es necesario, agregue miembros del caso o personal adicional a los campos **CC** y **CCO** .</span><span class="sxs-lookup"><span data-stu-id="7f304-153">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="7f304-154">Para agregar varios usuarios a estos campos, separe las direcciones de correo electrónico con un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="7f304-154">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="7f304-155">Especifique el **asunto** del aviso (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7f304-155">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="7f304-156">Especifique el contenido o las instrucciones adicionales que desearía proporcionar al custodio (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7f304-156">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="7f304-157">El contenido del portal que definió en el paso 2 se agrega al final del aviso de reemisión.</span><span class="sxs-lookup"><span data-stu-id="7f304-157">The portal content you defined in Step 2 is added to the end of the re-issuance notice.</span></span>

5. <span data-ttu-id="7f304-158">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7f304-158">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="7f304-159">Si se modifica el contenido del portal (en la página **definir contenido del portal** del Asistente para **Editar comunicación** ), la notificación de reemisión se enviará automáticamente a todos los custodios asignados al aviso.</span><span class="sxs-lookup"><span data-stu-id="7f304-159">If the portal content is modified (on the **Define Portal Content** page in the **Edit communication** wizard), the re-issuance notification will be automatically sent to all custodians assigned to the notice.</span></span> <span data-ttu-id="7f304-160">Una vez enviada la notificación, se pedirá a los custodios que vuelvan a confirmar su aviso de suspensión.</span><span class="sxs-lookup"><span data-stu-id="7f304-160">After the notification is sent, custodians will be asked to re-acknowledge their hold notice.</span></span> <span data-ttu-id="7f304-161">Si ha configurado un flujo de trabajo de aviso o de escalado, también se reiniciará.</span><span class="sxs-lookup"><span data-stu-id="7f304-161">If you have set up any reminder or escalation workflows, these will also re-start.</span></span> <span data-ttu-id="7f304-162">Para obtener más información sobre qué otros eventos de administración de casos desencadenan comunicaciones, consulte [eventos que desencadenan notificaciones](#events-that-trigger-notifications).</span><span class="sxs-lookup"><span data-stu-id="7f304-162">For more information about what other case management events trigger communications, see [Events that trigger notifications](#events-that-trigger-notifications).</span></span>

### <a name="release-notification"></a><span data-ttu-id="7f304-163">Notificación de versiones</span><span class="sxs-lookup"><span data-stu-id="7f304-163">Release notification</span></span>

<span data-ttu-id="7f304-164">Después de resolver una cuestión o si un custodio ya no está sujeto a preservar contenido, puede liberar el custodio de un caso.</span><span class="sxs-lookup"><span data-stu-id="7f304-164">After a matter is resolved or if a custodian is no longer subject to preserve content, you can release the custodian from a case.</span></span> <span data-ttu-id="7f304-165">Si el custodio ha emitido previamente un aviso de retención, la notificación de versión puede usarse para avisar a los custodios de que han sido entregados desde sus obligaciones.</span><span class="sxs-lookup"><span data-stu-id="7f304-165">If the custodian was previously issued a hold notice, the release notification can be used to alert custodians that they have been released from their obligation.</span></span>

<span data-ttu-id="7f304-166">Para crear una notificación de versión:</span><span class="sxs-lookup"><span data-stu-id="7f304-166">To create a release notification:</span></span> 

1. <span data-ttu-id="7f304-167">En el mosaico de **versión** , haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7f304-167">In the **Release** tile, click **Edit**.</span></span>

2. <span data-ttu-id="7f304-168">Si es necesario, agregue miembros del caso o personal adicional a los campos **CC** y **CCO** .</span><span class="sxs-lookup"><span data-stu-id="7f304-168">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="7f304-169">Para agregar varios usuarios a estos campos, separe las direcciones de correo electrónico con un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="7f304-169">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="7f304-170">Especifique el **asunto** del aviso (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7f304-170">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="7f304-171">Especifique el contenido o las instrucciones adicionales que desearía proporcionar al custodio (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7f304-171">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span>

5. <span data-ttu-id="7f304-172">Haga clic en **Guardar** y vaya al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="7f304-172">Click **Save** and go to the next step.</span></span>

## <a name="optional-step-4-set-the-optional-notifications"></a><span data-ttu-id="7f304-173">Opcional Paso 4: establecer las notificaciones opcionales</span><span class="sxs-lookup"><span data-stu-id="7f304-173">(Optional) Step 4: Set the optional notifications</span></span>

<span data-ttu-id="7f304-174">De manera opcional, puede simplificar el flujo de trabajo para seguir con los administradores que no responden mediante la creación y programación de notificaciones automatizadas de reaviso y reasignación de incidencias.</span><span class="sxs-lookup"><span data-stu-id="7f304-174">Optionally, you can simplify the workflow for following up with unresponsive custodians by creating and scheduling automated reminder and escalation notifications.</span></span>

![Página aviso/remisión](../media/ReminderEscalations.PNG)

### <a name="reminders"></a><span data-ttu-id="7f304-176">Reminders</span><span class="sxs-lookup"><span data-stu-id="7f304-176">Reminders</span></span>

<span data-ttu-id="7f304-177">Una vez que haya enviado una notificación de retención, puede realizar un seguimiento de los administradores que no responden mediante la definición de un flujo de trabajo de aviso.</span><span class="sxs-lookup"><span data-stu-id="7f304-177">After you have sent a hold notification, you can follow up with unresponsive custodians by defining a reminder workflow.</span></span>

<span data-ttu-id="7f304-178">Para programar los avisos:</span><span class="sxs-lookup"><span data-stu-id="7f304-178">To schedule reminders:</span></span>

1. <span data-ttu-id="7f304-179">En el icono de **aviso** , haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7f304-179">In the **Reminder** tile, click **Edit**.</span></span>

2. <span data-ttu-id="7f304-180">Habilite el flujo de trabajo de **aviso** activando el **Estado** de alternancia (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7f304-180">Enable the **Reminder** workflow by turning on the **Status** toggle (required).</span></span>

3. <span data-ttu-id="7f304-181">Especifique el **intervalo de aviso (en días)** (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7f304-181">Specify the **Reminder interval (in days)** (required).</span></span> <span data-ttu-id="7f304-182">Es el número de días que se debe esperar antes de enviar las notificaciones de aviso de primer y seguimiento.</span><span class="sxs-lookup"><span data-stu-id="7f304-182">This is the number of days to wait before sending the first and follow-up reminder notifications.</span></span> <span data-ttu-id="7f304-183">Por ejemplo, si establece el intervalo de recordatorio en siete días, se enviará el primer aviso siete días después de la emisión inicial de la notificación de retención.</span><span class="sxs-lookup"><span data-stu-id="7f304-183">For example, if you set the reminder interval to seven days, then the first reminder would be sent seven days after the hold notification was initially issued.</span></span> <span data-ttu-id="7f304-184">Todos los avisos subsiguientes se enviarán también cada siete días.</span><span class="sxs-lookup"><span data-stu-id="7f304-184">All subsequent reminders would also be sent every seven days.</span></span>

4. <span data-ttu-id="7f304-185">Especifique el **número de avisos** (obligatorios).</span><span class="sxs-lookup"><span data-stu-id="7f304-185">Specify the **Number of reminders** (required).</span></span> <span data-ttu-id="7f304-186">Este campo especifica cuántos avisos enviar a administradores que no responden.</span><span class="sxs-lookup"><span data-stu-id="7f304-186">This field specifies how many reminders to send to unresponsive custodians.</span></span> <span data-ttu-id="7f304-187">Por ejemplo, si establece el número de avisos en 3, un custodio recibirá un máximo de tres recordatorios.</span><span class="sxs-lookup"><span data-stu-id="7f304-187">For example, if you set the number of reminders to 3, then a custodian would receive a maximum of three reminders.</span></span> <span data-ttu-id="7f304-188">Una vez que un custodio reconoce la notificación de retención, ya no se enviarán avisos a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="7f304-188">After a custodian acknowledges the hold notification, reminders will no longer be sent to that user.</span></span>

5. <span data-ttu-id="7f304-189">Especifique el **asunto** del aviso (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7f304-189">Specify the **Subject** for the notice (required).</span></span> 

6. <span data-ttu-id="7f304-190">Especifique el contenido o las instrucciones adicionales que desearía proporcionar al custodio (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7f304-190">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="7f304-191">El contenido del portal que definió en el paso 2 se agrega al final de la notificación de aviso.</span><span class="sxs-lookup"><span data-stu-id="7f304-191">The portal content you defined in Step 2 is added to the end of the reminder notice.</span></span>

7. <span data-ttu-id="7f304-192">Haga clic en **Guardar** y continúe con el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="7f304-192">Click **Save** and go the next step.</span></span>

### <a name="escalations"></a><span data-ttu-id="7f304-193">Escalaciones</span><span class="sxs-lookup"><span data-stu-id="7f304-193">Escalations</span></span>

<span data-ttu-id="7f304-194">En algunas situaciones, es posible que necesite otras formas de realizar un seguimiento de los administradores que no responden.</span><span class="sxs-lookup"><span data-stu-id="7f304-194">In some situations, you may need additional ways to follow up with unresponsive custodians.</span></span> <span data-ttu-id="7f304-195">Si un custodio no reconoce una notificación de retención después de recibir el número especificado de avisos, el equipo legal puede especificar un flujo de trabajo para enviar automáticamente un aviso de escalado al custodio y a su administrador.</span><span class="sxs-lookup"><span data-stu-id="7f304-195">If a custodian doesn't acknowledge a hold notification after receiving the specified number of reminders, the legal team can specify a workflow to automatically send an escalation notice to the custodian and their manager.</span></span>

<span data-ttu-id="7f304-196">Para programar las escalaciones:</span><span class="sxs-lookup"><span data-stu-id="7f304-196">To schedule escalations:</span></span>

1. <span data-ttu-id="7f304-197">En el mosaico **escalado** , haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7f304-197">In the **Escalation** tile, click **Edit**.</span></span>

2. <span data-ttu-id="7f304-198">Habilite el flujo de trabajo de **escalado** activando el **Estado** de alternancia.</span><span class="sxs-lookup"><span data-stu-id="7f304-198">Enable the **Escalation** workflow by turning on the **Status** toggle.</span></span>

3. <span data-ttu-id="7f304-199">Especifique el **intervalo de escalación (en días)** (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7f304-199">Specify the **Escalation interval (in days)** (required).</span></span>

4. <span data-ttu-id="7f304-200">Especifique el **número de escalaciones** (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7f304-200">Specify the **Number of escalations** (required).</span></span> <span data-ttu-id="7f304-201">Este campo especifica cuántas escalaciones se deben enviar a los administradores que no responden.</span><span class="sxs-lookup"><span data-stu-id="7f304-201">This field specifies how many escalations to send to unresponsive custodians.</span></span> <span data-ttu-id="7f304-202">Por ejemplo, si establece el número de escalaciones en 3, se enviará un aviso de remisión a la custodio y a su administrador un máximo de tres veces.</span><span class="sxs-lookup"><span data-stu-id="7f304-202">For example, if you set the number of escalations to 3, then an escalation notice would be sent to the custodian and their manager a maximum of three times.</span></span> <span data-ttu-id="7f304-203">Después de que un custodio reconozca la notificación de retención, las escalaciones ya no se enviarán.</span><span class="sxs-lookup"><span data-stu-id="7f304-203">After a custodian acknowledges the hold notification, escalations will no longer be sent.</span></span>

5. <span data-ttu-id="7f304-204">Especifique el **asunto** del aviso (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7f304-204">Specify the **Subject** for the notice (required).</span></span> 

6. <span data-ttu-id="7f304-205">Especifique el contenido o las instrucciones adicionales que desearía proporcionar al custodio (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="7f304-205">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="7f304-206">El contenido del portal que definió en el paso 2 se agrega al final del aviso de escalado.</span><span class="sxs-lookup"><span data-stu-id="7f304-206">The portal content you defined in Step 2 is added to the end of the escalation notice.</span></span>

7. <span data-ttu-id="7f304-207">Haga clic en **Guardar** y continúe con el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="7f304-207">Click **Save** and go the next step.</span></span>

## <a name="step-5-assign-custodians-to-receive-notifications"></a><span data-ttu-id="7f304-208">Paso 5: asignar custodios para recibir notificaciones</span><span class="sxs-lookup"><span data-stu-id="7f304-208">Step 5: Assign custodians to receive notifications</span></span>

<span data-ttu-id="7f304-209">Una vez que haya finalizado el contenido de las notificaciones, seleccione los custodios a los que desea enviar notificaciones.</span><span class="sxs-lookup"><span data-stu-id="7f304-209">After you have finalized the content for notifications, select the custodians that you would like to send notifications to.</span></span> 

![Página seleccionar custodios](../media/SelectCustodians.PNG)

<span data-ttu-id="7f304-211">Para agregar custodios:</span><span class="sxs-lookup"><span data-stu-id="7f304-211">To add custodians:</span></span>

1. <span data-ttu-id="7f304-212">Asigne custodios a la comunicación haciendo clic en la casilla situada junto a su nombre.</span><span class="sxs-lookup"><span data-stu-id="7f304-212">Assign custodians to the communication by clicking the checkbox next to their name.</span></span>

    <span data-ttu-id="7f304-213">Una vez creada la comunicación, el flujo de trabajo de notificaciones se aplicará automáticamente a los custodios seleccionados.</span><span class="sxs-lookup"><span data-stu-id="7f304-213">After the communication is created, the notification workflow will automatically apply to the selected custodians.</span></span>

2. <span data-ttu-id="7f304-214">Haga clic en **siguiente** para revisar la configuración y los detalles de comunicación.</span><span class="sxs-lookup"><span data-stu-id="7f304-214">Click **Next** to review the communication settings and details.</span></span>

>[!NOTE]
><span data-ttu-id="7f304-215">Solo se pueden agregar custodios que se hayan agregado al caso y que no se haya enviado otra notificación en el caso.</span><span class="sxs-lookup"><span data-stu-id="7f304-215">You can only add custodians who have been added to the case and haven't been sent another notification within the case.</span></span>

## <a name="step-6-review-settings"></a><span data-ttu-id="7f304-216">Paso 6: revisar la configuración</span><span class="sxs-lookup"><span data-stu-id="7f304-216">Step 6: Review settings</span></span>

<span data-ttu-id="7f304-217">Después de revisar la configuración y hacer clic en **Enviar** para completar la comunicación, el sistema iniciará automáticamente el flujo de trabajo de comunicación enviando el aviso de emisión.</span><span class="sxs-lookup"><span data-stu-id="7f304-217">After you review the settings and click **Send** to complete the communication, the system will automatically start the communication workflow by sending the issuance notice.</span></span>

## <a name="events-that-trigger-notifications"></a><span data-ttu-id="7f304-218">Eventos que desencadenan notificaciones</span><span class="sxs-lookup"><span data-stu-id="7f304-218">Events that trigger notifications</span></span>

<span data-ttu-id="7f304-219">En la tabla siguiente se describen los eventos del proceso de administración de casos que se activan cuando los distintos tipos de notificaciones se envían a los custodios.</span><span class="sxs-lookup"><span data-stu-id="7f304-219">The following table describes events in the case management process that trigger when the different types of notifications are sent to custodians.</span></span>

|<span data-ttu-id="7f304-220">Tipo de comunicación</span><span class="sxs-lookup"><span data-stu-id="7f304-220">Type of communication</span></span>|<span data-ttu-id="7f304-221">Trigger</span><span class="sxs-lookup"><span data-stu-id="7f304-221">Trigger</span></span> |
|:---------|:---------|
|<span data-ttu-id="7f304-222">Avisos de emisión</span><span class="sxs-lookup"><span data-stu-id="7f304-222">Issuance notices</span></span>|<span data-ttu-id="7f304-223">La creación inicial de la notificación.</span><span class="sxs-lookup"><span data-stu-id="7f304-223">The initial creation of the notification.</span></span> <span data-ttu-id="7f304-224">También puede volver a enviar manualmente una notificación de retención.</span><span class="sxs-lookup"><span data-stu-id="7f304-224">You can also manually resend a hold notification.</span></span> |
|<span data-ttu-id="7f304-225">Avisos de nueva emisión</span><span class="sxs-lookup"><span data-stu-id="7f304-225">Re-issuance notices</span></span>|<span data-ttu-id="7f304-226">Actualizar el contenido del portal en la página **definir contenido del portal** en el Asistente para **Editar comunicación** .</span><span class="sxs-lookup"><span data-stu-id="7f304-226">Updating the portal content on the **Define Portal Content** page in the **Edit communication** wizard.</span></span>|
|<span data-ttu-id="7f304-227">Avisos de versión</span><span class="sxs-lookup"><span data-stu-id="7f304-227">Release notices</span></span>|<span data-ttu-id="7f304-228">El custodio se publica desde el caso.</span><span class="sxs-lookup"><span data-stu-id="7f304-228">The custodian is released from the case.</span></span>|
|<span data-ttu-id="7f304-229">Reminders</span><span class="sxs-lookup"><span data-stu-id="7f304-229">Reminders</span></span>|<span data-ttu-id="7f304-230">El intervalo y el número de avisos configurados para el aviso.</span><span class="sxs-lookup"><span data-stu-id="7f304-230">The interval and number of reminders configured for the reminder.</span></span>|
|<span data-ttu-id="7f304-231">Escalaciones</span><span class="sxs-lookup"><span data-stu-id="7f304-231">Escalations</span></span>|<span data-ttu-id="7f304-232">El intervalo y el número de avisos configurados para la escalación.</span><span class="sxs-lookup"><span data-stu-id="7f304-232">The interval and number of reminders configured for the escalation.</span></span>|
|||
