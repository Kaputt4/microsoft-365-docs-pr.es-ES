---
title: Administrar licencias para dispositivos
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Aprende a asignar licencias a grupos para su uso con dispositivos.
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: 29bd56ccff01d8c21cc67d1188fa21e338fb4b7e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638188"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="0546b-103">Administrar licencias para dispositivos</span><span class="sxs-lookup"><span data-stu-id="0546b-103">Manage licenses for devices</span></span>

<span data-ttu-id="0546b-104">Si tiene Aplicaciones de Microsoft 365 para empresas (dispositivo) o Aplicaciones de Microsoft 365 para educación (dispositivo), puede asignar licencias a dispositivos mediante grupos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0546b-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="0546b-105">Cuando un dispositivo tiene una licencia, cualquier persona que use ese dispositivo puede usar Aplicaciones de Microsoft 365 para empresas (anteriormente denominado Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="0546b-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="0546b-106">Por ejemplo, supongamos que tiene 20 portátiles y tabletas que usan las personas de su organización.</span><span class="sxs-lookup"><span data-stu-id="0546b-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="0546b-107">Cuando asigna una licencia a cada dispositivo, cada persona que inicia sesión en uno de los dispositivos usa Aplicaciones de Microsoft 365 para empresas sin necesidad de su propia licencia.</span><span class="sxs-lookup"><span data-stu-id="0546b-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0546b-108">Las licencias basadas en dispositivos para Aplicaciones de Microsoft 365 para empresas solo están disponibles como una licencia de complemento para algunos clientes comerciales y algunos clientes de educación.</span><span class="sxs-lookup"><span data-stu-id="0546b-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="0546b-109">Para los clientes comerciales, la licencia es Aplicaciones de *Microsoft 365* para empresas (dispositivo) y solo está disponible a través de Contrato Enterprise/Contrato Enterprise suscripción.</span><span class="sxs-lookup"><span data-stu-id="0546b-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="0546b-110">Para los clientes del sector educativo, la licencia es Aplicaciones de *Microsoft 365* para educación (dispositivo) y solo está disponible a través de Enrollment for Education Solutions (EES).</span><span class="sxs-lookup"><span data-stu-id="0546b-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="0546b-111">Para obtener más información, lea la entrada del blog sobre [la disponibilidad educativa.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/)</span><span class="sxs-lookup"><span data-stu-id="0546b-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="0546b-112">Para obtener disponibilidad comercial, póngase en contacto con el representante de su cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0546b-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="0546b-113">Para empezar, cree un grupo en el Centro de administración de Azure Active Directory y, a continuación, asigne dispositivos al grupo.</span><span class="sxs-lookup"><span data-stu-id="0546b-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="0546b-114">Para obtener más información sobre las licencias de dispositivos, incluidos los requisitos de dispositivo, los tipos de grupos que puede usar y cómo configurar Aplicaciones de Microsoft 365 para empresas para usar licencias de dispositivos, consulte Licencias basadas en dispositivos para Aplicaciones de [Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2094216)para empresas.</span><span class="sxs-lookup"><span data-stu-id="0546b-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0546b-115">Debe ser administrador global para completar las tareas de este artículo.</span><span class="sxs-lookup"><span data-stu-id="0546b-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="0546b-116">Asignar licencias a dispositivos</span><span class="sxs-lookup"><span data-stu-id="0546b-116">Assign licenses to devices</span></span>

<span data-ttu-id="0546b-117">Cuando asignas licencias a un grupo, asignas licencias a todos los dispositivos del grupo.</span><span class="sxs-lookup"><span data-stu-id="0546b-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="0546b-118">Solo puede asignar una suscripción a cualquier grupo único.</span><span class="sxs-lookup"><span data-stu-id="0546b-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="0546b-119">En el Centro de administración de Microsoft 365, vaya a la página  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licencias de</a> facturación.</span><span class="sxs-lookup"><span data-stu-id="0546b-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="0546b-120">En la **página Licencias,** elija Aplicaciones de **Microsoft 365** para educación (dispositivo) o Aplicaciones de **Microsoft 365** para empresas (dispositivo).</span><span class="sxs-lookup"><span data-stu-id="0546b-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="0546b-121">En la página siguiente, elija una suscripción y, a continuación, **elija Asignar licencias.**</span><span class="sxs-lookup"><span data-stu-id="0546b-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="0546b-122">En el panel Asignar licencias a un grupo, empiece a escribir un nombre de grupo y, a continuación, selecciónelo en los **resultados** para agregarlo a la lista.</span><span class="sxs-lookup"><span data-stu-id="0546b-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="0546b-123">Elija **Asignar** y, a continuación, **seleccione Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="0546b-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="0546b-124">Desasignación de licencias de dispositivos</span><span class="sxs-lookup"><span data-stu-id="0546b-124">Unassign licenses from devices</span></span>

<span data-ttu-id="0546b-125">Cuando desasignas licencias de un grupo, quitas las licencias de todos los dispositivos del grupo.</span><span class="sxs-lookup"><span data-stu-id="0546b-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="0546b-126">A continuación, todas las aplicaciones y sus datos asociados son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="0546b-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="0546b-127">En el centro de administración, vaya a la página  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licencias de</a> facturación.</span><span class="sxs-lookup"><span data-stu-id="0546b-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="0546b-128">En la **página Licencias,** elija Aplicaciones de **Microsoft 365** para educación (dispositivo) o Aplicaciones de **Microsoft 365** para empresas (dispositivo).</span><span class="sxs-lookup"><span data-stu-id="0546b-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="0546b-129">En la página siguiente, elija una suscripción, elija **Más acciones** y, a continuación, **desasigne licencias.**</span><span class="sxs-lookup"><span data-stu-id="0546b-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="0546b-130">En el **cuadro de diálogo Desasignación** de licencias, elija **Unassign**.</span><span class="sxs-lookup"><span data-stu-id="0546b-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>