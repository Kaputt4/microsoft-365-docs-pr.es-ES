---
title: Protección antivirus integrada en SharePoint Online, OneDrive y Microsoft Teams
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
ms.openlocfilehash: f774c9afd0988c504d6207b0e71ee9561312e6b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844241"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="3e596-103">Protección antivirus integrada en SharePoint Online, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3e596-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3e596-104">Microsoft 365 usa un motor de detección de virus común para analizar los archivos que los usuarios cargan en SharePoint Online, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3e596-104">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="3e596-105">Esta protección se incluye con todas las suscripciones que incluyen SharePoint Online, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3e596-105">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e596-106">Las capacidades antivirus integradas son una forma de ayudar a contener virus.</span><span class="sxs-lookup"><span data-stu-id="3e596-106">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="3e596-107">No pretenden ser un punto único de defensa contra el malware en su entorno.</span><span class="sxs-lookup"><span data-stu-id="3e596-107">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="3e596-108">Recomendamos a todos los clientes que investiguen y implementen la protección antimalware en varias capas y que apliquen los procedimientos recomendados para proteger su infraestructura empresarial.</span><span class="sxs-lookup"><span data-stu-id="3e596-108">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="3e596-109">Para obtener más información acerca de las estrategias y los procedimientos recomendados, consulte [plan de seguridad](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="3e596-109">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="3e596-110">¿Qué ocurre cuando se carga un archivo infectado en SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="3e596-110">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="3e596-111">El motor de detección de virus de Microsoft 365 se ejecuta de forma asincrónica dentro de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3e596-111">The Microsoft 365 virus detection engine runs asynchronously within SharePoint Online.</span></span> <span data-ttu-id="3e596-112">**No se examinan automáticamente todos los archivos al cargarlos**.</span><span class="sxs-lookup"><span data-stu-id="3e596-112">**All files are not automatically scanned on upload**.</span></span> <span data-ttu-id="3e596-113">La heurística determina los archivos que se van a analizar.</span><span class="sxs-lookup"><span data-stu-id="3e596-113">Heuristics determine the files to scan.</span></span> <span data-ttu-id="3e596-114">Cuando se encuentra un archivo que contiene un virus, el archivo se marca para que no se pueda descargar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="3e596-114">When a file is found to contain a virus, the file is flagged so it can't be downloaded again.</span></span> <span data-ttu-id="3e596-115">En abril de 2018, eliminamos el límite de 25 MB para los archivos examinados.</span><span class="sxs-lookup"><span data-stu-id="3e596-115">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="3e596-116">Esto es lo que sucede:</span><span class="sxs-lookup"><span data-stu-id="3e596-116">Here's what happens:</span></span>

1. <span data-ttu-id="3e596-117">Un usuario carga un archivo en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3e596-117">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="3e596-118">SharePoint Online determina si el archivo cumple los criterios de un examen.</span><span class="sxs-lookup"><span data-stu-id="3e596-118">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="3e596-119">El motor de detección de virus examina el archivo.</span><span class="sxs-lookup"><span data-stu-id="3e596-119">The virus detection engine scans the file.</span></span>
4. <span data-ttu-id="3e596-120">Si se encuentra un virus, el motor del virus establece una propiedad en el archivo que indica que está infectado.</span><span class="sxs-lookup"><span data-stu-id="3e596-120">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="3e596-121">¿Qué sucede cuando un usuario intenta descargar un archivo infectado con el explorador?</span><span class="sxs-lookup"><span data-stu-id="3e596-121">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="3e596-122">Si un archivo está infectado, los usuarios no pueden descargar el archivo de SharePoint Online con un explorador.</span><span class="sxs-lookup"><span data-stu-id="3e596-122">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="3e596-123">Esto es lo que sucede:</span><span class="sxs-lookup"><span data-stu-id="3e596-123">Here's what happens:</span></span>

1. <span data-ttu-id="3e596-124">Un usuario abre un explorador web e intenta descargar un archivo infectado de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3e596-124">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="3e596-125">Al usuario se le advierte de que se ha detectado un virus.</span><span class="sxs-lookup"><span data-stu-id="3e596-125">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="3e596-126">De forma predeterminada, se ofrece al usuario la opción de descargar el archivo e intentar limpiarlo mediante el software antivirus en su propio dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3e596-126">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="3e596-127">Los administradores pueden usar el parámetro *DisallowInfectedFileDownload* en el cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) de SharePoint Online PowerShell para evitar que los usuarios descarguen archivos infectados, incluso en la ventana de advertencia de antivirus.</span><span class="sxs-lookup"><span data-stu-id="3e596-127">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="3e596-128">Para obtener instrucciones, vea [usar SharePoint Online PowerShell para evitar que los usuarios descarguen archivos malintencionados](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span><span class="sxs-lookup"><span data-stu-id="3e596-128">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="3e596-129">En cuanto se habilita el parámetro *DisallowInfectedFileDownload* , el acceso a los archivos detectados o bloqueados se bloquea completamente para los usuarios y los administradores.</span><span class="sxs-lookup"><span data-stu-id="3e596-129">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="3e596-130">¿Qué sucede cuando el cliente de sincronización de OneDrive intenta sincronizar un archivo infectado?</span><span class="sxs-lookup"><span data-stu-id="3e596-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="3e596-131">Los clientes de sincronización de OneDrive no podrán descargar archivos que contengan virus.</span><span class="sxs-lookup"><span data-stu-id="3e596-131">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="3e596-132">El cliente de sincronización mostrará una notificación de que el archivo no se puede sincronizar.</span><span class="sxs-lookup"><span data-stu-id="3e596-132">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="3e596-133">Capacidades ampliadas con Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="3e596-133">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="3e596-134">Microsoft 365 organizaciones que tienen [Microsoft defender para Office 365](office-365-atp.md) incluidas en su suscripción o que se han comprado como complementos pueden habilitar ATP para SharePoint, OneDrive y Microsoft Teams para mejorar el informe y la protección.</span><span class="sxs-lookup"><span data-stu-id="3e596-134">Microsoft 365 organizations that have [Microsoft Defender for Office 365](office-365-atp.md) included in their subscription or purchased as an add-on can enable ATP for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="3e596-135">Para obtener más información, consulte [ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="3e596-135">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

## <a name="more-information"></a><span data-ttu-id="3e596-136">Más información</span><span class="sxs-lookup"><span data-stu-id="3e596-136">More information</span></span>

<span data-ttu-id="3e596-137">Para obtener más información sobre los antivirus en SharePoint Online, OneDrive y Microsoft Teams, consulte [proteger contra amenazas](protect-against-threats.md) y [Activar ATP para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="3e596-137">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
