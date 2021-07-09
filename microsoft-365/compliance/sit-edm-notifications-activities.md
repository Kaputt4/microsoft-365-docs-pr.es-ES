---
title: Crear notificaciones para actividades de coincidencia exacta de datos
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo crear notificaciones para actividades de coincidencia exacta de datos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 263dc319d7e7d3ee5f12ebe374e8f5bd44c4cc8c
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341681"
---
# <a name="create-notifications-for-exact-data-match-activities"></a><span data-ttu-id="c50c6-103">Crear notificaciones para actividades de coincidencia exacta de datos</span><span class="sxs-lookup"><span data-stu-id="c50c6-103">Create notifications for exact data match activities</span></span>

<span data-ttu-id="c50c6-104">Cuando [crea tipos de información confidencial personalizados con coincidencia exacta de datos (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) hay una serie de actividades que se crean en el [registro de auditoría](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log).</span><span class="sxs-lookup"><span data-stu-id="c50c6-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log).</span></span> <span data-ttu-id="c50c6-105">Puede utilizar el cmdlet de PowerShell [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) para crear notificaciones que le permitan saber cuándo se producen estas actividades:</span><span class="sxs-lookup"><span data-stu-id="c50c6-105">You can use the [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="c50c6-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="c50c6-106">CreateSchema</span></span>
- <span data-ttu-id="c50c6-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="c50c6-107">EditSchema</span></span>
- <span data-ttu-id="c50c6-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="c50c6-108">RemoveSchema</span></span>
- <span data-ttu-id="c50c6-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="c50c6-109">UploadDataFailed</span></span>
- <span data-ttu-id="c50c6-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="c50c6-110">UploadDataCompleted</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="c50c6-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c50c6-111">Pre-requisites</span></span>

<span data-ttu-id="c50c6-112">La cuenta que use debe estar en uno de los siguientes roles:</span><span class="sxs-lookup"><span data-stu-id="c50c6-112">The account you use must be one of the following:</span></span>

- <span data-ttu-id="c50c6-113">un administrador global</span><span class="sxs-lookup"><span data-stu-id="c50c6-113">a global admin</span></span>
- <span data-ttu-id="c50c6-114">administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="c50c6-114">compliance administrator</span></span>
- <span data-ttu-id="c50c6-115">administrador de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c50c6-115">Exchange Online administrator</span></span>

<span data-ttu-id="c50c6-116">Para obtener más información acerca de los permisos de DLP, consulte [Permisos](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="c50c6-116">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="c50c6-117">La clasificación basada en EDM se incluye en estas suscripciones:</span><span class="sxs-lookup"><span data-stu-id="c50c6-117">EDM-based classification is included in these subscriptions:</span></span>

- <span data-ttu-id="c50c6-118">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="c50c6-118">Office 365 E5</span></span>
- <span data-ttu-id="c50c6-119">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c50c6-119">Microsoft 365 E5</span></span>
- <span data-ttu-id="c50c6-120">Cumplimiento de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c50c6-120">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="c50c6-121">Gobierno y protección de información de Microsoft E5/A5</span><span class="sxs-lookup"><span data-stu-id="c50c6-121">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="c50c6-122">Para obtener más información sobre las licencias de DLP, consulte la [Guía de licencias de Microsoft 365 para la seguridad y cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span><span class="sxs-lookup"><span data-stu-id="c50c6-122">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="c50c6-123">Configurar notificaciones para actividades de EDM</span><span class="sxs-lookup"><span data-stu-id="c50c6-123">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="c50c6-124">Conectarse al [Centro de seguridad y cumplimiento de PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="c50c6-124">Connect to the [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="c50c6-125">Ejecute el cmdlet `New-ProtectionAlert` con la actividad para la que desea crear la notificación.</span><span class="sxs-lookup"><span data-stu-id="c50c6-125">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="c50c6-126">Por ejemplo, si desea recibir una notificación cuando se produzca la acción **UploadDataCompleted**, ejecute:</span><span class="sxs-lookup"><span data-stu-id="c50c6-126">For example, if you want to be notified when the **UploadDataCompleted** action occurred, run:</span></span>

    ```powershell
    New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <address to send notification to> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
    ```
    
    <span data-ttu-id="c50c6-127">para **UploadDataFailed** puede ejecutar:</span><span class="sxs-lookup"><span data-stu-id="c50c6-127">for the **UploadDataFailed** you can run:</span></span>
    
    ```powershell
    New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <SMTP address to send notification to> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
    ```

## <a name="related-articles"></a><span data-ttu-id="c50c6-128">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="c50c6-128">Related articles</span></span>

- [<span data-ttu-id="c50c6-129">Crear tipos de información confidencial personalizados con coincidencia exacta de datos (EDM)</span><span class="sxs-lookup"><span data-stu-id="c50c6-129">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="c50c6-130">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="c50c6-130">New-ProtectionAlert</span></span>](/powershell/module/exchange/new-protectionalert)