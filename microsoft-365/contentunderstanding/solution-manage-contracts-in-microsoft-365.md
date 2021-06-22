---
title: Administrar contratos con una solución de Microsoft 365
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
ms.collection: m365solution-managecontracts m365solution-overview
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Obtenga información sobre cómo administrar contratos mediante una Microsoft 365 de SharePoint Syntex, listas de SharePoint, Microsoft Teams y Power Automate.
ms.openlocfilehash: d3be12dbddabbcddc41f7c9d882db5473350266e
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054760"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a><span data-ttu-id="97dee-103">Administrar contratos con una solución de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="97dee-103">Manage contracts using a Microsoft 365 solution</span></span>

<span data-ttu-id="97dee-104">En este artículo se describe cómo crear una solución de administración de contratos para su organización mediante SharePoint Syntex y componentes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="97dee-104">This article describes how to create a contracts management solution for your organization by using SharePoint Syntex and components of Microsoft 365.</span></span> <span data-ttu-id="97dee-105">Le proporciona un marco para ayudarle a planear y crear una solución que se adapte a sus necesidades empresariales únicas.</span><span class="sxs-lookup"><span data-stu-id="97dee-105">It provides you with a framework to help you plan and create a solution that fits your unique business needs.</span></span> <span data-ttu-id="97dee-106">Incluso si esta solución no se adapta a sus necesidades empresariales en su conjunto, partes de ella se pueden adoptar en la planeación para crear una solución de administración de contratos personalizada.</span><span class="sxs-lookup"><span data-stu-id="97dee-106">Even if this solution doesn't suit your business needs as a whole, parts of it can be adopted in your planning to create a custom contract management solution.</span></span>

<span data-ttu-id="97dee-107">*Este conjunto de contenido documenta una Microsoft 365 desarrollada por Tomás Molbach con el Equipo de estrategia de soluciones de trabajo moderno de Microsoft.*</span><span class="sxs-lookup"><span data-stu-id="97dee-107">*This content set documents a Microsoft 365 solution developed by Thomas Molbach with the Modern Work Solution Strategy Team at Microsoft.*</span></span>

## <a name="identify-the-business-problem"></a><span data-ttu-id="97dee-108">Identificar el problema empresarial</span><span class="sxs-lookup"><span data-stu-id="97dee-108">Identify the business problem</span></span>

<span data-ttu-id="97dee-109">El primer paso para planear el sistema de administración de contratos es comprender el problema que está intentando resolver.</span><span class="sxs-lookup"><span data-stu-id="97dee-109">The first step in planning your contract management system is to understand the problem you're trying to solve.</span></span> <span data-ttu-id="97dee-110">Para esta solución, deben tratarse cuatro problemas clave:</span><span class="sxs-lookup"><span data-stu-id="97dee-110">For this solution, four key issues need to be addressed:</span></span>

- <span data-ttu-id="97dee-111">**Identificar contratos**.</span><span class="sxs-lookup"><span data-stu-id="97dee-111">**Identify contracts**.</span></span> <span data-ttu-id="97dee-112">Su organización trabaja con muchos documentos, como facturas, contratos, extractos de trabajo, entre otros.</span><span class="sxs-lookup"><span data-stu-id="97dee-112">Your organization works with many documents, such as invoices, contracts, statements of work, and so on.</span></span>  <span data-ttu-id="97dee-113">Algunos son activos digitales enviados por correo electrónico y otros son activos de papel enviados a través del correo tradicional.</span><span class="sxs-lookup"><span data-stu-id="97dee-113">Some are digital assets sent through email, and some are paper assets sent through traditional mail.</span></span> <span data-ttu-id="97dee-114">Necesita una forma de identificar todos los contratos de clientes de todos los demás documentos y, a continuación, clasificarlos como tales.</span><span class="sxs-lookup"><span data-stu-id="97dee-114">You need a way to identify all customer contracts from all other documents, and then classifying them as such.</span></span>

- <span data-ttu-id="97dee-115">**Realice un seguimiento del historial de aprobaciones de contratos**.</span><span class="sxs-lookup"><span data-stu-id="97dee-115">**Track the history of contract approvals**.</span></span> <span data-ttu-id="97dee-116">Su organización necesita una forma confiable de averiguar si los contratos se han aprobado o rechazado, y si se ha procesado el pago.</span><span class="sxs-lookup"><span data-stu-id="97dee-116">Your organization needs a reliable way to find whether contracts have been either approved or rejected, and whether payment has been processed.</span></span> 

- <span data-ttu-id="97dee-117">**Sitio para administrar aprobaciones de contratos**.</span><span class="sxs-lookup"><span data-stu-id="97dee-117">**Site to manage contract approvals**.</span></span> <span data-ttu-id="97dee-118">Su organización debe configurar un sitio de colaboración en el que todas las partes interesadas necesarias puedan revisar fácilmente los contratos.</span><span class="sxs-lookup"><span data-stu-id="97dee-118">Your organization needs to set up a collaborative site in which all required stakeholders can easily review contracts.</span></span> <span data-ttu-id="97dee-119">Las partes interesadas deben poder revisar todo el contrato si es necesario, pero sobre todo se preocupan por ver varios campos clave de cada contrato (por ejemplo, nombre del cliente, número de pedido y costo total).</span><span class="sxs-lookup"><span data-stu-id="97dee-119">Stakeholders should be able to review the whole contract if needed, but mostly care about seeing several key fields from each contract (for example, customer name, PO number, and total cost).</span></span> <span data-ttu-id="97dee-120">Las partes interesadas deben poder aprobar o rechazar fácilmente los contratos entrantes.</span><span class="sxs-lookup"><span data-stu-id="97dee-120">Stakeholders should be able to easily approve or reject incoming contracts.</span></span>

- <span data-ttu-id="97dee-121">**Enrutar contratos revisados**.</span><span class="sxs-lookup"><span data-stu-id="97dee-121">**Route reviewed contracts**.</span></span> <span data-ttu-id="97dee-122">Los contratos aprobados y rechazados deben enrutarse a través de un flujo de trabajo específico.</span><span class="sxs-lookup"><span data-stu-id="97dee-122">Approved and rejected contracts need to be routed through a specific workflow.</span></span> <span data-ttu-id="97dee-123">Los contratos aprobados deben enrutrse a una aplicación de terceros para el procesamiento de pagos.</span><span class="sxs-lookup"><span data-stu-id="97dee-123">Approved contracts need to be routed to a third-party application for payment processing.</span></span> <span data-ttu-id="97dee-124">Los contratos rechazados deben enrutarse para una revisión adicional.</span><span class="sxs-lookup"><span data-stu-id="97dee-124">Rejected contracts need to be routed for additional review.</span></span>

## <a name="overview-of-the-solution"></a><span data-ttu-id="97dee-125">Información general sobre la solución</span><span class="sxs-lookup"><span data-stu-id="97dee-125">Overview of the solution</span></span>

  ![Diagrama de la solución mediante SharePoint Syntex, SharePoint listas, Teams y Power Automate.](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

<span data-ttu-id="97dee-127">Esta guía de solución de administración de contratos incluye cuatro componentes Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="97dee-127">This contract management solution guidance includes four components of Microsoft 365:</span></span>

- <span data-ttu-id="97dee-128">**Microsoft SharePoint Syntex:** cree modelos para identificar y clasificar los archivos de contrato y, a continuación, extraer los datos adecuados de ellos.</span><span class="sxs-lookup"><span data-stu-id="97dee-128">**Microsoft SharePoint Syntex**: Create models to identify and classify your contract files and then extract the appropriate data from them.</span></span>

- <span data-ttu-id="97dee-129">**Listas SharePoint microsoft:** use el formato disponible en listas de SharePoint modernas para presentar contratos en un formato descriptivo para empresas.</span><span class="sxs-lookup"><span data-stu-id="97dee-129">**Microsoft SharePoint lists**: Use the formatting available in modern SharePoint lists to present contracts in a business-friendly format.</span></span>

- <span data-ttu-id="97dee-130">**Microsoft Teams:** use la funcionalidad de un canal de Teams y pestañas asociadas para permitir a las partes interesadas revisar y administrar contratos.</span><span class="sxs-lookup"><span data-stu-id="97dee-130">**Microsoft Teams**: Use the functionality of a Teams channel and associated tabs to allow your stakeholders to review and manage contracts.</span></span>

- <span data-ttu-id="97dee-131">**Power Automate:** use flujos para guiar los contratos a través del proceso de aprobación y, a continuación, a una aplicación de terceros para su pago.</span><span class="sxs-lookup"><span data-stu-id="97dee-131">**Power Automate**: Use flows to guide contracts through the approval process, and then to a third-party application for payment.</span></span>

### <a name="how-it-all-works"></a><span data-ttu-id="97dee-132">Cómo funciona todo</span><span class="sxs-lookup"><span data-stu-id="97dee-132">How it all works</span></span>

  ![Diagrama de la solución que muestra el flujo de trabajo para cargar documentos, extraer datos, notificar a las partes interesadas y aprobar o rechazar el contrato.](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. <span data-ttu-id="97dee-134">Los documentos se cargan en una SharePoint de documentos.</span><span class="sxs-lookup"><span data-stu-id="97dee-134">Documents are uploaded to a SharePoint document library.</span></span> <span data-ttu-id="97dee-135">Se SharePoint Syntex modelo de comprensión de documentos a la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="97dee-135">A SharePoint Syntex document understanding model has been applied to the document library.</span></span> <span data-ttu-id="97dee-136">Comprueba cada archivo para ver si coincide con un tipo de contenido "contrato" que está capacitado para buscar.</span><span class="sxs-lookup"><span data-stu-id="97dee-136">It checks each file to see if any match a "contract" content type it's trained to look for.</span></span> <span data-ttu-id="97dee-137">Si encuentra una coincidencia, clasifica el archivo como un "contrato" y actualiza el tipo de contenido del documento.</span><span class="sxs-lookup"><span data-stu-id="97dee-137">If it finds a match, it classifies the file as a "contract" and updates the content type for the document.</span></span>

2. <span data-ttu-id="97dee-138">El modelo también extrae datos específicos de cada archivo de contrato que las partes interesadas están interesadas en ver, como el importe de *cliente,* contratista *y* *tarifa.*</span><span class="sxs-lookup"><span data-stu-id="97dee-138">The model also pulls out specific data from each contract file that stakeholders are interested in seeing, such as the *Client*, *Contractor*, and *Fee amount*.</span></span>

    <span data-ttu-id="97dee-139">La página siguiente es un ejemplo de un contrato que el modelo está capacitado para identificar.</span><span class="sxs-lookup"><span data-stu-id="97dee-139">The following page is an example of a contract that the model is trained to identify.</span></span>

      ![Ejemplo de un contrato.](../media/content-understanding/contract.png)

3. <span data-ttu-id="97dee-141">En Microsoft Teams, todas las partes interesadas son miembros de un canal de Teams seguro en el que todos los contratos de la biblioteca de documentos están visibles para su aprobación o rechazo.</span><span class="sxs-lookup"><span data-stu-id="97dee-141">In Microsoft Teams, all stakeholders are members of a secure Teams channel in which all contracts in the document library are visible for approval or rejection.</span></span> <span data-ttu-id="97dee-142">Al usar Teams, se notifica a todas las partes interesadas cuando es necesario revisar nuevos contratos.</span><span class="sxs-lookup"><span data-stu-id="97dee-142">By using Teams functionality, all stakeholders are notified when new contracts need to be reviewed.</span></span>
 
4. <span data-ttu-id="97dee-143">Al usar Power Automate, los contratos se mueven a través del proceso de aprobación en el Teams canal.</span><span class="sxs-lookup"><span data-stu-id="97dee-143">By using Power Automate, contracts are moved through the approval process in the Teams channel.</span></span> <span data-ttu-id="97dee-144">Cuando un miembro aprueba un contrato, se cambia el estado del contrato para aprobarlo, se notifica a todos los miembros a través de una publicación de Teams y se crea un elemento de línea para mostrar que el contrato está listo para el pago.</span><span class="sxs-lookup"><span data-stu-id="97dee-144">When a member approves a contract, the contract status is changed to approve, all members are notified through a Teams post, and a line item is created to show that the contract is ready for payout.</span></span> <span data-ttu-id="97dee-145">Este proceso se puede extender para escribir directamente en una aplicación financiera de terceros para su pago.</span><span class="sxs-lookup"><span data-stu-id="97dee-145">This process can be extended to write directly to a third-party financial application for payment.</span></span>

5.  <span data-ttu-id="97dee-146">Cuando un miembro rechaza un contrato, el estado cambia a rechazado y se notifica a todos los miembros a través de una Teams correo.</span><span class="sxs-lookup"><span data-stu-id="97dee-146">When a member rejects a contract, the status is changed to rejected, and all members are notified through a Teams post.</span></span>

6. <span data-ttu-id="97dee-147">El resultado final de esta solución es un proceso de negocio automatizado para su organización.</span><span class="sxs-lookup"><span data-stu-id="97dee-147">The end result of this solution is an automated business process for your organization.</span></span> <span data-ttu-id="97dee-148">Los empleados pueden usar fácilmente la vista de mosaico personalizada Teams iniciar y supervisar el flujo de trabajo de aprobación de los documentos.</span><span class="sxs-lookup"><span data-stu-id="97dee-148">Employees can easily use the custom tile view in Teams to initiate and monitor the approval workflow of your documents.</span></span> 

     ![Ficha Contratos.](../media/content-understanding/tile-view.png)

### <a name="licensing-requirements"></a><span data-ttu-id="97dee-150">Requisitos de licencias</span><span class="sxs-lookup"><span data-stu-id="97dee-150">Licensing requirements</span></span>

<span data-ttu-id="97dee-151">Esta solución se basa en las siguientes funciones, todas disponibles como parte de una licencia de Microsoft 365 Enterprise (E1, E3, E5, F3) o Empresa (básica, estándar o Premium):</span><span class="sxs-lookup"><span data-stu-id="97dee-151">This solution relies on the following functionality, all available as part of a Microsoft 365 Enterprise (E1, E3, E5, F3) or Business (Basic, Standard, or Premium) license:</span></span>

-   <span data-ttu-id="97dee-152">Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="97dee-152">Microsoft SharePoint Syntex</span></span>
-   <span data-ttu-id="97dee-153">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="97dee-153">Microsoft Teams</span></span>
-   <span data-ttu-id="97dee-154">Power Automate</span><span class="sxs-lookup"><span data-stu-id="97dee-154">Power Automate</span></span>

## <a name="create-the-solution"></a><span data-ttu-id="97dee-155">Crear la solución</span><span class="sxs-lookup"><span data-stu-id="97dee-155">Create the solution</span></span>

<span data-ttu-id="97dee-156">En las siguientes secciones se detallará cómo configurar la solución de administración de contratos.</span><span class="sxs-lookup"><span data-stu-id="97dee-156">The next sections will go into detail about how to configure your contracts management solution.</span></span> <span data-ttu-id="97dee-157">Se divide en tres pasos:</span><span class="sxs-lookup"><span data-stu-id="97dee-157">It's divided into three steps:</span></span>

- [<span data-ttu-id="97dee-158">Paso 1. Usar SharePoint Syntex para identificar archivos de contrato y extraer datos</span><span class="sxs-lookup"><span data-stu-id="97dee-158">Step 1. Use SharePoint Syntex to identify contract files and extract data</span></span>](solution-manage-contracts-step1.md)
- [<span data-ttu-id="97dee-159">Paso 2. Usar Microsoft Teams para crear el canal de administración de contratos</span><span class="sxs-lookup"><span data-stu-id="97dee-159">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)
- [<span data-ttu-id="97dee-160">Paso 3. Usar Power Automate para crear el flujo para procesar los contratos</span><span class="sxs-lookup"><span data-stu-id="97dee-160">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
