---
title: Configurar directivas de vínculos a prueba de errores en Microsoft defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo ver, crear, modificar y eliminar directivas de vínculos seguros y la configuración de vínculos seguros globales en Microsoft defender para Office 365.
ms.openlocfilehash: 550be48d5f1cae490c53c8f4a9fcedb0b9f21f73
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572722"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="65921-103">Configurar directivas de vínculos a prueba de errores en Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="65921-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="65921-104">Este artículo está destinado a los clientes empresariales que tienen [Microsoft defender para Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="65921-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="65921-105">Si es un usuario doméstico que busca información sobre Safelinks en Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="65921-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="65921-106">Vínculos seguros es una característica de [Microsoft defender para Office 365](office-365-atp.md) que proporciona análisis de URL de los mensajes de correo electrónico entrantes en el flujo de correo y la hora de la comprobación de direcciones URL y vínculos en mensajes de correo electrónico y en otras ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="65921-106">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="65921-107">Para obtener más información, vea [vínculos a prueba de errores en Microsoft defender para Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="65921-107">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="65921-108">No hay ninguna directiva de vínculos a prueba de errores integrada o predeterminada.</span><span class="sxs-lookup"><span data-stu-id="65921-108">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="65921-109">Para obtener vínculos a prueba de errores de las direcciones URL, debe crear una o más directivas de vínculos seguros, como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="65921-109">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

<span data-ttu-id="65921-110">Puede configurar directivas de vínculos seguros en el centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para las organizaciones de Microsoft 365 con buzones de correo en Exchange Online; PowerShell de EOP independiente para las organizaciones sin buzones de Exchange Online, pero con Microsoft defender para Office 365 para las suscripciones complementarias).</span><span class="sxs-lookup"><span data-stu-id="65921-110">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="65921-111">Los elementos básicos de una directiva de vínculos seguros son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="65921-111">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="65921-112">**La Directiva de vínculos seguros**: activar la protección de vínculos seguros, activar el análisis de URL en tiempo real, especificar si se debe esperar a que se complete la detección en tiempo real antes de entregar el mensaje, activar el examen de mensajes internos, especificar si se realiza un seguimiento de los clics del usuario en las direcciones URL y especificar si se permite a los usuarios hacer clic en el valle.</span><span class="sxs-lookup"><span data-stu-id="65921-112">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="65921-113">**La regla de vínculos seguros**: especifica la prioridad y los filtros de destinatarios (a los que se aplica la Directiva).</span><span class="sxs-lookup"><span data-stu-id="65921-113">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="65921-114">La diferencia entre estos dos elementos no es obvia cuando se administran directivas de vínculos seguros en el centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="65921-114">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="65921-115">Al crear una directiva de vínculos seguros, en realidad está creando una regla de vínculos seguros y la Directiva de vínculos seguros asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="65921-115">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="65921-116">Cuando se modifica una directiva de vínculos seguros, la configuración relacionada con los filtros nombre, prioridad, habilitado o deshabilitado y de destinatarios modifica la regla de vínculos a prueba de errores.</span><span class="sxs-lookup"><span data-stu-id="65921-116">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="65921-117">Todas las demás opciones modifican la Directiva de vínculos seguros asociada.</span><span class="sxs-lookup"><span data-stu-id="65921-117">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="65921-118">Cuando se quita una directiva de vínculos seguros, se quitan la regla de vínculos seguros y la Directiva de vínculos seguros asociada.</span><span class="sxs-lookup"><span data-stu-id="65921-118">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="65921-119">En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado.</span><span class="sxs-lookup"><span data-stu-id="65921-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="65921-120">Para obtener más información, vea la sección [usar Exchange Online PowerShell o Standalone EOP PowerShell para configurar directivas de vínculos seguros](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) , más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="65921-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="65921-121">La configuración global de la protección de vínculos seguros se establece **fuera** de las directivas de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="65921-121">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="65921-122">Para obtener instrucciones, vea [Configure global Settings for Safe links in Microsoft defender for Office 365](configure-global-settings-for-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="65921-122">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="65921-123">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="65921-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="65921-124">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="65921-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="65921-125">Para ir directamente a la página de **vínculos seguros** , use <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="65921-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="65921-126">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="65921-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="65921-127">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="65921-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="65921-128">Debe tener asignados permisos en el centro de seguridad & cumplimiento antes de poder llevar a cabo los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="65921-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="65921-129">Para crear, modificar y eliminar directivas de vínculos a prueba de errores, debe ser miembro de los grupos de funciones administración de la **organización** o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="65921-129">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="65921-130">Para el acceso de solo lectura a las directivas de vínculos a prueba de errores, debe ser miembro de los grupos de roles **lector global** o **lector de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="65921-130">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="65921-131">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="65921-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="65921-132">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="65921-132">**Notes**:</span></span>

  - <span data-ttu-id="65921-133">La adición de usuarios al rol correspondiente de Azure Active Directory en el centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el centro de seguridad & cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="65921-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="65921-134">Para obtener más información, vea [Asignar roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="65921-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="65921-135">El grupo de roles administración de la **organización de solo vista** de [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="65921-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="65921-136">Para conocer la configuración recomendada para las directivas de vínculos seguros, consulte [configuración de directivas de vínculos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="65921-136">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="65921-137">Permitir que se aplique una directiva nueva o actualizada durante un máximo de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="65921-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="65921-138">[Las nuevas características se agregan continuamente a Microsoft defender para Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="65921-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="65921-139">A medida que se agreguen nuevas características, es posible que deba realizar ajustes en las directivas de vínculos a prueba de errores existentes.</span><span class="sxs-lookup"><span data-stu-id="65921-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="65921-140">Usar el centro de seguridad & cumplimiento para crear directivas de vínculos a prueba de errores</span><span class="sxs-lookup"><span data-stu-id="65921-140">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="65921-141">La creación de una directiva de vínculos seguros personalizada en el centro de seguridad & cumplimiento crea la regla de vínculos seguros y la Directiva de vínculos seguros asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="65921-141">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="65921-142">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP Safe links**.</span><span class="sxs-lookup"><span data-stu-id="65921-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="65921-143">En la página **vínculos seguros** , haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="65921-143">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="65921-144">Se abre el Asistente para **nueva Directiva de vínculos seguros** .</span><span class="sxs-lookup"><span data-stu-id="65921-144">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="65921-145">En la página **asigne un nombre a la Directiva** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="65921-145">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="65921-146">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="65921-146">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="65921-147">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="65921-147">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="65921-148">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="65921-148">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="65921-149">En la página de **configuración** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="65921-149">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="65921-150">**Seleccione la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes**: seleccione **activado** para habilitar la protección de vínculos seguros para vínculos en mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="65921-150">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="65921-151">**Seleccione la acción para direcciones URL potencialmente malintencionadas o desconocidas en Microsoft Teams**: seleccione **activado** para habilitar la protección de vínculos seguros para vínculos en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="65921-151">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="65921-152">**Aplique un análisis de URL en tiempo real en busca de vínculos y vínculos sospechosos que apunten a archivos**: Seleccione esta opción para habilitar el análisis en tiempo real de vínculos en mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="65921-152">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="65921-153">**Espere a que se complete el análisis de URL antes de entregar el mensaje**: Seleccione esta opción para esperar a que se complete el análisis de URL en tiempo real antes de entregar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="65921-153">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="65921-154">**Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización**: Seleccione esta opción para aplicar la Directiva de vínculos seguros a los mensajes entre los remitentes internos y los destinatarios internos.</span><span class="sxs-lookup"><span data-stu-id="65921-154">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="65921-155">**No hacer un seguimiento de los clics del usuario**: deje esta opción sin seleccionar para permitir que el seguimiento del usuario haga clic en direcciones URL en mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="65921-155">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="65921-156">**No permita que los usuarios hagan clic a través de la dirección URL original**: Seleccione esta opción para impedir que los usuarios hagan clic a través de la dirección URL original en [las páginas de advertencia](atp-safe-links.md#warning-pages-from-safe-links).</span><span class="sxs-lookup"><span data-stu-id="65921-156">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="65921-157">**No vuelva a escribir las siguientes direcciones URL**: permite el acceso a las direcciones URL especificadas que, de lo contrario, bloquearían mediante vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="65921-157">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="65921-158">En el cuadro, escriba la dirección URL o el valor que desee y, a continuación, haga clic en</span><span class="sxs-lookup"><span data-stu-id="65921-158">In the box, type the URL or value that you want, and then click</span></span> ![Icono Agregar botón](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="65921-160">.</span><span class="sxs-lookup"><span data-stu-id="65921-160">.</span></span>

     <span data-ttu-id="65921-161">Para quitar una entrada existente, selecciónela y, a continuación, haga clic en</span><span class="sxs-lookup"><span data-stu-id="65921-161">To remove an existing entry, select it and then click</span></span> ![Icono Eliminar botón](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="65921-163">.</span><span class="sxs-lookup"><span data-stu-id="65921-163">.</span></span>

     <span data-ttu-id="65921-164">Para obtener la sintaxis de la entrada, consulte [la sintaxis de la entrada "no reescribir las siguientes direcciones URL"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="65921-164">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="65921-165">Para obtener información detallada acerca de estas opciones, vea configuración de [vínculos seguros para los mensajes de correo electrónico](atp-safe-links.md#safe-links-settings-for-email-messages) y la [configuración de vínculos seguros para Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="65921-165">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="65921-166">Para obtener más información sobre los valores recomendados para la configuración de directivas estándar y estricta, consulte [configuración de directivas de vínculos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="65921-166">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="65921-167">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="65921-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="65921-168">En la página **aplicado a** que aparece, identifique los destinatarios internos a los que se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="65921-168">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="65921-169">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="65921-169">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="65921-170">Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="65921-170">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="65921-171">Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="65921-171">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="65921-172">Haga clic en **Agregar condición**.</span><span class="sxs-lookup"><span data-stu-id="65921-172">Click **Add a condition**.</span></span> <span data-ttu-id="65921-173">En la lista desplegable que aparece, seleccione una condición en **aplicado si**:</span><span class="sxs-lookup"><span data-stu-id="65921-173">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="65921-174">**El destinatario es**: especifica uno o más buzones de correo, usuarios de correo o contactos de correo de su organización.</span><span class="sxs-lookup"><span data-stu-id="65921-174">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="65921-175">**El destinatario es un miembro de**: especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="65921-175">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="65921-176">**El dominio del destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en su organización.</span><span class="sxs-lookup"><span data-stu-id="65921-176">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="65921-177">Después de seleccionar la condición, aparece la lista desplegable correspondiente con una **de estas** casillas.</span><span class="sxs-lookup"><span data-stu-id="65921-177">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="65921-178">Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="65921-178">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="65921-179">Haga clic en el cuadro y comience a escribir para filtrar la lista y seleccionar un valor.</span><span class="sxs-lookup"><span data-stu-id="65921-179">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="65921-180">Para agregar más valores, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="65921-180">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="65921-181">Para quitar entradas individuales, haga **Remove** clic en ![ el icono quitar quitar del ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="65921-181">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="65921-182">Para quitar toda la condición, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación en la condición.</span><span class="sxs-lookup"><span data-stu-id="65921-182">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="65921-183">Para agregar una condición adicional, haga clic en **Agregar condición** y seleccione un valor restante en **aplicado si**.</span><span class="sxs-lookup"><span data-stu-id="65921-183">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="65921-184">Para agregar excepciones, haga clic en **Agregar una condición** y seleccione una excepción en **excepto si**.</span><span class="sxs-lookup"><span data-stu-id="65921-184">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="65921-185">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="65921-185">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="65921-186">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="65921-186">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="65921-187">En la página **Revise la configuración** que aparece, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="65921-187">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="65921-188">Puede hacer clic en **Editar** en cada configuración para modificarla.</span><span class="sxs-lookup"><span data-stu-id="65921-188">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="65921-189">Cuando haya terminado, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="65921-189">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="65921-190">Usar el centro de seguridad & cumplimiento para ver las directivas de vínculos a prueba de errores</span><span class="sxs-lookup"><span data-stu-id="65921-190">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="65921-191">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP Safe links**.</span><span class="sxs-lookup"><span data-stu-id="65921-191">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="65921-192">En la página **vínculos seguros** , seleccione una directiva de la lista y haga clic en ella (no active la casilla de verificación).</span><span class="sxs-lookup"><span data-stu-id="65921-192">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="65921-193">Los detalles de la Directiva aparecen en un vuelo hacia fuera</span><span class="sxs-lookup"><span data-stu-id="65921-193">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="65921-194">Usar el centro de seguridad & cumplimiento para modificar las directivas de vínculos a prueba de errores</span><span class="sxs-lookup"><span data-stu-id="65921-194">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="65921-195">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP Safe links**.</span><span class="sxs-lookup"><span data-stu-id="65921-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="65921-196">En la página **vínculos seguros** , seleccione una directiva de la lista y haga clic en ella (no active la casilla de verificación).</span><span class="sxs-lookup"><span data-stu-id="65921-196">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="65921-197">En los detalles de la Directiva hacia fuera que aparece, haga clic en **Editar Directiva**.</span><span class="sxs-lookup"><span data-stu-id="65921-197">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="65921-198">La configuración disponible en la volar hacia fuera que aparece es idéntica a la que se describe en la sección [usar el centro de seguridad & cumplimiento para crear directivas de vínculos seguros](#use-the-security--compliance-center-to-create-safe-links-policies) .</span><span class="sxs-lookup"><span data-stu-id="65921-198">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="65921-199">Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la Directiva, consulte las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="65921-199">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="65921-200">Habilitar o deshabilitar las directivas de vínculos a prueba de errores</span><span class="sxs-lookup"><span data-stu-id="65921-200">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="65921-201">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP Safe links**.</span><span class="sxs-lookup"><span data-stu-id="65921-201">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="65921-202">Observe el valor de la columna **Estado** :</span><span class="sxs-lookup"><span data-stu-id="65921-202">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="65921-203">Mueva el botón de alternancia a la izquierda para deshabilitar la directiva:</span><span class="sxs-lookup"><span data-stu-id="65921-203">Move the toggle to the left to disable the policy:</span></span> ![Desactivar Directiva](../../media/scc-toggle-off.png)<span data-ttu-id="65921-205">.</span><span class="sxs-lookup"><span data-stu-id="65921-205">.</span></span>

   - <span data-ttu-id="65921-206">Mueva el botón de alternancia a la derecha para habilitar la directiva:</span><span class="sxs-lookup"><span data-stu-id="65921-206">Move the toggle to the right to enable the policy:</span></span> ![Activar la Directiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="65921-208">.</span><span class="sxs-lookup"><span data-stu-id="65921-208">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="65921-209">Establecer la prioridad de las directivas de vínculos a prueba de errores</span><span class="sxs-lookup"><span data-stu-id="65921-209">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="65921-210">De forma predeterminada, las directivas de vínculos a prueba de errores reciben una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen prioridad más baja que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="65921-210">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="65921-211">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="65921-211">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="65921-212">Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="65921-212">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="65921-213">Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="65921-213">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="65921-214">Las directivas de vínculos seguros se muestran en el orden en que se procesan (la primera Directiva tiene el valor de **prioridad** 0).</span><span class="sxs-lookup"><span data-stu-id="65921-214">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="65921-215">**Nota**: en el centro de seguridad & cumplimiento, solo puede cambiar la prioridad de la Directiva de vínculos seguros después de crearla.</span><span class="sxs-lookup"><span data-stu-id="65921-215">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="65921-216">En PowerShell, puede invalidar la prioridad predeterminada al crear la regla de vínculos seguros (que puede afectar a la prioridad de las reglas existentes).</span><span class="sxs-lookup"><span data-stu-id="65921-216">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="65921-217">Para cambiar la prioridad de una directiva, suba o baje la directiva en la lista (no puede modificar directamente el número de **Prioridad** en el Centro de seguridad y cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="65921-217">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="65921-218">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP Safe links**.</span><span class="sxs-lookup"><span data-stu-id="65921-218">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="65921-219">En la página **vínculos seguros** , seleccione una directiva de la lista y haga clic en ella (no active la casilla de verificación).</span><span class="sxs-lookup"><span data-stu-id="65921-219">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="65921-220">En los detalles de la Directiva volar hacia fuera que aparece, haga clic en el botón prioridad disponible:</span><span class="sxs-lookup"><span data-stu-id="65921-220">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="65921-221">La Directiva de vínculos seguros con el valor de **prioridad** **0** sólo tiene disponible el botón **disminuir prioridad** .</span><span class="sxs-lookup"><span data-stu-id="65921-221">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="65921-222">La Directiva de vínculos seguros con el valor de **prioridad** más bajo (por ejemplo, **3**) solo tiene el botón **aumentar prioridad** disponible.</span><span class="sxs-lookup"><span data-stu-id="65921-222">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="65921-223">Si tiene tres o más directivas de vínculos seguros, las directivas entre los valores de prioridad mayor y menor tienen los botones **aumentar prioridad** y **disminuir prioridad** disponibles.</span><span class="sxs-lookup"><span data-stu-id="65921-223">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="65921-224">Haga clic en **aumentar prioridad** o **disminuir prioridad** para cambiar el valor de **prioridad** .</span><span class="sxs-lookup"><span data-stu-id="65921-224">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="65921-225">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="65921-225">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="65921-226">Usar el centro de seguridad & cumplimiento para quitar directivas de vínculos a prueba de errores</span><span class="sxs-lookup"><span data-stu-id="65921-226">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="65921-227">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP Safe links**.</span><span class="sxs-lookup"><span data-stu-id="65921-227">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="65921-228">En la página **vínculos seguros** , seleccione una directiva de la lista y haga clic en ella (no active la casilla de verificación).</span><span class="sxs-lookup"><span data-stu-id="65921-228">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="65921-229">En los detalles de la Directiva que aparecen, haga clic en **eliminar Directiva** y, a continuación, haga clic en **sí** en el cuadro de diálogo de advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="65921-229">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="65921-230">Usar Exchange Online PowerShell o PowerShell independiente de EOP para configurar directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="65921-230">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="65921-231">Como se ha descrito anteriormente, una directiva de vínculos seguros consta de una directiva de vínculos seguros y una regla de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="65921-231">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="65921-232">En PowerShell, la diferencia entre las directivas de vínculos a prueba de errores y las reglas de vínculos seguros es evidente.</span><span class="sxs-lookup"><span data-stu-id="65921-232">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="65921-233">Las directivas de vínculos a prueba de errores se administran mediante los cmdlets **\* -SafeLinksPolicy** y se administran las reglas de vínculos a prueba de errores mediante los cmdlets **\* -SafeLinksRule** .</span><span class="sxs-lookup"><span data-stu-id="65921-233">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="65921-234">En PowerShell, se crea la Directiva de vínculos seguros en primer lugar y, a continuación, se crea la regla de vínculos seguros que identifica la Directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="65921-234">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="65921-235">En PowerShell, la configuración de la Directiva de vínculos seguros y la regla de vínculos seguros se modifica por separado.</span><span class="sxs-lookup"><span data-stu-id="65921-235">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="65921-236">Cuando se quita una directiva de vínculos seguros de PowerShell, la regla de vínculos seguros correspondiente no se quita automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="65921-236">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="65921-237">Usar PowerShell para crear directivas de vínculos a prueba de errores</span><span class="sxs-lookup"><span data-stu-id="65921-237">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="65921-238">La creación de una directiva de vínculos seguros en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="65921-238">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="65921-239">Cree la Directiva de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="65921-239">Create the safe links policy.</span></span>
2. <span data-ttu-id="65921-240">Cree la regla de vínculos seguros que especifica la Directiva de vínculos a prueba de errores a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="65921-240">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

 <span data-ttu-id="65921-241">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="65921-241">**Notes**:</span></span>

- <span data-ttu-id="65921-242">Puede crear una nueva regla de vínculos seguros y asignarle una directiva de vínculos seguros existente no asociada.</span><span class="sxs-lookup"><span data-stu-id="65921-242">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="65921-243">No se puede asociar una regla de vínculos seguros con más de una directiva de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="65921-243">A safe links rule can't be associated with more than one safe links policy.</span></span>

- <span data-ttu-id="65921-244">Puede configurar las siguientes opciones en nuevas directivas de vínculos a prueba de errores en PowerShell que no están disponibles en el centro de seguridad & cumplimiento hasta que se crea la Directiva:</span><span class="sxs-lookup"><span data-stu-id="65921-244">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="65921-245">Cree la nueva directiva como deshabilitada (_habilitada_ `$false` en el cmdlet **New-SafeLinksRule** ).</span><span class="sxs-lookup"><span data-stu-id="65921-245">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
  - <span data-ttu-id="65921-246">Establezca la prioridad de la Directiva durante la creación (_prioridad_ _\<Number\>_ ) en el cmdlet **New-SafeLinksRule** ).</span><span class="sxs-lookup"><span data-stu-id="65921-246">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>

- <span data-ttu-id="65921-247">Una nueva Directiva de vínculos seguros que se crea en PowerShell no es visible en el centro de seguridad & cumplimiento hasta que se asigna la Directiva a una regla de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="65921-247">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="65921-248">Paso 1: usar PowerShell para crear una directiva de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="65921-248">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="65921-249">Para crear una directiva de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="65921-249">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

<span data-ttu-id="65921-250">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="65921-250">**Notes**:</span></span>

- <span data-ttu-id="65921-251">Para obtener información detallada sobre la sintaxis de entrada que se debe usar para el parámetro _DoNotRewriteUrls_ , vea [la sintaxis de entrada de la lista "no reescribir las siguientes direcciones URL"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="65921-251">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

- <span data-ttu-id="65921-252">Para obtener más sintaxis que puede usar para el parámetro _DoNotRewriteUrls_ al modificar las directivas de vínculos a prueba de errores existentes mediante el cmdlet **set-SafeLinksPolicy** , consulte la sección [usar PowerShell para modificar las directivas de vínculos seguros](#use-powershell-to-modify-safe-links-policies) , más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="65921-252">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="65921-253">En este ejemplo se crea una directiva de vínculos seguros llamada contoso All con los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="65921-253">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="65921-254">Activar el análisis y la reescritura de URL en mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="65921-254">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="65921-255">Active el análisis de URL en Teams (pulse solo vista previa).</span><span class="sxs-lookup"><span data-stu-id="65921-255">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="65921-256">Active el análisis en tiempo real de las direcciones URL en las que hizo clic, incluidos los vínculos a los que se hizo clic que señalan a archivos.</span><span class="sxs-lookup"><span data-stu-id="65921-256">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="65921-257">Espere a que se complete el análisis de URL antes de entregar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="65921-257">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="65921-258">Activar el análisis y la reescritura de URL para los mensajes internos.</span><span class="sxs-lookup"><span data-stu-id="65921-258">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="65921-259">Realizar un seguimiento de los clics de usuario relacionados con la protección de vínculos seguros (no se usa el parámetro _DoNotTrackUserClicks_ y el valor predeterminado es $false, lo que significa que se realiza un seguimiento de los clics del usuario).</span><span class="sxs-lookup"><span data-stu-id="65921-259">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="65921-260">No permita que los usuarios hagan clic en la dirección URL original.</span><span class="sxs-lookup"><span data-stu-id="65921-260">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="65921-261">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="65921-261">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="65921-262">Paso 2: usar PowerShell para crear una regla de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="65921-262">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="65921-263">Para crear una regla de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="65921-263">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="65921-264">En este ejemplo se crea una regla de vínculos a prueba de errores denominada contoso All con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="65921-264">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="65921-265">La regla está asociada a la Directiva de vínculos a prueba de errores denominada contoso ALL.</span><span class="sxs-lookup"><span data-stu-id="65921-265">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="65921-266">La regla se aplica a todos los destinatarios del dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="65921-266">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="65921-267">Como no se usa el parámetro _Priority_ , se usa la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="65921-267">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="65921-268">La regla está habilitada (no se usa el parámetro _Enabled_ y el valor predeterminado es `$true` ).</span><span class="sxs-lookup"><span data-stu-id="65921-268">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="65921-269">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="65921-269">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="65921-270">Usar PowerShell para ver las directivas de vínculos a prueba de errores</span><span class="sxs-lookup"><span data-stu-id="65921-270">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="65921-271">Para ver las directivas de vínculos a prueba de errores existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="65921-271">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="65921-272">En este ejemplo se devuelve una lista resumida de todas las directivas de vínculos a prueba de errores.</span><span class="sxs-lookup"><span data-stu-id="65921-272">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="65921-273">En este ejemplo se muestra información detallada de la Directiva de vínculos a prueba de errores denominada ejecutivos de contoso.</span><span class="sxs-lookup"><span data-stu-id="65921-273">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="65921-274">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="65921-274">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="65921-275">Usar PowerShell para ver las reglas de vínculos a prueba de errores</span><span class="sxs-lookup"><span data-stu-id="65921-275">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="65921-276">Para ver las reglas de vínculos a prueba de errores existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="65921-276">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="65921-277">En este ejemplo se devuelve una lista resumida de todas las reglas de vínculos a prueba de errores.</span><span class="sxs-lookup"><span data-stu-id="65921-277">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="65921-278">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="65921-278">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="65921-279">En este ejemplo se muestra información detallada de la regla de vínculos a prueba de errores denominada ejecutivos de contoso.</span><span class="sxs-lookup"><span data-stu-id="65921-279">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="65921-280">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="65921-280">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="65921-281">Usar PowerShell para modificar directivas de vínculos a prueba de errores</span><span class="sxs-lookup"><span data-stu-id="65921-281">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="65921-282">No puede cambiar el nombre de una directiva de vínculos seguros en PowerShell (el cmdlet **set-SafeLinksPolicy** no tiene ningún parámetro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="65921-282">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="65921-283">Al cambiar el nombre de una directiva de vínculos seguros en el centro de seguridad & cumplimiento, sólo cambia el nombre de la _regla_ de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="65921-283">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="65921-284">La única consideración adicional para modificar las directivas de vínculos a prueba de errores en PowerShell es la sintaxis disponible para el parámetro _DoNotRewriteUrls_ (la [lista "no reescribir las siguientes direcciones URL"](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span><span class="sxs-lookup"><span data-stu-id="65921-284">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="65921-285">Para agregar valores que van a reemplazar las entradas existentes, use la siguiente sintaxis: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="65921-285">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="65921-286">Para agregar o quitar valores sin que ello afecte a las entradas existentes, use la sintaxis siguiente: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="65921-286">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="65921-287">De lo contrario, la misma configuración está disponible cuando se crea una directiva de vínculos seguros, tal como se describe en la sección [paso 1: usar PowerShell para crear una directiva de vínculos seguros](#step-1-use-powershell-to-create-a-safe-links-policy) anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="65921-287">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="65921-288">Para modificar una directiva de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="65921-288">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="65921-289">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="65921-289">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="65921-290">Usar PowerShell para modificar las reglas de vínculos a prueba de errores</span><span class="sxs-lookup"><span data-stu-id="65921-290">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="65921-291">La única opción que no está disponible cuando se modifica una regla de vínculos seguros en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="65921-291">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="65921-292">Para habilitar o deshabilitar reglas de vínculos a prueba de errores, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="65921-292">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="65921-293">De lo contrario, la misma configuración está disponible cuando se crea una regla tal y como se describe en la sección [paso 2: usar PowerShell para crear una regla de vínculos seguros](#step-2-use-powershell-to-create-a-safe-links-rule) anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="65921-293">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="65921-294">Para modificar una regla de vínculos a prueba de errores, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="65921-294">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="65921-295">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="65921-295">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="65921-296">Usar PowerShell para habilitar o deshabilitar reglas de vínculos a prueba de errores</span><span class="sxs-lookup"><span data-stu-id="65921-296">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="65921-297">Al habilitar o deshabilitar una regla de vínculos a prueba de errores en PowerShell, se habilita o deshabilita toda la Directiva de vínculos seguros (la regla de vínculos seguros y la Directiva de vínculos seguros asignada).</span><span class="sxs-lookup"><span data-stu-id="65921-297">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="65921-298">Para habilitar o deshabilitar una regla de vínculos a prueba de errores en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="65921-298">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="65921-299">En este ejemplo se deshabilita la regla de vínculos a prueba de errores denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="65921-299">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="65921-300">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="65921-300">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="65921-301">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) y [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="65921-301">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="65921-302">Usar PowerShell para establecer la prioridad de las reglas de vínculos a prueba de errores</span><span class="sxs-lookup"><span data-stu-id="65921-302">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="65921-303">El valor de prioridad máximo que se puede establecer en una regla es 0.</span><span class="sxs-lookup"><span data-stu-id="65921-303">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="65921-304">El valor mínimo que se puede establecer depende del número de reglas.</span><span class="sxs-lookup"><span data-stu-id="65921-304">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="65921-305">Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4.</span><span class="sxs-lookup"><span data-stu-id="65921-305">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="65921-306">El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas.</span><span class="sxs-lookup"><span data-stu-id="65921-306">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="65921-307">Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="65921-307">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="65921-308">Para establecer la prioridad de una regla de vínculos seguros en PowerShell, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="65921-308">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="65921-309">Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2.</span><span class="sxs-lookup"><span data-stu-id="65921-309">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="65921-310">Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="65921-310">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="65921-311">**Nota**: para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-SafeLinksRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="65921-311">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="65921-312">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="65921-312">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="65921-313">Usar PowerShell para quitar directivas de vínculos a prueba de errores</span><span class="sxs-lookup"><span data-stu-id="65921-313">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="65921-314">Cuando se usa PowerShell para quitar una directiva de vínculos seguros, no se quita la regla de vínculos seguros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="65921-314">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="65921-315">Para quitar una directiva de vínculos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="65921-315">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="65921-316">En este ejemplo se quita la Directiva de vínculos a prueba de errores denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="65921-316">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="65921-317">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="65921-317">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="65921-318">Usar PowerShell para quitar reglas de vínculos a prueba de errores</span><span class="sxs-lookup"><span data-stu-id="65921-318">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="65921-319">Cuando se usa PowerShell para quitar una regla de vínculos seguros, no se quita la Directiva de vínculos seguros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="65921-319">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="65921-320">Para quitar una regla de vínculos a prueba de errores en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="65921-320">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="65921-321">En este ejemplo se quita la regla de vínculos a prueba de errores denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="65921-321">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="65921-322">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="65921-322">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="65921-323">Para comprobar que vínculos seguros está examinando los mensajes, consulte los informes de Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="65921-323">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="65921-324">Para obtener más información, vea [ver informes de defender para Office 365](view-reports-for-atp.md) y [usar el explorador en el centro de seguridad & cumplimiento](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="65921-324">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="65921-325">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="65921-325">How do you know these procedures worked?</span></span>

<span data-ttu-id="65921-326">Para comprobar que las directivas de vínculos seguros se crearon, modificaron o quitaron correctamente, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="65921-326">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="65921-327">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP Safe links**.</span><span class="sxs-lookup"><span data-stu-id="65921-327">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="65921-328">Compruebe la lista de directivas, sus valores de **Estado** y sus valores de **prioridad** .</span><span class="sxs-lookup"><span data-stu-id="65921-328">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="65921-329">Para ver más detalles, seleccione la Directiva de la lista y vea los detalles en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="65921-329">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="65921-330">En PowerShell de Exchange Online PowerShell o Exchange Online Protection, reemplace \<Name\> por el nombre de la Directiva o regla, ejecute el siguiente comando y Compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="65921-330">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
