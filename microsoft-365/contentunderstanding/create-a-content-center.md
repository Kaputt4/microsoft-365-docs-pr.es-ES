---
title: Crear un centro de contenido en Microsoft SharePoint Syntex
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Obtenga información sobre cómo crear un centro de contenido.
ms.openlocfilehash: 878319dd938f565f00a250f0b08de15641644e1c
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087444"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="b67eb-103">Crear un centro de contenido en Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="b67eb-103">Create a content center in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="b67eb-104">Para crear y administrar modelos de comprensión de documentos, primero necesita un centro de contenido.</span><span class="sxs-lookup"><span data-stu-id="b67eb-104">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="b67eb-105">El centro de contenido es la interfaz de creación de modelos y también contiene información sobre los modelos publicados de bibliotecas de documentos que se han aplicado.</span><span class="sxs-lookup"><span data-stu-id="b67eb-105">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![Seleccione una biblioteca de documentos](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="b67eb-107">Puede crear un centro de contenido predeterminado durante la [configuración](set-up-content-understanding.md).</span><span class="sxs-lookup"><span data-stu-id="b67eb-107">You create a default content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="b67eb-108">Sin embargo, un administrador de SharePoint también puede optar por crear centros adicionales según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b67eb-108">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="b67eb-109">Mientras que un único centro de contenido puede ser apropiado para entornos en los que quiera realizar una implementación de todas las actividades del modelo, es posible que quiera disponer de centros adicionales para los distintos departamentos de su organización, que pueden tener distintos requisitos de permisos y necesidades para sus modelos.</span><span class="sxs-lookup"><span data-stu-id="b67eb-109">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and permission requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="b67eb-110">Un administrador de SharePoint puede crear un sitio del centro de contenido del mismo modo en que puede [crear cualquier otro sitio de SharePoint](https://docs.microsoft.com/sharepoint/create-site-collection) a través del panel de aprovisionamiento del sitio del centro de administración.</span><span class="sxs-lookup"><span data-stu-id="b67eb-110">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) through the admin center site provisioning panel.</span></span>

<span data-ttu-id="b67eb-111">Para crear un nuevo centro de contenido:</span><span class="sxs-lookup"><span data-stu-id="b67eb-111">To create a new content center:</span></span>

1. <span data-ttu-id="b67eb-112">En el Centro de administración de Microsoft 365, vaya al Centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b67eb-112">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="b67eb-113">En el nuevo Centro de administración de SharePoint, en **Sitios**, seleccione **Sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="b67eb-113">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="b67eb-114">En la página **Sitios activos**, haga clic en **Crear** y seleccione **Otras opciones**.</span><span class="sxs-lookup"><span data-stu-id="b67eb-114">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="b67eb-115">En el menú **Elegir una plantilla**, seleccione **Centro de contenido**.</span><span class="sxs-lookup"><span data-stu-id="b67eb-115">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="b67eb-116">Para el nuevo sitio, proporcione un **Nombre del sitio**, **Administrador principal** e **Idioma**.</span><span class="sxs-lookup"><span data-stu-id="b67eb-116">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="b67eb-117">Puede seleccionar un sitio de centro de contenido para que se procese en cualquiera de los idiomas disponibles, pero tenga en cuenta que actualmente los modelos solo se pueden crear para archivos en inglés.</span><span class="sxs-lookup"><span data-stu-id="b67eb-117">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span> <span data-ttu-id="b67eb-118">Además, tenga en cuenta que, al igual que otras plantillas de sitio, el idioma predeterminado del sitio no se puede modificar una vez creado el sitio.</span><span class="sxs-lookup"><span data-stu-id="b67eb-118">Also note that like other site templates, the default site language isn't editable after the site is created.</span></span></br>

6. <span data-ttu-id="b67eb-119">Seleccione **Terminado**.</span><span class="sxs-lookup"><span data-stu-id="b67eb-119">Select **Finished**.</span></span>
 
<span data-ttu-id="b67eb-120">Después de crear un sitio del centro de contenido, verá que aparece en la página **Sitios activos** en el Centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b67eb-120">After you create a content center site, you will see it listed on the **Active sites** page in the SharePoint admin center.</span></span> 

### <a name="give-access-to-additional-users"></a><span data-ttu-id="b67eb-121">Conceder acceso a otros usuarios</span><span class="sxs-lookup"><span data-stu-id="b67eb-121">Give access to additional users</span></span>
 
<span data-ttu-id="b67eb-122">Después de crear el sitio, puede conceder acceso a usuarios adicionales al sitio a través del [modelo de permisos del sitio de SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions) estándar.</span><span class="sxs-lookup"><span data-stu-id="b67eb-122">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="b67eb-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b67eb-123">See Also</span></span>
[<span data-ttu-id="b67eb-124">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="b67eb-124">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="b67eb-125">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="b67eb-125">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="b67eb-126">Crear un centro de contenido</span><span class="sxs-lookup"><span data-stu-id="b67eb-126">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="b67eb-127">Información general sobre la comprensión de documentos</span><span class="sxs-lookup"><span data-stu-id="b67eb-127">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="b67eb-128">Crear un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="b67eb-128">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="b67eb-129">Aplicar un modelo</span><span class="sxs-lookup"><span data-stu-id="b67eb-129">Apply a model</span></span>](apply-a-model.md)    
