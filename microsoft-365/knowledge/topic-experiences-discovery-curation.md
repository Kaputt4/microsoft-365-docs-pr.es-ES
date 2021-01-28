---
title: 'Detección y conservación de temas de experiencias de tema (versión preliminar) '
description: Información general sobre cómo se detectan los temas.
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-topics
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 08860b32b6809f489a9c108dcfaed3f61fb2e306
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029643"
---
# <a name="topic-experiences-discovery-and-curation-preview"></a><span data-ttu-id="03ad2-103">Detección y conservación de experiencias de tema (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="03ad2-103">Topic Experiences discovery and curation (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="03ad2-104">El contenido de este artículo es para Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="03ad2-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="03ad2-105">[Obtenga más información acerca del Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="03ad2-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="03ad2-106">Experiencias de tema convierte la información de conocimiento en conocimientos en su entorno de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="03ad2-106">Topic Experiences converts knowledge information to knowledge in your Microsoft 365 environment.</span></span> <span data-ttu-id="03ad2-107">Todos hemos experimentado la lectura a través de documentos y páginas del sitio donde encontramos términos con los que no estamos familiarizados.</span><span class="sxs-lookup"><span data-stu-id="03ad2-107">We've all experienced reading through documents and site pages where we encounter terms we are unfamiliar with.</span></span> <span data-ttu-id="03ad2-108">Muchas veces detenemos lo que estamos haciendo para dedicar mucho tiempo a buscar más información.</span><span class="sxs-lookup"><span data-stu-id="03ad2-108">Many times we stop what we are doing to spend precious time searching for more information.</span></span>

<span data-ttu-id="03ad2-109">Lo que hace Experiencias de tema es usar Microsoft Graph y AI para identificar **los temas** de su organización.</span><span class="sxs-lookup"><span data-stu-id="03ad2-109">What Topic Experiences does is use Microsoft Graph and AI to identify **topics** in your organization.</span></span>  <span data-ttu-id="03ad2-110">Un tema es una frase o término que tiene un significado específico para una organización, donde los usuarios se beneficiarían al poder ver una página wiki al respecto.</span><span class="sxs-lookup"><span data-stu-id="03ad2-110">A topic is a phrase or term that has a specific meaning to an organization, where users would benefit by being able to view a wiki page about it.</span></span> <span data-ttu-id="03ad2-111">La inteligencia artificial busca personas y contenido conectado al tema y, si es suficiente, se convierte en un tema sugerido.</span><span class="sxs-lookup"><span data-stu-id="03ad2-111">AI searches for people and content connected to the topic, and if enough it discovered, it becomes a suggested topic.</span></span>

<span data-ttu-id="03ad2-112">La información de tema sugerida por la IA se agrega a una **página De tema,** que puede contener:</span><span class="sxs-lookup"><span data-stu-id="03ad2-112">The AI suggested topic information is added to a **Topic page**, which can contain:</span></span>
- <span data-ttu-id="03ad2-113">Breve descripción del tema.</span><span class="sxs-lookup"><span data-stu-id="03ad2-113">A short description of the topic.</span></span>
- <span data-ttu-id="03ad2-114">Nombres alternativos para el tema.</span><span class="sxs-lookup"><span data-stu-id="03ad2-114">Alternate names for the topic.</span></span>
- <span data-ttu-id="03ad2-115">Personas que puedan conocer más sobre el tema.</span><span class="sxs-lookup"><span data-stu-id="03ad2-115">People who might know more about the topic.</span></span>
- <span data-ttu-id="03ad2-116">Sitios, archivos y páginas que pueden estar relacionados con el tema.</span><span class="sxs-lookup"><span data-stu-id="03ad2-116">Sites, files, and pages that might be related to the topic.</span></span>

<span data-ttu-id="03ad2-117">A continuación, las experiencias de tema, cuando el contexto es adecuado, sugieren que estos temas se resalte en todas las páginas de sitio modernas de SharePoint del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="03ad2-117">Topic experiences then, when the context is appropriate, suggests these topics to be highlighted on all SharePoint modern site pages in your tenant.</span></span> <span data-ttu-id="03ad2-118">Cuando un usuario tiene curiosidad por obtener más información sobre un  tema, puede seleccionar el tema resaltado para ver una tarjeta de resumen de tema que proporciona una breve descripción.</span><span class="sxs-lookup"><span data-stu-id="03ad2-118">When a user is curious to learn more about a topic, they can select the highlighted topic to view a **Topic summary** card that provides a short description.</span></span> <span data-ttu-id="03ad2-119">Y si quieren obtener más información, pueden seleccionar un vínculo **Detalles** del tema en el resumen para abrir la página de temas detallada.</span><span class="sxs-lookup"><span data-stu-id="03ad2-119">And if they want to learn more, they can select a **Topic details** link in the summary to open the detailed topic page.</span></span>

![Aspectos destacados del tema](../media/knowledge-management/saturn.png) </br>

<span data-ttu-id="03ad2-121">Además, los usuarios también podrán encontrar temas a través de Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="03ad2-121">Additionally, users will also be able to find topics through Microsoft Search.</span></span>


## <a name="topic-curation"></a><span data-ttu-id="03ad2-122">Curación de temas</span><span class="sxs-lookup"><span data-stu-id="03ad2-122">Topic curation</span></span>

<span data-ttu-id="03ad2-123">Experiencias de tema agradece la contribución humana para mejorar la calidad de sus temas.</span><span class="sxs-lookup"><span data-stu-id="03ad2-123">Topic Experiences welcomes human contribution to improve the quality of your topics.</span></span> <span data-ttu-id="03ad2-124">Aunque la inteligencia artificial identifica y sugiere temas inicialmente, los cambios realizados manualmente en el contenido de los colaboradores, la confirmación de los usuarios sobre el contenido generado por la inteligencia artificial y los comentarios sobre la utilidad de los temas son esenciales.</span><span class="sxs-lookup"><span data-stu-id="03ad2-124">While AI initially identifies and suggests topics, manually made edits to content from contributors, confirmation from users for AI generated content, and feedback on the usefulness of topics are all essential.</span></span>

- <span data-ttu-id="03ad2-125">Los administradores de conocimientos de la organización pueden revisar los temas generados por la inteligencia **artificial** ("temas sugeridos").</span><span class="sxs-lookup"><span data-stu-id="03ad2-125">AI generated topics ("suggested topics") can be reviewed by **knowledge managers** in your organization.</span></span> <span data-ttu-id="03ad2-126">En la página Administrar temas del Centro de temas, pueden elegir confirmarlos como válidos o rechazarlos para evitar que se puedan ver.</span><span class="sxs-lookup"><span data-stu-id="03ad2-126">In the Manage Topics page in the Topic Center, they can choose to confirm them as valid, or reject them to prevent them from being viewed.</span></span>

- <span data-ttu-id="03ad2-127">Puede asignar permisos de creación y *edición* de temas a cualquiera de los usuarios con licencia para que puedan realizar cambios en los temas existentes o crear nuevos temas cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="03ad2-127">You can assign *Create and edit topics* permissions to any of your licensed users so that they can make changes to existing topics or create new topics when needed.</span></span> 

- <span data-ttu-id="03ad2-128">Incluso a los usuarios que solo tienen acceso de lectura a un tema (visores de temas) se les pedirá que comprueben la utilidad de temas específicos.</span><span class="sxs-lookup"><span data-stu-id="03ad2-128">Even users who only have read access to topic (topic viewers) will be asked to verify the usefulness of specific topics.</span></span> <span data-ttu-id="03ad2-129">Sus comentarios también se toman para confirmar o rechazar un tema sugerido.</span><span class="sxs-lookup"><span data-stu-id="03ad2-129">Their feedback is also taken to confirm or reject a suggested topic.</span></span>

<span data-ttu-id="03ad2-130">Incluso con las ediciones humanas, la inteligencia artificial buscará continuamente más información sobre los temas y buscará la verificación humana.</span><span class="sxs-lookup"><span data-stu-id="03ad2-130">Even with human edits, AI will continually look for more information about topics, and will look for human verification.</span></span> <span data-ttu-id="03ad2-131">Por ejemplo, si AI cree que es una persona que debe aparecer como experto en un tema, le pedirá que lo confirme.</span><span class="sxs-lookup"><span data-stu-id="03ad2-131">For example, if AI thinks you are a person that should be listed as an expert on a topic, it will ask you to confirm this.</span></span> 



## <a name="see-also"></a><span data-ttu-id="03ad2-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="03ad2-132">See also</span></span>
