---
title: Usar Exchange Online y el Centro de seguridad y cumplimiento para cumplir con la norma SEC 17a-4
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Configure el Centro de cumplimiento y Exchange Online para cumplir con los requisitos de las normas CFTC 1.31(c)-(d), FINRA 4511 y SEC 17a-4.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 769e13951ce15fb698131860fa78f25fa133e327
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127307"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a><span data-ttu-id="c5965-103">Usar Exchange Online y el Centro de seguridad y cumplimiento para cumplir con la norma SEC 17a-4</span><span class="sxs-lookup"><span data-stu-id="c5965-103">Use Exchange Online and the Security & Compliance Center to comply with SEC Rule 17a-4</span></span>

><span data-ttu-id="c5965-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="c5965-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="c5965-105">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c5965-105">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online.</span></span> <span data-ttu-id="c5965-106">This includes the ability to retain, audit, search, and export your data.</span><span class="sxs-lookup"><span data-stu-id="c5965-106">This includes the ability to retain, audit, search, and export your data.</span></span> <span data-ttu-id="c5965-107">These capabilities are sufficient to meet the needs of most organizations.</span><span class="sxs-lookup"><span data-stu-id="c5965-107">These capabilities are sufficient to meet the needs of most organizations.</span></span>

<span data-ttu-id="c5965-108">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements.</span><span class="sxs-lookup"><span data-stu-id="c5965-108">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements.</span></span> <span data-ttu-id="c5965-109">For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC).</span><span class="sxs-lookup"><span data-stu-id="c5965-109">For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC).</span></span> <span data-ttu-id="c5965-110">Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span><span class="sxs-lookup"><span data-stu-id="c5965-110">Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span></span>

<span data-ttu-id="c5965-111">Para que estas organizaciones puedan comprender mejor cómo aprovechar el Centro de seguridad y cumplimiento para adaptarse a sus obligaciones reglamentarias para Exchange Online, específicamente en relación con los requisitos de la norma 17a-4, publicamos una evaluación de forma conjunta con Cohasset Associates.</span><span class="sxs-lookup"><span data-stu-id="c5965-111">To help these organizations better understand how the Security & Compliance Center can be leveraged to meet their regulatory obligations for Exchange Online, specifically in relation to Rule 17a-4 requirements, we have released an assessment in partnership with Cohasset Associates.</span></span>

<span data-ttu-id="c5965-112">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4.</span><span class="sxs-lookup"><span data-stu-id="c5965-112">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4.</span></span> <span data-ttu-id="c5965-113">We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span><span class="sxs-lookup"><span data-stu-id="c5965-113">We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span></span>

## <a name="download-the-cohasset-assessment"></a><span data-ttu-id="c5965-114">Descargar la evaluación de Cohasset</span><span class="sxs-lookup"><span data-stu-id="c5965-114">Download the Cohasset assessment</span></span>

<span data-ttu-id="c5965-115">Puede [descargar la evaluación de Cohasset aquí](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span><span class="sxs-lookup"><span data-stu-id="c5965-115">You can [download the Cohasset assessment here](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span></span>

![Página de título de la evaluación descargable por Cohasset Associates](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a><span data-ttu-id="c5965-117">Esta evaluación es específica para Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c5965-117">This assessment is specific to Exchange Online</span></span>

<span data-ttu-id="c5965-118">Note that this assessment is specific to Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c5965-118">Note that this assessment is specific to Exchange Online.</span></span> <span data-ttu-id="c5965-119">The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span><span class="sxs-lookup"><span data-stu-id="c5965-119">The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span></span>

<span data-ttu-id="c5965-120">It's important to understand that Skype for Business and Teams also store data in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c5965-120">It's important to understand that Skype for Business and Teams also store data in Exchange Online.</span></span> <span data-ttu-id="c5965-121">Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span><span class="sxs-lookup"><span data-stu-id="c5965-121">Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span></span>

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a><span data-ttu-id="c5965-122">Usar Bloqueo de conservación es clave para la configuración recomendada</span><span class="sxs-lookup"><span data-stu-id="c5965-122">Using Preservation Lock is key to the recommended configuration</span></span>

<span data-ttu-id="c5965-123">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement.</span><span class="sxs-lookup"><span data-stu-id="c5965-123">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement.</span></span> <span data-ttu-id="c5965-124">The WORM requirement dictates a storage solution in which a record must be:</span><span class="sxs-lookup"><span data-stu-id="c5965-124">The WORM requirement dictates a storage solution in which a record must be:</span></span>

- <span data-ttu-id="c5965-125">Conservarse durante un período de retención que no puede acortarse, solo incrementarse.</span><span class="sxs-lookup"><span data-stu-id="c5965-125">Retained for a required retention period that cannot be shortened, only increased.</span></span>
- <span data-ttu-id="c5965-126">Ser inmutable, lo que significa que el registro no se puede sobrescribir, borrar ni modificar durante el período de retención necesario.</span><span class="sxs-lookup"><span data-stu-id="c5965-126">Immutable, meaning that the record cannot be overwritten, erased, or altered during the required retention period.</span></span>

<span data-ttu-id="c5965-127">In Exchange Online, when a [retention policy](retention.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy.</span><span class="sxs-lookup"><span data-stu-id="c5965-127">In Exchange Online, when a [retention policy](retention.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy.</span></span> <span data-ttu-id="c5965-128">In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox.</span><span class="sxs-lookup"><span data-stu-id="c5965-128">In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox.</span></span> <span data-ttu-id="c5965-129">Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span><span class="sxs-lookup"><span data-stu-id="c5965-129">Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span></span>

<span data-ttu-id="c5965-130">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified.</span><span class="sxs-lookup"><span data-stu-id="c5965-130">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified.</span></span> <span data-ttu-id="c5965-131">In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span><span class="sxs-lookup"><span data-stu-id="c5965-131">In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span></span>

- <span data-ttu-id="c5965-132">El período de retención de la directiva solo se puede incrementar, no se puede acortar.</span><span class="sxs-lookup"><span data-stu-id="c5965-132">The retention period of the policy can only be increased, not shortened.</span></span>
- <span data-ttu-id="c5965-133">Se pueden agregar usuarios a la directiva, pero no se puede quitar ningún usuario.</span><span class="sxs-lookup"><span data-stu-id="c5965-133">Users can be added to the policy, but no user can be removed.</span></span>
- <span data-ttu-id="c5965-134">Un administrador no puede eliminar una directiva de retención.</span><span class="sxs-lookup"><span data-stu-id="c5965-134">The retention policy cannot be deleted by an administrator.</span></span>

<span data-ttu-id="c5965-135">Bloqueo de conservación puede ayudarle a cumplir con los requisitos reglamentarios de SEC 17a-4.</span><span class="sxs-lookup"><span data-stu-id="c5965-135">Preservation Lock can help you meet the SEC 17a-4 regulatory requirements.</span></span>

## <a name="how-to-set-up-preservation-lock"></a><span data-ttu-id="c5965-136">Configurar Bloqueo de conservación</span><span class="sxs-lookup"><span data-stu-id="c5965-136">How to set up Preservation Lock</span></span>

<span data-ttu-id="c5965-137">Puede bloquear una directiva de retención con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5965-137">You can lock a retention policy by using PowerShell.</span></span> <span data-ttu-id="c5965-138">Para más información, consulte [Usar el bloqueo de conservación para cumplir los requisitos normativos](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span><span class="sxs-lookup"><span data-stu-id="c5965-138">For more information, see [Use Preservation Lock to comply with regulatory requirements](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c5965-139">Limitaciones conocidas</span><span class="sxs-lookup"><span data-stu-id="c5965-139">Known limitations</span></span>

<span data-ttu-id="c5965-140">Actualmente existen algunas limitaciones para Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="c5965-140">Currently, there are a few limitations for Exchange Online:</span></span>

- <span data-ttu-id="c5965-141">Las comunicaciones en conversaciones no están disponibles para los mensajes de canal y de chat de Teams.</span><span class="sxs-lookup"><span data-stu-id="c5965-141">Threaded communications are not available for Teams chat and channel messages.</span></span>
- <span data-ttu-id="c5965-142">Los “me gusta” no se conservan para los mensajes de canal y de chat de Teams.</span><span class="sxs-lookup"><span data-stu-id="c5965-142">Likes are not retained for Teams chat and channel messages.</span></span>

> [!NOTE]
> <span data-ttu-id="c5965-143">La auditoría de nivel de elemento ya está disponible en los buzones de grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c5965-143">Item-level auditing is now available for Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="c5965-144">Para más información, consulte [Administrar auditoría del buzón](enable-mailbox-auditing.md)..</span><span class="sxs-lookup"><span data-stu-id="c5965-144">For more information, see [Manage mailbox auditing](enable-mailbox-auditing.md).</span></span>
