---
title: Protección contra virus integrada en SharePoint Online, OneDrive y Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo SharePoint Online detecta virus en archivos que los usuarios cargan e impide que los usuarios descarguen o sincronicen los archivos.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dd38b196c106a36fb1a1bfc0a441620b1c5b8ba5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205330"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="0346d-103">Protección contra virus integrada en SharePoint Online, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0346d-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0346d-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="0346d-104">**Applies to**</span></span>
- [<span data-ttu-id="0346d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0346d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0346d-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="0346d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="0346d-107">Microsoft 365 usa un motor de detección de virus común para examinar los archivos que los usuarios cargan en SharePoint Online, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0346d-107">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="0346d-108">Esta protección se incluye con todas las suscripciones que incluyen SharePoint Online, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0346d-108">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0346d-109">Las funcionalidades antivirus integradas son una forma de ayudar a contener virus.</span><span class="sxs-lookup"><span data-stu-id="0346d-109">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="0346d-110">No están pensados como un único punto de defensa contra malware para su entorno.</span><span class="sxs-lookup"><span data-stu-id="0346d-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="0346d-111">Animamos a todos los clientes a investigar e implementar la protección antimalware en varias capas y aplicar procedimientos recomendados para proteger su infraestructura empresarial.</span><span class="sxs-lookup"><span data-stu-id="0346d-111">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="0346d-112">Para obtener más información sobre estrategias y procedimientos recomendados, vea [Security roadmap](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="0346d-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="0346d-113">¿Qué sucede si se carga un archivo infectado en SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="0346d-113">What happens if an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="0346d-114">El motor de detección de virus de Microsoft 365 se ejecuta de forma asincrónica (independiente de las cargas de archivos) en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0346d-114">The Microsoft 365 virus detection engine runs asynchronously (independent from file uploads) within SharePoint Online.</span></span> <span data-ttu-id="0346d-115">**Todos los archivos no se examinan automáticamente.**</span><span class="sxs-lookup"><span data-stu-id="0346d-115">**All files are not automatically scanned**.</span></span> <span data-ttu-id="0346d-116">La heurística determina los archivos que se examinarán.</span><span class="sxs-lookup"><span data-stu-id="0346d-116">Heuristics determine the files to scan.</span></span> <span data-ttu-id="0346d-117">Cuando se encuentra que un archivo contiene un virus, se marca el archivo.</span><span class="sxs-lookup"><span data-stu-id="0346d-117">When a file is found to contain a virus, the file is flagged.</span></span> <span data-ttu-id="0346d-118">En abril de 2018, se eliminó el límite de 25 MB para los archivos analizados.</span><span class="sxs-lookup"><span data-stu-id="0346d-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="0346d-119">Esto es lo que sucede:</span><span class="sxs-lookup"><span data-stu-id="0346d-119">Here's what happens:</span></span>

1. <span data-ttu-id="0346d-120">Un usuario carga un archivo en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0346d-120">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="0346d-121">SharePoint Online, como parte de sus procesos de análisis de virus, determina más adelante si el archivo cumple los criterios para un examen.</span><span class="sxs-lookup"><span data-stu-id="0346d-121">SharePoint Online, as part of its virus scanning processes, later determines if the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="0346d-122">Si el archivo cumple los criterios para un examen, el motor de detección de virus examina el archivo.</span><span class="sxs-lookup"><span data-stu-id="0346d-122">If the file meets the criteria for a scan, the virus detection engine scans the file.</span></span>
4. <span data-ttu-id="0346d-123">Si se encuentra un virus en el archivo examinado, el motor de virus establece una propiedad en el archivo que indica que está infectado.</span><span class="sxs-lookup"><span data-stu-id="0346d-123">If a virus is found within the scanned file, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="0346d-124">¿Qué sucede cuando un usuario intenta descargar un archivo infectado mediante el explorador?</span><span class="sxs-lookup"><span data-stu-id="0346d-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="0346d-125">Si un archivo está infectado, los usuarios no pueden descargar el archivo desde SharePoint Online mediante un explorador.</span><span class="sxs-lookup"><span data-stu-id="0346d-125">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="0346d-126">Esto es lo que sucede:</span><span class="sxs-lookup"><span data-stu-id="0346d-126">Here's what happens:</span></span>

1. <span data-ttu-id="0346d-127">Un usuario abre un explorador web e intenta descargar un archivo infectado de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0346d-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="0346d-128">El usuario recibe una advertencia de que se ha detectado un virus.</span><span class="sxs-lookup"><span data-stu-id="0346d-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="0346d-129">De forma predeterminada, el usuario tiene la opción de descargar el archivo e intentar limpiarlo con el software antivirus en su propio dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0346d-129">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="0346d-130">Los administradores pueden usar el parámetro *DisallowInfectedFileDownload* en el cmdlet [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) en PowerShell de SharePoint Online para impedir que los usuarios descarguen archivos infectados, incluso en la ventana de advertencia antivirus.</span><span class="sxs-lookup"><span data-stu-id="0346d-130">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="0346d-131">Para obtener instrucciones, [vea Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span><span class="sxs-lookup"><span data-stu-id="0346d-131">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="0346d-132">Tan pronto como habilite el parámetro *DisallowInfectedFileDownload,* el acceso a los archivos detectados o bloqueados se bloqueará completamente para usuarios y administradores.</span><span class="sxs-lookup"><span data-stu-id="0346d-132">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="0346d-133">¿Qué sucede cuando el cliente de sincronización de OneDrive intenta sincronizar un archivo infectado?</span><span class="sxs-lookup"><span data-stu-id="0346d-133">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="0346d-134">Los clientes de sincronización de OneDrive no descargarán archivos que contengan virus.</span><span class="sxs-lookup"><span data-stu-id="0346d-134">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="0346d-135">El cliente de sincronización mostrará una notificación de que el archivo no se puede sincronizar.</span><span class="sxs-lookup"><span data-stu-id="0346d-135">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="0346d-136">Funcionalidades extendidas con Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="0346d-136">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0346d-137">Las organizaciones de Microsoft 365 que tienen [Microsoft Defender para Office 365](defender-for-office-365.md) incluidas en su suscripción o compradas como complemento pueden habilitar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams para mejorar la protección y los informes.</span><span class="sxs-lookup"><span data-stu-id="0346d-137">Microsoft 365 organizations that have [Microsoft Defender for Office 365](defender-for-office-365.md) included in their subscription or purchased as an add-on can enable Safe Attachments for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="0346d-138">Para obtener más información, vea [Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0346d-138">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="0346d-139">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="0346d-139">Related Articles</span></span>

[<span data-ttu-id="0346d-140">Protección contra malware y ransomware en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0346d-140">Malware and ransomware protection in Microsoft 365</span></span>](/compliance/assurance/assurance-malware-and-ransomware-protection)

<span data-ttu-id="0346d-141">Para obtener más información sobre antivirus en SharePoint Online, OneDrive y Microsoft Teams, vea [Proteger](protect-against-threats.md) contra amenazas y Activar datos adjuntos seguros para [SharePoint, OneDrive](turn-on-mdo-for-spo-odb-and-teams.md)y Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="0346d-141">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>
