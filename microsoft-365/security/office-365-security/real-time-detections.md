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
ms.openlocfilehash: 4d0a9ba7ee40c8ad97df745a20d6b5b3314bb3d8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083193"
---
# <a name="explorer-and-real-time-detections-basics"></a><span data-ttu-id="d74ad-103">Conceptos básicos de explorador y detecciones en tiempo real</span><span class="sxs-lookup"><span data-stu-id="d74ad-103">Explorer and Real-time detections basics</span></span>

<span data-ttu-id="d74ad-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="d74ad-104">**Applies to**</span></span>
- [<span data-ttu-id="d74ad-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="d74ad-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d74ad-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d74ad-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d74ad-107">En este artículo:</span><span class="sxs-lookup"><span data-stu-id="d74ad-107">In this article:</span></span>

- [<span data-ttu-id="d74ad-108">Diferencias entre detecciones en tiempo real y explorador</span><span class="sxs-lookup"><span data-stu-id="d74ad-108">Differences between Explorer and Real-time detections</span></span>](#differences-between-explorer-and-real-time-detections)
- [<span data-ttu-id="d74ad-109">Permisos y licencias necesarios</span><span class="sxs-lookup"><span data-stu-id="d74ad-109">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="d74ad-110">Esto forma parte de una serie de **3** artículos en **Explorer (también** conocido como Explorador de amenazas), seguridad de correo electrónico y **conceptos** básicos de explorer y detecciones en tiempo real (como las diferencias entre las herramientas y los permisos necesarios para operarlas).</span><span class="sxs-lookup"><span data-stu-id="d74ad-110">This is part of a **3-article series** on **Explorer (also known as Threat Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="d74ad-111">Los otros dos artículos de esta serie son [Threat hunting in Explorer](threat-hunting-in-threat-explorer.md) y Email security with [Explorer](email-security-in-microsoft-defender.md).</span><span class="sxs-lookup"><span data-stu-id="d74ad-111">The other two articles in this series are [Threat hunting in Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="d74ad-112">En este artículo se explica la diferencia entre el Explorador y los informes de detecciones en tiempo real, y las licencias y permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="d74ad-112">This article explains the difference between Explorer and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="d74ad-113">Si su organización tiene [Microsoft Defender](defender-for-office-365.md)para Office 365 y tiene los permisos, puede usar **explorer** (también conocido como Explorador de **amenazas)** o detecciones en tiempo **real** para detectar y corregir amenazas. [](#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="d74ad-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** (also known as **Threat Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="d74ad-114">En el portal Microsoft 365 Defender ( ), vaya a Correo electrónico & colaboración y, a continuación, elija <https://security.microsoft.com> **Explorador** _o_ **Detecciones en tiempo real**. </span><span class="sxs-lookup"><span data-stu-id="d74ad-114">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<span data-ttu-id="d74ad-115">Con estas herramientas, puede:</span><span class="sxs-lookup"><span data-stu-id="d74ad-115">With these tools, you can:</span></span>

- <span data-ttu-id="d74ad-116">Vea malware detectado por Microsoft 365 de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d74ad-116">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="d74ad-117">Ver la dirección URL de suplantación de identidad (phishing) y hacer clic en datos de veredicto.</span><span class="sxs-lookup"><span data-stu-id="d74ad-117">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="d74ad-118">Inicie un proceso automatizado de investigación y respuesta desde una vista en el Explorador.</span><span class="sxs-lookup"><span data-stu-id="d74ad-118">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="d74ad-119">Investigar correo electrónico malintencionado y mucho más.</span><span class="sxs-lookup"><span data-stu-id="d74ad-119">Investigate malicious email, and more.</span></span>

<span data-ttu-id="d74ad-120">Para obtener más información, vea [Email security with Explorer](email-security-in-microsoft-defender.md).</span><span class="sxs-lookup"><span data-stu-id="d74ad-120">For more information, see [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-explorer-and-real-time-detections"></a><span data-ttu-id="d74ad-121">Diferencias entre detecciones en tiempo real y explorador</span><span class="sxs-lookup"><span data-stu-id="d74ad-121">Differences between Explorer and Real-time detections</span></span>

- <span data-ttu-id="d74ad-122">*Las detecciones en* tiempo real son una herramienta de informes disponible en Defender para Office 365 Plan 1.</span><span class="sxs-lookup"><span data-stu-id="d74ad-122">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="d74ad-123">*El Explorador de* amenazas es una herramienta de búsqueda y corrección de amenazas disponible en Defender para Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="d74ad-123">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="d74ad-124">El informe de detecciones en tiempo real permite ver las detecciones en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="d74ad-124">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="d74ad-125">El Explorador de amenazas también lo hace, pero proporciona detalles adicionales para un ataque determinado, como resaltar las campañas de ataque, y ofrece a los equipos de operaciones de seguridad la capacidad de corregir amenazas (incluida la activación de una investigación automatizada de investigación y [respuesta).](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="d74ad-125">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="d74ad-126">Una *vista De todo* el correo electrónico está disponible en el Explorador de amenazas, pero no se incluye en el informe de detecciones en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="d74ad-126">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="d74ad-127">Las funciones de filtrado enriquecido y las acciones de corrección se incluyen en el Explorador de amenazas.</span><span class="sxs-lookup"><span data-stu-id="d74ad-127">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="d74ad-128">Para obtener más información, vea [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span><span class="sxs-lookup"><span data-stu-id="d74ad-128">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="d74ad-129">Permisos y licencias necesarios</span><span class="sxs-lookup"><span data-stu-id="d74ad-129">Required licenses and permissions</span></span>

<span data-ttu-id="d74ad-130">Debe tener [Microsoft Defender para Office 365](defender-for-office-365.md) usar cualquiera de las detecciones en tiempo real o explorer:</span><span class="sxs-lookup"><span data-stu-id="d74ad-130">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="d74ad-131">El Explorador solo se incluye en Defender for Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="d74ad-131">Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="d74ad-132">El informe de detecciones en tiempo real se incluye en Defender for Office 365 Plan 1.</span><span class="sxs-lookup"><span data-stu-id="d74ad-132">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="d74ad-133">Los equipos de operaciones de seguridad deben asignar licencias para todos los usuarios que deberán estar protegidos por Defender para Office 365 y tener en cuenta que las detecciones en tiempo real y explorador muestran datos de detección para usuarios con licencia.</span><span class="sxs-lookup"><span data-stu-id="d74ad-133">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="d74ad-134">Para ver y usar *detecciones* en tiempo real o explorador, necesita los siguientes permisos:</span><span class="sxs-lookup"><span data-stu-id="d74ad-134">To view and use Explorer *or* Real-time detections, you need the following permissions:</span></span>

- <span data-ttu-id="d74ad-135">En Defender para Office 365:</span><span class="sxs-lookup"><span data-stu-id="d74ad-135">In Defender for Office 365:</span></span>
  - <span data-ttu-id="d74ad-136">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="d74ad-136">Organization Management</span></span>
  - <span data-ttu-id="d74ad-137">Administrador de seguridad (se puede asignar en el centro Azure Active Directory de administración ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="d74ad-137">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="d74ad-138">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="d74ad-138">Security Reader</span></span>
- <span data-ttu-id="d74ad-139">En Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="d74ad-139">In Exchange Online:</span></span>
  - <span data-ttu-id="d74ad-140">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="d74ad-140">Organization Management</span></span>
  - <span data-ttu-id="d74ad-141">Administración de la organización de solo visualización</span><span class="sxs-lookup"><span data-stu-id="d74ad-141">View-Only Organization Management</span></span>
  - <span data-ttu-id="d74ad-142">Destinatarios con permiso de vista</span><span class="sxs-lookup"><span data-stu-id="d74ad-142">View-Only Recipients</span></span>
  - <span data-ttu-id="d74ad-143">Administración de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="d74ad-143">Compliance Management</span></span>

<span data-ttu-id="d74ad-144">Para obtener más información sobre roles y permisos, consulte los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="d74ad-144">To learn more about roles and permissions, see the following articles:</span></span>

- [<span data-ttu-id="d74ad-145">Permisos en el portal de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d74ad-145">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
- [<span data-ttu-id="d74ad-146">Permisos de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d74ad-146">Permissions in Exchange Online</span></span>](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a><span data-ttu-id="d74ad-147">Más información</span><span class="sxs-lookup"><span data-stu-id="d74ad-147">More information</span></span>

- [<span data-ttu-id="d74ad-148">El Explorador de amenazas recopila detalles de correo electrónico en la página de entidad de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="d74ad-148">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="d74ad-149">Buscar e investigar el correo electrónico malintencionado que se ha entregado</span><span class="sxs-lookup"><span data-stu-id="d74ad-149">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="d74ad-150">Ver archivos malintencionados detectados en SharePoint Online, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d74ad-150">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="d74ad-151">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="d74ad-151">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="d74ad-152">Investigación y respuesta automatizada en la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="d74ad-152">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)
