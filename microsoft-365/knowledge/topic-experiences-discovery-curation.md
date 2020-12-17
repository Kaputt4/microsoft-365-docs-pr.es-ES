---
title: 'Tema experiencia y descubrimiento de temas de curation (versión preliminar) '
description: Información general sobre cómo se detectan los temas.
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 2d885d841b280e345d90742fe003bb443160c21f
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699059"
---
# <a name="topic-experiences-discovery-and-curation-preview"></a><span data-ttu-id="86d8a-103">Tema experiencia de detección y curation (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="86d8a-103">Topic Experiences discovery and curation (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="86d8a-104">El contenido de este artículo es para la versión preliminar privada de Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="86d8a-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="86d8a-105">[Obtenga más información acerca del Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="86d8a-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="86d8a-106">El tema experiencias convierte la información de conocimiento a conocimiento en su entorno de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86d8a-106">Topic Experiences converts knowledge information to knowledge in your Microsoft 365 environment.</span></span> <span data-ttu-id="86d8a-107">Hemos experimentado mucha lectura a través de documentos y páginas de sitio donde nos encontramos con términos con los que no estamos familiarizados.</span><span class="sxs-lookup"><span data-stu-id="86d8a-107">We've all experienced reading through documents and site pages where we encounter terms we are unfamiliar with.</span></span> <span data-ttu-id="86d8a-108">Muchas veces detenemos lo que estamos haciendo para dedicar más tiempo a buscar más información.</span><span class="sxs-lookup"><span data-stu-id="86d8a-108">Many times we stop what we are doing to spend precious time searching for more information.</span></span>

<span data-ttu-id="86d8a-109">Las experiencias del tema usan Microsoft Graph y AI para identificar los **temas** de la organización.</span><span class="sxs-lookup"><span data-stu-id="86d8a-109">What Topic Experiences does is use Microsoft Graph and AI to identify **topics** in your organization.</span></span>  <span data-ttu-id="86d8a-110">Un tema es una frase o término que tiene un significado específico para una organización, donde los usuarios se beneficiarían al ser capaces de ver una página de wiki.</span><span class="sxs-lookup"><span data-stu-id="86d8a-110">A topic is a phrase or term that has a specific meaning to an organization, where users would benefit by being able to view a wiki page about it.</span></span> <span data-ttu-id="86d8a-111">AI busca personas y contenido conectados al tema y, si ha descubierto lo suficiente, se convierte en un tema sugerido.</span><span class="sxs-lookup"><span data-stu-id="86d8a-111">AI searches for people and content connected to the topic, and if enough it discovered, it becomes a suggested topic.</span></span>

<span data-ttu-id="86d8a-112">La información del tema generado de AI se agrega a una **página del tema**, que puede contener:</span><span class="sxs-lookup"><span data-stu-id="86d8a-112">The AI generated topic information is added to a **Topic page**, which can contain:</span></span>
- <span data-ttu-id="86d8a-113">Una breve descripción del tema.</span><span class="sxs-lookup"><span data-stu-id="86d8a-113">A short description of the topic.</span></span>
- <span data-ttu-id="86d8a-114">Nombres alternativos para el tema.</span><span class="sxs-lookup"><span data-stu-id="86d8a-114">Alternate names for the topic.</span></span>
- <span data-ttu-id="86d8a-115">Personas que podrían saber más sobre el tema.</span><span class="sxs-lookup"><span data-stu-id="86d8a-115">People who might know more about the topic.</span></span>
- <span data-ttu-id="86d8a-116">Sitios, archivos y páginas que podrían estar relacionadas con el tema.</span><span class="sxs-lookup"><span data-stu-id="86d8a-116">Sites, files, and pages that might be related to the topic.</span></span>

<span data-ttu-id="86d8a-117">A continuación, se asegura de que todas las instancias de un tema se resaltan en todas las páginas de sitio modernas de SharePoint de su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="86d8a-117">Topic experiences then makes sure that every instance of a topic is highlighted on all SharePoint modern site pages in your tenant.</span></span> <span data-ttu-id="86d8a-118">Cuando un usuario tiene curiosidad de obtener más información sobre un tema, puede seleccionar el tema resaltado para ver una tarjeta de **Resumen de temas** que proporcione una descripción breve.</span><span class="sxs-lookup"><span data-stu-id="86d8a-118">When a user is curious to learn more about a topic, they can select the highlighted topic to view a **Topic summary** card that provides a short description.</span></span> <span data-ttu-id="86d8a-119">Y si desea obtener más información, puede seleccionar un vínculo de **detalles del tema** en el resumen para abrir la página del tema detallado.</span><span class="sxs-lookup"><span data-stu-id="86d8a-119">And if they want to learn more, they can select a **Topic details** link in the summary to open the detailed topic page.</span></span>

![Aspectos destacados del tema](../media/knowledge-management/saturn.png) </br>

<span data-ttu-id="86d8a-121">Además, los usuarios también podrán buscar temas a través de Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="86d8a-121">Additionally, users will also be able to find topics through Microsoft Search.</span></span>


## <a name="topic-curation"></a><span data-ttu-id="86d8a-122">Tema curation</span><span class="sxs-lookup"><span data-stu-id="86d8a-122">Topic curation</span></span>

<span data-ttu-id="86d8a-123">El tema experiencias de bienvenida "curation" humano para mejorar la calidad de los temas.</span><span class="sxs-lookup"><span data-stu-id="86d8a-123">Topic Experiences welcomes human "curation" to improve the quality of your topics.</span></span> <span data-ttu-id="86d8a-124">Mientras que AI identifica y sugiere inicialmente los temas, ha realizado manualmente actualizaciones para el contenido de los colaboradores, la confirmación de los usuarios para el contenido generado por AI y los comentarios sobre la utilidad de los temas son fundamentales.</span><span class="sxs-lookup"><span data-stu-id="86d8a-124">While AI initially identifies and suggests topics, manually made updates to content from contributors, confirmation from users for AI generated content, and feedback on the usefulness of topics are all essential.</span></span>

- <span data-ttu-id="86d8a-125">Los **administradores del conocimiento** de la organización pueden revisar los temas generados por AI ("temas sugeridos").</span><span class="sxs-lookup"><span data-stu-id="86d8a-125">AI generated topics ("suggested topics") can be reviewed by **knowledge managers** in your organization.</span></span> <span data-ttu-id="86d8a-126">En la página Administrar temas del centro de temas, pueden optar por confirmarlos como válidos o rechazarlos para evitar que se vean.</span><span class="sxs-lookup"><span data-stu-id="86d8a-126">In the Manage Topics page in the Topic Center, they can choose to confirm them as valid, or reject them to prevent them from being viewed.</span></span>

- <span data-ttu-id="86d8a-127">Puede asignar los permisos *crear y editar temas* a cualquiera de los usuarios con licencia para que puedan realizar cambios en los temas existentes o crear temas nuevos cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="86d8a-127">You can assign *Create and edit topics* permissions to any of your licensed users so that they can make changes to existing topics or create new topics when needed.</span></span> 

- <span data-ttu-id="86d8a-128">Incluso se pedirá a los usuarios que solo tienen acceso de lectura al tema (visores de temas) que comprueben la utilidad de temas específicos.</span><span class="sxs-lookup"><span data-stu-id="86d8a-128">Even users who only have read access to topic (topic viewers) will be asked to verify the usefulness of specific topics.</span></span>

<span data-ttu-id="86d8a-129">Incluso con curation humanos, AI buscará continuamente más información sobre los temas y buscará la verificación humana.</span><span class="sxs-lookup"><span data-stu-id="86d8a-129">Even with human curation, AI will continually look for more information about topics, and will look for human verification.</span></span> <span data-ttu-id="86d8a-130">Por ejemplo, si AI cree que es una persona que debe anclarse como experto en un tema, le pedirá que confirme esto.</span><span class="sxs-lookup"><span data-stu-id="86d8a-130">For example, if AI thinks you are a person that should be pinned as an expert on a topic, it will ask you to confirm this.</span></span> 

















## <a name="see-also"></a><span data-ttu-id="86d8a-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86d8a-131">See also</span></span>



  






