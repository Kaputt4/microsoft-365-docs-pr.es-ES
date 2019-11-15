---
title: Detección de virus en SharePoint Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 01/14/2019
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
description: Office 365 puede ayudarle a proteger su entorno del malware detectando virus en los archivos que los usuarios cargan en SharePoint Online. Los archivos se examinan en busca de virus una vez cargados. Si se detecta que un archivo está infectado, se establece una propiedad para que los usuarios no puedan descargar ni sincronizar el archivo.
ms.openlocfilehash: 9776dd7791d8543e0fd401a3c21c95d9fbf60f09
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639830"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="e9d8c-105">Detección de virus en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e9d8c-105">Virus detection in SharePoint Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9d8c-106">Para usar esta característica, se necesita la protección contra amenazas avanzada (ATP) de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-106">To use this feature, Office 365 Advanced Threat Protection (ATP) is required.</span></span> <span data-ttu-id="e9d8c-107">Para obtener más información, consulte [Activar ATP de Office 365 para SharePoint, OneDrive y Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="e9d8c-107">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="e9d8c-108">Office 365 puede ayudarle a proteger su entorno del malware detectando virus en los archivos que los usuarios cargan en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-108">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="e9d8c-109">Los archivos se examinan en busca de virus una vez cargados.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-109">Files are scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="e9d8c-110">Si se detecta que un archivo está infectado, se establece una propiedad para que los usuarios no puedan descargar ni sincronizar el archivo.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-110">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e9d8c-111">Estas capacidades antivirus de SharePoint Online son una forma de contener virus.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-111">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="e9d8c-112">No pretenden ser un punto único de defensa contra el malware en su entorno.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-112">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="e9d8c-113">Recomendamos a todos los clientes que evalúen e implementen la protección antimalware en varias capas y que apliquen los procedimientos recomendados para proteger la infraestructura de la empresa.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-113">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="e9d8c-114">Para obtener más información acerca de las estrategias y los procedimientos recomendados, consulte [plan de seguridad](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="e9d8c-114">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span> 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="e9d8c-115">¿Qué ocurre cuando se carga un archivo infectado en SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="e9d8c-115">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="e9d8c-116">Office 365 usa un motor de detección de virus común.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-116">Office 365 uses a common virus detection engine.</span></span> <span data-ttu-id="e9d8c-117">El motor se ejecuta de forma asincrónica dentro de SharePoint Online y examina los archivos después de que se cargan.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-117">The engine runs asynchronously within SharePoint Online, and scans files after they're uploaded.</span></span> <span data-ttu-id="e9d8c-118">Cuando se encuentra un archivo que contiene un virus, se marca para que no se pueda descargar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-118">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="e9d8c-119">En abril de 2018, eliminamos el límite de 25 MB para los archivos examinados.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-119">In April 2018, we removed the 25 MB limit for scanned files.</span></span>
  
<span data-ttu-id="e9d8c-120">Esto es lo que sucede:</span><span class="sxs-lookup"><span data-stu-id="e9d8c-120">Here's what happens:</span></span>
  
1. <span data-ttu-id="e9d8c-121">Un usuario carga un archivo en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-121">A user uploads a file to SharePoint Online.</span></span>
    
2. <span data-ttu-id="e9d8c-122">El motor de detección de virus examina el archivo.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-122">The virus detection engine scans the file.</span></span>
    
3. <span data-ttu-id="e9d8c-123">Si se encuentra un virus, el motor del virus establece una propiedad en el archivo que indica que está infectado.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-123">If a virus is found, the virus engine sets a property on the file indicating that it is infected.</span></span>
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="e9d8c-124">¿Qué sucede cuando un usuario intenta descargar un archivo infectado con el explorador?</span><span class="sxs-lookup"><span data-stu-id="e9d8c-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="e9d8c-125">Si un archivo está infectado con un virus, los usuarios no pueden descargar el archivo de SharePoint Online con el explorador.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-125">If a file is infected with a virus, users can't download the file from SharePoint Online by using the browser.</span></span>
  
<span data-ttu-id="e9d8c-126">Esto es lo que sucede:</span><span class="sxs-lookup"><span data-stu-id="e9d8c-126">Here's what happens:</span></span>
  
1. <span data-ttu-id="e9d8c-127">Un usuario abre un explorador web e intenta descargar un archivo infectado de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
    
2. <span data-ttu-id="e9d8c-128">Al usuario se le advierte de que se ha detectado un virus.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="e9d8c-129">Al usuario se le ofrece la opción de descargar el archivo e intentar limpiarlo mediante su propio software antivirus.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-129">The user is given the option to download the file and attempt to clean it using their own virus software.</span></span>

> [!NOTE]
> <span data-ttu-id="e9d8c-130">Puede usar el cmdlet Set-SPOTenant con el parámetro **DisallowInfectedFileDownload** para no permitir que los usuarios descarguen un archivo detectado, incluso en la ventana de advertencia de antivirus.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-130">You can use the Set-SPOTenant cmdlet with the **DisallowInfectedFileDownload** parameter to not allow users to download a detected file, even in the anti-virus warning window.</span></span> <span data-ttu-id="e9d8c-131">Consulte [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="e9d8c-131">See [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="e9d8c-132">¿Qué sucede cuando el cliente de sincronización de OneDrive intenta sincronizar un archivo infectado?</span><span class="sxs-lookup"><span data-stu-id="e9d8c-132">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="e9d8c-133">Si los usuarios sincronizan archivos con el nuevo cliente de sincronización de OneDrive (OneDrive. exe) o el anterior cliente de sincronización de OneDrive para la empresa (Groove. exe), si un archivo contiene un virus, el cliente de sincronización no lo descargará.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-133">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="e9d8c-134">El cliente de sincronización mostrará una notificación de que el archivo no se puede sincronizar.</span><span class="sxs-lookup"><span data-stu-id="e9d8c-134">The sync client will display a notification that the file can't be synced.</span></span>
  

