---
title: ATP para SharePoint, OneDrive y Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365-initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Obtenga información sobre la protección contra amenazas avanzada de Office 365 para archivos en SharePoint Online, OneDrive para la empresa y Microsoft Teams.
ms.openlocfilehash: e36efba37ae21ee1e2044d8b631cb14b17fcca55
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48411763"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="9a579-103">ATP para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a579-103">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9a579-104">ATP para SharePoint, OneDrive y Microsoft Teams en [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) proporciona una capa adicional de protección para los archivos que el [motor de detección de virus Common](virus-detection-in-spo.md)ha examinado en el momento de la carga en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9a579-104">ATP for SharePoint, OneDrive, and Microsoft Teams in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="9a579-105">ATP para SharePoint, OneDrive y Microsoft Teams ayuda a detectar y bloquear los archivos existentes identificados como malintencionados en los sitios de grupo y las bibliotecas de documentos.</span><span class="sxs-lookup"><span data-stu-id="9a579-105">ATP for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="9a579-106">ATP para SharePoint, OneDrive y Microsoft Teams no está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9a579-106">ATP for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="9a579-107">Para activarla, consulte [Activar ATP para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9a579-107">To turn it on, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="9a579-108">Cómo funciona ATP para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a579-108">How ATP for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="9a579-109">Cuando ATP para SharePoint, OneDrive y Microsoft Teams está habilitado e identifica un archivo como malintencionado, el archivo se bloquea mediante la integración directa con los almacenes de archivos.</span><span class="sxs-lookup"><span data-stu-id="9a579-109">When ATP for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="9a579-110">La imagen siguiente muestra un ejemplo de un archivo malintencionado detectado en una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="9a579-110">The following image shows an example of a malicious file detected in a library.</span></span>

![Archivos en OneDrive para la empresa con uno detectado como malintencionado](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="9a579-112">Aunque el archivo bloqueado todavía aparece en la biblioteca de documentos y en las aplicaciones Web, móviles o de escritorio, los usuarios no pueden abrir, copiar, mover ni compartir el archivo.</span><span class="sxs-lookup"><span data-stu-id="9a579-112">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="9a579-113">Pero pueden eliminar el archivo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="9a579-113">But they can delete the blocked file.</span></span>

<span data-ttu-id="9a579-114">Este es un ejemplo de la apariencia de un archivo bloqueado en un dispositivo móvil:</span><span class="sxs-lookup"><span data-stu-id="9a579-114">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Eliminación de un archivo bloqueado de OneDrive para la empresa desde la aplicación móvil de OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="9a579-116">De forma predeterminada, los usuarios pueden descargar un archivo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="9a579-116">By default, people can download a blocked file.</span></span> <span data-ttu-id="9a579-117">Esto es lo que parece descargar un archivo bloqueado en un dispositivo móvil:</span><span class="sxs-lookup"><span data-stu-id="9a579-117">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![Descargar un archivo bloqueado en OneDrive para la empresa](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="9a579-119">Los administradores de SharePoint Online pueden impedir que los usuarios descarguen archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="9a579-119">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="9a579-120">Para obtener instrucciones, vea [usar SharePoint Online PowerShell para evitar que los usuarios descarguen archivos malintencionados](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span><span class="sxs-lookup"><span data-stu-id="9a579-120">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="9a579-121">Para obtener más información acerca de la experiencia del usuario cuando un archivo se ha detectado como malintencionado, consulte [Qué hacer cuando se encuentra un archivo malintencionado en SharePoint Online, en OneDrive o en Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span><span class="sxs-lookup"><span data-stu-id="9a579-121">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="9a579-122">Ver información sobre los archivos malintencionados detectados por ATP para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a579-122">View information about malicious files detected by ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="9a579-123">Los archivos identificados como malintencionados por ATP se mostrarán en los [informes de la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md) y en [el explorador (y las detecciones en tiempo real)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="9a579-123">Files that are identified as malicious by ATP will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="9a579-124">A partir del 2018 de mayo, cuando ATP identifica un archivo como malintencionado, el archivo también está disponible en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="9a579-124">As of May 2018, when a file is identified as malicious by ATP, the file is also available in quarantine.</span></span> <span data-ttu-id="9a579-125">Para obtener más información, consulte [use the Security & Compliance Center para administrar los archivos en cuarentena](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span><span class="sxs-lookup"><span data-stu-id="9a579-125">For more information, see [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="9a579-126">Tenga en cuenta estos puntos</span><span class="sxs-lookup"><span data-stu-id="9a579-126">Keep these points in mind</span></span>

- <span data-ttu-id="9a579-127">ATP no examinará cada archivo único en SharePoint Online, OneDrive para la empresa o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9a579-127">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="9a579-128">Esto es así por motivos de diseño.</span><span class="sxs-lookup"><span data-stu-id="9a579-128">This is by design.</span></span> <span data-ttu-id="9a579-129">Los archivos se examinan de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="9a579-129">Files are scanned asynchronously.</span></span> <span data-ttu-id="9a579-130">El proceso usa eventos de actividad de uso compartido e invitado junto con heurísticas inteligentes y señales de amenazas para identificar archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="9a579-130">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="9a579-131">Asegúrese de que los sitios de SharePoint están configurados para usar la [experiencia moderna](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span><span class="sxs-lookup"><span data-stu-id="9a579-131">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="9a579-132">La protección ATP se aplica si se usa la experiencia moderna o la vista clásica; sin embargo, los indicadores visuales que un archivo está bloqueado solo están disponibles en la experiencia moderna.</span><span class="sxs-lookup"><span data-stu-id="9a579-132">ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="9a579-133">ATP para SharePoint, OneDrive y Microsoft Teams forma parte de la estrategia de protección contra amenazas global de su organización, que incluye protección contra correo electrónico no deseado y antimalware en Exchange Online Protection (EOP), así como vínculos seguros y datos adjuntos seguros en Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="9a579-133">ATP for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Office 365 ATP.</span></span> <span data-ttu-id="9a579-134">Para obtener más información, consulte [proteger contra amenazas en Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="9a579-134">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
