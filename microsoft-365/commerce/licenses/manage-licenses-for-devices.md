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
ms.openlocfilehash: c7c747d5f4d2408b717bf16068d23c7882c2d667
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246352"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="d263f-103">Administrar licencias para dispositivos</span><span class="sxs-lookup"><span data-stu-id="d263f-103">Manage licenses for devices</span></span>

<span data-ttu-id="d263f-104">Si tiene Office 365 ProPlus for Education (dispositivo), puede asignar licencias a los dispositivos con grupos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d263f-104">If you have Office 365 ProPlus for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="d263f-105">Cuando un dispositivo tiene una licencia, cualquier usuario que use ese dispositivo puede usar Office 365.</span><span class="sxs-lookup"><span data-stu-id="d263f-105">When a device has a license, anyone who uses that device can use Office 365.</span></span> <span data-ttu-id="d263f-106">Por ejemplo, supongamos que tiene 20 equipos portátiles y tabletas que usan las personas de su organización.</span><span class="sxs-lookup"><span data-stu-id="d263f-106">For example, let’s say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="d263f-107">Cuando se asigna una licencia a cada dispositivo, cada persona que inicie sesión en uno de los dispositivos usa Office 365 sin la necesidad de su propia licencia.</span><span class="sxs-lookup"><span data-stu-id="d263f-107">When you assign a license to each device, each person who logs in to one of the devices uses Office 365 without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d263f-108">Office 365 ProPlus para el ámbito educativo (dispositivo) solo está disponible para los clientes de licencias por volumen a3 y A5.</span><span class="sxs-lookup"><span data-stu-id="d263f-108">Office 365 ProPlus for Education (device) is only available to Education A3 and A5 volume licensing customers.</span></span>

<span data-ttu-id="d263f-109">Para empezar, cree un grupo en el centro de administración de Azure Active Directory y, a continuación, asigne dispositivos al grupo.</span><span class="sxs-lookup"><span data-stu-id="d263f-109">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="d263f-110">Para obtener más información sobre las licencias de dispositivos, incluidos los requisitos de dispositivos, los tipos de grupos que puede usar y cómo configurar Office 365 ProPlus para usar licencias de dispositivos, vea [licencias de dispositivos para office 365 ProPlus para educación para clientes](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span><span class="sxs-lookup"><span data-stu-id="d263f-110">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Office 365 ProPlus to use device licensing, see [Device licensing for Office 365 ProPlus for Education customers](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d263f-111">Debe ser un administrador global para completar las tareas de este artículo.</span><span class="sxs-lookup"><span data-stu-id="d263f-111">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="d263f-112">Asignar licencias a dispositivos</span><span class="sxs-lookup"><span data-stu-id="d263f-112">Assign licenses to devices</span></span>

<span data-ttu-id="d263f-113">Cuando se asignan licencias a un grupo, se asignan licencias a todos los dispositivos del grupo.</span><span class="sxs-lookup"><span data-stu-id="d263f-113">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="d263f-114">Solo se puede asignar una suscripción a un único grupo.</span><span class="sxs-lookup"><span data-stu-id="d263f-114">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="d263f-115">En el centro de administración de Microsoft 365, vaya a la página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licencias</a> de **facturación** > .</span><span class="sxs-lookup"><span data-stu-id="d263f-115">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="d263f-116">En la página **licencias** , elija **Office 365 ProPlus para educación (dispositivo)**.</span><span class="sxs-lookup"><span data-stu-id="d263f-116">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)**.</span></span>
3. <span data-ttu-id="d263f-117">En la página **Office 365 ProPlus para educación (dispositivo)** , elija una suscripción y, a continuación, elija **asignar licencias**.</span><span class="sxs-lookup"><span data-stu-id="d263f-117">On the **Office 365 ProPlus for Education (device)** page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="d263f-118">En el panel **asignar licencias a un grupo** , empiece a escribir un nombre de grupo y, a continuación, selecciónelo en los resultados para agregarlo a la lista.</span><span class="sxs-lookup"><span data-stu-id="d263f-118">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
6. <span data-ttu-id="d263f-119">Elija **asignar**y, después, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="d263f-119">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="d263f-120">Cancelar la asignación de licencias de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d263f-120">Unassign licenses from devices</span></span>

<span data-ttu-id="d263f-121">Al anular la asignación de licencias de un grupo, se quitan las licencias de todos los dispositivos dentro del grupo.</span><span class="sxs-lookup"><span data-stu-id="d263f-121">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="d263f-122">Todas las aplicaciones y sus datos asociados son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="d263f-122">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="d263f-123">En el centro de administración, vaya a la página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licencias</a> de **facturación** > .</span><span class="sxs-lookup"><span data-stu-id="d263f-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="d263f-124">En la página **licencias** , elija **Office 365 ProPlus para educación (dispositivo)**.</span><span class="sxs-lookup"><span data-stu-id="d263f-124">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)**.</span></span>
3. <span data-ttu-id="d263f-125">En la página **Office 365 ProPlus para educación (dispositivo)** , elija una suscripción, elija **más acciones**y, a continuación, elija **Cancelar asignación de licencias**.</span><span class="sxs-lookup"><span data-stu-id="d263f-125">On the **Office 365 ProPlus for Education (device)** page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
5. <span data-ttu-id="d263f-126">En el cuadro de diálogo **cancelar la asignación de licencias** , elija **Anular asignación**.</span><span class="sxs-lookup"><span data-stu-id="d263f-126">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>