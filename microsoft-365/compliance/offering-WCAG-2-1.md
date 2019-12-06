---
title: Pautas de accesibilidad al contenido en la web 2.1
description: Microsoft publica informes WCAG 2.1 AA que reflejan el producto o el servicio completo, o partes del producto que pueden ser instalados por separado.
keywords: Microsoft 365, cumplimiento, ofertas
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: a1887bd2b6c04836ebb11d224fcc59debcd88e55
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859450"
---
# <a name="web-content-accessibility-guidelines-21"></a><span data-ttu-id="820be-104">Pautas de accesibilidad al contenido en la web 2.1</span><span class="sxs-lookup"><span data-stu-id="820be-104">Web Content Accessibility Guidelines 2.1</span></span>

## <a name="about-wcag-21"></a><span data-ttu-id="820be-105">Acerca de WCAG 2.1</span><span class="sxs-lookup"><span data-stu-id="820be-105">About WCAG 2.1</span></span>

<span data-ttu-id="820be-106">WCAG 2.1 proporciona un marco para el desarrollo de contenido web que mejora la accesibilidad para personas con discapacidad, además de hacerlo para los usuarios de dispositivos con capacidades gráficas limitadas.</span><span class="sxs-lookup"><span data-stu-id="820be-106">WCAG 2.1 provides a framework for developing web content that improves accessibility for people with disabilities, in addition to users of devices with limited graphical abilities.</span></span> <span data-ttu-id="820be-107">WCAG 2.0 fue publicada en 2008 por el World Wide Web Consortium (W3C), una organización internacional dedicada a la creación de estándares web, y actualizada a WCAG 2.1 el 1 de junio de 2018.</span><span class="sxs-lookup"><span data-stu-id="820be-107">WCAG 2.0 was published in 2008 by the World Wide Web Consortium (W3C), an international organization dedicated to creating web standards, and updated to WCAG 2.1 in June 2018.</span></span> <span data-ttu-id="820be-108">En 2012, la WCAG 2.0 también fue publicada por la Organización internacional de normalización (ISO) bajo el nombre de ISO/IEC 40500:2012.</span><span class="sxs-lookup"><span data-stu-id="820be-108">In 2012, WCAG 2.0 was also published by the International Organization for Standardization (ISO) as ISO/IEC 40500:2012.</span></span>  
  
<span data-ttu-id="820be-109">El contenido que se ajusta a WCAG 2.1 también cumple con WCAG 2.0.</span><span class="sxs-lookup"><span data-stu-id="820be-109">Content that conforms to WCAG 2.1 also conforms to WCAG 2.0.</span></span> <span data-ttu-id="820be-110">Para las directivas que exigen la conformidad con WCAG 2.0, la WCAG 2.1 puede ofrecer un medio alternativo de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="820be-110">For policies requiring conformance to WCAG 2.0, WCAG 2.1 can provide an alternate means of conformance.</span></span>  
  
<span data-ttu-id="820be-111">Los requisitos de conformidad para cada guía se miden en tres niveles: A, AA y AAA.</span><span class="sxs-lookup"><span data-stu-id="820be-111">Conformance requirements for each guideline are measured in three levels: A, AA, and AAA.</span></span> <span data-ttu-id="820be-112">Dado que Microsoft es uno de los proveedores principales de servicios en la nube y software para los países y gobiernos de todo el mundo, se compromete a cumplir con todos los [estándares internacionales y controles de cumplimiento normativo](https://go.microsoft.com/fwlink/p/?linkid=2052226) relevantes.</span><span class="sxs-lookup"><span data-stu-id="820be-112">Because Microsoft is a major software and cloud-services provider to states and governments around the world, it is committed to complying with all relevant [international standards and compliance controls](https://go.microsoft.com/fwlink/p/?linkid=2052226).</span></span> <span data-ttu-id="820be-113">Al ceñirse a estos estándares de accesibilidad amplios, Microsoft garantiza que todos los clientes (tanto dentro como fuera de la administración pública) puedan usar los servicios y productos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="820be-113">By adhering to these wide-ranging accessibility standards, Microsoft ensures that all customers — both inside and outside of government — can use Microsoft services and products.</span></span>  

## <a name="microsoft-and-wcag-21"></a><span data-ttu-id="820be-114">Microsoft y la WCAG 2.1</span><span class="sxs-lookup"><span data-stu-id="820be-114">Microsoft and WCAG 2.1</span></span>

<span data-ttu-id="820be-115">El cumplimiento de Microsoft a los estándares de WCAG 2.1 (ISO/IEC 40500) apunta al compromiso de hacer que la tecnología y los datos sean accesibles para todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="820be-115">Microsoft’s adherence to the WCAG 2.1 (ISO/IEC 40500) standard points to its commitment to making technology and data accessible for all customers.</span></span> <span data-ttu-id="820be-116">WCAG 2.1 (ISO/IEC 40500) es el requisito de accesibilidad internacional que complementa a EN 301 549 (Europa) y a la sección 508. (Estados Unidos).</span><span class="sxs-lookup"><span data-stu-id="820be-116">WCAG 2.1 (ISO/IEC 40500) is the international accessibility requirement that complements EN 301 549 (Europe) and Section 508 (U.S.).</span></span>  
  
<span data-ttu-id="820be-117">Microsoft publica informes WCAG 2.1 que reflejan el producto o servicio completo.</span><span class="sxs-lookup"><span data-stu-id="820be-117">Microsoft publishes WCAG 2.1 reports that reflect the complete product or service.</span></span> <span data-ttu-id="820be-118">Por lo general, no se crean informes para componentes o características individuales.</span><span class="sxs-lookup"><span data-stu-id="820be-118">It generally does not create reports for individual features or components.</span></span> <span data-ttu-id="820be-119">A veces, Microsoft puede publicar un nuevo componente para un producto existente, o una nueva versión de un componente existente, que los usuarios pueden elegir instalar por separado, y Microsoft también puede publicar un informe WCAG 2.1 para ese componente.</span><span class="sxs-lookup"><span data-stu-id="820be-119">Sometimes, Microsoft might release a new component for an existing product, or a new version of an existing component, which users can choose to install separately, and Microsoft might also publish a WCAG 2.1 report for that component.</span></span>  
  
[<span data-ttu-id="820be-120">Descargar los estándares de accesibilidad WCAG 2.1 (ISO/IEC 40500)</span><span class="sxs-lookup"><span data-stu-id="820be-120">Download the WCAG 2.1 (ISO/IEC 40500) accessibility standards</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2052226)

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="820be-121">Servicios de la nube dentro del alcance de Microsoft</span><span class="sxs-lookup"><span data-stu-id="820be-121">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="820be-122">Azure y Azure Government</span><span class="sxs-lookup"><span data-stu-id="820be-122">Azure and Azure Government</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2051569)
- <span data-ttu-id="820be-123">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="820be-123">Azure DevOps Services</span></span>
- <span data-ttu-id="820be-124">Dynamics 365 y Dynamics 365 para la Administración Pública de Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="820be-124">Dynamics 365 and Dynamics 365 U.S. Government</span></span>
- <span data-ttu-id="820be-125">Intune</span><span class="sxs-lookup"><span data-stu-id="820be-125">Intune</span></span>
- <span data-ttu-id="820be-126">Office 365 y Office 365 para las Administraciones públicas de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="820be-126">Office 365 and Office 365 U.S. Government</span></span>
- <span data-ttu-id="820be-127">Office 365 U.S. Government Defense</span><span class="sxs-lookup"><span data-stu-id="820be-127">Office 365 U.S. Government Defense</span></span>
- <span data-ttu-id="820be-128">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="820be-128">Windows Server 2016</span></span>

## <a name="microsoft-accessibility-conformance-reports"></a><span data-ttu-id="820be-129">Informes de conformidad de la accesibilidad de Microsoft</span><span class="sxs-lookup"><span data-stu-id="820be-129">Microsoft accessibility conformance reports</span></span>

<span data-ttu-id="820be-130">Obtenga informes WCAG para todos nuestros productos y servicios.</span><span class="sxs-lookup"><span data-stu-id="820be-130">Find WCAG reports for all our products and services.</span></span>

[<span data-ttu-id="820be-131">**Más información**</span><span class="sxs-lookup"><span data-stu-id="820be-131">**Learn more**</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2050974)

## <a name="resources"></a><span data-ttu-id="820be-132">Recursos</span><span class="sxs-lookup"><span data-stu-id="820be-132">Resources</span></span>

<span data-ttu-id="820be-133">[Sitio de accesibilidad de Microsoft: obtenga información sobre el uso de las características de accesibilidad y descubra las formas en que Microsoft innova para ayudar a los usuarios a lograr más.</span><span class="sxs-lookup"><span data-stu-id="820be-133">[Microsoft accessibility site — Get information on using accessibility features and explore the ways Microsoft innovates to help everyone achieve more.</span></span>

[<span data-ttu-id="820be-134">Centro de accesibilidad de Office 365</span><span class="sxs-lookup"><span data-stu-id="820be-134">Office 365 Accessibility Center</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2051801)
    - <span data-ttu-id="820be-135">Recursos de Office 365 para personas con discapacidad.</span><span class="sxs-lookup"><span data-stu-id="820be-135">Office 365 resources for people with disabilities.</span></span>

[<span data-ttu-id="820be-136">Answer Desk Accesibilidad Empresarial</span><span class="sxs-lookup"><span data-stu-id="820be-136">Enterprise Disability Answer Desk</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2050890)
    - <span data-ttu-id="820be-137">Soporte técnico especializado para los clientes empresariales con preguntas sobre la accesibilidad de nuestros productos y servicios o nuestro cumplimiento normativo.</span><span class="sxs-lookup"><span data-stu-id="820be-137">Dedicated support for enterprise customers with accessibility questions about our products and services or compliance.</span></span>

[<span data-ttu-id="820be-138">Cumplimiento en el centro de confianza de Microsoft </span><span class="sxs-lookup"><span data-stu-id="820be-138">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="820be-139">Descargar el documento de información general de la oferta</span><span class="sxs-lookup"><span data-stu-id="820be-139">Download the offering backgrounder</span></span>

<span data-ttu-id="820be-140">¿Necesita el documento de información general de esta oferta?</span><span class="sxs-lookup"><span data-stu-id="820be-140">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="820be-141">Descargue el [PDF](https://download.microsoft.com/download/3/E/1/3E10CC43-036D-4DB5-ACBA-8665A752C8F7/Accessibility-Compliance.pdf).</span><span class="sxs-lookup"><span data-stu-id="820be-141">Download the [PDF](https://download.microsoft.com/download/3/E/1/3E10CC43-036D-4DB5-ACBA-8665A752C8F7/Accessibility-Compliance.pdf).</span></span>
