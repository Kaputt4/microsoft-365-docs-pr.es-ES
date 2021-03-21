---
title: Crear notificaciones para actividades de coincidencia exacta de datos (vista previa)
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
description: Obtenga información sobre como crear notificaciones para actividades de coincidencia exacta de datos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2e2f67ef0f276211483519bd5e246e4e041b2b15
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919366"
---
# <a name="create-notifications-for-exact-data-match-activities-preview"></a><span data-ttu-id="9544d-103">Crear notificaciones para actividades de coincidencia exacta de datos (vista previa)</span><span class="sxs-lookup"><span data-stu-id="9544d-103">Create notifications for exact data match activities (preview)</span></span>

<span data-ttu-id="9544d-104">Cuando [crea tipos de información confidencial personalizados con coincidencia exacta de datos (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) hay una serie de actividades que se crean en el [registro de auditoría](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span><span class="sxs-lookup"><span data-stu-id="9544d-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span> <span data-ttu-id="9544d-105">Puede utilizar el cmdlet de PowerShell [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) para crear notificaciones que le permitan saber cuándo se producen estas actividades:</span><span class="sxs-lookup"><span data-stu-id="9544d-105">You can use the [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="9544d-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="9544d-106">CreateSchema</span></span>
- <span data-ttu-id="9544d-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="9544d-107">EditSchema</span></span>
- <span data-ttu-id="9544d-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="9544d-108">RemoveSchema</span></span>
- <span data-ttu-id="9544d-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="9544d-109">UploadDataFailed</span></span>
- <span data-ttu-id="9544d-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="9544d-110">UploadDataCompleted</span></span>

> [!NOTE]
> <span data-ttu-id="9544d-111">La capacidad de crear notificaciones de actividades de EDM solo está disponible para las nubes de World Wide y GCC.</span><span class="sxs-lookup"><span data-stu-id="9544d-111">The ability to create notifications for EDM activities is only available for the World Wide and GCC clouds only.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="9544d-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9544d-112">Pre-requisites</span></span>

<span data-ttu-id="9544d-113">La cuenta que use debe estar en uno de los siguientes roles:</span><span class="sxs-lookup"><span data-stu-id="9544d-113">The account you use must be one of the following:</span></span>

- <span data-ttu-id="9544d-114">un administrador global</span><span class="sxs-lookup"><span data-stu-id="9544d-114">a global admin</span></span>
- <span data-ttu-id="9544d-115">administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="9544d-115">compliance administrator</span></span>
- <span data-ttu-id="9544d-116">administrador de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9544d-116">Exchange Online administrator</span></span>

<span data-ttu-id="9544d-117">Para obtener más información acerca de los permisos de DLP, consulte [Permisos](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="9544d-117">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="9544d-118">La clasificación basada en EDM se incluye en estas suscripciones</span><span class="sxs-lookup"><span data-stu-id="9544d-118">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="9544d-119">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="9544d-119">Office 365 E5</span></span>
- <span data-ttu-id="9544d-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="9544d-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="9544d-121">Cumplimiento de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="9544d-121">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="9544d-122">Gobierno y protección de información de Microsoft E5/A5</span><span class="sxs-lookup"><span data-stu-id="9544d-122">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="9544d-123">Para obtener más información sobre las licencias de DLP, vea la [Guía de licencias de Microsoft 365 para la seguridad y cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span><span class="sxs-lookup"><span data-stu-id="9544d-123">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="9544d-124">Configurar notificaciones de actividades de EDM</span><span class="sxs-lookup"><span data-stu-id="9544d-124">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="9544d-125">Conectarse al [Centro de seguridad y cumplimiento de PowerShell](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="9544d-125">Connect to the [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span></span> 

2. <span data-ttu-id="9544d-126">Ejecute el cmdlet `New-ProtectionAlert` con la actividad para la que desea crear la notificación.</span><span class="sxs-lookup"><span data-stu-id="9544d-126">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="9544d-127">Por ejemplo, si desea que se le notifique cuando se produzca la acción **UploadDataCompleted**, ejecute</span><span class="sxs-lookup"><span data-stu-id="9544d-127">For example, if you want to be notified when the **UploadDataCompleted** action occured, run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

<span data-ttu-id="9544d-128">para **UploadDataFailed** puede ejecutar</span><span class="sxs-lookup"><span data-stu-id="9544d-128">for the **UploadDataFailed** you can run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a><span data-ttu-id="9544d-129">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="9544d-129">Related articles</span></span>

- [<span data-ttu-id="9544d-130">Crear tipos de información confidencial personalizados con coincidencia exacta de datos (EDM)</span><span class="sxs-lookup"><span data-stu-id="9544d-130">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="9544d-131">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="9544d-131">New-ProtectionAlert</span></span>](/powershell/module/exchange/new-protectionalert?view=exchange-ps)