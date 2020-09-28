---
title: Crear un centro de contenido en Microsoft SharePoint Syntex
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo crear un centro de contenido.
ms.openlocfilehash: 62977bc5a34b041e9e958ff46e0dbc010d6bd822
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295437"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="c1474-103">Crear un centro de contenido en Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="c1474-103">Create a content center in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="c1474-104">El contenido de este artículo es para la versión preliminar privada de Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="c1474-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="c1474-105">[Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="c1474-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="c1474-106">Para crear y administrar documentos que comprenda los modelos, primero necesita un centro de contenido.</span><span class="sxs-lookup"><span data-stu-id="c1474-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="c1474-107">El centro de contenido es la interfaz de creación de modelos y también contiene información sobre los modelos publicados de bibliotecas de documentos que se han aplicado.</span><span class="sxs-lookup"><span data-stu-id="c1474-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![Selección de una biblioteca de documentos](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="c1474-109">Se crea un centro de contenido inicial durante la [instalación](set-up-content-understanding.md).</span><span class="sxs-lookup"><span data-stu-id="c1474-109">You create an initial content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="c1474-110">Pero un administrador de SharePoint también puede optar por crear centros adicionales según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="c1474-110">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="c1474-111">Mientras que un único centro de contenido puede ser adecuado para entornos en los que desea una distribución de todas las actividades del modelo, es posible que desee tener centros adicionales para varios departamentos dentro de su organización, que pueden tener diferentes necesidades y requisitos para sus modelos.</span><span class="sxs-lookup"><span data-stu-id="c1474-111">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="c1474-112">Un administrador de SharePoint puede crear un sitio de centro de contenido del mismo modo que [crearía cualquier otro sitio de SharePoint](https://docs.microsoft.com/sharepoint/create-site-collection) mediante una plantilla de sitio.</span><span class="sxs-lookup"><span data-stu-id="c1474-112">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) by using a site template.</span></span>

<span data-ttu-id="c1474-113">Para crear un nuevo centro de contenido:</span><span class="sxs-lookup"><span data-stu-id="c1474-113">To create a new content center:</span></span>

1. <span data-ttu-id="c1474-114">En el centro de administración de Microsoft 365, vaya al centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c1474-114">From the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="c1474-115">En el centro de administración de SharePoint, en **sitios**, seleccione **sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="c1474-115">In the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="c1474-116">En la página **sitios activos** , haga clic en **crear**y, a continuación, seleccione **otras opciones**.</span><span class="sxs-lookup"><span data-stu-id="c1474-116">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="c1474-117">En el menú **elegir una plantilla** , seleccione **centro de contenido**.</span><span class="sxs-lookup"><span data-stu-id="c1474-117">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="c1474-118">Para el nuevo sitio, proporcione un **nombre de sitio**, un **Administrador principal**y un **idioma**.</span><span class="sxs-lookup"><span data-stu-id="c1474-118">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="c1474-119">Opcionalmente, puede seleccionar un sitio del centro de contenido para que se represente en cualquiera de los idiomas disponibles.</span><span class="sxs-lookup"><span data-stu-id="c1474-119">You can optionally select a content center site to render in any of the available languages.</span></span> <span data-ttu-id="c1474-120">Solo se pueden crear modelos actuales para archivos en inglés.</span><span class="sxs-lookup"><span data-stu-id="c1474-120">Only current models can be created for English files.</span></span></br>

6. <span data-ttu-id="c1474-121">Seleccione **finalizado**.</span><span class="sxs-lookup"><span data-stu-id="c1474-121">Select **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="c1474-122">Dar acceso a usuarios adicionales</span><span class="sxs-lookup"><span data-stu-id="c1474-122">Give access to additional users</span></span>
 
<span data-ttu-id="c1474-123">Después de crear el sitio, puede conceder a los usuarios adicionales acceso al sitio a través del [modelo de permisos de sitio de SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)estándar.</span><span class="sxs-lookup"><span data-stu-id="c1474-123">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="c1474-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1474-124">See Also</span></span>
[<span data-ttu-id="c1474-125">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="c1474-125">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="c1474-126">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="c1474-126">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="c1474-127">[Crear un centro](create-a-content-center.md) 
 de contenido [Información general sobre el documento](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c1474-127">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="c1474-128">Crear un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="c1474-128">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="c1474-129">Aplicar un modelo</span><span class="sxs-lookup"><span data-stu-id="c1474-129">Apply a model</span></span>](apply-a-model.md)    
