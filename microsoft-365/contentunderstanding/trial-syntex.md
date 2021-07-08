---
title: Ejecutar una prueba de Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: Obtenga información sobre cómo planear y ejecutar un programa piloto de prueba para SharePoint Syntex en su organización.
ms.openlocfilehash: 2668c0c85d6b8c73d377ac9efffc7f777fc7add6
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327149"
---
# <a name="run-a-trial-of-microsoft-sharepoint-syntex"></a><span data-ttu-id="b6ddf-103">Ejecutar una prueba de Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="b6ddf-103">Run a trial of Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="b6ddf-104">En este artículo se describe cómo configurar y ejecutar un programa piloto de prueba para implementar SharePoint Syntex en la organización.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-104">This article describes how to set up and run a trial pilot program to deploy SharePoint Syntex in your organization.</span></span> <span data-ttu-id="b6ddf-105">También recomienda procedimientos recomendados para la prueba.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-105">It also recommends best practices for the trial.</span></span>

## <a name="sign-up-for-a-trial"></a><span data-ttu-id="b6ddf-106">Registrarse para una versión de prueba</span><span class="sxs-lookup"><span data-stu-id="b6ddf-106">Sign up for a trial</span></span>

<span data-ttu-id="b6ddf-107">La versión de SharePoint Syntex ofrece acceso a 300 usuarios durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-107">The trial of SharePoint Syntex gives access to 300 users for 30 days.</span></span>

> [!NOTE]
> <span data-ttu-id="b6ddf-108">Hasta 300 usuarios se incluyen en la versión de prueba para garantizar la adición automática de 1 millón de créditos de AI Builder.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-108">Up to 300 users are included in the trial to ensure the automatic addition of 1 million AI Builder credits.</span></span> <span data-ttu-id="b6ddf-109">No es necesario incluir 300 usuarios para que una prueba se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-109">You do not have to include 300 users for a trial to succeed.</span></span>

<span data-ttu-id="b6ddf-110">Puede obtener la versión de prueba de uno de los siguientes orígenes:</span><span class="sxs-lookup"><span data-stu-id="b6ddf-110">You can get the trial version from one of the following sources:</span></span>

- <span data-ttu-id="b6ddf-111">Página [SharePoint Syntex producto](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)</span><span class="sxs-lookup"><span data-stu-id="b6ddf-111">The [SharePoint Syntex product page](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)</span></span>

- <span data-ttu-id="b6ddf-112">El [Centro de administración de Microsoft 365](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b6ddf-112">The [Microsoft 365 admin center](https://admin.microsoft.com)</span></span>
    1.  <span data-ttu-id="b6ddf-113">Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b6ddf-113">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
    2.  <span data-ttu-id="b6ddf-114">Vaya a **Servicios de compra** de  >  **facturación**.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-114">Go to **Billing** > **Purchase Services**.</span></span>
    3.  <span data-ttu-id="b6ddf-115">Desplácese hacia abajo hasta la sección **Complementos**.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-115">Scroll down to the **Add-Ons** section.</span></span>
    4.  <span data-ttu-id="b6ddf-116">En el icono SharePoint Syntex, seleccione **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-116">On the SharePoint Syntex tile, select **Details**.</span></span>
    5.  <span data-ttu-id="b6ddf-117">Seleccione **Obtener prueba gratuita**.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-117">Select **Get free trial**.</span></span>
    6.  <span data-ttu-id="b6ddf-118">Para confirmar la prueba, siga los pasos del asistente restantes.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-118">To confirm the trial, follow the remaining wizard steps.</span></span>

<span data-ttu-id="b6ddf-119">Debe ser un administrador Microsoft 365 global o administrador de facturación para activar una versión de prueba.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-119">You must be a Microsoft 365 global administrator or billing administrator to activate a trial.</span></span>

### <a name="who-should-be-involved-in-a-trial"></a><span data-ttu-id="b6ddf-120">Quién debe participar en una prueba</span><span class="sxs-lookup"><span data-stu-id="b6ddf-120">Who should be involved in a trial</span></span>

|<span data-ttu-id="b6ddf-121">Rol</span><span class="sxs-lookup"><span data-stu-id="b6ddf-121">Role</span></span>  |<span data-ttu-id="b6ddf-122">Actividad</span><span class="sxs-lookup"><span data-stu-id="b6ddf-122">Activity</span></span>  |
|---------|---------|
|<span data-ttu-id="b6ddf-123">Microsoft 365 administrador global o de facturación</span><span class="sxs-lookup"><span data-stu-id="b6ddf-123">Microsoft 365 global admin or billing admin</span></span>    |     <span data-ttu-id="b6ddf-124">Activar la versión de prueba y asignar licencias</span><span class="sxs-lookup"><span data-stu-id="b6ddf-124">Activate the trial and assign licenses</span></span>    |
|<span data-ttu-id="b6ddf-125">Microsoft 365 administrador global o administrador SharePoint administrador</span><span class="sxs-lookup"><span data-stu-id="b6ddf-125">Microsoft 365 global admin or SharePoint admin</span></span>     |   <span data-ttu-id="b6ddf-126">Configurar SharePoint Syntex y crear centros de contenido</span><span class="sxs-lookup"><span data-stu-id="b6ddf-126">Configure SharePoint Syntex and create content centers</span></span>      |
|<span data-ttu-id="b6ddf-127">Usuarios empresariales</span><span class="sxs-lookup"><span data-stu-id="b6ddf-127">Business users</span></span>     |    <span data-ttu-id="b6ddf-128">Creación y pruebas de modelos</span><span class="sxs-lookup"><span data-stu-id="b6ddf-128">Model building and testing</span></span>     |

### <a name="before-you-activate-a-trial"></a><span data-ttu-id="b6ddf-129">Antes de activar una versión de prueba</span><span class="sxs-lookup"><span data-stu-id="b6ddf-129">Before you activate a trial</span></span>

<span data-ttu-id="b6ddf-130">Para planear correctamente una SharePoint Syntex prueba, tenga en cuenta los siguientes factores:</span><span class="sxs-lookup"><span data-stu-id="b6ddf-130">To successfully plan a SharePoint Syntex trial, consider the following factors:</span></span>

- <span data-ttu-id="b6ddf-131">Las pruebas más significativas se completan en escenarios y datos del "mundo real".</span><span class="sxs-lookup"><span data-stu-id="b6ddf-131">The most meaningful testing is completed on “real world” scenarios and data.</span></span>
- <span data-ttu-id="b6ddf-132">Solo puede activar una versión de SharePoint Syntex una vez por inquilino.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-132">You can only activate a SharePoint Syntex trial once per tenant.</span></span>

<span data-ttu-id="b6ddf-133">Un inquilino de prueba o demostración puede usarse como una "ejecución en seco" para recorrer los pasos de activación y los controles administrativos.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-133">A test or demo tenant can be used as a “dry run” to walk through the activation steps and administrative controls.</span></span> <span data-ttu-id="b6ddf-134">Pero probablemente sea mejor evaluar la creación de modelos en un inquilino de producción.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-134">But it’s probably best to evaluate model building on a production tenant.</span></span>

<span data-ttu-id="b6ddf-135">Para maximizar el valor de una prueba en un inquilino de producción, la planeación y la participación empresarial son esenciales.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-135">To maximize the value of a trial on a production tenant, planning and business engagement are essential.</span></span> <span data-ttu-id="b6ddf-136">Debe participar en una o más áreas de negocio para identificar de tres a seis casos de uso que podrían ser posiblemente abordados por SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-136">You should engage one or more business areas to identify three-to-six use cases that could potentially be addressed by SharePoint Syntex.</span></span> <span data-ttu-id="b6ddf-137">Estos casos de uso deben:</span><span class="sxs-lookup"><span data-stu-id="b6ddf-137">These use cases should:</span></span>

- <span data-ttu-id="b6ddf-138">Incluya escenarios que podrían resolverse mediante el modelo de procesamiento de formularios o de comprensión de documentos.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-138">Include scenarios that could be solved by either the forms processing or document understanding model.</span></span>
- <span data-ttu-id="b6ddf-139">Tener una comprensión clara del propósito de los metadatos extraídos; por ejemplo, ver el formato o la automatización mediante Power Automate.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-139">Have a clear understanding of the purpose for any extracted metadata; for example, view formatting or automation by using Power Automate.</span></span> <span data-ttu-id="b6ddf-140">Aunque SharePoint Syntex está centrado en clasificar documentos y extraer metadatos, el valor que se va a cuantificar es lo que habilitan estos metadatos.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-140">While SharePoint Syntex is focused on classifying documents and extracting metadata, the value to quantify is what this metadata enables.</span></span>
- <span data-ttu-id="b6ddf-141">Se basa en un conjunto definido de datos; por ejemplo, sitios SharePoint o bibliotecas específicas.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-141">Be based on a defined set of data; for example, specific SharePoint sites or libraries.</span></span> <span data-ttu-id="b6ddf-142">Una idea errónea común de SharePoint Syntex es que los modelos de propósito general se pueden aplicar en todo el contenido de la organización.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-142">A common misconception of SharePoint Syntex is that general purpose models can be applied across all organization content.</span></span> <span data-ttu-id="b6ddf-143">Una vista más precisa es que los modelos se han creado para ayudar a resolver problemas empresariales específicos en ubicaciones dirigidas.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-143">A more accurate view is that models are built to help solve specific business problems in targeted locations.</span></span>

<span data-ttu-id="b6ddf-144">Es posible que todos estos casos de uso no sean adecuados para SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-144">All of these use cases might not be a good fit for SharePoint Syntex.</span></span> <span data-ttu-id="b6ddf-145">El objetivo de una prueba de calidad no es probar que SharePoint Syntex se ajuste a todos los escenarios.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-145">The goal of a quality trial isn't to prove that SharePoint Syntex will fit all the scenarios.</span></span> <span data-ttu-id="b6ddf-146">En su lugar, la prueba debe ayudarle a comprender mejor el valor del producto.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-146">Instead, the trial should help you better understand the value of product.</span></span>

<span data-ttu-id="b6ddf-147">Para cada uno de los casos de uso planeados, identifique a los usuarios que son expertos en la materia en el proceso o contenido relacionados.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-147">For each of the planned use cases, identify users who are subject matter experts in the related content or process.</span></span> <span data-ttu-id="b6ddf-148">La creación de SharePoint Syntex se centra en expertos de dominio en el contenido, en lugar de en profesionales de TI o recursos para desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-148">The creation of SharePoint Syntex models is focused on domain experts in the content, rather than on IT professionals or developer resources.</span></span>

## <a name="activate-a-trial"></a><span data-ttu-id="b6ddf-149">Activar una versión de prueba</span><span class="sxs-lookup"><span data-stu-id="b6ddf-149">Activate a trial</span></span>

<span data-ttu-id="b6ddf-150">Al iniciar una prueba, debe:</span><span class="sxs-lookup"><span data-stu-id="b6ddf-150">When you initiate a trial, you need to:</span></span>

- <span data-ttu-id="b6ddf-151">Asignar licencias a los usuarios relevantes.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-151">Assign licenses to the relevant users.</span></span>
- <span data-ttu-id="b6ddf-152">Realice [una configuración adicional de SharePoint Syntex](set-up-content-understanding.md).</span><span class="sxs-lookup"><span data-stu-id="b6ddf-152">Perform [additional setup of SharePoint Syntex](set-up-content-understanding.md).</span></span>
    - <span data-ttu-id="b6ddf-153">Es posible que desee crear [centros de contenido adicionales](create-a-content-center.md).</span><span class="sxs-lookup"><span data-stu-id="b6ddf-153">You might want to [create additional content centers](create-a-content-center.md).</span></span>

<span data-ttu-id="b6ddf-154">Después de activar la prueba, puede crear modelos y procesar archivos.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-154">After the trial is activated, you can create models and process files.</span></span> <span data-ttu-id="b6ddf-155">Vea [las instrucciones para la creación de modelos](create-a-content-center.md).</span><span class="sxs-lookup"><span data-stu-id="b6ddf-155">See [guidance for model creation](create-a-content-center.md).</span></span>

## <a name="during-a-trial"></a><span data-ttu-id="b6ddf-156">Durante una prueba</span><span class="sxs-lookup"><span data-stu-id="b6ddf-156">During a trial</span></span>

<span data-ttu-id="b6ddf-157">Los períodos de prueba son limitados, por lo que es mejor centrarse inicialmente en si los SharePoint Syntex pueden clasificar documentos y extraer metadatos para los casos de uso definidos.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-157">Trial periods are limited, so it’s best to focus initially on whether SharePoint Syntex models can classify documents and extract metadata for the defined use cases.</span></span> <span data-ttu-id="b6ddf-158">Una vez terminado el período de prueba, puede evaluar cómo se pueden aprovechar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-158">After the trial period is over, you can evaluate how the metadata can be exploited.</span></span>

## <a name="after-a-trial"></a><span data-ttu-id="b6ddf-159">Después de una prueba</span><span class="sxs-lookup"><span data-stu-id="b6ddf-159">After a trial</span></span>

<span data-ttu-id="b6ddf-160">En función del resultado de la prueba, puede decidir si procede al uso de producción de SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-160">Based on the outcome of the trial, you can decide whether to proceed to production use of SharePoint Syntex.</span></span>

### <a name="proceed-to-production-use"></a><span data-ttu-id="b6ddf-161">Continuar con el uso de producción</span><span class="sxs-lookup"><span data-stu-id="b6ddf-161">Proceed to production use</span></span>

<span data-ttu-id="b6ddf-162">Para garantizar la continuidad del servicio, debe comprar el número necesario de licencias y asignar esas licencias a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-162">To ensure continuity of service, you need to purchase the required number of licenses and assign those licenses to users.</span></span> <span data-ttu-id="b6ddf-163">Los usuarios de prueba que no tienen una licencia completa al final del período de prueba no podrán usar completamente SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-163">Trial users who don’t have a full license at the end of the trial period won’t be able to fully utilize SharePoint Syntex.</span></span>

<span data-ttu-id="b6ddf-164">Es posible que tenga que calcular el uso previsto del procesamiento de formularios y planear la cantidad esperada de créditos de AI Builder.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-164">You might have to estimate your projected use of forms processing and plan for the expected amount of AI Builder credits.</span></span> <span data-ttu-id="b6ddf-165">Para obtener ayuda, [vea Estimate the AI Builder capacity that's right for you](https://powerapps.microsoft.com/ai-builder-calculator/).</span><span class="sxs-lookup"><span data-stu-id="b6ddf-165">For help, see [Estimate the AI Builder capacity that’s right for you](https://powerapps.microsoft.com/ai-builder-calculator/).</span></span>

### <a name="dont-proceed-to-production-use"></a><span data-ttu-id="b6ddf-166">No continuar con el uso de producción</span><span class="sxs-lookup"><span data-stu-id="b6ddf-166">Don't proceed to production use</span></span>

<span data-ttu-id="b6ddf-167">Si no compra licencias después de la versión de prueba:</span><span class="sxs-lookup"><span data-stu-id="b6ddf-167">If you don’t purchase licenses following the trial:</span></span>

- <span data-ttu-id="b6ddf-168">No podrá crear nuevos modelos.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-168">You won’t be able to create new models.</span></span>
- <span data-ttu-id="b6ddf-169">Las bibliotecas que estaban ejecutando modelos ya no clasificarán automáticamente archivos ni extraerán modelos.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-169">Libraries that were running models will no longer automatically classify files or extract models.</span></span>
- <span data-ttu-id="b6ddf-170">Los archivos clasificados previamente o los metadatos extraídos no se verán afectados.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-170">Any previously classified files or extracted metadata won’t be affected.</span></span> 
- <span data-ttu-id="b6ddf-171">Los centros de contenido y los modelos de comprensión de documentos no se eliminarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-171">Content centers and any document-understanding models won’t be automatically deleted.</span></span> <span data-ttu-id="b6ddf-172">Estos permanecerán disponibles para su uso si decide comprar licencias en el futuro.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-172">These will remain available for use if you decide to purchase licenses in the future.</span></span>
- <span data-ttu-id="b6ddf-173">Los modelos de procesamiento de formularios se almacenarán en la instancia de Common Data Services (CDS) del entorno predeterminado de Power Platform.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-173">Forms-processing models will be stored in the Common Data Services (CDS) instance of the default Power Platform environment.</span></span> <span data-ttu-id="b6ddf-174">Se podrían usar con licencias futuras para SharePoint Syntex o con funcionalidades de AI Builder en power platform.</span><span class="sxs-lookup"><span data-stu-id="b6ddf-174">These could be used with future licensing for SharePoint Syntex or with AI Builder capabilities in the Power Platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6ddf-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6ddf-175">See also</span></span>

[<span data-ttu-id="b6ddf-176">Adopción SharePoint Syntex Microsoft: Introducción</span><span class="sxs-lookup"><span data-stu-id="b6ddf-176">Microsoft SharePoint Syntex adoption: Get started</span></span>](adoption-getstarted.md)
