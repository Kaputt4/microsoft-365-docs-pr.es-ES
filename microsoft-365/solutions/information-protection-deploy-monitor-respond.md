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
ms.openlocfilehash: 3ae0f2a6528f6188500c7cee7732c6447013eaa6
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749592"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="6c677-103">Supervisar y responder a incidentes de privacidad de datos en su organización</span><span class="sxs-lookup"><span data-stu-id="6c677-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="6c677-104">Las características de Microsoft 365 están disponibles para ayudarle a supervisar, investigar y responder a incidentes de privacidad de datos en su organización a medida que opera las capacidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="6c677-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="6c677-105">Tener procesos, procedimientos y otra documentación para cada uno de ellos también puede ser importante para demostrar el cumplimiento de los organismos reguladores.</span><span class="sxs-lookup"><span data-stu-id="6c677-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="6c677-106">Entre ellos se incluyen:</span><span class="sxs-lookup"><span data-stu-id="6c677-106">These include:</span></span> 

- <span data-ttu-id="6c677-107">Directivas de auditoría y alerta</span><span class="sxs-lookup"><span data-stu-id="6c677-107">Auditing and alert policies</span></span>
- <span data-ttu-id="6c677-108">Solicitudes del interesado (incluida la búsqueda de contenido y la exhibición de documentos electrónicos)</span><span class="sxs-lookup"><span data-stu-id="6c677-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="6c677-109">Herramientas de investigación e informes adicionales</span><span class="sxs-lookup"><span data-stu-id="6c677-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="6c677-110">Normativas de privacidad de datos que afectan al uso de herramientas de supervisión y respuesta</span><span class="sxs-lookup"><span data-stu-id="6c677-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="6c677-111">Esta es una lista de ejemplo de las normativas de privacidad de datos que pueden estar relacionadas con los controles de gobierno de la información:</span><span class="sxs-lookup"><span data-stu-id="6c677-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="6c677-112">Artículo 46 lgpd</span><span class="sxs-lookup"><span data-stu-id="6c677-112">LGPD Article 46</span></span>
- <span data-ttu-id="6c677-113">Artículo 48 lgpd</span><span class="sxs-lookup"><span data-stu-id="6c677-113">LGPD Article 48</span></span>
- <span data-ttu-id="6c677-114">Artículo del RGPD (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="6c677-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="6c677-115">Artículo del RGPD (15)(1)(e)</span><span class="sxs-lookup"><span data-stu-id="6c677-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="6c677-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="6c677-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="6c677-117">164.308(a)(1)(ii)(D))</span><span class="sxs-lookup"><span data-stu-id="6c677-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="6c677-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="6c677-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="6c677-119">164.308(a)(6)(ii)</span><span class="sxs-lookup"><span data-stu-id="6c677-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="6c677-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="6c677-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="6c677-121">164.312(b))</span><span class="sxs-lookup"><span data-stu-id="6c677-121">164.312(b))</span></span>
- <span data-ttu-id="6c677-122">CCPA (1798.105(c))</span><span class="sxs-lookup"><span data-stu-id="6c677-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="6c677-123">Para obtener más información, vea [Evaluar los riesgos de privacidad de los datos e identificar información confidencial.](information-protection-deploy-assess.md)</span><span class="sxs-lookup"><span data-stu-id="6c677-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="6c677-124">Por lo general, las normativas de privacidad de datos exigen lo siguiente para la supervisión y la respuesta:</span><span class="sxs-lookup"><span data-stu-id="6c677-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="6c677-125">Auditoría, alertas e informes de actividades relacionadas con el almacenamiento, el uso compartido y el procesamiento de datos personales</span><span class="sxs-lookup"><span data-stu-id="6c677-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="6c677-126">La capacidad de responder a una solicitud del interesado (DSR) y, en algunos casos, realizar investigaciones y otras medidas administrativas para cumplir con dichas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="6c677-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="6c677-127">Es posible que su organización también desee realizar actividades de supervisión y respuesta con otros fines, como otras necesidades de cumplimiento o por motivos empresariales.</span><span class="sxs-lookup"><span data-stu-id="6c677-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="6c677-128">El establecimiento del esquema de supervisión y respuesta para la privacidad de los datos debe realizarse como parte de la planeación, la implementación y la administración generales de la supervisión y la respuesta.</span><span class="sxs-lookup"><span data-stu-id="6c677-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="6c677-129">Para ayudarle a empezar a usar un esquema de supervisión y respuesta en Microsoft 365 para normativas de privacidad de datos, en este artículo se enumeran las funcionalidades útiles de Microsoft 365 para responder preguntas como:</span><span class="sxs-lookup"><span data-stu-id="6c677-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="6c677-130">¿Qué tipo de técnicas diarias de supervisión, investigación e informes están disponibles para los distintos tipos de datos y orígenes?</span><span class="sxs-lookup"><span data-stu-id="6c677-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="6c677-131">Qué mecanismos se necesitan para controlar las solicitudes del interesado (DSR) y las acciones correctivas, como anonimización, reacción y eliminación.</span><span class="sxs-lookup"><span data-stu-id="6c677-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="6c677-132">Auditoría y directivas de alerta en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="6c677-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="6c677-133">Consulte estos artículos para configurar directivas de auditoría, auditoría avanzada y alertas:</span><span class="sxs-lookup"><span data-stu-id="6c677-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="6c677-134">Auditoría unificada</span><span class="sxs-lookup"><span data-stu-id="6c677-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="6c677-135">Auditoría de buzones</span><span class="sxs-lookup"><span data-stu-id="6c677-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="6c677-136">Auditoría avanzada</span><span class="sxs-lookup"><span data-stu-id="6c677-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="6c677-137">Directivas de alerta</span><span class="sxs-lookup"><span data-stu-id="6c677-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="6c677-138">Solicitudes del interesado para el RGPD y la CCPA</span><span class="sxs-lookup"><span data-stu-id="6c677-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="6c677-139">Consulte solicitudes del interesado para el RGPD y [la CCPA](../compliance/gdpr-dsr-office365.md) para obtener información sobre cómo responder a una solicitud de interesado en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6c677-139">See [Data Subject Requests for the GDPR and CCPA](../compliance/gdpr-dsr-office365.md) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="6c677-140">Administrar usuarios eliminados en Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="6c677-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="6c677-141">Para Microsoft Stream, cuando se elimina un usuario de Azure Active Directory (Azure AD), si su nombre estaba asociado a un vídeo de Stream publicado antes de ese punto, su dirección de correo electrónico permanece asociada con el vídeo.</span><span class="sxs-lookup"><span data-stu-id="6c677-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="6c677-142">Consulta [Administrar usuarios eliminados de Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) para quitarlo.</span><span class="sxs-lookup"><span data-stu-id="6c677-142">See [Manage deleted users from Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) to remove it.</span></span>

## <a name="insider-risk-management-as-an-investigative-tool"></a><span data-ttu-id="6c677-143">Administración de riesgos de Insider como herramienta de investigación</span><span class="sxs-lookup"><span data-stu-id="6c677-143">Insider risk management as an investigative tool</span></span>

<span data-ttu-id="6c677-144">La administración de riesgos internos en [Microsoft 365](../compliance/insider-risk-management.md) es una característica del Centro de administración de cumplimiento de Microsoft para ayudarle a minimizar los riesgos internos, ya que le permite detectar, investigar y tomar medidas en actividades de riesgo en su organización.</span><span class="sxs-lookup"><span data-stu-id="6c677-144">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md) is a feature of the Microsoft Compliance admin center to help you minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>
