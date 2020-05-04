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
ms.openlocfilehash: 1a525117c25a2471ad696ef1447fd7e4ccb6bed0
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011190"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="bda15-103">Administrar licencias para dispositivos</span><span class="sxs-lookup"><span data-stu-id="bda15-103">Manage licenses for devices</span></span>

<span data-ttu-id="bda15-104">Si tiene Microsoft 365 apps for Enterprise (Device) o Microsoft 365 apps for Education (Device), puede asignar licencias a los dispositivos con grupos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bda15-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="bda15-105">Cuando un dispositivo tiene una licencia, cualquier usuario que use ese dispositivo puede usar las aplicaciones de Microsoft 365 para empresas (anteriormente denominado Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="bda15-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="bda15-106">Por ejemplo, supongamos que tiene 20 equipos portátiles y tabletas que usan las personas de su organización.</span><span class="sxs-lookup"><span data-stu-id="bda15-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="bda15-107">Cuando se asigna una licencia a cada dispositivo, todas las personas que inicien sesión en uno de los dispositivos usan las aplicaciones de Microsoft 365 para empresas sin necesidad de su propia licencia.</span><span class="sxs-lookup"><span data-stu-id="bda15-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bda15-108">La licencia basada en dispositivos para las aplicaciones de Microsoft 365 para empresas solo está disponible como licencia de complemento para algunos clientes comerciales y algunos clientes de educación.</span><span class="sxs-lookup"><span data-stu-id="bda15-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="bda15-109">Para los clientes comerciales, la licencia es *Microsoft 365 apps for Enterprise (Device)* y solo está disponible a través de Enterprise Agreement/Enterprise Agreement subscription.</span><span class="sxs-lookup"><span data-stu-id="bda15-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="bda15-110">Para los clientes de educación, la licencia es *Microsoft 365 apps for Education (Device)* y solo está disponible a través de la inscripción para las soluciones educativas (EES).</span><span class="sxs-lookup"><span data-stu-id="bda15-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="bda15-111">Para obtener más información, lea la entrada de blog sobre la [disponibilidad de educación](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span><span class="sxs-lookup"><span data-stu-id="bda15-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="bda15-112">Para obtener disponibilidad comercial, póngase en contacto con el representante de su cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bda15-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="bda15-113">Para empezar, cree un grupo en el centro de administración de Azure Active Directory y, a continuación, asigne dispositivos al grupo.</span><span class="sxs-lookup"><span data-stu-id="bda15-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="bda15-114">Para obtener más información sobre las licencias de dispositivos, incluidos los requisitos de dispositivos, los tipos de grupos que puede usar y cómo configurar las aplicaciones de Microsoft 365 para la empresa para usar licencias de dispositivos, consulte [licencias basadas en dispositivos para microsoft 365 apps for Enterprise](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span><span class="sxs-lookup"><span data-stu-id="bda15-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bda15-115">Debe ser un administrador global para completar las tareas de este artículo.</span><span class="sxs-lookup"><span data-stu-id="bda15-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="bda15-116">Asignar licencias a dispositivos</span><span class="sxs-lookup"><span data-stu-id="bda15-116">Assign licenses to devices</span></span>

<span data-ttu-id="bda15-117">Cuando se asignan licencias a un grupo, se asignan licencias a todos los dispositivos del grupo.</span><span class="sxs-lookup"><span data-stu-id="bda15-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="bda15-118">Solo se puede asignar una suscripción a un único grupo.</span><span class="sxs-lookup"><span data-stu-id="bda15-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="bda15-119">En el centro de administración de Microsoft 365, vaya a la página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licencias</a> de **facturación** > .</span><span class="sxs-lookup"><span data-stu-id="bda15-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="bda15-120">En la página **licencias** , elija **Microsoft 365 apps for Education (Device)** o **Microsoft 365 apps for Enterprise (Device)**.</span><span class="sxs-lookup"><span data-stu-id="bda15-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="bda15-121">En la página siguiente, elija una suscripción y, a continuación, elija **asignar licencias**.</span><span class="sxs-lookup"><span data-stu-id="bda15-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="bda15-122">En el panel **asignar licencias a un grupo** , empiece a escribir un nombre de grupo y, a continuación, selecciónelo en los resultados para agregarlo a la lista.</span><span class="sxs-lookup"><span data-stu-id="bda15-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="bda15-123">Elija **asignar**y, después, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="bda15-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="bda15-124">Cancelar la asignación de licencias de dispositivos</span><span class="sxs-lookup"><span data-stu-id="bda15-124">Unassign licenses from devices</span></span>

<span data-ttu-id="bda15-125">Al anular la asignación de licencias de un grupo, se quitan las licencias de todos los dispositivos dentro del grupo.</span><span class="sxs-lookup"><span data-stu-id="bda15-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="bda15-126">Todas las aplicaciones y sus datos asociados son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="bda15-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="bda15-127">En el centro de administración, vaya a la página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licencias</a> de **facturación** > .</span><span class="sxs-lookup"><span data-stu-id="bda15-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="bda15-128">En la página **licencias** , elija **Microsoft 365 apps for Education (Device)** o **Microsoft 365 apps for Enterprise (Device)**.</span><span class="sxs-lookup"><span data-stu-id="bda15-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="bda15-129">En la página siguiente, elija una suscripción, elija **más acciones**y, a continuación, elija **Cancelar asignación de licencias**.</span><span class="sxs-lookup"><span data-stu-id="bda15-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="bda15-130">En el cuadro de diálogo **cancelar la asignación de licencias** , elija **Anular asignación**.</span><span class="sxs-lookup"><span data-stu-id="bda15-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>