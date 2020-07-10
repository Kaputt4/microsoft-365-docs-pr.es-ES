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
ms.openlocfilehash: c97106597733460caeab8d1d398ff81e23dd2727
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068119"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="c93aa-103">Retención automática basada en eventos</span><span class="sxs-lookup"><span data-stu-id="c93aa-103">Automate event-based retention</span></span>

><span data-ttu-id="c93aa-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="c93aa-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="c93aa-105">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business.</span><span class="sxs-lookup"><span data-stu-id="c93aa-105">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business.</span></span> <span data-ttu-id="c93aa-106">To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant.</span><span class="sxs-lookup"><span data-stu-id="c93aa-106">To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant.</span></span> <span data-ttu-id="c93aa-107">Retaining only important, pertinent information is key to an organization's success.</span><span class="sxs-lookup"><span data-stu-id="c93aa-107">Retaining only important, pertinent information is key to an organization's success.</span></span>

<span data-ttu-id="c93aa-108">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="c93aa-108">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="c93aa-109">Retention can be triggered by using [retention labels](labels.md).</span><span class="sxs-lookup"><span data-stu-id="c93aa-109">Retention can be triggered by using [retention labels](labels.md).</span></span> <span data-ttu-id="c93aa-110">A retention label has the option to [base the retention period on a specific event](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="c93aa-110">A retention label has the option to [base the retention period on a specific event](event-driven-retention.md).</span></span> <span data-ttu-id="c93aa-111">Typically, the retention period is based on a known date, such as the creation date or last modified date for the content.</span><span class="sxs-lookup"><span data-stu-id="c93aa-111">Typically, the retention period is based on a known date, such as the creation date or last modified date for the content.</span></span> <span data-ttu-id="c93aa-112">However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span><span class="sxs-lookup"><span data-stu-id="c93aa-112">However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span></span>

<span data-ttu-id="c93aa-113">To ensure compliant disposal of content, it's imperative to know when an event takes place.</span><span class="sxs-lookup"><span data-stu-id="c93aa-113">To ensure compliant disposal of content, it's imperative to know when an event takes place.</span></span> <span data-ttu-id="c93aa-114">With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span><span class="sxs-lookup"><span data-stu-id="c93aa-114">With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="c93aa-115">Event-based retention solves this problem.</span><span class="sxs-lookup"><span data-stu-id="c93aa-115">Event-based retention solves this problem.</span></span> <span data-ttu-id="c93aa-116">This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span><span class="sxs-lookup"><span data-stu-id="c93aa-116">This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="c93aa-117">Acerca de la retención basada en eventos</span><span class="sxs-lookup"><span data-stu-id="c93aa-117">About event-based retention</span></span>

<span data-ttu-id="c93aa-118">An organization can be small, medium, or large.</span><span class="sxs-lookup"><span data-stu-id="c93aa-118">An organization can be small, medium, or large.</span></span> <span data-ttu-id="c93aa-119">The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span><span class="sxs-lookup"><span data-stu-id="c93aa-119">The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span></span>

<span data-ttu-id="c93aa-120">For example, each day, tens and hundreds of employees are joining and leaving organizations.</span><span class="sxs-lookup"><span data-stu-id="c93aa-120">For example, each day, tens and hundreds of employees are joining and leaving organizations.</span></span> <span data-ttu-id="c93aa-121">The HR department continues to create, update, or delete employee-related documents as per business requirements.</span><span class="sxs-lookup"><span data-stu-id="c93aa-121">The HR department continues to create, update, or delete employee-related documents as per business requirements.</span></span> <span data-ttu-id="c93aa-122">This process is subject to the different retention policies outlined for the business:</span><span class="sxs-lookup"><span data-stu-id="c93aa-122">This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="c93aa-123">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled.</span><span class="sxs-lookup"><span data-stu-id="c93aa-123">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled.</span></span> <span data-ttu-id="c93aa-124">For example, you might retain documents for seven years after they're created and then delete them.</span><span class="sxs-lookup"><span data-stu-id="c93aa-124">For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="c93aa-125">**The period of retention of content can also be an unknown date**.</span><span class="sxs-lookup"><span data-stu-id="c93aa-125">**The period of retention of content can also be an unknown date**.</span></span> <span data-ttu-id="c93aa-126">For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span><span class="sxs-lookup"><span data-stu-id="c93aa-126">For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="c93aa-127">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them.</span><span class="sxs-lookup"><span data-stu-id="c93aa-127">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them.</span></span> <span data-ttu-id="c93aa-128">This is called event-based retention.</span><span class="sxs-lookup"><span data-stu-id="c93aa-128">This is called event-based retention.</span></span> <span data-ttu-id="c93aa-129">To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="c93aa-129">To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="c93aa-130">Configuración de la retención basada en eventos</span><span class="sxs-lookup"><span data-stu-id="c93aa-130">Set up event-based retention</span></span>

<span data-ttu-id="c93aa-131">Esta sección describe lo que es necesario realizar antes de retener contenido.</span><span class="sxs-lookup"><span data-stu-id="c93aa-131">This section describes what needs to be done before retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="c93aa-132">Identificación de funciones</span><span class="sxs-lookup"><span data-stu-id="c93aa-132">Identify roles</span></span>

<span data-ttu-id="c93aa-133">Identifica las diferentes funciones en una organización que realizan tareas de administración de registros y son responsables de una retención eficaz y eficiente de los documentos empresariales.</span><span class="sxs-lookup"><span data-stu-id="c93aa-133">Identify the different roles in an organization that perform Record Management tasks and would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="c93aa-134">Persona</span><span class="sxs-lookup"><span data-stu-id="c93aa-134">Persona</span></span> | <span data-ttu-id="c93aa-135">Rol</span><span class="sxs-lookup"><span data-stu-id="c93aa-135">Role</span></span> |
  | - | - |
  | <span data-ttu-id="c93aa-136">Administrador</span><span class="sxs-lookup"><span data-stu-id="c93aa-136">Admin</span></span> | <span data-ttu-id="c93aa-137">Crea tipos de eventos de retención, etiquetas de retención y repositorios de registros en SharePoint</span><span class="sxs-lookup"><span data-stu-id="c93aa-137">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="c93aa-138">Administrador de registros</span><span class="sxs-lookup"><span data-stu-id="c93aa-138">Records Manager</span></span>                                  | <span data-ttu-id="c93aa-139">Proporciona detalles de cumplimiento y guías de políticas de retención y programaciones de retención</span><span class="sxs-lookup"><span data-stu-id="c93aa-139">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="c93aa-140">Administrador del sistema (empresa)</span><span class="sxs-lookup"><span data-stu-id="c93aa-140">System Admin (business)</span></span>                          | <span data-ttu-id="c93aa-141">Configura y administra sistemas externos para que funcionen con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c93aa-141">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="c93aa-142">Trabajador de información</span><span class="sxs-lookup"><span data-stu-id="c93aa-142">Information Worker</span></span>                               | <span data-ttu-id="c93aa-143">Administra el ciclo de vida de los procesos de su empresa (Recursos Humanos, Finanzas, TI, etc.)</span><span class="sxs-lookup"><span data-stu-id="c93aa-143">Manages the lifecycle of their business process (HR, Finance, IT, and so on)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="c93aa-144">Configuración del Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="c93aa-144">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="c93aa-145">La administración del cumplimiento crea un tipo de evento &ndash; como el final de una relación laboral, la finalización del contrato o el final de fabricación del producto.</span><span class="sxs-lookup"><span data-stu-id="c93aa-145">Compliance admin creates an event type &ndash; for example, Employee Termination or Contract Expiration or End of Product Manufacturing.</span></span> <span data-ttu-id="c93aa-146">(Consulte el proceso paso a paso en el artículo [Retención de eventos](event-driven-retention.md)).</span><span class="sxs-lookup"><span data-stu-id="c93aa-146">(See the step-by-step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
2. <span data-ttu-id="c93aa-147">La administración de cumplimiento crea una etiqueta de retención basada en un evento y asocia la etiqueta con un tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="c93aa-147">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
    <span data-ttu-id="c93aa-148">Hay 4 tipos de desencadenadores para las etiquetas de retención:</span><span class="sxs-lookup"><span data-stu-id="c93aa-148">There are four types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="c93aa-149">Fecha de creación</span><span class="sxs-lookup"><span data-stu-id="c93aa-149">Create date</span></span>
                
    2. <span data-ttu-id="c93aa-150">Última modificación</span><span class="sxs-lookup"><span data-stu-id="c93aa-150">Last modified</span></span>
                
    3. <span data-ttu-id="c93aa-151">Fecha de la etiqueta (cuando se etiquetó el contenido)</span><span class="sxs-lookup"><span data-stu-id="c93aa-151">Label date (when the content was labeled)</span></span>
                
    4. <span data-ttu-id="c93aa-152">Basado en eventos</span><span class="sxs-lookup"><span data-stu-id="c93aa-152">Event-based</span></span>
    
3. <span data-ttu-id="c93aa-153">La administración del cumplimiento publica la etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="c93aa-153">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="c93aa-154">Configurar SharePoint</span><span class="sxs-lookup"><span data-stu-id="c93aa-154">Set up SharePoint</span></span>
   
<span data-ttu-id="c93aa-155">Para crear un repositorio de registros, la administración del cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="c93aa-155">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="c93aa-156">Crea un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c93aa-156">Creates a SharePoint site.</span></span>

2. <span data-ttu-id="c93aa-157">Realiza una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="c93aa-157">Does one of the following:</span></span>
        
   - <span data-ttu-id="c93aa-158">Creates a SharePoint library: Set event-based label at the library level.</span><span class="sxs-lookup"><span data-stu-id="c93aa-158">Creates a SharePoint library: Set event-based label at the library level.</span></span> <span data-ttu-id="c93aa-159">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="c93aa-159">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
   - <span data-ttu-id="c93aa-160">Configura un conjunto de documentos en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c93aa-160">Sets up a document set in SharePoint.</span></span> <span data-ttu-id="c93aa-161">Para más información, vea [Introducción a los conjuntos de documentos](https://support.microsoft.com/es-ES/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234).</span><span class="sxs-lookup"><span data-stu-id="c93aa-161">For more information, see [Introduction to document sets](https://support.microsoft.com/es-ES/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234).</span></span>
      
3. <span data-ttu-id="c93aa-162">Asigna un ID. de activo para cada conjunto de documentos de empleado.</span><span class="sxs-lookup"><span data-stu-id="c93aa-162">Assigns an asset ID to each employee document set.</span></span> <span data-ttu-id="c93aa-163">Un ID. de activo es el nombre o código de producto usado por la organización. Por ejemplo, el número de empleado puede ser un ID. de activo.</span><span class="sxs-lookup"><span data-stu-id="c93aa-163">An asset ID is a product name or code used by the organization, for example, Employee number can be an asset ID.</span></span> <span data-ttu-id="c93aa-164">Al asignar el ID. de activo a una carpeta, cada elemento de esta carpeta hereda automáticamente el mismo ID. de activo.</span><span class="sxs-lookup"><span data-stu-id="c93aa-164">By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID.</span></span> <span data-ttu-id="c93aa-165">Esto significa que todos los elementos pueden tener un periodo de retención activado por el mismo evento.</span><span class="sxs-lookup"><span data-stu-id="c93aa-165">This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="c93aa-166">Formas de desencadenar la retención basada en eventos</span><span class="sxs-lookup"><span data-stu-id="c93aa-166">Ways to trigger event-based retention</span></span>

<span data-ttu-id="c93aa-167">Existen dos formas de desencadenar la retención basada en eventos:</span><span class="sxs-lookup"><span data-stu-id="c93aa-167">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="c93aa-168">**Uso de la interfaz de usuario del Centro de administración** Con este proceso puede retener menos contenido a la vez, o bien, la frecuencia de activación de la retención puede ser menor (p. ej., mensual o anual).</span><span class="sxs-lookup"><span data-stu-id="c93aa-168">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention isn't often, such as monthly or yearly.</span></span> <span data-ttu-id="c93aa-169">Para obtener más información sobre este método, consulte [Información general sobre la retención basada en eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="c93aa-169">For more information about this method, see [Overview of event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="c93aa-170">Sin embargo, este método para desencadenar la retención puede consumir demasiado tiempo y producir más errores, lo que daña la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="c93aa-170">However, this method of triggering retention can be time consuming and prone to error, thus stunting scalability.</span></span> <span data-ttu-id="c93aa-171">Por lo tanto, una solución automatizada y sin errores para activar la retención puede mejorar la seguridad de los datos y el cumplimiento normativo.</span><span class="sxs-lookup"><span data-stu-id="c93aa-171">Therefore, an automated, seamless solution to trigger retention can enhance data security and compliance.</span></span>

- <span data-ttu-id="c93aa-172">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly.</span><span class="sxs-lookup"><span data-stu-id="c93aa-172">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly.</span></span> <span data-ttu-id="c93aa-173">The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="c93aa-173">The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center.</span></span> <span data-ttu-id="c93aa-174">You don't need to manually create an event in the UI each time one occurs.</span><span class="sxs-lookup"><span data-stu-id="c93aa-174">You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="c93aa-175">Hay dos opciones para usar la API de REST:</span><span class="sxs-lookup"><span data-stu-id="c93aa-175">There are two options for using the REST API:</span></span>

- <span data-ttu-id="c93aa-176">**Usar Microsoft Flow o una aplicación similar** para desencadenar un evento automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c93aa-176">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="c93aa-177">Microsoft Flow puede orquestar la conexión a otros sistemas.</span><span class="sxs-lookup"><span data-stu-id="c93aa-177">Microsoft Flow is an orchestrator for connecting to other systems.</span></span> <span data-ttu-id="c93aa-178">Además, su uso no requiere una solución personalizada.</span><span class="sxs-lookup"><span data-stu-id="c93aa-178">Using Microsoft Flow doesn't require a custom solution.</span></span>

- <span data-ttu-id="c93aa-179">**PowerShell o un cliente de HTTP para llamar a la API de REST** Usar PowerShell (versión 6 o posterior) para pedirle a la API de REST de Microsoft 365 que cree eventos.</span><span class="sxs-lookup"><span data-stu-id="c93aa-179">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="c93aa-180">Una API de REST es un punto de conexión de servicio que admite conjuntos de operaciones HTTP (métodos), que proporcionan acceso de creación/recuperación/actualización/eliminación a los recursos del servicio.</span><span class="sxs-lookup"><span data-stu-id="c93aa-180">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="c93aa-181">Para obtener más información, vea [Componentes de una solicitud o respuesta de API de REST](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="c93aa-181">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="c93aa-182">En este caso, al usar la API de REST de Microsoft 365, puede crear y recuperar eventos mediante el uso de operaciones (métodos) POST y GET.</span><span class="sxs-lookup"><span data-stu-id="c93aa-182">In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="c93aa-183">Escenarios de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c93aa-183">Example scenarios</span></span>

<span data-ttu-id="c93aa-184">Consideremos los siguientes escenarios.</span><span class="sxs-lookup"><span data-stu-id="c93aa-184">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="c93aa-185">Escenario 1: Empleados que dejan la organización</span><span class="sxs-lookup"><span data-stu-id="c93aa-185">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="c93aa-186">La organización crea y almacena numerosos documentos relacionados con cada empleado.</span><span class="sxs-lookup"><span data-stu-id="c93aa-186">An organization creates and stores numerous employee-related documents per employee.</span></span> <span data-ttu-id="c93aa-187">Estos documentos se administran y conservan durante el tiempo de contratación del empleado.</span><span class="sxs-lookup"><span data-stu-id="c93aa-187">These documents are managed and retained during the employment of each employee.</span></span> <span data-ttu-id="c93aa-188">Sin embargo, cuando el empleado abandona la organización o deja de trabajar para ella, la organización esta comercial y legalmente obligada a conservar los documentos de ese empleado durante un período estipulado.</span><span class="sxs-lookup"><span data-stu-id="c93aa-188">However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="c93aa-189">Ahora si varios empleados dejan la organización todos los días, la organización debe activar el reloj de retención de cientos o miles de documentos cada día.</span><span class="sxs-lookup"><span data-stu-id="c93aa-189">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="c93aa-190">Además, se debe calcular el período de retención de cada uno de estos empleados con el siguiente formato: fecha de despido del empleado + número de días, meses o años en función del tipo de registro del empleado.</span><span class="sxs-lookup"><span data-stu-id="c93aa-190">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months, or years based on the type of the employee record.</span></span> <span data-ttu-id="c93aa-191">Por ejemplo, es posible que la compensación y la tramitación de beneficios del mismo empleado necesiten retenciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="c93aa-191">For example, worker’s compensation of the employee vs. benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="c93aa-192">El siguiente diagrama muestra cómo puede haber varias etiquetas asociadas a un único evento.</span><span class="sxs-lookup"><span data-stu-id="c93aa-192">The diagram below shows how there can be multiple labels that are associated with a single event.</span></span> <span data-ttu-id="c93aa-193">En este caso, todos los archivos de la etiqueta de indemnización del Trabajador y los que pertenecen a la etiqueta de beneficios del Trabajador se asocian a un único evento, que es la salida del empleado.</span><span class="sxs-lookup"><span data-stu-id="c93aa-193">Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event, which is the employee leaving the organization.</span></span> <span data-ttu-id="c93aa-194">Cada uno de estos archivos diferentes tiene diferentes relojes de retención.</span><span class="sxs-lookup"><span data-stu-id="c93aa-194">Each of these different files has different retention clocks.</span></span> <span data-ttu-id="c93aa-195">Por lo tanto, cuando un empleado deja la organización, cada archivo dentro de una misma etiqueta experimenta un período de retención diferente.</span><span class="sxs-lookup"><span data-stu-id="c93aa-195">So, when an employee leaves the organization, these files within each label experience a different retention period.</span></span> <span data-ttu-id="c93aa-196">Activar todos estos relojes de retención diferentes para cada tipo de archivo o etiqueta en un solo empleado es una tarea muy desafiante.</span><span class="sxs-lookup"><span data-stu-id="c93aa-196">Triggering all these different retention clocks for each file type or label for each employee is a very challenging task.</span></span> <span data-ttu-id="c93aa-197">Imagine este proceso con varios empleados.</span><span class="sxs-lookup"><span data-stu-id="c93aa-197">Imagine doing this for multiple employees.</span></span>

![Diagrama de tipo de evento, evento y etiquetas](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="c93aa-199">Por lo tanto, un proceso automatizado para activar estos relojes de retención diferentes para varios empleados permitirá ahorrar tiempo, evitar errores y lograr una alta eficiencia.</span><span class="sxs-lookup"><span data-stu-id="c93aa-199">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free, and extremely efficient.</span></span>

<span data-ttu-id="c93aa-200">**Configuración de retención automatizada basada en eventos para este escenario:**</span><span class="sxs-lookup"><span data-stu-id="c93aa-200">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de funciones y acciones para el escenario del empleado que deja la organización](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="c93aa-202">La administración crea carpetas del empleado en un conjunto de documentos denominado Naiara Padilla, David Pulido.</span><span class="sxs-lookup"><span data-stu-id="c93aa-202">Admin creates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="c93aa-203">La administración agrega archivos del empleado, como los de beneficios, nómina o compensación del trabajador a cada carpeta de empleado.</span><span class="sxs-lookup"><span data-stu-id="c93aa-203">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder.</span></span>

  - <span data-ttu-id="c93aa-204">La administración asigna el id. de activo a la carpeta de cada empleado.</span><span class="sxs-lookup"><span data-stu-id="c93aa-204">Admin assigns Asset ID to each employee folder.</span></span> 

  - <span data-ttu-id="c93aa-205">La administración de SSC inicia sesión en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="c93aa-205">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="c93aa-206">La administración de SCC crea tipos de eventos relacionados con el empleado como “Desvinculación del empleado”, “Contratación del empleados”.</span><span class="sxs-lookup"><span data-stu-id="c93aa-206">SCC Admin creates employee-related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="c93aa-207">La administración de SCC crea la etiqueta de "Retención de empleados".</span><span class="sxs-lookup"><span data-stu-id="c93aa-207">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="c93aa-208">Esta etiqueta de "Retención de empleados" se publica y se aplican manual o automáticamente a los archivos de empleado en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c93aa-208">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint.</span></span>

  - <span data-ttu-id="c93aa-209">Un sistema de administración de Recursos Humanos como Workday puede trabajar con Microsoft Flow para ejecutarse periódicamente para administrar archivos del empleado.</span><span class="sxs-lookup"><span data-stu-id="c93aa-209">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files.</span></span>

  - <span data-ttu-id="c93aa-210">Cuando un empleado deja la organización, Flow activa la API de REST de retención basada en eventos de M365 que inicia el reloj de retención de archivos específicos del empleado.</span><span class="sxs-lookup"><span data-stu-id="c93aa-210">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="c93aa-211">Usar Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="c93aa-211">Using Microsoft Flow</span></span>

<span data-ttu-id="c93aa-212">Paso 1: crear un flujo para crear un evento mediante la API de REST de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c93aa-212">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Usar Flow para crear un evento](../media/automate-event-driven-retention-flow-1.png)

![Usar Flow para llamar a la API de REST](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="c93aa-215">Crear un evento</span><span class="sxs-lookup"><span data-stu-id="c93aa-215">Create an event</span></span>

<span data-ttu-id="c93aa-216">Código de ejemplo para llamar a la API de REST:</span><span class="sxs-lookup"><span data-stu-id="c93aa-216">Sample code to call the REST API:</span></span>

- <span data-ttu-id="c93aa-217">**Método**: POST</span><span class="sxs-lookup"><span data-stu-id="c93aa-217">**Method**: POST</span></span>
- <span data-ttu-id="c93aa-218">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="c93aa-218">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="c93aa-219">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="c93aa-219">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="c93aa-220">**Body**:</span><span class="sxs-lookup"><span data-stu-id="c93aa-220">**Body**:</span></span>
    
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
- <span data-ttu-id="c93aa-221">**Autenticación**: Básica</span><span class="sxs-lookup"><span data-stu-id="c93aa-221">**Authentication**: Basic</span></span>
- <span data-ttu-id="c93aa-222">**Nombre de usuario**: “Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="c93aa-222">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="c93aa-223">**Contraseña**: “Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="c93aa-223">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="c93aa-224">Parámetros disponibles</span><span class="sxs-lookup"><span data-stu-id="c93aa-224">Available parameters</span></span>


|<span data-ttu-id="c93aa-225">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c93aa-225">Parameters</span></span>|<span data-ttu-id="c93aa-226">Description</span><span class="sxs-lookup"><span data-stu-id="c93aa-226">Description</span></span>|<span data-ttu-id="c93aa-227">Notas</span><span class="sxs-lookup"><span data-stu-id="c93aa-227">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="c93aa-228"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="c93aa-228"><d:Name></d:Name></span></span>|<span data-ttu-id="c93aa-229">Escriba un nombre único para el evento.</span><span class="sxs-lookup"><span data-stu-id="c93aa-229">Provide a unique name for the event,</span></span>|<span data-ttu-id="c93aa-230">No puede contener espacios finales ni los siguientes caracteres: % \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="c93aa-230">Cannot contain trailing spaces, and the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="c93aa-231">, : ;</span><span class="sxs-lookup"><span data-stu-id="c93aa-231">, : ;</span></span>|
|<span data-ttu-id="c93aa-232"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="c93aa-232"><d:EventType></d:EventType></span></span>|<span data-ttu-id="c93aa-233">Escribe el nombre del tipo de evento (o Guid)</span><span class="sxs-lookup"><span data-stu-id="c93aa-233">Enter event type name (or Guid),</span></span>|<span data-ttu-id="c93aa-234">Example: “Employee termination”.</span><span class="sxs-lookup"><span data-stu-id="c93aa-234">Example: “Employee termination”.</span></span> <span data-ttu-id="c93aa-235">Event type has to be associated with a retention label.</span><span class="sxs-lookup"><span data-stu-id="c93aa-235">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="c93aa-236"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="c93aa-236"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="c93aa-237">Escriba "ComplianceAssetId:" + el Id. del empleado</span><span class="sxs-lookup"><span data-stu-id="c93aa-237">Enter “ComplianceAssetId:” + employee Id</span></span>|<span data-ttu-id="c93aa-238">Ejemplo: "ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="c93aa-238">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="c93aa-239"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="c93aa-239"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="c93aa-240">Fecha y hora del evento</span><span class="sxs-lookup"><span data-stu-id="c93aa-240">Event Date and Time</span></span>|<span data-ttu-id="c93aa-241">Formato: aaaa-MM-ddTHH:mm:ssZ, ejemplo: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="c93aa-241">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

##### <a name="response-codes"></a><span data-ttu-id="c93aa-242">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="c93aa-242">Response codes</span></span>

| <span data-ttu-id="c93aa-243">Código de respuesta</span><span class="sxs-lookup"><span data-stu-id="c93aa-243">Response Code</span></span> | <span data-ttu-id="c93aa-244">Descripción</span><span class="sxs-lookup"><span data-stu-id="c93aa-244">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="c93aa-245">302</span><span class="sxs-lookup"><span data-stu-id="c93aa-245">302</span></span>               | <span data-ttu-id="c93aa-246">Redirigir</span><span class="sxs-lookup"><span data-stu-id="c93aa-246">Redirect</span></span>              |
| <span data-ttu-id="c93aa-247">201</span><span class="sxs-lookup"><span data-stu-id="c93aa-247">201</span></span>               | <span data-ttu-id="c93aa-248">Fecha de creación</span><span class="sxs-lookup"><span data-stu-id="c93aa-248">Created</span></span>               |
| <span data-ttu-id="c93aa-249">403</span><span class="sxs-lookup"><span data-stu-id="c93aa-249">403</span></span>               | <span data-ttu-id="c93aa-250">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="c93aa-250">Authorization Failed</span></span>  |
| <span data-ttu-id="c93aa-251">401</span><span class="sxs-lookup"><span data-stu-id="c93aa-251">401</span></span>               | <span data-ttu-id="c93aa-252">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="c93aa-252">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="c93aa-253">Obtener eventos según el intervalo de tiempo</span><span class="sxs-lookup"><span data-stu-id="c93aa-253">Get Events based on time range</span></span>

- <span data-ttu-id="c93aa-254">**Método**: GET</span><span class="sxs-lookup"><span data-stu-id="c93aa-254">**Method**: GET</span></span>

- <span data-ttu-id="c93aa-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="c93aa-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="c93aa-256">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="c93aa-256">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="c93aa-257">**Autenticación**: Básica</span><span class="sxs-lookup"><span data-stu-id="c93aa-257">**Authentication**: Basic</span></span>

- <span data-ttu-id="c93aa-258">**Nombre de usuario**: “Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="c93aa-258">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="c93aa-259">**Contraseña**: “Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="c93aa-259">**Password**: "Compliancepassword"</span></span>


##### <a name="response-codes"></a><span data-ttu-id="c93aa-260">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="c93aa-260">Response codes</span></span>

| <span data-ttu-id="c93aa-261">Código de respuesta</span><span class="sxs-lookup"><span data-stu-id="c93aa-261">Response Code</span></span> | <span data-ttu-id="c93aa-262">Descripción</span><span class="sxs-lookup"><span data-stu-id="c93aa-262">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="c93aa-263">200</span><span class="sxs-lookup"><span data-stu-id="c93aa-263">200</span></span>               | <span data-ttu-id="c93aa-264">Aceptar, una lista de eventos de atom+ xml</span><span class="sxs-lookup"><span data-stu-id="c93aa-264">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="c93aa-265">404</span><span class="sxs-lookup"><span data-stu-id="c93aa-265">404</span></span>               | <span data-ttu-id="c93aa-266">No encontrado</span><span class="sxs-lookup"><span data-stu-id="c93aa-266">Not found</span></span>                         |
| <span data-ttu-id="c93aa-267">302</span><span class="sxs-lookup"><span data-stu-id="c93aa-267">302</span></span>               | <span data-ttu-id="c93aa-268">Redirigir</span><span class="sxs-lookup"><span data-stu-id="c93aa-268">Redirect</span></span>                          |
| <span data-ttu-id="c93aa-269">401</span><span class="sxs-lookup"><span data-stu-id="c93aa-269">401</span></span>               | <span data-ttu-id="c93aa-270">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="c93aa-270">Authorization Failed</span></span>              |
| <span data-ttu-id="c93aa-271">403</span><span class="sxs-lookup"><span data-stu-id="c93aa-271">403</span></span>               | <span data-ttu-id="c93aa-272">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="c93aa-272">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="c93aa-273">Obtén un objeto por id.</span><span class="sxs-lookup"><span data-stu-id="c93aa-273">Get an event by ID</span></span>

- <span data-ttu-id="c93aa-274">**Método**: GET</span><span class="sxs-lookup"><span data-stu-id="c93aa-274">**Method**: GET</span></span>

- <span data-ttu-id="c93aa-275">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="c93aa-275">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="c93aa-276">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="c93aa-276">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="c93aa-277">**Autenticación**: Básica</span><span class="sxs-lookup"><span data-stu-id="c93aa-277">**Authentication**: Basic</span></span>

- <span data-ttu-id="c93aa-278">**Nombre de usuario**: “Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="c93aa-278">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="c93aa-279">**Contraseña**: “Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="c93aa-279">**Password**: "Compliancepassword"</span></span>



##### <a name="response-codes"></a><span data-ttu-id="c93aa-280">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="c93aa-280">Response codes</span></span>

| <span data-ttu-id="c93aa-281">Código de respuesta</span><span class="sxs-lookup"><span data-stu-id="c93aa-281">Response Code</span></span> | <span data-ttu-id="c93aa-282">Descripción</span><span class="sxs-lookup"><span data-stu-id="c93aa-282">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="c93aa-283">200</span><span class="sxs-lookup"><span data-stu-id="c93aa-283">200</span></span>               | <span data-ttu-id="c93aa-284">Aceptar, el cuerpo de la respuesta contiene el evento en atom+ xml</span><span class="sxs-lookup"><span data-stu-id="c93aa-284">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="c93aa-285">404</span><span class="sxs-lookup"><span data-stu-id="c93aa-285">404</span></span>               | <span data-ttu-id="c93aa-286">No encontrado</span><span class="sxs-lookup"><span data-stu-id="c93aa-286">Not found</span></span>                                            |
| <span data-ttu-id="c93aa-287">302</span><span class="sxs-lookup"><span data-stu-id="c93aa-287">302</span></span>               | <span data-ttu-id="c93aa-288">Redirigir</span><span class="sxs-lookup"><span data-stu-id="c93aa-288">Redirect</span></span>                                             |
| <span data-ttu-id="c93aa-289">401</span><span class="sxs-lookup"><span data-stu-id="c93aa-289">401</span></span>               | <span data-ttu-id="c93aa-290">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="c93aa-290">Authorization Failed</span></span>                                 |
| <span data-ttu-id="c93aa-291">403</span><span class="sxs-lookup"><span data-stu-id="c93aa-291">403</span></span>               | <span data-ttu-id="c93aa-292">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="c93aa-292">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="c93aa-293">Obtén un evento por nombre</span><span class="sxs-lookup"><span data-stu-id="c93aa-293">Get an event by name</span></span>

- <span data-ttu-id="c93aa-294">**Método**: GET</span><span class="sxs-lookup"><span data-stu-id="c93aa-294">**Method**: GET</span></span>

- <span data-ttu-id="c93aa-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="c93aa-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="c93aa-296">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="c93aa-296">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="c93aa-297">**Autenticación**: Básica</span><span class="sxs-lookup"><span data-stu-id="c93aa-297">**Authentication**: Basic</span></span>

- <span data-ttu-id="c93aa-298">**Nombre de usuario**: “Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="c93aa-298">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="c93aa-299">**Contraseña**: “Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="c93aa-299">**Password**: "Compliancepassword"</span></span>


##### <a name="response-codes"></a><span data-ttu-id="c93aa-300">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="c93aa-300">Response codes</span></span>

| <span data-ttu-id="c93aa-301">Código de respuesta</span><span class="sxs-lookup"><span data-stu-id="c93aa-301">Response Code</span></span> | <span data-ttu-id="c93aa-302">Descripción</span><span class="sxs-lookup"><span data-stu-id="c93aa-302">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="c93aa-303">200</span><span class="sxs-lookup"><span data-stu-id="c93aa-303">200</span></span>               | <span data-ttu-id="c93aa-304">Aceptar, el cuerpo de la respuesta contiene el evento en atom+ xml</span><span class="sxs-lookup"><span data-stu-id="c93aa-304">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="c93aa-305">404</span><span class="sxs-lookup"><span data-stu-id="c93aa-305">404</span></span>               | <span data-ttu-id="c93aa-306">No encontrado</span><span class="sxs-lookup"><span data-stu-id="c93aa-306">Not found</span></span>                                            |
| <span data-ttu-id="c93aa-307">302</span><span class="sxs-lookup"><span data-stu-id="c93aa-307">302</span></span>               | <span data-ttu-id="c93aa-308">Redirigir</span><span class="sxs-lookup"><span data-stu-id="c93aa-308">Redirect</span></span>                                             |
| <span data-ttu-id="c93aa-309">401</span><span class="sxs-lookup"><span data-stu-id="c93aa-309">401</span></span>               | <span data-ttu-id="c93aa-310">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="c93aa-310">Authorization Failed</span></span>                                 |
| <span data-ttu-id="c93aa-311">403</span><span class="sxs-lookup"><span data-stu-id="c93aa-311">403</span></span>               | <span data-ttu-id="c93aa-312">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="c93aa-312">Authentication Failed</span></span>                                |

#### <a name="using-powershell-version-6-or-later-or-any-http-client"></a><span data-ttu-id="c93aa-313">Usar PowerShell (versión 6 o posterior) o cualquier cliente HTTP</span><span class="sxs-lookup"><span data-stu-id="c93aa-313">Using PowerShell (version 6 or later) or any HTTP client</span></span>

<span data-ttu-id="c93aa-314">Paso 1: Conéctate a PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c93aa-314">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="c93aa-315">Paso 2: Ejecuta el siguiente script.</span><span class="sxs-lookup"><span data-stu-id="c93aa-315">Step 2: Run the following script.</span></span>

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


#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="c93aa-316">Comprobar el resultado en ambas opciones.</span><span class="sxs-lookup"><span data-stu-id="c93aa-316">Verify the outcome in both options</span></span>

<span data-ttu-id="c93aa-317">Paso 1: Ir al Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="c93aa-317">Step 1: Go to the Security & Compliance Center.</span></span>

<span data-ttu-id="c93aa-318">Paso 2: seleccione los **eventos** en **control de la información**.</span><span class="sxs-lookup"><span data-stu-id="c93aa-318">Step 2: Select **Events** under **Information governance**.</span></span>

<span data-ttu-id="c93aa-319">Paso 3: Comprobar que se creó el evento.</span><span class="sxs-lookup"><span data-stu-id="c93aa-319">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="c93aa-320">De forma similar, también se pueden usar las opciones anteriores para automatizar la retención basada en eventos para los siguientes escenarios.</span><span class="sxs-lookup"><span data-stu-id="c93aa-320">Similarly, the above options to automate event-based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="c93aa-321">Escenario 2: Contratos que expiran</span><span class="sxs-lookup"><span data-stu-id="c93aa-321">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="c93aa-322">Una organización puede tener varios registros para un contrato único con clientes, proveedores y asociados.</span><span class="sxs-lookup"><span data-stu-id="c93aa-322">An organization can have multiple records for a single contract with customers, vendors, and partners.</span></span> <span data-ttu-id="c93aa-323">Estos documentos pueden residir en una biblioteca de documentos como SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c93aa-323">These documents can reside in a document library like SharePoint.</span></span> <span data-ttu-id="c93aa-324">Con la finalización de un contrato empieza el periodo de retención de los documentos asociados al contrato.</span><span class="sxs-lookup"><span data-stu-id="c93aa-324">The end of a contract determines the start of the retention period of the documents associated with the contract.</span></span> <span data-ttu-id="c93aa-325">Por ejemplo, se deben conservar todos los registros relacionados con un contrato cinco años después de que expire.</span><span class="sxs-lookup"><span data-stu-id="c93aa-325">For example, all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="c93aa-326">El evento que desencadena el período de retención de cinco años es la expiración del contrato.</span><span class="sxs-lookup"><span data-stu-id="c93aa-326">The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="c93aa-327">Un sistema de administración de relaciones de cliente (CRM) puede trabajar con Microsoft 365 y activar la retención de documentos del contrato.</span><span class="sxs-lookup"><span data-stu-id="c93aa-327">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents.</span></span>

<span data-ttu-id="c93aa-328">**Configuración de retención automatizada basada en eventos para este escenario:**</span><span class="sxs-lookup"><span data-stu-id="c93aa-328">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de los funciones y tareas para escenarios de expiración del contrato](../media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="c93aa-330">La administración crea una biblioteca de SharePoint con carpetas diferentes para cada tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="c93aa-330">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="c93aa-331">La administración agrega archivos del contrato como contratos de licencia y contratos de desarrollo para cada carpeta del contrato.</span><span class="sxs-lookup"><span data-stu-id="c93aa-331">Admin adds contract files such as License Contracts, Development Contracts to each contract folder.</span></span>

  - <span data-ttu-id="c93aa-332">La administración asigna el id. de activo a cada carpeta de contrato.</span><span class="sxs-lookup"><span data-stu-id="c93aa-332">Admin assigns Asset ID to each contract folder.</span></span>

  - <span data-ttu-id="c93aa-333">La administración de SSC inicia sesión en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="c93aa-333">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="c93aa-334">La administración de SCC crea tipos de eventos relacionados con el contrato como eventos de "Creación del contrato" y de "Expiración del contrato".</span><span class="sxs-lookup"><span data-stu-id="c93aa-334">SCC Admin creates contract-related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="c93aa-335">La administración de SCC crea la etiqueta "Expiración del contrato".</span><span class="sxs-lookup"><span data-stu-id="c93aa-335">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="c93aa-336">Esta etiqueta de "Expiración del contrato" se publica y se aplican de forma manual o automática a los archivos del contrato en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c93aa-336">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint.</span></span>

  - <span data-ttu-id="c93aa-337">El sistema de administración de contrato puede trabajar con Microsoft Flow o una aplicación similar para ejecutarse periódicamente para administrar archivos de contrato.</span><span class="sxs-lookup"><span data-stu-id="c93aa-337">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files.</span></span>

  - <span data-ttu-id="c93aa-338">Si un contrato vence, Microsoft Flow activará la API de REST de retención basada en eventos de M365 que iniciará el reloj de retención de archivos específicos del contrato.</span><span class="sxs-lookup"><span data-stu-id="c93aa-338">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="c93aa-339">Escenario 3: Final de fabricación de productos</span><span class="sxs-lookup"><span data-stu-id="c93aa-339">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="c93aa-340">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents.</span><span class="sxs-lookup"><span data-stu-id="c93aa-340">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents.</span></span> <span data-ttu-id="c93aa-341">When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span><span class="sxs-lookup"><span data-stu-id="c93aa-341">When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="c93aa-342">Un sistema de planeación de recursos empresariales (ERP) puede trabajar con Microsoft 365 y Microsoft Flow para activar la retención.</span><span class="sxs-lookup"><span data-stu-id="c93aa-342">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="c93aa-343">**Configuración de retención automatizada basada en eventos para este escenario:**</span><span class="sxs-lookup"><span data-stu-id="c93aa-343">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de las funciones y tareas para escenarios de ciclo de vida del producto](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="c93aa-345">La administración crea carpetas de productos en el conjunto de documentos como Producto 1, Producto 2, etc.</span><span class="sxs-lookup"><span data-stu-id="c93aa-345">Admin creates product folders in the Document set such as Product 1, Product 2, and so on.</span></span>

  - <span data-ttu-id="c93aa-346">La administración agrega los archivos de productos como Especificaciones de fabricación, Precio del producto y Licencias del producto a cada carpeta de producto.</span><span class="sxs-lookup"><span data-stu-id="c93aa-346">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder.</span></span>

  - <span data-ttu-id="c93aa-347">La administración le asigna el id. de activo a cada carpeta del producto.</span><span class="sxs-lookup"><span data-stu-id="c93aa-347">Admin assigns Asset ID to each product folder.</span></span>

  - <span data-ttu-id="c93aa-348">La administración de SSC inicia sesión en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="c93aa-348">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="c93aa-349">La administración de SCC crea tipos de eventos relacionados con el empleado como "Inicio de fabricación del producto" y "Final de fabricación del producto".</span><span class="sxs-lookup"><span data-stu-id="c93aa-349">SCC Admin creates employee-related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="c93aa-350">La administración de SCC crea la etiqueta "Final de fabricación del producto".</span><span class="sxs-lookup"><span data-stu-id="c93aa-350">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="c93aa-351">Esta etiqueta de "Final de fabricación del producto" se publica y se aplica de forma manual o automática a los archivos del producto en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c93aa-351">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint.</span></span>

  - <span data-ttu-id="c93aa-352">Los sistemas de ERP pueden funcionar con Microsoft Flow o con aplicaciones similares para ejecutarse periódicamente para administrar archivos del producto.</span><span class="sxs-lookup"><span data-stu-id="c93aa-352">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files.</span></span>

  - <span data-ttu-id="c93aa-353">Si se termina la fabricación de un producto, Microsoft Flow activará la API de REST de retención basada en eventos de M365 que iniciará el reloj de retención de archivos específicos del producto.</span><span class="sxs-lookup"><span data-stu-id="c93aa-353">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="c93aa-354">Apéndice</span><span class="sxs-lookup"><span data-stu-id="c93aa-354">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="c93aa-355">Cómo usar los resultados de respuesta Redirect 302 para llamar a la API de REST</span><span class="sxs-lookup"><span data-stu-id="c93aa-355">Using Redirect 302 response results to call the REST API</span></span>

1. <span data-ttu-id="c93aa-356">Invoque una llamada al evento de retención POST con la dirección URL de la API de REST: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="c93aa-356">Invoke a POST retention event call by using the REST API URL: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
    
    <span data-ttu-id="c93aa-357">Se necesitan permisos de administrador global.</span><span class="sxs-lookup"><span data-stu-id="c93aa-357">Global administrator permissions are required.</span></span>

2. <span data-ttu-id="c93aa-358">Compruebe el código de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c93aa-358">Check the response code.</span></span> <span data-ttu-id="c93aa-359">Si es 302, obtener la dirección URL redirigida de la propiedad de ubicación del encabezado de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c93aa-359">If it's 302, then get the redirected URL from Location property of the response header.</span></span>

3. <span data-ttu-id="c93aa-360">Invocar la llamada al evento de retención POST nuevamente mediante el URL redireccionado.</span><span class="sxs-lookup"><span data-stu-id="c93aa-360">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="c93aa-361">Créditos</span><span class="sxs-lookup"><span data-stu-id="c93aa-361">Credits</span></span>

<span data-ttu-id="c93aa-362">Este tema fue revisado por:</span><span class="sxs-lookup"><span data-stu-id="c93aa-362">This topic was reviewed by:</span></span>

<span data-ttu-id="c93aa-363">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="c93aa-363">Antonio Maio</span></span><br/><span data-ttu-id="c93aa-364">MVP de servicios y aplicaciones de Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="c93aa-364">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="c93aa-365">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="c93aa-365">Antonio.Maio@Protiviti.com</span></span>
