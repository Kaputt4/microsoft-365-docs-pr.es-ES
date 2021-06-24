---
title: Configurar directivas Caja fuerte datos adjuntos en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo definir directivas Caja fuerte datos adjuntos para proteger su organización de archivos malintencionados en el correo electrónico.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e516a16ff28c762e154fd908312df65ea48699bc
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108228"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="a338b-103">Configurar directivas Caja fuerte datos adjuntos en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a338b-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a338b-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="a338b-104">**Applies to**</span></span>
- [<span data-ttu-id="a338b-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a338b-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a338b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a338b-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="a338b-107">Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](whats-new-in-defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="a338b-107">This article is intended for business customers who have [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md).</span></span> <span data-ttu-id="a338b-108">Si es un usuario principal que busca información sobre el examen de datos adjuntos en Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="a338b-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="a338b-109">Caja fuerte Los datos adjuntos son una característica de [Microsoft Defender](whats-new-in-defender-for-office-365.md) para Office 365 que usa un entorno virtual para comprobar los datos adjuntos de los mensajes de correo electrónico entrantes después de haber sido examinados por la protección antimalware en [Exchange Online Protection (EOP),](anti-malware-protection.md)pero antes de la entrega a los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="a338b-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="a338b-110">Para obtener más información, [vea Caja fuerte datos adjuntos de Microsoft Defender para Office 365](safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="a338b-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](safe-attachments.md).</span></span>

<span data-ttu-id="a338b-111">No hay ninguna directiva de datos adjuntos integrada o predeterminada Caja fuerte datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="a338b-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="a338b-112">Para obtener Caja fuerte análisis de datos adjuntos de mensajes de correo electrónico, debe crear una o más directivas de datos adjuntos Caja fuerte como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="a338b-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="a338b-113">Puede configurar directivas de datos adjuntos de Caja fuerte en el portal de Microsoft 365 Defender o en PowerShell (PowerShell de Exchange Online para organizaciones de Microsoft 365 elegibles con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de Exchange Online, pero con Defender para suscripciones de complemento de Office 365).</span><span class="sxs-lookup"><span data-stu-id="a338b-113">You can configure Safe Attachments policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="a338b-114">Los elementos básicos de una directiva Caja fuerte datos adjuntos son:</span><span class="sxs-lookup"><span data-stu-id="a338b-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="a338b-115">La **directiva** de datos adjuntos seguros: especifica las acciones para detecciones de malware desconocidas, si se envían mensajes con datos adjuntos de malware a una dirección de correo electrónico especificada y si se entregan mensajes si no se puede completar el examen de datos adjuntos Caja fuerte.</span><span class="sxs-lookup"><span data-stu-id="a338b-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="a338b-116">**La regla de datos adjuntos seguros:** especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva).</span><span class="sxs-lookup"><span data-stu-id="a338b-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="a338b-117">La diferencia entre estos dos elementos no es obvia al administrar las directivas Caja fuerte datos adjuntos en el portal Microsoft 365 Defender datos adjuntos:</span><span class="sxs-lookup"><span data-stu-id="a338b-117">The difference between these two elements isn't obvious when you manage Safe Attachments policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="a338b-118">Al crear una directiva Caja fuerte datos adjuntos, en realidad está creando una regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="a338b-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="a338b-119">Al modificar una directiva Caja fuerte datos adjuntos, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada y los filtros de destinatarios modifican la regla de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="a338b-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="a338b-120">Todas las demás opciones modifican la directiva de datos adjuntos seguros asociada.</span><span class="sxs-lookup"><span data-stu-id="a338b-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="a338b-121">Al quitar una directiva Caja fuerte datos adjuntos, se quitan la regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asociada.</span><span class="sxs-lookup"><span data-stu-id="a338b-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="a338b-122">En Exchange Online PowerShell o en un EOP PowerShell independiente, usted administra la directiva y la regla por separado.</span><span class="sxs-lookup"><span data-stu-id="a338b-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="a338b-123">Para obtener más información, vea la sección [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Caja fuerte Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="a338b-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="a338b-124">En el área de configuración global de Caja fuerte datos adjuntos, se configuran características que no dependen de Caja fuerte de datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="a338b-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="a338b-125">Para obtener instrucciones, vea [Turn on Caja fuerte Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and Caja fuerte Documents in [Microsoft 365 E5](safe-docs.md).</span><span class="sxs-lookup"><span data-stu-id="a338b-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a338b-126">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="a338b-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a338b-127">Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="a338b-127">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="a338b-128">Para ir directamente a la **página Caja fuerte datos adjuntos,** use <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="a338b-128">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="a338b-129">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a338b-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a338b-130">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="a338b-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a338b-131">Necesita permisos para poder realizar los procedimientos descritos en este artículo:</span><span class="sxs-lookup"><span data-stu-id="a338b-131">You need permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a338b-132">Para crear, modificar y eliminar directivas de datos adjuntos de  Caja fuerte,  debe ser miembro de los grupos de roles  Administración de la organización o Administrador de seguridad en el **portal** de Microsoft 365 Defender y miembro del grupo de roles Administración de la organización en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a338b-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="a338b-133">Para obtener acceso de solo lectura a Caja fuerte de datos adjuntos,  debe ser miembro de los grupos de roles Lector **global** o Lector de seguridad en el portal de Microsoft 365 Defender datos.</span><span class="sxs-lookup"><span data-stu-id="a338b-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Microsoft 365 Defender portal.</span></span>

  <span data-ttu-id="a338b-134">Para obtener más información, vea [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="a338b-134">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="a338b-135">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="a338b-135">**Notes**:</span></span>

  - <span data-ttu-id="a338b-136">Agregar usuarios al rol Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el _portal_ de Microsoft 365 Defender y permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a338b-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a338b-137">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a338b-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="a338b-138">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="a338b-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="a338b-139">Para obtener la configuración recomendada para las Caja fuerte de datos adjuntos, [vea Caja fuerte de datos adjuntos](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="a338b-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="a338b-140">Permitir hasta 30 minutos para que se aplique una directiva nueva o actualizada.</span><span class="sxs-lookup"><span data-stu-id="a338b-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a><span data-ttu-id="a338b-141">Usar el portal Microsoft 365 Defender para crear directivas Caja fuerte datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="a338b-141">Use the Microsoft 365 Defender portal to create Safe Attachments policies</span></span>

<span data-ttu-id="a338b-142">La creación de una directiva Caja fuerte datos adjuntos personalizada en el portal de Microsoft 365 Defender crea la regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="a338b-142">Creating a custom Safe Attachments policy in the Microsoft 365 Defender portal creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="a338b-143">En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  Caja fuerte \>  \> **datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="a338b-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="a338b-144">En la **página Caja fuerte datos adjuntos,** haga clic en Crear ![ icono ](../../media/m365-cc-sc-create-icon.png) **Crear**.</span><span class="sxs-lookup"><span data-stu-id="a338b-144">On the **Safe Attachments** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="a338b-145">Se abrirá el asistente para directivas.</span><span class="sxs-lookup"><span data-stu-id="a338b-145">The policy wizard opens.</span></span> <span data-ttu-id="a338b-146">En la **página Nombre de la directiva,** configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a338b-146">On the **Name your policy** page, configure the following settings:</span></span>
   - <span data-ttu-id="a338b-147">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="a338b-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="a338b-148">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="a338b-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="a338b-149">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a338b-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a338b-150">En la **página Usuarios y dominios** que aparece, identifique los destinatarios internos a los que se aplica la directiva (condiciones de destinatario):</span><span class="sxs-lookup"><span data-stu-id="a338b-150">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="a338b-151">**Usuarios**: los buzones, usuarios de correo o contactos de correo especificados de su organización.</span><span class="sxs-lookup"><span data-stu-id="a338b-151">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="a338b-152">**Grupos**: los grupos de distribución, los grupos de seguridad habilitados para correo electrónico o los Grupos de Microsoft 365 especificados de la organización.</span><span class="sxs-lookup"><span data-stu-id="a338b-152">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="a338b-153">**Dominios**: todos los destinatarios de los [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados en la organización.</span><span class="sxs-lookup"><span data-stu-id="a338b-153">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="a338b-154">Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados.</span><span class="sxs-lookup"><span data-stu-id="a338b-154">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="a338b-155">Repita este proceso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a338b-155">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="a338b-156">Para quitar un valor existente, haga clic en Quitar</span><span class="sxs-lookup"><span data-stu-id="a338b-156">To remove an existing value, click remove</span></span> ![Icono de quitar](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="a338b-158">junto al valor.</span><span class="sxs-lookup"><span data-stu-id="a338b-158">next to the value.</span></span>

   <span data-ttu-id="a338b-159">Para los usuarios o grupos, puede usar la mayoría de los identificadores (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de cuenta, etc.), pero el nombre para mostrar correspondiente se muestra en los resultados.</span><span class="sxs-lookup"><span data-stu-id="a338b-159">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="a338b-160">Para los usuarios, escriba un asterisco (\*) para ver todos los valores disponibles.</span><span class="sxs-lookup"><span data-stu-id="a338b-160">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="a338b-161">Varios valores en la misma condición usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="a338b-161">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="a338b-162">Hay diferentes condiciones que usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="a338b-162">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="a338b-163">**Excluir estos usuarios, grupos y dominios**: para agregar excepciones a los destinatarios internos a los que se aplica la directiva (excepciones de destinatarios), seleccione esta opción y configure las excepciones.</span><span class="sxs-lookup"><span data-stu-id="a338b-163">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="a338b-164">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="a338b-164">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="a338b-165">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a338b-165">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a338b-166">En la **Configuración,** configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a338b-166">On the **Settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="a338b-167">**Caja fuerte datos adjuntos respuesta de malware desconocido:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a338b-167">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>
     - <span data-ttu-id="a338b-168">**Off**: Normalmente, no recomendamos este valor.</span><span class="sxs-lookup"><span data-stu-id="a338b-168">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="a338b-169">**Supervisar**</span><span class="sxs-lookup"><span data-stu-id="a338b-169">**Monitor**</span></span>
     - <span data-ttu-id="a338b-170">**Block:** este es el valor predeterminado y el valor recomendado en Directivas de seguridad predeterminadas estándar y [estrictas.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a338b-170">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="a338b-171">**Replace**</span><span class="sxs-lookup"><span data-stu-id="a338b-171">**Replace**</span></span>
     - <span data-ttu-id="a338b-172">**Entrega dinámica (característica de vista previa)**</span><span class="sxs-lookup"><span data-stu-id="a338b-172">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="a338b-173">Estos valores se explican en Caja fuerte [de directiva de datos adjuntos](safe-attachments.md#safe-attachments-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="a338b-173">These values are explained in [Safe Attachments policy settings](safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="a338b-174">Redirigir mensajes con datos adjuntos detectados: si selecciona Habilitar redireccionamiento, puede especificar una dirección de correo electrónico en el cuadro Enviar mensajes que contengan datos adjuntos **bloqueados,** supervisados o reemplazados en el cuadro dirección de correo electrónico especificada para enviar mensajes que contengan datos adjuntos de malware para su análisis e investigación.</span><span class="sxs-lookup"><span data-stu-id="a338b-174">**Redirect messages with detected attachments**: If you select **Enable redirect**, you can specify an email address in the **Send messages that contain blocked, monitored, or replaced attachments to the specified email address** box to send messages that contain malware attachments for analysis and investigation.</span></span>

     <span data-ttu-id="a338b-175">La recomendación para la configuración de directivas estándar y estricta es habilitar la redirección.</span><span class="sxs-lookup"><span data-stu-id="a338b-175">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="a338b-176">Para obtener más información, [vea Caja fuerte configuración de datos adjuntos](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="a338b-176">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="a338b-177">Aplicar la respuesta de detección de datos adjuntos de Caja fuerte si el examen no se puede completar (tiempo de espera o **errores):** la acción especificada por **Caja fuerte Attachments unknown malware response** se toma en mensajes incluso cuando no se puede completar el examen de datos adjuntos Caja fuerte.</span><span class="sxs-lookup"><span data-stu-id="a338b-177">**Apply the Safe Attachments detection response if scanning can't complete (timeout or errors)**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="a338b-178">Si seleccionó esta opción, seleccione siempre Habilitar redireccionamiento y especifique una dirección de correo electrónico para enviar mensajes que contengan datos adjuntos de malware. </span><span class="sxs-lookup"><span data-stu-id="a338b-178">If you selected this option, always select **Enable redirect** and specify an email address to send messages that contain malware attachments.</span></span> <span data-ttu-id="a338b-179">De lo contrario, los mensajes podrían perderse.</span><span class="sxs-lookup"><span data-stu-id="a338b-179">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="a338b-180">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a338b-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="a338b-181">En la página **Revisar** que aparece, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="a338b-181">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="a338b-182">Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección.</span><span class="sxs-lookup"><span data-stu-id="a338b-182">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="a338b-183">También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.</span><span class="sxs-lookup"><span data-stu-id="a338b-183">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="a338b-184">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="a338b-184">When you're finished, click **Submit**.</span></span>

7. <span data-ttu-id="a338b-185">En la página de confirmación que aparece, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="a338b-185">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a><span data-ttu-id="a338b-186">Usar el portal Microsoft 365 Defender para ver las directivas Caja fuerte datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="a338b-186">Use the Microsoft 365 Defender portal to view Safe Attachments policies</span></span>

1. <span data-ttu-id="a338b-187">En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  Caja fuerte \>  \> **datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="a338b-187">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="a338b-188">En la **Caja fuerte datos adjuntos,** las siguientes propiedades se muestran en la lista de directivas:</span><span class="sxs-lookup"><span data-stu-id="a338b-188">On the **Safe Attachments** page, the following properties are displayed in the list of policies:</span></span>
   - <span data-ttu-id="a338b-189">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="a338b-189">**Name**</span></span>
   - <span data-ttu-id="a338b-190">**Estado**</span><span class="sxs-lookup"><span data-stu-id="a338b-190">**Status**</span></span>
   - <span data-ttu-id="a338b-191">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="a338b-191">**Priority**</span></span>

3. <span data-ttu-id="a338b-192">Al seleccionar una directiva haciendo clic en el nombre, la configuración de la directiva se muestra en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="a338b-192">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a><span data-ttu-id="a338b-193">Usar el portal Microsoft 365 Defender para modificar las directivas Caja fuerte datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="a338b-193">Use the Microsoft 365 Defender portal to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="a338b-194">En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  Caja fuerte \>  \> **datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="a338b-194">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="a338b-195">En la **Caja fuerte datos adjuntos,** seleccione una directiva de la lista haciendo clic en el nombre.</span><span class="sxs-lookup"><span data-stu-id="a338b-195">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="a338b-196">En el control flotante de detalles de la directiva que aparece, seleccione **Editar** en cada sección para modificar la configuración dentro de la sección.</span><span class="sxs-lookup"><span data-stu-id="a338b-196">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="a338b-197">Para obtener más información acerca de la configuración, vea la sección Use [the Microsoft 365 Defender portal to create Caja fuerte Attachments policies](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) anterior en este artículo.</span><span class="sxs-lookup"><span data-stu-id="a338b-197">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create Safe Attachments policies](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) section earlier in this article.</span></span>  

<span data-ttu-id="a338b-198">Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la directiva, consulte las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="a338b-198">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="a338b-199">Habilitar o deshabilitar directivas Caja fuerte datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="a338b-199">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="a338b-200">En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  Caja fuerte \>  \> **datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="a338b-200">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="a338b-201">En la **Caja fuerte datos adjuntos,** seleccione una directiva de la lista haciendo clic en el nombre.</span><span class="sxs-lookup"><span data-stu-id="a338b-201">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="a338b-202">En la parte superior del control flotante de detalles de la directiva que aparece, verá uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a338b-202">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="a338b-203">**Directiva desactivada**: para activar la directiva, haga clic en el ![Icono Activar](../../media/m365-cc-sc-turn-on-off-icon.png) **Activar**.</span><span class="sxs-lookup"><span data-stu-id="a338b-203">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="a338b-204">**Directiva activada**: Para desactivar la directiva, haga clic en el ![Icono desactivar](../../media/m365-cc-sc-turn-on-off-icon.png) y **Desactivar**.</span><span class="sxs-lookup"><span data-stu-id="a338b-204">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="a338b-205">En el cuadro de diálogo de confirmación que aparece, haga clic **Activar** o **Desactivar**.</span><span class="sxs-lookup"><span data-stu-id="a338b-205">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="a338b-206">Haga clic en **Cerrar** en el control flotante de detalles de la directiva.</span><span class="sxs-lookup"><span data-stu-id="a338b-206">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="a338b-207">De nuevo en la página principal de la directiva, el valor **Estado** de la directiva estará **Activado** o **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="a338b-207">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="a338b-208">Establecer la prioridad de las directivas Caja fuerte datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="a338b-208">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="a338b-209">De forma predeterminada, Caja fuerte de datos adjuntos tienen una prioridad que se basa en el orden en que se crearon (las directivas más recientes son de menor prioridad que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="a338b-209">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="a338b-210">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="a338b-210">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="a338b-211">Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="a338b-211">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="a338b-212">Para obtener más información sobre el orden de prioridad y cómo se evalúan y aplican las distintas directivas, consulte [Orden y prioridad de la protección de correo electrónico](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="a338b-212">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="a338b-213">Caja fuerte Las directivas de datos adjuntos se muestran en el orden en que se procesan (la primera directiva tiene el **valor de** prioridad 0).</span><span class="sxs-lookup"><span data-stu-id="a338b-213">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="a338b-214">**Nota:** En el portal Microsoft 365 Defender, solo puede cambiar la prioridad de la directiva de datos adjuntos Caja fuerte después de crearla.</span><span class="sxs-lookup"><span data-stu-id="a338b-214">**Note**: In the Microsoft 365 Defender portal, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="a338b-215">En PowerShell, puede invalidar la prioridad predeterminada al crear la regla de datos adjuntos seguros (lo que puede afectar a la prioridad de las reglas existentes).</span><span class="sxs-lookup"><span data-stu-id="a338b-215">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="a338b-216">Para cambiar la prioridad de una directiva, haga clic en **Aumentar la prioridad** o en **Reducir la prioridad** en las propiedades de la directiva (no se puede modificar directamente el número de **Prioridad** en el portal de Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="a338b-216">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="a338b-217">Cambiar la prioridad de una directiva solo tiene sentido si tiene varias directivas.</span><span class="sxs-lookup"><span data-stu-id="a338b-217">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="a338b-218">En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  Caja fuerte \>  \> **datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="a338b-218">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="a338b-219">En la **Caja fuerte datos adjuntos,** seleccione una directiva de la lista haciendo clic en el nombre.</span><span class="sxs-lookup"><span data-stu-id="a338b-219">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="a338b-220">En la parte superior del menú desplegable de  detalles de  la directiva que aparece, verá Aumentar prioridad o Disminuir prioridad en función del valor de prioridad actual y el número de directivas:</span><span class="sxs-lookup"><span data-stu-id="a338b-220">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of policies:</span></span>
   - <span data-ttu-id="a338b-221">La directiva con el **valor de prioridad** **0** solo tiene disponible la **opción Disminuir** prioridad.</span><span class="sxs-lookup"><span data-stu-id="a338b-221">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="a338b-222">La directiva con el valor **de prioridad** más bajo (por ejemplo, **3**) solo tiene disponible **la opción Aumentar** prioridad.</span><span class="sxs-lookup"><span data-stu-id="a338b-222">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="a338b-223">Si tiene tres o más directivas, las directivas entre los valores de prioridad más alta y más baja tienen disponibles las opciones **Aumentar** prioridad y **Disminuir** prioridad.</span><span class="sxs-lookup"><span data-stu-id="a338b-223">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="a338b-224">Haga clic en el ![Icono Aumentar la prioridad](../../media/m365-cc-sc-increase-icon.png) **Aumentar la prioridad** o en el ![Icono Disminuir la prioridad](../../media/m365-cc-sc-decrease-icon.png) **Reducir la prioridad** para cambiar el valor de **Prioridad**.</span><span class="sxs-lookup"><span data-stu-id="a338b-224">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="a338b-225">Cuando haya terminado, haga clic en **Cerrar** en el control flotante de detalles de la directiva.</span><span class="sxs-lookup"><span data-stu-id="a338b-225">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a><span data-ttu-id="a338b-226">Usar el portal Microsoft 365 Defender para quitar directivas Caja fuerte datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="a338b-226">Use the Microsoft 365 Defender portal to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="a338b-227">En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  Caja fuerte \>  \> **datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="a338b-227">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="a338b-228">En la **Caja fuerte datos adjuntos,** seleccione una directiva personalizada de la lista haciendo clic en el nombre de la directiva.</span><span class="sxs-lookup"><span data-stu-id="a338b-228">On the **Safe Attachments** page, select a custom policy from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="a338b-229">En la parte superior del control flotante de detalles de la directiva que aparece, haga clic en el ![Icono Más acciones](../../media/m365-cc-sc-more-actions-icon.png) **Más acciones** \> ![Icono Eliminar directiva](../../media/m365-cc-sc-delete-icon.png) **Eliminar directiva**.</span><span class="sxs-lookup"><span data-stu-id="a338b-229">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="a338b-230">En el cuadro de diálogo de confirmación que aparece, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a338b-230">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="a338b-231">Usar Exchange Online PowerShell o PowerShell de EOP independiente para configurar directivas de datos adjuntos Caja fuerte independientes</span><span class="sxs-lookup"><span data-stu-id="a338b-231">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="a338b-232">Como se describió anteriormente, una directiva Caja fuerte datos adjuntos consiste en una directiva de datos adjuntos seguros y una regla de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="a338b-232">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="a338b-233">En PowerShell, la diferencia entre las directivas de datos adjuntos seguros y las reglas de datos adjuntos seguros es aparente.</span><span class="sxs-lookup"><span data-stu-id="a338b-233">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="a338b-234">Las directivas de datos adjuntos seguros se administran mediante los cmdlets **\* -SafeAttachmentPolicy** y se administran reglas de datos adjuntos seguros mediante los cmdlets **\* -SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="a338b-234">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="a338b-235">En PowerShell, primero se crea la directiva de datos adjuntos seguros y, a continuación, se crea la regla de datos adjuntos seguros que identifica la directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="a338b-235">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="a338b-236">En PowerShell, modifica la configuración de la directiva de datos adjuntos seguros y la regla de datos adjuntos seguros por separado.</span><span class="sxs-lookup"><span data-stu-id="a338b-236">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="a338b-237">Al quitar una directiva de datos adjuntos seguros de PowerShell, la regla de datos adjuntos seguros correspondiente no se quita automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="a338b-237">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="a338b-238">Usar PowerShell para crear directivas Caja fuerte datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="a338b-238">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="a338b-239">Crear una directiva Caja fuerte datos adjuntos en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="a338b-239">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="a338b-240">Cree la directiva de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="a338b-240">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="a338b-241">Cree la regla de datos adjuntos seguros que especifique la directiva de datos adjuntos seguros a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="a338b-241">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="a338b-242">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="a338b-242">**Notes**:</span></span>

- <span data-ttu-id="a338b-243">Puede crear una nueva regla de datos adjuntos seguros y asignarle una directiva de datos adjuntos seguros existente y no asociada.</span><span class="sxs-lookup"><span data-stu-id="a338b-243">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="a338b-244">Una regla de datos adjuntos seguros no se puede asociar a más de una directiva de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="a338b-244">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="a338b-245">Puede configurar las siguientes opciones en las nuevas directivas de datos adjuntos seguros en PowerShell que no están disponibles en el portal de Microsoft 365 Defender hasta después de crear la directiva:</span><span class="sxs-lookup"><span data-stu-id="a338b-245">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="a338b-246">Cree la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="a338b-246">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="a338b-247">Establezca la prioridad de la directiva durante la creación (_Prioridad_ ) en _\<Number\>_ el cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="a338b-247">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="a338b-248">Una nueva directiva de datos adjuntos seguros que cree en PowerShell no será visible en el portal de Microsoft 365 Defender hasta que asigne la directiva a una regla de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="a338b-248">A new safe attachment policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="a338b-249">Paso 1: Usar PowerShell para crear una directiva de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="a338b-249">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="a338b-250">Para crear una directiva de datos adjuntos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a338b-250">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="a338b-251">En este ejemplo se crea una directiva de datos adjuntos segura denominada Contoso All con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a338b-251">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="a338b-252">Bloquear los mensajes que se encuentran que contienen malware mediante el examen de documentos Caja fuerte (no estamos usando el parámetro _Action_ y el valor predeterminado es `Block` ).</span><span class="sxs-lookup"><span data-stu-id="a338b-252">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="a338b-253">El redireccionamiento está habilitado y los mensajes que se encuentran que contienen malware se envían a sec-ops@contoso.com para su análisis e investigación.</span><span class="sxs-lookup"><span data-stu-id="a338b-253">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="a338b-254">Si Caja fuerte análisis de datos adjuntos no está disponible o encuentra errores, no entregue el mensaje (no estamos usando el parámetro _ActionOnError_ y el valor predeterminado es `$true` ).</span><span class="sxs-lookup"><span data-stu-id="a338b-254">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="a338b-255">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="a338b-255">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="a338b-256">Paso 2: Usar PowerShell para crear una regla de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="a338b-256">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="a338b-257">Para crear una regla de datos adjuntos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a338b-257">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="a338b-258">En este ejemplo se crea una regla de datos adjuntos segura denominada Contoso All con las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a338b-258">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="a338b-259">La regla está asociada con la directiva de datos adjuntos seguros denominada Contoso All.</span><span class="sxs-lookup"><span data-stu-id="a338b-259">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="a338b-260">La regla se aplica a todos los destinatarios del contoso.com dominio.</span><span class="sxs-lookup"><span data-stu-id="a338b-260">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="a338b-261">Dado que no estamos usando el parámetro _Priority,_ se usa la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a338b-261">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="a338b-262">La regla está habilitada (no estamos usando el parámetro _Enabled_ y el valor predeterminado es `$true` ).</span><span class="sxs-lookup"><span data-stu-id="a338b-262">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="a338b-263">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="a338b-263">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="a338b-264">Usar PowerShell para ver directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="a338b-264">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="a338b-265">Para ver las directivas de datos adjuntos seguros existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a338b-265">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="a338b-266">En este ejemplo se devuelve una lista resumida de todas las directivas de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="a338b-266">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="a338b-267">En este ejemplo se devuelve información detallada sobre la directiva de datos adjuntos seguros denominada Ejecutivos de Contoso.</span><span class="sxs-lookup"><span data-stu-id="a338b-267">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="a338b-268">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="a338b-268">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="a338b-269">Usar PowerShell para ver reglas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="a338b-269">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="a338b-270">Para ver las reglas de datos adjuntos seguros existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a338b-270">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="a338b-271">En este ejemplo se devuelve una lista resumida de todas las reglas de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="a338b-271">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="a338b-272">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="a338b-272">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="a338b-273">En este ejemplo se devuelve información detallada sobre la regla de datos adjuntos seguros denominada Ejecutivos de Contoso.</span><span class="sxs-lookup"><span data-stu-id="a338b-273">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="a338b-274">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="a338b-274">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="a338b-275">Usar PowerShell para modificar directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="a338b-275">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="a338b-276">No puede cambiar el nombre de una directiva de datos adjuntos seguros en PowerShell (el cmdlet **Set-SafeAttachmentPolicy** no tiene ningún _parámetro Name)._</span><span class="sxs-lookup"><span data-stu-id="a338b-276">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="a338b-277">Al cambiar el nombre de una directiva Caja fuerte datos adjuntos en el portal de Microsoft 365 Defender, solo se cambia el nombre de la regla de datos _adjuntos seguros._</span><span class="sxs-lookup"><span data-stu-id="a338b-277">When you rename a Safe Attachments policy in the Microsoft 365 Defender portal, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="a338b-278">De lo contrario, la misma configuración está disponible al crear una directiva de datos adjuntos seguros, tal como se describe en step [1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span><span class="sxs-lookup"><span data-stu-id="a338b-278">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="a338b-279">Para modificar una directiva de datos adjuntos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a338b-279">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="a338b-280">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="a338b-280">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="a338b-281">Usar PowerShell para modificar reglas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="a338b-281">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="a338b-282">La única configuración que no está disponible al modificar una regla de datos adjuntos seguros en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="a338b-282">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="a338b-283">Para habilitar o deshabilitar las reglas de datos adjuntos seguros existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="a338b-283">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="a338b-284">De lo contrario, la misma configuración está disponible al crear una regla tal como se describe en el paso [2: Usar PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) para crear una regla de datos adjuntos segura anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="a338b-284">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="a338b-285">Para modificar una regla de datos adjuntos seguros, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a338b-285">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="a338b-286">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="a338b-286">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="a338b-287">Usar PowerShell para habilitar o deshabilitar reglas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="a338b-287">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="a338b-288">Habilitar o deshabilitar una regla de datos adjuntos seguros en PowerShell habilita o deshabilita toda la directiva de datos adjuntos de Caja fuerte (la regla de datos adjuntos seguros y la directiva de datos adjuntos seguros asignada).</span><span class="sxs-lookup"><span data-stu-id="a338b-288">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="a338b-289">Para habilitar o deshabilitar una regla de datos adjuntos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a338b-289">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="a338b-290">En este ejemplo se deshabilita la regla de datos adjuntos seguros denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="a338b-290">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="a338b-291">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="a338b-291">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="a338b-292">Para obtener información detallada sobre la sintaxis y los parámetros, vea [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) y [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="a338b-292">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="a338b-293">Usar PowerShell para establecer la prioridad de las reglas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="a338b-293">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="a338b-p126">El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="a338b-p126">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="a338b-299">Para establecer la prioridad de una regla de datos adjuntos seguros en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a338b-299">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="a338b-p127">En el ejemplo siguiente, la prioridad de la regla denominada "Marketing Department" se establece en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="a338b-p127">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="a338b-302">**Nota:** Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-SafeAttachmentRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="a338b-302">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="a338b-303">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="a338b-303">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="a338b-304">Usar PowerShell para quitar directivas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="a338b-304">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="a338b-305">Cuando usa PowerShell para quitar una directiva de datos adjuntos seguros, no se quita la regla de datos adjuntos seguros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a338b-305">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="a338b-306">Para quitar una directiva de datos adjuntos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a338b-306">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="a338b-307">En este ejemplo se quita la directiva de datos adjuntos seguros denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="a338b-307">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="a338b-308">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="a338b-308">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="a338b-309">Usar PowerShell para quitar reglas de datos adjuntos seguros</span><span class="sxs-lookup"><span data-stu-id="a338b-309">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="a338b-310">Al usar PowerShell para quitar una regla de datos adjuntos seguros, no se quita la directiva de datos adjuntos seguros correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a338b-310">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="a338b-311">Para quitar una regla de datos adjuntos seguros en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a338b-311">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="a338b-312">En este ejemplo se quita la regla de datos adjuntos seguros denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="a338b-312">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="a338b-313">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="a338b-313">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="a338b-314">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="a338b-314">How do you know these procedures worked?</span></span>

<span data-ttu-id="a338b-315">Para comprobar que ha creado, modificado o quitado correctamente las directivas de datos adjuntos de Caja fuerte, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a338b-315">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="a338b-316">En el portal de Microsoft 365 Defender, vaya a Correo electrónico **&** directivas de colaboración & página Directivas de amenazas de reglas sección Directivas \>  \>  Caja fuerte \>  \> **datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="a338b-316">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span> <span data-ttu-id="a338b-317">Compruebe la lista de directivas, sus **valores de** estado y sus **valores de** prioridad.</span><span class="sxs-lookup"><span data-stu-id="a338b-317">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="a338b-318">Para ver más detalles, seleccione la directiva de la lista haciendo clic en el nombre y vea los detalles en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="a338b-318">To view more details, select the policy from the list by clicking on the name, and view the details in the fly out.</span></span>

- <span data-ttu-id="a338b-319">En Exchange Online PowerShell o Exchange Online Protection PowerShell, reemplace por el nombre de la directiva o regla, ejecute el siguiente comando y compruebe \<Name\> la configuración:</span><span class="sxs-lookup"><span data-stu-id="a338b-319">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="a338b-320">Para comprobar que Caja fuerte datos adjuntos está analizando mensajes, compruebe el Defender disponible para Office 365 informes.</span><span class="sxs-lookup"><span data-stu-id="a338b-320">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="a338b-321">Para obtener más información, vea [View reports for Defender for Office 365](view-reports-for-mdo.md) and Use Explorer in the Microsoft 365 Defender [portal](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="a338b-321">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>
