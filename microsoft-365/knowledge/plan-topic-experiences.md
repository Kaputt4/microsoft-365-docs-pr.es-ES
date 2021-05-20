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
description: Obtenga información sobre cómo planear los temas de Microsoft Viva
ms.openlocfilehash: de7534ce58a7888ac822826ef4ef1b4934ed8cb1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583117"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="3c786-103">Planeación de temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="3c786-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="3c786-104">Tiene el control de cómo se experimentan los temas en su organización.</span><span class="sxs-lookup"><span data-stu-id="3c786-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="3c786-105">Las decisiones de planeación de temas garantizan que los temas de alta calidad se muestran a los usuarios y que tienen los permisos adecuados para consumir y aportar conocimientos.</span><span class="sxs-lookup"><span data-stu-id="3c786-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="3c786-106">En este artículo examinaremos estas decisiones de planeación:</span><span class="sxs-lookup"><span data-stu-id="3c786-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="3c786-107">Qué SharePoint los sitios que desea rastrear para los temas</span><span class="sxs-lookup"><span data-stu-id="3c786-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="3c786-108">Qué temas, si los hay, que desea excluir de las experiencias de temas</span><span class="sxs-lookup"><span data-stu-id="3c786-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="3c786-109">Qué usuarios desea que los temas sean visibles</span><span class="sxs-lookup"><span data-stu-id="3c786-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="3c786-110">Qué usuarios desea conceder permisos para administrar temas en el centro de temas</span><span class="sxs-lookup"><span data-stu-id="3c786-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="3c786-111">Qué usuarios desea conceder permisos para crear o editar temas en el centro de temas</span><span class="sxs-lookup"><span data-stu-id="3c786-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="3c786-112">Qué nombre desea dar al centro de temas</span><span class="sxs-lookup"><span data-stu-id="3c786-112">What name you want to give your topic center</span></span>

<span data-ttu-id="3c786-113">Se respeta la seguridad y privacidad de los datos y las experiencias de temas no conceden a los usuarios acceso adicional a los archivos a los que no tienen derechos.</span><span class="sxs-lookup"><span data-stu-id="3c786-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="3c786-114">También se recomienda leer Temas de [Microsoft Viva seguridad y privacidad](topic-experiences-security-privacy.md) como parte del proceso de planeación.</span><span class="sxs-lookup"><span data-stu-id="3c786-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

<span data-ttu-id="3c786-115">Para obtener más información sobre la tecnología de inteligencia artificial detrás de Los temas de Viva, lea El tema de Alejandría en [Temas de Microsoft Viva: de big data a big knowledge](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge).</span><span class="sxs-lookup"><span data-stu-id="3c786-115">To learn more about the AI technology behind Viva Topics, read [Alexandria in Microsoft Viva Topics: from big data to big knowledge](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge).</span></span>

## <a name="requirements"></a><span data-ttu-id="3c786-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c786-116">Requirements</span></span>

<span data-ttu-id="3c786-117">Debe estar suscrito a [Viva Topics](https://www.microsoft.com/microsoft-viva/topics) y ser administrador global o administrador de SharePoint para tener acceso al centro de administración de Microsoft 365 y configurar Temas.</span><span class="sxs-lookup"><span data-stu-id="3c786-117">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="3c786-118">Todos los usuarios que van a usar Temas requieren una **licencia de Experiencias de** tema.</span><span class="sxs-lookup"><span data-stu-id="3c786-118">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="3c786-119">La asignación de licencias se trata [en Configurar temas de Microsoft Viva](set-up-topic-experiences.md).</span><span class="sxs-lookup"><span data-stu-id="3c786-119">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="3c786-120">Detección de temas</span><span class="sxs-lookup"><span data-stu-id="3c786-120">Topic discovery</span></span>

<span data-ttu-id="3c786-121">La configuración de la detección de temas especifica qué sitios de SharePoint se utilizan como fuentes de temas.</span><span class="sxs-lookup"><span data-stu-id="3c786-121">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="3c786-122">Puede elegir entre incluir todos los sitios de SharePoint, una lista específica de sitios o ningún sitio.</span><span class="sxs-lookup"><span data-stu-id="3c786-122">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="3c786-123">Le recomendamos que elija todos los sitios para que las experiencias del tema puedan descubrir una gran cantidad de temas buenos para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3c786-123">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="3c786-124">Cuando se configuran los Temas, se puede elegir entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3c786-124">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="3c786-125">**Todos los sitios**: Todos los sitios de SharePoint de su organización.</span><span class="sxs-lookup"><span data-stu-id="3c786-125">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="3c786-126">Esto incluye los sitios actuales y futuros.</span><span class="sxs-lookup"><span data-stu-id="3c786-126">This includes current and future sites.</span></span>
- <span data-ttu-id="3c786-127">**Todos, excepto los sitios seleccionados**: Todos los sitios excepto los que usted especifique.</span><span class="sxs-lookup"><span data-stu-id="3c786-127">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="3c786-128">Los sitios creados en el futuro se incluirán como orígenes para la detección de temas.</span><span class="sxs-lookup"><span data-stu-id="3c786-128">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="3c786-129">**Solo sitios seleccionados:** solo los sitios que especifique.</span><span class="sxs-lookup"><span data-stu-id="3c786-129">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="3c786-130">Los sitios creados en el futuro no se incluirán como fuentes para el descubrimiento de temas.</span><span class="sxs-lookup"><span data-stu-id="3c786-130">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="3c786-131">**Ningún sitio**: No incluya ningún sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3c786-131">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="3c786-132">Si elige **Todos,** excepto los sitios seleccionados o Solo los sitios seleccionados, puede cargar un archivo .csv con una lista de sitios.</span><span class="sxs-lookup"><span data-stu-id="3c786-132">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="3c786-133">Estas opciones son útiles si está realizando una prueba piloto y desea incluir un número limitado de sitios para iniciar.</span><span class="sxs-lookup"><span data-stu-id="3c786-133">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="3c786-134">Puede copiar la siguiente .csv siguiente:</span><span class="sxs-lookup"><span data-stu-id="3c786-134">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="3c786-135">No se recomienda elegir **Ningún sitio** porque impide que los temas se creen o actualicen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3c786-135">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="3c786-136">Sin embargo, puede elegir esta opción si desea configurar Temas y, a continuación, agregar sitios más adelante.</span><span class="sxs-lookup"><span data-stu-id="3c786-136">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="3c786-137">Se recomienda crear un proceso para que los usuarios o administradores de conocimientos soliciten que los sitios individuales se quiten de la detección de temas si es necesario en la organización.</span><span class="sxs-lookup"><span data-stu-id="3c786-137">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

### <a name="multi-geo"></a><span data-ttu-id="3c786-138">Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="3c786-138">Multi-geo</span></span>

<span data-ttu-id="3c786-139">Si su organización ha implementado [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), el centro de temas se aprovisiona en la ubicación central y solo SharePoint los sitios de la ubicación central están disponibles para su uso como orígenes para los temas.</span><span class="sxs-lookup"><span data-stu-id="3c786-139">If your organization has deployed [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), the topic center is provisioned in the central location and only SharePoint sites in the central location are available to use as sources for topics.</span></span> <span data-ttu-id="3c786-140">(Si selecciona Todos **los sitios,** Viva Topics usará todos los sitios de la ubicación central).</span><span class="sxs-lookup"><span data-stu-id="3c786-140">(If you select **All sites**, Viva Topics will use all site in the central location.)</span></span>

<span data-ttu-id="3c786-141">Todo el procesamiento y almacenamiento del contenido se realiza en la ubicación central.</span><span class="sxs-lookup"><span data-stu-id="3c786-141">All processing and storage of content is done in the central location.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="3c786-142">Permisos de usuario</span><span class="sxs-lookup"><span data-stu-id="3c786-142">User permissions</span></span>

<span data-ttu-id="3c786-143">Los permisos de usuario que especifique determinan qué personas de la organización interactúan con los temas y qué pueden hacer.</span><span class="sxs-lookup"><span data-stu-id="3c786-143">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

> [!Note] 
> <span data-ttu-id="3c786-144">En este momento, Viva Topics no admite proporcionar licencias o permisos de usuario para usuarios invitados (externos).</span><span class="sxs-lookup"><span data-stu-id="3c786-144">At this time, Viva Topics doesn't support providing licenses or user permissions for Guest (External) users.</span></span> 

<span data-ttu-id="3c786-145">*Administrar temas*</span><span class="sxs-lookup"><span data-stu-id="3c786-145">*Manage topics*</span></span>

<span data-ttu-id="3c786-146">Los administradores de conocimientos supervisan la calidad de la información, su estructura y otros procedimientos recomendados en su organización.</span><span class="sxs-lookup"><span data-stu-id="3c786-146">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="3c786-147">Pueden confirmar y rechazar temas.</span><span class="sxs-lookup"><span data-stu-id="3c786-147">They can confirm and reject topics.</span></span>

<span data-ttu-id="3c786-148">Aunque puede especificar administradores de temas individuales, le recomendamos que cree un grupo de seguridad (o use uno existente) que contenga las personas que desea que sean administradores de conocimientos.</span><span class="sxs-lookup"><span data-stu-id="3c786-148">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="3c786-149">Puede especificar este grupo de seguridad durante el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="3c786-149">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="3c786-150">*Crear y editar temas*</span><span class="sxs-lookup"><span data-stu-id="3c786-150">*Create and edit topics*</span></span>

<span data-ttu-id="3c786-151">Los colaboradores de temas son los campeones y expertos en la materia de su organización.</span><span class="sxs-lookup"><span data-stu-id="3c786-151">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="3c786-152">Pueden crear y editar temas.</span><span class="sxs-lookup"><span data-stu-id="3c786-152">They can create and edit topics.</span></span> 

<span data-ttu-id="3c786-153">Se recomienda permitir que todos los usuarios de la organización creen y editan temas porque las experiencias de tema funcionan mejor cuando todos los usuarios pueden compartir información.</span><span class="sxs-lookup"><span data-stu-id="3c786-153">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="3c786-154">Si desea limitar la creación y edición de temas para personas o grupos específicos, cree un grupo de seguridad para ellos y especifiquelo durante el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="3c786-154">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="3c786-155">Puedes elegir no permitir que nadie contribuya a los temas, pero esto no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="3c786-155">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="3c786-156">Los administradores de conocimientos podrán editar y crear temas si elige esta opción.</span><span class="sxs-lookup"><span data-stu-id="3c786-156">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="3c786-157">*Visores de temas*</span><span class="sxs-lookup"><span data-stu-id="3c786-157">*Topic viewers*</span></span>

<span data-ttu-id="3c786-158">Los visores de temas pueden ver información sobre las páginas de temas, los resultados de la búsqueda y cuándo se resaltan los temas en el contenido, como SharePoint páginas.</span><span class="sxs-lookup"><span data-stu-id="3c786-158">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="3c786-159">Los usuarios solo pueden ver temas detectados cuando tienen acceso a los archivos y páginas en los que se descubrió el tema.</span><span class="sxs-lookup"><span data-stu-id="3c786-159">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="3c786-160">Al configurar visores de temas, puede elegir entre:</span><span class="sxs-lookup"><span data-stu-id="3c786-160">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="3c786-161">**Todos los miembros de mi organización**</span><span class="sxs-lookup"><span data-stu-id="3c786-161">**Everyone in my organization**</span></span>
- <span data-ttu-id="3c786-162">**Solo personas o grupos de seguridad seleccionados**</span><span class="sxs-lookup"><span data-stu-id="3c786-162">**Only selected people or security groups**</span></span>
- <span data-ttu-id="3c786-163">**Nadie**</span><span class="sxs-lookup"><span data-stu-id="3c786-163">**No one**</span></span>

<span data-ttu-id="3c786-164">Recomendamos **todos los miembros de** mi organización, pero si está realizando un piloto, es posible que desee elegir solo personas seleccionadas o grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3c786-164">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="3c786-165">También puede elegir **Nadie si** desea configurar Temas, pero no permitir que los usuarios vean temas todavía.</span><span class="sxs-lookup"><span data-stu-id="3c786-165">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="3c786-166">(Los administradores de conocimientos seguirán teniendo acceso para permitirles ver los temas y ayudarles con la decisión de hacer que los temas estén ampliamente disponibles).</span><span class="sxs-lookup"><span data-stu-id="3c786-166">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="3c786-167">Reglas de conocimiento</span><span class="sxs-lookup"><span data-stu-id="3c786-167">Knowledge rules</span></span>

<span data-ttu-id="3c786-168">Como administrador, puede excluir determinados temas de las experiencias del tema.</span><span class="sxs-lookup"><span data-stu-id="3c786-168">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="3c786-169">Esto es útil si desea evitar que los datos confidenciales aparezcan en los temas.</span><span class="sxs-lookup"><span data-stu-id="3c786-169">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="3c786-170">Aunque los administradores de conocimientos pueden excluir los temas del centro de temas, los temas excluidos por el administrador ni siquiera son visibles para los administradores de conocimientos.</span><span class="sxs-lookup"><span data-stu-id="3c786-170">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="3c786-171">(Los administradores de conocimientos también pueden quitar temas en el centro de temas después de la detección).</span><span class="sxs-lookup"><span data-stu-id="3c786-171">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="3c786-172">Si desea excluir temas en el nivel de administrador, debe agregarlos a un archivo .csv y cargar el archivo.</span><span class="sxs-lookup"><span data-stu-id="3c786-172">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="3c786-173">Puede hacerlo durante la instalación o posterior.</span><span class="sxs-lookup"><span data-stu-id="3c786-173">You can do this during setup or later.</span></span>

<span data-ttu-id="3c786-174">El .csv debe contener los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="3c786-174">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="3c786-175">**Nombre**: Escriba el nombre del tema que quiera excluir.</span><span class="sxs-lookup"><span data-stu-id="3c786-175">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="3c786-176">Hay dos formas de hacerlo:</span><span class="sxs-lookup"><span data-stu-id="3c786-176">There are two ways to do this:</span></span>
- <span data-ttu-id="3c786-177">**MatchType-Exact/Partial:** escriba si el nombre que escribió era *un tipo de* coincidencia exacto *o* parcial.</span><span class="sxs-lookup"><span data-stu-id="3c786-177">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="3c786-178">Coincidencia exacta: puede incluir el nombre exacto o el acrónimo (por ejemplo, *Contoso* o *ATL*).</span><span class="sxs-lookup"><span data-stu-id="3c786-178">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="3c786-179">Coincidencia parcial: puede excluir todos los temas que tengan una palabra específica.</span><span class="sxs-lookup"><span data-stu-id="3c786-179">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="3c786-180">Por ejemplo, *el arco* excluirá  todos los temas con la palabra arco en él, como *Círculo* de arco, *Soldador de arco de* plasma o Arco *de aprendizaje.* Tenga en cuenta que no excluirá los temas en los que el texto se incluye como parte de una palabra, como *Arquitectura*.</span><span class="sxs-lookup"><span data-stu-id="3c786-180">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="3c786-181">**Significa (opcional)**: (También conocido como expansión *)* Si desea excluir un acrónimo, escriba las palabras que el acrónimo representa.</span><span class="sxs-lookup"><span data-stu-id="3c786-181">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Excluir temas en plantilla CSV](../media/exclude-topics-csv.png) 

<span data-ttu-id="3c786-183">Puede copiar la plantilla csv siguiente:</span><span class="sxs-lookup"><span data-stu-id="3c786-183">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="3c786-184">Administración</span><span class="sxs-lookup"><span data-stu-id="3c786-184">Administration</span></span>

<span data-ttu-id="3c786-185">Al configurar Temas, como parte del proceso de configuración, se crea automáticamente un centro de temas.</span><span class="sxs-lookup"><span data-stu-id="3c786-185">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="3c786-186">Piense en lo que desea nombrar el centro de temas y en qué desea que sea la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="3c786-186">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="3c786-187">Puede establecer el nombre y la dirección URL como parte del proceso de instalación y puede cambiar el nombre (pero no la dirección URL) más adelante en el centro de administración de Microsoft 365 configuración.</span><span class="sxs-lookup"><span data-stu-id="3c786-187">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3c786-188">Solo puede tener un centro de temas.</span><span class="sxs-lookup"><span data-stu-id="3c786-188">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="3c786-189">Lista de comprobación de configuración</span><span class="sxs-lookup"><span data-stu-id="3c786-189">Setup checklist</span></span>

<span data-ttu-id="3c786-190">Cuando configures experiencias de tema, necesitarás los siguientes elementos a medida que pases por el asistente de configuración:</span><span class="sxs-lookup"><span data-stu-id="3c786-190">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="3c786-191">Lista de sitios que se incluirán o excluirán si no se incluyen todos los sitios para la detección de temas</span><span class="sxs-lookup"><span data-stu-id="3c786-191">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="3c786-192">Grupo de seguridad para lectores de temas si no se permite que todos los usuarios puedan ver los temas</span><span class="sxs-lookup"><span data-stu-id="3c786-192">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="3c786-193">Grupo de seguridad para colaboradores de temas si no se permite que los usuarios creen y editen temas</span><span class="sxs-lookup"><span data-stu-id="3c786-193">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="3c786-194">Grupo de seguridad para gerentes de información de temas si no se permite que todos los usuarios administren temas</span><span class="sxs-lookup"><span data-stu-id="3c786-194">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="3c786-195">Lista de temas confidenciales que se excluirán de la detección de temas</span><span class="sxs-lookup"><span data-stu-id="3c786-195">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="3c786-196">Un nombre para el sitio del centro de temas</span><span class="sxs-lookup"><span data-stu-id="3c786-196">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="3c786-197">Consulta también</span><span class="sxs-lookup"><span data-stu-id="3c786-197">See also</span></span>

[<span data-ttu-id="3c786-198">Configurar las experiencias temáticas</span><span class="sxs-lookup"><span data-stu-id="3c786-198">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="3c786-199">Administrar la detección de temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3c786-199">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="3c786-200">Administrar la visibilidad del tema en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3c786-200">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="3c786-201">Administrar permisos de temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3c786-201">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="3c786-202">Cambie el nombre del centro de temas en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3c786-202">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
