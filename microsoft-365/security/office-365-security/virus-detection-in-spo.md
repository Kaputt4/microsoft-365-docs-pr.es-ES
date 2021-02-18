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
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo SharePoint Online detecta virus en los archivos que los usuarios cargan e impide que los usuarios descarguen o sincronicen los archivos.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0eafb9e5e2f0c9d86791fe83931276e420afcd9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286506"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="900ec-103">Protección antivirus integrada en SharePoint Online, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="900ec-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="900ec-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="900ec-104">**Applies to**</span></span>
- [<span data-ttu-id="900ec-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="900ec-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="900ec-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="900ec-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

<span data-ttu-id="900ec-107">Microsoft 365 usa un motor de detección de virus común para examinar los archivos que los usuarios cargan en SharePoint Online, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="900ec-107">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="900ec-108">Esta protección se incluye con todas las suscripciones que incluyen SharePoint Online, OneDrive y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="900ec-108">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="900ec-109">Las funcionalidades antivirus integradas son una forma de ayudar a contener virus.</span><span class="sxs-lookup"><span data-stu-id="900ec-109">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="900ec-110">No están pensadas como un único punto de defensa contra el malware para su entorno.</span><span class="sxs-lookup"><span data-stu-id="900ec-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="900ec-111">Animamos a todos los clientes a investigar e implementar la protección antimalware en varias capas y aplicar procedimientos recomendados para proteger su infraestructura empresarial.</span><span class="sxs-lookup"><span data-stu-id="900ec-111">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="900ec-112">Para obtener más información acerca de las estrategias y los procedimientos recomendados, vea [el mapa de ruta de seguridad.](security-roadmap.md)</span><span class="sxs-lookup"><span data-stu-id="900ec-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="900ec-113">¿Qué sucede cuando se carga un archivo infectado en SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="900ec-113">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="900ec-114">El motor de detección de virus de Microsoft 365 se ejecuta asincrónicamente en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="900ec-114">The Microsoft 365 virus detection engine runs asynchronously within SharePoint Online.</span></span> <span data-ttu-id="900ec-115">**Todos los archivos no se examinan automáticamente al cargarse.**</span><span class="sxs-lookup"><span data-stu-id="900ec-115">**All files are not automatically scanned on upload**.</span></span> <span data-ttu-id="900ec-116">La heurística determina los archivos que se examinarán.</span><span class="sxs-lookup"><span data-stu-id="900ec-116">Heuristics determine the files to scan.</span></span> <span data-ttu-id="900ec-117">Cuando se encuentra que un archivo contiene un virus, el archivo se marca para que no se pueda volver a descargar.</span><span class="sxs-lookup"><span data-stu-id="900ec-117">When a file is found to contain a virus, the file is flagged so it can't be downloaded again.</span></span> <span data-ttu-id="900ec-118">En abril de 2018, eliminamos el límite de 25 MB para los archivos examinados.</span><span class="sxs-lookup"><span data-stu-id="900ec-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="900ec-119">Esto es lo que sucede:</span><span class="sxs-lookup"><span data-stu-id="900ec-119">Here's what happens:</span></span>

1. <span data-ttu-id="900ec-120">Un usuario carga un archivo en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="900ec-120">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="900ec-121">SharePoint Online determina si el archivo cumple los criterios para un examen.</span><span class="sxs-lookup"><span data-stu-id="900ec-121">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="900ec-122">El motor de detección de virus examina el archivo.</span><span class="sxs-lookup"><span data-stu-id="900ec-122">The virus detection engine scans the file.</span></span>
4. <span data-ttu-id="900ec-123">Si se encuentra un virus, el motor de virus establece una propiedad en el archivo que indica que está infectado.</span><span class="sxs-lookup"><span data-stu-id="900ec-123">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="900ec-124">¿Qué sucede cuando un usuario intenta descargar un archivo infectado mediante el explorador?</span><span class="sxs-lookup"><span data-stu-id="900ec-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="900ec-125">Si un archivo está infectado, los usuarios no pueden descargar el archivo desde SharePoint Online mediante un explorador.</span><span class="sxs-lookup"><span data-stu-id="900ec-125">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="900ec-126">Esto es lo que sucede:</span><span class="sxs-lookup"><span data-stu-id="900ec-126">Here's what happens:</span></span>

1. <span data-ttu-id="900ec-127">Un usuario abre un explorador web e intenta descargar un archivo infectado de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="900ec-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="900ec-128">El usuario recibe una advertencia de que se ha detectado un virus.</span><span class="sxs-lookup"><span data-stu-id="900ec-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="900ec-129">De forma predeterminada, el usuario tiene la opción de descargar el archivo e intentar limpiarlo con el software antivirus en su propio dispositivo.</span><span class="sxs-lookup"><span data-stu-id="900ec-129">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="900ec-130">Los administradores pueden usar el parámetro *DisallowInfectedFileDownload* en el cmdlet [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) en SharePoint Online PowerShell para evitar que los usuarios descarguen archivos infectados, incluso en la ventana de advertencia antivirus.</span><span class="sxs-lookup"><span data-stu-id="900ec-130">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="900ec-131">Para obtener instrucciones, [vea Usar SharePoint Online PowerShell para evitar que los usuarios descarguen archivos malintencionados.](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)</span><span class="sxs-lookup"><span data-stu-id="900ec-131">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="900ec-132">Tan pronto como habilites el parámetro *DisallowInfectedFileDownload,* el acceso a los archivos detectados o bloqueados se bloqueará completamente para los usuarios y administradores.</span><span class="sxs-lookup"><span data-stu-id="900ec-132">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="900ec-133">¿Qué sucede cuando el cliente de sincronización de OneDrive intenta sincronizar un archivo infectado?</span><span class="sxs-lookup"><span data-stu-id="900ec-133">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="900ec-134">Los clientes de sincronización de OneDrive no descargarán archivos que contengan virus.</span><span class="sxs-lookup"><span data-stu-id="900ec-134">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="900ec-135">El cliente de sincronización mostrará una notificación de que no se puede sincronizar el archivo.</span><span class="sxs-lookup"><span data-stu-id="900ec-135">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="900ec-136">Funcionalidades extendidas con Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="900ec-136">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="900ec-137">Las organizaciones de Microsoft 365 que tienen Microsoft Defender para [Office 365](office-365-atp.md) incluidas en su suscripción o adquiridas como complemento pueden habilitar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams para mejorar la protección y los informes.</span><span class="sxs-lookup"><span data-stu-id="900ec-137">Microsoft 365 organizations that have [Microsoft Defender for Office 365](office-365-atp.md) included in their subscription or purchased as an add-on can enable Safe Attachments for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="900ec-138">Para obtener más información, vea Datos adjuntos [seguros para SharePoint, OneDrive y Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="900ec-138">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="900ec-139">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="900ec-139">Related Articles</span></span>

[<span data-ttu-id="900ec-140">Protección contra malware y ransomware en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="900ec-140">Malware and ransomware protection in Microsoft 365</span></span>](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)

<span data-ttu-id="900ec-141">Para obtener más información acerca de los antivirus en SharePoint [](protect-against-threats.md) Online, OneDrive y Microsoft Teams, vea Protección contra amenazas y Activar datos adjuntos seguros para [SharePoint, OneDrive](turn-on-atp-for-spo-odb-and-teams.md)y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="900ec-141">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
