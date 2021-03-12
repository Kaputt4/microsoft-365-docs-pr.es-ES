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
- m365-security-compliance
search.appverid:
- MOE150
- MET150
description: El flujo de trabajo integrado de eDiscovery avanzado en Microsoft 365 se alinea con el proceso de exhibición de documentos electrónicos descrito por el Modelo de referencia de detección electrónica (EDRM).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f2e7886eb67a58b43e9fb638fafb358fd9ee832c
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727493"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a><span data-ttu-id="22ed3-103">Alineación avanzada de eDiscovery con el modelo de referencia de detección electrónica</span><span class="sxs-lookup"><span data-stu-id="22ed3-103">Advanced eDiscovery alignment with the Electronic Discovery Reference Model</span></span>

<span data-ttu-id="22ed3-104">El flujo de trabajo integrado de eDiscovery avanzado en Microsoft 365 se alinea con el proceso de exhibición de documentos electrónicos descrito por el Modelo de referencia de detección electrónica (EDRM).</span><span class="sxs-lookup"><span data-stu-id="22ed3-104">The built-in workflow of Advanced eDiscovery in Microsoft 365 aligns with the eDiscovery process outlined by the Electronic Discovery Reference Model (EDRM).</span></span>

![Modelo de referencia de detección electrónica (EDRM)](../media/EDRMv1.png)

<span data-ttu-id="22ed3-106">(Origen de la imagen cortesía de edrm.net.</span><span class="sxs-lookup"><span data-stu-id="22ed3-106">(Image source courtesy of edrm.net.</span></span> <span data-ttu-id="22ed3-107">La imagen de origen estaba disponible en Creative Commons Attribution 3.0 Unported License).)</span><span class="sxs-lookup"><span data-stu-id="22ed3-107">The source image was made available under Creative Commons Attribution 3.0 Unported License.)</span></span>

<span data-ttu-id="22ed3-108">En un nivel alto, este es el modo en que eDiscovery avanzado admite el flujo de trabajo de EDRM:</span><span class="sxs-lookup"><span data-stu-id="22ed3-108">At a high level, here's how Advanced eDiscovery supports the EDRM workflow:</span></span>

- <span data-ttu-id="22ed3-109">**Identificación.**</span><span class="sxs-lookup"><span data-stu-id="22ed3-109">**Identification.**</span></span> <span data-ttu-id="22ed3-110">Después de identificar posibles personas de interés en una investigación, puede agregarlas como custodios (también *denominadas custodios* de datos, porque pueden tener información relevante para la investigación) a un caso de exhibición de documentos electrónicos avanzado.</span><span class="sxs-lookup"><span data-stu-id="22ed3-110">After you identify potential persons of interest in an investigation, you can add them as custodians (also called *data custodians*, because they may possess information that's relevant to the investigation) to an Advanced eDiscovery case.</span></span> <span data-ttu-id="22ed3-111">Después de agregar a los usuarios como custodios, es fácil conservar, recopilar y revisar documentos de custodia.</span><span class="sxs-lookup"><span data-stu-id="22ed3-111">After users are added as custodians, it's easy to preserve, collect, and review custodian documents.</span></span>

- <span data-ttu-id="22ed3-112">**Conservación.**</span><span class="sxs-lookup"><span data-stu-id="22ed3-112">**Preservation.**</span></span> <span data-ttu-id="22ed3-113">Para conservar y proteger los datos que son relevantes para una investigación, eDiscovery avanzado le permite colocar una retención legal en los orígenes de datos asociados con los custodios en un caso.</span><span class="sxs-lookup"><span data-stu-id="22ed3-113">To preserve and protect data that's relevant to an investigation, Advanced eDiscovery lets you place a legal hold on the data sources associated with the custodians in a case.</span></span> <span data-ttu-id="22ed3-114">También puede poner en espera datos que no son custodia.</span><span class="sxs-lookup"><span data-stu-id="22ed3-114">You can also place non-custodial data on hold.</span></span> <span data-ttu-id="22ed3-115">La exhibición de documentos electrónicos avanzada también tiene un flujo de trabajo de comunicaciones integrado para que pueda enviar notificaciones de retención legal a los custodios y realizar un seguimiento de sus confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="22ed3-115">Advanced eDiscovery also has a built-in communications workflow so you can send legal hold notifications to custodians and track their acknowledgments.</span></span>

- <span data-ttu-id="22ed3-116">**Colección.**</span><span class="sxs-lookup"><span data-stu-id="22ed3-116">**Collection.**</span></span> <span data-ttu-id="22ed3-117">Después de identificar (y conservar) los orígenes de datos relevantes para la investigación, puede usar la herramienta de búsqueda integrada en Búsqueda avanzada de exhibición de documentos electrónicos para buscar y recopilar datos en directo de los orígenes de datos con custodia (y orígenes de datos no custodiados, si procede) que puedan ser relevantes para el caso.</span><span class="sxs-lookup"><span data-stu-id="22ed3-117">After you identified (and preserved) the data sources relevant to the investigation, you can use the built-in search tool in Advanced eDiscovery search for and collect live data from the custodial data sources (and non-custodial data sources, if applicable) that may be relevant to the case.</span></span>

- <span data-ttu-id="22ed3-118">**Procesamiento.**</span><span class="sxs-lookup"><span data-stu-id="22ed3-118">**Processing.**</span></span> <span data-ttu-id="22ed3-119">Después de recopilar todos los datos relevantes para el caso, el siguiente paso es procesarlo para su posterior revisión y análisis.</span><span class="sxs-lookup"><span data-stu-id="22ed3-119">After you've collected all data relevant to the case, the next step is process it for further review and analysis.</span></span> <span data-ttu-id="22ed3-120">En exhibición de documentos electrónicos avanzada, los datos en sitio que identificó en la fase de colección se copian en una ubicación de Azure Storage (denominada conjunto de revisión), lo que le proporciona una vista estática de los datos de caso.</span><span class="sxs-lookup"><span data-stu-id="22ed3-120">In Advanced eDiscovery, the in-place data that you identified in the collection phase is copied to an Azure Storage location (called a *review set*), which provides you with a static view of the case data.</span></span> 

- <span data-ttu-id="22ed3-121">**Revisar.**</span><span class="sxs-lookup"><span data-stu-id="22ed3-121">**Review.**</span></span> <span data-ttu-id="22ed3-122">Después de agregar datos a un conjunto de revisión, puede ver documentos específicos y ejecutar consultas adicionales para reducir los datos a lo que es más relevante para el caso.</span><span class="sxs-lookup"><span data-stu-id="22ed3-122">After data has been added to a review set, you can view specific documents and run additional queries to reduce the data to what is most relevant to the case.</span></span> <span data-ttu-id="22ed3-123">Además, puede anotar y etiquetar documentos específicos.</span><span class="sxs-lookup"><span data-stu-id="22ed3-123">Also, can annotate and tag specific documents.</span></span>

- <span data-ttu-id="22ed3-124">**Análisis.**</span><span class="sxs-lookup"><span data-stu-id="22ed3-124">**Analysis.**</span></span> <span data-ttu-id="22ed3-125">La exhibición de documentos electrónicos avanzada proporciona una herramienta de análisis integrada que le ayuda a obtener más datos del conjunto de revisión que determine que no es relevante para la investigación.</span><span class="sxs-lookup"><span data-stu-id="22ed3-125">Advanced eDiscovery provides integrated analytics tool that helps you further cull data from the review set that you determine isn't relevant to the investigation.</span></span> <span data-ttu-id="22ed3-126">Además de reducir el volumen de datos relevantes, la exhibición de documentos electrónicos anticipada también le ayuda a ahorrar costos de revisión legal, ya que le permite organizar el contenido para que el proceso de revisión sea más fácil y eficaz.</span><span class="sxs-lookup"><span data-stu-id="22ed3-126">In addition to reducing the volume of relevant data, Advance eDiscovery also helps you save legal review costs by letting you organize content to make the review process easier and more efficient.</span></span>

- <span data-ttu-id="22ed3-127">**Producción** y **presentación.**</span><span class="sxs-lookup"><span data-stu-id="22ed3-127">**Production** and **Presentation.**</span></span> <span data-ttu-id="22ed3-128">Cuando esté listo, puede exportar documentos de un conjunto de revisión para su revisión legal.</span><span class="sxs-lookup"><span data-stu-id="22ed3-128">When you're ready, you can export documents from a review set for legal review.</span></span> <span data-ttu-id="22ed3-129">Puede exportar documentos en su formato nativo o en un formato especificado por EDRM para que se puedan importar a aplicaciones de revisión de terceros.</span><span class="sxs-lookup"><span data-stu-id="22ed3-129">You can export documents in their native format or in an EDRM-specified format so they can be imported into third-party review applications.</span></span>

## <a name="more-information"></a><span data-ttu-id="22ed3-130">Más información</span><span class="sxs-lookup"><span data-stu-id="22ed3-130">More information</span></span>

<span data-ttu-id="22ed3-131">Para empezar a usar eDiscovery avanzada, consulte:</span><span class="sxs-lookup"><span data-stu-id="22ed3-131">To get started using Advanced eDiscovery, see:</span></span>

- [<span data-ttu-id="22ed3-132">Configurar eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="22ed3-132">Set up Advanced eDiscovery</span></span>](get-started-with-advanced-ediscovery.md)

- [<span data-ttu-id="22ed3-133">Crear y administrar un caso de exhibición de documentos electrónicos avanzada</span><span class="sxs-lookup"><span data-stu-id="22ed3-133">Create and manage an Advanced eDiscovery case</span></span>](create-and-manage-advanced-ediscoveryv2-case.md)