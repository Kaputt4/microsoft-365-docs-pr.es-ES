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
ms.openlocfilehash: 8d42051d2ca4f26758cbe7334d427f3f93178f97
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108216"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0b0c0-103">Configurar directivas Caja fuerte vínculos en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="0b0c0-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0b0c0-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="0b0c0-104">**Applies to**</span></span>
- [<span data-ttu-id="0b0c0-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="0b0c0-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0b0c0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b0c0-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="0b0c0-107">Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="0b0c0-108">Si es un usuario principal que busca información sobre safelinks en Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="0b0c0-109">Caja fuerte Los vínculos de [Microsoft Defender para Office 365](defender-for-office-365.md) proporcionan el examen de direcciones URL de los mensajes de correo electrónico entrantes en el flujo de correo y el momento de la comprobación de clics de direcciones URL y vínculos en mensajes de correo electrónico y en otras ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-109">Safe Links in [Microsoft Defender for Office 365](defender-for-office-365.md) provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="0b0c0-110">Para obtener más información, [vea Caja fuerte Links in Microsoft Defender for Office 365](safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="0b0c0-111">No hay ninguna directiva de vínculos integrada o Caja fuerte predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="0b0c0-112">Para obtener Caja fuerte de vínculos de búsqueda de direcciones URL, debe crear una o más directivas de vínculos de Caja fuerte como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
>
> <span data-ttu-id="0b0c0-113">Puede configurar la configuración global para la protección de Caja fuerte de vínculos **fuera** de Caja fuerte directivas de vínculos.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="0b0c0-114">Para obtener instrucciones, vea [Configure global settings for Caja fuerte Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>
>
> <span data-ttu-id="0b0c0-115">Los administradores deben tener en cuenta las diferentes opciones de configuración para Caja fuerte vínculos.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-115">Admins should consider the different configuration settings for Safe Links.</span></span> <span data-ttu-id="0b0c0-116">Una de las opciones disponibles es incluir información de identificación del usuario en Caja fuerte vínculos.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-116">One of the available options is to include user identifiable information in Safe Links.</span></span> <span data-ttu-id="0b0c0-117">Esta característica permite a los *equipos de Operaciones* de seguridad investigar posibles riesgos de usuario, tomar medidas correctivas y limitar infracciones costosas.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-117">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="0b0c0-118">Puede configurar directivas de vínculos de Caja fuerte en el portal de Microsoft 365 Defender o en PowerShell (powershell de Exchange Online para organizaciones de Microsoft 365 elegibles con buzones en Exchange Online; PowerShell EOP independiente para organizaciones sin buzones de Exchange Online, pero con Microsoft Defender para suscripciones de complemento Office 365).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-118">You can configure Safe Links policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="0b0c0-119">Los elementos básicos de una directiva Caja fuerte links son:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-119">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="0b0c0-120">La directiva de vínculos **seguros:** active la protección de vínculos de Caja fuerte, active la detección de direcciones URL en tiempo real, especifique si debe esperar a que se complete el examen en tiempo real antes de entregar el mensaje, activar el examen de mensajes internos, especificar si se debe realizar un seguimiento de los clics de usuario en las direcciones URL y especificar si se permite a los usuarios hacer clic en la url original.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-120">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="0b0c0-121">**La regla de vínculos seguros:** especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-121">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="0b0c0-122">La diferencia entre estos dos elementos no es obvia cuando se administran directivas de vínculos Caja fuerte en el portal de Microsoft 365 Defender web:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-122">The difference between these two elements isn't obvious when you manage Safe Links policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="0b0c0-123">Al crear una directiva Caja fuerte vínculos, en realidad está creando una regla de vínculos seguros y la directiva de vínculos seguros asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="0b0c0-124">Al modificar una directiva Caja fuerte vínculos, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada y los filtros de destinatarios modifican la regla de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="0b0c0-125">Todas las demás opciones modifican la directiva de vínculos seguros asociada.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="0b0c0-126">Al quitar una directiva de vínculos Caja fuerte, se quitan la regla de vínculos seguros y la directiva de vínculos seguros asociada.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="0b0c0-127">En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="0b0c0-128">Para obtener más información, vea la sección [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Caja fuerte Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0b0c0-129">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="0b0c0-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0b0c0-130">Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-130">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="0b0c0-131">Para ir directamente a la **página Caja fuerte vínculos,** use <https://security.microsoft.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="0b0c0-131">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="0b0c0-132">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0b0c0-133">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0b0c0-134">Debe tener asignados permisos antes de poder realizar los procedimientos descritos en este artículo:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="0b0c0-135">Para crear, modificar y eliminar directivas de vínculos de Caja fuerte, debe  ser miembro de los grupos de roles Administración  de la organización o Administrador de seguridad en el **portal** de Microsoft 365 Defender y miembro del grupo de roles Administración de la organización en Exchange Online. </span><span class="sxs-lookup"><span data-stu-id="0b0c0-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="0b0c0-136">Para obtener acceso de solo lectura a Caja fuerte de vínculos, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="0b0c0-137">Para obtener más información, vea [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="0b0c0-138">Agregar usuarios al rol Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el _portal_ de Microsoft 365 Defender y permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="0b0c0-139">Para obtener más información, vea [Asignar roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="0b0c0-140">.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-140">.</span></span> <span data-ttu-id="0b0c0-141">- El **grupo de roles Administración** de la organización de solo vista [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="0b0c0-142">Para obtener información sobre la configuración recomendada para Caja fuerte de vínculos, [consulte Caja fuerte configuración de directiva de vínculos.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="0b0c0-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="0b0c0-143">Permitir hasta 30 minutos para que se aplique una directiva nueva o actualizada.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="0b0c0-144">[Las nuevas características se agregan continuamente a Microsoft Defender para Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="0b0c0-145">A medida que se agregan nuevas características, es posible que deba realizar ajustes en las directivas de vínculos de Caja fuerte existentes.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a><span data-ttu-id="0b0c0-146">Usar el portal Microsoft 365 Defender para crear directivas Caja fuerte vínculos</span><span class="sxs-lookup"><span data-stu-id="0b0c0-146">Use the Microsoft 365 Defender portal to create Safe Links policies</span></span>

<span data-ttu-id="0b0c0-147">La creación de una directiva Caja fuerte links personalizada en el portal de Microsoft 365 Defender crea la regla de vínculos seguros y la directiva de vínculos seguros asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-147">Creating a custom Safe Links policy in the Microsoft 365 Defender portal creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="0b0c0-148">En el portal Microsoft 365 Defender, vaya **a Directivas &** de directivas de amenazas sección Directivas \>  \> **de** amenazas \> **Caja fuerte Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-148">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="0b0c0-149">En la **página Caja fuerte,** haga clic ![ en Crear icono ](../../media/m365-cc-sc-create-icon.png) **Crear**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-149">On the **Safe Links** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="0b0c0-150">Se **abrirá el Asistente para Caja fuerte de directivas de nuevos** vínculos.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="0b0c0-151">En la **página Nombre de la directiva,** configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="0b0c0-152">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="0b0c0-153">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="0b0c0-154">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0b0c0-155">En la **página Usuarios y dominios** que aparece, identifique los destinatarios internos a los que se aplica la directiva (condiciones de destinatario):</span><span class="sxs-lookup"><span data-stu-id="0b0c0-155">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="0b0c0-156">**Usuarios**: los buzones, usuarios de correo o contactos de correo especificados de su organización.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="0b0c0-157">**Grupos**: los grupos de distribución, los grupos de seguridad habilitados para correo electrónico o los Grupos de Microsoft 365 especificados de la organización.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="0b0c0-158">**Dominios**: todos los destinatarios de los [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados en la organización.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="0b0c0-159">Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="0b0c0-160">Repita este proceso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="0b0c0-161">Para quitar un valor existente, haga clic en Quitar</span><span class="sxs-lookup"><span data-stu-id="0b0c0-161">To remove an existing value, click remove</span></span> ![Icono de quitar](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="0b0c0-163">junto al valor.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-163">next to the value.</span></span>

   <span data-ttu-id="0b0c0-164">Para los usuarios o grupos, puede usar la mayoría de los identificadores (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de cuenta, etc.), pero el nombre para mostrar correspondiente se muestra en los resultados.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="0b0c0-165">Para los usuarios, escriba un asterisco (\*) para ver todos los valores disponibles.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="0b0c0-166">Varios valores en la misma condición usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="0b0c0-167">Hay diferentes condiciones que usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="0b0c0-168">**Excluir estos usuarios,** grupos y dominios: para agregar excepciones para los destinatarios internos a los que se aplica la directiva (excepciones de destinatarios), seleccione esta opción y configure las excepciones.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recipient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="0b0c0-169">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="0b0c0-170">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0b0c0-171">En la **página Configuración de** protección que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-171">On the **Protection settings** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="0b0c0-172">**Seleccione la acción para direcciones** URL potencialmente  malintencionadas desconocidas en mensajes: seleccione Activar para habilitar la protección de vínculos de Caja fuerte para vínculos en mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-172">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span> <span data-ttu-id="0b0c0-173">Si activa esta configuración, estará disponible la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-173">If you turn this setting on, the following settings are available:</span></span>
     - <span data-ttu-id="0b0c0-174">**Aplicar análisis de direcciones URL** en tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos: seleccione esta opción para habilitar el examen en tiempo real de vínculos en mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-174">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this option to enable real-time scanning of links in email messages.</span></span> <span data-ttu-id="0b0c0-175">Si activa esta opción en la siguiente configuración, estará disponible:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-175">If you turn this setting on the following setting is available:</span></span>
       - <span data-ttu-id="0b0c0-176">**Espere a que se** complete el examen de direcciones URL antes de entregar el mensaje: seleccione esta opción para esperar a que se complete el examen de direcciones URL en tiempo real antes de entregar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-176">**Wait for URL scanning to complete before delivering the message**: Select this option to wait for real-time URL scanning to complete before delivering the message.</span></span>
     - <span data-ttu-id="0b0c0-177">**Aplicar Caja fuerte vínculos** a mensajes de correo electrónico enviados dentro de la organización: seleccione esta opción para aplicar la directiva de vínculos de Caja fuerte a los mensajes entre remitentes internos y destinatarios internos.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-177">**Apply Safe Links to email messages sent within the organization**: Select this option to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>
   - <span data-ttu-id="0b0c0-178">**Seleccione la acción para direcciones** URL desconocidas o  potencialmente malintencionadas dentro de Microsoft Teams : Seleccione Activar para habilitar la protección de vínculos de Caja fuerte para vínculos de Teams.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-178">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>
   - <span data-ttu-id="0b0c0-179">**No realizar un seguimiento de los clics del** usuario: deje esta configuración sin elegir para habilitar los clics de usuario de seguimiento en las direcciones URL de los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-179">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>
   - <span data-ttu-id="0b0c0-180">**No permitir que los usuarios hagan clic en** la dirección URL original: seleccione esta opción para impedir que los usuarios hagan clic en la dirección URL original en las páginas de [advertencia.](safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="0b0c0-180">**Do not allow users to click through to original URL**: Select this option to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>
   - <span data-ttu-id="0b0c0-181">**No vuelva a escribir las** siguientes direcciones URL: permite obtener acceso a las direcciones URL especificadas que, de lo contrario, se bloquearían mediante Caja fuerte vínculos.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-181">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="0b0c0-182">En el cuadro, escriba la dirección URL o el valor que desee y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-182">In the box, type the URL or value that you want, and then click **Add**.</span></span> <span data-ttu-id="0b0c0-183">Repita este paso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-183">Repeat this step as many times as necessary.</span></span>

     <span data-ttu-id="0b0c0-184">Para quitar una entrada existente, haga clic en</span><span class="sxs-lookup"><span data-stu-id="0b0c0-184">To remove an existing entry, click</span></span> ![Icono de quitar](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="0b0c0-186">junto a la entrada.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-186">next to the entry.</span></span>

     <span data-ttu-id="0b0c0-187">Para obtener sintaxis de entrada, vea Sintaxis de entrada para la lista "No volver a [escribir las siguientes direcciones URL".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="0b0c0-187">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="0b0c0-188">Para obtener información detallada acerca de esta configuración, consulte [Caja fuerte links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and Caja fuerte Links settings for [Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-188">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="0b0c0-189">Para obtener más información sobre los valores recomendados para la configuración de directivas estándar y estricta, consulte [Caja fuerte configuración de directiva de vínculos](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-189">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="0b0c0-190">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-190">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="0b0c0-191">En la **página Notificación** que aparece, seleccione uno de los siguientes valores para ¿Cómo desea notificar a **los usuarios?**:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-191">On the **Notification** page that appears, select one of the following values for **How would you like to notify your users?**:</span></span>
   - <span data-ttu-id="0b0c0-192">**Usar el texto de notificación predeterminado**</span><span class="sxs-lookup"><span data-stu-id="0b0c0-192">**Use the default notification text**</span></span>
   - <span data-ttu-id="0b0c0-193">**Usar texto de notificación** personalizado: si selecciona este valor (la longitud no puede superar los 200 caracteres), aparecerá la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-193">**Use custom notification text**: If you select this value (the length cannot exceed 200 characters), the following settings appear:</span></span>
     - <span data-ttu-id="0b0c0-194">**Usar Traductor de Microsoft para la localización automática**</span><span class="sxs-lookup"><span data-stu-id="0b0c0-194">**Use Microsoft Translator for automatic localization**</span></span>
     - <span data-ttu-id="0b0c0-195">**Texto de notificación personalizado:** escriba el texto de notificación personalizado en este cuadro.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-195">**Custom notification text**: Enter the custom notification text in this box.</span></span>

   <span data-ttu-id="0b0c0-196">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-196">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="0b0c0-197">En la página **Revisar** que aparece, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-197">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="0b0c0-198">Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-198">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="0b0c0-199">También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-199">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="0b0c0-200">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-200">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="0b0c0-201">En la página de confirmación que aparece, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-201">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a><span data-ttu-id="0b0c0-202">Usar el portal de Microsoft 365 Defender para ver directivas Caja fuerte vínculos</span><span class="sxs-lookup"><span data-stu-id="0b0c0-202">Use the Microsoft 365 Defender portal to view Safe Links policies</span></span>

1. <span data-ttu-id="0b0c0-203">En el portal Microsoft 365 Defender, vaya **a Directivas &** de directivas de amenazas sección Directivas \>  \> **de** amenazas \> **Caja fuerte Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-203">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="0b0c0-204">En la **página Caja fuerte vínculos,** se muestran las siguientes propiedades en la lista de directivas Caja fuerte vínculos:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-204">On the **Safe Links** page, the following properties are displayed in the list of Safe Links policies:</span></span>
   - <span data-ttu-id="0b0c0-205">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="0b0c0-205">**Name**</span></span>
   - <span data-ttu-id="0b0c0-206">**Estado**</span><span class="sxs-lookup"><span data-stu-id="0b0c0-206">**Status**</span></span>
   - <span data-ttu-id="0b0c0-207">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="0b0c0-207">**Priority**</span></span>

3. <span data-ttu-id="0b0c0-208">Al seleccionar una directiva haciendo clic en el nombre, la configuración de la directiva se muestra en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-208">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a><span data-ttu-id="0b0c0-209">Usar el portal Microsoft 365 Defender para modificar las directivas Caja fuerte vínculos</span><span class="sxs-lookup"><span data-stu-id="0b0c0-209">Use the Microsoft 365 Defender portal to modify Safe Links policies</span></span>

1. <span data-ttu-id="0b0c0-210">En el portal Microsoft 365 Defender, vaya **a Directivas &** de directivas de amenazas sección Directivas \>  \> **de** amenazas \> **Caja fuerte Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-210">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="0b0c0-211">En la **Caja fuerte vínculos,** seleccione una directiva de la lista haciendo clic en el nombre.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-211">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="0b0c0-212">En el control flotante de detalles de la directiva que aparece, seleccione **Editar** en cada sección para modificar la configuración dentro de la sección.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-212">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="0b0c0-213">Para obtener más información acerca de la configuración, vea la sección anterior Use [the Microsoft 365 Defender portal to create Caja fuerte Links policies](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) en este artículo.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-213">For more information about the settings, see the previous [Use the Microsoft 365 Defender portal to create Safe Links policies](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) section in this article.</span></span>  

<span data-ttu-id="0b0c0-214">Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la directiva, consulte las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-214">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="0b0c0-215">Habilitar o deshabilitar directivas Caja fuerte vínculos</span><span class="sxs-lookup"><span data-stu-id="0b0c0-215">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="0b0c0-216">En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  \>  \> **Caja fuerte vínculos**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-216">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="0b0c0-217">En la **Caja fuerte vínculos,** seleccione una directiva de la lista haciendo clic en el nombre.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-217">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="0b0c0-218">En la parte superior del control flotante de detalles de la directiva que aparece, verá uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-218">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="0b0c0-219">**Directiva desactivada**: para activar la directiva, haga clic en el ![Icono Activar](../../media/m365-cc-sc-turn-on-off-icon.png) **Activar**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-219">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="0b0c0-220">**Directiva activada**: Para desactivar la directiva, haga clic en el ![Icono desactivar](../../media/m365-cc-sc-turn-on-off-icon.png) y **Desactivar**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-220">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="0b0c0-221">En el cuadro de diálogo de confirmación que aparece, haga clic **Activar** o **Desactivar**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-221">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="0b0c0-222">Haga clic en **Cerrar** en el control flotante de detalles de la directiva.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-222">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="0b0c0-223">De nuevo en la página principal de la directiva, el valor **Estado** de la directiva estará **Activado** o **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-223">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="0b0c0-224">Establecer la prioridad de las directivas Caja fuerte vínculos</span><span class="sxs-lookup"><span data-stu-id="0b0c0-224">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="0b0c0-225">De forma predeterminada, Caja fuerte a los vínculos se les da una prioridad que se basa en el orden en que se crearon (las directivas más recientes son de menor prioridad que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-225">By default, Safe Links are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="0b0c0-226">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-226">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="0b0c0-227">Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-227">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="0b0c0-228">Para cambiar la prioridad de una directiva, haga clic en **Aumentar la prioridad** o en **Reducir la prioridad** en las propiedades de la directiva (no se puede modificar directamente el número de **Prioridad** en el portal de Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-228">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="0b0c0-229">Cambiar la prioridad de una directiva solo tiene sentido si tiene varias directivas.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-229">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

<span data-ttu-id="0b0c0-230">**Nota**:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-230">**Note**:</span></span>

- <span data-ttu-id="0b0c0-231">En el portal Microsoft 365 Defender, solo puede cambiar la prioridad de la directiva de vínculos de Caja fuerte después de crearla.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-231">In the Microsoft 365 Defender portal, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="0b0c0-232">En PowerShell, puede invalidar la prioridad predeterminada al crear la regla de vínculos seguros (lo que puede afectar a la prioridad de las reglas existentes).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-232">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="0b0c0-233">Caja fuerte Las directivas de vínculos se procesan en el orden en que se muestran (la primera directiva tiene el **valor de** prioridad 0).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-233">Safe Links policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="0b0c0-234">Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-234">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

1. <span data-ttu-id="0b0c0-235">En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  \>  \> **Caja fuerte vínculos**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-235">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="0b0c0-236">En la **Caja fuerte vínculos,** seleccione una directiva de la lista haciendo clic en el nombre.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-236">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="0b0c0-237">En la parte superior del control flotante de detalles de la directiva que aparece, verá **Aumentar la prioridad** o **Disminuir la prioridad** en función del valor de prioridad actual y del número de directivas personalizadas:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-237">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="0b0c0-238">La directiva con el **valor de prioridad** **0** solo tiene disponible la **opción Disminuir** prioridad.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-238">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="0b0c0-239">La directiva con el valor **de prioridad** más bajo (por ejemplo, **3**) solo tiene disponible **la opción Aumentar** prioridad.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-239">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="0b0c0-240">Si tiene tres o más directivas, las directivas entre los valores de prioridad más alta y más baja tienen disponibles las opciones **Aumentar** prioridad y **Disminuir** prioridad.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-240">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="0b0c0-241">Haga clic en el ![Icono Aumentar la prioridad](../../media/m365-cc-sc-increase-icon.png) **Aumentar la prioridad** o en el ![Icono Disminuir la prioridad](../../media/m365-cc-sc-decrease-icon.png) **Reducir la prioridad** para cambiar el valor de **Prioridad**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-241">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="0b0c0-242">Cuando haya terminado, haga clic en **Cerrar** en el control flotante de detalles de la directiva.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-242">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a><span data-ttu-id="0b0c0-243">Usar el portal Microsoft 365 Defender para quitar directivas Caja fuerte vínculos</span><span class="sxs-lookup"><span data-stu-id="0b0c0-243">Use the Microsoft 365 Defender portal to remove Safe Links policies</span></span>

1. <span data-ttu-id="0b0c0-244">En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  \>  \> **Caja fuerte vínculos**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-244">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="0b0c0-245">En la **Caja fuerte vínculos,** seleccione una directiva de la lista haciendo clic en el nombre.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-245">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span> <span data-ttu-id="0b0c0-246">En la parte superior del control flotante de detalles de la directiva que aparece, haga clic en el ![Icono Más acciones](../../media/m365-cc-sc-more-actions-icon.png) **Más acciones** \> ![Icono Eliminar directiva](../../media/m365-cc-sc-delete-icon.png) **Eliminar directiva**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-246">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="0b0c0-247">En el cuadro de diálogo de confirmación que aparece, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-247">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="0b0c0-248">Usar Exchange Online PowerShell o PowerShell independiente de EOP para configurar directivas Caja fuerte vínculos</span><span class="sxs-lookup"><span data-stu-id="0b0c0-248">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="0b0c0-249">Como se describió anteriormente, una directiva Caja fuerte links consiste en una directiva de vínculos seguros y una regla de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-249">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="0b0c0-250">En PowerShell, la diferencia entre las directivas de vínculos seguros y las reglas de vínculos seguros es aparente.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-250">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="0b0c0-251">Las directivas de vínculos seguros se administran mediante los cmdlets **\* -SafeLinksPolicy** y se administran reglas de vínculos seguros mediante los cmdlets **\* -SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="0b0c0-251">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="0b0c0-252">En PowerShell, primero se crea la directiva de vínculos seguros y, a continuación, se crea la regla de vínculos seguros que identifica la directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-252">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="0b0c0-253">En PowerShell, se modifica la configuración de la directiva de vínculos seguros y la regla de vínculos seguros por separado.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-253">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="0b0c0-254">Al quitar una directiva de vínculos seguros de PowerShell, la regla de vínculos seguros correspondiente no se quita automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-254">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="0b0c0-255">Usar PowerShell para crear directivas Caja fuerte vínculos</span><span class="sxs-lookup"><span data-stu-id="0b0c0-255">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="0b0c0-256">Crear una directiva Caja fuerte vínculos en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-256">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="0b0c0-257">Cree la directiva de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-257">Create the safe links policy.</span></span>
2. <span data-ttu-id="0b0c0-258">Cree la regla de vínculos seguros que especifica la directiva de vínculos seguros a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-258">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="0b0c0-259">Puede crear una nueva regla de vínculos seguros y asignarle una directiva de vínculos seguros existente y sin asociar.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-259">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="0b0c0-260">Una regla de vínculos seguros no se puede asociar a más de una directiva de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-260">A safe links rule can't be associated with more than one safe links policy.</span></span>
>
> - <span data-ttu-id="0b0c0-261">Puede configurar las siguientes opciones en nuevas directivas de vínculos seguros en PowerShell que no estén disponibles en el portal de Microsoft 365 Defender hasta después de crear la directiva:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-261">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
>   - <span data-ttu-id="0b0c0-262">Cree la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="0b0c0-262">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="0b0c0-263">Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_ ) en el cmdlet **New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="0b0c0-263">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
>
> - <span data-ttu-id="0b0c0-264">Una nueva directiva de vínculos seguros que cree en PowerShell no será visible en el portal de Microsoft 365 Defender hasta que asigne la directiva a una regla de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-264">A new safe links policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="0b0c0-265">Paso 1: Usar PowerShell para crear una directiva de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="0b0c0-265">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="0b0c0-266">Para crear una directiva de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-266">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - <span data-ttu-id="0b0c0-267">Para obtener más información acerca de la sintaxis de entrada que se va a usar para el parámetro _DoNotRewriteUrls,_ vea [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-267">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
>
> - <span data-ttu-id="0b0c0-268">Para obtener una sintaxis adicional que puede usar para el parámetro _DoNotRewriteUrls_ al modificar las directivas de vínculos seguros existentes mediante el cmdlet **Set-SafeLinksPolicy,** vea la sección Usar [PowerShell](#use-powershell-to-modify-safe-links-policies) para modificar directivas de vínculos seguros más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-268">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="0b0c0-269">En este ejemplo se crea una directiva de vínculos seguros denominada Contoso All con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-269">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="0b0c0-270">Activa la detección y reescritura de direcciones URL en los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-270">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="0b0c0-271">Activa el examen de direcciones URL en Teams (solo vista previa de TAP).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-271">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="0b0c0-272">Activa el examen en tiempo real de las direcciones URL en las que se hace clic, incluidos los vínculos en los que se hace clic que apuntan a archivos.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-272">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="0b0c0-273">Espere a que se complete el examen de direcciones URL antes de entregar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-273">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="0b0c0-274">Activa la detección y reescritura de direcciones URL para los mensajes internos.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-274">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="0b0c0-275">Realizar un seguimiento de los clics de usuario relacionados con la protección de vínculos de Caja fuerte (no estamos usando el parámetro _DoNotTrackUserClicks_ y el valor predeterminado es $false, lo que significa que se realiza un seguimiento de los clics del usuario).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-275">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="0b0c0-276">No permitir que los usuarios hagan clic en la dirección URL original.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-276">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="0b0c0-277">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-277">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="0b0c0-278">Paso 2: Usar PowerShell para crear una regla de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="0b0c0-278">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="0b0c0-279">Para crear una regla de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-279">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="0b0c0-280">En este ejemplo se crea una regla de vínculos seguros denominada Contoso All con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-280">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="0b0c0-281">La regla está asociada con la directiva de vínculos seguros denominada Contoso All.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-281">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="0b0c0-282">La regla se aplica a todos los destinatarios del contoso.com dominio.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-282">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="0b0c0-283">Dado que no estamos usando el parámetro _Priority,_ se usa la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-283">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="0b0c0-284">La regla está habilitada (no estamos usando el parámetro _Enabled_ y el valor predeterminado es `$true` ).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-284">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="0b0c0-285">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-285">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="0b0c0-286">Usar PowerShell para ver directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="0b0c0-286">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="0b0c0-287">Para ver las directivas de vínculos seguros existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-287">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0b0c0-288">En este ejemplo se devuelve una lista resumida de todas las directivas de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-288">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="0b0c0-289">En este ejemplo se devuelve información detallada sobre la directiva de vínculos seguros denominada Ejecutivos de Contoso.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-289">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="0b0c0-290">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-290">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="0b0c0-291">Usar PowerShell para ver reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="0b0c0-291">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="0b0c0-292">Para ver las reglas de vínculos seguros existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-292">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0b0c0-293">En este ejemplo se devuelve una lista resumida de todas las reglas de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-293">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="0b0c0-294">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-294">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="0b0c0-295">En este ejemplo se devuelve información detallada para la regla de vínculos seguros denominada Ejecutivos de Contoso.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-295">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="0b0c0-296">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-296">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="0b0c0-297">Usar PowerShell para modificar directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="0b0c0-297">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="0b0c0-298">No puede cambiar el nombre de una directiva de vínculos seguros en PowerShell (el cmdlet **Set-SafeLinksPolicy** no tiene ningún _parámetro Name)._</span><span class="sxs-lookup"><span data-stu-id="0b0c0-298">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="0b0c0-299">Al cambiar el nombre de una directiva Caja fuerte vínculos en el portal de Microsoft 365 Defender, solo se cambia el nombre de la regla de vínculos _seguros_.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-299">When you rename a Safe Links policy in the Microsoft 365 Defender portal, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="0b0c0-300">La única consideración adicional para modificar directivas de vínculos seguros en PowerShell es la sintaxis disponible para el parámetro _DoNotRewriteUrls_ (la lista ["No volver](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)a escribir las siguientes direcciones URL" ):</span><span class="sxs-lookup"><span data-stu-id="0b0c0-300">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="0b0c0-301">Para agregar valores que reemplacen las entradas existentes, use la sintaxis siguiente: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="0b0c0-301">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="0b0c0-302">Para agregar o quitar valores sin afectar a otras entradas existentes, use la sintaxis siguiente: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="0b0c0-302">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="0b0c0-303">De lo contrario, la misma configuración está disponible al crear una directiva de vínculos seguros como se describe en el paso [1: Usar PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) para crear una directiva de vínculos seguros anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-303">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="0b0c0-304">Para modificar una directiva de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-304">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="0b0c0-305">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-305">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="0b0c0-306">Usar PowerShell para modificar reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="0b0c0-306">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="0b0c0-307">La única configuración que no está disponible al modificar una regla de vínculos seguros en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-307">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="0b0c0-308">Para habilitar o deshabilitar las reglas de vínculos seguros existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-308">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="0b0c0-309">De lo contrario, la misma configuración está disponible al crear una regla tal como se describe en el paso [2: Usar PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) para crear una regla de vínculos seguros anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-309">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="0b0c0-310">Para modificar una regla de vínculos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-310">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="0b0c0-311">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-311">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="0b0c0-312">Usar PowerShell para habilitar o deshabilitar reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="0b0c0-312">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="0b0c0-313">Habilitar o deshabilitar una regla de vínculos seguros en PowerShell habilita o deshabilita toda la directiva de vínculos de Caja fuerte (la regla de vínculos seguros y la directiva de vínculos seguros asignada).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-313">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="0b0c0-314">Para habilitar o deshabilitar una regla de vínculos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-314">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="0b0c0-315">En este ejemplo se deshabilita la regla de vínculos seguros denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-315">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="0b0c0-316">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-316">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="0b0c0-317">Para obtener información detallada acerca de la sintaxis y los parámetros, vea [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) y [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-317">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="0b0c0-318">Usar PowerShell para establecer la prioridad de las reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="0b0c0-318">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="0b0c0-p131">El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-p131">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="0b0c0-324">Para establecer la prioridad de una regla de vínculos seguros en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-324">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="0b0c0-p132">En el ejemplo siguiente, la prioridad de la regla denominada "Marketing Department" se establece en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-p132">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="0b0c0-327">Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-SafeLinksRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-327">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="0b0c0-328">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-328">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="0b0c0-329">Usar PowerShell para quitar directivas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="0b0c0-329">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="0b0c0-330">Cuando usa PowerShell para quitar una directiva de vínculos seguros, no se quita la regla de vínculos seguros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-330">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="0b0c0-331">Para quitar una directiva de vínculos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-331">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="0b0c0-332">En este ejemplo se quita la directiva de vínculos seguros denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-332">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="0b0c0-333">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-333">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="0b0c0-334">Usar PowerShell para quitar reglas de vínculos seguros</span><span class="sxs-lookup"><span data-stu-id="0b0c0-334">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="0b0c0-335">Cuando usa PowerShell para quitar una regla de vínculos seguros, no se quita la directiva de vínculos seguros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-335">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="0b0c0-336">Para quitar una regla de vínculos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-336">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="0b0c0-337">En este ejemplo se quita la regla de vínculos seguros denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-337">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="0b0c0-338">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-338">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="0b0c0-339">Para comprobar que los Caja fuerte están analizando mensajes, compruebe los informes de Microsoft Defender disponibles Office 365 datos.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-339">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="0b0c0-340">Para obtener más información, vea [View reports for Defender for Office 365](view-reports-for-mdo.md) and Use Explorer in the Microsoft 365 Defender [portal](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="0b0c0-340">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0b0c0-341">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="0b0c0-341">How do you know these procedures worked?</span></span>

<span data-ttu-id="0b0c0-342">Para comprobar que ha creado, modificado o quitado correctamente las directivas de vínculos Caja fuerte, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-342">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="0b0c0-343">En el portal Microsoft 365 Defender, vaya **a Directivas & reglas** de amenazas \> **Caja fuerte** \> **vínculos**.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-343">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe Links**.</span></span> <span data-ttu-id="0b0c0-344">Compruebe la lista de directivas, sus **valores de** estado y sus **valores de** prioridad.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-344">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="0b0c0-345">Para ver más detalles, seleccione la directiva de la lista y vea los detalles en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="0b0c0-345">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="0b0c0-346">En Exchange Online PowerShell o Exchange Online Protection PowerShell, reemplace por el nombre de la directiva o regla, ejecute el siguiente comando y compruebe \<Name\> la configuración:</span><span class="sxs-lookup"><span data-stu-id="0b0c0-346">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
