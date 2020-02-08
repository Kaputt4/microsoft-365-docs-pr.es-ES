---
title: Retención automática controlada por eventos
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: En este tema se explica cómo configurar los flujos de procesos empresariales para automatizar la retención mediante eventos con la API de REST de Microsoft 365.
ms.openlocfilehash: 46276e1a40df8c5491d569337a683666984be23a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596327"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="29b8e-103">Retención automática basada en eventos</span><span class="sxs-lookup"><span data-stu-id="29b8e-103">Automate event-based retention</span></span>

<span data-ttu-id="29b8e-p101">La explosión de contenido en las organizaciones y la forma en la que se convierte en ROT (redundante obsoleto, trivial) constituye un asunto importante. Para seguir satisfaciendo los desafíos de cumplimiento legal, normativo y empresarial, las organizaciones deben conservar y proteger la información importante y encontrar rápidamente lo que es relevante. Conservar solo información importante y relevante es clave para el éxito de la organización.</span><span class="sxs-lookup"><span data-stu-id="29b8e-p101">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to an organization's success.</span></span>

<span data-ttu-id="29b8e-p102">Para cumplir esta necesidad, las organizaciones pueden beneficiarse de las soluciones de retención del Centro de seguridad y cumplimiento de Office 365. La retención puede activarse con [etiquetas de retención](labels.md). Una etiqueta de retención tiene la opción de [basar el período de retención en un evento específico](event-driven-retention.md). Normalmente, el período de retención se basa en una fecha conocida, como la fecha de creación o fecha de última modificación del contenido. Sin embargo, las organizaciones también tienen requisitos para eliminar el contenido en función de la ocurrencia de un evento, como 7 años después de que un empleado deje la organización.</span><span class="sxs-lookup"><span data-stu-id="29b8e-p102">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span></span>

<span data-ttu-id="29b8e-p103">Para garantizar que las normas eliminación de contenido cumplen con las normas, es imprescindible conocer cuándo sucede un evento. Con un volumen de contenido en rápido aumento, se torna cada vez más difícil retener y eliminar contenido de manera oportuna y que cumpla con las normas.</span><span class="sxs-lookup"><span data-stu-id="29b8e-p103">To ensure compliant disposal of content, it's imperative to know when an event takes place. With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="29b8e-p104">La retención basada en eventos soluciona este problema. En este tema se explica cómo configurar los flujos de procesos empresariales para automatizar la retención mediante eventos con la API de REST de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="29b8e-p104">Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="29b8e-116">Acerca de la retención basada en eventos</span><span class="sxs-lookup"><span data-stu-id="29b8e-116">About event-based retention</span></span>

<span data-ttu-id="29b8e-p105">Una organización puede ser pequeña, mediana o grande. La cantidad de documentos empresariales, documentos legales, archivos de empleados, contratos y documentos de productos que se crean y administran a diario aumenta enormemente.</span><span class="sxs-lookup"><span data-stu-id="29b8e-p105">An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span></span>

<span data-ttu-id="29b8e-p106">Por ejemplo, cada día, decenas y cientos de empleados se unen a organizaciones y las dejan. El departamento de RR. HH. sigue creando, actualizando o eliminando documentos relacionados con los empleados según los requisitos empresariales. Este proceso está sujeto a las distintas directivas de retención indicadas para la empresa:</span><span class="sxs-lookup"><span data-stu-id="29b8e-p106">For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="29b8e-p107">**El período de retención de contenido puede ser una fecha conocida**, como la fecha en la que se creó, modificó por última vez o etiquetó el contenido. Por ejemplo, puedes retener documentos durante siete años después de su creación y luego eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="29b8e-p107">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled. For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="29b8e-p108">**El período de retención de contenido también puede ser una fecha desconocida**. Por ejemplo, con las etiquetas de retención, también puedes basar un período de retención en el momento en el que se produce un tipo de evento específico, como cuando un empleado deja la organización.</span><span class="sxs-lookup"><span data-stu-id="29b8e-p108">**The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="29b8e-p109">El evento desencadena el inicio del período de retención y a todo el contenido con una etiqueta aplicada para ese tipo de evento se le aplican las acciones de retención de la etiqueta. Esto se denomina retención basada en eventos: para obtener más información, consulta [Introducción a la retención basada en eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="29b8e-p109">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention. To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="29b8e-129">Configuración de la retención basada en eventos</span><span class="sxs-lookup"><span data-stu-id="29b8e-129">Set up event-based retention</span></span>

<span data-ttu-id="29b8e-130">Esta sección describe lo que es necesario realizar antes de retener contenido.</span><span class="sxs-lookup"><span data-stu-id="29b8e-130">This section describes what needs to be done before retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="29b8e-131">Identificación de funciones</span><span class="sxs-lookup"><span data-stu-id="29b8e-131">Identify roles</span></span>

<span data-ttu-id="29b8e-132">Identifica las diferentes funciones en una organización que realizan tareas de administración de registros y son responsables de una retención eficaz y eficiente de los documentos empresariales.</span><span class="sxs-lookup"><span data-stu-id="29b8e-132">Identify the different roles in an organization that perform Record Management tasks and would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="29b8e-133">**Rol**</span><span class="sxs-lookup"><span data-stu-id="29b8e-133">**Persona**</span></span>| <span data-ttu-id="29b8e-134">**Rol**</span><span class="sxs-lookup"><span data-stu-id="29b8e-134">**Role**</span></span>|
  | - | - |
  | <span data-ttu-id="29b8e-135">Administración</span><span class="sxs-lookup"><span data-stu-id="29b8e-135">Admin</span></span> | <span data-ttu-id="29b8e-136">Crea tipos de eventos de retención, etiquetas de retención y repositorios de registros en SharePoint</span><span class="sxs-lookup"><span data-stu-id="29b8e-136">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="29b8e-137">Administrador de registros</span><span class="sxs-lookup"><span data-stu-id="29b8e-137">Records Manager</span></span>                                  | <span data-ttu-id="29b8e-138">Proporciona detalles de cumplimiento y guías de políticas de retención y programaciones de retención</span><span class="sxs-lookup"><span data-stu-id="29b8e-138">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="29b8e-139">Administrador del sistema (empresa)</span><span class="sxs-lookup"><span data-stu-id="29b8e-139">System Admin (business)</span></span>                          | <span data-ttu-id="29b8e-140">Configura y administra sistemas externos para que funcionen con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="29b8e-140">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="29b8e-141">Trabajador de información</span><span class="sxs-lookup"><span data-stu-id="29b8e-141">Information Worker</span></span>                               | <span data-ttu-id="29b8e-142">Administra el ciclo de vida de los procesos de su empresa (Recursos Humanos, Finanzas, TI, etc.)</span><span class="sxs-lookup"><span data-stu-id="29b8e-142">Manages the lifecycle of their business process (HR, Finance, IT, and so on)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="29b8e-143">Configuración del Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="29b8e-143">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="29b8e-144">La administración del cumplimiento crea un tipo de evento &ndash; como el final de una relación laboral, la finalización del contrato o el final de fabricación del producto.</span><span class="sxs-lookup"><span data-stu-id="29b8e-144">Compliance admin creates an event type &ndash; for example, Employee Termination or Contract Expiration or End of Product Manufacturing.</span></span> <span data-ttu-id="29b8e-145">(Consulte el proceso paso a paso en el artículo [Retención de eventos](event-driven-retention.md)).</span><span class="sxs-lookup"><span data-stu-id="29b8e-145">(See the step-by-step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
2. <span data-ttu-id="29b8e-146">La administración de cumplimiento crea una etiqueta de retención basada en un evento y asocia la etiqueta con un tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="29b8e-146">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
    <span data-ttu-id="29b8e-147">Hay 4 tipos de desencadenadores para las etiquetas de retención:</span><span class="sxs-lookup"><span data-stu-id="29b8e-147">There are four types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="29b8e-148">Fecha de creación</span><span class="sxs-lookup"><span data-stu-id="29b8e-148">Create date</span></span>
                
    2. <span data-ttu-id="29b8e-149">Última modificación</span><span class="sxs-lookup"><span data-stu-id="29b8e-149">Last modified</span></span>
                
    3. <span data-ttu-id="29b8e-150">Fecha de la etiqueta (cuando se etiquetó el contenido)</span><span class="sxs-lookup"><span data-stu-id="29b8e-150">Label date (when the content was labeled)</span></span>
                
    4. <span data-ttu-id="29b8e-151">Basado en eventos</span><span class="sxs-lookup"><span data-stu-id="29b8e-151">Event-based</span></span>
    
3. <span data-ttu-id="29b8e-152">La administración del cumplimiento publica la etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="29b8e-152">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="29b8e-153">Configurar SharePoint</span><span class="sxs-lookup"><span data-stu-id="29b8e-153">Set up SharePoint</span></span>
   
<span data-ttu-id="29b8e-154">Para crear un repositorio de registros, la administración del cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="29b8e-154">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="29b8e-155">Crea un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="29b8e-155">Creates a SharePoint site.</span></span>

2. <span data-ttu-id="29b8e-156">Realiza una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="29b8e-156">Does one of the following:</span></span>
        
    - <span data-ttu-id="29b8e-p111">Crea una biblioteca de SharePoint: establece una etiqueta basada en eventos en el nivel de la biblioteca. Para obtener más información, consulta [Aplicar una etiqueta de retención predeterminada a todo el contenido de una biblioteca, carpeta o conjunto de documentos de SharePoint](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="29b8e-p111">Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
    - <span data-ttu-id="29b8e-159">Configura un conjunto de documentos en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="29b8e-159">Sets up a document set in SharePoint.</span></span> <span data-ttu-id="29b8e-160">Para más información, vea [Introducción a los conjuntos de documentos](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span><span class="sxs-lookup"><span data-stu-id="29b8e-160">For more information, see [Introduction to document sets](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span></span>
      
3. <span data-ttu-id="29b8e-161">Asigna un ID. de activo para cada conjunto de documentos de empleado.</span><span class="sxs-lookup"><span data-stu-id="29b8e-161">Assigns an asset ID to each employee document set.</span></span> <span data-ttu-id="29b8e-162">Un ID. de activo es el nombre o código de producto usado por la organización. Por ejemplo, el número de empleado puede ser un ID. de activo.</span><span class="sxs-lookup"><span data-stu-id="29b8e-162">An asset ID is a product name or code used by the organization, for example, Employee number can be an asset ID.</span></span> <span data-ttu-id="29b8e-163">Al asignar el ID. de activo a una carpeta, cada elemento de esta carpeta hereda automáticamente el mismo ID. de activo.</span><span class="sxs-lookup"><span data-stu-id="29b8e-163">By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID.</span></span> <span data-ttu-id="29b8e-164">Esto significa que todos los elementos pueden tener un periodo de retención activado por el mismo evento.</span><span class="sxs-lookup"><span data-stu-id="29b8e-164">This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="29b8e-165">Formas de desencadenar la retención basada en eventos</span><span class="sxs-lookup"><span data-stu-id="29b8e-165">Ways to trigger event-based retention</span></span>

<span data-ttu-id="29b8e-166">Existen dos formas de desencadenar la retención basada en eventos:</span><span class="sxs-lookup"><span data-stu-id="29b8e-166">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="29b8e-167">**Uso de la interfaz de usuario del Centro de administración** Con este proceso puede retener menos contenido a la vez, o bien, la frecuencia de activación de la retención puede ser menor (p. ej., mensual o anual).</span><span class="sxs-lookup"><span data-stu-id="29b8e-167">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention isn't often, such as monthly or yearly.</span></span> <span data-ttu-id="29b8e-168">Para obtener más información sobre este método, consulte [Información general sobre la retención basada en eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="29b8e-168">For more information about this method, see [Overview of event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="29b8e-169">Sin embargo, este método para desencadenar la retención puede consumir demasiado tiempo y producir más errores, lo que daña la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="29b8e-169">However, this method of triggering retention can be time consuming and prone to error, thus stunting scalability.</span></span> <span data-ttu-id="29b8e-170">Por lo tanto, una solución automatizada y sin errores para activar la retención puede mejorar la seguridad de los datos y el cumplimiento normativo.</span><span class="sxs-lookup"><span data-stu-id="29b8e-170">Therefore, an automated, seamless solution to trigger retention can enhance data security and compliance.</span></span>

- <span data-ttu-id="29b8e-p115">**Con una API de REST de M365** Este proceso puede usarse cuando se deben retener grandes cantidades de contenido a la vez o cuando la frecuencia para activar la retención es asidua (diaria o semanal). El flujo detecta cuando un evento se ejecuta en el sistema de línea de negocio y crea automáticamente un evento relacionado en el Centro de seguridad y cumplimiento. No es necesario crear manualmente un evento en la interfaz de usuario cada vez que se produce un evento.</span><span class="sxs-lookup"><span data-stu-id="29b8e-p115">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="29b8e-174">Hay dos opciones para usar la API de REST:</span><span class="sxs-lookup"><span data-stu-id="29b8e-174">There are two options for using the REST API:</span></span>

- <span data-ttu-id="29b8e-175">**Usar Microsoft Flow o una aplicación similar** para desencadenar un evento automáticamente.</span><span class="sxs-lookup"><span data-stu-id="29b8e-175">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="29b8e-176">Microsoft Flow puede orquestar la conexión a otros sistemas.</span><span class="sxs-lookup"><span data-stu-id="29b8e-176">Microsoft Flow is an orchestrator for connecting to other systems.</span></span> <span data-ttu-id="29b8e-177">Además, su uso no requiere una solución personalizada.</span><span class="sxs-lookup"><span data-stu-id="29b8e-177">Using Microsoft Flow doesn't require a custom solution.</span></span>

- <span data-ttu-id="29b8e-178">**PowerShell o un cliente de HTTP para llamar a la API de REST** Usar PowerShell (versión 6 o posterior) para pedirle a la API de REST de Microsoft 365 que cree eventos.</span><span class="sxs-lookup"><span data-stu-id="29b8e-178">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="29b8e-179">Una API de REST es un punto de conexión de servicio que admite conjuntos de operaciones HTTP (métodos), que proporcionan acceso de creación/recuperación/actualización/eliminación a los recursos del servicio.</span><span class="sxs-lookup"><span data-stu-id="29b8e-179">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="29b8e-180">Para obtener más información, vea [Componentes de una solicitud o respuesta de API de REST](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="29b8e-180">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="29b8e-181">En este caso, al usar la API de REST de Microsoft 365, puede crear y recuperar eventos mediante el uso de operaciones (métodos) POST y GET.</span><span class="sxs-lookup"><span data-stu-id="29b8e-181">In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="29b8e-182">Escenarios de ejemplo</span><span class="sxs-lookup"><span data-stu-id="29b8e-182">Example scenarios</span></span>

<span data-ttu-id="29b8e-183">Consideremos los siguientes escenarios.</span><span class="sxs-lookup"><span data-stu-id="29b8e-183">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="29b8e-184">Escenario 1: Empleados que dejan la organización</span><span class="sxs-lookup"><span data-stu-id="29b8e-184">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="29b8e-185">La organización crea y almacena numerosos documentos relacionados con cada empleado.</span><span class="sxs-lookup"><span data-stu-id="29b8e-185">An organization creates and stores numerous employee-related documents per employee.</span></span> <span data-ttu-id="29b8e-186">Estos documentos se administran y conservan durante el tiempo de contratación del empleado.</span><span class="sxs-lookup"><span data-stu-id="29b8e-186">These documents are managed and retained during the employment of each employee.</span></span> <span data-ttu-id="29b8e-187">Sin embargo, cuando el empleado abandona la organización o deja de trabajar para ella, la organización esta comercial y legalmente obligada a conservar los documentos de ese empleado durante un período estipulado.</span><span class="sxs-lookup"><span data-stu-id="29b8e-187">However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="29b8e-188">Ahora si varios empleados dejan la organización todos los días, la organización debe activar el reloj de retención de cientos o miles de documentos cada día.</span><span class="sxs-lookup"><span data-stu-id="29b8e-188">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="29b8e-189">Además, se debe calcular el período de retención de cada uno de estos empleados con el siguiente formato: fecha de despido del empleado + número de días, meses o años en función del tipo de registro del empleado.</span><span class="sxs-lookup"><span data-stu-id="29b8e-189">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months, or years based on the type of the employee record.</span></span> <span data-ttu-id="29b8e-190">Por ejemplo, es posible que la compensación y la tramitación de beneficios del mismo empleado necesiten retenciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="29b8e-190">For example, worker’s compensation of the employee vs. benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="29b8e-191">El siguiente diagrama muestra cómo puede haber varias etiquetas asociadas a un único evento.</span><span class="sxs-lookup"><span data-stu-id="29b8e-191">The diagram below shows how there can be multiple labels that are associated with a single event.</span></span> <span data-ttu-id="29b8e-192">En este caso, todos los archivos de la etiqueta de indemnización del Trabajador y los que pertenecen a la etiqueta de beneficios del Trabajador se asocian a un único evento, que es la salida del empleado.</span><span class="sxs-lookup"><span data-stu-id="29b8e-192">Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event, which is the employee leaving the organization.</span></span> <span data-ttu-id="29b8e-193">Cada uno de estos archivos diferentes tiene diferentes relojes de retención.</span><span class="sxs-lookup"><span data-stu-id="29b8e-193">Each of these different files has different retention clocks.</span></span> <span data-ttu-id="29b8e-194">Por lo tanto, cuando un empleado deja la organización, cada archivo dentro de una misma etiqueta experimenta un período de retención diferente.</span><span class="sxs-lookup"><span data-stu-id="29b8e-194">So, when an employee leaves the organization, these files within each label experience a different retention period.</span></span> <span data-ttu-id="29b8e-195">Activar todos estos relojes de retención diferentes para cada tipo de archivo o etiqueta en un solo empleado es una tarea muy desafiante.</span><span class="sxs-lookup"><span data-stu-id="29b8e-195">Triggering all these different retention clocks for each file type or label for each employee is a very challenging task.</span></span> <span data-ttu-id="29b8e-196">Imagine este proceso con varios empleados.</span><span class="sxs-lookup"><span data-stu-id="29b8e-196">Imagine doing this for multiple employees.</span></span>

![Diagrama de tipo de evento, evento y etiquetas](media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="29b8e-198">Por lo tanto, un proceso automatizado para activar estos relojes de retención diferentes para varios empleados permitirá ahorrar tiempo, evitar errores y lograr una alta eficiencia.</span><span class="sxs-lookup"><span data-stu-id="29b8e-198">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free, and extremely efficient.</span></span>

<span data-ttu-id="29b8e-199">**Configuración de retención automatizada basada en eventos para este escenario:**</span><span class="sxs-lookup"><span data-stu-id="29b8e-199">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de funciones y acciones para el escenario del empleado que deja la organización](media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="29b8e-201">La administración crea carpetas del empleado en un conjunto de documentos denominado Naiara Padilla, David Pulido.</span><span class="sxs-lookup"><span data-stu-id="29b8e-201">Admin creates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="29b8e-202">La administración agrega archivos del empleado, como los de beneficios, nómina o compensación del trabajador a cada carpeta de empleado.</span><span class="sxs-lookup"><span data-stu-id="29b8e-202">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder.</span></span>

  - <span data-ttu-id="29b8e-203">La administración asigna el id. de activo a la carpeta de cada empleado.</span><span class="sxs-lookup"><span data-stu-id="29b8e-203">Admin assigns Asset ID to each employee folder.</span></span> 

  - <span data-ttu-id="29b8e-204">La administración de SSC inicia sesión en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="29b8e-204">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="29b8e-205">La administración de SCC crea tipos de eventos relacionados con el empleado como “Desvinculación del empleado”, “Contratación del empleados”.</span><span class="sxs-lookup"><span data-stu-id="29b8e-205">SCC Admin creates employee-related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="29b8e-206">La administración de SCC crea la etiqueta de "Retención de empleados".</span><span class="sxs-lookup"><span data-stu-id="29b8e-206">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="29b8e-207">Esta etiqueta de "Retención de empleados" se publica y se aplican manual o automáticamente a los archivos de empleado en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="29b8e-207">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint.</span></span>

  - <span data-ttu-id="29b8e-208">Un sistema de administración de Recursos Humanos como Workday puede trabajar con Microsoft Flow para ejecutarse periódicamente para administrar archivos del empleado.</span><span class="sxs-lookup"><span data-stu-id="29b8e-208">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files.</span></span>

  - <span data-ttu-id="29b8e-209">Cuando un empleado deja la organización, Flow activa la API de REST de retención basada en eventos de M365 que inicia el reloj de retención de archivos específicos del empleado.</span><span class="sxs-lookup"><span data-stu-id="29b8e-209">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="29b8e-210">Usar Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="29b8e-210">Using Microsoft Flow</span></span>

<span data-ttu-id="29b8e-211">Paso 1: crear un flujo para crear un evento mediante la API de REST de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="29b8e-211">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Usar Flow para crear un evento](media/automate-event-driven-retention-flow-1.png)

![Usar Flow para llamar a la API de REST](media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="29b8e-214">Crear un evento</span><span class="sxs-lookup"><span data-stu-id="29b8e-214">Create an event</span></span>

<span data-ttu-id="29b8e-215">Código de ejemplo para llamar a la API de REST</span><span class="sxs-lookup"><span data-stu-id="29b8e-215">Sample code to call the REST API</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="29b8e-216">Método</span><span class="sxs-lookup"><span data-stu-id="29b8e-216">Method</span></span></th>
<th><span data-ttu-id="29b8e-217">POST</span><span class="sxs-lookup"><span data-stu-id="29b8e-217">POST</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="29b8e-218">URL</span><span class="sxs-lookup"><span data-stu-id="29b8e-218">URL</span></span></td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="29b8e-219">Encabezados</span><span class="sxs-lookup"><span data-stu-id="29b8e-219">Headers</span></span></td>
<td><span data-ttu-id="29b8e-220">Tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="29b8e-220">Content-Type</span></span></td>
<td><span data-ttu-id="29b8e-221">aplicación/atom+xml</span><span class="sxs-lookup"><span data-stu-id="29b8e-221">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="29b8e-222">Cuerpo</span><span class="sxs-lookup"><span data-stu-id="29b8e-222">Body</span></span></td>
<td><p><span data-ttu-id="29b8e-223">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-223">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="29b8e-224">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="29b8e-224">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="29b8e-225">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="29b8e-225">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="29b8e-226">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-226">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="29b8e-227">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-227">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="29b8e-228">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-228">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="29b8e-229">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-229">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="29b8e-230">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-230">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="29b8e-231">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-231">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="29b8e-232">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-232">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="29b8e-233">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-233">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="29b8e-234">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-234">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span></span></p>
<p><span data-ttu-id="29b8e-235">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-235">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="29b8e-236">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-236">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="29b8e-237">&lt;/entry&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-237">&lt;/entry&gt;</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="29b8e-238">Autenticación</span><span class="sxs-lookup"><span data-stu-id="29b8e-238">Authentication</span></span></td>
<td><span data-ttu-id="29b8e-239">Básica</span><span class="sxs-lookup"><span data-stu-id="29b8e-239">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="29b8e-240">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="29b8e-240">Username</span></span></td>
<td><span data-ttu-id="29b8e-241">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="29b8e-241">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="29b8e-242">Contraseña</span><span class="sxs-lookup"><span data-stu-id="29b8e-242">Password</span></span></td>
<td><span data-ttu-id="29b8e-243">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="29b8e-243">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a><span data-ttu-id="29b8e-244">Parámetros disponibles</span><span class="sxs-lookup"><span data-stu-id="29b8e-244">Available parameters</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="29b8e-245"><strong>Parámetros</strong></span><span class="sxs-lookup"><span data-stu-id="29b8e-245"><strong>Parameters</strong></span></span></th>
<th><span data-ttu-id="29b8e-246"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="29b8e-246"><strong>Description</strong></span></span></th>
<th><span data-ttu-id="29b8e-247"><strong>Notas</strong></span><span class="sxs-lookup"><span data-stu-id="29b8e-247"><strong>Notes</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="29b8e-248">&lt;d:Name&gt;&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-248">&lt;d:Name&gt;&lt;/d:Name&gt;</span></span></td>
<td><span data-ttu-id="29b8e-249">Escribe un nombre único para el evento.</span><span class="sxs-lookup"><span data-stu-id="29b8e-249">Provide a unique name for the event,</span></span></td>
<td><span data-ttu-id="29b8e-p121">No puede contener espacios finales ni los siguientes caracteres: % \* \ &amp; &lt; &gt; | # ? , : ;</span><span class="sxs-lookup"><span data-stu-id="29b8e-p121">Cannot contain trailing spaces, and the following characters: % \* \ &amp; &lt; &gt; | # ? , : ;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="29b8e-252">&lt;d:eventType&gt;&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-252">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span></span></td>
<td><span data-ttu-id="29b8e-253">Escribe el nombre del tipo de evento (o Guid)</span><span class="sxs-lookup"><span data-stu-id="29b8e-253">Enter event type name (or Guid),</span></span></td>
<td><span data-ttu-id="29b8e-p122">Ejemplo: "Desvinculación del empleado". El tipo de evento debe estar asociado con una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="29b8e-p122">Example: “Employee termination”. Event type has to be associated with a retention label.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="29b8e-256">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-256">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span></span></td>
<td><span data-ttu-id="29b8e-257">Escribe "ComplianceAssetId:" + Id. de empleado</span><span class="sxs-lookup"><span data-stu-id="29b8e-257">Enter “ComplianceAssetId:” + employee Id</span></span></td>
<td><span data-ttu-id="29b8e-258">Ejemplo:&quot;ComplianceAssetId:12345&quot;</span><span class="sxs-lookup"><span data-stu-id="29b8e-258">Example:&quot;ComplianceAssetId:12345&quot;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="29b8e-259">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-259">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span></span></td>
<td><span data-ttu-id="29b8e-260">Fecha y hora del evento</span><span class="sxs-lookup"><span data-stu-id="29b8e-260">Event Date and Time</span></span></td>
<td><p><span data-ttu-id="29b8e-261">Formato: aaaa-MM-ddTHH:mm:ssZ, ejemplo:</span><span class="sxs-lookup"><span data-stu-id="29b8e-261">Format: yyyy-MM-ddTHH:mm:ssZ, Example:</span></span></p>
<p><span data-ttu-id="29b8e-262">2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="29b8e-262">2018-12-01T00:00:00Z</span></span></p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="29b8e-263">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="29b8e-263">Response codes</span></span>

| <span data-ttu-id="29b8e-264">**Código de respuesta**</span><span class="sxs-lookup"><span data-stu-id="29b8e-264">**Response Code**</span></span> | <span data-ttu-id="29b8e-265">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="29b8e-265">**Description**</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="29b8e-266">302</span><span class="sxs-lookup"><span data-stu-id="29b8e-266">302</span></span>               | <span data-ttu-id="29b8e-267">Redirigir</span><span class="sxs-lookup"><span data-stu-id="29b8e-267">Redirect</span></span>              |
| <span data-ttu-id="29b8e-268">201</span><span class="sxs-lookup"><span data-stu-id="29b8e-268">201</span></span>               | <span data-ttu-id="29b8e-269">Fecha de creación</span><span class="sxs-lookup"><span data-stu-id="29b8e-269">Created</span></span>               |
| <span data-ttu-id="29b8e-270">403</span><span class="sxs-lookup"><span data-stu-id="29b8e-270">403</span></span>               | <span data-ttu-id="29b8e-271">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="29b8e-271">Authorization Failed</span></span>  |
| <span data-ttu-id="29b8e-272">401</span><span class="sxs-lookup"><span data-stu-id="29b8e-272">401</span></span>               | <span data-ttu-id="29b8e-273">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="29b8e-273">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="29b8e-274">Obtener eventos según el intervalo de tiempo</span><span class="sxs-lookup"><span data-stu-id="29b8e-274">Get Events based on time range</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="29b8e-275">Método</span><span class="sxs-lookup"><span data-stu-id="29b8e-275">Method</span></span></th>
<th><span data-ttu-id="29b8e-276">GET</span><span class="sxs-lookup"><span data-stu-id="29b8e-276">GET</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="29b8e-277">URL</span><span class="sxs-lookup"><span data-stu-id="29b8e-277">URL</span></span></td>
<td><ol start="4" type="1">
<li><p><span data-ttu-id="29b8e-278">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp; EndDateTime = 2019-16: 01</span><span class="sxs-lookup"><span data-stu-id="29b8e-278">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span></span></p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="29b8e-279">Encabezados</span><span class="sxs-lookup"><span data-stu-id="29b8e-279">Headers</span></span></td>
<td><span data-ttu-id="29b8e-280">Tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="29b8e-280">Content-Type</span></span></td>
<td><span data-ttu-id="29b8e-281">aplicación/atom+xml</span><span class="sxs-lookup"><span data-stu-id="29b8e-281">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="29b8e-282">Autenticación</span><span class="sxs-lookup"><span data-stu-id="29b8e-282">Authentication</span></span></td>
<td><span data-ttu-id="29b8e-283">Básica</span><span class="sxs-lookup"><span data-stu-id="29b8e-283">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="29b8e-284">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="29b8e-284">Username</span></span></td>
<td><span data-ttu-id="29b8e-285">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="29b8e-285">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="29b8e-286">Contraseña</span><span class="sxs-lookup"><span data-stu-id="29b8e-286">Password</span></span></td>
<td><span data-ttu-id="29b8e-287">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="29b8e-287">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="29b8e-288">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="29b8e-288">Response codes</span></span>

| <span data-ttu-id="29b8e-289">**Código de respuesta**</span><span class="sxs-lookup"><span data-stu-id="29b8e-289">**Response Code**</span></span> | <span data-ttu-id="29b8e-290">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="29b8e-290">**Description**</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="29b8e-291">200</span><span class="sxs-lookup"><span data-stu-id="29b8e-291">200</span></span>               | <span data-ttu-id="29b8e-292">Aceptar, una lista de eventos de atom+ xml</span><span class="sxs-lookup"><span data-stu-id="29b8e-292">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="29b8e-293">404</span><span class="sxs-lookup"><span data-stu-id="29b8e-293">404</span></span>               | <span data-ttu-id="29b8e-294">No encontrado</span><span class="sxs-lookup"><span data-stu-id="29b8e-294">Not found</span></span>                         |
| <span data-ttu-id="29b8e-295">302</span><span class="sxs-lookup"><span data-stu-id="29b8e-295">302</span></span>               | <span data-ttu-id="29b8e-296">Redirigir</span><span class="sxs-lookup"><span data-stu-id="29b8e-296">Redirect</span></span>                          |
| <span data-ttu-id="29b8e-297">401</span><span class="sxs-lookup"><span data-stu-id="29b8e-297">401</span></span>               | <span data-ttu-id="29b8e-298">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="29b8e-298">Authorization Failed</span></span>              |
| <span data-ttu-id="29b8e-299">403</span><span class="sxs-lookup"><span data-stu-id="29b8e-299">403</span></span>               | <span data-ttu-id="29b8e-300">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="29b8e-300">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="29b8e-301">Obtén un objeto por id.</span><span class="sxs-lookup"><span data-stu-id="29b8e-301">Get an event by ID</span></span>

| <span data-ttu-id="29b8e-302">Método</span><span class="sxs-lookup"><span data-stu-id="29b8e-302">Method</span></span>         | <span data-ttu-id="29b8e-303">GET</span><span class="sxs-lookup"><span data-stu-id="29b8e-303">GET</span></span>   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| <span data-ttu-id="29b8e-304">URL</span><span class="sxs-lookup"><span data-stu-id="29b8e-304">URL</span></span>            | <span data-ttu-id="29b8e-305">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span><span class="sxs-lookup"><span data-stu-id="29b8e-305">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span></span> |                      |
| <span data-ttu-id="29b8e-306">Encabezado</span><span class="sxs-lookup"><span data-stu-id="29b8e-306">Header</span></span>         | <span data-ttu-id="29b8e-307">Tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="29b8e-307">Content-Type</span></span>                                                                                                                                                                                                                                                       | <span data-ttu-id="29b8e-308">aplicación/atom+xml</span><span class="sxs-lookup"><span data-stu-id="29b8e-308">application/atom+xml</span></span> |
| <span data-ttu-id="29b8e-309">Autenticación</span><span class="sxs-lookup"><span data-stu-id="29b8e-309">Authentication</span></span> | <span data-ttu-id="29b8e-310">Básica</span><span class="sxs-lookup"><span data-stu-id="29b8e-310">Basic</span></span>                                                                                                                                                                                                                                                              |                      |
| <span data-ttu-id="29b8e-311">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="29b8e-311">Username</span></span>       | <span data-ttu-id="29b8e-312">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="29b8e-312">“Complianceuser”</span></span>                                                                                                                                                                                                                                                   |                      |
| <span data-ttu-id="29b8e-313">Contraseña</span><span class="sxs-lookup"><span data-stu-id="29b8e-313">Password</span></span>       | <span data-ttu-id="29b8e-314">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="29b8e-314">“Compliancepassword”</span></span>                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a><span data-ttu-id="29b8e-315">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="29b8e-315">Response codes</span></span>

| <span data-ttu-id="29b8e-316">**Código de respuesta**</span><span class="sxs-lookup"><span data-stu-id="29b8e-316">**Response Code**</span></span> | <span data-ttu-id="29b8e-317">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="29b8e-317">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="29b8e-318">200</span><span class="sxs-lookup"><span data-stu-id="29b8e-318">200</span></span>               | <span data-ttu-id="29b8e-319">Aceptar, el cuerpo de la respuesta contiene el evento en atom+ xml</span><span class="sxs-lookup"><span data-stu-id="29b8e-319">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="29b8e-320">404</span><span class="sxs-lookup"><span data-stu-id="29b8e-320">404</span></span>               | <span data-ttu-id="29b8e-321">No encontrado</span><span class="sxs-lookup"><span data-stu-id="29b8e-321">Not found</span></span>                                            |
| <span data-ttu-id="29b8e-322">302</span><span class="sxs-lookup"><span data-stu-id="29b8e-322">302</span></span>               | <span data-ttu-id="29b8e-323">Redirigir</span><span class="sxs-lookup"><span data-stu-id="29b8e-323">Redirect</span></span>                                             |
| <span data-ttu-id="29b8e-324">401</span><span class="sxs-lookup"><span data-stu-id="29b8e-324">401</span></span>               | <span data-ttu-id="29b8e-325">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="29b8e-325">Authorization Failed</span></span>                                 |
| <span data-ttu-id="29b8e-326">403</span><span class="sxs-lookup"><span data-stu-id="29b8e-326">403</span></span>               | <span data-ttu-id="29b8e-327">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="29b8e-327">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="29b8e-328">Obtén un evento por nombre</span><span class="sxs-lookup"><span data-stu-id="29b8e-328">Get an event by name</span></span>

| <span data-ttu-id="29b8e-329">Método</span><span class="sxs-lookup"><span data-stu-id="29b8e-329">Method</span></span>         | <span data-ttu-id="29b8e-330">GET</span><span class="sxs-lookup"><span data-stu-id="29b8e-330">GET</span></span>       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| <span data-ttu-id="29b8e-331">URL</span><span class="sxs-lookup"><span data-stu-id="29b8e-331">URL</span></span>            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| <span data-ttu-id="29b8e-332">Encabezados</span><span class="sxs-lookup"><span data-stu-id="29b8e-332">Headers</span></span>        | <span data-ttu-id="29b8e-333">Tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="29b8e-333">Content-Type</span></span>                                                                                                                                 | <span data-ttu-id="29b8e-334">aplicación/atom+xml</span><span class="sxs-lookup"><span data-stu-id="29b8e-334">application/atom+xml</span></span> |
| <span data-ttu-id="29b8e-335">Autenticación</span><span class="sxs-lookup"><span data-stu-id="29b8e-335">Authentication</span></span> | <span data-ttu-id="29b8e-336">Básica</span><span class="sxs-lookup"><span data-stu-id="29b8e-336">Basic</span></span>                                                                                                                                        |                      |
| <span data-ttu-id="29b8e-337">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="29b8e-337">Username</span></span>       | <span data-ttu-id="29b8e-338">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="29b8e-338">“Complianceuser”</span></span>                                                                                                                             |                      |
| <span data-ttu-id="29b8e-339">Contraseña</span><span class="sxs-lookup"><span data-stu-id="29b8e-339">Password</span></span>       | <span data-ttu-id="29b8e-340">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="29b8e-340">“Compliancepassword”</span></span>                                                                                                                         |                      |

##### <a name="response-codes"></a><span data-ttu-id="29b8e-341">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="29b8e-341">Response codes</span></span>

| <span data-ttu-id="29b8e-342">**Código de respuesta**</span><span class="sxs-lookup"><span data-stu-id="29b8e-342">**Response Code**</span></span> | <span data-ttu-id="29b8e-343">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="29b8e-343">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="29b8e-344">200</span><span class="sxs-lookup"><span data-stu-id="29b8e-344">200</span></span>               | <span data-ttu-id="29b8e-345">Aceptar, el cuerpo de la respuesta contiene el evento en atom+ xml</span><span class="sxs-lookup"><span data-stu-id="29b8e-345">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="29b8e-346">404</span><span class="sxs-lookup"><span data-stu-id="29b8e-346">404</span></span>               | <span data-ttu-id="29b8e-347">No encontrado</span><span class="sxs-lookup"><span data-stu-id="29b8e-347">Not found</span></span>                                            |
| <span data-ttu-id="29b8e-348">302</span><span class="sxs-lookup"><span data-stu-id="29b8e-348">302</span></span>               | <span data-ttu-id="29b8e-349">Redirigir</span><span class="sxs-lookup"><span data-stu-id="29b8e-349">Redirect</span></span>                                             |
| <span data-ttu-id="29b8e-350">401</span><span class="sxs-lookup"><span data-stu-id="29b8e-350">401</span></span>               | <span data-ttu-id="29b8e-351">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="29b8e-351">Authorization Failed</span></span>                                 |
| <span data-ttu-id="29b8e-352">403</span><span class="sxs-lookup"><span data-stu-id="29b8e-352">403</span></span>               | <span data-ttu-id="29b8e-353">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="29b8e-353">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="29b8e-354">Uso de PowerShell (ver.6 o posterior) o cualquier cliente HTTP</span><span class="sxs-lookup"><span data-stu-id="29b8e-354">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="29b8e-355">Paso 1: Conéctate a PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29b8e-355">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="29b8e-356">Paso 2: Ejecuta el siguiente script.</span><span class="sxs-lookup"><span data-stu-id="29b8e-356">Step 2: Run the following script.</span></span>

<table>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29b8e-357">param([string]$baseUri)</span><span class="sxs-lookup"><span data-stu-id="29b8e-357">param([string]$baseUri)</span></span></p>
<p><span data-ttu-id="29b8e-358">$userName = &quot;UserName&quot;</span><span class="sxs-lookup"><span data-stu-id="29b8e-358">$userName = &quot;UserName&quot;</span></span></p>
<p><span data-ttu-id="29b8e-359">$password = &quot;Password&quot;</span><span class="sxs-lookup"><span data-stu-id="29b8e-359">$password = &quot;Password&quot;</span></span></p>
<p><span data-ttu-id="29b8e-360">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span><span class="sxs-lookup"><span data-stu-id="29b8e-360">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span></span></p>
<p><span data-ttu-id="29b8e-361">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span><span class="sxs-lookup"><span data-stu-id="29b8e-361">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span></span></p>
<p><span data-ttu-id="29b8e-362">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span><span class="sxs-lookup"><span data-stu-id="29b8e-362">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span></span></p>
<p><span data-ttu-id="29b8e-363">Write-Host &quot;Comienza a crear un evento con el nombre: $EventName&quot;</span><span class="sxs-lookup"><span data-stu-id="29b8e-363">Write-Host &quot;Start to create an event with name: $EventName&quot;</span></span></p>
<p><span data-ttu-id="29b8e-364">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-364">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="29b8e-365">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="29b8e-365">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="29b8e-366">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="29b8e-366">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="29b8e-367">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-367">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="29b8e-368">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-368">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="29b8e-369">&lt;actualizado&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-369">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="29b8e-370">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-370">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="29b8e-371">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-371">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="29b8e-372">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-372">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="29b8e-373">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-373">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="29b8e-374">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-374">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="29b8e-375">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-375">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="29b8e-376">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="29b8e-376">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="29b8e-377">&lt;/entry&gt;&quot;</span><span class="sxs-lookup"><span data-stu-id="29b8e-377">&lt;/entry&gt;&quot;</span></span></p>
<p><span data-ttu-id="29b8e-378">$event = $null</span><span class="sxs-lookup"><span data-stu-id="29b8e-378">$event = $null</span></span></p>
<p><span data-ttu-id="29b8e-379">probar</span><span class="sxs-lookup"><span data-stu-id="29b8e-379">try</span></span></p>
<p><span data-ttu-id="29b8e-380">{</span><span class="sxs-lookup"><span data-stu-id="29b8e-380">{</span></span></p>
<p><span data-ttu-id="29b8e-381">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="29b8e-381">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="29b8e-382">}</span><span class="sxs-lookup"><span data-stu-id="29b8e-382">}</span></span></p>
<p><span data-ttu-id="29b8e-383">catch</span><span class="sxs-lookup"><span data-stu-id="29b8e-383">catch</span></span></p>
<p><span data-ttu-id="29b8e-384">{</span><span class="sxs-lookup"><span data-stu-id="29b8e-384">{</span></span></p>
<p><span data-ttu-id="29b8e-385">$response = $_. Exception.Response</span><span class="sxs-lookup"><span data-stu-id="29b8e-385">$response = $_.Exception.Response</span></span></p>
<p><span data-ttu-id="29b8e-386">if($response.StatusCode -eq &quot;Redirect&quot;)</span><span class="sxs-lookup"><span data-stu-id="29b8e-386">if($response.StatusCode -eq &quot;Redirect&quot;)</span></span></p>
<p><span data-ttu-id="29b8e-387">{</span><span class="sxs-lookup"><span data-stu-id="29b8e-387">{</span></span></p>
<p><span data-ttu-id="29b8e-388">$url = $response.Headers.Location</span><span class="sxs-lookup"><span data-stu-id="29b8e-388">$url = $response.Headers.Location</span></span></p>
<p><span data-ttu-id="29b8e-389">Write-Host &quot;redirected to $url&quot;</span><span class="sxs-lookup"><span data-stu-id="29b8e-389">Write-Host &quot;redirected to $url&quot;</span></span></p>
<p><span data-ttu-id="29b8e-390">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="29b8e-390">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="29b8e-391">}</span><span class="sxs-lookup"><span data-stu-id="29b8e-391">}</span></span></p>
<p><span data-ttu-id="29b8e-392">}</span><span class="sxs-lookup"><span data-stu-id="29b8e-392">}</span></span></p>
<p><span data-ttu-id="29b8e-393">$event | fl \*</span><span class="sxs-lookup"><span data-stu-id="29b8e-393">$event | fl \*</span></span></p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="29b8e-394">Comprobar el resultado en ambas opciones.</span><span class="sxs-lookup"><span data-stu-id="29b8e-394">Verify the outcome in both options</span></span>

<span data-ttu-id="29b8e-395">Paso 1: Ir al Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="29b8e-395">Step 1: Go to the Security & Compliance Center.</span></span>

<span data-ttu-id="29b8e-396">Paso 2: seleccione los **eventos** en **control de la información**.</span><span class="sxs-lookup"><span data-stu-id="29b8e-396">Step 2: Select **Events** under **Information governance**.</span></span>

<span data-ttu-id="29b8e-397">Paso 3: Comprobar que se creó el evento.</span><span class="sxs-lookup"><span data-stu-id="29b8e-397">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="29b8e-398">De forma similar, también se pueden usar las opciones anteriores para automatizar la retención basada en eventos para los siguientes escenarios.</span><span class="sxs-lookup"><span data-stu-id="29b8e-398">Similarly, the above options to automate event-based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="29b8e-399">Escenario 2: Contratos que expiran</span><span class="sxs-lookup"><span data-stu-id="29b8e-399">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="29b8e-400">Una organización puede tener varios registros para un contrato único con clientes, proveedores y asociados.</span><span class="sxs-lookup"><span data-stu-id="29b8e-400">An organization can have multiple records for a single contract with customers, vendors, and partners.</span></span> <span data-ttu-id="29b8e-401">Estos documentos pueden residir en una biblioteca de documentos como SharePoint.</span><span class="sxs-lookup"><span data-stu-id="29b8e-401">These documents can reside in a document library like SharePoint.</span></span> <span data-ttu-id="29b8e-402">Con la finalización de un contrato empieza el periodo de retención de los documentos asociados al contrato.</span><span class="sxs-lookup"><span data-stu-id="29b8e-402">The end of a contract determines the start of the retention period of the documents associated with the contract.</span></span> <span data-ttu-id="29b8e-403">Por ejemplo, se deben conservar todos los registros relacionados con un contrato cinco años después de que expire.</span><span class="sxs-lookup"><span data-stu-id="29b8e-403">For example, all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="29b8e-404">El evento que desencadena el período de retención de cinco años es la expiración del contrato.</span><span class="sxs-lookup"><span data-stu-id="29b8e-404">The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="29b8e-405">Un sistema de administración de relaciones de cliente (CRM) puede trabajar con Microsoft 365 y activar la retención de documentos del contrato.</span><span class="sxs-lookup"><span data-stu-id="29b8e-405">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents</span></span>

<span data-ttu-id="29b8e-406">**Configuración de retención automatizada basada en eventos para este escenario:**</span><span class="sxs-lookup"><span data-stu-id="29b8e-406">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de los funciones y tareas para escenarios de expiración del contrato](media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="29b8e-408">La administración crea una biblioteca de SharePoint con carpetas diferentes para cada tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="29b8e-408">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="29b8e-409">La administración agrega archivos del contrato como contratos de licencia y contratos de desarrollo para cada carpeta del contrato.</span><span class="sxs-lookup"><span data-stu-id="29b8e-409">Admin adds contract files such as License Contracts, Development Contracts to each contract folder.</span></span>

  - <span data-ttu-id="29b8e-410">La administración asigna el id. de activo a cada carpeta de contrato.</span><span class="sxs-lookup"><span data-stu-id="29b8e-410">Admin assigns Asset ID to each contract folder.</span></span>

  - <span data-ttu-id="29b8e-411">La administración de SSC inicia sesión en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="29b8e-411">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="29b8e-412">La administración de SCC crea tipos de eventos relacionados con el contrato como eventos de "Creación del contrato" y de "Expiración del contrato".</span><span class="sxs-lookup"><span data-stu-id="29b8e-412">SCC Admin creates contract-related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="29b8e-413">La administración de SCC crea la etiqueta "Expiración del contrato".</span><span class="sxs-lookup"><span data-stu-id="29b8e-413">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="29b8e-414">Esta etiqueta de "Expiración del contrato" se publica y se aplican de forma manual o automática a los archivos del contrato en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="29b8e-414">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint.</span></span>

  - <span data-ttu-id="29b8e-415">El sistema de administración de contrato puede trabajar con Microsoft Flow o una aplicación similar para ejecutarse periódicamente para administrar archivos de contrato.</span><span class="sxs-lookup"><span data-stu-id="29b8e-415">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files.</span></span>

  - <span data-ttu-id="29b8e-416">Si un contrato vence, Microsoft Flow activará la API de REST de retención basada en eventos de M365 que iniciará el reloj de retención de archivos específicos del contrato.</span><span class="sxs-lookup"><span data-stu-id="29b8e-416">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="29b8e-417">Escenario 3: Final de fabricación de productos</span><span class="sxs-lookup"><span data-stu-id="29b8e-417">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="29b8e-p124">Una empresa de elaboración que fabrica diferentes líneas de productos crea varias especificaciones de elaboración y documentos de precios. Cuando el producto ya no se fabrica, todas las especificaciones y documentos vinculados a este producto deben conservarse durante un período específico después del final de la vida útil del producto.</span><span class="sxs-lookup"><span data-stu-id="29b8e-p124">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="29b8e-420">Un sistema de planeación de recursos empresariales (ERP) puede trabajar con Microsoft 365 y Microsoft Flow para activar la retención.</span><span class="sxs-lookup"><span data-stu-id="29b8e-420">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="29b8e-421">**Configuración de retención automatizada basada en eventos para este escenario:**</span><span class="sxs-lookup"><span data-stu-id="29b8e-421">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de las funciones y tareas para escenarios de ciclo de vida del producto](media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="29b8e-423">La administración crea carpetas de productos en el conjunto de documentos como Producto 1, Producto 2, etc.</span><span class="sxs-lookup"><span data-stu-id="29b8e-423">Admin creates product folders in the Document set such as Product 1, Product 2, and so on.</span></span>

  - <span data-ttu-id="29b8e-424">La administración agrega los archivos de productos como Especificaciones de fabricación, Precio del producto y Licencias del producto a cada carpeta de producto.</span><span class="sxs-lookup"><span data-stu-id="29b8e-424">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder.</span></span>

  - <span data-ttu-id="29b8e-425">La administración le asigna el id. de activo a cada carpeta del producto.</span><span class="sxs-lookup"><span data-stu-id="29b8e-425">Admin assigns Asset ID to each product folder.</span></span>

  - <span data-ttu-id="29b8e-426">La administración de SSC inicia sesión en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="29b8e-426">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="29b8e-427">La administración de SCC crea tipos de eventos relacionados con el empleado como "Inicio de fabricación del producto" y "Final de fabricación del producto".</span><span class="sxs-lookup"><span data-stu-id="29b8e-427">SCC Admin creates employee-related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="29b8e-428">La administración de SCC crea la etiqueta "Final de fabricación del producto".</span><span class="sxs-lookup"><span data-stu-id="29b8e-428">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="29b8e-429">Esta etiqueta de "Final de fabricación del producto" se publica y se aplica de forma manual o automática a los archivos del producto en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="29b8e-429">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint.</span></span>

  - <span data-ttu-id="29b8e-430">Los sistemas de ERP pueden funcionar con Microsoft Flow o con aplicaciones similares para ejecutarse periódicamente para administrar archivos del producto.</span><span class="sxs-lookup"><span data-stu-id="29b8e-430">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files.</span></span>

  - <span data-ttu-id="29b8e-431">Si se termina la fabricación de un producto, Microsoft Flow activará la API de REST de retención basada en eventos de M365 que iniciará el reloj de retención de archivos específicos del producto.</span><span class="sxs-lookup"><span data-stu-id="29b8e-431">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="29b8e-432">Apéndice</span><span class="sxs-lookup"><span data-stu-id="29b8e-432">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="29b8e-433">Cómo usar los resultados de respuesta Redirect 302 para llamar a la API de REST</span><span class="sxs-lookup"><span data-stu-id="29b8e-433">Using Redirect 302 response results to call the REST API</span></span>

1. <span data-ttu-id="29b8e-434">Invocar una llamada de evento de retención POST con la URL de la API de REST <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (se requieren permisos de administrador global).</span><span class="sxs-lookup"><span data-stu-id="29b8e-434">Invoke a POST retention event call using the REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required)</span></span>

2. <span data-ttu-id="29b8e-p125">Comprobar el código de respuesta. Si es 302, obtener la dirección URL redirigida de la propiedad de ubicación del encabezado de respuesta.</span><span class="sxs-lookup"><span data-stu-id="29b8e-p125">Check the response code. If it’s 302, then get the redirected URL from Location property of the response header</span></span>

3. <span data-ttu-id="29b8e-437">Invocar la llamada al evento de retención POST nuevamente mediante el URL redireccionado.</span><span class="sxs-lookup"><span data-stu-id="29b8e-437">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="29b8e-438">Créditos</span><span class="sxs-lookup"><span data-stu-id="29b8e-438">Credits</span></span>

<span data-ttu-id="29b8e-439">Este tema fue revisado por:</span><span class="sxs-lookup"><span data-stu-id="29b8e-439">This topic was reviewed by:</span></span>

<span data-ttu-id="29b8e-440">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="29b8e-440">Antonio Maio</span></span><br/><span data-ttu-id="29b8e-441">MVP de servicios y aplicaciones de Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="29b8e-441">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="29b8e-442">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="29b8e-442">Antonio.Maio@Protiviti.com</span></span>
