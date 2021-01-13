---
title: Alineación avanzada de eDiscovery con EDRM
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: El flujo de trabajo integrado de eDiscovery avanzado en Microsoft 365 se alinea con el proceso de exhibición de documentos electrónicos que describe el modelo de referencia de detección electrónica (EDRM).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ca94baf1fc57ac014a32a80ddc5705feeb2c842
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841658"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a><span data-ttu-id="6d934-103">Alineación avanzada de eDiscovery con el modelo de referencia de detección electrónica</span><span class="sxs-lookup"><span data-stu-id="6d934-103">Advanced eDiscovery alignment with the Electronic Discovery Reference Model</span></span>

<span data-ttu-id="6d934-104">El flujo de trabajo integrado de eDiscovery avanzado en Microsoft 365 se alinea con el proceso de exhibición de documentos electrónicos que describe el modelo de referencia de detección electrónica (EDRM).</span><span class="sxs-lookup"><span data-stu-id="6d934-104">The built-in workflow of Advanced eDiscovery in Microsoft 365 aligns with the eDiscovery process outlined by the Electronic Discovery Reference Model (EDRM).</span></span>

![Modelo de referencia de detección electrónica (EDRM)](../media/EDRMv1.png)

<span data-ttu-id="6d934-106">(El origen de la imagen es cortesía de edrm.net.</span><span class="sxs-lookup"><span data-stu-id="6d934-106">(Image source courtesy of edrm.net.</span></span> <span data-ttu-id="6d934-107">La imagen de origen estaba disponible en Creative Commons Attribution 3.0 Unported License.)</span><span class="sxs-lookup"><span data-stu-id="6d934-107">The source image was made available under Creative Commons Attribution 3.0 Unported License.)</span></span>

<span data-ttu-id="6d934-108">En un nivel alto, así es como eDiscovery avanzado admite el flujo de trabajo de EDRM:</span><span class="sxs-lookup"><span data-stu-id="6d934-108">At a high level, here's how Advanced eDiscovery supports the EDRM workflow:</span></span>

- <span data-ttu-id="6d934-109">**Identificación.**</span><span class="sxs-lookup"><span data-stu-id="6d934-109">**Identification.**</span></span> <span data-ttu-id="6d934-110">Después de identificar posibles personas de interés en una investigación, puede agregarlas como administradores (también *denominados* administradores de datos, porque pueden poseer información relevante para la investigación) a un caso de eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="6d934-110">After you identify potential persons of interest in an investigation, you can add them as custodians (also called *data custodians*, because they may possess information that's relevant to the investigation) to an Advanced eDiscovery case.</span></span> <span data-ttu-id="6d934-111">Una vez que los usuarios se agregan como administradores, es fácil conservar, recopilar y revisar documentos de administrador.</span><span class="sxs-lookup"><span data-stu-id="6d934-111">After users are added as custodians, it's easy to preserve, collect, and review custodian documents.</span></span>

- <span data-ttu-id="6d934-112">**Conservación.**</span><span class="sxs-lookup"><span data-stu-id="6d934-112">**Preservation.**</span></span> <span data-ttu-id="6d934-113">Para conservar y proteger los datos que son relevantes para una investigación, eDiscovery avanzado le permite colocar una retención legal en los orígenes de datos asociados con los administradores en un caso.</span><span class="sxs-lookup"><span data-stu-id="6d934-113">To preserve and protect data that's relevant to an investigation, Advanced eDiscovery lets you place a legal hold on the data sources associated with the custodians in a case.</span></span> <span data-ttu-id="6d934-114">También puede poner en retención los datos que no son de custodia.</span><span class="sxs-lookup"><span data-stu-id="6d934-114">You can also place non-custodial data on hold.</span></span> <span data-ttu-id="6d934-115">EDiscovery avanzado también tiene un flujo de trabajo de comunicaciones integrado para que pueda enviar notificaciones de retención legal a los administradores y realizar un seguimiento de sus confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="6d934-115">Advanced eDiscovery also has a built-in communications workflow so you can send legal hold notifications to custodians and track their acknowledgments.</span></span>

- <span data-ttu-id="6d934-116">**Colección.**</span><span class="sxs-lookup"><span data-stu-id="6d934-116">**Collection.**</span></span> <span data-ttu-id="6d934-117">Después de identificar (y conservar) los orígenes de datos relevantes para la investigación, puede usar la herramienta de búsqueda integrada en la búsqueda de eDiscovery avanzado para buscar y recopilar datos en directo de los orígenes de datos de custodia (y orígenes de datos no administradores, si procede) que puedan ser relevantes para el caso.</span><span class="sxs-lookup"><span data-stu-id="6d934-117">After you identified (and preserved) the data sources relevant to the investigation, you can use the built-in search tool in Advanced eDiscovery search for and collect live data from the custodial data sources (and non-custodial data sources, if applicable) that may be relevant to the case.</span></span>

- <span data-ttu-id="6d934-118">**Procesamiento.**</span><span class="sxs-lookup"><span data-stu-id="6d934-118">**Processing.**</span></span> <span data-ttu-id="6d934-119">Después de recopilar todos los datos relevantes para el caso, el siguiente paso es procesarlo para su posterior revisión y análisis.</span><span class="sxs-lookup"><span data-stu-id="6d934-119">After you've collected all data relevant to the case, the next step is process it for further review and analysis.</span></span> <span data-ttu-id="6d934-120">En eDiscovery avanzado, los datos en el lugar que identificó en la fase de recopilación se copian *en* una ubicación de Azure Storage (denominada conjunto de revisión), que proporciona una vista estática de los datos del caso.</span><span class="sxs-lookup"><span data-stu-id="6d934-120">In Advanced eDiscovery, the in-place data that you identified in the collection phase is copied to an Azure Storage location (called a *review set*), which provides you with a static view of the case data.</span></span> 

- <span data-ttu-id="6d934-121">**Revisar.**</span><span class="sxs-lookup"><span data-stu-id="6d934-121">**Review.**</span></span> <span data-ttu-id="6d934-122">Después de agregar datos a un conjunto de revisión, puede ver documentos específicos y ejecutar consultas adicionales para reducir los datos a lo más relevante para el caso.</span><span class="sxs-lookup"><span data-stu-id="6d934-122">After data has been added to a review set, you can view specific documents and run additional queries to reduce the data to what is most relevant to the case.</span></span> <span data-ttu-id="6d934-123">Además, puede anotar y etiquetar documentos específicos.</span><span class="sxs-lookup"><span data-stu-id="6d934-123">Also, can annotate and tag specific documents.</span></span>

- <span data-ttu-id="6d934-124">**Análisis.**</span><span class="sxs-lookup"><span data-stu-id="6d934-124">**Analysis.**</span></span> <span data-ttu-id="6d934-125">EDiscovery avanzado proporciona una herramienta de análisis integrado que le ayuda a obtener más información sobre el conjunto de revisión que determine que no es relevante para la investigación.</span><span class="sxs-lookup"><span data-stu-id="6d934-125">Advanced eDiscovery provides integrated analytics tool that helps you further cull data from the review set that you determine isn't relevant to the investigation.</span></span> <span data-ttu-id="6d934-126">Además de reducir el volumen de datos relevantes, eDiscovery avanzado también le ayuda a ahorrar costos de revisión legal, ya que le permite organizar el contenido para que el proceso de revisión sea más fácil y eficaz.</span><span class="sxs-lookup"><span data-stu-id="6d934-126">In addition to reducing the volume of relevant data, Advance eDiscovery also helps you save legal review costs by letting you organize content to make the review process easier and more efficient.</span></span>

- <span data-ttu-id="6d934-127">**Producción** y **presentación.**</span><span class="sxs-lookup"><span data-stu-id="6d934-127">**Production** and **Presentation.**</span></span> <span data-ttu-id="6d934-128">Cuando esté listo, puede exportar documentos de un conjunto de revisión para revisión legal.</span><span class="sxs-lookup"><span data-stu-id="6d934-128">When you're ready, you can export documents from a review set for legal review.</span></span> <span data-ttu-id="6d934-129">Puede exportar documentos en su formato nativo o en un formato especificado por EDRM para que se puedan importar a aplicaciones de revisión de terceros.</span><span class="sxs-lookup"><span data-stu-id="6d934-129">You can export documents in their native format or in an EDRM-specified format so they can be imported into third-party review applications.</span></span>

## <a name="more-information"></a><span data-ttu-id="6d934-130">Más información</span><span class="sxs-lookup"><span data-stu-id="6d934-130">More information</span></span>

<span data-ttu-id="6d934-131">Para empezar a usar eDiscovery avanzado, consulte:</span><span class="sxs-lookup"><span data-stu-id="6d934-131">To get started using Advanced eDiscovery, see:</span></span>

- [<span data-ttu-id="6d934-132">Configurar eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="6d934-132">Set up Advanced eDiscovery</span></span>](get-started-with-advanced-ediscovery.md)

- [<span data-ttu-id="6d934-133">Crear y administrar un caso de eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="6d934-133">Create and manage an Advanced eDiscovery case</span></span>](create-and-manage-advanced-ediscoveryv2-case.md)