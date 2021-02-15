---
title: Administrar y supervisar cuentas de prioridad
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: Supervisar mensajes de correo electrónico con errores y retrasos enviados a o desde cuentas que tienen un alto impacto en la empresa.
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477618"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="4f855-103">Administrar y supervisar cuentas de prioridad</span><span class="sxs-lookup"><span data-stu-id="4f855-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="4f855-104">En todas las organizaciones de Microsoft 365, hay personas que son esenciales, como ejecutivos, líderes, administradores u otros usuarios que tienen acceso a información confidencial, propietaria o de prioridad alta.</span><span class="sxs-lookup"><span data-stu-id="4f855-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="4f855-105">Para ayudar a su organización a proteger estas cuentas, ahora puede designar usuarios específicos como cuentas de prioridad y aprovechar las características específicas de la aplicación que les proporcionan protección adicional.</span><span class="sxs-lookup"><span data-stu-id="4f855-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="4f855-106">En el futuro, más aplicaciones y características admitirán cuentas de prioridad y, para empezar, hemos anunciado dos **funcionalidades:** protección de cuentas de prioridad y supervisión del flujo de correo **premium.**</span><span class="sxs-lookup"><span data-stu-id="4f855-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="4f855-107">**Protección** de cuentas de prioridad: Microsoft Defender para Office 365 (anteriormente Protección contra amenazas avanzada de Office 365) admite cuentas de prioridad como etiquetas que se pueden usar en filtros en alertas, informes e investigaciones.</span><span class="sxs-lookup"><span data-stu-id="4f855-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="4f855-108">Para obtener más información, consulte [Etiquetas de usuario en Microsoft Defender para Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="4f855-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span></span>
- <span data-ttu-id="4f855-109">**Supervisión del flujo de correo premium:** un flujo de correo correcto puede ser fundamental para el éxito de la empresa y los retrasos o errores en la entrega pueden tener un impacto negativo en el negocio.</span><span class="sxs-lookup"><span data-stu-id="4f855-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="4f855-110">Puede elegir un umbral para mensajes de correo electrónico con errores o retrasos, recibir alertas cuando se supera ese umbral y ver un informe de problemas de correo electrónico para cuentas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="4f855-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="4f855-111">Para obtener más información, consulte problemas [de correo electrónico para el informe de cuentas de prioridad en el EAC moderno.](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="4f855-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4f855-112">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="4f855-112">Before you begin</span></span>

<span data-ttu-id="4f855-113">La **característica de protección de** cuentas de prioridad que se describe en este tema solo está disponible para las organizaciones que cumplen los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="4f855-113">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="4f855-114">Microsoft Defender para Office 365 Plan 2, incluidos aquellos con Office 365 E3, Office 365 E5, Microsoft 365 E5 o Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="4f855-114">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="4f855-115">La **característica de supervisión del** flujo de correo premium que se describe en este tema solo está disponible para las organizaciones que cumplen los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="4f855-115">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="4f855-116">Su organización debe tener un recuento de licencias de al menos 10 000, ya sea de uno de los siguientes productos o una combinación de ellos: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4f855-116">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="4f855-117">Por ejemplo, su organización puede tener 3000 licencias de Office 365 E3 y 8500 Microsoft 365 E5, para un total de 11.500 licencias de los productos elegibles.</span><span class="sxs-lookup"><span data-stu-id="4f855-117">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="4f855-118">Su organización necesita tener al menos 50 usuarios activos de Exchange Online mensuales.</span><span class="sxs-lookup"><span data-stu-id="4f855-118">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="4f855-119">Puede supervisar hasta 250 cuentas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="4f855-119">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="4f855-120">Agregar cuentas de prioridad desde la página de instalación</span><span class="sxs-lookup"><span data-stu-id="4f855-120">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="4f855-121">Agregue cuentas de prioridad desde la **página de instalación.**</span><span class="sxs-lookup"><span data-stu-id="4f855-121">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="4f855-122">Vaya al Centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="4f855-122">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="4f855-123">Vaya a **Configurar**  >  **conocimientos de** la organización y elija **Ver en** Supervisar las cuentas **más importantes.**</span><span class="sxs-lookup"><span data-stu-id="4f855-123">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="4f855-124">Seleccione **Introducción o** **Administrar.**</span><span class="sxs-lookup"><span data-stu-id="4f855-124">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="4f855-125">En la **página Agregar cuentas de** prioridad, en el campo de búsqueda, escriba el nombre o la dirección de correo electrónico de la persona que desea agregar a la lista de cuentas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="4f855-125">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="4f855-126">También puede establecer su umbral de correo electrónico para mensajes de correo electrónico con errores o retrasos y obtener un informe semanal de problemas para cuentas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="4f855-126">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="4f855-127">Seleccione el usuario y elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4f855-127">Select the user and choose **Save**.</span></span>

<span data-ttu-id="4f855-128">También puede agregar cuentas de prioridad desde la página Usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="4f855-128">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="4f855-129">Agregar cuentas de prioridad desde la página Usuarios activos</span><span class="sxs-lookup"><span data-stu-id="4f855-129">Add priority accounts from Active users page</span></span>

<span data-ttu-id="4f855-130">Agregue cuentas de prioridad desde la página Usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="4f855-130">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="4f855-131">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="4f855-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="4f855-132">Vaya a **Usuarios**  >  **activos y** elija **...** en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="4f855-132">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="4f855-133">Seleccione **Administrar cuentas de prioridad.**</span><span class="sxs-lookup"><span data-stu-id="4f855-133">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="4f855-134">Seleccione **Agregar cuentas y,** en la página Agregar cuentas de prioridad, en el campo de búsqueda, escriba el nombre de la persona que desea agregar a la lista de cuentas de prioridad. </span><span class="sxs-lookup"><span data-stu-id="4f855-134">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="4f855-135">Seleccione el usuario y elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4f855-135">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="4f855-136">Quitar un usuario de la lista de cuentas de prioridad</span><span class="sxs-lookup"><span data-stu-id="4f855-136">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="4f855-137">Vaya al Centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="4f855-137">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="4f855-138">Vaya a **Configurar**  >  **conocimientos de** la organización y elija **Ver en** Supervisar las cuentas **más importantes.**</span><span class="sxs-lookup"><span data-stu-id="4f855-138">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="4f855-139">En la **página Supervisar la mayoría de las cuentas,** elija Cuentas de **prioridad** en Administrar **esta característica.**</span><span class="sxs-lookup"><span data-stu-id="4f855-139">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="4f855-140">En la **página Cuentas de** prioridad, seleccione el usuario o los usuarios que desea quitar de la lista y elija Quitar **cuentas.**</span><span class="sxs-lookup"><span data-stu-id="4f855-140">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4f855-141">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4f855-141">Related topics</span></span>

[<span data-ttu-id="4f855-142">Uso de cuentas de prioridad en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4f855-142">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)