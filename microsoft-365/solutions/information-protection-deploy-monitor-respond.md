---
title: Supervisar y responder a incidentes de privacidad de datos en su organización
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Use directivas de auditoría y alertas y solicitudes del interesado para supervisar y responder a incidentes de datos personales.
ms.openlocfilehash: 4070cd772d243bcfba33bfb164fd05e1f0911b3b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928429"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="d6e4f-103">Supervisar y responder a incidentes de privacidad de datos en su organización</span><span class="sxs-lookup"><span data-stu-id="d6e4f-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="d6e4f-104">Microsoft 365 están disponibles para ayudarle a supervisar, investigar y responder a incidentes de privacidad de datos en su organización a medida que opera las capacidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="d6e4f-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="d6e4f-105">Tener procesos, procedimientos y otra documentación para cada uno de ellos también puede ser importante para demostrar el cumplimiento de los organismos reguladores.</span><span class="sxs-lookup"><span data-stu-id="d6e4f-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="d6e4f-106">Entre ellas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="d6e4f-106">These include:</span></span> 

- <span data-ttu-id="d6e4f-107">Directivas de auditoría y alerta</span><span class="sxs-lookup"><span data-stu-id="d6e4f-107">Auditing and alert policies</span></span>
- <span data-ttu-id="d6e4f-108">Solicitudes del interesado (incluida la búsqueda de contenido y la exhibición de documentos electrónicos)</span><span class="sxs-lookup"><span data-stu-id="d6e4f-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="d6e4f-109">Herramientas de investigación e informes adicionales</span><span class="sxs-lookup"><span data-stu-id="d6e4f-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="d6e4f-110">Normativas de privacidad de datos que afectan al uso de herramientas de supervisión y respuesta</span><span class="sxs-lookup"><span data-stu-id="d6e4f-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="d6e4f-111">Esta es una lista de ejemplo de las normativas de privacidad de datos que pueden estar relacionadas con los controles de gobierno de la información:</span><span class="sxs-lookup"><span data-stu-id="d6e4f-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="d6e4f-112">Artículo 46 de LGPD</span><span class="sxs-lookup"><span data-stu-id="d6e4f-112">LGPD Article 46</span></span>
- <span data-ttu-id="d6e4f-113">Artículo 48 de LGPD</span><span class="sxs-lookup"><span data-stu-id="d6e4f-113">LGPD Article 48</span></span>
- <span data-ttu-id="d6e4f-114">Artículo del RGPD (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="d6e4f-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="d6e4f-115">Artículo del RGPD (15)(1)(e)</span><span class="sxs-lookup"><span data-stu-id="d6e4f-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="d6e4f-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="d6e4f-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="d6e4f-117">164.308(a)(1)(ii)(D))</span><span class="sxs-lookup"><span data-stu-id="d6e4f-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="d6e4f-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="d6e4f-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="d6e4f-119">164.308(a)(6)(ii)</span><span class="sxs-lookup"><span data-stu-id="d6e4f-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="d6e4f-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="d6e4f-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="d6e4f-121">164.312(b))</span><span class="sxs-lookup"><span data-stu-id="d6e4f-121">164.312(b))</span></span>
- <span data-ttu-id="d6e4f-122">CCPA (1798.105(c))</span><span class="sxs-lookup"><span data-stu-id="d6e4f-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="d6e4f-123">Para obtener más información, vea [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="d6e4f-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="d6e4f-124">Por lo general, los reglamentos de privacidad de datos piden lo siguiente para la supervisión y respuesta:</span><span class="sxs-lookup"><span data-stu-id="d6e4f-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="d6e4f-125">Auditoría, alerta e informes de actividades relacionadas con el almacenamiento, uso compartido y procesamiento de datos personales</span><span class="sxs-lookup"><span data-stu-id="d6e4f-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="d6e4f-126">La capacidad de responder a una solicitud de interesado (DSR) y, en algunos casos, realizar medidas de investigación y otras medidas administrativas para cumplir con dichas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="d6e4f-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="d6e4f-127">Es posible que su organización también desee realizar actividades de supervisión y respuesta para otros fines, como otras necesidades de cumplimiento o por motivos empresariales.</span><span class="sxs-lookup"><span data-stu-id="d6e4f-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="d6e4f-128">Establecer el esquema de supervisión y respuesta para la privacidad de datos debe realizarse como parte de la planeación, implementación y administración de la supervisión y respuesta generales.</span><span class="sxs-lookup"><span data-stu-id="d6e4f-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="d6e4f-129">Para ayudarle a empezar con un esquema de supervisión y respuesta en Microsoft 365 para las regulaciones de privacidad de datos, en este artículo se enumeran las funcionalidades útiles en Microsoft 365 para responder a preguntas como:</span><span class="sxs-lookup"><span data-stu-id="d6e4f-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="d6e4f-130">¿Qué tipo de técnicas diarias de supervisión, investigación e informes están disponibles para los distintos tipos de datos y orígenes?</span><span class="sxs-lookup"><span data-stu-id="d6e4f-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="d6e4f-131">Qué mecanismos se necesitan para controlar las solicitudes de interesados (DSR) y las acciones correctivas, como anonimización, redacción y eliminación.</span><span class="sxs-lookup"><span data-stu-id="d6e4f-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="d6e4f-132">Auditoría y directivas de alerta en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="d6e4f-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="d6e4f-133">Vea estos artículos para configurar directivas de auditoría, auditoría avanzada y alertas:</span><span class="sxs-lookup"><span data-stu-id="d6e4f-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="d6e4f-134">Auditoría unificada</span><span class="sxs-lookup"><span data-stu-id="d6e4f-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="d6e4f-135">Auditoría de buzones</span><span class="sxs-lookup"><span data-stu-id="d6e4f-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="d6e4f-136">Auditoría avanzada</span><span class="sxs-lookup"><span data-stu-id="d6e4f-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="d6e4f-137">Directivas de alerta</span><span class="sxs-lookup"><span data-stu-id="d6e4f-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="d6e4f-138">Solicitudes del interesado para el RGPD y el CCPA</span><span class="sxs-lookup"><span data-stu-id="d6e4f-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="d6e4f-139">Consulte Solicitudes del interesado para el RGPD y [el CCPA](/compliance/regulatory/gdpr-dsr-Office365) para obtener información sobre cómo responder a un DSR en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6e4f-139">See [Data Subject Requests for the GDPR and CCPA](/compliance/regulatory/gdpr-dsr-Office365) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="d6e4f-140">Administrar usuarios eliminados en Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="d6e4f-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="d6e4f-141">Para Microsoft Stream, cuando se elimina un usuario de Azure Active Directory (Azure AD), si su nombre estaba asociado a un vídeo stream publicado antes de ese punto, su dirección de correo electrónico permanece asociada al vídeo.</span><span class="sxs-lookup"><span data-stu-id="d6e4f-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="d6e4f-142">Consulta [Administrar usuarios eliminados de Microsoft Stream](/stream/managing-deleted-users) para quitarlo.</span><span class="sxs-lookup"><span data-stu-id="d6e4f-142">See [Manage deleted users from Microsoft Stream](/stream/managing-deleted-users) to remove it.</span></span>

## <a name="insider-risk-management-as-an-investigative-tool"></a><span data-ttu-id="d6e4f-143">Administración de riesgos de Insider como herramienta de investigación</span><span class="sxs-lookup"><span data-stu-id="d6e4f-143">Insider risk management as an investigative tool</span></span>

<span data-ttu-id="d6e4f-144">La administración de riesgos de [Insider](../compliance/insider-risk-management.md) en Microsoft 365 es una característica del Centro de administración de Cumplimiento de Microsoft para ayudarle a minimizar los riesgos internos, ya que le permite detectar, investigar y tomar medidas en actividades de riesgo en su organización.</span><span class="sxs-lookup"><span data-stu-id="d6e4f-144">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md) is a feature of the Microsoft Compliance admin center to help you minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>