---
title: Crear un centro de contenido (versión preliminar)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo crear un centro de contenido.
ms.openlocfilehash: 5332ffa195519aebd5ae8dd2c26d7d62fd9b3267
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612755"
---
# <a name="create-a-content-center-preview"></a><span data-ttu-id="29641-103">Crear un centro de contenido (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="29641-103">Create a content center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="29641-104">El contenido de este artículo es para la versión preliminar privada de Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="29641-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="29641-105">[Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="29641-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="29641-106">Para crear y administrar documentos que comprenda los modelos, primero necesita un centro de contenido.</span><span class="sxs-lookup"><span data-stu-id="29641-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="29641-107">El centro de contenido es la interfaz de creación de modelos y también contiene información sobre qué modelos publicados de bibliotecas de documentos se han aplicado.</span><span class="sxs-lookup"><span data-stu-id="29641-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied.</span></span></br>

   ![Selección de una biblioteca de documentos](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="29641-109">Se crea un centro de contenido inicial durante la [configuración](set-up-content-understanding.md), pero un administrador de SharePoint puede elegir crear otros adicionales según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="29641-109">An initial content center is created during [setup](set-up-content-understanding.md), but a SharePoint admin can choose to create additional ones as needed.</span></span> <span data-ttu-id="29641-110">Mientras que un único centro de contenido puede ser adecuado para entornos en los que desea ver un resumen de todas las actividades del modelo, es posible que desee disponer de varios departamentos en su organización que puedan tener diferentes necesidades y requisitos para sus modelos.</span><span class="sxs-lookup"><span data-stu-id="29641-110">While a single content center may be fine for environments in which you want to see a roll-up of all model activity, you may want to have additional ones if your have multiple departments within your organization that may have different needs and requirements for their models.</span></span>

<span data-ttu-id="29641-111">Un administrador de SharePoint puede crear un sitio de centro de contenido del mismo modo que [crearía cualquier otro sitio de SharePoint](https://docs.microsoft.com/sharepoint/create-site-collection) a través de una plantilla de sitio.</span><span class="sxs-lookup"><span data-stu-id="29641-111">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) - through a site template.</span></span>

<span data-ttu-id="29641-112">Para crear un nuevo centro de contenido:</span><span class="sxs-lookup"><span data-stu-id="29641-112">To create a new content center:</span></span>

1. <span data-ttu-id="29641-113">En el centro de administración de Microsoft 365, vaya al centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="29641-113">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="29641-114">En el centro de administración de SharePoint, en **sitios**, seleccione **sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="29641-114">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="29641-115">En la página **sitios activos** , haga clic en **crear**y, a continuación, seleccione **otras opciones**.</span><span class="sxs-lookup"><span data-stu-id="29641-115">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="29641-116">En el menú **elegir una plantilla** , seleccione **centro de contenido**.</span><span class="sxs-lookup"><span data-stu-id="29641-116">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="29641-117">Para el nuevo sitio, proporcione un **nombre de sitio**, un **Administrador principal**y un **idioma**.</span><span class="sxs-lookup"><span data-stu-id="29641-117">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!Note] 
> <span data-ttu-id="29641-118">Puede seleccionar un sitio del centro de contenido para que se represente en cualquiera de los idiomas disponibles, pero tenga en cuenta que actualmente los modelos solo se pueden crear para archivos en inglés.</span><span class="sxs-lookup"><span data-stu-id="29641-118">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span></br>

6. <span data-ttu-id="29641-119">Haga clic en **Finalizado**.</span><span class="sxs-lookup"><span data-stu-id="29641-119">Click **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="29641-120">Dar acceso a usuarios adicionales</span><span class="sxs-lookup"><span data-stu-id="29641-120">Give access to additional users</span></span>
 
<span data-ttu-id="29641-121">Una vez creado el sitio, puede conceder a los usuarios adicionales acceso al sitio a través del [modelo de permisos de sitio de SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)estándar.</span><span class="sxs-lookup"><span data-stu-id="29641-121">After the site is created, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>





## <a name="see-also"></a><span data-ttu-id="29641-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="29641-122">See Also</span></span>
[<span data-ttu-id="29641-123">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="29641-123">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="29641-124">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="29641-124">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="29641-125">[Crear un centro](create-a-content-center.md) 
 de contenido [Información general sobre el documento](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="29641-125">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="29641-126">Crear un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="29641-126">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="29641-127">Aplicar un modelo</span><span class="sxs-lookup"><span data-stu-id="29641-127">Apply a model</span></span>](apply-a-model.md)    




