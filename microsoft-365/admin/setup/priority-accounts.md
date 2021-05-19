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
description: Supervisar los mensajes de correo electrónico con errores y retrasos enviados a o desde cuentas que tienen un alto impacto empresarial.
ms.openlocfilehash: 2a58f4090244fc6d68be69cf6b3c8ab6e00874fa
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535811"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="46f14-103">Administrar y supervisar cuentas de prioridad</span><span class="sxs-lookup"><span data-stu-id="46f14-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="46f14-104">En todas Microsoft 365 organización, hay personas que son esenciales, como ejecutivos, líderes, administradores u otros usuarios que tienen acceso a información confidencial, propietaria o de alta prioridad.</span><span class="sxs-lookup"><span data-stu-id="46f14-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="46f14-105">Para ayudar a su organización a proteger estas cuentas, ahora puede designar usuarios específicos como cuentas de prioridad y aprovechar las características específicas de la aplicación que les proporcionan protección adicional.</span><span class="sxs-lookup"><span data-stu-id="46f14-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="46f14-106">En el futuro, más aplicaciones y características admitirán cuentas de prioridad y, para empezar, hemos anunciado dos **funcionalidades:** protección de cuentas prioritarias y supervisión de flujo de correo **premium.**</span><span class="sxs-lookup"><span data-stu-id="46f14-106">In the future, more apps and features will support priority accounts, and to start with, we've announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="46f14-107">**Protección de** cuentas de prioridad: Microsoft Defender para Office 365 (anteriormente Office 365 Advanced Threat Protection) admite cuentas de prioridad como etiquetas que se pueden usar en filtros en alertas, informes e investigaciones.</span><span class="sxs-lookup"><span data-stu-id="46f14-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="46f14-108">Para obtener más información, consulte [Etiquetas de usuario en Microsoft Defender para obtener Office 365](../../security/office-365-security/user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="46f14-108">For more information, check out [User tags in Microsoft Defender for Office 365](../../security/office-365-security/user-tags.md).</span></span>

  <span data-ttu-id="46f14-109">Una pregunta natural es: "¿No son todos los usuarios una prioridad?</span><span class="sxs-lookup"><span data-stu-id="46f14-109">A natural question is, "Aren't all users a priority?</span></span> <span data-ttu-id="46f14-110">¿Por qué no designar a todos los usuarios como cuentas de prioridad?"</span><span class="sxs-lookup"><span data-stu-id="46f14-110">Why not designate all users as priority accounts?"</span></span> <span data-ttu-id="46f14-111">Sí, todos los usuarios son una prioridad, pero la protección de cuentas de prioridad ofrece las siguientes ventajas adicionales:</span><span class="sxs-lookup"><span data-stu-id="46f14-111">Yes, all users are a priority, but priority account protection offers the following additional benefits:</span></span>

  - <span data-ttu-id="46f14-112">**Heurística adicional:** nuestro análisis del flujo de correo en los centros de datos de Microsoft indica que los patrones de flujo de correo para los ejecutivos de la compañía son diferentes del empleado promedio.</span><span class="sxs-lookup"><span data-stu-id="46f14-112">**Additional heuristics**: Our analysis of mail flow in the Microsoft datacenters indicates that mail flow patterns for company executives are different than the average employee.</span></span> <span data-ttu-id="46f14-113">La protección de cuentas prioritarias ofrece heurísticas adicionales adaptadas específicamente a los ejecutivos de la compañía que no beneficiarían a un empleado normal.</span><span class="sxs-lookup"><span data-stu-id="46f14-113">Priority account protection offers additional heuristics that are specifically tailored to company executives that wouldn't benefit a regular employee.</span></span>
  - <span data-ttu-id="46f14-114">**Visibilidad adicional en los informes:** en efecto, la información de todos los usuarios (o todos los usuarios afectados) ya está disponible en alertas, informes e investigaciones.</span><span class="sxs-lookup"><span data-stu-id="46f14-114">**Additional visibility in reporting**: In effect, information for all users (or all affected users) is already available in alerts, reports, and investigations.</span></span> <span data-ttu-id="46f14-115">La etiqueta cuentas de prioridad como filtro le permite dirigirse específicamente a sus investigaciones.</span><span class="sxs-lookup"><span data-stu-id="46f14-115">The priority accounts tag as a filter allows you to specifically target your investigations.</span></span>

- <span data-ttu-id="46f14-116">**Premium supervisión Flow** correo electrónico: un flujo de correo correcto puede ser fundamental para el éxito empresarial y los retrasos o errores de entrega pueden tener un impacto negativo en el negocio.</span><span class="sxs-lookup"><span data-stu-id="46f14-116">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="46f14-117">Puede elegir un umbral para mensajes de correo electrónico con errores o retrasos, recibir alertas cuando se supere ese umbral y ver un informe de problemas de correo electrónico para cuentas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="46f14-117">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="46f14-118">Para obtener más información, consulte Problemas de correo electrónico para el informe de cuentas [de prioridad en el EAC moderno](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="46f14-118">For more information, check out [Email issues for priority accounts report in the modern EAC](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="46f14-119">Para obtener información sobre los procedimientos recomendados de seguridad para cuentas de prioridad, vea [Recomendaciones de seguridad para cuentas de prioridad.](../../security/office-365-security/security-recommendations-for-priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="46f14-119">For security best practices for priority accounts, see [Security recommendations for priority accounts](../../security/office-365-security/security-recommendations-for-priority-accounts.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="46f14-120">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="46f14-120">Before you begin</span></span>

<span data-ttu-id="46f14-121">La **característica de protección de** cuentas de prioridad que se describe en este tema solo está disponible para las organizaciones que cumplen los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="46f14-121">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="46f14-122">Microsoft Defender para Office 365 plan 2, incluidos aquellos con Office 365 E3, Office 365 E5, Microsoft 365 E5 o Seguridad de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="46f14-122">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="46f14-123">La **Premium supervisión Flow correo** electrónico que se describe en este tema solo está disponible para las organizaciones que cumplen los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="46f14-123">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="46f14-124">Su organización debe tener un recuento de licencias de al menos 10 000, desde uno de los siguientes productos o una combinación de los siguientes: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="46f14-124">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="46f14-125">Por ejemplo, su organización puede tener 3000 licencias Office 365 E3 y 8500 Microsoft 365 E5, para un total de 11.500 licencias de los productos que califican.</span><span class="sxs-lookup"><span data-stu-id="46f14-125">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="46f14-126">Su organización necesita tener al menos 50 usuarios activos de Exchange Online mensuales.</span><span class="sxs-lookup"><span data-stu-id="46f14-126">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="46f14-127">Puede supervisar hasta 250 cuentas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="46f14-127">You can monitor up to 250 priority accounts.</span></span>

<span data-ttu-id="46f14-128">Al aplicar la protección de cuenta de prioridad a un buzón de correo, también debe aplicar la protección de cuenta de prioridad a los usuarios que tienen acceso al buzón (por ejemplo, el director ejecutivo y el asistente ejecutivo del CEO que administra el calendario del CEO).</span><span class="sxs-lookup"><span data-stu-id="46f14-128">When you apply priority account protection to a mailbox, you should also apply priority account protection to users who have access to the mailbox (for example, the CEO and the CEO's executive assistant who manages the CEO's calendar).</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="46f14-129">Agregar cuentas de prioridad desde la página Configuración</span><span class="sxs-lookup"><span data-stu-id="46f14-129">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="46f14-130">Agregue cuentas de prioridad desde la **página De instalación**.</span><span class="sxs-lookup"><span data-stu-id="46f14-130">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="46f14-131">Vaya al Centro Microsoft 365 administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="46f14-131">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="46f14-132">Vaya a **Configurar**  >  **conocimientos de** la organización y elija Ver **en** Supervisar las cuentas **más importantes.**</span><span class="sxs-lookup"><span data-stu-id="46f14-132">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="46f14-133">Seleccione **Introducción** o **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="46f14-133">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="46f14-134">En la **página Agregar cuentas de** prioridad, en el campo de búsqueda, escriba el nombre o la dirección de correo electrónico de la persona que desea agregar a la lista de cuentas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="46f14-134">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="46f14-135">También puede establecer el umbral de correo electrónico para mensajes de correo electrónico con errores o retrasos y obtener un informe semanal de problemas para cuentas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="46f14-135">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="46f14-136">Seleccione el usuario y elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="46f14-136">Select the user and choose **Save**.</span></span>

<span data-ttu-id="46f14-137">También puede agregar cuentas de prioridad desde la página Usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="46f14-137">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="46f14-138">Agregar cuentas de prioridad desde la página Usuarios activos</span><span class="sxs-lookup"><span data-stu-id="46f14-138">Add priority accounts from Active users page</span></span>

<span data-ttu-id="46f14-139">Agregue cuentas de prioridad desde la página Usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="46f14-139">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="46f14-140">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="46f14-140">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="46f14-141">Vaya a **Usuarios**  >  **Usuarios activos** y seleccione los tres puntos (más acciones) en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="46f14-141">Go to **Users** > **Active users** and select the three dots (more actions) at the top of the page.</span></span> <span data-ttu-id="46f14-142">Seleccione **Administrar cuentas de prioridad**.</span><span class="sxs-lookup"><span data-stu-id="46f14-142">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="46f14-143">Seleccione **Agregar cuentas** y, en la página Agregar cuentas de prioridad, en el campo de búsqueda, escriba el nombre de la persona que desea agregar a la lista de cuentas de prioridad. </span><span class="sxs-lookup"><span data-stu-id="46f14-143">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="46f14-144">Seleccione el usuario y elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="46f14-144">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="46f14-145">Quitar un usuario de la lista de cuentas de prioridad</span><span class="sxs-lookup"><span data-stu-id="46f14-145">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="46f14-146">Vaya al Centro Microsoft 365 administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="46f14-146">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="46f14-147">Vaya a **Configurar**  >  **conocimientos de** la organización y elija Ver **en** Supervisar las cuentas **más importantes.**</span><span class="sxs-lookup"><span data-stu-id="46f14-147">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="46f14-148">En la **página Supervisar la mayoría de las cuentas,** elija Cuentas de **prioridad** en Administrar **esta característica.**</span><span class="sxs-lookup"><span data-stu-id="46f14-148">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="46f14-149">En la **página Cuentas de** prioridad, seleccione el usuario o los usuarios que desea quitar de la lista y elija Quitar **cuentas.**</span><span class="sxs-lookup"><span data-stu-id="46f14-149">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="46f14-150">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="46f14-150">Related topics</span></span>

[<span data-ttu-id="46f14-151">Uso de cuentas de prioridad en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="46f14-151">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
