---
title: Planeación de experiencias de temas en Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo planear experiencias de temas en Microsoft 365
ms.openlocfilehash: 153937cf6bc4a12f0a27866204b2286c343ddf55
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668230"
---
# <a name="plan-topic-experiences-in-microsoft-365"></a><span data-ttu-id="f10a9-103">Planeación de experiencias de temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f10a9-103">Plan topic experiences in Microsoft 365</span></span>

<span data-ttu-id="f10a9-104">Tiene el control de cómo se experimentan los temas en su organización.</span><span class="sxs-lookup"><span data-stu-id="f10a9-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="f10a9-105">Las decisiones de planeación para las experiencias de los temas garantizan que se muestren temas de alta calidad a los usuarios y tengan los permisos adecuados para consumir y contribuir con el conocimiento.</span><span class="sxs-lookup"><span data-stu-id="f10a9-105">Your planning decisions for topic experiences ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="f10a9-106">En este artículo, analizaremos estas decisiones de planeación:</span><span class="sxs-lookup"><span data-stu-id="f10a9-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="f10a9-107">Los sitios de SharePoint que desea rastrear en busca de temas.</span><span class="sxs-lookup"><span data-stu-id="f10a9-107">Which SharePoint sites you want to crawl for topics.</span></span>
- <span data-ttu-id="f10a9-108">Qué temas, en caso de haberlos, desea excluir de las experiencias del tema</span><span class="sxs-lookup"><span data-stu-id="f10a9-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="f10a9-109">Los usuarios a los que desea que los temas sean visibles.</span><span class="sxs-lookup"><span data-stu-id="f10a9-109">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="f10a9-110">Los usuarios a los que desea conceder permisos para administrar temas en el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="f10a9-110">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="f10a9-111">Los usuarios a los que desea conceder permisos para crear o editar temas en el centro de temas.</span><span class="sxs-lookup"><span data-stu-id="f10a9-111">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="f10a9-112">El nombre que desea dar al centro de temas.</span><span class="sxs-lookup"><span data-stu-id="f10a9-112">What name you want to give your topic center.</span></span>

<span data-ttu-id="f10a9-113">La seguridad y privacidad de los datos se respetan y las experiencias del tema no conceden a los usuarios acceso adicional a los archivos a los que no tienen derechos.</span><span class="sxs-lookup"><span data-stu-id="f10a9-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="f10a9-114">También le recomendamos que lea el [tema experiencias de seguridad y privacidad](topic-experiences-security-privacy.md) como parte del proceso de planeación.</span><span class="sxs-lookup"><span data-stu-id="f10a9-114">We recommend you also read [Topic experiences security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="f10a9-115">Requirements</span><span class="sxs-lookup"><span data-stu-id="f10a9-115">Requirements</span></span>

<span data-ttu-id="f10a9-116">Debe ser administrador global o administrador de SharePoint para tener acceso al centro de administración de Microsoft 365 y configurar las experiencias de los temas.</span><span class="sxs-lookup"><span data-stu-id="f10a9-116">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up topic experiences.</span></span>

<span data-ttu-id="f10a9-117">Todos los usuarios que vayan a usar las experiencias de los temas requieren un tema de licencia de **experiencia** .</span><span class="sxs-lookup"><span data-stu-id="f10a9-117">All users who are going to use topic experiences require a **Topic Experiences** license.</span></span> <span data-ttu-id="f10a9-118">La asignación de licencias se describe en [set up topic experiencias](set-up-topic-experiences.md).</span><span class="sxs-lookup"><span data-stu-id="f10a9-118">Assigning licenses is covered in [Set up topic experiences](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="f10a9-119">Detección de temas</span><span class="sxs-lookup"><span data-stu-id="f10a9-119">Topic discovery</span></span>

<span data-ttu-id="f10a9-120">La configuración de detección de temas especifica los sitios de SharePoint que se usan como orígenes para los temas.</span><span class="sxs-lookup"><span data-stu-id="f10a9-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="f10a9-121">Puede elegir incluir todos los sitios de SharePoint, una lista específica de sitios o ningún sitio.</span><span class="sxs-lookup"><span data-stu-id="f10a9-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="f10a9-122">Le recomendamos que elija todos los sitios para que las experiencias del tema puedan detectar un gran número de temas buenos para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f10a9-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="f10a9-123">Al configurar las experiencias de los temas, puede elegir entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f10a9-123">When you set up topic experiences, you can choose from the following options:</span></span>

- <span data-ttu-id="f10a9-124">**Todos los sitios**: todos los sitios de SharePoint de la organización.</span><span class="sxs-lookup"><span data-stu-id="f10a9-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="f10a9-125">Esto incluye los sitios actuales y futuros.</span><span class="sxs-lookup"><span data-stu-id="f10a9-125">This includes current and future sites.</span></span>
- <span data-ttu-id="f10a9-126">**Todos, excepto los sitios seleccionados**: todos los sitios excepto los que usted especifique.</span><span class="sxs-lookup"><span data-stu-id="f10a9-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="f10a9-127">Los sitios creados en el futuro se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="f10a9-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="f10a9-128">**Solo sitios seleccionados**: solo los sitios que especifique.</span><span class="sxs-lookup"><span data-stu-id="f10a9-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="f10a9-129">Los sitios que se creen en el futuro no se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="f10a9-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="f10a9-130">**Sin sitios**: no incluye ningún sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f10a9-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="f10a9-131">Si elige **todos los sitios, excepto los seleccionados** o **solo los seleccionados**, puede cargar un archivo. csv con una lista de sitios.</span><span class="sxs-lookup"><span data-stu-id="f10a9-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="f10a9-132">Estas opciones son útiles si está realizando una prueba piloto y desea incluir un número limitado de sitios para iniciarse.</span><span class="sxs-lookup"><span data-stu-id="f10a9-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="f10a9-133">Puede copiar la plantilla. csv a continuación:</span><span class="sxs-lookup"><span data-stu-id="f10a9-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="f10a9-134">No se recomienda no elegir **ningún sitio** porque impide que los temas se creen o actualicen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f10a9-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="f10a9-135">Sin embargo, puede elegir esta opción si desea configurar experiencias de tema y agregar sitios más adelante.</span><span class="sxs-lookup"><span data-stu-id="f10a9-135">However, you can choose this option if you want to set up topic experiences and then add sites later.</span></span>

<span data-ttu-id="f10a9-136">Le recomendamos que cree un proceso para que los usuarios o los administradores del conocimiento soliciten sitios individuales para que se elimine de la detección de temas si es necesario en su organización.</span><span class="sxs-lookup"><span data-stu-id="f10a9-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="f10a9-137">Permisos de usuario</span><span class="sxs-lookup"><span data-stu-id="f10a9-137">User permissions</span></span>

<span data-ttu-id="f10a9-138">Los permisos de usuario que especifique determinan las personas de su organización que interactúan con los temas y lo que pueden hacer.</span><span class="sxs-lookup"><span data-stu-id="f10a9-138">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

<span data-ttu-id="f10a9-139">*Administrar temas*</span><span class="sxs-lookup"><span data-stu-id="f10a9-139">*Manage topics*</span></span>

<span data-ttu-id="f10a9-140">Los administradores de conocimientos supervisan la calidad de la información, el modo en que se han estructurado y otros procedimientos recomendados en la organización.</span><span class="sxs-lookup"><span data-stu-id="f10a9-140">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="f10a9-141">Pueden confirmar y rechazar temas.</span><span class="sxs-lookup"><span data-stu-id="f10a9-141">They can confirm and reject topics.</span></span>

<span data-ttu-id="f10a9-142">Aunque puede especificar los administradores de temas individuales, le recomendamos que cree un grupo de seguridad (o use uno existente) que contenga las personas que desea que sean responsables de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="f10a9-142">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="f10a9-143">Puede especificar este grupo de seguridad durante el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="f10a9-143">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="f10a9-144">*Creación y edición de temas*</span><span class="sxs-lookup"><span data-stu-id="f10a9-144">*Create and edit topics*</span></span>

<span data-ttu-id="f10a9-145">Los colaboradores de temas son los expertos y expertos en la materia de la organización.</span><span class="sxs-lookup"><span data-stu-id="f10a9-145">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="f10a9-146">Pueden crear y editar temas.</span><span class="sxs-lookup"><span data-stu-id="f10a9-146">They can create and edit topics.</span></span> 

<span data-ttu-id="f10a9-147">Le recomendamos que permita que todos los usuarios de la organización creen y editen temas porque la experiencia del tema funciona mejor cuando todos los usuarios pueden compartir información.</span><span class="sxs-lookup"><span data-stu-id="f10a9-147">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="f10a9-148">Si desea limitar la creación y edición de temas a personas o grupos específicos, cree un grupo de seguridad para ellos y, a continuación, especifique durante el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="f10a9-148">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="f10a9-149">Sin embargo, puede optar por no permitir que nadie contribuya con temas, pero no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="f10a9-149">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="f10a9-150">Los administradores de conocimiento seguirán pudiendo editar y crear temas.</span><span class="sxs-lookup"><span data-stu-id="f10a9-150">Knowledge managers will still be able to edit and create topics.</span></span>

<span data-ttu-id="f10a9-151">*Visores de temas*</span><span class="sxs-lookup"><span data-stu-id="f10a9-151">*Topic viewers*</span></span>

<span data-ttu-id="f10a9-152">Los visores de temas pueden ver información sobre las páginas del tema, en los resultados de la búsqueda y cuando los temas están resaltados en el contenido como las páginas de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f10a9-152">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="f10a9-153">Los usuarios solo pueden ver los temas detectados cuando tienen acceso a los archivos y las páginas en los que se detectó el tema.</span><span class="sxs-lookup"><span data-stu-id="f10a9-153">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="f10a9-154">Al configurar los visores de temas, puede elegir entre:</span><span class="sxs-lookup"><span data-stu-id="f10a9-154">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="f10a9-155">**Todos los usuarios de mi organización**</span><span class="sxs-lookup"><span data-stu-id="f10a9-155">**Everyone in my organization**</span></span>
- <span data-ttu-id="f10a9-156">**Solo personas seleccionadas o grupos de seguridad**</span><span class="sxs-lookup"><span data-stu-id="f10a9-156">**Only selected people or security groups**</span></span>
- <span data-ttu-id="f10a9-157">**No hay nadie**</span><span class="sxs-lookup"><span data-stu-id="f10a9-157">**No one**</span></span>

<span data-ttu-id="f10a9-158">Recomendamos a **todos los usuarios de mi organización**, pero si está realizando una prueba piloto, es posible que quiera elegir solo a las personas o grupos de seguridad seleccionados.</span><span class="sxs-lookup"><span data-stu-id="f10a9-158">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="f10a9-159">También puede elegir **nadie** si desea configurar experiencias de tema, pero no permitir que los usuarios vean todavía los temas.</span><span class="sxs-lookup"><span data-stu-id="f10a9-159">You can also choose **No one** if you want to set up topic experiences, but not allow people to see topics yet.</span></span> <span data-ttu-id="f10a9-160">(Los administradores de conocimiento seguirán teniendo acceso para permitirles ver los temas y la ayuda con la decisión de que las experiencias de los temas estén disponibles de forma generalizada).</span><span class="sxs-lookup"><span data-stu-id="f10a9-160">(Knowledge managers will still have access to allow them view the topics and help with the decision to make topic experiences broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="f10a9-161">Reglas de conocimiento</span><span class="sxs-lookup"><span data-stu-id="f10a9-161">Knowledge rules</span></span>

<span data-ttu-id="f10a9-162">Como administrador, puede excluir determinados temas de las experiencias de los temas.</span><span class="sxs-lookup"><span data-stu-id="f10a9-162">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="f10a9-163">Esto es útil si desea impedir que los datos confidenciales aparezcan en los temas.</span><span class="sxs-lookup"><span data-stu-id="f10a9-163">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="f10a9-164">Mientras que los administradores de conocimiento pueden excluir temas en el centro de temas, los temas excluidos por el administrador ni son visibles para los administradores de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="f10a9-164">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="f10a9-165">(Los administradores de conocimientos también pueden quitar temas del centro de temas después de la detección).</span><span class="sxs-lookup"><span data-stu-id="f10a9-165">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="f10a9-166">Si desea excluir temas en el nivel de administrador, debe agregarlos a un archivo. csv y cargar el archivo.</span><span class="sxs-lookup"><span data-stu-id="f10a9-166">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="f10a9-167">Puede hacerlo durante la instalación o posteriormente.</span><span class="sxs-lookup"><span data-stu-id="f10a9-167">You can do this during setup or later.</span></span>

<span data-ttu-id="f10a9-168">El archivo. csv debe contener los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="f10a9-168">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="f10a9-169">**Name**: escriba el nombre del tema que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="f10a9-169">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="f10a9-170">Puede realizar esto de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="f10a9-170">There are two ways to do this:</span></span>
- <span data-ttu-id="f10a9-171">**MatchType-Exact/Partial**: escriba si el nombre que ha escrito es un tipo de coincidencia *exacta* o *parcial* .</span><span class="sxs-lookup"><span data-stu-id="f10a9-171">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="f10a9-172">Coincidencia exacta: puede incluir el acrónimo o el nombre exacto (por ejemplo, *contoso* o *ATL*).</span><span class="sxs-lookup"><span data-stu-id="f10a9-172">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="f10a9-173">Coincidencia parcial: puede excluir todos los temas que contengan una palabra específica.</span><span class="sxs-lookup"><span data-stu-id="f10a9-173">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="f10a9-174">Por ejemplo, *arco* excluirá todos los temas que contengan la palabra *Arc* , como *círculo arco*, *soldadura de arco de plasma* o arco de *formación*. Tenga en cuenta que no se excluirán los temas en los que se incluya el texto como parte de una palabra, como la *arquitectura*.</span><span class="sxs-lookup"><span data-stu-id="f10a9-174">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="f10a9-175">**Significa (opcional)**: (también conocido como *expansión*) Si desea excluir un acrónimo, escriba las palabras que representa el acrónimo.</span><span class="sxs-lookup"><span data-stu-id="f10a9-175">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Excluir temas en la plantilla CSV](../media/exclude-topics-csv.png) 

<span data-ttu-id="f10a9-177">Puede copiar la plantilla CSV a continuación:</span><span class="sxs-lookup"><span data-stu-id="f10a9-177">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="f10a9-178">Administración</span><span class="sxs-lookup"><span data-stu-id="f10a9-178">Administration</span></span>

<span data-ttu-id="f10a9-179">Cuando se configuran experiencias de tema, como parte del proceso de configuración, se crea automáticamente un centro de temas.</span><span class="sxs-lookup"><span data-stu-id="f10a9-179">When you set up topic experiences, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="f10a9-180">Piense en lo que desea asignar al centro de temas y en lo que desea que sea la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="f10a9-180">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="f10a9-181">Puede establecer el nombre y la dirección URL como parte del proceso de instalación y puede cambiar el nombre (pero no la dirección URL) más adelante en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f10a9-181">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f10a9-182">Solo puede tener un centro de temas.</span><span class="sxs-lookup"><span data-stu-id="f10a9-182">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="f10a9-183">Lista de comprobación de configuración</span><span class="sxs-lookup"><span data-stu-id="f10a9-183">Setup checklist</span></span>

<span data-ttu-id="f10a9-184">Al configurar las experiencias de los temas, necesitará los siguientes elementos a medida que avanza en el Asistente de configuración:</span><span class="sxs-lookup"><span data-stu-id="f10a9-184">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="f10a9-185">Lista de sitios que se van a incluir o excluir si no se incluyen todos los sitios para la detección de temas</span><span class="sxs-lookup"><span data-stu-id="f10a9-185">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="f10a9-186">Grupo de seguridad para visores de temas si no permite que todos los usuarios vean temas</span><span class="sxs-lookup"><span data-stu-id="f10a9-186">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="f10a9-187">Grupo de seguridad para colaboradores de temas si no permite a todos los usuarios crear y editar temas</span><span class="sxs-lookup"><span data-stu-id="f10a9-187">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="f10a9-188">Grupo de seguridad para administradores de conocimiento del tema si no permite que todos los usuarios administren temas</span><span class="sxs-lookup"><span data-stu-id="f10a9-188">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="f10a9-189">Lista de temas confidenciales que se deben excluir del descubrimiento de temas</span><span class="sxs-lookup"><span data-stu-id="f10a9-189">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="f10a9-190">Un nombre para el sitio del centro de temas</span><span class="sxs-lookup"><span data-stu-id="f10a9-190">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="f10a9-191">Vea también</span><span class="sxs-lookup"><span data-stu-id="f10a9-191">See also</span></span>

[<span data-ttu-id="f10a9-192">Configurar experiencias de tema</span><span class="sxs-lookup"><span data-stu-id="f10a9-192">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="f10a9-193">Administrar la detección de temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f10a9-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="f10a9-194">Administrar la visibilidad de los temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f10a9-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="f10a9-195">Administrar los permisos de temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f10a9-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="f10a9-196">Cambiar el nombre del centro de temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f10a9-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
