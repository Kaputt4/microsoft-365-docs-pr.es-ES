---
title: Administrar licencias para dispositivos
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: shegu, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: Obtenga información sobre cómo asignar licencias a grupos para su uso con dispositivos.
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_licensing
search.appverid: MET150
ms.date: 03/17/2021
ms.openlocfilehash: 67bd0734953c64f51390aac949a7da477914c7b4
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331663"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="a3741-103">Administrar licencias para dispositivos</span><span class="sxs-lookup"><span data-stu-id="a3741-103">Manage licenses for devices</span></span>

<span data-ttu-id="a3741-104">Si tienes Aplicaciones de Microsoft 365 para empresas (dispositivo) o Aplicaciones de Microsoft 365 para Educación (dispositivo), puedes asignar licencias a dispositivos mediante grupos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a3741-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="a3741-105">Cuando un dispositivo tiene una licencia, cualquier persona que use ese dispositivo puede usar Aplicaciones de Microsoft 365 para empresas (anteriormente denominada Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="a3741-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="a3741-106">Por ejemplo, supongamos que tiene 20 portátiles y tabletas que usan los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="a3741-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="a3741-107">Cuando asignas una licencia a cada dispositivo, cada persona que inicia sesión en uno de los dispositivos usa Aplicaciones de Microsoft 365 para empresas sin necesidad de su propia licencia.</span><span class="sxs-lookup"><span data-stu-id="a3741-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3741-108">Las licencias basadas en dispositivos para Aplicaciones de Microsoft 365 para empresas solo están disponibles como una licencia de complemento para algunos clientes comerciales y algunos clientes de educación.</span><span class="sxs-lookup"><span data-stu-id="a3741-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="a3741-109">Para los clientes comerciales, la licencia es Aplicaciones de *Microsoft 365* para empresas (dispositivo) y solo está disponible a través de Contrato Enterprise/Contrato Enterprise suscripción.</span><span class="sxs-lookup"><span data-stu-id="a3741-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="a3741-110">Para los clientes de educación, la licencia es Aplicaciones de *Microsoft 365* para educación (dispositivo) y solo está disponible a través de Enrollment for Education Solutions (EES).</span><span class="sxs-lookup"><span data-stu-id="a3741-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="a3741-111">Para obtener más información, lea la entrada de blog sobre [disponibilidad educativa](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education).</span><span class="sxs-lookup"><span data-stu-id="a3741-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education).</span></span> <span data-ttu-id="a3741-112">Para obtener disponibilidad comercial, póngase en contacto con el representante de la cuenta microsoft.</span><span class="sxs-lookup"><span data-stu-id="a3741-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="a3741-113">Para empezar, cree un grupo en el Centro de administración de Azure Active Directory y, a continuación, asigne dispositivos al grupo.</span><span class="sxs-lookup"><span data-stu-id="a3741-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="a3741-114">Para obtener más información sobre las licencias de dispositivos, incluidos los requisitos de dispositivo, qué tipos de grupos puede usar y cómo configurar Aplicaciones de Microsoft 365 para empresas para que usen licencias de dispositivos, consulte Licencias basadas en dispositivos para Aplicaciones de [Microsoft 365](/deployoffice/device-based-licensing)para empresas.</span><span class="sxs-lookup"><span data-stu-id="a3741-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](/deployoffice/device-based-licensing).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3741-115">Debe ser un administrador global para completar las tareas de este artículo.</span><span class="sxs-lookup"><span data-stu-id="a3741-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="a3741-116">Asignar licencias a dispositivos</span><span class="sxs-lookup"><span data-stu-id="a3741-116">Assign licenses to devices</span></span>

<span data-ttu-id="a3741-117">Al asignar licencias a un grupo, se asignan licencias a todos los dispositivos del grupo.</span><span class="sxs-lookup"><span data-stu-id="a3741-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="a3741-118">Solo puede asignar una suscripción a cualquier grupo.</span><span class="sxs-lookup"><span data-stu-id="a3741-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="a3741-119">En el Centro de administración de Microsoft 365, vaya a la página **Licencias**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">de</a> facturación.</span><span class="sxs-lookup"><span data-stu-id="a3741-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="a3741-120">En la **página Licencias,** elija Aplicaciones de **Microsoft 365** para Educación (dispositivo) o Aplicaciones de **Microsoft 365 para empresas (dispositivo).**</span><span class="sxs-lookup"><span data-stu-id="a3741-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="a3741-121">En la página siguiente, elija una suscripción y, a continuación, **elija Asignar licencias.**</span><span class="sxs-lookup"><span data-stu-id="a3741-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="a3741-122">En el panel Asignar licencias a un grupo, empiece a escribir un nombre de grupo y, a continuación, elija en los **resultados** para agregarlo a la lista.</span><span class="sxs-lookup"><span data-stu-id="a3741-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="a3741-123">Elija **Asignar** y, a continuación, **seleccione Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="a3741-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="a3741-124">Unassign licenses from devices</span><span class="sxs-lookup"><span data-stu-id="a3741-124">Unassign licenses from devices</span></span>

<span data-ttu-id="a3741-125">Cuando se quitan las licencias de un grupo, se quitan las licencias de todos los dispositivos del grupo.</span><span class="sxs-lookup"><span data-stu-id="a3741-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="a3741-126">A continuación, todas las aplicaciones y sus datos asociados son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="a3741-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="a3741-127">En el Centro de administración, vaya a la página **Licencias**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">de</a> facturación.</span><span class="sxs-lookup"><span data-stu-id="a3741-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="a3741-128">En la **página Licencias,** elija Aplicaciones de **Microsoft 365** para Educación (dispositivo) o Aplicaciones de **Microsoft 365 para empresas (dispositivo).**</span><span class="sxs-lookup"><span data-stu-id="a3741-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="a3741-129">En la página siguiente, elija una suscripción, elija **Más acciones** y, a continuación, **elija Unassign licenses**.</span><span class="sxs-lookup"><span data-stu-id="a3741-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="a3741-130">En el **cuadro de diálogo Unassign licenses,** elija **Unassign**.</span><span class="sxs-lookup"><span data-stu-id="a3741-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>
