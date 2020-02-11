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
description: Obtenga información sobre la protección antivirus en SharePoint Online.
ms.openlocfilehash: f22c2a3280148eb23f4ba53ff467a533186ed791
ms.sourcegitcommit: 3d17c1d6b80672719b1878e2f321f0de39595226
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887277"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="2bebe-103">Detección de virus en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2bebe-103">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="2bebe-104">Office 365 puede ayudarle a proteger su entorno del malware detectando virus en los archivos que los usuarios cargan en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2bebe-104">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="2bebe-105">Los archivos pueden analizarse en busca de virus una vez cargados.</span><span class="sxs-lookup"><span data-stu-id="2bebe-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="2bebe-106">Si se detecta que un archivo está infectado, se establece una propiedad para que los usuarios no puedan descargar ni sincronizar el archivo.</span><span class="sxs-lookup"><span data-stu-id="2bebe-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2bebe-107">Estas capacidades antivirus de SharePoint Online son una forma de contener virus.</span><span class="sxs-lookup"><span data-stu-id="2bebe-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="2bebe-108">No pretenden ser un punto único de defensa contra el malware en su entorno.</span><span class="sxs-lookup"><span data-stu-id="2bebe-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="2bebe-109">Recomendamos a todos los clientes que evalúen e implementen la protección antimalware en varias capas y que apliquen los procedimientos recomendados para proteger la infraestructura de la empresa.</span><span class="sxs-lookup"><span data-stu-id="2bebe-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="2bebe-110">Para obtener más información acerca de las estrategias y los procedimientos recomendados, consulte [plan de seguridad](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="2bebe-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="2bebe-111">¿Qué ocurre cuando se carga un archivo infectado en SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="2bebe-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="2bebe-112">Office 365 usa un motor de detección de virus común.</span><span class="sxs-lookup"><span data-stu-id="2bebe-112">Office 365 uses a common virus detection engine.</span></span> <span data-ttu-id="2bebe-113">El motor se ejecuta de forma asincrónica dentro de SharePoint Online y examina algunos archivos después de que se carguen.</span><span class="sxs-lookup"><span data-stu-id="2bebe-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="2bebe-114">Se usan heurísticas para determinar qué archivos se examinan.</span><span class="sxs-lookup"><span data-stu-id="2bebe-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="2bebe-115">Cuando se encuentra un archivo que contiene un virus, se marca para que no se pueda descargar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="2bebe-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="2bebe-116">En abril de 2018, eliminamos el límite de 25 MB para los archivos examinados.</span><span class="sxs-lookup"><span data-stu-id="2bebe-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="2bebe-117">Esto es lo que sucede:</span><span class="sxs-lookup"><span data-stu-id="2bebe-117">Here's what happens:</span></span>

1. <span data-ttu-id="2bebe-118">Un usuario carga un archivo en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2bebe-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="2bebe-119">SharePoint Online determina si el archivo cumple los criterios de un examen.</span><span class="sxs-lookup"><span data-stu-id="2bebe-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="2bebe-120">El motor de detección de virus examina el archivo.</span><span class="sxs-lookup"><span data-stu-id="2bebe-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="2bebe-121">Si se encuentra un virus, el motor del virus establece una propiedad en el archivo que indica que está infectado.</span><span class="sxs-lookup"><span data-stu-id="2bebe-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="2bebe-122">¿Qué sucede cuando un usuario intenta descargar un archivo infectado con el explorador?</span><span class="sxs-lookup"><span data-stu-id="2bebe-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="2bebe-123">Si un archivo está infectado, los usuarios no pueden descargar el archivo de SharePoint Online con el explorador.</span><span class="sxs-lookup"><span data-stu-id="2bebe-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="2bebe-124">Esto es lo que sucede:</span><span class="sxs-lookup"><span data-stu-id="2bebe-124">Here's what happens:</span></span>

1. <span data-ttu-id="2bebe-125">Un usuario abre un explorador web e intenta descargar un archivo infectado de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2bebe-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="2bebe-126">Al usuario se le advierte de que se ha detectado un virus.</span><span class="sxs-lookup"><span data-stu-id="2bebe-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="2bebe-127">Al usuario se le ofrece la opción de descargar el archivo e intentar limpiarlo mediante su propio software antivirus.</span><span class="sxs-lookup"><span data-stu-id="2bebe-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
> <span data-ttu-id="2bebe-128">Puede usar el parámetro *DisallowInfectedFileDownload* en el cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) de PowerShell de SharePoint Online para evitar que los usuarios descarguen un archivo infectado, incluso en la ventana de advertencia de antivirus.</span><span class="sxs-lookup"><span data-stu-id="2bebe-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="2bebe-129">¿Qué sucede cuando el cliente de sincronización de OneDrive intenta sincronizar un archivo infectado?</span><span class="sxs-lookup"><span data-stu-id="2bebe-129">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="2bebe-130">Si los usuarios sincronizan archivos con el nuevo cliente de sincronización de OneDrive (OneDrive. exe) o el anterior cliente de sincronización de OneDrive para la empresa (Groove. exe), si un archivo contiene un virus, el cliente de sincronización no lo descargará.</span><span class="sxs-lookup"><span data-stu-id="2bebe-130">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="2bebe-131">El cliente de sincronización mostrará una notificación de que el archivo no se puede sincronizar.</span><span class="sxs-lookup"><span data-stu-id="2bebe-131">The sync client will display a notification that the file can't be synced.</span></span>
