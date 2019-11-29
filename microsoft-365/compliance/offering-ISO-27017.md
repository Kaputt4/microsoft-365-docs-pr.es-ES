---
title: Código de prácticas para los controles de la seguridad de la información ISO/IEC 27017:2015
description: Los servicios en la nube de Microsoft han implementado este código de prácticas para los controles de seguridad de la información.
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
ms.openlocfilehash: 6002637496cfa01bc7b14ad29069493e45142c33
ms.sourcegitcommit: b2197dbf723d11992bbad568a84df3ef3cff421d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "39625320"
---
# <a name="compliance-offering-isoiec-270172015-code-of-practice-for-information-security-controls"></a><span data-ttu-id="927b8-104">Oferta de cumplimiento: Código de prácticas para los controles de la seguridad de la información ISO/IEC 27017:2015</span><span class="sxs-lookup"><span data-stu-id="927b8-104">Compliance offering: ISO/IEC 27017:2015 Code of Practice for Information Security Controls</span></span>

## <a name="iso-iec-27017-overview"></a><span data-ttu-id="927b8-105">Introducción a la norma ISO-IEC 27017</span><span class="sxs-lookup"><span data-stu-id="927b8-105">ISO-IEC 27017 Overview</span></span>

<span data-ttu-id="927b8-106">El código de prácticas ISO/IEC 27017:2015 está diseñado para que las organizaciones lo usen como referencia para seleccionar controles de seguridad de la información de servicios en la nube al implementar un sistema de administración de seguridad de la información de informática en la nube basado en la norma ISO/IEC 27002:2013.</span><span class="sxs-lookup"><span data-stu-id="927b8-106">The ISO/IEC 27017:2015 code of practice is designed for organizations to use as a reference for selecting cloud services information security controls when implementing a cloud computing information security management system based on ISO/IEC 27002:2013.</span></span> <span data-ttu-id="927b8-107">Los proveedores de servicios en la nube también pueden usar este documento como guía para implementar controles de protección comúnmente aceptados.</span><span class="sxs-lookup"><span data-stu-id="927b8-107">It can also be used by cloud service providers as a guidance document for implementing commonly accepted protection controls.</span></span>

<span data-ttu-id="927b8-108">Este estándar internacional proporciona instrucciones adicionales para las implementaciones específicas para la nube basadas en la norma ISO/IEC 27002, así como controles adicionales para abordar los riesgos y las amenazas de seguridad de la información específicos de la nube que hacen referencia a las cláusulas 5 a 18 de la norma ISO/IEC 27002:2013 sobre controles, instrucciones de implementación y otra información.</span><span class="sxs-lookup"><span data-stu-id="927b8-108">This international standard provides additional cloud-specific implementation guidance based on ISO/IEC 27002, and provides additional controls to address cloud-specific information security threats and risks referring to clauses 5–18 in ISO/IEC 27002: 2013 for controls, implementation guidance, and other information.</span></span> <span data-ttu-id="927b8-109">En concreto, en este estándar se proporcionan instrucciones sobre 37 controles de la norma ISO/IEC 27002, además de siete nuevos controles que no se encuentran en la ISO/IEC 27002.</span><span class="sxs-lookup"><span data-stu-id="927b8-109">Specifically, this standard provides guidance on 37 controls in ISO/IEC 27002, and it also features seven new controls that are not duplicated in ISO/IEC 27002.</span></span> <span data-ttu-id="927b8-110">Estos nuevos controles abordan las siguientes áreas de importancia:</span><span class="sxs-lookup"><span data-stu-id="927b8-110">These new controls address the following important areas:</span></span>

- <span data-ttu-id="927b8-111">Roles y responsabilidades compartidos en un entorno informático en la nube</span><span class="sxs-lookup"><span data-stu-id="927b8-111">Shared roles and responsibilities within a cloud computing environment</span></span>
- <span data-ttu-id="927b8-112">Eliminación y devolución de los activos de los clientes del servicio en la nube una vez que finaliza el contrato</span><span class="sxs-lookup"><span data-stu-id="927b8-112">Removal and return of cloud service customer assets upon contract termination</span></span>
- <span data-ttu-id="927b8-113">Protección y separación del entorno virtual de un cliente de los de otros clientes</span><span class="sxs-lookup"><span data-stu-id="927b8-113">Protection and separation of a customer’s virtual environment from that of other customers</span></span>
- <span data-ttu-id="927b8-114">Requisitos de refuerzo de las máquinas virtuales para satisfacer las necesidades de la empresa</span><span class="sxs-lookup"><span data-stu-id="927b8-114">Virtual machine hardening requirements to meet business needs</span></span>
- <span data-ttu-id="927b8-115">Procedimientos para las operaciones administrativas de un entorno informático en la nube</span><span class="sxs-lookup"><span data-stu-id="927b8-115">Procedures for administrative operations of a cloud computing environment</span></span>
- <span data-ttu-id="927b8-116">Permitir a los clientes supervisar las actividades pertinentes en un entorno informático en la nube</span><span class="sxs-lookup"><span data-stu-id="927b8-116">Enabling customers to monitor relevant activities within a cloud computing environment</span></span>
- <span data-ttu-id="927b8-117">Alineación de la administración de seguridad de las redes virtuales y físicas</span><span class="sxs-lookup"><span data-stu-id="927b8-117">Alignment of security management for virtual and physical networks</span></span>

## <a name="microsoft-and-isoiec-27017"></a><span data-ttu-id="927b8-118">Microsoft y la norma ISO/IEC 27017</span><span class="sxs-lookup"><span data-stu-id="927b8-118">Microsoft and ISO/IEC 27001</span></span>

<span data-ttu-id="927b8-119">La ISO/IEC 27017 es única en cuanto a que proporciona instrucciones tanto para los proveedores de servicios en la nube como para los clientes de servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="927b8-119">ISO/IEC 27017 is unique in providing guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="927b8-120">También proporciona a los clientes de servicios en la nube información práctica sobre lo que deben esperar de los proveedores de servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="927b8-120">It also provides cloud service customers with practical information on what they should expect from cloud service providers.</span></span> <span data-ttu-id="927b8-121">Los clientes pueden beneficiarse directamente de la ISO/IEC 27017, ya que les permitirá comprender las responsabilidades compartidas en la nube.</span><span class="sxs-lookup"><span data-stu-id="927b8-121">Customers can benefit directly from ISO/IEC 27017 by ensuring they understand the shared responsibilities in the cloud.</span></span>

<span data-ttu-id="927b8-122">Obtenga más información acerca de las ventajas de la norma ISO/IEC 27017 en la nube de Microsoft: [Descargar el Código de prácticas para los controles de la seguridad de la información ISO/IEC 27017](https://aka.ms/iso27017-backgrounder)</span><span class="sxs-lookup"><span data-stu-id="927b8-122">Learn about the benefits of ISO/IEC 27017 on the Microsoft Cloud: [Download the ISO/IEC 27017: Code of Practice for Information Security Controls](https://aka.ms/iso27017-backgrounder)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="927b8-123">Servicios de nube de Microsoft dentro de ámbito</span><span class="sxs-lookup"><span data-stu-id="927b8-123">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="927b8-124">Azure, Azure Government y Azure Alemania</span><span class="sxs-lookup"><span data-stu-id="927b8-124">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="927b8-125">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="927b8-125">Cloud App Security</span></span>
- [<span data-ttu-id="927b8-126">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="927b8-126">Dynamics 365</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="927b8-127">Genomics</span><span class="sxs-lookup"><span data-stu-id="927b8-127">Genomics</span></span>
- <span data-ttu-id="927b8-128">Graph</span><span class="sxs-lookup"><span data-stu-id="927b8-128">Graph</span></span>
- <span data-ttu-id="927b8-129">Intune</span><span class="sxs-lookup"><span data-stu-id="927b8-129">Intune</span></span>
- <span data-ttu-id="927b8-130">El servicio de nube de Microsoft Flow como un servicio independiente o incluido en un plan o un conjunto de aplicaciones de Office 365 o Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="927b8-130">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="927b8-131">Office 365, Office 365 Administración Pública para Estados Unidos, Office 365 U.S. Government Defense y Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="927b8-131">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense</span></span>
- <span data-ttu-id="927b8-132">El servicio de nube de PowerApps como servicio independiente o incluido en un plan o conjunto de aplicaciones de Office 365 o Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="927b8-132">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="927b8-133">El servicio de nube de Power BI como servicio independiente o incluido en un plan o conjunto de aplicaciones de Office 365</span><span class="sxs-lookup"><span data-stu-id="927b8-133">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="927b8-134">Vea una [lista detallada](https://go.microsoft.com/fwlink/p/?linkid=2077751) de los servicios cubiertos en Office 365</span><span class="sxs-lookup"><span data-stu-id="927b8-134">See a [detailed list](https://go.microsoft.com/fwlink/p/?linkid=2077751) of covered services in Office 365</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="927b8-135">Auditorías, informes y certificados</span><span class="sxs-lookup"><span data-stu-id="927b8-135">Audits, reports, and certificates</span></span>

<span data-ttu-id="927b8-136">Los servicios en la nube de Microsoft se auditan una vez al año para certificar que cumplen el código de prácticas de la norma ISO/IEC 27017:2015 como parte del proceso de certificación de la ISO/IEC 27001:2013.</span><span class="sxs-lookup"><span data-stu-id="927b8-136">Microsoft cloud and commercial technical support services are audited once a year for the ISO/IEC 27018 code of practice as part of the certification process for ISO/IEC 27001.</span></span>

- [<span data-ttu-id="927b8-137">Certificado de Azure ISO 27017</span><span class="sxs-lookup"><span data-stu-id="927b8-137">Azure ISO 27017 Certificate</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078005)
- [<span data-ttu-id="927b8-138">Informe de evaluación de Azure ISO 27017</span><span class="sxs-lookup"><span data-stu-id="927b8-138">Azure ISO 27017 Assessment report</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078010)
- [<span data-ttu-id="927b8-139">Estado de aplicabilidad de Azure ISO 27017</span><span class="sxs-lookup"><span data-stu-id="927b8-139">Azure ISO 27017 Statement of Applicability</span></span>](https://aka.ms/azureiso27017StatementofApplicability)
- [<span data-ttu-id="927b8-140">Office 365: Informe de evaluación de auditoría de las ISO 27001, 27018 y 27017</span><span class="sxs-lookup"><span data-stu-id="927b8-140">Office 365 — ISO 27001, ISO 27018, and ISO 27017 Audit Assessment Report</span></span>](https://aka.ms/o365isoreport)

## <a name="frequently-asked-questions"></a><span data-ttu-id="927b8-141">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="927b8-141">Frequently asked questions</span></span>

<span data-ttu-id="927b8-142">¿A quién se aplica la norma?</span><span class="sxs-lookup"><span data-stu-id="927b8-142">To whom does the standard apply?</span></span>

<span data-ttu-id="927b8-143">Este código de prácticas proporciona controles e instrucciones de implementación tanto para los clientes de servicios en la nube como para los proveedores de servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="927b8-143">This code of practice provides controls and implementation guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="927b8-144">Está estructurado en un formato similar al de la norma ISO 27002:2013.</span><span class="sxs-lookup"><span data-stu-id="927b8-144">It is structured in a format similar to ISO/IEC 27002:2013.</span></span>

<span data-ttu-id="927b8-145">**¿Dónde puedo ver la información de cumplimiento normativo de Microsoft para la norma ISO/IEC 27017:2015?**</span><span class="sxs-lookup"><span data-stu-id="927b8-145">**Where can I view Microsoft compliance information for ISO/IEC 27018?**</span></span>

<span data-ttu-id="927b8-146">Puede descargar el [certificado ISO/IEC 27017:2015](https://aka.ms/azureiso27017) para Azure, Intune y Power BI.</span><span class="sxs-lookup"><span data-stu-id="927b8-146">You can download the [ISO/IEC 27017:2015 certificate](https://aka.ms/azureiso27017) for Azure, Intune, and Power BI.</span></span>

<span data-ttu-id="927b8-147">**¿Puedo usar el cumplimiento de la norma ISO/IEC 27017 de los servicios Microsoft en el proceso de certificación de mi organización?**</span><span class="sxs-lookup"><span data-stu-id="927b8-147">**Can I use the ISO/IEC 27001 compliance of Microsoft services in my organization’s certification?**</span></span>

<span data-ttu-id="927b8-148">Sí.</span><span class="sxs-lookup"><span data-stu-id="927b8-148">Yes.</span></span> <span data-ttu-id="927b8-149">Si su empresa desea obtener una certificación para las implementaciones desarrolladas en cualquiera de los servicios empresariales en la nube incluidos en el ámbito de Microsoft, puede usar las certificaciones correspondientes de Microsoft en la evaluación de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="927b8-149">If your business is seeking certification for implementations deployed on any Microsoft in-scope enterprise cloud services, you can use Microsoft’s relevant certifications in your compliance assessment.</span></span> <span data-ttu-id="927b8-150">Sin embargo, usted tiene la responsabilidad de contratar un asesor para evaluar la implementación para el cumplimiento normativo y los controles y procesos de su propia organización.</span><span class="sxs-lookup"><span data-stu-id="927b8-150">However, you are responsible for engaging an assessor to evaluate your implementation for compliance, and for the controls and processes within your own organization.</span></span>

<span data-ttu-id="927b8-151">**¿Cómo puedo obtener copias de los informes de auditoría aplicables?**</span><span class="sxs-lookup"><span data-stu-id="927b8-151">**How can I get copies of the SOC reports?**</span></span>

<span data-ttu-id="927b8-152">En el [Portal de confianza de servicios](https://aka.ms/stphelp) encontrará informes de auditoría independientes de terceros y otros documentos relacionados.</span><span class="sxs-lookup"><span data-stu-id="927b8-152">The [Service Trust Portal](https://aka.ms/stphelp) provides independent, third-party audit reports and other related documentation.</span></span> <span data-ttu-id="927b8-153">Puede usar el portal para descargar y revisar esa documentación para obtener ayuda con sus propios requisitos normativos.</span><span class="sxs-lookup"><span data-stu-id="927b8-153">You can use the portal to download and review this documentation for assistance with your own regulatory requirements.</span></span>

## <a name="resources"></a><span data-ttu-id="927b8-154">Recursos</span><span class="sxs-lookup"><span data-stu-id="927b8-154">Resources</span></span>

- [<span data-ttu-id="927b8-155">Código de prácticas de la norma ISO/IEC 27017:2015</span><span class="sxs-lookup"><span data-stu-id="927b8-155">ISO/IEC 27017:2015 code of practice</span></span>](https://www.iso.org/iso/iso_catalogue/catalogue_tc/catalogue_detail.htm?csnumber=43757)
- [<span data-ttu-id="927b8-156">Términos de Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="927b8-156">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="927b8-157">Cumplimiento normativo en el Centro de confianza de Microsoft</span><span class="sxs-lookup"><span data-stu-id="927b8-157">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="927b8-158">Descargar el documento de información general de la oferta</span><span class="sxs-lookup"><span data-stu-id="927b8-158">Download the offering backgrounder</span></span>

<span data-ttu-id="927b8-159">¿Necesita el documento de información general de esta oferta?</span><span class="sxs-lookup"><span data-stu-id="927b8-159">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="927b8-160">Descargue el [PDF](https://download.microsoft.com/download/7/7/9/7799D02B-A97A-48E0-A057-C19DD543BB24/ISO-IEC-27017_backgrounder.pdf).</span><span class="sxs-lookup"><span data-stu-id="927b8-160">Download the [PDF](https://download.microsoft.com/download/7/7/9/7799D02B-A97A-48E0-A057-C19DD543BB24/ISO-IEC-27017_backgrounder.pdf).</span></span>
