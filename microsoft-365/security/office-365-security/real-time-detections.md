---
title: Conceptos básicos del Explorador de amenazas y detecciones en tiempo real en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Use detecciones en tiempo real o explorador para investigar y responder a las amenazas de forma eficaz.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300220"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a><span data-ttu-id="ffc4a-103">Conceptos básicos del Explorador de amenazas y detección en tiempo real</span><span class="sxs-lookup"><span data-stu-id="ffc4a-103">Threat Explorer and Real-time detections basics</span></span>

<span data-ttu-id="ffc4a-104">En este artículo:</span><span class="sxs-lookup"><span data-stu-id="ffc4a-104">In this article:</span></span>

- [<span data-ttu-id="ffc4a-105">Diferencias entre el Explorador de amenazas y las detecciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="ffc4a-105">Differences between Threat Explorer and Real-time detections</span></span>](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [<span data-ttu-id="ffc4a-106">Permisos y licencias necesarios</span><span class="sxs-lookup"><span data-stu-id="ffc4a-106">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="ffc4a-107">Esto forma parte de una serie de **3** artículos sobre explorador de amenazas **(Explorer),** seguridad de correo electrónico y **conceptos** básicos de detecciones de Explorador y tiempo real (como diferencias entre las herramientas y los permisos necesarios para operarlas).</span><span class="sxs-lookup"><span data-stu-id="ffc4a-107">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="ffc4a-108">Los otros dos artículos de esta serie son Búsqueda de [amenazas en](threat-hunting-in-threat-explorer.md) el Explorador de amenazas y Seguridad de correo electrónico con el Explorador [de amenazas.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="ffc4a-108">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="ffc4a-109">En este artículo se explica la diferencia entre la exploración de amenazas y los informes de detecciones en tiempo real, y las licencias y permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="ffc4a-109">This article explains the difference between threat exploration and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="ffc4a-110">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="ffc4a-110">**Applies to**</span></span>
- [<span data-ttu-id="ffc4a-111">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="ffc4a-111">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ffc4a-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ffc4a-112">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ffc4a-113">Si su organización tiene [Microsoft Defender](defender-for-office-365.md)para Office 365 y tiene los [permisos,](#required-licenses-and-permissions)puede usar el Explorador de amenazas **(denominado** **Explorador)** o detecciones en tiempo **real** para detectar y corregir amenazas.</span><span class="sxs-lookup"><span data-stu-id="ffc4a-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Threat Explorer** (called **Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="ffc4a-114">En el **Centro de & seguridad,** vaya a **Administración** de amenazas y, a continuación, elija **Explorador**  o **Detecciones en tiempo real.**</span><span class="sxs-lookup"><span data-stu-id="ffc4a-114">In the **Security & Compliance Center**, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="ffc4a-115">Con Microsoft Defender para Office 365 plan 2, verá:</span><span class="sxs-lookup"><span data-stu-id="ffc4a-115">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="ffc4a-116">Con Microsoft Defender para Office 365 plan 1, verá:</span><span class="sxs-lookup"><span data-stu-id="ffc4a-116">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![Explorador de amenazas](../../media/threatmgmt-explorer.png)|![Detecciones en tiempo real](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="ffc4a-119">Con estas herramientas, puede:</span><span class="sxs-lookup"><span data-stu-id="ffc4a-119">With these tools, you can:</span></span>

- <span data-ttu-id="ffc4a-120">Vea malware detectado por Microsoft 365 de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ffc4a-120">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="ffc4a-121">Ver la dirección URL de suplantación de identidad (phishing) y hacer clic en datos de veredicto.</span><span class="sxs-lookup"><span data-stu-id="ffc4a-121">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="ffc4a-122">Inicie un proceso automatizado de investigación y respuesta desde una vista en el Explorador.</span><span class="sxs-lookup"><span data-stu-id="ffc4a-122">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="ffc4a-123">Investigar correo electrónico malintencionado y mucho más.</span><span class="sxs-lookup"><span data-stu-id="ffc4a-123">Investigate malicious email, and more.</span></span>

<span data-ttu-id="ffc4a-124">Para obtener más información, vea [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span><span class="sxs-lookup"><span data-stu-id="ffc4a-124">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="ffc4a-125">Diferencias entre el Explorador de amenazas y las detecciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="ffc4a-125">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="ffc4a-126">*Las detecciones en* tiempo real son una herramienta de informes disponible en Defender para Office 365 Plan 1.</span><span class="sxs-lookup"><span data-stu-id="ffc4a-126">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="ffc4a-127">*El Explorador de* amenazas es una herramienta de búsqueda y corrección de amenazas disponible en Defender para Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="ffc4a-127">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="ffc4a-128">El informe de detecciones en tiempo real permite ver las detecciones en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="ffc4a-128">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="ffc4a-129">El Explorador de amenazas también lo hace, pero proporciona detalles adicionales para un ataque determinado, como resaltar las campañas de ataque, y ofrece a los equipos de operaciones de seguridad la capacidad de corregir amenazas (incluida la activación de una investigación automatizada de investigación y [respuesta).](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="ffc4a-129">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="ffc4a-130">Una *vista De todo* el correo electrónico está disponible en el Explorador de amenazas, pero no se incluye en el informe de detecciones en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="ffc4a-130">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="ffc4a-131">Las funciones de filtrado enriquecido y las acciones de corrección se incluyen en el Explorador de amenazas.</span><span class="sxs-lookup"><span data-stu-id="ffc4a-131">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="ffc4a-132">Para obtener más información, vea [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span><span class="sxs-lookup"><span data-stu-id="ffc4a-132">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="ffc4a-133">Permisos y licencias necesarios</span><span class="sxs-lookup"><span data-stu-id="ffc4a-133">Required licenses and permissions</span></span>

<span data-ttu-id="ffc4a-134">Debe tener [Microsoft Defender para Office 365](defender-for-office-365.md) usar cualquiera de las detecciones en tiempo real o explorer:</span><span class="sxs-lookup"><span data-stu-id="ffc4a-134">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="ffc4a-135">Pero el Explorador solo se incluye en Defender para Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="ffc4a-135">But Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="ffc4a-136">El informe de detecciones en tiempo real se incluye en Defender for Office 365 Plan 1.</span><span class="sxs-lookup"><span data-stu-id="ffc4a-136">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="ffc4a-137">Los equipos de operaciones de seguridad deben asignar licencias para todos los usuarios que deberán estar protegidos por Defender para Office 365 y tener en cuenta que las detecciones en tiempo real y explorador muestran datos de detección para usuarios con licencia.</span><span class="sxs-lookup"><span data-stu-id="ffc4a-137">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="ffc4a-138">Para ver y usar *detecciones* en tiempo real o explorador, debe tener lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ffc4a-138">To view and use Explorer *or* Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="ffc4a-139">Para el Centro de & seguridad:</span><span class="sxs-lookup"><span data-stu-id="ffc4a-139">For the Security & Compliance Center:</span></span>

  - <span data-ttu-id="ffc4a-140">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="ffc4a-140">Organization Management</span></span>
  - <span data-ttu-id="ffc4a-141">Administrador de seguridad (se puede asignar en el centro Azure Active Directory de administración ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="ffc4a-141">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="ffc4a-142">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="ffc4a-142">Security Reader</span></span>

- <span data-ttu-id="ffc4a-143">Para Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="ffc4a-143">For Exchange Online:</span></span>

  - <span data-ttu-id="ffc4a-144">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="ffc4a-144">Organization Management</span></span>
  - <span data-ttu-id="ffc4a-145">Administración de la organización de solo visualización</span><span class="sxs-lookup"><span data-stu-id="ffc4a-145">View-Only Organization Management</span></span>
  - <span data-ttu-id="ffc4a-146">Destinatarios con permiso de vista</span><span class="sxs-lookup"><span data-stu-id="ffc4a-146">View-Only Recipients</span></span>
  - <span data-ttu-id="ffc4a-147">Administración de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="ffc4a-147">Compliance Management</span></span>

<span data-ttu-id="ffc4a-148">Para obtener más información sobre roles y permisos, consulte los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="ffc4a-148">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="ffc4a-149">Permisos en el Centro de seguridad y cumplimiento </span><span class="sxs-lookup"><span data-stu-id="ffc4a-149">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="ffc4a-150">Permisos de características de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ffc4a-150">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="ffc4a-151">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="ffc4a-151">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="ffc4a-152">Más información</span><span class="sxs-lookup"><span data-stu-id="ffc4a-152">More information</span></span>
- [<span data-ttu-id="ffc4a-153">El Explorador de amenazas recopila detalles de correo electrónico en la página de entidad de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="ffc4a-153">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="ffc4a-154">Buscar e investigar el correo electrónico malintencionado que se ha entregado</span><span class="sxs-lookup"><span data-stu-id="ffc4a-154">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="ffc4a-155">Ver archivos malintencionados detectados en SharePoint Online, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ffc4a-155">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="ffc4a-156">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="ffc4a-156">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="ffc4a-157">Investigación y respuesta automatizada en la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="ffc4a-157">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)