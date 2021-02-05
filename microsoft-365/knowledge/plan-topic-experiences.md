---
title: Planeación de temas de Microsoft Viva
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Obtenga información sobre cómo planear los temas de Planeación de Microsoft Viva
ms.openlocfilehash: 65983f342b3277d33c7bfeb21d8481b1d3d5e817
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107959"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="fd78c-103">Planeación de temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="fd78c-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="fd78c-104">Tiene el control de la experiencia de los temas en su organización.</span><span class="sxs-lookup"><span data-stu-id="fd78c-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="fd78c-105">Las decisiones de planeación para temas garantizan que los temas de alta calidad se muestran a los usuarios y que tienen los permisos adecuados para consumir y aportar conocimientos.</span><span class="sxs-lookup"><span data-stu-id="fd78c-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="fd78c-106">En este artículo analizaremos estas decisiones de planeación:</span><span class="sxs-lookup"><span data-stu-id="fd78c-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="fd78c-107">Los sitios de SharePoint que desea rastrear para obtener temas</span><span class="sxs-lookup"><span data-stu-id="fd78c-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="fd78c-108">Qué temas, si los hay, que desea excluir de las experiencias de tema</span><span class="sxs-lookup"><span data-stu-id="fd78c-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="fd78c-109">Qué usuarios desea que los temas sean visibles para</span><span class="sxs-lookup"><span data-stu-id="fd78c-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="fd78c-110">Qué usuarios desea conceder permisos para administrar temas en el centro de temas</span><span class="sxs-lookup"><span data-stu-id="fd78c-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="fd78c-111">Qué usuarios desea conceder permisos para crear o editar temas en el centro de temas</span><span class="sxs-lookup"><span data-stu-id="fd78c-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="fd78c-112">Qué nombre desea dar al centro de temas</span><span class="sxs-lookup"><span data-stu-id="fd78c-112">What name you want to give your topic center</span></span>

<span data-ttu-id="fd78c-113">Se respeta la seguridad y privacidad de los datos, y las experiencias de tema no conceden a los usuarios acceso adicional a los archivos a los que no tienen derechos.</span><span class="sxs-lookup"><span data-stu-id="fd78c-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="fd78c-114">Le recomendamos que lea también la seguridad y privacidad de [Microsoft Viva Topics](topic-experiences-security-privacy.md) como parte de su proceso de planeación.</span><span class="sxs-lookup"><span data-stu-id="fd78c-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="fd78c-115">Requirements</span><span class="sxs-lookup"><span data-stu-id="fd78c-115">Requirements</span></span>

<span data-ttu-id="fd78c-116">Debe ser administrador global o administrador de SharePoint para tener acceso al Centro de administración de Microsoft 365 y configurar temas.</span><span class="sxs-lookup"><span data-stu-id="fd78c-116">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="fd78c-117">Todos los usuarios que van a usar Temas requieren una licencia **de Experiencias de** tema.</span><span class="sxs-lookup"><span data-stu-id="fd78c-117">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="fd78c-118">La asignación de licencias se trata [en Configurar temas de Microsoft Viva](set-up-topic-experiences.md).</span><span class="sxs-lookup"><span data-stu-id="fd78c-118">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="fd78c-119">Detección de temas</span><span class="sxs-lookup"><span data-stu-id="fd78c-119">Topic discovery</span></span>

<span data-ttu-id="fd78c-120">La configuración de detección de temas especifica qué sitios de SharePoint se usan como orígenes para los temas.</span><span class="sxs-lookup"><span data-stu-id="fd78c-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="fd78c-121">Puede elegir incluir todos los sitios de SharePoint, una lista específica de sitios o ningún sitio.</span><span class="sxs-lookup"><span data-stu-id="fd78c-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="fd78c-122">Se recomienda elegir todos los sitios para que las experiencias de tema puedan detectar una gran cantidad de temas buenos para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="fd78c-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="fd78c-123">Al configurar Temas, puede elegir entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="fd78c-123">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="fd78c-124">**Todos los sitios:** todos los sitios de SharePoint de la organización.</span><span class="sxs-lookup"><span data-stu-id="fd78c-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="fd78c-125">Esto incluye los sitios actuales y futuros.</span><span class="sxs-lookup"><span data-stu-id="fd78c-125">This includes current and future sites.</span></span>
- <span data-ttu-id="fd78c-126">**Todos, excepto los sitios seleccionados:** todos los sitios excepto los que especifique.</span><span class="sxs-lookup"><span data-stu-id="fd78c-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="fd78c-127">Los sitios creados en el futuro se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="fd78c-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="fd78c-128">**Solo los sitios seleccionados:** solo los sitios que especifique.</span><span class="sxs-lookup"><span data-stu-id="fd78c-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="fd78c-129">Los sitios creados en el futuro no se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="fd78c-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="fd78c-130">**Ningún sitio:** no incluya ningún sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fd78c-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="fd78c-131">Si elige **Todos, excepto los** sitios seleccionados o solo los sitios seleccionados, puede cargar un archivo .csv con una lista de sitios.</span><span class="sxs-lookup"><span data-stu-id="fd78c-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="fd78c-132">Estas opciones son útiles si está realizando una prueba piloto y desea incluir un número limitado de sitios para iniciar.</span><span class="sxs-lookup"><span data-stu-id="fd78c-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="fd78c-133">Puede copiar la plantilla .csv a continuación:</span><span class="sxs-lookup"><span data-stu-id="fd78c-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="fd78c-134">No se recomienda elegir Ningún **sitio** porque impide que los temas se creen o actualicen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="fd78c-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="fd78c-135">Sin embargo, puede elegir esta opción si desea configurar Temas y, a continuación, agregar sitios más adelante.</span><span class="sxs-lookup"><span data-stu-id="fd78c-135">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="fd78c-136">Se recomienda crear un proceso para que los usuarios o administradores de conocimientos soliciten que se quiten sitios individuales de la detección de temas si es necesario en la organización.</span><span class="sxs-lookup"><span data-stu-id="fd78c-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="fd78c-137">Permisos de usuario</span><span class="sxs-lookup"><span data-stu-id="fd78c-137">User permissions</span></span>

<span data-ttu-id="fd78c-138">Los permisos de usuario que especifique determinan qué personas de la organización interactúan con los temas y qué pueden hacer.</span><span class="sxs-lookup"><span data-stu-id="fd78c-138">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

<span data-ttu-id="fd78c-139">*Administrar temas*</span><span class="sxs-lookup"><span data-stu-id="fd78c-139">*Manage topics*</span></span>

<span data-ttu-id="fd78c-140">Los administradores de conocimientos supervisan la calidad de la información, su estructura y otros procedimientos recomendados en su organización.</span><span class="sxs-lookup"><span data-stu-id="fd78c-140">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="fd78c-141">Pueden confirmar y rechazar temas.</span><span class="sxs-lookup"><span data-stu-id="fd78c-141">They can confirm and reject topics.</span></span>

<span data-ttu-id="fd78c-142">Aunque puede especificar administradores de temas individuales, le recomendamos que cree un grupo de seguridad (o use uno existente) que contenga las personas que desea que sean administradores de conocimientos.</span><span class="sxs-lookup"><span data-stu-id="fd78c-142">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="fd78c-143">Puede especificar este grupo de seguridad durante el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="fd78c-143">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="fd78c-144">*Crear y editar temas*</span><span class="sxs-lookup"><span data-stu-id="fd78c-144">*Create and edit topics*</span></span>

<span data-ttu-id="fd78c-145">Los colaboradores de temas son los expertos y expertos en la materia de su organización.</span><span class="sxs-lookup"><span data-stu-id="fd78c-145">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="fd78c-146">Pueden crear y editar temas.</span><span class="sxs-lookup"><span data-stu-id="fd78c-146">They can create and edit topics.</span></span> 

<span data-ttu-id="fd78c-147">Se recomienda permitir que todos los usuarios de la organización creen y editan temas porque las experiencias de tema funcionan mejor cuando todos los usuarios pueden compartir información.</span><span class="sxs-lookup"><span data-stu-id="fd78c-147">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="fd78c-148">Si desea limitar la creación y edición de temas a personas o grupos específicos, cree un grupo de seguridad para ellos y es específico durante el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="fd78c-148">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="fd78c-149">Puede optar por no permitir que nadie contribuya a los temas, pero esto no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="fd78c-149">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="fd78c-150">Los administradores de conocimientos podrán editar y crear temas si elige esta opción.</span><span class="sxs-lookup"><span data-stu-id="fd78c-150">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="fd78c-151">*Visores de temas*</span><span class="sxs-lookup"><span data-stu-id="fd78c-151">*Topic viewers*</span></span>

<span data-ttu-id="fd78c-152">Los visores de temas pueden ver información sobre las páginas del tema, los resultados de la búsqueda y cuándo se resaltan los temas en el contenido, como las páginas de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fd78c-152">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="fd78c-153">Los usuarios solo pueden ver los temas detectados cuando tienen acceso a los archivos y páginas en los que se ha detectado el tema.</span><span class="sxs-lookup"><span data-stu-id="fd78c-153">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="fd78c-154">Al configurar visores de temas, puede elegir entre:</span><span class="sxs-lookup"><span data-stu-id="fd78c-154">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="fd78c-155">**Todos los miembros de mi organización**</span><span class="sxs-lookup"><span data-stu-id="fd78c-155">**Everyone in my organization**</span></span>
- <span data-ttu-id="fd78c-156">**Solo personas o grupos de seguridad seleccionados**</span><span class="sxs-lookup"><span data-stu-id="fd78c-156">**Only selected people or security groups**</span></span>
- <span data-ttu-id="fd78c-157">**Nadie**</span><span class="sxs-lookup"><span data-stu-id="fd78c-157">**No one**</span></span>

<span data-ttu-id="fd78c-158">Recomendamos **todos los usuarios de mi** organización, pero si está realizando una prueba piloto, es posible que desee elegir solo a personas o grupos de seguridad seleccionados.</span><span class="sxs-lookup"><span data-stu-id="fd78c-158">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="fd78c-159">También puede elegir **No hay nadie** si desea configurar Temas, pero no permitir que los usuarios vean temas todavía.</span><span class="sxs-lookup"><span data-stu-id="fd78c-159">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="fd78c-160">(Los administradores de conocimientos seguirán teniendo acceso para permitirles ver los temas y ayudar con la decisión de hacer que los temas estén ampliamente disponibles).</span><span class="sxs-lookup"><span data-stu-id="fd78c-160">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="fd78c-161">Reglas de conocimiento</span><span class="sxs-lookup"><span data-stu-id="fd78c-161">Knowledge rules</span></span>

<span data-ttu-id="fd78c-162">Como administrador, puede excluir determinados temas de las experiencias del tema.</span><span class="sxs-lookup"><span data-stu-id="fd78c-162">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="fd78c-163">Esto es útil si desea evitar que los datos confidenciales aparezcan en los temas.</span><span class="sxs-lookup"><span data-stu-id="fd78c-163">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="fd78c-164">Aunque los administradores de conocimientos pueden excluir temas del centro de temas, los temas excluidos por el administrador ni siquiera son visibles para los administradores de conocimientos.</span><span class="sxs-lookup"><span data-stu-id="fd78c-164">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="fd78c-165">(Los administradores de conocimientos también pueden quitar temas en el centro de temas después de la detección).</span><span class="sxs-lookup"><span data-stu-id="fd78c-165">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="fd78c-166">Si desea excluir temas en el nivel de administrador, debe agregarlos a un archivo .csv y cargar el archivo.</span><span class="sxs-lookup"><span data-stu-id="fd78c-166">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="fd78c-167">Puede hacerlo durante la instalación o posterior.</span><span class="sxs-lookup"><span data-stu-id="fd78c-167">You can do this during setup or later.</span></span>

<span data-ttu-id="fd78c-168">El archivo .csv debe contener los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="fd78c-168">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="fd78c-169">**Nombre:** escriba el nombre del tema que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="fd78c-169">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="fd78c-170">Puede realizar esto de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="fd78c-170">There are two ways to do this:</span></span>
- <span data-ttu-id="fd78c-171">**MatchType-Exact/Partial**: Escriba si el nombre que escribió fue *un tipo de* coincidencia exacta *o* parcial.</span><span class="sxs-lookup"><span data-stu-id="fd78c-171">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="fd78c-172">Coincidencia exacta: puede incluir el nombre exacto o el acrónimo (por ejemplo, *Contoso* o *ATL*).</span><span class="sxs-lookup"><span data-stu-id="fd78c-172">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="fd78c-173">Coincidencia parcial: puede excluir todos los temas que tengan una palabra específica.</span><span class="sxs-lookup"><span data-stu-id="fd78c-173">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="fd78c-174">Por ejemplo, *el arco* excluirá  todos los temas con la palabra arco en él, como el círculo de *arco,* el arco de *plasma y* el arco *de aprendizaje.* Tenga en cuenta que no excluirá los temas en los que se incluye el texto como parte de una palabra, como *Arquitectura*.</span><span class="sxs-lookup"><span data-stu-id="fd78c-174">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="fd78c-175">**Significa (opcional):**(también conocido como expansión) Si desea excluir un acrónimo, escriba las palabras que el acrónimo significa.</span><span class="sxs-lookup"><span data-stu-id="fd78c-175">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Excluir temas de la plantilla CSV](../media/exclude-topics-csv.png) 

<span data-ttu-id="fd78c-177">Puede copiar la plantilla csv siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd78c-177">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="fd78c-178">Administración</span><span class="sxs-lookup"><span data-stu-id="fd78c-178">Administration</span></span>

<span data-ttu-id="fd78c-179">Al configurar Temas, como parte del proceso de configuración, se crea automáticamente un centro de temas.</span><span class="sxs-lookup"><span data-stu-id="fd78c-179">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="fd78c-180">Piense en lo que desea nombrar el centro de temas y en lo que desea que sea la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="fd78c-180">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="fd78c-181">Puede establecer el nombre y la dirección URL como parte del proceso de configuración y puede cambiar el nombre (pero no la dirección URL) más adelante en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd78c-181">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="fd78c-182">Solo puede tener un centro de temas.</span><span class="sxs-lookup"><span data-stu-id="fd78c-182">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="fd78c-183">Lista de comprobación del programa de instalación</span><span class="sxs-lookup"><span data-stu-id="fd78c-183">Setup checklist</span></span>

<span data-ttu-id="fd78c-184">Al configurar experiencias de tema, necesitará los siguientes elementos a medida que pase por el Asistente para configuración:</span><span class="sxs-lookup"><span data-stu-id="fd78c-184">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="fd78c-185">Lista de sitios que se incluirán o excluirán si no se incluyen todos los sitios para la detección de temas</span><span class="sxs-lookup"><span data-stu-id="fd78c-185">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="fd78c-186">Grupo de seguridad para visores de temas si no permite que todos los usuarios puedan ver temas</span><span class="sxs-lookup"><span data-stu-id="fd78c-186">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="fd78c-187">Grupo de seguridad para colaboradores de temas si no permite que todos los usuarios creen y editan temas</span><span class="sxs-lookup"><span data-stu-id="fd78c-187">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="fd78c-188">Grupo de seguridad para administradores de conocimientos de temas si no permite que todos los usuarios administren temas</span><span class="sxs-lookup"><span data-stu-id="fd78c-188">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="fd78c-189">Lista de temas confidenciales que se excluirán de la detección de temas</span><span class="sxs-lookup"><span data-stu-id="fd78c-189">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="fd78c-190">Un nombre para el sitio del centro de temas</span><span class="sxs-lookup"><span data-stu-id="fd78c-190">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="fd78c-191">Ver también</span><span class="sxs-lookup"><span data-stu-id="fd78c-191">See also</span></span>

[<span data-ttu-id="fd78c-192">Configurar las experiencias temáticas</span><span class="sxs-lookup"><span data-stu-id="fd78c-192">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="fd78c-193">Administrar la detección de temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fd78c-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="fd78c-194">Administrar la visibilidad de temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fd78c-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="fd78c-195">Administrar permisos de tema en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fd78c-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="fd78c-196">Cambiar el nombre del centro de temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fd78c-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
