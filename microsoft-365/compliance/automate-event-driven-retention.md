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
ms.openlocfilehash: 1e7255fe8f21328b93ac95c0377ccd9017195caa
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636368"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="0a620-103">Retención automática basada en eventos</span><span class="sxs-lookup"><span data-stu-id="0a620-103">Automate event-based retention</span></span>

><span data-ttu-id="0a620-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="0a620-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="0a620-p101">La explosión de contenido en las organizaciones y la forma en la que se convierte en ROT (redundante obsoleto, trivial) constituye un asunto importante. Para seguir satisfaciendo los desafíos de cumplimiento legal, normativo y empresarial, las organizaciones deben conservar y proteger la información importante y encontrar rápidamente lo que es relevante. Conservar solo información importante y relevante es clave para el éxito de la organización.</span><span class="sxs-lookup"><span data-stu-id="0a620-p101">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to an organization's success.</span></span>

<span data-ttu-id="0a620-p102">Para cumplir esta necesidad, las organizaciones pueden beneficiarse de las soluciones de retención del Centro de seguridad y cumplimiento de Office 365. La retención puede activarse con [etiquetas de retención](labels.md). Una etiqueta de retención tiene la opción de [basar el período de retención en un evento específico](event-driven-retention.md). Normalmente, el período de retención se basa en una fecha conocida, como la fecha de creación o fecha de última modificación del contenido. Sin embargo, las organizaciones también tienen requisitos para eliminar el contenido en función de la ocurrencia de un evento, como 7 años después de que un empleado deje la organización.</span><span class="sxs-lookup"><span data-stu-id="0a620-p102">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span></span>

<span data-ttu-id="0a620-p103">Para garantizar que las normas eliminación de contenido cumplen con las normas, es imprescindible conocer cuándo sucede un evento. Con un volumen de contenido en rápido aumento, se torna cada vez más difícil retener y eliminar contenido de manera oportuna y que cumpla con las normas.</span><span class="sxs-lookup"><span data-stu-id="0a620-p103">To ensure compliant disposal of content, it's imperative to know when an event takes place. With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="0a620-p104">La retención basada en eventos soluciona este problema. En este tema se explica cómo configurar los flujos de procesos empresariales para automatizar la retención mediante eventos con la API de REST de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0a620-p104">Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="0a620-117">Acerca de la retención basada en eventos</span><span class="sxs-lookup"><span data-stu-id="0a620-117">About event-based retention</span></span>

<span data-ttu-id="0a620-p105">Una organización puede ser pequeña, mediana o grande. La cantidad de documentos empresariales, documentos legales, archivos de empleados, contratos y documentos de productos que se crean y administran a diario aumenta enormemente.</span><span class="sxs-lookup"><span data-stu-id="0a620-p105">An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span></span>

<span data-ttu-id="0a620-p106">Por ejemplo, cada día, decenas y cientos de empleados se unen a organizaciones y las dejan. El departamento de RR. HH. sigue creando, actualizando o eliminando documentos relacionados con los empleados según los requisitos empresariales. Este proceso está sujeto a las distintas directivas de retención indicadas para la empresa:</span><span class="sxs-lookup"><span data-stu-id="0a620-p106">For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="0a620-p107">**El período de retención de contenido puede ser una fecha conocida**, como la fecha en la que se creó, modificó por última vez o etiquetó el contenido. Por ejemplo, puedes retener documentos durante siete años después de su creación y luego eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="0a620-p107">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled. For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="0a620-p108">**El período de retención de contenido también puede ser una fecha desconocida**. Por ejemplo, con las etiquetas de retención, también puedes basar un período de retención en el momento en el que se produce un tipo de evento específico, como cuando un empleado deja la organización.</span><span class="sxs-lookup"><span data-stu-id="0a620-p108">**The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="0a620-p109">El evento desencadena el inicio del período de retención y a todo el contenido con una etiqueta aplicada para ese tipo de evento se le aplican las acciones de retención de la etiqueta. Esto se denomina retención basada en eventos: para obtener más información, consulta [Introducción a la retención basada en eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="0a620-p109">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention. To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="0a620-130">Configuración de la retención basada en eventos</span><span class="sxs-lookup"><span data-stu-id="0a620-130">Set up event-based retention</span></span>

<span data-ttu-id="0a620-131">Esta sección describe lo que es necesario realizar antes de retener contenido.</span><span class="sxs-lookup"><span data-stu-id="0a620-131">This section describes what needs to be done before retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="0a620-132">Identificación de funciones</span><span class="sxs-lookup"><span data-stu-id="0a620-132">Identify roles</span></span>

<span data-ttu-id="0a620-133">Identifica las diferentes funciones en una organización que realizan tareas de administración de registros y son responsables de una retención eficaz y eficiente de los documentos empresariales.</span><span class="sxs-lookup"><span data-stu-id="0a620-133">Identify the different roles in an organization that perform Record Management tasks and would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="0a620-134">**Rol**</span><span class="sxs-lookup"><span data-stu-id="0a620-134">**Persona**</span></span>| <span data-ttu-id="0a620-135">**Rol**</span><span class="sxs-lookup"><span data-stu-id="0a620-135">**Role**</span></span>|
  | - | - |
  | <span data-ttu-id="0a620-136">Administración</span><span class="sxs-lookup"><span data-stu-id="0a620-136">Admin</span></span> | <span data-ttu-id="0a620-137">Crea tipos de eventos de retención, etiquetas de retención y repositorios de registros en SharePoint</span><span class="sxs-lookup"><span data-stu-id="0a620-137">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="0a620-138">Administrador de registros</span><span class="sxs-lookup"><span data-stu-id="0a620-138">Records Manager</span></span>                                  | <span data-ttu-id="0a620-139">Proporciona detalles de cumplimiento y guías de políticas de retención y programaciones de retención</span><span class="sxs-lookup"><span data-stu-id="0a620-139">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="0a620-140">Administrador del sistema (empresa)</span><span class="sxs-lookup"><span data-stu-id="0a620-140">System Admin (business)</span></span>                          | <span data-ttu-id="0a620-141">Configura y administra sistemas externos para que funcionen con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0a620-141">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="0a620-142">Trabajador de información</span><span class="sxs-lookup"><span data-stu-id="0a620-142">Information Worker</span></span>                               | <span data-ttu-id="0a620-143">Administra el ciclo de vida de los procesos de su empresa (Recursos Humanos, Finanzas, TI, etc.)</span><span class="sxs-lookup"><span data-stu-id="0a620-143">Manages the lifecycle of their business process (HR, Finance, IT, and so on)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="0a620-144">Configuración del Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="0a620-144">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="0a620-145">La administración del cumplimiento crea un tipo de evento &ndash; como el final de una relación laboral, la finalización del contrato o el final de fabricación del producto.</span><span class="sxs-lookup"><span data-stu-id="0a620-145">Compliance admin creates an event type &ndash; for example, Employee Termination or Contract Expiration or End of Product Manufacturing.</span></span> <span data-ttu-id="0a620-146">(Consulte el proceso paso a paso en el artículo [Retención de eventos](event-driven-retention.md)).</span><span class="sxs-lookup"><span data-stu-id="0a620-146">(See the step-by-step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
2. <span data-ttu-id="0a620-147">La administración de cumplimiento crea una etiqueta de retención basada en un evento y asocia la etiqueta con un tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="0a620-147">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
    <span data-ttu-id="0a620-148">Hay 4 tipos de desencadenadores para las etiquetas de retención:</span><span class="sxs-lookup"><span data-stu-id="0a620-148">There are four types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="0a620-149">Fecha de creación</span><span class="sxs-lookup"><span data-stu-id="0a620-149">Create date</span></span>
                
    2. <span data-ttu-id="0a620-150">Última modificación</span><span class="sxs-lookup"><span data-stu-id="0a620-150">Last modified</span></span>
                
    3. <span data-ttu-id="0a620-151">Fecha de la etiqueta (cuando se etiquetó el contenido)</span><span class="sxs-lookup"><span data-stu-id="0a620-151">Label date (when the content was labeled)</span></span>
                
    4. <span data-ttu-id="0a620-152">Basado en eventos</span><span class="sxs-lookup"><span data-stu-id="0a620-152">Event-based</span></span>
    
3. <span data-ttu-id="0a620-153">La administración del cumplimiento publica la etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="0a620-153">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="0a620-154">Configurar SharePoint</span><span class="sxs-lookup"><span data-stu-id="0a620-154">Set up SharePoint</span></span>
   
<span data-ttu-id="0a620-155">Para crear un repositorio de registros, la administración del cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="0a620-155">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="0a620-156">Crea un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0a620-156">Creates a SharePoint site.</span></span>

2. <span data-ttu-id="0a620-157">Realiza una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="0a620-157">Does one of the following:</span></span>
        
    - <span data-ttu-id="0a620-p111">Crea una biblioteca de SharePoint: establece una etiqueta basada en eventos en el nivel de la biblioteca. Para obtener más información, consulta [Aplicar una etiqueta de retención predeterminada a todo el contenido de una biblioteca, carpeta o conjunto de documentos de SharePoint](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="0a620-p111">Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
    - <span data-ttu-id="0a620-160">Configura un conjunto de documentos en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0a620-160">Sets up a document set in SharePoint.</span></span> <span data-ttu-id="0a620-161">Para más información, vea [Introducción a los conjuntos de documentos](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span><span class="sxs-lookup"><span data-stu-id="0a620-161">For more information, see [Introduction to document sets](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span></span>
      
3. <span data-ttu-id="0a620-162">Asigna un ID. de activo para cada conjunto de documentos de empleado.</span><span class="sxs-lookup"><span data-stu-id="0a620-162">Assigns an asset ID to each employee document set.</span></span> <span data-ttu-id="0a620-163">Un ID. de activo es el nombre o código de producto usado por la organización. Por ejemplo, el número de empleado puede ser un ID. de activo.</span><span class="sxs-lookup"><span data-stu-id="0a620-163">An asset ID is a product name or code used by the organization, for example, Employee number can be an asset ID.</span></span> <span data-ttu-id="0a620-164">Al asignar el ID. de activo a una carpeta, cada elemento de esta carpeta hereda automáticamente el mismo ID. de activo.</span><span class="sxs-lookup"><span data-stu-id="0a620-164">By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID.</span></span> <span data-ttu-id="0a620-165">Esto significa que todos los elementos pueden tener un periodo de retención activado por el mismo evento.</span><span class="sxs-lookup"><span data-stu-id="0a620-165">This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="0a620-166">Formas de desencadenar la retención basada en eventos</span><span class="sxs-lookup"><span data-stu-id="0a620-166">Ways to trigger event-based retention</span></span>

<span data-ttu-id="0a620-167">Existen dos formas de desencadenar la retención basada en eventos:</span><span class="sxs-lookup"><span data-stu-id="0a620-167">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="0a620-168">**Uso de la interfaz de usuario del Centro de administración** Con este proceso puede retener menos contenido a la vez, o bien, la frecuencia de activación de la retención puede ser menor (p. ej., mensual o anual).</span><span class="sxs-lookup"><span data-stu-id="0a620-168">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention isn't often, such as monthly or yearly.</span></span> <span data-ttu-id="0a620-169">Para obtener más información sobre este método, consulte [Información general sobre la retención basada en eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="0a620-169">For more information about this method, see [Overview of event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="0a620-170">Sin embargo, este método para desencadenar la retención puede consumir demasiado tiempo y producir más errores, lo que daña la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="0a620-170">However, this method of triggering retention can be time consuming and prone to error, thus stunting scalability.</span></span> <span data-ttu-id="0a620-171">Por lo tanto, una solución automatizada y sin errores para activar la retención puede mejorar la seguridad de los datos y el cumplimiento normativo.</span><span class="sxs-lookup"><span data-stu-id="0a620-171">Therefore, an automated, seamless solution to trigger retention can enhance data security and compliance.</span></span>

- <span data-ttu-id="0a620-p115">**Con una API de REST de M365** Este proceso puede usarse cuando se deben retener grandes cantidades de contenido a la vez o cuando la frecuencia para activar la retención es asidua (diaria o semanal). El flujo detecta cuando un evento se ejecuta en el sistema de línea de negocio y crea automáticamente un evento relacionado en el Centro de seguridad y cumplimiento. No es necesario crear manualmente un evento en la interfaz de usuario cada vez que se produce un evento.</span><span class="sxs-lookup"><span data-stu-id="0a620-p115">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="0a620-175">Hay dos opciones para usar la API de REST:</span><span class="sxs-lookup"><span data-stu-id="0a620-175">There are two options for using the REST API:</span></span>

- <span data-ttu-id="0a620-176">**Usar Microsoft Flow o una aplicación similar** para desencadenar un evento automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0a620-176">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="0a620-177">Microsoft Flow puede orquestar la conexión a otros sistemas.</span><span class="sxs-lookup"><span data-stu-id="0a620-177">Microsoft Flow is an orchestrator for connecting to other systems.</span></span> <span data-ttu-id="0a620-178">Además, su uso no requiere una solución personalizada.</span><span class="sxs-lookup"><span data-stu-id="0a620-178">Using Microsoft Flow doesn't require a custom solution.</span></span>

- <span data-ttu-id="0a620-179">**PowerShell o un cliente de HTTP para llamar a la API de REST** Usar PowerShell (versión 6 o posterior) para pedirle a la API de REST de Microsoft 365 que cree eventos.</span><span class="sxs-lookup"><span data-stu-id="0a620-179">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="0a620-180">Una API de REST es un punto de conexión de servicio que admite conjuntos de operaciones HTTP (métodos), que proporcionan acceso de creación/recuperación/actualización/eliminación a los recursos del servicio.</span><span class="sxs-lookup"><span data-stu-id="0a620-180">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="0a620-181">Para obtener más información, vea [Componentes de una solicitud o respuesta de API de REST](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="0a620-181">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="0a620-182">En este caso, al usar la API de REST de Microsoft 365, puede crear y recuperar eventos mediante el uso de operaciones (métodos) POST y GET.</span><span class="sxs-lookup"><span data-stu-id="0a620-182">In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="0a620-183">Escenarios de ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a620-183">Example scenarios</span></span>

<span data-ttu-id="0a620-184">Consideremos los siguientes escenarios.</span><span class="sxs-lookup"><span data-stu-id="0a620-184">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="0a620-185">Escenario 1: Empleados que dejan la organización</span><span class="sxs-lookup"><span data-stu-id="0a620-185">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="0a620-186">La organización crea y almacena numerosos documentos relacionados con cada empleado.</span><span class="sxs-lookup"><span data-stu-id="0a620-186">An organization creates and stores numerous employee-related documents per employee.</span></span> <span data-ttu-id="0a620-187">Estos documentos se administran y conservan durante el tiempo de contratación del empleado.</span><span class="sxs-lookup"><span data-stu-id="0a620-187">These documents are managed and retained during the employment of each employee.</span></span> <span data-ttu-id="0a620-188">Sin embargo, cuando el empleado abandona la organización o deja de trabajar para ella, la organización esta comercial y legalmente obligada a conservar los documentos de ese empleado durante un período estipulado.</span><span class="sxs-lookup"><span data-stu-id="0a620-188">However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="0a620-189">Ahora si varios empleados dejan la organización todos los días, la organización debe activar el reloj de retención de cientos o miles de documentos cada día.</span><span class="sxs-lookup"><span data-stu-id="0a620-189">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="0a620-190">Además, se debe calcular el período de retención de cada uno de estos empleados con el siguiente formato: fecha de despido del empleado + número de días, meses o años en función del tipo de registro del empleado.</span><span class="sxs-lookup"><span data-stu-id="0a620-190">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months, or years based on the type of the employee record.</span></span> <span data-ttu-id="0a620-191">Por ejemplo, es posible que la compensación y la tramitación de beneficios del mismo empleado necesiten retenciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="0a620-191">For example, worker’s compensation of the employee vs. benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="0a620-192">El siguiente diagrama muestra cómo puede haber varias etiquetas asociadas a un único evento.</span><span class="sxs-lookup"><span data-stu-id="0a620-192">The diagram below shows how there can be multiple labels that are associated with a single event.</span></span> <span data-ttu-id="0a620-193">En este caso, todos los archivos de la etiqueta de indemnización del Trabajador y los que pertenecen a la etiqueta de beneficios del Trabajador se asocian a un único evento, que es la salida del empleado.</span><span class="sxs-lookup"><span data-stu-id="0a620-193">Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event, which is the employee leaving the organization.</span></span> <span data-ttu-id="0a620-194">Cada uno de estos archivos diferentes tiene diferentes relojes de retención.</span><span class="sxs-lookup"><span data-stu-id="0a620-194">Each of these different files has different retention clocks.</span></span> <span data-ttu-id="0a620-195">Por lo tanto, cuando un empleado deja la organización, cada archivo dentro de una misma etiqueta experimenta un período de retención diferente.</span><span class="sxs-lookup"><span data-stu-id="0a620-195">So, when an employee leaves the organization, these files within each label experience a different retention period.</span></span> <span data-ttu-id="0a620-196">Activar todos estos relojes de retención diferentes para cada tipo de archivo o etiqueta en un solo empleado es una tarea muy desafiante.</span><span class="sxs-lookup"><span data-stu-id="0a620-196">Triggering all these different retention clocks for each file type or label for each employee is a very challenging task.</span></span> <span data-ttu-id="0a620-197">Imagine este proceso con varios empleados.</span><span class="sxs-lookup"><span data-stu-id="0a620-197">Imagine doing this for multiple employees.</span></span>

![Diagrama de tipo de evento, evento y etiquetas](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="0a620-199">Por lo tanto, un proceso automatizado para activar estos relojes de retención diferentes para varios empleados permitirá ahorrar tiempo, evitar errores y lograr una alta eficiencia.</span><span class="sxs-lookup"><span data-stu-id="0a620-199">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free, and extremely efficient.</span></span>

<span data-ttu-id="0a620-200">**Configuración de retención automatizada basada en eventos para este escenario:**</span><span class="sxs-lookup"><span data-stu-id="0a620-200">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de funciones y acciones para el escenario del empleado que deja la organización](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="0a620-202">La administración crea carpetas del empleado en un conjunto de documentos denominado Naiara Padilla, David Pulido.</span><span class="sxs-lookup"><span data-stu-id="0a620-202">Admin creates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="0a620-203">La administración agrega archivos del empleado, como los de beneficios, nómina o compensación del trabajador a cada carpeta de empleado.</span><span class="sxs-lookup"><span data-stu-id="0a620-203">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder.</span></span>

  - <span data-ttu-id="0a620-204">La administración asigna el id. de activo a la carpeta de cada empleado.</span><span class="sxs-lookup"><span data-stu-id="0a620-204">Admin assigns Asset ID to each employee folder.</span></span> 

  - <span data-ttu-id="0a620-205">La administración de SSC inicia sesión en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="0a620-205">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="0a620-206">La administración de SCC crea tipos de eventos relacionados con el empleado como “Desvinculación del empleado”, “Contratación del empleados”.</span><span class="sxs-lookup"><span data-stu-id="0a620-206">SCC Admin creates employee-related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="0a620-207">La administración de SCC crea la etiqueta de "Retención de empleados".</span><span class="sxs-lookup"><span data-stu-id="0a620-207">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="0a620-208">Esta etiqueta de "Retención de empleados" se publica y se aplican manual o automáticamente a los archivos de empleado en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0a620-208">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint.</span></span>

  - <span data-ttu-id="0a620-209">Un sistema de administración de Recursos Humanos como Workday puede trabajar con Microsoft Flow para ejecutarse periódicamente para administrar archivos del empleado.</span><span class="sxs-lookup"><span data-stu-id="0a620-209">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files.</span></span>

  - <span data-ttu-id="0a620-210">Cuando un empleado deja la organización, Flow activa la API de REST de retención basada en eventos de M365 que inicia el reloj de retención de archivos específicos del empleado.</span><span class="sxs-lookup"><span data-stu-id="0a620-210">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="0a620-211">Usar Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="0a620-211">Using Microsoft Flow</span></span>

<span data-ttu-id="0a620-212">Paso 1: crear un flujo para crear un evento mediante la API de REST de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0a620-212">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Usar Flow para crear un evento](../media/automate-event-driven-retention-flow-1.png)

![Usar Flow para llamar a la API de REST](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="0a620-215">Crear un evento</span><span class="sxs-lookup"><span data-stu-id="0a620-215">Create an event</span></span>

<span data-ttu-id="0a620-216">Código de ejemplo para llamar a la API de REST</span><span class="sxs-lookup"><span data-stu-id="0a620-216">Sample code to call the REST API</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="0a620-217">Método</span><span class="sxs-lookup"><span data-stu-id="0a620-217">Method</span></span></th>
<th><span data-ttu-id="0a620-218">POST</span><span class="sxs-lookup"><span data-stu-id="0a620-218">POST</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0a620-219">URL</span><span class="sxs-lookup"><span data-stu-id="0a620-219">URL</span></span></td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0a620-220">Encabezados</span><span class="sxs-lookup"><span data-stu-id="0a620-220">Headers</span></span></td>
<td><span data-ttu-id="0a620-221">Tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="0a620-221">Content-Type</span></span></td>
<td><span data-ttu-id="0a620-222">aplicación/atom+xml</span><span class="sxs-lookup"><span data-stu-id="0a620-222">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0a620-223">Cuerpo</span><span class="sxs-lookup"><span data-stu-id="0a620-223">Body</span></span></td>
<td><p><span data-ttu-id="0a620-224">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-224">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="0a620-225">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="0a620-225">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="0a620-226">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="0a620-226">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="0a620-227">xmlns='http://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-227">xmlns='http://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="0a620-228">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-228">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="0a620-229">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-229">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="0a620-230">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-230">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="0a620-231">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-231">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="0a620-232">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-232">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="0a620-233">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-233">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="0a620-234">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-234">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="0a620-235">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-235">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span></span></p>
<p><span data-ttu-id="0a620-236">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-236">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="0a620-237">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-237">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="0a620-238">&lt;/entry&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-238">&lt;/entry&gt;</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0a620-239">Autenticación</span><span class="sxs-lookup"><span data-stu-id="0a620-239">Authentication</span></span></td>
<td><span data-ttu-id="0a620-240">Básica</span><span class="sxs-lookup"><span data-stu-id="0a620-240">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0a620-241">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="0a620-241">Username</span></span></td>
<td><span data-ttu-id="0a620-242">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="0a620-242">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0a620-243">Contraseña</span><span class="sxs-lookup"><span data-stu-id="0a620-243">Password</span></span></td>
<td><span data-ttu-id="0a620-244">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="0a620-244">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a><span data-ttu-id="0a620-245">Parámetros disponibles</span><span class="sxs-lookup"><span data-stu-id="0a620-245">Available parameters</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="0a620-246"><strong>Parámetros</strong></span><span class="sxs-lookup"><span data-stu-id="0a620-246"><strong>Parameters</strong></span></span></th>
<th><span data-ttu-id="0a620-247"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="0a620-247"><strong>Description</strong></span></span></th>
<th><span data-ttu-id="0a620-248"><strong>Notas</strong></span><span class="sxs-lookup"><span data-stu-id="0a620-248"><strong>Notes</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0a620-249">&lt;d:Name&gt;&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-249">&lt;d:Name&gt;&lt;/d:Name&gt;</span></span></td>
<td><span data-ttu-id="0a620-250">Escribe un nombre único para el evento.</span><span class="sxs-lookup"><span data-stu-id="0a620-250">Provide a unique name for the event,</span></span></td>
<td><span data-ttu-id="0a620-p121">No puede contener espacios finales ni los siguientes caracteres: % \* \ &amp; &lt; &gt; | # ? , : ;</span><span class="sxs-lookup"><span data-stu-id="0a620-p121">Cannot contain trailing spaces, and the following characters: % \* \ &amp; &lt; &gt; | # ? , : ;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0a620-253">&lt;d:eventType&gt;&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-253">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span></span></td>
<td><span data-ttu-id="0a620-254">Escribe el nombre del tipo de evento (o Guid)</span><span class="sxs-lookup"><span data-stu-id="0a620-254">Enter event type name (or Guid),</span></span></td>
<td><span data-ttu-id="0a620-p122">Ejemplo: "Desvinculación del empleado". El tipo de evento debe estar asociado con una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="0a620-p122">Example: “Employee termination”. Event type has to be associated with a retention label.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0a620-257">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-257">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span></span></td>
<td><span data-ttu-id="0a620-258">Escribe "ComplianceAssetId:" + Id. de empleado</span><span class="sxs-lookup"><span data-stu-id="0a620-258">Enter “ComplianceAssetId:” + employee Id</span></span></td>
<td><span data-ttu-id="0a620-259">Ejemplo:&quot;ComplianceAssetId:12345&quot;</span><span class="sxs-lookup"><span data-stu-id="0a620-259">Example:&quot;ComplianceAssetId:12345&quot;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0a620-260">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-260">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span></span></td>
<td><span data-ttu-id="0a620-261">Fecha y hora del evento</span><span class="sxs-lookup"><span data-stu-id="0a620-261">Event Date and Time</span></span></td>
<td><p><span data-ttu-id="0a620-262">Formato: aaaa-MM-ddTHH:mm:ssZ, ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0a620-262">Format: yyyy-MM-ddTHH:mm:ssZ, Example:</span></span></p>
<p><span data-ttu-id="0a620-263">2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="0a620-263">2018-12-01T00:00:00Z</span></span></p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="0a620-264">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="0a620-264">Response codes</span></span>

| <span data-ttu-id="0a620-265">**Código de respuesta**</span><span class="sxs-lookup"><span data-stu-id="0a620-265">**Response Code**</span></span> | <span data-ttu-id="0a620-266">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0a620-266">**Description**</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="0a620-267">302</span><span class="sxs-lookup"><span data-stu-id="0a620-267">302</span></span>               | <span data-ttu-id="0a620-268">Redirigir</span><span class="sxs-lookup"><span data-stu-id="0a620-268">Redirect</span></span>              |
| <span data-ttu-id="0a620-269">201</span><span class="sxs-lookup"><span data-stu-id="0a620-269">201</span></span>               | <span data-ttu-id="0a620-270">Fecha de creación</span><span class="sxs-lookup"><span data-stu-id="0a620-270">Created</span></span>               |
| <span data-ttu-id="0a620-271">403</span><span class="sxs-lookup"><span data-stu-id="0a620-271">403</span></span>               | <span data-ttu-id="0a620-272">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="0a620-272">Authorization Failed</span></span>  |
| <span data-ttu-id="0a620-273">401</span><span class="sxs-lookup"><span data-stu-id="0a620-273">401</span></span>               | <span data-ttu-id="0a620-274">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="0a620-274">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="0a620-275">Obtener eventos según el intervalo de tiempo</span><span class="sxs-lookup"><span data-stu-id="0a620-275">Get Events based on time range</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="0a620-276">Método</span><span class="sxs-lookup"><span data-stu-id="0a620-276">Method</span></span></th>
<th><span data-ttu-id="0a620-277">GET</span><span class="sxs-lookup"><span data-stu-id="0a620-277">GET</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0a620-278">URL</span><span class="sxs-lookup"><span data-stu-id="0a620-278">URL</span></span></td>
<td><ol start="4" type="1">
<li><p><span data-ttu-id="0a620-279">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp; EndDateTime = 2019-16: 01</span><span class="sxs-lookup"><span data-stu-id="0a620-279">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span></span></p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0a620-280">Encabezados</span><span class="sxs-lookup"><span data-stu-id="0a620-280">Headers</span></span></td>
<td><span data-ttu-id="0a620-281">Tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="0a620-281">Content-Type</span></span></td>
<td><span data-ttu-id="0a620-282">aplicación/atom+xml</span><span class="sxs-lookup"><span data-stu-id="0a620-282">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0a620-283">Autenticación</span><span class="sxs-lookup"><span data-stu-id="0a620-283">Authentication</span></span></td>
<td><span data-ttu-id="0a620-284">Básica</span><span class="sxs-lookup"><span data-stu-id="0a620-284">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0a620-285">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="0a620-285">Username</span></span></td>
<td><span data-ttu-id="0a620-286">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="0a620-286">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0a620-287">Contraseña</span><span class="sxs-lookup"><span data-stu-id="0a620-287">Password</span></span></td>
<td><span data-ttu-id="0a620-288">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="0a620-288">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="0a620-289">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="0a620-289">Response codes</span></span>

| <span data-ttu-id="0a620-290">**Código de respuesta**</span><span class="sxs-lookup"><span data-stu-id="0a620-290">**Response Code**</span></span> | <span data-ttu-id="0a620-291">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0a620-291">**Description**</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="0a620-292">200</span><span class="sxs-lookup"><span data-stu-id="0a620-292">200</span></span>               | <span data-ttu-id="0a620-293">Aceptar, una lista de eventos de atom+ xml</span><span class="sxs-lookup"><span data-stu-id="0a620-293">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="0a620-294">404</span><span class="sxs-lookup"><span data-stu-id="0a620-294">404</span></span>               | <span data-ttu-id="0a620-295">No encontrado</span><span class="sxs-lookup"><span data-stu-id="0a620-295">Not found</span></span>                         |
| <span data-ttu-id="0a620-296">302</span><span class="sxs-lookup"><span data-stu-id="0a620-296">302</span></span>               | <span data-ttu-id="0a620-297">Redirigir</span><span class="sxs-lookup"><span data-stu-id="0a620-297">Redirect</span></span>                          |
| <span data-ttu-id="0a620-298">401</span><span class="sxs-lookup"><span data-stu-id="0a620-298">401</span></span>               | <span data-ttu-id="0a620-299">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="0a620-299">Authorization Failed</span></span>              |
| <span data-ttu-id="0a620-300">403</span><span class="sxs-lookup"><span data-stu-id="0a620-300">403</span></span>               | <span data-ttu-id="0a620-301">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="0a620-301">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="0a620-302">Obtén un objeto por id.</span><span class="sxs-lookup"><span data-stu-id="0a620-302">Get an event by ID</span></span>

| <span data-ttu-id="0a620-303">Método</span><span class="sxs-lookup"><span data-stu-id="0a620-303">Method</span></span>         | <span data-ttu-id="0a620-304">GET</span><span class="sxs-lookup"><span data-stu-id="0a620-304">GET</span></span>   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| <span data-ttu-id="0a620-305">URL</span><span class="sxs-lookup"><span data-stu-id="0a620-305">URL</span></span>            | <span data-ttu-id="0a620-306">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span><span class="sxs-lookup"><span data-stu-id="0a620-306">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span></span> |                      |
| <span data-ttu-id="0a620-307">Encabezado</span><span class="sxs-lookup"><span data-stu-id="0a620-307">Header</span></span>         | <span data-ttu-id="0a620-308">Tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="0a620-308">Content-Type</span></span>                                                                                                                                                                                                                                                       | <span data-ttu-id="0a620-309">aplicación/atom+xml</span><span class="sxs-lookup"><span data-stu-id="0a620-309">application/atom+xml</span></span> |
| <span data-ttu-id="0a620-310">Autenticación</span><span class="sxs-lookup"><span data-stu-id="0a620-310">Authentication</span></span> | <span data-ttu-id="0a620-311">Básica</span><span class="sxs-lookup"><span data-stu-id="0a620-311">Basic</span></span>                                                                                                                                                                                                                                                              |                      |
| <span data-ttu-id="0a620-312">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="0a620-312">Username</span></span>       | <span data-ttu-id="0a620-313">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="0a620-313">“Complianceuser”</span></span>                                                                                                                                                                                                                                                   |                      |
| <span data-ttu-id="0a620-314">Contraseña</span><span class="sxs-lookup"><span data-stu-id="0a620-314">Password</span></span>       | <span data-ttu-id="0a620-315">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="0a620-315">“Compliancepassword”</span></span>                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a><span data-ttu-id="0a620-316">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="0a620-316">Response codes</span></span>

| <span data-ttu-id="0a620-317">**Código de respuesta**</span><span class="sxs-lookup"><span data-stu-id="0a620-317">**Response Code**</span></span> | <span data-ttu-id="0a620-318">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0a620-318">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="0a620-319">200</span><span class="sxs-lookup"><span data-stu-id="0a620-319">200</span></span>               | <span data-ttu-id="0a620-320">Aceptar, el cuerpo de la respuesta contiene el evento en atom+ xml</span><span class="sxs-lookup"><span data-stu-id="0a620-320">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="0a620-321">404</span><span class="sxs-lookup"><span data-stu-id="0a620-321">404</span></span>               | <span data-ttu-id="0a620-322">No encontrado</span><span class="sxs-lookup"><span data-stu-id="0a620-322">Not found</span></span>                                            |
| <span data-ttu-id="0a620-323">302</span><span class="sxs-lookup"><span data-stu-id="0a620-323">302</span></span>               | <span data-ttu-id="0a620-324">Redirigir</span><span class="sxs-lookup"><span data-stu-id="0a620-324">Redirect</span></span>                                             |
| <span data-ttu-id="0a620-325">401</span><span class="sxs-lookup"><span data-stu-id="0a620-325">401</span></span>               | <span data-ttu-id="0a620-326">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="0a620-326">Authorization Failed</span></span>                                 |
| <span data-ttu-id="0a620-327">403</span><span class="sxs-lookup"><span data-stu-id="0a620-327">403</span></span>               | <span data-ttu-id="0a620-328">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="0a620-328">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="0a620-329">Obtén un evento por nombre</span><span class="sxs-lookup"><span data-stu-id="0a620-329">Get an event by name</span></span>

| <span data-ttu-id="0a620-330">Método</span><span class="sxs-lookup"><span data-stu-id="0a620-330">Method</span></span>         | <span data-ttu-id="0a620-331">GET</span><span class="sxs-lookup"><span data-stu-id="0a620-331">GET</span></span>       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| <span data-ttu-id="0a620-332">URL</span><span class="sxs-lookup"><span data-stu-id="0a620-332">URL</span></span>            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| <span data-ttu-id="0a620-333">Encabezados</span><span class="sxs-lookup"><span data-stu-id="0a620-333">Headers</span></span>        | <span data-ttu-id="0a620-334">Tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="0a620-334">Content-Type</span></span>                                                                                                                                 | <span data-ttu-id="0a620-335">aplicación/atom+xml</span><span class="sxs-lookup"><span data-stu-id="0a620-335">application/atom+xml</span></span> |
| <span data-ttu-id="0a620-336">Autenticación</span><span class="sxs-lookup"><span data-stu-id="0a620-336">Authentication</span></span> | <span data-ttu-id="0a620-337">Básica</span><span class="sxs-lookup"><span data-stu-id="0a620-337">Basic</span></span>                                                                                                                                        |                      |
| <span data-ttu-id="0a620-338">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="0a620-338">Username</span></span>       | <span data-ttu-id="0a620-339">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="0a620-339">“Complianceuser”</span></span>                                                                                                                             |                      |
| <span data-ttu-id="0a620-340">Contraseña</span><span class="sxs-lookup"><span data-stu-id="0a620-340">Password</span></span>       | <span data-ttu-id="0a620-341">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="0a620-341">“Compliancepassword”</span></span>                                                                                                                         |                      |

##### <a name="response-codes"></a><span data-ttu-id="0a620-342">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="0a620-342">Response codes</span></span>

| <span data-ttu-id="0a620-343">**Código de respuesta**</span><span class="sxs-lookup"><span data-stu-id="0a620-343">**Response Code**</span></span> | <span data-ttu-id="0a620-344">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0a620-344">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="0a620-345">200</span><span class="sxs-lookup"><span data-stu-id="0a620-345">200</span></span>               | <span data-ttu-id="0a620-346">Aceptar, el cuerpo de la respuesta contiene el evento en atom+ xml</span><span class="sxs-lookup"><span data-stu-id="0a620-346">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="0a620-347">404</span><span class="sxs-lookup"><span data-stu-id="0a620-347">404</span></span>               | <span data-ttu-id="0a620-348">No encontrado</span><span class="sxs-lookup"><span data-stu-id="0a620-348">Not found</span></span>                                            |
| <span data-ttu-id="0a620-349">302</span><span class="sxs-lookup"><span data-stu-id="0a620-349">302</span></span>               | <span data-ttu-id="0a620-350">Redirigir</span><span class="sxs-lookup"><span data-stu-id="0a620-350">Redirect</span></span>                                             |
| <span data-ttu-id="0a620-351">401</span><span class="sxs-lookup"><span data-stu-id="0a620-351">401</span></span>               | <span data-ttu-id="0a620-352">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="0a620-352">Authorization Failed</span></span>                                 |
| <span data-ttu-id="0a620-353">403</span><span class="sxs-lookup"><span data-stu-id="0a620-353">403</span></span>               | <span data-ttu-id="0a620-354">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="0a620-354">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="0a620-355">Uso de PowerShell (ver.6 o posterior) o cualquier cliente HTTP</span><span class="sxs-lookup"><span data-stu-id="0a620-355">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="0a620-356">Paso 1: Conéctate a PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0a620-356">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="0a620-357">Paso 2: Ejecuta el siguiente script.</span><span class="sxs-lookup"><span data-stu-id="0a620-357">Step 2: Run the following script.</span></span>

<table>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a620-358">param([string]$baseUri)</span><span class="sxs-lookup"><span data-stu-id="0a620-358">param([string]$baseUri)</span></span></p>
<p><span data-ttu-id="0a620-359">$userName = &quot;UserName&quot;</span><span class="sxs-lookup"><span data-stu-id="0a620-359">$userName = &quot;UserName&quot;</span></span></p>
<p><span data-ttu-id="0a620-360">$password = &quot;Password&quot;</span><span class="sxs-lookup"><span data-stu-id="0a620-360">$password = &quot;Password&quot;</span></span></p>
<p><span data-ttu-id="0a620-361">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span><span class="sxs-lookup"><span data-stu-id="0a620-361">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span></span></p>
<p><span data-ttu-id="0a620-362">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span><span class="sxs-lookup"><span data-stu-id="0a620-362">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span></span></p>
<p><span data-ttu-id="0a620-363">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span><span class="sxs-lookup"><span data-stu-id="0a620-363">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span></span></p>
<p><span data-ttu-id="0a620-364">Write-Host &quot;Comienza a crear un evento con el nombre: $EventName&quot;</span><span class="sxs-lookup"><span data-stu-id="0a620-364">Write-Host &quot;Start to create an event with name: $EventName&quot;</span></span></p>
<p><span data-ttu-id="0a620-365">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-365">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="0a620-366">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="0a620-366">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="0a620-367">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="0a620-367">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="0a620-368">xmlns='http://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-368">xmlns='http://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="0a620-369">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-369">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="0a620-370">&lt;actualizado&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-370">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="0a620-371">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-371">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="0a620-372">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-372">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="0a620-373">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-373">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="0a620-374">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-374">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="0a620-375">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-375">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="0a620-376">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-376">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="0a620-377">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="0a620-377">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="0a620-378">&lt;/entry&gt;&quot;</span><span class="sxs-lookup"><span data-stu-id="0a620-378">&lt;/entry&gt;&quot;</span></span></p>
<p><span data-ttu-id="0a620-379">$event = $null</span><span class="sxs-lookup"><span data-stu-id="0a620-379">$event = $null</span></span></p>
<p><span data-ttu-id="0a620-380">probar</span><span class="sxs-lookup"><span data-stu-id="0a620-380">try</span></span></p>
<p><span data-ttu-id="0a620-381">{</span><span class="sxs-lookup"><span data-stu-id="0a620-381">{</span></span></p>
<p><span data-ttu-id="0a620-382">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="0a620-382">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="0a620-383">}</span><span class="sxs-lookup"><span data-stu-id="0a620-383">}</span></span></p>
<p><span data-ttu-id="0a620-384">catch</span><span class="sxs-lookup"><span data-stu-id="0a620-384">catch</span></span></p>
<p><span data-ttu-id="0a620-385">{</span><span class="sxs-lookup"><span data-stu-id="0a620-385">{</span></span></p>
<p><span data-ttu-id="0a620-386">$response = $_. Exception.Response</span><span class="sxs-lookup"><span data-stu-id="0a620-386">$response = $_.Exception.Response</span></span></p>
<p><span data-ttu-id="0a620-387">if($response.StatusCode -eq &quot;Redirect&quot;)</span><span class="sxs-lookup"><span data-stu-id="0a620-387">if($response.StatusCode -eq &quot;Redirect&quot;)</span></span></p>
<p><span data-ttu-id="0a620-388">{</span><span class="sxs-lookup"><span data-stu-id="0a620-388">{</span></span></p>
<p><span data-ttu-id="0a620-389">$url = $response.Headers.Location</span><span class="sxs-lookup"><span data-stu-id="0a620-389">$url = $response.Headers.Location</span></span></p>
<p><span data-ttu-id="0a620-390">Write-Host &quot;redirected to $url&quot;</span><span class="sxs-lookup"><span data-stu-id="0a620-390">Write-Host &quot;redirected to $url&quot;</span></span></p>
<p><span data-ttu-id="0a620-391">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="0a620-391">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="0a620-392">}</span><span class="sxs-lookup"><span data-stu-id="0a620-392">}</span></span></p>
<p><span data-ttu-id="0a620-393">}</span><span class="sxs-lookup"><span data-stu-id="0a620-393">}</span></span></p>
<p><span data-ttu-id="0a620-394">$event | fl \*</span><span class="sxs-lookup"><span data-stu-id="0a620-394">$event | fl \*</span></span></p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="0a620-395">Comprobar el resultado en ambas opciones.</span><span class="sxs-lookup"><span data-stu-id="0a620-395">Verify the outcome in both options</span></span>

<span data-ttu-id="0a620-396">Paso 1: Ir al Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="0a620-396">Step 1: Go to the Security & Compliance Center.</span></span>

<span data-ttu-id="0a620-397">Paso 2: seleccione los **eventos** en **control de la información**.</span><span class="sxs-lookup"><span data-stu-id="0a620-397">Step 2: Select **Events** under **Information governance**.</span></span>

<span data-ttu-id="0a620-398">Paso 3: Comprobar que se creó el evento.</span><span class="sxs-lookup"><span data-stu-id="0a620-398">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="0a620-399">De forma similar, también se pueden usar las opciones anteriores para automatizar la retención basada en eventos para los siguientes escenarios.</span><span class="sxs-lookup"><span data-stu-id="0a620-399">Similarly, the above options to automate event-based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="0a620-400">Escenario 2: Contratos que expiran</span><span class="sxs-lookup"><span data-stu-id="0a620-400">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="0a620-401">Una organización puede tener varios registros para un contrato único con clientes, proveedores y asociados.</span><span class="sxs-lookup"><span data-stu-id="0a620-401">An organization can have multiple records for a single contract with customers, vendors, and partners.</span></span> <span data-ttu-id="0a620-402">Estos documentos pueden residir en una biblioteca de documentos como SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0a620-402">These documents can reside in a document library like SharePoint.</span></span> <span data-ttu-id="0a620-403">Con la finalización de un contrato empieza el periodo de retención de los documentos asociados al contrato.</span><span class="sxs-lookup"><span data-stu-id="0a620-403">The end of a contract determines the start of the retention period of the documents associated with the contract.</span></span> <span data-ttu-id="0a620-404">Por ejemplo, se deben conservar todos los registros relacionados con un contrato cinco años después de que expire.</span><span class="sxs-lookup"><span data-stu-id="0a620-404">For example, all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="0a620-405">El evento que desencadena el período de retención de cinco años es la expiración del contrato.</span><span class="sxs-lookup"><span data-stu-id="0a620-405">The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="0a620-406">Un sistema de administración de relaciones de cliente (CRM) puede trabajar con Microsoft 365 y activar la retención de documentos del contrato.</span><span class="sxs-lookup"><span data-stu-id="0a620-406">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents</span></span>

<span data-ttu-id="0a620-407">**Configuración de retención automatizada basada en eventos para este escenario:**</span><span class="sxs-lookup"><span data-stu-id="0a620-407">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de los funciones y tareas para escenarios de expiración del contrato](../media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="0a620-409">La administración crea una biblioteca de SharePoint con carpetas diferentes para cada tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="0a620-409">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="0a620-410">La administración agrega archivos del contrato como contratos de licencia y contratos de desarrollo para cada carpeta del contrato.</span><span class="sxs-lookup"><span data-stu-id="0a620-410">Admin adds contract files such as License Contracts, Development Contracts to each contract folder.</span></span>

  - <span data-ttu-id="0a620-411">La administración asigna el id. de activo a cada carpeta de contrato.</span><span class="sxs-lookup"><span data-stu-id="0a620-411">Admin assigns Asset ID to each contract folder.</span></span>

  - <span data-ttu-id="0a620-412">La administración de SSC inicia sesión en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="0a620-412">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="0a620-413">La administración de SCC crea tipos de eventos relacionados con el contrato como eventos de "Creación del contrato" y de "Expiración del contrato".</span><span class="sxs-lookup"><span data-stu-id="0a620-413">SCC Admin creates contract-related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="0a620-414">La administración de SCC crea la etiqueta "Expiración del contrato".</span><span class="sxs-lookup"><span data-stu-id="0a620-414">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="0a620-415">Esta etiqueta de "Expiración del contrato" se publica y se aplican de forma manual o automática a los archivos del contrato en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0a620-415">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint.</span></span>

  - <span data-ttu-id="0a620-416">El sistema de administración de contrato puede trabajar con Microsoft Flow o una aplicación similar para ejecutarse periódicamente para administrar archivos de contrato.</span><span class="sxs-lookup"><span data-stu-id="0a620-416">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files.</span></span>

  - <span data-ttu-id="0a620-417">Si un contrato vence, Microsoft Flow activará la API de REST de retención basada en eventos de M365 que iniciará el reloj de retención de archivos específicos del contrato.</span><span class="sxs-lookup"><span data-stu-id="0a620-417">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="0a620-418">Escenario 3: Final de fabricación de productos</span><span class="sxs-lookup"><span data-stu-id="0a620-418">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="0a620-p124">Una empresa de elaboración que fabrica diferentes líneas de productos crea varias especificaciones de elaboración y documentos de precios. Cuando el producto ya no se fabrica, todas las especificaciones y documentos vinculados a este producto deben conservarse durante un período específico después del final de la vida útil del producto.</span><span class="sxs-lookup"><span data-stu-id="0a620-p124">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="0a620-421">Un sistema de planeación de recursos empresariales (ERP) puede trabajar con Microsoft 365 y Microsoft Flow para activar la retención.</span><span class="sxs-lookup"><span data-stu-id="0a620-421">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="0a620-422">**Configuración de retención automatizada basada en eventos para este escenario:**</span><span class="sxs-lookup"><span data-stu-id="0a620-422">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de las funciones y tareas para escenarios de ciclo de vida del producto](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="0a620-424">La administración crea carpetas de productos en el conjunto de documentos como Producto 1, Producto 2, etc.</span><span class="sxs-lookup"><span data-stu-id="0a620-424">Admin creates product folders in the Document set such as Product 1, Product 2, and so on.</span></span>

  - <span data-ttu-id="0a620-425">La administración agrega los archivos de productos como Especificaciones de fabricación, Precio del producto y Licencias del producto a cada carpeta de producto.</span><span class="sxs-lookup"><span data-stu-id="0a620-425">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder.</span></span>

  - <span data-ttu-id="0a620-426">La administración le asigna el id. de activo a cada carpeta del producto.</span><span class="sxs-lookup"><span data-stu-id="0a620-426">Admin assigns Asset ID to each product folder.</span></span>

  - <span data-ttu-id="0a620-427">La administración de SSC inicia sesión en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="0a620-427">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="0a620-428">La administración de SCC crea tipos de eventos relacionados con el empleado como "Inicio de fabricación del producto" y "Final de fabricación del producto".</span><span class="sxs-lookup"><span data-stu-id="0a620-428">SCC Admin creates employee-related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="0a620-429">La administración de SCC crea la etiqueta "Final de fabricación del producto".</span><span class="sxs-lookup"><span data-stu-id="0a620-429">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="0a620-430">Esta etiqueta de "Final de fabricación del producto" se publica y se aplica de forma manual o automática a los archivos del producto en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0a620-430">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint.</span></span>

  - <span data-ttu-id="0a620-431">Los sistemas de ERP pueden funcionar con Microsoft Flow o con aplicaciones similares para ejecutarse periódicamente para administrar archivos del producto.</span><span class="sxs-lookup"><span data-stu-id="0a620-431">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files.</span></span>

  - <span data-ttu-id="0a620-432">Si se termina la fabricación de un producto, Microsoft Flow activará la API de REST de retención basada en eventos de M365 que iniciará el reloj de retención de archivos específicos del producto.</span><span class="sxs-lookup"><span data-stu-id="0a620-432">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="0a620-433">Apéndice</span><span class="sxs-lookup"><span data-stu-id="0a620-433">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="0a620-434">Cómo usar los resultados de respuesta Redirect 302 para llamar a la API de REST</span><span class="sxs-lookup"><span data-stu-id="0a620-434">Using Redirect 302 response results to call the REST API</span></span>

1. <span data-ttu-id="0a620-435">Invocar una llamada de evento de retención POST con la URL de la API de REST <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (se requieren permisos de administrador global).</span><span class="sxs-lookup"><span data-stu-id="0a620-435">Invoke a POST retention event call using the REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required)</span></span>

2. <span data-ttu-id="0a620-p125">Comprobar el código de respuesta. Si es 302, obtener la dirección URL redirigida de la propiedad de ubicación del encabezado de respuesta.</span><span class="sxs-lookup"><span data-stu-id="0a620-p125">Check the response code. If it’s 302, then get the redirected URL from Location property of the response header</span></span>

3. <span data-ttu-id="0a620-438">Invocar la llamada al evento de retención POST nuevamente mediante el URL redireccionado.</span><span class="sxs-lookup"><span data-stu-id="0a620-438">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="0a620-439">Créditos</span><span class="sxs-lookup"><span data-stu-id="0a620-439">Credits</span></span>

<span data-ttu-id="0a620-440">Este tema fue revisado por:</span><span class="sxs-lookup"><span data-stu-id="0a620-440">This topic was reviewed by:</span></span>

<span data-ttu-id="0a620-441">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="0a620-441">Antonio Maio</span></span><br/><span data-ttu-id="0a620-442">MVP de servicios y aplicaciones de Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="0a620-442">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="0a620-443">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="0a620-443">Antonio.Maio@Protiviti.com</span></span>