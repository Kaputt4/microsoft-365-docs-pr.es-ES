---
title: Supervisar y responder a los incidentes de privacidad de los datos de la organización
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
description: Use las directivas de auditoría y alerta y las solicitudes de sujetos de datos para supervisar y responder a los incidentes de datos personales.
ms.openlocfilehash: 5760bb40eb26e2ff0636ea9604cc7c45b7d0ca63
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695072"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="0c5d9-103">Supervisar y responder a los incidentes de privacidad de los datos de la organización</span><span class="sxs-lookup"><span data-stu-id="0c5d9-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="0c5d9-104">Las características de Microsoft 365 están disponibles para ayudarle a supervisar, investigar y responder a los incidentes de privacidad de los datos de su organización a medida que opera las capacidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="0c5d9-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="0c5d9-105">Tener procesos, procedimientos y otra documentación para cada uno de ellos también puede ser importante para demostrar el cumplimiento de los organismos reguladores.</span><span class="sxs-lookup"><span data-stu-id="0c5d9-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="0c5d9-106">Entre ellos se incluyen:</span><span class="sxs-lookup"><span data-stu-id="0c5d9-106">These include:</span></span> 

- <span data-ttu-id="0c5d9-107">Directivas de auditoría y alerta</span><span class="sxs-lookup"><span data-stu-id="0c5d9-107">Auditing and alert policies</span></span>
- <span data-ttu-id="0c5d9-108">Solicitudes de los interesados (incluida la búsqueda de contenido y eDiscovery)</span><span class="sxs-lookup"><span data-stu-id="0c5d9-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="0c5d9-109">Informes y herramientas de investigación adicionales</span><span class="sxs-lookup"><span data-stu-id="0c5d9-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="0c5d9-110">Regulaciones de privacidad de datos que afectan al uso de herramientas de supervisión y respuesta</span><span class="sxs-lookup"><span data-stu-id="0c5d9-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="0c5d9-111">A continuación, se incluye una lista de muestra de las normas de privacidad de datos que pueden relacionarse con controles de gobierno de información:</span><span class="sxs-lookup"><span data-stu-id="0c5d9-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="0c5d9-112">Artículo 46 de LGPD</span><span class="sxs-lookup"><span data-stu-id="0c5d9-112">LGPD Article 46</span></span>
- <span data-ttu-id="0c5d9-113">Artículo 48 de LGPD</span><span class="sxs-lookup"><span data-stu-id="0c5d9-113">LGPD Article 48</span></span>
- <span data-ttu-id="0c5d9-114">Artículo de RGPD (5) (1) (f)</span><span class="sxs-lookup"><span data-stu-id="0c5d9-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="0c5d9-115">Artículo de RGPD (15) (1) (e)</span><span class="sxs-lookup"><span data-stu-id="0c5d9-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="0c5d9-116">HIPAA-TECNOLOGÍA (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="0c5d9-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="0c5d9-117">164.308 (a) (1) (II) (D))</span><span class="sxs-lookup"><span data-stu-id="0c5d9-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="0c5d9-118">HIPAA-TECNOLOGÍA (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="0c5d9-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="0c5d9-119">164.308(a)(6)(ii)</span><span class="sxs-lookup"><span data-stu-id="0c5d9-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="0c5d9-120">HIPAA-TECNOLOGÍA (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="0c5d9-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="0c5d9-121">164.312 (b))</span><span class="sxs-lookup"><span data-stu-id="0c5d9-121">164.312(b))</span></span>
- <span data-ttu-id="0c5d9-122">CCPA (1798.105 (c))</span><span class="sxs-lookup"><span data-stu-id="0c5d9-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="0c5d9-123">Para obtener más información, consulte [evaluar los riesgos de privacidad de datos e identificar la información confidencial](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="0c5d9-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="0c5d9-124">Las regulaciones de privacidad de datos generalmente llaman a los siguientes elementos para la supervisión y la respuesta:</span><span class="sxs-lookup"><span data-stu-id="0c5d9-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="0c5d9-125">Auditoría, alertas e informes de actividades relacionadas con el almacenamiento, el uso compartido y el procesamiento de datos personales</span><span class="sxs-lookup"><span data-stu-id="0c5d9-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="0c5d9-126">La capacidad para responder a una solicitud de interesado (DSR) y, en algunos casos, realizar una investigación y otras medidas administrativas para cumplir con dichas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="0c5d9-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="0c5d9-127">La organización también puede desear realizar actividades de supervisión y respuesta para otros fines, como otras necesidades de cumplimiento o motivos empresariales.</span><span class="sxs-lookup"><span data-stu-id="0c5d9-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="0c5d9-128">El establecimiento de la supervisión y el esquema de respuesta para la privacidad de los datos debe realizarse como parte de la planeación general y la planeación, implementación y administración de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="0c5d9-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="0c5d9-129">Para ayudarle a empezar con un esquema de supervisión y respuesta en Microsoft 365 para las regulaciones de privacidad de datos, en este artículo se enumeran las capacidades útiles de Microsoft 365 para responder a preguntas como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="0c5d9-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="0c5d9-130">¿Qué tipo de técnicas de supervisión, investigación e informes se encuentran disponibles para los distintos tipos y orígenes de datos?</span><span class="sxs-lookup"><span data-stu-id="0c5d9-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="0c5d9-131">Qué mecanismos se necesitarán para controlar las solicitudes del interesado (interesado) y cualquier acción correctiva, como anonymization, censura y eliminación.</span><span class="sxs-lookup"><span data-stu-id="0c5d9-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="0c5d9-132">Directivas de auditoría y alerta en el centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="0c5d9-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="0c5d9-133">Consulte estos artículos para la configuración de auditoría, auditoría avanzada y directivas de alerta:</span><span class="sxs-lookup"><span data-stu-id="0c5d9-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="0c5d9-134">Auditoría unificada</span><span class="sxs-lookup"><span data-stu-id="0c5d9-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="0c5d9-135">Auditoría de buzones</span><span class="sxs-lookup"><span data-stu-id="0c5d9-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="0c5d9-136">Auditoría avanzada</span><span class="sxs-lookup"><span data-stu-id="0c5d9-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="0c5d9-137">Directivas de alerta</span><span class="sxs-lookup"><span data-stu-id="0c5d9-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="0c5d9-138">Solicitudes de interesados para RGPD y CCPA</span><span class="sxs-lookup"><span data-stu-id="0c5d9-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="0c5d9-139">Consulte [solicitudes de interesados de datos para RGPD y CCPA](../compliance/gdpr-dsr-office365.md) para obtener información sobre cómo responder a un DSR en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c5d9-139">See [Data Subject Requests for the GDPR and CCPA](../compliance/gdpr-dsr-office365.md) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="0c5d9-140">Administrar usuarios eliminados en Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="0c5d9-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="0c5d9-141">Para Microsoft Stream, cuando se elimina un usuario de Azure Active Directory (Azure AD), si su nombre estaba asociado con un vídeo de transmisión por secuencias anterior a ese punto, su dirección de correo electrónico permanece asociada al vídeo.</span><span class="sxs-lookup"><span data-stu-id="0c5d9-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="0c5d9-142">Consulte [administrar usuarios eliminados de Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) para quitarlo.</span><span class="sxs-lookup"><span data-stu-id="0c5d9-142">See [Manage deleted users from Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) to remove it.</span></span>

## <a name="additional-investigative-tools"></a><span data-ttu-id="0c5d9-143">Herramientas de investigación adicionales</span><span class="sxs-lookup"><span data-stu-id="0c5d9-143">Additional investigative tools</span></span>

<span data-ttu-id="0c5d9-144">A continuación se muestran dos herramientas adicionales que podrían ser útiles para supervisar, investigar y corregir incidentes relacionados con la privacidad de los datos en su organización:</span><span class="sxs-lookup"><span data-stu-id="0c5d9-144">Here are two additional tools that might be useful for monitoring, investigating, and remediating data privacy-related incidents in your organization:</span></span>

- <span data-ttu-id="0c5d9-145">[Administración de riesgos de Insider en microsoft 365](../compliance/insider-risk-management.md), una característica del centro de administración de cumplimiento de Microsoft para ayudar a minimizar el riesgo interno, ya que permite detectar, investigar y realizar acciones en actividades de riesgo de la organización.</span><span class="sxs-lookup"><span data-stu-id="0c5d9-145">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md), a feature of the Microsoft Compliance admin center to help minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>
- <span data-ttu-id="0c5d9-146">[Investigaciones de datos en microsoft 365](../compliance/overview-data-investigations.md), una característica del centro de administración de cumplimiento de Microsoft para buscar datos confidenciales, malintencionados o mal colocados en Microsoft 365 y, a continuación, investigar qué ocurrió para llevar a cabo las acciones adecuadas para corregir el incidente.</span><span class="sxs-lookup"><span data-stu-id="0c5d9-146">[Data investigations in Microsoft 365](../compliance/overview-data-investigations.md), a feature of the Microsoft Compliance admin center to search for sensitive, malicious, or misplaced data across Microsoft 365, and then investigate what happened to take the appropriate actions to remediate the incident.</span></span>
