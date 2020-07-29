---
title: Detección de virus en SharePoint Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo SharePoint Online detecta los virus en los archivos que los usuarios cargan y evita que los usuarios descarguen o sincronicen los archivos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6bfc23ca4120122ecfa44ad4d39795fed22af84
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429925"
---
# <a name="virus-detection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="58b43-103">Detección de virus en SharePoint Online, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="58b43-103">Virus detection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="58b43-104">Microsoft 365 puede ayudarle a proteger su entorno del malware detectando virus en los archivos que los usuarios cargan en SharePoint Online, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="58b43-104">Microsoft 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="58b43-105">Los archivos pueden analizarse en busca de virus una vez cargados.</span><span class="sxs-lookup"><span data-stu-id="58b43-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="58b43-106">Si se detecta que un archivo está infectado, se establece una propiedad para que los usuarios no puedan descargar ni sincronizar el archivo.</span><span class="sxs-lookup"><span data-stu-id="58b43-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58b43-107">Estas capacidades antivirus de SharePoint Online son una forma de contener virus.</span><span class="sxs-lookup"><span data-stu-id="58b43-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="58b43-108">No pretenden ser un punto único de defensa contra el malware en su entorno.</span><span class="sxs-lookup"><span data-stu-id="58b43-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="58b43-109">Recomendamos a todos los clientes que evalúen e implementen la protección antimalware en varias capas y que apliquen los procedimientos recomendados para proteger la infraestructura de la empresa.</span><span class="sxs-lookup"><span data-stu-id="58b43-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="58b43-110">Para obtener más información acerca de las estrategias y los procedimientos recomendados, consulte [plan de seguridad](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="58b43-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="58b43-111">¿Qué ocurre cuando se carga un archivo infectado en SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="58b43-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="58b43-112">Microsoft 365 usa un motor de detección de virus común.</span><span class="sxs-lookup"><span data-stu-id="58b43-112">Microsoft 365 uses a common virus detection engine.</span></span> <span data-ttu-id="58b43-113">El motor se ejecuta de forma asincrónica dentro de SharePoint Online y examina algunos archivos después de que se carguen.</span><span class="sxs-lookup"><span data-stu-id="58b43-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="58b43-114">Se usan heurísticas para determinar qué archivos se examinan.</span><span class="sxs-lookup"><span data-stu-id="58b43-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="58b43-115">Cuando se encuentra un archivo que contiene un virus, se marca para que no se pueda descargar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="58b43-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="58b43-116">En abril de 2018, eliminamos el límite de 25 MB para los archivos examinados.</span><span class="sxs-lookup"><span data-stu-id="58b43-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="58b43-117">Esto es lo que sucede:</span><span class="sxs-lookup"><span data-stu-id="58b43-117">Here's what happens:</span></span>

1. <span data-ttu-id="58b43-118">Un usuario carga un archivo en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="58b43-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="58b43-119">SharePoint Online determina si el archivo cumple los criterios de un examen.</span><span class="sxs-lookup"><span data-stu-id="58b43-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="58b43-120">El motor de detección de virus examina el archivo.</span><span class="sxs-lookup"><span data-stu-id="58b43-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="58b43-121">Si se encuentra un virus, el motor del virus establece una propiedad en el archivo que indica que está infectado.</span><span class="sxs-lookup"><span data-stu-id="58b43-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="58b43-122">¿Qué sucede cuando un usuario intenta descargar un archivo infectado con el explorador?</span><span class="sxs-lookup"><span data-stu-id="58b43-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="58b43-123">Si un archivo está infectado, los usuarios no pueden descargar el archivo de SharePoint Online con el explorador.</span><span class="sxs-lookup"><span data-stu-id="58b43-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="58b43-124">Esto es lo que sucede:</span><span class="sxs-lookup"><span data-stu-id="58b43-124">Here's what happens:</span></span>

1. <span data-ttu-id="58b43-125">Un usuario abre un explorador web e intenta descargar un archivo infectado de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="58b43-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="58b43-126">Al usuario se le advierte de que se ha detectado un virus.</span><span class="sxs-lookup"><span data-stu-id="58b43-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="58b43-127">Al usuario se le ofrece la opción de descargar el archivo e intentar limpiarlo mediante su propio software antivirus.</span><span class="sxs-lookup"><span data-stu-id="58b43-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
> 
> <span data-ttu-id="58b43-128">Puede usar el parámetro *DisallowInfectedFileDownload* en el cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) de PowerShell de SharePoint Online para evitar que los usuarios descarguen un archivo infectado, incluso en la ventana de advertencia de antivirus.</span><span class="sxs-lookup"><span data-stu-id="58b43-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>
> 
> <span data-ttu-id="58b43-129">Tenga en cuenta también que, en cuanto habilite el parámetro *DisallowInfectedFileDownload* , el acceso a los archivos detectados o bloqueados queda bloqueado completamente para los usuarios y los administradores.</span><span class="sxs-lookup"><span data-stu-id="58b43-129">Also keep in mind, that as soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completly blocked for users and administrators.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="58b43-130">¿Qué sucede cuando el cliente de sincronización de OneDrive intenta sincronizar un archivo infectado?</span><span class="sxs-lookup"><span data-stu-id="58b43-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="58b43-131">Si los usuarios sincronizan archivos con el nuevo cliente de sincronización de OneDrive (OneDrive.exe) o el anterior cliente de sincronización de OneDrive para la empresa (Groove.exe), si un archivo contiene un virus, el cliente de sincronización no lo descargará.</span><span class="sxs-lookup"><span data-stu-id="58b43-131">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="58b43-132">El cliente de sincronización mostrará una notificación de que el archivo no se puede sincronizar.</span><span class="sxs-lookup"><span data-stu-id="58b43-132">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-office-365-atp"></a><span data-ttu-id="58b43-133">Capacidades ampliadas con Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="58b43-133">Extended capabilities with Office 365 ATP</span></span>

<span data-ttu-id="58b43-134">Los clientes que habilitaron Office 365 ATP para SharePoint, OneDrive y Microsoft Teams [activan ATP para SharePoint, onedrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) pueden usar el centro de seguridad & cumplimiento para administrar los archivos en cuarentena para detecciones AV y ATP.</span><span class="sxs-lookup"><span data-stu-id="58b43-134">Customers who enabled Office 365 ATP for Sharepoint, OneDrive, and Microsoft Teams [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) are able to use the Security & Compliance Center to manage quarantined files for AV and ATP detections.</span></span> <span data-ttu-id="58b43-135">[Solo ATP: Use el centro de seguridad & cumplimiento para administrar los archivos en cuarentena](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span><span class="sxs-lookup"><span data-stu-id="58b43-135">[ATP Only: Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="more-information"></a><span data-ttu-id="58b43-136">Más información</span><span class="sxs-lookup"><span data-stu-id="58b43-136">More information</span></span>

<span data-ttu-id="58b43-137">Consulte [proteger contra amenazas](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) y [Activar ATP para SharePoint, OneDrive y Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) para obtener más información sobre cómo configurar el antivirus de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="58b43-137">See [Protect against threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) for more information on how to configure SharePoint Online antivirus.</span></span>


