---
title: Ver los resultados de ANALYZE en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: Comprenda dónde ver los resultados del proceso de análisis en la exhibición avanzada de documentos electrónicos, incluidas las definiciones de las opciones de tarea mostradas.
ms.openlocfilehash: 64c91cb5929a7a74e53d653faff98d5792d3f131
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663264"
---
# <a name="view-analyze-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="e5c1b-103">Ver los resultados de ANALYZE en eDiscovery avanzado (clásico)</span><span class="sxs-lookup"><span data-stu-id="e5c1b-103">View Analyze results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="e5c1b-p101">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="e5c1b-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="e5c1b-106">En la exhibición avanzada de documentos electrónicos, el progreso y los resultados del proceso de análisis se pueden ver en varias pantallas, como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-106">In Advanced eDiscovery, progress and results for the Analyze process can be viewed in a variety of displays as described below.</span></span>
  
## <a name="view-analyze-task-status"></a><span data-ttu-id="e5c1b-107">Ver el estado de la tarea de análisis</span><span class="sxs-lookup"><span data-stu-id="e5c1b-107">View Analyze task status</span></span>

<span data-ttu-id="e5c1b-108">En **preparar el estado de la tarea de \> \> resultados \> del análisis**, el estado se muestra durante y después de analizar la ejecución del proceso.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-108">In **Prepare \> Analyze \> Results \> Task status**, the status is displayed during and after Analyze process execution.</span></span> 
  
![Analizar el estado de la tarea](../media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
<span data-ttu-id="e5c1b-110">Las tareas mostradas pueden variar en función de las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-110">The tasks displayed may vary depending on the options selected.</span></span> 
  
- <span data-ttu-id="e5c1b-111">**ND/et: Setup**: se prepara para la ejecución, por ejemplo, establece los parámetros Run y case.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-111">**ND/ET: setup**: Prepares for the run, for example, sets run and case parameters.</span></span>
    
- <span data-ttu-id="e5c1b-112">**ND/et: ND Calculation**: procesa el análisis de archivos casi duplicados.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-112">**ND/ET: ND calculation**: Processes Near-duplicate analysis of files.</span></span>
    
- <span data-ttu-id="e5c1b-113">**ND-et: et Calculation**: realiza análisis de subprocesos de correo electrónico en todo el conjunto de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-113">**ND/ET: ET calculation**: Performs Email Thread analysis on the entire email set.</span></span>
    
- <span data-ttu-id="e5c1b-114">**ND/et: tablas dinámicas y similitudes**: realiza el procesamiento de similitudes de archivos y tablas dinámicas.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-114">**ND/ET: pivots and similarities**: Performs pivot and file similarity processing.</span></span>
    
- <span data-ttu-id="e5c1b-115">**ND/et: metadatos Update**: finaliza los nuevos datos recopilados en los archivos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-115">**ND/ET: metadata update**: Finalizes the new data collected on the files in the database.</span></span>
    
- <span data-ttu-id="e5c1b-116">**Temas: cálculo de temas**: ejecuta el análisis de temas.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-116">**Themes: themes calculation**: Runs themes analysis.</span></span> <span data-ttu-id="e5c1b-117">(Solo se muestra si está seleccionado).</span><span class="sxs-lookup"><span data-stu-id="e5c1b-117">(Displayed only if selected.)</span></span>
    
- <span data-ttu-id="e5c1b-118">**Estado** de la tarea: esta línea se muestra después de la finalización de la tarea.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-118">**Task status**: This line is displayed after task completion.</span></span> <span data-ttu-id="e5c1b-119">Mientras se ejecutan las tareas, se muestra la duración de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-119">While tasks are running, run duration is displayed.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e5c1b-120">Los resultados del análisis de casi duplicados y subprocesos de correo electrónico (ND y ED) se aplican al número de documentos que se van a procesar.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-120">The Analyze results of Near-duplicates and Email Threads (ND and ED) applies to the number of documents to be processed.</span></span> <span data-ttu-id="e5c1b-121">No incluye los archivos duplicados exactos.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-121">It does not include Exact duplicate files.</span></span> 
  
## <a name="view-near-duplicates-and-email-threads-status"></a><span data-ttu-id="e5c1b-122">Ver el estado de subprocesos Near-duplicados y correo electrónico</span><span class="sxs-lookup"><span data-stu-id="e5c1b-122">View Near-duplicates and Email Threads status</span></span>

<span data-ttu-id="e5c1b-123">Los resultados de la población de **destino** muestran el número de documentos, mensajes de correo electrónico, datos adjuntos y errores en el rellenado de destino.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-123">The **Target** population results display the number of documents, emails, attachments, and errors in the target population.</span></span> 
  
<span data-ttu-id="e5c1b-124">Los resultados de los **documentos** muestran el número de elementos dinámicos, los únicos casi duplicados y los archivos duplicados exactos.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-124">The **Documents** results display the number of pivots, unique near-duplicates, and exact duplicate files.</span></span> 
  
<span data-ttu-id="e5c1b-125">Los resultados de los **mensajes** de correo electrónico muestran el número de copias inclusivas inclusivas inclusive, únicas y exclusivas, así como el resto de los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-125">The **Emails** results display the number of inclusive, inclusive minus, unique inclusive copies, and the rest of the email messages.</span></span> <span data-ttu-id="e5c1b-126">Los diferentes tipos de resultados de correo electrónico son:</span><span class="sxs-lookup"><span data-stu-id="e5c1b-126">The different types of email results are:</span></span> 
  
- <span data-ttu-id="e5c1b-127">**Inclusive**: un correo electrónico inclusivo es el nodo de terminación en un hilo de correo electrónico y contiene todo el historial anterior de ese hilo.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-127">**Inclusive**: An inclusive email is the terminating node in an email thread and contains all the previous history of that thread.</span></span> <span data-ttu-id="e5c1b-128">Como resultado, el revisor puede centrarse de forma segura en el correo electrónico inclusivo, sin necesidad de leer los mensajes anteriores en el hilo.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-128">As a result, the reviewer can safely focus on the inclusive email, without the need to read the previous messages in the thread.</span></span> 
    
- <span data-ttu-id="e5c1b-129">**Impuestos incluidos**: un correo electrónico inclusivo se designa como inclusivo menos si hay uno o varios datos adjuntos diferentes asociados con los elementos primarios del mensaje inclusivo.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-129">**Inclusive minus**: An inclusive email is designated as inclusive minus if there are one or more different attachments associated with the parents of the inclusive message.</span></span> <span data-ttu-id="e5c1b-130">En este contexto, el término "primario" se usa para los mensajes ubicados hacia arriba en la conversación de correo electrónico o conversaciones incluidas en ese correo electrónico específico inclusivo.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-130">In this context, the term Parent is used for messages located upwards on the email thread or conversations included in that specific inclusive email.</span></span> <span data-ttu-id="e5c1b-131">Un revisor puede usar la indicación de menos inclusivo como una señal que, aunque puede que no sea necesario revisar el contenido de los elementos primarios de correo electrónico inclusivos, puede resultar útil revisar los datos adjuntos asociados a los elementos principales de la ruta de acceso inclusiva.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-131">A reviewer can use the inclusive minus indication as a signal that although it might not be necessary to review the content of the inclusive email parents, it may be useful to review the attachments associated with the inclusive path parents.</span></span> 
    
- <span data-ttu-id="e5c1b-132">**Copia inclusiva**: los correos electrónicos inclusivos se designan como copia inclusiva si es la copia de otro mensaje marcada como un signo menos inclusivo o inclusivo.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-132">**Inclusive copy**: An inclusive email is designated as inclusive copy if it's the copy of another message marked as inclusive or inclusive minus.</span></span> <span data-ttu-id="e5c1b-133">Es decir, este mensaje tiene el mismo asunto y el mismo cuerpo que otro mensaje inclusivo y, como tal, coexiste en el mismo nodo.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-133">In other words, this message has the same subject and body as another inclusive message and, as such, co-resides in the same node.</span></span> <span data-ttu-id="e5c1b-134">Como los mensajes de copia inclusivos contienen el mismo contenido, normalmente se pueden omitir en el proceso de revisión.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-134">Because inclusive copy messages contain the same content, they can usually be skipped in the review process.</span></span> 
    
- <span data-ttu-id="e5c1b-135">**El resto**: indica el correo electrónico que no contiene ningún contenido único y, por lo tanto, no se incluye en ninguna de las tres categorías anteriores.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-135">**The rest**: This indicates email that doesn't contain any unique content, and therefore doesn't fall into any of the previous three categories.</span></span> <span data-ttu-id="e5c1b-136">No es necesario revisar estos mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-136">These email messages don't need to be reviewed.</span></span> <span data-ttu-id="e5c1b-137">Si un mensaje contiene datos adjuntos que no están en un correo electrónico inclusivo posterior, es posible que sea necesario revisar los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-137">If a message contains an attachment that isn't on a later inclusive email, then the attachment might need to be reviewed.</span></span> <span data-ttu-id="e5c1b-138">Esto se indica mediante la existencia de un correo electrónico menos inclusivo dentro del hilo.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-138">This is indicated by the existence of an inclusive minus email within the thread.</span></span>
    
<span data-ttu-id="e5c1b-139">Los resultados de los **datos adjuntos** muestran el número de datos adjuntos, según el tipo único y duplicados.</span><span class="sxs-lookup"><span data-stu-id="e5c1b-139">The **Attachments** results display the number of attachments, according to such type as unique and duplicates.</span></span> 
  
![Casi duplicados y subprocesos de correo electrónico](../media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a><span data-ttu-id="e5c1b-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5c1b-141">See also</span></span>

[<span data-ttu-id="e5c1b-142">Advanced eDiscovery (clásico)</span><span class="sxs-lookup"><span data-stu-id="e5c1b-142">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="e5c1b-143">Descripción de la similitud de documentos</span><span class="sxs-lookup"><span data-stu-id="e5c1b-143">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="e5c1b-144">Configuración de las opciones de análisis</span><span class="sxs-lookup"><span data-stu-id="e5c1b-144">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="e5c1b-145">Configuración de omitir texto</span><span class="sxs-lookup"><span data-stu-id="e5c1b-145">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="e5c1b-146">Configuración de la configuración avanzada de análisis</span><span class="sxs-lookup"><span data-stu-id="e5c1b-146">Setting Analyze advanced settings</span></span>](view-analyze-results-in-advanced-ediscovery.md)

