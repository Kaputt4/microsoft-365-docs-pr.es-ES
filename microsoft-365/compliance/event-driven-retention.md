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
ms.openlocfilehash: e5b3b1f5d3af8185c424abede2f31675ab854f4a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287532"
---
# <a name="start-retention-when-an-event-occurs"></a><span data-ttu-id="31066-103">Iniciar la retención cuando se produzca un evento</span><span class="sxs-lookup"><span data-stu-id="31066-103">Start retention when an event occurs</span></span>

><span data-ttu-id="31066-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="31066-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="31066-p101">Al conservar contenido, el período de retención suele basarse en la antigüedad del contenido. Por ejemplo, puede conservar documentos durante siete años después de su creación y eliminarlos cuando transcurra ese período. Pero cuando configura [etiquetas de retención](retention.md#retention-labels), también puede hacer que un período de retención se base en el momento en que se produzca un tipo específico de evento. El evento desencadena el inicio del período de retención y se exigirán las acciones de retención de etiqueta en todo el contenido que tenga aplicada una etiqueta de retención para ese tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="31066-p101">When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](retention.md#retention-labels), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="31066-109">Ejemplos de uso de retención basada en eventos:</span><span class="sxs-lookup"><span data-stu-id="31066-109">Examples for using event-based retention:</span></span>
  
- <span data-ttu-id="31066-110">**Empleados que abandonan la organización** Imagine que tiene que conservar registros de empleados durante 10 años desde el momento en que un empleado abandona la organización.</span><span class="sxs-lookup"><span data-stu-id="31066-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="31066-111">Después de 10 años, se deberá eliminar todos los documentos relacionados con la contratación, la evaluación de rendimiento y la finalización de ese empleado.</span><span class="sxs-lookup"><span data-stu-id="31066-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="31066-112">El evento que desencadena el período de retención de 10 años es el empleado que abandona la organización.</span><span class="sxs-lookup"><span data-stu-id="31066-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="31066-113">**Expiración de contratos** Imagine que debe conservar todos los registros relacionados con un contrato cinco años después de que este expire.</span><span class="sxs-lookup"><span data-stu-id="31066-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="31066-114">El evento que desencadena el período de retención de cinco años es la expiración del contrato.</span><span class="sxs-lookup"><span data-stu-id="31066-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="31066-p104">**Vida útil del producto** Puede que su organización tenga requisitos de retención relacionados con la última fecha de fabricación de productos para contenido como especificaciones técnicas. En ese caso, la última fecha de fabricación es el evento que desencadena el período de retención.</span><span class="sxs-lookup"><span data-stu-id="31066-p104">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="31066-p105">La retención basada en eventos suele usarse como parte de un proceso de administración de registros. Esto quiere decir que:</span><span class="sxs-lookup"><span data-stu-id="31066-p105">Event-based retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="31066-119">Las etiquetas de retención basadas en eventos también suelen marcar los elementos como un registro, como parte de una solución de administración de registros.</span><span class="sxs-lookup"><span data-stu-id="31066-119">Retention labels based on events also usually mark items as a record, as a part of a records management solution.</span></span> <span data-ttu-id="31066-120">Para más información, vea [Más información sobre la administración de registros](records-management.md).</span><span class="sxs-lookup"><span data-stu-id="31066-120">For more information, see [Learn about records management](records-management.md).</span></span>

- <span data-ttu-id="31066-121">Un documento que se ha declarado como un registro, pero cuyo desencadenador de eventos aún no se ha producido, se conserva de manera indefinida (los registros no se pueden eliminar de forma permanente), hasta que un evento desencadene el período de retención del documento.</span><span class="sxs-lookup"><span data-stu-id="31066-121">A document that's been declared a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="31066-122">Las etiquetas de retención basadas en eventos suelen desencadenar una revisión de disposición al finalizar el período de retención, para que un administrador de registros pueda revisar de forma manual el contenido y eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="31066-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="31066-123">Para obtener más información, vea [ Eliminación de contenido](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="31066-123">For more information, see [Disposition of content](disposition.md).</span></span>
    

<span data-ttu-id="31066-124">Una etiqueta de retención basada en un evento tiene las mismas funciones que cualquier etiqueta de retención en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31066-124">A retention label based on an event has the same capabilities as any retention label in Microsoft 365.</span></span> <span data-ttu-id="31066-125">Para obtener más información, vea [Información sobre las etiquetas y directivas de retención](retention.md).</span><span class="sxs-lookup"><span data-stu-id="31066-125">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="31066-126">Información sobre la relación entre tipos de evento, etiquetas, eventos e id. de activo</span><span class="sxs-lookup"><span data-stu-id="31066-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="31066-127">Para usar correctamente la retención basada en eventos, es importante comprender la relación entre tipos de evento, etiquetas de retención, eventos e id. de activos, tal como se muestra en los diagramas y en la siguiente explicación:</span><span class="sxs-lookup"><span data-stu-id="31066-127">To successfully use event-based retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![Diagrama 1 de 2: tipo de evento, etiquetas, eventos e id. de activo](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Diagrama 2 de 2: tipo de evento, etiquetas, eventos e id. de activo](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="31066-p109">Las etiquetas de retención se crean para distintos tipos de contenido y, después, se asocian con un tipo de evento. Por ejemplo, las etiquetas de retención para distintos tipos de registros y archivos de producto se asocian con un tipo de evento denominado “Vida útil del producto”, ya que esos registros tienen que conservarse durante 10 años desde el momento en que el producto alcanza el final de su ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="31066-p109">You create retention labels for different types of content and then associate them with a type of event. For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="31066-132">Los usuarios (normalmente administradores de registros) aplican esas etiquetas de retención en el contenido y (para documentos SharePoint y OneDrive) escriben un id. de activo para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="31066-132">Users (typically records managers) apply those retention labels to content and (for documents in SharePoint and OneDrive) enter an asset ID for each item.</span></span> <span data-ttu-id="31066-133">En este ejemplo, el identificador de activo es un nombre de producto o un código usado por la organización.</span><span class="sxs-lookup"><span data-stu-id="31066-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="31066-134">Después, se asigna una etiqueta de retención a los registros de cada producto, y cada registro tiene una propiedad que contiene un id. de activo.</span><span class="sxs-lookup"><span data-stu-id="31066-134">Then, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="31066-135">El diagrama representa **todo el contenido** de todos los registros de productos de una organización, y cada elemento tiene asignado el id. de activo del producto al que pertenece el registro.</span><span class="sxs-lookup"><span data-stu-id="31066-135">The diagram represents **all the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="31066-p111">La vida útil del producto es el tipo de evento; un producto específico que llega al fin de su ciclo de vida es un evento. Cuando se produce este tipo de evento (en este caso, cuando un producto alcanza el fin de su ciclo de vida), creará un evento que especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="31066-p111">Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs—in this case, when a product reaches its end of life—you create an event that specifies:</span></span>
    
   - <span data-ttu-id="31066-138">Un id. de activo (para documentos de OneDrive y SharePoint)</span><span class="sxs-lookup"><span data-stu-id="31066-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
   - <span data-ttu-id="31066-p112">Palabras clave (para elementos de Exchange). En este ejemplo, la organización usa un código de producto en mensajes que contengan registros de productos, para que la palabra clave de los elementos de Exchange coincida con el id. de activo para documentos de OneDrive y SharePoint.</span><span class="sxs-lookup"><span data-stu-id="31066-p112">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is functionally the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
   - <span data-ttu-id="31066-p113">La fecha en que se produjo el evento. La fecha se usa como el inicio del período de retención. Esta fecha puede ser la fecha actual, una fecha pasada o una fecha futura.</span><span class="sxs-lookup"><span data-stu-id="31066-p113">The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.</span></span>

4. <span data-ttu-id="31066-p114">Después de crear un evento, esa fecha del evento se sincroniza con todo el contenido que tenga una etiqueta de retención para ese tipo de evento y que contenga la palabra clave o el Id. de activo especificado. Al igual que con cualquier etiqueta de retención, esta sincronización puede tardar hasta siete días. En el diagrama anterior, este evento desencadena el período de retención de todos los elementos rodeados con un círculo rojo. Es decir, cuando este producto alcanza el final de su ciclo de vida, el evento desencadena el período de retención para esos registros del producto.</span><span class="sxs-lookup"><span data-stu-id="31066-p114">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword. Like any retention label, this synchronization can take up to seven days. In the previous diagram, all the items circled in red have their retention period triggered by this event. In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>

<span data-ttu-id="31066-148">Es importante comprender que, si no especifica palabras clave o un id. de activo para un evento, el evento desencadenará el período de retención de **todo el contenido** que tenga una etiqueta de retención de ese tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="31066-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a retention label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="31066-149">En el diagrama anterior, esto quiere decir que se empezaría a conservar todo el contenido.</span><span class="sxs-lookup"><span data-stu-id="31066-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="31066-150">Es posible que no sea esto lo que quiera realizar.</span><span class="sxs-lookup"><span data-stu-id="31066-150">This might not be what you intend.</span></span>

<span data-ttu-id="31066-p116">Por último, recuerde que cada etiqueta de retención tiene su propia configuración de retención. En este ejemplo, todas especifican 10 años, pero puede que un evento desencadene etiquetas de retención donde cada etiqueta tenga un período de retención distinto.</span><span class="sxs-lookup"><span data-stu-id="31066-p116">Finally, remember that each retention label has its own retention settings. In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="31066-153">Configurar la retención controlada por eventos</span><span class="sxs-lookup"><span data-stu-id="31066-153">How to set up event-driven retention</span></span>

<span data-ttu-id="31066-154">Flujo de trabajo general para la retención controlada por eventos:</span><span class="sxs-lookup"><span data-stu-id="31066-154">High-level workflow for event-driven retention:</span></span>
  
![Diagrama del flujo de trabajo para configurar la retención controlada por eventos](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="31066-156">Vea [Usar las etiquetas de retención para administrar el ciclo de vida de los documentos almacenados en SharePoint](auto-apply-retention-labels-scenario.md) para más información sobre cómo usar las propiedades administradas en SharePoint para aplicar automáticamente las etiquetas de retención e implementar la retención basada en eventos.</span><span class="sxs-lookup"><span data-stu-id="31066-156">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="31066-157">Paso 1: Crear una etiqueta cuyo período de retención se base en un evento</span><span class="sxs-lookup"><span data-stu-id="31066-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="31066-158">Para crear y configurar su etiqueta de retención, siga las instrucciones de [Crear etiquetas de retención](./create-apply-retention-labels.md#step-1-create-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="31066-158">To create and configure your retention label, see the instructions for [Create retention labels](./create-apply-retention-labels.md#step-1-create-retention-labels).</span></span> <span data-ttu-id="31066-159">Sin embargo, específicamente para la retención basada en eventos, en la página **Definir configuración de retención** del asistente de creación de etiquetas de retención, después **Iniciar el período de retención basado en eventos**, seleccione uno de los tipos de eventos predeterminados de la lista desplegable o cree el suyo propio seleccionando **Crear nuevo tipo de evento**:</span><span class="sxs-lookup"><span data-stu-id="31066-159">But specific to event-based retention, on the **Define retention settings** page of the Create retention label wizard, after **Start the retention period based on**, select one of the default event types from the dropdown list, or create your own by selecting **Create new event type**:</span></span>

![Crear un nuevo tipo de evento para una etiqueta de retención](../media/SPRetention6.png)

<span data-ttu-id="31066-161">Un tipo de evento es simplemente una descripción general de un evento al que desea asociar una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="31066-161">An event type is simply a general description of an event that you want to associate with a retention label.</span></span>

<span data-ttu-id="31066-162">Los tipos de sucesos predeterminados tienen **(tipo de evento)** después de su nombre en la lista desplegable para facilitar su identificación, y también puede ver y crear el tipo de evento desde la pestaña **Administración de registros** > **Eventos** > **Administrar tipos de eventos**.</span><span class="sxs-lookup"><span data-stu-id="31066-162">The default event types have **(event type)** after their name in the dropdown list for easier identification, and you can also see and create event type from the **Records management** > **Events** tab > **Manage event types**.</span></span>

<span data-ttu-id="31066-163">La retención basada en eventos necesita una configuración de retención que:</span><span class="sxs-lookup"><span data-stu-id="31066-163">Event-based retention requires retention settings that:</span></span>
  
- <span data-ttu-id="31066-164">Conserve el contenido.</span><span class="sxs-lookup"><span data-stu-id="31066-164">Retain the content.</span></span>
    
- <span data-ttu-id="31066-165">Elimine el contenido automáticamente o desencadene una revisión para eliminación al finalizar el período de retención.</span><span class="sxs-lookup"><span data-stu-id="31066-165">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
  
<span data-ttu-id="31066-166">La retención basada en eventos suele usarse para el contenido que se declara como registro, por lo que este es un buen momento para comprobar si también es necesario seleccionar la opción que marca el contenido como [registro](records-management.md#records).</span><span class="sxs-lookup"><span data-stu-id="31066-166">Event-based retention is typically used for content that's declared a record, so this is a good time to check whether you also need to select the option that marks content as a [record](records-management.md#records).</span></span>

<span data-ttu-id="31066-167">Si está usando un tipo de evento existente en lugar de crear un nuevo tipo de evento, vaya al paso 3.</span><span class="sxs-lookup"><span data-stu-id="31066-167">If you're using an existing event type rather than creating a new event type, skip to step 3.</span></span>

> [!NOTE]
> <span data-ttu-id="31066-168">Después de seleccionar un tipo de evento y guardar la etiqueta de retención, el tipo de evento no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="31066-168">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>

### <a name="step-2-create-a-new-event-type-for-your-label"></a><span data-ttu-id="31066-169">Paso 2: crear un nuevo tipo de evento para su etiqueta</span><span class="sxs-lookup"><span data-stu-id="31066-169">Step 2: Create a new event type for your label</span></span>

<span data-ttu-id="31066-170">Para la configuración de retención, si seleccionó **Crear nuevo tipo de evento**, escriba un nombre y una descripción para su tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="31066-170">For the retention settings, if you selected **Create new event type**, enter a name and description for your event type.</span></span> <span data-ttu-id="31066-171">Luego seleccione **Siguiente**, **Enviar** y **Listo**.</span><span class="sxs-lookup"><span data-stu-id="31066-171">Then select **Next**, **Submit**, and **Done**.</span></span>

<span data-ttu-id="31066-172">Regrese a la página **Definir la configuración de retención**, para **Iniciar el período de retención basado en eventos**, utilice la lista desplegable para seleccionar el tipo de evento que creó.</span><span class="sxs-lookup"><span data-stu-id="31066-172">Back on the **Define retention settings** page, for **Start the retention period based on**, use the dropdown list to select the event type that you created.</span></span>

  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="31066-173">Paso 3: Publicar o aplicar automáticamente las etiquetas de retención basadas en eventos</span><span class="sxs-lookup"><span data-stu-id="31066-173">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="31066-174">Al igual que las etiquetas de retención, debe publicar o aplicar automáticamente una etiqueta basada en eventos para que se aplique de forma manual o automática al contenido:</span><span class="sxs-lookup"><span data-stu-id="31066-174">Just like any retention label, you need to publish or auto-apply an event-based label, for it to be manually or automatically applied to content:</span></span>
- [<span data-ttu-id="31066-175">Crear etiquetas de retención y aplicarlas en aplicaciones</span><span class="sxs-lookup"><span data-stu-id="31066-175">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="31066-176">Aplicar una etiqueta de retención automáticamente al contenido</span><span class="sxs-lookup"><span data-stu-id="31066-176">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="31066-177">Paso 4: Escribir un id. de activo</span><span class="sxs-lookup"><span data-stu-id="31066-177">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="31066-p119">Después de que una etiqueta basada en evento se aplica al contenido, puede especificar un Id. de activo para cada elemento. Por ejemplo, su organización podría usar:</span><span class="sxs-lookup"><span data-stu-id="31066-p119">After an event-based label is applied to content, you can enter an asset ID for each item. For example, your organization might use:</span></span>
  
- <span data-ttu-id="31066-180">Códigos de producto que puede usar para conservar contenido solo para un producto específico.</span><span class="sxs-lookup"><span data-stu-id="31066-180">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="31066-181">Códigos de proyecto que puede usar para conservar contenido solo para un proyecto específico.</span><span class="sxs-lookup"><span data-stu-id="31066-181">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="31066-182">Id. de empleado que puede usar para conservar contenido solo para una persona específica.</span><span class="sxs-lookup"><span data-stu-id="31066-182">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="31066-183">El Id. de activo es simplemente otra propiedad de documento disponible en SharePoint y OneDrive.</span><span class="sxs-lookup"><span data-stu-id="31066-183">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="31066-184">Es posible que la organización ya use otras propiedades del documento o id. para clasificar contenido.</span><span class="sxs-lookup"><span data-stu-id="31066-184">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="31066-185">En ese caso, puede usar esas propiedades y valores al crear un evento (vea el paso 6 más adelante).</span><span class="sxs-lookup"><span data-stu-id="31066-185">If so, you can also use those properties and values when you create an event—see step 6 that follows.</span></span> <span data-ttu-id="31066-186">Lo importante es que su organización tiene que usar alguna combinación de *propiedad:valor* en las propiedades del documento para asociar ese elemento con un tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="31066-186">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![Cuadro de texto para especificar un id. de activo](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="31066-188">Paso 5: Crear un evento</span><span class="sxs-lookup"><span data-stu-id="31066-188">Step 5: Create an event</span></span>

<span data-ttu-id="31066-189">Cuando se produzca una instancia específica de ese tipo de evento, como cuando un producto llega al final de su vida útil, vaya a la página **Administración de registros** > **Eventos** en el Centro de cumplimiento de Microsoft 365 y seleccione **+Crear** para crear un evento.</span><span class="sxs-lookup"><span data-stu-id="31066-189">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center, and select **+ Create** to create an event.</span></span> <span data-ttu-id="31066-190">Desencadena el evento creándolo, aquí.</span><span class="sxs-lookup"><span data-stu-id="31066-190">You trigger the event by creating it, here.</span></span>

![Crear un evento para desencadenar el inicio de la retención para las etiquetas de retención basadas en eventos](../media/create-event-records-management.png)

<span data-ttu-id="31066-192">Se admiten hasta 1 millón de eventos por espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="31066-192">Up to one million events are supported per tenant.</span></span>

### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="31066-193">Paso 6: seleccionar el mismo tipo de evento usado por la etiqueta en el paso 2</span><span class="sxs-lookup"><span data-stu-id="31066-193">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="31066-194">Cuando cree el evento, elija el mismo tipo de evento especificado en la configuración de la etiqueta de retención en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="31066-194">When you create the event, choose the same event type specified in the retention label settings in step 2.</span></span> <span data-ttu-id="31066-195">Por ejemplo, si seleccionó **Duración del producto** como tipo de evento para la configuración de la etiqueta, seleccione **Duración del producto** cuando cree el evento.</span><span class="sxs-lookup"><span data-stu-id="31066-195">For example, if you selected **Product Lifetime** as your event type for the label settings, select **Product Lifetime** when you create the event.</span></span> <span data-ttu-id="31066-196">Solo se desencadenará el período de retención del contenido que tenga aplicadas etiquetas de retención de ese tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="31066-196">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>

![Opción en Configuración de evento para seleccionar un tipo de evento](../media/choose-event-type-records-management.png)

<span data-ttu-id="31066-198">Por otra parte, si necesita crear un evento para múltiples etiquetas de retención que tienen diferentes tipos de eventos, seleccione la opción **Elegir etiquetas existentes**.</span><span class="sxs-lookup"><span data-stu-id="31066-198">Alternatively, if you need to create an event for multiple retention labels that have different event types, select the **Choose Existing Labels** option.</span></span> <span data-ttu-id="31066-199">Después, seleccione las etiquetas que están configuradas para los tipos de eventos que quiere asociar con este evento.</span><span class="sxs-lookup"><span data-stu-id="31066-199">Then, select the labels that are configured for the event types you want to associate with this event.</span></span>

### <a name="step-7-enter-keywords-or-query-for-exchange-asset-id-for-sharepoint-and-onedrive"></a><span data-ttu-id="31066-200">Paso 7: Escribir palabras clave o consultas para Exchange, Id. de activo para SharePoint y OneDrive</span><span class="sxs-lookup"><span data-stu-id="31066-200">Step 7: Enter keywords or query for Exchange, asset ID for SharePoint and OneDrive</span></span>

<span data-ttu-id="31066-201">Ahora limite el ámbito del contenido.</span><span class="sxs-lookup"><span data-stu-id="31066-201">Now you narrow the scope of the content.</span></span> <span data-ttu-id="31066-202">Para el contenido de Exchange, puede hacerlo especificando palabras clave o una consulta.</span><span class="sxs-lookup"><span data-stu-id="31066-202">For Exchange content, you do this by specifying keywords or a query.</span></span> <span data-ttu-id="31066-203">Para el contenido de SharePoint y OneDrive, puede hacerlo especificando Identificadores de activos.</span><span class="sxs-lookup"><span data-stu-id="31066-203">For SharePoint and OneDrive content, you do this by specifying asset IDs.</span></span>

<span data-ttu-id="31066-204">Para los elementos de Exchange, use palabras clave o una consulta que use el Lenguaje de consulta de palabras clave (KQL).</span><span class="sxs-lookup"><span data-stu-id="31066-204">For Exchange items, use keywords or a query that uses Keyword Query Language (KQL).</span></span> <span data-ttu-id="31066-205">Para obtener más información, vea [Referencia de sintaxis del Lenguaje de consultas de palabras clave (KQL)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="31066-205">For more information about the query syntax, see [Keyword Query Language (KQL) syntax reference](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span> <span data-ttu-id="31066-206">Para obtener más información sobre las propiedades que se pueden usar para la búsqueda en Exchange, vea [Consultas de palabras clave y condiciones de búsqueda para la Búsqueda de contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="31066-206">For more information about the searchable properties that you can use for Exchange, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

<span data-ttu-id="31066-207">Para los Id. de activo, la retención solo se aplicará en el contenido que tenga la combinación de *propiedad:valor* especificada.</span><span class="sxs-lookup"><span data-stu-id="31066-207">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="31066-208">Por ejemplo: si usa la propiedad de Id. de activo, escriba `ComplianceAssetID:<value>` en el cuadro de Id. de activo que se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="31066-208">For example, if you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown in the following picture.</span></span>

<span data-ttu-id="31066-209">Si no se especifica un Id. de activo, se aplicará la misma fecha de retención a todo el contenido con etiquetas para ese tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="31066-209">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="31066-210">Puede que su organización aplicara otras propiedades e id. a los documentos relacionados con este tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="31066-210">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="31066-211">Por ejemplo, si necesita encontrar los registros de un producto específico, el id. puede ser una combinación de la propiedad personalizada “IdProducto” y el valor “XYZ”.</span><span class="sxs-lookup"><span data-stu-id="31066-211">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="31066-212">En este caso, escriba `ProductID:XYZ` en el cuadro de id. de activo que se muestra abajo.</span><span class="sxs-lookup"><span data-stu-id="31066-212">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>

<span data-ttu-id="31066-p128">Por último, seleccione la fecha en que se produjo el evento; esta fecha se usará como el inicio del período de retención. Después de crear un evento, la fecha del evento se sincronizará con todo el contenido mediante una etiqueta de retención para ese tipo de evento, Id. de activo y consultas o palabras clave. Al igual que con cualquier etiqueta de retención, esta sincronización puede tardar hasta siete días.</span><span class="sxs-lookup"><span data-stu-id="31066-p128">Finally, choose the date when the event occurred; this date is used as the start of the retention period. After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords or queries. As with any retention label, this synchronization can take up to seven days.</span></span>
  
![Página Configuración de evento](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="31066-217">Después de crear un evento, la configuración de retención surte efecto para el contenido que ya está etiquetado e indexado.</span><span class="sxs-lookup"><span data-stu-id="31066-217">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="31066-218">Si se agrega la etiqueta de retención a contenido nuevo tras crear el evento, deberá crear un nuevo evento con los mismos detalles.</span><span class="sxs-lookup"><span data-stu-id="31066-218">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="31066-219">Al eliminar un evento, no se cancela la configuración de retención que está vigente en el contenido que ya está etiquetado.</span><span class="sxs-lookup"><span data-stu-id="31066-219">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="31066-220">Para ello, cree un nuevo evento con los mismos detalles, pero deje la fecha en blanco.</span><span class="sxs-lookup"><span data-stu-id="31066-220">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="31066-221">Usar Búsqueda de contenido para encontrar todo el contenido que tenga aplicada una etiqueta o id. de activo específicos</span><span class="sxs-lookup"><span data-stu-id="31066-221">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="31066-222">Después de asignar etiquetas de retención a contenido, puede usar la búsqueda de contenido para encontrar todo el contenido clasificado con una etiqueta de retención específica o que contiene un id. de activo específico:</span><span class="sxs-lookup"><span data-stu-id="31066-222">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="31066-223">Para encontrar todo el contenido con una etiqueta de retención específica, seleccione la condición **Etiqueta de retención** y, después, escriba el nombre de etiqueta completo o una parte del nombre de la etiqueta y use un comodín.</span><span class="sxs-lookup"><span data-stu-id="31066-223">To find all content with a specific retention label, choose the **Retention label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="31066-224">Para encontrar todo el contenido con un id. de activo específico, escriba la propiedad **ComplianceAssetID** y un valor con el formato `ComplianceAssetID:<value>`.</span><span class="sxs-lookup"><span data-stu-id="31066-224">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="31066-225">Para obtener más información, consulte [Consultas de palabras clave y condiciones de búsqueda para la Búsqueda de Contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="31066-225">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="31066-226">Automatizar eventos con PowerShell</span><span class="sxs-lookup"><span data-stu-id="31066-226">Automate events by using PowerShell</span></span>

<span data-ttu-id="31066-227">Puede usar un script de PowerShell para automatizar la retención basada en eventos desde sus aplicaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="31066-227">You can use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="31066-228">Los cmdlets de PowerShell disponibles para la retención basada en eventos son:</span><span class="sxs-lookup"><span data-stu-id="31066-228">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="31066-229">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="31066-229">Get-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/get-complianceretentioneventtype)
    
- [<span data-ttu-id="31066-230">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="31066-230">New-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/new-complianceretentioneventtype)
    
- [<span data-ttu-id="31066-231">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="31066-231">Remove-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/remove-complianceretentioneventtype)
    
- [<span data-ttu-id="31066-232">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="31066-232">Set-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/set-complianceretentioneventtype)
    
- [<span data-ttu-id="31066-233">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="31066-233">Get-ComplianceRetentionEvent</span></span>](/powershell/module/exchange/get-complianceretentionevent)
    
- [<span data-ttu-id="31066-234">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="31066-234">New-ComplianceRetentionEvent</span></span>](/powershell/module/exchange/new-complianceretentionevent)
    

## <a name="automate-events-by-using-a-rest-api"></a><span data-ttu-id="31066-235">Automatizar eventos mediante una API de REST</span><span class="sxs-lookup"><span data-stu-id="31066-235">Automate events by using a REST API</span></span>

<span data-ttu-id="31066-236">Puede usar una API de REST para crear automáticamente eventos que desencadenen el inicio del tiempo de retención.</span><span class="sxs-lookup"><span data-stu-id="31066-236">You can use a REST API to automatically create the events that trigger the start of the retention time.</span></span>

<span data-ttu-id="31066-237">Una API de REST es un punto de conexión de servicio que admite conjuntos de operaciones (métodos) HTTP, que proporcionan acceso de creación/recuperación/actualización/eliminación a los recursos del servicio.</span><span class="sxs-lookup"><span data-stu-id="31066-237">A REST API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="31066-238">Para obtener más información, vea [Componentes de una solicitud o respuesta de la API de REST](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="31066-238">For more information, see [Components of a REST API request/response](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="31066-239">Al usar la API de REST de Microsoft 365, se pueden crear y recuperar eventos mediante el uso de métodos POST y GET.</span><span class="sxs-lookup"><span data-stu-id="31066-239">By using the Microsoft 365 REST API, events can be created and retrieved using the POST and GET methods.</span></span>

<span data-ttu-id="31066-240">Hay dos opciones para usar la API de REST:</span><span class="sxs-lookup"><span data-stu-id="31066-240">There are two options for using the REST API:</span></span>

- <span data-ttu-id="31066-241">**Usar Microsoft Power Automate o una aplicación similar** para desencadenar un evento automáticamente.</span><span class="sxs-lookup"><span data-stu-id="31066-241">**Microsoft Power Automate or a similar application** to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="31066-242">Microsoft Power Automate es un orquestador para conectarse a otros sistemas, por lo que no tiene que escribir una solución personalizada.</span><span class="sxs-lookup"><span data-stu-id="31066-242">Microsoft Power Automate is an orchestrator for connecting to other systems, so you don't need to write a custom solution.</span></span> <span data-ttu-id="31066-243">Para obtener más información, consulte el [sitio de Power Automate](https://flow.microsoft.com/es-ES/).</span><span class="sxs-lookup"><span data-stu-id="31066-243">For more information, see the [Power Automate website](https://flow.microsoft.com/es-ES/).</span></span>

- <span data-ttu-id="31066-244">**Usar PowerShell o un cliente HTTP para llamar a la API de REST** a fin de crear eventos con PowerShell (versión 6 o posterior), lo que forma parte de una solución personalizada.</span><span class="sxs-lookup"><span data-stu-id="31066-244">**PowerShell or an HTTP client to call the REST API** to create events by using PowerShell (version 6 or later), which is part of a custom solution.</span></span>

<span data-ttu-id="31066-245">Antes de usar la API de REST, como administrador global, confirme la dirección URL que se usará para la llamada al evento de retención.</span><span class="sxs-lookup"><span data-stu-id="31066-245">Before you use the REST API, as a global administrator, confirm the URL to use for the retention event call.</span></span> <span data-ttu-id="31066-246">Para ello, ejecute una llamada GET al evento de retención con la dirección URL de la API de REST:</span><span class="sxs-lookup"><span data-stu-id="31066-246">To do this, run a GET retention event call by using the REST API URL:</span></span>

```http
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

<span data-ttu-id="31066-247">Compruebe el código de respuesta.</span><span class="sxs-lookup"><span data-stu-id="31066-247">Check the response code.</span></span> <span data-ttu-id="31066-248">Si es 302, obtenga la URL redirigida de la propiedad Ubicación del encabezado de respuesta y use esa dirección URL en lugar de `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` en las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="31066-248">If it's 302, get the redirected URL from the Location property of the response header and use that URL instead of `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in the instructions that follow.</span></span>

<span data-ttu-id="31066-249">Los eventos que se crean automáticamente se pueden visualizar y confirmar en el Centro de cumplimiento de Microsoft 365 > **Administración de registros** >  **Eventos**.</span><span class="sxs-lookup"><span data-stu-id="31066-249">The events that get automatically created can be confirmed by viewing them in the Microsoft 365 compliance center > **Records management** >  **Events**.</span></span>

### <a name="use-microsoft-power-automate-to-create-the-event"></a><span data-ttu-id="31066-250">Usar Microsoft Power Automate para crear el evento</span><span class="sxs-lookup"><span data-stu-id="31066-250">Use Microsoft Power Automate to create the event</span></span>

<span data-ttu-id="31066-251">Cree un flujo que cree un evento mediante la API de REST de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="31066-251">Create a flow that creates an event using the Microsoft 365 REST API:</span></span>

![Usar Flow para crear un evento](../media/automate-event-driven-retention-flow-1.png)

![Usar Flow para llamar a la API de REST](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a><span data-ttu-id="31066-254">Crear un evento</span><span class="sxs-lookup"><span data-stu-id="31066-254">Create an event</span></span>

<span data-ttu-id="31066-255">Código de ejemplo para llamar a la API de REST:</span><span class="sxs-lookup"><span data-stu-id="31066-255">Sample code to call the REST API:</span></span>

- <span data-ttu-id="31066-256">**Método**: POST</span><span class="sxs-lookup"><span data-stu-id="31066-256">**Method**: POST</span></span>
- <span data-ttu-id="31066-257">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="31066-257">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="31066-258">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="31066-258">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="31066-259">**Body**:</span><span class="sxs-lookup"><span data-stu-id="31066-259">**Body**:</span></span>

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

- <span data-ttu-id="31066-260">**Autenticación**: Básica</span><span class="sxs-lookup"><span data-stu-id="31066-260">**Authentication**: Basic</span></span>
- <span data-ttu-id="31066-261">**Nombre de usuario**: “Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="31066-261">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="31066-262">**Contraseña**: “Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="31066-262">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="31066-263">Parámetros disponibles</span><span class="sxs-lookup"><span data-stu-id="31066-263">Available parameters</span></span>


|<span data-ttu-id="31066-264">Parámetros</span><span class="sxs-lookup"><span data-stu-id="31066-264">Parameters</span></span>|<span data-ttu-id="31066-265">Description</span><span class="sxs-lookup"><span data-stu-id="31066-265">Description</span></span>|<span data-ttu-id="31066-266">Notas</span><span class="sxs-lookup"><span data-stu-id="31066-266">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="31066-267"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="31066-267"><d:Name></d:Name></span></span>|<span data-ttu-id="31066-268">Escriba un nombre único para el evento.</span><span class="sxs-lookup"><span data-stu-id="31066-268">Provide a unique name for the event,</span></span>|<span data-ttu-id="31066-269">No puede contener espacios finales ni los caracteres siguientes: % \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="31066-269">Cannot contain trailing spaces or the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="31066-270">, : ;</span><span class="sxs-lookup"><span data-stu-id="31066-270">, : ;</span></span>|
|<span data-ttu-id="31066-271"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="31066-271"><d:EventType></d:EventType></span></span>|<span data-ttu-id="31066-272">Escribe el nombre del tipo de evento (o Guid)</span><span class="sxs-lookup"><span data-stu-id="31066-272">Enter event type name (or Guid),</span></span>|<span data-ttu-id="31066-p137">Ejemplo: "Desvinculación del empleado". El tipo de evento debe estar asociado con una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="31066-p137">Example: "Employee termination". Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="31066-275"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="31066-275"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="31066-276">Escriba "ComplianceAssetId:" + el id. del empleado</span><span class="sxs-lookup"><span data-stu-id="31066-276">Enter "ComplianceAssetId:" + employee ID</span></span>|<span data-ttu-id="31066-277">Ejemplo: "ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="31066-277">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="31066-278"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="31066-278"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="31066-279">Fecha y hora del evento</span><span class="sxs-lookup"><span data-stu-id="31066-279">Event Date and Time</span></span>|<span data-ttu-id="31066-280">Formato: aaaa-MM-ddTHH:mm:ssZ, ejemplo: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="31066-280">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

###### <a name="response-codes"></a><span data-ttu-id="31066-281">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="31066-281">Response codes</span></span>

| <span data-ttu-id="31066-282">Código de respuesta</span><span class="sxs-lookup"><span data-stu-id="31066-282">Response Code</span></span> | <span data-ttu-id="31066-283">Descripción</span><span class="sxs-lookup"><span data-stu-id="31066-283">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="31066-284">302</span><span class="sxs-lookup"><span data-stu-id="31066-284">302</span></span>               | <span data-ttu-id="31066-285">Redirigir</span><span class="sxs-lookup"><span data-stu-id="31066-285">Redirect</span></span>              |
| <span data-ttu-id="31066-286">201</span><span class="sxs-lookup"><span data-stu-id="31066-286">201</span></span>               | <span data-ttu-id="31066-287">Fecha de creación</span><span class="sxs-lookup"><span data-stu-id="31066-287">Created</span></span>               |
| <span data-ttu-id="31066-288">403</span><span class="sxs-lookup"><span data-stu-id="31066-288">403</span></span>               | <span data-ttu-id="31066-289">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="31066-289">Authorization Failed</span></span>  |
| <span data-ttu-id="31066-290">401</span><span class="sxs-lookup"><span data-stu-id="31066-290">401</span></span>               | <span data-ttu-id="31066-291">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="31066-291">Authentication Failed</span></span> |

##### <a name="get-events-based-on-a-time-range"></a><span data-ttu-id="31066-292">Obtener eventos según un intervalo de tiempo</span><span class="sxs-lookup"><span data-stu-id="31066-292">Get events based on a time range</span></span>

- <span data-ttu-id="31066-293">**Método**: GET</span><span class="sxs-lookup"><span data-stu-id="31066-293">**Method**: GET</span></span>

- <span data-ttu-id="31066-294">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="31066-294">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="31066-295">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="31066-295">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="31066-296">**Autenticación**: Básica</span><span class="sxs-lookup"><span data-stu-id="31066-296">**Authentication**: Basic</span></span>

- <span data-ttu-id="31066-297">**Nombre de usuario**: “Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="31066-297">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="31066-298">**Contraseña**: “Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="31066-298">**Password**: "Compliancepassword"</span></span>

###### <a name="response-codes"></a><span data-ttu-id="31066-299">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="31066-299">Response codes</span></span>

| <span data-ttu-id="31066-300">Código de respuesta</span><span class="sxs-lookup"><span data-stu-id="31066-300">Response Code</span></span> | <span data-ttu-id="31066-301">Descripción</span><span class="sxs-lookup"><span data-stu-id="31066-301">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="31066-302">200</span><span class="sxs-lookup"><span data-stu-id="31066-302">200</span></span>               | <span data-ttu-id="31066-303">Aceptar, una lista de eventos de atom+ xml</span><span class="sxs-lookup"><span data-stu-id="31066-303">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="31066-304">404</span><span class="sxs-lookup"><span data-stu-id="31066-304">404</span></span>               | <span data-ttu-id="31066-305">No encontrado</span><span class="sxs-lookup"><span data-stu-id="31066-305">Not found</span></span>                         |
| <span data-ttu-id="31066-306">302</span><span class="sxs-lookup"><span data-stu-id="31066-306">302</span></span>               | <span data-ttu-id="31066-307">Redirigir</span><span class="sxs-lookup"><span data-stu-id="31066-307">Redirect</span></span>                          |
| <span data-ttu-id="31066-308">401</span><span class="sxs-lookup"><span data-stu-id="31066-308">401</span></span>               | <span data-ttu-id="31066-309">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="31066-309">Authorization Failed</span></span>              |
| <span data-ttu-id="31066-310">403</span><span class="sxs-lookup"><span data-stu-id="31066-310">403</span></span>               | <span data-ttu-id="31066-311">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="31066-311">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="31066-312">Obtén un objeto por id.</span><span class="sxs-lookup"><span data-stu-id="31066-312">Get an event by ID</span></span>

- <span data-ttu-id="31066-313">**Método**: GET</span><span class="sxs-lookup"><span data-stu-id="31066-313">**Method**: GET</span></span>

- <span data-ttu-id="31066-314">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="31066-314">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="31066-315">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="31066-315">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="31066-316">**Autenticación**: Básica</span><span class="sxs-lookup"><span data-stu-id="31066-316">**Authentication**: Basic</span></span>

- <span data-ttu-id="31066-317">**Nombre de usuario**: “Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="31066-317">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="31066-318">**Contraseña**: “Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="31066-318">**Password**: "Compliancepassword"</span></span>

###### <a name="response-codes"></a><span data-ttu-id="31066-319">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="31066-319">Response codes</span></span>

| <span data-ttu-id="31066-320">Código de respuesta</span><span class="sxs-lookup"><span data-stu-id="31066-320">Response Code</span></span> | <span data-ttu-id="31066-321">Descripción</span><span class="sxs-lookup"><span data-stu-id="31066-321">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="31066-322">200</span><span class="sxs-lookup"><span data-stu-id="31066-322">200</span></span>               | <span data-ttu-id="31066-323">Aceptar, el cuerpo de la respuesta contiene el evento en atom+ xml</span><span class="sxs-lookup"><span data-stu-id="31066-323">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="31066-324">404</span><span class="sxs-lookup"><span data-stu-id="31066-324">404</span></span>               | <span data-ttu-id="31066-325">No encontrado</span><span class="sxs-lookup"><span data-stu-id="31066-325">Not found</span></span>                                            |
| <span data-ttu-id="31066-326">302</span><span class="sxs-lookup"><span data-stu-id="31066-326">302</span></span>               | <span data-ttu-id="31066-327">Redirigir</span><span class="sxs-lookup"><span data-stu-id="31066-327">Redirect</span></span>                                             |
| <span data-ttu-id="31066-328">401</span><span class="sxs-lookup"><span data-stu-id="31066-328">401</span></span>               | <span data-ttu-id="31066-329">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="31066-329">Authorization Failed</span></span>                                 |
| <span data-ttu-id="31066-330">403</span><span class="sxs-lookup"><span data-stu-id="31066-330">403</span></span>               | <span data-ttu-id="31066-331">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="31066-331">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="31066-332">Obtén un evento por nombre</span><span class="sxs-lookup"><span data-stu-id="31066-332">Get an event by name</span></span>

- <span data-ttu-id="31066-333">**Método**: GET</span><span class="sxs-lookup"><span data-stu-id="31066-333">**Method**: GET</span></span>

- <span data-ttu-id="31066-334">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="31066-334">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="31066-335">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="31066-335">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="31066-336">**Autenticación**: Básica</span><span class="sxs-lookup"><span data-stu-id="31066-336">**Authentication**: Basic</span></span>

- <span data-ttu-id="31066-337">**Nombre de usuario**: “Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="31066-337">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="31066-338">**Contraseña**: “Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="31066-338">**Password**: "Compliancepassword"</span></span>

###### <a name="response-codes"></a><span data-ttu-id="31066-339">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="31066-339">Response codes</span></span>

| <span data-ttu-id="31066-340">Código de respuesta</span><span class="sxs-lookup"><span data-stu-id="31066-340">Response Code</span></span> | <span data-ttu-id="31066-341">Descripción</span><span class="sxs-lookup"><span data-stu-id="31066-341">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="31066-342">200</span><span class="sxs-lookup"><span data-stu-id="31066-342">200</span></span>               | <span data-ttu-id="31066-343">Aceptar, el cuerpo de la respuesta contiene el evento en atom+ xml</span><span class="sxs-lookup"><span data-stu-id="31066-343">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="31066-344">404</span><span class="sxs-lookup"><span data-stu-id="31066-344">404</span></span>               | <span data-ttu-id="31066-345">No encontrado</span><span class="sxs-lookup"><span data-stu-id="31066-345">Not found</span></span>                                            |
| <span data-ttu-id="31066-346">302</span><span class="sxs-lookup"><span data-stu-id="31066-346">302</span></span>               | <span data-ttu-id="31066-347">Redirigir</span><span class="sxs-lookup"><span data-stu-id="31066-347">Redirect</span></span>                                             |
| <span data-ttu-id="31066-348">401</span><span class="sxs-lookup"><span data-stu-id="31066-348">401</span></span>               | <span data-ttu-id="31066-349">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="31066-349">Authorization Failed</span></span>                                 |
| <span data-ttu-id="31066-350">403</span><span class="sxs-lookup"><span data-stu-id="31066-350">403</span></span>               | <span data-ttu-id="31066-351">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="31066-351">Authentication Failed</span></span>                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a><span data-ttu-id="31066-352">Usar PowerShell o cualquier cliente HTTP para crear el evento</span><span class="sxs-lookup"><span data-stu-id="31066-352">Use PowerShell or any HTTP client to create the event</span></span>

<span data-ttu-id="31066-353">La versión de PowerShell debe ser 6 o posterior.</span><span class="sxs-lookup"><span data-stu-id="31066-353">PowerShell must be version 6 or later.</span></span>

<span data-ttu-id="31066-354">En una sesión de PowerShell, ejecute el siguiente script:</span><span class="sxs-lookup"><span data-stu-id="31066-354">In a PowerShell session, run the following script:</span></span>

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
