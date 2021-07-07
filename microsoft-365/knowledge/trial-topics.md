---
title: Ejecutar una versión de prueba de Temas de Microsoft Viva
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: ''
search.appverid: ''
localization_priority: Normal
description: Obtenga información sobre cómo planear y ejecutar un programa piloto de prueba para temas de Microsoft Viva en su organización.
ms.openlocfilehash: 128e82e7664a76baa55d37e983319c9f344624fd
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327146"
---
# <a name="run-a-trial-of-microsoft-viva-topics"></a><span data-ttu-id="bc1d5-103">Ejecutar una versión de prueba de Temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="bc1d5-103">Run a trial of Microsoft Viva Topics</span></span>

<span data-ttu-id="bc1d5-104">En este artículo se describe cómo configurar y ejecutar un programa piloto de prueba para implementar Viva Topics en su organización.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-104">This article describes how to set up and run a trial pilot program to deploy Viva Topics to your organization.</span></span> <span data-ttu-id="bc1d5-105">En este artículo también se recomiendan los procedimientos recomendados para la prueba.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-105">This article also recommends best practices for the trial.</span></span>

## <a name="sign-up-for-a-trial"></a><span data-ttu-id="bc1d5-106">Registrarse para una versión de prueba</span><span class="sxs-lookup"><span data-stu-id="bc1d5-106">Sign up for a trial</span></span>

<span data-ttu-id="bc1d5-107">Las pruebas están disponibles públicamente en uno de los siguientes orígenes.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-107">Trials are publicly available from one of the following sources.</span></span> <span data-ttu-id="bc1d5-108">Estas pruebas ofrecen a 25 usuarios acceso a Temas de Viva durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-108">These trials offer 25 users access to Viva Topics for 30 days.</span></span>

- <span data-ttu-id="bc1d5-109">Página [del producto Temas de Viva](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)</span><span class="sxs-lookup"><span data-stu-id="bc1d5-109">The [Viva Topics product page](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)</span></span>

- <span data-ttu-id="bc1d5-110">El [Centro de administración de Microsoft 365](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="bc1d5-110">The [Microsoft 365 admin center](https://admin.microsoft.com)</span></span>
    1.  <span data-ttu-id="bc1d5-111">Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="bc1d5-111">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
    2.  <span data-ttu-id="bc1d5-112">Vaya a **Servicios de compra** de  >  **facturación**.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-112">Go to **Billing** > **Purchase Services**.</span></span>
    3.  <span data-ttu-id="bc1d5-113">Desplácese hacia abajo hasta la sección **Complementos**.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-113">Scroll down to the **Add-Ons** section.</span></span>
    4.  <span data-ttu-id="bc1d5-114">En el **icono Experiencias del** tema, seleccione **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-114">On the **Topic Experiences** tile, select **Details**.</span></span>
    5.  <span data-ttu-id="bc1d5-115">Seleccione **Obtener prueba gratuita**.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-115">Select **Get free trial**.</span></span>
    6.  <span data-ttu-id="bc1d5-116">Siga los pasos del asistente restantes para confirmar la prueba.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-116">Follow the remaining wizard steps to confirm the trial.</span></span>

<span data-ttu-id="bc1d5-117">Debe ser un administrador Microsoft 365 global o administrador de facturación para activar una versión de prueba.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-117">You must be a Microsoft 365 global administrator or billing administrator to activate a trial.</span></span>

> [!NOTE]
> <span data-ttu-id="bc1d5-118">Las pruebas públicas solo se pueden agregar una vez para cada Microsoft 365 inquilino.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-118">Public trials can only be added once for each Microsoft 365 tenant.</span></span>

### <a name="who-should-be-involved-in-a-trial"></a><span data-ttu-id="bc1d5-119">Quién debe participar en una prueba</span><span class="sxs-lookup"><span data-stu-id="bc1d5-119">Who should be involved in a trial</span></span>

|<span data-ttu-id="bc1d5-120">Rol</span><span class="sxs-lookup"><span data-stu-id="bc1d5-120">Role</span></span>  |<span data-ttu-id="bc1d5-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="bc1d5-121">Activity</span></span>  |
|---------|---------|
|<span data-ttu-id="bc1d5-122">Microsoft 365 administrador global o de facturación</span><span class="sxs-lookup"><span data-stu-id="bc1d5-122">Microsoft 365 global admin or billing admin</span></span>  |   <span data-ttu-id="bc1d5-123">Activar la versión de prueba y asignar licencias</span><span class="sxs-lookup"><span data-stu-id="bc1d5-123">Activate the trial and assign licenses</span></span>      |
|<span data-ttu-id="bc1d5-124">Microsoft 365 administrador global o administrador SharePoint administrador</span><span class="sxs-lookup"><span data-stu-id="bc1d5-124">Microsoft 365 global admin or SharePoint admin</span></span>    |       <span data-ttu-id="bc1d5-125">Configurar Temas de Viva y crear centros de temas</span><span class="sxs-lookup"><span data-stu-id="bc1d5-125">Configure  Viva Topics and create topic centers</span></span>  |
|<span data-ttu-id="bc1d5-126">Usuario empresarial</span><span class="sxs-lookup"><span data-stu-id="bc1d5-126">Business user</span></span>     |   <span data-ttu-id="bc1d5-127">Realizar roles de administrador de conocimientos, colaborador de temas y consumidor de temas</span><span class="sxs-lookup"><span data-stu-id="bc1d5-127">Perform knowledge manager, topic contributor, and topic consumer roles</span></span>      |

### <a name="before-you-activate-a-trial"></a><span data-ttu-id="bc1d5-128">Antes de activar una versión de prueba</span><span class="sxs-lookup"><span data-stu-id="bc1d5-128">Before you activate a trial</span></span>

<span data-ttu-id="bc1d5-129">La planeación es esencial para una prueba eficaz de Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-129">Planning is essential for an effective trial of Viva Topics.</span></span> <span data-ttu-id="bc1d5-130">El período de prueba es limitado y debe incluir la detección de temas y la exploración de experiencias de calidad, administración y usuario final.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-130">The trial period is limited and must include topic discovery and exploring topic quality, management, and end-user experiences.</span></span>

#### <a name="discovery"></a><span data-ttu-id="bc1d5-131">Descubrimiento</span><span class="sxs-lookup"><span data-stu-id="bc1d5-131">Discovery</span></span>

<span data-ttu-id="bc1d5-132">Hay dos opciones de estrategia de alto nivel para la configuración de la detección de temas durante una prueba:</span><span class="sxs-lookup"><span data-stu-id="bc1d5-132">There are two high-level strategy options for configuration of topic discovery during a trial:</span></span>

- <span data-ttu-id="bc1d5-133">Indexe todo o la mayor parte de SharePoint contenido en línea.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-133">Index all or most of your SharePoint Online content.</span></span>
   - <span data-ttu-id="bc1d5-134">Los inquilinos grandes pueden tardar hasta dos semanas en indizar por completo.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-134">Large tenants can take up to two weeks to fully index.</span></span> <span data-ttu-id="bc1d5-135">Aunque los temas se generarán de forma incremental durante este período, la indización completa podría consumir hasta la mitad del período de prueba.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-135">While topics will be generated incrementally throughout this period, full indexing could consume up to half the trial period.</span></span>
   - <span data-ttu-id="bc1d5-136">Para los inquilinos con un volumen de datos significativo, esta opción puede producir un gran número de temas, quizás decenas de miles.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-136">For tenants with a significant volume of data, this option can produce a very large number of topics, perhaps tens of thousands.</span></span>

- <span data-ttu-id="bc1d5-137">Identifique un subconjunto de los SharePoint web para la indización.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-137">Identify a subset of your SharePoint sites for indexing.</span></span>

<span data-ttu-id="bc1d5-138">La elección de estas estrategias es un equilibrio de los dos factores siguientes:</span><span class="sxs-lookup"><span data-stu-id="bc1d5-138">The choice of these strategies is a balance of the following two factors:</span></span>

- <span data-ttu-id="bc1d5-139">Tener suficientes datos para generar temas significativos.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-139">Having enough data to generate meaningful topics.</span></span> <span data-ttu-id="bc1d5-140">La inteligencia artificial de Viva Topics está ajustada para funcionar en conjuntos de datos grandes, idealmente los que tienen más de 10 000 documentos.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-140">The AI in Viva Topics is tuned to work on large datasets, ideally ones that have more than 10,000 documents.</span></span>
- <span data-ttu-id="bc1d5-141">No generar tantos temas durante el período de prueba que evaluarlos durante el período de tiempo disponible es abrumador.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-141">Not generating so many topics during the trial period that evaluating them during the available time period is overwhelming.</span></span>

<span data-ttu-id="bc1d5-142">Para la mayoría de las organizaciones, la segunda estrategia produce el mejor resultado.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-142">For most organizations, the second strategy produces the best outcome.</span></span>

> [!NOTE]
> <span data-ttu-id="bc1d5-143">Debido al número de documentos requeridos por la IA, se recomienda ejecutar pruebas de Viva Topics en un inquilino de producción.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-143">Due to the number of documents required by the AI, we recommend that you run Viva Topics trials on a production tenant.</span></span> <span data-ttu-id="bc1d5-144">No hay ningún impacto en el rendimiento del inquilino durante este período.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-144">There’s no impact on the performance of the tenant during this period.</span></span> <span data-ttu-id="bc1d5-145">Solo los usuarios que tienen una licencia de prueba pueden acceder a las experiencias de usuario de Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-145">Only users who have a trial license can access Viva Topics user experiences.</span></span>

#### <a name="roles"></a><span data-ttu-id="bc1d5-146">Funciones</span><span class="sxs-lookup"><span data-stu-id="bc1d5-146">Roles</span></span>

<span data-ttu-id="bc1d5-147">Durante la prueba, hay tres roles que deben estar activos, que se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-147">During the trial, there are three roles that must be active, which are described in the following table.</span></span>

|<span data-ttu-id="bc1d5-148">Rol</span><span class="sxs-lookup"><span data-stu-id="bc1d5-148">Role</span></span>  |<span data-ttu-id="bc1d5-149">Actividad</span><span class="sxs-lookup"><span data-stu-id="bc1d5-149">Activity</span></span>  |
|---------|---------|
|<span data-ttu-id="bc1d5-150">Gerente de información</span><span class="sxs-lookup"><span data-stu-id="bc1d5-150">Knowledge manager</span></span>     |   <span data-ttu-id="bc1d5-151">Controlar las fases del ciclo de vida de los temas; confirmar y quitar temas; actuar como administrador de la comunidad para colaboradores de temas</span><span class="sxs-lookup"><span data-stu-id="bc1d5-151">Control the lifecycle stages of topics; confirm and remove topics; act as a community manager for topic contributors</span></span>      |
|<span data-ttu-id="bc1d5-152">Colaborador de tema</span><span class="sxs-lookup"><span data-stu-id="bc1d5-152">Topic contributor</span></span>    |      <span data-ttu-id="bc1d5-153">Expertos en la materia del contenido, que pueden:</span><span class="sxs-lookup"><span data-stu-id="bc1d5-153">Content subject matter experts, who can:</span></span><br> <span data-ttu-id="bc1d5-154">Revisar temas para evaluar la calidad del contenido definido por AI</span><span class="sxs-lookup"><span data-stu-id="bc1d5-154">Review topics to evaluate the quality of AI-defined content</span></span><br><span data-ttu-id="bc1d5-155">Curación de temas detectados con contenido adicional</span><span class="sxs-lookup"><span data-stu-id="bc1d5-155">Curate discovered topics with additional content</span></span><br><span data-ttu-id="bc1d5-156">Crear temas adicionales que no fueron detectados por AI</span><span class="sxs-lookup"><span data-stu-id="bc1d5-156">Create additional topics that weren’t discovered by AI</span></span>   |
|<span data-ttu-id="bc1d5-157">Consumidor de temas</span><span class="sxs-lookup"><span data-stu-id="bc1d5-157">Topic consumer</span></span>    |     <span data-ttu-id="bc1d5-158">Consumir temas a través de los resaltados de página y la búsqueda</span><span class="sxs-lookup"><span data-stu-id="bc1d5-158">Consume topics through page highlights and search</span></span><br><span data-ttu-id="bc1d5-159">Proporcionar comentarios sobre el valor de los temas presentados</span><span class="sxs-lookup"><span data-stu-id="bc1d5-159">Provide feedback on the value of the topics presented</span></span>    |

#### <a name="expected-topics"></a><span data-ttu-id="bc1d5-160">Temas esperados</span><span class="sxs-lookup"><span data-stu-id="bc1d5-160">Expected topics</span></span>

<span data-ttu-id="bc1d5-161">Puede ser útil documentar los temas que espera que genere la IA, incluso si esto se basa solo en suposiciones.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-161">It can be useful to document the topics you expect to be generated by the AI, even if this is based only on assumptions.</span></span> <span data-ttu-id="bc1d5-162">Esta tarea se completa más fácilmente al indizar un subconjunto definido de los sitios SharePoint para los que las pymes se pueden identificar fácilmente.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-162">This task is most easily completed when you index a defined subset of your SharePoint sites for which SMEs can be easily identified.</span></span>

<span data-ttu-id="bc1d5-163">Tener una lista documentada le ayudará a:</span><span class="sxs-lookup"><span data-stu-id="bc1d5-163">Having a documented list will help you to:</span></span>

- <span data-ttu-id="bc1d5-164">Revise la lista de temas generados por IA, que puede ser mayor de lo esperado.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-164">Review the list of AI-generated topics, which might be larger than you expect.</span></span>
- <span data-ttu-id="bc1d5-165">Conozca los temas que puede que necesite crear manualmente o que son prioridades para la curación.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-165">Know the topics you might need to manually create or that are priorities for curation.</span></span>

<span data-ttu-id="bc1d5-166">Siempre habrá una necesidad de una mezcla de temas definidos por la IA y creados por humanos en una implementación o prueba correcta de Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-166">There will always be a need for a mixture of AI-defined and human-created topics in a successful deployment or trial of Viva Topics.</span></span>

## <a name="activate-a-trial"></a><span data-ttu-id="bc1d5-167">Activar una versión de prueba</span><span class="sxs-lookup"><span data-stu-id="bc1d5-167">Activate a trial</span></span>

<span data-ttu-id="bc1d5-168">Al iniciar una prueba, debe:</span><span class="sxs-lookup"><span data-stu-id="bc1d5-168">When you initiate a trial, you need to:</span></span>

- <span data-ttu-id="bc1d5-169">Asignar licencias a los usuarios relevantes.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-169">Assign licenses to the relevant users.</span></span>
- <span data-ttu-id="bc1d5-170">Realice [una configuración adicional](set-up-topic-experiences.md) de Temas de Viva.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-170">Perform [additional setup](set-up-topic-experiences.md) of Viva Topics.</span></span>

<span data-ttu-id="bc1d5-171">Cuando se activa la prueba, comienza el proceso de detección de temas.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-171">When the trial is activated, the topic discovery process begins.</span></span>

## <a name="during-a-trial"></a><span data-ttu-id="bc1d5-172">Durante una prueba</span><span class="sxs-lookup"><span data-stu-id="bc1d5-172">During a trial</span></span>

<span data-ttu-id="bc1d5-173">El período de prueba debe usarse para evaluar los siguientes componentes de Viva Topics:</span><span class="sxs-lookup"><span data-stu-id="bc1d5-173">The trial period should be used to evaluate the following components of Viva Topics:</span></span>

- <span data-ttu-id="bc1d5-174">Los temas y el contenido del tema sugeridos por AI</span><span class="sxs-lookup"><span data-stu-id="bc1d5-174">The AI-suggested topics and topic content</span></span>
- <span data-ttu-id="bc1d5-175">Las experiencias del usuario final, la presentación de tarjetas de temas en páginas SharePoint y en Búsqueda de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bc1d5-175">The end-user experiences, surfacing topic cards on modern SharePoint pages and in Microsoft Search</span></span>

<span data-ttu-id="bc1d5-176">Ten en cuenta los siguientes factores:</span><span class="sxs-lookup"><span data-stu-id="bc1d5-176">Consider these factors:</span></span>

- <span data-ttu-id="bc1d5-177">Para que Viva Topics proporcione el valor máximo, el contenido de los temas debe ser una combinación de contenido definido por la IA y contenido de curación humana.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-177">For Viva Topics to deliver the maximum value, the content in topics needs to be a combination of AI-defined content and human-curated content.</span></span>
- <span data-ttu-id="bc1d5-178">Todas las experiencias de usuario están "recortadas por permisos" (incluida la vista del administrador de conocimientos en la **página Administrar temas).**</span><span class="sxs-lookup"><span data-stu-id="bc1d5-178">All user experiences are “permission trimmed” (including the knowledge manager’s view on the **Manage topics** page).</span></span> <span data-ttu-id="bc1d5-179">Los usuarios solo verán un tema si tienen permisos para ver algunos de los recursos que se usaron para generar el tema.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-179">Users will only see a topic if they have permissions to view some of the resources that were used to generate the topic.</span></span> <span data-ttu-id="bc1d5-180">Esto significa que los diferentes usuarios pueden ver contenido diferente en la misma página de tema.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-180">This means that different users might see different content on the same topic page.</span></span>
- <span data-ttu-id="bc1d5-181">Los usuarios pueden ver varios temas con el mismo nombre en la **página Administrar temas.**</span><span class="sxs-lookup"><span data-stu-id="bc1d5-181">Users might see multiple topics that have the same name in the **Manage topics** page.</span></span> <span data-ttu-id="bc1d5-182">Estos temas no son necesariamente duplicados, pero pueden deberse a un solo término que se usa en varios contextos de los datos, como un nombre de código de proyecto que usan dos proyectos distintos.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-182">These topics aren't necessarily duplicates but might be because of a single term that’s used in multiple contexts in the data, such as a project code name that’s used by two distinct projects.</span></span>

## <a name="after-a-trial"></a><span data-ttu-id="bc1d5-183">Después de una prueba</span><span class="sxs-lookup"><span data-stu-id="bc1d5-183">After a trial</span></span>

<span data-ttu-id="bc1d5-184">En función del resultado de la prueba, puede decidir si continúa con el uso en producción de Temas de Viva.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-184">Based on the outcome of the trial, you can decide whether to proceed to production use of Viva Topics.</span></span>

### <a name="proceed-to-production-use"></a><span data-ttu-id="bc1d5-185">Continuar con el uso de producción</span><span class="sxs-lookup"><span data-stu-id="bc1d5-185">Proceed to production use</span></span>

<span data-ttu-id="bc1d5-186">Para garantizar la continuidad del servicio, debe comprar el número necesario de licencias y asignar esas licencias a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-186">To ensure continuity of service, you must purchase the required number of licenses and assign those licenses to users.</span></span> <span data-ttu-id="bc1d5-187">Los usuarios de prueba que no tienen una licencia completa al final del período de prueba no podrán acceder a ninguna experiencia de Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-187">Trial users who don’t have a full license at the end of the trial period won’t be able to access any Viva Topics experiences.</span></span>

### <a name="dont-proceed-to-production-use"></a><span data-ttu-id="bc1d5-188">No continuar con el uso de producción</span><span class="sxs-lookup"><span data-stu-id="bc1d5-188">Don’t proceed to production use</span></span>

<span data-ttu-id="bc1d5-189">Si no compra licencias después de la versión de prueba:</span><span class="sxs-lookup"><span data-stu-id="bc1d5-189">If you don’t purchase licenses following the trial:</span></span>

- <span data-ttu-id="bc1d5-190">La detección de temas se detendrá.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-190">Topic discovery will stop.</span></span>
- <span data-ttu-id="bc1d5-191">Los usuarios ya no verán las tarjetas o los aspectos destacados del tema.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-191">Users will no longer see topic highlights or cards.</span></span>
- <span data-ttu-id="bc1d5-192">El centro de temas no se eliminará, pero los temas sugeridos y las experiencias de administración de temas no estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-192">The topic center won’t be deleted, but the suggested topics and manage topics experiences won’t be available.</span></span>
- <span data-ttu-id="bc1d5-193">Se perderán los temas definidos por IA.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-193">Any AI-defined topics will be lost.</span></span>
- <span data-ttu-id="bc1d5-194">Los temas que haya editado un colaborador de temas permanecerán en la biblioteca de páginas del centro de temas.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-194">Topics that have been edited by a topic contributor will remain in the topic center pages library.</span></span> <span data-ttu-id="bc1d5-195">Solo el contenido proporcionado manualmente permanecerá en estas páginas, no cualquier contenido sugerido por AI.</span><span class="sxs-lookup"><span data-stu-id="bc1d5-195">Only the manually provided content will remain on these pages, not any AI-suggested content.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc1d5-196">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc1d5-196">See also</span></span>

[<span data-ttu-id="bc1d5-197">Introducción a la adopción de temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="bc1d5-197">Get started driving adoption of Microsoft Viva Topics</span></span>](topics-adoption-getstarted.md)

