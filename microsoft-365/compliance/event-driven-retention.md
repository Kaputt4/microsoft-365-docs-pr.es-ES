---
title: Iniciar la retención cuando se produzca un evento
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: Por lo general, como parte de una solución de administración de registros, puede configurar una etiqueta para iniciar el período de retención en función de un evento identificado.
ms.openlocfilehash: 49fe330fa6844361a77caaebb0e6a411297ee643
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907020"
---
# <a name="start-retention-when-an-event-occurs"></a><span data-ttu-id="f3454-103">Iniciar la retención cuando se produzca un evento</span><span class="sxs-lookup"><span data-stu-id="f3454-103">Start retention when an event occurs</span></span>

><span data-ttu-id="f3454-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="f3454-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="f3454-p101">Al conservar contenido, el período de retención suele basarse en la antigüedad del contenido. Por ejemplo, puede conservar documentos durante siete años después de su creación y eliminarlos cuando transcurra ese período. Pero cuando configura [etiquetas de retención](retention.md#retention-labels), también puede hacer que un período de retención se base en el momento en que se produzca un tipo específico de evento. El evento desencadena el inicio del período de retención y se exigirán las acciones de retención de etiqueta en todo el contenido que tenga aplicada una etiqueta de retención para ese tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="f3454-p101">When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](retention.md#retention-labels), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="f3454-109">Ejemplos de uso de retención basada en eventos:</span><span class="sxs-lookup"><span data-stu-id="f3454-109">Examples for using event-based retention:</span></span>
  
- <span data-ttu-id="f3454-110">**Empleados que abandonan la organización** Imagine que tiene que conservar registros de empleados durante 10 años desde el momento en que un empleado abandona la organización.</span><span class="sxs-lookup"><span data-stu-id="f3454-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="f3454-111">Después de 10 años, se deberá eliminar todos los documentos relacionados con la contratación, la evaluación de rendimiento y la finalización de ese empleado.</span><span class="sxs-lookup"><span data-stu-id="f3454-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="f3454-112">El evento que desencadena el período de retención de 10 años es el empleado que abandona la organización.</span><span class="sxs-lookup"><span data-stu-id="f3454-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="f3454-113">**Expiración de contratos** Imagine que debe conservar todos los registros relacionados con un contrato cinco años después de que este expire.</span><span class="sxs-lookup"><span data-stu-id="f3454-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="f3454-114">El evento que desencadena el período de retención de cinco años es la expiración del contrato.</span><span class="sxs-lookup"><span data-stu-id="f3454-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="f3454-p104">**Vida útil del producto** Puede que su organización tenga requisitos de retención relacionados con la última fecha de fabricación de productos para contenido como especificaciones técnicas. En ese caso, la última fecha de fabricación es el evento que desencadena el período de retención.</span><span class="sxs-lookup"><span data-stu-id="f3454-p104">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="f3454-p105">La retención basada en eventos suele usarse como parte de un proceso de administración de registros. Esto quiere decir que:</span><span class="sxs-lookup"><span data-stu-id="f3454-p105">Event-based retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="f3454-119">Las etiquetas de retención basadas en eventos también suelen marcar los elementos como un registro, como parte de una solución de administración de registros.</span><span class="sxs-lookup"><span data-stu-id="f3454-119">Retention labels based on events also usually mark items as a record, as a part of a records management solution.</span></span> <span data-ttu-id="f3454-120">Para más información, vea [Más información sobre la administración de registros](records-management.md).</span><span class="sxs-lookup"><span data-stu-id="f3454-120">For more information, see [Learn about records management](records-management.md).</span></span>

- <span data-ttu-id="f3454-121">Un documento que se ha declarado como un registro, pero cuyo desencadenador de eventos aún no se ha producido, se conserva de manera indefinida (los registros no se pueden eliminar de forma permanente), hasta que un evento desencadene el período de retención del documento.</span><span class="sxs-lookup"><span data-stu-id="f3454-121">A document that's been declared a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="f3454-122">Las etiquetas de retención basadas en eventos suelen desencadenar una revisión de disposición al finalizar el período de retención, para que un administrador de registros pueda revisar de forma manual el contenido y eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="f3454-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="f3454-123">Para obtener más información, vea [ Eliminación de contenido](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="f3454-123">For more information, see [Disposition of content](disposition.md).</span></span>
    

<span data-ttu-id="f3454-124">Una etiqueta de retención basada en un evento tiene las mismas funciones que cualquier etiqueta de retención en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3454-124">A retention label based on an event has the same capabilities as any retention label in Microsoft 365.</span></span> <span data-ttu-id="f3454-125">Para obtener más información, vea [Información sobre las etiquetas y directivas de retención](retention.md).</span><span class="sxs-lookup"><span data-stu-id="f3454-125">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="f3454-126">Información sobre la relación entre tipos de evento, etiquetas, eventos e id. de activo</span><span class="sxs-lookup"><span data-stu-id="f3454-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="f3454-127">Para usar correctamente la retención basada en eventos, es importante comprender la relación entre tipos de evento, etiquetas de retención, eventos e id. de activos, tal como se muestra en los diagramas y en la siguiente explicación:</span><span class="sxs-lookup"><span data-stu-id="f3454-127">To successfully use event-based retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![Diagrama 1 de 2: tipo de evento, etiquetas, eventos e id. de activo](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Diagrama 2 de 2: tipo de evento, etiquetas, eventos e id. de activo](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="f3454-130">Puede crear etiquetas de retención para diferentes tipos de contenido y asociarlas a un tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="f3454-130">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="f3454-131">Por ejemplo, las etiquetas de retención para distintos tipos de registros y archivos de producto se asocian con un tipo de evento denominado Vida útil del producto, ya que esos registros tienen que conservarse durante 10 años desde el momento en que el producto alcanza el fin de vida.</span><span class="sxs-lookup"><span data-stu-id="f3454-131">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="f3454-132">Los usuarios (normalmente administradores de registros) aplican esas etiquetas de retención en el contenido y (para documentos SharePoint y OneDrive) escriben un id. de activo para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="f3454-132">Users (typically records managers) apply those retention labels to content and (for documents in SharePoint and OneDrive) enter an asset ID for each item.</span></span> <span data-ttu-id="f3454-133">En este ejemplo, el identificador de activo es un nombre de producto o un código usado por la organización.</span><span class="sxs-lookup"><span data-stu-id="f3454-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="f3454-134">Después, se asigna una etiqueta de retención a los registros de cada producto, y cada registro tiene una propiedad que contiene un id. de activo.</span><span class="sxs-lookup"><span data-stu-id="f3454-134">Then, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="f3454-135">El diagrama representa **todo el contenido** de todos los registros de productos de una organización, y cada elemento tiene asignado el id. de activo del producto al que pertenece el registro.</span><span class="sxs-lookup"><span data-stu-id="f3454-135">The diagram represents **all the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="f3454-p111">La vida útil del producto es el tipo de evento; un producto específico que llega al fin de su ciclo de vida es un evento. Cuando se produce este tipo de evento (en este caso, cuando un producto alcanza el fin de su ciclo de vida), creará un evento que especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f3454-p111">Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs—in this case, when a product reaches its end of life—you create an event that specifies:</span></span>
    
   - <span data-ttu-id="f3454-138">Un id. de activo (para documentos de OneDrive y SharePoint)</span><span class="sxs-lookup"><span data-stu-id="f3454-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
   - <span data-ttu-id="f3454-p112">Palabras clave (para elementos de Exchange). En este ejemplo, la organización usa un código de producto en mensajes que contengan registros de productos, para que la palabra clave de los elementos de Exchange coincida con el id. de activo para documentos de OneDrive y SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f3454-p112">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is functionally the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
   - <span data-ttu-id="f3454-p113">La fecha en que se produjo el evento. La fecha se usa como el inicio del período de retención. Esta fecha puede ser la fecha actual, una fecha pasada o una fecha futura.</span><span class="sxs-lookup"><span data-stu-id="f3454-p113">The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.</span></span>

4. <span data-ttu-id="f3454-144">Después de crear un evento, la fecha del evento se sincroniza con todo el contenido que tenga aplicada una etiqueta de retención de ese tipo de evento y que contenga la palabra clave o el id. de activo especificado.</span><span class="sxs-lookup"><span data-stu-id="f3454-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="f3454-145">Al igual que con cualquier etiqueta de retención, esta sincronización puede tardar hasta siete días en completarse.</span><span class="sxs-lookup"><span data-stu-id="f3454-145">Like any retention label, this synchronization can take up to seven days.</span></span> <span data-ttu-id="f3454-146">En el diagrama anterior, todos los elementos rodeados con un círculo rojo tienen el período de retención activado por este evento.</span><span class="sxs-lookup"><span data-stu-id="f3454-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="f3454-147">Es decir, cuando este producto llega al final de su vida, el evento provoca el período de retención de los registros del producto.</span><span class="sxs-lookup"><span data-stu-id="f3454-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>

<span data-ttu-id="f3454-148">Es importante comprender que, si no especifica palabras clave o un id. de activo para un evento, el evento desencadenará el período de retención de **todo el contenido** que tenga una etiqueta de retención de ese tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="f3454-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a retention label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="f3454-149">En el diagrama anterior, esto quiere decir que se empezaría a conservar todo el contenido.</span><span class="sxs-lookup"><span data-stu-id="f3454-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="f3454-150">Es posible que no sea esto lo que quiera realizar.</span><span class="sxs-lookup"><span data-stu-id="f3454-150">This might not be what you intend.</span></span>

<span data-ttu-id="f3454-151">Por último, recuerde que cada etiqueta de retención tiene sus propias opciones de retención.</span><span class="sxs-lookup"><span data-stu-id="f3454-151">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="f3454-152">En este ejemplo, todas especifican 10 años, pero puede que un evento desencadene etiquetas de retención donde cada etiqueta tenga un período de retención distinto.</span><span class="sxs-lookup"><span data-stu-id="f3454-152">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="f3454-153">Configurar la retención controlada por eventos</span><span class="sxs-lookup"><span data-stu-id="f3454-153">How to set up event-driven retention</span></span>

<span data-ttu-id="f3454-154">Flujo de trabajo general para la retención controlada por eventos:</span><span class="sxs-lookup"><span data-stu-id="f3454-154">High-level workflow for event-driven retention:</span></span>
  
![Diagrama del flujo de trabajo para configurar la retención controlada por eventos](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="f3454-156">Vea [Usar las etiquetas de retención para administrar el ciclo de vida de los documentos almacenados en SharePoint](auto-apply-retention-labels-scenario.md) para más información sobre cómo usar las propiedades administradas en SharePoint para aplicar automáticamente las etiquetas de retención e implementar la retención basada en eventos.</span><span class="sxs-lookup"><span data-stu-id="f3454-156">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="f3454-157">Paso 1: Crear una etiqueta cuyo período de retención se base en un evento</span><span class="sxs-lookup"><span data-stu-id="f3454-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="f3454-158">Para crear y configurar su etiqueta de retención, siga las instrucciones de [Crear y configurar las etiquetas de retención](./create-apply-retention-labels.md#create-and-configure-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="f3454-158">To create and configure your retention label, use the instructions from [Create and configure retention labels](./create-apply-retention-labels.md#create-and-configure-retention-labels).</span></span> <span data-ttu-id="f3454-159">Sin embargo, específicamente para la retención basada en eventos, en la página **Definir configuración de retención** del asistente de creación de etiquetas de retención, después **Iniciar el período de retención basado en eventos**, seleccione uno de los tipos de eventos predeterminados de la lista desplegable o cree el suyo propio seleccionando **Crear nuevo tipo de evento**:</span><span class="sxs-lookup"><span data-stu-id="f3454-159">But specific to event-based retention, on the **Define retention settings** page of the Create retention label wizard, after **Start the retention period based on**, select one of the default event types from the dropdown list, or create your own by selecting **Create new event type**:</span></span>

![Crear un nuevo tipo de evento para una etiqueta de retención](../media/SPRetention6.png)

<span data-ttu-id="f3454-161">Un tipo de evento es simplemente una descripción general de un evento al que desea asociar una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="f3454-161">An event type is simply a general description of an event that you want to associate with a retention label.</span></span>

<span data-ttu-id="f3454-162">Los tipos de sucesos predeterminados tienen **(tipo de evento)** después de su nombre en la lista desplegable para facilitar su identificación, y también puede ver y crear el tipo de evento desde la pestaña **Administración de registros** > **Eventos** > **Administrar tipos de eventos**.</span><span class="sxs-lookup"><span data-stu-id="f3454-162">The default event types have **(event type)** after their name in the dropdown list for easier identification, and you can also see and create event type from the **Records management** > **Events** tab > **Manage event types**.</span></span>

<span data-ttu-id="f3454-163">La retención basada en eventos necesita una configuración de retención que:</span><span class="sxs-lookup"><span data-stu-id="f3454-163">Event-based retention requires retention settings that:</span></span>
  
- <span data-ttu-id="f3454-164">Conserve el contenido.</span><span class="sxs-lookup"><span data-stu-id="f3454-164">Retain the content.</span></span>
    
- <span data-ttu-id="f3454-165">Elimine el contenido automáticamente o desencadene una revisión para eliminación al finalizar el período de retención.</span><span class="sxs-lookup"><span data-stu-id="f3454-165">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
  
<span data-ttu-id="f3454-166">La retención basada en eventos suele usarse para el contenido que se declara como registro, por lo que este es un buen momento para comprobar si también es necesario seleccionar la opción que marca el contenido como [registro](records-management.md#records).</span><span class="sxs-lookup"><span data-stu-id="f3454-166">Event-based retention is typically used for content that's declared a record, so this is a good time to check whether you also need to select the option that marks content as a [record](records-management.md#records).</span></span>

<span data-ttu-id="f3454-167">Si está usando un tipo de evento existente en lugar de crear un nuevo tipo de evento, vaya al paso 3.</span><span class="sxs-lookup"><span data-stu-id="f3454-167">If you're using an existing event type rather than creating a new event type, skip to step 3.</span></span>

> [!NOTE]
> <span data-ttu-id="f3454-168">Después de seleccionar un tipo de evento y guardar la etiqueta de retención, el tipo de evento no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="f3454-168">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>

### <a name="step-2-create-a-new-event-type-for-your-label"></a><span data-ttu-id="f3454-169">Paso 2: crear un nuevo tipo de evento para su etiqueta</span><span class="sxs-lookup"><span data-stu-id="f3454-169">Step 2: Create a new event type for your label</span></span>

<span data-ttu-id="f3454-170">Para la configuración de retención, si seleccionó **Crear nuevo tipo de evento**, escriba un nombre y una descripción para su tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="f3454-170">For the retention settings, if you selected **Create new event type**, enter a name and description for your event type.</span></span> <span data-ttu-id="f3454-171">Luego seleccione **Siguiente**, **Enviar** y **Listo**.</span><span class="sxs-lookup"><span data-stu-id="f3454-171">Then select **Next**, **Submit**, and **Done**.</span></span>

<span data-ttu-id="f3454-172">Regrese a la página **Definir la configuración de retención**, para **Iniciar el período de retención basado en eventos**, utilice la lista desplegable para seleccionar el tipo de evento que creó.</span><span class="sxs-lookup"><span data-stu-id="f3454-172">Back on the **Define retention settings** page, for **Start the retention period based on**, use the dropdown list to select the event type that you created.</span></span>

  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="f3454-173">Paso 3: Publicar o aplicar automáticamente las etiquetas de retención basadas en eventos</span><span class="sxs-lookup"><span data-stu-id="f3454-173">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="f3454-174">Al igual que las etiquetas de retención, debe publicar o aplicar automáticamente una etiqueta basada en eventos para que se aplique de forma manual o automática al contenido:</span><span class="sxs-lookup"><span data-stu-id="f3454-174">Just like any retention label, you need to publish or auto-apply an event-based label, for it to be manually or automatically applied to content:</span></span>
- [<span data-ttu-id="f3454-175">Crear etiquetas de retención y aplicarlas en aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f3454-175">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="f3454-176">Aplicar una etiqueta de retención automáticamente al contenido</span><span class="sxs-lookup"><span data-stu-id="f3454-176">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="f3454-177">Paso 4: Escribir un id. de activo</span><span class="sxs-lookup"><span data-stu-id="f3454-177">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="f3454-178">Después de aplicar una etiqueta basada en eventos al contenido, puede especificar un id. de activo para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="f3454-178">After an event-based label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="f3454-179">Por ejemplo, puede que su organización use:</span><span class="sxs-lookup"><span data-stu-id="f3454-179">For example, your organization might use:</span></span>
  
- <span data-ttu-id="f3454-180">Códigos de producto que puede usar para conservar contenido solo para un producto específico.</span><span class="sxs-lookup"><span data-stu-id="f3454-180">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="f3454-181">Códigos de proyecto que puede usar para conservar contenido solo para un proyecto específico.</span><span class="sxs-lookup"><span data-stu-id="f3454-181">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="f3454-182">Id. de empleado que puede usar para conservar contenido solo para una persona específica.</span><span class="sxs-lookup"><span data-stu-id="f3454-182">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="f3454-183">El Id. de activo es simplemente otra propiedad de documento disponible en SharePoint y OneDrive.</span><span class="sxs-lookup"><span data-stu-id="f3454-183">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="f3454-184">Es posible que la organización ya use otras propiedades del documento o id. para clasificar contenido.</span><span class="sxs-lookup"><span data-stu-id="f3454-184">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="f3454-185">En ese caso, puede usar esas propiedades y valores al crear un evento (vea el paso 6 más adelante).</span><span class="sxs-lookup"><span data-stu-id="f3454-185">If so, you can also use those properties and values when you create an event—see step 6 that follows.</span></span> <span data-ttu-id="f3454-186">Lo importante es que su organización tiene que usar alguna combinación de *propiedad:valor* en las propiedades del documento para asociar ese elemento con un tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="f3454-186">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![Cuadro de texto para especificar un id. de activo](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="f3454-188">Paso 5: Crear un evento</span><span class="sxs-lookup"><span data-stu-id="f3454-188">Step 5: Create an event</span></span>

<span data-ttu-id="f3454-189">Cuando se produzca una instancia específica de ese tipo de evento, como cuando un producto llega al final de su vida útil, vaya a la página **Administración de registros** > **Eventos** en el Centro de cumplimiento de Microsoft 365 y seleccione **+Crear** para crear un evento.</span><span class="sxs-lookup"><span data-stu-id="f3454-189">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center, and select **+ Create** to create an event.</span></span> <span data-ttu-id="f3454-190">Desencadena el evento creándolo, aquí.</span><span class="sxs-lookup"><span data-stu-id="f3454-190">You trigger the event by creating it, here.</span></span>

![Crear un evento para desencadenar el inicio de la retención para las etiquetas de retención basadas en eventos](../media/create-event-records-management.png)

<span data-ttu-id="f3454-192">Se admiten hasta 1 millón de eventos por espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="f3454-192">Up to one million events are supported per tenant.</span></span>

### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="f3454-193">Paso 6: seleccionar el mismo tipo de evento usado por la etiqueta en el paso 2</span><span class="sxs-lookup"><span data-stu-id="f3454-193">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="f3454-194">Cuando cree el evento, elija el mismo tipo de evento especificado en la configuración de la etiqueta de retención en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="f3454-194">When you create the event, choose the same event type specified in the retention label settings in step 2.</span></span> <span data-ttu-id="f3454-195">Por ejemplo, si seleccionó **Duración del producto** como tipo de evento para la configuración de la etiqueta, seleccione **Duración del producto** cuando cree el evento.</span><span class="sxs-lookup"><span data-stu-id="f3454-195">For example, if you selected **Product Lifetime** as your event type for the label settings, select **Product Lifetime** when you create the event.</span></span> <span data-ttu-id="f3454-196">Solo se desencadenará el período de retención del contenido que tenga aplicadas etiquetas de retención de ese tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="f3454-196">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>

![Opción en Configuración de evento para seleccionar un tipo de evento](../media/choose-event-type-records-management.png)

<span data-ttu-id="f3454-198">Por otra parte, si necesita crear un evento para múltiples etiquetas de retención que tienen diferentes tipos de eventos, seleccione la opción **Elegir etiquetas existentes**.</span><span class="sxs-lookup"><span data-stu-id="f3454-198">Alternatively, if you need to create an event for multiple retention labels that have different event types, select the **Choose Existing Labels** option.</span></span> <span data-ttu-id="f3454-199">Después, seleccione las etiquetas que están configuradas para los tipos de eventos que quiere asociar con este evento.</span><span class="sxs-lookup"><span data-stu-id="f3454-199">Then, select the labels that are configured for the event types you want to associate with this event.</span></span>

### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="f3454-200">Paso 7: Escribir las palabras clave o un id. de activo</span><span class="sxs-lookup"><span data-stu-id="f3454-200">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="f3454-201">Ahora, restrinja el ámbito del contenido. Para ello, especifique los id. de activo para el contenido de SharePoint y OneDrive, o las palabras clave para el contenido de Exchange.</span><span class="sxs-lookup"><span data-stu-id="f3454-201">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content, or keywords for Exchange content.</span></span> <span data-ttu-id="f3454-202">Para los id. de activo, la retención solo se aplicará en el contenido que tenga la combinación de *propiedad:valor* especificada.</span><span class="sxs-lookup"><span data-stu-id="f3454-202">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="f3454-203">Si no se especifica un id. de activo, se aplicará la misma fecha de retención a todo el contenido con etiquetas de ese tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="f3454-203">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="f3454-204">Por ejemplo: si usa la propiedad de id. de activo, escriba `ComplianceAssetID:<value>` en el cuadro de id. de activo que se muestra abajo.</span><span class="sxs-lookup"><span data-stu-id="f3454-204">For example: If you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="f3454-205">Puede que su organización aplicara otras propiedades e id. a los documentos relacionados con este tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="f3454-205">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="f3454-206">Por ejemplo, si necesita encontrar los registros de un producto específico, el id. puede ser una combinación de la propiedad personalizada “IdProducto” y el valor “XYZ”.</span><span class="sxs-lookup"><span data-stu-id="f3454-206">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="f3454-207">En este caso, escriba `ProductID:XYZ` en el cuadro de id. de activo que se muestra abajo.</span><span class="sxs-lookup"><span data-stu-id="f3454-207">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>
  
<span data-ttu-id="f3454-208">Paro los elementos de Exchange, use palabras clave.</span><span class="sxs-lookup"><span data-stu-id="f3454-208">For Exchange items, use keywords.</span></span> <span data-ttu-id="f3454-209">Puede usar una consulta con operadores de búsqueda como AND, OR y NOT.</span><span class="sxs-lookup"><span data-stu-id="f3454-209">You can use a query by using search operators such as AND, OR, and NOT.</span></span> <span data-ttu-id="f3454-210">Para obtener más información, vea [Consultas de palabras clave y condiciones de búsqueda para la Búsqueda de Contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="f3454-210">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="f3454-211">Por último, elija la fecha en la que se ha producido el evento, esta fecha se usa como inicio del periodo de retención.</span><span class="sxs-lookup"><span data-stu-id="f3454-211">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="f3454-212">Después de crear un evento, la fecha del evento se sincroniza con todo el contenido con una etiqueta de retención de ese tipo de evento, id. de activo y palabras clave.</span><span class="sxs-lookup"><span data-stu-id="f3454-212">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="f3454-213">Al igual que con cualquier etiqueta de retención, esta sincronización puede tardar hasta siete días en completarse.</span><span class="sxs-lookup"><span data-stu-id="f3454-213">As with any retention label, this synchronization can take up to seven days.</span></span>
  
![Página Configuración de evento](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="f3454-215">Después de crear un evento, la configuración de retención surte efecto para el contenido que ya está etiquetado e indexado.</span><span class="sxs-lookup"><span data-stu-id="f3454-215">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="f3454-216">Si se agrega la etiqueta de retención a contenido nuevo tras crear el evento, deberá crear un nuevo evento con los mismos detalles.</span><span class="sxs-lookup"><span data-stu-id="f3454-216">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="f3454-217">Al eliminar un evento, no se cancela la configuración de retención que está vigente en el contenido que ya está etiquetado.</span><span class="sxs-lookup"><span data-stu-id="f3454-217">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="f3454-218">Para ello, cree un nuevo evento con los mismos detalles, pero deje la fecha en blanco.</span><span class="sxs-lookup"><span data-stu-id="f3454-218">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="f3454-219">Usar Búsqueda de contenido para encontrar todo el contenido que tenga aplicada una etiqueta o id. de activo específicos</span><span class="sxs-lookup"><span data-stu-id="f3454-219">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="f3454-220">Después de asignar etiquetas de retención a contenido, puede usar la búsqueda de contenido para encontrar todo el contenido clasificado con una etiqueta de retención específica o que contiene un id. de activo específico:</span><span class="sxs-lookup"><span data-stu-id="f3454-220">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="f3454-221">Para encontrar todo el contenido con una etiqueta de retención específica, seleccione la condición **Etiqueta de retención** y, después, escriba el nombre de etiqueta completo o una parte del nombre de la etiqueta y use un comodín.</span><span class="sxs-lookup"><span data-stu-id="f3454-221">To find all content with a specific retention label, choose the **Retention label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="f3454-222">Para encontrar todo el contenido con un id. de activo específico, escriba la propiedad **ComplianceAssetID** y un valor con el formato `ComplianceAssetID:<value>`.</span><span class="sxs-lookup"><span data-stu-id="f3454-222">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="f3454-223">Para obtener más información, consulte [Consultas de palabras clave y condiciones de búsqueda para la Búsqueda de Contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="f3454-223">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="f3454-224">Automatizar eventos con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3454-224">Automate events by using PowerShell</span></span>

<span data-ttu-id="f3454-225">Puede usar un script de PowerShell para automatizar la retención basada en eventos desde sus aplicaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="f3454-225">You can use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="f3454-226">Los cmdlets de PowerShell disponibles para la retención basada en eventos son:</span><span class="sxs-lookup"><span data-stu-id="f3454-226">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="f3454-227">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="f3454-227">Get-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/get-complianceretentioneventtype)
    
- [<span data-ttu-id="f3454-228">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="f3454-228">New-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/new-complianceretentioneventtype)
    
- [<span data-ttu-id="f3454-229">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="f3454-229">Remove-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/remove-complianceretentioneventtype)
    
- [<span data-ttu-id="f3454-230">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="f3454-230">Set-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/set-complianceretentioneventtype)
    
- [<span data-ttu-id="f3454-231">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="f3454-231">Get-ComplianceRetentionEvent</span></span>](/powershell/module/exchange/get-complianceretentionevent)
    
- [<span data-ttu-id="f3454-232">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="f3454-232">New-ComplianceRetentionEvent</span></span>](/powershell/module/exchange/new-complianceretentionevent)
    

## <a name="automate-events-by-using-a-rest-api"></a><span data-ttu-id="f3454-233">Automatizar eventos mediante una API de REST</span><span class="sxs-lookup"><span data-stu-id="f3454-233">Automate events by using a REST API</span></span>

<span data-ttu-id="f3454-234">Puede usar una API de REST para crear automáticamente eventos que desencadenen el inicio del tiempo de retención.</span><span class="sxs-lookup"><span data-stu-id="f3454-234">You can use a REST API to automatically create the events that trigger the start of the retention time.</span></span>

<span data-ttu-id="f3454-235">Una API de REST es un punto de conexión de servicio que admite conjuntos de operaciones (métodos) HTTP, que proporcionan acceso de creación/recuperación/actualización/eliminación a los recursos del servicio.</span><span class="sxs-lookup"><span data-stu-id="f3454-235">A REST API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="f3454-236">Para obtener más información, vea [Componentes de una solicitud o respuesta de la API de REST](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="f3454-236">For more information, see [Components of a REST API request/response](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="f3454-237">Al usar la API de REST de Microsoft 365, se pueden crear y recuperar eventos mediante el uso de métodos POST y GET.</span><span class="sxs-lookup"><span data-stu-id="f3454-237">By using the Microsoft 365 REST API, events can be created and retrieved using the POST and GET methods.</span></span>

<span data-ttu-id="f3454-238">Hay dos opciones para usar la API de REST:</span><span class="sxs-lookup"><span data-stu-id="f3454-238">There are two options for using the REST API:</span></span>

- <span data-ttu-id="f3454-239">**Usar Microsoft Power Automate o una aplicación similar** para desencadenar un evento automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f3454-239">**Microsoft Power Automate or a similar application** to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="f3454-240">Microsoft Power Automate es un orquestador para conectarse a otros sistemas, por lo que no tiene que escribir una solución personalizada.</span><span class="sxs-lookup"><span data-stu-id="f3454-240">Microsoft Power Automate is an orchestrator for connecting to other systems, so you don't need to write a custom solution.</span></span> <span data-ttu-id="f3454-241">Para obtener más información, consulte el [sitio de Power Automate](https://flow.microsoft.com/es-ES/).</span><span class="sxs-lookup"><span data-stu-id="f3454-241">For more information, see the [Power Automate website](https://flow.microsoft.com/es-ES/).</span></span>

- <span data-ttu-id="f3454-242">**Usar PowerShell o un cliente HTTP para llamar a la API de REST** a fin de crear eventos con PowerShell (versión 6 o posterior), lo que forma parte de una solución personalizada.</span><span class="sxs-lookup"><span data-stu-id="f3454-242">**PowerShell or an HTTP client to call the REST API** to create events by using PowerShell (version 6 or later), which is part of a custom solution.</span></span>

<span data-ttu-id="f3454-243">Antes de usar la API de REST, como administrador global, confirme la dirección URL que se usará para la llamada al evento de retención.</span><span class="sxs-lookup"><span data-stu-id="f3454-243">Before you use the REST API, as a global administrator, confirm the URL to use for the retention event call.</span></span> <span data-ttu-id="f3454-244">Para ello, ejecute una llamada GET al evento de retención con la dirección URL de la API de REST:</span><span class="sxs-lookup"><span data-stu-id="f3454-244">To do this, run a GET retention event call by using the REST API URL:</span></span>

```console
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

<span data-ttu-id="f3454-245">Compruebe el código de respuesta.</span><span class="sxs-lookup"><span data-stu-id="f3454-245">Check the response code.</span></span> <span data-ttu-id="f3454-246">Si es 302, obtenga la URL redirigida de la propiedad Ubicación del encabezado de respuesta y use esa dirección URL en lugar de `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` en las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="f3454-246">If it's 302, get the redirected URL from the Location property of the response header and use that URL instead of `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in the instructions that follow.</span></span>

<span data-ttu-id="f3454-247">Los eventos que se crean automáticamente se pueden visualizar y confirmar en el Centro de cumplimiento de Microsoft 365 > **Administración de registros** >  **Eventos**.</span><span class="sxs-lookup"><span data-stu-id="f3454-247">The events that get automatically created can be confirmed by viewing them in the Microsoft 365 compliance center > **Records management** >  **Events**.</span></span>

### <a name="use-microsoft-power-automate-to-create-the-event"></a><span data-ttu-id="f3454-248">Usar Microsoft Power Automate para crear el evento</span><span class="sxs-lookup"><span data-stu-id="f3454-248">Use Microsoft Power Automate to create the event</span></span>

<span data-ttu-id="f3454-249">Cree un flujo que cree un evento mediante la API de REST de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="f3454-249">Create a flow that creates an event using the Microsoft 365 REST API:</span></span>

![Usar Flow para crear un evento](../media/automate-event-driven-retention-flow-1.png)

![Usar Flow para llamar a la API de REST](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a><span data-ttu-id="f3454-252">Crear un evento</span><span class="sxs-lookup"><span data-stu-id="f3454-252">Create an event</span></span>

<span data-ttu-id="f3454-253">Código de ejemplo para llamar a la API de REST:</span><span class="sxs-lookup"><span data-stu-id="f3454-253">Sample code to call the REST API:</span></span>

- <span data-ttu-id="f3454-254">**Método**: POST</span><span class="sxs-lookup"><span data-stu-id="f3454-254">**Method**: POST</span></span>
- <span data-ttu-id="f3454-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="f3454-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="f3454-256">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="f3454-256">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="f3454-257">**Body**:</span><span class="sxs-lookup"><span data-stu-id="f3454-257">**Body**:</span></span>
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
    
- <span data-ttu-id="f3454-258">**Autenticación**: Básica</span><span class="sxs-lookup"><span data-stu-id="f3454-258">**Authentication**: Basic</span></span>
- <span data-ttu-id="f3454-259">**Nombre de usuario**: “Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="f3454-259">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="f3454-260">**Contraseña**: “Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="f3454-260">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="f3454-261">Parámetros disponibles</span><span class="sxs-lookup"><span data-stu-id="f3454-261">Available parameters</span></span>


|<span data-ttu-id="f3454-262">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f3454-262">Parameters</span></span>|<span data-ttu-id="f3454-263">Description</span><span class="sxs-lookup"><span data-stu-id="f3454-263">Description</span></span>|<span data-ttu-id="f3454-264">Notas</span><span class="sxs-lookup"><span data-stu-id="f3454-264">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="f3454-265"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="f3454-265"><d:Name></d:Name></span></span>|<span data-ttu-id="f3454-266">Escriba un nombre único para el evento.</span><span class="sxs-lookup"><span data-stu-id="f3454-266">Provide a unique name for the event,</span></span>|<span data-ttu-id="f3454-267">No puede contener espacios finales ni los caracteres siguientes: % \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="f3454-267">Cannot contain trailing spaces or the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="f3454-268">, : ;</span><span class="sxs-lookup"><span data-stu-id="f3454-268">, : ;</span></span>|
|<span data-ttu-id="f3454-269"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="f3454-269"><d:EventType></d:EventType></span></span>|<span data-ttu-id="f3454-270">Escribe el nombre del tipo de evento (o Guid)</span><span class="sxs-lookup"><span data-stu-id="f3454-270">Enter event type name (or Guid),</span></span>|<span data-ttu-id="f3454-271">Ejemplo: "Recisión de contrato del empleado".</span><span class="sxs-lookup"><span data-stu-id="f3454-271">Example: "Employee termination".</span></span> <span data-ttu-id="f3454-272">El tipo de evento debe estar asociado con una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="f3454-272">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="f3454-273"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="f3454-273"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="f3454-274">Escriba "ComplianceAssetId:" + el id. del empleado</span><span class="sxs-lookup"><span data-stu-id="f3454-274">Enter "ComplianceAssetId:" + employee ID</span></span>|<span data-ttu-id="f3454-275">Ejemplo: "ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="f3454-275">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="f3454-276"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="f3454-276"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="f3454-277">Fecha y hora del evento</span><span class="sxs-lookup"><span data-stu-id="f3454-277">Event Date and Time</span></span>|<span data-ttu-id="f3454-278">Formato: aaaa-MM-ddTHH:mm:ssZ, ejemplo: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="f3454-278">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

###### <a name="response-codes"></a><span data-ttu-id="f3454-279">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="f3454-279">Response codes</span></span>

| <span data-ttu-id="f3454-280">Código de respuesta</span><span class="sxs-lookup"><span data-stu-id="f3454-280">Response Code</span></span> | <span data-ttu-id="f3454-281">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3454-281">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="f3454-282">302</span><span class="sxs-lookup"><span data-stu-id="f3454-282">302</span></span>               | <span data-ttu-id="f3454-283">Redirigir</span><span class="sxs-lookup"><span data-stu-id="f3454-283">Redirect</span></span>              |
| <span data-ttu-id="f3454-284">201</span><span class="sxs-lookup"><span data-stu-id="f3454-284">201</span></span>               | <span data-ttu-id="f3454-285">Fecha de creación</span><span class="sxs-lookup"><span data-stu-id="f3454-285">Created</span></span>               |
| <span data-ttu-id="f3454-286">403</span><span class="sxs-lookup"><span data-stu-id="f3454-286">403</span></span>               | <span data-ttu-id="f3454-287">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="f3454-287">Authorization Failed</span></span>  |
| <span data-ttu-id="f3454-288">401</span><span class="sxs-lookup"><span data-stu-id="f3454-288">401</span></span>               | <span data-ttu-id="f3454-289">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="f3454-289">Authentication Failed</span></span> |

##### <a name="get-events-based-on-a-time-range"></a><span data-ttu-id="f3454-290">Obtener eventos según un intervalo de tiempo</span><span class="sxs-lookup"><span data-stu-id="f3454-290">Get events based on a time range</span></span>

- <span data-ttu-id="f3454-291">**Método**: GET</span><span class="sxs-lookup"><span data-stu-id="f3454-291">**Method**: GET</span></span>

- <span data-ttu-id="f3454-292">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="f3454-292">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="f3454-293">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="f3454-293">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="f3454-294">**Autenticación**: Básica</span><span class="sxs-lookup"><span data-stu-id="f3454-294">**Authentication**: Basic</span></span>

- <span data-ttu-id="f3454-295">**Nombre de usuario**: “Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="f3454-295">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="f3454-296">**Contraseña**: “Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="f3454-296">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="f3454-297">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="f3454-297">Response codes</span></span>

| <span data-ttu-id="f3454-298">Código de respuesta</span><span class="sxs-lookup"><span data-stu-id="f3454-298">Response Code</span></span> | <span data-ttu-id="f3454-299">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3454-299">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="f3454-300">200</span><span class="sxs-lookup"><span data-stu-id="f3454-300">200</span></span>               | <span data-ttu-id="f3454-301">Aceptar, una lista de eventos de atom+ xml</span><span class="sxs-lookup"><span data-stu-id="f3454-301">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="f3454-302">404</span><span class="sxs-lookup"><span data-stu-id="f3454-302">404</span></span>               | <span data-ttu-id="f3454-303">No encontrado</span><span class="sxs-lookup"><span data-stu-id="f3454-303">Not found</span></span>                         |
| <span data-ttu-id="f3454-304">302</span><span class="sxs-lookup"><span data-stu-id="f3454-304">302</span></span>               | <span data-ttu-id="f3454-305">Redirigir</span><span class="sxs-lookup"><span data-stu-id="f3454-305">Redirect</span></span>                          |
| <span data-ttu-id="f3454-306">401</span><span class="sxs-lookup"><span data-stu-id="f3454-306">401</span></span>               | <span data-ttu-id="f3454-307">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="f3454-307">Authorization Failed</span></span>              |
| <span data-ttu-id="f3454-308">403</span><span class="sxs-lookup"><span data-stu-id="f3454-308">403</span></span>               | <span data-ttu-id="f3454-309">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="f3454-309">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="f3454-310">Obtén un objeto por id.</span><span class="sxs-lookup"><span data-stu-id="f3454-310">Get an event by ID</span></span>

- <span data-ttu-id="f3454-311">**Método**: GET</span><span class="sxs-lookup"><span data-stu-id="f3454-311">**Method**: GET</span></span>

- <span data-ttu-id="f3454-312">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="f3454-312">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="f3454-313">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="f3454-313">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="f3454-314">**Autenticación**: Básica</span><span class="sxs-lookup"><span data-stu-id="f3454-314">**Authentication**: Basic</span></span>

- <span data-ttu-id="f3454-315">**Nombre de usuario**: “Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="f3454-315">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="f3454-316">**Contraseña**: “Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="f3454-316">**Password**: "Compliancepassword"</span></span>

###### <a name="response-codes"></a><span data-ttu-id="f3454-317">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="f3454-317">Response codes</span></span>

| <span data-ttu-id="f3454-318">Código de respuesta</span><span class="sxs-lookup"><span data-stu-id="f3454-318">Response Code</span></span> | <span data-ttu-id="f3454-319">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3454-319">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="f3454-320">200</span><span class="sxs-lookup"><span data-stu-id="f3454-320">200</span></span>               | <span data-ttu-id="f3454-321">Aceptar, el cuerpo de la respuesta contiene el evento en atom+ xml</span><span class="sxs-lookup"><span data-stu-id="f3454-321">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="f3454-322">404</span><span class="sxs-lookup"><span data-stu-id="f3454-322">404</span></span>               | <span data-ttu-id="f3454-323">No encontrado</span><span class="sxs-lookup"><span data-stu-id="f3454-323">Not found</span></span>                                            |
| <span data-ttu-id="f3454-324">302</span><span class="sxs-lookup"><span data-stu-id="f3454-324">302</span></span>               | <span data-ttu-id="f3454-325">Redirigir</span><span class="sxs-lookup"><span data-stu-id="f3454-325">Redirect</span></span>                                             |
| <span data-ttu-id="f3454-326">401</span><span class="sxs-lookup"><span data-stu-id="f3454-326">401</span></span>               | <span data-ttu-id="f3454-327">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="f3454-327">Authorization Failed</span></span>                                 |
| <span data-ttu-id="f3454-328">403</span><span class="sxs-lookup"><span data-stu-id="f3454-328">403</span></span>               | <span data-ttu-id="f3454-329">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="f3454-329">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="f3454-330">Obtén un evento por nombre</span><span class="sxs-lookup"><span data-stu-id="f3454-330">Get an event by name</span></span>

- <span data-ttu-id="f3454-331">**Método**: GET</span><span class="sxs-lookup"><span data-stu-id="f3454-331">**Method**: GET</span></span>

- <span data-ttu-id="f3454-332">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="f3454-332">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="f3454-333">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="f3454-333">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="f3454-334">**Autenticación**: Básica</span><span class="sxs-lookup"><span data-stu-id="f3454-334">**Authentication**: Basic</span></span>

- <span data-ttu-id="f3454-335">**Nombre de usuario**: “Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="f3454-335">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="f3454-336">**Contraseña**: “Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="f3454-336">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="f3454-337">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="f3454-337">Response codes</span></span>

| <span data-ttu-id="f3454-338">Código de respuesta</span><span class="sxs-lookup"><span data-stu-id="f3454-338">Response Code</span></span> | <span data-ttu-id="f3454-339">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3454-339">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="f3454-340">200</span><span class="sxs-lookup"><span data-stu-id="f3454-340">200</span></span>               | <span data-ttu-id="f3454-341">Aceptar, el cuerpo de la respuesta contiene el evento en atom+ xml</span><span class="sxs-lookup"><span data-stu-id="f3454-341">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="f3454-342">404</span><span class="sxs-lookup"><span data-stu-id="f3454-342">404</span></span>               | <span data-ttu-id="f3454-343">No encontrado</span><span class="sxs-lookup"><span data-stu-id="f3454-343">Not found</span></span>                                            |
| <span data-ttu-id="f3454-344">302</span><span class="sxs-lookup"><span data-stu-id="f3454-344">302</span></span>               | <span data-ttu-id="f3454-345">Redirigir</span><span class="sxs-lookup"><span data-stu-id="f3454-345">Redirect</span></span>                                             |
| <span data-ttu-id="f3454-346">401</span><span class="sxs-lookup"><span data-stu-id="f3454-346">401</span></span>               | <span data-ttu-id="f3454-347">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="f3454-347">Authorization Failed</span></span>                                 |
| <span data-ttu-id="f3454-348">403</span><span class="sxs-lookup"><span data-stu-id="f3454-348">403</span></span>               | <span data-ttu-id="f3454-349">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="f3454-349">Authentication Failed</span></span>                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a><span data-ttu-id="f3454-350">Usar PowerShell o cualquier cliente HTTP para crear el evento</span><span class="sxs-lookup"><span data-stu-id="f3454-350">Use PowerShell or any HTTP client to create the event</span></span>

<span data-ttu-id="f3454-351">La versión de PowerShell debe ser 6 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f3454-351">PowerShell must be version 6 or later.</span></span>

<span data-ttu-id="f3454-352">En una sesión de PowerShell, ejecute el siguiente script:</span><span class="sxs-lookup"><span data-stu-id="f3454-352">In a PowerShell session, run the following script:</span></span>

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```