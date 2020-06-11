---
title: Implementar la protección de la información para las regulaciones de privacidad de datos con Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Configure la infraestructura de seguridad y servicio para proteger su información y cumplir con las regulaciones de privacidad de datos.
ms.openlocfilehash: 35ccfb21accd969c2a2cbdddde9a4ec1c7eeed64
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695115"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a><span data-ttu-id="add75-103">Implementar la protección de la información para las regulaciones de privacidad de datos con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="add75-103">Deploy information protection for data privacy regulations with Microsoft 365</span></span>

<span data-ttu-id="add75-104">Esta solución proporciona instrucciones sobre cómo planear y proteger los datos personales almacenados en los servicios de 365 de Microsoft y, potencialmente, sujetos a normas de privacidad de datos, como el Reglamento General de protección de datos (RGPD) de la Unión Europea.</span><span class="sxs-lookup"><span data-stu-id="add75-104">This solution provides guidance on how to plan for and protect personal data that is stored in Microsoft 365 services and potentially subject to data privacy regulations such as the European Union's General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="add75-105">Esta solución se centra en las características de cumplimiento y protección de la información de Microsoft, la puntuación de cumplimiento de Microsoft y las herramientas de evaluación para ayudarle a conocer sus datos.</span><span class="sxs-lookup"><span data-stu-id="add75-105">This solution focuses on applicable Microsoft information protection and compliance features, Microsoft Compliance Score, and assessment tools to help you know your data.</span></span> 
 
<span data-ttu-id="add75-106">También se proporciona información adicional sobre el uso de controles de identidad de Microsoft, dispositivos y protección contra amenazas para las necesidades de privacidad de datos, así como para las herramientas de detección y respuesta de incidentes de datos.</span><span class="sxs-lookup"><span data-stu-id="add75-106">Additional information is also provided on the use of Microsoft identity, device, and threat protection controls for your data privacy needs, as well as data incident discovery and response tools.</span></span> 

## <a name="organization-of-this-guidance-material"></a><span data-ttu-id="add75-107">Organización de este material de orientación</span><span class="sxs-lookup"><span data-stu-id="add75-107">Organization of this guidance material</span></span>

<span data-ttu-id="add75-108">Para ayudarle a comprender las herramientas de Microsoft 365 disponibles para identificar, administrar, controlar y supervisar los datos personales sujetos a una o más regulaciones relacionadas con la privacidad, esta guía se organiza en secciones.</span><span class="sxs-lookup"><span data-stu-id="add75-108">To help you understand the Microsoft 365 tools available to identify, manage, control, and monitor personal data subject to one or more privacy-related regulations, this guidance is organized into sections.</span></span>
 
![Implementación de protección de la información para las normativas de privacidad de los datos](../media/information-protection-deploy/information-protection-deploy-grid.png)

<span data-ttu-id="add75-110">Cada una de estas secciones corresponde a un artículo independiente en esta solución.</span><span class="sxs-lookup"><span data-stu-id="add75-110">Each of these sections correspond to a separate article in this solution.</span></span>

>[!Note]
><span data-ttu-id="add75-111">Si ya está familiarizado con sus obligaciones de privacidad de datos y se está ejecutando en un plan existente, es posible que quiera centrarse en las instrucciones de prevención, protección, retención e investigación.</span><span class="sxs-lookup"><span data-stu-id="add75-111">If you are already familiar with your data privacy obligations and are executing against an existing plan, you may want to focus on the Prevent, Protect, Retain, and Investigate guidance.</span></span>

>[!Important]
><span data-ttu-id="add75-112">Seguir esta guía no necesariamente hará que cumpla con ninguna normativa de privacidad de datos, especialmente teniendo en cuenta el número de pasos necesarios que se encuentran fuera del contexto de las características.</span><span class="sxs-lookup"><span data-stu-id="add75-112">Following this guidance will not necessarily make you compliant with any data privacy regulation, especially considering the number of steps required that are outside the context of the features.</span></span> <span data-ttu-id="add75-113">Usted es responsable de garantizar su cumplimiento y de consultar a sus equipos legales y de cumplimiento, o bien buscar orientación y consejos de terceros que se especializan en el cumplimiento de las normas.</span><span class="sxs-lookup"><span data-stu-id="add75-113">You are responsible for ensuring your compliance and to consult your legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a><span data-ttu-id="add75-114">Planeación: evaluación de los riesgos de privacidad de datos e identificación de elementos confidenciales</span><span class="sxs-lookup"><span data-stu-id="add75-114">Plan: Assess data privacy risks and identify sensitive items</span></span> 

<span data-ttu-id="add75-115">La evaluación de los riesgos y las regulaciones de privacidad de datos a los que está sujeta su organización es un primer paso clave antes de empezar a implementar mejoras, incluidas las que se pueden obtener a través de la configuración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="add75-115">Assessing data privacy regulations and risks that your organization is subject to is a key first step to take before starting to implement improvements, including those achievable through Microsoft 365 configuration.</span></span> <span data-ttu-id="add75-116">Esto puede incluir una evaluación general de la preparación o la identificación de los tipos de información confidencial que están sujetos a controles normativos que la organización debe cumplir, así como la ocurrencia de los mismos en el entorno de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="add75-116">This may include an overall readiness assessment or identification of particular sensitive information types that are subject to regulatory controls your organization needs to comply with, as well as the occurrence of them in your Microsoft 365 environment.</span></span>

<span data-ttu-id="add75-117">Para obtener más información, vea [evaluar los riesgos de privacidad de datos e identificar elementos confidenciales](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="add75-117">For more information, see [Assess data privacy risks and identify sensitive items](information-protection-deploy-assess.md).</span></span>

## <a name="track-use-compliance-score-and-compliance-manager"></a><span data-ttu-id="add75-118">Seguir: usar la puntuación de cumplimiento y el administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="add75-118">Track: Use Compliance Score and Compliance Manager</span></span> 

<span data-ttu-id="add75-119">La puntuación de cumplimiento y el administrador de cumplimiento proporcionan un conjunto integrado de herramientas disponibles en el centro de administración de cumplimiento de Microsoft 365 y en el portal de confianza de servicios.</span><span class="sxs-lookup"><span data-stu-id="add75-119">Compliance Score and Compliance Manager provide an integrated set of tools available in the Microsoft 365 Compliance admin center and Services Trust Portal.</span></span> <span data-ttu-id="add75-120">Juntas, estas herramientas le proporcionan una capacidad integrada para realizar un seguimiento de las acciones de mejora y administrarlas en todo el conjunto, así como las relacionadas con las diversas regulaciones de privacidad de datos a las que está sometido.</span><span class="sxs-lookup"><span data-stu-id="add75-120">Together, these tools provide you with a built-in ability to track and manage improvement actions overall as well as those related to multiple data privacy regulations to which you are subjected.</span></span>

<span data-ttu-id="add75-121">Las herramientas también le permiten aprovechar las plantillas de evaluación integradas específicas de cada reglamentación, donde puede realizar un seguimiento de los elementos de acción para cada plantilla de evaluación seleccionada, así como ver los controles reguladores específicos y relacionarlos con acciones específicas.</span><span class="sxs-lookup"><span data-stu-id="add75-121">The tools also allow you to leverage built in assessment templates specific to each regulation, where you can track action items for each assessment template selected, as well as view specific regulatory controls, and relate them to specific actions.</span></span>

<span data-ttu-id="add75-122">Para obtener más información, consulte [usar la puntuación de cumplimiento y el administrador de cumplimiento para administrar las acciones de mejora](information-protection-deploy-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="add75-122">For more information, see [Use Compliance Score and Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).</span></span>

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="add75-123">Evitar: usar la identidad, el dispositivo y la protección contra amenazas para la privacidad de la privacidad de los datos</span><span class="sxs-lookup"><span data-stu-id="add75-123">Prevent: Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="add75-124">Microsoft 365 proporciona una serie de capacidades de identidad, dispositivo y protección contra amenazas que puede usar para cumplir con el cumplimiento de las normas de privacidad de los datos.</span><span class="sxs-lookup"><span data-stu-id="add75-124">Microsoft 365 provides a number of identity, device, and threat protection capabilities that you can use to help comply with data privacy regulatory compliance.</span></span> 

<span data-ttu-id="add75-125">Para obtener más información, consulte [usar identidad, dispositivo y protección contra amenazas para la normativa de privacidad de datos](information-protection-deploy-identity-device-threat.md).</span><span class="sxs-lookup"><span data-stu-id="add75-125">For more information, see [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).</span></span>

<span data-ttu-id="add75-126">En este artículo se describen brevemente las necesidades de privacidad de los datos por lo general en estas áreas y se proporciona una lista de soluciones de Microsoft 365 relacionadas, con vínculos a más información para ayudarle a solucionar los requisitos de implementación.</span><span class="sxs-lookup"><span data-stu-id="add75-126">This article briefly describes what the data privacy regulations generally call for in these areas and provides a listing of related Microsoft 365 solutions, with links to more information to help you address any implementation requirements.</span></span> 

## <a name="protect-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="add75-127">Proteger la información sujeta a la normativa de privacidad de datos</span><span class="sxs-lookup"><span data-stu-id="add75-127">Protect information subject to data privacy regulation</span></span>

<span data-ttu-id="add75-128">Las regulaciones de privacidad de datos establecen una serie de controles de protección de información personal que se pueden usar en su entorno, incluidos más que 40 proteger los controles de la información a través de las cuatro normas de privacidad de datos en nuestro conjunto de ejemplo de RGPD, California Consumer Protection Act (CCPA), HIPAA-Technology (Act de Sanidad de salud de Estados Unidos) y la ley de protección de datos</span><span class="sxs-lookup"><span data-stu-id="add75-128">Data privacy regulations dictate a number of personal information protection controls that can be employed in your environment, including more than forty Protect Information controls across just the four data privacy regulations in our sample set of GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="add75-129">Para obtener más información, consulte [proteger la información sujeta a la normativa de privacidad de datos en la organización](information-protection-deploy-protect-information.md).</span><span class="sxs-lookup"><span data-stu-id="add75-129">For more information, see [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).</span></span>

<span data-ttu-id="add75-130">En este artículo se presentan los principales esquemas de control que se pueden usar para tratar las necesidades de protección de la información para la privacidad de los datos en la organización.</span><span class="sxs-lookup"><span data-stu-id="add75-130">This article lays out the main control schemes that can be used for addressing information protection needs for data privacy in your organization.</span></span>

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="add75-131">Retain: controle la información sujeta a la normativa de privacidad de datos</span><span class="sxs-lookup"><span data-stu-id="add75-131">Retain: Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="add75-132">Normas de privacidad de datos llame a los controles de gobierno de información personal que se pueden usar en su entorno, incluidos más de veinte controles en las cuatro normas de privacidad de datos en nuestro conjunto de ejemplo de RGPD, CCPA, HIPAA-tecnología y LGPD.</span><span class="sxs-lookup"><span data-stu-id="add75-132">Data privacy regulations call for personal information governance controls that can be employed in your environment, including more than twenty-four controls across the four data privacy regulations in our sample set of GDPR, CCPA, HIPAA-HITECH, and LGPD.</span></span>

<span data-ttu-id="add75-133">Para obtener más información, consulte [regir la información sujeta a la normativa de privacidad de datos en su organización](information-protection-deploy-govern.md).</span><span class="sxs-lookup"><span data-stu-id="add75-133">For more information, see [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).</span></span>

<span data-ttu-id="add75-134">Aunque las regulaciones de privacidad de datos pueden ser imprecisas para el gobierno de la información, como la &mdash; retención con fines, la eliminación y el archivado &mdash; en este artículo se presentan los principales esquemas de control que se pueden usar para satisfacer la privacidad de los datos en la organización.</span><span class="sxs-lookup"><span data-stu-id="add75-134">While the data privacy regulations can be vague regarding information governance&mdash;such as purposeful retention, deletion and archiving&mdash;this article lays out the primary control schemes that you can use address information governance needs for data privacy in your organization.</span></span>

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a><span data-ttu-id="add75-135">Investigar: supervisar y responder sujeto a la normativa de privacidad de datos</span><span class="sxs-lookup"><span data-stu-id="add75-135">Investigate: Monitor and respond subject to data privacy regulation</span></span>

<span data-ttu-id="add75-136">Hay disponibles características de Microsoft 365 para ayudarle a supervisar, investigar y responder a los incidentes de privacidad de los datos de su organización a medida que opera las capacidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="add75-136">There are Microsoft 365 features available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> 

<span data-ttu-id="add75-137">Tener procesos, procedimientos y otra documentación para cada uno de ellos puede ser importante para demostrar el cumplimiento de los organismos reguladores.</span><span class="sxs-lookup"><span data-stu-id="add75-137">Having processes, procedures, and other documentation for each of these can be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="add75-138">Para obtener más información, vea [supervisar y responder a incidentes de privacidad de datos en la organización](information-protection-deploy-monitor-respond.md).</span><span class="sxs-lookup"><span data-stu-id="add75-138">For more information, see [Monitor and respond to data privacy incidents in your organization](information-protection-deploy-monitor-respond.md).</span></span>
