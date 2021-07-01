---
title: Revisar conversaciones en Advanced eDiscovery
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
description: Obtenga información sobre la característica de reconstrucción de conversación en Advanced eDiscovery (denominado subproceso de conversación) para reconstruir, revisar y exportar conversaciones de chat en Microsoft Teams y Yammer grupos.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9848280a7d6dbcbd6128fff06f150c8458f09701
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227192"
---
# <a name="conversation-threading-in-advanced-ediscovery"></a><span data-ttu-id="7286b-103">Subprocesos de conversación en Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7286b-103">Conversation threading in Advanced eDiscovery</span></span>

<span data-ttu-id="7286b-104">La mensajería instantánea es una forma cómoda de hacer preguntas, compartir ideas o comunicarse rápidamente entre grandes audiencias.</span><span class="sxs-lookup"><span data-stu-id="7286b-104">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="7286b-105">A medida que las plataformas de mensajería instantánea, como los grupos Microsoft Teams y Yammer, se convierten en el núcleo de la colaboración empresarial, las organizaciones deben evaluar cómo su flujo de trabajo de exhibición de documentos electrónicos aborda estas nuevas formas de comunicación y colaboración.</span><span class="sxs-lookup"><span data-stu-id="7286b-105">As instant messaging platforms, like Microsoft Teams and Yammer groups, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span>

<span data-ttu-id="7286b-106">La característica De reconstrucción de Advanced eDiscovery está diseñada para ayudarle a identificar contenido contextual y producir vistas de conversación distintas.</span><span class="sxs-lookup"><span data-stu-id="7286b-106">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="7286b-107">Esta funcionalidad le permite revisar de forma eficaz y rápida conversaciones de mensajes instantáneos completas (también denominadas conversaciones enhebradas) que se generan en plataformas como Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7286b-107">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="7286b-108">Con la reconstrucción de conversación, puede usar las funciones integradas para reconstruir, revisar y exportar conversaciones en subprocesos.</span><span class="sxs-lookup"><span data-stu-id="7286b-108">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="7286b-109">Use Advanced eDiscovery reconstrucción de conversación para:</span><span class="sxs-lookup"><span data-stu-id="7286b-109">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="7286b-110">Conserve metadatos únicos de nivel de mensaje en todos los mensajes de una conversación.</span><span class="sxs-lookup"><span data-stu-id="7286b-110">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="7286b-111">Recopilar mensajes contextuales alrededor de los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7286b-111">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="7286b-112">Revisar, anotar y redactar conversaciones enhebradas.</span><span class="sxs-lookup"><span data-stu-id="7286b-112">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="7286b-113">Exportar mensajes individuales o conversaciones en subprocesos</span><span class="sxs-lookup"><span data-stu-id="7286b-113">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="7286b-114">Terminología</span><span class="sxs-lookup"><span data-stu-id="7286b-114">Terminology</span></span>

<span data-ttu-id="7286b-115">Estas son algunas definiciones que le ayudarán a empezar a usar la reconstrucción de conversación.</span><span class="sxs-lookup"><span data-stu-id="7286b-115">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="7286b-116">**Mensajes:** Representa la unidad más pequeña de una conversación.</span><span class="sxs-lookup"><span data-stu-id="7286b-116">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="7286b-117">Los mensajes pueden variar en tamaño, estructura y metadatos.</span><span class="sxs-lookup"><span data-stu-id="7286b-117">Messages may vary in size, structure, and metadata.</span></span>

- <span data-ttu-id="7286b-118">**Conversación:** Representa una agrupación de uno o varios mensajes.</span><span class="sxs-lookup"><span data-stu-id="7286b-118">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="7286b-119">En diferentes aplicaciones, las conversaciones pueden representarse de diferentes maneras.</span><span class="sxs-lookup"><span data-stu-id="7286b-119">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="7286b-120">En algunas aplicaciones, hay una acción explícita que resulta de responder a un mensaje existente.</span><span class="sxs-lookup"><span data-stu-id="7286b-120">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="7286b-121">Las conversaciones se forman explícitamente como resultado de esta acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="7286b-121">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="7286b-122">Por ejemplo, esta es una captura de pantalla de una conversación de canal en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7286b-122">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Microsoft Teams Conversación de canal](../media/threadedchat.png)

   <span data-ttu-id="7286b-124">En otras aplicaciones (como los mensajes de chat de 1xN en Teams), no hay una cadena de respuesta formal y, en su lugar, los mensajes aparecen como un "río plano de mensajes" dentro de un único subproceso.</span><span class="sxs-lookup"><span data-stu-id="7286b-124">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="7286b-125">En estos tipos de aplicaciones, las conversaciones se deducen de un grupo de mensajes que se producen en un tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="7286b-125">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="7286b-126">Esta "agrupación suave" de mensajes (en lugar de una cadena de respuesta) representa la conversación "ida y vuelta" sobre un tema específico de interés.</span><span class="sxs-lookup"><span data-stu-id="7286b-126">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span>

## <a name="step-1-create-a-draft-collection"></a><span data-ttu-id="7286b-127">Paso 1: Crear una colección de borradores</span><span class="sxs-lookup"><span data-stu-id="7286b-127">Step 1: Create a draft collection</span></span>

<span data-ttu-id="7286b-128">Después de identificar los custodios relevantes y las ubicaciones de contenido, puede crear una búsqueda para buscar contenido potencialmente relevante.</span><span class="sxs-lookup"><span data-stu-id="7286b-128">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="7286b-129">En la **ficha Colecciones** del Advanced eDiscovery, puede crear una colección haciendo clic en **Nueva** colección y siguiendo el asistente.</span><span class="sxs-lookup"><span data-stu-id="7286b-129">On the **Collections** tab in the Advanced eDiscovery case, you can create a collection by clicking **New collection** and following the wizard.</span></span> <span data-ttu-id="7286b-130">Para obtener información sobre cómo crear una colección, crear una consulta de búsqueda y obtener una vista previa de los resultados de la [búsqueda,](create-draft-collection.md)vea Create a draft collection .</span><span class="sxs-lookup"><span data-stu-id="7286b-130">For information about how you can create a collection, build a search query, and preview the search results, see [Create a draft collection](create-draft-collection.md).</span></span>

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a><span data-ttu-id="7286b-131">Paso 2: Confirmar un borrador de colección en un conjunto de revisión</span><span class="sxs-lookup"><span data-stu-id="7286b-131">Step 2: Commit a draft collection to a review set</span></span>

<span data-ttu-id="7286b-132">Después de revisar y finalizar la consulta de búsqueda en una colección, puede agregar los resultados de búsqueda a un conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="7286b-132">After you have reviewed and finalized the search query in a collection, you can add the search results to a review set.</span></span> <span data-ttu-id="7286b-133">Al agregar los resultados de búsqueda a un conjunto de revisión, los datos originales se copian en un área de Azure Storage para facilitar el proceso de revisión y análisis.</span><span class="sxs-lookup"><span data-stu-id="7286b-133">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="7286b-134">Para obtener más información acerca de cómo agregar resultados de búsqueda a un conjunto de revisión, vea [Commit a draft collection to a review set](commit-draft-collection.md).</span><span class="sxs-lookup"><span data-stu-id="7286b-134">For more information about adding search results to a review set, see [Commit a draft collection to a review set](commit-draft-collection.md).</span></span>

<span data-ttu-id="7286b-135">Al agregar elementos de conversaciones a un conjunto de revisión, puede usar la opción conversaciones en subprocesos para recopilar mensajes contextuales de conversaciones que contienen elementos que coinciden con los criterios de búsqueda de la colección.</span><span class="sxs-lookup"><span data-stu-id="7286b-135">When you add items from conversations to a review set, you can use the threaded conversations option to collect contextual messages from conversations that contain items that match the search criteria of the collection.</span></span> <span data-ttu-id="7286b-136">Después de seleccionar la opción conversaciones de subprocesos, pueden suceder lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7286b-136">After you select the thread conversations option, the following things can happen:</span></span>

  ![Recuperación de conversaciones](../media/messagesandconversations.png)

1. <span data-ttu-id="7286b-138">Con una consulta de palabra clave y intervalo de fechas, la búsqueda devolvió un éxito en *el mensaje 3*.</span><span class="sxs-lookup"><span data-stu-id="7286b-138">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="7286b-139">Este mensaje formaba parte de una conversación más grande, ilustrada por *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="7286b-139">This message was part of a larger conversation, illustrated by *CRC1*.</span></span>

2. <span data-ttu-id="7286b-140">Al agregar los datos a un conjunto de revisión y habilitar las opciones de recuperación de conversaciones, Advanced eDiscovery volverá y recopilará otros elementos en *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="7286b-140">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span>

3. <span data-ttu-id="7286b-141">Después de agregar los elementos al conjunto de revisión, puede revisar todos los mensajes individuales de *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="7286b-141">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span>

<span data-ttu-id="7286b-142">Para habilitar la opción conversaciones enhebradas, vea [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set).</span><span class="sxs-lookup"><span data-stu-id="7286b-142">To enabled the threaded conversations option, see [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set).</span></span>

## <a name="step-3-review-and-export-threaded-conversations"></a><span data-ttu-id="7286b-143">Paso 3: Revisar y exportar conversaciones enhebradas</span><span class="sxs-lookup"><span data-stu-id="7286b-143">Step 3: Review and export threaded conversations</span></span>

<span data-ttu-id="7286b-144">Después de procesar y agregar el contenido al conjunto de revisión, puede empezar a revisar los datos del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="7286b-144">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="7286b-145">Las funcionalidades de revisión son diferentes en función de si el contenido se agregó a un conjunto de revisión estándar o a un conjunto de revisión de conversación.</span><span class="sxs-lookup"><span data-stu-id="7286b-145">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span>

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="7286b-146">Revisar conversaciones en un conjunto de revisión estándar</span><span class="sxs-lookup"><span data-stu-id="7286b-146">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="7286b-147">En un conjunto de revisión estándar, los mensajes se procesan y se muestran como elementos individuales, de forma similar a como se almacenan en una carpeta de buzones.</span><span class="sxs-lookup"><span data-stu-id="7286b-147">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="7286b-148">En este flujo de trabajo, cada mensaje se procesa como un elemento independiente.</span><span class="sxs-lookup"><span data-stu-id="7286b-148">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="7286b-149">Como resultado, las opciones de resumen y exportación en subprocesos no están disponibles en un conjunto de revisión estándar.</span><span class="sxs-lookup"><span data-stu-id="7286b-149">As a result, the threaded summary and export options aren't available in a standard review set.</span></span>

  ![Conjunto de revisión estándar](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="7286b-151">Revisión de conversaciones en un conjunto de revisión de conversación</span><span class="sxs-lookup"><span data-stu-id="7286b-151">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="7286b-152">En un conjunto de revisión de conversación, los mensajes individuales se enhebran y se presentan como conversaciones.</span><span class="sxs-lookup"><span data-stu-id="7286b-152">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="7286b-153">Esto le permite revisar y exportar conversaciones contextuales.</span><span class="sxs-lookup"><span data-stu-id="7286b-153">This lets you review and export contextual conversations.</span></span>

  ![Conjunto de revisión de conversación](../media/ConversationRSOptions.PNG)

<span data-ttu-id="7286b-155">En las secciones siguientes se describe la revisión y exportación de conversaciones en un conjunto de revisión de conversación.</span><span class="sxs-lookup"><span data-stu-id="7286b-155">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="7286b-156">Revisión de conversaciones</span><span class="sxs-lookup"><span data-stu-id="7286b-156">Reviewing conversations</span></span>

<span data-ttu-id="7286b-157">En un conjunto de revisión de conversación, puede usar las siguientes opciones para facilitar el proceso de revisión.</span><span class="sxs-lookup"><span data-stu-id="7286b-157">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="7286b-158">**Agrupar por conversación:** Agrupa mensajes dentro de la misma conversación para ayudar a los usuarios a simplificar y acelerar su proceso de revisión.</span><span class="sxs-lookup"><span data-stu-id="7286b-158">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span>

- <span data-ttu-id="7286b-159">**Vista de resumen:** Muestra la conversación enhebrada.</span><span class="sxs-lookup"><span data-stu-id="7286b-159">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="7286b-160">En esta vista, puede ver toda la conversación y también tener acceso a los metadatos de cada mensaje individual.</span><span class="sxs-lookup"><span data-stu-id="7286b-160">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>

   - <span data-ttu-id="7286b-161">Ver metadatos de mensajes individuales</span><span class="sxs-lookup"><span data-stu-id="7286b-161">View metadata for individual messages</span></span>

   - <span data-ttu-id="7286b-162">Descargar mensajes individuales</span><span class="sxs-lookup"><span data-stu-id="7286b-162">Download individual messages</span></span>

- <span data-ttu-id="7286b-163">**Vista texto:** Proporciona el texto extraído para toda la conversación.</span><span class="sxs-lookup"><span data-stu-id="7286b-163">**Text view:** Provides the extracted text for the entire conversation.</span></span>

- <span data-ttu-id="7286b-164">**Vista Anotar:** Permite marcar una vista de subproceso de la conversación.</span><span class="sxs-lookup"><span data-stu-id="7286b-164">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="7286b-165">Todos los mensajes de la conversación comparten el mismo documento anotado.</span><span class="sxs-lookup"><span data-stu-id="7286b-165">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="7286b-166">**Etiquetado:** Al ver conversaciones en un conjunto de revisión, puede ver y aplicar etiquetas haciendo clic en **Panel de** etiquetado en el panel Codificación.</span><span class="sxs-lookup"><span data-stu-id="7286b-166">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="7286b-167">**Volver a ejecutar la conversión de conversación:** Cuando se agregan mensajes a un conjunto de revisión de conversación, se ejecuta automáticamente un trabajo de conversión para crear el resumen enhebrado y anotar vistas.</span><span class="sxs-lookup"><span data-stu-id="7286b-167">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="7286b-168">Si se produce un error en el trabajo de reconstrucción de conversación, puede volver a ejecutar este trabajo haciendo clic en Acción **> Crear archivos PDF de** conversación en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="7286b-168">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>

#### <a name="exporting-conversations"></a><span data-ttu-id="7286b-169">Exportar conversaciones</span><span class="sxs-lookup"><span data-stu-id="7286b-169">Exporting conversations</span></span>

<span data-ttu-id="7286b-170">En un conjunto de revisión de conversación, puede establecer las siguientes opciones para exportar conversaciones:</span><span class="sxs-lookup"><span data-stu-id="7286b-170">In a conversation review set, you can set the following options to export conversations:</span></span>

![Exportar opciones para conversaciones](../media/export.png)

1. <span data-ttu-id="7286b-172">Opciones de metadatos:</span><span class="sxs-lookup"><span data-stu-id="7286b-172">Metadata options:</span></span>
   - <span data-ttu-id="7286b-173">**Cargar archivo:** Los metadatos se incluyen para cada mensaje individual, correo electrónico y documento.</span><span class="sxs-lookup"><span data-stu-id="7286b-173">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="7286b-174">Hay una fila para cada mensaje de una conversación.</span><span class="sxs-lookup"><span data-stu-id="7286b-174">There is one row for each message in a conversation.</span></span>
   - <span data-ttu-id="7286b-175">**Etiquetas:** Las etiquetas del proceso de revisión se incluyen en el archivo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="7286b-175">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="7286b-176">Los mensajes de una conversación comparten las mismas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="7286b-176">Messages in a conversation share the same tags.</span></span>

2. <span data-ttu-id="7286b-177">Opciones de conversación:</span><span class="sxs-lookup"><span data-stu-id="7286b-177">Conversation options:</span></span>
   - <span data-ttu-id="7286b-178">**Archivos de conversación:** Al exportar archivos de conversación, la vista anotada se convierte en un archivo PDF y se descarga en la carpeta de exportación.</span><span class="sxs-lookup"><span data-stu-id="7286b-178">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="7286b-179">Los mensajes de un archivo de conversación apuntan a la versión PDF del mismo archivo de conversación.</span><span class="sxs-lookup"><span data-stu-id="7286b-179">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>
   - <span data-ttu-id="7286b-180">**Mensajes de chat individuales:** Al exportar mensajes individuales, cada mensaje único de la conversación se exporta como un elemento independiente.</span><span class="sxs-lookup"><span data-stu-id="7286b-180">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="7286b-181">El archivo se exporta en el mismo formato que se guardó en el buzón.</span><span class="sxs-lookup"><span data-stu-id="7286b-181">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="7286b-182">Para una conversación específica, recibe varios archivos .msg.</span><span class="sxs-lookup"><span data-stu-id="7286b-182">For a specific conversation, you receive multiple .msg files.</span></span>

     > [!NOTE]
     > <span data-ttu-id="7286b-183">Si aplicó anotaciones al archivo de conversación, estas anotaciones no se transferirán a los mensajes individuales.</span><span class="sxs-lookup"><span data-stu-id="7286b-183">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span>

3. <span data-ttu-id="7286b-184">Otras opciones:</span><span class="sxs-lookup"><span data-stu-id="7286b-184">Other options:</span></span>
   - <span data-ttu-id="7286b-185">**Generar archivos de texto para todo el contenido exportado:** Genera un archivo de texto para cada conversación exportada desde el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="7286b-185">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span>
   - <span data-ttu-id="7286b-186">**Reemplace el contenido exportado por archivos PDF redactados:** Si los archivos de conversación redactadas se generan durante el proceso de revisión, estos archivos estarán disponibles durante la exportación.</span><span class="sxs-lookup"><span data-stu-id="7286b-186">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="7286b-187">Puede decidir si desea exportar solo los archivos nativos (no seleccionando esta opción) o reemplazar los archivos nativos por las versiones redactadas de los archivos nativos (seleccionando esta opción), que se exportan como archivos PDF.</span><span class="sxs-lookup"><span data-stu-id="7286b-187">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="7286b-188">Más información</span><span class="sxs-lookup"><span data-stu-id="7286b-188">More information</span></span>

<span data-ttu-id="7286b-189">Para obtener más información sobre cómo revisar los datos de casos Advanced eDiscovery, vea los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="7286b-189">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="7286b-190">Ver datos de casos</span><span class="sxs-lookup"><span data-stu-id="7286b-190">View case data</span></span>](view-documents-in-review-set.md)
- [<span data-ttu-id="7286b-191">Analizar datos de casos</span><span class="sxs-lookup"><span data-stu-id="7286b-191">Analyze case data</span></span>](analyzing-data-in-review-set.md)
- [<span data-ttu-id="7286b-192">Exportar datos de casos</span><span class="sxs-lookup"><span data-stu-id="7286b-192">Export case data</span></span>](exporting-data-ediscover20.md)
