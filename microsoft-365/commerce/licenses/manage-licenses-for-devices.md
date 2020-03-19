---
title: Administrar licencias para dispositivos
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Obtenga información sobre cómo asignar licencias a grupos para usarlas con dispositivos.
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: a29465e9425694f8913cc09d1b8a0c761c79803c
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826284"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="db6d1-103">Administrar licencias para dispositivos</span><span class="sxs-lookup"><span data-stu-id="db6d1-103">Manage licenses for devices</span></span>

<span data-ttu-id="db6d1-104">Si tiene Office 365 ProPlus (dispositivo) u Office 365 ProPlus para educación (dispositivo), puede asignar licencias a los dispositivos con grupos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="db6d1-104">If you have Office 365 ProPlus (device) or Office 365 ProPlus for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="db6d1-105">Cuando un dispositivo tiene una licencia, cualquier usuario que use ese dispositivo puede usar Office 365.</span><span class="sxs-lookup"><span data-stu-id="db6d1-105">When a device has a license, anyone who uses that device can use Office 365.</span></span> <span data-ttu-id="db6d1-106">Por ejemplo, supongamos que tiene 20 equipos portátiles y tabletas que usan las personas de su organización.</span><span class="sxs-lookup"><span data-stu-id="db6d1-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="db6d1-107">Cuando se asigna una licencia a cada dispositivo, cada persona que inicie sesión en uno de los dispositivos usa Office 365 sin la necesidad de su propia licencia.</span><span class="sxs-lookup"><span data-stu-id="db6d1-107">When you assign a license to each device, each person who logs in to one of the devices uses Office 365 without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db6d1-108">La licencia basada en dispositivos para Office 365 ProPlus solo está disponible como una licencia de complemento para algunos clientes de commerical y para algunos clientes de educación.</span><span class="sxs-lookup"><span data-stu-id="db6d1-108">Device-based licensing for Office 365 ProPlus is available only as an add-on license for some commerical customers and some education customers.</span></span> <span data-ttu-id="db6d1-109">Para los clientes comerciales, la licencia es *Office 365 ProPlus (dispositivo)* y solo está disponible a través de Enterprise Agreement/Enterprise Agreement subscription.</span><span class="sxs-lookup"><span data-stu-id="db6d1-109">For commercial customers, the license is *Office 365 ProPlus (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="db6d1-110">Para los clientes de educación, la licencia es *Office 365 ProPlus para el ámbito educativo (dispositivo)* y está disponible solo a través de la inscripción para las soluciones educativas (EES).</span><span class="sxs-lookup"><span data-stu-id="db6d1-110">For education customers, the license is *Office 365 ProPlus for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="db6d1-111">Para obtener más información, lea la entrada de blog sobre la [disponibilidad de educación](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span><span class="sxs-lookup"><span data-stu-id="db6d1-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="db6d1-112">Para obtener disponibilidad comercial, póngase en contacto con el representante de su cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="db6d1-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="db6d1-113">Para empezar, cree un grupo en el centro de administración de Azure Active Directory y, a continuación, asigne dispositivos al grupo.</span><span class="sxs-lookup"><span data-stu-id="db6d1-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="db6d1-114">Para obtener más información sobre las licencias de dispositivos, incluidos los requisitos de dispositivos, los tipos de grupos que puede usar y cómo configurar Office 365 ProPlus para usar licencias de dispositivos, consulte [licencias basadas en dispositivos para office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span><span class="sxs-lookup"><span data-stu-id="db6d1-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Office 365 ProPlus to use device licensing, see [Device-based licensing for Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db6d1-115">Debe ser un administrador global para completar las tareas de este artículo.</span><span class="sxs-lookup"><span data-stu-id="db6d1-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="db6d1-116">Asignar licencias a dispositivos</span><span class="sxs-lookup"><span data-stu-id="db6d1-116">Assign licenses to devices</span></span>

<span data-ttu-id="db6d1-117">Cuando se asignan licencias a un grupo, se asignan licencias a todos los dispositivos del grupo.</span><span class="sxs-lookup"><span data-stu-id="db6d1-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="db6d1-118">Solo se puede asignar una suscripción a un único grupo.</span><span class="sxs-lookup"><span data-stu-id="db6d1-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="db6d1-119">En el centro de administración de Microsoft 365, vaya a la página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licencias</a> de **facturación** > .</span><span class="sxs-lookup"><span data-stu-id="db6d1-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="db6d1-120">En la página **licencias** , elija **Office 365 ProPlus para educación (dispositivo)** u **Office ProPlus (dispositivo)**.</span><span class="sxs-lookup"><span data-stu-id="db6d1-120">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)** or **Office ProPlus (device)**.</span></span>
3. <span data-ttu-id="db6d1-121">En la página siguiente, elija una suscripción y, a continuación, elija **asignar licencias**.</span><span class="sxs-lookup"><span data-stu-id="db6d1-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="db6d1-122">En el panel **asignar licencias a un grupo** , empiece a escribir un nombre de grupo y, a continuación, selecciónelo en los resultados para agregarlo a la lista.</span><span class="sxs-lookup"><span data-stu-id="db6d1-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="db6d1-123">Elija **asignar**y, después, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="db6d1-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="db6d1-124">Cancelar la asignación de licencias de dispositivos</span><span class="sxs-lookup"><span data-stu-id="db6d1-124">Unassign licenses from devices</span></span>

<span data-ttu-id="db6d1-125">Al anular la asignación de licencias de un grupo, se quitan las licencias de todos los dispositivos dentro del grupo.</span><span class="sxs-lookup"><span data-stu-id="db6d1-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="db6d1-126">Todas las aplicaciones y sus datos asociados son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="db6d1-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="db6d1-127">En el centro de administración, vaya a la página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licencias</a> de **facturación** > .</span><span class="sxs-lookup"><span data-stu-id="db6d1-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="db6d1-128">En la página **licencias** , elija **Office 365 ProPlus para educación (dispositivo)** u **Office ProPlus (dispositivo)**.</span><span class="sxs-lookup"><span data-stu-id="db6d1-128">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)** or **Office ProPlus (device)**.</span></span>
3. <span data-ttu-id="db6d1-129">En la página siguiente, elija una suscripción, elija **más acciones**y, a continuación, elija **Cancelar asignación de licencias**.</span><span class="sxs-lookup"><span data-stu-id="db6d1-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="db6d1-130">En el cuadro de diálogo **cancelar la asignación de licencias** , elija **Anular asignación**.</span><span class="sxs-lookup"><span data-stu-id="db6d1-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>