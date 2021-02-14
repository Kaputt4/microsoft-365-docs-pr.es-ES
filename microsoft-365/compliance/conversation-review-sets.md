---
title: Revisar conversaciones en eDiscovery avanzado
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
description: Obtenga información sobre cómo usar la característica reconstrucción de conversaciones en eDiscovery avanzado para reconstruir, revisar y exportar conversaciones en curso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bf5c39f567240b58546dbeb353e3e461e9b69e48
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358348"
---
# <a name="review-conversations-in-advanced-ediscovery"></a><span data-ttu-id="89539-103">Revisar conversaciones en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="89539-103">Review conversations in Advanced eDiscovery</span></span> 

<span data-ttu-id="89539-104">La mensajería instantánea es una forma cómoda de hacer preguntas, compartir ideas o comunicarse rápidamente entre grandes audiencias.</span><span class="sxs-lookup"><span data-stu-id="89539-104">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="89539-105">A medida que las plataformas de mensajería instantánea, como Microsoft Teams, se convierten en el núcleo de la colaboración empresarial, las organizaciones deben evaluar cómo su flujo de trabajo de exhibición de documentos electrónicos aborda estas nuevas formas de comunicación y colaboración.</span><span class="sxs-lookup"><span data-stu-id="89539-105">As instant messaging platforms, like Microsoft Teams, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span> 

<span data-ttu-id="89539-106">La característica Reconstrucción de conversación de eDiscovery avanzado está diseñada para ayudarle a identificar contenido contextual y producir vistas de conversación distintas.</span><span class="sxs-lookup"><span data-stu-id="89539-106">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="89539-107">Esta funcionalidad le permite revisar de forma eficaz y rápida conversaciones de mensajes instantáneos completas (también denominadas conversaciones en *secuencias)* que se generan en plataformas como Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="89539-107">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="89539-108">Con la reconstrucción de conversaciones, puede usar funciones integradas para reconstruir, revisar y exportar conversaciones en subprocesos.</span><span class="sxs-lookup"><span data-stu-id="89539-108">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="89539-109">Use la reconstrucción avanzada de conversaciones de exhibición de documentos electrónicos para:</span><span class="sxs-lookup"><span data-stu-id="89539-109">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="89539-110">Conservar metadatos únicos de nivel de mensaje en todos los mensajes de una conversación.</span><span class="sxs-lookup"><span data-stu-id="89539-110">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="89539-111">Recopilar mensajes contextuales alrededor de los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="89539-111">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="89539-112">Revisar, anotar y censurar conversaciones en subprocesos.</span><span class="sxs-lookup"><span data-stu-id="89539-112">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="89539-113">Exportar mensajes individuales o conversaciones en secuencias</span><span class="sxs-lookup"><span data-stu-id="89539-113">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="89539-114">Terminología</span><span class="sxs-lookup"><span data-stu-id="89539-114">Terminology</span></span>

<span data-ttu-id="89539-115">Estas son algunas definiciones que le ayudarán a empezar a usar la reconstrucción de conversación.</span><span class="sxs-lookup"><span data-stu-id="89539-115">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="89539-116">**Mensajes:** Representa la unidad más pequeña de una conversación.</span><span class="sxs-lookup"><span data-stu-id="89539-116">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="89539-117">Los mensajes pueden variar en tamaño, estructura y metadatos.</span><span class="sxs-lookup"><span data-stu-id="89539-117">Messages may vary in size, structure, and metadata.</span></span> 

- <span data-ttu-id="89539-118">**Conversación:** Representa una agrupación de uno o más mensajes.</span><span class="sxs-lookup"><span data-stu-id="89539-118">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="89539-119">En diferentes aplicaciones, las conversaciones pueden representarse de diferentes maneras.</span><span class="sxs-lookup"><span data-stu-id="89539-119">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="89539-120">En algunas aplicaciones, hay una acción explícita que se produce al responder a un mensaje existente.</span><span class="sxs-lookup"><span data-stu-id="89539-120">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="89539-121">Las conversaciones se forman explícitamente como resultado de esta acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="89539-121">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="89539-122">Por ejemplo, aquí tiene una captura de pantalla de una conversación de canal en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="89539-122">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Conversación del canal de Microsoft Teams](../media/threadedchat.png)

   <span data-ttu-id="89539-124">En otras aplicaciones (como los mensajes de chat 1xN en Teams), no hay una cadena de respuesta formal y, en su lugar, los mensajes aparecen como un "hilo plano de mensajes" dentro de un solo subproceso.</span><span class="sxs-lookup"><span data-stu-id="89539-124">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="89539-125">En estos tipos de aplicaciones, las conversaciones se deducen de un grupo de mensajes que se producen en un momento determinado.</span><span class="sxs-lookup"><span data-stu-id="89539-125">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="89539-126">Esta "agrupación suave" de mensajes (en lugar de una cadena de respuesta) representa la conversación de "ida y vuelta" sobre un tema específico de interés.</span><span class="sxs-lookup"><span data-stu-id="89539-126">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span> 

## <a name="step-1-run-a-search"></a><span data-ttu-id="89539-127">Paso 1: Ejecutar una búsqueda</span><span class="sxs-lookup"><span data-stu-id="89539-127">Step 1: Run a search</span></span>

<span data-ttu-id="89539-128">Una vez identificados los administradores y las ubicaciones de contenido relevantes, puede crear una búsqueda para encontrar contenido potencialmente relevante.</span><span class="sxs-lookup"><span data-stu-id="89539-128">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="89539-129">En la **pestaña Búsquedas** en el caso de eDiscovery avanzado, puede crear una búsqueda haciendo clic en **Nueva** búsqueda y siguiendo el asistente.</span><span class="sxs-lookup"><span data-stu-id="89539-129">On the **Searches** tab in the Advanced eDiscovery case, you can create a search by clicking **New search** and following the wizard.</span></span> <span data-ttu-id="89539-130">Para obtener información acerca de cómo puede crear una búsqueda, crear una consulta de búsqueda y ver los resultados de la búsqueda, vea Recopilar datos [para un caso.](create-search-to-collect-data.md)</span><span class="sxs-lookup"><span data-stu-id="89539-130">For information about how you can create a search, build a search query, and view the search results, see [Collect data for a case](create-search-to-collect-data.md).</span></span>

## <a name="step-2-create-a-conversation-review-set"></a><span data-ttu-id="89539-131">Paso 2: Crear un conjunto de revisión de conversación</span><span class="sxs-lookup"><span data-stu-id="89539-131">Step 2: Create a conversation review set</span></span>

<span data-ttu-id="89539-132">En un conjunto de revisión, puede buscar, etiquetar, anotar y censurar documentos, mensajes de correo electrónico y conversaciones de chat.</span><span class="sxs-lookup"><span data-stu-id="89539-132">In a review set, you can search, tag, annotate, and redact documents, email messages, and chat conversations.</span></span> <span data-ttu-id="89539-133">En eDiscovery avanzado, puede personalizar la revisión de las conversaciones, basadas en mensajes individuales o conversaciones en subprocesos.</span><span class="sxs-lookup"><span data-stu-id="89539-133">In Advanced eDiscovery, you can customize your review of conversations, based in individual messages or threaded conversations.</span></span> <span data-ttu-id="89539-134">Esto viene determinado por el tipo de conjunto de revisión al que agrega los resultados de la búsqueda creada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="89539-134">This is determined by the type of review set that you add the results of the search created in Step 1 to.</span></span> <span data-ttu-id="89539-135">Hay dos tipos diferentes de conjuntos de revisión:</span><span class="sxs-lookup"><span data-stu-id="89539-135">There are two different types of review sets:</span></span> 
  
  - <span data-ttu-id="89539-136">**Conjuntos de revisión estándar:** Los mensajes de las conversaciones se procesan y se muestran como elementos individuales.</span><span class="sxs-lookup"><span data-stu-id="89539-136">**Standard review sets:** Messages in conversations are processed and displayed as individual items.</span></span> 
  
  -  <span data-ttu-id="89539-137">**Conjuntos de revisión de conversación:** Los mensajes de las conversaciones se procesan individualmente, pero se muestran en una vista de conversación.</span><span class="sxs-lookup"><span data-stu-id="89539-137">**Conversation review sets:** Messages in conversations are processed individually but displayed in a conversation view.</span></span> <span data-ttu-id="89539-138">En un conjunto de revisión de conversación, puede anotar, etiquetar y censurar mensajes en una vista de conversación en secuencia.</span><span class="sxs-lookup"><span data-stu-id="89539-138">In a conversation review set, you can annotate, tag, and redact messages in a threaded conversation view.</span></span> 

<span data-ttu-id="89539-139">Para obtener más información acerca de cómo revisar y administrar el contenido de un conjunto de revisión, vea [Administrar conjuntos de revisión.](managing-review-sets.md)</span><span class="sxs-lookup"><span data-stu-id="89539-139">For more information about how to review and manage content in a review set, see [Manage review sets](managing-review-sets.md).</span></span> 

## <a name="step-3-enable-conversation-retrieval-options"></a><span data-ttu-id="89539-140">Paso 3: Habilitar las opciones de recuperación de conversaciones</span><span class="sxs-lookup"><span data-stu-id="89539-140">Step 3: Enable conversation retrieval options</span></span>

<span data-ttu-id="89539-141">Después de revisar y finalizar la consulta de búsqueda, puede agregar los resultados de la búsqueda a un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="89539-141">After you have reviewed and finalized your search query, you can add the search results to a review set.</span></span> <span data-ttu-id="89539-142">Cuando agrega los resultados de búsqueda a un conjunto de revisión, los datos originales se copian en un área de Azure Storage para facilitar el proceso de revisión y análisis.</span><span class="sxs-lookup"><span data-stu-id="89539-142">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="89539-143">Para obtener más información acerca de cómo agregar resultados de búsqueda a un conjunto de revisión, vea Agregar resultados [de búsqueda a un conjunto de revisión.](add-data-to-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="89539-143">For more information about adding search results to a review set, see [Add search results to a review set](add-data-to-review-set.md).</span></span> 

<span data-ttu-id="89539-144">Al agregar datos de conversaciones a un conjunto de revisión, puede usar las opciones de recuperación de conversaciones para expandir la búsqueda e incluir mensajes contextuales.</span><span class="sxs-lookup"><span data-stu-id="89539-144">When you add data from conversations to a review set, you can use the conversation retrieval options to expand your search and include contextual messages.</span></span> <span data-ttu-id="89539-145">Después de establecer las opciones de recuperación de conversaciones, pueden suceder lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89539-145">After you set the conversation retrieval options, the following things can happen:</span></span>

  ![Recuperación de conversación](../media/messagesandconversations.png)
  
1. <span data-ttu-id="89539-147">Mediante una consulta de palabra clave y de intervalo de fechas, la búsqueda devolvió un resultado en *el mensaje 3*.</span><span class="sxs-lookup"><span data-stu-id="89539-147">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="89539-148">Este mensaje formaba parte de una conversación más grande, ilustrada por *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="89539-148">This message was part of a larger conversation, illustrated by *CRC1*.</span></span> 
  
2. <span data-ttu-id="89539-149">Al agregar los datos a un conjunto de revisión y habilitar las opciones de recuperación de conversaciones, eDiscovery avanzado volverá y recopilará otros elementos en *CRC1.*</span><span class="sxs-lookup"><span data-stu-id="89539-149">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span> 
  
3. <span data-ttu-id="89539-150">Después de agregar los elementos al conjunto de revisión, puede revisar todos los mensajes individuales de *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="89539-150">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span> 

<span data-ttu-id="89539-151">Para habilitar la recuperación de conversaciones:</span><span class="sxs-lookup"><span data-stu-id="89539-151">To enable conversation retrieval:</span></span>
  
1. <span data-ttu-id="89539-152">En la **pestaña Búsquedas** en el caso de eDiscovery avanzado, seleccione una búsqueda y, a continuación, haga clic en Agregar para revisar el conjunto en la página desplegable. </span><span class="sxs-lookup"><span data-stu-id="89539-152">On the **Searches** tab in the Advanced eDiscovery case, select a search, and then click **Add to review set** on the flyout page.</span></span>
  
2. <span data-ttu-id="89539-153">Seleccione un conjunto de revisión existente o cree un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="89539-153">Select an existing review set or create a review set.</span></span> <span data-ttu-id="89539-154">Puede configurar las opciones de recuperación al agregar resultados de búsqueda a un conjunto de revisión estándar o de conversación.</span><span class="sxs-lookup"><span data-stu-id="89539-154">You can configure retrieval options when adding search results to a standard or a conversation review set.</span></span>
  
3. <span data-ttu-id="89539-155">En **Opciones de colección,** configure las opciones de recuperación de conversaciones para  los orígenes de contenido que desea expandir en la búsqueda y, a continuación, haga clic en Agregar para iniciar el proceso.</span><span class="sxs-lookup"><span data-stu-id="89539-155">Under **Collection options**, configure the conversation retrieval options for the content sources that you want to expand in your search, and then click **Add** to start the process.</span></span>  
  
4. <span data-ttu-id="89539-156">Una vez finalizado el trabajo  del conjunto **Agregar** a revisión en la pestaña Trabajos, puede empezar a revisar las conversaciones.</span><span class="sxs-lookup"><span data-stu-id="89539-156">After the **Add to review set** job on the **Jobs** tab has finished, you can start reviewing the conversations.</span></span>

## <a name="step-4-review-and-export-conversations-in-a-review-set"></a><span data-ttu-id="89539-157">Paso 4: Revisar y exportar conversaciones en un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="89539-157">Step 4: Review and export conversations in a review set</span></span>

<span data-ttu-id="89539-158">Una vez que el contenido se haya procesado y agregado al conjunto de revisión, puedes empezar a revisar los datos del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="89539-158">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="89539-159">Las capacidades de revisión son diferentes en función de si el contenido se agregó a un conjunto de revisión estándar o a un conjunto de revisión de conversación.</span><span class="sxs-lookup"><span data-stu-id="89539-159">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span> 

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="89539-160">Revisión de conversaciones en un conjunto de revisión estándar</span><span class="sxs-lookup"><span data-stu-id="89539-160">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="89539-161">En un conjunto de revisión estándar, los mensajes se procesan y se muestran como elementos individuales, de forma similar a como se almacenan en una carpeta de buzón.</span><span class="sxs-lookup"><span data-stu-id="89539-161">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="89539-162">En este flujo de trabajo, cada mensaje se procesa como un elemento independiente.</span><span class="sxs-lookup"><span data-stu-id="89539-162">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="89539-163">Como resultado, las opciones de resumen y exportación en subproceso no están disponibles en un conjunto de revisión estándar.</span><span class="sxs-lookup"><span data-stu-id="89539-163">As a result, the threaded summary and export options aren't available in a standard review set.</span></span> 

  ![Conjunto de revisión estándar](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="89539-165">Revisión de conversaciones en un conjunto de revisión de conversación</span><span class="sxs-lookup"><span data-stu-id="89539-165">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="89539-166">En un conjunto de revisión de conversación, los mensajes individuales se en subprocesos y se presentan como conversaciones.</span><span class="sxs-lookup"><span data-stu-id="89539-166">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="89539-167">Esto le permite revisar y exportar conversaciones contextuales.</span><span class="sxs-lookup"><span data-stu-id="89539-167">This lets you review and export contextual conversations.</span></span> 

  ![Conjunto de revisión de conversación](../media/ConversationRSOptions.PNG)

<span data-ttu-id="89539-169">En las secciones siguientes se describe la revisión y exportación de conversaciones en un conjunto de revisión de conversación.</span><span class="sxs-lookup"><span data-stu-id="89539-169">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="89539-170">Revisión de conversaciones</span><span class="sxs-lookup"><span data-stu-id="89539-170">Reviewing conversations</span></span>

<span data-ttu-id="89539-171">En un conjunto de revisión de conversación, puede usar las siguientes opciones para facilitar el proceso de revisión.</span><span class="sxs-lookup"><span data-stu-id="89539-171">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="89539-172">**Agrupar por conversación:** Agrupa los mensajes dentro de la misma conversación para ayudar a los usuarios a simplificar y acelerar su proceso de revisión.</span><span class="sxs-lookup"><span data-stu-id="89539-172">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span> 

- <span data-ttu-id="89539-173">**Vista de resumen:** Muestra la conversación en secuencia.</span><span class="sxs-lookup"><span data-stu-id="89539-173">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="89539-174">En esta vista, puede ver toda la conversación y también tener acceso a los metadatos de cada mensaje individual.</span><span class="sxs-lookup"><span data-stu-id="89539-174">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>  
  
   - <span data-ttu-id="89539-175">Ver metadatos de mensajes individuales</span><span class="sxs-lookup"><span data-stu-id="89539-175">View metadata for individual messages</span></span>
   
   - <span data-ttu-id="89539-176">Descargar mensajes individuales</span><span class="sxs-lookup"><span data-stu-id="89539-176">Download individual messages</span></span>

- <span data-ttu-id="89539-177">**Vista de texto:** Proporciona el texto extraído para toda la conversación.</span><span class="sxs-lookup"><span data-stu-id="89539-177">**Text view:** Provides the extracted text for the entire conversation.</span></span> 

- <span data-ttu-id="89539-178">**Vista anotada:** Permite marcar una vista en secuencia de la conversación.</span><span class="sxs-lookup"><span data-stu-id="89539-178">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="89539-179">Todos los mensajes de la conversación comparten el mismo documento anotado.</span><span class="sxs-lookup"><span data-stu-id="89539-179">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="89539-180">**Etiquetado:** Al ver conversaciones en un conjunto de revisión, puede ver y aplicar etiquetas haciendo clic en **el Panel de** etiquetado del Panel de codificación.</span><span class="sxs-lookup"><span data-stu-id="89539-180">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="89539-181">**Vuelva a ejecutar la conversión de conversación:** Cuando se agregan mensajes a un conjunto de revisión de conversación, se ejecuta automáticamente un trabajo de conversión para crear el resumen en secuencias y anotar vistas.</span><span class="sxs-lookup"><span data-stu-id="89539-181">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="89539-182">Si se produce un error en el trabajo de reconstrucción de conversación, puede volver a ejecutar este trabajo haciendo clic en Acción **> Crear** archivos PDF de conversación en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="89539-182">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>

#### <a name="exporting-conversations"></a><span data-ttu-id="89539-183">Exportar conversaciones</span><span class="sxs-lookup"><span data-stu-id="89539-183">Exporting conversations</span></span>

<span data-ttu-id="89539-184">En un conjunto de revisión de conversación, puede establecer las siguientes opciones para exportar conversaciones:</span><span class="sxs-lookup"><span data-stu-id="89539-184">In a conversation review set, you can set the following options to export conversations:</span></span>

![Opciones de exportación para conversaciones](../media/export.png)

<span data-ttu-id="89539-186">a.</span><span class="sxs-lookup"><span data-stu-id="89539-186">a.</span></span> <span data-ttu-id="89539-187">Opciones de metadatos</span><span class="sxs-lookup"><span data-stu-id="89539-187">Metadata options</span></span>

   - <span data-ttu-id="89539-188">**Cargar archivo:** Los metadatos se incluyen para cada mensaje, correo electrónico y documento individuales.</span><span class="sxs-lookup"><span data-stu-id="89539-188">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="89539-189">Hay una fila para cada mensaje en una conversación.</span><span class="sxs-lookup"><span data-stu-id="89539-189">There is one row for each message in a conversation.</span></span> 

   - <span data-ttu-id="89539-190">**Etiquetas:** Las etiquetas del proceso de revisión se incluyen en el archivo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="89539-190">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="89539-191">Los mensajes de una conversación comparten las mismas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="89539-191">Messages in a conversation share the same tags.</span></span> 

<span data-ttu-id="89539-192">b.</span><span class="sxs-lookup"><span data-stu-id="89539-192">b.</span></span> <span data-ttu-id="89539-193">Opciones de conversación</span><span class="sxs-lookup"><span data-stu-id="89539-193">Conversation options</span></span>
  
   - <span data-ttu-id="89539-194">**Archivos de conversación:** Al exportar archivos de conversación, la vista anotada se convierte en un archivo PDF y se descarga en la carpeta de exportación.</span><span class="sxs-lookup"><span data-stu-id="89539-194">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="89539-195">Los mensajes de un archivo de conversación apuntan a la versión PDF del mismo archivo de conversación.</span><span class="sxs-lookup"><span data-stu-id="89539-195">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>  
  
   - <span data-ttu-id="89539-196">**Mensajes de chat individuales:** Al exportar mensajes individuales, cada mensaje único de la conversación se exporta como un elemento independiente.</span><span class="sxs-lookup"><span data-stu-id="89539-196">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="89539-197">El archivo se exporta en el mismo formato que se guardó en el buzón.</span><span class="sxs-lookup"><span data-stu-id="89539-197">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="89539-198">Para una conversación específica, recibe varios archivos .msg.</span><span class="sxs-lookup"><span data-stu-id="89539-198">For a specific conversation, you receive multiple .msg files.</span></span> 

     >[!NOTE]
     > <span data-ttu-id="89539-199">Si aplicó anotaciones al archivo de conversación, estas anotaciones no se transferirán a los mensajes individuales.</span><span class="sxs-lookup"><span data-stu-id="89539-199">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span> 

<span data-ttu-id="89539-200">c.</span><span class="sxs-lookup"><span data-stu-id="89539-200">c.</span></span> <span data-ttu-id="89539-201">Otras opciones</span><span class="sxs-lookup"><span data-stu-id="89539-201">Other options</span></span>

   - <span data-ttu-id="89539-202">**Generar archivos de texto para todo el contenido exportado:** Genera un archivo de texto para cada conversación exportada desde el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="89539-202">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span> 

   - <span data-ttu-id="89539-203">**Reemplace el contenido exportado por archivos PDF redactados:** Si los archivos de conversación redactadas se generan durante el proceso de revisión, estos archivos están disponibles durante la exportación.</span><span class="sxs-lookup"><span data-stu-id="89539-203">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="89539-204">Puede decidir si exportar solo los archivos nativos (no seleccionando esta opción) o reemplazar los archivos nativos con las versiones redactadas de los archivos nativos (seleccionando esta opción), que se exportan como archivos PDF.</span><span class="sxs-lookup"><span data-stu-id="89539-204">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="89539-205">Más información</span><span class="sxs-lookup"><span data-stu-id="89539-205">More information</span></span>

<span data-ttu-id="89539-206">Para obtener más información sobre cómo revisar los datos de casos en eDiscovery avanzado, vea los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="89539-206">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="89539-207">Ver datos de casos</span><span class="sxs-lookup"><span data-stu-id="89539-207">View case data</span></span>](view-documents-in-review-set.md)

- [<span data-ttu-id="89539-208">Analizar datos de casos</span><span class="sxs-lookup"><span data-stu-id="89539-208">Analyze case data</span></span>](analyzing-data-in-review-set.md)

- [<span data-ttu-id="89539-209">Exportar datos de casos</span><span class="sxs-lookup"><span data-stu-id="89539-209">Export case data</span></span>](exporting-data-ediscover20.md)
