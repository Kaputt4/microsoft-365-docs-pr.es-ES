---
title: Revisar las conversaciones en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Obtenga información sobre cómo usar la característica de reconstrucción de conversaciones en eDiscovery avanzado para reconstruir, revisar y exportar conversaciones encadenadas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bf5c39f567240b58546dbeb353e3e461e9b69e48
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358348"
---
# <a name="review-conversations-in-advanced-ediscovery"></a><span data-ttu-id="95af7-103">Revisar las conversaciones en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="95af7-103">Review conversations in Advanced eDiscovery</span></span> 

<span data-ttu-id="95af7-104">La mensajería instantánea es una forma cómoda de plantear preguntas, compartir ideas o comunicarse rápidamente a través de grandes audiencias.</span><span class="sxs-lookup"><span data-stu-id="95af7-104">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="95af7-105">A medida que las plataformas de mensajería instantánea, como Microsoft Teams, se convierten en las principales de colaboración empresarial, las organizaciones deben evaluar cómo el flujo de trabajo de eDiscovery aborda estas nuevas formas de comunicación y colaboración.</span><span class="sxs-lookup"><span data-stu-id="95af7-105">As instant messaging platforms, like Microsoft Teams, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span> 

<span data-ttu-id="95af7-106">La característica de reconstrucción de conversaciones en eDiscovery avanzado está diseñada para ayudarle a identificar el contenido contextual y producir vistas de conversación distintas.</span><span class="sxs-lookup"><span data-stu-id="95af7-106">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="95af7-107">Esta función le permite revisar de forma rápida y eficaz las conversaciones de mensajes instantáneos completa (también denominadas *conversaciones encadenadas*) que se generan en plataformas como Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="95af7-107">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="95af7-108">Con la reconstrucción de conversaciones, puede usar capacidades integradas para reconstruir, revisar y exportar conversaciones encadenadas.</span><span class="sxs-lookup"><span data-stu-id="95af7-108">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="95af7-109">Use la reconstrucción avanzada de conversaciones de exhibición de documentos electrónicos para:</span><span class="sxs-lookup"><span data-stu-id="95af7-109">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="95af7-110">Conserve los metadatos exclusivos en el nivel de mensaje en todos los mensajes de una conversación.</span><span class="sxs-lookup"><span data-stu-id="95af7-110">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="95af7-111">Recopilar mensajes contextuales alrededor de los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="95af7-111">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="95af7-112">Revisar, anotar y censurar conversaciones encadenadas.</span><span class="sxs-lookup"><span data-stu-id="95af7-112">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="95af7-113">Exportar mensajes individuales o conversaciones encadenadas</span><span class="sxs-lookup"><span data-stu-id="95af7-113">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="95af7-114">Terminología</span><span class="sxs-lookup"><span data-stu-id="95af7-114">Terminology</span></span>

<span data-ttu-id="95af7-115">Estas son algunas definiciones para ayudarle a empezar a usar la reconstrucción de conversaciones.</span><span class="sxs-lookup"><span data-stu-id="95af7-115">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="95af7-116">**Mensajes:** Representan la unidad más pequeña de una conversación.</span><span class="sxs-lookup"><span data-stu-id="95af7-116">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="95af7-117">Los mensajes pueden variar en tamaño, estructura y metadatos.</span><span class="sxs-lookup"><span data-stu-id="95af7-117">Messages may vary in size, structure, and metadata.</span></span> 

- <span data-ttu-id="95af7-118">**Conversación:** Representa una agrupación de uno o más mensajes.</span><span class="sxs-lookup"><span data-stu-id="95af7-118">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="95af7-119">En las distintas aplicaciones, las conversaciones pueden representarse de formas diferentes.</span><span class="sxs-lookup"><span data-stu-id="95af7-119">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="95af7-120">En algunas aplicaciones, hay una acción explícita que se produce al responder a un mensaje existente.</span><span class="sxs-lookup"><span data-stu-id="95af7-120">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="95af7-121">Las conversaciones se crean de forma explícita como resultado de esta acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="95af7-121">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="95af7-122">Por ejemplo, aquí se muestra una captura de pantalla de una conversación de canal en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="95af7-122">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Conversación de canal de Microsoft Teams](../media/threadedchat.png)

   <span data-ttu-id="95af7-124">En otras aplicaciones (como los mensajes de chat de 1xN en Microsoft Teams), no hay una cadena de respuestas formales y en su lugar los mensajes aparecen como una "río plano de mensajes" en un único subproceso.</span><span class="sxs-lookup"><span data-stu-id="95af7-124">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="95af7-125">En estas aplicaciones de tipos, las conversaciones se deducen de un grupo de mensajes que se producen en un momento determinado.</span><span class="sxs-lookup"><span data-stu-id="95af7-125">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="95af7-126">Esta "agrupación flexible" de mensajes (a diferencia de una cadena de respuesta) representa la conversación "hacia delante y hacia atrás" sobre un tema específico de interés.</span><span class="sxs-lookup"><span data-stu-id="95af7-126">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span> 

## <a name="step-1-run-a-search"></a><span data-ttu-id="95af7-127">Paso 1: ejecutar una búsqueda</span><span class="sxs-lookup"><span data-stu-id="95af7-127">Step 1: Run a search</span></span>

<span data-ttu-id="95af7-128">Una vez que haya identificado los custodios y las ubicaciones de contenido relevantes, puede crear una búsqueda para encontrar contenido potencialmente relevante.</span><span class="sxs-lookup"><span data-stu-id="95af7-128">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="95af7-129">En la ficha **búsquedas** en el caso de exhibición avanzada de documentos electrónicos, puede crear una búsqueda haciendo clic en **nueva búsqueda** y siguiendo el asistente.</span><span class="sxs-lookup"><span data-stu-id="95af7-129">On the **Searches** tab in the Advanced eDiscovery case, you can create a search by clicking **New search** and following the wizard.</span></span> <span data-ttu-id="95af7-130">Para obtener información sobre cómo se puede crear una búsqueda, crear una consulta de búsqueda y ver los resultados de la búsqueda, vea [recopilar datos para un caso](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="95af7-130">For information about how you can create a search, build a search query, and view the search results, see [Collect data for a case](create-search-to-collect-data.md).</span></span>

## <a name="step-2-create-a-conversation-review-set"></a><span data-ttu-id="95af7-131">Paso 2: crear un conjunto de revisión de conversación</span><span class="sxs-lookup"><span data-stu-id="95af7-131">Step 2: Create a conversation review set</span></span>

<span data-ttu-id="95af7-132">En un conjunto de revisiones, puede buscar, etiquetar, anotar y censurar documentos, mensajes de correo electrónico y conversaciones de chat.</span><span class="sxs-lookup"><span data-stu-id="95af7-132">In a review set, you can search, tag, annotate, and redact documents, email messages, and chat conversations.</span></span> <span data-ttu-id="95af7-133">En la exhibición avanzada de documentos electrónicos, puede personalizar la revisión de las conversaciones, en función de mensajes individuales o conversaciones encadenadas.</span><span class="sxs-lookup"><span data-stu-id="95af7-133">In Advanced eDiscovery, you can customize your review of conversations, based in individual messages or threaded conversations.</span></span> <span data-ttu-id="95af7-134">Esto lo determina el tipo de conjunto de revisión que agrega los resultados de la búsqueda creada en el paso 1 a.</span><span class="sxs-lookup"><span data-stu-id="95af7-134">This is determined by the type of review set that you add the results of the search created in Step 1 to.</span></span> <span data-ttu-id="95af7-135">Hay dos tipos diferentes de conjuntos de revisión:</span><span class="sxs-lookup"><span data-stu-id="95af7-135">There are two different types of review sets:</span></span> 
  
  - <span data-ttu-id="95af7-136">**Conjuntos de revisión estándar:** Los mensajes en conversaciones se procesan y se muestran como elementos individuales.</span><span class="sxs-lookup"><span data-stu-id="95af7-136">**Standard review sets:** Messages in conversations are processed and displayed as individual items.</span></span> 
  
  -  <span data-ttu-id="95af7-137">**Conjuntos de revisión de conversación:** Los mensajes en conversaciones se procesan de forma individual, pero se muestran en una vista de conversación.</span><span class="sxs-lookup"><span data-stu-id="95af7-137">**Conversation review sets:** Messages in conversations are processed individually but displayed in a conversation view.</span></span> <span data-ttu-id="95af7-138">En un conjunto de revisión de conversación, puede anotar, etiquetar y censurar mensajes en una vista de conversación encadenada.</span><span class="sxs-lookup"><span data-stu-id="95af7-138">In a conversation review set, you can annotate, tag, and redact messages in a threaded conversation view.</span></span> 

<span data-ttu-id="95af7-139">Para obtener más información acerca de cómo revisar y administrar el contenido de un conjunto de revisión, consulte [Manage Review sets](managing-review-sets.md).</span><span class="sxs-lookup"><span data-stu-id="95af7-139">For more information about how to review and manage content in a review set, see [Manage review sets](managing-review-sets.md).</span></span> 

## <a name="step-3-enable-conversation-retrieval-options"></a><span data-ttu-id="95af7-140">Paso 3: habilitar las opciones de recuperación de conversaciones</span><span class="sxs-lookup"><span data-stu-id="95af7-140">Step 3: Enable conversation retrieval options</span></span>

<span data-ttu-id="95af7-141">Una vez que haya revisado y finalizado la consulta de búsqueda, puede Agregar los resultados de la búsqueda a un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="95af7-141">After you have reviewed and finalized your search query, you can add the search results to a review set.</span></span> <span data-ttu-id="95af7-142">Cuando se agregan los resultados de la búsqueda a un conjunto de revisión, los datos originales se copian en un área de almacenamiento de Azure para facilitar el proceso de revisión y análisis.</span><span class="sxs-lookup"><span data-stu-id="95af7-142">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="95af7-143">Para obtener más información acerca de cómo agregar resultados de búsqueda a un conjunto de revisiones, consulte [Agregar resultados de búsqueda a un conjunto de revisiones](add-data-to-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="95af7-143">For more information about adding search results to a review set, see [Add search results to a review set](add-data-to-review-set.md).</span></span> 

<span data-ttu-id="95af7-144">Al agregar datos de conversaciones a un conjunto de revisión, puede usar las opciones de recuperación de conversaciones para expandir la búsqueda e incluir mensajes contextuales.</span><span class="sxs-lookup"><span data-stu-id="95af7-144">When you add data from conversations to a review set, you can use the conversation retrieval options to expand your search and include contextual messages.</span></span> <span data-ttu-id="95af7-145">Después de establecer las opciones de recuperación de conversaciones, pueden ocurrir las siguientes cosas:</span><span class="sxs-lookup"><span data-stu-id="95af7-145">After you set the conversation retrieval options, the following things can happen:</span></span>

  ![Recuperación de conversaciones](../media/messagesandconversations.png)
  
1. <span data-ttu-id="95af7-147">Mediante una consulta de palabra clave y un intervalo de fechas, la búsqueda devolvió un error en el *mensaje 3*.</span><span class="sxs-lookup"><span data-stu-id="95af7-147">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="95af7-148">Este mensaje formaba parte de una conversación más amplia, ilustrada por *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="95af7-148">This message was part of a larger conversation, illustrated by *CRC1*.</span></span> 
  
2. <span data-ttu-id="95af7-149">Al agregar los datos a un conjunto de revisión y habilitar las opciones de recuperación de conversaciones, la exhibición avanzada de documentos electrónicos se revertirá y recopilará otros elementos en *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="95af7-149">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span> 
  
3. <span data-ttu-id="95af7-150">Una vez agregados los elementos al conjunto de revisión, puede revisar todos los mensajes individuales de *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="95af7-150">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span> 

<span data-ttu-id="95af7-151">Para habilitar la recuperación de conversaciones:</span><span class="sxs-lookup"><span data-stu-id="95af7-151">To enable conversation retrieval:</span></span>
  
1. <span data-ttu-id="95af7-152">En la pestaña **búsquedas** en el caso de eDiscovery avanzado, seleccione una búsqueda y, a continuación, haga clic en **Agregar a conjunto de revisiones** en la página de flotante.</span><span class="sxs-lookup"><span data-stu-id="95af7-152">On the **Searches** tab in the Advanced eDiscovery case, select a search, and then click **Add to review set** on the flyout page.</span></span>
  
2. <span data-ttu-id="95af7-153">Seleccione un conjunto de revisiones existente o cree un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="95af7-153">Select an existing review set or create a review set.</span></span> <span data-ttu-id="95af7-154">Puede configurar las opciones de recuperación al agregar resultados de búsqueda a un conjunto de revisión estándar o de conversación.</span><span class="sxs-lookup"><span data-stu-id="95af7-154">You can configure retrieval options when adding search results to a standard or a conversation review set.</span></span>
  
3. <span data-ttu-id="95af7-155">En **Opciones de colección**, configure las opciones de recuperación de conversaciones para los orígenes de contenido que desee expandir en la búsqueda y, a continuación, haga clic en **Agregar** para iniciar el proceso.</span><span class="sxs-lookup"><span data-stu-id="95af7-155">Under **Collection options**, configure the conversation retrieval options for the content sources that you want to expand in your search, and then click **Add** to start the process.</span></span>  
  
4. <span data-ttu-id="95af7-156">Una vez finalizado el trabajo **Agregar a la definición de revisión** en la ficha **trabajos** , puede iniciar la revisión de las conversaciones.</span><span class="sxs-lookup"><span data-stu-id="95af7-156">After the **Add to review set** job on the **Jobs** tab has finished, you can start reviewing the conversations.</span></span>

## <a name="step-4-review-and-export-conversations-in-a-review-set"></a><span data-ttu-id="95af7-157">Paso 4: revisar y exportar conversaciones en un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="95af7-157">Step 4: Review and export conversations in a review set</span></span>

<span data-ttu-id="95af7-158">Una vez que el contenido se ha procesado y agregado al conjunto de revisiones, puede iniciar la revisión de los datos en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="95af7-158">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="95af7-159">Las capacidades de revisión son diferentes en función de si el contenido se agregó a un conjunto de revisión estándar o un conjunto de revisión de conversación.</span><span class="sxs-lookup"><span data-stu-id="95af7-159">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span> 

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="95af7-160">Revisión de conversaciones en un conjunto de revisión estándar</span><span class="sxs-lookup"><span data-stu-id="95af7-160">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="95af7-161">En un conjunto de revisiones estándar, los mensajes se procesan y se muestran como elementos individuales, de manera similar a como se almacenan en una carpeta de buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="95af7-161">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="95af7-162">En este flujo de trabajo, cada mensaje se procesa como un elemento independiente.</span><span class="sxs-lookup"><span data-stu-id="95af7-162">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="95af7-163">Como resultado, las opciones de exportación y Resumen encadenados no están disponibles en un conjunto de revisión estándar.</span><span class="sxs-lookup"><span data-stu-id="95af7-163">As a result, the threaded summary and export options aren't available in a standard review set.</span></span> 

  ![Conjunto de revisión estándar](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="95af7-165">Revisar conversaciones en un conjunto de revisión de conversación</span><span class="sxs-lookup"><span data-stu-id="95af7-165">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="95af7-166">En un conjunto de revisión de conversación, los mensajes individuales se enlazan juntos y se presentan como conversaciones.</span><span class="sxs-lookup"><span data-stu-id="95af7-166">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="95af7-167">Esto le permite revisar y exportar conversaciones contextuales.</span><span class="sxs-lookup"><span data-stu-id="95af7-167">This lets you review and export contextual conversations.</span></span> 

  ![Conjunto de revisión de conversación](../media/ConversationRSOptions.PNG)

<span data-ttu-id="95af7-169">En las siguientes secciones se describe cómo revisar y exportar conversaciones en un conjunto de revisión de conversación.</span><span class="sxs-lookup"><span data-stu-id="95af7-169">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="95af7-170">Revisión de conversaciones</span><span class="sxs-lookup"><span data-stu-id="95af7-170">Reviewing conversations</span></span>

<span data-ttu-id="95af7-171">En un conjunto de revisión de conversación, puede usar las siguientes opciones para facilitar el proceso de revisión.</span><span class="sxs-lookup"><span data-stu-id="95af7-171">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="95af7-172">**Agrupar por conversación:** Agrupa mensajes dentro de la misma conversación para ayudar a los usuarios a simplificar y acelerar su proceso de revisión.</span><span class="sxs-lookup"><span data-stu-id="95af7-172">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span> 

- <span data-ttu-id="95af7-173">**Vista de Resumen:** Muestra la conversación encadenada.</span><span class="sxs-lookup"><span data-stu-id="95af7-173">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="95af7-174">En esta vista, puede ver la conversación completa y también tener acceso a los metadatos de cada mensaje individual.</span><span class="sxs-lookup"><span data-stu-id="95af7-174">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>  
  
   - <span data-ttu-id="95af7-175">Ver metadatos de mensajes individuales</span><span class="sxs-lookup"><span data-stu-id="95af7-175">View metadata for individual messages</span></span>
   
   - <span data-ttu-id="95af7-176">Descargar mensajes individuales</span><span class="sxs-lookup"><span data-stu-id="95af7-176">Download individual messages</span></span>

- <span data-ttu-id="95af7-177">**Vista de texto:** Proporciona el texto extraído de toda la conversación.</span><span class="sxs-lookup"><span data-stu-id="95af7-177">**Text view:** Provides the extracted text for the entire conversation.</span></span> 

- <span data-ttu-id="95af7-178">**Vista de anotar:** Permite marcar una vista encadenada de la conversación.</span><span class="sxs-lookup"><span data-stu-id="95af7-178">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="95af7-179">Todos los mensajes de la conversación comparten el mismo documento con comentarios.</span><span class="sxs-lookup"><span data-stu-id="95af7-179">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="95af7-180">**Etiquetado:** Al ver conversaciones en un conjunto de revisiones, puede ver y aplicar etiquetas haciendo clic en **Panel de etiquetado** en el panel de codificación.</span><span class="sxs-lookup"><span data-stu-id="95af7-180">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="95af7-181">**Volver a ejecutar la conversión de conversación:** Cuando se agregan mensajes a un conjunto de revisión de conversación, se ejecuta automáticamente un trabajo de conversión para crear las vistas de Resumen y anotaciones de conversaciones.</span><span class="sxs-lookup"><span data-stu-id="95af7-181">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="95af7-182">Si se produce un error en el trabajo de reconstrucción de conversaciones, puede volver a ejecutar este trabajo haciendo clic en **acción > crear una conversación en PDF** en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="95af7-182">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>

#### <a name="exporting-conversations"></a><span data-ttu-id="95af7-183">Exportar conversaciones</span><span class="sxs-lookup"><span data-stu-id="95af7-183">Exporting conversations</span></span>

<span data-ttu-id="95af7-184">En un conjunto de revisión de conversación, puede establecer las siguientes opciones para exportar conversaciones:</span><span class="sxs-lookup"><span data-stu-id="95af7-184">In a conversation review set, you can set the following options to export conversations:</span></span>

![Opciones de exportación para conversaciones](../media/export.png)

<span data-ttu-id="95af7-186">a.</span><span class="sxs-lookup"><span data-stu-id="95af7-186">a.</span></span> <span data-ttu-id="95af7-187">Opciones de metadatos</span><span class="sxs-lookup"><span data-stu-id="95af7-187">Metadata options</span></span>

   - <span data-ttu-id="95af7-188">**Cargar archivo:** Los metadatos se incluyen para cada mensaje, correo electrónico y documento individual.</span><span class="sxs-lookup"><span data-stu-id="95af7-188">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="95af7-189">Hay una fila por cada mensaje en una conversación.</span><span class="sxs-lookup"><span data-stu-id="95af7-189">There is one row for each message in a conversation.</span></span> 

   - <span data-ttu-id="95af7-190">**Etiquetas:** Las etiquetas del proceso de revisión se incluyen en el archivo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="95af7-190">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="95af7-191">Los mensajes de una conversación comparten las mismas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="95af7-191">Messages in a conversation share the same tags.</span></span> 

<span data-ttu-id="95af7-192">b.</span><span class="sxs-lookup"><span data-stu-id="95af7-192">b.</span></span> <span data-ttu-id="95af7-193">Opciones de conversación</span><span class="sxs-lookup"><span data-stu-id="95af7-193">Conversation options</span></span>
  
   - <span data-ttu-id="95af7-194">**Archivos de conversación:** Cuando se exportan archivos de conversación, la vista anotada se convierte en un archivo PDF y se descarga en la carpeta de exportación.</span><span class="sxs-lookup"><span data-stu-id="95af7-194">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="95af7-195">Los mensajes de un archivo de conversación apuntan a la versión PDF del mismo archivo de conversación.</span><span class="sxs-lookup"><span data-stu-id="95af7-195">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>  
  
   - <span data-ttu-id="95af7-196">**Mensajes de chat individuales:** Cuando se exportan mensajes individuales, cada mensaje único de la conversación se exporta como un elemento independiente.</span><span class="sxs-lookup"><span data-stu-id="95af7-196">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="95af7-197">El archivo se exporta en el mismo formato en el que se guardó como en el buzón.</span><span class="sxs-lookup"><span data-stu-id="95af7-197">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="95af7-198">Para una conversación específica, recibe varios archivos. msg.</span><span class="sxs-lookup"><span data-stu-id="95af7-198">For a specific conversation, you receive multiple .msg files.</span></span> 

     >[!NOTE]
     > <span data-ttu-id="95af7-199">Si ha aplicado anotaciones en el archivo de conversación, estas anotaciones no se transferirán a los mensajes individuales.</span><span class="sxs-lookup"><span data-stu-id="95af7-199">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span> 

<span data-ttu-id="95af7-200">c.</span><span class="sxs-lookup"><span data-stu-id="95af7-200">c.</span></span> <span data-ttu-id="95af7-201">Otras opciones</span><span class="sxs-lookup"><span data-stu-id="95af7-201">Other options</span></span>

   - <span data-ttu-id="95af7-202">**Generar archivos de texto para todo el contenido exportado:** Genera un archivo de texto para cada conversación exportada desde el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="95af7-202">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span> 

   - <span data-ttu-id="95af7-203">**Reemplazar el contenido exportado con documentos PDF censurados:** Si se generan archivos de conversación censurados durante el proceso de revisión, estos archivos estarán disponibles durante la exportación.</span><span class="sxs-lookup"><span data-stu-id="95af7-203">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="95af7-204">Puede decidir si desea exportar sólo los archivos nativos (no selecciona esta opción) o reemplazar los archivos nativos con las versiones censuradas de los archivos nativos (seleccionando esta opción), que se exportan como archivos PDF.</span><span class="sxs-lookup"><span data-stu-id="95af7-204">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="95af7-205">Más información</span><span class="sxs-lookup"><span data-stu-id="95af7-205">More information</span></span>

<span data-ttu-id="95af7-206">Para obtener más información sobre cómo revisar los datos de casos en la exhibición avanzada de documentos electrónicos, vea los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="95af7-206">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="95af7-207">Ver datos de casos</span><span class="sxs-lookup"><span data-stu-id="95af7-207">View case data</span></span>](view-documents-in-review-set.md)

- [<span data-ttu-id="95af7-208">Analizar datos de casos</span><span class="sxs-lookup"><span data-stu-id="95af7-208">Analyze case data</span></span>](analyzing-data-in-review-set.md)

- [<span data-ttu-id="95af7-209">Exportar datos de casos</span><span class="sxs-lookup"><span data-stu-id="95af7-209">Export case data</span></span>](exporting-data-ediscover20.md)
