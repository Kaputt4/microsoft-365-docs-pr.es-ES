---
title: Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Obtenga información sobre Microsoft Defender para Office 365 para archivos en SharePoint Online, OneDrive para la Empresa y Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9b69d2b6f075539f411da971a314c127843b945a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917575"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="65dcd-103">Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="65dcd-103">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="65dcd-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="65dcd-104">**Applies to**</span></span>
- [<span data-ttu-id="65dcd-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="65dcd-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="65dcd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65dcd-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="65dcd-107">Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams en [Microsoft Defender para Office 365](office-365-atp.md) proporciona una capa adicional de protección para los archivos que ya han sido examinados en el momento de la carga por el motor de detección de virus común en Microsoft [365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="65dcd-107">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](office-365-atp.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="65dcd-108">Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams ayuda a detectar y bloquear archivos existentes que se identifican como malintencionados en sitios de grupo y bibliotecas de documentos.</span><span class="sxs-lookup"><span data-stu-id="65dcd-108">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="65dcd-109">Los datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams no están habilitados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="65dcd-109">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="65dcd-110">Para activarlo, vea [Activar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="65dcd-110">To turn it on, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="65dcd-111">Cómo funcionan los datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="65dcd-111">How Safe Attachments for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="65dcd-112">Cuando los datos adjuntos seguros de SharePoint, OneDrive y Microsoft Teams están habilitados e identifican un archivo como malintencionado, el archivo se bloquea mediante la integración directa con los almacenes de archivos.</span><span class="sxs-lookup"><span data-stu-id="65dcd-112">When Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="65dcd-113">En la siguiente imagen se muestra un ejemplo de un archivo malintencionado detectado en una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="65dcd-113">The following image shows an example of a malicious file detected in a library.</span></span>

![Archivos en OneDrive para la Empresa con uno detectado como malintencionado](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="65dcd-115">Aunque el archivo bloqueado todavía se muestra en la biblioteca de documentos y en aplicaciones web, móviles o de escritorio, las personas no pueden abrir, copiar, mover o compartir el archivo.</span><span class="sxs-lookup"><span data-stu-id="65dcd-115">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="65dcd-116">Pero pueden eliminar el archivo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="65dcd-116">But they can delete the blocked file.</span></span>

<span data-ttu-id="65dcd-117">Este es un ejemplo de cómo es un archivo bloqueado en un dispositivo móvil:</span><span class="sxs-lookup"><span data-stu-id="65dcd-117">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Eliminación de un archivo bloqueado de OneDrive para la Empresa desde la aplicación móvil de OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="65dcd-119">De forma predeterminada, los usuarios pueden descargar un archivo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="65dcd-119">By default, people can download a blocked file.</span></span> <span data-ttu-id="65dcd-120">Este es el aspecto que tiene la descarga de un archivo bloqueado en un dispositivo móvil:</span><span class="sxs-lookup"><span data-stu-id="65dcd-120">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![Descargar un archivo bloqueado en OneDrive para la Empresa](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="65dcd-122">Los administradores de SharePoint Online pueden impedir que los usuarios descarguen archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="65dcd-122">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="65dcd-123">Para obtener instrucciones, [vea Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span><span class="sxs-lookup"><span data-stu-id="65dcd-123">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="65dcd-124">Para obtener más información sobre la experiencia del usuario cuando un archivo se ha detectado como malintencionado, vea [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span><span class="sxs-lookup"><span data-stu-id="65dcd-124">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="65dcd-125">Ver información sobre los archivos malintencionados detectados por datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="65dcd-125">View information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="65dcd-126">Los archivos identificados como malintencionados por Microsoft Defender para Office 365 se mostrarán en informes de [Microsoft Defender para Office 365](view-reports-for-atp.md) y en el Explorador (y detecciones en tiempo [real).](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="65dcd-126">Files that are identified as malicious by Microsoft Defender for Office 365 will show up in [reports for Microsoft Defender for Office 365](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="65dcd-127">A partir de mayo de 2018, cuando Microsoft Defender para Office 365 identifica un archivo como malintencionado, el archivo también está disponible en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="65dcd-127">As of May 2018, when a file is identified as malicious by Microsoft Defender for Office 365, the file is also available in quarantine.</span></span> <span data-ttu-id="65dcd-128">Para obtener más información, vea [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).</span><span class="sxs-lookup"><span data-stu-id="65dcd-128">For more information, see [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="65dcd-129">Tenga en cuenta estos puntos</span><span class="sxs-lookup"><span data-stu-id="65dcd-129">Keep these points in mind</span></span>

- <span data-ttu-id="65dcd-130">Defender para Office 365 no examinará todos los archivos de SharePoint Online, OneDrive para la Empresa o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="65dcd-130">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="65dcd-131">Esto es así por motivos de diseño.</span><span class="sxs-lookup"><span data-stu-id="65dcd-131">This is by design.</span></span> <span data-ttu-id="65dcd-132">Los archivos se examinan de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="65dcd-132">Files are scanned asynchronously.</span></span> <span data-ttu-id="65dcd-133">El proceso usa eventos de actividad de invitado y uso compartido junto con heurística inteligente y señales de amenaza para identificar archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="65dcd-133">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="65dcd-134">Asegúrese de que los sitios de SharePoint están configurados para usar la [experiencia moderna](/sharepoint/guide-to-sharepoint-modern-experience).</span><span class="sxs-lookup"><span data-stu-id="65dcd-134">Make sure your SharePoint sites are configured to use the [Modern experience](/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="65dcd-135">La protección de Defender para Office 365 se aplica tanto si se usa la experiencia moderna como la vista clásica; sin embargo, los indicadores visuales de que un archivo está bloqueado solo están disponibles en la experiencia moderna.</span><span class="sxs-lookup"><span data-stu-id="65dcd-135">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="65dcd-136">Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams forma parte de la estrategia general de protección contra amenazas de su organización, que incluye protección contra correo no deseado y antimalware en Exchange Online Protection (EOP), así como vínculos seguros y datos adjuntos seguros en Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="65dcd-136">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="65dcd-137">Para obtener más información, vea [Protect against threats in Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="65dcd-137">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>