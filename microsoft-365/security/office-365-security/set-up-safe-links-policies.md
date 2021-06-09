---
title: Configurar directivas Caja fuerte vínculos en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a ver, crear, modificar y eliminar directivas de vínculos de Caja fuerte y configuración global de vínculos de Caja fuerte en Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 61cb4746289a8acbdd9af7f668010604de511902
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694502"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="97c50-103">Configurar directivas Caja fuerte vínculos en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="97c50-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="97c50-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="97c50-104">**Applies to**</span></span>
- [<span data-ttu-id="97c50-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="97c50-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="97c50-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97c50-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="97c50-107">Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="97c50-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="97c50-108">Si es un usuario principal que busca información sobre safelinks en Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="97c50-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="97c50-109">Caja fuerte Vínculos es una característica de [Microsoft Defender](defender-for-office-365.md) para Office 365 que proporciona el examen de direcciones URL de los mensajes de correo electrónico entrantes en el flujo de correo y el tiempo de comprobación de clics de direcciones URL y vínculos en mensajes de correo electrónico y en otras ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="97c50-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="97c50-110">Para obtener más información, [vea Caja fuerte Links in Microsoft Defender for Office 365](safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="97c50-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="97c50-111">No hay ninguna directiva de vínculos integrada o Caja fuerte predeterminada.</span><span class="sxs-lookup"><span data-stu-id="97c50-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="97c50-112">Para obtener Caja fuerte de vínculos de búsqueda de direcciones URL, debe crear una o más directivas de vínculos de Caja fuerte como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="97c50-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="97c50-113">Puede configurar la configuración global para la protección de Caja fuerte de vínculos **fuera** de Caja fuerte directivas de vínculos.</span><span class="sxs-lookup"><span data-stu-id="97c50-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="97c50-114">Para obtener instrucciones, vea [Configure global settings for Caja fuerte Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="97c50-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="97c50-115">Puede configurar directivas de vínculos de Caja fuerte en el Centro de seguridad y cumplimiento de & o en PowerShell (PowerShell de Exchange Online para organizaciones Microsoft 365 elegibles con buzones de correo en Exchange Online; PowerShell EOP independiente para organizaciones sin buzones de Exchange Online, pero con Microsoft Defender para suscripciones de complemento Office 365).</span><span class="sxs-lookup"><span data-stu-id="97c50-115">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="97c50-116">Los elementos básicos de una directiva Caja fuerte links son:</span><span class="sxs-lookup"><span data-stu-id="97c50-116">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="97c50-117">La directiva de vínculos **seguros:** active la protección de vínculos de Caja fuerte, active la detección de direcciones URL en tiempo real, especifique si debe esperar a que se complete el examen en tiempo real antes de entregar el mensaje, activar el examen de mensajes internos, especificar si se debe realizar un seguimiento de los clics de usuario en las direcciones URL y especificar si se permite a los usuarios hacer clic en la url original.</span><span class="sxs-lookup"><span data-stu-id="97c50-117">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="97c50-118">**La regla de vínculos seguros:** especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva).</span><span class="sxs-lookup"><span data-stu-id="97c50-118">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97c50-119">Los administradores deben tener en cuenta las distintas opciones de configuración de SafeLinks.</span><span class="sxs-lookup"><span data-stu-id="97c50-119">Admins should consider the different configuration settings for SafeLinks.</span></span> <span data-ttu-id="97c50-120">Una de las opciones disponibles es incluir información de identificación del usuario en SafeLinks.</span><span class="sxs-lookup"><span data-stu-id="97c50-120">One of the available options is to include user identifiable information in SafeLinks.</span></span> <span data-ttu-id="97c50-121">Esta característica permite a los *equipos de Operaciones* de seguridad investigar posibles riesgos de usuario, tomar medidas correctivas y limitar infracciones costosas.</span><span class="sxs-lookup"><span data-stu-id="97c50-121">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="97c50-122">La diferencia entre estos dos elementos no es obvia al administrar las directivas de vínculos de Caja fuerte en el Centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="97c50-122">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="97c50-123">Al crear una directiva Caja fuerte vínculos, en realidad está creando una regla de vínculos seguros y la directiva de vínculos seguros asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="97c50-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="97c50-124">Al modificar una directiva Caja fuerte vínculos, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada y los filtros de destinatarios modifican la regla de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="97c50-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="97c50-125">Todas las demás opciones modifican la directiva de vínculos seguros asociada.</span><span class="sxs-lookup"><span data-stu-id="97c50-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="97c50-126">Al quitar una directiva de vínculos Caja fuerte, se quitan la regla de vínculos seguros y la directiva de vínculos seguros asociada.</span><span class="sxs-lookup"><span data-stu-id="97c50-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="97c50-127">En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado.</span><span class="sxs-lookup"><span data-stu-id="97c50-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="97c50-128">Para obtener más información, vea la sección [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Caja fuerte Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="97c50-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="97c50-129">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="97c50-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="97c50-130">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="97c50-130">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="97c50-131">Para ir directamente a la **página Caja fuerte vínculos,** use <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="97c50-131">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="97c50-132">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="97c50-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="97c50-133">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="97c50-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="97c50-134">Debe tener asignados permisos antes de poder realizar los procedimientos descritos en este artículo:</span><span class="sxs-lookup"><span data-stu-id="97c50-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="97c50-135">Para crear, modificar y eliminar directivas de vínculos de Caja fuerte, debe ser miembro de los grupos de  roles Administración de  la organización o Administrador de seguridad en el Centro de cumplimiento de & y miembro del grupo de roles Administración de la organización en Exchange Online.  </span><span class="sxs-lookup"><span data-stu-id="97c50-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="97c50-136">Para obtener acceso de solo lectura a Caja fuerte de vínculos, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="97c50-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="97c50-137">Para obtener más información, vea [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="97c50-137">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="97c50-138">Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="97c50-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="97c50-139">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="97c50-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="97c50-140">.</span><span class="sxs-lookup"><span data-stu-id="97c50-140">.</span></span> <span data-ttu-id="97c50-141">- El **grupo de roles Administración** de la organización de solo vista [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="97c50-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="97c50-142">Para obtener información sobre la configuración recomendada para Caja fuerte de vínculos, [consulte Caja fuerte configuración de directiva de vínculos.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="97c50-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="97c50-143">Permitir hasta 30 minutos para que se aplique una directiva nueva o actualizada.</span><span class="sxs-lookup"><span data-stu-id="97c50-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="97c50-144">[Las nuevas características se agregan continuamente a Microsoft Defender para Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="97c50-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="97c50-145">A medida que se agregan nuevas características, es posible que deba realizar ajustes en las directivas de vínculos de Caja fuerte existentes.</span><span class="sxs-lookup"><span data-stu-id="97c50-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="97c50-146">Usar el Centro de seguridad & cumplimiento para crear directivas Caja fuerte vínculos</span><span class="sxs-lookup"><span data-stu-id="97c50-146">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="97c50-147">La creación de una directiva de vínculos de Caja fuerte personalizada en el Centro de seguridad y cumplimiento de & crea la regla de vínculos seguros y la directiva de vínculos seguros asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="97c50-147">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="97c50-148">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas ATP Caja fuerte \>  \> **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="97c50-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="97c50-149">En la **página Caja fuerte,** haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="97c50-149">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="97c50-150">Se **abrirá el Asistente para Caja fuerte de directivas de nuevos** vínculos.</span><span class="sxs-lookup"><span data-stu-id="97c50-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="97c50-151">En la **página Nombre de la directiva,** configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="97c50-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="97c50-152">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="97c50-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="97c50-153">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="97c50-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="97c50-154">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="97c50-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="97c50-155">En la **Configuración** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="97c50-155">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="97c50-156">**Seleccione la acción para direcciones** URL potencialmente  malintencionadas desconocidas en mensajes: seleccione Activar para habilitar la protección de vínculos de Caja fuerte para vínculos en mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="97c50-156">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="97c50-157">**Seleccione la acción para direcciones** URL desconocidas o  potencialmente malintencionadas dentro de Microsoft Teams : Seleccione Activar para habilitar la protección de vínculos de Caja fuerte para vínculos de Teams.</span><span class="sxs-lookup"><span data-stu-id="97c50-157">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="97c50-158">**Aplicar análisis de direcciones URL** en tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos: seleccione esta opción para habilitar el examen en tiempo real de vínculos en mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="97c50-158">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="97c50-159">**Espere a que se complete el examen** de direcciones URL antes de entregar el mensaje: seleccione esta opción para esperar a que se complete el examen de direcciones URL en tiempo real antes de entregar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="97c50-159">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="97c50-160">**Aplicar Caja fuerte vínculos** a mensajes de correo electrónico enviados dentro de la organización: seleccione esta opción para aplicar la directiva de vínculos de Caja fuerte a los mensajes entre remitentes internos y destinatarios internos.</span><span class="sxs-lookup"><span data-stu-id="97c50-160">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="97c50-161">**No realizar un seguimiento de los clics del** usuario: deje esta configuración sin elegir para habilitar los clics de usuario de seguimiento en las direcciones URL de los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="97c50-161">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="97c50-162">**No permitir que los usuarios hagan clic en** la dirección URL original: seleccione esta opción para impedir que los usuarios hagan clic en la dirección URL original en las páginas de [advertencia.](safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="97c50-162">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="97c50-163">**No vuelva a escribir las** siguientes direcciones URL: permite obtener acceso a las direcciones URL especificadas que, de lo contrario, se bloquearían mediante Caja fuerte vínculos.</span><span class="sxs-lookup"><span data-stu-id="97c50-163">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="97c50-164">En el cuadro, escriba la dirección URL o el valor que desee y, a continuación, haga clic en</span><span class="sxs-lookup"><span data-stu-id="97c50-164">In the box, type the URL or value that you want, and then click</span></span> ![Icono de botón Agregar](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="97c50-166">.</span><span class="sxs-lookup"><span data-stu-id="97c50-166">.</span></span>

     <span data-ttu-id="97c50-167">Para quitar una entrada existente, selecciónelo y, a continuación, haga clic en</span><span class="sxs-lookup"><span data-stu-id="97c50-167">To remove an existing entry, select it and then click</span></span> ![Icono del botón Eliminar](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="97c50-169">.</span><span class="sxs-lookup"><span data-stu-id="97c50-169">.</span></span>

     <span data-ttu-id="97c50-170">Para obtener sintaxis de entrada, vea Sintaxis de entrada para la lista "No volver a [escribir las siguientes direcciones URL".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="97c50-170">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="97c50-171">Para obtener información detallada acerca de esta configuración, consulte [Caja fuerte links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and Caja fuerte Links settings for [Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="97c50-171">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="97c50-172">Para obtener más información sobre los valores recomendados para la configuración de directivas estándar y estricta, consulte [Caja fuerte configuración de directiva de vínculos](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="97c50-172">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="97c50-173">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="97c50-173">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="97c50-174">En la **página Aplicada a** que aparece, identifique los destinatarios internos a los que se aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="97c50-174">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="97c50-175">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="97c50-175">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="97c50-176">Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="97c50-176">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="97c50-177">Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="97c50-177">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="97c50-178">Haga **clic en Agregar una condición**.</span><span class="sxs-lookup"><span data-stu-id="97c50-178">Click **Add a condition**.</span></span> <span data-ttu-id="97c50-179">En el desplegable que aparece, seleccione una condición en **Aplicada si**:</span><span class="sxs-lookup"><span data-stu-id="97c50-179">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="97c50-180">**El destinatario es**: especifica uno o varios buzones, usuarios de correo o contactos de correo de la organización.</span><span class="sxs-lookup"><span data-stu-id="97c50-180">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="97c50-181">**El destinatario es miembro de**: Especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="97c50-181">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="97c50-182">**El dominio del destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en su organización.</span><span class="sxs-lookup"><span data-stu-id="97c50-182">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="97c50-183">Después de seleccionar la condición, aparece un desplegable correspondiente con **un cuadro Cualquiera de estos.**</span><span class="sxs-lookup"><span data-stu-id="97c50-183">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="97c50-184">Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="97c50-184">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="97c50-185">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un valor.</span><span class="sxs-lookup"><span data-stu-id="97c50-185">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="97c50-186">Para agregar valores adicionales, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="97c50-186">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="97c50-187">Para quitar entradas individuales, haga clic **en Quitar** ![ icono Quitar del ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="97c50-187">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="97c50-188">Para quitar toda la condición, haga clic **en Quitar** icono Quitar en ![ la ](../../media/scc-remove-icon.png) condición.</span><span class="sxs-lookup"><span data-stu-id="97c50-188">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="97c50-189">Para agregar una condición adicional, haga clic **en Agregar una condición** y seleccione un valor restante en Aplicado **si**.</span><span class="sxs-lookup"><span data-stu-id="97c50-189">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="97c50-190">Para agregar excepciones, haga clic **en Agregar una condición** y seleccione una excepción en Excepto **si**.</span><span class="sxs-lookup"><span data-stu-id="97c50-190">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="97c50-191">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="97c50-191">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="97c50-192">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="97c50-192">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="97c50-193">En la **página Revisar la configuración** que aparece, revisa la configuración.</span><span class="sxs-lookup"><span data-stu-id="97c50-193">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="97c50-194">Puede hacer clic **en Editar** en cada configuración para modificarla.</span><span class="sxs-lookup"><span data-stu-id="97c50-194">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="97c50-195">Cuando haya terminado, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="97c50-195">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="97c50-196">Usar el Centro de seguridad & cumplimiento para ver las directivas Caja fuerte vínculos</span><span class="sxs-lookup"><span data-stu-id="97c50-196">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="97c50-197">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas ATP Caja fuerte \>  \> **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="97c50-197">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="97c50-198">En la **Caja fuerte vínculos,** seleccione una directiva de la lista y haga clic en ella (no active la casilla).</span><span class="sxs-lookup"><span data-stu-id="97c50-198">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="97c50-199">Los detalles de la directiva aparecen en un desplegable</span><span class="sxs-lookup"><span data-stu-id="97c50-199">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="97c50-200">Usar el Centro de seguridad & cumplimiento para modificar las directivas Caja fuerte vínculos</span><span class="sxs-lookup"><span data-stu-id="97c50-200">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="97c50-201">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas ATP Caja fuerte \>  \> **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="97c50-201">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="97c50-202">En la **Caja fuerte vínculos,** seleccione una directiva de la lista y haga clic en ella (no active la casilla).</span><span class="sxs-lookup"><span data-stu-id="97c50-202">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="97c50-203">En el desplegable de detalles de la directiva que aparece, haga clic **en Editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="97c50-203">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="97c50-204">La configuración disponible en el menú desplegable que aparece es idéntica a la descrita en la sección Usar el Centro de seguridad [y & cumplimiento](#use-the-security--compliance-center-to-create-safe-links-policies) para crear Caja fuerte de vínculos.</span><span class="sxs-lookup"><span data-stu-id="97c50-204">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="97c50-205">Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la directiva, consulte las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="97c50-205">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="97c50-206">Habilitar o deshabilitar directivas Caja fuerte vínculos</span><span class="sxs-lookup"><span data-stu-id="97c50-206">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="97c50-207">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas ATP Caja fuerte \>  \> **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="97c50-207">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="97c50-208">Observe el valor de la **columna Estado:**</span><span class="sxs-lookup"><span data-stu-id="97c50-208">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="97c50-209">Mueva el botón de alternancia a la izquierda para deshabilitar la directiva:</span><span class="sxs-lookup"><span data-stu-id="97c50-209">Move the toggle to the left to disable the policy:</span></span> ![Desactivar directiva](../../media/scc-toggle-off.png)<span data-ttu-id="97c50-211">.</span><span class="sxs-lookup"><span data-stu-id="97c50-211">.</span></span>

   - <span data-ttu-id="97c50-212">Mueva el botón de alternancia a la derecha para habilitar la directiva:</span><span class="sxs-lookup"><span data-stu-id="97c50-212">Move the toggle to the right to enable the policy:</span></span> ![Activar directiva](../../media/scc-toggle-on.png)<span data-ttu-id="97c50-214">.</span><span class="sxs-lookup"><span data-stu-id="97c50-214">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="97c50-215">Establecer la prioridad de las directivas Caja fuerte vínculos</span><span class="sxs-lookup"><span data-stu-id="97c50-215">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="97c50-216">De forma predeterminada, Caja fuerte las directivas de vínculos se les da una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen menor prioridad que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="97c50-216">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="97c50-217">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="97c50-217">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="97c50-218">Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="97c50-218">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="97c50-219">Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="97c50-219">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="97c50-220">Caja fuerte Las directivas de vínculos se muestran en el orden en que se procesan (la primera directiva tiene el **valor de** prioridad 0).</span><span class="sxs-lookup"><span data-stu-id="97c50-220">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

> [!NOTE]
> <span data-ttu-id="97c50-221">En el Centro de & cumplimiento, solo puede cambiar la prioridad de la directiva de vínculos de Caja fuerte después de crearla.</span><span class="sxs-lookup"><span data-stu-id="97c50-221">In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="97c50-222">En PowerShell, puede invalidar la prioridad predeterminada al crear la regla de vínculos seguros (lo que puede afectar a la prioridad de las reglas existentes).</span><span class="sxs-lookup"><span data-stu-id="97c50-222">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="97c50-223">Para cambiar la prioridad de una directiva, suba o baje la directiva en la lista (no puede modificar directamente el número de **Prioridad** en el Centro de seguridad y cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="97c50-223">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="97c50-224">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas ATP Caja fuerte \>  \> **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="97c50-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="97c50-225">En la **Caja fuerte vínculos,** seleccione una directiva de la lista y haga clic en ella (no active la casilla).</span><span class="sxs-lookup"><span data-stu-id="97c50-225">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="97c50-226">En el desplegable de detalles de la directiva que aparece, haga clic en el botón de prioridad disponible:</span><span class="sxs-lookup"><span data-stu-id="97c50-226">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="97c50-227">La directiva Caja fuerte vínculos con el **valor de prioridad** **0** solo tiene disponible **el botón Disminuir** prioridad.</span><span class="sxs-lookup"><span data-stu-id="97c50-227">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="97c50-228">La directiva Caja fuerte vínculos con el valor **de prioridad** más bajo (por ejemplo, **3**) solo tiene disponible **el botón Aumentar** prioridad.</span><span class="sxs-lookup"><span data-stu-id="97c50-228">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="97c50-229">Si tiene tres o más directivas de vínculos Caja fuerte, las directivas  entre los  valores de prioridad más alta y más baja tienen disponibles los botones Aumentar prioridad y Disminuir prioridad.</span><span class="sxs-lookup"><span data-stu-id="97c50-229">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="97c50-230">Haga **clic en Aumentar prioridad** o Disminuir **prioridad** para cambiar el valor **De** prioridad.</span><span class="sxs-lookup"><span data-stu-id="97c50-230">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="97c50-231">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="97c50-231">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="97c50-232">Usar el Centro de seguridad & cumplimiento para quitar directivas Caja fuerte vínculos</span><span class="sxs-lookup"><span data-stu-id="97c50-232">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="97c50-233">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas ATP Caja fuerte \>  \> **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="97c50-233">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="97c50-234">En la **Caja fuerte vínculos,** seleccione una directiva de la lista y haga clic en ella (no active la casilla).</span><span class="sxs-lookup"><span data-stu-id="97c50-234">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="97c50-235">En el desplegable de detalles de directiva que aparece, haga clic en **Eliminar** directiva y, a continuación, haga clic en **Sí** en el cuadro de diálogo de advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="97c50-235">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="97c50-236">Usar Exchange Online PowerShell o PowerShell independiente de EOP para configurar directivas Caja fuerte vínculos</span><span class="sxs-lookup"><span data-stu-id="97c50-236">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="97c50-237">Como se describió anteriormente, una directiva Caja fuerte links consiste en una directiva de vínculos seguros y una regla de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="97c50-237">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="97c50-238">En PowerShell, la diferencia entre las directivas de vínculos seguros y las reglas de vínculos seguros es aparente.</span><span class="sxs-lookup"><span data-stu-id="97c50-238">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="97c50-239">Las directivas de vínculos seguros se administran mediante los cmdlets **\* -SafeLinksPolicy** y se administran reglas de vínculos seguros mediante los cmdlets **\* -SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="97c50-239">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="97c50-240">En PowerShell, primero se crea la directiva de vínculos seguros y, a continuación, se crea la regla de vínculos seguros que identifica la directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="97c50-240">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="97c50-241">En PowerShell, se modifica la configuración de la directiva de vínculos seguros y la regla de vínculos seguros por separado.</span><span class="sxs-lookup"><span data-stu-id="97c50-241">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="97c50-242">Al quitar una directiva de vínculos seguros de PowerShell, la regla de vínculos seguros correspondiente no se quita automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="97c50-242">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="97c50-243">Usar PowerShell para crear directivas Caja fuerte vínculos</span><span class="sxs-lookup"><span data-stu-id="97c50-243">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="97c50-244">Crear una directiva Caja fuerte vínculos en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="97c50-244">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="97c50-245">Cree la directiva de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="97c50-245">Create the safe links policy.</span></span>
2. <span data-ttu-id="97c50-246">Cree la regla de vínculos seguros que especifica la directiva de vínculos seguros a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="97c50-246">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="97c50-247">Puede crear una nueva regla de vínculos seguros y asignarle una directiva de vínculos seguros existente y sin asociar.</span><span class="sxs-lookup"><span data-stu-id="97c50-247">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="97c50-248">Una regla de vínculos seguros no se puede asociar a más de una directiva de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="97c50-248">A safe links rule can't be associated with more than one safe links policy.</span></span>
> 
> - <span data-ttu-id="97c50-249">Puede configurar las siguientes opciones en nuevas directivas de vínculos seguros en PowerShell que no estén disponibles en el Centro de seguridad y cumplimiento de & hasta después de crear la directiva:</span><span class="sxs-lookup"><span data-stu-id="97c50-249">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="97c50-250">Cree la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="97c50-250">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="97c50-251">Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_ ) en el cmdlet **New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="97c50-251">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="97c50-252">Una nueva directiva de vínculos seguros que cree en PowerShell no está visible en el Centro de seguridad & cumplimiento hasta que asigne la directiva a una regla de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="97c50-252">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="97c50-253">Paso 1: Usar PowerShell para crear una directiva de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="97c50-253">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="97c50-254">Para crear una directiva de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="97c50-254">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - <span data-ttu-id="97c50-255">Para obtener más información acerca de la sintaxis de entrada que se va a usar para el parámetro _DoNotRewriteUrls,_ vea [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="97c50-255">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
> 
> - <span data-ttu-id="97c50-256">Para obtener una sintaxis adicional que puede usar para el parámetro _DoNotRewriteUrls_ al modificar las directivas de vínculos seguros existentes mediante el cmdlet **Set-SafeLinksPolicy,** vea la sección Usar [PowerShell](#use-powershell-to-modify-safe-links-policies) para modificar directivas de vínculos seguros más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="97c50-256">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="97c50-257">En este ejemplo se crea una directiva de vínculos seguros denominada Contoso All con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="97c50-257">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="97c50-258">Activa la detección y reescritura de direcciones URL en los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="97c50-258">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="97c50-259">Activa el examen de direcciones URL en Teams (solo vista previa de TAP).</span><span class="sxs-lookup"><span data-stu-id="97c50-259">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="97c50-260">Activa el examen en tiempo real de las direcciones URL en las que se hace clic, incluidos los vínculos en los que se hace clic que apuntan a archivos.</span><span class="sxs-lookup"><span data-stu-id="97c50-260">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="97c50-261">Espere a que se complete el examen de direcciones URL antes de entregar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="97c50-261">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="97c50-262">Activa la detección y reescritura de direcciones URL para los mensajes internos.</span><span class="sxs-lookup"><span data-stu-id="97c50-262">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="97c50-263">Realizar un seguimiento de los clics de usuario relacionados con la protección de vínculos de Caja fuerte (no estamos usando el parámetro _DoNotTrackUserClicks_ y el valor predeterminado es $false, lo que significa que se realiza un seguimiento de los clics del usuario).</span><span class="sxs-lookup"><span data-stu-id="97c50-263">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="97c50-264">No permitir que los usuarios hagan clic en la dirección URL original.</span><span class="sxs-lookup"><span data-stu-id="97c50-264">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="97c50-265">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="97c50-265">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="97c50-266">Paso 2: Usar PowerShell para crear una regla de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="97c50-266">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="97c50-267">Para crear una regla de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="97c50-267">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="97c50-268">En este ejemplo se crea una regla de vínculos seguros denominada Contoso All con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="97c50-268">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="97c50-269">La regla está asociada con la directiva de vínculos seguros denominada Contoso All.</span><span class="sxs-lookup"><span data-stu-id="97c50-269">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="97c50-270">La regla se aplica a todos los destinatarios del contoso.com dominio.</span><span class="sxs-lookup"><span data-stu-id="97c50-270">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="97c50-271">Dado que no estamos usando el parámetro _Priority,_ se usa la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="97c50-271">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="97c50-272">La regla está habilitada (no estamos usando el parámetro _Enabled_ y el valor predeterminado es `$true` ).</span><span class="sxs-lookup"><span data-stu-id="97c50-272">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="97c50-273">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="97c50-273">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="97c50-274">Usar PowerShell para ver directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="97c50-274">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="97c50-275">Para ver las directivas de vínculos seguros existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="97c50-275">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="97c50-276">En este ejemplo se devuelve una lista resumida de todas las directivas de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="97c50-276">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="97c50-277">En este ejemplo se devuelve información detallada sobre la directiva de vínculos seguros denominada Ejecutivos de Contoso.</span><span class="sxs-lookup"><span data-stu-id="97c50-277">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="97c50-278">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="97c50-278">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="97c50-279">Usar PowerShell para ver reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="97c50-279">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="97c50-280">Para ver las reglas de vínculos seguros existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="97c50-280">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="97c50-281">En este ejemplo se devuelve una lista resumida de todas las reglas de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="97c50-281">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="97c50-282">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="97c50-282">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="97c50-283">En este ejemplo se devuelve información detallada para la regla de vínculos seguros denominada Ejecutivos de Contoso.</span><span class="sxs-lookup"><span data-stu-id="97c50-283">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="97c50-284">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="97c50-284">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="97c50-285">Usar PowerShell para modificar directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="97c50-285">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="97c50-286">No puede cambiar el nombre de una directiva de vínculos seguros en PowerShell (el cmdlet **Set-SafeLinksPolicy** no tiene ningún _parámetro Name)._</span><span class="sxs-lookup"><span data-stu-id="97c50-286">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="97c50-287">Al cambiar el nombre de una directiva Caja fuerte vínculos en el Centro de seguridad & cumplimiento, solo se cambia el nombre de la regla de vínculos _seguros_.</span><span class="sxs-lookup"><span data-stu-id="97c50-287">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="97c50-288">La única consideración adicional para modificar directivas de vínculos seguros en PowerShell es la sintaxis disponible para el parámetro _DoNotRewriteUrls_ (la lista ["No volver](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)a escribir las siguientes direcciones URL" ):</span><span class="sxs-lookup"><span data-stu-id="97c50-288">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="97c50-289">Para agregar valores que reemplacen las entradas existentes, use la sintaxis siguiente: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="97c50-289">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="97c50-290">Para agregar o quitar valores sin afectar a otras entradas existentes, use la sintaxis siguiente: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="97c50-290">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="97c50-291">De lo contrario, la misma configuración está disponible al crear una directiva de vínculos seguros como se describe en el paso [1: Usar PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) para crear una directiva de vínculos seguros anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="97c50-291">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="97c50-292">Para modificar una directiva de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="97c50-292">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="97c50-293">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="97c50-293">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="97c50-294">Usar PowerShell para modificar reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="97c50-294">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="97c50-295">La única configuración que no está disponible al modificar una regla de vínculos seguros en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="97c50-295">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="97c50-296">Para habilitar o deshabilitar las reglas de vínculos seguros existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="97c50-296">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="97c50-297">De lo contrario, la misma configuración está disponible al crear una regla tal como se describe en el paso [2: Usar PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) para crear una regla de vínculos seguros anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="97c50-297">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="97c50-298">Para modificar una regla de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="97c50-298">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="97c50-299">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="97c50-299">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="97c50-300">Usar PowerShell para habilitar o deshabilitar reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="97c50-300">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="97c50-301">Habilitar o deshabilitar una regla de vínculos seguros en PowerShell habilita o deshabilita toda la directiva de vínculos de Caja fuerte (la regla de vínculos seguros y la directiva de vínculos seguros asignada).</span><span class="sxs-lookup"><span data-stu-id="97c50-301">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="97c50-302">Para habilitar o deshabilitar una regla de vínculos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="97c50-302">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="97c50-303">En este ejemplo se deshabilita la regla de vínculos seguros denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="97c50-303">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="97c50-304">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="97c50-304">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="97c50-305">Para obtener información detallada acerca de la sintaxis y los parámetros, vea [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) y [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="97c50-305">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="97c50-306">Usar PowerShell para establecer la prioridad de las reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="97c50-306">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="97c50-p123">El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="97c50-p123">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="97c50-312">Para establecer la prioridad de una regla de vínculos seguros en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="97c50-312">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="97c50-p124">En el ejemplo siguiente, la prioridad de la regla denominada "Marketing Department" se establece en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="97c50-p124">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="97c50-315">Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-SafeLinksRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="97c50-315">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="97c50-316">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="97c50-316">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="97c50-317">Usar PowerShell para quitar directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="97c50-317">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="97c50-318">Cuando usa PowerShell para quitar una directiva de vínculos seguros, no se quita la regla de vínculos seguros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="97c50-318">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="97c50-319">Para quitar una directiva de vínculos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="97c50-319">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="97c50-320">En este ejemplo se quita la directiva de vínculos seguros denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="97c50-320">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="97c50-321">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="97c50-321">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="97c50-322">Usar PowerShell para quitar reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="97c50-322">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="97c50-323">Cuando usa PowerShell para quitar una regla de vínculos seguros, no se quita la directiva de vínculos seguros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="97c50-323">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="97c50-324">Para quitar una regla de vínculos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="97c50-324">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="97c50-325">En este ejemplo se quita la regla de vínculos seguros denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="97c50-325">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="97c50-326">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="97c50-326">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="97c50-327">Para comprobar que los Caja fuerte están analizando mensajes, compruebe los informes de Microsoft Defender disponibles Office 365 datos.</span><span class="sxs-lookup"><span data-stu-id="97c50-327">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="97c50-328">Para obtener más información, vea [View reports for Defender for Office 365](view-reports-for-mdo.md) and Use Explorer in the Security & Compliance [Center](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="97c50-328">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="97c50-329">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="97c50-329">How do you know these procedures worked?</span></span>

<span data-ttu-id="97c50-330">Para comprobar que ha creado, modificado o quitado correctamente las directivas de vínculos Caja fuerte, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="97c50-330">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="97c50-331">En el Centro de seguridad & cumplimiento, vaya a **Directiva de administración** de amenazas ATP Caja fuerte \>  \> **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="97c50-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="97c50-332">Compruebe la lista de directivas, sus **valores de** estado y sus **valores de** prioridad.</span><span class="sxs-lookup"><span data-stu-id="97c50-332">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="97c50-333">Para ver más detalles, seleccione la directiva de la lista y vea los detalles en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="97c50-333">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="97c50-334">En Exchange Online PowerShell o Exchange Online Protection PowerShell, reemplace por el nombre de la directiva o regla, ejecute el siguiente comando y compruebe \<Name\> la configuración:</span><span class="sxs-lookup"><span data-stu-id="97c50-334">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```