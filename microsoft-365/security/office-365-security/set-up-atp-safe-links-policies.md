---
title: Configurar directivas de vínculos seguros en Microsoft Defender para Office 365
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
description: Los administradores pueden aprender a ver, crear, modificar y eliminar directivas de vínculos seguros y la configuración global de vínculos seguros en Microsoft Defender para Office 365.
ms.openlocfilehash: ef83d0dba1de03aa2b36384474791783e926059f
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780537"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="74786-103">Configurar directivas de vínculos seguros en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="74786-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="74786-104">Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="74786-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="74786-105">Si es un usuario principal que busca información sobre safelinks en Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="74786-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="74786-106">Vínculos seguros es una característica de Microsoft Defender para [Office 365](office-365-atp.md) que proporciona el análisis de direcciones URL de los mensajes de correo electrónico entrantes en el flujo de correo y el tiempo de comprobación de clics de direcciones URL y vínculos en mensajes de correo electrónico y en otras ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="74786-106">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="74786-107">Para obtener más información, vea [Vínculos seguros en Microsoft Defender para Office 365.](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="74786-107">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="74786-108">No hay ninguna directiva de vínculos seguros integrada o predeterminada.</span><span class="sxs-lookup"><span data-stu-id="74786-108">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="74786-109">Para obtener el análisis de vínculos seguros de direcciones URL, debe crear una o más directivas de vínculos seguros, tal como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="74786-109">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="74786-110">Las opciones globales de protección de vínculos seguros se configuran **fuera de** las directivas de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="74786-110">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="74786-111">Para obtener instrucciones, [consulte Configuración global de vínculos seguros en Microsoft Defender para Office 365.](configure-global-settings-for-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="74786-111">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="74786-112">Puede configurar directivas de vínculos seguros en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones elegibles de Microsoft 365 con buzones en Exchange Online; EOP PowerShell independiente para organizaciones sin buzones de Exchange Online, pero con suscripciones de complemento de Microsoft Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="74786-112">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="74786-113">Los elementos básicos de una directiva de vínculos seguros son:</span><span class="sxs-lookup"><span data-stu-id="74786-113">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="74786-114">La directiva de vínculos **seguros:** activar la protección de vínculos seguros, activar el examen de direcciones URL en tiempo real, especificar si se debe esperar a que se complete el análisis en tiempo real antes de entregar el mensaje, activar el examen de mensajes internos, especificar si se va a realizar un seguimiento de los clics del usuario en las direcciones URL y especificar si se permite a los usuarios hacer clic en la dirección URL original.</span><span class="sxs-lookup"><span data-stu-id="74786-114">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="74786-115">**La regla de vínculos seguros:** especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva).</span><span class="sxs-lookup"><span data-stu-id="74786-115">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="74786-116">La diferencia entre estos dos elementos no es obvia cuando administra directivas de vínculos seguros en el Centro de & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="74786-116">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="74786-117">Al crear una directiva de vínculos seguros, realmente está creando una regla de vínculos seguros y la directiva de vínculos seguros asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="74786-117">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="74786-118">Al modificar una directiva de vínculos seguros, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada, y los filtros de destinatarios modifican la regla de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="74786-118">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="74786-119">Todas las demás opciones modifican la directiva de vínculos seguros asociada.</span><span class="sxs-lookup"><span data-stu-id="74786-119">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="74786-120">Al quitar una directiva de vínculos seguros, se quitan la regla de vínculos seguros y la directiva de vínculos seguros asociada.</span><span class="sxs-lookup"><span data-stu-id="74786-120">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="74786-121">En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado.</span><span class="sxs-lookup"><span data-stu-id="74786-121">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="74786-122">Para obtener más información, vea la sección Usar Exchange Online PowerShell o [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) independiente para configurar directivas de vínculos seguros más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="74786-122">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="74786-123">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="74786-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="74786-124">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="74786-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="74786-125">Para ir directamente a la **página Vínculos seguros,** use <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="74786-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="74786-126">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="74786-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="74786-127">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="74786-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="74786-128">Deberá tener asignados permisos antes de poder realizar los procedimientos descritos en este artículo:</span><span class="sxs-lookup"><span data-stu-id="74786-128">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="74786-129">Para crear, modificar y eliminar directivas de vínculos seguros, debe ser miembro de los grupos de  roles Administración de  la organización o Administrador de seguridad en el Centro de cumplimiento de & de seguridad y miembro del grupo de roles Administración de la organización en Exchange Online.  </span><span class="sxs-lookup"><span data-stu-id="74786-129">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="74786-130">Para obtener acceso de solo lectura a las directivas de vínculos seguros, debe ser miembro de los grupos de roles Lector **global** o **Lector de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="74786-130">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="74786-131">Para obtener más información, vea [Permisos en el Centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md) y permisos en Exchange [Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="74786-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="74786-132">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="74786-132">**Notes**:</span></span>

  - <span data-ttu-id="74786-133">Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74786-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="74786-134">Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="74786-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="74786-135">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="74786-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="74786-136">Para obtener la configuración recomendada para las directivas de vínculos seguros, vea [la configuración de la directiva de vínculos seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="74786-136">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="74786-137">Espere hasta 30 minutos para que se aplique una directiva nueva o actualizada.</span><span class="sxs-lookup"><span data-stu-id="74786-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="74786-138">[Las nuevas características se agregan continuamente a Microsoft Defender para Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="74786-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="74786-139">A medida que se agregan nuevas características, es posible que deba realizar ajustes en las directivas de vínculos seguros existentes.</span><span class="sxs-lookup"><span data-stu-id="74786-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="74786-140">Usar el Centro de seguridad & cumplimiento para crear directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="74786-140">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="74786-141">La creación de una directiva de vínculos seguros personalizada en el Centro de seguridad y cumplimiento de & crea la regla de vínculos seguros y la directiva de vínculos seguros asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="74786-141">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="74786-142">En el Centro de & cumplimiento, vaya **a** Vínculos seguros de ATP de la directiva de administración \>  \> **de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="74786-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="74786-143">En la **página Vínculos seguros,** haga clic **en Crear**.</span><span class="sxs-lookup"><span data-stu-id="74786-143">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="74786-144">Se **abrirá el Asistente para nueva directiva de vínculos** seguros.</span><span class="sxs-lookup"><span data-stu-id="74786-144">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="74786-145">En la **página Nombre de la directiva,** configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="74786-145">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="74786-146">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="74786-146">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="74786-147">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="74786-147">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="74786-148">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="74786-148">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="74786-149">En la **página Configuración** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="74786-149">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="74786-150">**Seleccione la acción para direcciones URL potencialmente** malintencionadas desconocidas en los mensajes: seleccione Activar para habilitar la protección de vínculos seguros para vínculos en mensajes de correo electrónico. </span><span class="sxs-lookup"><span data-stu-id="74786-150">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="74786-151">**Seleccione la acción para direcciones** URL desconocidas o  potencialmente malintencionadas en Microsoft Teams: seleccione Activar para habilitar la protección de vínculos seguros para vínculos en Teams.</span><span class="sxs-lookup"><span data-stu-id="74786-151">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="74786-152">**Aplicar el examen de direcciones URL** en tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos: seleccione esta opción para habilitar el examen en tiempo real de los vínculos de los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="74786-152">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="74786-153">**Espere a que se complete el** examen de direcciones URL antes de entregar el mensaje: seleccione esta opción para esperar a que se complete el examen de url en tiempo real antes de entregar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="74786-153">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="74786-154">**Aplicar vínculos seguros a los** mensajes de correo electrónico enviados dentro de la organización: seleccione esta opción para aplicar la directiva de vínculos seguros a los mensajes entre remitentes internos y destinatarios internos.</span><span class="sxs-lookup"><span data-stu-id="74786-154">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="74786-155">**No realizar un seguimiento de los clics del** usuario: deje esta opción sin activar para habilitar los clics del usuario de seguimiento en las direcciones URL de los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="74786-155">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="74786-156">**No permitir que los usuarios hagan clic** en la dirección URL original: seleccione esta opción para impedir que los usuarios hagan clic en la dirección URL original en las páginas de [advertencia.](atp-safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="74786-156">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="74786-157">**No reescriba las siguientes** direcciones URL: permite el acceso a las direcciones URL especificadas que, de lo contrario, estarían bloqueadas por vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="74786-157">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="74786-158">En el cuadro, escriba la dirección URL o el valor que desee y, a continuación, haga clic en</span><span class="sxs-lookup"><span data-stu-id="74786-158">In the box, type the URL or value that you want, and then click</span></span> ![Icono de botón Agregar](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="74786-160">.</span><span class="sxs-lookup"><span data-stu-id="74786-160">.</span></span>

     <span data-ttu-id="74786-161">Para quitar una entrada existente, selecciónelo y, a continuación, haga clic en</span><span class="sxs-lookup"><span data-stu-id="74786-161">To remove an existing entry, select it and then click</span></span> ![Icono de botón Eliminar](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="74786-163">.</span><span class="sxs-lookup"><span data-stu-id="74786-163">.</span></span>

     <span data-ttu-id="74786-164">Para obtener la sintaxis de entrada, vea la sintaxis entry para la lista ["No reescribir las siguientes direcciones URL".](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="74786-164">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="74786-165">Para obtener información detallada acerca de esta configuración, vea La configuración de vínculos [seguros](atp-safe-links.md#safe-links-settings-for-email-messages) para los mensajes de correo electrónico y la configuración de [vínculos seguros para Microsoft Teams.](atp-safe-links.md#safe-links-settings-for-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="74786-165">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="74786-166">Para obtener más información sobre los valores recomendados para la configuración de directivas estándar y estricta, consulte [Configuración de directiva de vínculos seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="74786-166">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="74786-167">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="74786-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="74786-168">En la **página Aplicada a** que aparece, identifique los destinatarios internos a los que se aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="74786-168">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="74786-169">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="74786-169">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="74786-170">Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="74786-170">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="74786-171">Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="74786-171">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="74786-172">Haga **clic en Agregar una condición.**</span><span class="sxs-lookup"><span data-stu-id="74786-172">Click **Add a condition**.</span></span> <span data-ttu-id="74786-173">En la lista desplegable que aparece, seleccione una condición en **Aplicada si:**</span><span class="sxs-lookup"><span data-stu-id="74786-173">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="74786-174">**El destinatario es**: especifica uno o varios buzones, usuarios de correo o contactos de correo de su organización.</span><span class="sxs-lookup"><span data-stu-id="74786-174">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="74786-175">**El destinatario es miembro de**: Especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="74786-175">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="74786-176">**El dominio del destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en su organización.</span><span class="sxs-lookup"><span data-stu-id="74786-176">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="74786-177">Después de seleccionar la condición, aparece un desplegable correspondiente con **uno de estos** cuadros.</span><span class="sxs-lookup"><span data-stu-id="74786-177">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="74786-178">Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="74786-178">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="74786-179">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un valor.</span><span class="sxs-lookup"><span data-stu-id="74786-179">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="74786-180">Para agregar valores adicionales, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="74786-180">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="74786-181">Para quitar entradas individuales, haga clic **en el** ![ icono Quitar del ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="74786-181">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="74786-182">Para quitar toda la condición, haga clic **en el** icono Quitar de ![ la ](../../media/scc-remove-icon.png) condición.</span><span class="sxs-lookup"><span data-stu-id="74786-182">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="74786-183">Para agregar una condición adicional, haga clic **en Agregar una condición** y seleccione un valor restante en Aplicado **si**.</span><span class="sxs-lookup"><span data-stu-id="74786-183">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="74786-184">Para agregar excepciones, haga **clic en Agregar una condición** y seleccione una excepción en Excepto **si**.</span><span class="sxs-lookup"><span data-stu-id="74786-184">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="74786-185">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="74786-185">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="74786-186">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="74786-186">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="74786-187">En la **página Revisar la configuración** que aparece, revisa la configuración.</span><span class="sxs-lookup"><span data-stu-id="74786-187">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="74786-188">Puedes hacer clic **en Editar** en cada opción para modificarla.</span><span class="sxs-lookup"><span data-stu-id="74786-188">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="74786-189">Cuando haya terminado, haga clic **en Finalizar.**</span><span class="sxs-lookup"><span data-stu-id="74786-189">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="74786-190">Usar el Centro de & cumplimiento para ver directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="74786-190">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="74786-191">En el Centro de & cumplimiento, vaya **a** Vínculos seguros de ATP de la directiva de administración \>  \> **de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="74786-191">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="74786-192">En la **página Vínculos** seguros, seleccione una directiva de la lista y haga clic en ella (no active la casilla).</span><span class="sxs-lookup"><span data-stu-id="74786-192">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="74786-193">Los detalles de la directiva aparecen en un menú desplegable</span><span class="sxs-lookup"><span data-stu-id="74786-193">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="74786-194">Usar el Centro de seguridad & cumplimiento para modificar directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="74786-194">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="74786-195">En el Centro de & cumplimiento, vaya **a** Vínculos seguros de ATP de la directiva de administración \>  \> **de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="74786-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="74786-196">En la **página Vínculos** seguros, seleccione una directiva de la lista y haga clic en ella (no active la casilla).</span><span class="sxs-lookup"><span data-stu-id="74786-196">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="74786-197">En el control emergente de detalles de la directiva que aparece, haga clic **en Editar directiva.**</span><span class="sxs-lookup"><span data-stu-id="74786-197">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="74786-198">La configuración disponible en el control emergente que aparece es idéntica a la que se describe en la sección Usar el Centro de seguridad & cumplimiento para crear directivas [de vínculos seguros.](#use-the-security--compliance-center-to-create-safe-links-policies)</span><span class="sxs-lookup"><span data-stu-id="74786-198">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="74786-199">Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la directiva, consulte las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="74786-199">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="74786-200">Habilitar o deshabilitar directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="74786-200">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="74786-201">En el Centro de & cumplimiento, vaya **a** Vínculos seguros de ATP de la directiva de administración \>  \> **de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="74786-201">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="74786-202">Observe el valor de la columna **Estado:**</span><span class="sxs-lookup"><span data-stu-id="74786-202">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="74786-203">Mueva el botón de alternancia a la izquierda para deshabilitar la directiva:</span><span class="sxs-lookup"><span data-stu-id="74786-203">Move the toggle to the left to disable the policy:</span></span> ![Desactivar la directiva](../../media/scc-toggle-off.png)<span data-ttu-id="74786-205">.</span><span class="sxs-lookup"><span data-stu-id="74786-205">.</span></span>

   - <span data-ttu-id="74786-206">Mueva el botón de alternancia a la derecha para habilitar la directiva:</span><span class="sxs-lookup"><span data-stu-id="74786-206">Move the toggle to the right to enable the policy:</span></span> ![Activar la directiva](../../media/scc-toggle-on.png)<span data-ttu-id="74786-208">.</span><span class="sxs-lookup"><span data-stu-id="74786-208">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="74786-209">Establecer la prioridad de las directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="74786-209">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="74786-210">De forma predeterminada, a las directivas de vínculos seguros se les da una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen una prioridad menor que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="74786-210">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="74786-211">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="74786-211">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="74786-212">Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="74786-212">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="74786-213">Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="74786-213">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="74786-214">Las directivas de vínculos seguros se muestran en el orden en que se procesan (la primera directiva tiene el **valor de** prioridad 0).</span><span class="sxs-lookup"><span data-stu-id="74786-214">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="74786-215">**Nota:** En el Centro de & cumplimiento, solo puede cambiar la prioridad de la directiva de vínculos seguros después de crearla.</span><span class="sxs-lookup"><span data-stu-id="74786-215">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="74786-216">En PowerShell, puede invalidar la prioridad predeterminada al crear la regla de vínculos seguros (que puede afectar a la prioridad de las reglas existentes).</span><span class="sxs-lookup"><span data-stu-id="74786-216">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="74786-217">Para cambiar la prioridad de una directiva, suba o baje la directiva en la lista (no puede modificar directamente el número de **Prioridad** en el Centro de seguridad y cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="74786-217">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="74786-218">En el Centro de & cumplimiento, vaya **a** Vínculos seguros de ATP de la directiva de administración \>  \> **de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="74786-218">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="74786-219">En la **página Vínculos** seguros, seleccione una directiva de la lista y haga clic en ella (no active la casilla).</span><span class="sxs-lookup"><span data-stu-id="74786-219">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="74786-220">En el control emergente de detalles de la directiva que aparece, haga clic en el botón de prioridad disponible:</span><span class="sxs-lookup"><span data-stu-id="74786-220">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="74786-221">La directiva de vínculos seguros con **el valor de** **prioridad 0** solo tiene disponible el **botón** Disminuir prioridad.</span><span class="sxs-lookup"><span data-stu-id="74786-221">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="74786-222">La directiva de vínculos seguros con el valor **de prioridad** más bajo (por ejemplo, **3)** solo tiene el **botón Aumentar** prioridad disponible.</span><span class="sxs-lookup"><span data-stu-id="74786-222">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="74786-223">Si tiene tres o más directivas de vínculos seguros, las  directivas entre los valores de prioridad más alta y menor tienen disponibles los botones Aumentar prioridad **y** Disminuir prioridad.</span><span class="sxs-lookup"><span data-stu-id="74786-223">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="74786-224">Haga **clic en Aumentar prioridad** o **Disminuir** prioridad para cambiar el valor **de Prioridad.**</span><span class="sxs-lookup"><span data-stu-id="74786-224">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="74786-225">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="74786-225">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="74786-226">Usar el Centro de seguridad & cumplimiento para quitar directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="74786-226">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="74786-227">En el Centro de & cumplimiento, vaya **a** Vínculos seguros de ATP de la directiva de administración \>  \> **de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="74786-227">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="74786-228">En la **página Vínculos** seguros, seleccione una directiva de la lista y haga clic en ella (no active la casilla).</span><span class="sxs-lookup"><span data-stu-id="74786-228">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="74786-229">En el menú desplegable de detalles de la directiva que aparece, haga clic en Eliminar directiva y, a continuación, haga clic en **Sí** en el cuadro de diálogo de advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="74786-229">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="74786-230">Usar Exchange Online PowerShell o EOP PowerShell independiente para configurar directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="74786-230">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="74786-231">Como se describió anteriormente, una directiva de vínculos seguros consta de una directiva de vínculos seguros y una regla de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="74786-231">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="74786-232">En PowerShell, la diferencia entre las directivas de vínculos seguros y las reglas de vínculos seguros es aparente.</span><span class="sxs-lookup"><span data-stu-id="74786-232">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="74786-233">Las directivas de vínculos seguros se administran mediante los cmdlets **\* -SafeLinksPolicy** y se administran mediante los cmdlets **\* -SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="74786-233">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="74786-234">En PowerShell, primero se crea la directiva de vínculos seguros y, a continuación, se crea la regla de vínculos seguros que identifica la directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="74786-234">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="74786-235">En PowerShell, puede modificar la configuración de la directiva de vínculos seguros y la regla de vínculos seguros por separado.</span><span class="sxs-lookup"><span data-stu-id="74786-235">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="74786-236">Al quitar una directiva de vínculos seguros de PowerShell, la regla de vínculos seguros correspondiente no se quita automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="74786-236">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="74786-237">Usar PowerShell para crear directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="74786-237">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="74786-238">Crear una directiva de vínculos seguros en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="74786-238">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="74786-239">Cree la directiva de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="74786-239">Create the safe links policy.</span></span>
2. <span data-ttu-id="74786-240">Cree la regla de vínculos seguros que especifique la directiva de vínculos seguros a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="74786-240">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

 <span data-ttu-id="74786-241">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="74786-241">**Notes**:</span></span>

- <span data-ttu-id="74786-242">Puede crear una nueva regla de vínculos seguros y asignarle una directiva de vínculos seguros existente y sin asociar.</span><span class="sxs-lookup"><span data-stu-id="74786-242">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="74786-243">Una regla de vínculos seguros no se puede asociar a más de una directiva de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="74786-243">A safe links rule can't be associated with more than one safe links policy.</span></span>

- <span data-ttu-id="74786-244">Puede configurar las siguientes opciones en las nuevas directivas de vínculos seguros en PowerShell que no estén disponibles en el Centro de seguridad & Cumplimiento hasta después de crear la directiva:</span><span class="sxs-lookup"><span data-stu-id="74786-244">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="74786-245">Cree la nueva directiva como deshabilitada _(habilitada en_ `$false` el cmdlet **New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="74786-245">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
  - <span data-ttu-id="74786-246">Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_ ) en el cmdlet **New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="74786-246">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>

- <span data-ttu-id="74786-247">Una nueva directiva de vínculos seguros que cree en PowerShell no será visible en el Centro de seguridad & Cumplimiento hasta que asigne la directiva a una regla de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="74786-247">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="74786-248">Paso 1: Usar PowerShell para crear una directiva de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="74786-248">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="74786-249">Para crear una directiva de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="74786-249">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

<span data-ttu-id="74786-250">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="74786-250">**Notes**:</span></span>

- <span data-ttu-id="74786-251">Para obtener más información acerca de la sintaxis de entrada que se va a usar para el parámetro _DoNotRewriteUrls,_ vea la sintaxis entry para la lista ["No reescribir](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)las siguientes direcciones URL".</span><span class="sxs-lookup"><span data-stu-id="74786-251">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

- <span data-ttu-id="74786-252">Para obtener sintaxis adicional que puede usar para el parámetro _DoNotRewriteUrls_ al modificar directivas de vínculos seguros existentes mediante el cmdlet **Set-SafeLinksPolicy,** vea la sección Usar [PowerShell](#use-powershell-to-modify-safe-links-policies) para modificar directivas de vínculos seguros más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="74786-252">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="74786-253">En este ejemplo se crea una directiva de vínculos seguros denominada Contoso All con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="74786-253">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="74786-254">Active el análisis y la reescritura de direcciones URL en los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="74786-254">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="74786-255">Activar el examen de direcciones URL en Teams (solo vista previa de TAP).</span><span class="sxs-lookup"><span data-stu-id="74786-255">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="74786-256">Activa el examen en tiempo real de las direcciones URL en las que se ha hecho clic, incluidos los vínculos en los que se hace clic y que apuntan a archivos.</span><span class="sxs-lookup"><span data-stu-id="74786-256">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="74786-257">Espere a que se complete el examen de direcciones URL antes de entregar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="74786-257">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="74786-258">Active la reescritura y el examen de direcciones URL para los mensajes internos.</span><span class="sxs-lookup"><span data-stu-id="74786-258">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="74786-259">Realizar un seguimiento de los clics de usuario relacionados con la protección de vínculos seguros (no estamos usando el parámetro _DoNotTrackUserClicks_ y el valor predeterminado es $false, lo que significa que se realiza un seguimiento de los clics del usuario).</span><span class="sxs-lookup"><span data-stu-id="74786-259">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="74786-260">No permita a los usuarios hacer clic en la dirección URL original.</span><span class="sxs-lookup"><span data-stu-id="74786-260">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="74786-261">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="74786-261">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="74786-262">Paso 2: Usar PowerShell para crear una regla de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="74786-262">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="74786-263">Para crear una regla de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="74786-263">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="74786-264">En este ejemplo se crea una regla de vínculos seguros denominada Contoso All con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="74786-264">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="74786-265">La regla está asociada a la directiva de vínculos seguros denominada Contoso All.</span><span class="sxs-lookup"><span data-stu-id="74786-265">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="74786-266">La regla se aplica a todos los destinatarios del contoso.com dominio.</span><span class="sxs-lookup"><span data-stu-id="74786-266">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="74786-267">Como no estamos usando el parámetro _Priority,_ se usa la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="74786-267">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="74786-268">La regla está habilitada (no estamos usando el parámetro _Enabled_ y el valor predeterminado es `$true` ).</span><span class="sxs-lookup"><span data-stu-id="74786-268">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="74786-269">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="74786-269">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="74786-270">Usar PowerShell para ver directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="74786-270">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="74786-271">Para ver las directivas de vínculos seguros existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="74786-271">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="74786-272">En este ejemplo se devuelve una lista resumida de todas las directivas de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="74786-272">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="74786-273">En este ejemplo se devuelve información detallada de la directiva de vínculos seguros denominada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="74786-273">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="74786-274">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="74786-274">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="74786-275">Usar PowerShell para ver reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="74786-275">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="74786-276">Para ver las reglas de vínculos seguros existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="74786-276">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="74786-277">En este ejemplo se devuelve una lista resumida de todas las reglas de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="74786-277">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="74786-278">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="74786-278">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="74786-279">En este ejemplo se devuelve información detallada de la regla de vínculos seguros denominada Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="74786-279">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="74786-280">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="74786-280">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="74786-281">Usar PowerShell para modificar directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="74786-281">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="74786-282">No puede cambiar el nombre de una directiva de vínculos seguros en PowerShell (el cmdlet **Set-SafeLinksPolicy** no tiene ningún _parámetro Name)._</span><span class="sxs-lookup"><span data-stu-id="74786-282">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="74786-283">Cuando cambia el nombre de una directiva de vínculos seguros en el Centro de seguridad & cumplimiento, solo cambia el nombre de la regla de vínculos _seguros._</span><span class="sxs-lookup"><span data-stu-id="74786-283">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="74786-284">La única consideración adicional para modificar directivas de vínculos seguros en PowerShell es la sintaxis disponible para el parámetro _DoNotRewriteUrls_ (la lista ["No reescribir](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)las siguientes direcciones URL" ):</span><span class="sxs-lookup"><span data-stu-id="74786-284">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="74786-285">Para agregar valores que reemplacen las entradas existentes, use la sintaxis siguiente: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="74786-285">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="74786-286">Para agregar o quitar valores sin que ello afecte a otras entradas existentes, use la siguiente sintaxis: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="74786-286">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="74786-287">De lo contrario, la misma configuración está disponible al crear una directiva de vínculos seguros, como se describe en el paso [1: Usar PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) para crear una sección de directiva de vínculos seguros anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="74786-287">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="74786-288">Para modificar una directiva de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="74786-288">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="74786-289">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="74786-289">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="74786-290">Usar PowerShell para modificar reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="74786-290">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="74786-291">La única configuración que no está disponible al modificar una regla de vínculos seguros en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="74786-291">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="74786-292">Para habilitar o deshabilitar reglas de vínculos seguros existentes, consulte la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="74786-292">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="74786-293">De lo contrario, la misma configuración está disponible al crear una regla como se describe en el paso [2: Usar PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) para crear una sección de regla de vínculos seguros anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="74786-293">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="74786-294">Para modificar una regla de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="74786-294">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="74786-295">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="74786-295">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="74786-296">Usar PowerShell para habilitar o deshabilitar reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="74786-296">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="74786-297">Habilitar o deshabilitar una regla de vínculos seguros en PowerShell habilita o deshabilita toda la directiva de vínculos seguros (la regla de vínculos seguros y la directiva de vínculos seguros asignada).</span><span class="sxs-lookup"><span data-stu-id="74786-297">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="74786-298">Para habilitar o deshabilitar una regla de vínculos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="74786-298">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="74786-299">En este ejemplo se deshabilita la regla de vínculos seguros denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="74786-299">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="74786-300">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="74786-300">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="74786-301">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) y [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="74786-301">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="74786-302">Usar PowerShell para establecer la prioridad de las reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="74786-302">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="74786-303">El valor de prioridad máximo que se puede establecer en una regla es 0.</span><span class="sxs-lookup"><span data-stu-id="74786-303">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="74786-304">El valor mínimo que se puede establecer depende del número de reglas.</span><span class="sxs-lookup"><span data-stu-id="74786-304">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="74786-305">Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4.</span><span class="sxs-lookup"><span data-stu-id="74786-305">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="74786-306">El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas.</span><span class="sxs-lookup"><span data-stu-id="74786-306">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="74786-307">Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="74786-307">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="74786-308">Para establecer la prioridad de una regla de vínculos seguros en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="74786-308">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="74786-309">Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2.</span><span class="sxs-lookup"><span data-stu-id="74786-309">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="74786-310">Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="74786-310">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="74786-311">**Nota:** Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="74786-311">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="74786-312">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="74786-312">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="74786-313">Usar PowerShell para quitar directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="74786-313">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="74786-314">Al usar PowerShell para quitar una directiva de vínculos seguros, no se quita la regla de vínculos seguros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="74786-314">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="74786-315">Para quitar una directiva de vínculos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="74786-315">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="74786-316">En este ejemplo se quita la directiva de vínculos seguros denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="74786-316">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="74786-317">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="74786-317">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="74786-318">Usar PowerShell para quitar reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="74786-318">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="74786-319">Al usar PowerShell para quitar una regla de vínculos seguros, no se quita la directiva de vínculos seguros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="74786-319">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="74786-320">Para quitar una regla de vínculos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="74786-320">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="74786-321">En este ejemplo se quita la regla de vínculos seguros denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="74786-321">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="74786-322">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="74786-322">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="74786-323">Para comprobar que Vínculos seguros está analizando mensajes, compruebe los informes disponibles de Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="74786-323">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="74786-324">Para obtener más información, vea Ver informes de Defender para [Office 365](view-reports-for-atp.md) y Usar el Explorador en el Centro de [& cumplimiento.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="74786-324">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="74786-325">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="74786-325">How do you know these procedures worked?</span></span>

<span data-ttu-id="74786-326">Para comprobar que ha creado, modificado o quitado correctamente directivas de vínculos a prueba de problemas, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="74786-326">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="74786-327">En el Centro de & cumplimiento, vaya **a** Vínculos seguros de ATP de la directiva de administración \>  \> **de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="74786-327">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="74786-328">Compruebe la lista de directivas, sus **valores de** estado y sus **valores de** prioridad.</span><span class="sxs-lookup"><span data-stu-id="74786-328">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="74786-329">Para ver más detalles, seleccione la directiva de la lista y vea los detalles en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="74786-329">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="74786-330">En Exchange Online PowerShell o Exchange Online Protection PowerShell, reemplace por el nombre de la directiva o regla, ejecute el siguiente comando y \<Name\> compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="74786-330">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
