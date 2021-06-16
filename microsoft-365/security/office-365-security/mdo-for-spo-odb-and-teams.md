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
ms.openlocfilehash: 7aa375020ce05ca1d484bb7ed18b8cf7a6e7d04e
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2021
ms.locfileid: "52932847"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="e35c8-103">Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e35c8-103">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e35c8-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="e35c8-104">**Applies to**</span></span>
- [<span data-ttu-id="e35c8-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e35c8-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e35c8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e35c8-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e35c8-107">Caja fuerte Los datos adjuntos de SharePoint, OneDrive y Microsoft Teams en [Microsoft Defender para Office 365](whats-new-in-defender-for-office-365.md) proporcionan una capa adicional de protección para los archivos que ya han sido examinados en el momento de la carga por el motor de detección de virus común en [Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="e35c8-107">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="e35c8-108">Caja fuerte Los datos adjuntos SharePoint, OneDrive y Microsoft Teams ayudan a detectar y bloquear archivos existentes que se identifican como malintencionados en sitios de grupo y bibliotecas de documentos.</span><span class="sxs-lookup"><span data-stu-id="e35c8-108">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="e35c8-109">Caja fuerte Los datos adjuntos SharePoint, OneDrive y Microsoft Teams no están habilitados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e35c8-109">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="e35c8-110">Para activarlo, vea [Turn on Caja fuerte Attachments for SharePoint, OneDrive y Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="e35c8-110">To turn it on, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="e35c8-111">Cómo Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams funciona</span><span class="sxs-lookup"><span data-stu-id="e35c8-111">How Safe Attachments for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="e35c8-112">Cuando Caja fuerte datos adjuntos de SharePoint, OneDrive y Microsoft Teams está habilitado e identifica un archivo como malintencionado, el archivo se bloquea mediante la integración directa con los almacenes de archivos.</span><span class="sxs-lookup"><span data-stu-id="e35c8-112">When Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="e35c8-113">La imagen siguiente muestra un ejemplo de un archivo malintencionado detectado en una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e35c8-113">The following image shows an example of a malicious file detected in a library.</span></span>

![Archivos en OneDrive para la Empresa con uno detectado como malintencionado](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="e35c8-115">Aunque el archivo bloqueado todavía se muestra en la biblioteca de documentos y en aplicaciones web, móviles o de escritorio, las personas no pueden abrir, copiar, mover o compartir el archivo.</span><span class="sxs-lookup"><span data-stu-id="e35c8-115">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="e35c8-116">Pero pueden eliminar el archivo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="e35c8-116">But they can delete the blocked file.</span></span>

<span data-ttu-id="e35c8-117">Este es un ejemplo de cómo es un archivo bloqueado en un dispositivo móvil:</span><span class="sxs-lookup"><span data-stu-id="e35c8-117">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Eliminación de un archivo bloqueado OneDrive para la Empresa desde la aplicación OneDrive móvil](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="e35c8-119">De forma predeterminada, los usuarios pueden descargar un archivo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="e35c8-119">By default, people can download a blocked file.</span></span> <span data-ttu-id="e35c8-120">Este es el aspecto que tiene la descarga de un archivo bloqueado en un dispositivo móvil:</span><span class="sxs-lookup"><span data-stu-id="e35c8-120">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![Descargar un archivo bloqueado en OneDrive para la Empresa](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="e35c8-122">SharePoint Los administradores en línea pueden impedir que los usuarios descarguen archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="e35c8-122">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="e35c8-123">Para obtener instrucciones, vea [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span><span class="sxs-lookup"><span data-stu-id="e35c8-123">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="e35c8-124">Para obtener más información acerca de la experiencia del usuario cuando se ha detectado un archivo como malintencionado, vea What [to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span><span class="sxs-lookup"><span data-stu-id="e35c8-124">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="e35c8-125">Ver información sobre archivos malintencionados detectados por Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e35c8-125">View information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="e35c8-126">Los archivos identificados como malintencionados por Caja fuerte Attachments for SharePoint, OneDrive y Microsoft Teams aparecerán en informes de [Microsoft Defender](view-reports-for-mdo.md) para Office 365 y en el Explorador (y detecciones en tiempo [real).](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="e35c8-126">Files that are identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams will show up in [reports for Microsoft Defender for Office 365](view-reports-for-mdo.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="e35c8-127">A partir de mayo de 2018, cuando un archivo se identifica como malintencionado por los datos adjuntos de Caja fuerte para SharePoint, OneDrive y Microsoft Teams, el archivo también está disponible en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="e35c8-127">As of May 2018, when a file is identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, the file is also available in quarantine.</span></span> <span data-ttu-id="e35c8-128">Para obtener más información, vea [Manage quarantined files in Defender for Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="e35c8-128">For more information, see [Manage quarantined files in Defender for Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="e35c8-129">Tenga en cuenta estos puntos</span><span class="sxs-lookup"><span data-stu-id="e35c8-129">Keep these points in mind</span></span>

- <span data-ttu-id="e35c8-130">Defender for Office 365 no examinará todos los archivos de SharePoint Online, OneDrive para la Empresa o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e35c8-130">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="e35c8-131">Esto es así por motivos de diseño.</span><span class="sxs-lookup"><span data-stu-id="e35c8-131">This is by design.</span></span> <span data-ttu-id="e35c8-132">Los archivos se examinan de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="e35c8-132">Files are scanned asynchronously.</span></span> <span data-ttu-id="e35c8-133">El proceso usa eventos de actividad de invitado y uso compartido junto con heurística inteligente y señales de amenaza para identificar archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="e35c8-133">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="e35c8-134">Asegúrese de que los SharePoint están configurados para usar la [experiencia moderna](/sharepoint/guide-to-sharepoint-modern-experience).</span><span class="sxs-lookup"><span data-stu-id="e35c8-134">Make sure your SharePoint sites are configured to use the [Modern experience](/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="e35c8-135">Defender para Office 365 se aplica si se usa la experiencia moderna o la vista clásica; sin embargo, los indicadores visuales de que un archivo está bloqueado solo están disponibles en la experiencia moderna.</span><span class="sxs-lookup"><span data-stu-id="e35c8-135">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="e35c8-136">Caja fuerte Los datos adjuntos de SharePoint, OneDrive y Microsoft Teams forman parte de la estrategia general de protección contra amenazas de su organización, que incluye protección contra correo no deseado y antimalware en Exchange Online Protection (EOP), así como vínculos de Caja fuerte y datos adjuntos de Caja fuerte en Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="e35c8-136">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="e35c8-137">Para obtener más información, vea [Proteger contra amenazas en Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="e35c8-137">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
